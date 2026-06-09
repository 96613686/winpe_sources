# CodeIntegrity::Management::GetDiskPolicies(void)

- ea: `0x18000ad4c`
- end: `0x18000b12c`
- name: `?GetDiskPolicies@Management@CodeIntegrity@@YA?AV?$unique_ptr@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@@2@@std@@XZ`
- size: `992`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014ee0`

## callees

- `0x180002a90`
- `0x180002ab4`
- `0x180002edc`
- `0x180003888`
- `0x180009c40`
- `0x18000a2c0`
- `0x18000a308`
- `0x18000a324`
- `0x18000ad20`
- `0x18000ad4c`
- `0x18000b540`
- `0x18000d450`
- `0x18000d470`
- `0x180020f78`
- `0x180022a30`
- `0x180022f2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b023`

## string_xrefs

- `0x18000b0da`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b0ef`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b104`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b119`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::Management::GetDiskPolicies(_QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rbx
  _QWORD *v3; // rax
  int ExtensionRegistry; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  HLOCAL *v8; // r14
  int AllPolicyFiles; // eax
  HLOCAL v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  void *v13; // rdi
  char v14; // r12
  _QWORD *v15; // r13
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  unsigned __int64 i; // rbx
  int v23; // eax
  char v24; // r12
  unsigned __int64 v25; // rdx
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  unsigned int v29; // ebx
  int v30; // edi
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // [rsp+20h] [rbp-118h]
  int v35; // [rsp+20h] [rbp-118h]
  int v36; // [rsp+20h] [rbp-118h]
  unsigned int v37; // [rsp+40h] [rbp-F8h]
  unsigned __int64 v39; // [rsp+48h] [rbp-F0h] BYREF
  HLOCAL v40[2]; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v41; // [rsp+60h] [rbp-D8h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-D0h] BYREF
  unsigned __int64 v43; // [rsp+70h] [rbp-C8h]
  __int64 v44; // [rsp+78h] [rbp-C0h] BYREF
  HLOCAL v45; // [rsp+80h] [rbp-B8h] BYREF
  char *v46; // [rsp+88h] [rbp-B0h] BYREF
  _QWORD *v47; // [rsp+90h] [rbp-A8h]
  _QWORD **v48; // [rsp+98h] [rbp-A0h]
  unsigned __int64 *v49; // [rsp+A0h] [rbp-98h]
  char v50; // [rsp+A8h] [rbp-90h]
  HLOCAL *v51; // [rsp+B0h] [rbp-88h]
  char v52; // [rsp+B8h] [rbp-80h]
  __int64 v53; // [rsp+C0h] [rbp-78h] BYREF
  HLOCAL *p_hMem; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v55; // [rsp+D8h] [rbp-60h] BYREF
  char v56; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v1 = a1;
  v47 = a1;
  v2 = operator new(0x10u);
  v45 = v2;
  *v2 = 0;
  v2[1] = 0;
  v3 = operator new(0xD0u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *v2 = v3;
  *v1 = v2;
  v39 = 0;
  v40[1] = v40;
  v40[0] = v40;
  ExtensionRegistry = CodeIntegrity::Management::LoadExtensionRegistry((__int64)v40);
  if ( ExtensionRegistry < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x162,
      (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
      (const char *)(unsigned int)ExtensionRegistry,
      v34);
  v8 = v40;
  v51 = v40;
  v52 = 1;
  AllPolicyFiles = SIPolicyPmGetAllPolicyFiles((int)retaddr, v5, v6, v7, (__int64)v40, 0, v39, (__int64)&v39);
  if ( AllPolicyFiles < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x176,
      (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
      (const char *)(unsigned int)AllPolicyFiles,
      v35);
  if ( v39 )
  {
    v12 = saturated_mul(v39, 0x18u);
    v13 = operator new[](v12);
    memset_0(v13, 0, v12);
    v41 = v13;
    v14 = 13;
    v37 = 13;
    v15 = &v41;
    v48 = &v41;
    v49 = &v39;
    v50 = 1;
    v20 = SIPolicyPmGetAllPolicyFiles(v17, v16, v18, v19, (__int64)v40, (__int64)v13, v39, (__int64)&v39);
    v21 = retaddr;
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x18E,
        (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
        (const char *)(unsigned int)v20,
        v36);
    for ( i = 0; ; ++i )
    {
      v43 = i;
      if ( i >= v39 )
        break;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        hMem = 0;
        v44 = 0;
        p_hMem = &hMem;
        v55 = 0;
        v56 = 1;
        v23 = SIPolicyPmReadPolicy((__int64)v21, (struct _UNICODE_STRING *)&v41[3 * i], &v55, (ULONG *)&v44);
        if ( v23 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x19B,
            (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
            (const char *)(unsigned int)v23,
            v36);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>((__int64)&p_hMem);
        v46 = (char *)&v41[3 * i];
        v45 = hMem;
        std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::_Emplace<unsigned char *,unsigned __int64 &,_SIPOLICY_FILE_ITEM *>(
          *v1,
          (int)&v53,
          (int)&v45,
          (int)&v44,
          (__int64)&v46);
        *(_BYTE *)(v53 + 122) = 1;
        v21 = (wil::details::in1diag3 *)hMem;
        hMem = 0;
        if ( v21 )
          LocalFree(v21);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
        {
          if ( (Microsoft_Windows_DeviceGuardEnableBits & 1) != 0 )
          {
            v29 = wil::ResultFromCaughtException(v21);
            std::wstring::wstring(&p_hMem, v41[3 * v43 + 1], (unsigned __int64)LOWORD(v41[3 * v43]) >> 1);
            v30 = v37 | 2;
            v37 |= 2u;
            v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            McTemplateU0zd_EventWriteTransfer(v33, v32, v31, v29);
          }
          else
          {
            v30 = v37;
          }
          if ( (v30 & 2) != 0 )
          {
            v37 = v30 & 0xFFFFFFFD;
            std::wstring::_Tidy_deallocate((__int64)&p_hMem);
          }
          v8 = v51;
          v15 = v48;
          i = v43;
          v14 = v37;
          v1 = v47;
          __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18000B02C);
        }
      }
    }
    SIPolicyPmFreeFileItems(*v15, *(unsigned int *)v49);
    v24 = v14 & 0xFE;
    std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>((void **)&v41, v25);
    while ( 1 )
    {
      v26 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (HLOCAL *)v26[1] != v8 || (v27 = (_QWORD *)*v26, *(_QWORD **)(*v26 + 8LL) != v26) )
LABEL_22:
        __fastfail(3u);
      *v8 = v27;
      v27[1] = v8;
      CodeIntegrity::Management::FreeExtRegistry(v26);
    }
    if ( (v24 & 1) != 0 )
      std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>::~unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>(v1);
  }
  else
  {
    while ( 1 )
    {
      v10 = v40[0];
      if ( v40[0] == v40 )
        break;
      if ( *((HLOCAL **)v40[0] + 1) != v40 )
        goto LABEL_22;
      v11 = *(_QWORD *)v40[0];
      if ( *(HLOCAL *)(*(_QWORD *)v40[0] + 8LL) != v40[0] )
        goto LABEL_22;
      v40[0] = *(HLOCAL *)v40[0];
      *(_QWORD *)(v11 + 8) = v40;
      CodeIntegrity::Management::FreeExtRegistry(v10);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000ad4c  push    rbx
0x18000ad4e  push    rdi
0x18000ad4f  push    r12
0x18000ad51  push    r13
0x18000ad53  push    r14
0x18000ad55  push    r15
0x18000ad57  sub     rsp, 108h
0x18000ad5e  mov     rax, cs:__security_cookie
0x18000ad65  xor     rax, rsp
0x18000ad68  mov     [rsp+138h+var_48], rax
0x18000ad70  mov     r15, rcx
0x18000ad73  mov     [rsp+138h+var_A8], rcx
0x18000ad7b  mov     [rsp+138h+var_F8], 1
0x18000ad83  mov     ecx, 10h; Size
0x18000ad88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad8d  mov     rbx, rax
0x18000ad90  mov     [rsp+138h+var_B8], rax
0x18000ad98  mov     qword ptr [rax], 0
0x18000ad9f  mov     qword ptr [rax+8], 0
0x18000ada7  mov     ecx, 0D0h; Size
0x18000adac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000adb1  mov     [rax], rax
0x18000adb4  mov     [rax+8], rax
0x18000adb8  mov     [rax+10h], rax
0x18000adbc  mov     word ptr [rax+18h], 101h
0x18000adc2  mov     [rbx], rax
0x18000adc5  mov     [r15], rbx
0x18000adc8  mov     [rsp+138h+var_F8], 5
0x18000add0  mov     [rsp+138h+var_F0], 0
0x18000add9  lea     rax, [rsp+138h+var_E8]
0x18000adde  mov     [rsp+138h+var_E0], rax
0x18000ade3  lea     rax, [rsp+138h+var_E8]
0x18000ade8  mov     [rsp+138h+var_E8], rax
0x18000aded  lea     rcx, [rsp+138h+var_E8]
0x18000adf2  call    CodeIntegrity__Management__LoadExtensionRegistry
0x18000adf7  mov     rcx, [rsp+138h]; this
0x18000adff  test    eax, eax
0x18000ae01  js      loc_18000B0D7
0x18000ae07  lea     r14, [rsp+138h+var_E8]
0x18000ae0c  mov     [rsp+138h+var_88], r14
0x18000ae14  mov     [rsp+138h+var_80], 1
0x18000ae1c  lea     rax, [rsp+138h+var_F0]
0x18000ae21  mov     [rsp+138h+var_100], rax
0x18000ae26  mov     eax, dword ptr [rsp+138h+var_F0]
0x18000ae2a  mov     [rsp+138h+var_108], eax
0x18000ae2e  mov     [rsp+138h+var_110], 0
0x18000ae37  lea     rax, [rsp+138h+var_E8]
0x18000ae3c  mov     qword ptr [rsp+138h+var_118], rax; int
0x18000ae41  call    SIPolicyPmGetAllPolicyFiles
0x18000ae46  mov     rcx, [rsp+138h]; this
0x18000ae4e  test    eax, eax
0x18000ae50  js      loc_18000B0EC
0x18000ae56  cmp     [rsp+138h+var_F0], 0
0x18000ae5c  jnz     short loc_18000AEA3
0x18000ae5e  lea     rax, [rsp+138h+var_E8]
0x18000ae63  mov     rcx, [rsp+138h+var_E8]; hMem
0x18000ae68  cmp     rcx, rax
0x18000ae6b  jz      short loc_18000AE9E
0x18000ae6d  lea     rax, [rsp+138h+var_E8]
0x18000ae72  cmp     [rcx+8], rax
0x18000ae76  jnz     loc_18000B09D
0x18000ae7c  mov     rax, [rcx]
0x18000ae7f  cmp     [rax+8], rcx
0x18000ae83  jnz     loc_18000B09D
0x18000ae89  mov     [rsp+138h+var_E8], rax
0x18000ae8e  lea     rdx, [rsp+138h+var_E8]
0x18000ae93  mov     [rax+8], rdx
0x18000ae97  call    CodeIntegrity__Management__FreeExtRegistry
0x18000ae9c  jmp     short loc_18000AE5E
0x18000ae9e  jmp     loc_18000B0B2
0x18000aea3  mov     eax, 18h
0x18000aea8  mul     [rsp+138h+var_F0]
0x18000aead  mov     rbx, rax
0x18000aeb0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000aeb7  cmovb   rbx, rax
0x18000aebb  mov     rcx, rbx; unsigned __int64
0x18000aebe  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000aec3  mov     rdi, rax
0x18000aec6  mov     r8, rbx; Size
0x18000aec9  xor     edx, edx; Val
0x18000aecb  mov     rcx, rax; void *
0x18000aece  call    memset_0
0x18000aed3  mov     [rsp+138h+var_D8], rdi
0x18000aed8  mov     r12d, 0Dh
0x18000aede  mov     [rsp+138h+var_F8], r12d
0x18000aee3  lea     r13, [rsp+138h+var_D8]
0x18000aee8  mov     [rsp+138h+var_A0], r13
0x18000aef0  lea     rax, [rsp+138h+var_F0]
0x18000aef5  mov     [rsp+138h+var_98], rax
0x18000aefd  mov     [rsp+138h+var_90], 1
0x18000af05  lea     rax, [rsp+138h+var_F0]
0x18000af0a  mov     [rsp+138h+var_100], rax
0x18000af0f  mov     eax, dword ptr [rsp+138h+var_F0]
0x18000af13  mov     [rsp+138h+var_108], eax
0x18000af17  mov     [rsp+138h+var_110], rdi
0x18000af1c  lea     rax, [rsp+138h+var_E8]
0x18000af21  mov     qword ptr [rsp+138h+var_118], rax; int
0x18000af26  call    SIPolicyPmGetAllPolicyFiles
0x18000af2b  mov     rcx, [rsp+138h]; this
0x18000af33  test    eax, eax
0x18000af35  js      loc_18000B101
0x18000af3b  xor     ebx, ebx
0x18000af3d  mov     [rsp+138h+var_C8], rbx
0x18000af42  cmp     rbx, [rsp+138h+var_F0]
0x18000af47  jnb     loc_18000B056
0x18000af4d  mov     [rsp+138h+hMem], 0
0x18000af56  mov     [rsp+138h+var_C0], 0
0x18000af5f  lea     rax, [rsp+138h+hMem]
0x18000af64  mov     [rsp+138h+var_68], rax
0x18000af6c  mov     [rsp+138h+var_60], 0
0x18000af78  mov     [rsp+138h+var_58], 1
0x18000af80  lea     rdi, [rbx+rbx*2]
0x18000af84  mov     rax, [rsp+138h+var_D8]
0x18000af89  lea     rdx, [rax+rdi*8]
0x18000af8d  lea     r9, [rsp+138h+var_C0]
0x18000af92  lea     r8, [rsp+138h+var_60]
0x18000af9a  call    SIPolicyPmReadPolicy
0x18000af9f  mov     rcx, [rsp+138h]; this
0x18000afa7  test    eax, eax
0x18000afa9  js      loc_18000B116
0x18000afaf  lea     rcx, [rsp+138h+var_68]
0x18000afb7  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>(void)
0x18000afbc  mov     rax, [rsp+138h+var_D8]
0x18000afc1  lea     rcx, [rax+rdi*8]
0x18000afc5  mov     [rsp+138h+var_B0], rcx
0x18000afcd  mov     rax, [rsp+138h+hMem]
0x18000afd2  mov     [rsp+138h+var_B8], rax
0x18000afda  lea     rax, [rsp+138h+var_B0]
0x18000afe2  mov     qword ptr [rsp+138h+var_118], rax
0x18000afe7  lea     r9, [rsp+138h+var_C0]
0x18000afec  lea     r8, [rsp+138h+var_B8]
0x18000aff4  lea     rdx, [rsp+138h+var_78]
0x18000affc  mov     rcx, [r15]
0x18000afff  call    ??$_Emplace@PEAEAEA_KPEAU_SIPOLICY_FILE_ITEM@@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@_N@1@$$QEAPEAEAEA_K$$QEAPEAU_SIPOLICY_FILE_ITEM@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::_Emplace<uchar *,unsigned __int64 &,_SIPOLICY_FILE_ITEM *>(uchar * &&,unsigned __int64 &,_SIPOLICY_FILE_ITEM * &&)
0x18000b004  mov     rax, [rsp+138h+var_78]
0x18000b00c  mov     byte ptr [rax+7Ah], 1
0x18000b010  mov     rcx, [rsp+138h+hMem]; hMem
0x18000b015  mov     [rsp+138h+hMem], 0
0x18000b01e  test    rcx, rcx
0x18000b021  jz      short loc_18000B02A
0x18000b023  call    cs:__imp_LocalFree
0x18000b029  nop
0x18000b02a  jmp     short loc_18000B04E
0x18000b02c  mov     r14, [rsp+138h+var_88]
0x18000b034  mov     r13, [rsp+138h+var_A0]
0x18000b03c  mov     rbx, [rsp+138h+var_C8]
0x18000b041  mov     r12d, [rsp+138h+var_F8]
0x18000b046  mov     r15, [rsp+138h+var_A8]
0x18000b04e  inc     rbx
0x18000b051  jmp     loc_18000AF3D
0x18000b056  mov     rdx, [rsp+138h+var_98]
0x18000b05e  mov     edx, [rdx]
0x18000b060  mov     rcx, [r13+0]
0x18000b064  call    SIPolicyPmFreeFileItems
0x18000b069  and     r12d, 0FFFFFFFEh
0x18000b06d  lea     rcx, [rsp+138h+var_D8]
0x18000b072  call    ??1?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$default_delete@$$BY0A@U_SIPOLICY_FILE_ITEM@@@std@@@std@@QEAA@XZ; std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(void)
0x18000b077  nop
0x18000b078  mov     rcx, [r14]; hMem
0x18000b07b  cmp     rcx, r14
0x18000b07e  jz      short loc_18000B0A4
0x18000b080  cmp     [rcx+8], r14
0x18000b084  jnz     short loc_18000B09D
0x18000b086  mov     rax, [rcx]
0x18000b089  cmp     [rax+8], rcx
0x18000b08d  jnz     short loc_18000B09D
0x18000b08f  mov     [r14], rax
0x18000b092  mov     [rax+8], r14
0x18000b096  call    CodeIntegrity__Management__FreeExtRegistry
0x18000b09b  jmp     short loc_18000B078
0x18000b09d  mov     ecx, 3
0x18000b0a2  int     29h; Win8: RtlFailFast(ecx)
0x18000b0a4  test    r12b, 1
0x18000b0a8  jz      short loc_18000B0B2
0x18000b0aa  mov     rcx, r15
0x18000b0ad  call    ??1?$unique_ptr@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>::~unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>(void)
0x18000b0b2  mov     rax, r15
0x18000b0b5  mov     rcx, [rsp+138h+var_48]
0x18000b0bd  xor     rcx, rsp; StackCookie
0x18000b0c0  call    __security_check_cookie
0x18000b0c5  add     rsp, 108h
0x18000b0cc  pop     r15
0x18000b0ce  pop     r14
0x18000b0d0  pop     r13
0x18000b0d2  pop     r12
0x18000b0d4  pop     rdi
0x18000b0d5  pop     rbx
0x18000b0d6  retn
0x18000b0d7  mov     r9d, eax; char *
0x18000b0da  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b0e1  mov     edx, 162h; void *
0x18000b0e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b0ec  mov     r9d, eax; char *
0x18000b0ef  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b0f6  mov     edx, 176h; void *
0x18000b0fb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000b101  mov     r9d, eax; char *
0x18000b104  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b10b  mov     edx, 18Eh; void *
0x18000b110  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000b116  mov     r9d, eax; char *
0x18000b119  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b120  mov     edx, 19Bh; void *
0x18000b125  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
