# AslRegistryGetKey

- ea: `0x18004c404`
- end: `0x18004c4f5`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047a10`

## callees

- `0x18004c020`
- `0x18004c31c`
- `0x18004c404`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18004c49d`
- `ntdll!ZwOpenKey` at `0x18004c49d`
- `ntdll!RtlFreeHeap` at `0x18004c4e4`
- `ntdll!RtlFreeHeap` at `0x18004c4e4`

## string_xrefs

- `0x18004c441`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x18004c453`: `AslRegistryGetKey`
- `0x18004c4b0`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  PVOID P[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v4 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "AslRegistryBuildMachinePath failed %x for %ws";
    v7 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v7, v6, v4, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v4 != -1073741772 )
  {
    v6 = "NtOpenKey failed %x for %ws";
    v7 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v5;
}

```

## disassembly

```asm
0x18004c404  push    rbp
0x18004c406  push    rbx
0x18004c407  push    rsi
0x18004c408  push    rdi
0x18004c409  mov     rbp, rsp
0x18004c40c  sub     rsp, 78h
0x18004c410  xorps   xmm0, xmm0
0x18004c413  xor     eax, eax
0x18004c415  mov     [rcx], rax
0x18004c418  mov     rsi, rcx
0x18004c41b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004c41f  lea     rcx, [rbp+P]; Destination
0x18004c423  mov     [rbp+KeyHandle], rax
0x18004c427  mov     rdi, rdx
0x18004c42a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004c42e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18004c432  movups  xmmword ptr [rbp+P], xmm0
0x18004c436  call    AslRegistryBuildMachinePath
0x18004c43b  mov     ebx, eax
0x18004c43d  test    eax, eax
0x18004c43f  jns     short loc_18004C46A
0x18004c441  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x18004c448  mov     r8d, 6B6h
0x18004c44e  mov     [rsp+78h+var_50], rdi
0x18004c453  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x18004c45a  mov     ecx, 1
0x18004c45f  mov     [rsp+78h+var_58], eax
0x18004c463  call    AslLogCallPrintf
0x18004c468  jmp     short loc_18004C4CC
0x18004c46a  lea     rax, [rbp+P]
0x18004c46e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004c475  xorps   xmm0, xmm0
0x18004c478  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004c47c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004c480  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18004c488  mov     edx, 1; DesiredAccess
0x18004c48d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004c494  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c498  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004c49d  call    cs:__imp_ZwOpenKey
0x18004c4a3  mov     ebx, eax
0x18004c4a5  test    eax, eax
0x18004c4a7  jns     short loc_18004C4BF
0x18004c4a9  cmp     eax, 0C0000034h
0x18004c4ae  jz      short loc_18004C4CC
0x18004c4b0  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x18004c4b7  mov     r8d, 6E1h
0x18004c4bd  jmp     short loc_18004C44E
0x18004c4bf  mov     rax, [rbp+KeyHandle]
0x18004c4c3  xor     ebx, ebx
0x18004c4c5  mov     [rsi], rax
0x18004c4c8  mov     [rbp+KeyHandle], rbx
0x18004c4cc  mov     r8, [rbp+P+8]; P
0x18004c4d0  test    r8, r8
0x18004c4d3  jz      short loc_18004C4EA
0x18004c4d5  mov     rcx, gs:60h
0x18004c4de  xor     edx, edx; Flags
0x18004c4e0  mov     rcx, [rcx+30h]; HeapHandle
0x18004c4e4  call    cs:__imp_RtlFreeHeap
0x18004c4ea  mov     eax, ebx
0x18004c4ec  add     rsp, 78h
0x18004c4f0  pop     rdi
0x18004c4f1  pop     rsi
0x18004c4f2  pop     rbx
0x18004c4f3  pop     rbp
0x18004c4f4  retn
```
