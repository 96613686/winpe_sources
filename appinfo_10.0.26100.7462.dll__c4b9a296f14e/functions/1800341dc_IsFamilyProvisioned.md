# IsFamilyProvisioned

- ea: `0x1800341dc`
- end: `0x180034562`
- name: `IsFamilyProvisioned`
- size: `902`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032ad0`

## callees

- `0x180007c78`
- `0x180025c04`
- `0x18002ce2c`
- `0x180034150`
- `0x1800341dc`
- `0x180044a20`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034428`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034449`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034449`

## string_xrefs

- `0x180034251`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003428c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800342f9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003433f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034522`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034540`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall IsFamilyProvisioned(LPCWCH lpString2, _BYTE *a2)
{
  __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64 *); // rdi
  int v20; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  _BYTE v27[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-31h] BYREF
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h] BYREF
  __int64 v32; // [rsp+58h] [rbp-11h] BYREF
  UINT32 length; // [rsp+60h] [rbp-9h] BYREF
  __int64 v34; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v37; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v34 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.PackageManager",
    0x2Du,
    0x2Cu);
  v4 = v37;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v5 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager9>(v4, &v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E2,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    goto LABEL_32;
  }
  v28 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v34 + 48LL))(
         v34,
         &v28);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E5,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    goto LABEL_5;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
  v30 = 0;
  v10 = **v28;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v11 = v10(v9, &GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d, &v30);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E8,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
LABEL_5:
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v8)[2])(v8);
    }
    goto LABEL_32;
  }
  v29 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v29);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 6635;
    goto LABEL_12;
  }
  v27[0] = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v27);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 6638;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
LABEL_13:
    v14 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_9;
  }
  v32 = 0;
  while ( 1 )
  {
    if ( !v27[0] )
      goto LABEL_27;
    v15 = v29;
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v17 = v16(v15, &v32);
    v6 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F4,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v17,
        bIgnoreCase);
      goto LABEL_37;
    }
    v18 = v32;
    v31 = 0;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v20 = v19(v18, &v31);
    v6 = v20;
    if ( v20 < 0 )
    {
      v22 = 6647;
      goto LABEL_35;
    }
    string = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL))(v31, &string);
    v6 = v20;
    if ( v20 < 0 )
    {
      v22 = 6650;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
LABEL_37:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      goto LABEL_13;
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( CompareStringOrdinal(StringRawBuffer, length, lpString2, -1, 1) == 2 )
      break;
    v20 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 64LL))(v29, v27);
    v6 = v20;
    if ( v20 < 0 )
    {
      v22 = 6661;
      goto LABEL_35;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  }
  *a2 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
LABEL_27:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
  if ( v28 )
  {
    v28 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
  }
  v6 = 0;
LABEL_32:
  v37 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  return v6;
}

