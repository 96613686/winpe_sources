# OSIntegration::DEH::CMRTHandler::_WriteRegistryKeys(ushort const *,ushort const *,ushort const *,ulong,OSIntegration::DEH::CMRTHandler::WRITE_REGISTRY_FLAGS)

- ea: `0x180073764`
- end: `0x180073b08`
- name: `?_WriteRegistryKeys@CMRTHandler@DEH@OSIntegration@@AEAAJPEBG00KW4WRITE_REGISTRY_FLAGS@123@@Z`
- size: `932`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049990`
- `0x1800734b0`
- `0x18013e680`

## callees

- `0x18000e6e0`
- `0x18000fed0`
- `0x1800138e0`
- `0x180073764`
- `0x180098bf4`
- `0x1800f0700`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800738d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800738d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800738a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800738ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800738a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800738ee`
- `Bcp47Langs!GetApplicationManifestLanguages` at `0x1800738c3`
- `Bcp47Langs!GetApplicationManifestLanguages` at `0x1800738c3`
- `Bcp47Langs!ClearApplicationManifestLanguages` at `0x180073a87`
- `Bcp47Langs!ClearApplicationManifestLanguages` at `0x180073a87`
- `Bcp47Langs!SetApplicationManifestLanguages` at `0x180073933`
- `Bcp47Langs!SetApplicationManifestLanguages` at `0x180073933`

## string_xrefs

- `0x1800737ea`: `CachedMergedResourcesPriFileName`
- `0x18007396d`: `CachedMergedResourcesPriFileName`
- `0x180073871`: `ManifestLanguagesList`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::CMRTHandler::_WriteRegistryKeys(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        char a6)
{
  int v10; // edi
  int v11; // eax
  int v12; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // ebx
  __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  __int64 v27; // rdx
  int v28; // [rsp+20h] [rbp-48h]
  int v29; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v31[2]; // [rsp+40h] [rbp-28h] BYREF
  int v32; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  char v34; // [rsp+A0h] [rbp+38h] BYREF

  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 40) + 8LL))(
          *(_QWORD *)(a1 + 40),
          *(_QWORD *)(a1 + 32));
  if ( v10 < 0 )
  {
    v16 = 513;
    goto LABEL_19;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 16LL))(*(_QWORD *)(a1 + 40));
  if ( v10 < 0 )
  {
    v16 = 515;
    goto LABEL_19;
  }
  if ( (a6 & 1) != 0 )
  {
    *(_OWORD *)v31 = 0;
    v32 = 0;
    v29 = 101;
    v34 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            L"CachedMergedResourcesPriFileName",
            &v34,
            a1 + 384);
    v10 = v11;
    if ( v11 < 0 )
    {
      v27 = 525;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
              *(_QWORD *)(a1 + 40),
              L"SharedMergedResourcesPriFileName",
              &v34,
              a1 + 408);
      v10 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
          (const char *)(unsigned int)v12,
          v28);
        if ( v31[1] )
          operator delete(v31[1], v26);
        return (unsigned int)v10;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *, int *))(**(_QWORD **)(a1 + 40) + 56LL))(
              *(_QWORD *)(a1 + 40),
              L"MergedResourcesIndex",
              &v34,
              &v29);
      v10 = v11;
      if ( v11 < 0 )
      {
        v27 = 527;
      }
      else
      {
        *(_DWORD *)(a1 + 432) = v29;
        v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *, unsigned __int16 **))(**(_QWORD **)(a1 + 40)
                                                                                              + 32LL))(
                *(_QWORD *)(a1 + 40),
                L"ManifestLanguagesList",
                &v34,
                v31);
        v10 = v11;
        if ( v11 >= 0 )
        {
          if ( v34 && LODWORD(v31[0]) )
          {
            string = 0;
            WindowsDeleteString(0);
            string = 0;
            if ( (int)GetApplicationManifestLanguages(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 248LL), 59, &string) >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v31, StringRawBuffer);
            }
            if ( string )
              WindowsDeleteString(string);
          }
          Common::StringBuffer::SetValue((Common::StringBuffer *)(a1 + 360), v31[1], (unsigned int)v31[0]);
          if ( v31[1] )
            operator delete(v31[1], v14);
          goto LABEL_16;
        }
        v27 = 530;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
      (const char *)(unsigned int)v11,
      v28);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
    return (unsigned int)v10;
  }
