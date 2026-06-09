# LanguageComponentsInstallerTelemetry::InstallationTaskRun::StartActivity(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x18001bb94`
- end: `0x18001bdc1`
- name: `?StartActivity@InstallationTaskRun@LanguageComponentsInstallerTelemetry@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `557`
- prototype: `void __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800140e0`

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
- `0x18001bb94`
- `0x1800214f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd7a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bc6f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bc6f`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationTaskRun::StartActivity(
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
          (int)&byte_18002F7D7,
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
0x18001bb94  mov     [rsp-28h+arg_10], rbx
0x18001bb99  push    rbp
0x18001bb9a  push    rsi
0x18001bb9b  push    rdi
0x18001bb9c  push    r14
0x18001bb9e  push    r15
0x18001bba0  mov     rbp, rsp
0x18001bba3  sub     rsp, 80h
0x18001bbaa  mov     rax, cs:__security_cookie
0x18001bbb1  xor     rax, rsp
0x18001bbb4  mov     [rbp+var_8], rax
0x18001bbb8  mov     r14, rdx
0x18001bbbb  mov     rsi, rcx
0x18001bbbe  mov     [rbp+var_30], rdx
0x18001bbc2  mov     rdx, [rdx+8]
0x18001bbc6  xor     r9b, r9b
0x18001bbc9  mov     r8, rdx
0x18001bbcc  sub     r8, [r14]
0x18001bbcf  sar     r8, 5
0x18001bbd3  mov     rcx, [r14]
0x18001bbd6  call    ??$_Sort_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x18001bbdb  mov     r8, [r14+8]
0x18001bbdf  mov     rdx, [r14]
0x18001bbe2  lea     rcx, [rbp+SRWLock]
0x18001bbe6  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@0@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x18001bbeb  mov     r15, [r14+8]
0x18001bbef  mov     rdi, [rbp+SRWLock]
0x18001bbf3  cmp     rdi, r15
0x18001bbf6  jz      short loc_18001BC12
0x18001bbf8  mov     rbx, rdi
0x18001bbfb  mov     rcx, rbx; void *
0x18001bbfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bc03  add     rbx, 20h ; ' '
0x18001bc07  cmp     rbx, r15
0x18001bc0a  jnz     short loc_18001BBFB
0x18001bc0c  mov     [r14+8], rdi
0x18001bc10  jmp     short loc_18001BC15
0x18001bc12  mov     rdi, r15
0x18001bc15  mov     r8, rdi
0x18001bc18  mov     rdx, [r14]
0x18001bc1b  lea     rcx, [rbp+Src]; Src
0x18001bc1f  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18001bc24  nop
0x18001bc25  lea     rdx, [rbp+SRWLock]
0x18001bc29  mov     rcx, rsi
0x18001bc2c  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001bc31  mov     rbx, [rsi+110h]
0x18001bc38  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001bc3d  mov     ecx, [rax]
0x18001bc3f  mov     rdi, 400000000000h
0x18001bc49  cmp     ecx, 5
0x18001bc4c  jbe     short loc_18001BC77
0x18001bc4e  mov     rcx, [rax+18h]
0x18001bc52  mov     rax, [rax+10h]
0x18001bc56  test    rdi, rax
0x18001bc59  jz      short loc_18001BC77
0x18001bc5b  mov     rax, rcx
0x18001bc5e  and     rax, rdi
0x18001bc61  cmp     rax, rcx
0x18001bc64  jnz     short loc_18001BC77
0x18001bc66  lea     rdx, [rbx+8]; ActivityId
0x18001bc6a  mov     ecx, 3; ControlCode
0x18001bc6f  call    cs:__imp_EventActivityIdControl
0x18001bc75  jmp     short loc_18001BC7E
0x18001bc77  xorps   xmm0, xmm0
0x18001bc7a  movups  xmmword ptr [rbx+8], xmm0
0x18001bc7e  mov     dword ptr [rbx], 1
0x18001bc84  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001bc88  test    rcx, rcx
0x18001bc8b  jz      short loc_18001BC93
0x18001bc8d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bc93  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001bc98  mov     rbx, rax
0x18001bc9b  mov     ecx, [rax]
0x18001bc9d  cmp     ecx, 5
0x18001bca0  jbe     loc_18001BD47
0x18001bca6  mov     rax, [rax+18h]
0x18001bcaa  mov     rcx, [rbx+10h]
0x18001bcae  test    rdi, rcx
0x18001bcb1  jz      loc_18001BD47
0x18001bcb7  mov     rcx, rax
0x18001bcba  and     rcx, rdi
0x18001bcbd  cmp     rcx, rax
0x18001bcc0  jnz     loc_18001BD47
0x18001bcc6  lea     rax, [rbp+Src]
0x18001bcca  cmp     [rbp+var_10], 7
0x18001bccf  cmova   rax, [rbp+Src]
0x18001bcd4  mov     [rbp+var_38], rax
0x18001bcd8  call    cs:__imp_GetCurrentThreadId
0x18001bcde  mov     dword ptr [rbp+SRWLock], eax
0x18001bce1  mov     [rbp+var_30], 3000000h
0x18001bce9  mov     r8, [rsi+110h]
0x18001bcf0  cmp     byte ptr [r8+4], 0
0x18001bcf5  jz      short loc_18001BD16
0x18001bcf7  lea     r9, [r8+18h]
0x18001bcfb  cmp     dword ptr [r9], 0
0x18001bcff  jnz     short loc_18001BD19
0x18001bd01  cmp     dword ptr [r9+4], 0
0x18001bd06  jnz     short loc_18001BD19
0x18001bd08  cmp     dword ptr [r9+8], 0
0x18001bd0d  jnz     short loc_18001BD19
0x18001bd0f  cmp     dword ptr [r9+0Ch], 0
0x18001bd14  jnz     short loc_18001BD19
0x18001bd16  xor     r9d, r9d
0x18001bd19  add     r8, 8
0x18001bd1d  lea     rax, [rbp+var_38]
0x18001bd21  mov     [rsp+80h+var_50], rax; __int64
0x18001bd26  lea     rax, [rbp+SRWLock]
0x18001bd2a  mov     [rsp+80h+var_58], rax; __int64
0x18001bd2f  lea     rax, [rbp+var_30]
0x18001bd33  mov     [rsp+80h+var_60], rax; __int64
0x18001bd38  lea     rdx, byte_18002F7D7
0x18001bd3f  mov     rcx, rbx; int
0x18001bd42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001bd47  cmp     dword ptr [rsi+138h], 0
0x18001bd4e  jnz     short loc_18001BD8C
0x18001bd50  lea     rbx, [rsi+120h]
0x18001bd57  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bd5f  jz      short loc_18001BD85
0x18001bd61  mov     dl, 1
0x18001bd63  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001bd68  mov     [rbx], rax
0x18001bd6b  test    rax, rax
0x18001bd6e  jz      short loc_18001BD8C
0x18001bd70  mov     rcx, [rax]
0x18001bd73  mov     [rbx+10h], rcx
0x18001bd77  mov     [rax], rbx
0x18001bd7a  call    cs:__imp_GetCurrentThreadId
0x18001bd80  mov     [rbx+18h], eax
0x18001bd83  jmp     short loc_18001BD8C
0x18001bd85  mov     qword ptr [rbx], 0
0x18001bd8c  lea     rcx, [rbp+Src]; void *
0x18001bd90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bd95  nop
0x18001bd96  mov     rcx, r14
0x18001bd99  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001bd9e  mov     rcx, [rbp+var_8]
0x18001bda2  xor     rcx, rsp; StackCookie
0x18001bda5  call    __security_check_cookie
0x18001bdaa  mov     rbx, [rsp+80h+arg_10]
0x18001bdb2  add     rsp, 80h
0x18001bdb9  pop     r15
0x18001bdbb  pop     r14
0x18001bdbd  pop     rdi
0x18001bdbe  pop     rsi
0x18001bdbf  pop     rbp
0x18001bdc0  retn
```
