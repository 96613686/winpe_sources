# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)

- ea: `0x180043258`
- end: `0x1800434de`
- name: `?GetPackageFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `646`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fb8c`
- `0x180043770`
- `0x180043aa0`
- `0x180043f80`
- `0x1800457f0`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x180013be0`
- `0x18003e754`
- `0x180043258`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800434b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  char v9; // r8
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING, __int64); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned __int64 v17; // r14
  unsigned int i; // esi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  int v24; // [rsp+20h] [rbp-40h]
  int v25[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+38h] [rbp-28h] BYREF
  __int64 v27; // [rsp+40h] [rbp-20h] BYREF
  __int64 v28; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v31; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+48h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+58h] BYREF

  v32 = a2;
  if ( *(_QWORD *)(a1 + 368) )
  {
    v28 = 0;
    v6 = *(_QWORD *)(a1 + 384);
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v8 = v7(v6, &v28);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72F,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v8,
        v24);
LABEL_29:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      return v5;
    }
    string = 0;
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
            (Microsoft::WRL::Wrappers::HString *)&string,
            &v32,
            v9);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x732,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v10,
        v24);
LABEL_7:
      WindowsDeleteString(string);
LABEL_28:
      string = 0;
      goto LABEL_29;
    }
    *(_QWORD *)v25 = 0;
    v11 = *(_QWORD *)(a1 + 368);
    v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v11 + 424LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    v13 = v12(v11, v28, string, 1);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v31 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v25 + 56LL))(*(_QWORD *)v25, &v31);
      v5 = v13;
      if ( v13 >= 0 )
      {
        v16 = v31;
        if ( v31 )
        {
          v17 = 0;
          v27 = 0;
          for ( i = 0; i < v16; ++i )
          {
            v26 = 0;
            v19 = *(_QWORD *)v25;
            v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v25 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v21 = v20(v19, i, &v26);
            v5 = v21;
            if ( v21 < 0 )
            {
              v22 = 1859;
              goto LABEL_25;
            }
            v29 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v26 + 104LL))(v26, &v29);
            v5 = v21;
            if ( v21 < 0 )
            {
              v22 = 1862;
LABEL_25:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v22,
                (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
                (const char *)(unsigned int)v21,
                (int)v25);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              goto LABEL_12;
            }
            if ( v29 >= v17 )
            {
              v17 = v29;
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(&v27, &v26);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v16 = v31;
          }
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(a3, &v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
          WindowsDeleteString(string);
          v5 = 0;
          goto LABEL_28;
        }
        v5 = -2147467259;
        v15 = 2147500037LL;
        v14 = 1852;
        goto LABEL_11;
      }
      v14 = 1851;
    }
    else
    {
      v14 = 1848;
    }
    v15 = (unsigned int)v13;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)v15,
      (int)v25);
LABEL_12:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    goto LABEL_7;
  }
  v5 = -2147467259;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72C,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
    (const char *)0x80004005LL,
    v24);
  return v5;
}

```

## disassembly

