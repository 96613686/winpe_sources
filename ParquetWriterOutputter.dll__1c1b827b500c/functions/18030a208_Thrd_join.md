# _Thrd_join

- ea: `0x18030a208`
- end: `0x18030a26d`
- name: `_Thrd_join`
- size: `101`
- prototype: `int __cdecl(_Thrd_t *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800dd910`

## callees

- `0x18030a208`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18030a24c`
- `KERNEL32!CloseHandle` at `0x18030a24c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18030a221`
- `KERNEL32!WaitForSingleObjectEx` at `0x18030a221`
- `KERNEL32!GetExitCodeThread` at `0x18030a234`
- `KERNEL32!GetExitCodeThread` at `0x18030a234`

## pseudocode

```c
int __cdecl Thrd_join(_Thrd_t *a1, int *a2)
{
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  if ( WaitForSingleObjectEx(a1->_Hnd, 0xFFFFFFFF, 0) == -1 || !GetExitCodeThread(a1->_Hnd, &ExitCode) )
    return 4;
  if ( a2 )
    *a2 = ExitCode;
  return !CloseHandle(a1->_Hnd) ? 4 : 0;
}

```

## disassembly

```asm
0x18030a208  mov     [rsp+arg_8], rbx
0x18030a20d  push    rdi
0x18030a20e  sub     rsp, 20h
0x18030a212  mov     rbx, rdx
0x18030a215  mov     rdi, rcx
0x18030a218  mov     rcx, [rcx]; hHandle
0x18030a21b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18030a21e  xor     r8d, r8d; bAlertable
0x18030a221  call    cs:__imp_WaitForSingleObjectEx
0x18030a227  cmp     eax, 0FFFFFFFFh
0x18030a22a  jz      short loc_18030A25D
0x18030a22c  mov     rcx, [rdi]; hThread
0x18030a22f  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x18030a234  call    cs:__imp_GetExitCodeThread
0x18030a23a  test    eax, eax
0x18030a23c  jz      short loc_18030A25D
0x18030a23e  test    rbx, rbx
0x18030a241  jz      short loc_18030A249
0x18030a243  mov     eax, [rsp+28h+ExitCode]
0x18030a247  mov     [rbx], eax
0x18030a249  mov     rcx, [rdi]; hObject
0x18030a24c  call    cs:__imp_CloseHandle
0x18030a252  neg     eax
0x18030a254  sbb     eax, eax
0x18030a256  not     eax
0x18030a258  and     eax, 4
0x18030a25b  jmp     short loc_18030A262
0x18030a25d  mov     eax, 4
0x18030a262  mov     rbx, [rsp+28h+arg_8]
0x18030a267  add     rsp, 20h
0x18030a26b  pop     rdi
0x18030a26c  retn
```
