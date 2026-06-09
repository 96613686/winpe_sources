# IsFamilyProvisioned

- ea: `0x180033e6c`
- end: `0x1800341f2`
- name: `IsFamilyProvisioned`
- size: `902`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800327a0`

## callees

- `0x180007c78`
- `0x180027244`
- `0x18002e37c`
- `0x180033de0`
- `0x180033e6c`
- `0x180042950`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800340b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800340b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800340d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800340d9`

## string_xrefs

- `0x180033ee1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033f1c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033f89`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033fcf`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800341b2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800341d0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x18DE,
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
      (void *)0x18E1,
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
      (void *)0x18E4,
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
    v13 = 6375;
    goto LABEL_12;
  }
  v27[0] = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v27);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 6378;
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
        (void *)0x18F0,
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
      v22 = 6387;
      goto LABEL_35;
    }
    string = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL))(v31, &string);
    v6 = v20;
    if ( v20 < 0 )
    {
      v22 = 6390;
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
      v22 = 6401;
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
0x180033e6c  mov     [rsp-8+arg_10], rbx
0x180033e71  push    rbp
0x180033e72  push    rsi
0x180033e73  push    rdi
0x180033e74  push    r14
0x180033e76  push    r15
0x180033e78  lea     rbp, [rsp-37h]
0x180033e7d  sub     rsp, 0A0h
0x180033e84  mov     rax, cs:__security_cookie
0x180033e8b  xor     rax, rsp
0x180033e8e  mov     [rbp+57h+var_28], rax
0x180033e92  xor     r15d, r15d
0x180033e95  mov     rsi, rdx
0x180033e98  mov     r14, rcx
0x180033e9b  mov     [rdx], r15b
0x180033e9e  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180033ea5  mov     [rbp+57h+var_58], r15
0x180033ea9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180033ead  mov     [rbp+57h+var_30], r15
0x180033eb1  lea     r9d, [r15+2Ch]; unsigned int
0x180033eb5  lea     r8d, [r15+2Dh]; unsigned int
0x180033eb9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180033ebe  mov     rbx, [rbp+57h+var_30]
0x180033ec2  lea     rcx, [rbp+57h+var_58]
0x180033ec6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033ecb  lea     rdx, [rbp+57h+var_58]
0x180033ecf  mov     rcx, rbx
0x180033ed2  call    ??$ActivateInstance@UIPackageManager9@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager9@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager9>(HSTRING__ *,Windows::Management::Deployment::IPackageManager9 * *)
0x180033ed7  mov     ebx, eax
0x180033ed9  test    eax, eax
0x180033edb  jns     short loc_180033EFA
0x180033edd  mov     rcx, [rbp+5Fh]; this
0x180033ee1  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033ee8  mov     r9d, eax; char *
0x180033eeb  mov     edx, 18DEh; void *
0x180033ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ef5  jmp     loc_18003416F
0x180033efa  mov     rcx, [rbp+57h+var_58]
0x180033efe  lea     rdx, [rbp+57h+var_88]
0x180033f02  mov     [rbp+57h+var_88], r15
0x180033f06  mov     rax, [rcx]
0x180033f09  mov     rax, [rax+30h]
0x180033f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f12  mov     ebx, eax
0x180033f14  test    eax, eax
0x180033f16  jns     short loc_180033F52
0x180033f18  mov     rcx, [rbp+5Fh]; this
0x180033f1c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033f23  mov     r9d, eax; char *
0x180033f26  mov     edx, 18E1h; void *
0x180033f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f30  mov     rcx, [rbp+57h+var_88]
0x180033f34  test    rcx, rcx
0x180033f37  jz      loc_18003416F
0x180033f3d  mov     [rbp+57h+var_88], r15
0x180033f41  mov     rax, [rcx]
0x180033f44  mov     rax, [rax+10h]
0x180033f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f4d  jmp     loc_18003416F
0x180033f52  mov     rbx, [rbp+57h+var_88]
0x180033f56  lea     rcx, [rbp+57h+var_78]
0x180033f5a  mov     [rbp+57h+var_78], r15
0x180033f5e  mov     rax, [rbx]
0x180033f61  mov     rdi, [rax]
0x180033f64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033f69  lea     r8, [rbp+57h+var_78]
0x180033f6d  mov     rcx, rbx
0x180033f70  lea     rdx, _GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d
0x180033f77  mov     rax, rdi
0x180033f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f7f  mov     ebx, eax
0x180033f81  test    eax, eax
0x180033f83  jns     short loc_180033FA8
0x180033f85  mov     rcx, [rbp+5Fh]; this
0x180033f89  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033f90  mov     r9d, eax; char *
0x180033f93  mov     edx, 18E4h; void *
0x180033f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f9d  lea     rcx, [rbp+57h+var_78]
0x180033fa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033fa6  jmp     short loc_180033F30
0x180033fa8  mov     rcx, [rbp+57h+var_78]
0x180033fac  lea     rdx, [rbp+57h+var_80]
0x180033fb0  mov     [rbp+57h+var_80], r15
0x180033fb4  mov     rax, [rcx]
0x180033fb7  mov     rax, [rax+30h]
0x180033fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fc0  mov     ebx, eax
0x180033fc2  test    eax, eax
0x180033fc4  jns     short loc_180033FF9
0x180033fc6  mov     edx, 18E7h; void *
0x180033fcb  mov     rcx, [rbp+5Fh]; this
0x180033fcf  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180033fd6  mov     r9d, eax; char *
0x180033fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033fde  mov     rcx, [rbp+57h+var_80]
0x180033fe2  test    rcx, rcx
0x180033fe5  jz      short loc_180033F9D
0x180033fe7  mov     [rbp+57h+var_80], r15
0x180033feb  mov     rax, [rcx]
0x180033fee  mov     rax, [rax+10h]
0x180033ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ff7  jmp     short loc_180033F9D
0x180033ff9  mov     rcx, [rbp+57h+var_80]
0x180033ffd  lea     rdx, [rbp+57h+var_90]
0x180034001  mov     [rbp+57h+var_90], r15b
0x180034005  mov     rax, [rcx]
0x180034008  mov     rax, [rax+38h]
0x18003400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034011  mov     ebx, eax
0x180034013  test    eax, eax
0x180034015  jns     short loc_18003401E
0x180034017  mov     edx, 18EAh
0x18003401c  jmp     short loc_180033FCB
0x18003401e  mov     [rbp+57h+var_68], r15
0x180034022  cmp     [rbp+57h+var_90], r15b
0x180034026  jz      loc_180034128
0x18003402c  mov     rbx, [rbp+57h+var_80]
0x180034030  lea     rcx, [rbp+57h+var_68]
0x180034034  mov     rax, [rbx]
0x180034037  mov     rdi, [rax+30h]
0x18003403b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034040  lea     rdx, [rbp+57h+var_68]
0x180034044  mov     rcx, rbx
0x180034047  mov     rax, rdi
0x18003404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003404f  mov     ebx, eax
0x180034051  test    eax, eax
0x180034053  js      loc_1800341CC
0x180034059  mov     rbx, [rbp+57h+var_68]
0x18003405d  lea     rcx, [rbp+57h+var_70]
0x180034061  mov     [rbp+57h+var_70], r15
0x180034065  mov     rax, [rbx]
0x180034068  mov     rdi, [rax+30h]
0x18003406c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034071  lea     rdx, [rbp+57h+var_70]
0x180034075  mov     rcx, rbx
0x180034078  mov     rax, rdi
0x18003407b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034080  mov     ebx, eax
0x180034082  test    eax, eax
0x180034084  js      loc_1800341A9
0x18003408a  mov     rcx, [rbp+57h+var_70]
0x18003408e  lea     rdx, [rbp+57h+string]
0x180034092  mov     [rbp+57h+string], r15
0x180034096  mov     rax, [rcx]
0x180034099  mov     rax, [rax+68h]
0x18003409d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340a2  mov     ebx, eax
0x1800340a4  test    eax, eax
0x1800340a6  js      loc_1800341A2
0x1800340ac  mov     rcx, [rbp+57h+string]; string
0x1800340b0  lea     rdx, [rbp+57h+length]; length
0x1800340b4  mov     [rbp+57h+length], r15d
0x1800340b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800340bf  nop     dword ptr [rax+rax+00h]
0x1800340c4  mov     edx, [rbp+57h+length]; cchCount1
0x1800340c7  or      r9d, 0FFFFFFFFh; cchCount2
0x1800340cb  mov     rcx, rax; lpString1
0x1800340ce  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x1800340d6  mov     r8, r14; lpString2
0x1800340d9  call    cs:__imp_CompareStringOrdinal
0x1800340e0  nop     dword ptr [rax+rax+00h]
0x1800340e5  cmp     eax, 2
0x1800340e8  jz      short loc_18003411C
0x1800340ea  mov     rcx, [rbp+57h+var_80]
0x1800340ee  lea     rdx, [rbp+57h+var_90]
0x1800340f2  mov     rax, [rcx]
0x1800340f5  mov     rax, [rax+40h]
0x1800340f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340fe  mov     ebx, eax
0x180034100  test    eax, eax
0x180034102  js      short loc_180034112
0x180034104  lea     rcx, [rbp+57h+var_70]
0x180034108  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003410d  jmp     loc_180034022
0x180034112  mov     edx, 1901h
0x180034117  jmp     loc_1800341AE
0x18003411c  lea     rcx, [rbp+57h+var_70]
0x180034120  mov     byte ptr [rsi], 1
0x180034123  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034128  lea     rcx, [rbp+57h+var_68]
0x18003412c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034131  mov     rcx, [rbp+57h+var_80]
0x180034135  test    rcx, rcx
0x180034138  jz      short loc_18003414A
0x18003413a  mov     [rbp+57h+var_80], r15
0x18003413e  mov     rax, [rcx]
0x180034141  mov     rax, [rax+10h]
0x180034145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003414a  lea     rcx, [rbp+57h+var_78]
0x18003414e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034153  mov     rcx, [rbp+57h+var_88]
0x180034157  test    rcx, rcx
0x18003415a  jz      short loc_18003416C
0x18003415c  mov     [rbp+57h+var_88], r15
0x180034160  mov     rax, [rcx]
0x180034163  mov     rax, [rax+10h]
0x180034167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003416c  mov     ebx, r15d
0x18003416f  lea     rcx, [rbp+57h+var_58]
0x180034173  mov     [rbp+57h+var_30], r15
0x180034177  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003417c  mov     eax, ebx
0x18003417e  mov     rcx, [rbp+57h+var_28]
0x180034182  xor     rcx, rsp; StackCookie
0x180034185  call    __security_check_cookie
0x18003418a  mov     rbx, [rsp+0C0h+arg_10]
0x180034192  add     rsp, 0A0h
0x180034199  pop     r15
0x18003419b  pop     r14
0x18003419d  pop     rdi
0x18003419e  pop     rsi
0x18003419f  pop     rbp
0x1800341a0  retn
0x1800341a2  mov     edx, 18F6h
0x1800341a7  jmp     short loc_1800341AE
0x1800341a9  mov     edx, 18F3h; void *
0x1800341ae  mov     rcx, [rbp+5Fh]; this
0x1800341b2  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800341b9  mov     r9d, eax; char *
0x1800341bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341c1  lea     rcx, [rbp+57h+var_70]
0x1800341c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800341ca  jmp     short loc_1800341E4
0x1800341cc  mov     rcx, [rbp+5Fh]; this
0x1800341d0  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800341d7  mov     r9d, eax; char *
0x1800341da  mov     edx, 18F0h; void *
0x1800341df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341e4  lea     rcx, [rbp+57h+var_68]
0x1800341e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800341ed  jmp     loc_180033FDE
```
