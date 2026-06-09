# IsFamilyProvisioned

- ea: `0x180037274`
- end: `0x1800375e1`
- name: `IsFamilyProvisioned`
- size: `877`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035dbc`

## callees

- `0x18000720c`
- `0x180029d90`
- `0x18003150c`
- `0x1800371ec`
- `0x180037274`
- `0x180046e50`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800374b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800374b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800374cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800374cf`

## string_xrefs

- `0x1800372dd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180037318`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180037385`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800373cb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800375a1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800375bf`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall IsFamilyProvisioned(LPCWCH lpString2, _BYTE *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  _BYTE v26[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  __int64 v31; // [rsp+58h] [rbp-11h] BYREF
  UINT32 length; // [rsp+60h] [rbp-9h] BYREF
  __int64 v33; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v36; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v33 = 0;
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.PackageManager",
    0x2Du,
    0x2Cu);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager9>>(
         v36,
         &v33);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C27,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    goto LABEL_32;
  }
  v27 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v33 + 48LL))(
         v33,
         &v27);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2A,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    goto LABEL_5;
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
  v29 = 0;
  v9 = **v27;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v10 = v9(v8, &GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d, &v29);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2D,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
LABEL_5:
    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
    if ( v27 )
    {
      v27 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
    }
    goto LABEL_32;
  }
  v28 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v28);
  v5 = v11;
  if ( v11 < 0 )
  {
    v12 = 7216;
    goto LABEL_12;
  }
  v26[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v28 + 56LL))(v28, v26);
  v5 = v11;
  if ( v11 < 0 )
  {
    v12 = 7219;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
LABEL_13:
    v13 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_9;
  }
  v31 = 0;
  while ( 1 )
  {
    if ( !v26[0] )
      goto LABEL_27;
    v14 = v28;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v16 = v15(v14, &v31);
    v5 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C39,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v16,
        bIgnoreCase);
      goto LABEL_37;
    }
    v17 = v31;
    v30 = 0;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v19 = v18(v17, &v30);
    v5 = v19;
    if ( v19 < 0 )
    {
      v21 = 7228;
      goto LABEL_35;
    }
    string = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 104LL))(v30, &string);
    v5 = v19;
    if ( v19 < 0 )
    {
      v21 = 7231;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v19,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
LABEL_37:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      goto LABEL_13;
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( CompareStringOrdinal(StringRawBuffer, length, lpString2, -1, 1) == 2 )
      break;
    v19 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v28 + 64LL))(v28, v26);
    v5 = v19;
    if ( v19 < 0 )
    {
      v21 = 7242;
      goto LABEL_35;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  }
  *a2 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
LABEL_27:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  }
  v5 = 0;
LABEL_32:
  v36 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  return v5;
}

