# ConstructPluginsRule(ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x18001c8b4`
- end: `0x18001cc4d`
- name: `?ConstructPluginsRule@@YAJKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d180`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000a7f8`
- `0x18000ac6c`
- `0x18000bbe8`
- `0x18000c9e0`
- `0x18000cab8`
- `0x18000e9d4`
- `0x1800119bc`
- `0x180011c8c`
- `0x180011ea8`
- `0x18001aa2c`
- `0x18001b734`
- `0x18001c3f0`
- `0x18001c510`
- `0x18001c67c`
- `0x18001c878`
- `0x18001c8b4`
- `0x18001cc54`
- `0x1800219a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001cb6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001cb6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c917`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c917`

## string_xrefs

- `0x18001c910`: `NaturalAuth.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConstructPluginsRule(unsigned int a1, __int64 a2)
{
  __int64 v2; // r13
  __int64 CorrelationVector; // rbx
  __int64 v4; // rax
  unsigned int DeviceUnlockPluginsPolicy; // eax
  signed int v6; // ebx
  signed int v7; // r14d
  PVOID *v8; // r10
  int v9; // r12d
  char *v10; // rdi
  char *v11; // r15
  HINSTANCE v12; // r13
  __int64 v13; // rax
  __int64 v14; // r10
  const char *v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  _QWORD *v19; // rdx
  UINT v20; // edx
  __int64 v21; // rbx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  char *v26; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h]
  unsigned int v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  HINSTANCE hInstance; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  WCHAR *v32; // [rsp+70h] [rbp-90h] BYREF
  char v33[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h]
  _BYTE v35[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v36[1040]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[32]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v2 = a2;
  v31 = a2;
  v28 = a1;
  v34 = a2;
  memset_0(v36, 0, 0x408u);
  v29 = 0;
  v25 = 0;
  hInstance = GetModuleHandleW(L"NaturalAuth.dll");
  std::vector<_bstr_t>::vector<_bstr_t>(&v26);
  v32 = Buffer;
  CorrelationVector = NaturalAuthTraceLogging::GetCorrelationVector(Buffer);
  v4 = std::string::string(v35);
  DeviceUnlockPluginsPolicy = NaturalAuthHelper::_anonymous_namespace_::GetDeviceUnlockPluginsPolicy(
                                v4,
                                CorrelationVector,
                                (__int64)&v26);
  v6 = DeviceUnlockPluginsPolicy;
  if ( DeviceUnlockPluginsPolicy )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_0b234503d699372e033b81b870c30083_Traceguids,
        DeviceUnlockPluginsPolicy);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v26 )
    {
      std::_Destroy_range<std::allocator<std::string>>(v26, v27);
      std::_Deallocate<16>(
        v26,
        (struct std::nothrow_t *)((*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL));
      v26 = 0;
      v27 = 0;
    }
    goto LABEL_35;
  }
  v7 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_0b234503d699372e033b81b870c30083_Traceguids,
      (__int64)(v27 - (_QWORD)v26) >> 5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  v10 = v26;
  v11 = (char *)v27;
  if ( v26 != (char *)v27 )
  {
    v12 = hInstance;
    while ( 1 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      {
        v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
        WPP_SF_ds(*(_QWORD *)(v14 + 16), 14, (unsigned int)WPP_0b234503d699372e033b81b870c30083_Traceguids, v9, v13);
      }
      v15 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
      v16 = NAPRuleRegister(
              v15,
              &stru_18005F490,
              v28,
              (struct NA_XML_PARSE_ERROR_DETAILS *)v36,
              &v29,
              (enum NA_SIGNAL_TYPE_INFO *)&v25);
      if ( v16 >= 0 )
      {
        std::map<__int64,std::wstring>::_Try_emplace<__int64 const &,>(v17, v33, &v29);
        v18 = std::_WChar_traits<unsigned short>::length(&Class);
        std::wstring::_Assign<unsigned short>(*v19 + 40LL, &Class, v18);
        if ( v12 )
        {
          memset_0(Buffer, 0, sizeof(Buffer));
          if ( v25 == 1 )
          {
            v20 = 301;
          }
          else
          {
            v20 = 300;
            if ( v25 == 2 )
              v20 = 302;
          }
          LoadStringW(v12, v20, Buffer, 32);
          v21 = std::wstring::wstring((__int64)v35, (__int64)Buffer);
          v23 = (_QWORD *)std::map<__int64,std::wstring>::_Try_emplace<__int64 const &,>(v22, &v32, &v29);
          std::wstring::operator=(*v23 + 40LL, v21);
          std::wstring::_Tidy_deallocate(v35);
        }
      }
      else
      {
        v7 = v16;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_0b234503d699372e033b81b870c30083_Traceguids,
          (unsigned int)v16);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_28:
      ++v9;
      v10 += 32;
      if ( v10 == v11 )
      {
        v11 = (char *)v27;
        v10 = v26;
        v2 = v31;
        break;
      }
    }
  }
  if ( qword_18005F988 )
    v7 = 0;
  if ( v10 )
  {
    std::_Destroy_range<std::allocator<std::string>>(v10, v11);
    std::_Deallocate<16>(v26, (struct std::nothrow_t *)((*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFE0uLL));
    v26 = 0;
    v27 = 0;
  }
  v6 = v7;
LABEL_35:
  std::string::_Tidy_deallocate(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c8b4  mov     [rsp-8+arg_10], rbx
0x18001c8b9  push    rbp
0x18001c8ba  push    rsi
0x18001c8bb  push    rdi
0x18001c8bc  push    r12
0x18001c8be  push    r13
0x18001c8c0  push    r14
0x18001c8c2  push    r15
0x18001c8c4  lea     rbp, [rsp-420h]
0x18001c8cc  sub     rsp, 520h
0x18001c8d3  mov     rax, cs:__security_cookie
0x18001c8da  xor     rax, rsp
0x18001c8dd  mov     [rbp+450h+var_40], rax
0x18001c8e4  mov     r13, rdx
0x18001c8e7  mov     [rsp+550h+var_4E8], rdx
0x18001c8ec  mov     [rsp+550h+var_500], ecx
0x18001c8f0  mov     [rbp+450h+var_4C0], rdx
0x18001c8f4  xor     edx, edx; Val
0x18001c8f6  mov     r8d, 408h; Size
0x18001c8fc  lea     rcx, [rbp+450h+var_490]; void *
0x18001c900  call    memset_0
0x18001c905  xor     edi, edi
0x18001c907  mov     [rsp+550h+var_4F8], rdi
0x18001c90c  mov     [rsp+550h+var_520], edi
0x18001c910  lea     rcx, aNaturalauthDll_0; "NaturalAuth.dll"
0x18001c917  call    cs:__imp_GetModuleHandleW
0x18001c91d  mov     [rsp+550h+hInstance], rax
0x18001c922  lea     rcx, [rsp+550h+var_518]
0x18001c927  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18001c92c  nop
0x18001c92d  lea     rax, [rbp+450h+Buffer]
0x18001c934  mov     [rsp+550h+var_4E0], rax
0x18001c939  lea     rcx, [rbp+450h+Buffer]
0x18001c940  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x18001c945  mov     rbx, rax
0x18001c948  mov     rdx, r13
0x18001c94b  lea     rcx, [rbp+450h+var_4B8]
0x18001c94f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18001c954  nop
0x18001c955  lea     r8, [rsp+550h+var_518]
0x18001c95a  mov     rdx, rbx
0x18001c95d  mov     rcx, rax
0x18001c960  call    NaturalAuthHelper___anonymous_namespace___GetDeviceUnlockPluginsPolicy
0x18001c965  mov     ebx, eax
0x18001c967  test    eax, eax
0x18001c969  jz      short loc_18001C9E8
0x18001c96b  lea     rsi, WPP_GLOBAL_Control
0x18001c972  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c979  cmp     rcx, rsi
0x18001c97c  jz      short loc_18001C99A
0x18001c97e  test    byte ptr [rcx+1Ch], 1
0x18001c982  jz      short loc_18001C99A
0x18001c984  lea     edx, [rdi+0Ch]
0x18001c987  mov     r9d, eax
0x18001c98a  lea     r8, WPP_0b234503d699372e033b81b870c30083_Traceguids
0x18001c991  mov     rcx, [rcx+10h]
0x18001c995  call    WPP_SF_d
0x18001c99a  test    ebx, ebx
0x18001c99c  jle     short loc_18001C9A7
0x18001c99e  movzx   ebx, bx
0x18001c9a1  or      ebx, 80070000h
0x18001c9a7  mov     rcx, [rsp+550h+var_518]
0x18001c9ac  test    rcx, rcx
0x18001c9af  jz      loc_18001CC19
0x18001c9b5  mov     rdx, qword ptr [rsp+550h+var_510]
0x18001c9ba  call    ??$_Destroy_range@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::string>>(std::string *,std::string * const,std::allocator<std::string> &)
0x18001c9bf  mov     rcx, [rsp+550h+var_518]
0x18001c9c4  mov     rdx, qword ptr [rsp+550h+var_510+8]
0x18001c9c9  sub     rdx, rcx
0x18001c9cc  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001c9d0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c9d5  mov     [rsp+550h+var_518], rdi
0x18001c9da  xorps   xmm0, xmm0
0x18001c9dd  movdqu  [rsp+550h+var_510], xmm0
0x18001c9e3  jmp     loc_18001CC19
0x18001c9e8  mov     r14d, edi
0x18001c9eb  lea     rsi, WPP_GLOBAL_Control
0x18001c9f2  mov     r10, cs:WPP_GLOBAL_Control
0x18001c9f9  cmp     r10, rsi
0x18001c9fc  jz      short loc_18001CA2F
0x18001c9fe  test    byte ptr [r10+1Ch], 4
0x18001ca03  jz      short loc_18001CA2F
0x18001ca05  mov     r9, qword ptr [rsp+550h+var_510]
0x18001ca0a  sub     r9, [rsp+550h+var_518]
0x18001ca0f  sar     r9, 5
0x18001ca13  mov     edx, 0Dh
0x18001ca18  lea     r8, WPP_0b234503d699372e033b81b870c30083_Traceguids
0x18001ca1f  mov     rcx, [r10+10h]
0x18001ca23  call    WPP_SF_d
0x18001ca28  mov     r10, cs:WPP_GLOBAL_Control
0x18001ca2f  mov     r12d, edi
0x18001ca32  mov     rdi, [rsp+550h+var_518]
0x18001ca37  mov     r15, qword ptr [rsp+550h+var_510]
0x18001ca3c  cmp     rdi, r15
0x18001ca3f  jz      loc_18001CBD1
0x18001ca45  mov     r13, [rsp+550h+hInstance]
0x18001ca4a  cmp     r10, rsi
0x18001ca4d  jz      short loc_18001CA7B
0x18001ca4f  test    byte ptr [r10+1Ch], 4
0x18001ca54  jz      short loc_18001CA7B
0x18001ca56  mov     rcx, rdi
0x18001ca59  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001ca5e  mov     edx, 0Eh
0x18001ca63  mov     [rsp+550h+var_530], rax
0x18001ca68  mov     r9d, r12d
0x18001ca6b  lea     r8, WPP_0b234503d699372e033b81b870c30083_Traceguids
0x18001ca72  mov     rcx, [r10+10h]
0x18001ca76  call    WPP_SF_ds
0x18001ca7b  mov     rcx, rdi
0x18001ca7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001ca83  lea     rcx, [rsp+550h+var_520]
0x18001ca88  mov     [rsp+550h+var_528], rcx; enum NA_SIGNAL_TYPE_INFO *
0x18001ca8d  lea     rcx, [rsp+550h+var_4F8]
0x18001ca92  mov     [rsp+550h+var_530], rcx; __int64 *
0x18001ca97  lea     r9, [rbp+450h+var_490]; struct NA_XML_PARSE_ERROR_DETAILS *
0x18001ca9b  mov     r8d, [rsp+550h+var_500]; unsigned int
0x18001caa0  lea     rdx, stru_18005F490; struct _WNF_STATE_NAME *
0x18001caa7  mov     rcx, rax; char *
0x18001caaa  call    ?NAPRuleRegister@@YAJPEBDPEAU_WNF_STATE_NAME@@KPEAUNA_XML_PARSE_ERROR_DETAILS@@PEA_JPEAW4NA_SIGNAL_TYPE_INFO@@@Z; NAPRuleRegister(char const *,_WNF_STATE_NAME *,ulong,NA_XML_PARSE_ERROR_DETAILS *,__int64 *,NA_SIGNAL_TYPE_INFO *)
0x18001caaf  test    eax, eax
0x18001cab1  jns     short loc_18001CAEE
0x18001cab3  mov     r14d, eax
0x18001cab6  mov     r10, cs:WPP_GLOBAL_Control
0x18001cabd  cmp     r10, rsi
0x18001cac0  jz      loc_18001CBB2
0x18001cac6  test    byte ptr [r10+1Ch], 1
0x18001cacb  jz      loc_18001CBB2
0x18001cad1  mov     edx, 0Fh
0x18001cad6  mov     r9d, eax
0x18001cad9  lea     r8, WPP_0b234503d699372e033b81b870c30083_Traceguids
0x18001cae0  mov     rcx, [r10+10h]
0x18001cae4  call    WPP_SF_d
0x18001cae9  jmp     loc_18001CBAB
0x18001caee  lea     r8, [rsp+550h+var_4F8]
0x18001caf3  lea     rdx, [rbp+450h+var_4D0]
0x18001caf7  call    ??$_Try_emplace@AEB_J$$V@?$map@_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,std::wstring>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18001cafc  mov     rdx, rax
0x18001caff  lea     rcx, Class
0x18001cb06  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001cb0b  mov     r8, rax
0x18001cb0e  mov     rcx, [rdx]
0x18001cb11  add     rcx, 28h ; '('
0x18001cb15  lea     rdx, Class
0x18001cb1c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001cb21  test    r13, r13
0x18001cb24  jz      loc_18001CBAB
0x18001cb2a  xor     edx, edx; Val
0x18001cb2c  lea     r8d, [rdx+40h]; Size
0x18001cb30  lea     rcx, [rbp+450h+Buffer]; void *
0x18001cb37  call    memset_0
0x18001cb3c  cmp     [rsp+550h+var_520], 1
0x18001cb41  jnz     short loc_18001CB4A
0x18001cb43  mov     edx, 12Dh
0x18001cb48  jmp     short loc_18001CB5A
0x18001cb4a  mov     edx, 12Ch
0x18001cb4f  lea     eax, [rdx+2]
0x18001cb52  cmp     [rsp+550h+var_520], 2
0x18001cb57  cmovz   edx, eax; uID
0x18001cb5a  mov     r9d, 20h ; ' '; cchBufferMax
0x18001cb60  lea     r8, [rbp+450h+Buffer]; lpBuffer
0x18001cb67  mov     rcx, r13; hInstance
0x18001cb6a  call    cs:__imp_LoadStringW
0x18001cb70  lea     rdx, [rbp+450h+Buffer]
0x18001cb77  lea     rcx, [rbp+450h+var_4B8]
0x18001cb7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001cb80  mov     rbx, rax
0x18001cb83  lea     r8, [rsp+550h+var_4F8]
0x18001cb88  lea     rdx, [rsp+550h+var_4E0]
0x18001cb8d  call    ??$_Try_emplace@AEB_J$$V@?$map@_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,std::wstring>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18001cb92  mov     rcx, [rax]
0x18001cb95  add     rcx, 28h ; '('
0x18001cb99  mov     rdx, rbx
0x18001cb9c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001cba1  nop
0x18001cba2  lea     rcx, [rbp+450h+var_4B8]
0x18001cba6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cbab  mov     r10, cs:WPP_GLOBAL_Control
0x18001cbb2  inc     r12d
0x18001cbb5  add     rdi, 20h ; ' '
0x18001cbb9  cmp     rdi, r15
0x18001cbbc  jnz     loc_18001CA4A
0x18001cbc2  mov     r15, qword ptr [rsp+550h+var_510]
0x18001cbc7  mov     rdi, [rsp+550h+var_518]
0x18001cbcc  mov     r13, [rsp+550h+var_4E8]
0x18001cbd1  xor     eax, eax
0x18001cbd3  cmp     cs:qword_18005F988, rax
0x18001cbda  cmova   r14d, eax
0x18001cbde  test    rdi, rdi
0x18001cbe1  jz      short loc_18001CC16
0x18001cbe3  mov     rdx, r15
0x18001cbe6  mov     rcx, rdi
0x18001cbe9  call    ??$_Destroy_range@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::string>>(std::string *,std::string * const,std::allocator<std::string> &)
0x18001cbee  mov     rcx, [rsp+550h+var_518]
0x18001cbf3  mov     rdx, qword ptr [rsp+550h+var_510+8]
0x18001cbf8  sub     rdx, rcx
0x18001cbfb  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001cbff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001cc04  mov     [rsp+550h+var_518], 0
0x18001cc0d  xorps   xmm0, xmm0
0x18001cc10  movdqu  [rsp+550h+var_510], xmm0
0x18001cc16  mov     ebx, r14d
0x18001cc19  mov     rcx, r13
0x18001cc1c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001cc21  mov     eax, ebx
0x18001cc23  mov     rcx, [rbp+450h+var_40]
0x18001cc2a  xor     rcx, rsp; StackCookie
0x18001cc2d  call    __security_check_cookie
0x18001cc32  mov     rbx, [rsp+550h+arg_10]
0x18001cc3a  add     rsp, 520h
0x18001cc41  pop     r15
0x18001cc43  pop     r14
0x18001cc45  pop     r13
0x18001cc47  pop     r12
0x18001cc49  pop     rdi
0x18001cc4a  pop     rsi
0x18001cc4b  pop     rbp
0x18001cc4c  retn
```
