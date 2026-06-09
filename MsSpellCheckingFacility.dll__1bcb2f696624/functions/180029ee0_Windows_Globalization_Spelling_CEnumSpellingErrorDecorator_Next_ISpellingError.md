# Windows::Globalization::Spelling::CEnumSpellingErrorDecorator::Next(ISpellingError * *)

- ea: `0x180029ee0`
- end: `0x18002a27b`
- name: `?Next@CEnumSpellingErrorDecorator@Spelling@Globalization@Windows@@UEAAJPEAPEAUISpellingError@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CEnumSpellingErrorDecorator *__hidden this, struct ISpellingError **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180029ee0`
- `0x18002a30c`
- `0x18002a3d8`
- `0x18002a4e0`
- `0x18002a5e0`
- `0x18002a708`
- `0x18002a7c0`
- `0x18002a8cc`
- `0x1800511f4`
- `0x180061320`
- `0x180070908`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180029f87`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180029f87`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029fab`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029fab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180029fc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180029fc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Globalization::Spelling::CEnumSpellingErrorDecorator::Next(
        Windows::Globalization::Spelling::CEnumSpellingErrorDecorator *this,
        struct ISpellingError **a2,
        __int64 a3)
{
  int v5; // r13d
  int FirstErrorAtOrAfterIndex; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rdx
  int v10; // ecx
  int v11; // r9d
  int v12; // edx
  char *v13; // rsi
  char *v14; // rcx
  __int64 v15; // rax
  int v16; // r9d
  char *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r15
  char *v21; // rcx
  bool v22; // si
  struct ISpellingError *v23; // rcx
  struct ISpellingError *v24; // rax
  int v25; // [rsp+30h] [rbp-79h] BYREF
  struct ISpellingError *v26; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v28[7]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v29; // [rsp+88h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+90h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+A0h] [rbp-9h] BYREF
  HANDLE Timer; // [rsp+B0h] [rbp+7h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+B8h] [rbp+Fh] BYREF

  v5 = 0;
  *a2 = 0;
  if ( !*((_QWORD *)this + 4) )
    return 1;
  if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)SPELL_CHECKING_ETW_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)EnumSpellingErrorDecoratorNextSend,
      a3,
      1u,
      &v30);
  v27[0] = 0;
  v28[0] = &std::_Func_impl_no_alloc<_lambda_e706ed36542a5067463818d1e2c6c89e_,long,>::`vftable';
  v28[1] = this;
  v28[2] = v27;
  v29 = v28;
  CRPCTimeout::CRPCTimeout((CRPCTimeout *)&v31);
  if ( !v29 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  FirstErrorAtOrAfterIndex = (*(__int64 (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
  if ( (v31.Size & 0x80000000) == 0 )
  {
    v31.Size = -2147467259;
    CoDisableCallCancellation(0);
    if ( Timer )
      DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  if ( v29 )
  {
    v9 = v28;
    LOBYTE(v9) = v29 != v28;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v29 + 32LL))(v29, v9);
  }
  v26 = 0;
  if ( !FirstErrorAtOrAfterIndex )
  {
    v30.Ptr = 0;
    FirstErrorAtOrAfterIndex = Windows::Globalization::Spelling::CSpellingErrorDecorator::CreateInstance(v27, &v30);
    ATL::CComPtr<ISpellingError>::operator=<Windows::Globalization::Spelling::CSpellingErrorDecorator>(
      (__int64 *)&v26,
      &v30);
    ATL::CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>::~CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>(&v30);
    while ( !FirstErrorAtOrAfterIndex )
    {
      v25 = 0;
      LODWORD(v30.Ptr) = 0;
      v10 = (*(__int64 (__fastcall **)(struct ISpellingError *, int *))(*(_QWORD *)v26 + 24LL))(v26, &v25);
      if ( v10 < 0
        || (v10 = (*(__int64 (__fastcall **)(struct ISpellingError *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v26 + 32LL))(
                    v26,
                    &v30),
            v10 < 0) )
      {
        v12 = v25;
      }
      else
      {
        v12 = v25;
        if ( (unsigned __int64)(unsigned int)v25 >= *((_QWORD *)this + 7)
          || (v8 = (unsigned int)(v25 + LODWORD(v30.Ptr)), v25 >= (unsigned int)v8)
          || (unsigned __int64)(unsigned int)v8 > *((_QWORD *)this + 7) )
        {
          if ( (Microsoft_Windows_Spell_CheckingEnableBits & 4) != 0 )
            McGenEventWrite_EventWriteTransfer(
              (REGHANDLE *)SPELL_CHECKING_ETW_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)ProviderReturnedErrorOutOfBounds,
              v8,
              1u,
              &v31);
          FirstErrorAtOrAfterIndex = -2147483637;
          break;
        }
      }
      FirstErrorAtOrAfterIndex = 0;
      if ( v10 < 0 )
        FirstErrorAtOrAfterIndex = v10;
      if ( FirstErrorAtOrAfterIndex )
        break;
      v13 = (char *)this + 40;
      if ( *((_QWORD *)this + 8) <= 7u )
        LODWORD(v14) = (_DWORD)this + 40;
      else
        v14 = *(char **)v13;
      v15 = std::_Traits_find_last_of<std::char_traits<unsigned short>>((int)v14, *((_QWORD *)this + 7), v12, v11, 3u);
      if ( v15 != -1 )
        v5 = v15 + 1;
      if ( *((_QWORD *)this + 8) <= 7u )
        LODWORD(v17) = (_DWORD)this + 40;
      else
        v17 = *(char **)v13;
      v18 = std::_Traits_find_first_of<std::char_traits<unsigned short>>(
              (int)v17,
              *((_QWORD *)this + 7),
              LODWORD(v30.Ptr) + v25 - 1,
              v16,
              3u);
      LODWORD(v20) = v18;
      if ( v18 == -1 )
        v20 = *((_QWORD *)this + 7);
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)SPELL_CHECKING_ETW_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)CheckURISend,
          v19,
          1u,
          &v33);
      if ( *((_QWORD *)this + 8) <= 7u )
      {
        v21 = (char *)this + 40;
      }
      else
      {
        v21 = *(char **)v13;
        v13 = *(char **)v13;
      }
      v22 = Windows::Globalization::Spelling::CheckURI::IsURI<unsigned short *>(
              (__int64)&v21[2 * v5],
              (__int64)&v13[2 * (unsigned int)v20]);
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)SPELL_CHECKING_ETW_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)CheckURIReceive,
          v8,
          1u,
          &v31);
      v5 = 0;
      if ( !v22 )
      {
        v24 = v26;
        v26 = 0;
        *a2 = v24;
        break;
      }
      v23 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(struct ISpellingError *))(*(_QWORD *)v23 + 16LL))(v23);
      }
      FirstErrorAtOrAfterIndex = Windows::Globalization::Spelling::CEnumSpellingErrorDecorator::GetFirstErrorAtOrAfterIndex(
                                   this,
                                   v20,
                                   &v26);
    }
  }
  if ( (Microsoft_Windows_Spell_CheckingEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)SPELL_CHECKING_ETW_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)EnumSpellingErrorDecoratorNextReceive,
      v8,
      1u,
      &v31);
  _InterlockedAdd((volatile signed __int32 *)&SpellingTelemetry::m_errorNextResult, 1u);
  if ( FirstErrorAtOrAfterIndex >= 0 )
    _InterlockedAdd(&dword_18014052C, 1u);
  if ( v26 )
    (*(void (__fastcall **)(struct ISpellingError *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 16LL))(v27[0]);
  return (unsigned int)FirstErrorAtOrAfterIndex;
}