```

## disassembly

```asm
0x1800341dc  mov     [rsp-8+arg_10], rbx
0x1800341e1  push    rbp
0x1800341e2  push    rsi
0x1800341e3  push    rdi
0x1800341e4  push    r14
0x1800341e6  push    r15
0x1800341e8  lea     rbp, [rsp-37h]
0x1800341ed  sub     rsp, 0A0h
0x1800341f4  mov     rax, cs:__security_cookie
0x1800341fb  xor     rax, rsp
0x1800341fe  mov     [rbp+57h+var_28], rax
0x180034202  xor     r15d, r15d
0x180034205  mov     rsi, rdx
0x180034208  mov     r14, rcx
0x18003420b  mov     [rdx], r15b
0x18003420e  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180034215  mov     [rbp+57h+var_58], r15
0x180034219  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18003421d  mov     [rbp+57h+var_30], r15
0x180034221  lea     r9d, [r15+2Ch]; unsigned int
0x180034225  lea     r8d, [r15+2Dh]; unsigned int
0x180034229  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003422e  mov     rbx, [rbp+57h+var_30]
0x180034232  lea     rcx, [rbp+57h+var_58]
0x180034236  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003423b  lea     rdx, [rbp+57h+var_58]
0x18003423f  mov     rcx, rbx
0x180034242  call    ??$ActivateInstance@UIPackageManager9@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager9@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager9>(HSTRING__ *,Windows::Management::Deployment::IPackageManager9 * *)
0x180034247  mov     ebx, eax
0x180034249  test    eax, eax
0x18003424b  jns     short loc_18003426A
0x18003424d  mov     rcx, [rbp+5Fh]; this
0x180034251  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034258  mov     r9d, eax; char *
0x18003425b  mov     edx, 19E2h; void *
0x180034260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034265  jmp     loc_1800344DF
0x18003426a  mov     rcx, [rbp+57h+var_58]
0x18003426e  lea     rdx, [rbp+57h+var_88]
0x180034272  mov     [rbp+57h+var_88], r15
0x180034276  mov     rax, [rcx]
0x180034279  mov     rax, [rax+30h]
0x18003427d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034282  mov     ebx, eax
0x180034284  test    eax, eax
0x180034286  jns     short loc_1800342C2
0x180034288  mov     rcx, [rbp+5Fh]; this
0x18003428c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034293  mov     r9d, eax; char *
0x180034296  mov     edx, 19E5h; void *
0x18003429b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342a0  mov     rcx, [rbp+57h+var_88]
0x1800342a4  test    rcx, rcx
0x1800342a7  jz      loc_1800344DF
0x1800342ad  mov     [rbp+57h+var_88], r15
0x1800342b1  mov     rax, [rcx]
0x1800342b4  mov     rax, [rax+10h]
0x1800342b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342bd  jmp     loc_1800344DF
0x1800342c2  mov     rbx, [rbp+57h+var_88]
0x1800342c6  lea     rcx, [rbp+57h+var_78]
0x1800342ca  mov     [rbp+57h+var_78], r15
0x1800342ce  mov     rax, [rbx]
0x1800342d1  mov     rdi, [rax]
0x1800342d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800342d9  lea     r8, [rbp+57h+var_78]
0x1800342dd  mov     rcx, rbx
0x1800342e0  lea     rdx, _GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d
0x1800342e7  mov     rax, rdi
0x1800342ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ef  mov     ebx, eax
0x1800342f1  test    eax, eax
0x1800342f3  jns     short loc_180034318
0x1800342f5  mov     rcx, [rbp+5Fh]; this
0x1800342f9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034300  mov     r9d, eax; char *
0x180034303  mov     edx, 19E8h; void *
0x180034308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003430d  lea     rcx, [rbp+57h+var_78]
0x180034311  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034316  jmp     short loc_1800342A0
0x180034318  mov     rcx, [rbp+57h+var_78]
0x18003431c  lea     rdx, [rbp+57h+var_80]
0x180034320  mov     [rbp+57h+var_80], r15
0x180034324  mov     rax, [rcx]
0x180034327  mov     rax, [rax+30h]
0x18003432b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034330  mov     ebx, eax
0x180034332  test    eax, eax
0x180034334  jns     short loc_180034369
0x180034336  mov     edx, 19EBh; void *
0x18003433b  mov     rcx, [rbp+5Fh]; this
0x18003433f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034346  mov     r9d, eax; char *
0x180034349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003434e  mov     rcx, [rbp+57h+var_80]
0x180034352  test    rcx, rcx
0x180034355  jz      short loc_18003430D
0x180034357  mov     [rbp+57h+var_80], r15
0x18003435b  mov     rax, [rcx]
0x18003435e  mov     rax, [rax+10h]
0x180034362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034367  jmp     short loc_18003430D
0x180034369  mov     rcx, [rbp+57h+var_80]
0x18003436d  lea     rdx, [rbp+57h+var_90]
0x180034371  mov     [rbp+57h+var_90], r15b
0x180034375  mov     rax, [rcx]
0x180034378  mov     rax, [rax+38h]
0x18003437c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034381  mov     ebx, eax
0x180034383  test    eax, eax
0x180034385  jns     short loc_18003438E
0x180034387  mov     edx, 19EEh
0x18003438c  jmp     short loc_18003433B
0x18003438e  mov     [rbp+57h+var_68], r15
0x180034392  cmp     [rbp+57h+var_90], r15b
0x180034396  jz      loc_180034498
0x18003439c  mov     rbx, [rbp+57h+var_80]
0x1800343a0  lea     rcx, [rbp+57h+var_68]
0x1800343a4  mov     rax, [rbx]
0x1800343a7  mov     rdi, [rax+30h]
0x1800343ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800343b0  lea     rdx, [rbp+57h+var_68]
0x1800343b4  mov     rcx, rbx
0x1800343b7  mov     rax, rdi
0x1800343ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343bf  mov     ebx, eax
0x1800343c1  test    eax, eax
0x1800343c3  js      loc_18003453C
0x1800343c9  mov     rbx, [rbp+57h+var_68]
0x1800343cd  lea     rcx, [rbp+57h+var_70]
0x1800343d1  mov     [rbp+57h+var_70], r15
0x1800343d5  mov     rax, [rbx]
0x1800343d8  mov     rdi, [rax+30h]
0x1800343dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800343e1  lea     rdx, [rbp+57h+var_70]
0x1800343e5  mov     rcx, rbx
0x1800343e8  mov     rax, rdi
0x1800343eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343f0  mov     ebx, eax
0x1800343f2  test    eax, eax
0x1800343f4  js      loc_180034519
0x1800343fa  mov     rcx, [rbp+57h+var_70]
0x1800343fe  lea     rdx, [rbp+57h+string]
0x180034402  mov     [rbp+57h+string], r15
0x180034406  mov     rax, [rcx]
0x180034409  mov     rax, [rax+68h]
0x18003440d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034412  mov     ebx, eax
0x180034414  test    eax, eax
0x180034416  js      loc_180034512
0x18003441c  mov     rcx, [rbp+57h+string]; string
0x180034420  lea     rdx, [rbp+57h+length]; length
0x180034424  mov     [rbp+57h+length], r15d
0x180034428  call    cs:__imp_WindowsGetStringRawBuffer
0x18003442f  nop     dword ptr [rax+rax+00h]
0x180034434  mov     edx, [rbp+57h+length]; cchCount1
0x180034437  or      r9d, 0FFFFFFFFh; cchCount2
0x18003443b  mov     rcx, rax; lpString1
0x18003443e  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x180034446  mov     r8, r14; lpString2
0x180034449  call    cs:__imp_CompareStringOrdinal
0x180034450  nop     dword ptr [rax+rax+00h]
0x180034455  cmp     eax, 2
0x180034458  jz      short loc_18003448C
0x18003445a  mov     rcx, [rbp+57h+var_80]
0x18003445e  lea     rdx, [rbp+57h+var_90]
0x180034462  mov     rax, [rcx]
0x180034465  mov     rax, [rax+40h]
0x180034469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003446e  mov     ebx, eax
0x180034470  test    eax, eax
0x180034472  js      short loc_180034482
0x180034474  lea     rcx, [rbp+57h+var_70]
0x180034478  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003447d  jmp     loc_180034392
0x180034482  mov     edx, 1A05h
0x180034487  jmp     loc_18003451E
0x18003448c  lea     rcx, [rbp+57h+var_70]
0x180034490  mov     byte ptr [rsi], 1
0x180034493  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034498  lea     rcx, [rbp+57h+var_68]
0x18003449c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800344a1  mov     rcx, [rbp+57h+var_80]
0x1800344a5  test    rcx, rcx
0x1800344a8  jz      short loc_1800344BA
0x1800344aa  mov     [rbp+57h+var_80], r15
0x1800344ae  mov     rax, [rcx]
0x1800344b1  mov     rax, [rax+10h]
0x1800344b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344ba  lea     rcx, [rbp+57h+var_78]
0x1800344be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800344c3  mov     rcx, [rbp+57h+var_88]
0x1800344c7  test    rcx, rcx
0x1800344ca  jz      short loc_1800344DC
0x1800344cc  mov     [rbp+57h+var_88], r15
0x1800344d0  mov     rax, [rcx]
0x1800344d3  mov     rax, [rax+10h]
0x1800344d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344dc  mov     ebx, r15d
0x1800344df  lea     rcx, [rbp+57h+var_58]
0x1800344e3  mov     [rbp+57h+var_30], r15
0x1800344e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800344ec  mov     eax, ebx
0x1800344ee  mov     rcx, [rbp+57h+var_28]
0x1800344f2  xor     rcx, rsp; StackCookie
0x1800344f5  call    __security_check_cookie
0x1800344fa  mov     rbx, [rsp+0C0h+arg_10]
0x180034502  add     rsp, 0A0h
0x180034509  pop     r15
0x18003450b  pop     r14
0x18003450d  pop     rdi
0x18003450e  pop     rsi
0x18003450f  pop     rbp
0x180034510  retn
0x180034512  mov     edx, 19FAh
0x180034517  jmp     short loc_18003451E
0x180034519  mov     edx, 19F7h; void *
0x18003451e  mov     rcx, [rbp+5Fh]; this
0x180034522  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034529  mov     r9d, eax; char *
0x18003452c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034531  lea     rcx, [rbp+57h+var_70]
0x180034535  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003453a  jmp     short loc_180034554
0x18003453c  mov     rcx, [rbp+5Fh]; this
0x180034540  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034547  mov     r9d, eax; char *
0x18003454a  mov     edx, 19F4h; void *
0x18003454f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034554  lea     rcx, [rbp+57h+var_68]
0x180034558  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003455d  jmp     loc_18003434E
```
