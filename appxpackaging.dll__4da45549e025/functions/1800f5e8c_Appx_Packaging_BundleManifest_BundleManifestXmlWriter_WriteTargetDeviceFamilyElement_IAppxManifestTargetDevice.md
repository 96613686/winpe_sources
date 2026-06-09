# Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteTargetDeviceFamilyElement(IAppxManifestTargetDeviceFamily *)

- ea: `0x1800f5e8c`
- end: `0x1800f62e6`
- name: `?WriteTargetDeviceFamilyElement@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEAUIAppxManifestTargetDeviceFamily@@@Z`
- size: `1114`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *__hidden this, struct IAppxManifestTargetDeviceFamily *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f4a44`

## callees

- `0x1800133fc`
- `0x180050e7c`
- `0x18006021c`
- `0x18007b024`
- `0x18007d95c`
- `0x18007da44`
- `0x18007df1c`
- `0x1800992c4`
- `0x1800f4710`
- `0x1800f5e8c`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62b4`

## string_xrefs

- `0x1800f617a`: `http://schemas.microsoft.com/appx/2018/bundle`
- `0x1800f61d9`: `http://schemas.microsoft.com/appx/2018/bundle`
- `0x1800f6243`: `http://schemas.microsoft.com/appx/2018/bundle`
- `0x1800f5ed6`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5f15`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5fce`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f601a`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f6075`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f60cf`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f6121`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f6197`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f61f7`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f6261`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteTargetDeviceFamilyElement(
        Appx::Packaging::Xml::MXWriter **this,
        struct IAppxManifestTargetDeviceFamily *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  Appx::Packaging::Xml::MXAttributes *v6; // rsi
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  unsigned __int64 v11; // rdx
  Appx::Packaging::Xml::MXAttributes *v12; // rbx
  int v13; // eax
  unsigned int v14; // r14d
  unsigned __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  unsigned __int64 v18; // rdx
  int v19; // eax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  Appx::Packaging::Xml::MXAttributes *v22; // rdi
  int v23; // eax
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  int ElementName; // eax
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  const unsigned __int16 *v30; // r14
  int started; // eax
  unsigned int v32; // r15d
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdx
  int v36; // eax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  unsigned __int16 **v44; // [rsp+20h] [rbp-30h]
  unsigned __int16 **v45; // [rsp+20h] [rbp-30h]
  int v46; // [rsp+20h] [rbp-30h]
  int v47; // [rsp+20h] [rbp-30h]
  int v48; // [rsp+20h] [rbp-30h]
  Appx::Packaging *v49; // [rsp+30h] [rbp-20h] BYREF
  Appx::Packaging *v50; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v51[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  Appx::Packaging::Xml::MXAttributes *v54; // [rsp+98h] [rbp+48h] BYREF

  v51[1] = (unsigned __int16 *)-2LL;
  v54 = 0;
  v4 = Appx::Packaging::Xml::MXAttributes::Create(&v54);
  v5 = v4;
  v6 = v54;
  if ( v4 >= 0 )
  {
    pv = 0;
    v7 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamily *, LPVOID *))a2->lpVtbl->GetName)(a2, &pv);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 630;
LABEL_5:
      v9 = (unsigned int)v7;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)v9,
        (int)v44);
LABEL_7:
      CoTaskMemFree(pv);
      goto LABEL_33;
    }
    if ( !pv )
    {
      v5 = -2147024882;
      v9 = 2147942414LL;
      v8 = 631;
      goto LABEL_6;
    }
    v7 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"Name", (const unsigned __int16 *)pv);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 636;
      goto LABEL_5;
    }
    v49 = 0;
    v7 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamily *, Appx::Packaging **))a2->lpVtbl->GetMinVersion)(
           a2,
           &v49);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = 639;
      goto LABEL_5;
    }
    v54 = 0;
    v10 = Appx::Packaging::ConvertVersionToString(v49, 4u, 4u, (unsigned int)&v54, v44);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x281,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v10,
        (int)v45);
      operator delete(v54, v11);
      goto LABEL_7;
    }
    v12 = v54;
    v13 = Appx::Packaging::Xml::MXAttributes::AddAttribute(
            v6,
            &LocaleName,
            L"MinVersion",
            (const unsigned __int16 *)v54);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v13,
        (int)v45);
      operator delete(v12, v15);
LABEL_18:
      CoTaskMemFree(pv);
      v5 = v14;
      goto LABEL_33;
    }
    v50 = 0;
    v16 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamily *, Appx::Packaging **))a2->lpVtbl->GetMaxVersionTested)(
            a2,
            &v50);
    v17 = v16;
    if ( v16 >= 0 )
    {
      v54 = 0;
      v19 = Appx::Packaging::ConvertVersionToString(v50, 4u, 4u, (unsigned int)&v54, v45);
      v17 = v19;
      if ( v19 >= 0 )
      {
        v22 = v54;
        v23 = Appx::Packaging::Xml::MXAttributes::AddAttribute(
                v6,
                &LocaleName,
                L"MaxVersionTested",
                (const unsigned __int16 *)v54);
        v14 = v23;
        if ( v23 >= 0 )
        {
          v51[0] = 0;
          v54 = 0;
          ElementName = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(
                          (Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)this,
                          L"http://schemas.microsoft.com/appx/2018/bundle",
                          L"b4",
                          L"TargetDeviceFamily",
                          (const unsigned __int16 **)v51,
                          (unsigned __int16 **)&v54);
          v14 = ElementName;
          if ( ElementName >= 0 )
          {
            v30 = v51[0];
            started = Appx::Packaging::Xml::MXWriter::StartElement(
                        this[1],
                        L"http://schemas.microsoft.com/appx/2018/bundle",
                        v51[0],
                        v51[0],
                        v6);
            v32 = started;
            if ( started < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x294,
                (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
                (const char *)(unsigned int)started,
                v48);
              operator delete(v54, v33);
              operator delete(v22, v34);
              operator delete(v12, v35);
              CoTaskMemFree(pv);
              v5 = v32;
              goto LABEL_33;
            }
            v36 = Appx::Packaging::Xml::MXWriter::EndElement(
                    this[1],
                    L"http://schemas.microsoft.com/appx/2018/bundle",
                    v30,
                    v30);
            v14 = v36;
            if ( v36 >= 0 )
            {
              operator delete(v54, v37);
              operator delete(v22, v41);
              operator delete(v12, v42);
              CoTaskMemFree(pv);
              v5 = 0;
              goto LABEL_33;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x295,
              (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
              (const char *)(unsigned int)v36,
              v48);
            operator delete(v54, v38);
            operator delete(v22, v39);
            operator delete(v12, v40);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x292,
              (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
              (const char *)(unsigned int)ElementName,
              v47);
            operator delete(v54, v27);
            operator delete(v22, v28);
            operator delete(v12, v29);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28E,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
            (const char *)(unsigned int)v23,
            v46);
          operator delete(v22, v24);
          operator delete(v12, v25);
        }
        goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v19,
        v46);
      operator delete(v54, v20);
      operator delete(v12, v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v16,
        (int)v45);
      operator delete(v12, v18);
    }
    CoTaskMemFree(pv);
    v5 = v17;
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x273,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
    (const char *)(unsigned int)v4,
    (int)v44);
LABEL_33:
  Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(v6);
  return v5;
}

```

