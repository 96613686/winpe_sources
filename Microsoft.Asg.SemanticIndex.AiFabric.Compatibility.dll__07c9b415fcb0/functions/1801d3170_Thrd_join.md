# _Thrd_join

- ea: `0x1801d3170`
- end: `0x1801d31d5`
- name: `_Thrd_join`
- size: `101`
- prototype: `int __cdecl(_Thrd_t *__struct_ptr, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180046f00`
- `0x180229ef0`

## callees

- `0x1801d3170`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801d31b4`
- `KERNEL32!CloseHandle` at `0x1801d31b4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1801d3189`
- `KERNEL32!WaitForSingleObjectEx` at `0x1801d3189`
- `KERNEL32!GetExitCodeThread` at `0x1801d31a1`
- `KERNEL32!GetExitCodeThread` at `0x1801d31a1`

## pseudocode

```c
int __cdecl Thrd_join(_Thrd_t *a1, int *a2)
{
  void *Hnd; // rdi
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  Hnd = a1->_Hnd;
  if ( WaitForSingleObjectEx(a1->_Hnd, 0xFFFFFFFF, 0) != -1 )
  {
    if ( !a2 )
      return !CloseHandle(Hnd) ? 4 : 0;
    if ( GetExitCodeThread(Hnd, &ExitCode) )
    {
      *a2 = ExitCode;
      return !CloseHandle(Hnd) ? 4 : 0;
    }
  }
  return 4;
}

```

## disassembly

```asm
0x1801d3170  mov     [rsp+arg_8], rbx
0x1801d3175  push    rdi
0x1801d3176  sub     rsp, 20h
0x1801d317a  mov     rdi, [rcx]
0x1801d317d  mov     rbx, rdx
0x1801d3180  mov     rcx, rdi; hHandle
0x1801d3183  xor     r8d, r8d; bAlertable
0x1801d3186  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801d3189  call    cs:__imp_WaitForSingleObjectEx
0x1801d318f  cmp     eax, 0FFFFFFFFh
0x1801d3192  jz      short loc_1801D31C5
0x1801d3194  test    rbx, rbx
0x1801d3197  jz      short loc_1801D31B1
0x1801d3199  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1801d319e  mov     rcx, rdi; hThread
0x1801d31a1  call    cs:__imp_GetExitCodeThread
0x1801d31a7  test    eax, eax
0x1801d31a9  jz      short loc_1801D31C5
0x1801d31ab  mov     eax, [rsp+28h+ExitCode]
0x1801d31af  mov     [rbx], eax
0x1801d31b1  mov     rcx, rdi; hObject
0x1801d31b4  call    cs:__imp_CloseHandle
0x1801d31ba  neg     eax
0x1801d31bc  sbb     eax, eax
0x1801d31be  not     eax
0x1801d31c0  and     eax, 4
0x1801d31c3  jmp     short loc_1801D31CA
0x1801d31c5  mov     eax, 4
0x1801d31ca  mov     rbx, [rsp+28h+arg_8]
0x1801d31cf  add     rsp, 20h
0x1801d31d3  pop     rdi
0x1801d31d4  retn
```
