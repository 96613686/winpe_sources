# av_hwframe_map

- ea: `0x18003f740`
- end: `0x18003f8e2`
- name: `av_hwframe_map`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003f600`

## callees

- `0x18003ba10`
- `0x18003bd20`
- `0x18003f740`
- `0x180042ad0`
- `0x180078c2c`
- `0x18007a900`

## string_xrefs

- `0x18003f7b7`: `Invalid mapping found when attempting unmap.\n`

## pseudocode

```c
__int64 __fastcall av_hwframe_map(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r9
  __int64 v5; // rsi
  unsigned int v7; // r14d
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 result; // rax
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(__int64, __int64, __int64, _QWORD); // rax
  unsigned int v16; // edi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(__int64, __int64, __int64, _QWORD); // rax

  v3 = *(_QWORD *)(a2 + 328);
  v5 = *(_QWORD *)(a1 + 328);
  v7 = *(_DWORD *)(a1 + 116);
  if ( !v3 )
    goto LABEL_15;
  if ( v5 )
  {
    if ( (v9 = *(_QWORD *)(v3 + 8), v10 = *(_QWORD *)(v5 + 8), v9 == v10)
      && __PAIR64__(*(_DWORD *)(a2 + 116), v7) == *(_QWORD *)(v10 + 60)
      || (v11 = *(_QWORD *)(v9 + 96)) != 0 && *(_QWORD *)(v11 + 8) == v10 )
    {
      v12 = *(_QWORD *)(a2 + 184);
      if ( v12 )
        return av_frame_replace(a1, **(_QWORD **)(v12 + 8));
      av_log(v9, 16, "Invalid mapping found when attempting unmap.\n");
      return 4294967274LL;
    }
  }
  v14 = *(_QWORD *)(v3 + 8);
  if ( *(_DWORD *)(v14 + 60) != *(_DWORD *)(a2 + 116) )
    goto LABEL_15;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)(v14 + 80) + 144LL);
  if ( !v15 )
    goto LABEL_15;
  result = v15(v14, a1, a2, a3);
  v16 = result;
  if ( (int)result >= 0 )
  {
LABEL_13:
    _mm_lfence();
    return result;
  }
  if ( (_DWORD)result == -40 )
  {
LABEL_15:
    v17 = *(_QWORD *)(a1 + 328);
    if ( !v17 )
      return 4294967256LL;
    v18 = *(_QWORD *)(v17 + 8);
    if ( *(_DWORD *)(v18 + 60) != *(_DWORD *)(a1 + 116) )
      return 4294967256LL;
    v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)(v18 + 80) + 136LL);
    if ( !v19 )
      return 4294967256LL;
    result = v19(v18, a1, a2, a3);
    v16 = result;
    if ( (int)result >= 0 )
      goto LABEL_13;
    if ( (_DWORD)result == -40 )
      return 4294967256LL;
  }
  if ( v5 && v5 != *(_QWORD *)(a1 + 328) )
  {
    av_log(
      0,
      0,
      "Assertion %s failed at %s:%d\n",
      "orig_dst_frames == ((void *)0) || orig_dst_frames == dst->hw_frames_ctx",
      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/hwcontext.c",
      858);
    abort();
  }
  *(_QWORD *)(a1 + 328) = 0;
  av_frame_unref(a1);
  result = v16;
  *(_QWORD *)(a1 + 328) = v5;
  *(_DWORD *)(a1 + 116) = v7;
  return result;
}