## disassembly

```asm
0x1800f5e8c  mov     rax, rsp
0x1800f5e8f  push    rbp
0x1800f5e90  push    rdi
0x1800f5e91  push    r13
0x1800f5e93  push    r14
0x1800f5e95  push    r15
0x1800f5e97  mov     rbp, rsp
0x1800f5e9a  sub     rsp, 50h
0x1800f5e9e  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1800f5ea6  mov     [rax+8], rbx
0x1800f5eaa  mov     [rax+10h], rsi
0x1800f5eae  mov     rdi, rdx
0x1800f5eb1  mov     r13, rcx
0x1800f5eb4  mov     [rbp+arg_18], 0
0x1800f5ebc  lea     rcx, [rbp+arg_18]; struct Appx::Packaging::Xml::MXAttributes **
0x1800f5ec0  call    ?Create@MXAttributes@Xml@Packaging@Appx@@SAJPEAPEAV1234@@Z; Appx::Packaging::Xml::MXAttributes::Create(Appx::Packaging::Xml::MXAttributes * *)
0x1800f5ec5  mov     ebx, eax
0x1800f5ec7  mov     rsi, [rbp+arg_18]
0x1800f5ecb  test    eax, eax
0x1800f5ecd  jns     short loc_1800F5EEC
0x1800f5ecf  mov     rcx, [rbp+28h]; this
0x1800f5ed3  mov     r9d, eax; char *
0x1800f5ed6  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5edd  mov     edx, 273h; void *
0x1800f5ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5ee7  jmp     loc_1800F62C2
0x1800f5eec  mov     [rbp+pv], 0
0x1800f5ef4  mov     rax, [rdi]
0x1800f5ef7  lea     rdx, [rbp+pv]
0x1800f5efb  mov     rcx, rdi
0x1800f5efe  mov     rax, [rax+18h]
0x1800f5f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5f07  mov     ebx, eax
0x1800f5f09  test    eax, eax
0x1800f5f0b  jns     short loc_1800F5F3A
0x1800f5f0d  mov     edx, 276h; void *
0x1800f5f12  mov     r9d, eax; char *
0x1800f5f15  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5f1c  mov     rcx, [rbp+28h]; this
0x1800f5f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5f25  mov     rcx, [rbp+pv]; pv
0x1800f5f29  call    cs:__imp_CoTaskMemFree
0x1800f5f30  nop     dword ptr [rax+rax+00h]
0x1800f5f35  jmp     loc_1800F62C2
0x1800f5f3a  mov     r9, [rbp+pv]; unsigned __int16 *
0x1800f5f3e  test    r9, r9
0x1800f5f41  jnz     short loc_1800F5F52
0x1800f5f43  mov     ebx, 8007000Eh
0x1800f5f48  mov     r9d, ebx
0x1800f5f4b  mov     edx, 277h
0x1800f5f50  jmp     short loc_1800F5F15
0x1800f5f52  lea     r8, ?Name@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Name"
0x1800f5f59  lea     rdx, LocaleName; unsigned __int16 *
0x1800f5f60  mov     rcx, rsi; this
0x1800f5f63  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f5f68  mov     ebx, eax
0x1800f5f6a  test    eax, eax
0x1800f5f6c  jns     short loc_1800F5F75
0x1800f5f6e  mov     edx, 27Ch
0x1800f5f73  jmp     short loc_1800F5F12
0x1800f5f75  mov     [rbp+var_20], 0
0x1800f5f7d  mov     rax, [rdi]
0x1800f5f80  lea     rdx, [rbp+var_20]
0x1800f5f84  mov     rcx, rdi
0x1800f5f87  mov     rax, [rax+20h]
0x1800f5f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5f90  mov     ebx, eax
0x1800f5f92  test    eax, eax
0x1800f5f94  jns     short loc_1800F5FA0
0x1800f5f96  mov     edx, 27Fh
0x1800f5f9b  jmp     loc_1800F5F12
0x1800f5fa0  mov     [rbp+arg_18], 0
0x1800f5fa8  lea     r9, [rbp+arg_18]; unsigned int
0x1800f5fac  mov     r15d, 4
0x1800f5fb2  mov     r8d, r15d; unsigned int
0x1800f5fb5  mov     edx, r15d; unsigned __int64
0x1800f5fb8  mov     rcx, [rbp+var_20]; this
0x1800f5fbc  call    ?ConvertVersionToString@Packaging@Appx@@YAJ_KKKPEAPEAG@Z; Appx::Packaging::ConvertVersionToString(unsigned __int64,ulong,ulong,ushort * *)
0x1800f5fc1  mov     ebx, eax
0x1800f5fc3  test    eax, eax
0x1800f5fc5  jns     short loc_1800F5FEF
0x1800f5fc7  mov     rcx, [rbp+28h]; this
0x1800f5fcb  mov     r9d, eax; char *
0x1800f5fce  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5fd5  mov     edx, 281h; void *
0x1800f5fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5fdf  nop
0x1800f5fe0  mov     rcx, [rbp+arg_18]; void *
0x1800f5fe4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5fe9  nop
0x1800f5fea  jmp     loc_1800F5F25
0x1800f5fef  mov     rbx, [rbp+arg_18]
0x1800f5ff3  mov     r9, rbx; unsigned __int16 *
0x1800f5ff6  lea     r8, ?MinVersion@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "MinVersion"
0x1800f5ffd  lea     rdx, LocaleName; unsigned __int16 *
0x1800f6004  mov     rcx, rsi; this
0x1800f6007  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f600c  mov     r14d, eax
0x1800f600f  test    eax, eax
0x1800f6011  jns     short loc_1800F604D
0x1800f6013  mov     rcx, [rbp+28h]; this
0x1800f6017  mov     r9d, eax; char *
0x1800f601a  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f6021  mov     edx, 285h; void *
0x1800f6026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f602b  nop
0x1800f602c  mov     rcx, rbx; void *
0x1800f602f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f6034  nop
0x1800f6035  mov     rcx, [rbp+pv]; pv
0x1800f6039  call    cs:__imp_CoTaskMemFree
0x1800f6040  nop     dword ptr [rax+rax+00h]
0x1800f6045  mov     ebx, r14d
0x1800f6048  jmp     loc_1800F62C2
0x1800f604d  mov     [rbp+var_18], 0
0x1800f6055  mov     rax, [rdi]
0x1800f6058  lea     rdx, [rbp+var_18]
0x1800f605c  mov     rcx, rdi
0x1800f605f  mov     rax, [rax+28h]
0x1800f6063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6068  mov     edi, eax
0x1800f606a  test    eax, eax
0x1800f606c  jns     short loc_1800F60A7
0x1800f606e  mov     rcx, [rbp+28h]; this
0x1800f6072  mov     r9d, eax; char *
0x1800f6075  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f607c  mov     edx, 288h; void *
0x1800f6081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6086  nop
0x1800f6087  mov     rcx, rbx; void *
0x1800f608a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f608f  nop
0x1800f6090  mov     rcx, [rbp+pv]; pv
0x1800f6094  call    cs:__imp_CoTaskMemFree
0x1800f609b  nop     dword ptr [rax+rax+00h]
0x1800f60a0  mov     ebx, edi
0x1800f60a2  jmp     loc_1800F62C2
0x1800f60a7  mov     [rbp+arg_18], 0
0x1800f60af  lea     r9, [rbp+arg_18]; unsigned int
0x1800f60b3  mov     r8d, r15d; unsigned int
0x1800f60b6  mov     edx, r15d; unsigned __int64
0x1800f60b9  mov     rcx, [rbp+var_18]; this
0x1800f60bd  call    ?ConvertVersionToString@Packaging@Appx@@YAJ_KKKPEAPEAG@Z; Appx::Packaging::ConvertVersionToString(unsigned __int64,ulong,ulong,ushort * *)
0x1800f60c2  mov     edi, eax
0x1800f60c4  test    eax, eax
0x1800f60c6  jns     short loc_1800F60F6
0x1800f60c8  mov     rcx, [rbp+28h]; this
0x1800f60cc  mov     r9d, eax; char *
0x1800f60cf  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f60d6  mov     edx, 28Ah; void *
0x1800f60db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f60e0  nop
0x1800f60e1  mov     rcx, [rbp+arg_18]; void *
0x1800f60e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f60ea  nop
0x1800f60eb  mov     rcx, rbx; void *
0x1800f60ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f60f3  nop
0x1800f60f4  jmp     short loc_1800F6090
0x1800f60f6  mov     rdi, [rbp+arg_18]
0x1800f60fa  mov     r9, rdi; unsigned __int16 *
0x1800f60fd  lea     r8, ?MaxVersionTested@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "MaxVersionTested"
0x1800f6104  lea     rdx, LocaleName; unsigned __int16 *
0x1800f610b  mov     rcx, rsi; this
0x1800f610e  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f6113  mov     r14d, eax
0x1800f6116  test    eax, eax
0x1800f6118  jns     short loc_1800F614A
0x1800f611a  mov     rcx, [rbp+28h]; this
0x1800f611e  mov     r9d, eax; char *
0x1800f6121  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f6128  mov     edx, 28Eh; void *
0x1800f612d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6132  nop
0x1800f6133  mov     rcx, rdi; void *
0x1800f6136  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f613b  nop
0x1800f613c  mov     rcx, rbx; void *
0x1800f613f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f6144  nop
0x1800f6145  jmp     loc_1800F6035
0x1800f614a  mov     [rbp+var_10], 0
0x1800f6152  mov     [rbp+arg_18], 0
0x1800f615a  lea     rax, [rbp+arg_18]
0x1800f615e  mov     [rsp+50h+var_28], rax; unsigned __int16 **
0x1800f6163  lea     rax, [rbp+var_10]
0x1800f6167  mov     [rsp+50h+var_30], rax; int
0x1800f616c  lea     r9, ?TargetDeviceFamily@ElementNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "TargetDeviceFamily"
0x1800f6173  lea     r8, ?Namespace2018Alias@BundleManifest@Packaging@Appx@@3QBGB; "b4"
0x1800f617a  lea     rdx, ?Namespace2018@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2018/"...
0x1800f6181  mov     rcx, r13; this
0x1800f6184  call    ?GetElementName@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEBG00PEAPEBGPEAPEAG@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(ushort const *,ushort const *,ushort const *,ushort const * *,ushort * *)
0x1800f6189  mov     r14d, eax
0x1800f618c  test    eax, eax
0x1800f618e  jns     short loc_1800F61CA
0x1800f6190  mov     rcx, [rbp+28h]; this
0x1800f6194  mov     r9d, eax; char *
0x1800f6197  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f619e  mov     edx, 292h; void *
0x1800f61a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f61a8  nop
0x1800f61a9  mov     rcx, [rbp+arg_18]; void *
0x1800f61ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f61b2  nop
0x1800f61b3  mov     rcx, rdi; void *
0x1800f61b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f61bb  nop
0x1800f61bc  mov     rcx, rbx; void *
0x1800f61bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f61c4  nop
0x1800f61c5  jmp     loc_1800F6035
0x1800f61ca  mov     r14, [rbp+var_10]
0x1800f61ce  mov     [rsp+50h+var_30], rsi; int
0x1800f61d3  mov     r9, r14; unsigned __int16 *
0x1800f61d6  mov     r8, r14; unsigned __int16 *
0x1800f61d9  lea     rdx, ?Namespace2018@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2018/"...
0x1800f61e0  mov     rcx, [r13+8]; this
0x1800f61e4  call    ?StartElement@MXWriter@Xml@Packaging@Appx@@QEAAJPEBG00AEBVMXAttributes@234@@Z; Appx::Packaging::Xml::MXWriter::StartElement(ushort const *,ushort const *,ushort const *,Appx::Packaging::Xml::MXAttributes const &)
0x1800f61e9  mov     r15d, eax
0x1800f61ec  test    eax, eax
0x1800f61ee  jns     short loc_1800F623D
0x1800f61f0  mov     rcx, [rbp+28h]; this
0x1800f61f4  mov     r9d, eax; char *
0x1800f61f7  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f61fe  mov     edx, 294h; void *
0x1800f6203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6208  nop
0x1800f6209  mov     rcx, [rbp+arg_18]; void *
0x1800f620d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f6212  nop
0x1800f6213  mov     rcx, rdi; void *
0x1800f6216  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f621b  nop
0x1800f621c  mov     rcx, rbx; void *
0x1800f621f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f6224  nop
0x1800f6225  mov     rcx, [rbp+pv]; pv
0x1800f6229  call    cs:__imp_CoTaskMemFree
0x1800f6230  nop     dword ptr [rax+rax+00h]
0x1800f6235  mov     ebx, r15d
0x1800f6238  jmp     loc_1800F62C2
0x1800f623d  mov     r9, r14; unsigned __int16 *
0x1800f6240  mov     r8, r14; unsigned __int16 *
0x1800f6243  lea     rdx, ?Namespace2018@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2018/"...
0x1800f624a  mov     rcx, [r13+8]; this
0x1800f624e  call    ?EndElement@MXWriter@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXWriter::EndElement(ushort const *,ushort const *,ushort const *)
0x1800f6253  mov     r14d, eax
0x1800f6256  test    eax, eax
0x1800f6258  jns     short loc_1800F6294
0x1800f625a  mov     rcx, [rbp+28h]; this
0x1800f625e  mov     r9d, eax; char *
0x1800f6261  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f6268  mov     edx, 295h; void *
0x1800f626d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6272  nop
0x1800f6273  mov     rcx, [rbp+arg_18]; void *
0x1800f6277  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f627c  nop
0x1800f627d  mov     rcx, rdi; void *
0x1800f6280  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f6285  nop
0x1800f6286  mov     rcx, rbx; void *
0x1800f6289  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f628e  nop
0x1800f628f  jmp     loc_1800F6035
0x1800f6294  mov     rcx, [rbp+arg_18]; void *
0x1800f6298  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f629d  nop
0x1800f629e  mov     rcx, rdi; void *
0x1800f62a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f62a6  nop
0x1800f62a7  mov     rcx, rbx; void *
0x1800f62aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f62af  nop
0x1800f62b0  mov     rcx, [rbp+pv]; pv
0x1800f62b4  call    cs:__imp_CoTaskMemFree
0x1800f62bb  nop     dword ptr [rax+rax+00h]
0x1800f62c0  xor     ebx, ebx
0x1800f62c2  mov     rcx, rsi; void *
0x1800f62c5  call    ??$AutoPtrDeallocate@VMXAttributes@Xml@Packaging@Appx@@@Common@@YAXPEAVMXAttributes@Xml@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(Appx::Packaging::Xml::MXAttributes *)
0x1800f62ca  mov     eax, ebx
0x1800f62cc  lea     r11, [rsp+50h+var_s0]
0x1800f62d1  mov     rbx, [r11+30h]
0x1800f62d5  mov     rsi, [r11+38h]
0x1800f62d9  mov     rsp, r11
0x1800f62dc  pop     r15
0x1800f62de  pop     r14
0x1800f62e0  pop     r13
0x1800f62e2  pop     rdi
0x1800f62e3  pop     rbp
0x1800f62e4  retn
```
