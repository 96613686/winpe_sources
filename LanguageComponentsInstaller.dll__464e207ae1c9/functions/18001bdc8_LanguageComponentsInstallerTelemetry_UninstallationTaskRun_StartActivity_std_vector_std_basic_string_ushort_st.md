# LanguageComponentsInstallerTelemetry::UninstallationTaskRun::StartActivity(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x18001bdc8`
- end: `0x18001bff5`
- name: `?StartActivity@UninstallationTaskRun@LanguageComponentsInstallerTelemetry@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `557`
- prototype: `void __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014788`

## callees

- `0x180001f98`
- `0x180003520`
- `0x180006380`
- `0x1800080e0`
- `0x18000b498`
- `0x18000f0a8`
- `0x180010a7c`
- `0x180018b8c`
- `0x1800195c0`
- `0x18001bdc8`
- `0x1800214f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bec1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bfae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bfae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bea3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bea3`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationTaskRun::StartActivity(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  RTL_SRWLOCK *v6; // r15
  PSRWLOCK v7; // rdi
  char **v8; // rbx
  __int64 v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  char **v15; // rax
  __int64 v16; // r8
  int v17; // r9d
  _QWORD *v18; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  char *Src[4]; // [rsp+58h] [rbp-28h] BYREF

  v22 = (__int64)a2;
  LOBYTE(a4) = 0;
  std::_Sort_unchecked<std::wstring *,std::less<void>>(*a2, a2[1], (__int64)(a2[1] - *a2) >> 5, a4);
  std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(&SRWLock, *a2, a2[1]);
  v6 = (RTL_SRWLOCK *)a2[1];
  v7 = SRWLock;
  if ( SRWLock != v6 )
  {
    v8 = (char **)SRWLock;
    do
    {
      std::wstring::~wstring(v8);
      v8 += 4;
    }
    while ( v8 != (char **)v6 );
    a2[1] = v7;
  }
  DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(Src);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v9 = *(_QWORD *)(a1 + 272);
  v10 = LanguageComponentsInstallerTelemetryProvider::Provider();
  if ( *(_DWORD *)v10 > 5u
    && (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v9 + 8));
  }
  else
  {
    *(_OWORD *)(v9 + 8) = 0;
  }
  *(_DWORD *)v9 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v11 = LanguageComponentsInstallerTelemetryProvider::Provider();
  v12 = v11;
  v13 = *(unsigned int *)v11;
  if ( (unsigned int)v13 > 5 )
  {
    v14 = *((_QWORD *)v11 + 3);
    v13 = *((_QWORD *)v12 + 2);
    if ( (v13 & 0x400000000000LL) != 0 )
    {
      v13 = v14 & 0x400000000000LL;
      if ( (v14 & 0x400000000000LL) == v14 )
      {
        v15 = Src;
        if ( Src[3] > (char *)7 )
          v15 = (char **)Src[0];
        v21 = (__int64)v15;
        LODWORD(SRWLock) = GetCurrentThreadId();
        v22 = 50331648;
        v16 = *(_QWORD *)(a1 + 272);
        if ( !*(_BYTE *)(v16 + 4)
          || (v17 = v16 + 24, !*(_DWORD *)(v16 + 24))
          && !*(_DWORD *)(v16 + 28)
          && !*(_DWORD *)(v16 + 32)
          && !*(_DWORD *)(v16 + 36) )
        {
          v17 = 0;
        }
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          (int)v12,
          (int)byte_18002F779,
          v16 + 8,
          v17,
          (__int64)&v22,
          (__int64)&SRWLock,
          (__int64 **)&v21);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v18 = (_QWORD *)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v13,
                          1);
      *v18 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *Local;
        *Local = v18;
        *(_DWORD *)(a1 + 312) = GetCurrentThreadId();
      }
    }
    else
    {
      *v18 = 0;
    }
  }
  std::wstring::~wstring(Src);
  std::vector<std::wstring>::_Tidy((__int64)a2);
}

```

## disassembly

