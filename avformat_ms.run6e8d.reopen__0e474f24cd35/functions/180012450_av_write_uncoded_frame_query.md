# av_write_uncoded_frame_query

- ea: `0x180012450`
- end: `0x1800124b5`
- name: `av_write_uncoded_frame_query`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180012450`
- `0x18001bb58`
- `0x18001bdc6`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall av_write_uncoded_frame_query(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v3)(__int64, __int64, _QWORD, __int64); // rax

  v2 = *(_QWORD *)(a1 + 16);
  if ( !v2 )
  {
    av_log(0, 0, "Assertion %s failed at %s:%d\n", "of", "C:/__w/1/s/FFmpegInterop/ffmpeg/libavformat/mux.c", 1431);
    abort();
  }
  v3 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(v2 + 128);
  if ( v3 )
    return v3(a1, a2, 0, 1);
  else
    return 4294967256LL;
}

```

## disassembly

```asm
0x180012450  sub     rsp, 38h
0x180012454  mov     rax, [rcx+10h]
0x180012458  test    rax, rax
0x18001245b  jz      short loc_180012484
0x18001245d  mov     rax, [rax+80h]
0x180012464  test    rax, rax
0x180012467  jnz     short loc_180012470
0x180012469  mov     eax, 0FFFFFFD8h
0x18001246e  jmp     short loc_18001247F
0x180012470  mov     r9d, 1
0x180012476  xor     r8d, r8d
0x180012479  call    cs:__guard_dispatch_icall_fptr
0x18001247f  add     rsp, 38h
0x180012483  retn
0x180012484  lea     rax, aCW1SFfmpeginte_3; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavfo"...
0x18001248b  mov     [rsp+38h+var_10], 597h
0x180012493  lea     r9, aOf; "of"
0x18001249a  mov     [rsp+38h+var_18], rax
0x18001249f  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x1800124a6  xor     edx, edx
0x1800124a8  xor     ecx, ecx
0x1800124aa  call    av_log
0x1800124af  call    abort
```
