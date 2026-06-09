# CMpeg2PCRParser::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x18002a480`
- end: `0x18002a5c9`
- name: `?ProcessSysBuffer@CMpeg2PCRParser@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `329`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180028a7c`
- `0x180028dc4`
- `0x180028fd8`
- `0x180029270`
- `0x18002a480`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2PCRParser::ProcessSysBuffer(
        CCopyFrameParser *this,
        struct IMediaSample *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  unsigned int v9; // eax
  __int64 **v11; // rdi
  __int64 *v12; // rcx
  __int64 v13; // rax
  int NewFrameBuffer; // edi
  int v15; // ecx
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int8 v18[8]; // [rsp+38h] [rbp-28h] BYREF
  int v19; // [rsp+40h] [rbp-20h]
  int v20; // [rsp+44h] [rbp-1Ch]
  GUID v21; // [rsp+50h] [rbp-10h] BYREF
  int v22; // [rsp+90h] [rbp+30h] BYREF

  v9 = *(_DWORD *)(a3 + 56) - 2;
  *(_QWORD *)v18 = 0;
  if ( v9 <= 1 && *(_DWORD *)(a3 + 64) && *(_DWORD *)(a3 + 80) && !a4 )
  {
    v11 = (__int64 **)*((_QWORD *)this + 49);
    *(_QWORD *)v18 = *(unsigned int *)(a3 + 112) + 300LL * *(_QWORD *)(a3 + 104);
    v17 = *(_QWORD *)v18;
    v22 = 0;
    if ( *v11 )
    {
      (*(void (__fastcall **)(__int64 *, int *))(**v11 + 24))(*v11, &v22);
      if ( v22 )
      {
        v12 = *v11;
        v13 = **v11;
        v21 = GUID_7e5477ff_0cb6_4880_8479_0dde6b2d5756;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64 *, __int64))(v13 + 32))(v12, &v21, &v17, 8);
      }
    }
    v20 = a8 - 177;
    NewFrameBuffer = CCopyFrameParser::GetNewFrameBuffer(this, a2);
    if ( NewFrameBuffer >= 0 )
    {
      v15 = *(_DWORD *)(a3 + 28) & 0x1FFF;
      v22 = 0;
      v19 = v15;
      if ( (unsigned int)CBufferSourceManager::CopyBlock((CCopyFrameParser *)((char *)this + 48), v18, 16, &v22) )
      {
        CBufferSourceManager::Complete((__int64)this + 48);
      }
      else
      {
        if ( *((_DWORD *)this + 95) )
          *(_DWORD *)(a3 + 28) |= 0x2000u;
        CBufferSourceManager::AbortBuffer((CCopyFrameParser *)((char *)this + 48));
        return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)NewFrameBuffer;
}

```

## disassembly

```asm
0x18002a480  mov     [rsp-18h+arg_0], rbx
0x18002a485  mov     [rsp-18h+arg_8], rsi
0x18002a48a  push    rbp
0x18002a48b  push    rdi
0x18002a48c  push    r14
0x18002a48e  mov     rbp, rsp
0x18002a491  sub     rsp, 60h
0x18002a495  mov     eax, [r8+38h]
0x18002a499  mov     rbx, r8
0x18002a49c  sub     eax, 2
0x18002a49f  mov     qword ptr [rbp+var_28], 0
0x18002a4a7  mov     rsi, rcx
0x18002a4aa  cmp     eax, 1
0x18002a4ad  ja      loc_18002A5B0
0x18002a4b3  cmp     dword ptr [r8+40h], 0
0x18002a4b8  jbe     loc_18002A5B0
0x18002a4be  cmp     dword ptr [r8+50h], 0
0x18002a4c3  jz      loc_18002A5B0
0x18002a4c9  test    r9d, r9d
0x18002a4cc  jnz     loc_18002A5B0
0x18002a4d2  imul    rcx, [r8+68h], 12Ch
0x18002a4da  mov     eax, [r8+70h]
0x18002a4de  mov     rdi, [rsi+188h]
0x18002a4e5  add     rcx, rax
0x18002a4e8  mov     qword ptr [rbp+var_28], rcx
0x18002a4ec  mov     [rbp+var_30], rcx
0x18002a4f0  mov     [rbp+arg_10], r9d
0x18002a4f4  mov     rcx, [rdi]
0x18002a4f7  test    rcx, rcx
0x18002a4fa  jz      short loc_18002A53B
0x18002a4fc  mov     rax, [rcx]
0x18002a4ff  lea     rdx, [rbp+arg_10]
0x18002a503  mov     rax, [rax+18h]
0x18002a507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a50c  cmp     [rbp+arg_10], 0
0x18002a510  jz      short loc_18002A53B
0x18002a512  mov     rcx, [rdi]
0x18002a515  lea     r8, [rbp+var_30]
0x18002a519  movups  xmm0, xmmword ptr cs:_GUID_7e5477ff_0cb6_4880_8479_0dde6b2d5756.Data1
0x18002a520  mov     r9d, 8
0x18002a526  lea     rdx, [rbp+var_10]
0x18002a52a  mov     rax, [rcx]
0x18002a52d  movdqu  [rbp+var_10], xmm0
0x18002a532  mov     rax, [rax+20h]
0x18002a536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a53b  mov     eax, [rbp+arg_38]
0x18002a53e  mov     rcx, rsi; this
0x18002a541  add     eax, 0FFFFFF4Fh
0x18002a546  mov     [rbp+var_1C], eax
0x18002a549  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x18002a54e  mov     edi, eax
0x18002a550  test    eax, eax
0x18002a552  js      short loc_18002A5B2
0x18002a554  mov     ecx, [rbx+1Ch]
0x18002a557  lea     r14, [rsi+30h]
0x18002a55b  and     ecx, 1FFFh
0x18002a561  mov     [rbp+arg_10], 0
0x18002a568  mov     [rbp+var_20], ecx
0x18002a56b  lea     r9, [rbp+arg_10]; int *
0x18002a56f  mov     rcx, r14; this
0x18002a572  lea     rdx, [rbp+var_28]; unsigned __int8 *
0x18002a576  mov     r8d, 10h; int
0x18002a57c  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x18002a581  test    eax, eax
0x18002a583  jz      short loc_18002A593
0x18002a585  mov     rdx, [rbp+arg_40]
0x18002a589  mov     rcx, r14
0x18002a58c  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x18002a591  jmp     short loc_18002A5B2
0x18002a593  cmp     dword ptr [rsi+17Ch], 0
0x18002a59a  jz      short loc_18002A5A1
0x18002a59c  bts     dword ptr [rbx+1Ch], 0Dh
0x18002a5a1  mov     rcx, r14; this
0x18002a5a4  call    ?AbortBuffer@CBufferSourceManager@@IEAAXXZ; CBufferSourceManager::AbortBuffer(void)
0x18002a5a9  mov     edi, 80004005h
0x18002a5ae  jmp     short loc_18002A5B2
0x18002a5b0  xor     edi, edi
0x18002a5b2  lea     r11, [rsp+60h+var_s0]
0x18002a5b7  mov     eax, edi
0x18002a5b9  mov     rbx, [r11+20h]
0x18002a5bd  mov     rsi, [r11+28h]
0x18002a5c1  mov     rsp, r11
0x18002a5c4  pop     r14
0x18002a5c6  pop     rdi
0x18002a5c7  pop     rbp
0x18002a5c8  retn
```
