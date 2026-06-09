# MitigationExecutionContext::GetMitigationContext(_GUID)

- ea: `0x180042f54`
- end: `0x1800430e5`
- name: `?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@U_GUID@@@Z`
- size: `401`
- prototype: `struct MitigationContext *__fastcall(IID *rclsid)`
- caller_count: `21`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a970`
- `0x18001b9e0`
- `0x18001c09c`
- `0x18001c374`
- `0x18001c7b0`
- `0x18001cbfc`
- `0x18001da18`
- `0x18001edf4`
- `0x18001fb30`
- `0x1800203d0`
- `0x180027270`
- `0x180028148`
- `0x1800283a4`
- `0x18002bc50`
- `0x18003c7a0`
- `0x18003ccf0`
- `0x18003da90`
- `0x180042b94`
- `0x180042c00`
- `0x180042da4`
- `0x180042edc`

## callees

- `0x18000a6e0`
- `0x180013ebc`
- `0x180018858`
- `0x18002407c`
- `0x180041e94`
- `0x1800422f8`
- `0x1800425e0`
- `0x180042754`
- `0x180042988`
- `0x180042f54`
- `0x1800440e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180043004`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180043004`
- `RPCRT4!UuidHash` at `0x180042f9f`
- `RPCRT4!UuidHash` at `0x180042f9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct MitigationContext *__fastcall MitigationExecutionContext::GetMitigationContext(IID *rclsid)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  unsigned __int8 *v4; // rcx
  unsigned __int8 *v5; // rcx
  __int64 v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int8 v11[4]; // [rsp+20h] [rbp-E0h] BYREF
  RPC_STATUS Status; // [rsp+24h] [rbp-DCh] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+38h] [rbp-C8h]
  _BYTE v16[16]; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[40]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[408]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v20[8]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v21[440]; // [rsp+228h] [rbp+128h] BYREF

  Status = 0;
  *(_WORD *)v11 = 0;
  Uuid = *rclsid;
  *(_WORD *)v11 = UuidHash(&Uuid, &Status);
  v3 = (_QWORD *)std::_Hash<std::_Umap_traits<unsigned short,MitigationContext,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,MitigationContext>>,0>>::find(
                   v2,
                   v16,
                   v11);
  v4 = (unsigned __int8 *)qword_180081C28;
  if ( *v3 == qword_180081C28 )
  {
    lpsz = 0;
    v14 = 0;
    v15 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    v14 = -1;
    v15 = -1;
    if ( StringFromCLSID(rclsid, &lpsz) < 0 )
    {
      v6 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned short,MitigationContext,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,MitigationContext>>,0>>::_Try_emplace<unsigned short const &,>(
                        v5,
                        (__int64)v16,
                        v11);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
      return (struct MitigationContext *)(v6 + 24);
    }
    MitigationContext::MitigationContext((MitigationContext *)v18);
    if ( !v18[34] )
    {
      v8 = std::_WChar_traits<unsigned short>::length(lpsz);
      std::wstring::_Assign<unsigned short>(v19, v9, v8);
    }
    *(_WORD *)v20 = *(_WORD *)v11;
    MitigationContext::MitigationContext((MitigationContext *)v21, (const struct MitigationContext *)v18);
    std::_Hash<std::_Umap_traits<unsigned short,MitigationContext,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,MitigationContext>>,0>>::emplace<std::pair<unsigned short,MitigationContext>>(
      v10,
      (__int64)v16,
      v20);
    MitigationContext::~MitigationContext((MitigationContext *)v21);
    MitigationContext::~MitigationContext((MitigationContext *)v18);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  return (struct MitigationContext *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned short,MitigationContext,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,MitigationContext>>,0>>::_Try_emplace<unsigned short const &,>(
                                                   v4,
                                                   (__int64)v16,
                                                   v11)
                                    + 24LL);
}

```

## disassembly

