# avpriv_report_missing_feature

- ea: `0x180042c90`
- end: `0x180042cd2`
- name: `avpriv_report_missing_feature`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180042ad0`
- `0x180042c40`

## string_xrefs

- `0x180042cb8`: ` is not implemented. Update your FFmpeg version to the newest one from Git. If the problem still occurs, it means that your file has a feature which has not been implemented.\n`

## pseudocode

```c
__int64 avpriv_report_missing_feature(__int64 a1, __int64 a2, ...)
{
  va_list va; // [rsp+40h] [rbp+18h] BYREF

  va_start(va, a2);
  av_vlog(a1, 24, a2, (__int64 *)va);
  return av_log(
           a1,
           24,
           " is not implemented. Update your FFmpeg version to the newest one from Git. If the problem still occurs, it m"
           "eans that your file has a feature which has not been implemented.\n");
}

```

## disassembly

```asm
0x180042c90  mov     rax, rsp
0x180042c93  mov     [rax+10h], rdx
0x180042c97  mov     [rax+18h], r8
0x180042c9b  mov     [rax+20h], r9
0x180042c9f  push    rbx
0x180042ca0  sub     rsp, 20h
0x180042ca4  mov     r8, rdx
0x180042ca7  lea     r9, [rax+18h]
0x180042cab  mov     edx, 18h
0x180042cb0  mov     rbx, rcx
0x180042cb3  call    av_vlog
0x180042cb8  lea     r8, aIsNotImplement; " is not implemented. Update your FFmpeg"...
0x180042cbf  mov     edx, 18h
0x180042cc4  mov     rcx, rbx
0x180042cc7  call    av_log
0x180042ccc  add     rsp, 20h
0x180042cd0  pop     rbx
0x180042cd1  retn
```