LABEL_16:
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 248LL);
  if ( a2 )
  {
    v10 = SetApplicationManifestLanguages(v15, 59, a2);
    if ( v10 < 0 )
    {
      v16 = 547;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v10,
        v28);
      return (unsigned int)v10;
    }
  }
  else
  {
    v10 = ClearApplicationManifestLanguages(v15);
    if ( v10 < 0 )
    {
      v16 = 551;
      goto LABEL_19;
    }
  }
  v18 = *(__int64 **)(a1 + 40);
  v19 = *v18;
  if ( a3 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(v19 + 40))(
            v18,
            L"CachedMergedResourcesPriFileName",
            a3);
    if ( v10 < 0 )
    {
      v16 = 556;
      goto LABEL_19;
    }
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(v19 + 48))(v18, L"CachedMergedResourcesPriFileName");
    if ( v10 < 0 )
    {
      v16 = 560;
      goto LABEL_19;
    }
  }
  v20 = *(__int64 **)(a1 + 40);
  v21 = *v20;
  if ( a4 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(v21 + 40))(
            v20,
            L"SharedMergedResourcesPriFileName",
            a4);
    if ( v10 < 0 )
    {
      v16 = 565;
      goto LABEL_19;
    }
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(v21 + 48))(v20, L"SharedMergedResourcesPriFileName");
    if ( v10 < 0 )
    {
      v16 = 569;
      goto LABEL_19;
    }
  }
  v22 = *(__int64 **)(a1 + 40);
  v23 = *v22;
  if ( a5 >= 0x64 )
  {
    v24 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(v23 + 48))(v22, L"MergedResourcesIndex");
    if ( v24 < 0 )
    {
      v25 = 578;
      goto LABEL_29;
    }
  }
  else
  {
    v24 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(v23 + 64))(v22, L"MergedResourcesIndex");
    if ( v24 < 0 )
    {
      v25 = 574;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
        (const char *)(unsigned int)v24,
        v28);
      return (unsigned int)v24;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180073764  push    rbp
