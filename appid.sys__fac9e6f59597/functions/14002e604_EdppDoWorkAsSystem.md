# EdppDoWorkAsSystem

- ea: `0x14002e604`
- end: `0x14002e6e5`
- name: `EdppDoWorkAsSystem`
- size: `225`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002ba70`
- `0x14002bb30`
- `0x14002c090`

## callees

- `0x14002e604`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x14002e698`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002e698`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e67d`
- `ntoskrnl!PsCreateSystemThread` at `0x14002e67d`
- `ntoskrnl!ZwClose` at `0x14002e6c5`
- `ntoskrnl!ZwClose` at `0x14002e6c5`

## pseudocode

```c
__int64 __fastcall EdppDoWorkAsSystem(__int64 a1)
{
  NTSTATUS v1; // ebx
  __int64 v3; // [rsp+40h] [rbp-40h] BYREF
  __int64 v4; // [rsp+48h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+90h] [rbp+10h] BYREF

  v3 = a1;
  v4 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, &ObjectAttributes, 0, 0, (PKSTART_ROUTINE)EdppThreadStart, &v3);
  if ( v1 >= 0 )
  {
    v1 = ZwWaitForSingleObject(ThreadHandle, 0, 0);
    if ( v1 >= 0 )
    {
      if ( v1 )
        v1 = -1073739509;
      if ( (int)v4 < 0 )
        v1 = v4;
    }
  }
  if ( ThreadHandle )
    ZwClose(ThreadHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14002e604  mov     r11, rsp
0x14002e607  mov     [r11+10h], rbx
0x14002e60b  push    rbp
0x14002e60c  mov     rbp, rsp
0x14002e60f  sub     rsp, 80h
0x14002e616  lea     rax, [rbp+var_40]
0x14002e61a  mov     [rbp+var_40], rcx
0x14002e61e  mov     [r11-58h], rax
0x14002e622  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002e626  lea     rax, EdppThreadStart
0x14002e62d  mov     [rbp+var_38], 0
0x14002e635  xorps   xmm0, xmm0
0x14002e638  mov     [r11-60h], rax
0x14002e63c  xor     r9d, r9d; ProcessHandle
0x14002e63f  mov     qword ptr [r11-68h], 0
0x14002e647  mov     edx, 1FFFFFh; DesiredAccess
0x14002e64c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002e654  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002e658  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14002e660  mov     [rbp+ThreadHandle], 0
0x14002e668  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002e670  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14002e678  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002e67d  call    cs:__imp_PsCreateSystemThread
0x14002e684  nop     dword ptr [rax+rax+00h]
0x14002e689  mov     ebx, eax
0x14002e68b  test    eax, eax
0x14002e68d  js      short loc_14002E6BC
0x14002e68f  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e693  xor     r8d, r8d; Timeout
0x14002e696  xor     edx, edx; Alertable
0x14002e698  call    cs:__imp_ZwWaitForSingleObject
0x14002e69f  nop     dword ptr [rax+rax+00h]
0x14002e6a4  mov     ebx, eax
0x14002e6a6  test    eax, eax
0x14002e6a8  js      short loc_14002E6BC
0x14002e6aa  test    ebx, ebx
0x14002e6ac  mov     eax, 0C000090Bh
0x14002e6b1  cmovnz  ebx, eax
0x14002e6b4  mov     eax, dword ptr [rbp+var_38]
0x14002e6b7  test    eax, eax
0x14002e6b9  cmovs   ebx, eax
0x14002e6bc  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002e6c0  test    rcx, rcx
0x14002e6c3  jz      short loc_14002E6D1
0x14002e6c5  call    cs:__imp_ZwClose
0x14002e6cc  nop     dword ptr [rax+rax+00h]
0x14002e6d1  mov     eax, ebx
0x14002e6d3  mov     rbx, [rsp+80h+arg_8]
0x14002e6db  add     rsp, 80h
0x14002e6e2  pop     rbp
0x14002e6e3  retn
```
