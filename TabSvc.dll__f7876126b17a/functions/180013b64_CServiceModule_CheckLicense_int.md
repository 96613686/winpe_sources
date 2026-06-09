# CServiceModule::_CheckLicense(int)

- ea: `0x180013b64`
- end: `0x180013cb5`
- name: `?_CheckLicense@CServiceModule@@AEAAHH@Z`
- size: `337`
- prototype: `__int64 __fastcall(CServiceModule *this, __int64, struct _GUID *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000fa00`
- `0x180023bd0`
- `0x180025bbc`
- `0x180028964`

## callees

- `0x180003860`
- `0x1800110e0`
- `0x180012680`
- `0x180013b64`
- `0x1800197dc`
- `0x18001a174`
- `0x180028578`

## string_xrefs

- `0x180013c59`: `drivers\tablet\platform\pen\penservice\tpcquery\tpcquery.cpp`

## pseudocode

```c
__int64 __fastcall CServiceModule::_CheckLicense(CServiceModule *this, __int64 a2, struct _GUID *a3, unsigned int a4)
{
  unsigned int v4; // edi
  unsigned __int64 v6; // r8
  char *v7; // rax
  const struct _GUID *v8; // rcx
  unsigned __int64 v9; // r8
  const struct _GUID *v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  char IsEnabled; // al
  unsigned int v17; // ecx
  unsigned int v18; // esi
  unsigned int v19; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = a2;
  if ( !(_DWORD)a2 )
    goto LABEL_15;
  v6 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v6 )
    PrivateTraceEvent((const struct _GUID *)this, 0x615u, v6, 1u);
  v7 = CPenProcessInfo::Path(*((CPenProcessInfo **)this + 70));
  a3 = WPP_GLOBAL_Control;
  v8 = 0;
  if ( v7 )
    v8 = (const struct _GUID *)v4;
  v4 = (unsigned int)v8;
  if ( *(_QWORD *)WPP_GLOBAL_Control[3].Data4 )
  {
    PrivateTraceEvent(v8, 0x615u, *(_QWORD *)WPP_GLOBAL_Control[3].Data4, 2u);
    a3 = WPP_GLOBAL_Control;
  }
  if ( !v4 )
    goto LABEL_15;
  v9 = *(_QWORD *)a3[3].Data4;
  if ( v9 )
    PrivateTraceEvent(v8, 0x614u, v9, 1u);
  v4 = LicenseCheck();
  a3 = *(struct _GUID **)WPP_GLOBAL_Control[3].Data4;
  if ( a3 )
    PrivateTraceEvent(v10, 0x614u, (unsigned __int64)a3, 2u);
  if ( v4 )
    v11 = HIDWORD(qword_180041278) | 0x80;
  else
LABEL_15:
    v11 = HIDWORD(qword_180041278) & 0xFFFFFF7F;
  v12 = dword_180041280;
  HIDWORD(qword_180041278) = v11;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          a2,
                          (__int64)a3,
                          a4)
    && (v11 & 0xFFFFFE30) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB2,
      (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\tpcquery\\tpcquery.cpp",
      v15);
  }
  if ( v12 > 0xFFFF )
    v12 = 0xFFFF;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                v13,
                v14,
                (unsigned int)v15);
  v17 = v12;
  v18 = v12 << 16;
  v19 = v17 << 8;
  if ( !IsEnabled )
    v18 = v19;
  CTabTipProcessInfo::_AddRemoveUserAgentStringKey((v11 & 0x1CF | v18) != 0);
  return v4;
}

```

## disassembly

