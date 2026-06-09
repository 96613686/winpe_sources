# PhoneLine::CheckOwnershipPolicy(ushort const *,ISecurityToken *)

- ea: `0x18006df58`
- end: `0x18006e275`
- name: `?CheckOwnershipPolicy@PhoneLine@@QEAAJPEBGPEAUISecurityToken@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(PhoneLine *__hidden this, const unsigned __int16 *, struct ISecurityToken *)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022b10`
- `0x180029990`
- `0x18002d8c0`
- `0x180030ee0`
- `0x1800368d0`
- `0x180037804`
- `0x18003993c`
- `0x180039b14`
- `0x18003bcc8`

## callees

- `0x180006e94`
- `0x18000c058`
- `0x18006df58`
- `0x180070030`
- `0x180071ba8`
- `0x180076f7c`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e252`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e19c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e19c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e216`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e157`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e157`
- `PhoneUtil!GetUserSecurityIdentifierForToken` at `0x18006e0c2`
- `PhoneUtil!GetUserSecurityIdentifierForToken` at `0x18006e0c2`

## string_xrefs

- `0x18006dfd7`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18006e03a`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18006e0dc`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18006e185`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneLine::CheckOwnershipPolicy(
        PhoneLine *this,
        const unsigned __int16 *a2,
        struct ISecurityToken *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  int v7; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rbx
  int v11; // eax
  BackTraceCollection *v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rdi
  int UserSecurityIdentifierForToken; // eax
  BackTraceCollection *v16; // rcx
  signed int LastError; // eax
  BackTraceCollection *v18; // rcx
  unsigned int v19; // esi
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  BackTraceCollection *v23; // rcx
  __int64 v25; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid; // [rsp+40h] [rbp-20h] BYREF
  int v28; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-10h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( *((_OWORD *)this + 7) == __PAIR128__(0xE69A23D3981DAB9FuLL, CellularLineType) )
  {
LABEL_44:
    v9 = 0;
    goto LABEL_45;
  }
  v25 = 0;
  v7 = WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get((char *)this + 32, &v25);
  v9 = v7;
  if ( v7 < 0 )
  {
    BackTraceCollection::Capture(v8, v7);
    Log_HREvent_19(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1935);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    goto LABEL_45;
  }
  v10 = v25;
  v26[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 192LL))(v25, v26);
  v13 = v11;
  if ( v11 < 0 )
  {
    BackTraceCollection::Capture(v12, v11);
    Log_HREvent_19(v13, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1938);
LABEL_7:
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v9 = v13;
    goto LABEL_45;
  }
  if ( !v26[0] )
  {
LABEL_42:
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_44;
  }
  v14 = *((_QWORD *)this + 13);
  v28 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  (*(void (__fastcall **)(__int64, struct ISecurityToken *, int *))(*(_QWORD *)v14 + 32LL))(v14, a3, &v28);
  if ( v28 )
    goto LABEL_41;
  Sid = 0;
  UserSecurityIdentifierForToken = GetUserSecurityIdentifierForToken(a3, (struct _SID **)&Sid);
  v13 = UserSecurityIdentifierForToken;
  if ( UserSecurityIdentifierForToken < 0 )
  {
    BackTraceCollection::Capture(v16, UserSecurityIdentifierForToken);
    Log_HREvent_19(v13, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1953);
    if ( Sid )
      _HeapFreer<_SID>(Sid);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_7;
  }
  if ( !Sid )
  {
LABEL_41:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_42;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
      goto LABEL_39;
  }
  else if ( !a2 )
  {
    goto LABEL_24;
  }
  if ( !*a2 )
  {
LABEL_39:
    if ( Sid )
      _HeapFreer<_SID>(Sid);
    goto LABEL_41;
  }
LABEL_24:
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v22 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, LPWSTR))(*(_QWORD *)v10 + 200LL))(
            v10,
            a2,
            StringSid);
    v19 = v22;
    if ( v22 >= 0 )
    {
      if ( StringSid )
        LocalFree(StringSid);
      goto LABEL_39;
    }
    BackTraceCollection::Capture(v23, v22);
    v20 = 1985;
    v21 = 1;
  }
  else
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v18, v19);
    v20 = 1983;
    v21 = 0;
  }
  Log_HREvent_19(v19, v21, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v20);
  if ( StringSid )
    LocalFree(StringSid);
  if ( Sid )
    _HeapFreer<_SID>(Sid);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v9 = v19;
LABEL_45:
  LeaveCriticalSection(v3);
  return v9;
}

```

## disassembly

