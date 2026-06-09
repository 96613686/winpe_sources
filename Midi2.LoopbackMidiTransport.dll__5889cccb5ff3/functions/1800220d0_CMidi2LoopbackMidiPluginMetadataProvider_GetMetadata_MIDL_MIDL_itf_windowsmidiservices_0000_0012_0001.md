# CMidi2LoopbackMidiPluginMetadataProvider::GetMetadata(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)

- ea: `0x1800220d0`
- end: `0x180022285`
- name: `?GetMetadata@CMidi2LoopbackMidiPluginMetadataProvider@@UEAAJPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiPluginMetadataProvider *__hidden this, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004180`
- `0x18000a024`
- `0x18000b740`
- `0x18001b9ec`
- `0x180021d54`
- `0x180021f0c`
- `0x1800220d0`
- `0x18002228c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022231`

## string_xrefs

- `0x1800220fe`: `avcore\midi2\transport\loopbackmiditransport\midi2loopbackmidipluginmetadataprovider.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiPluginMetadataProvider::GetMetadata(
        CMidi2LoopbackMidiPluginMetadataProvider *this,
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
    v5 = 27;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2loopbackmidipluginmetadataprovider.cpp",
      (const char *)v4,
      (int)pv);
    return v4;
  }
  v7 = 0;
  *(GUID *)a2 = GUID_942bf02d_93c0_4ea8_b03e_d51156ca75e1;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, L"LOOP", a3);
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
    v5 = 33;
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
    v5 = 41;
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
    v5 = 47;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 7) = v15;
  result = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 16) = 11;
  return result;
}

```

## disassembly

```asm
0x1800220d0  mov     [rsp+arg_0], rbx
0x1800220d5  push    rdi
0x1800220d6  sub     rsp, 70h
0x1800220da  mov     rax, cs:__security_cookie
0x1800220e1  xor     rax, rsp
0x1800220e4  mov     [rsp+78h+var_18], rax
0x1800220e9  mov     rdi, rdx
0x1800220ec  test    rdx, rdx
0x1800220ef  jnz     short loc_180022114
0x1800220f1  mov     ebx, 80070057h
0x1800220f6  lea     edx, [rdi+1Bh]; void *
0x1800220f9  mov     rcx, [rsp+78h]; this
0x1800220fe  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\loopbackmidit"...
0x180022105  mov     r9d, ebx; char *
0x180022108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002210d  mov     eax, ebx
0x18002210f  jmp     loc_18002226A
0x180022114  movups  xmm0, xmmword ptr cs:_GUID_942bf02d_93c0_4ea8_b03e_d51156ca75e1.Data1
0x18002211b  lea     rcx, [rsp+78h+pv]; this
0x180022120  xor     ebx, ebx
0x180022122  movdqu  xmmword ptr [rdx], xmm0
0x180022126  lea     rdx, aLoop; "LOOP"
0x18002212d  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180022132  lea     rcx, [rsp+78h+var_50]
0x180022137  cmp     rcx, rax
0x18002213a  jz      short loc_180022146
0x18002213c  mov     rbx, [rax]
0x18002213f  mov     qword ptr [rax], 0
0x180022146  mov     rcx, [rsp+78h+pv]; pv
0x18002214b  test    rcx, rcx
0x18002214e  jz      short loc_180022156
0x180022150  call    cs:__imp_CoTaskMemFree
0x180022156  test    rbx, rbx
0x180022159  jnz     short loc_180022167
0x18002215b  mov     ebx, 8007000Eh
0x180022160  mov     edx, 21h ; '!'
0x180022165  jmp     short loc_1800220F9
0x180022167  lea     rdx, [rdi+18h]; unsigned int
0x18002216b  mov     [rdi+10h], rbx
0x18002216f  mov     ecx, 1F5h; this
0x180022174  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x180022179  lea     rdx, [rdi+20h]; unsigned int
0x18002217d  mov     ecx, 1F6h; this
0x180022182  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x180022187  lea     rcx, [rsp+78h+var_38]
0x18002218c  xor     ebx, ebx
0x18002218e  call    ?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)
0x180022193  cmp     qword ptr [rax+18h], 7
0x180022198  jbe     short loc_18002219D
0x18002219a  mov     rax, [rax]
0x18002219d  mov     rdx, rax; unsigned __int16 *
0x1800221a0  lea     rcx, [rsp+78h+pv]; this
0x1800221a5  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800221aa  lea     rcx, [rsp+78h+var_48]
0x1800221af  cmp     rcx, rax
0x1800221b2  jz      short loc_1800221BE
0x1800221b4  mov     rbx, [rax]
0x1800221b7  mov     qword ptr [rax], 0
0x1800221be  mov     rcx, [rsp+78h+pv]; pv
0x1800221c3  test    rcx, rcx
0x1800221c6  jz      short loc_1800221CE
0x1800221c8  call    cs:__imp_CoTaskMemFree
0x1800221ce  lea     rcx, [rsp+78h+var_38]; void *
0x1800221d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800221d8  test    rbx, rbx
0x1800221db  jnz     short loc_1800221EC
0x1800221dd  mov     ebx, 8007000Eh
0x1800221e2  mov     edx, 29h ; ')'
0x1800221e7  jmp     loc_1800220F9
0x1800221ec  mov     [rdi+28h], rbx
0x1800221f0  lea     rcx, [rsp+78h+var_38]
0x1800221f5  xor     ebx, ebx
0x1800221f7  call    ?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersion(void)
0x1800221fc  cmp     qword ptr [rax+18h], 7
0x180022201  jbe     short loc_180022206
0x180022203  mov     rax, [rax]
0x180022206  mov     rdx, rax; unsigned __int16 *
0x180022209  lea     rcx, [rsp+78h+pv]; this
0x18002220e  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180022213  lea     rcx, [rsp+78h+var_40]
0x180022218  cmp     rcx, rax
0x18002221b  jz      short loc_180022227
0x18002221d  mov     rbx, [rax]
0x180022220  mov     qword ptr [rax], 0
0x180022227  mov     rcx, [rsp+78h+pv]; pv
0x18002222c  test    rcx, rcx
0x18002222f  jz      short loc_180022237
0x180022231  call    cs:__imp_CoTaskMemFree
0x180022237  lea     rcx, [rsp+78h+var_38]; void *
0x18002223c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022241  test    rbx, rbx
0x180022244  jnz     short loc_180022255
0x180022246  mov     ebx, 8007000Eh
0x18002224b  mov     edx, 2Fh ; '/'
0x180022250  jmp     loc_1800220F9
0x180022255  mov     [rdi+38h], rbx
0x180022259  xor     eax, eax
0x18002225b  mov     qword ptr [rdi+30h], 0
0x180022263  mov     dword ptr [rdi+40h], 0Bh
0x18002226a  mov     rcx, [rsp+78h+var_18]
0x18002226f  xor     rcx, rsp; StackCookie
0x180022272  call    __security_check_cookie
0x180022277  mov     rbx, [rsp+78h+arg_0]
0x18002227f  add     rsp, 70h
0x180022283  pop     rdi
0x180022284  retn
```
