# StartAddress

- ea: `0x14001e090`
- end: `0x14001e0fc`
- name: `StartAddress`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD *Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000aca0`
- `0x14001dad0`
- `0x14001e090`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14001e0b9`
- `KERNEL32!GetCurrentThread` at `0x14001e0b9`
- `KERNEL32!SetThreadPriority` at `0x14001e0c4`
- `KERNEL32!SetThreadPriority` at `0x14001e0c4`
- `KERNEL32!FreeLibraryAndExitThread` at `0x14001e0ea`
- `KERNEL32!FreeLibraryAndExitThread` at `0x14001e0ea`

## pseudocode

```c
__int64 __fastcall StartAddress(_QWORD *Parameter)
{
  __int64 v1; // r14
  __int64 (__fastcall *v3)(__int64); // rbp
  HMODULE v4; // rdi
  int v5; // esi
  HANDLE CurrentThread; // rax
  __int64 result; // rax

  v1 = Parameter[2];
  v3 = (__int64 (__fastcall *)(__int64))Parameter[1];
  v4 = (HMODULE)Parameter[3];
  Parameter[3] = 0;
  v5 = *((_DWORD *)Parameter + 8);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v5);
  }
  sub_14001DAD0(Parameter);
  result = v3(v1);
  if ( v4 )
    FreeLibraryAndExitThread(v4, result);
  return result;
}

```

## disassembly

```asm
0x14001e090  push    rbx
0x14001e092  push    rbp
0x14001e093  push    rsi
0x14001e094  push    rdi
0x14001e095  push    r14
0x14001e097  sub     rsp, 20h
0x14001e09b  mov     r14, [rcx+10h]
0x14001e09f  mov     rbx, rcx
0x14001e0a2  mov     rbp, [rcx+8]
0x14001e0a6  mov     rdi, [rcx+18h]
0x14001e0aa  mov     qword ptr [rcx+18h], 0
0x14001e0b2  mov     esi, [rcx+20h]
0x14001e0b5  test    esi, esi
0x14001e0b7  jz      short loc_14001E0CA
0x14001e0b9  call    cs:GetCurrentThread
0x14001e0bf  mov     rcx, rax; hThread
0x14001e0c2  mov     edx, esi; nPriority
0x14001e0c4  call    cs:SetThreadPriority
0x14001e0ca  mov     rcx, rbx
0x14001e0cd  call    sub_14001DAD0
0x14001e0d2  mov     rcx, rbp
0x14001e0d5  call    cs:__guard_check_icall_fptr
0x14001e0db  mov     rcx, r14
0x14001e0de  call    rbp
0x14001e0e0  test    rdi, rdi
0x14001e0e3  jz      short loc_14001E0F1
0x14001e0e5  mov     edx, eax; dwExitCode
0x14001e0e7  mov     rcx, rdi; hLibModule
0x14001e0ea  call    cs:FreeLibraryAndExitThread
0x14001e0f1  add     rsp, 20h
0x14001e0f5  pop     r14
0x14001e0f7  pop     rdi
0x14001e0f8  pop     rsi
0x14001e0f9  pop     rbp
0x14001e0fa  pop     rbx
0x14001e0fb  retn
```
