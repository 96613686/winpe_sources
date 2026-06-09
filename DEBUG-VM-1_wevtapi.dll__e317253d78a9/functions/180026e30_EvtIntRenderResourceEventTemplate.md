# EvtIntRenderResourceEventTemplate

- ea: `0x180026e30`
- end: `0x180027375`
- name: `EvtIntRenderResourceEventTemplate`
- size: `1349`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003158`
- `0x180003dc0`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000b95c`
- `0x180012cb0`
- `0x1800196a0`
- `0x180023548`
- `0x180024388`
- `0x1800249f0`
- `0x180026e30`
- `0x18002e234`
- `0x18002f324`
- `0x18002f454`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002704a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002704a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EvtIntRenderResourceEventTemplate(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned __int8 *a7,
        _DWORD *a8)
{
  unsigned int v8; // esi
  __int64 v9; // rbx
  struct BinXmlTmplInstWriter *started; // rdi
  unsigned int i; // r15d
  __m128i v12; // xmm1
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // edi
  unsigned __int32 j; // esi
  _BYTE *v17; // rdx
  __int64 v18; // r8
  DWORD LengthSid; // eax
  _WORD *v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r8d
  __int64 result; // rax
  __m128i v24; // [rsp+48h] [rbp-3D0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-3C0h]
  __int64 v26; // [rsp+60h] [rbp-3B8h]
  BinXmlTmplInstWriter *v27; // [rsp+68h] [rbp-3B0h]
  char v28[8]; // [rsp+70h] [rbp-3A8h] BYREF
  __int64 v29; // [rsp+78h] [rbp-3A0h]
  __int128 pExceptionObject; // [rsp+90h] [rbp-388h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-378h]
  int v32; // [rsp+A8h] [rbp-370h]
  int v33; // [rsp+ACh] [rbp-36Ch]
  int v34; // [rsp+B0h] [rbp-368h]
  __int128 v35; // [rsp+B8h] [rbp-360h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-350h]
  int v37; // [rsp+D0h] [rbp-348h]
  int v38; // [rsp+D4h] [rbp-344h]
  int v39; // [rsp+D8h] [rbp-340h]
  char v40[8]; // [rsp+E0h] [rbp-338h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-330h]
  unsigned int v42; // [rsp+F0h] [rbp-328h]
  char v43[8]; // [rsp+F8h] [rbp-320h] BYREF
  unsigned __int8 *v44; // [rsp+100h] [rbp-318h]
  int v45; // [rsp+108h] [rbp-310h]
  EvtException *v46; // [rsp+110h] [rbp-308h] BYREF
  _BYTE v47[32]; // [rsp+118h] [rbp-300h] BYREF
  _BYTE v48[32]; // [rsp+138h] [rbp-2E0h] BYREF
  _QWORD v49[3]; // [rsp+158h] [rbp-2C0h] BYREF
  __int128 v50; // [rsp+170h] [rbp-2A8h]
  _BYTE v51[48]; // [rsp+180h] [rbp-298h] BYREF
  _BYTE v52[64]; // [rsp+1B0h] [rbp-268h] BYREF
  _BYTE v53[192]; // [rsp+1F0h] [rbp-228h] BYREF
  _QWORD v54[2]; // [rsp+2B0h] [rbp-168h] BYREF
  __int128 v55; // [rsp+2C0h] [rbp-158h]
  __int128 v56; // [rsp+2D0h] [rbp-148h]
  unsigned __int8 v57[256]; // [rsp+2E0h] [rbp-138h] BYREF

  try
  {
    v8 = a4;
    v25 = a4;
    v9 = a3;
    v26 = a3;
    if ( !a8 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v31 = 0;
      v32 = 87;
      v33 = -1;
      v34 = 125;
      throw (EvtException *)&pExceptionObject;
    }
    *a8 = 0;
    if ( !a1 || a5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      v35 = 0;
      v36 = 0;
      v37 = 87;
      v38 = -1;
      v39 = 132;
      throw (EvtException *)&v35;
    }
    v54[0] = a1;
    v54[1] = a2;
    v55 = 0;
    v56 = 0;
    Buffer::Buffer((Buffer *)v48, v57, 0x100u, 0);
    WriteBuffer::WriteBuffer((WriteBuffer *)v40, (struct BufferStream *)v48);
    BinXmlWriter::BinXmlWriter((BinXmlWriter *)v51, 0, (struct WriteBuffer *)v40, 0, 0, 0, 0);
    started = BinXmlWriter::StartTemplateInstance((BinXmlWriter *)v51, v8, (struct BinXmlTemplate *)v54);
    v27 = started;
    for ( i = 0; ; ++i )
    {
      if ( i >= v8 )
      {
        BinXmlWriter::EndOfFile((BinXmlWriter *)v51);
        v49[0] = 0;
        v50 = 0;
        v49[1] = v41;
        v49[2] = v42;
        BinXmlReader::BinXmlReader((BinXmlReader *)v53, (struct BinXmlReaderData *)v49, v22, 0, 0, 0);
        Buffer::Buffer((Buffer *)v47, a7, 2 * a6, 0);
        WriteBuffer::WriteBuffer((WriteBuffer *)v43, (struct BufferStream *)v47);
        BinXmlReader::GetXmlText((BinXmlReader *)v53, (struct WriteBuffer *)v43);
        *a8 = v45;
        if ( v44 == a7 )
        {
          Buffer::~Buffer((Buffer *)v47);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v53);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v52);
          Buffer::~Buffer((Buffer *)v48);
          return 0;
        }
        else
        {
          Buffer::~Buffer((Buffer *)v47);
          BinXmlReader::~BinXmlReader((BinXmlReader *)v53);
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v52);
          Buffer::~Buffer((Buffer *)v48);
          return 122;
        }
      }
      v12 = *(__m128i *)(v9 + 16LL * i);
      v24 = v12;
      v13 = HIDWORD(*(_QWORD *)(v9 + 16LL * i + 8));
      if ( (v13 & 0x80u) == 0LL )
        break;
      v15 = v24.m128i_i32[3] & 0xFFFFFF7F;
      Buffer::Buffer((Buffer *)v28, 0, 0, 1);
      for ( j = 0; j < v24.m128i_i32[2]; ++j )
      {
        switch ( v15 )
        {
          case 1u:
          case 0x23u:
            v20 = *(_WORD **)(*(_QWORD *)(v9 + 16LL * i) + 8LL * j);
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            Buffer::Write((Buffer *)v28, v20, 2 * v21 + 2);
            break;
          case 2u:
            v17 = *(_BYTE **)(*(_QWORD *)(v9 + 16LL * i) + 8LL * j);
            v18 = -1;
            do
              ++v18;
            while ( v17[v18] );
            Buffer::Write((Buffer *)v28, v17, v18 + 1);
            break;
          case 0x13u:
            LengthSid = GetLengthSid(*(PSID *)(*(_QWORD *)(v26 + 16LL * i) + 8LL * j));
            Buffer::Write((Buffer *)v28, *(const void *const *)(*(_QWORD *)(v26 + 16LL * i) + 8LL * j), LengthSid);
            v9 = v26;
            break;
        }
      }
      v24.m128i_i64[0] = v29;
      started = v27;
      BinXmlTmplInstWriter::Value(v27, (struct BinXmlVariant *)&v24);
      Buffer::~Buffer((Buffer *)v28);
      v8 = v25;