```

## disassembly

```asm
0x180037274  mov     [rsp-8+arg_10], rbx
0x180037279  push    rbp
0x18003727a  push    rsi
0x18003727b  push    rdi
0x18003727c  push    r14
0x18003727e  push    r15
0x180037280  lea     rbp, [rsp-37h]
0x180037285  sub     rsp, 0A0h
0x18003728c  mov     rax, cs:__security_cookie
0x180037293  xor     rax, rsp
0x180037296  mov     [rbp+57h+var_28], rax
0x18003729a  xor     r15d, r15d
0x18003729d  mov     rsi, rdx
0x1800372a0  mov     r14, rcx
0x1800372a3  mov     [rdx], r15b
0x1800372a6  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800372ad  mov     [rbp+57h+var_58], r15
0x1800372b1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800372b5  mov     [rbp+57h+var_30], r15
0x1800372b9  lea     r9d, [r15+2Ch]; unsigned int
0x1800372bd  lea     r8d, [r15+2Dh]; unsigned int
0x1800372c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800372c6  mov     rcx, [rbp+57h+var_30]
0x1800372ca  lea     rdx, [rbp+57h+var_58]
0x1800372ce  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager9@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager9@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager9>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager9>>)
0x1800372d3  mov     ebx, eax
0x1800372d5  test    eax, eax
0x1800372d7  jns     short loc_1800372F6
0x1800372d9  mov     rcx, [rbp+5Fh]; this
0x1800372dd  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800372e4  mov     r9d, eax; char *
0x1800372e7  mov     edx, 1C27h; void *
0x1800372ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800372f1  jmp     loc_18003755F
0x1800372f6  mov     rcx, [rbp+57h+var_58]
0x1800372fa  lea     rdx, [rbp+57h+var_88]
0x1800372fe  mov     [rbp+57h+var_88], r15
0x180037302  mov     rax, [rcx]
0x180037305  mov     rax, [rax+30h]
0x180037309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003730e  mov     ebx, eax
0x180037310  test    eax, eax
0x180037312  jns     short loc_18003734E
0x180037314  mov     rcx, [rbp+5Fh]; this
0x180037318  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003731f  mov     r9d, eax; char *
0x180037322  mov     edx, 1C2Ah; void *
0x180037327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003732c  mov     rcx, [rbp+57h+var_88]
0x180037330  test    rcx, rcx
0x180037333  jz      loc_18003755F
0x180037339  mov     [rbp+57h+var_88], r15
0x18003733d  mov     rax, [rcx]
0x180037340  mov     rax, [rax+10h]
0x180037344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037349  jmp     loc_18003755F
0x18003734e  mov     rbx, [rbp+57h+var_88]
0x180037352  lea     rcx, [rbp+57h+var_78]
0x180037356  mov     [rbp+57h+var_78], r15
0x18003735a  mov     rax, [rbx]
0x18003735d  mov     rdi, [rax]
0x180037360  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037365  lea     r8, [rbp+57h+var_78]
0x180037369  mov     rcx, rbx
0x18003736c  lea     rdx, _GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d
0x180037373  mov     rax, rdi
0x180037376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003737b  mov     ebx, eax
0x18003737d  test    eax, eax
0x18003737f  jns     short loc_1800373A4
0x180037381  mov     rcx, [rbp+5Fh]; this
0x180037385  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003738c  mov     r9d, eax; char *
0x18003738f  mov     edx, 1C2Dh; void *
0x180037394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037399  lea     rcx, [rbp+57h+var_78]
0x18003739d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800373a2  jmp     short loc_18003732C
0x1800373a4  mov     rcx, [rbp+57h+var_78]
0x1800373a8  lea     rdx, [rbp+57h+var_80]
0x1800373ac  mov     [rbp+57h+var_80], r15
0x1800373b0  mov     rax, [rcx]
0x1800373b3  mov     rax, [rax+30h]
0x1800373b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373bc  mov     ebx, eax
0x1800373be  test    eax, eax
0x1800373c0  jns     short loc_1800373F5
0x1800373c2  mov     edx, 1C30h; void *
0x1800373c7  mov     rcx, [rbp+5Fh]; this
0x1800373cb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800373d2  mov     r9d, eax; char *
0x1800373d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800373da  mov     rcx, [rbp+57h+var_80]
0x1800373de  test    rcx, rcx
0x1800373e1  jz      short loc_180037399
0x1800373e3  mov     [rbp+57h+var_80], r15
0x1800373e7  mov     rax, [rcx]
0x1800373ea  mov     rax, [rax+10h]
0x1800373ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373f3  jmp     short loc_180037399
0x1800373f5  mov     rcx, [rbp+57h+var_80]
0x1800373f9  lea     rdx, [rbp+57h+var_90]
0x1800373fd  mov     [rbp+57h+var_90], r15b
0x180037401  mov     rax, [rcx]
0x180037404  mov     rax, [rax+38h]
0x180037408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003740d  mov     ebx, eax
0x18003740f  test    eax, eax
0x180037411  jns     short loc_18003741A
0x180037413  mov     edx, 1C33h
0x180037418  jmp     short loc_1800373C7
0x18003741a  mov     [rbp+57h+var_68], r15
0x18003741e  cmp     [rbp+57h+var_90], r15b
0x180037422  jz      loc_180037518
0x180037428  mov     rdi, [rbp+57h+var_80]
0x18003742c  lea     rcx, [rbp+57h+var_68]
0x180037430  mov     rax, [rdi]
0x180037433  mov     rbx, [rax+30h]
0x180037437  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003743c  lea     rdx, [rbp+57h+var_68]
0x180037440  mov     rcx, rdi
0x180037443  mov     rax, rbx
0x180037446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003744b  mov     ebx, eax
0x18003744d  test    eax, eax
0x18003744f  js      loc_1800375BB
0x180037455  mov     rdi, [rbp+57h+var_68]
0x180037459  lea     rcx, [rbp+57h+var_70]
0x18003745d  mov     [rbp+57h+var_70], r15
0x180037461  mov     rax, [rdi]
0x180037464  mov     rbx, [rax+30h]
0x180037468  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003746d  lea     rdx, [rbp+57h+var_70]
0x180037471  mov     rcx, rdi
0x180037474  mov     rax, rbx
0x180037477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003747c  mov     ebx, eax
0x18003747e  test    eax, eax
0x180037480  js      loc_180037598
0x180037486  mov     rcx, [rbp+57h+var_70]
0x18003748a  lea     rdx, [rbp+57h+string]
0x18003748e  mov     [rbp+57h+string], r15
0x180037492  mov     rax, [rcx]
0x180037495  mov     rax, [rax+68h]
0x180037499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003749e  mov     ebx, eax
0x1800374a0  test    eax, eax
0x1800374a2  js      loc_180037591
0x1800374a8  mov     rcx, [rbp+57h+string]; string
0x1800374ac  lea     rdx, [rbp+57h+length]; length
0x1800374b0  mov     [rbp+57h+length], r15d
0x1800374b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800374ba  mov     edx, [rbp+57h+length]; cchCount1
0x1800374bd  or      r9d, 0FFFFFFFFh; cchCount2
0x1800374c1  mov     rcx, rax; lpString1
0x1800374c4  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x1800374cc  mov     r8, r14; lpString2
0x1800374cf  call    cs:__imp_CompareStringOrdinal
0x1800374d5  cmp     eax, 2
0x1800374d8  jz      short loc_18003750C
0x1800374da  mov     rcx, [rbp+57h+var_80]
0x1800374de  lea     rdx, [rbp+57h+var_90]
0x1800374e2  mov     rax, [rcx]
0x1800374e5  mov     rax, [rax+40h]
0x1800374e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374ee  mov     ebx, eax
0x1800374f0  test    eax, eax
0x1800374f2  js      short loc_180037502
0x1800374f4  lea     rcx, [rbp+57h+var_70]
0x1800374f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800374fd  jmp     loc_18003741E
0x180037502  mov     edx, 1C4Ah
0x180037507  jmp     loc_18003759D
0x18003750c  lea     rcx, [rbp+57h+var_70]
0x180037510  mov     byte ptr [rsi], 1
0x180037513  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037518  lea     rcx, [rbp+57h+var_68]
0x18003751c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037521  mov     rcx, [rbp+57h+var_80]
0x180037525  test    rcx, rcx
0x180037528  jz      short loc_18003753A
0x18003752a  mov     [rbp+57h+var_80], r15
0x18003752e  mov     rax, [rcx]
0x180037531  mov     rax, [rax+10h]
0x180037535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003753a  lea     rcx, [rbp+57h+var_78]
0x18003753e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037543  mov     rcx, [rbp+57h+var_88]
0x180037547  test    rcx, rcx
0x18003754a  jz      short loc_18003755C
0x18003754c  mov     [rbp+57h+var_88], r15
0x180037550  mov     rax, [rcx]
0x180037553  mov     rax, [rax+10h]
0x180037557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003755c  mov     ebx, r15d
0x18003755f  lea     rcx, [rbp+57h+var_58]
0x180037563  mov     [rbp+57h+var_30], r15
0x180037567  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003756c  mov     eax, ebx
0x18003756e  mov     rcx, [rbp+57h+var_28]
0x180037572  xor     rcx, rsp; StackCookie
0x180037575  call    __security_check_cookie
0x18003757a  mov     rbx, [rsp+0C0h+arg_10]
0x180037582  add     rsp, 0A0h
0x180037589  pop     r15
0x18003758b  pop     r14
0x18003758d  pop     rdi
0x18003758e  pop     rsi
0x18003758f  pop     rbp
0x180037590  retn
0x180037591  mov     edx, 1C3Fh
0x180037596  jmp     short loc_18003759D
0x180037598  mov     edx, 1C3Ch; void *
0x18003759d  mov     rcx, [rbp+5Fh]; this
0x1800375a1  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800375a8  mov     r9d, eax; char *
0x1800375ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800375b0  lea     rcx, [rbp+57h+var_70]
0x1800375b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800375b9  jmp     short loc_1800375D3
0x1800375bb  mov     rcx, [rbp+5Fh]; this
0x1800375bf  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800375c6  mov     r9d, eax; char *
0x1800375c9  mov     edx, 1C39h; void *
0x1800375ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800375d3  lea     rcx, [rbp+57h+var_68]
0x1800375d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800375dc  jmp     loc_1800373DA
```
