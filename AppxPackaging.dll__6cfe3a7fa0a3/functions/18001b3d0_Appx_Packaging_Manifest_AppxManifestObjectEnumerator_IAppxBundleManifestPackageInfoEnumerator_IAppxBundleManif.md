# Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::Create(IXMLDOMNodeList *,ushort const *,ushort const *,IAppxBundleManifestPackageInfoEnumerator * *)

- ea: `0x18001b3d0`
- end: `0x18001b637`
- name: `?Create@?$AppxManifestObjectEnumerator@UIAppxBundleManifestPackageInfoEnumerator@@UIAppxBundleManifestPackageInfo@@VBundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@$01@Manifest@Packaging@Appx@@SAJPEAUIXMLDOMNodeList@@PEBG1PEAPEAUIAppxBundleManifestPackageInfoEnumerator@@@Z`
- size: `615`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001afd0`
- `0x1800e4bc0`

## callees

- `0x1800133fc`
- `0x18001b3d0`
- `0x18001b7c4`
- `0x18001b804`
- `0x18001bb60`
- `0x180071f50`
- `0x1800992d0`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b603`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b603`

## string_xrefs

- `0x18001b520`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001b567`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001b5c7`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001b5ea`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18001b619`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::Create(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v7; // r14d
  LPVOID v8; // rbp
  void *v9; // rbx
  LPVOID v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  int v13; // edi
  __int64 v14; // rax
  void *v15; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // eax
  int v21; // [rsp+20h] [rbp-58h]
  LPVOID pv[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v24; // [rsp+98h] [rbp+20h] BYREF

  v7 = a1;
  if ( !a4 )
  {
    v18 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x80004003LL,
      v21);
    return v18;
  }
  v24 = 0;
  if ( !a1 || (v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 64LL))(a1, &v24), v18 = v17, v17 >= 0) )
  {
    v8 = 0;
    pv[0] = 0;
    if ( a2 )
    {
      v19 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
              pv,
              a2);
      v18 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
          (const char *)(unsigned int)v19,
          v21);
        CoTaskMemFree(pv[0]);
        return v18;
      }
      v8 = pv[0];
    }
    v9 = 0;
    pv[0] = 0;
    if ( !a3 )
      goto LABEL_5;
    v20 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
            pv,
            a3);
    v13 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
        (const char *)(unsigned int)v20,
        v21);
      v9 = pv[0];
      goto LABEL_18;
    }
    v9 = pv[0];
    if ( pv[0] )
      v10 = pv[0];
    else
LABEL_5:
      v10 = 0;
    *a4 = 0;
    v11 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( v11 )
    {
      v11[2] = 0;
      *((_DWORD *)v11 + 7) = 0;
      Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfoEnumerator>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfoEnumerator>(v11);
      *v12 = &Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::`vftable';
      v12[4] = 0;
      v12[5] = 0;
      v13 = Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::RuntimeClassInitialize(
              (_DWORD)v12,
              v7,
              v24,
              (_DWORD)v8,
              (__int64)v10);
      v14 = *v12;
      if ( v13 < 0 )
      {
        (*(void (__fastcall **)(_QWORD *))(v14 + 16))(v12);
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))v14)(
                v12,
                &GUID_f9b856ee_49a6_4e19_b2b0_6a2406d63a32,
                a4);
        (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
        if ( v13 >= 0 )
        {
          CoTaskMemFree(0);
          v15 = 0;
LABEL_10:
          CoTaskMemFree(v15);
          return (unsigned int)v13;
        }
      }
    }
    else
    {
      v13 = -2147024882;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v13,
      v21);
LABEL_18:
    CoTaskMemFree(v9);
    v15 = v8;
    goto LABEL_10;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1C9,
    (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
    (const char *)(unsigned int)v17,
    v21);
  return v18;
}