0x180073766  push    rbx
0x180073767  push    rsi
0x180073768  push    rdi
0x180073769  push    r14
0x18007376b  push    r15
0x18007376d  mov     rbp, rsp
0x180073770  sub     rsp, 68h
0x180073774  mov     r15, r9
0x180073777  mov     r14, r8
0x18007377a  mov     rsi, rdx
0x18007377d  mov     rbx, rcx
0x180073780  mov     rcx, [rcx+28h]
0x180073784  mov     rax, [rcx]
0x180073787  mov     rdx, [rbx+20h]
0x18007378b  mov     rax, [rax+8]
0x18007378f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073794  mov     edi, eax
0x180073796  test    eax, eax
0x180073798  js      loc_180073A3E
0x18007379e  mov     rcx, [rbx+28h]
0x1800737a2  mov     rax, [rcx]
0x1800737a5  mov     rax, [rax+10h]
0x1800737a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737ae  mov     edi, eax
0x1800737b0  test    eax, eax
0x1800737b2  js      loc_180073A48
0x1800737b8  test    [rbp+arg_28], 1
0x1800737bc  jz      loc_180073917
0x1800737c2  xor     eax, eax
0x1800737c4  xorps   xmm0, xmm0
0x1800737c7  movups  xmmword ptr [rbp+var_28], xmm0
0x1800737cb  mov     [rbp+var_18], eax
0x1800737ce  mov     [rbp+var_38], 65h ; 'e'
0x1800737d5  mov     [rbp+arg_0], al
0x1800737d8  mov     rcx, [rbx+28h]
0x1800737dc  mov     rax, [rcx]
0x1800737df  lea     r9, [rbx+180h]
0x1800737e6  lea     r8, [rbp+arg_0]
0x1800737ea  lea     rdx, aCachedmergedre; "CachedMergedResourcesPriFileName"
0x1800737f1  mov     rax, [rax+20h]
0x1800737f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737fa  mov     edi, eax
0x1800737fc  test    eax, eax
0x1800737fe  js      loc_180073A52
0x180073804  mov     rcx, [rbx+28h]
0x180073808  mov     rax, [rcx]
0x18007380b  lea     r9, [rbx+198h]
0x180073812  lea     r8, [rbp+arg_0]
0x180073816  lea     rdx, aSharedmergedre; "SharedMergedResourcesPriFileName"
0x18007381d  mov     rax, [rax+20h]
0x180073821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073826  mov     edi, eax
0x180073828  test    eax, eax
0x18007382a  js      loc_180073A0E
0x180073830  mov     rcx, [rbx+28h]
0x180073834  mov     rax, [rcx]
0x180073837  lea     r9, [rbp+var_38]
0x18007383b  lea     r8, [rbp+arg_0]
0x18007383f  lea     rdx, aMergedresource; "MergedResourcesIndex"
0x180073846  mov     rax, [rax+38h]
0x18007384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007384f  mov     edi, eax
0x180073851  test    eax, eax
0x180073853  js      loc_180073A59
0x180073859  mov     eax, [rbp+var_38]
0x18007385c  mov     [rbx+1B0h], eax
0x180073862  mov     rcx, [rbx+28h]
0x180073866  mov     rax, [rcx]
0x180073869  lea     r9, [rbp+var_28]
0x18007386d  lea     r8, [rbp+arg_0]
0x180073871  lea     rdx, aManifestlangua; "ManifestLanguagesList"
0x180073878  mov     rax, [rax+20h]
0x18007387c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073881  mov     edi, eax
0x180073883  test    eax, eax
0x180073885  js      loc_180073A60
0x18007388b  cmp     [rbp+arg_0], 0
0x18007388f  jz      short loc_1800738F4
0x180073891  cmp     dword ptr [rbp+var_28], 0
0x180073895  jbe     short loc_1800738F4
0x180073897  mov     [rbp+string], 0
0x18007389f  xor     ecx, ecx; string
0x1800738a1  call    cs:__imp_WindowsDeleteString
0x1800738a7  mov     [rbp+string], 0
0x1800738af  mov     edx, 3Bh ; ';'
0x1800738b4  mov     rcx, [rbx+20h]
0x1800738b8  lea     r8, [rbp+string]
0x1800738bc  mov     rcx, [rcx+0F8h]
0x1800738c3  call    cs:__imp_GetApplicationManifestLanguages
0x1800738c9  test    eax, eax
0x1800738cb  js      short loc_1800738E5
0x1800738cd  xor     edx, edx; length
0x1800738cf  mov     rcx, [rbp+string]; string
0x1800738d3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800738d9  mov     rdx, rax; unsigned __int16 *
0x1800738dc  lea     rcx, [rbp+var_28]; this
0x1800738e0  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800738e5  mov     rcx, [rbp+string]; string
0x1800738e9  test    rcx, rcx
0x1800738ec  jz      short loc_1800738F4
0x1800738ee  call    cs:__imp_WindowsDeleteString
0x1800738f4  lea     rcx, [rbx+168h]; this
0x1800738fb  mov     r8d, dword ptr [rbp+var_28]; unsigned int
0x1800738ff  mov     rdx, [rbp+var_28+8]; unsigned __int16 *
0x180073903  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180073908  nop
0x180073909  mov     rcx, [rbp+var_28+8]; void *
0x18007390d  test    rcx, rcx
0x180073910  jz      short loc_180073917
0x180073912  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180073917  mov     rax, [rbx+20h]
0x18007391b  mov     rcx, [rax+0F8h]
0x180073922  test    rsi, rsi
0x180073925  jz      loc_180073A87
0x18007392b  mov     edx, 3Bh ; ';'
0x180073930  mov     r8, rsi
0x180073933  call    cs:__imp_SetApplicationManifestLanguages
0x180073939  mov     edi, eax
0x18007393b  test    eax, eax
0x18007393d  jns     short loc_180073966
0x18007393f  mov     edx, 223h; void *
0x180073944  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007394b  mov     r9d, edi; char *
0x18007394e  mov     rcx, [rbp+30h]; this
0x180073952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073957  mov     eax, edi
0x180073959  add     rsp, 68h
0x18007395d  pop     r15
0x18007395f  pop     r14
0x180073961  pop     rdi
0x180073962  pop     rsi
0x180073963  pop     rbx
0x180073964  pop     rbp
0x180073965  retn
0x180073966  mov     rcx, [rbx+28h]
0x18007396a  mov     rax, [rcx]
0x18007396d  lea     rdx, aCachedmergedre; "CachedMergedResourcesPriFileName"
0x180073974  test    r14, r14
0x180073977  jnz     loc_180073AA1
0x18007397d  mov     rax, [rax+30h]
0x180073981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073986  mov     edi, eax
0x180073988  test    eax, eax
0x18007398a  jns     short loc_180073993
0x18007398c  mov     edx, 230h
0x180073991  jmp     short loc_180073944
0x180073993  mov     rcx, [rbx+28h]
0x180073997  mov     rax, [rcx]
0x18007399a  lea     rdx, aSharedmergedre; "SharedMergedResourcesPriFileName"
0x1800739a1  test    r15, r15
0x1800739a4  jz      loc_180073ACB
0x1800739aa  mov     r8, r15
0x1800739ad  mov     rax, [rax+28h]
0x1800739b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739b6  mov     edi, eax
0x1800739b8  test    eax, eax
0x1800739ba  js      loc_180073AC1
0x1800739c0  mov     rcx, [rbx+28h]
0x1800739c4  mov     rax, [rcx]
0x1800739c7  mov     r8d, [rbp+arg_20]
0x1800739cb  lea     rdx, aMergedresource; "MergedResourcesIndex"
0x1800739d2  cmp     r8d, 64h ; 'd'
0x1800739d6  jnb     loc_180073AE8
0x1800739dc  mov     rax, [rax+40h]
0x1800739e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739e5  mov     ebx, eax
0x1800739e7  test    eax, eax
0x1800739e9  jns     loc_180073B01
0x1800739ef  mov     edx, 23Eh; void *
0x1800739f4  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800739fb  mov     r9d, ebx; char *
0x1800739fe  mov     rcx, [rbp+30h]; this
0x180073a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073a07  mov     eax, ebx
0x180073a09  jmp     loc_180073959
0x180073a0e  mov     rcx, [rbp+30h]; this
0x180073a12  mov     r9d, edi; char *
0x180073a15  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180073a1c  mov     edx, 20Eh; void *
0x180073a21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073a26  nop
0x180073a27  mov     rcx, [rbp+var_28+8]; void *
0x180073a2b  test    rcx, rcx
0x180073a2e  jz      loc_180073957
0x180073a34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180073a39  jmp     loc_180073957
0x180073a3e  mov     edx, 201h
0x180073a43  jmp     loc_180073944
0x180073a48  mov     edx, 203h
0x180073a4d  jmp     loc_180073944
0x180073a52  mov     edx, 20Dh
0x180073a57  jmp     short loc_180073A65
0x180073a59  mov     edx, 20Fh
0x180073a5e  jmp     short loc_180073A65
0x180073a60  mov     edx, 212h; void *
0x180073a65  mov     r9d, eax; char *
0x180073a68  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180073a6f  mov     rcx, [rbp+30h]; this
0x180073a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073a78  nop
0x180073a79  lea     rcx, [rbp+var_28]; this
0x180073a7d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180073a82  jmp     loc_180073957
0x180073a87  call    cs:__imp_ClearApplicationManifestLanguages
0x180073a8d  mov     edi, eax
0x180073a8f  test    eax, eax
0x180073a91  jns     loc_180073966
0x180073a97  mov     edx, 227h
0x180073a9c  jmp     loc_180073944
0x180073aa1  mov     r8, r14
0x180073aa4  mov     rax, [rax+28h]
0x180073aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073aad  mov     edi, eax
0x180073aaf  test    eax, eax
0x180073ab1  jns     loc_180073993
0x180073ab7  mov     edx, 22Ch
0x180073abc  jmp     loc_180073944
0x180073ac1  mov     edx, 235h
0x180073ac6  jmp     loc_180073944
0x180073acb  mov     rax, [rax+30h]
0x180073acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ad4  mov     edi, eax
0x180073ad6  test    eax, eax
0x180073ad8  jns     loc_1800739C0
0x180073ade  mov     edx, 239h
0x180073ae3  jmp     loc_180073944
0x180073ae8  mov     rax, [rax+30h]
0x180073aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073af1  mov     ebx, eax
0x180073af3  test    eax, eax
0x180073af5  jns     short loc_180073B01
0x180073af7  mov     edx, 242h
0x180073afc  jmp     loc_1800739F4
0x180073b01  xor     eax, eax
0x180073b03  jmp     loc_180073959
```
