# ipx::mtf::CMtfSuggestionClient::OnResult(_CLIENT_KEY const *,ulong,IUnknown *)

- ea: `0x180018f80`
- end: `0x1800195e9`
- name: `?OnResult@CMtfSuggestionClient@mtf@ipx@@UEAAJPEBU_CLIENT_KEY@@KPEAUIUnknown@@@Z`
- size: `1641`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, const struct _CLIENT_KEY *, unsigned int, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800046d4`
- `0x180006074`
- `0x180014014`
- `0x180014258`
- `0x180016a08`
- `0x180018f80`
- `0x18001b48c`
- `0x18001b8f4`
- `0x18001e068`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800192e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001948a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019563`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800192e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001948a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019563`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018fb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fc3`

## string_xrefs

- `0x1800190e7`: `SuggestionReady`
- `0x1800193c4`: `SuggestionReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::OnResult(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _CLIENT_KEY *a2,
        unsigned int a3,
        struct IUnknown *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  const char *v9; // r9
  char v10; // al
  unsigned int v11; // r14d
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  unsigned int v15; // r15d
  __int64 v16; // rcx
  int v18; // eax
  unsigned int v19; // r12d
  __int64 v20; // rcx
  __int64 v21; // r8
  int v22; // eax
  unsigned int v23; // r14d
  __int64 v24; // rcx
  int (__fastcall ***v25)(_QWORD, GUID *, int *); // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int (__fastcall ***v28)(_QWORD, GUID *, int *); // rcx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // r14d
  __int64 v32; // rcx
  int (__fastcall ***v33)(_QWORD, GUID *, int *); // rcx
  __int64 v34; // rcx
  int v35; // [rsp+20h] [rbp-1E8h]
  __int64 v36; // [rsp+30h] [rbp-1D8h] BYREF
  int (__fastcall ***v37)(_QWORD, GUID *, int *); // [rsp+38h] [rbp-1D0h] BYREF
  int v38; // [rsp+40h] [rbp-1C8h] BYREF
  int v39[2]; // [rsp+48h] [rbp-1C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v40; // [rsp+50h] [rbp-1B8h]
  __int128 v41; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-1A0h]
  _QWORD v43[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v8 = this + 1;
  EnterCriticalSection(this + 1);
  v40 = v8;
  if ( LODWORD(this[4].OwningThread) != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCC,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      v9);
  if ( LODWORD(this->LockSemaphore) == *(_DWORD *)a2
    && HIDWORD(this->LockSemaphore) == *((_DWORD *)a2 + 1)
    && LOWORD(this->SpinCount) == *((_WORD *)a2 + 4) )
  {
    v10 = 0;
    v11 = 1;
  }
  else
  {
    v11 = 1;
    v10 = 1;
  }
  if ( v10 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCD,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      v9);
  v36 = 0;
  v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
          a4,
          &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5,
          &v36);
  if ( v12 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v12,
      v35);
  v38 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *, int *, __int64))(*(_QWORD *)v36 + 40LL))(
          v36,
          &GUID_MTFCORE_VERB,
          &v38,
          4);
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v13,
      v35);
    v16 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( v8 )
      LeaveCriticalSection(v8);
    return v15;
  }
  if ( v38 == 19 )
    goto LABEL_70;
  if ( v38 != 20 )
  {
    if ( v38 == 21 )
    {
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v43,
        "SuggestionReady");
      v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
      MtfPlatformTelemetry::SuggestionReady::StartActivity((MtfPlatformTelemetry::SuggestionReady *)v43);
      if ( this[2].LockSemaphore )
      {
        v41 = 0;
        v42 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *, __int64))(*(_QWORD *)v36 + 40LL))(
                v36,
                &GUID_MTFCORE_RESULT,
                &v41,
                24);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v18,
            v35);
          v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
          v20 = v36;
          if ( v36 )
          {
            v36 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( v8 )
            LeaveCriticalSection(v8);
          return v19;
        }
        if ( BYTE2(v42) )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, GUID *, int *)))(*(_QWORD *)v36 + 56LL))(
            v36,
            &GUID_MTFCORE_SUGGESTIONLIST,
            &GUID_bf445657_712d_488f_b37f_2e303c7420d3,
            &v37);
          *(_QWORD *)v39 = 0;
          if ( (**v37)(v37, &GUID_ee445657_a83d_450f_871b_8e404574e6ec, v39) < 0 || (v21 = *(_QWORD *)v39) == 0 )
          {
            v22 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))Hooked_CoCreateInstance)(
                    &CLSID_MtfLattice,
                    0,
                    1,
                    &GUID_ee445657_a83d_450f_871b_8e404574e6ec);
            v23 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x110,
                (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                (const char *)(unsigned int)v22,
                (int)v39);
              v24 = *(_QWORD *)v39;
              *(_QWORD *)v39 = 0;
              if ( v24 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              v25 = v37;
              v37 = 0;
              if ( v25 )
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, int *)))(*v25)[2])(v25);
              v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
              wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
              wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
              v26 = v36;
              if ( v36 )
              {
                v36 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              if ( v8 )
                LeaveCriticalSection(v8);
              return v23;
            }
            v21 = *(_QWORD *)v39;
          }
          v11 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64, int (__fastcall ***)(_QWORD, GUID *, int *)))(*(_QWORD *)this[2].LockSemaphore + 24LL))(
                  this[2].LockSemaphore,
                  a3,
                  v21,
                  v37);
          v27 = *(_QWORD *)v39;
          *(_QWORD *)v39 = 0;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          v28 = v37;
          v37 = 0;
          if ( v28 )
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, int *)))(*v28)[2])(v28);
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this[2].LockSemaphore + 24LL))(
                  this[2].LockSemaphore,
                  a3,
                  0,
                  0);
        }
      }
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v43);
      v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
      v29 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      if ( v8 )
        LeaveCriticalSection(v8);
      return v11;
    }
LABEL_70:
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDA,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      v14);
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v43,
    "SuggestionReady");
  v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
  MtfPlatformTelemetry::SuggestionReady::StartActivity((MtfPlatformTelemetry::SuggestionReady *)v43);
  if ( this[2].OwningThread )
  {
    v41 = 0;
    v42 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *, __int64))(*(_QWORD *)v36 + 40LL))(
            v36,
            &GUID_MTFCORE_RESULT,
            &v41,
            24);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v30,
        v35);
      v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
      v32 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      if ( v8 )
        LeaveCriticalSection(v8);
      return v31;
    }
    if ( BYTE2(v42) )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, GUID *, int *)))(*(_QWORD *)v36 + 56LL))(
        v36,
        &GUID_MTFCORE_SUGGESTIONLIST,
        &GUID_7f445657_d12f_426f_a09d_f8df369d9a50,
        &v37);
      v11 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD))(*(_QWORD *)this[2].OwningThread + 24LL))(
              this[2].OwningThread,
              a3,
              v37);
      v33 = v37;
      v37 = 0;
      if ( v33 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, int *)))(*v33)[2])(v33);
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD))(*(_QWORD *)this[2].OwningThread + 24LL))(
              this[2].OwningThread,
              a3,
              0);
    }
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v43);
  v43[0] = &MtfPlatformTelemetry::SuggestionReady::`vftable';
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v43);
  v34 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  if ( v8 )
    LeaveCriticalSection(v8);
  return v11;
}

