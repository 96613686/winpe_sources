# SafeServiceHandle::SafeServiceHandle(SafeScmHandle &,wchar_t const *,ulong)

- ea: `0x1800255dc`
- end: `0x180025619`
- name: `??0SafeServiceHandle@@QEAA@AEAVSafeScmHandle@@PEB_WK@Z`
- size: `61`
- prototype: `SafeServiceHandle *__fastcall(SafeServiceHandle *this, SC_HANDLE *, const wchar_t *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180025680`

## callees

- `0x18000d384`
- `0x1800255dc`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800255fc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800255fc`

## pseudocode

```c
SafeServiceHandle *__fastcall SafeServiceHandle::SafeServiceHandle(
        SafeServiceHandle *this,
        SC_HANDLE *a2,
        const wchar_t *a3,
        DWORD a4)
{
  SC_HANDLE v5; // rax

  v5 = OpenServiceW(*a2, a3, a4);
  if ( !v5 )
    Win32Exception::ThrowLastError();
  *(_QWORD *)this = v5;
  return this;
}

```

## disassembly

```asm
0x1800255dc  push    rbx
0x1800255de  sub     rsp, 30h
0x1800255e2  mov     rax, rdx
0x1800255e5  mov     [rsp+38h+var_18], rcx
0x1800255ea  mov     r10d, r9d
0x1800255ed  mov     rbx, rcx
0x1800255f0  mov     r9, r8
0x1800255f3  mov     r8d, r10d; dwDesiredAccess
0x1800255f6  mov     rdx, r9; lpServiceName
0x1800255f9  mov     rcx, [rax]; hSCManager
0x1800255fc  call    cs:__imp_OpenServiceW
0x180025602  test    rax, rax
0x180025605  jnz     short loc_18002560D
0x180025607  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x18002560d  mov     [rbx], rax
0x180025610  mov     rax, rbx
0x180025613  add     rsp, 30h
0x180025617  pop     rbx
0x180025618  retn
```
