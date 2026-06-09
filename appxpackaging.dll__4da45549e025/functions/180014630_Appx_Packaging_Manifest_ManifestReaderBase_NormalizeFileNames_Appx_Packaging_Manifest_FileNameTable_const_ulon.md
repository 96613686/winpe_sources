# Appx::Packaging::Manifest::ManifestReaderBase::NormalizeFileNames(Appx::Packaging::Manifest::FileNameTable const *,ulong)

- ea: `0x180014630`
- end: `0x180014c79`
- name: `?NormalizeFileNames@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEBUFileNameTable@234@K@Z`
- size: `1609`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::ManifestReaderBase *__hidden this, const struct Appx::Packaging::Manifest::FileNameTable *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800154e4`
- `0x18002119c`

## callees

- `0x180005eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x180014630`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014a65`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180014a65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800148af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800148e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014915`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800148af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800148e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014915`
- `OLEAUT32!__imp_SysFreeString` at `0x1800147df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001492e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014973`
- `OLEAUT32!__imp_SysFreeString` at `0x1800149da`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a09`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014ac4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b64`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c16`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c37`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c66`
- `OLEAUT32!__imp_SysFreeString` at `0x1800147df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001492e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014973`
- `OLEAUT32!__imp_SysFreeString` at `0x1800149da`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a09`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180014ac4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b64`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c16`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c37`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c66`
- `OLEAUT32!__imp_SysStringLen` at `0x18001487d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001487d`

## string_xrefs