```

## disassembly

```asm
0x180018f80  push    rbx
0x180018f82  push    rsi
0x180018f83  push    rdi
0x180018f84  push    r12
0x180018f86  push    r13
0x180018f88  push    r14
0x180018f8a  push    r15
0x180018f8c  sub     rsp, 1D0h
0x180018f93  mov     rax, cs:__security_cookie
0x180018f9a  xor     rax, rsp
0x180018f9d  mov     [rsp+208h+var_48], rax
0x180018fa5  mov     r15, r9
0x180018fa8  mov     r13d, r8d
0x180018fab  mov     rdi, rdx
0x180018fae  mov     rsi, rcx
0x180018fb1  lea     rbx, [rcx+28h]
0x180018fb5  mov     rcx, rbx; lpCriticalSection
0x180018fb8  call    cs:__imp_EnterCriticalSection
0x180018fbe  mov     [rsp+208h+var_1B8], rbx
0x180018fc3  call    cs:__imp_GetCurrentThreadId
0x180018fc9  mov     rcx, [rsp+208h]; this
0x180018fd1  cmp     [rsi+0B0h], eax
0x180018fd7  jnz     loc_180019595
0x180018fdd  mov     eax, [rdi]
0x180018fdf  cmp     [rsi+18h], eax
0x180018fe2  jnz     short loc_180019001
0x180018fe4  mov     eax, [rdi+4]
0x180018fe7  cmp     [rsi+1Ch], eax
0x180018fea  jnz     short loc_180019001
0x180018fec  movzx   eax, word ptr [rdi+8]
0x180018ff0  cmp     [rsi+20h], ax
0x180018ff4  jnz     short loc_180019001
0x180018ff6  xor     edi, edi
0x180018ff8  mov     al, dil
0x180018ffb  lea     r14d, [rdi+1]
0x180018fff  jmp     short loc_18001900C
0x180019001  mov     r14d, 1
0x180019007  mov     al, r14b
0x18001900a  xor     edi, edi
0x18001900c  mov     rcx, [rsp+208h]; this
0x180019014  test    al, al
0x180019016  jnz     loc_1800195A7
0x18001901c  mov     [rsp+208h+var_1D8], rdi
0x180019021  mov     rax, [r15]
0x180019024  lea     r8, [rsp+208h+var_1D8]
0x180019029  lea     rdx, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5
0x180019030  mov     rcx, r15
0x180019033  mov     rax, [rax]
0x180019036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903b  mov     rcx, [rsp+208h]; this
0x180019043  test    eax, eax
0x180019045  js      loc_1800195B9
0x18001904b  mov     [rsp+208h+var_1C8], edi
0x18001904f  mov     rcx, [rsp+208h+var_1D8]
0x180019054  mov     rax, [rcx]
0x180019057  mov     r9d, 4
0x18001905d  lea     r8, [rsp+208h+var_1C8]
0x180019062  lea     rdx, GUID_MTFCORE_VERB
0x180019069  mov     rax, [rax+28h]
0x18001906d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019072  mov     r15d, eax
0x180019075  test    eax, eax
0x180019077  jns     short loc_1800190C8
0x180019079  mov     rcx, [rsp+208h]; this
0x180019081  mov     r9d, eax; char *
0x180019084  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001908b  mov     edx, 0D4h; void *
0x180019090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019095  nop
0x180019096  mov     rcx, [rsp+208h+var_1D8]
0x18001909b  test    rcx, rcx
0x18001909e  jz      short loc_1800190B2
0x1800190a0  mov     [rsp+208h+var_1D8], rdi
0x1800190a5  mov     rax, [rcx]
0x1800190a8  mov     rax, [rax+10h]
0x1800190ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190b1  nop
0x1800190b2  test    rbx, rbx
0x1800190b5  jz      short loc_1800190C0
0x1800190b7  mov     rcx, rbx; lpCriticalSection
0x1800190ba  call    cs:__imp_LeaveCriticalSection
0x1800190c0  mov     eax, r15d
0x1800190c3  jmp     loc_180019572
0x1800190c8  mov     eax, [rsp+208h+var_1C8]
0x1800190cc  sub     eax, 13h
0x1800190cf  jz      loc_1800195CE
0x1800190d5  sub     eax, 1
0x1800190d8  jz      loc_1800193C4
0x1800190de  cmp     eax, 1
0x1800190e1  jnz     loc_1800195CE
0x1800190e7  lea     rdx, aSuggestionread; "SuggestionReady"
0x1800190ee  lea     rcx, [rsp+208h+var_198]
0x1800190f3  call    ??0?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800190f8  lea     r15, ??_7SuggestionReady@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::SuggestionReady::`vftable'
0x1800190ff  mov     [rsp+208h+var_198], r15
0x180019104  lea     rcx, [rsp+208h+var_198]; this
0x180019109  call    ?StartActivity@SuggestionReady@MtfPlatformTelemetry@@QEAAXXZ; MtfPlatformTelemetry::SuggestionReady::StartActivity(void)
0x18001910e  nop
0x18001910f  cmp     [rsi+68h], rdi
0x180019113  jz      loc_18001936D
0x180019119  xorps   xmm0, xmm0
0x18001911c  xor     eax, eax
0x18001911e  movups  [rsp+208h+var_1B0], xmm0
0x180019123  mov     [rsp+208h+var_1A0], rax
0x180019128  mov     rcx, [rsp+208h+var_1D8]
0x18001912d  mov     rax, [rcx]
0x180019130  mov     r9d, 18h
0x180019136  lea     r8, [rsp+208h+var_1B0]
0x18001913b  lea     rdx, GUID_MTFCORE_RESULT
0x180019142  mov     rax, [rax+28h]
0x180019146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001914b  mov     r12d, eax
0x18001914e  test    eax, eax
0x180019150  jns     short loc_1800191BB
0x180019152  mov     rcx, [rsp+208h]; this
0x18001915a  mov     r9d, eax; char *
0x18001915d  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019164  mov     edx, 100h; void *
0x180019169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001916e  nop
0x18001916f  mov     [rsp+208h+var_198], r15
0x180019174  lea     rcx, [rsp+208h+var_198]
0x180019179  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001917e  lea     rcx, [rsp+208h+var_198]
0x180019183  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180019188  nop
0x180019189  mov     rcx, [rsp+208h+var_1D8]
0x18001918e  test    rcx, rcx
0x180019191  jz      short loc_1800191A5
0x180019193  mov     [rsp+208h+var_1D8], rdi
0x180019198  mov     rax, [rcx]
0x18001919b  mov     rax, [rax+10h]
0x18001919f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191a4  nop
0x1800191a5  test    rbx, rbx
0x1800191a8  jz      short loc_1800191B3
0x1800191aa  mov     rcx, rbx; lpCriticalSection
0x1800191ad  call    cs:__imp_LeaveCriticalSection
0x1800191b3  mov     eax, r12d
0x1800191b6  jmp     loc_180019572
0x1800191bb  cmp     byte ptr [rsp+208h+var_1A0+2], dil
0x1800191c0  jz      loc_180019351
0x1800191c6  mov     [rsp+208h+var_1D0], rdi
0x1800191cb  mov     rcx, [rsp+208h+var_1D8]
0x1800191d0  mov     rax, [rcx]
0x1800191d3  lea     r9, [rsp+208h+var_1D0]
0x1800191d8  lea     r8, _GUID_bf445657_712d_488f_b37f_2e303c7420d3
0x1800191df  lea     rdx, GUID_MTFCORE_SUGGESTIONLIST
0x1800191e6  mov     rax, [rax+38h]
0x1800191ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191ef  mov     qword ptr [rsp+208h+var_1C0], rdi
0x1800191f4  mov     rcx, [rsp+208h+var_1D0]
0x1800191f9  mov     rax, [rcx]
0x1800191fc  lea     r8, [rsp+208h+var_1C0]
0x180019201  lea     rdx, _GUID_ee445657_a83d_450f_871b_8e404574e6ec
0x180019208  mov     rax, [rax]
0x18001920b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019210  test    eax, eax
0x180019212  js      short loc_180019222
0x180019214  mov     r8, qword ptr [rsp+208h+var_1C0]
0x180019219  test    r8, r8
0x18001921c  jnz     loc_1800192FC
0x180019222  lea     rax, [rsp+208h+var_1C0]
0x180019227  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x18001922c  lea     r9, _GUID_ee445657_a83d_450f_871b_8e404574e6ec
0x180019233  mov     r8d, r14d
0x180019236  xor     edx, edx
0x180019238  lea     rcx, CLSID_MtfLattice
0x18001923f  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180019246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001924b  mov     r14d, eax
0x18001924e  test    eax, eax
0x180019250  jns     loc_1800192F7
0x180019256  mov     rcx, [rsp+208h]; this
0x18001925e  mov     r9d, eax; char *
0x180019261  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019268  mov     edx, 110h; void *
0x18001926d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019272  nop
0x180019273  mov     rcx, qword ptr [rsp+208h+var_1C0]
0x180019278  mov     qword ptr [rsp+208h+var_1C0], rdi
0x18001927d  test    rcx, rcx
0x180019280  jz      short loc_18001928F
0x180019282  mov     rax, [rcx]
0x180019285  mov     rax, [rax+10h]
0x180019289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928e  nop
0x18001928f  mov     rcx, [rsp+208h+var_1D0]
0x180019294  mov     [rsp+208h+var_1D0], rdi
0x180019299  test    rcx, rcx
0x18001929c  jz      short loc_1800192AB
0x18001929e  mov     rax, [rcx]
0x1800192a1  mov     rax, [rax+10h]
0x1800192a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192aa  nop
0x1800192ab  mov     [rsp+208h+var_198], r15
0x1800192b0  lea     rcx, [rsp+208h+var_198]
0x1800192b5  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800192ba  lea     rcx, [rsp+208h+var_198]
0x1800192bf  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800192c4  nop
0x1800192c5  mov     rcx, [rsp+208h+var_1D8]
0x1800192ca  test    rcx, rcx
0x1800192cd  jz      short loc_1800192E1
0x1800192cf  mov     [rsp+208h+var_1D8], rdi
0x1800192d4  mov     rax, [rcx]
0x1800192d7  mov     rax, [rax+10h]
0x1800192db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192e0  nop
0x1800192e1  test    rbx, rbx
0x1800192e4  jz      short loc_1800192EF
0x1800192e6  mov     rcx, rbx; lpCriticalSection
0x1800192e9  call    cs:__imp_LeaveCriticalSection
0x1800192ef  mov     eax, r14d
0x1800192f2  jmp     loc_180019572
0x1800192f7  mov     r8, qword ptr [rsp+208h+var_1C0]
0x1800192fc  mov     rcx, [rsi+68h]
0x180019300  mov     rax, [rcx]
0x180019303  mov     r9, [rsp+208h+var_1D0]
0x180019308  mov     edx, r13d
0x18001930b  mov     rax, [rax+18h]
0x18001930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019314  mov     r14d, eax
0x180019317  mov     rcx, qword ptr [rsp+208h+var_1C0]
0x18001931c  mov     qword ptr [rsp+208h+var_1C0], rdi
0x180019321  test    rcx, rcx
0x180019324  jz      short loc_180019333
0x180019326  mov     rax, [rcx]
0x180019329  mov     rax, [rax+10h]
0x18001932d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019332  nop
0x180019333  mov     rcx, [rsp+208h+var_1D0]
0x180019338  mov     [rsp+208h+var_1D0], rdi
0x18001933d  test    rcx, rcx
0x180019340  jz      short loc_18001934F
0x180019342  mov     rax, [rcx]
0x180019345  mov     rax, [rax+10h]
0x180019349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001934e  nop
0x18001934f  jmp     short loc_18001936D
0x180019351  mov     rcx, [rsi+68h]
0x180019355  mov     rax, [rcx]
0x180019358  xor     r9d, r9d
0x18001935b  xor     r8d, r8d
0x18001935e  mov     edx, r13d
0x180019361  mov     rax, [rax+18h]
0x180019365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001936a  mov     r14d, eax
0x18001936d  lea     rcx, [rsp+208h+var_198]
0x180019372  call    ?Stop@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180019377  nop
0x180019378  mov     [rsp+208h+var_198], r15
0x18001937d  lea     rcx, [rsp+208h+var_198]
0x180019382  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180019387  lea     rcx, [rsp+208h+var_198]
0x18001938c  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180019391  nop
0x180019392  mov     rcx, [rsp+208h+var_1D8]
0x180019397  test    rcx, rcx
0x18001939a  jz      short loc_1800193AE
0x18001939c  mov     [rsp+208h+var_1D8], rdi
0x1800193a1  mov     rax, [rcx]
0x1800193a4  mov     rax, [rax+10h]
0x1800193a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ad  nop
0x1800193ae  test    rbx, rbx
0x1800193b1  jz      short loc_1800193BC
0x1800193b3  mov     rcx, rbx; lpCriticalSection
0x1800193b6  call    cs:__imp_LeaveCriticalSection
0x1800193bc  mov     eax, r14d
0x1800193bf  jmp     loc_180019572
0x1800193c4  lea     rdx, aSuggestionread; "SuggestionReady"
0x1800193cb  lea     rcx, [rsp+208h+var_198]
0x1800193d0  call    ??0?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800193d5  lea     r15, ??_7SuggestionReady@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::SuggestionReady::`vftable'
0x1800193dc  mov     [rsp+208h+var_198], r15
0x1800193e1  lea     rcx, [rsp+208h+var_198]; this
0x1800193e6  call    ?StartActivity@SuggestionReady@MtfPlatformTelemetry@@QEAAXXZ; MtfPlatformTelemetry::SuggestionReady::StartActivity(void)
0x1800193eb  nop
0x1800193ec  cmp     [rsi+60h], rdi
0x1800193f0  jz      loc_18001951A
0x1800193f6  xorps   xmm0, xmm0
0x1800193f9  xor     eax, eax
0x1800193fb  movups  [rsp+208h+var_1B0], xmm0
0x180019400  mov     [rsp+208h+var_1A0], rax
0x180019405  mov     rcx, [rsp+208h+var_1D8]
0x18001940a  mov     rax, [rcx]
0x18001940d  mov     r9d, 18h
0x180019413  lea     r8, [rsp+208h+var_1B0]
0x180019418  lea     rdx, GUID_MTFCORE_RESULT
0x18001941f  mov     rax, [rax+28h]
0x180019423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019428  mov     r14d, eax
0x18001942b  test    eax, eax
0x18001942d  jns     short loc_180019498
0x18001942f  mov     rcx, [rsp+208h]; this
0x180019437  mov     r9d, eax; char *
0x18001943a  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019441  mov     edx, 0E5h; void *
0x180019446  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
