# Broker::BrokerBase::RestoreEventFromBI(_GUID const &)

- ea: `0x1800188c0`
- end: `0x180018eb7`
- name: `?RestoreEventFromBI@BrokerBase@Broker@@AEAAXAEBU_GUID@@@Z`
- size: `1527`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011cd4`

## callees

- `0x180004d70`
- `0x180005b50`
- `0x180008340`
- `0x18000e8a4`
- `0x18000e9f4`
- `0x18000f648`
- `0x18000f794`
- `0x18001184c`
- `0x1800126e0`
- `0x180014a7c`
- `0x180014ed4`
- `0x180015af0`
- `0x1800165aa`
- `0x1800165da`
- `0x1800186a8`
- `0x1800188c0`
- `0x180019660`
- `0x18001e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::RestoreEventFromBI(Broker::BrokerBase *this, const struct _GUID *a2)
{
  size_t v4; // r14
  size_t v5; // rsi
  void **v6; // rax
  void **v7; // rbx
  void **v8; // rdx
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(_QWORD, void **, _QWORD); // rax
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  void *v15; // rsi
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  void **v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // r12d
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // r9
  PVOID v28; // rcx
  __int64 v29; // rdi
  char v30; // dl
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  Broker::BrokerBase *v34; // rbx
  void **v35; // rsi
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  char v41; // [rsp+60h] [rbp-1E8h] BYREF
  char v42; // [rsp+61h] [rbp-1E7h]
  unsigned int v43; // [rsp+64h] [rbp-1E4h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-1E0h] BYREF
  void *v45; // [rsp+70h] [rbp-1D8h] BYREF
  void *v46; // [rsp+78h] [rbp-1D0h] BYREF
  const struct _GUID *v47; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v48; // [rsp+88h] [rbp-1C0h] BYREF
  __int64 v49; // [rsp+90h] [rbp-1B8h] BYREF
  __int64 v50; // [rsp+98h] [rbp-1B0h] BYREF
  const struct _GUID *v51; // [rsp+A0h] [rbp-1A8h] BYREF
  const WCHAR *v52; // [rsp+A8h] [rbp-1A0h] BYREF
  void **v53; // [rsp+B0h] [rbp-198h]
  const struct _GUID *v54; // [rsp+B8h] [rbp-190h]
  Broker::BrokerBase *v55; // [rsp+C0h] [rbp-188h]
  __int128 v56; // [rsp+C8h] [rbp-180h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-170h]
  __int64 v58; // [rsp+E0h] [rbp-168h] BYREF
  __int128 v59; // [rsp+E8h] [rbp-160h] BYREF
  __int128 v60; // [rsp+F8h] [rbp-150h]
  _BYTE pExceptionObject[24]; // [rsp+108h] [rbp-140h] BYREF
  _BYTE v62[24]; // [rsp+120h] [rbp-128h] BYREF
  _BYTE v63[40]; // [rsp+138h] [rbp-110h] BYREF
  _BYTE v64[40]; // [rsp+160h] [rbp-E8h] BYREF
  __int128 v65; // [rsp+188h] [rbp-C0h] BYREF
  __int128 v66; // [rsp+198h] [rbp-B0h]
  void *v67[2]; // [rsp+1B0h] [rbp-98h] BYREF
  __int64 v68; // [rsp+1C0h] [rbp-88h]
  __int128 v69; // [rsp+1C8h] [rbp-80h]
  __int64 v70; // [rsp+1D8h] [rbp-70h]
  __int64 v71; // [rsp+1E0h] [rbp-68h]
  void *Src[2]; // [rsp+1E8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+1F8h] [rbp-50h]
  unsigned __int64 v74; // [rsp+200h] [rbp-48h]

  v55 = this;
  v54 = a2;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, a2);
  try
  {
    v53 = 0;
    v46 = 0;
    v49 = 0;
    v42 = 0;
    v43 = 1;
    v59 = 0;
    v60 = 0;
    v65 = 0;
    v66 = 0;
    LODWORD(v65) = -1;
    *(_OWORD *)v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 7;
    LOWORD(v69) = 0;
    *(_OWORD *)Src = 0;
    v73 = 0;
    v74 = 7;
    LOWORD(Src[0]) = 0;
    v56 = 0;
    v57 = 0;
    v44 = 0;
    Broker::BILayer::QueryEventInformation(
      (__int64)a2,
      (Broker::ApplicationIdentity *)v67,
      (_DWORD *)&v65 + 2,
      &v56,
      &v44);
    v4 = 2 * v73 + 2;
    v5 = (char *)v67[1] - (char *)v67[0];
    v6 = (void **)BciHeapAlloc((char *)v67[1] - (char *)v67[0] + 2 * v73 + 58);
    v7 = v6;
    v53 = v6;
    if ( !v6 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    *(struct _GUID *)v6 = *a2;
    *((_DWORD *)v6 + 10) = 0;
    *((_DWORD *)v6 + 11) = DWORD2(v65);
    v6[3] = v6 + 7;
    v6[4] = (char *)v6 + v4 + 56;
    v8 = Src;
    if ( v74 > 7 )
      v8 = (void **)Src[0];
    memcpy_0(v6 + 7, v8, v4);
    memcpy_0(v7[4], v67[0], v5);
    v10 = (__int64 (__fastcall *)(_QWORD, void **, _QWORD))*((_QWORD *)this + 12);
    if ( v10 )
    {
      v11 = v10(*((_QWORD *)this + 1), v7, (unsigned int)(DWORD2(v56) - v56));
      if ( v11 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)v63, v11);
        throw (Broker::Win32Error *)v63;
      }
    }
    if ( *((_QWORD *)this + 15) && *((_QWORD *)this + 16) )
    {
      if ( (DWORD2(v65) & 0x800000) != 0 )
      {
        Broker::BrokerBase::DecodeBrokeredEvent(v9, &v56, &v46);
        v15 = v46;
      }
      else
      {
        v16 = BciHeapAlloc(0x10u);
        v15 = v16;
        v46 = v16;
        if ( !v16 )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)v62);
          throw (std::bad_alloc *)v62;
        }
        DWORD2(v59) = 4;
        *(_QWORD *)&v59 = L"EventInformation";
        v12 = v56;
        *((_QWORD *)&v60 + 1) = v56;
        LOWORD(v60) = WORD4(v56) - v56;
        *(_WORD *)v16 = 1;
        v16[1] = &v59;
      }
      if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v12, 2, v13, v14) )
      {
        v45 = v7[4];
        v52 = (const WCHAR *)v7[3];
        v41 = 2;
        v51 = a2;
        v50 = *((_QWORD *)this + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>>(
          v17,
          byte_180021EE2,
          v18,
          v19,
          &v50,
          (__int64 *)&v51,
          (__int64)&v41,
          &v52,
          (__int64 *)&v45);
      }
      v20 = Src;
      if ( v74 > 7 )
        v20 = (void **)Src[0];
      v23 = (*((__int64 (__fastcall **)(__int64, _QWORD, void **, void *, void **, void *, _QWORD, _QWORD, __int64 *, unsigned int *, __int128 *))this
             + 15))(
              2,
              *((_QWORD *)this + 1),
              v7,
              v15,
              v20,
              v67[0],
              0,
              0,
              &v49,
              &v43,
              &v65);
      if ( (unsigned int)dword_180028000 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v21, v22) )
      {
        v44 = v43;
        LODWORD(v50) = DWORD2(v65);
        LODWORD(v51) = DWORD1(v65);
        LODWORD(v52) = v65;
        v58 = v49;
        LODWORD(v45) = v23;
        v47 = a2;
        v48 = *((_QWORD *)this + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v43,
          byte_180021E63,
          v24,
          v25,
          &v48,
          (__int64 *)&v47,
          (__int64)&v45,
          (__int64)&v58,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v50,
          (__int64)&v44);
      }
      if ( v23 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)v64, v23);
        throw (Broker::Win32Error *)v64;
      }
      v42 = 1;
      *((_DWORD *)v7 + 10) = DWORD1(v65);
      Broker::BrokerBase::RegisterEvent((_DWORD)this, 2, (_DWORD)v7, v65, v43, v49, SBYTE12(v66));
      BciHeapFree(v15);
      v46 = 0;
    }
    std::vector<unsigned char>::_Tidy(&v56);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v67);
  }
  catch ( ... )
  {
    v28 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = (__int64)v54;
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v54);
    }
    else
    {
      v29 = (__int64)v54;
    }
    if ( v42 )
    {
      if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v28, 2, v26, v27) )
      {
        v41 = v30;
        v48 = v29;
        v34 = v55;
        v47 = (const struct _GUID *)*((_QWORD *)v55 + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
          v31,
          byte_18002207A,
          v32,
          v33,
          (__int64 *)&v47,
          &v48,
          (__int64)&v41);
      }
      else
      {
        v34 = v55;
      }
      v35 = v53;
      v36 = (*((unsigned int (__fastcall **)(__int64, _QWORD, void **, __int64))v34 + 16))(
              2,
              *((_QWORD *)v34 + 1),
              v53,
              v49);
      if ( (unsigned int)dword_180028000 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v36, v37) )
        {
          LODWORD(v45) = v39;
          v48 = v29;
          v47 = (const struct _GUID *)*((_QWORD *)v34 + 1);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v38,
            byte_180021F3C,
            v39,
            v40,
            (__int64 *)&v47,
            &v48,
            (__int64)&v45);
        }
      }
    }
    else
    {
      v35 = v53;
    }
    BciHeapFree(v46);
    BciHeapFree(v35);
  }
}

