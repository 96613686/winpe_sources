# SectionCache::LoadSectionTable(void)

- ea: `0x180037da8`
- end: `0x1800381e9`
- name: `?LoadSectionTable@SectionCache@@AEAAXXZ`
- size: `1089`
- prototype: `void __fastcall(SectionCache *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180036588`

## callees

- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x18000a724`
- `0x18000c374`
- `0x180013cc4`
- `0x1800169e8`
- `0x180023548`
- `0x1800239c0`
- `0x1800249f0`
- `0x180028794`
- `0x1800362d8`
- `0x180036aa4`
- `0x180036d20`
- `0x180037da8`
- `0x1800384f8`
- `0x1800385ec`
- `0x180038fb4`
- `0x180038fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037dfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003814d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003814d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SectionCache::LoadSectionTable(RTL_SRWLOCK *this)
{
  unsigned int Ptr; // eax
  int v3; // r14d
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rdi
  char v7; // di
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h]
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  int v12; // [rsp+50h] [rbp-B0h]
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  char v15; // [rsp+78h] [rbp-88h]
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-58h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  _QWORD v20[4]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v21[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF
  RTL_SRWLOCK *v23; // [rsp+100h] [rbp+0h]
  __int64 Buf1; // [rsp+108h] [rbp+8h] BYREF
  __int64 v25; // [rsp+110h] [rbp+10h]
  unsigned int v26[2]; // [rsp+118h] [rbp+18h]

  Buf1 = 0;
  v25 = 0;
  *(_QWORD *)v26 = 0;
  Buffer::Buffer((Buffer *)v22, 0, 0, 1);
  v23 = this + 8;
  AcquireSRWLockExclusive(this + 8);
  if ( this[7].Ptr == (PVOID)-1LL || this[7].Ptr == 0 || !LOBYTE(this[9].Ptr) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 4317);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 4317;
    v11 = -1;
    v12 = 611;
    throw (EvtException *)&pExceptionObject;
  }
  RecordCache::Seek((RecordCache *)this, 0);
  Buffer::Set((Buffer *)v22, (const unsigned __int8 *)&Buf1, 0x18u);
  Buffer::SetCurrentIndex((Buffer *)v22, 0x18u);
  RecordCache::ReadBytes(&this->Ptr, (struct Buffer *)v22);
  if ( strcmp((const char *)&Buf1, "MTAFile") )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1500);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 1500;
    v11 = -1;
    v12 = 626;
    throw (EvtException *)&pExceptionObject;
  }
  Ptr = (unsigned int)this[135].Ptr;
  if ( (unsigned int)v25 > Ptr )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 15035);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 15035;
    v11 = -1;
    v12 = 631;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned int)v25 < Ptr )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 15034);
    }
    pExceptionObject = 0;
    v9 = 0;
    v10 = 15034;
    v11 = -1;
    v12 = 636;
    throw (EvtException *)&pExceptionObject;
  }
  SectionCache::SectionHeader::SectionHeader((SectionCache::SectionHeader *)&v17);
  Buffer::Buffer((Buffer *)v16, 0, 0, 1);
  Buffer::SetCurrentIndex((Buffer *)v16, v26[0]);
  RecordCache::ReadBytes(&this->Ptr, (struct Buffer *)v16);
  Buffer::SetCurrentIndex((Buffer *)v16, 0);
  v3 = -1;
  while ( ++v3 < v26[1] )
  {
    SectionCache::SectionHeader::Deserialize((SectionCache::SectionHeader *)&v17, (struct Buffer *)v16);
    v13[0] = v20[0];
    v13[1] = (__int64)(v20[1] - v20[0]) >> 1;
    v4 = MakeOrThrowOOM(&pExceptionObject, v13);
    utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(
      (_DWORD)this + 1088,
      (unsigned int)&v14,
      v5,
      v4,
      (__int64)&v17);
    v6 = v14;
    if ( !v15 )
    {
      if ( !v14 )
        goto LABEL_27;
      *(_DWORD *)(v14 + 56) = v17;
      *(_QWORD *)(v6 + 64) = v18;
      *(_QWORD *)(v6 + 72) = v19;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v6 + 80, v20);
      utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>>::operator=(v6 + 112, v21);
    }
    if ( v6 )
    {
      v7 = 0;
      goto LABEL_29;
    }
LABEL_27:
    v7 = 1;
LABEL_29:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 14;
      v11 = -1;
      v12 = 657;
      throw (EvtException *)&pExceptionObject;
    }
  }
  Buffer::~Buffer((Buffer *)v16);
  SectionCache::SectionHeader::~SectionHeader((SectionCache::SectionHeader *)&v17);
  ReleaseSRWLockExclusive(this + 8);
  Buffer::~Buffer((Buffer *)v22);
}