```asm
0x18001bdc8  mov     [rsp-28h+arg_10], rbx
0x18001bdcd  push    rbp
0x18001bdce  push    rsi
0x18001bdcf  push    rdi
0x18001bdd0  push    r14
0x18001bdd2  push    r15
0x18001bdd4  mov     rbp, rsp
0x18001bdd7  sub     rsp, 80h
0x18001bdde  mov     rax, cs:__security_cookie
0x18001bde5  xor     rax, rsp
0x18001bde8  mov     [rbp+var_8], rax
0x18001bdec  mov     r14, rdx
0x18001bdef  mov     rsi, rcx
0x18001bdf2  mov     [rbp+var_30], rdx
0x18001bdf6  mov     rdx, [rdx+8]
0x18001bdfa  xor     r9b, r9b
0x18001bdfd  mov     r8, rdx
0x18001be00  sub     r8, [r14]
0x18001be03  sar     r8, 5
0x18001be07  mov     rcx, [r14]
0x18001be0a  call    ??$_Sort_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x18001be0f  mov     r8, [r14+8]
0x18001be13  mov     rdx, [r14]
0x18001be16  lea     rcx, [rbp+SRWLock]
0x18001be1a  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@0@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x18001be1f  mov     r15, [r14+8]
0x18001be23  mov     rdi, [rbp+SRWLock]
0x18001be27  cmp     rdi, r15
0x18001be2a  jz      short loc_18001BE46
0x18001be2c  mov     rbx, rdi
0x18001be2f  mov     rcx, rbx; void *
0x18001be32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001be37  add     rbx, 20h ; ' '
0x18001be3b  cmp     rbx, r15
0x18001be3e  jnz     short loc_18001BE2F
0x18001be40  mov     [r14+8], rdi
0x18001be44  jmp     short loc_18001BE49
0x18001be46  mov     rdi, r15
0x18001be49  mov     r8, rdi
0x18001be4c  mov     rdx, [r14]
0x18001be4f  lea     rcx, [rbp+Src]; Src
0x18001be53  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18001be58  nop
0x18001be59  lea     rdx, [rbp+SRWLock]
0x18001be5d  mov     rcx, rsi
0x18001be60  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001be65  mov     rbx, [rsi+110h]
0x18001be6c  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001be71  mov     ecx, [rax]
0x18001be73  mov     rdi, 400000000000h
0x18001be7d  cmp     ecx, 5
0x18001be80  jbe     short loc_18001BEAB
0x18001be82  mov     rcx, [rax+18h]
0x18001be86  mov     rax, [rax+10h]
0x18001be8a  test    rdi, rax
0x18001be8d  jz      short loc_18001BEAB
0x18001be8f  mov     rax, rcx
0x18001be92  and     rax, rdi
0x18001be95  cmp     rax, rcx
0x18001be98  jnz     short loc_18001BEAB
0x18001be9a  lea     rdx, [rbx+8]; ActivityId
0x18001be9e  mov     ecx, 3; ControlCode
0x18001bea3  call    cs:__imp_EventActivityIdControl
0x18001bea9  jmp     short loc_18001BEB2
0x18001beab  xorps   xmm0, xmm0
0x18001beae  movups  xmmword ptr [rbx+8], xmm0
0x18001beb2  mov     dword ptr [rbx], 1
0x18001beb8  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001bebc  test    rcx, rcx
0x18001bebf  jz      short loc_18001BEC7
0x18001bec1  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bec7  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001becc  mov     rbx, rax
0x18001becf  mov     ecx, [rax]
0x18001bed1  cmp     ecx, 5
0x18001bed4  jbe     loc_18001BF7B
0x18001beda  mov     rax, [rax+18h]
0x18001bede  mov     rcx, [rbx+10h]
0x18001bee2  test    rdi, rcx
0x18001bee5  jz      loc_18001BF7B
0x18001beeb  mov     rcx, rax
0x18001beee  and     rcx, rdi
0x18001bef1  cmp     rcx, rax
0x18001bef4  jnz     loc_18001BF7B
0x18001befa  lea     rax, [rbp+Src]
0x18001befe  cmp     [rbp+var_10], 7
0x18001bf03  cmova   rax, [rbp+Src]
0x18001bf08  mov     [rbp+var_38], rax
0x18001bf0c  call    cs:__imp_GetCurrentThreadId
0x18001bf12  mov     dword ptr [rbp+SRWLock], eax
0x18001bf15  mov     [rbp+var_30], 3000000h
0x18001bf1d  mov     r8, [rsi+110h]
0x18001bf24  cmp     byte ptr [r8+4], 0
0x18001bf29  jz      short loc_18001BF4A
0x18001bf2b  lea     r9, [r8+18h]
0x18001bf2f  cmp     dword ptr [r9], 0
0x18001bf33  jnz     short loc_18001BF4D
0x18001bf35  cmp     dword ptr [r9+4], 0
0x18001bf3a  jnz     short loc_18001BF4D
0x18001bf3c  cmp     dword ptr [r9+8], 0
0x18001bf41  jnz     short loc_18001BF4D
0x18001bf43  cmp     dword ptr [r9+0Ch], 0
0x18001bf48  jnz     short loc_18001BF4D
0x18001bf4a  xor     r9d, r9d
0x18001bf4d  add     r8, 8
0x18001bf51  lea     rax, [rbp+var_38]
0x18001bf55  mov     [rsp+80h+var_50], rax; __int64
0x18001bf5a  lea     rax, [rbp+SRWLock]
0x18001bf5e  mov     [rsp+80h+var_58], rax; __int64
0x18001bf63  lea     rax, [rbp+var_30]
0x18001bf67  mov     [rsp+80h+var_60], rax; __int64
0x18001bf6c  lea     rdx, byte_18002F779
0x18001bf73  mov     rcx, rbx; int
0x18001bf76  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001bf7b  cmp     dword ptr [rsi+138h], 0
0x18001bf82  jnz     short loc_18001BFC0
0x18001bf84  lea     rbx, [rsi+120h]
0x18001bf8b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bf93  jz      short loc_18001BFB9
0x18001bf95  mov     dl, 1
0x18001bf97  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001bf9c  mov     [rbx], rax
0x18001bf9f  test    rax, rax
0x18001bfa2  jz      short loc_18001BFC0
0x18001bfa4  mov     rcx, [rax]
0x18001bfa7  mov     [rbx+10h], rcx
0x18001bfab  mov     [rax], rbx
0x18001bfae  call    cs:__imp_GetCurrentThreadId
0x18001bfb4  mov     [rbx+18h], eax
0x18001bfb7  jmp     short loc_18001BFC0
0x18001bfb9  mov     qword ptr [rbx], 0
0x18001bfc0  lea     rcx, [rbp+Src]; void *
0x18001bfc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfc9  nop
0x18001bfca  mov     rcx, r14
0x18001bfcd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001bfd2  mov     rcx, [rbp+var_8]
0x18001bfd6  xor     rcx, rsp; StackCookie
0x18001bfd9  call    __security_check_cookie
0x18001bfde  mov     rbx, [rsp+80h+arg_10]
0x18001bfe6  add     rsp, 80h
0x18001bfed  pop     r15
0x18001bfef  pop     r14
0x18001bff1  pop     rdi
0x18001bff2  pop     rsi
0x18001bff3  pop     rbp
0x18001bff4  retn
```
