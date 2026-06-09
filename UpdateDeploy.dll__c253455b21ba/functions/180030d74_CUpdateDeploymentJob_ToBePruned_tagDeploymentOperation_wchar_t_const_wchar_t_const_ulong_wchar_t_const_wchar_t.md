# CUpdateDeploymentJob::ToBePruned(tagDeploymentOperation,wchar_t const *,wchar_t const *,ulong,wchar_t const *,wchar_t const *,bool,bool *,bool *)

- ea: `0x180030d74`
- end: `0x1800314a0`
- name: `?ToBePruned@CUpdateDeploymentJob@@AEBAJW4tagDeploymentOperation@@PEB_W1K11_NPEA_N3@Z`
- size: `1836`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800314a8`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x1800217c8`
- `0x180022790`
- `0x180030d74`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`

## string_xrefs

- `0x1800313e6`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031467`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031095`: `Deployment job Id %ws : update %ws.%d is not explicity deployable, prune it`
- `0x180031038`: `Deployment job Id %ws : update %ws.%d is out of scope, prune it`
- `0x18003113a`: `Deployment job Id %ws : update %ws.%d is not installable, prune it`
- `0x1800310e5`: `Deployment job Id %ws : update %ws.%d is a non top level bundle, prune it`
- `0x1800311d6`: `Deployment job Id %ws : update %ws.%d has no install blob, prune it`
- `0x18003119f`: `Deployment job Id %ws : update %ws.%d is not deployed for install or detection, prune it`
- `0x180031274`: `Deployment job Id %ws : update %ws.%d is not present, prune it`
- `0x180031237`: `Deployment job Id %ws : update %ws.%d has no payload, prune it`
- `0x180031324`: `Deployment job Id %ws : update %ws.%d has no uninstall blob, prune it`
- `0x1800312c4`: `Deployment job Id %ws : update %ws.%d is approved scan only, prune it`
- `0x18003135b`: `Deployment job Id %ws : update %ws.%d has is not pending reboot and cannot be reverted, prune it`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CUpdateDeploymentJob::ToBePruned(
        const struct _GUID *a1,
        int a2,
        _WORD *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        char a8,
        char *a9,
        char *a10)
{
  unsigned int v12; // ebx
  __int64 v13; // rdx
  char v14; // r15
  char v15; // bl
  int v16; // edi
  __int64 v17; // rdx
  char *v18; // r13
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // ecx
  int v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+30h] [rbp-D0h]
  __int64 v34; // [rsp+40h] [rbp-C0h]
  int v36; // [rsp+7Ch] [rbp-84h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  _BYTE v38[80]; // [rsp+B0h] [rbp-50h] BYREF
  void **v39; // [rsp+100h] [rbp+0h]
  void **v40; // [rsp+108h] [rbp+8h]
  void **v41; // [rsp+110h] [rbp+10h]
  char v42; // [rsp+118h] [rbp+18h]
  void *v43; // [rsp+120h] [rbp+20h] BYREF
  void *v44; // [rsp+128h] [rbp+28h] BYREF
  void *v45; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( !a3 || !*a3 )
  {
    v12 = -2147024809;
    v13 = 3656;
    goto LABEL_73;
  }
  if ( !a9 )
  {
    v12 = -2147467261;
    v13 = 3657;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)v12,
      v27);
    return v12;
  }
  if ( !a10 )
  {
    v12 = -2147467261;
    v13 = 3658;
    goto LABEL_73;
  }
  v14 = 0;
  v37 = *(_QWORD *)a1[44].Data4;
  v43 = 0;
  v45 = 0;
  v44 = 0;
  v39 = &v43;
  v40 = &v45;
  v41 = &v44;
  v15 = 1;
  v42 = 1;
  v16 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v43);
  if ( v16 >= 0 )
  {
    v16 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v45);
    if ( v16 < 0 )
    {
      v17 = 3674;
      goto LABEL_64;
    }
    v16 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v44);
    if ( v16 < 0 )
    {
      v17 = 3675;
      goto LABEL_64;
    }
    v36 = 0;
    do
    {
      v27 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v37 + 24LL))(
              v37,
              2,
              a1[50].Data1,
              3631);
      if ( v16 < 0 )
      {
        v17 = 3690;
        goto LABEL_64;
      }
      v27 = 1;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v37 + 24LL))(v37, 3, a1[50].Data1);
      if ( v16 < 0 )
      {
        v17 = 3702;
        goto LABEL_64;
      }
      HIDWORD(v34) = HIDWORD(a6);
      v27 = 1;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v37 + 24LL))(v37, 5, a1[50].Data1);
      if ( v16 < 0 )
      {
        v17 = 3714;
        goto LABEL_64;
      }
      ++v36;
    }
    while ( !v36 );
    v18 = a9;
    *a9 = 0;
    if ( !*((_DWORD *)v44 + 2) )
    {
      v19 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
      LODWORD(v34) = a5;
      WUTrace(0, 0, 0x1000000, 5, 0, L"Deployment job Id %ws : update %ws.%d is out of scope, prune it", v19, a4, v34);
      v14 = 1;
LABEL_53:
      if ( v44 )
      {
        v25 = *((_DWORD *)v45 + 2);
        if ( ((unsigned int)(v25 - 1) > 1 || *((_DWORD *)v43 + 34) != 2) && (v25 != 3 || *((_DWORD *)v43 + 37) != 2) )
          v15 = 0;
        *v18 = v15;
      }
      *a10 = v14;
      v16 = 0;
      goto LABEL_65;
    }
    if ( a8 )
    {
      if ( !*((_DWORD *)v43 + 23) )
      {
        LODWORD(v34) = a5;
        v28 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
        WUTrace(
          0,
          0,
          0x1000000,
          5,
          0,
          L"Deployment job Id %ws : update %ws.%d is not explicity deployable, prune it",
          v28,
          a4,
          v34);
LABEL_23:
        v14 = 1;
LABEL_52:
        v18 = a9;
        goto LABEL_53;
      }
    }
    else if ( *((_DWORD *)v43 + 130) )
    {
      LODWORD(v34) = a5;
      v29 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
      WUTrace(
        0,
        0,
        0x1000000,
        5,
        0,
        L"Deployment job Id %ws : update %ws.%d is a non top level bundle, prune it",
        v29,
        a4,
        v34);
      goto LABEL_23;
    }
    if ( a2 == 2 )
    {
      if ( (a1[49].Data4[0] & 1) == 0 && !*((_DWORD *)v44 + 4) )
      {
        v14 = 1;
        v23 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
        LODWORD(v34) = a5;
        WUTrace(0, 0, 0x1000000, 5, 0, L"Deployment job Id %ws : update %ws.%d is not present, prune it", v23, a4, v34);
      }
    }
    else if ( a2 != 4 )
    {
      if ( (a1[49].Data4[0] & 1) == 0 && *((_DWORD *)v44 + 3) != 2 )
      {
        v14 = 1;
        v20 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
        LODWORD(v34) = a5;
        WUTrace(
          0,
          0,
          0x1000000,
          5,
          0,
          L"Deployment job Id %ws : update %ws.%d is not installable, prune it",
          v20,
          a4,
          v34);
      }
      if ( a8 )
      {
        v21 = *((_DWORD *)v45 + 2);
        if ( ((v21 - 1) & 0xFFFFFFFC) != 0 || v21 == 3 )
        {
          v14 = 1;
          LODWORD(v34) = a5;
          v30 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
          WUTrace(
            0,
            0,
            0x1000000,
            5,
            0,
            L"Deployment job Id %ws : update %ws.%d is not deployed for install or detection, prune it",
            v30,
            a4,
            v34);
        }
      }
      else
      {
        if ( (*((_BYTE *)v43 + 140) & 1) == 0 )
        {
          v14 = 1;
          v22 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
          LODWORD(v34) = a5;
          WUTrace(
            0,
            0,
            0x1000000,
            5,
            0,
            L"Deployment job Id %ws : update %ws.%d has no install blob, prune it",
            v22,
            a4,
            v34);
        }
        if ( !*((_DWORD *)v43 + 118) || !*((_QWORD *)v43 + 60) )
        {
          v14 = 1;
          LODWORD(v34) = a5;
          v31 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
          WUTrace(
            0,
            0,
            0x1000000,
            5,
            0,
            L"Deployment job Id %ws : update %ws.%d has no payload, prune it",
            v31,
            a4,
            v34);
        }
      }
      goto LABEL_52;
    }
    if ( *((_DWORD *)v43 + 2) == 4 )
    {
      v14 = 1;
      v24 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
      LODWORD(v34) = a5;
      WUTrace(
        0,
        0,
        0x1000000,
        5,
        0,
        L"Deployment job Id %ws : update %ws.%d is approved scan only, prune it",
        v24,
        a4,
        v34);
    }
    if ( a8 || a2 != 2 )
    {
      if ( a2 == 4 && !*((_DWORD *)v44 + 5) )
      {
        v14 = 1;
        LODWORD(v34) = a5;
        v33 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
        WUTrace(
          0,
          0,
          0x1000000,
          5,
          0,
          L"Deployment job Id %ws : update %ws.%d has is not pending reboot and cannot be reverted, prune it",
          v33,
          a4,
          v34);
      }
    }
    else if ( (*((_BYTE *)v43 + 152) & 1) == 0 )
    {
      v14 = 1;
      LODWORD(v34) = a5;
      v32 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v38, a1 + 1);
      WUTrace(
        0,
        0,
        0x1000000,
        5,
        0,
        L"Deployment job Id %ws : update %ws.%d has no uninstall blob, prune it",
        v32,
        a4,
        v34);
    }
    goto LABEL_52;
  }
  v17 = 3673;
LABEL_64:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
    (const char *)(unsigned int)v16,
    v27);
LABEL_65:
  DPFreeDeployableUpdateData((char *)v43);
  DPFreeDeployableUpdateData((char *)v45);
  DPFreeDeployableUpdateData((char *)v44);
  if ( v44 )
  {
    operator delete(v44, (const struct std::nothrow_t *)0x288);
    v44 = 0;
  }
  if ( v45 )
  {
    operator delete(v45, (const struct std::nothrow_t *)0x288);
    v45 = 0;
  }
  if ( v43 )
    operator delete(v43, (const struct std::nothrow_t *)0x288);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180030d74  mov     [rsp-8+arg_8], rbx
0x180030d79  push    rbp
0x180030d7a  push    rsi
0x180030d7b  push    rdi
0x180030d7c  push    r12
0x180030d7e  push    r13
0x180030d80  push    r14
0x180030d82  push    r15
0x180030d84  lea     rbp, [rsp-40h]
0x180030d89  sub     rsp, 140h
0x180030d90  mov     rax, cs:__security_cookie
0x180030d97  xor     rax, rsp
0x180030d9a  mov     [rbp+70h+var_38], rax
0x180030d9e  mov     r12, r9
0x180030da1  mov     r13, r8
0x180030da4  mov     [rsp+170h+var_F8], edx
0x180030da8  mov     rsi, rcx
0x180030dab  mov     rax, [rbp+70h+arg_28]
0x180030db2  mov     [rbp+70h+var_E8], rax
0x180030db6  mov     rax, [rbp+70h+arg_30]
0x180030dbd  mov     [rbp+70h+var_D8], rax
0x180030dc1  mov     rax, [rbp+70h+arg_40]
0x180030dc8  mov     [rsp+170h+var_100], rax
0x180030dcd  mov     rcx, [rbp+70h+arg_48]
0x180030dd4  mov     [rbp+70h+var_D0], rcx
0x180030dd8  xor     r14d, r14d
0x180030ddb  test    r8, r8
0x180030dde  jz      loc_18003145A
0x180030de4  cmp     [r8], r14w
0x180030de8  jz      loc_18003145A
0x180030dee  test    rax, rax
0x180030df1  jnz     short loc_180030E02
0x180030df3  mov     ebx, 80004003h
0x180030df8  mov     edx, 0E49h
0x180030dfd  jmp     loc_180031464
0x180030e02  test    rcx, rcx
0x180030e05  jnz     short loc_180030E16
0x180030e07  mov     ebx, 80004003h
0x180030e0c  mov     edx, 0E4Ah
0x180030e11  jmp     loc_180031464
0x180030e16  mov     r15b, r14b
0x180030e19  mov     rax, [rsi+2C8h]
0x180030e20  mov     [rbp+70h+var_F0], rax
0x180030e24  mov     [rbp+70h+var_50], r14
0x180030e28  mov     [rbp+70h+var_40], r14
0x180030e2c  mov     [rbp+70h+var_48], r14
0x180030e30  lea     rax, [rbp+70h+var_50]
0x180030e34  mov     [rbp+70h+var_70], rax
0x180030e38  lea     rax, [rbp+70h+var_40]
0x180030e3c  mov     [rbp+70h+var_68], rax
0x180030e40  lea     rax, [rbp+70h+var_48]
0x180030e44  mov     [rbp+70h+var_60], rax
0x180030e48  mov     ebx, 1
0x180030e4d  mov     [rbp+70h+var_58], bl
0x180030e50  lea     rcx, [rbp+70h+var_50]
0x180030e54  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x180030e59  mov     edi, eax
0x180030e5b  test    eax, eax
0x180030e5d  jns     short loc_180030E69
0x180030e5f  mov     edx, 0E59h
0x180030e64  jmp     loc_1800313DF
0x180030e69  lea     rcx, [rbp+70h+var_40]
0x180030e6d  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x180030e72  mov     edi, eax
0x180030e74  test    eax, eax
0x180030e76  jns     short loc_180030E82
0x180030e78  mov     edx, 0E5Ah
0x180030e7d  jmp     loc_1800313DF
0x180030e82  lea     rcx, [rbp+70h+var_48]
0x180030e86  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x180030e8b  mov     edi, eax
0x180030e8d  test    eax, eax
0x180030e8f  jns     short loc_180030E9B
0x180030e91  mov     edx, 0E5Bh
0x180030e96  jmp     loc_1800313DF
0x180030e9b  mov     eax, r14d
0x180030e9e  mov     [rsp+170h+var_F4], eax
0x180030ea2  mov     r14d, [rbp+70h+arg_20]
0x180030ea9  imul    rcx, rax, 288h
0x180030eb0  mov     [rbp+70h+var_E0], rcx
0x180030eb4  add     rcx, [rbp+70h+var_50]
0x180030eb8  mov     r10, [rbp+70h+var_F0]
0x180030ebc  mov     rax, [r10]
0x180030ebf  mov     [rsp+170h+var_110], 0
0x180030ec7  mov     [rsp+170h+var_118], rcx
0x180030ecc  mov     [rsp+170h+var_120], 0
0x180030ed5  mov     [rsp+170h+var_128], 0
0x180030ede  mov     rcx, [rbp+70h+var_E8]
0x180030ee2  mov     [rsp+170h+var_130], rcx
0x180030ee7  mov     dword ptr [rsp+170h+var_138], r14d
0x180030eec  mov     [rsp+170h+var_140], r12
0x180030ef1  mov     [rsp+170h+var_148], r13
0x180030ef6  mov     [rsp+170h+var_150], 0; int
0x180030efe  mov     r9d, 0E2Fh
0x180030f04  mov     r8d, [rsi+320h]
0x180030f0b  mov     edx, 2
0x180030f10  mov     rcx, r10
0x180030f13  mov     rax, [rax+18h]
0x180030f17  call    _guard_dispatch_icall
0x180030f1c  mov     edi, eax
0x180030f1e  xor     r8d, r8d
0x180030f21  test    eax, eax
0x180030f23  js      loc_1800313DA
0x180030f29  mov     rcx, [rbp+70h+var_E0]
0x180030f2d  add     rcx, [rbp+70h+var_40]
0x180030f31  mov     r10, [rbp+70h+var_F0]
0x180030f35  mov     rax, [r10]
0x180030f38  mov     [rsp+170h+var_110], r8d
0x180030f3d  mov     [rsp+170h+var_118], rcx
0x180030f42  mov     [rsp+170h+var_120], r8
0x180030f47  mov     [rsp+170h+var_128], r8
0x180030f4c  mov     rcx, [rbp+70h+var_E8]
0x180030f50  mov     [rsp+170h+var_130], rcx
0x180030f55  mov     dword ptr [rsp+170h+var_138], r14d
0x180030f5a  mov     [rsp+170h+var_140], r12
0x180030f5f  mov     [rsp+170h+var_148], r13
0x180030f64  mov     [rsp+170h+var_150], ebx
0x180030f68  xor     r9d, r9d
0x180030f6b  mov     r8d, [rsi+320h]
0x180030f72  lea     edx, [r9+3]
0x180030f76  mov     rcx, r10
0x180030f79  mov     rax, [rax+18h]
0x180030f7d  call    _guard_dispatch_icall
0x180030f82  mov     edi, eax
0x180030f84  xor     r8d, r8d
0x180030f87  test    eax, eax
0x180030f89  js      loc_1800313D3
0x180030f8f  mov     rcx, [rbp+70h+var_E0]
0x180030f93  add     rcx, [rbp+70h+var_48]
0x180030f97  mov     r10, [rbp+70h+var_F0]
0x180030f9b  mov     rax, [r10]
0x180030f9e  mov     [rsp+170h+var_110], r8d
0x180030fa3  mov     [rsp+170h+var_118], rcx
0x180030fa8  mov     [rsp+170h+var_120], r8
0x180030fad  mov     rcx, [rbp+70h+var_D8]
0x180030fb1  mov     [rsp+170h+var_128], rcx
0x180030fb6  mov     rcx, [rbp+70h+var_E8]
0x180030fba  mov     [rsp+170h+var_130], rcx
0x180030fbf  mov     dword ptr [rsp+170h+var_138], r14d
0x180030fc4  mov     [rsp+170h+var_140], r12
0x180030fc9  mov     [rsp+170h+var_148], r13
0x180030fce  mov     [rsp+170h+var_150], ebx
0x180030fd2  xor     r9d, r9d
0x180030fd5  mov     r8d, [rsi+320h]
0x180030fdc  lea     edx, [r9+5]
0x180030fe0  mov     rcx, r10
0x180030fe3  mov     rax, [rax+18h]
0x180030fe7  call    _guard_dispatch_icall
0x180030fec  mov     edi, eax
0x180030fee  test    eax, eax
0x180030ff0  js      loc_1800313CC
0x180030ff6  mov     eax, [rsp+170h+var_F4]
0x180030ffa  add     eax, ebx
0x180030ffc  mov     [rsp+170h+var_F4], eax
0x180031000  cmp     eax, ebx
0x180031002  jb      loc_180030EA9
0x180031008  mov     r13, [rsp+170h+var_100]
0x18003100d  xor     edi, edi
0x18003100f  mov     [r13+0], dil
0x180031013  mov     rax, [rbp+70h+var_48]
0x180031017  cmp     [rax+8], edi
0x18003101a  jnz     short loc_180031064
0x18003101c  lea     rdx, [rsi+10h]; struct _GUID *
0x180031020  lea     rcx, [rbp+70h+var_C0]; this
0x180031024  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031029  mov     dword ptr [rsp+170h+var_130], r14d
0x18003102e  mov     [rsp+170h+var_138], r12
0x180031033  mov     [rsp+170h+var_140], rax
0x180031038  lea     rax, aDeploymentJobI_23; "Deployment job Id %ws : update %ws.%d i"...
0x18003103f  mov     [rsp+170h+var_148], rax
0x180031044  mov     qword ptr [rsp+170h+var_150], rdi
0x180031049  xor     edx, edx
0x18003104b  xor     ecx, ecx
0x18003104d  lea     r9d, [rdi+5]
0x180031051  mov     r8d, 1000000h
0x180031057  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003105c  mov     r15b, bl
0x18003105f  jmp     loc_180031387
0x180031064  mov     r13b, [rbp+70h+arg_38]
0x18003106b  mov     rax, [rbp+70h+var_50]
0x18003106f  test    r13b, r13b
0x180031072  jz      short loc_1800310C1
0x180031074  cmp     [rax+5Ch], edi
0x180031077  jnz     short loc_1800310EE
0x180031079  lea     rdx, [rsi+10h]; struct _GUID *
0x18003107d  lea     rcx, [rbp+70h+var_C0]; this
0x180031081  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031086  mov     dword ptr [rsp+170h+var_130], r14d
0x18003108b  mov     [rsp+170h+var_138], r12
0x180031090  mov     [rsp+170h+var_140], rax
0x180031095  lea     rax, aDeploymentJobI_76; "Deployment job Id %ws : update %ws.%d i"...
0x18003109c  mov     [rsp+170h+var_148], rax
0x1800310a1  mov     qword ptr [rsp+170h+var_150], rdi
0x1800310a6  xor     edx, edx
0x1800310a8  xor     ecx, ecx
0x1800310aa  lea     r9d, [rdx+5]
0x1800310ae  mov     r8d, 1000000h
0x1800310b4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800310b9  mov     r15b, bl
0x1800310bc  jmp     loc_180031382
0x1800310c1  cmp     [rax+208h], edi
0x1800310c7  jbe     short loc_1800310EE
0x1800310c9  lea     rdx, [rsi+10h]; struct _GUID *
0x1800310cd  lea     rcx, [rbp+70h+var_C0]; this
0x1800310d1  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800310d6  mov     dword ptr [rsp+170h+var_130], r14d
0x1800310db  mov     [rsp+170h+var_138], r12
0x1800310e0  mov     [rsp+170h+var_140], rax
0x1800310e5  lea     rax, aDeploymentJobI_66; "Deployment job Id %ws : update %ws.%d i"...
0x1800310ec  jmp     short loc_18003109C
0x1800310ee  mov     edi, 1000000h
0x1800310f3  mov     eax, [rsp+170h+var_F8]
0x1800310f7  cmp     eax, 2
0x1800310fa  jz      loc_180031243
0x180031100  cmp     eax, 4
0x180031103  jz      loc_18003129B
0x180031109  test    [rsi+318h], bl
0x18003110f  jnz     short loc_180031161
0x180031111  mov     rax, [rbp+70h+var_48]
0x180031115  cmp     dword ptr [rax+0Ch], 2
0x180031119  jz      short loc_180031161
0x18003111b  mov     r15b, bl
0x18003111e  lea     rdx, [rsi+10h]; struct _GUID *
0x180031122  lea     rcx, [rbp+70h+var_C0]; this
0x180031126  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003112b  mov     dword ptr [rsp+170h+var_130], r14d
0x180031130  mov     [rsp+170h+var_138], r12
0x180031135  mov     [rsp+170h+var_140], rax
0x18003113a  lea     rax, aDeploymentJobI_7; "Deployment job Id %ws : update %ws.%d i"...
0x180031141  mov     [rsp+170h+var_148], rax
0x180031146  mov     qword ptr [rsp+170h+var_150], 0
0x18003114f  mov     r9d, 5
0x180031155  mov     r8d, edi
0x180031158  xor     edx, edx
0x18003115a  xor     ecx, ecx
0x18003115c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180031161  test    r13b, r13b
0x180031164  jz      short loc_1800311AB
0x180031166  mov     rax, [rbp+70h+var_40]
0x18003116a  mov     ecx, [rax+8]
0x18003116d  lea     eax, [rcx-1]
0x180031170  test    eax, 0FFFFFFFCh
0x180031175  jnz     short loc_180031180
0x180031177  cmp     ecx, 3
0x18003117a  jnz     loc_180031382
0x180031180  mov     r15b, bl
0x180031183  lea     rdx, [rsi+10h]; struct _GUID *
0x180031187  lea     rcx, [rbp+70h+var_C0]; this
0x18003118b  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031190  mov     dword ptr [rsp+170h+var_130], r14d
0x180031195  mov     [rsp+170h+var_138], r12
0x18003119a  mov     [rsp+170h+var_140], rax
0x18003119f  lea     rax, aDeploymentJobI_50; "Deployment job Id %ws : update %ws.%d i"...
0x1800311a6  jmp     loc_180031362
0x1800311ab  mov     rax, [rbp+70h+var_50]
0x1800311af  test    [rax+8Ch], bl
0x1800311b5  jnz     short loc_1800311FD
0x1800311b7  mov     r15b, bl
0x1800311ba  lea     rdx, [rsi+10h]; struct _GUID *
0x1800311be  lea     rcx, [rbp+70h+var_C0]; this
0x1800311c2  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800311c7  mov     dword ptr [rsp+170h+var_130], r14d
0x1800311cc  mov     [rsp+170h+var_138], r12
0x1800311d1  mov     [rsp+170h+var_140], rax
0x1800311d6  lea     rax, aDeploymentJobI_79; "Deployment job Id %ws : update %ws.%d h"...
0x1800311dd  mov     [rsp+170h+var_148], rax
0x1800311e2  mov     qword ptr [rsp+170h+var_150], 0
0x1800311eb  mov     r9d, 5
0x1800311f1  mov     r8d, edi
0x1800311f4  xor     edx, edx
0x1800311f6  xor     ecx, ecx
0x1800311f8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800311fd  mov     rax, [rbp+70h+var_50]
0x180031201  cmp     dword ptr [rax+1D8h], 0
0x180031208  jbe     short loc_180031218
0x18003120a  cmp     qword ptr [rax+1E0h], 0
0x180031212  jnz     loc_180031382
0x180031218  mov     r15b, bl
0x18003121b  lea     rdx, [rsi+10h]; struct _GUID *
0x18003121f  lea     rcx, [rbp+70h+var_C0]; this
0x180031223  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031228  mov     dword ptr [rsp+170h+var_130], r14d
0x18003122d  mov     [rsp+170h+var_138], r12
0x180031232  mov     [rsp+170h+var_140], rax
0x180031237  lea     rax, aDeploymentJobI_52; "Deployment job Id %ws : update %ws.%d h"...
0x18003123e  jmp     loc_180031362
0x180031243  test    [rsi+318h], bl
0x180031249  jnz     short loc_18003129B
0x18003124b  mov     rax, [rbp+70h+var_48]
0x18003124f  cmp     dword ptr [rax+10h], 0
0x180031253  jnz     short loc_18003129B
0x180031255  mov     r15b, bl
0x180031258  lea     rdx, [rsi+10h]; struct _GUID *
0x18003125c  lea     rcx, [rbp+70h+var_C0]; this
0x180031260  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031265  mov     dword ptr [rsp+170h+var_130], r14d
0x18003126a  mov     [rsp+170h+var_138], r12
0x18003126f  mov     [rsp+170h+var_140], rax
0x180031274  lea     rax, aDeploymentJobI_24; "Deployment job Id %ws : update %ws.%d i"...
0x18003127b  mov     [rsp+170h+var_148], rax
  ... truncated ...
```