```

## disassembly

```asm
0x18003f740  mov     [rsp+arg_0], rbx
0x18003f745  mov     [rsp+arg_8], rbp
0x18003f74a  mov     [rsp+arg_10], rsi
0x18003f74f  push    rdi
0x18003f750  push    r14
0x18003f752  push    r15
0x18003f754  sub     rsp, 30h
0x18003f758  mov     r9, [rdx+148h]
0x18003f75f  mov     r15d, r8d
0x18003f762  mov     rsi, [rcx+148h]
0x18003f769  mov     rbp, rdx
0x18003f76c  mov     r14d, [rcx+74h]
0x18003f770  mov     rbx, rcx
0x18003f773  test    r9, r9
0x18003f776  jz      loc_18003F821
0x18003f77c  test    rsi, rsi
0x18003f77f  jz      short loc_18003F7E6
0x18003f781  mov     rcx, [r9+8]
0x18003f785  mov     rdx, [rsi+8]
0x18003f789  cmp     rcx, rdx
0x18003f78c  jnz     short loc_18003F79C
0x18003f78e  mov     eax, [rdx+40h]
0x18003f791  cmp     [rbp+74h], eax
0x18003f794  jnz     short loc_18003F79C
0x18003f796  cmp     r14d, [rdx+3Ch]
0x18003f79a  jz      short loc_18003F7AB
0x18003f79c  mov     rax, [rcx+60h]
0x18003f7a0  test    rax, rax
0x18003f7a3  jz      short loc_18003F7E6
0x18003f7a5  cmp     [rax+8], rdx
0x18003f7a9  jnz     short loc_18003F7E6
0x18003f7ab  mov     rdx, [rbp+0B8h]
0x18003f7b2  test    rdx, rdx
0x18003f7b5  jnz     short loc_18003F7D2
0x18003f7b7  lea     r8, aInvalidMapping; "Invalid mapping found when attempting u"...
0x18003f7be  mov     edx, 10h
0x18003f7c3  call    av_log
0x18003f7c8  mov     eax, 0FFFFFFEAh
0x18003f7cd  jmp     loc_18003F898
0x18003f7d2  mov     rdx, [rdx+8]
0x18003f7d6  mov     rcx, rbx
0x18003f7d9  mov     rdx, [rdx]
0x18003f7dc  call    av_frame_replace
0x18003f7e1  jmp     loc_18003F898
0x18003f7e6  mov     rcx, [r9+8]
0x18003f7ea  mov     eax, [rbp+74h]
0x18003f7ed  cmp     [rcx+3Ch], eax
0x18003f7f0  jnz     short loc_18003F821
0x18003f7f2  mov     rax, [rcx+50h]
0x18003f7f6  mov     rax, [rax+90h]
0x18003f7fd  test    rax, rax
0x18003f800  jz      short loc_18003F821
0x18003f802  mov     r9d, r15d
0x18003f805  mov     r8, rbp
0x18003f808  mov     rdx, rbx
0x18003f80b  call    cs:__guard_dispatch_icall_fptr
0x18003f811  mov     edi, eax
0x18003f813  test    eax, eax
0x18003f815  js      short loc_18003F81C
0x18003f817  lfence
0x18003f81a  jmp     short loc_18003F898
0x18003f81c  cmp     eax, 0FFFFFFD8h
0x18003f81f  jnz     short loc_18003F863
0x18003f821  mov     rax, [rbx+148h]
0x18003f828  test    rax, rax
0x18003f82b  jz      short loc_18003F893
0x18003f82d  mov     rcx, [rax+8]
0x18003f831  mov     eax, [rbx+74h]
0x18003f834  cmp     [rcx+3Ch], eax
0x18003f837  jnz     short loc_18003F893
0x18003f839  mov     rax, [rcx+50h]
0x18003f83d  mov     rax, [rax+88h]
0x18003f844  test    rax, rax
0x18003f847  jz      short loc_18003F893
0x18003f849  mov     r9d, r15d
0x18003f84c  mov     r8, rbp
0x18003f84f  mov     rdx, rbx
0x18003f852  call    cs:__guard_dispatch_icall_fptr
0x18003f858  mov     edi, eax
0x18003f85a  test    eax, eax
0x18003f85c  jns     short loc_18003F817
0x18003f85e  cmp     eax, 0FFFFFFD8h
0x18003f861  jz      short loc_18003F893
0x18003f863  test    rsi, rsi
0x18003f866  jz      short loc_18003F871
0x18003f868  cmp     rsi, [rbx+148h]
0x18003f86f  jnz     short loc_18003F8B1
0x18003f871  mov     rcx, rbx
0x18003f874  mov     qword ptr [rbx+148h], 0
0x18003f87f  call    av_frame_unref
0x18003f884  mov     eax, edi
0x18003f886  mov     [rbx+148h], rsi
0x18003f88d  mov     [rbx+74h], r14d
0x18003f891  jmp     short loc_18003F898
0x18003f893  mov     eax, 0FFFFFFD8h
0x18003f898  mov     rbx, [rsp+48h+arg_0]
0x18003f89d  mov     rbp, [rsp+48h+arg_8]
0x18003f8a2  mov     rsi, [rsp+48h+arg_10]
0x18003f8a7  add     rsp, 30h
0x18003f8ab  pop     r15
0x18003f8ad  pop     r14
0x18003f8af  pop     rdi
0x18003f8b0  retn
0x18003f8b1  lea     rax, aCW1SFfmpeginte_7; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x18003f8b8  mov     [rsp+48h+var_20], 35Ah
0x18003f8c0  lea     r9, aOrigDstFramesV; "orig_dst_frames == ((void *)0) || orig_"...
0x18003f8c7  mov     [rsp+48h+var_28], rax
0x18003f8cc  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x18003f8d3  xor     edx, edx
0x18003f8d5  xor     ecx, ecx
0x18003f8d7  call    av_log
0x18003f8dc  call    abort
```
