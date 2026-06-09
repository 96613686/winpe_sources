# GetApplicablePackagesWithAppChosenResources

- ea: `0x18000cef0`
- end: `0x18000d12a`
- name: `GetApplicablePackagesWithAppChosenResources`
- size: `570`
- prototype: `__int64 __fastcall(struct IAppxBundleManifestReader *, struct ApplicabilityContext *, __int64, const unsigned __int16 **, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ce90`
- `0x18000d510`

## callees

- `0x180001250`
- `0x1800012e8`
- `0x18000181c`
- `0x180003b30`
- `0x180003c00`
- `0x180003c30`
- `0x180004304`
- `0x180004494`
- `0x18000a9a4`
- `0x18000b468`
- `0x18000cef0`
- `0x180016b8c`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d00c`

## pseudocode

```c
__int64 __fastcall GetApplicablePackagesWithAppChosenResources(
        struct IAppxBundleManifestReader *a1,
        struct ApplicabilityContext *a2,
        __int64 a3,
        const unsigned __int16 **a4,
        _DWORD *a5,
        _QWORD *a6)
{
  unsigned int v7; // ebx
  __int64 ApplicablePackages; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  LPVOID v13; // rax
  const char *v14; // r9
  __int64 v15; // rsi
  _QWORD *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 i; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  const char *v22; // r9
  __int64 result; // rax
  _BYTE v24[8]; // [rsp+38h] [rbp-220h] BYREF
  _QWORD *v25; // [rsp+40h] [rbp-218h]
  __int64 v26; // [rsp+48h] [rbp-210h]
  __int64 v27; // [rsp+58h] [rbp-200h]
  _BYTE v28[416]; // [rsp+60h] [rbp-1F8h] BYREF
  _QWORD v29[4]; // [rsp+200h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v27 = -2;
  v7 = a3;
  if ( (Microsoft_Windows_ApplicabilityEngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, GetApplicablePackages_Start, a3, 1, v29);
  *a6 = 0;
  *a5 = 0;
  try
  {
    ResourcePackResolver::ResourcePackResolver((ResourcePackResolver *)v28, a1, a2);
    ResourcePackResolver::InitializeAppChosenPackages((ResourcePackResolver *)v28, v7, a4);
    std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(v24);
    ApplicablePackages = ResourcePackResolver::GetApplicablePackages((ResourcePackResolver *)v28);
    if ( v24 != (_BYTE *)ApplicablePackages )
    {
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::clear(v24);
      v11 = v25;
      v25 = *(_QWORD **)(ApplicablePackages + 8);
      *(_QWORD *)(ApplicablePackages + 8) = v11;
      v12 = v26;
      v26 = *(_QWORD *)(ApplicablePackages + 16);
      *(_QWORD *)(ApplicablePackages + 16) = v12;
    }
    std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(v29);
    if ( v26 )
    {
      v13 = CoTaskMemAlloc(8 * v26);
      *a6 = v13;
      if ( !v13 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          v14);
      v15 = 0;
      v16 = v25;
      v17 = *v25;
      while ( (_QWORD *)v17 != v16 )
      {
        v18 = *(_QWORD *)(v17 + 24);
        if ( v18 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*(_QWORD *)(v17 + 24));
        v29[0] = 0;
        *(_QWORD *)(*a6 + 8 * v15) = v18;
        Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v29);
        if ( !*(_BYTE *)(v17 + 33) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v17 + 16) + 33LL) )
          {
            for ( i = *(_QWORD *)(v17 + 8); !*(_BYTE *)(i + 33) && v17 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v17 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Min();
          }
          v17 = i;
        }
        v15 = (unsigned int)(v15 + 1);
        v16 = v25;
      }
      *a5 = v15;
    }
    std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(v24);
    ResourcePackResolver::~ResourcePackResolver((ResourcePackResolver *)v28);
    if ( (Microsoft_Windows_ApplicabilityEngineEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v20, "k", v21, 1, v29);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x234,
                           (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x18000cef0  mov     r11, rsp
0x18000cef3  push    rsi
0x18000cef4  push    rdi
0x18000cef5  push    r12
0x18000cef7  push    r14
0x18000cef9  push    r15
0x18000cefb  sub     rsp, 230h
0x18000cf02  mov     [rsp+258h+var_200], 0FFFFFFFFFFFFFFFEh
0x18000cf0b  mov     [r11+10h], rbx
0x18000cf0f  mov     rax, cs:__security_cookie
0x18000cf16  xor     rax, rsp
0x18000cf19  mov     [rsp+258h+var_38], rax
0x18000cf21  mov     rdi, r9
0x18000cf24  mov     ebx, r8d
0x18000cf27  mov     rsi, rdx
0x18000cf2a  mov     r14, rcx
0x18000cf2d  mov     r12, [rsp+258h+arg_20]
0x18000cf35  mov     r15, [rsp+258h+arg_28]
0x18000cf3d  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 1
0x18000cf44  jz      short loc_18000CF61
0x18000cf46  lea     rax, [r11-58h]
0x18000cf4a  mov     [rsp+258h+var_238], rax
0x18000cf4f  mov     r9d, 1
0x18000cf55  lea     rdx, GetApplicablePackages_Start
0x18000cf5c  call    McGenEventWrite_EventWriteTransfer
0x18000cf61  mov     [rsp+258h+var_227], 1
0x18000cf66  mov     qword ptr [r15], 0
0x18000cf6d  mov     dword ptr [r12], 0
0x18000cf75  mov     r8, rsi; struct ApplicabilityContext *
0x18000cf78  mov     rdx, r14; struct IAppxBundleManifestReader *
0x18000cf7b  lea     rcx, [rsp+258h+var_1F8]; this
0x18000cf80  call    ??0ResourcePackResolver@@QEAA@PEAUIAppxBundleManifestReader@@PEAVApplicabilityContext@@@Z; ResourcePackResolver::ResourcePackResolver(IAppxBundleManifestReader *,ApplicabilityContext *)
0x18000cf85  nop
0x18000cf86  mov     r8, rdi; unsigned __int16 **
0x18000cf89  mov     edx, ebx; unsigned int
0x18000cf8b  lea     rcx, [rsp+258h+var_1F8]; this
0x18000cf90  call    ?InitializeAppChosenPackages@ResourcePackResolver@@QEAAXIPEAPEBG@Z; ResourcePackResolver::InitializeAppChosenPackages(uint,ushort const * *)
0x18000cf95  lea     rcx, [rsp+258h+var_220]
0x18000cf9a  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x18000cf9f  nop
0x18000cfa0  lea     rdx, [rsp+258h+var_58]
0x18000cfa8  lea     rcx, [rsp+258h+var_1F8]; this
0x18000cfad  call    ?GetApplicablePackages@ResourcePackResolver@@QEAA?AV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@XZ; ResourcePackResolver::GetApplicablePackages(void)
0x18000cfb2  mov     rbx, rax
0x18000cfb5  lea     rax, [rsp+258h+var_220]
0x18000cfba  cmp     rax, rbx
0x18000cfbd  jz      short loc_18000CFED
0x18000cfbf  lea     rcx, [rsp+258h+var_220]
0x18000cfc4  call    ?clear@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::clear(void)
0x18000cfc9  mov     rcx, [rsp+258h+var_218]
0x18000cfce  mov     rax, [rbx+8]
0x18000cfd2  mov     [rsp+258h+var_218], rax
0x18000cfd7  mov     [rbx+8], rcx
0x18000cfdb  mov     rcx, [rsp+258h+var_210]
0x18000cfe0  mov     rax, [rbx+10h]
0x18000cfe4  mov     [rsp+258h+var_210], rax
0x18000cfe9  mov     [rbx+10h], rcx
0x18000cfed  lea     rcx, [rsp+258h+var_58]
0x18000cff5  call    ??1?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(void)
0x18000cffa  mov     rcx, [rsp+258h+var_210]
0x18000cfff  test    rcx, rcx
0x18000d002  jz      loc_18000D0BB
0x18000d008  shl     rcx, 3; cb
0x18000d00c  call    cs:__imp_CoTaskMemAlloc
0x18000d012  mov     [r15], rax
0x18000d015  mov     rcx, [rsp+258h]; this
0x18000d01d  test    rax, rax
0x18000d020  jnz     short loc_18000D033
0x18000d022  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d029  mov     edx, 227h; void *
0x18000d02e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000d033  xor     esi, esi
0x18000d035  mov     rax, [rsp+258h+var_218]
0x18000d03a  mov     rbx, [rax]
0x18000d03d  cmp     rbx, rax
0x18000d040  jz      short loc_18000D0B7
0x18000d042  mov     rdi, [rbx+18h]
0x18000d046  test    rdi, rdi
0x18000d049  jz      short loc_18000D05B
0x18000d04b  mov     rax, [rdi]
0x18000d04e  mov     rcx, rdi
0x18000d051  mov     rax, [rax+8]
0x18000d055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d05a  nop
0x18000d05b  mov     [rsp+258h+var_58], 0
0x18000d067  mov     rax, [r15]
0x18000d06a  mov     [rax+rsi*8], rdi
0x18000d06e  lea     rcx, [rsp+258h+var_58]
0x18000d076  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x18000d07b  cmp     byte ptr [rbx+21h], 0
0x18000d07f  jnz     short loc_18000D0AE
0x18000d081  mov     rcx, [rbx+10h]
0x18000d085  cmp     byte ptr [rcx+21h], 0
0x18000d089  jnz     short loc_18000D092
0x18000d08b  call    ?_Min@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Min(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x18000d090  jmp     short loc_18000D0AB
0x18000d092  mov     rax, [rbx+8]
0x18000d096  jmp     short loc_18000D0A5
0x18000d098  cmp     rbx, [rax+10h]
0x18000d09c  jnz     short loc_18000D0AB
0x18000d09e  mov     rbx, rax
0x18000d0a1  mov     rax, [rax+8]
0x18000d0a5  cmp     byte ptr [rax+21h], 0
0x18000d0a9  jz      short loc_18000D098
0x18000d0ab  mov     rbx, rax
0x18000d0ae  inc     esi
0x18000d0b0  mov     rax, [rsp+258h+var_218]
0x18000d0b5  jmp     short loc_18000D03D
0x18000d0b7  mov     [r12], esi
0x18000d0bb  lea     rcx, [rsp+258h+var_220]
0x18000d0c0  call    ??1?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(void)
0x18000d0c5  nop
0x18000d0c6  lea     rcx, [rsp+258h+var_1F8]; this
0x18000d0cb  call    ??1ResourcePackResolver@@QEAA@XZ; ResourcePackResolver::~ResourcePackResolver(void)
0x18000d0d0  nop
0x18000d0d1  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 1
0x18000d0d8  jz      short loc_18000D0F9
0x18000d0da  lea     rax, [rsp+258h+var_58]
0x18000d0e2  mov     [rsp+258h+var_238], rax
0x18000d0e7  mov     r9d, 1
0x18000d0ed  lea     rdx, GetApplicablePackages_Stop; "k"
0x18000d0f4  call    McGenEventWrite_EventWriteTransfer
0x18000d0f9  xor     eax, eax
0x18000d0fb  jmp     short loc_18000D101
0x18000d0fd  mov     eax, [rsp+30h]
0x18000d101  mov     rcx, [rsp+258h+var_38]
0x18000d109  xor     rcx, rsp; StackCookie
0x18000d10c  call    __security_check_cookie
0x18000d111  mov     rbx, [rsp+258h+arg_8]
0x18000d119  add     rsp, 230h
0x18000d120  pop     r15
0x18000d122  pop     r14
0x18000d124  pop     r12
0x18000d126  pop     rdi
0x18000d127  pop     rsi
0x18000d128  retn
```