- `0x1800147ab`: `onecore\printscan\appxpackaging\lib\core\src\xpathhelper.cpp`
- `0x1800147c8`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014996`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x1800149f1`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014aac`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014b4d`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014b8c`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014bf9`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180014c4e`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::ManifestReaderBase::NormalizeFileNames(
        Appx::Packaging::Manifest::ManifestReaderBase *this,
        const struct Appx::Packaging::Manifest::FileNameTable *a2,
        unsigned int a3)
{
  unsigned int v3; // eax
  unsigned int v4; // r14d
  unsigned int v5; // r12d
  Appx::Packaging::Manifest::ManifestReaderBase *v6; // rsi
  OLECHAR *v7; // rbx
  char *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 *v14; // rcx
  OLECHAR *v15; // r13
  __int64 v16; // r15
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // edi
  __int64 v22; // rcx
  int i; // esi
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  UINT v27; // eax
  const WCHAR *v28; // rdi
  unsigned int v29; // ebx
  __int64 v30; // rcx
  __int64 v31; // rcx
  wchar_t *v32; // rax
  char j; // bl
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-69h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-69h]
  __int64 v40; // [rsp+30h] [rbp-59h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-49h] BYREF
  __int64 v43; // [rsp+48h] [rbp-41h] BYREF
  int v44; // [rsp+50h] [rbp-39h] BYREF
  __int64 v45; // [rsp+58h] [rbp-31h]
  int v46; // [rsp+60h] [rbp-29h]
  const wchar_t *v47; // [rsp+68h] [rbp-21h]
  int v48; // [rsp+70h] [rbp-19h]
  int v49; // [rsp+78h] [rbp-11h]
  __int64 v50; // [rsp+80h] [rbp-9h]
  int v51; // [rsp+88h] [rbp-1h]
  const WCHAR *v52; // [rsp+90h] [rbp+7h]
  int v53; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  const struct Appx::Packaging::Manifest::FileNameTable *v56; // [rsp+F8h] [rbp+6Fh]
  int v58; // [rsp+108h] [rbp+7Fh] BYREF

  v56 = a2;
  v3 = a3;
  v4 = 0;
  v5 = 0;
  v6 = this;
  while ( v5 < v3 )
  {
    v7 = 0;
    v8 = (char *)a2 + 32 * v5;
    bstrString = 0;
    v9 = *((_QWORD *)v8 + 2);
    v10 = *(_QWORD *)v8;
    if ( v9 )
    {
      v46 = *((_DWORD *)v8 + 2);
      v11 = *((_DWORD *)v8 + 6);
      v45 = v10;
      v50 = v9;
      v44 = 1;
      v47 = &LocaleName;
      v48 = 0;
      v49 = 4;
      v51 = v11;
      v52 = &LocaleName;
      v53 = 0;
      v12 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v44,
              (const struct Appx::Packaging::XPathComponent *)2,
              (unsigned int)&bstrString,
              (struct Common::AutoBStr *)&LocaleName);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
        SysFreeString(bstrString);
        return v13;
      }
    }
    else
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v10 + 2 * v19) );
      if ( (unsigned __int64)(v19 - 1) > 0xFFFFFFFD )
      {
        v20 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xpathhelper.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCase);
LABEL_14:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCase);
        SysFreeString(v7);
        return (unsigned int)v20;
      }
      v45 = *(_QWORD *)v8;
      v44 = 1;
      v46 = v19;
      v47 = L"']";
      v48 = 0;
      v20 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v44,
              (const struct Appx::Packaging::XPathComponent *)1,
              (unsigned int)&bstrString,
              (struct Common::AutoBStr *)&LocaleName);
      if ( v20 < 0 )
      {
        v7 = bstrString;
        goto LABEL_14;
      }
    }
    v14 = (__int64 *)*((_QWORD *)v6 + 3);
    v15 = bstrString;
    v16 = 0;
    v40 = 0;
    v58 = 0;
    v17 = *v14;
    v43 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v17 + 288))(v14, bstrString, &v40);
    v4 = v18;
    if ( v18 < 0 )
    {
      v36 = 139;
LABEL_54:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
      v37 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)v4,
        bIgnoreCasea);
      SysFreeString(v15);
      return v4;
    }
    if ( v40 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v58);
      v4 = v18;
      if ( v18 < 0 )
      {
        v36 = 143;
        goto LABEL_54;
      }
      if ( v58 <= 0 )
      {
        v22 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v4 = 0;
      }
      else
      {
        v16 = v40;
        v43 = v40;
      }
    }
    else
    {
      v4 = 0;
    }
    for ( i = 0; i < v58; ++i )
    {
      v40 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 72LL))(v16, &v40);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCase);
        v31 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        SysFreeString(v15);
        return v25;
      }
      pbstr = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v40 + 208LL))(v40, &pbstr);
      v4 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)(unsigned int)v26,
          bIgnoreCase);
        SysFreeString(pbstr);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
        SysFreeString(v15);
        return v4;
      }
      if ( !pbstr )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCase);
        SysFreeString(pbstr);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
        SysFreeString(v15);
        return 2147549183LL;
      }
      v27 = SysStringLen(pbstr);
      v28 = pbstr;
      v29 = v27;
      if ( (v27 < 7 || CompareStringOrdinal(pbstr, 7, L"http://", 7, 1) != 2)
        && (v29 < 8 || CompareStringOrdinal(v28, 8, L"https://", 8, 1) != 2)
        && (v29 < 0xE || CompareStringOrdinal(v28, 14, L"ms-appx-web://", 14, 1) != 2) )
      {
        v32 = pbstr;
        if ( pbstr )
        {
          if ( *pbstr )
          {
            for ( j = 0; ; j = 1 )
            {
              v32 = wcschr(v32, 0x2Fu);
              if ( !v32 )
                break;
              *v32 = 92;
            }
            v15 = bstrString;
            if ( j )
            {
              v34 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v40 + 216LL))(v40, pbstr);
              v4 = v34;
              if ( v34 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD7,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
                  (const char *)(unsigned int)v34,
                  bIgnoreCase);
                SysFreeString(pbstr);
                v35 = v40;
                if ( v40 )
                {
                  v40 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                }
                if ( v16 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                SysFreeString(v15);
                return v4;
              }
            }
          }
        }
      }
      SysFreeString(pbstr);
      v30 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    SysFreeString(v15);
    v3 = a3;
    ++v5;
    a2 = v56;
    v6 = this;
  }
  if ( (v4 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
      (const char *)v4,
      bIgnoreCase);
  return v4;
}

```

## disassembly

