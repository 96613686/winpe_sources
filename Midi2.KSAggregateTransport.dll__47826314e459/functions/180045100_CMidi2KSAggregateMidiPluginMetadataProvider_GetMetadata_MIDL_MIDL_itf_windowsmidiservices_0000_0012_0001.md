# CMidi2KSAggregateMidiPluginMetadataProvider::GetMetadata(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)

- ea: `0x180045100`
- end: `0x1800452b5`
- name: `?GetMetadata@CMidi2KSAggregateMidiPluginMetadataProvider@@UEAAJPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiPluginMetadataProvider *__hidden this, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005020`
- `0x18000b394`
- `0x18000d430`
- `0x18001f6f8`
- `0x180044d8c`
- `0x180044f44`
- `0x180045100`
- `0x1800452bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800451f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045261`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800451f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045261`

## string_xrefs

- `0x18004512e`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidipluginmetadataprovider.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2KSAggregateMidiPluginMetadataProvider::GetMetadata(
        CMidi2KSAggregateMidiPluginMetadataProvider *this,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *a2,
        unsigned __int64 a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // rbx
  char *cotaskmem_string_nothrow; // rax
  unsigned __int16 **v9; // r8
  unsigned __int16 **v10; // r8
  __int64 v11; // rbx
  __int64 CurrentModuleVersionCompanyName; // rax
  unsigned __int64 v13; // r8
  char *v14; // rax
  __int64 v15; // rbx
  __int64 CurrentModuleVersion; // rax
  unsigned __int64 v17; // r8
  char *v18; // rax
  LPVOID pv; // [rsp+20h] [rbp-58h] BYREF
  char v20; // [rsp+28h] [rbp-50h] BYREF
  char v21; // [rsp+30h] [rbp-48h] BYREF
  char v22; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 26;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidipluginmetadataprovider.cpp",
      (const char *)v4,
      (int)pv);
    return v4;
  }
  v7 = 0;
  *(GUID *)a2 = GUID_0f273b18_e372_4d95_87ac_c31c3d22e937;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, L"KSA", a3);
  if ( &v20 != cotaskmem_string_nothrow )
  {
    v7 = *(_QWORD *)cotaskmem_string_nothrow;
    *(_QWORD *)cotaskmem_string_nothrow = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 41;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 2) = v7;
  WindowsMidiServicesInternal::ResourceCopyToCoString((WindowsMidiServicesInternal *)0x1F5, (_DWORD)a2 + 24, v9);
  WindowsMidiServicesInternal::ResourceCopyToCoString((WindowsMidiServicesInternal *)0x1F6, (_DWORD)a2 + 32, v10);
  v11 = 0;
  CurrentModuleVersionCompanyName = WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(v23);
  if ( *(_QWORD *)(CurrentModuleVersionCompanyName + 24) > 7u )
    CurrentModuleVersionCompanyName = *(_QWORD *)CurrentModuleVersionCompanyName;
  v14 = (char *)wil::make_cotaskmem_string_nothrow(
                  (wil *)&pv,
                  (const unsigned __int16 *)CurrentModuleVersionCompanyName,
                  v13);
  if ( &v21 != v14 )
  {
    v11 = *(_QWORD *)v14;
    *(_QWORD *)v14 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::~wstring(v23);
  if ( !v11 )
  {
    v4 = -2147024882;
    v5 = 49;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 5) = v11;
  v15 = 0;
  CurrentModuleVersion = WindowsMidiServicesInternal::GetCurrentModuleVersion(v23);
  if ( *(_QWORD *)(CurrentModuleVersion + 24) > 7u )
    CurrentModuleVersion = *(_QWORD *)CurrentModuleVersion;
  v18 = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, (const unsigned __int16 *)CurrentModuleVersion, v17);
  if ( &v22 != v18 )
  {
    v15 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::~wstring(v23);
  if ( !v15 )
  {
    v4 = -2147024882;
    v5 = 54;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 7) = v15;
  result = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180045100  mov     [rsp+arg_0], rbx
0x180045105  push    rdi
0x180045106  sub     rsp, 70h
0x18004510a  mov     rax, cs:__security_cookie
0x180045111  xor     rax, rsp
0x180045114  mov     [rsp+78h+var_18], rax
0x180045119  mov     rdi, rdx
0x18004511c  test    rdx, rdx
0x18004511f  jnz     short loc_180045144
0x180045121  mov     ebx, 80070057h
0x180045126  lea     edx, [rdi+1Ah]; void *
0x180045129  mov     rcx, [rsp+78h]; this
0x18004512e  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180045135  mov     r9d, ebx; char *
0x180045138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004513d  mov     eax, ebx
0x18004513f  jmp     loc_18004529A
0x180045144  movups  xmm0, xmmword ptr cs:_GUID_0f273b18_e372_4d95_87ac_c31c3d22e937.Data1
0x18004514b  lea     rcx, [rsp+78h+pv]; this
0x180045150  xor     ebx, ebx
0x180045152  movdqu  xmmword ptr [rdx], xmm0
0x180045156  lea     rdx, aKsa; "KSA"
0x18004515d  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180045162  lea     rcx, [rsp+78h+var_50]
0x180045167  cmp     rcx, rax
0x18004516a  jz      short loc_180045176
0x18004516c  mov     rbx, [rax]
0x18004516f  mov     qword ptr [rax], 0
0x180045176  mov     rcx, [rsp+78h+pv]; pv
0x18004517b  test    rcx, rcx
0x18004517e  jz      short loc_180045186
0x180045180  call    cs:__imp_CoTaskMemFree
0x180045186  test    rbx, rbx
0x180045189  jnz     short loc_180045197
0x18004518b  mov     ebx, 8007000Eh
0x180045190  mov     edx, 29h ; ')'
0x180045195  jmp     short loc_180045129
0x180045197  lea     rdx, [rdi+18h]; unsigned int
0x18004519b  mov     [rdi+10h], rbx
0x18004519f  mov     ecx, 1F5h; this
0x1800451a4  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x1800451a9  lea     rdx, [rdi+20h]; unsigned int
0x1800451ad  mov     ecx, 1F6h; this
0x1800451b2  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x1800451b7  lea     rcx, [rsp+78h+var_38]
0x1800451bc  xor     ebx, ebx
0x1800451be  call    ?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)
0x1800451c3  cmp     qword ptr [rax+18h], 7
0x1800451c8  jbe     short loc_1800451CD
0x1800451ca  mov     rax, [rax]
0x1800451cd  mov     rdx, rax; unsigned __int16 *
0x1800451d0  lea     rcx, [rsp+78h+pv]; this
0x1800451d5  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800451da  lea     rcx, [rsp+78h+var_48]
0x1800451df  cmp     rcx, rax
0x1800451e2  jz      short loc_1800451EE
0x1800451e4  mov     rbx, [rax]
0x1800451e7  mov     qword ptr [rax], 0
0x1800451ee  mov     rcx, [rsp+78h+pv]; pv
0x1800451f3  test    rcx, rcx
0x1800451f6  jz      short loc_1800451FE
0x1800451f8  call    cs:__imp_CoTaskMemFree
0x1800451fe  lea     rcx, [rsp+78h+var_38]; void *
0x180045203  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045208  test    rbx, rbx
0x18004520b  jnz     short loc_18004521C
0x18004520d  mov     ebx, 8007000Eh
0x180045212  mov     edx, 31h ; '1'
0x180045217  jmp     loc_180045129
0x18004521c  mov     [rdi+28h], rbx
0x180045220  lea     rcx, [rsp+78h+var_38]
0x180045225  xor     ebx, ebx
0x180045227  call    ?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersion(void)
0x18004522c  cmp     qword ptr [rax+18h], 7
0x180045231  jbe     short loc_180045236
0x180045233  mov     rax, [rax]
0x180045236  mov     rdx, rax; unsigned __int16 *
0x180045239  lea     rcx, [rsp+78h+pv]; this
0x18004523e  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180045243  lea     rcx, [rsp+78h+var_40]
0x180045248  cmp     rcx, rax
0x18004524b  jz      short loc_180045257
0x18004524d  mov     rbx, [rax]
0x180045250  mov     qword ptr [rax], 0
0x180045257  mov     rcx, [rsp+78h+pv]; pv
0x18004525c  test    rcx, rcx
0x18004525f  jz      short loc_180045267
0x180045261  call    cs:__imp_CoTaskMemFree
0x180045267  lea     rcx, [rsp+78h+var_38]; void *
0x18004526c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045271  test    rbx, rbx
0x180045274  jnz     short loc_180045285
0x180045276  mov     ebx, 8007000Eh
0x18004527b  mov     edx, 36h ; '6'
0x180045280  jmp     loc_180045129
0x180045285  mov     [rdi+38h], rbx
0x180045289  xor     eax, eax
0x18004528b  mov     qword ptr [rdi+30h], 0
0x180045293  mov     dword ptr [rdi+40h], 0
0x18004529a  mov     rcx, [rsp+78h+var_18]
0x18004529f  xor     rcx, rsp; StackCookie
0x1800452a2  call    __security_check_cookie
0x1800452a7  mov     rbx, [rsp+78h+arg_0]
0x1800452af  add     rsp, 70h
0x1800452b3  pop     rdi
0x1800452b4  retn
```