```asm
0x18006df58  push    rbp
0x18006df5a  push    rbx
0x18006df5b  push    rsi
0x18006df5c  push    rdi
0x18006df5d  push    r12
0x18006df5f  push    r14
0x18006df61  push    r15
0x18006df63  mov     rbp, rsp
0x18006df66  sub     rsp, 60h
0x18006df6a  mov     rax, cs:__security_cookie
0x18006df71  xor     rax, rsp
0x18006df74  mov     [rbp+var_8], rax
0x18006df78  lea     r12, [rcx+88h]
0x18006df7f  mov     rdi, rcx
0x18006df82  mov     rcx, r12; lpCriticalSection
0x18006df85  mov     r15, r8
0x18006df88  mov     rsi, rdx
0x18006df8b  call    cs:__imp_EnterCriticalSection
0x18006df91  mov     rax, [rdi+70h]
0x18006df95  cmp     rax, cs:CellularLineType
0x18006df9c  jnz     short loc_18006DFAF
0x18006df9e  mov     rax, [rdi+78h]
0x18006dfa2  cmp     rax, cs:qword_18009AC68
0x18006dfa9  jz      loc_18006E24D
0x18006dfaf  lea     rcx, [rdi+20h]
0x18006dfb3  mov     [rbp+var_30], 0
0x18006dfbb  lea     rdx, [rbp+var_30]
0x18006dfbf  call    ?Get@?$WrappedComPtrBase@UIPhoneLine@@VSupportsShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneLine@@@Z; WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get(IPhoneLine * *)
0x18006dfc4  mov     ebx, eax
0x18006dfc6  test    eax, eax
0x18006dfc8  jns     short loc_18006E008
0x18006dfca  mov     edx, eax; int
0x18006dfcc  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006dfd1  mov     r9d, 78Fh
0x18006dfd7  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006dfde  mov     edx, 1
0x18006dfe3  mov     ecx, ebx
0x18006dfe5  call    Log_HREvent_19
0x18006dfea  mov     rcx, [rbp+var_30]
0x18006dfee  test    rcx, rcx
0x18006dff1  jz      loc_18006E24F
0x18006dff7  mov     rax, [rcx]
0x18006dffa  mov     rax, [rax+10h]
0x18006dffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e003  jmp     loc_18006E24F
0x18006e008  mov     rbx, [rbp+var_30]
0x18006e00c  lea     rdx, [rbp+var_28]
0x18006e010  mov     [rbp+var_28], 0
0x18006e014  mov     rcx, rbx
0x18006e017  mov     rax, [rbx]
0x18006e01a  mov     rax, [rax+0C0h]
0x18006e021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e026  mov     r14d, eax
0x18006e029  test    eax, eax
0x18006e02b  jns     short loc_18006E06A
0x18006e02d  mov     edx, eax; int
0x18006e02f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006e034  mov     r9d, 792h
0x18006e03a  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006e041  mov     edx, 1
0x18006e046  mov     ecx, r14d
0x18006e049  call    Log_HREvent_19
0x18006e04e  test    rbx, rbx
0x18006e051  jz      short loc_18006E062
0x18006e053  mov     rax, [rbx]
0x18006e056  mov     rcx, rbx
0x18006e059  mov     rax, [rax+10h]
0x18006e05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e062  mov     ebx, r14d
0x18006e065  jmp     loc_18006E24F
0x18006e06a  cmp     [rbp+var_28], 0
0x18006e06e  jz      loc_18006E239
0x18006e074  mov     rdi, [rdi+68h]
0x18006e078  mov     [rbp+var_18], 0
0x18006e07f  test    rdi, rdi
0x18006e082  jz      short loc_18006E093
0x18006e084  mov     rax, [rdi]
0x18006e087  mov     rcx, rdi
0x18006e08a  mov     rax, [rax+8]
0x18006e08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e093  mov     rax, [rdi]
0x18006e096  lea     r8, [rbp+var_18]
0x18006e09a  mov     rdx, r15
0x18006e09d  mov     rcx, rdi
0x18006e0a0  mov     rax, [rax+20h]
0x18006e0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0a9  cmp     [rbp+var_18], 0
0x18006e0ad  jnz     loc_18006E22A
0x18006e0b3  lea     rdx, [rbp+Sid]
0x18006e0b7  mov     [rbp+Sid], 0
0x18006e0bf  mov     rcx, r15
0x18006e0c2  call    cs:__imp_?GetUserSecurityIdentifierForToken@@YAJPEAUISecurityToken@@PEAPEAU_SID@@@Z; GetUserSecurityIdentifierForToken(ISecurityToken *,_SID * *)
0x18006e0c8  mov     r14d, eax
0x18006e0cb  test    eax, eax
0x18006e0cd  jns     short loc_18006E112
0x18006e0cf  mov     edx, eax; int
0x18006e0d1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006e0d6  mov     r9d, 7A1h
0x18006e0dc  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006e0e3  mov     edx, 1
0x18006e0e8  mov     ecx, r14d
0x18006e0eb  call    Log_HREvent_19
0x18006e0f0  mov     rcx, [rbp+Sid]
0x18006e0f4  test    rcx, rcx
0x18006e0f7  jz      short loc_18006E0FE
0x18006e0f9  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x18006e0fe  mov     rax, [rdi]
0x18006e101  mov     rcx, rdi
0x18006e104  mov     rax, [rax+10h]
0x18006e108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e10d  jmp     loc_18006E04E
0x18006e112  cmp     [rbp+Sid], 0
0x18006e117  jz      loc_18006E22A
0x18006e11d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard> `wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard>::GetImpl(void)'::`2'::impl
0x18006e124  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_NullAumidGuard>::__private_IsEnabled(void)
0x18006e129  test    al, al
0x18006e12b  jz      short loc_18006E142
0x18006e12d  test    rsi, rsi
0x18006e130  jz      loc_18006E21C
0x18006e136  xor     eax, eax
0x18006e138  cmp     ax, [rsi]
0x18006e13b  jnz     short loc_18006E147
0x18006e13d  jmp     loc_18006E21C
0x18006e142  test    rsi, rsi
0x18006e145  jnz     short loc_18006E136
0x18006e147  mov     rcx, [rbp+Sid]; Sid
0x18006e14b  lea     rdx, [rbp+StringSid]; StringSid
0x18006e14f  mov     [rbp+StringSid], 0
0x18006e157  call    cs:__imp_ConvertSidToStringSidW
0x18006e15d  test    eax, eax
0x18006e15f  jnz     short loc_18006E1D7
0x18006e161  call    cs:__imp_GetLastError
0x18006e167  mov     esi, eax
0x18006e169  test    eax, eax
0x18006e16b  jle     short loc_18006E176
0x18006e16d  movzx   esi, ax
0x18006e170  or      esi, 80070000h
0x18006e176  mov     edx, esi; int
0x18006e178  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006e17d  mov     r9d, 7BFh
0x18006e183  xor     edx, edx
0x18006e185  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006e18c  mov     ecx, esi
0x18006e18e  call    Log_HREvent_19
0x18006e193  mov     rcx, [rbp+StringSid]; hMem
0x18006e197  test    rcx, rcx
0x18006e19a  jz      short loc_18006E1A2
0x18006e19c  call    cs:__imp_LocalFree
0x18006e1a2  mov     rcx, [rbp+Sid]
0x18006e1a6  test    rcx, rcx
0x18006e1a9  jz      short loc_18006E1B0
0x18006e1ab  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x18006e1b0  mov     rax, [rdi]
0x18006e1b3  mov     rcx, rdi
0x18006e1b6  mov     rax, [rax+10h]
0x18006e1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1bf  test    rbx, rbx
0x18006e1c2  jz      short loc_18006E1D3
0x18006e1c4  mov     rax, [rbx]
0x18006e1c7  mov     rcx, rbx
0x18006e1ca  mov     rax, [rax+10h]
0x18006e1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1d3  mov     ebx, esi
0x18006e1d5  jmp     short loc_18006E24F
0x18006e1d7  mov     rax, [rbx]
0x18006e1da  mov     rdx, rsi
0x18006e1dd  mov     r8, [rbp+StringSid]
0x18006e1e1  mov     rcx, rbx
0x18006e1e4  mov     rax, [rax+0C8h]
0x18006e1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1f0  mov     esi, eax
0x18006e1f2  test    eax, eax
0x18006e1f4  jns     short loc_18006E20D
0x18006e1f6  mov     edx, eax; int
0x18006e1f8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006e1fd  mov     r9d, 7C1h
0x18006e203  mov     edx, 1
0x18006e208  jmp     loc_18006E185
0x18006e20d  mov     rcx, [rbp+StringSid]; hMem
0x18006e211  test    rcx, rcx
0x18006e214  jz      short loc_18006E21C
0x18006e216  call    cs:__imp_LocalFree
0x18006e21c  mov     rcx, [rbp+Sid]
0x18006e220  test    rcx, rcx
0x18006e223  jz      short loc_18006E22A
0x18006e225  call    ??$_HeapFreer@U_SID@@@@YAXPEAU_SID@@@Z; _HeapFreer<_SID>(_SID *)
0x18006e22a  mov     rax, [rdi]
0x18006e22d  mov     rcx, rdi
0x18006e230  mov     rax, [rax+10h]
0x18006e234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e239  test    rbx, rbx
0x18006e23c  jz      short loc_18006E24D
0x18006e23e  mov     rax, [rbx]
0x18006e241  mov     rcx, rbx
0x18006e244  mov     rax, [rax+10h]
0x18006e248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e24d  xor     ebx, ebx
0x18006e24f  mov     rcx, r12; lpCriticalSection
0x18006e252  call    cs:__imp_LeaveCriticalSection
0x18006e258  mov     eax, ebx
0x18006e25a  mov     rcx, [rbp+var_8]
0x18006e25e  xor     rcx, rsp; StackCookie
0x18006e261  call    __security_check_cookie
0x18006e266  add     rsp, 60h
0x18006e26a  pop     r15
0x18006e26c  pop     r14
0x18006e26e  pop     r12
0x18006e270  pop     rdi
0x18006e271  pop     rsi
0x18006e272  pop     rbx
0x18006e273  pop     rbp
0x18006e274  retn
```
