# WriteBlankChunk

- ea: `0x180033b9c`
- end: `0x180033ce6`
- name: `WriteBlankChunk`
- size: `330`
- prototype: `__int64 __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800314a0`
- `0x180033258`

## callees

- `0x180023548`
- `0x1800249f0`
- `0x1800254b4`
- `0x180033b9c`
- `0x180034ba4`
- `0x180034ca4`
- `0x180034fc0`
- `0x180034fe4`
- `0x180035320`
- `0x180038fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WriteBlankChunk(void *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  ULONG v8; // eax
  unsigned int v9; // ebx
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+3Ch] [rbp-C4h]
  char v13; // [rsp+44h] [rbp-BCh]
  _BYTE v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  PUCHAR Buffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+78h] [rbp-88h]
  void *v17; // [rsp+98h] [rbp-68h]
  void *v18; // [rsp+1B0h] [rbp+B0h]

  WriteFileView::WriteFileView((WriteFileView *)v14, a2, 1);
  Buffer[1] = (PUCHAR)((a3 << 16) + 4096);
  InitializeChunkHeaderInfo((struct ChunkHeader *)Buffer[0], a2);
  memset_0(v17, 0, 0x100u);
  memset_0(v18, 0, 0x80u);
  v8 = CalcGeneralHeaderCRC(Buffer[0], v6, v7, 512);
  *((_DWORD *)Buffer[0] + 31) = v8;
  v9 = FileView::ActualWrite((FileView *)Buffer, a1, 0, v16);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v9);
    }
    pExceptionObject[0] = &word_18004024A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v11 = v9;
    v12 = -1;
    v13 = 0;
    throw (EvtException *)pExceptionObject;
  }
  FileView::~FileView((FileView *)Buffer);
}

```

## disassembly

```asm
0x180033b9c  push    rbp
0x180033b9e  push    rbx
0x180033b9f  push    rsi
0x180033ba0  push    rdi
0x180033ba1  lea     rbp, [rsp-158h]
0x180033ba9  sub     rsp, 258h
0x180033bb0  mov     rax, cs:__security_cookie
0x180033bb7  xor     rax, rsp
0x180033bba  mov     [rbp+170h+var_30], rax
0x180033bc1  mov     rbx, r8
0x180033bc4  mov     rdi, rdx
0x180033bc7  mov     rsi, rcx
0x180033bca  mov     r8b, 1; bool
0x180033bcd  lea     rcx, [rsp+270h+var_220]; this
0x180033bd2  call    ??0WriteFileView@@QEAA@K_N@Z; WriteFileView::WriteFileView(ulong,bool)
0x180033bd7  nop
0x180033bd8  shl     rbx, 10h
0x180033bdc  add     rbx, 1000h
0x180033be3  mov     [rsp+270h+var_210], rbx
0x180033be8  mov     rdx, rdi; unsigned __int64
0x180033beb  mov     rcx, [rsp+270h+Buffer]; struct ChunkHeader *
0x180033bf0  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180033bf5  xor     edx, edx; Val
0x180033bf7  mov     r8d, 100h; Size
0x180033bfd  mov     rcx, [rbp+170h+var_1D8]; void *
0x180033c01  call    memset_0
0x180033c06  xor     edx, edx; Val
0x180033c08  mov     r8d, 80h; Size
0x180033c0e  mov     rcx, [rbp+170h+var_C0]; void *
0x180033c15  call    memset_0
0x180033c1a  mov     r9d, 200h; unsigned int
0x180033c20  mov     rcx, [rsp+270h+Buffer]; Buffer
0x180033c25  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x180033c2a  mov     rcx, [rsp+270h+Buffer]
0x180033c2f  mov     [rcx+7Ch], eax
0x180033c32  mov     r9d, [rsp+270h+var_1F8]; unsigned int
0x180033c37  xor     r8d, r8d; unsigned int
0x180033c3a  mov     rdx, rsi; void *
0x180033c3d  lea     rcx, [rsp+270h+Buffer]; this
0x180033c42  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180033c47  mov     ebx, eax
0x180033c49  xor     edi, edi
0x180033c4b  test    eax, eax
0x180033c4d  jz      short loc_180033CC1
0x180033c4f  lea     rax, WPP_GLOBAL_Control
0x180033c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c5d  cmp     rcx, rax
0x180033c60  jz      short loc_180033C87
0x180033c62  test    dword ptr [rcx+1Ch], 8000h
0x180033c69  jz      short loc_180033C87
0x180033c6b  cmp     byte ptr [rcx+19h], 2
0x180033c6f  jb      short loc_180033C87
0x180033c71  lea     edx, [rdi+0Bh]
0x180033c74  mov     r9d, ebx
0x180033c77  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180033c7e  mov     rcx, [rcx+10h]
0x180033c82  call    WPP_SF_D
0x180033c87  lea     rax, word_18004024A
0x180033c8e  mov     [rsp+270h+pExceptionObject], rax
0x180033c93  mov     [rsp+270h+var_248], rdi
0x180033c98  mov     [rsp+270h+var_240], rdi
0x180033c9d  mov     [rsp+270h+var_238], ebx
0x180033ca1  mov     [rsp+270h+var_234], 0FFFFFFFFFFFFFFFFh
0x180033caa  mov     [rsp+270h+var_22C], dil
0x180033caf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180033cb6  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180033cbb  call    _CxxThrowException_0
0x180033cc1  lea     rcx, [rsp+270h+Buffer]; this
0x180033cc6  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180033ccb  mov     rcx, [rbp+170h+var_30]
0x180033cd2  xor     rcx, rsp; StackCookie
0x180033cd5  call    __security_check_cookie
0x180033cda  add     rsp, 258h
0x180033ce1  pop     rdi
0x180033ce2  pop     rsi
0x180033ce3  pop     rbx
0x180033ce4  pop     rbp
0x180033ce5  retn
```