```asm
0x180014630  mov     [rsp-8+arg_10], r8d
0x180014635  mov     [rsp-8+arg_8], rdx
0x18001463a  mov     [rsp-8+arg_0], rcx
0x18001463f  push    rbp
0x180014640  push    rbx
0x180014641  push    rsi
0x180014642  push    rdi
0x180014643  push    r12
0x180014645  push    r13
0x180014647  push    r14
0x180014649  push    r15
0x18001464b  lea     rbp, [rsp-1Fh]
0x180014650  sub     rsp, 0A8h
0x180014657  xor     edi, edi
0x180014659  mov     eax, r8d
0x18001465c  mov     r14d, edi
0x18001465f  mov     r12d, edi
0x180014662  mov     rsi, rcx
0x180014665  lea     r9, LocaleName; struct Common::AutoBStr *
0x18001466c  mov     r11d, 0FFFFFFFDh
0x180014672  lea     r10, asc_1801177B4; "']"
0x180014679  cmp     r12d, eax
0x18001467c  jnb     loc_180014B7F
0x180014682  mov     ecx, r12d
0x180014685  mov     rbx, rdi
0x180014688  shl     rcx, 5
0x18001468c  add     rcx, rdx
0x18001468f  mov     [rbp+57h+bstrString], rbx
0x180014693  mov     r8, [rcx+10h]
0x180014697  mov     rdx, [rcx]
0x18001469a  test    r8, r8
0x18001469d  jz      loc_180014781
0x1800146a3  mov     eax, [rcx+8]
0x1800146a6  mov     [rbp+57h+var_80], eax
0x1800146a9  mov     eax, [rcx+18h]
0x1800146ac  lea     rcx, [rbp+57h+var_90]; this
0x1800146b0  mov     [rbp+57h+var_88], rdx
0x1800146b4  mov     edx, 2; struct Appx::Packaging::XPathComponent *
0x1800146b9  mov     [rbp+57h+var_60], r8
0x1800146bd  lea     r8, [rbp+57h+bstrString]; unsigned int
0x1800146c1  mov     [rbp+57h+var_90], 1
0x1800146c8  mov     [rbp+57h+var_78], r9
0x1800146cc  mov     [rbp+57h+var_70], edi
0x1800146cf  mov     [rbp+57h+var_68], 4
0x1800146d6  mov     [rbp+57h+var_58], eax
0x1800146d9  mov     [rbp+57h+var_50], r9
0x1800146dd  mov     [rbp+57h+var_48], edi
0x1800146e0  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800146e5  mov     ebx, eax
0x1800146e7  test    eax, eax
0x1800146e9  js      loc_180014C4A
0x1800146ef  mov     rcx, [rsi+18h]
0x1800146f3  lea     r8, [rbp+57h+var_B0]
0x1800146f7  mov     r13, [rbp+57h+bstrString]
0x1800146fb  mov     r15, rdi
0x1800146fe  mov     [rbp+57h+var_B0], rdi
0x180014702  mov     rdx, r13
0x180014705  mov     [rbp+57h+arg_18], edi
0x180014708  mov     rax, [rcx]
0x18001470b  mov     [rbp+57h+var_98], rdi
0x18001470f  mov     rax, [rax+120h]
0x180014716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471b  mov     r14d, eax
0x18001471e  test    eax, eax
0x180014720  js      loc_180014B18
0x180014726  mov     rcx, [rbp+57h+var_B0]
0x18001472a  test    rcx, rcx
0x18001472d  jz      loc_180014BA5
0x180014733  mov     rax, [rcx]
0x180014736  lea     rdx, [rbp+57h+arg_18]
0x18001473a  mov     rax, [rax+40h]
0x18001473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014743  mov     r14d, eax
0x180014746  test    eax, eax
0x180014748  js      loc_180014B78
0x18001474e  cmp     [rbp+57h+arg_18], 0
0x180014752  jle     loc_180014802
0x180014758  mov     r15, [rbp+57h+var_B0]
0x18001475c  mov     rcx, rdi
0x18001475f  mov     [rbp+57h+var_98], r15
0x180014763  test    rdi, rdi
0x180014766  jz      loc_18001481E
0x18001476c  mov     [rbp+57h+var_B0], rdi
0x180014770  mov     rax, [rdi]
0x180014773  mov     rax, [rax+10h]
0x180014777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001477c  jmp     loc_18001481E
0x180014781  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014788  nop     dword ptr [rax+rax+00000000h]
0x180014790  inc     rax
0x180014793  cmp     word ptr [rdx+rax*2], 0
0x180014798  jnz     short loc_180014790
0x18001479a  lea     rcx, [rax-1]
0x18001479e  cmp     rcx, r11
0x1800147a1  jbe     loc_180014BAD
0x1800147a7  mov     rcx, [rbp+5Fh]; this
0x1800147ab  lea     r8, aOnecorePrintsc_117; "onecore\\printscan\\appxpackaging\\lib"...
0x1800147b2  mov     edi, 8000FFFFh
0x1800147b7  mov     edx, 6Ah ; 'j'; void *
0x1800147bc  mov     r9d, edi; char *
0x1800147bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147c4  mov     rcx, [rbp+5Fh]; this
0x1800147c8  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800147cf  mov     r9d, edi; char *
0x1800147d2  mov     edx, 0AFh; void *
0x1800147d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800147dc  mov     rcx, rbx; bstrString
0x1800147df  call    cs:__imp_SysFreeString
0x1800147e6  nop     dword ptr [rax+rax+00h]
0x1800147eb  mov     eax, edi
0x1800147ed  add     rsp, 0A8h
0x1800147f4  pop     r15
0x1800147f6  pop     r14
0x1800147f8  pop     r13
0x1800147fa  pop     r12
0x1800147fc  pop     rdi
0x1800147fd  pop     rsi
0x1800147fe  pop     rbx
0x1800147ff  pop     rbp
0x180014800  retn
0x180014802  mov     rcx, [rbp+57h+var_B0]
0x180014806  test    rcx, rcx
0x180014809  jz      short loc_18001481B
0x18001480b  mov     [rbp+57h+var_B0], rdi
0x18001480f  mov     rax, [rcx]
0x180014812  mov     rax, [rax+10h]
0x180014816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001481b  mov     r14d, edi
0x18001481e  mov     esi, edi
0x180014820  cmp     esi, [rbp+57h+arg_18]
0x180014823  jge     loc_18001495C
0x180014829  mov     [rbp+57h+var_B0], rdi
0x18001482d  lea     rdx, [rbp+57h+var_B0]
0x180014831  mov     rax, [r15]
0x180014834  mov     rcx, r15
0x180014837  mov     rax, [rax+48h]
0x18001483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014840  mov     ebx, eax
0x180014842  test    eax, eax
0x180014844  js      loc_180014992
0x18001484a  mov     rcx, [rbp+57h+var_B0]
0x18001484e  lea     rdx, [rbp+57h+pbstr]
0x180014852  mov     [rbp+57h+pbstr], rdi
0x180014856  mov     rax, [rcx]
0x180014859  mov     rax, [rax+0D0h]
0x180014860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014865  mov     r14d, eax
0x180014868  test    eax, eax
0x18001486a  js      loc_1800149ED
0x180014870  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180014874  test    rcx, rcx
0x180014877  jz      loc_180014BF5
0x18001487d  call    cs:__imp_SysStringLen
0x180014884  nop     dword ptr [rax+rax+00h]
0x180014889  mov     rdi, [rbp+57h+pbstr]
0x18001488d  mov     ebx, eax
0x18001488f  cmp     eax, 7
0x180014892  jb      short loc_1800148C0
0x180014894  mov     r9d, 7; cchCount2
0x18001489a  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x1800148a2  mov     edx, r9d; cchCount1
0x1800148a5  lea     r8, ?UriPrefixHttp@Packaging@Appx@@3QBGB; "http://"
0x1800148ac  mov     rcx, rdi; lpString1
0x1800148af  call    cs:__imp_CompareStringOrdinal
0x1800148b6  nop     dword ptr [rax+rax+00h]
0x1800148bb  cmp     eax, 2
0x1800148be  jz      short loc_18001492A
0x1800148c0  cmp     ebx, 8
0x1800148c3  jb      short loc_1800148F1
0x1800148c5  mov     r9d, 8; cchCount2
0x1800148cb  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x1800148d3  mov     edx, r9d; cchCount1
0x1800148d6  lea     r8, ?UriPrefixHttps@Packaging@Appx@@3QBGB; "https://"
0x1800148dd  mov     rcx, rdi; lpString1
0x1800148e0  call    cs:__imp_CompareStringOrdinal
0x1800148e7  nop     dword ptr [rax+rax+00h]
0x1800148ec  cmp     eax, 2
0x1800148ef  jz      short loc_18001492A
0x1800148f1  cmp     ebx, 0Eh
0x1800148f4  jb      loc_180014A3E
0x1800148fa  mov     r9d, 0Eh; cchCount2
0x180014900  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x180014908  mov     edx, r9d; cchCount1
0x18001490b  lea     r8, ?UriPrefixMsAppxWeb@Packaging@Appx@@3QBGB; "ms-appx-web://"
0x180014912  mov     rcx, rdi; lpString1
0x180014915  call    cs:__imp_CompareStringOrdinal
0x18001491c  nop     dword ptr [rax+rax+00h]
0x180014921  cmp     eax, 2
0x180014924  jnz     loc_180014A3E
0x18001492a  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18001492e  call    cs:__imp_SysFreeString
0x180014935  nop     dword ptr [rax+rax+00h]
0x18001493a  mov     rcx, [rbp+57h+var_B0]
0x18001493e  xor     edi, edi
0x180014940  test    rcx, rcx
0x180014943  jz      short loc_180014955
0x180014945  mov     [rbp+57h+var_B0], rdi
0x180014949  mov     rax, [rcx]
0x18001494c  mov     rax, [rax+10h]
0x180014950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014955  inc     esi
0x180014957  jmp     loc_180014820
0x18001495c  test    r15, r15
0x18001495f  jz      short loc_180014970
0x180014961  mov     rax, [r15]
0x180014964  mov     rcx, r15
0x180014967  mov     rax, [rax+10h]
0x18001496b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014970  mov     rcx, r13; bstrString
0x180014973  call    cs:__imp_SysFreeString
0x18001497a  nop     dword ptr [rax+rax+00h]
0x18001497f  mov     eax, [rbp+57h+arg_10]
0x180014982  inc     r12d
0x180014985  mov     rdx, [rbp+57h+arg_8]
0x180014989  mov     rsi, [rbp+57h+arg_0]
0x18001498d  jmp     loc_180014665
0x180014992  mov     rcx, [rbp+5Fh]; this
0x180014996  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18001499d  mov     r9d, ebx; char *
0x1800149a0  mov     edx, 0C2h; void *
0x1800149a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800149aa  mov     rcx, [rbp+57h+var_B0]
0x1800149ae  test    rcx, rcx
0x1800149b1  jz      short loc_1800149C3
0x1800149b3  mov     [rbp+57h+var_B0], rdi
0x1800149b7  mov     rax, [rcx]
0x1800149ba  mov     rax, [rax+10h]
0x1800149be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149c3  test    r15, r15
0x1800149c6  jz      short loc_1800149D7
0x1800149c8  mov     rax, [r15]
0x1800149cb  mov     rcx, r15
0x1800149ce  mov     rax, [rax+10h]
0x1800149d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d7  mov     rcx, r13; bstrString
0x1800149da  call    cs:__imp_SysFreeString
0x1800149e1  nop     dword ptr [rax+rax+00h]
0x1800149e6  mov     eax, ebx
0x1800149e8  jmp     loc_1800147ED
0x1800149ed  mov     rcx, [rbp+5Fh]; this
0x1800149f1  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800149f8  mov     r9d, r14d; char *
0x1800149fb  mov     edx, 0C5h; void *
0x180014a00  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014a05  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180014a09  call    cs:__imp_SysFreeString
0x180014a10  nop     dword ptr [rax+rax+00h]
0x180014a15  lea     rcx, [rbp+57h+var_B0]
0x180014a19  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180014a1e  lea     rcx, [rbp+57h+var_98]
0x180014a22  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180014a27  mov     rcx, r13; bstrString
0x180014a2a  call    cs:__imp_SysFreeString
0x180014a31  nop     dword ptr [rax+rax+00h]
0x180014a36  mov     eax, r14d
0x180014a39  jmp     loc_1800147ED
0x180014a3e  mov     rax, [rbp+57h+pbstr]
0x180014a42  test    rax, rax
0x180014a45  jz      loc_18001492A
0x180014a4b  cmp     word ptr [rax], 0
0x180014a4f  jz      loc_18001492A
0x180014a55  xor     bl, bl
0x180014a57  mov     r13d, 5Ch ; '\'
0x180014a5d  mov     edx, 2Fh ; '/'; Ch
0x180014a62  mov     rcx, rax; Str
0x180014a65  call    cs:__imp_wcschr
0x180014a6c  nop     dword ptr [rax+rax+00h]
0x180014a71  test    rax, rax
0x180014a74  jnz     loc_180014BEA
0x180014a7a  mov     r13, [rbp+57h+bstrString]
0x180014a7e  test    bl, bl
0x180014a80  jz      loc_18001492A
0x180014a86  mov     rcx, [rbp+57h+var_B0]
0x180014a8a  mov     rdx, [rbp+57h+pbstr]
0x180014a8e  mov     rax, [rcx]
0x180014a91  mov     rax, [rax+0D8h]
0x180014a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a9d  mov     r14d, eax
0x180014aa0  test    eax, eax
0x180014aa2  jns     loc_18001492A
0x180014aa8  mov     rcx, [rbp+5Fh]; this
0x180014aac  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180014ab3  mov     r9d, eax; char *
0x180014ab6  mov     edx, 0D7h; void *
0x180014abb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014ac0  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180014ac4  call    cs:__imp_SysFreeString
0x180014acb  nop     dword ptr [rax+rax+00h]
0x180014ad0  mov     rcx, [rbp+57h+var_B0]
0x180014ad4  test    rcx, rcx
0x180014ad7  jz      short loc_180014AED
0x180014ad9  mov     [rbp+57h+var_B0], 0
0x180014ae1  mov     rax, [rcx]
0x180014ae4  mov     rax, [rax+10h]
0x180014ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aed  test    r15, r15
0x180014af0  jz      short loc_180014B01
0x180014af2  mov     rax, [r15]
0x180014af5  mov     rcx, r15
0x180014af8  mov     rax, [rax+10h]
  ... truncated ...
```
