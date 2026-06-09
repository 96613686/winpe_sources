# WaitForWerSvc(ulong)

- ea: `0x180029810`
- end: `0x1800298c9`
- name: `?WaitForWerSvc@@YAJK@Z`
- size: `185`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001dc54`

## callees

- `0x180029810`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800298aa`
- `ntdll!NtWaitForSingleObject` at `0x1800298aa`
- `ntdll!NtOpenEvent` at `0x180029878`
- `ntdll!NtOpenEvent` at `0x180029878`
- `ntdll!NtClose` at `0x1800298b6`
- `ntdll!NtClose` at `0x1800298b6`

## string_xrefs

- `0x18002981d`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
NTSTATUS __fastcall WaitForWerSvc(int a1)
{
  __int64 v1; // rbx
  NTSTATUS result; // eax
  char v3; // dl
  union _LARGE_INTEGER *v4; // r8
  NTSTATUS v5; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+78h] [rbp+18h] BYREF
  __int64 v9; // [rsp+80h] [rbp+20h] BYREF

  v1 = a1;
  v6[1] = L"\\KernelObjects\\SystemErrorPortReady";
  v6[0] = 4718662;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  EventHandle = 0;
  v9 = 0;
  ObjectAttributes.RootDirectory = 0;
  result = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
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
    v5 = NtWaitForSingleObject(EventHandle, 0, v4);
    NtClose(EventHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180029810  mov     [rsp-8+arg_0], rbx
0x180029815  push    rbp
0x180029816  mov     rbp, rsp
0x180029819  sub     rsp, 60h
0x18002981d  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x180029824  movsxd  rbx, ecx
0x180029827  mov     [rbp+var_38], rax
0x18002982b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002982f  lea     rax, [rbp+var_40]
0x180029833  mov     [rbp+var_40], 480046h
0x18002983b  xorps   xmm0, xmm0
0x18002983e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180029842  mov     edx, 100001h; DesiredAccess
0x180029847  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002984f  lea     rcx, [rbp+EventHandle]; EventHandle
0x180029853  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18002985b  mov     [rbp+EventHandle], 0
0x180029863  mov     [rbp+arg_10], 0
0x18002986b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180029873  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180029878  call    cs:__imp_NtOpenEvent
0x18002987e  test    eax, eax
0x180029880  js      short loc_1800298BE
0x180029882  cmp     ebx, 0FFFFFFFFh
0x180029885  jnz     short loc_18002988B
0x180029887  mov     dl, 1
0x180029889  jmp     short loc_180029898
0x18002988b  xor     dl, dl
0x18002988d  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x180029894  mov     [rbp+arg_10], rcx
0x180029898  mov     rcx, [rbp+EventHandle]; Handle
0x18002989c  lea     r8, [rbp+arg_10]
0x1800298a0  xor     eax, eax
0x1800298a2  test    dl, dl
0x1800298a4  cmovnz  r8, rax; Timeout
0x1800298a8  xor     edx, edx; Alertable
0x1800298aa  call    cs:__imp_NtWaitForSingleObject
0x1800298b0  mov     rcx, [rbp+EventHandle]; Handle
0x1800298b4  mov     ebx, eax
0x1800298b6  call    cs:__imp_NtClose
0x1800298bc  mov     eax, ebx
0x1800298be  mov     rbx, [rsp+60h+arg_0]
0x1800298c3  add     rsp, 60h
0x1800298c7  pop     rbp
0x1800298c8  retn
```
