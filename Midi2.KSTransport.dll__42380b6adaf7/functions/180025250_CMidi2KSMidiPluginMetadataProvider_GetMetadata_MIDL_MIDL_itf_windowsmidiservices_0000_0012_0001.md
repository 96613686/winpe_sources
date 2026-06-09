# CMidi2KSMidiPluginMetadataProvider::GetMetadata(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)

- ea: `0x180025250`
- end: `0x180025405`
- name: `?GetMetadata@CMidi2KSMidiPluginMetadataProvider@@UEAAJPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CMidi2KSMidiPluginMetadataProvider *__hidden this, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004410`
- `0x18000a814`
- `0x18000c250`
- `0x180024cf4`
- `0x180024ee0`
- `0x180025098`
- `0x180025250`
- `0x18002540c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253b1`

## string_xrefs

- `0x18002527e`: `avcore\midi2\transport\kstransport\midi2.ksmidipluginmetadataprovider.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2KSMidiPluginMetadataProvider::GetMetadata(
        CMidi2KSMidiPluginMetadataProvider *this,
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
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidipluginmetadataprovider.cpp",
      (const char *)v4,
      (int)pv);
    return v4;
  }
  v7 = 0;
  *(GUID *)a2 = GUID_26fa740d_469c_4d33_beb1_3885de7d6df1;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, L"KS", a3);
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
    v5 = 36;
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
    v5 = 44;
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
    v5 = 49;
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
0x180025250  mov     [rsp+arg_0], rbx
0x180025255  push    rdi
0x180025256  sub     rsp, 70h
0x18002525a  mov     rax, cs:__security_cookie
0x180025261  xor     rax, rsp
0x180025264  mov     [rsp+78h+var_18], rax
0x180025269  mov     rdi, rdx
0x18002526c  test    rdx, rdx
0x18002526f  jnz     short loc_180025294
0x180025271  mov     ebx, 80070057h
0x180025276  lea     edx, [rdi+1Ah]; void *
0x180025279  mov     rcx, [rsp+78h]; this
0x18002527e  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\kstransport\\"...
0x180025285  mov     r9d, ebx; char *
0x180025288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002528d  mov     eax, ebx
0x18002528f  jmp     loc_1800253EA
0x180025294  movups  xmm0, xmmword ptr cs:_GUID_26fa740d_469c_4d33_beb1_3885de7d6df1.Data1
0x18002529b  lea     rcx, [rsp+78h+pv]; this
0x1800252a0  xor     ebx, ebx
0x1800252a2  movdqu  xmmword ptr [rdx], xmm0
0x1800252a6  lea     rdx, aKs_0; "KS"
0x1800252ad  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800252b2  lea     rcx, [rsp+78h+var_50]
0x1800252b7  cmp     rcx, rax
0x1800252ba  jz      short loc_1800252C6
0x1800252bc  mov     rbx, [rax]
0x1800252bf  mov     qword ptr [rax], 0
0x1800252c6  mov     rcx, [rsp+78h+pv]; pv
0x1800252cb  test    rcx, rcx
0x1800252ce  jz      short loc_1800252D6
0x1800252d0  call    cs:__imp_CoTaskMemFree
0x1800252d6  test    rbx, rbx
0x1800252d9  jnz     short loc_1800252E7
0x1800252db  mov     ebx, 8007000Eh
0x1800252e0  mov     edx, 24h ; '$'
0x1800252e5  jmp     short loc_180025279
0x1800252e7  lea     rdx, [rdi+18h]; unsigned int
0x1800252eb  mov     [rdi+10h], rbx
0x1800252ef  mov     ecx, 1F5h; this
0x1800252f4  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x1800252f9  lea     rdx, [rdi+20h]; unsigned int
0x1800252fd  mov     ecx, 1F6h; this
0x180025302  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x180025307  lea     rcx, [rsp+78h+var_38]
0x18002530c  xor     ebx, ebx
0x18002530e  call    ?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)
0x180025313  cmp     qword ptr [rax+18h], 7
0x180025318  jbe     short loc_18002531D
0x18002531a  mov     rax, [rax]
0x18002531d  mov     rdx, rax; unsigned __int16 *
0x180025320  lea     rcx, [rsp+78h+pv]; this
0x180025325  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18002532a  lea     rcx, [rsp+78h+var_48]
0x18002532f  cmp     rcx, rax
0x180025332  jz      short loc_18002533E
0x180025334  mov     rbx, [rax]
0x180025337  mov     qword ptr [rax], 0
0x18002533e  mov     rcx, [rsp+78h+pv]; pv
0x180025343  test    rcx, rcx
0x180025346  jz      short loc_18002534E
0x180025348  call    cs:__imp_CoTaskMemFree
0x18002534e  lea     rcx, [rsp+78h+var_38]; void *
0x180025353  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025358  test    rbx, rbx
0x18002535b  jnz     short loc_18002536C
0x18002535d  mov     ebx, 8007000Eh
0x180025362  mov     edx, 2Ch ; ','
0x180025367  jmp     loc_180025279
0x18002536c  mov     [rdi+28h], rbx
0x180025370  lea     rcx, [rsp+78h+var_38]
0x180025375  xor     ebx, ebx
0x180025377  call    ?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersion(void)
0x18002537c  cmp     qword ptr [rax+18h], 7
0x180025381  jbe     short loc_180025386
0x180025383  mov     rax, [rax]
0x180025386  mov     rdx, rax; unsigned __int16 *
0x180025389  lea     rcx, [rsp+78h+pv]; this
0x18002538e  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180025393  lea     rcx, [rsp+78h+var_40]
0x180025398  cmp     rcx, rax
0x18002539b  jz      short loc_1800253A7
0x18002539d  mov     rbx, [rax]
0x1800253a0  mov     qword ptr [rax], 0
0x1800253a7  mov     rcx, [rsp+78h+pv]; pv
0x1800253ac  test    rcx, rcx
0x1800253af  jz      short loc_1800253B7
0x1800253b1  call    cs:__imp_CoTaskMemFree
0x1800253b7  lea     rcx, [rsp+78h+var_38]; void *
0x1800253bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800253c1  test    rbx, rbx
0x1800253c4  jnz     short loc_1800253D5
0x1800253c6  mov     ebx, 8007000Eh
0x1800253cb  mov     edx, 31h ; '1'
0x1800253d0  jmp     loc_180025279
0x1800253d5  mov     [rdi+38h], rbx
0x1800253d9  xor     eax, eax
0x1800253db  mov     qword ptr [rdi+30h], 0
0x1800253e3  mov     dword ptr [rdi+40h], 0
0x1800253ea  mov     rcx, [rsp+78h+var_18]
0x1800253ef  xor     rcx, rsp; StackCookie
0x1800253f2  call    __security_check_cookie
0x1800253f7  mov     rbx, [rsp+78h+arg_0]
0x1800253ff  add     rsp, 70h
0x180025403  pop     rdi
0x180025404  retn
```
