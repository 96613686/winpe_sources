# CReader::InitializeReaderName(void)

- ea: `0x18001af40`
- end: `0x18001b2fd`
- name: `?InitializeReaderName@CReader@@MEAAXXZ`
- size: `957`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops`

## callees

- `0x1800044e0`
- `0x18000d7a0`
- `0x1800125e0`
- `0x1800136a0`
- `0x180014b88`
- `0x180017388`
- `0x180018658`
- `0x180019bc4`
- `0x18001a598`
- `0x18001a634`
- `0x18001a6c0`
- `0x18001af40`
- `0x18001b304`
- `0x18001b380`
- `0x18001b3fc`
- `0x180023168`
- `0x180023282`
- `0x18002939c`
- `0x18002d7c8`
- `0x18003261b`
- `0x1800326d0`

## pseudocode

```c
void __fastcall CReader::InitializeReaderName(CReader *this)
{
  unsigned int v2; // r9d
  unsigned int v3; // r9d
  const WCHAR *v4; // rbx
  const WCHAR *v5; // rdx
  unsigned int v6; // r8d
  const unsigned __int8 *v7; // rcx
  const unsigned __int16 *v8; // r9
  unsigned int ReaderAttr; // eax
  int v10; // eax
  unsigned int v11; // ebx
  const unsigned __int8 *v12; // rax
  ulong pExceptionObject; // [rsp+30h] [rbp-168h] BYREF
  ulong v14; // [rsp+34h] [rbp-164h] BYREF
  CReader *v15; // [rsp+38h] [rbp-160h]
  _BYTE v16[8]; // [rsp+40h] [rbp-158h] BYREF
  void *Block; // [rsp+48h] [rbp-150h]
  int v18; // [rsp+50h] [rbp-148h]
  int v19; // [rsp+54h] [rbp-144h]
  void **v20; // [rsp+60h] [rbp-138h] BYREF
  int v21; // [rsp+68h] [rbp-130h]
  void **v22; // [rsp+70h] [rbp-128h]
  __int64 v23; // [rsp+78h] [rbp-120h]
  __int64 v24; // [rsp+80h] [rbp-118h]
  void **v25; // [rsp+88h] [rbp-110h]
  __int64 v26; // [rsp+90h] [rbp-108h]
  __int64 v27; // [rsp+98h] [rbp-100h]
  void **v28; // [rsp+A0h] [rbp-F8h] BYREF
  int v29; // [rsp+A8h] [rbp-F0h]
  void **v30; // [rsp+B0h] [rbp-E8h]
  __int64 v31; // [rsp+B8h] [rbp-E0h]
  __int64 v32; // [rsp+C0h] [rbp-D8h]
  void **v33; // [rsp+C8h] [rbp-D0h]
  __int64 v34; // [rsp+D0h] [rbp-C8h]
  __int64 v35; // [rsp+D8h] [rbp-C0h]
  void **v36; // [rsp+E0h] [rbp-B8h] BYREF
  int v37; // [rsp+E8h] [rbp-B0h]
  void **v38; // [rsp+F0h] [rbp-A8h]
  __int64 v39; // [rsp+F8h] [rbp-A0h]
  __int64 v40; // [rsp+100h] [rbp-98h]
  void **v41; // [rsp+108h] [rbp-90h]
  __int64 v42; // [rsp+110h] [rbp-88h]
  __int64 v43; // [rsp+118h] [rbp-80h]
  _BYTE v44[16]; // [rsp+120h] [rbp-78h] BYREF
  unsigned __int16 v45[32]; // [rsp+130h] [rbp-68h] BYREF
  ulong v46; // [rsp+170h] [rbp-28h] BYREF
  ulong v47; // [rsp+174h] [rbp-24h] BYREF
  ulong v48; // [rsp+178h] [rbp-20h] BYREF

  v15 = this;
  memset_0(v45, 0, sizeof(v45));
  v36 = &CTextString::`vftable';
  v38 = &CBuffer::`vftable';
  v39 = 0;
  v40 = 0;
  v41 = &CBuffer::`vftable';
  v42 = 0;
  v43 = 0;
  v37 = 3;
  v28 = &CTextString::`vftable';
  v30 = &CBuffer::`vftable';
  v31 = 0;
  v32 = 0;
  v33 = &CBuffer::`vftable';
  v34 = 0;
  v35 = 0;
  v29 = 3;
  v20 = &CTextString::`vftable';
  v22 = &CBuffer::`vftable';
  v23 = 0;
  v24 = 0;
  v25 = &CBuffer::`vftable';
  v26 = 0;
  v27 = 0;
  v21 = 3;
  CBuffer::CBuffer((CBuffer *)v16, 0x24u);
  CLockWrite::CLockWrite((CLockWrite *)v44, (CReader *)((char *)this + 56));
  try
  {
    CReader::GetReaderAttr(this, 65792, (struct CBuffer *)v16, v2);
    if ( v18 )
    {
      CBuffer::Append((CBuffer *)v16, &qword_180040A90, 1u);
      v4 = &Data;
      v5 = &Data;
      if ( v19 )
        v5 = (const WCHAR *)Block;
      CTextString::operator=(&v36, v5);
    }
    else
    {
      v4 = &Data;
    }
  }
  catch ( ulong v46 )
  {
    LODWORD(v40) = 0;
    LODWORD(v43) = 0;
    v37 = 3;
    v4 = &Data;
  }
  catch ( ... )
  {
    LODWORD(v40) = 0;
    LODWORD(v43) = 0;
    v37 = 3;
    v4 = &Data;
  }
  try
  {
    CReader::GetReaderAttr(v15, 65793, (struct CBuffer *)v16, v3);
    if ( v18 )
    {
      CBuffer::Append((CBuffer *)v16, &qword_180040A90, 1u);
      if ( v19 )
        v4 = (const WCHAR *)Block;
      CTextString::operator=(&v28, v4);
    }
  }
  catch ( ulong v47 )
  {
    LODWORD(v32) = 0;
    LODWORD(v35) = 0;
    v29 = 3;
  }
  catch ( ... )
  {
    LODWORD(v32) = 0;
    LODWORD(v35) = 0;
    v29 = 3;
  }
  if ( !CTextString::Length((CTextString *)&v36) && !CTextString::Length((CTextString *)&v28) )
  {
    CalaisError(v7, 0x196u, 0, v8);
    pExceptionObject = -2146435046;
    throw &pExceptionObject;
  }
  try
  {
    ReaderAttr = CReader::GetReaderAttr(v15, 2147418113, v6);
    v10 = StringCbPrintfW(v45, 0x40u, L"%lu", ReaderAttr);
    if ( v10 < 0 )
    {
      v14 = (unsigned __int16)v10;
      throw &v14;
    }
  }
  catch ( ulong v48 )
  {
    v45[0] = 0;
  }
  catch ( ... )
  {
    v45[0] = 0;
  }
  LODWORD(v24) = 0;
  LODWORD(v27) = 0;
  v21 = 3;
  if ( CTextString::Length((CTextString *)&v36) )
    CTextString::operator+=(&v20, &v36);
  if ( CTextString::Length((CTextString *)&v28) )
  {
    if ( CTextString::Length((CTextString *)&v20) )
      CTextString::operator+=((CTextString *)&v20, " ");
    CTextString::operator+=(&v20, &v28);
  }
  if ( v45[0] )
  {
    if ( CTextString::Length((CTextString *)&v20) )
      CTextString::operator+=((CTextString *)&v20, " ");
    CTextString::operator+=((CTextString *)&v20, (unsigned __int8 *)v45);
  }
  v11 = 2 * CTextString::Length((CTextString *)&v20) + 2;
  v12 = (const unsigned __int8 *)CTextString::Unicode((CTextString *)&v20);
  CBuffer::Set((CReader *)((char *)v15 + 8), v12, v11);
  CLockWrite::~CLockWrite((CLockWrite *)v44);
  if ( Block )
    operator delete[](Block);
  CTextString::~CTextString((CTextString *)&v20);
  CTextString::~CTextString((CTextString *)&v28);
  CTextString::~CTextString((CTextString *)&v36);
}

```

## disassembly

```asm
0x18001af40  mov     r11, rsp
0x18001af43  mov     [r11+10h], rbx
0x18001af47  push    rdi
0x18001af48  sub     rsp, 190h
0x18001af4f  mov     rax, cs:__security_cookie
0x18001af56  xor     rax, rsp
0x18001af59  mov     [rsp+198h+var_18], rax
0x18001af61  mov     rbx, rcx
0x18001af64  mov     [rsp+198h+var_160], rcx
0x18001af69  xor     edx, edx; Val
0x18001af6b  lea     r8d, [rdx+40h]; Size
0x18001af6f  lea     rcx, [r11-68h]; void *
0x18001af73  call    memset_0
0x18001af78  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18001af7f  mov     [rsp+198h+var_B8], rax
0x18001af87  lea     rcx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001af8e  mov     [rsp+198h+var_A8], rcx
0x18001af96  xor     edi, edi
0x18001af98  mov     [rsp+198h+var_A0], rdi
0x18001afa0  mov     [rsp+198h+var_98], rdi
0x18001afa8  mov     [rsp+198h+var_90], rcx
0x18001afb0  mov     [rsp+198h+var_88], rdi
0x18001afb8  mov     [rsp+198h+var_80], rdi
0x18001afc0  mov     [rsp+198h+var_B0], 3
0x18001afcb  mov     [rsp+198h+var_F8], rax
0x18001afd3  mov     [rsp+198h+var_E8], rcx
0x18001afdb  mov     [rsp+198h+var_E0], rdi
0x18001afe3  mov     [rsp+198h+var_D8], rdi
0x18001afeb  mov     [rsp+198h+var_D0], rcx
0x18001aff3  mov     [rsp+198h+var_C8], rdi
0x18001affb  mov     [rsp+198h+var_C0], rdi
0x18001b003  mov     [rsp+198h+var_F0], 3
0x18001b00e  mov     [rsp+198h+var_138], rax
0x18001b013  mov     [rsp+198h+var_128], rcx
0x18001b018  mov     [rsp+198h+var_120], rdi
0x18001b01d  mov     [rsp+198h+var_118], rdi
0x18001b025  mov     [rsp+198h+var_110], rcx
0x18001b02d  mov     [rsp+198h+var_108], rdi
0x18001b035  mov     [rsp+198h+var_100], rdi
0x18001b03d  mov     [rsp+198h+var_130], 3
0x18001b045  lea     edx, [rdi+24h]; unsigned int
0x18001b048  lea     rcx, [rsp+198h+var_158]; this
0x18001b04d  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x18001b052  nop
0x18001b053  lea     rdx, [rbx+38h]; struct CAccessLock *
0x18001b057  lea     rcx, [rsp+198h+var_78]; this
0x18001b05f  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18001b064  nop
0x18001b065  lea     r8, [rsp+198h+var_158]; struct CBuffer *
0x18001b06a  mov     edx, 10100h; unsigned int
0x18001b06f  mov     rcx, rbx; this
0x18001b072  call    ?GetReaderAttr@CReader@@QEAAXKAEAVCBuffer@@H@Z; CReader::GetReaderAttr(ulong,CBuffer &,int)
0x18001b077  cmp     [rsp+198h+var_148], edi
0x18001b07b  jz      short loc_18001B0B5
0x18001b07d  lea     r8d, [rdi+1]; unsigned int
0x18001b081  lea     rdx, qword_180040A90; unsigned __int8 *
0x18001b088  lea     rcx, [rsp+198h+var_158]; this
0x18001b08d  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18001b092  lea     rbx, Data
0x18001b099  mov     rdx, rbx
0x18001b09c  cmp     [rsp+198h+var_144], edi
0x18001b0a0  cmova   rdx, [rsp+198h+Block]
0x18001b0a6  lea     rcx, [rsp+198h+var_B8]
0x18001b0ae  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x18001b0b3  jmp     short loc_18001B0BC
0x18001b0b5  lea     rbx, Data
0x18001b0bc  jmp     short loc_18001B0C9
0x18001b0be  jmp     short $+2
0x18001b0c0  lea     rbx, Data
0x18001b0c7  xor     edi, edi
0x18001b0c9  lea     r8, [rsp+198h+var_158]; struct CBuffer *
0x18001b0ce  mov     edx, 10101h; unsigned int
0x18001b0d3  mov     rcx, [rsp+198h+var_160]; this
0x18001b0d8  call    ?GetReaderAttr@CReader@@QEAAXKAEAVCBuffer@@H@Z; CReader::GetReaderAttr(ulong,CBuffer &,int)
0x18001b0dd  cmp     [rsp+198h+var_148], edi
0x18001b0e1  jz      short loc_18001B115
0x18001b0e3  mov     r8d, 1; unsigned int
0x18001b0e9  lea     rdx, qword_180040A90; unsigned __int8 *
0x18001b0f0  lea     rcx, [rsp+198h+var_158]; this
0x18001b0f5  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18001b0fa  cmp     [rsp+198h+var_144], edi
0x18001b0fe  cmova   rbx, [rsp+198h+Block]
0x18001b104  mov     rdx, rbx
0x18001b107  lea     rcx, [rsp+198h+var_F8]
0x18001b10f  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x18001b114  nop
0x18001b115  jmp     short loc_18001B11B
0x18001b117  jmp     short $+2
0x18001b119  xor     edi, edi
0x18001b11b  lea     rcx, [rsp+198h+var_B8]; this
0x18001b123  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b128  test    eax, eax
0x18001b12a  jnz     short loc_18001B164
0x18001b12c  lea     rcx, [rsp+198h+var_F8]; this
0x18001b134  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b139  test    eax, eax
0x18001b13b  jnz     short loc_18001B164
0x18001b13d  xor     r8d, r8d; unsigned __int16 *
0x18001b140  mov     edx, 196h; unsigned int
0x18001b145  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18001b14a  mov     [rsp+198h+pExceptionObject], 8010001Ah
0x18001b152  lea     rdx, _TI1K; pThrowInfo
0x18001b159  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18001b15e  call    _CxxThrowException_0
0x18001b164  mov     edx, 7FFF0001h; unsigned int
0x18001b169  mov     rcx, [rsp+198h+var_160]; this
0x18001b16e  call    ?GetReaderAttr@CReader@@QEAAKKH@Z; CReader::GetReaderAttr(ulong,int)
0x18001b173  mov     r9d, eax
0x18001b176  lea     r8, aLu; "%lu"
0x18001b17d  mov     edx, 40h ; '@'; unsigned __int64
0x18001b182  lea     rcx, [rsp+198h+var_68]; unsigned __int16 *
0x18001b18a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b18f  test    eax, eax
0x18001b191  jns     short loc_18001B1AC
0x18001b193  movzx   eax, ax
0x18001b196  mov     [rsp+198h+var_164], eax
0x18001b19a  lea     rdx, _TI1K; pThrowInfo
0x18001b1a1  lea     rcx, [rsp+198h+var_164]; pExceptionObject
0x18001b1a6  call    _CxxThrowException_0
0x18001b1ac  jmp     short loc_18001B1B2
0x18001b1ae  jmp     short $+2
0x18001b1b0  xor     edi, edi
0x18001b1b2  mov     dword ptr [rsp+198h+var_118], edi
0x18001b1b9  mov     dword ptr [rsp+198h+var_100], edi
0x18001b1c0  mov     [rsp+198h+var_130], 3
0x18001b1c8  lea     rcx, [rsp+198h+var_B8]; this
0x18001b1d0  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b1d5  test    eax, eax
0x18001b1d7  jz      short loc_18001B1EB
0x18001b1d9  lea     rdx, [rsp+198h+var_B8]
0x18001b1e1  lea     rcx, [rsp+198h+var_138]
0x18001b1e6  call    ??YCTextString@@QEAAAEAV0@AEBV0@@Z; CTextString::operator+=(CTextString const &)
0x18001b1eb  lea     rcx, [rsp+198h+var_F8]; this
0x18001b1f3  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b1f8  test    eax, eax
0x18001b1fa  jz      short loc_18001B22D
0x18001b1fc  lea     rcx, [rsp+198h+var_138]; this
0x18001b201  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b206  test    eax, eax
0x18001b208  jz      short loc_18001B21B
0x18001b20a  lea     rdx, asc_18003BC60; " "
0x18001b211  lea     rcx, [rsp+198h+var_138]; this
0x18001b216  call    ??YCTextString@@QEAAPEBDPEBD@Z; CTextString::operator+=(char const *)
0x18001b21b  lea     rdx, [rsp+198h+var_F8]
0x18001b223  lea     rcx, [rsp+198h+var_138]
0x18001b228  call    ??YCTextString@@QEAAAEAV0@AEBV0@@Z; CTextString::operator+=(CTextString const &)
0x18001b22d  cmp     di, [rsp+198h+var_68]
0x18001b235  jz      short loc_18001B268
0x18001b237  lea     rcx, [rsp+198h+var_138]; this
0x18001b23c  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b241  test    eax, eax
0x18001b243  jz      short loc_18001B256
0x18001b245  lea     rdx, asc_18003BC60; " "
0x18001b24c  lea     rcx, [rsp+198h+var_138]; this
0x18001b251  call    ??YCTextString@@QEAAPEBDPEBD@Z; CTextString::operator+=(char const *)
0x18001b256  lea     rdx, [rsp+198h+var_68]; unsigned __int8 *
0x18001b25e  lea     rcx, [rsp+198h+var_138]; this
0x18001b263  call    ??YCTextString@@QEAAPEBGPEBG@Z; CTextString::operator+=(ushort const *)
0x18001b268  lea     rcx, [rsp+198h+var_138]; this
0x18001b26d  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001b272  lea     ebx, ds:2[rax*2]
0x18001b279  lea     rcx, [rsp+198h+var_138]; this
0x18001b27e  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18001b283  mov     rcx, [rsp+198h+var_160]
0x18001b288  add     rcx, 8; this
0x18001b28c  mov     r8d, ebx; unsigned int
0x18001b28f  mov     rdx, rax; unsigned __int8 *
0x18001b292  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18001b297  nop
0x18001b298  lea     rcx, [rsp+198h+var_78]; this
0x18001b2a0  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18001b2a5  nop
0x18001b2a6  mov     rcx, [rsp+198h+Block]; Block
0x18001b2ab  test    rcx, rcx
0x18001b2ae  jz      short loc_18001B2B6
0x18001b2b0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b2b5  nop
0x18001b2b6  lea     rcx, [rsp+198h+var_138]; this
0x18001b2bb  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18001b2c0  nop
0x18001b2c1  lea     rcx, [rsp+198h+var_F8]; this
0x18001b2c9  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18001b2ce  nop
0x18001b2cf  lea     rcx, [rsp+198h+var_B8]; this
0x18001b2d7  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18001b2dc  mov     rcx, [rsp+198h+var_18]
0x18001b2e4  xor     rcx, rsp; StackCookie
0x18001b2e7  call    __security_check_cookie
0x18001b2ec  mov     rbx, [rsp+198h+arg_8]
0x18001b2f4  add     rsp, 190h
0x18001b2fb  pop     rdi
0x18001b2fc  retn
```
