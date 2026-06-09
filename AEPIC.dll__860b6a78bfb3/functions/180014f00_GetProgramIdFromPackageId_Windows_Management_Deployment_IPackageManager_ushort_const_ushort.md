# GetProgramIdFromPackageId(Windows::Management::Deployment::IPackageManager *,ushort const *,ushort *)

- ea: `0x180014f00`
- end: `0x180015298`
- name: `?GetProgramIdFromPackageId@@YAJPEAUIPackageManager@Deployment@Management@Windows@@PEBGPEAG@Z`
- size: `920`
- prototype: `__int64 __fastcall(struct Windows::Management::Deployment::IPackageManager *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001cc80`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000cb74`
- `0x18001082c`
- `0x180014f00`
- `0x1800295dc`
- `0x180037ac0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001515f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001515f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001507f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001507f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f92`

## pseudocode

```c
__int64 __fastcall GetProgramIdFromPackageId(
        struct Windows::Management::Deployment::IPackageManager *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v6; // rdx
  int v7; // eax
  int v8; // ebx
  HSTRING v9; // rbx
  __int64 (__fastcall *v10)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, __int64 *); // rdi
  int v11; // eax
  int v12; // edi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  const char *v15; // r9
  __int64 v16; // r8
  PCWSTR StringRawBuffer; // rax
  LCID v18; // eax
  int v19; // eax
  const wchar_t *v20; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v35[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v36[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v37[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v30 = 0;
  v27 = 0;
  v29 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v28 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  string = 0;
  v7 = WindowsCreateString(a2, v6, &string);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed initialize [%#x]";
    v16 = 258;
    goto LABEL_34;
  }
  v9 = string;
  v32 = string;
  WindowsDeleteString(0);
  v10 = *(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, __int64 *))(*(_QWORD *)a1 + 136LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v11 = v10(a1, v9, &v30);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v30 )
    {
      if ( v11 != -2147467261 )
        AslLogCallPrintf(1, "GetProgramIdFromPackageId", 272, "Failed to find package [%#x]", v11);
      v8 = v12;
      goto LABEL_35;
    }
LABEL_29:
    v8 = -2147467261;
    goto LABEL_35;
  }
  v13 = v30;
  if ( !v30 )
    goto LABEL_29;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v8 = v14(v13, &v27);
  if ( v8 < 0 )
  {
    if ( v27 )
    {
LABEL_27:
      v24 = v8;
      AslLogCallPrintf(1, "GetProgramIdFromPackageId", 285, "Failed to get id [%#x]", v24);
      goto LABEL_35;
    }
LABEL_26:
    v8 = -2147467261;
    goto LABEL_27;
  }
  if ( !v27 )
    goto LABEL_26;
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 48LL))(v27, &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed to get name [%#x]";
    v16 = 296;
LABEL_34:
    LODWORD(v22) = v7;
    AslLogCallPrintf(1, "GetProgramIdFromPackageId", v16, v15, v22);
    goto LABEL_35;
  }
  v35[0] = (unsigned __int16 *)WindowsGetStringRawBuffer(v28, 0);
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 80LL))(v27, &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed to get publisher [%#x]";
    v16 = 308;
    goto LABEL_34;
  }
  v35[1] = (unsigned __int16 *)WindowsGetStringRawBuffer(v28, 0);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v29);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed to get version [%#x]";
    v16 = 320;
    goto LABEL_34;
  }
  v26 = HIWORD(v29);
  v25 = WORD2(v29);
  v23 = WORD1(v29);
  v7 = StringCchPrintfW(v36, 0x104u, L"%d.%d.%d.%d", (unsigned __int16)v29, v23, v25, v26);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed make version [%#x]";
    v16 = 333;
    goto LABEL_34;
  }
  v35[2] = v36;
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 72LL))(v27, &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed to get language [%#x]";
    v16 = 345;
    goto LABEL_34;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v28, 0);
  if ( !StringRawBuffer || !*StringRawBuffer )
    StringRawBuffer = L"en-us";
  v18 = LocaleNameToLCID(StringRawBuffer, 0);
  v19 = StringCchPrintfW(v37, 0x104u, L"%d", v18);
  v20 = L"1033";
  if ( v19 >= 0 )
    v20 = v37;
  v35[3] = (unsigned __int16 *)v20;
  v7 = AeComputeProgramIdentityHash(v35, a3);
  v8 = v7;
  if ( v7 < 0 )
  {
    v15 = "Failed to generate program id [%#x]";
    v16 = 376;
    goto LABEL_34;
  }
LABEL_35:
  Windows::Internal::String::~String((Windows::Internal::String *)&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014f00  mov     [rsp-8+arg_18], rbx
0x180014f05  push    rbp
0x180014f06  push    rsi
0x180014f07  push    rdi
0x180014f08  push    r14
0x180014f0a  push    r15
0x180014f0c  lea     rbp, [rsp-3D0h]
0x180014f14  sub     rsp, 4D0h
0x180014f1b  mov     rax, cs:__security_cookie
0x180014f22  xor     rax, rsp
0x180014f25  mov     [rbp+3F0h+var_30], rax
0x180014f2c  mov     r14, r8
0x180014f2f  mov     rax, rdx
0x180014f32  mov     rsi, rcx
0x180014f35  xor     r15d, r15d
0x180014f38  mov     [rsp+4F0h+var_498], r15
0x180014f3d  mov     [rsp+4F0h+var_4B0], r15
0x180014f42  mov     [rsp+4F0h+var_4A0], r15
0x180014f47  mov     [rsp+4F0h+var_478], r15
0x180014f4c  mov     [rsp+4F0h+var_480], r15
0x180014f51  mov     [rsp+4F0h+var_488], r15
0x180014f56  mov     [rsp+4F0h+var_4A8], r15
0x180014f5b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014f5f  inc     rdx; length
0x180014f62  cmp     [rax+rdx*2], r15w
0x180014f67  jnz     short loc_180014F5F
0x180014f69  mov     [rsp+4F0h+string], r15
0x180014f6e  lea     r8, [rsp+4F0h+string]; string
0x180014f73  mov     rcx, rax; sourceString
0x180014f76  call    cs:__imp_WindowsCreateString
0x180014f7c  mov     ebx, eax
0x180014f7e  test    eax, eax
0x180014f80  js      loc_180015217
0x180014f86  mov     rbx, [rsp+4F0h+string]
0x180014f8b  mov     [rsp+4F0h+var_488], rbx
0x180014f90  xor     ecx, ecx; string
0x180014f92  call    cs:__imp_WindowsDeleteString
0x180014f98  mov     rax, [rsi]
0x180014f9b  mov     rdi, [rax+88h]
0x180014fa2  lea     rcx, [rsp+4F0h+var_498]
0x180014fa7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014fac  lea     r8, [rsp+4F0h+var_498]
0x180014fb1  mov     rdx, rbx
0x180014fb4  mov     rcx, rsi
0x180014fb7  mov     rax, rdi
0x180014fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fbf  mov     edi, eax
0x180014fc1  test    eax, eax
0x180014fc3  js      loc_1800151DA
0x180014fc9  mov     rbx, [rsp+4F0h+var_498]
0x180014fce  test    rbx, rbx
0x180014fd1  jz      loc_1800151E1
0x180014fd7  mov     rax, [rbx]
0x180014fda  mov     rdi, [rax+30h]
0x180014fde  lea     rcx, [rsp+4F0h+var_4B0]
0x180014fe3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014fe8  lea     rdx, [rsp+4F0h+var_4B0]
0x180014fed  mov     rcx, rbx
0x180014ff0  mov     rax, rdi
0x180014ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff8  mov     ebx, eax
0x180014ffa  test    eax, eax
0x180014ffc  js      loc_1800151BB
0x180015002  mov     rcx, [rsp+4F0h+var_4B0]
0x180015007  test    rcx, rcx
0x18001500a  jz      loc_1800151C2
0x180015010  mov     rax, [rcx]
0x180015013  lea     rdx, [rsp+4F0h+var_4A8]
0x180015018  mov     rax, [rax+30h]
0x18001501c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015021  mov     ebx, eax
0x180015023  test    eax, eax
0x180015025  jns     short loc_180015039
0x180015027  lea     r9, aFailedToGetNam; "Failed to get name [%#x]"
0x18001502e  mov     r8d, 128h
0x180015034  jmp     loc_180015224
0x180015039  xor     edx, edx; length
0x18001503b  mov     rcx, [rsp+4F0h+var_4A8]; string
0x180015040  call    cs:__imp_WindowsGetStringRawBuffer
0x180015046  mov     [rbp+3F0h+var_470], rax
0x18001504a  mov     rcx, [rsp+4F0h+var_4B0]
0x18001504f  mov     rax, [rcx]
0x180015052  lea     rdx, [rsp+4F0h+var_4A8]
0x180015057  mov     rax, [rax+50h]
0x18001505b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015060  mov     ebx, eax
0x180015062  test    eax, eax
0x180015064  jns     short loc_180015078
0x180015066  lea     r9, aFailedToGetPub; "Failed to get publisher [%#x]"
0x18001506d  mov     r8d, 134h
0x180015073  jmp     loc_180015224
0x180015078  xor     edx, edx; length
0x18001507a  mov     rcx, [rsp+4F0h+var_4A8]; string
0x18001507f  call    cs:__imp_WindowsGetStringRawBuffer
0x180015085  mov     [rbp+3F0h+var_468], rax
0x180015089  mov     rcx, [rsp+4F0h+var_4B0]
0x18001508e  mov     rax, [rcx]
0x180015091  lea     rdx, [rsp+4F0h+var_4A0]
0x180015096  mov     rax, [rax+38h]
0x18001509a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001509f  mov     ebx, eax
0x1800150a1  test    eax, eax
0x1800150a3  jns     short loc_1800150B7
0x1800150a5  lea     r9, aFailedToGetVer; "Failed to get version [%#x]"
0x1800150ac  mov     r8d, 140h
0x1800150b2  jmp     loc_180015224
0x1800150b7  movzx   eax, word ptr [rsp+4F0h+var_4A0+6]
0x1800150bc  movzx   ecx, word ptr [rsp+4F0h+var_4A0+4]
0x1800150c1  movzx   edx, word ptr [rsp+4F0h+var_4A0+2]
0x1800150c6  movzx   r9d, word ptr [rsp+4F0h+var_4A0]
0x1800150cc  mov     [rsp+4F0h+var_4C0], eax
0x1800150d0  mov     [rsp+4F0h+var_4C8], ecx
0x1800150d4  mov     dword ptr [rsp+4F0h+var_4D0], edx
0x1800150d8  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800150df  mov     edi, 104h
0x1800150e4  mov     edx, edi; unsigned __int64
0x1800150e6  lea     rcx, [rbp+3F0h+var_450]; unsigned __int16 *
0x1800150ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800150ef  mov     ebx, eax
0x1800150f1  test    eax, eax
0x1800150f3  jns     short loc_180015105
0x1800150f5  lea     r9, aFailedMakeVers; "Failed make version [%#x]"
0x1800150fc  lea     r8d, [rdi+49h]
0x180015100  jmp     loc_180015224
0x180015105  lea     rax, [rbp+3F0h+var_450]
0x180015109  mov     [rbp+3F0h+var_460], rax
0x18001510d  mov     rcx, [rsp+4F0h+var_4B0]
0x180015112  mov     rax, [rcx]
0x180015115  lea     rdx, [rsp+4F0h+var_4A8]
0x18001511a  mov     rax, [rax+48h]
0x18001511e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015123  mov     ebx, eax
0x180015125  test    eax, eax
0x180015127  jns     short loc_18001513B
0x180015129  lea     r9, aFailedToGetLan; "Failed to get language [%#x]"
0x180015130  mov     r8d, 159h
0x180015136  jmp     loc_180015224
0x18001513b  xor     edx, edx; length
0x18001513d  mov     rcx, [rsp+4F0h+var_4A8]; string
0x180015142  call    cs:__imp_WindowsGetStringRawBuffer
0x180015148  test    rax, rax
0x18001514b  jz      short loc_180015153
0x18001514d  cmp     [rax], r15w
0x180015151  jnz     short loc_18001515A
0x180015153  lea     rax, aEnUs; "en-us"
0x18001515a  xor     edx, edx; dwFlags
0x18001515c  mov     rcx, rax; lpName
0x18001515f  call    cs:__imp_LocaleNameToLCID
0x180015165  mov     r9d, eax
0x180015168  lea     r8, aD; "%d"
0x18001516f  mov     rdx, rdi; unsigned __int64
0x180015172  lea     rcx, [rbp+3F0h+var_240]; unsigned __int16 *
0x180015179  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001517e  lea     rcx, a1033; "1033"
0x180015185  lea     rdx, [rbp+3F0h+var_240]
0x18001518c  test    eax, eax
0x18001518e  cmovns  rcx, rdx
0x180015192  mov     [rbp+3F0h+var_458], rcx
0x180015196  mov     rdx, r14
0x180015199  lea     rcx, [rbp+3F0h+var_470]
0x18001519d  call    AeComputeProgramIdentityHash
0x1800151a2  mov     ebx, eax
0x1800151a4  test    eax, eax
0x1800151a6  jns     loc_18001523A
0x1800151ac  lea     r9, aFailedToGenera; "Failed to generate program id [%#x]"
0x1800151b3  mov     r8d, 178h
0x1800151b9  jmp     short loc_180015224
0x1800151bb  cmp     [rsp+4F0h+var_4B0], r15
0x1800151c0  jnz     short loc_1800151C7
0x1800151c2  mov     ebx, 80004003h
0x1800151c7  mov     dword ptr [rsp+4F0h+var_4D0], ebx
0x1800151cb  lea     r9, aFailedToGetIdX; "Failed to get id [%#x]"
0x1800151d2  mov     r8d, 11Dh
0x1800151d8  jmp     short loc_180015228
0x1800151da  cmp     [rsp+4F0h+var_498], r15
0x1800151df  jnz     short loc_1800151E8
0x1800151e1  mov     ebx, 80004003h
0x1800151e6  jmp     short loc_18001523A
0x1800151e8  mov     ebx, 80004003h
0x1800151ed  cmp     edi, ebx
0x1800151ef  jz      short loc_180015213
0x1800151f1  mov     dword ptr [rsp+4F0h+var_4D0], edi
0x1800151f5  lea     r9, aFailedToFindPa; "Failed to find package [%#x]"
0x1800151fc  mov     r8d, 110h
0x180015202  lea     rdx, aGetprogramidfr; "GetProgramIdFromPackageId"
0x180015209  mov     ecx, 1
0x18001520e  call    AslLogCallPrintf
0x180015213  mov     ebx, edi
0x180015215  jmp     short loc_18001523A
0x180015217  lea     r9, aFailedInitiali; "Failed initialize [%#x]"
0x18001521e  mov     r8d, 102h
0x180015224  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x180015228  lea     rdx, aGetprogramidfr; "GetProgramIdFromPackageId"
0x18001522f  mov     ecx, 1
0x180015234  call    AslLogCallPrintf
0x180015239  nop
0x18001523a  lea     rcx, [rsp+4F0h+var_488]; this
0x18001523f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180015244  nop
0x180015245  lea     rcx, [rsp+4F0h+var_480]
0x18001524a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001524f  nop
0x180015250  lea     rcx, [rsp+4F0h+var_478]
0x180015255  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001525a  nop
0x18001525b  lea     rcx, [rsp+4F0h+var_4B0]
0x180015260  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015265  nop
0x180015266  lea     rcx, [rsp+4F0h+var_498]
0x18001526b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015270  mov     eax, ebx
0x180015272  mov     rcx, [rbp+3F0h+var_30]
0x180015279  xor     rcx, rsp; StackCookie
0x18001527c  call    __security_check_cookie
0x180015281  mov     rbx, [rsp+4F0h+arg_18]
0x180015289  add     rsp, 4D0h
0x180015290  pop     r15
0x180015292  pop     r14
0x180015294  pop     rdi
0x180015295  pop     rsi
0x180015296  pop     rbp
0x180015297  retn
```