```

## disassembly

```asm
0x180037da8  push    rbp
0x180037daa  push    rbx
0x180037dab  push    rsi
0x180037dac  push    rdi
0x180037dad  push    r14
0x180037daf  push    r15
0x180037db1  lea     rbp, [rsp-38h]
0x180037db6  sub     rsp, 138h
0x180037dbd  mov     rax, cs:__security_cookie
0x180037dc4  xor     rax, rsp
0x180037dc7  mov     [rbp+60h+var_40], rax
0x180037dcb  mov     rsi, rcx
0x180037dce  xor     eax, eax
0x180037dd0  mov     [rbp+60h+Buf1], rax
0x180037dd4  xor     r15d, r15d
0x180037dd7  mov     [rbp+60h+var_50], r15
0x180037ddb  mov     qword ptr [rbp+60h+var_48], r15
0x180037ddf  mov     r9b, 1; bool
0x180037de2  xor     r8d, r8d; unsigned int
0x180037de5  xor     edx, edx; unsigned __int8 *
0x180037de7  lea     rcx, [rbp+60h+var_80]; this
0x180037deb  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180037df0  nop
0x180037df1  lea     rbx, [rsi+40h]
0x180037df5  mov     [rbp+60h+var_60], rbx
0x180037df9  mov     rcx, rbx; SRWLock
0x180037dfc  call    cs:__imp_AcquireSRWLockExclusive
0x180037e02  nop
0x180037e03  mov     rax, [rsi+38h]
0x180037e07  inc     rax
0x180037e0a  cmp     rax, 1
0x180037e0e  jbe     loc_180038179
0x180037e14  cmp     [rsi+48h], r15b
0x180037e18  jz      loc_180038179
0x180037e1e  xor     edx, edx; unsigned __int64
0x180037e20  mov     rcx, rsi; this
0x180037e23  call    ?Seek@RecordCache@@IEAAX_K@Z; RecordCache::Seek(unsigned __int64)
0x180037e28  lea     edi, [r15+18h]
0x180037e2c  mov     r8d, edi; unsigned int
0x180037e2f  lea     rdx, [rbp+60h+Buf1]; unsigned __int8 *
0x180037e33  lea     rcx, [rbp+60h+var_80]; this
0x180037e37  call    ?Set@Buffer@@QEAAXPEBEK@Z; Buffer::Set(uchar const *,ulong)
0x180037e3c  mov     edx, edi; unsigned int
0x180037e3e  lea     rcx, [rbp+60h+var_80]; this
0x180037e42  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037e47  lea     rdx, [rbp+60h+var_80]; struct Buffer *
0x180037e4b  mov     rcx, rsi; this
0x180037e4e  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x180037e53  lea     r8d, [r15+8]; Size
0x180037e57  lea     rdx, aMtafile; "MTAFile"
0x180037e5e  lea     rcx, [rbp+60h+Buf1]; Buf1
0x180037e62  call    memcmp_0
0x180037e67  test    eax, eax
0x180037e69  jz      short loc_180037ED9
0x180037e6b  lea     rax, WPP_GLOBAL_Control
0x180037e72  mov     ebx, 5DCh
0x180037e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e7e  cmp     rcx, rax
0x180037e81  jz      short loc_180037EA5
0x180037e83  test    byte ptr [rcx+1Ch], 1
0x180037e87  jz      short loc_180037EA5
0x180037e89  cmp     byte ptr [rcx+19h], 2
0x180037e8d  jb      short loc_180037EA5
0x180037e8f  lea     edx, [rdi+6]
0x180037e92  mov     r9d, ebx
0x180037e95  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037e9c  mov     rcx, [rcx+10h]
0x180037ea0  call    WPP_SF_D
0x180037ea5  xorps   xmm0, xmm0
0x180037ea8  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037eae  mov     [rsp+160h+var_120], r15
0x180037eb3  mov     [rsp+160h+var_118], ebx
0x180037eb7  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037ebf  mov     [rsp+160h+var_110], 272h
0x180037ec7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037ece  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037ed3  call    _CxxThrowException_0
0x180037ed9  mov     eax, [rsi+438h]
0x180037edf  cmp     dword ptr [rbp+60h+var_50], eax
0x180037ee2  jbe     short loc_180037F54
0x180037ee4  lea     rax, WPP_GLOBAL_Control
0x180037eeb  mov     ebx, 3ABBh
0x180037ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ef7  cmp     rcx, rax
0x180037efa  jz      short loc_180037F20
0x180037efc  test    byte ptr [rcx+1Ch], 1
0x180037f00  jz      short loc_180037F20
0x180037f02  cmp     byte ptr [rcx+19h], 2
0x180037f06  jb      short loc_180037F20
0x180037f08  mov     edx, 1Fh
0x180037f0d  mov     r9d, ebx
0x180037f10  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037f17  mov     rcx, [rcx+10h]
0x180037f1b  call    WPP_SF_D
0x180037f20  xorps   xmm0, xmm0
0x180037f23  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037f29  mov     [rsp+160h+var_120], r15
0x180037f2e  mov     [rsp+160h+var_118], ebx
0x180037f32  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037f3a  mov     [rsp+160h+var_110], 277h
0x180037f42  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037f49  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037f4e  call    _CxxThrowException_0
0x180037f54  jnb     short loc_180037FC6
0x180037f56  lea     rax, WPP_GLOBAL_Control
0x180037f5d  mov     ebx, 3ABAh
0x180037f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f69  cmp     rcx, rax
0x180037f6c  jz      short loc_180037F92
0x180037f6e  test    byte ptr [rcx+1Ch], 1
0x180037f72  jz      short loc_180037F92
0x180037f74  cmp     byte ptr [rcx+19h], 2
0x180037f78  jb      short loc_180037F92
0x180037f7a  mov     edx, 20h ; ' '
0x180037f7f  mov     r9d, ebx
0x180037f82  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037f89  mov     rcx, [rcx+10h]
0x180037f8d  call    WPP_SF_D
0x180037f92  xorps   xmm0, xmm0
0x180037f95  movdqu  [rsp+160h+pExceptionObject], xmm0
0x180037f9b  mov     [rsp+160h+var_120], r15
0x180037fa0  mov     [rsp+160h+var_118], ebx
0x180037fa4  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x180037fac  mov     [rsp+160h+var_110], 27Ch
0x180037fb4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037fbb  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180037fc0  call    _CxxThrowException_0
0x180037fc6  lea     rcx, [rbp+60h+var_C0]; this
0x180037fca  call    ??0SectionHeader@SectionCache@@QEAA@XZ; SectionCache::SectionHeader::SectionHeader(void)
0x180037fcf  nop
0x180037fd0  mov     r9b, 1; bool
0x180037fd3  xor     r8d, r8d; unsigned int
0x180037fd6  xor     edx, edx; unsigned __int8 *
0x180037fd8  lea     rcx, [rbp+60h+var_E0]; this
0x180037fdc  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x180037fe1  nop
0x180037fe2  mov     edx, [rbp+60h+var_48]; unsigned int
0x180037fe5  lea     rcx, [rbp+60h+var_E0]; this
0x180037fe9  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037fee  lea     rdx, [rbp+60h+var_E0]; struct Buffer *
0x180037ff2  mov     rcx, rsi; this
0x180037ff5  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x180037ffa  xor     edx, edx; unsigned int
0x180037ffc  lea     rcx, [rbp+60h+var_E0]; this
0x180038000  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180038005  or      r14d, 0FFFFFFFFh
0x180038009  inc     r14d
0x18003800c  cmp     r14d, [rbp+60h+var_48+4]
0x180038010  jnb     loc_180038136
0x180038016  lea     rdx, [rbp+60h+var_E0]; struct Buffer *
0x18003801a  lea     rcx, [rbp+60h+var_C0]; this
0x18003801e  call    ?Deserialize@SectionHeader@SectionCache@@QEAAXAEAVBuffer@@@Z; SectionCache::SectionHeader::Deserialize(Buffer &)
0x180038023  mov     rax, [rbp+60h+var_A8]
0x180038027  mov     [rsp+160h+var_100], rax
0x18003802c  mov     rcx, [rbp+60h+var_A0]
0x180038030  sub     rcx, rax
0x180038033  sar     rcx, 1
0x180038036  mov     [rsp+160h+var_F8], rcx
0x18003803b  lea     rdx, [rsp+160h+var_100]
0x180038040  lea     rcx, [rsp+160h+pExceptionObject]
0x180038045  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18003804a  lea     rcx, [rsi+440h]
0x180038051  lea     rdx, [rbp+60h+var_C0]
0x180038055  mov     [rsp+160h+var_140], rdx
0x18003805a  mov     r9, rax
0x18003805d  lea     rdx, [rsp+160h+var_F0]
0x180038062  call    ??$_TryEmplace@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAUSectionHeader@SectionCache@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,SectionCache::SectionHeader &&)
0x180038067  mov     rdi, [rsp+160h+var_F0]
0x18003806c  cmp     [rsp+160h+var_E8], r15b
0x180038071  jnz     short loc_1800380A8
0x180038073  test    rdi, rdi
0x180038076  jz      short loc_1800380AD
0x180038078  mov     eax, [rbp+60h+var_C0]
0x18003807b  mov     [rdi+38h], eax
0x18003807e  mov     rax, [rbp+60h+var_B8]
0x180038082  mov     [rdi+40h], rax
0x180038086  mov     rax, [rbp+60h+var_B0]
0x18003808a  mov     [rdi+48h], rax
0x18003808e  lea     rcx, [rdi+50h]
0x180038092  lea     rdx, [rbp+60h+var_A8]
0x180038096  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18003809b  lea     rcx, [rdi+70h]
0x18003809f  lea     rdx, [rbp+60h+var_88]
0x1800380a3  call    ??4?$unique_ptr@VValuesRenderContext@@U?$default_delete@VValuesRenderContext@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>>::operator=(utl::unique_ptr<ValuesRenderContext,utl::default_delete<ValuesRenderContext>> &&)
0x1800380a8  test    rdi, rdi
0x1800380ab  jnz     short loc_1800380B2
0x1800380ad  mov     dil, 1
0x1800380b0  jmp     short loc_1800380B5
0x1800380b2  mov     dil, r15b
0x1800380b5  lea     rcx, [rsp+160h+pExceptionObject]
0x1800380ba  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800380bf  test    dil, dil
0x1800380c2  jz      loc_180038009
0x1800380c8  lea     rax, WPP_GLOBAL_Control
0x1800380cf  mov     ebx, 0Eh
0x1800380d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380db  cmp     rcx, rax
0x1800380de  jz      short loc_180038102
0x1800380e0  test    byte ptr [rcx+1Ch], 1
0x1800380e4  jz      short loc_180038102
0x1800380e6  cmp     byte ptr [rcx+19h], 2
0x1800380ea  jb      short loc_180038102
0x1800380ec  lea     edx, [rbx+13h]
0x1800380ef  mov     r9d, ebx
0x1800380f2  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800380f9  mov     rcx, [rcx+10h]
0x1800380fd  call    WPP_SF_D
0x180038102  xorps   xmm0, xmm0
0x180038105  movdqu  [rsp+160h+pExceptionObject], xmm0
0x18003810b  mov     [rsp+160h+var_120], r15
0x180038110  mov     [rsp+160h+var_118], ebx
0x180038114  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x18003811c  mov     [rsp+160h+var_110], 291h
0x180038124  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003812b  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x180038130  call    _CxxThrowException_0
0x180038136  lea     rcx, [rbp+60h+var_E0]; this
0x18003813a  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003813f  nop
0x180038140  lea     rcx, [rbp+60h+var_C0]; this
0x180038144  call    ??1SectionHeader@SectionCache@@QEAA@XZ; SectionCache::SectionHeader::~SectionHeader(void)
0x180038149  nop
0x18003814a  mov     rcx, rbx; SRWLock
0x18003814d  call    cs:__imp_ReleaseSRWLockExclusive
0x180038153  nop
0x180038154  lea     rcx, [rbp+60h+var_80]; this
0x180038158  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003815d  mov     rcx, [rbp+60h+var_40]
0x180038161  xor     rcx, rsp; StackCookie
0x180038164  call    __security_check_cookie
0x180038169  add     rsp, 138h
0x180038170  pop     r15
0x180038172  pop     r14
0x180038174  pop     rdi
0x180038175  pop     rsi
0x180038176  pop     rbx
0x180038177  pop     rbp
0x180038178  retn
0x180038179  lea     rax, WPP_GLOBAL_Control
0x180038180  mov     ebx, 10DDh
0x180038185  mov     rcx, cs:WPP_GLOBAL_Control
0x18003818c  cmp     rcx, rax
0x18003818f  jz      short loc_1800381B5
0x180038191  test    byte ptr [rcx+1Ch], 1
0x180038195  jz      short loc_1800381B5
0x180038197  cmp     byte ptr [rcx+19h], 2
0x18003819b  jb      short loc_1800381B5
0x18003819d  mov     edx, 1Dh
0x1800381a2  mov     r9d, ebx
0x1800381a5  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800381ac  mov     rcx, [rcx+10h]
0x1800381b0  call    WPP_SF_D
0x1800381b5  xorps   xmm0, xmm0
0x1800381b8  movdqu  [rsp+160h+pExceptionObject], xmm0
0x1800381be  mov     [rsp+160h+var_120], r15
0x1800381c3  mov     [rsp+160h+var_118], ebx
0x1800381c7  mov     [rsp+160h+var_114], 0FFFFFFFFh
0x1800381cf  mov     [rsp+160h+var_110], 263h
0x1800381d7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800381de  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800381e3  call    _CxxThrowException_0
```
