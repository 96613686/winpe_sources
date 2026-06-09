# HidForceFeedbackScheduler::AdvanceThread(unsigned __int64,unsigned __int64 *)

- ea: `0x180010dc0`
- end: `0x180011161`
- name: `?AdvanceThread@HidForceFeedbackScheduler@@AEAAJ_KPEA_K@Z`
- size: `929`
- prototype: `int(HidForceFeedbackScheduler *__hidden this, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180022188`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x180010204`
- `0x1800108f4`
- `0x180010dc0`
- `0x180016350`
- `0x18001a610`
- `0x18001d384`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackScheduler::AdvanceThread(
        HidForceFeedbackScheduler *this,
        unsigned __int64 a2,
        unsigned __int64 *a3)
{
  __int64 v5; // rax
  char v6; // cl
  HidForceFeedbackEffect **i; // rdi
  HidForceFeedbackEffect *v8; // rsi
  const struct std::nothrow_t *v9; // rdx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  char *v14; // rdi
  __int64 v15; // rax
  struct HidForceFeedbackEffect *v16; // rsi
  __int64 v17; // r15
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r14d
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  void *v26; // r14
  const struct std::nothrow_t *v27; // rdx
  const struct std::nothrow_t *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  char v31; // cl
  __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rcx
  unsigned __int64 v38; // [rsp+40h] [rbp-18h]
  const char *v39; // [rsp+48h] [rbp-10h] BYREF
  int v40; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int64 v41; // [rsp+A8h] [rbp+50h]
  int v42; // [rsp+B0h] [rbp+58h] BYREF
  unsigned __int64 v43; // [rsp+B8h] [rbp+60h] BYREF

  v41 = a2;
  *a3 = -1;
  v5 = _InterlockedExchange64((volatile __int64 *)this + 5, *((_QWORD *)this + 4));
  v6 = 0;
  if ( v5 != *((_QWORD *)this + 4) )
  {
    *((_QWORD *)this + 6) = v5;
    _mm_mfence();
    v6 = 1;
  }
  v38 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = *((_QWORD *)this + 4);
  _mm_mfence();
  if ( v6 )
  {
    for ( i = (HidForceFeedbackEffect **)((char *)this + 80); i != (HidForceFeedbackEffect **)((char *)this + 336); i += 2 )
    {
      v8 = i[1];
      if ( v8 )
      {
        HidForceFeedbackEffect::~HidForceFeedbackEffect(i[1]);
        operator delete(v8, v9);
      }
      i[1] = 0;
      _mm_mfence();
    }
    v10 = HidForceFeedbackDriver::Reset(*(HidForceFeedbackDriver **)this);
    if ( v10 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
    {
      v13 = qword_180069018 & 8;
      if ( v13 == qword_180069018 )
      {
        v40 = v10;
        v42 = 99;
        v43 = (unsigned __int64)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned __int8 *)&unk_18005AAF8,
          v11,
          v12,
          (__int64 **)&v43,
          (__int64)&v42,
          (__int64)&v40);
      }
    }
    a2 = v41;
  }
  v14 = (char *)this + 80;
  if ( (char *)this + 80 == (char *)this + 336 )
  {
LABEL_45:
    v31 = 0;
    v32 = _InterlockedExchange64((volatile __int64 *)this + 8, *((_QWORD *)this + 7));
    if ( v32 != *((_QWORD *)this + 7) )
    {
      *((_QWORD *)this + 9) = v32;
      _mm_mfence();
      v31 = 1;
    }
    v33 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = *((_QWORD *)this + 7);
    _mm_mfence();
    if ( v31 )
    {
      v34 = HidForceFeedbackDriver::SetGain(*(HidForceFeedbackDriver **)this, *(float *)&v33);
      if ( v34 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
      {
        v37 = qword_180069018 & 8;
        if ( v37 == qword_180069018 )
        {
          v40 = v34;
          v42 = 138;
          v43 = (unsigned __int64)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v37,
            (unsigned __int8 *)word_18005BA2A,
            v35,
            v36,
            (__int64 **)&v43,
            (__int64)&v42,
            (__int64)&v40);
        }
      }
    }
    return 0;
  }
  while ( 1 )
  {
    v15 = _InterlockedExchange64((volatile __int64 *)v14, 0);
    if ( v15 )
    {
      v16 = (struct HidForceFeedbackEffect *)*((_QWORD *)v14 + 1);
      *((_QWORD *)v14 + 1) = v15;
      _mm_mfence();
      LOBYTE(v15) = 1;
    }
    else
    {
      v16 = 0;
    }
    v17 = *((_QWORD *)v14 + 1);
    if ( !v17 )
      goto LABEL_34;
    if ( (_BYTE)v15 )
    {
      v20 = HidForceFeedbackEffect::Initialize(*((HidForceFeedbackEffect **)v14 + 1), v16, a2);
      if ( v20 < 0 )
        break;
    }
    if ( *(_QWORD *)(v17 + 24) > v38 )
    {
      v43 = -1;
      v21 = HidForceFeedbackEffect::Advance((HidForceFeedbackEffect *)v17, &v43, v41);
      if ( v21 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
      {
        v24 = qword_180069018 & 8;
        if ( v24 == qword_180069018 )
        {
          v40 = v21;
          v42 = 121;
          v39 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v24,
            (unsigned __int8 *)byte_18005B8A9,
            v22,
            v23,
            (__int64 **)&v39,
            (__int64)&v42,
            (__int64)&v40);
        }
      }
      v25 = *a3;
      if ( v43 < *a3 )
        v25 = v43;
      *a3 = v25;
      if ( !*(_DWORD *)(v17 + 20) )
      {
        v26 = (void *)*((_QWORD *)v14 + 1);
        if ( v26 )
        {
          HidForceFeedbackEffect::~HidForceFeedbackEffect(*((HidForceFeedbackEffect **)v14 + 1));
          operator delete(v26, v27);
        }
        *((_QWORD *)v14 + 1) = 0;
        _mm_mfence();
      }
    }
LABEL_34:
    if ( v16 )
    {
      HidForceFeedbackEffect::~HidForceFeedbackEffect(v16);
      operator delete(v16, v28);
    }
    v14 += 16;
    if ( v14 == (char *)this + 336 )
      goto LABEL_45;
    a2 = v41;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v40 = v20;
    v43 = (unsigned __int64)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
    v42 = 115;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&word_18005B5CE,
      v18,
      v19,
      (__int64 **)&v43,
      (__int64)&v42,
      (__int64)&v40);
  }
  if ( v16 )
  {
    HidForceFeedbackEffect::~HidForceFeedbackEffect(v16);
    operator delete(v16, v29);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180010dc0  mov     [rsp-40h+arg_8], rdx
0x180010dc5  push    rbp
0x180010dc6  push    rbx
0x180010dc7  push    rsi
0x180010dc8  push    rdi
0x180010dc9  push    r12
0x180010dcb  push    r13
0x180010dcd  push    r14
0x180010dcf  push    r15
0x180010dd1  mov     rbp, rsp
0x180010dd4  sub     rsp, 58h
0x180010dd8  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180010ddf  mov     rbx, rcx
0x180010de2  mov     rax, [rcx+20h]
0x180010de6  mov     r13, r8
0x180010de9  nop
0x180010dea  xchg    rax, [rcx+28h]
0x180010dee  xor     cl, cl
0x180010df0  nop
0x180010df1  cmp     rax, [rbx+20h]
0x180010df5  jz      short loc_180010E01
0x180010df7  nop
0x180010df8  mov     [rbx+30h], rax
0x180010dfc  mfence
0x180010dff  mov     cl, 1
0x180010e01  mov     rax, [rbx+30h]
0x180010e05  nop
0x180010e06  mov     [rbp+var_18], rax
0x180010e0a  mov     rax, [rbx+20h]
0x180010e0e  nop
0x180010e0f  mov     [rbx+30h], rax
0x180010e13  mfence
0x180010e16  lea     r15, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180010e1d  test    cl, cl
0x180010e1f  jz      loc_180010ECF
0x180010e25  lea     rdi, [rbx+50h]
0x180010e29  lea     r14, [rdi+100h]
0x180010e30  jmp     short loc_180010E5C
0x180010e32  mov     rsi, [rdi+8]
0x180010e36  nop
0x180010e37  test    rsi, rsi
0x180010e3a  jz      short loc_180010E4C
0x180010e3c  mov     rcx, rsi; this
0x180010e3f  call    ??1HidForceFeedbackEffect@@QEAA@XZ; HidForceFeedbackEffect::~HidForceFeedbackEffect(void)
0x180010e44  mov     rcx, rsi; P
0x180010e47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010e4c  nop
0x180010e4d  mov     qword ptr [rdi+8], 0
0x180010e55  mfence
0x180010e58  add     rdi, 10h
0x180010e5c  cmp     rdi, r14
0x180010e5f  jnz     short loc_180010E32
0x180010e61  mov     rcx, [rbx]; this
0x180010e64  call    ?Reset@HidForceFeedbackDriver@@QEAAJXZ; HidForceFeedbackDriver::Reset(void)
0x180010e69  test    eax, eax
0x180010e6b  jns     short loc_180010ECB
0x180010e6d  mov     ecx, cs:dword_180069000
0x180010e73  cmp     ecx, 2
0x180010e76  jbe     short loc_180010ECB
0x180010e78  mov     rdx, cs:qword_180069018
0x180010e7f  mov     rcx, cs:qword_180069010
0x180010e86  test    cl, 8
0x180010e89  jz      short loc_180010ECB
0x180010e8b  mov     rcx, rdx
0x180010e8e  and     ecx, 8
0x180010e91  cmp     rcx, rdx
0x180010e94  jnz     short loc_180010ECB
0x180010e96  mov     [rbp+arg_0], eax
0x180010e99  lea     rdx, unk_18005AAF8
0x180010ea0  lea     rax, [rbp+arg_0]
0x180010ea4  mov     [rbp+arg_10], 63h ; 'c'
0x180010eab  mov     [rsp+58h+var_28], rax
0x180010eb0  lea     rax, [rbp+arg_10]
0x180010eb4  mov     [rsp+58h+var_30], rax
0x180010eb9  lea     rax, [rbp+arg_18]
0x180010ebd  mov     [rsp+58h+var_38], rax
0x180010ec2  mov     [rbp+arg_18], r15
0x180010ec6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010ecb  mov     rdx, [rbp+arg_8]
0x180010ecf  lea     rdi, [rbx+50h]
0x180010ed3  lea     r12, [rdi+100h]
0x180010eda  cmp     rdi, r12
0x180010edd  jz      loc_1800110AE
0x180010ee3  xor     eax, eax
0x180010ee5  nop
0x180010ee6  xchg    rax, [rdi]
0x180010ee9  nop
0x180010eea  test    rax, rax
0x180010eed  jnz     short loc_180010EF3
0x180010eef  xor     esi, esi
0x180010ef1  jmp     short loc_180010F02
0x180010ef3  mov     rsi, [rdi+8]
0x180010ef7  nop
0x180010ef8  nop
0x180010ef9  mov     [rdi+8], rax
0x180010efd  mfence
0x180010f00  mov     al, 1
0x180010f02  mov     r15, [rdi+8]
0x180010f06  nop
0x180010f07  test    r15, r15
0x180010f0a  jz      loc_180010FFA
0x180010f10  test    al, al
0x180010f12  jz      short loc_180010F2D
0x180010f14  mov     r8, rdx; unsigned __int64
0x180010f17  mov     rcx, r15; this
0x180010f1a  mov     rdx, rsi; struct HidForceFeedbackEffect *
0x180010f1d  call    ?Initialize@HidForceFeedbackEffect@@QEAAJPEAV1@_K@Z; HidForceFeedbackEffect::Initialize(HidForceFeedbackEffect *,unsigned __int64)
0x180010f22  mov     r14d, eax
0x180010f25  test    eax, eax
0x180010f27  js      loc_180011025
0x180010f2d  mov     rax, [rbp+var_18]
0x180010f31  cmp     [r15+18h], rax
0x180010f35  jbe     loc_180010FFA
0x180010f3b  mov     r8, [rbp+arg_8]; unsigned __int64
0x180010f3f  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180010f43  mov     rcx, r15; this
0x180010f46  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x180010f4e  call    ?Advance@HidForceFeedbackEffect@@QEAAJPEA_K_K@Z; HidForceFeedbackEffect::Advance(unsigned __int64 *,unsigned __int64)
0x180010f53  test    eax, eax
0x180010f55  jns     short loc_180010FBC
0x180010f57  mov     ecx, cs:dword_180069000
0x180010f5d  cmp     ecx, 2
0x180010f60  jbe     short loc_180010FBC
0x180010f62  mov     rdx, cs:qword_180069018
0x180010f69  mov     rcx, cs:qword_180069010
0x180010f70  test    cl, 8
0x180010f73  jz      short loc_180010FBC
0x180010f75  mov     rcx, rdx
0x180010f78  and     ecx, 8
0x180010f7b  cmp     rcx, rdx
0x180010f7e  jnz     short loc_180010FBC
0x180010f80  mov     [rbp+arg_0], eax
0x180010f83  lea     rdx, byte_18005B8A9
0x180010f8a  lea     rax, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180010f91  mov     [rbp+arg_10], 79h ; 'y'
0x180010f98  mov     [rbp+var_10], rax
0x180010f9c  lea     rax, [rbp+arg_0]
0x180010fa0  mov     [rsp+58h+var_28], rax
0x180010fa5  lea     rax, [rbp+arg_10]
0x180010fa9  mov     [rsp+58h+var_30], rax
0x180010fae  lea     rax, [rbp+var_10]
0x180010fb2  mov     [rsp+58h+var_38], rax
0x180010fb7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010fbc  mov     rax, [r13+0]
0x180010fc0  cmp     [rbp+arg_18], rax
0x180010fc4  cmovb   rax, [rbp+arg_18]
0x180010fc9  mov     [r13+0], rax
0x180010fcd  cmp     dword ptr [r15+14h], 0
0x180010fd2  jnz     short loc_180010FFA
0x180010fd4  mov     r14, [rdi+8]
0x180010fd8  nop
0x180010fd9  test    r14, r14
0x180010fdc  jz      short loc_180010FEE
0x180010fde  mov     rcx, r14; this
0x180010fe1  call    ??1HidForceFeedbackEffect@@QEAA@XZ; HidForceFeedbackEffect::~HidForceFeedbackEffect(void)
0x180010fe6  mov     rcx, r14; P
0x180010fe9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010fee  nop
0x180010fef  mov     qword ptr [rdi+8], 0
0x180010ff7  mfence
0x180010ffa  test    rsi, rsi
0x180010ffd  jz      short loc_18001100F
0x180010fff  mov     rcx, rsi; this
0x180011002  call    ??1HidForceFeedbackEffect@@QEAA@XZ; HidForceFeedbackEffect::~HidForceFeedbackEffect(void)
0x180011007  mov     rcx, rsi; P
0x18001100a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001100f  add     rdi, 10h
0x180011013  cmp     rdi, r12
0x180011016  jz      loc_1800110A7
0x18001101c  mov     rdx, [rbp+arg_8]
0x180011020  jmp     loc_180010EE3
0x180011025  mov     eax, cs:dword_180069000
0x18001102b  cmp     eax, 2
0x18001102e  jbe     short loc_18001108A
0x180011030  mov     rcx, cs:qword_180069018
0x180011037  mov     rax, cs:qword_180069010
0x18001103e  test    al, 8
0x180011040  jz      short loc_18001108A
0x180011042  mov     rax, rcx
0x180011045  and     eax, 8
0x180011048  cmp     rax, rcx
0x18001104b  jnz     short loc_18001108A
0x18001104d  lea     rax, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180011054  mov     [rbp+arg_0], r14d
0x180011058  mov     [rbp+arg_18], rax
0x18001105c  lea     rdx, word_18005B5CE
0x180011063  lea     rax, [rbp+arg_0]
0x180011067  mov     [rbp+arg_10], 73h ; 's'
0x18001106e  mov     [rsp+58h+var_28], rax
0x180011073  lea     rax, [rbp+arg_10]
0x180011077  mov     [rsp+58h+var_30], rax
0x18001107c  lea     rax, [rbp+arg_18]
0x180011080  mov     [rsp+58h+var_38], rax
0x180011085  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001108a  test    rsi, rsi
0x18001108d  jz      short loc_18001109F
0x18001108f  mov     rcx, rsi; this
0x180011092  call    ??1HidForceFeedbackEffect@@QEAA@XZ; HidForceFeedbackEffect::~HidForceFeedbackEffect(void)
0x180011097  mov     rcx, rsi; P
0x18001109a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001109f  mov     eax, r14d
0x1800110a2  jmp     loc_18001114F
0x1800110a7  lea     r15, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800110ae  mov     rax, [rbx+38h]
0x1800110b2  xor     cl, cl
0x1800110b4  nop
0x1800110b5  xchg    rax, [rbx+40h]
0x1800110b9  nop
0x1800110ba  cmp     rax, [rbx+38h]
0x1800110be  jz      short loc_1800110CA
0x1800110c0  nop
0x1800110c1  mov     [rbx+48h], rax
0x1800110c5  mfence
0x1800110c8  mov     cl, 1
0x1800110ca  mov     rdx, [rbx+48h]
0x1800110ce  nop
0x1800110cf  mov     rax, [rbx+38h]
0x1800110d3  nop
0x1800110d4  mov     [rbx+48h], rax
0x1800110d8  mfence
0x1800110db  test    cl, cl
0x1800110dd  jz      short loc_18001114D
0x1800110df  mov     rcx, [rbx]; this
0x1800110e2  movd    xmm1, edx; float
0x1800110e6  call    ?SetGain@HidForceFeedbackDriver@@QEAAJM@Z; HidForceFeedbackDriver::SetGain(float)
0x1800110eb  test    eax, eax
0x1800110ed  jns     short loc_18001114D
0x1800110ef  mov     ecx, cs:dword_180069000
0x1800110f5  cmp     ecx, 2
0x1800110f8  jbe     short loc_18001114D
0x1800110fa  mov     rdx, cs:qword_180069018
0x180011101  mov     rcx, cs:qword_180069010
0x180011108  test    cl, 8
0x18001110b  jz      short loc_18001114D
0x18001110d  mov     rcx, rdx
0x180011110  and     ecx, 8
0x180011113  cmp     rcx, rdx
0x180011116  jnz     short loc_18001114D
0x180011118  mov     [rbp+arg_0], eax
0x18001111b  lea     rdx, word_18005BA2A
0x180011122  lea     rax, [rbp+arg_0]
0x180011126  mov     [rbp+arg_10], 8Ah
0x18001112d  mov     [rsp+58h+var_28], rax
0x180011132  lea     rax, [rbp+arg_10]
0x180011136  mov     [rsp+58h+var_30], rax
0x18001113b  lea     rax, [rbp+arg_18]
0x18001113f  mov     [rsp+58h+var_38], rax
0x180011144  mov     [rbp+arg_18], r15
0x180011148  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001114d  xor     eax, eax
0x18001114f  add     rsp, 58h
0x180011153  pop     r15
0x180011155  pop     r14
0x180011157  pop     r13
0x180011159  pop     r12
0x18001115b  pop     rdi
0x18001115c  pop     rsi
0x18001115d  pop     rbx
0x18001115e  pop     rbp
0x18001115f  retn
```