```asm
0x180042f54  mov     [rsp-8+arg_8], rbx
0x180042f59  push    rbp
0x180042f5a  lea     rbp, [rsp-2F0h]
0x180042f62  sub     rsp, 3F0h
0x180042f69  mov     rax, cs:__security_cookie
0x180042f70  xor     rax, rsp
0x180042f73  mov     [rbp+2F0h+var_10], rax
0x180042f7a  mov     rbx, rcx
0x180042f7d  mov     [rsp+3F0h+Status], 0
0x180042f85  xor     eax, eax
0x180042f87  mov     word ptr [rsp+3F0h+var_3D0], ax
0x180042f8c  movaps  xmm0, xmmword ptr [rcx]
0x180042f8f  movdqu  xmmword ptr [rsp+3F0h+Uuid.Data1], xmm0
0x180042f95  lea     rdx, [rsp+3F0h+Status]; Status
0x180042f9a  lea     rcx, [rsp+3F0h+Uuid]; Uuid
0x180042f9f  call    cs:__imp_UuidHash
0x180042fa5  mov     word ptr [rsp+3F0h+var_3D0], ax
0x180042faa  lea     r8, [rsp+3F0h+var_3D0]
0x180042faf  lea     rdx, [rsp+3F0h+var_3B0]
0x180042fb4  call    ?find@?$_Hash@V?$_Umap_traits@GVMitigationContext@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGVMitigationContext@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGVMitigationContext@@@std@@@std@@@std@@@2@AEBG@Z; std::_Hash<std::_Umap_traits<ushort,MitigationContext,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,MitigationContext>>,0>>::find(ushort const &)
0x180042fb9  mov     rcx, cs:qword_180081C28
0x180042fc0  cmp     [rax], rcx
0x180042fc3  jnz     loc_1800430AF
0x180042fc9  mov     [rsp+3F0h+lpsz], 0
0x180042fd2  mov     [rsp+3F0h+var_3C0], 0
0x180042fdb  mov     [rsp+3F0h+var_3B8], 0
0x180042fe4  lea     rcx, [rsp+3F0h+lpsz]
0x180042fe9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042fee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042ff2  mov     [rsp+3F0h+var_3C0], rax
0x180042ff7  mov     [rsp+3F0h+var_3B8], rax
0x180042ffc  lea     rdx, [rsp+3F0h+lpsz]; lplpsz
0x180043001  mov     rcx, rbx; rclsid
0x180043004  call    cs:__imp_StringFromCLSID
0x18004300a  test    eax, eax
0x18004300c  jns     short loc_180043033
0x18004300e  lea     r8, [rsp+3F0h+var_3D0]
0x180043013  lea     rdx, [rsp+3F0h+var_3B0]
0x180043018  call    ??$_Try_emplace@AEBG$$V@?$_Hash@V?$_Umap_traits@GVMitigationContext@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGVMitigationContext@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBGVMitigationContext@@@std@@PEAX@std@@_N@1@AEBG@Z; std::_Hash<std::_Umap_traits<ushort,MitigationContext,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,MitigationContext>>,0>>::_Try_emplace<ushort const &,>(ushort const &)
0x18004301d  mov     rbx, [rax]
0x180043020  lea     rcx, [rsp+3F0h+lpsz]
0x180043025  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004302a  lea     rax, [rbx+18h]
0x18004302e  jmp     loc_1800430C5
0x180043033  lea     rcx, [rsp+3F0h+var_390]; this
0x180043038  call    ??0MitigationContext@@QEAA@XZ; MitigationContext::MitigationContext(void)
0x18004303d  nop
0x18004303e  cmp     [rbp+2F0h+var_36E], 0
0x180043042  jnz     short loc_18004305D
0x180043044  mov     rcx, [rsp+3F0h+lpsz]
0x180043049  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004304e  mov     r8, rax
0x180043051  mov     rdx, rcx
0x180043054  lea     rcx, [rbp+2F0h+var_368]
0x180043058  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004305d  movzx   eax, word ptr [rsp+3F0h+var_3D0]
0x180043062  mov     word ptr [rbp+2F0h+var_1D0], ax
0x180043069  lea     rdx, [rsp+3F0h+var_390]; struct MitigationContext *
0x18004306e  lea     rcx, [rbp+2F0h+var_1C8]; this
0x180043075  call    ??0MitigationContext@@QEAA@AEBV0@@Z; MitigationContext::MitigationContext(MitigationContext const &)
0x18004307a  nop
0x18004307b  lea     r8, [rbp+2F0h+var_1D0]
0x180043082  lea     rdx, [rsp+3F0h+var_3B0]
0x180043087  call    ??$emplace@U?$pair@GVMitigationContext@@@std@@@?$_Hash@V?$_Umap_traits@GVMitigationContext@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGVMitigationContext@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGVMitigationContext@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@GVMitigationContext@@@1@@Z; std::_Hash<std::_Umap_traits<ushort,MitigationContext,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,MitigationContext>>,0>>::emplace<std::pair<ushort,MitigationContext>>(std::pair<ushort,MitigationContext> &&)
0x18004308c  nop
0x18004308d  lea     rcx, [rbp+2F0h+var_1C8]; this
0x180043094  call    ??1MitigationContext@@QEAA@XZ; MitigationContext::~MitigationContext(void)
0x180043099  nop
0x18004309a  lea     rcx, [rsp+3F0h+var_390]; this
0x18004309f  call    ??1MitigationContext@@QEAA@XZ; MitigationContext::~MitigationContext(void)
0x1800430a4  nop
0x1800430a5  lea     rcx, [rsp+3F0h+lpsz]
0x1800430aa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800430af  lea     r8, [rsp+3F0h+var_3D0]
0x1800430b4  lea     rdx, [rsp+3F0h+var_3B0]
0x1800430b9  call    ??$_Try_emplace@AEBG$$V@?$_Hash@V?$_Umap_traits@GVMitigationContext@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGVMitigationContext@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBGVMitigationContext@@@std@@PEAX@std@@_N@1@AEBG@Z; std::_Hash<std::_Umap_traits<ushort,MitigationContext,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,MitigationContext>>,0>>::_Try_emplace<ushort const &,>(ushort const &)
0x1800430be  mov     rax, [rax]
0x1800430c1  add     rax, 18h
0x1800430c5  mov     rcx, [rbp+2F0h+var_10]
0x1800430cc  xor     rcx, rsp; StackCookie
0x1800430cf  call    __security_check_cookie
0x1800430d4  mov     rbx, [rsp+3F0h+arg_8]
0x1800430dc  add     rsp, 3F0h
0x1800430e3  pop     rbp
0x1800430e4  retn
```
