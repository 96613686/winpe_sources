# _Thrd_join

- ea: `0x14001f0dc`
- end: `0x14001f141`
- name: `_Thrd_join`
- size: `101`
- prototype: `int __cdecl(_Thrd_t *__struct_ptr, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140096bf0`
- `0x1400af54c`
- `0x140101810`

## callees

- `0x14001f0dc`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x14001f0f5`
- `KERNEL32!WaitForSingleObjectEx` at `0x14001f0f5`
- `KERNEL32!CloseHandle` at `0x14001f120`
- `KERNEL32!CloseHandle` at `0x14001f120`
- `KERNEL32!GetExitCodeThread` at `0x14001f10d`
- `KERNEL32!GetExitCodeThread` at `0x14001f10d`

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
0x14001f0dc  mov     [rsp+arg_8], rbx
0x14001f0e1  push    rdi
0x14001f0e2  sub     rsp, 20h
0x14001f0e6  mov     rdi, [rcx]
0x14001f0e9  mov     rbx, rdx
0x14001f0ec  mov     rcx, rdi; hHandle
0x14001f0ef  xor     r8d, r8d; bAlertable
0x14001f0f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001f0f5  call    cs:__imp_WaitForSingleObjectEx
0x14001f0fb  cmp     eax, 0FFFFFFFFh
0x14001f0fe  jz      short loc_14001F131
0x14001f100  test    rbx, rbx
0x14001f103  jz      short loc_14001F11D
0x14001f105  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x14001f10a  mov     rcx, rdi; hThread
0x14001f10d  call    cs:__imp_GetExitCodeThread
0x14001f113  test    eax, eax
0x14001f115  jz      short loc_14001F131
0x14001f117  mov     eax, [rsp+28h+ExitCode]
0x14001f11b  mov     [rbx], eax
0x14001f11d  mov     rcx, rdi; hObject
0x14001f120  call    cs:__imp_CloseHandle
0x14001f126  neg     eax
0x14001f128  sbb     eax, eax
0x14001f12a  not     eax
0x14001f12c  and     eax, 4
0x14001f12f  jmp     short loc_14001F136
0x14001f131  mov     eax, 4
0x14001f136  mov     rbx, [rsp+28h+arg_8]
0x14001f13b  add     rsp, 20h
0x14001f13f  pop     rdi
0x14001f140  retn
```