```

## disassembly

```asm
0x1800188c0  mov     [rsp+arg_10], rbx
0x1800188c5  mov     [rsp+arg_18], rsi
0x1800188ca  push    rdi
0x1800188cb  push    r12
0x1800188cd  push    r13
0x1800188cf  push    r14
0x1800188d1  push    r15
0x1800188d3  sub     rsp, 220h
0x1800188da  mov     rax, cs:__security_cookie
0x1800188e1  xor     rax, rsp
0x1800188e4  mov     [rsp+248h+var_38], rax
0x1800188ec  mov     r15, rdx
0x1800188ef  mov     rdi, rcx
0x1800188f2  mov     [rsp+248h+var_188], rcx
0x1800188fa  mov     [rsp+248h+var_190], rdx
0x180018902  mov     rcx, cs:WPP_GLOBAL_Control
0x180018909  test    dword ptr [rcx+1Ch], 800h
0x180018910  jz      short loc_180018930
0x180018912  cmp     byte ptr [rcx+19h], 5
0x180018916  jb      short loc_180018930
0x180018918  mov     edx, 2Eh ; '.'
0x18001891d  mov     r9, r15
0x180018920  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180018927  mov     rcx, [rcx+10h]
0x18001892b  call    WPP_SF__guid_
0x180018930  xor     r13d, r13d
0x180018933  mov     [rsp+248h+var_198], r13
0x18001893b  mov     [rsp+248h+var_1D0], r13
0x180018940  mov     [rsp+248h+var_1B8], r13
0x180018948  mov     [rsp+248h+var_1E7], r13b
0x18001894d  lea     r12d, [r13+1]
0x180018951  mov     [rsp+248h+var_1E4], r12d
0x180018956  xorps   xmm0, xmm0
0x180018959  movups  [rsp+248h+var_160], xmm0
0x180018961  movups  [rsp+248h+var_150], xmm0
0x180018969  xorps   xmm1, xmm1
0x18001896c  movups  [rsp+248h+var_C0], xmm1
0x180018974  movups  [rsp+248h+var_B0], xmm1
0x18001897c  mov     dword ptr [rsp+248h+var_C0], 0FFFFFFFFh
0x180018987  movdqa  xmmword ptr [rsp+248h+var_98], xmm0
0x180018990  mov     [rsp+248h+var_88], r13
0x180018998  movups  [rsp+248h+var_80], xmm1
0x1800189a0  mov     [rsp+248h+var_70], r13
0x1800189a8  lea     ecx, [r13+7]
0x1800189ac  mov     [rsp+248h+var_68], rcx
0x1800189b4  mov     word ptr [rsp+248h+var_80], r13w
0x1800189bd  movups  xmmword ptr [rsp+248h+Src], xmm0
0x1800189c5  mov     [rsp+248h+var_50], r13
0x1800189cd  mov     [rsp+248h+var_48], rcx
0x1800189d5  mov     word ptr [rsp+248h+Src], r13w
0x1800189de  movdqu  [rsp+248h+var_180], xmm0
0x1800189e7  mov     [rsp+248h+var_170], r13
0x1800189ef  mov     [rsp+248h+var_1E0], r13d
0x1800189f4  lea     rax, [rsp+248h+var_1E0]
0x1800189f9  mov     [rsp+248h+var_228], rax
0x1800189fe  lea     r9, [rsp+248h+var_180]
0x180018a06  lea     r8, [rsp+248h+var_C0+8]
0x180018a0e  lea     rdx, [rsp+248h+var_98]
0x180018a16  mov     rcx, r15
0x180018a19  call    ?QueryEventInformation@BILayer@Broker@@YAXAEBU_GUID@@AEAUApplicationIdentity@2@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@2@Z; Broker::BILayer::QueryEventInformation(_GUID const &,Broker::ApplicationIdentity &,ulong &,std::vector<uchar> &,ulong &)
0x180018a1e  mov     rax, [rsp+248h+var_50]
0x180018a26  lea     r14, ds:2[rax*2]
0x180018a2e  mov     rsi, [rsp+248h+var_98+8]
0x180018a36  sub     rsi, [rsp+248h+var_98]
0x180018a3e  lea     rcx, [r14+38h]
0x180018a42  add     rcx, rsi; unsigned __int64
0x180018a45  call    ?BciHeapAlloc@@YAPEAX_K@Z; BciHeapAlloc(unsigned __int64)
0x180018a4a  mov     rbx, rax
0x180018a4d  mov     [rsp+248h+var_198], rax
0x180018a55  test    rax, rax
0x180018a58  jz      loc_180018E2C
0x180018a5e  movups  xmm0, xmmword ptr [r15]
0x180018a62  movdqu  xmmword ptr [rax], xmm0
0x180018a66  mov     [rax+28h], r13d
0x180018a6a  mov     eax, dword ptr [rsp+248h+var_C0+8]
0x180018a71  mov     [rbx+2Ch], eax
0x180018a74  lea     rcx, [rbx+38h]; void *
0x180018a78  mov     [rbx+18h], rcx
0x180018a7c  lea     rax, [r14+38h]
0x180018a80  add     rax, rbx
0x180018a83  mov     [rbx+20h], rax
0x180018a87  lea     rdx, [rsp+248h+Src]
0x180018a8f  cmp     [rsp+248h+var_48], 7
0x180018a98  cmova   rdx, [rsp+248h+Src]; Src
0x180018aa1  mov     r8, r14; Size
0x180018aa4  call    memcpy_0
0x180018aa9  mov     r8, rsi; Size
0x180018aac  mov     rdx, [rsp+248h+var_98]; Src
0x180018ab4  mov     rcx, [rbx+20h]; void *
0x180018ab8  call    memcpy_0
0x180018abd  mov     rax, [rdi+60h]
0x180018ac1  test    rax, rax
0x180018ac4  jz      short loc_180018AED
0x180018ac6  mov     r9, qword ptr [rsp+248h+var_180]
0x180018ace  mov     r8d, dword ptr [rsp+248h+var_180+8]
0x180018ad6  sub     r8d, r9d
0x180018ad9  mov     rdx, rbx
0x180018adc  mov     rcx, [rdi+8]
0x180018ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae5  test    eax, eax
0x180018ae7  jnz     loc_180018E4D
0x180018aed  cmp     [rdi+78h], r13
0x180018af1  jz      loc_180018DE3
0x180018af7  cmp     [rdi+80h], r13
0x180018afe  jz      loc_180018DE3
0x180018b04  test    dword ptr [rsp+248h+var_C0+8], 800000h
0x180018b0f  jz      short loc_180018B2A
0x180018b11  lea     r8, [rsp+248h+var_1D0]
0x180018b16  lea     rdx, [rsp+248h+var_180]
0x180018b1e  call    ?DecodeBrokeredEvent@BrokerBase@Broker@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAU_BR_EVENT_PARAMETERS@@@Z; Broker::BrokerBase::DecodeBrokeredEvent(std::vector<uchar> &,_BR_EVENT_PARAMETERS * *)
0x180018b23  mov     rsi, [rsp+248h+var_1D0]
0x180018b28  jmp     short loc_180018B92
0x180018b2a  mov     ecx, 10h; unsigned __int64
0x180018b2f  call    ?BciHeapAlloc@@YAPEAX_K@Z; BciHeapAlloc(unsigned __int64)
0x180018b34  mov     rsi, rax
0x180018b37  mov     [rsp+248h+var_1D0], rax
0x180018b3c  test    rax, rax
0x180018b3f  jz      loc_180018E70
0x180018b45  mov     dword ptr [rsp+248h+var_160+8], 4
0x180018b50  lea     rax, aEventinformati; "EventInformation"
0x180018b57  mov     qword ptr [rsp+248h+var_160], rax
0x180018b5f  mov     rcx, qword ptr [rsp+248h+var_180]
0x180018b67  mov     qword ptr [rsp+248h+var_150+8], rcx
0x180018b6f  movzx   eax, word ptr [rsp+248h+var_180+8]
0x180018b77  sub     ax, cx
0x180018b7a  mov     word ptr [rsp+248h+var_150], ax
0x180018b82  mov     [rsi], r12w
0x180018b86  lea     rax, [rsp+248h+var_160]
0x180018b8e  mov     [rsi+8], rax
0x180018b92  mov     eax, cs:dword_180028000
0x180018b98  mov     r14d, 2
0x180018b9e  cmp     eax, 4
0x180018ba1  jbe     loc_180018C28
0x180018ba7  mov     edx, r14d
0x180018baa  call    _tlgKeywordOn
0x180018baf  test    al, al
0x180018bb1  jz      short loc_180018C28
0x180018bb3  mov     rax, [rbx+20h]
0x180018bb7  mov     [rsp+248h+var_1D8], rax
0x180018bbc  mov     rax, [rbx+18h]
0x180018bc0  mov     [rsp+248h+var_1A0], rax
0x180018bc8  mov     [rsp+248h+var_1E8], r14b
0x180018bcd  mov     [rsp+248h+var_1A8], r15
0x180018bd5  mov     rax, [rdi+8]
0x180018bd9  mov     [rsp+248h+var_1B0], rax
0x180018be1  lea     rax, [rsp+248h+var_1D8]
0x180018be6  mov     [rsp+248h+var_208], rax
0x180018beb  lea     rax, [rsp+248h+var_1A0]
0x180018bf3  mov     [rsp+248h+var_210], rax
0x180018bf8  lea     rax, [rsp+248h+var_1E8]
0x180018bfd  mov     [rsp+248h+var_218], rax
0x180018c02  lea     rax, [rsp+248h+var_1A8]
0x180018c0a  mov     [rsp+248h+var_220], rax
0x180018c0f  lea     rax, [rsp+248h+var_1B0]
0x180018c17  mov     [rsp+248h+var_228], rax
0x180018c1c  lea     rdx, byte_180021EE2
0x180018c23  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSid<_SID>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &)
0x180018c28  mov     rcx, [rsp+248h+var_98]
0x180018c30  lea     rdx, [rsp+248h+Src]
0x180018c38  cmp     [rsp+248h+var_48], 7
0x180018c41  cmova   rdx, [rsp+248h+Src]
0x180018c4a  lea     rax, [rsp+248h+var_C0]
0x180018c52  mov     [rsp+248h+var_1F8], rax
0x180018c57  lea     rax, [rsp+248h+var_1E4]
0x180018c5c  mov     [rsp+248h+var_200], rax
0x180018c61  lea     rax, [rsp+248h+var_1B8]
0x180018c69  mov     [rsp+248h+var_208], rax
0x180018c6e  mov     [rsp+248h+var_210], r13
0x180018c73  mov     [rsp+248h+var_218], r13
0x180018c78  mov     [rsp+248h+var_220], rcx
0x180018c7d  mov     [rsp+248h+var_228], rdx
0x180018c82  mov     r9, rsi
0x180018c85  mov     r8, rbx
0x180018c88  mov     rdx, [rdi+8]
0x180018c8c  mov     ecx, r14d
0x180018c8f  mov     rax, [rdi+78h]
0x180018c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c98  mov     r12d, eax
0x180018c9b  mov     ecx, cs:dword_180028000
0x180018ca1  cmp     ecx, 4
0x180018ca4  jbe     loc_180018D83
0x180018caa  mov     rdx, r14
0x180018cad  call    _tlgKeywordOn
0x180018cb2  test    al, al
0x180018cb4  jz      loc_180018D83
0x180018cba  mov     ecx, [rsp+248h+var_1E4]
0x180018cbe  mov     [rsp+248h+var_1E0], ecx
0x180018cc2  mov     eax, dword ptr [rsp+248h+var_C0+8]
0x180018cc9  mov     dword ptr [rsp+248h+var_1B0], eax
0x180018cd0  mov     eax, dword ptr [rsp+248h+var_C0+4]
0x180018cd7  mov     dword ptr [rsp+248h+var_1A8], eax
0x180018cde  mov     eax, dword ptr [rsp+248h+var_C0]
0x180018ce5  mov     dword ptr [rsp+248h+var_1A0], eax
0x180018cec  mov     rax, [rsp+248h+var_1B8]
0x180018cf4  mov     [rsp+248h+var_168], rax
0x180018cfc  mov     dword ptr [rsp+248h+var_1D8], r12d
0x180018d01  mov     [rsp+248h+var_1C8], r15
0x180018d09  mov     rax, [rdi+8]
0x180018d0d  mov     [rsp+248h+var_1C0], rax
0x180018d15  lea     rax, [rsp+248h+var_1E0]
0x180018d1a  mov     [rsp+248h+var_1F0], rax
0x180018d1f  lea     rax, [rsp+248h+var_1B0]
0x180018d27  mov     [rsp+248h+var_1F8], rax
0x180018d2c  lea     rax, [rsp+248h+var_1A8]
0x180018d34  mov     [rsp+248h+var_200], rax
0x180018d39  lea     rax, [rsp+248h+var_1A0]
0x180018d41  mov     [rsp+248h+var_208], rax
0x180018d46  lea     rax, [rsp+248h+var_168]
0x180018d4e  mov     [rsp+248h+var_210], rax
0x180018d53  lea     rax, [rsp+248h+var_1D8]
0x180018d58  mov     [rsp+248h+var_218], rax
0x180018d5d  lea     rax, [rsp+248h+var_1C8]
0x180018d65  mov     [rsp+248h+var_220], rax
0x180018d6a  lea     rax, [rsp+248h+var_1C0]
0x180018d72  mov     [rsp+248h+var_228], rax
0x180018d77  lea     rdx, byte_180021E63
0x180018d7e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018d83  test    r12d, r12d
0x180018d86  jnz     loc_180018E91
0x180018d8c  mov     [rsp+248h+var_1E7], 1
0x180018d91  mov     eax, dword ptr [rsp+248h+var_C0+4]
0x180018d98  mov     [rbx+28h], eax
0x180018d9b  mov     [rsp+248h+var_208], r13
0x180018da0  mov     al, byte ptr [rsp+248h+var_B0+0Ch]
0x180018da7  mov     byte ptr [rsp+248h+var_218], al
0x180018dab  mov     rax, [rsp+248h+var_1B8]
0x180018db3  mov     [rsp+248h+var_220], rax
0x180018db8  mov     eax, [rsp+248h+var_1E4]
0x180018dbc  mov     dword ptr [rsp+248h+var_228], eax
0x180018dc0  mov     r9d, dword ptr [rsp+248h+var_C0]
0x180018dc8  mov     r8, rbx
0x180018dcb  mov     edx, r14d
0x180018dce  mov     rcx, rdi
0x180018dd1  call    ?RegisterEvent@BrokerBase@Broker@@QEAAXW4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@KKPEAXEPEAU_WNF_STATE_NAME@@PEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::RegisterEvent(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *,ulong,ulong,void *,uchar,_WNF_STATE_NAME *,std::shared_ptr<Broker::BrokerEvent> *)
0x180018dd6  mov     rcx, rsi; void *
0x180018dd9  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x180018dde  mov     [rsp+248h+var_1D0], r13
0x180018de3  lea     rcx, [rsp+248h+var_180]
0x180018deb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018df0  nop
0x180018df1  lea     rcx, [rsp+248h+var_98]; this
0x180018df9  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180018dfe  nop
0x180018dff  mov     rcx, [rsp+248h+var_38]
0x180018e07  xor     rcx, rsp; StackCookie
0x180018e0a  call    __security_check_cookie
0x180018e0f  lea     r11, [rsp+248h+var_28]
0x180018e17  mov     rbx, [r11+40h]
0x180018e1b  mov     rsi, [r11+48h]
0x180018e1f  mov     rsp, r11
0x180018e22  pop     r15
0x180018e24  pop     r14
0x180018e26  pop     r13
0x180018e28  pop     r12
0x180018e2a  pop     rdi
0x180018e2b  retn
0x180018e2c  lea     rcx, [rsp+248h+pExceptionObject]; this
0x180018e34  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180018e39  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180018e40  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x180018e48  call    _CxxThrowException_0
0x180018e4d  mov     edx, eax; unsigned int
0x180018e4f  lea     rcx, [rsp+248h+var_110]; this
0x180018e57  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180018e5c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180018e63  lea     rcx, [rsp+248h+var_110]; pExceptionObject
0x180018e6b  call    _CxxThrowException_0
0x180018e70  lea     rcx, [rsp+248h+var_128]; this
0x180018e78  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180018e7d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180018e84  lea     rcx, [rsp+248h+var_128]; pExceptionObject
0x180018e8c  call    _CxxThrowException_0
0x180018e91  mov     edx, r12d; unsigned int
0x180018e94  lea     rcx, [rsp+248h+var_E8]; this
0x180018e9c  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180018ea1  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180018ea8  lea     rcx, [rsp+248h+var_E8]; pExceptionObject
0x180018eb0  call    _CxxThrowException_0
```
