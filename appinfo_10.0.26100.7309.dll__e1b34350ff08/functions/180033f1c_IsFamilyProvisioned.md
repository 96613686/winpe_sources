# IsFamilyProvisioned

- ea: `0x180033f1c`
- end: `0x1800342a2`
- name: `IsFamilyProvisioned`
- size: `902`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032810`

## callees

- `0x180007c78`
- `0x180025c04`
- `0x18002cd5c`
- `0x180033e90`
- `0x180033f1c`
- `0x1800444e0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034168`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034189`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034189`

## string_xrefs

- `0x180033f91`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180033fcc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034039`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003407f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034262`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180034280`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
      (void *)0x19AB,
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
      (void *)0x19AE,
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
      (void *)0x19B1,
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
    v13 = 6580;
    goto LABEL_12;
  }
  v27[0] = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v27);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 6583;
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
        (void *)0x19BD,
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
      v22 = 6592;
      goto LABEL_35;
    }
    string = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL))(v31, &string);
    v6 = v20;
    if ( v20 < 0 )
    {
      v22 = 6595;
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
      v22 = 6606;
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
0x180033f1c  mov     [rsp-8+arg_10], rbx
0x180033f21  push    rbp
0x180033f22  push    rsi
0x180033f23  push    rdi
0x180033f24  push    r14
0x180033f26  push    r15
0x180033f28  lea     rbp, [rsp-37h]
0x180033f2d  sub     rsp, 0A0h
0x180033f34  mov     rax, cs:__security_cookie
0x180033f3b  xor     rax, rsp
0x180033f3e  mov     [rbp+57h+var_28], rax
0x180033f42  xor     r15d, r15d
0x180033f45  mov     rsi, rdx
0x180033f48  mov     r14, rcx
0x180033f4b  mov     [rdx], r15b
0x180033f4e  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180033f55  mov     [rbp+57h+var_58], r15
0x180033f59  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180033f5d  mov     [rbp+57h+var_30], r15
0x180033f61  lea     r9d, [r15+2Ch]; unsigned int
0x180033f65  lea     r8d, [r15+2Dh]; unsigned int
0x180033f69  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180033f6e  mov     rbx, [rbp+57h+var_30]
0x180033f72  lea     rcx, [rbp+57h+var_58]
0x180033f76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033f7b  lea     rdx, [rbp+57h+var_58]
0x180033f7f  mov     rcx, rbx
0x180033f82  call    ??$ActivateInstance@UIPackageManager9@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager9@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager9>(HSTRING__ *,Windows::Management::Deployment::IPackageManager9 * *)
0x180033f87  mov     ebx, eax
0x180033f89  test    eax, eax
0x180033f8b  jns     short loc_180033FAA
0x180033f8d  mov     rcx, [rbp+5Fh]; this
0x180033f91  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033f98  mov     r9d, eax; char *
0x180033f9b  mov     edx, 19ABh; void *
0x180033fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033fa5  jmp     loc_18003421F
0x180033faa  mov     rcx, [rbp+57h+var_58]
0x180033fae  lea     rdx, [rbp+57h+var_88]
0x180033fb2  mov     [rbp+57h+var_88], r15
0x180033fb6  mov     rax, [rcx]
0x180033fb9  mov     rax, [rax+30h]
0x180033fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fc2  mov     ebx, eax
0x180033fc4  test    eax, eax
0x180033fc6  jns     short loc_180034002
0x180033fc8  mov     rcx, [rbp+5Fh]; this
0x180033fcc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180033fd3  mov     r9d, eax; char *
0x180033fd6  mov     edx, 19AEh; void *
0x180033fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033fe0  mov     rcx, [rbp+57h+var_88]
0x180033fe4  test    rcx, rcx
0x180033fe7  jz      loc_18003421F
0x180033fed  mov     [rbp+57h+var_88], r15
0x180033ff1  mov     rax, [rcx]
0x180033ff4  mov     rax, [rax+10h]
0x180033ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ffd  jmp     loc_18003421F
0x180034002  mov     rbx, [rbp+57h+var_88]
0x180034006  lea     rcx, [rbp+57h+var_78]
0x18003400a  mov     [rbp+57h+var_78], r15
0x18003400e  mov     rax, [rbx]
0x180034011  mov     rdi, [rax]
0x180034014  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034019  lea     r8, [rbp+57h+var_78]
0x18003401d  mov     rcx, rbx
0x180034020  lea     rdx, _GUID_69ad6aa7_0c49_5f27_a5eb_ef4d59467b6d
0x180034027  mov     rax, rdi
0x18003402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003402f  mov     ebx, eax
0x180034031  test    eax, eax
0x180034033  jns     short loc_180034058
0x180034035  mov     rcx, [rbp+5Fh]; this
0x180034039  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034040  mov     r9d, eax; char *
0x180034043  mov     edx, 19B1h; void *
0x180034048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003404d  lea     rcx, [rbp+57h+var_78]
0x180034051  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034056  jmp     short loc_180033FE0
0x180034058  mov     rcx, [rbp+57h+var_78]
0x18003405c  lea     rdx, [rbp+57h+var_80]
0x180034060  mov     [rbp+57h+var_80], r15
0x180034064  mov     rax, [rcx]
0x180034067  mov     rax, [rax+30h]
0x18003406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034070  mov     ebx, eax
0x180034072  test    eax, eax
0x180034074  jns     short loc_1800340A9
0x180034076  mov     edx, 19B4h; void *
0x18003407b  mov     rcx, [rbp+5Fh]; this
0x18003407f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034086  mov     r9d, eax; char *
0x180034089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003408e  mov     rcx, [rbp+57h+var_80]
0x180034092  test    rcx, rcx
0x180034095  jz      short loc_18003404D
0x180034097  mov     [rbp+57h+var_80], r15
0x18003409b  mov     rax, [rcx]
0x18003409e  mov     rax, [rax+10h]
0x1800340a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340a7  jmp     short loc_18003404D
0x1800340a9  mov     rcx, [rbp+57h+var_80]
0x1800340ad  lea     rdx, [rbp+57h+var_90]
0x1800340b1  mov     [rbp+57h+var_90], r15b
0x1800340b5  mov     rax, [rcx]
0x1800340b8  mov     rax, [rax+38h]
0x1800340bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340c1  mov     ebx, eax
0x1800340c3  test    eax, eax
0x1800340c5  jns     short loc_1800340CE
0x1800340c7  mov     edx, 19B7h
0x1800340cc  jmp     short loc_18003407B
0x1800340ce  mov     [rbp+57h+var_68], r15
0x1800340d2  cmp     [rbp+57h+var_90], r15b
0x1800340d6  jz      loc_1800341D8
0x1800340dc  mov     rbx, [rbp+57h+var_80]
0x1800340e0  lea     rcx, [rbp+57h+var_68]
0x1800340e4  mov     rax, [rbx]
0x1800340e7  mov     rdi, [rax+30h]
0x1800340eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800340f0  lea     rdx, [rbp+57h+var_68]
0x1800340f4  mov     rcx, rbx
0x1800340f7  mov     rax, rdi
0x1800340fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340ff  mov     ebx, eax
0x180034101  test    eax, eax
0x180034103  js      loc_18003427C
0x180034109  mov     rbx, [rbp+57h+var_68]
0x18003410d  lea     rcx, [rbp+57h+var_70]
0x180034111  mov     [rbp+57h+var_70], r15
0x180034115  mov     rax, [rbx]
0x180034118  mov     rdi, [rax+30h]
0x18003411c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034121  lea     rdx, [rbp+57h+var_70]
0x180034125  mov     rcx, rbx
0x180034128  mov     rax, rdi
0x18003412b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034130  mov     ebx, eax
0x180034132  test    eax, eax
0x180034134  js      loc_180034259
0x18003413a  mov     rcx, [rbp+57h+var_70]
0x18003413e  lea     rdx, [rbp+57h+string]
0x180034142  mov     [rbp+57h+string], r15
0x180034146  mov     rax, [rcx]
0x180034149  mov     rax, [rax+68h]
0x18003414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034152  mov     ebx, eax
0x180034154  test    eax, eax
0x180034156  js      loc_180034252
0x18003415c  mov     rcx, [rbp+57h+string]; string
0x180034160  lea     rdx, [rbp+57h+length]; length
0x180034164  mov     [rbp+57h+length], r15d
0x180034168  call    cs:__imp_WindowsGetStringRawBuffer
0x18003416f  nop     dword ptr [rax+rax+00h]
0x180034174  mov     edx, [rbp+57h+length]; cchCount1
0x180034177  or      r9d, 0FFFFFFFFh; cchCount2
0x18003417b  mov     rcx, rax; lpString1
0x18003417e  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x180034186  mov     r8, r14; lpString2
0x180034189  call    cs:__imp_CompareStringOrdinal
0x180034190  nop     dword ptr [rax+rax+00h]
0x180034195  cmp     eax, 2
0x180034198  jz      short loc_1800341CC
0x18003419a  mov     rcx, [rbp+57h+var_80]
0x18003419e  lea     rdx, [rbp+57h+var_90]
0x1800341a2  mov     rax, [rcx]
0x1800341a5  mov     rax, [rax+40h]
0x1800341a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341ae  mov     ebx, eax
0x1800341b0  test    eax, eax
0x1800341b2  js      short loc_1800341C2
0x1800341b4  lea     rcx, [rbp+57h+var_70]
0x1800341b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800341bd  jmp     loc_1800340D2
0x1800341c2  mov     edx, 19CEh
0x1800341c7  jmp     loc_18003425E
0x1800341cc  lea     rcx, [rbp+57h+var_70]
0x1800341d0  mov     byte ptr [rsi], 1
0x1800341d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800341d8  lea     rcx, [rbp+57h+var_68]
0x1800341dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800341e1  mov     rcx, [rbp+57h+var_80]
0x1800341e5  test    rcx, rcx
0x1800341e8  jz      short loc_1800341FA
0x1800341ea  mov     [rbp+57h+var_80], r15
0x1800341ee  mov     rax, [rcx]
0x1800341f1  mov     rax, [rax+10h]
0x1800341f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341fa  lea     rcx, [rbp+57h+var_78]
0x1800341fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034203  mov     rcx, [rbp+57h+var_88]
0x180034207  test    rcx, rcx
0x18003420a  jz      short loc_18003421C
0x18003420c  mov     [rbp+57h+var_88], r15
0x180034210  mov     rax, [rcx]
0x180034213  mov     rax, [rax+10h]
0x180034217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003421c  mov     ebx, r15d
0x18003421f  lea     rcx, [rbp+57h+var_58]
0x180034223  mov     [rbp+57h+var_30], r15
0x180034227  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003422c  mov     eax, ebx
0x18003422e  mov     rcx, [rbp+57h+var_28]
0x180034232  xor     rcx, rsp; StackCookie
0x180034235  call    __security_check_cookie
0x18003423a  mov     rbx, [rsp+0C0h+arg_10]
0x180034242  add     rsp, 0A0h
0x180034249  pop     r15
0x18003424b  pop     r14
0x18003424d  pop     rdi
0x18003424e  pop     rsi
0x18003424f  pop     rbp
0x180034250  retn
0x180034252  mov     edx, 19C3h
0x180034257  jmp     short loc_18003425E
0x180034259  mov     edx, 19C0h; void *
0x18003425e  mov     rcx, [rbp+5Fh]; this
0x180034262  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034269  mov     r9d, eax; char *
0x18003426c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034271  lea     rcx, [rbp+57h+var_70]
0x180034275  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003427a  jmp     short loc_180034294
0x18003427c  mov     rcx, [rbp+5Fh]; this
0x180034280  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180034287  mov     r9d, eax; char *
0x18003428a  mov     edx, 19BDh; void *
0x18003428f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034294  lea     rcx, [rbp+57h+var_68]
0x180034298  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003429d  jmp     loc_18003408E
```
