# WerWaitForSystemErrorHandler

- ea: `0x140059350`
- end: `0x140059412`
- name: `WerWaitForSystemErrorHandler`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140058c20`

## callees

- `0x140059350`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400593f8`
- `ntoskrnl!ZwClose` at `0x1400593f8`
- `ntoskrnl!ZwOpenEvent` at `0x1400593ae`
- `ntoskrnl!ZwOpenEvent` at `0x1400593ae`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400593e6`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400593e6`

## string_xrefs

- `0x14005935d`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
NTSTATUS __fastcall WerWaitForSystemErrorHandler(int a1)
{
  __int64 v1; // rbx
  NTSTATUS result; // eax
  char v3; // dl
  union _LARGE_INTEGER *v4; // r8
  NTSTATUS v5; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+78h] [rbp+18h] BYREF
  __int64 v9; // [rsp+80h] [rbp+20h] BYREF

  v1 = a1;
  v6[1] = L"\\KernelObjects\\SystemErrorPortReady";
  v6[0] = 4718662;
  EventHandle = 0;
  v9 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( (_DWORD)v1 == -1 )
    {
      v3 = 1;
    }
    else
    {
      v3 = 0;
      v9 = -10000 * v1;
    }
    v4 = (union _LARGE_INTEGER *)&v9;
    if ( v3 )
      v4 = 0;
    v5 = ZwWaitForSingleObject(EventHandle, 0, v4);
    ZwClose(EventHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140059350  mov     [rsp-8+arg_0], rbx
0x140059355  push    rbp
0x140059356  mov     rbp, rsp
0x140059359  sub     rsp, 60h
0x14005935d  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x140059364  movsxd  rbx, ecx
0x140059367  mov     [rbp+var_38], rax
0x14005936b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14005936f  xor     eax, eax
0x140059371  mov     [rbp+var_40], 480046h
0x140059379  mov     [rbp+EventHandle], rax
0x14005937d  lea     rcx, [rbp+EventHandle]; EventHandle
0x140059381  mov     [rbp+arg_10], rax
0x140059385  xorps   xmm0, xmm0
0x140059388  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14005938c  mov     edx, 100001h; DesiredAccess
0x140059391  lea     rax, [rbp+var_40]
0x140059395  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14005939d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400593a1  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x1400593a9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400593ae  call    cs:__imp_ZwOpenEvent
0x1400593b5  nop     dword ptr [rax+rax+00h]
0x1400593ba  test    eax, eax
0x1400593bc  js      short loc_140059406
0x1400593be  cmp     ebx, 0FFFFFFFFh
0x1400593c1  jnz     short loc_1400593C7
0x1400593c3  mov     dl, 1
0x1400593c5  jmp     short loc_1400593D4
0x1400593c7  xor     dl, dl
0x1400593c9  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x1400593d0  mov     [rbp+arg_10], rcx
0x1400593d4  mov     rcx, [rbp+EventHandle]; Handle
0x1400593d8  lea     r8, [rbp+arg_10]
0x1400593dc  xor     eax, eax
0x1400593de  test    dl, dl
0x1400593e0  cmovnz  r8, rax; Timeout
0x1400593e4  xor     edx, edx; Alertable
0x1400593e6  call    cs:__imp_ZwWaitForSingleObject
0x1400593ed  nop     dword ptr [rax+rax+00h]
0x1400593f2  mov     rcx, [rbp+EventHandle]; Handle
0x1400593f6  mov     ebx, eax
0x1400593f8  call    cs:__imp_ZwClose
0x1400593ff  nop     dword ptr [rax+rax+00h]
0x140059404  mov     eax, ebx
0x140059406  mov     rbx, [rsp+60h+arg_0]
0x14005940b  add     rsp, 60h
0x14005940f  pop     rbp
0x140059410  retn
```
