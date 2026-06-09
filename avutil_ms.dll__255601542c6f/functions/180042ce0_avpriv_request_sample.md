# avpriv_request_sample

- ea: `0x180042ce0`
- end: `0x180042d36`
- name: `avpriv_request_sample`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180042ad0`
- `0x180042c40`

## string_xrefs

- `0x180042d08`: ` is not implemented. Update your FFmpeg version to the newest one from Git. If the problem still occurs, it means that your file has a feature which has not been implemented.\n`

## pseudocode

```c
__int64 avpriv_request_sample(__int64 a1, __int64 a2, ...)
{
  va_list va; // [rsp+40h] [rbp+18h] BYREF

  va_start(va, a2);
  av_vlog(a1, 24, a2, (__int64 *)va);
  av_log(
    a1,
    24,
    " is not implemented. Update your FFmpeg version to the newest one from Git. If the problem still occurs, it means th"
    "at your file has a feature which has not been implemented.\n");
  return av_log(
           a1,
           24,
           "If you want to help, upload a sample of this file to https://streams.videolan.org/upload/ and contact the ffm"
           "peg-devel mailing list. (ffmpeg-devel@ffmpeg.org)\n");
}

```

## disassembly

```asm
0x180042ce0  mov     rax, rsp
0x180042ce3  mov     [rax+10h], rdx
0x180042ce7  mov     [rax+18h], r8
0x180042ceb  mov     [rax+20h], r9
0x180042cef  push    rbx
0x180042cf0  sub     rsp, 20h
0x180042cf4  mov     r8, rdx
0x180042cf7  lea     r9, [rax+18h]
0x180042cfb  mov     edx, 18h
0x180042d00  mov     rbx, rcx
0x180042d03  call    av_vlog
0x180042d08  lea     r8, aIsNotImplement; " is not implemented. Update your FFmpeg"...
0x180042d0f  mov     edx, 18h
0x180042d14  mov     rcx, rbx
0x180042d17  call    av_log
0x180042d1c  lea     r8, aIfYouWantToHel; "If you want to help, upload a sample of"...
0x180042d23  mov     edx, 18h
0x180042d28  mov     rcx, rbx
0x180042d2b  call    av_log
0x180042d30  add     rsp, 20h
0x180042d34  pop     rbx
0x180042d35  retn
```