LABEL_44:
      ;
    }
    if ( (_DWORD)v13 == 1 || (_DWORD)v13 == 35 )
    {
      if ( v12.m128i_i64[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v12.m128i_i64[0] + 2 * v14) );
        goto LABEL_26;
      }
    }
    else if ( (_DWORD)v13 == 2 )
    {
      if ( v12.m128i_i64[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_BYTE *)(v12.m128i_i64[0] + v14) );
        goto LABEL_26;
      }
    }
    else
    {
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v12, 12)) != 19 )
      {
LABEL_28:
        BinXmlTmplInstWriter::Value(started, (struct BinXmlVariant *)&v24);
        goto LABEL_44;
      }
      if ( v12.m128i_i64[0] )
      {
        LODWORD(v14) = GetLengthSid((PSID)v12.m128i_i64[0]);
LABEL_26:
        v24.m128i_i32[2] = v14;
        goto LABEL_28;
      }
    }
    v24.m128i_i32[2] = 0;
    goto LABEL_28;
  }
  catch ( EvtException *v46 )
  {
    return *((unsigned int *)v46 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x180026e30  mov     [rsp+arg_0], rbx
0x180026e35  mov     [rsp+arg_8], rsi
0x180026e3a  push    rdi
0x180026e3b  push    r12
0x180026e3d  push    r13
0x180026e3f  push    r14
0x180026e41  push    r15
0x180026e43  sub     rsp, 3F0h
0x180026e4a  mov     rax, cs:__security_cookie
0x180026e51  xor     rax, rsp
0x180026e54  mov     [rsp+418h+var_38], rax
0x180026e5c  mov     esi, r9d
0x180026e5f  mov     [rsp+418h+var_3C0], r9d
0x180026e64  mov     rbx, r8
0x180026e67  mov     [rsp+418h+var_3B8], rbx
0x180026e6c  mov     r14d, [rsp+418h+arg_28]
0x180026e74  mov     [rsp+418h+var_3D8], r14d
0x180026e79  mov     r13, [rsp+418h+arg_30]
0x180026e81  mov     r12, [rsp+418h+arg_38]
0x180026e89  xor     r14d, r14d
0x180026e8c  test    r12, r12
0x180026e8f  jnz     loc_180026F17
0x180026e95  lea     rax, WPP_GLOBAL_Control
0x180026e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ea3  cmp     rcx, rax
0x180026ea6  jz      short loc_180026ECE
0x180026ea8  test    byte ptr [rcx+1Ch], 1
0x180026eac  jz      short loc_180026ECE
0x180026eae  cmp     byte ptr [rcx+19h], 2
0x180026eb2  jb      short loc_180026ECE
0x180026eb4  lea     edx, [r12+0Ah]
0x180026eb9  lea     r9d, [r12+57h]
0x180026ebe  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x180026ec5  mov     rcx, [rcx+10h]
0x180026ec9  call    WPP_SF_D
0x180026ece  xorps   xmm0, xmm0
0x180026ed1  movdqu  [rsp+418h+pExceptionObject], xmm0
0x180026eda  mov     [rsp+418h+var_378], r14
0x180026ee2  mov     [rsp+418h+var_370], 57h ; 'W'
0x180026eed  mov     [rsp+418h+var_36C], 0FFFFFFFFh
0x180026ef8  mov     [rsp+418h+var_368], 7Dh ; '}'
0x180026f03  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180026f0a  lea     rcx, [rsp+418h+pExceptionObject]; pExceptionObject
0x180026f12  call    _CxxThrowException_0
0x180026f17  mov     [r12], r14d
0x180026f1b  test    rcx, rcx
0x180026f1e  jz      loc_1800272C1
0x180026f24  cmp     [rsp+418h+arg_20], r14d
0x180026f2c  jnz     loc_1800272C1
0x180026f32  xorps   xmm0, xmm0
0x180026f35  mov     [rsp+418h+var_168], rcx
0x180026f3d  mov     eax, edx
0x180026f3f  mov     [rsp+418h+var_160], rax
0x180026f47  movdqu  [rsp+418h+var_158], xmm0
0x180026f50  movdqu  [rsp+418h+var_148], xmm0
0x180026f59  xor     r9d, r9d; bool
0x180026f5c  mov     r8d, 100h; unsigned int
0x180026f62  lea     rdx, [rsp+418h+var_138]; unsigned __int8 *
0x180026f6a  lea     rcx, [rsp+418h+var_2E0]; this
0x180026f72  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180026f77  nop
0x180026f78  lea     rdx, [rsp+418h+var_2E0]; struct BufferStream *
0x180026f80  lea     rcx, [rsp+418h+var_338]; this
0x180026f88  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180026f8d  mov     [rsp+418h+var_3E8], r14d; unsigned int
0x180026f92  mov     [rsp+418h+var_3F0], r14; unsigned int *
0x180026f97  mov     [rsp+418h+var_3F8], r14; struct BinXmlTemplateTable *
0x180026f9c  xor     r9d, r9d; struct BinXmlStringTable *
0x180026f9f  lea     r8, [rsp+418h+var_338]; struct WriteBuffer *
0x180026fa7  xor     edx, edx; bool
0x180026fa9  lea     rcx, [rsp+418h+var_298]; this
0x180026fb1  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x180026fb6  nop
0x180026fb7  lea     r8, [rsp+418h+var_168]; struct BinXmlTemplate *
0x180026fbf  mov     edx, esi; unsigned int
0x180026fc1  lea     rcx, [rsp+418h+var_298]; this
0x180026fc9  call    ?StartTemplateInstance@BinXmlWriter@@QEAAPEAVBinXmlTmplInstWriter@@KPEAVBinXmlTemplate@@@Z; BinXmlWriter::StartTemplateInstance(ulong,BinXmlTemplate *)
0x180026fce  mov     rdi, rax
0x180026fd1  mov     [rsp+418h+var_3B0], rax
0x180026fd6  mov     r15d, r14d
0x180026fd9  cmp     r15d, esi
0x180026fdc  jnb     loc_180027189
0x180026fe2  mov     r14d, r15d
0x180026fe5  add     r14, r14
0x180026fe8  movups  xmm1, xmmword ptr [rbx+r14*8]
0x180026fed  movups  [rsp+418h+var_3D0], xmm1
0x180026ff2  mov     rax, [rbx+r14*8+8]
0x180026ff7  shr     rax, 20h
0x180026ffb  test    al, al
0x180026ffd  js      loc_180027087
0x180027003  cmp     eax, 1
0x180027006  jz      short loc_180027052
0x180027008  cmp     eax, 23h ; '#'
0x18002700b  jz      short loc_180027052
0x18002700d  cmp     eax, 2
0x180027010  jnz     short loc_18002702C
0x180027012  movq    rcx, xmm1
0x180027017  xor     edx, edx
0x180027019  test    rcx, rcx
0x18002701c  jz      short loc_180027071
0x18002701e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027022  inc     rax
0x180027025  cmp     [rcx+rax], dl
0x180027028  jnz     short loc_180027022
0x18002702a  jmp     short loc_18002706B
0x18002702c  movdqa  xmm0, xmm1
0x180027030  psrldq  xmm0, 0Ch
0x180027035  movd    eax, xmm0
0x180027039  cmp     eax, 13h
0x18002703c  jnz     short loc_180027075
0x18002703e  movq    rcx, xmm1; pSid
0x180027043  xor     edx, edx
0x180027045  test    rcx, rcx
0x180027048  jz      short loc_180027071
0x18002704a  call    cs:__imp_GetLengthSid
0x180027050  jmp     short loc_18002706B
0x180027052  movq    rcx, xmm1
0x180027057  xor     edx, edx
0x180027059  test    rcx, rcx
0x18002705c  jz      short loc_180027071
0x18002705e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027062  inc     rax
0x180027065  cmp     [rcx+rax*2], dx
0x180027069  jnz     short loc_180027062
0x18002706b  mov     dword ptr [rsp+418h+var_3D0+8], eax
0x18002706f  jmp     short loc_180027075
0x180027071  mov     dword ptr [rsp+418h+var_3D0+8], edx
0x180027075  lea     rdx, [rsp+418h+var_3D0]; struct BinXmlVariant *
0x18002707a  mov     rcx, rdi; this
0x18002707d  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x180027082  jmp     loc_180027181
0x180027087  mov     edi, dword ptr [rsp+418h+var_3D0+0Ch]
0x18002708b  btr     edi, 7
0x18002708f  mov     r9b, 1; bool
0x180027092  xor     r8d, r8d; unsigned int
0x180027095  xor     edx, edx; unsigned __int8 *
0x180027097  lea     rcx, [rsp+418h+var_3A8]; this
0x18002709c  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x1800270a1  nop
0x1800270a2  xor     r9d, r9d
0x1800270a5  mov     esi, r9d
0x1800270a8  cmp     esi, dword ptr [rsp+418h+var_3D0+8]
0x1800270ac  jnb     loc_180027156
0x1800270b2  cmp     edi, 1
0x1800270b5  jz      short loc_180027122
0x1800270b7  cmp     edi, 23h ; '#'
0x1800270ba  jz      short loc_180027122
0x1800270bc  cmp     edi, 2
0x1800270bf  jnz     short loc_1800270E7
0x1800270c1  mov     ecx, esi
0x1800270c3  mov     rax, [rbx+r14*8]
0x1800270c7  mov     rdx, [rax+rcx*8]; void *
0x1800270cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800270cf  inc     r8
0x1800270d2  cmp     [rdx+r8], r9b
0x1800270d6  jnz     short loc_1800270CF
0x1800270d8  inc     r8d; unsigned int
0x1800270db  lea     rcx, [rsp+418h+var_3A8]; this
0x1800270e0  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x1800270e5  jmp     short loc_18002714C
0x1800270e7  cmp     edi, 13h
0x1800270ea  jnz     short loc_18002714F
0x1800270ec  mov     ebx, esi
0x1800270ee  mov     rax, [rsp+418h+var_3B8]
0x1800270f3  mov     rcx, [rax+r14*8]
0x1800270f7  mov     rcx, [rcx+rbx*8]; pSid
0x1800270fb  call    cs:__imp_GetLengthSid
0x180027101  mov     rdx, [rsp+418h+var_3B8]
0x180027106  mov     rdx, [rdx+r14*8]
0x18002710a  mov     r8d, eax; unsigned int
0x18002710d  mov     rdx, [rdx+rbx*8]; void *
0x180027111  lea     rcx, [rsp+418h+var_3A8]; this
0x180027116  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18002711b  mov     rbx, [rsp+418h+var_3B8]
0x180027120  jmp     short loc_18002714C
0x180027122  mov     ecx, esi
0x180027124  mov     rax, [rbx+r14*8]
0x180027128  mov     rdx, [rax+rcx*8]; void *
0x18002712c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027130  inc     r8
0x180027133  cmp     [rdx+r8*2], r9w
0x180027138  jnz     short loc_180027130
0x18002713a  lea     r8d, ds:2[r8*2]; unsigned int
0x180027142  lea     rcx, [rsp+418h+var_3A8]; this
0x180027147  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x18002714c  xor     r9d, r9d
0x18002714f  inc     esi
0x180027151  jmp     loc_1800270A8
0x180027156  mov     rax, [rsp+418h+var_3A0]
0x18002715b  mov     qword ptr [rsp+418h+var_3D0], rax
0x180027160  lea     rdx, [rsp+418h+var_3D0]; struct BinXmlVariant *
0x180027165  mov     rdi, [rsp+418h+var_3B0]
0x18002716a  mov     rcx, rdi; this
0x18002716d  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x180027172  nop
0x180027173  lea     rcx, [rsp+418h+var_3A8]; this
0x180027178  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002717d  mov     esi, [rsp+418h+var_3C0]
0x180027181  inc     r15d
0x180027184  jmp     loc_180026FD9
0x180027189  lea     rcx, [rsp+418h+var_298]; this
0x180027191  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x180027196  xor     ecx, ecx
0x180027198  mov     [rsp+418h+var_2C0], rcx
0x1800271a0  xorps   xmm0, xmm0
0x1800271a3  movdqu  [rsp+418h+var_2A8], xmm0
0x1800271ac  mov     rax, [rsp+418h+var_330]
0x1800271b4  mov     [rsp+418h+var_2B8], rax
0x1800271bc  mov     eax, [rsp+418h+var_328]
0x1800271c3  mov     [rsp+418h+var_2B0], rax
0x1800271cb  mov     [rsp+418h+var_3F0], rcx; struct BinXmlTemplateTable *
0x1800271d0  mov     [rsp+418h+var_3F8], rcx; struct BinXmlStringTable *
0x1800271d5  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x1800271d8  lea     rdx, [rsp+418h+var_2C0]; struct BinXmlReaderData *
0x1800271e0  lea     rcx, [rsp+418h+var_228]; this
0x1800271e8  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x1800271ed  nop
0x1800271ee  mov     r8d, [rsp+418h+var_3D8]
0x1800271f3  add     r8d, r8d; unsigned int
0x1800271f6  xor     r9d, r9d; bool
0x1800271f9  mov     rdx, r13; unsigned __int8 *
0x1800271fc  lea     rcx, [rsp+418h+var_300]; this
0x180027204  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180027209  nop
0x18002720a  lea     rdx, [rsp+418h+var_300]; struct BufferStream *
0x180027212  lea     rcx, [rsp+418h+var_320]; this
0x18002721a  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x18002721f  lea     rdx, [rsp+418h+var_320]; struct WriteBuffer *
0x180027227  lea     rcx, [rsp+418h+var_228]; this
0x18002722f  call    ?GetXmlText@BinXmlReader@@QEAAXAEAVWriteBuffer@@@Z; BinXmlReader::GetXmlText(WriteBuffer &)
0x180027234  mov     eax, [rsp+418h+var_310]
0x18002723b  mov     [r12], eax
0x18002723f  lea     rcx, [rsp+418h+var_300]; this
0x180027247  cmp     [rsp+418h+var_318], r13
0x18002724f  jz      short loc_18002728A
0x180027251  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x180027256  nop
0x180027257  lea     rcx, [rsp+418h+var_228]; this
0x18002725f  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180027264  nop
0x180027265  lea     rcx, [rsp+418h+var_268]
0x18002726d  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x180027272  nop
0x180027273  lea     rcx, [rsp+418h+var_2E0]; this
0x18002727b  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x180027280  mov     eax, 7Ah ; 'z'
0x180027285  jmp     loc_180027347
0x18002728a  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002728f  nop
0x180027290  lea     rcx, [rsp+418h+var_228]; this
0x180027298  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x18002729d  nop
0x18002729e  lea     rcx, [rsp+418h+var_268]
0x1800272a6  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800272ab  nop
0x1800272ac  lea     rcx, [rsp+418h+var_2E0]; this
0x1800272b4  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800272b9  nop
0x1800272ba  xor     eax, eax
0x1800272bc  jmp     loc_180027347
0x1800272c1  lea     rax, WPP_GLOBAL_Control
0x1800272c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272cf  cmp     rcx, rax
0x1800272d2  jz      short loc_1800272F9
0x1800272d4  test    byte ptr [rcx+1Ch], 1
0x1800272d8  jz      short loc_1800272F9
0x1800272da  cmp     byte ptr [rcx+19h], 2
0x1800272de  jb      short loc_1800272F9
0x1800272e0  mov     edx, 0Bh
0x1800272e5  lea     r9d, [rdx+4Ch]
0x1800272e9  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x1800272f0  mov     rcx, [rcx+10h]
0x1800272f4  call    WPP_SF_D
0x1800272f9  xorps   xmm0, xmm0
0x1800272fc  movdqu  [rsp+418h+var_360], xmm0
0x180027305  mov     [rsp+418h+var_350], r14
0x18002730d  mov     [rsp+418h+var_348], 57h ; 'W'
0x180027318  mov     [rsp+418h+var_344], 0FFFFFFFFh
0x180027323  mov     [rsp+418h+var_340], 84h
0x18002732e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027335  lea     rcx, [rsp+418h+var_360]; pExceptionObject
0x18002733d  call    _CxxThrowException_0
0x180027343  mov     eax, [rsp+418h+var_3D8]
0x180027347  mov     rcx, [rsp+418h+var_38]
0x18002734f  xor     rcx, rsp; StackCookie
0x180027352  call    __security_check_cookie
0x180027357  lea     r11, [rsp+418h+var_28]
0x18002735f  mov     rbx, [r11+30h]
0x180027363  mov     rsi, [r11+38h]
0x180027367  mov     rsp, r11
0x18002736a  pop     r15
0x18002736c  pop     r14
0x18002736e  pop     r13
0x180027370  pop     r12
0x180027372  pop     rdi
0x180027373  retn
```
