# Microsoft::CoreUI::Support::IoCompletionPort::Create(void)

- ea: `0x18005dd04`
- end: `0x18005dd50`
- name: `?Create@IoCompletionPort@Support@CoreUI@Microsoft@@SA?AU1234@XZ`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005cc98`
- `0x1800a63d0`

## callees

- `0x18005dd04`
- `0x18008f3cc`

## import_xrefs

- `ntdll!NtCreateIoCompletion` at `0x18005dd2d`
- `ntdll!NtCreateIoCompletion` at `0x18005dd2d`

## pseudocode

```c
void **__fastcall Microsoft::CoreUI::Support::IoCompletionPort::Create(void **a1)
{
  NTSTATUS v2; // eax
  void *IoCompletionHandle; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  IoCompletionHandle = 0;
  v2 = NtCreateIoCompletion(&IoCompletionHandle, 0x1F0003u, 0, 0);
  if ( v2 < 0 )
    Cn::FailFast::ForNtStatus(v2);
  *a1 = IoCompletionHandle;
  return a1;
}

```

## disassembly

```asm
0x18005dd04  push    rbx
0x18005dd06  sub     rsp, 20h
0x18005dd0a  mov     rbx, rcx
0x18005dd0d  mov     qword ptr [rcx], 0
0x18005dd14  lea     rcx, [rsp+28h+IoCompletionHandle]; IoCompletionHandle
0x18005dd19  mov     [rsp+28h+IoCompletionHandle], 0
0x18005dd22  xor     r9d, r9d; NumberOfConcurrentThreads
0x18005dd25  xor     r8d, r8d; ObjectAttributes
0x18005dd28  mov     edx, 1F0003h; DesiredAccess
0x18005dd2d  call    cs:__imp_NtCreateIoCompletion
0x18005dd33  test    eax, eax
0x18005dd35  js      short loc_18005DD48
0x18005dd37  mov     rax, [rsp+28h+IoCompletionHandle]
0x18005dd3c  mov     [rbx], rax
0x18005dd3f  mov     rax, rbx
0x18005dd42  add     rsp, 20h
0x18005dd46  pop     rbx
0x18005dd47  retn
0x18005dd48  mov     ecx, eax; int
0x18005dd4a  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
```