```asm
0x180043258  mov     [rsp-38h+arg_8], rdx
0x18004325d  push    rbp
0x18004325e  push    rbx
0x18004325f  push    rsi
0x180043260  push    rdi
0x180043261  push    r12
0x180043263  push    r14
0x180043265  push    r15
0x180043267  mov     rbp, rsp
0x18004326a  sub     rsp, 60h
0x18004326e  mov     r15, r8
0x180043271  mov     rsi, rcx
0x180043274  xor     r12d, r12d
0x180043277  cmp     [rcx+170h], r12
0x18004327e  jnz     short loc_1800432A2
0x180043280  mov     rcx, [rbp+38h]; this
0x180043284  mov     ebx, 80004005h
0x180043289  mov     r9d, ebx; char *
0x18004328c  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043293  mov     edx, 72Ch; void *
0x180043298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004329d  jmp     loc_1800434CD
0x1800432a2  mov     [rbp+var_18], r12
0x1800432a6  mov     rdi, [rcx+180h]
0x1800432ad  mov     rax, [rdi]
0x1800432b0  mov     rbx, [rax+68h]
0x1800432b4  lea     rcx, [rbp+var_18]
0x1800432b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800432bd  lea     rdx, [rbp+var_18]
0x1800432c1  mov     rcx, rdi
0x1800432c4  mov     rax, rbx
0x1800432c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432cc  mov     ebx, eax
0x1800432ce  test    eax, eax
0x1800432d0  jns     short loc_1800432EF
0x1800432d2  mov     rcx, [rbp+38h]; this
0x1800432d6  mov     r9d, eax; char *
0x1800432d9  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800432e0  mov     edx, 72Fh; void *
0x1800432e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800432ea  jmp     loc_1800434C4
0x1800432ef  mov     [rbp+string], r12
0x1800432f3  lea     rdx, [rbp+arg_8]
0x1800432f7  lea     rcx, [rbp+string]
0x1800432fb  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180043300  mov     ebx, eax
0x180043302  test    eax, eax
0x180043304  jns     short loc_18004332E
0x180043306  mov     rcx, [rbp+38h]; this
0x18004330a  mov     r9d, eax; char *
0x18004330d  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043314  mov     edx, 732h; void *
0x180043319  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004331e  nop
0x18004331f  mov     rcx, [rbp+string]; string
0x180043323  call    cs:__imp_WindowsDeleteString
0x180043329  jmp     loc_1800434C0
0x18004332e  mov     qword ptr [rbp+var_30], r12
0x180043332  mov     rdi, [rsi+170h]
0x180043339  mov     rax, [rdi]
0x18004333c  mov     rbx, [rax+1A8h]
0x180043343  lea     rcx, [rbp+var_30]
0x180043347  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004334c  lea     rax, [rbp+var_30]
0x180043350  mov     qword ptr [rsp+60h+var_40], rax; int
0x180043355  mov     r9d, 1
0x18004335b  mov     r8, [rbp+string]
0x18004335f  mov     rdx, [rbp+var_18]
0x180043363  mov     rcx, rdi
0x180043366  mov     rax, rbx
0x180043369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004336e  mov     ebx, eax
0x180043370  test    eax, eax
0x180043372  jns     short loc_180043398
0x180043374  mov     edx, 738h; void *
0x180043379  mov     r9d, eax; char *
0x18004337c  mov     rcx, [rbp+38h]; this
0x180043380  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004338c  nop
0x18004338d  lea     rcx, [rbp+var_30]
0x180043391  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043396  jmp     short loc_18004331F
0x180043398  mov     [rbp+arg_0], r12d
0x18004339c  mov     rcx, qword ptr [rbp+var_30]
0x1800433a0  mov     rax, [rcx]
0x1800433a3  lea     rdx, [rbp+arg_0]
0x1800433a7  mov     rax, [rax+38h]
0x1800433ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433b0  mov     ebx, eax
0x1800433b2  test    eax, eax
0x1800433b4  jns     short loc_1800433BD
0x1800433b6  mov     edx, 73Bh
0x1800433bb  jmp     short loc_180043379
0x1800433bd  mov     eax, [rbp+arg_0]
0x1800433c0  test    eax, eax
0x1800433c2  jnz     short loc_1800433D3
0x1800433c4  mov     ebx, 80004005h
0x1800433c9  mov     r9d, ebx
0x1800433cc  mov     edx, 73Ch
0x1800433d1  jmp     short loc_18004337C
0x1800433d3  mov     r14, r12
0x1800433d6  mov     [rbp+var_20], r12
0x1800433da  mov     esi, r12d
0x1800433dd  cmp     esi, eax
0x1800433df  jnb     loc_180043492
0x1800433e5  mov     [rbp+var_28], r12
0x1800433e9  mov     rdi, qword ptr [rbp+var_30]
0x1800433ed  mov     rax, [rdi]
0x1800433f0  mov     rbx, [rax+30h]
0x1800433f4  lea     rcx, [rbp+var_28]
0x1800433f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800433fd  lea     r8, [rbp+var_28]
0x180043401  mov     edx, esi
0x180043403  mov     rcx, rdi
0x180043406  mov     rax, rbx
0x180043409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004340e  mov     ebx, eax
0x180043410  test    eax, eax
0x180043412  js      short loc_18004348B
0x180043414  mov     [rbp+var_10], r12
0x180043418  mov     rcx, [rbp+var_28]
0x18004341c  mov     rax, [rcx]
0x18004341f  lea     rdx, [rbp+var_10]
0x180043423  mov     rax, [rax+68h]
0x180043427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004342c  mov     ebx, eax
0x18004342e  test    eax, eax
0x180043430  js      short loc_18004345A
0x180043432  cmp     [rbp+var_10], r14
0x180043436  jb      short loc_18004344A
0x180043438  mov     r14, [rbp+var_10]
0x18004343c  lea     rdx, [rbp+var_28]
0x180043440  lea     rcx, [rbp+var_20]
0x180043444  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x180043449  nop
0x18004344a  lea     rcx, [rbp+var_28]
0x18004344e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043453  inc     esi
0x180043455  mov     eax, [rbp+arg_0]
0x180043458  jmp     short loc_1800433DD
0x18004345a  mov     edx, 746h; void *
0x18004345f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043466  mov     r9d, eax; char *
0x180043469  mov     rcx, [rbp+38h]; this
0x18004346d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043472  nop
0x180043473  lea     rcx, [rbp+var_28]
0x180043477  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004347c  nop
0x18004347d  lea     rcx, [rbp+var_20]
0x180043481  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043486  jmp     loc_18004338D
0x18004348b  mov     edx, 743h
0x180043490  jmp     short loc_18004345F
0x180043492  lea     rdx, [rbp+var_20]
0x180043496  mov     rcx, r15
0x180043499  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x18004349e  nop
0x18004349f  lea     rcx, [rbp+var_20]
0x1800434a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800434a8  nop
0x1800434a9  lea     rcx, [rbp+var_30]
0x1800434ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800434b2  nop
0x1800434b3  mov     rcx, [rbp+string]; string
0x1800434b7  call    cs:__imp_WindowsDeleteString
0x1800434bd  mov     ebx, r12d
0x1800434c0  mov     [rbp+string], r12
0x1800434c4  lea     rcx, [rbp+var_18]
0x1800434c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800434cd  mov     eax, ebx
0x1800434cf  add     rsp, 60h
0x1800434d3  pop     r15
0x1800434d5  pop     r14
0x1800434d7  pop     r12
0x1800434d9  pop     rdi
0x1800434da  pop     rsi
0x1800434db  pop     rbx
0x1800434dc  pop     rbp
0x1800434dd  retn
```