```

## disassembly

```asm
0x180029ee0  mov     [rsp-8+arg_10], rbx
0x180029ee5  push    rbp
0x180029ee6  push    rsi
0x180029ee7  push    rdi
0x180029ee8  push    r12
0x180029eea  push    r13
0x180029eec  push    r14
0x180029eee  push    r15
0x180029ef0  lea     rbp, [rsp-27h]
0x180029ef5  sub     rsp, 0D0h
0x180029efc  mov     rax, cs:__security_cookie
0x180029f03  xor     rax, rsp
0x180029f06  mov     [rbp+57h+var_38], rax
0x180029f0a  mov     r12, rdx
0x180029f0d  mov     r14, rcx
0x180029f10  xor     r13d, r13d
0x180029f13  mov     [rdx], r13
0x180029f16  cmp     [rcx+20h], r13
0x180029f1a  jnz     short loc_180029F25
0x180029f1c  lea     eax, [r13+1]
0x180029f20  jmp     loc_18002A254
0x180029f25  mov     edi, 1
0x180029f2a  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, dil
0x180029f31  jz      short loc_180029F52
0x180029f33  lea     rax, [rbp+57h+var_70]
0x180029f37  mov     [rsp+100h+N], rax
0x180029f3c  mov     r9d, edi
0x180029f3f  lea     rdx, EnumSpellingErrorDecoratorNextSend
0x180029f46  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x180029f4d  call    McGenEventWrite_EventWriteTransfer
0x180029f52  mov     [rbp+57h+var_C0], r13
0x180029f56  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e706ed36542a5067463818d1e2c6c89e_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e706ed36542a5067463818d1e2c6c89e_,long,>::`vftable'
0x180029f5d  mov     [rbp+57h+var_B0], rax
0x180029f61  mov     [rbp+57h+var_A8], r14
0x180029f65  lea     rax, [rbp+57h+var_C0]
0x180029f69  mov     [rbp+57h+var_A0], rax
0x180029f6d  lea     rax, [rbp+57h+var_B0]
0x180029f71  mov     [rbp+57h+var_78], rax
0x180029f75  lea     rcx, [rbp+57h+var_60]; this
0x180029f79  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180029f7e  mov     rcx, [rbp+57h+var_78]
0x180029f82  test    rcx, rcx
0x180029f85  jnz     short loc_180029F8E
0x180029f87  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180029f8d  int     3; Trap to Debugger
0x180029f8e  mov     rax, [rcx]
0x180029f91  mov     rax, [rax+10h]
0x180029f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f9a  mov     ebx, eax
0x180029f9c  cmp     [rbp+57h+var_58], r13d
0x180029fa0  jl      short loc_180029FC6
0x180029fa2  mov     [rbp+57h+var_58], 80004005h
0x180029fa9  xor     ecx, ecx; pReserved
0x180029fab  call    cs:__imp_CoDisableCallCancellation
0x180029fb1  mov     rdx, [rbp+57h+Timer]; Timer
0x180029fb5  test    rdx, rdx
0x180029fb8  jz      short loc_180029FC6
0x180029fba  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180029fbe  xor     ecx, ecx; TimerQueue
0x180029fc0  call    cs:__imp_DeleteTimerQueueTimer
0x180029fc6  mov     rcx, [rbp+57h+var_78]
0x180029fca  test    rcx, rcx
0x180029fcd  jz      short loc_180029FE5
0x180029fcf  mov     rax, [rcx]
0x180029fd2  lea     rdx, [rbp+57h+var_B0]
0x180029fd6  cmp     rcx, rdx
0x180029fd9  setnz   dl
0x180029fdc  mov     rax, [rax+20h]
0x180029fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fe5  mov     [rbp+57h+var_C8], r13
0x180029fe9  test    ebx, ebx
0x180029feb  jnz     loc_18002A1EC
0x180029ff1  mov     qword ptr [rbp+57h+var_70], r13
0x180029ff5  lea     rdx, [rbp+57h+var_70]
0x180029ff9  lea     rcx, [rbp+57h+var_C0]
0x180029ffd  call    ?CreateInstance@CSpellingErrorDecorator@Spelling@Globalization@Windows@@SAJAEBV?$CComPtr@UISpellingError@@@ATL@@PEAPEAV1234@@Z; Windows::Globalization::Spelling::CSpellingErrorDecorator::CreateInstance(ATL::CComPtr<ISpellingError> const &,Windows::Globalization::Spelling::CSpellingErrorDecorator * *)
0x18002a002  mov     ebx, eax
0x18002a004  lea     rdx, [rbp+57h+var_70]
0x18002a008  lea     rcx, [rbp+57h+var_C8]
0x18002a00c  call    ??$?4VCSpellingErrorDecorator@Spelling@Globalization@Windows@@@?$CComPtr@UISpellingError@@@ATL@@QEAAPEAUISpellingError@@AEBV?$CComPtr@VCSpellingErrorDecorator@Spelling@Globalization@Windows@@@1@@Z; ATL::CComPtr<ISpellingError>::operator=<Windows::Globalization::Spelling::CSpellingErrorDecorator>(ATL::CComPtr<Windows::Globalization::Spelling::CSpellingErrorDecorator> const &)
0x18002a011  lea     rcx, [rbp+57h+var_70]
0x18002a015  call    ??1?$CComPtrBase@VCPrivateSpellCheckerFactoryWrapper@Spelling@Globalization@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>::~CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>(void)
0x18002a01a  jmp     loc_18002A1D6
0x18002a01f  mov     [rbp+57h+var_D0], r13d
0x18002a023  mov     dword ptr [rbp+57h+var_70], r13d
0x18002a027  mov     rcx, [rbp+57h+var_C8]
0x18002a02b  mov     rax, [rcx]
0x18002a02e  lea     rdx, [rbp+57h+var_D0]
0x18002a032  mov     rax, [rax+18h]
0x18002a036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a03b  mov     ecx, eax
0x18002a03d  test    eax, eax
0x18002a03f  js      short loc_18002A0AB
0x18002a041  mov     rcx, [rbp+57h+var_C8]
0x18002a045  mov     rax, [rcx]
0x18002a048  lea     rdx, [rbp+57h+var_70]
0x18002a04c  mov     rax, [rax+20h]
0x18002a050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a055  mov     ecx, eax
0x18002a057  test    eax, eax
0x18002a059  js      short loc_18002A0AB
0x18002a05b  mov     edx, [rbp+57h+var_D0]
0x18002a05e  cmp     rdx, [r14+38h]
0x18002a062  jnb     short loc_18002A079
0x18002a064  mov     r8d, dword ptr [rbp+57h+var_70]
0x18002a068  add     r8d, edx
0x18002a06b  cmp     edx, r8d
0x18002a06e  jnb     short loc_18002A079
0x18002a070  mov     eax, r8d
0x18002a073  cmp     rax, [r14+38h]
0x18002a077  jbe     short loc_18002A0AE
0x18002a079  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 4
0x18002a080  jz      short loc_18002A0A1
0x18002a082  lea     rax, [rbp+57h+var_60]
0x18002a086  mov     [rsp+100h+N], rax
0x18002a08b  mov     r9d, edi
0x18002a08e  lea     rdx, ProviderReturnedErrorOutOfBounds
0x18002a095  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002a09c  call    McGenEventWrite_EventWriteTransfer
0x18002a0a1  mov     ebx, 8000000Bh
0x18002a0a6  jmp     loc_18002A1EC
0x18002a0ab  mov     edx, [rbp+57h+var_D0]
0x18002a0ae  mov     ebx, r13d
0x18002a0b1  test    ecx, ecx
0x18002a0b3  cmovs   ebx, ecx
0x18002a0b6  test    ebx, ebx
0x18002a0b8  jnz     loc_18002A1EC
0x18002a0be  lea     rsi, [r14+28h]
0x18002a0c2  cmp     qword ptr [rsi+18h], 7
0x18002a0c7  jbe     short loc_18002A0CE
0x18002a0c9  mov     rcx, [rsi]
0x18002a0cc  jmp     short loc_18002A0D1
0x18002a0ce  mov     rcx, rsi; int
0x18002a0d1  mov     r8d, edx; int
0x18002a0d4  mov     [rsp+100h+N], 3; N
0x18002a0dd  mov     rdx, [rsi+10h]; int
0x18002a0e1  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18002a0e6  lea     rcx, [rax+1]
0x18002a0ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a0ee  cmovnz  r13, rcx
0x18002a0f2  mov     edx, [rbp+57h+var_D0]
0x18002a0f5  dec     edx
0x18002a0f7  add     edx, dword ptr [rbp+57h+var_70]
0x18002a0fa  cmp     qword ptr [rsi+18h], 7
0x18002a0ff  jbe     short loc_18002A106
0x18002a101  mov     rcx, [rsi]
0x18002a104  jmp     short loc_18002A109
0x18002a106  mov     rcx, rsi; int
0x18002a109  mov     r8d, edx; int
0x18002a10c  mov     [rsp+100h+N], 3; N
0x18002a115  mov     rdx, [rsi+10h]; int
0x18002a119  call    ??$_Traits_find_first_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18002a11e  mov     r15, rax
0x18002a121  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a125  jnz     short loc_18002A12B
0x18002a127  mov     r15, [rsi+10h]
0x18002a12b  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, dil
0x18002a132  jz      short loc_18002A153
0x18002a134  lea     rax, [rbp+57h+var_48]
0x18002a138  mov     [rsp+100h+N], rax
0x18002a13d  mov     r9d, edi
0x18002a140  lea     rdx, CheckURISend
0x18002a147  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002a14e  call    McGenEventWrite_EventWriteTransfer
0x18002a153  cmp     qword ptr [r14+40h], 7
0x18002a158  jbe     short loc_18002A162
0x18002a15a  mov     rcx, [rsi]
0x18002a15d  mov     rsi, rcx
0x18002a160  jmp     short loc_18002A165
0x18002a162  mov     rcx, rsi
0x18002a165  mov     r15d, r15d
0x18002a168  lea     rdx, [rsi+r15*2]
0x18002a16c  mov     eax, r13d
0x18002a16f  lea     rcx, [rcx+rax*2]
0x18002a173  call    ??$IsURI@PEAG@CheckURI@Spelling@Globalization@Windows@@SA_NQEAG0@Z; Windows::Globalization::Spelling::CheckURI::IsURI<ushort *>(ushort * const,ushort * const)
0x18002a178  mov     sil, al
0x18002a17b  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, dil
0x18002a182  jz      short loc_18002A1A3
0x18002a184  lea     rax, [rbp+57h+var_60]
0x18002a188  mov     [rsp+100h+N], rax
0x18002a18d  mov     r9d, edi
0x18002a190  lea     rdx, CheckURIReceive
0x18002a197  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002a19e  call    McGenEventWrite_EventWriteTransfer
0x18002a1a3  xor     r13d, r13d
0x18002a1a6  test    sil, sil
0x18002a1a9  jz      short loc_18002A1E0
0x18002a1ab  mov     rcx, [rbp+57h+var_C8]
0x18002a1af  test    rcx, rcx
0x18002a1b2  jz      short loc_18002A1C5
0x18002a1b4  mov     [rbp+57h+var_C8], r13
0x18002a1b8  mov     rax, [rcx]
0x18002a1bb  mov     rax, [rax+10h]
0x18002a1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1c4  nop
0x18002a1c5  lea     r8, [rbp+57h+var_C8]; struct ISpellingError **
0x18002a1c9  mov     edx, r15d; unsigned int
0x18002a1cc  mov     rcx, r14; this
0x18002a1cf  call    ?GetFirstErrorAtOrAfterIndex@CEnumSpellingErrorDecorator@Spelling@Globalization@Windows@@QEAAJKPEAPEAUISpellingError@@@Z; Windows::Globalization::Spelling::CEnumSpellingErrorDecorator::GetFirstErrorAtOrAfterIndex(ulong,ISpellingError * *)
0x18002a1d4  mov     ebx, eax
0x18002a1d6  test    ebx, ebx
0x18002a1d8  jz      loc_18002A01F
0x18002a1de  jmp     short loc_18002A1EC
0x18002a1e0  mov     rax, [rbp+57h+var_C8]
0x18002a1e4  mov     [rbp+57h+var_C8], r13
0x18002a1e8  mov     [r12], rax
0x18002a1ec  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, dil
0x18002a1f3  jz      short loc_18002A214
0x18002a1f5  lea     rax, [rbp+57h+var_60]
0x18002a1f9  mov     [rsp+100h+N], rax
0x18002a1fe  mov     r9d, edi
0x18002a201  lea     rdx, EnumSpellingErrorDecoratorNextReceive
0x18002a208  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002a20f  call    McGenEventWrite_EventWriteTransfer
0x18002a214  lock add cs:?m_errorNextResult@SpellingTelemetry@@0UResultAggregation@@A, edi; ResultAggregation SpellingTelemetry::m_errorNextResult
0x18002a21b  test    ebx, ebx
0x18002a21d  js      short loc_18002A226
0x18002a21f  lock add cs:dword_18014052C, edi
0x18002a226  mov     rcx, [rbp+57h+var_C8]
0x18002a22a  test    rcx, rcx
0x18002a22d  jz      short loc_18002A23C
0x18002a22f  mov     rax, [rcx]
0x18002a232  mov     rax, [rax+10h]
0x18002a236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a23b  nop
0x18002a23c  mov     rcx, [rbp+57h+var_C0]
0x18002a240  test    rcx, rcx
0x18002a243  jz      short loc_18002A252
0x18002a245  mov     rax, [rcx]
0x18002a248  mov     rax, [rax+10h]
0x18002a24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a251  nop
0x18002a252  mov     eax, ebx
0x18002a254  mov     rcx, [rbp+57h+var_38]
0x18002a258  xor     rcx, rsp; StackCookie
0x18002a25b  call    __security_check_cookie
0x18002a260  mov     rbx, [rsp+100h+arg_10]
0x18002a268  add     rsp, 0D0h
0x18002a26f  pop     r15
0x18002a271  pop     r14
0x18002a273  pop     r13
0x18002a275  pop     r12
0x18002a277  pop     rdi
0x18002a278  pop     rsi
0x18002a279  pop     rbp
0x18002a27a  retn
```