```

## disassembly

```asm
0x18001b3d0  mov     rax, rsp
0x18001b3d3  push    rbx
0x18001b3d4  push    rbp
0x18001b3d5  push    rsi
0x18001b3d6  push    rdi
0x18001b3d7  push    r14
0x18001b3d9  push    r15
0x18001b3db  sub     rsp, 48h
0x18001b3df  mov     r15, r9
0x18001b3e2  mov     rsi, r8
0x18001b3e5  mov     rdi, rdx
0x18001b3e8  mov     r14, rcx
0x18001b3eb  test    r9, r9
0x18001b3ee  jz      loc_18001B5C2
0x18001b3f4  mov     dword ptr [rax+20h], 0
0x18001b3fb  test    rcx, rcx
0x18001b3fe  jnz     loc_18001B4FD
0x18001b404  xor     ebp, ebp
0x18001b406  mov     [rsp+78h+pv], rbp
0x18001b40b  test    rdi, rdi
0x18001b40e  jnz     loc_18001B538
0x18001b414  xor     ebx, ebx
0x18001b416  mov     [rsp+78h+pv], rbx
0x18001b41b  test    rsi, rsi
0x18001b41e  jnz     loc_18001B599
0x18001b424  xor     edi, edi
0x18001b426  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b42d  mov     qword ptr [r15], 0
0x18001b434  mov     ecx, 30h ; '0'; unsigned __int64
0x18001b439  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b43e  mov     rsi, rax
0x18001b441  test    rax, rax
0x18001b444  jz      loc_18001B592
0x18001b44a  mov     qword ptr [rax+10h], 0
0x18001b452  mov     rcx, rax
0x18001b455  mov     dword ptr [rax+1Ch], 0
0x18001b45c  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfoEnumerator@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfoEnumerator>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfoEnumerator>(void)
0x18001b461  lea     rax, ??_7?$AppxManifestObjectEnumerator@UIAppxBundleManifestPackageInfoEnumerator@@UIAppxBundleManifestPackageInfo@@VBundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@$01@Manifest@Packaging@Appx@@6B@; const Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::`vftable'
0x18001b468  mov     qword ptr [rsp+78h+var_58], rdi; int
0x18001b46d  mov     [rsi], rax
0x18001b470  mov     r9, rbp
0x18001b473  mov     qword ptr [rsi+20h], 0
0x18001b47b  mov     rdx, r14
0x18001b47e  mov     qword ptr [rsi+28h], 0
0x18001b486  mov     rcx, rsi
0x18001b489  mov     r8d, [rsp+78h+arg_18]
0x18001b491  call    ?RuntimeClassInitialize@?$AppxManifestObjectEnumerator@UIAppxBundleManifestPackageInfoEnumerator@@UIAppxBundleManifestPackageInfo@@VBundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@$01@Manifest@Packaging@Appx@@QEAAJPEAUIXMLDOMNodeList@@KPEBG1@Z; Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::RuntimeClassInitialize(IXMLDOMNodeList *,ulong,ushort const *,ushort const *)
0x18001b496  mov     edi, eax
0x18001b498  mov     rcx, rsi
0x18001b49b  mov     rax, [rsi]
0x18001b49e  test    edi, edi
0x18001b4a0  js      loc_18001B559
0x18001b4a6  mov     rax, [rax]
0x18001b4a9  lea     rdx, _GUID_f9b856ee_49a6_4e19_b2b0_6a2406d63a32
0x18001b4b0  mov     r8, r15
0x18001b4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4b8  mov     edi, eax
0x18001b4ba  mov     rcx, rsi
0x18001b4bd  mov     rax, [rsi]
0x18001b4c0  mov     rax, [rax+10h]
0x18001b4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c9  test    edi, edi
0x18001b4cb  js      loc_18001B562
0x18001b4d1  xor     ecx, ecx; pv
0x18001b4d3  call    cs:__imp_CoTaskMemFree
0x18001b4da  nop     dword ptr [rax+rax+00h]
0x18001b4df  xor     ecx, ecx; pv
0x18001b4e1  call    cs:__imp_CoTaskMemFree
0x18001b4e8  nop     dword ptr [rax+rax+00h]
0x18001b4ed  mov     eax, edi
0x18001b4ef  add     rsp, 48h
0x18001b4f3  pop     r15
0x18001b4f5  pop     r14
0x18001b4f7  pop     rdi
0x18001b4f8  pop     rsi
0x18001b4f9  pop     rbp
0x18001b4fa  pop     rbx
0x18001b4fb  retn
0x18001b4fd  mov     rax, [rcx]
0x18001b500  lea     rdx, [rsp+78h+arg_18]
0x18001b508  mov     rax, [rax+40h]
0x18001b50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b511  mov     ebx, eax
0x18001b513  test    eax, eax
0x18001b515  jns     loc_18001B404
0x18001b51b  mov     rcx, [rsp+78h]; this
0x18001b520  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001b527  mov     r9d, eax; char *
0x18001b52a  mov     edx, 1C9h; void *
0x18001b52f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b534  mov     eax, ebx
0x18001b536  jmp     short loc_18001B4EF
0x18001b538  mov     rdx, rdi
0x18001b53b  lea     rcx, [rsp+78h+pv]
0x18001b540  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x18001b545  mov     ebx, eax
0x18001b547  test    eax, eax
0x18001b549  js      loc_18001B5E5
0x18001b54f  mov     rbp, [rsp+78h+pv]
0x18001b554  jmp     loc_18001B414
0x18001b559  mov     rax, [rax+10h]
0x18001b55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b562  mov     rcx, [rsp+78h]; this
0x18001b567  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001b56e  mov     r9d, edi; char *
0x18001b571  mov     edx, 1DEh; void *
0x18001b576  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b57b  mov     rcx, rbx; pv
0x18001b57e  call    cs:__imp_CoTaskMemFree
0x18001b585  nop     dword ptr [rax+rax+00h]
0x18001b58a  mov     rcx, rbp
0x18001b58d  jmp     loc_18001B4E1
0x18001b592  mov     edi, 8007000Eh
0x18001b597  jmp     short loc_18001B562
0x18001b599  mov     rdx, rsi
0x18001b59c  lea     rcx, [rsp+78h+pv]
0x18001b5a1  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x18001b5a6  mov     edi, eax
0x18001b5a8  test    eax, eax
0x18001b5aa  js      short loc_18001B614
0x18001b5ac  mov     rbx, [rsp+78h+pv]
0x18001b5b1  test    rbx, rbx
0x18001b5b4  jz      loc_18001B424
0x18001b5ba  mov     rdi, rbx
0x18001b5bd  jmp     loc_18001B426
0x18001b5c2  mov     rcx, [rsp+78h]; this
0x18001b5c7  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001b5ce  mov     ebx, 80004003h
0x18001b5d3  mov     edx, 1C3h; void *
0x18001b5d8  mov     r9d, ebx; char *
0x18001b5db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5e0  jmp     loc_18001B534
0x18001b5e5  mov     rcx, [rsp+78h]; this
0x18001b5ea  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001b5f1  mov     r9d, ebx; char *
0x18001b5f4  mov     edx, 1CFh; void *
0x18001b5f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b5fe  mov     rcx, [rsp+78h+pv]; pv
0x18001b603  call    cs:__imp_CoTaskMemFree
0x18001b60a  nop     dword ptr [rax+rax+00h]
0x18001b60f  jmp     loc_18001B534
0x18001b614  mov     rcx, [rsp+78h]; this
0x18001b619  lea     r8, aOnecorePrintsc_7; "onecore\\printscan\\AppxPackaging\\Mani"...
0x18001b620  mov     r9d, eax; char *
0x18001b623  mov     edx, 1D5h; void *
0x18001b628  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b62d  mov     rbx, [rsp+78h+pv]
0x18001b632  jmp     loc_18001B57B
```
