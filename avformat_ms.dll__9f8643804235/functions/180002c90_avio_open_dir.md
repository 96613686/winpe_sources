# avio_open_dir

- ea: `0x180002c90`
- end: `0x180002e15`
- name: `avio_open_dir`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002c90`
- `0x1800031a4`
- `0x18001bb58`
- `0x18001bb94`
- `0x18001bba0`
- `0x18001bba6`
- `0x18001bbbe`
- `0x18001bc00`
- `0x18001bdc6`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avio_open_dir(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  _QWORD *v7; // rsi
  int v8; // edi
  int v9; // eax
  _QWORD *v10; // rax
  __int64 result; // rax
  void (__fastcall *v12)(__int64); // rax
  __int64 v13; // rax
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  v14 = 0;
  if ( !a1 )
  {
    av_log(0, 0, "Assertion %s failed at %s:%d\n", "s", "C:/__w/1/s/FFmpegInterop/ffmpeg/libavformat/avio.c", 731);
    abort();
  }
  v7 = (_QWORD *)av_mallocz(8);
  if ( v7 )
  {
    v9 = sub_1800031A4(&v14, a2, 1);
    v3 = v14;
    v8 = v9;
    if ( v9 >= 0 )
    {
      v10 = *(_QWORD **)(v14 + 8);
      if ( v10[18] && v10[19] && v10[20] )
      {
        if ( !a3 || !v10[15] || (v8 = av_opt_set_dict(*(_QWORD *)(v14 + 16), a3), v8 >= 0) )
        {
          v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v3 + 8) + 144LL))(v3);
          if ( v8 >= 0 )
          {
            *(_DWORD *)(v3 + 44) = 1;
            result = 0;
            *v7 = v3;
            *a1 = v7;
            return result;
          }
        }
      }
      else
      {
        v8 = -40;
      }
    }
  }
  else
  {
    v8 = -12;
  }
  av_free(v7);
  *a1 = 0;
  v14 = v3;
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 44) )
    {
      v12 = *(void (__fastcall **)(__int64))(*(_QWORD *)(v3 + 8) + 64LL);
      if ( v12 )
        v12(v3);
    }
    v13 = *(_QWORD *)(v3 + 8);
    if ( *(_DWORD *)(v13 + 128) )
    {
      if ( *(_QWORD *)(v13 + 120) )
        av_opt_free(*(_QWORD *)(v3 + 16));
      av_freep(v3 + 16);
    }
    av_opt_free(v3);
    av_freep(&v14);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002c90  mov     [rsp+arg_8], rbx
0x180002c95  mov     [rsp+arg_10], rbp
0x180002c9a  push    rsi
0x180002c9b  push    rdi
0x180002c9c  push    r14
0x180002c9e  sub     rsp, 30h
0x180002ca2  xor     ebx, ebx
0x180002ca4  mov     rbp, r8
0x180002ca7  mov     [rsp+48h+arg_0], rbx
0x180002cac  mov     rdi, rdx
0x180002caf  mov     r14, rcx
0x180002cb2  test    rcx, rcx
0x180002cb5  jz      loc_180002DE4
0x180002cbb  lea     ecx, [rbx+8]
0x180002cbe  call    av_mallocz
0x180002cc3  mov     rsi, rax
0x180002cc6  test    rax, rax
0x180002cc9  jnz     short loc_180002CD3
0x180002ccb  lea     edi, [rbx-0Ch]
0x180002cce  jmp     loc_180002D62
0x180002cd3  xor     r9d, r9d
0x180002cd6  lea     rcx, [rsp+48h+arg_0]
0x180002cdb  mov     rdx, rdi
0x180002cde  lea     r8d, [r9+1]
0x180002ce2  call    sub_1800031A4
0x180002ce7  mov     rbx, [rsp+48h+arg_0]
0x180002cec  mov     edi, eax
0x180002cee  test    eax, eax
0x180002cf0  js      short loc_180002D62
0x180002cf2  mov     rax, [rbx+8]
0x180002cf6  cmp     qword ptr [rax+90h], 0
0x180002cfe  jz      short loc_180002D5D
0x180002d00  cmp     qword ptr [rax+98h], 0
0x180002d08  jz      short loc_180002D5D
0x180002d0a  cmp     qword ptr [rax+0A0h], 0
0x180002d12  jz      short loc_180002D5D
0x180002d14  test    rbp, rbp
0x180002d17  jz      short loc_180002D32
0x180002d19  cmp     qword ptr [rax+78h], 0
0x180002d1e  jz      short loc_180002D32
0x180002d20  mov     rcx, [rbx+10h]
0x180002d24  mov     rdx, rbp
0x180002d27  call    av_opt_set_dict
0x180002d2c  mov     edi, eax
0x180002d2e  test    eax, eax
0x180002d30  js      short loc_180002D62
0x180002d32  mov     rax, [rbx+8]
0x180002d36  mov     rcx, rbx
0x180002d39  mov     rax, [rax+90h]
0x180002d40  call    cs:__guard_dispatch_icall_fptr
0x180002d46  mov     edi, eax
0x180002d48  test    eax, eax
0x180002d4a  js      short loc_180002D62
0x180002d4c  mov     dword ptr [rbx+2Ch], 1
0x180002d53  xor     eax, eax
0x180002d55  mov     [rsi], rbx
0x180002d58  mov     [r14], rsi
0x180002d5b  jmp     short loc_180002DD1
0x180002d5d  mov     edi, 0FFFFFFD8h
0x180002d62  mov     rcx, rsi
0x180002d65  call    av_free
0x180002d6a  mov     qword ptr [r14], 0
0x180002d71  mov     [rsp+48h+arg_0], rbx
0x180002d76  test    rbx, rbx
0x180002d79  jz      short loc_180002DCF
0x180002d7b  cmp     dword ptr [rbx+2Ch], 0
0x180002d7f  jz      short loc_180002D97
0x180002d81  mov     rax, [rbx+8]
0x180002d85  mov     rax, [rax+40h]
0x180002d89  test    rax, rax
0x180002d8c  jz      short loc_180002D97
0x180002d8e  mov     rcx, rbx
0x180002d91  call    cs:__guard_dispatch_icall_fptr
0x180002d97  mov     rax, [rbx+8]
0x180002d9b  cmp     dword ptr [rax+80h], 0
0x180002da2  jz      short loc_180002DBD
0x180002da4  cmp     qword ptr [rax+78h], 0
0x180002da9  jz      short loc_180002DB4
0x180002dab  mov     rcx, [rbx+10h]
0x180002daf  call    av_opt_free
0x180002db4  lea     rcx, [rbx+10h]
0x180002db8  call    av_freep
0x180002dbd  mov     rcx, rbx
0x180002dc0  call    av_opt_free
0x180002dc5  lea     rcx, [rsp+48h+arg_0]
0x180002dca  call    av_freep
0x180002dcf  mov     eax, edi
0x180002dd1  mov     rbx, [rsp+48h+arg_8]
0x180002dd6  mov     rbp, [rsp+48h+arg_10]
0x180002ddb  add     rsp, 30h
0x180002ddf  pop     r14
0x180002de1  pop     rdi
0x180002de2  pop     rsi
0x180002de3  retn
0x180002de4  lea     rax, aCW1SFfmpeginte_0; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavfo"...
0x180002deb  mov     [rsp+48h+var_20], 2DBh
0x180002df3  lea     r9, aS; "s"
0x180002dfa  mov     [rsp+48h+var_28], rax
0x180002dff  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x180002e06  xor     edx, edx
0x180002e08  xor     ecx, ecx
0x180002e0a  call    av_log
0x180002e0f  call    abort
```
