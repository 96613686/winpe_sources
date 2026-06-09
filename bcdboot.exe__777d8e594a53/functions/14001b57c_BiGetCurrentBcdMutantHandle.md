# BiGetCurrentBcdMutantHandle

- ea: `0x14001b57c`
- end: `0x14001b644`
- name: `BiGetCurrentBcdMutantHandle`
- size: `200`
- prototype: `NTSTATUS __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ae94`

## callees

- `0x14001b57c`

## import_xrefs

- `ntdll!ZwOpenMutant` at `0x14001b5e6`
- `ntdll!ZwOpenMutant` at `0x14001b5e6`
- `ntdll!ZwClose` at `0x14001b627`
- `ntdll!ZwClose` at `0x14001b627`

## pseudocode

```c
NTSTATUS __fastcall BiGetCurrentBcdMutantHandle(_QWORD *a1)
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *MutantHandle; // [rsp+68h] [rbp+18h] BYREF

  MutantHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( BcdMutantHandle )
  {
    *a1 = BcdMutantHandle;
  }
  else
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"8:";
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenMutant(&MutantHandle, 0x100000u, &ObjectAttributes);
    if ( result == -1073741772 )
    {
      _InterlockedCompareExchange64((volatile signed __int64 *)&BcdMutantHandle, -1, 0);
      *a1 = BcdMutantHandle;
    }
    else
    {
      if ( result < 0 )
        return result;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&BcdMutantHandle, (signed __int64)MutantHandle, 0) )
        ZwClose(MutantHandle);
      *a1 = BcdMutantHandle;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001b57c  mov     [rsp-8+arg_0], rbx
0x14001b581  push    rbp
0x14001b582  mov     rbp, rsp
0x14001b585  sub     rsp, 50h
0x14001b589  xor     eax, eax
0x14001b58b  mov     [rbp+MutantHandle], 0
0x14001b593  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x14001b596  mov     rbx, rcx
0x14001b599  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x14001b59c  mov     rax, cs:BcdMutantHandle
0x14001b5a3  test    rax, rax
0x14001b5a6  jz      short loc_14001B5B0
0x14001b5a8  mov     [rcx], rax
0x14001b5ab  jmp     loc_14001B637
0x14001b5b0  lea     rax, BcdSyncMutantName; "8:"
0x14001b5b7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001b5be  xorps   xmm0, xmm0
0x14001b5c1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001b5c5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001b5c9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001b5d1  mov     edx, 100000h; DesiredAccess
0x14001b5d6  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001b5dd  lea     rcx, [rbp+MutantHandle]; MutantHandle
0x14001b5e1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001b5e6  call    cs:__imp_ZwOpenMutant
0x14001b5ec  cmp     eax, 0C0000034h
0x14001b5f1  jnz     short loc_14001B60E
0x14001b5f3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001b5f7  xor     eax, eax
0x14001b5f9  lock cmpxchg cs:BcdMutantHandle, rcx
0x14001b602  mov     rcx, cs:BcdMutantHandle
0x14001b609  mov     [rbx], rcx
0x14001b60c  jmp     short loc_14001B637
0x14001b60e  test    eax, eax
0x14001b610  js      short loc_14001B639
0x14001b612  mov     rcx, [rbp+MutantHandle]
0x14001b616  xor     eax, eax
0x14001b618  lock cmpxchg cs:BcdMutantHandle, rcx
0x14001b621  jz      short loc_14001B62D
0x14001b623  mov     rcx, [rbp+MutantHandle]; Handle
0x14001b627  call    cs:__imp_ZwClose
0x14001b62d  mov     rax, cs:BcdMutantHandle
0x14001b634  mov     [rbx], rax
0x14001b637  xor     eax, eax
0x14001b639  mov     rbx, [rsp+50h+arg_0]
0x14001b63e  add     rsp, 50h
0x14001b642  pop     rbp
0x14001b643  retn
```