```asm
0x180013b64  mov     [rsp+arg_0], rbx
0x180013b69  mov     [rsp+arg_8], rsi
0x180013b6e  push    rdi
0x180013b6f  sub     rsp, 20h
0x180013b73  mov     edi, edx
0x180013b75  mov     rbx, rcx
0x180013b78  test    edx, edx
0x180013b7a  jz      loc_180013C26
0x180013b80  mov     rax, cs:WPP_GLOBAL_Control
0x180013b87  mov     esi, 615h
0x180013b8c  mov     r8, [rax+38h]; unsigned __int64
0x180013b90  test    r8, r8
0x180013b93  jz      short loc_180013B9F
0x180013b95  mov     r9b, 1; unsigned __int8
0x180013b98  mov     edx, esi; unsigned int
0x180013b9a  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180013b9f  mov     rcx, [rbx+230h]; this
0x180013ba6  call    ?Path@CPenProcessInfo@@QEBAPEBGXZ; CPenProcessInfo::Path(void)
0x180013bab  mov     r8, cs:WPP_GLOBAL_Control
0x180013bb2  xor     ecx, ecx
0x180013bb4  test    rax, rax
0x180013bb7  cmovnz  ecx, edi; struct _GUID *
0x180013bba  mov     rax, [r8+38h]
0x180013bbe  mov     edi, ecx
0x180013bc0  test    rax, rax
0x180013bc3  jz      short loc_180013BD9
0x180013bc5  mov     r9b, 2; unsigned __int8
0x180013bc8  mov     r8, rax; unsigned __int64
0x180013bcb  mov     edx, esi; unsigned int
0x180013bcd  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180013bd2  mov     r8, cs:WPP_GLOBAL_Control
0x180013bd9  test    edi, edi
0x180013bdb  jz      short loc_180013C26
0x180013bdd  mov     r8, [r8+38h]; unsigned __int64
0x180013be1  mov     ebx, 614h
0x180013be6  test    r8, r8
0x180013be9  jz      short loc_180013BF5
0x180013beb  mov     r9b, 1; unsigned __int8
0x180013bee  mov     edx, ebx; unsigned int
0x180013bf0  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180013bf5  call    ?LicenseCheck@@YAHXZ; LicenseCheck(void)
0x180013bfa  mov     edi, eax
0x180013bfc  mov     rax, cs:WPP_GLOBAL_Control
0x180013c03  mov     r8, [rax+38h]; unsigned __int64
0x180013c07  test    r8, r8
0x180013c0a  jz      short loc_180013C16
0x180013c0c  mov     r9b, 2; unsigned __int8
0x180013c0f  mov     edx, ebx; unsigned int
0x180013c11  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180013c16  test    edi, edi
0x180013c18  jz      short loc_180013C26
0x180013c1a  mov     ebx, dword ptr cs:qword_180041278+4
0x180013c20  bts     ebx, 7
0x180013c24  jmp     short loc_180013C30
0x180013c26  mov     ebx, dword ptr cs:qword_180041278+4
0x180013c2c  btr     ebx, 7
0x180013c30  mov     esi, cs:dword_180041280
0x180013c36  mov     dword ptr cs:qword_180041278+4, ebx
0x180013c3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180013c43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180013c48  test    al, al
0x180013c4a  jz      short loc_180013C6B
0x180013c4c  test    ebx, 0FFFFFE30h
0x180013c52  jz      short loc_180013C6B
0x180013c54  mov     rcx, [rsp+28h]; this
0x180013c59  lea     r8, aDriversTabletP_0; "drivers\\tablet\\platform\\pen\\penserv"...
0x180013c60  mov     edx, 0B2h; void *
0x180013c65  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013c6b  mov     eax, 0FFFFh
0x180013c70  cmp     esi, eax
0x180013c72  cmova   esi, eax
0x180013c75  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180013c7c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180013c81  mov     ecx, esi
0x180013c83  shl     esi, 10h
0x180013c86  shl     ecx, 8
0x180013c89  test    al, al
0x180013c8b  cmovz   esi, ecx
0x180013c8e  and     ebx, 1CFh
0x180013c94  or      esi, ebx
0x180013c96  mov     ecx, 0
0x180013c9b  setnz   cl; int
0x180013c9e  call    ?_AddRemoveUserAgentStringKey@CTabTipProcessInfo@@CAXH@Z; CTabTipProcessInfo::_AddRemoveUserAgentStringKey(int)
0x180013ca3  mov     rbx, [rsp+28h+arg_0]
0x180013ca8  mov     eax, edi
0x180013caa  mov     rsi, [rsp+28h+arg_8]
0x180013caf  add     rsp, 20h
0x180013cb3  pop     rdi
0x180013cb4  retn
```
