# AADUtil::ExtractAADDeviceTicketAndDataBoundary(Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> const &,HSTRING__ * *,HSTRING__ * *)

- ea: `0x14003f590`
- end: `0x14003f965`
- name: `?ExtractAADDeviceTicketAndDataBoundary@AADUtil@@YAJAEBV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@PEAPEAUHSTRING__@@1@Z`
- size: `981`
- prototype: `__int64 __fastcall(_QWORD *, HSTRING *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f96c`

## callees

- `0x140008de4`
- `0x14003cfb0`
- `0x14003f590`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003f7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003f7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003f796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003f902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003f796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003f902`

## pseudocode

```c
__int64 __fastcall AADUtil::ExtractAADDeviceTicketAndDataBoundary(_QWORD *a1, HSTRING *a2, _QWORD *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rdi
  unsigned int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, PVOID, _BYTE *); // rdi
  HSTRING_HEADER *v19; // rax
  unsigned int v20; // r8d
  unsigned __int64 v21; // r9
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, PVOID, _QWORD *); // rdi
  HSTRING_HEADER *v24; // rax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  HSTRING_HEADER v30; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v31[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  int v34; // [rsp+58h] [rbp-28h] BYREF
  int v35; // [rsp+5Ch] [rbp-24h] BYREF
  __int64 v36; // [rsp+60h] [rbp-20h] BYREF
  __int64 v37; // [rsp+68h] [rbp-18h] BYREF
  __int64 v38; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( *a1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      if ( !a3 )
        goto LABEL_10;
    }
    else if ( !a3 )
    {
      v6 = 55;
      goto LABEL_3;
    }
    *a3 = 0;
LABEL_10:
    v34 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v34);
    if ( v7 < 0 )
    {
      v6 = 68;
      goto LABEL_4;
    }
    if ( v34 )
    {
      if ( v34 == 1 )
        return 2147943623LL;
      if ( v34 == 3 )
        return 2147943717LL;
      if ( v34 != 5 )
        return 2147549183LL;
      v38 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 64LL))(*a1, &v38);
      if ( v7 >= 0 )
      {
        LODWORD(v32) = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v32);
        if ( v7 >= 0 )
        {
          v7 = (unsigned __int16)v32 | 0x80070000;
          if ( (int)v32 <= 0 )
            v7 = v32;
          goto LABEL_24;
        }
        v9 = 89;
      }
      else
      {
        v9 = 86;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
        (const char *)(unsigned int)v7,
        (int)v30.Reserved.Reserved1);
LABEL_24:
      v10 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return (unsigned int)v7;
    }
    v37 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 48LL))(*a1, &v37);
    if ( v7 < 0 )
    {
      v11 = 99;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
        (const char *)(unsigned int)v7,
        (int)v30.Reserved.Reserved1);
LABEL_61:
      v29 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      return (unsigned int)v7;
    }
    v35 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 56LL))(v37, &v35);
    if ( v7 < 0 )
    {
      v11 = 102;
      goto LABEL_33;
    }
    v36 = 0;
    string = 0;
    if ( !v35 )
    {
      v7 = -2147467259;
      v12 = 114;
      goto LABEL_58;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, 0, &v36);
    if ( v7 < 0 )
    {
      v12 = 109;
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
        (const char *)(unsigned int)v7,
        (int)v30.Reserved.Reserved1);
LABEL_59:
      WindowsDeleteString(string);
      string = 0;
      v28 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      goto LABEL_61;
    }
    v13 = v36;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v7 = v14(v13, &string);
    if ( v7 < 0 )
    {
      v12 = 110;
      goto LABEL_58;
    }
    if ( a2 )
    {
      v7 = WindowsDuplicateString(string, a2);
      if ( v7 < 0 )
      {
        v12 = 119;
        goto LABEL_58;
      }
    }
    if ( a3 )
    {
      v32 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 72LL))(v36, &v32);
      if ( v7 < 0 )
      {
        v16 = 125;
LABEL_47:
        v21 = (unsigned int)v7;
        goto LABEL_51;
      }
      v31[0] = 0;
      v17 = v32;
      v18 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)v32 + 64LL);
      v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v30, (const WCHAR **)off_14006F218, v15);
      v7 = v18(v17, v19[1].Reserved.Reserved1, v31);
      if ( v7 < 0 )
      {
        v16 = 128;
        goto LABEL_47;
      }
      if ( v31[0] )
      {
        v22 = v32;
        v23 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD *))(*(_QWORD *)v32 + 48LL);
        v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v30, (const WCHAR **)off_14006F218, v20);
        v25 = v23(v22, v24[1].Reserved.Reserved1, a3);
        v7 = v25;
        if ( v25 < 0 )
        {
          v21 = (unsigned int)v25;
          v16 = 132;
LABEL_51:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
            (const char *)v21,
            (int)v30.Reserved.Reserved1);
          v26 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          goto LABEL_59;
        }
      }
      v27 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
    }
    v7 = 0;
    goto LABEL_59;
  }
  v6 = 52;
LABEL_3:
  v7 = -2147467261;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\AADUtil.cpp",
    (const char *)(unsigned int)v7,
    (int)v30.Reserved.Reserved1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003f590  mov     [rsp-28h+arg_18], rbx
0x14003f595  push    rbp
0x14003f596  push    rsi
0x14003f597  push    rdi
0x14003f598  push    r14
0x14003f59a  push    r15
0x14003f59c  mov     rbp, rsp
0x14003f59f  sub     rsp, 80h
0x14003f5a6  mov     rax, cs:__security_cookie
0x14003f5ad  xor     rax, rsp
0x14003f5b0  mov     [rbp+var_8], rax
0x14003f5b4  mov     rsi, r8
0x14003f5b7  mov     r14, rdx
0x14003f5ba  mov     rdi, rcx
0x14003f5bd  xor     r15d, r15d
0x14003f5c0  cmp     [rcx], r15
0x14003f5c3  jnz     short loc_14003F5E6
0x14003f5c5  lea     edx, [r15+34h]; void *
0x14003f5c9  mov     ebx, 80004003h
0x14003f5ce  mov     rcx, [rbp+28h]; this
0x14003f5d2  mov     r9d, ebx; char *
0x14003f5d5  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f5dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f5e1  jmp     loc_14003F940
0x14003f5e6  test    r14, r14
0x14003f5e9  jnz     short loc_14003F5F5
0x14003f5eb  test    rsi, rsi
0x14003f5ee  jnz     short loc_14003F5FD
0x14003f5f0  lea     edx, [rsi+37h]
0x14003f5f3  jmp     short loc_14003F5C9
0x14003f5f5  mov     [rdx], r15
0x14003f5f8  test    rsi, rsi
0x14003f5fb  jz      short loc_14003F600
0x14003f5fd  mov     [r8], r15
0x14003f600  mov     [rbp+var_28], r15d
0x14003f604  mov     rcx, [rcx]
0x14003f607  mov     rax, [rcx]
0x14003f60a  lea     rdx, [rbp+var_28]
0x14003f60e  mov     rax, [rax+38h]
0x14003f612  call    _guard_dispatch_icall
0x14003f617  mov     ebx, eax
0x14003f619  test    eax, eax
0x14003f61b  jns     short loc_14003F624
0x14003f61d  mov     edx, 44h ; 'D'
0x14003f622  jmp     short loc_14003F5CE
0x14003f624  mov     ecx, [rbp+var_28]
0x14003f627  test    ecx, ecx
0x14003f629  jz      loc_14003F6F0
0x14003f62f  sub     ecx, 1
0x14003f632  jz      loc_14003F6E6
0x14003f638  sub     ecx, 2
0x14003f63b  jz      loc_14003F6DC
0x14003f641  cmp     ecx, 2
0x14003f644  jz      short loc_14003F650
0x14003f646  mov     eax, 8000FFFFh
0x14003f64b  jmp     loc_14003F942
0x14003f650  mov     [rbp+var_10], r15
0x14003f654  mov     rcx, [rdi]
0x14003f657  mov     rax, [rcx]
0x14003f65a  lea     rdx, [rbp+var_10]
0x14003f65e  mov     rax, [rax+40h]
0x14003f662  call    _guard_dispatch_icall
0x14003f667  mov     ebx, eax
0x14003f669  test    eax, eax
0x14003f66b  jns     short loc_14003F674
0x14003f66d  mov     edx, 56h ; 'V'
0x14003f672  jmp     short loc_14003F697
0x14003f674  mov     dword ptr [rbp+var_38], r15d
0x14003f678  mov     rcx, [rbp+var_10]
0x14003f67c  mov     rax, [rcx]
0x14003f67f  lea     rdx, [rbp+var_38]
0x14003f683  mov     rax, [rax+30h]
0x14003f687  call    _guard_dispatch_icall
0x14003f68c  mov     ebx, eax
0x14003f68e  test    eax, eax
0x14003f690  jns     short loc_14003F6AC
0x14003f692  mov     edx, 59h ; 'Y'; void *
0x14003f697  mov     rcx, [rbp+28h]; this
0x14003f69b  mov     r9d, ebx; char *
0x14003f69e  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f6a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f6aa  jmp     short loc_14003F6BD
0x14003f6ac  mov     eax, dword ptr [rbp+var_38]
0x14003f6af  movzx   ebx, ax
0x14003f6b2  or      ebx, 80070000h
0x14003f6b8  test    eax, eax
0x14003f6ba  cmovle  ebx, eax
0x14003f6bd  mov     rcx, [rbp+var_10]
0x14003f6c1  test    rcx, rcx
0x14003f6c4  jz      short loc_14003F6D7
0x14003f6c6  mov     [rbp+var_10], r15
0x14003f6ca  mov     rdx, [rcx]
0x14003f6cd  mov     rax, [rdx+10h]
0x14003f6d1  call    _guard_dispatch_icall
0x14003f6d6  nop
0x14003f6d7  jmp     loc_14003F940
0x14003f6dc  mov     eax, 80070525h
0x14003f6e1  jmp     loc_14003F942
0x14003f6e6  mov     eax, 800704C7h
0x14003f6eb  jmp     loc_14003F942
0x14003f6f0  mov     [rbp+var_18], r15
0x14003f6f4  mov     rcx, [rdi]
0x14003f6f7  mov     rax, [rcx]
0x14003f6fa  lea     rdx, [rbp+var_18]
0x14003f6fe  mov     rax, [rax+30h]
0x14003f702  call    _guard_dispatch_icall
0x14003f707  mov     ebx, eax
0x14003f709  test    eax, eax
0x14003f70b  jns     short loc_14003F714
0x14003f70d  mov     edx, 63h ; 'c'
0x14003f712  jmp     short loc_14003F737
0x14003f714  mov     [rbp+var_24], r15d
0x14003f718  mov     rcx, [rbp+var_18]
0x14003f71c  mov     rax, [rcx]
0x14003f71f  lea     rdx, [rbp+var_24]
0x14003f723  mov     rax, [rax+38h]
0x14003f727  call    _guard_dispatch_icall
0x14003f72c  mov     ebx, eax
0x14003f72e  test    eax, eax
0x14003f730  jns     short loc_14003F74F
0x14003f732  mov     edx, 66h ; 'f'; void *
0x14003f737  mov     rcx, [rbp+28h]; this
0x14003f73b  mov     r9d, ebx; char *
0x14003f73e  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f74a  jmp     loc_14003F926
0x14003f74f  mov     [rbp+var_20], r15
0x14003f753  mov     [rbp+string], r15
0x14003f757  cmp     [rbp+var_24], r15d
0x14003f75b  jbe     loc_14003F8E0
0x14003f761  mov     rcx, [rbp+var_18]
0x14003f765  mov     rax, [rcx]
0x14003f768  lea     r8, [rbp+var_20]
0x14003f76c  xor     edx, edx
0x14003f76e  mov     rax, [rax+30h]
0x14003f772  call    _guard_dispatch_icall
0x14003f777  mov     ebx, eax
0x14003f779  test    eax, eax
0x14003f77b  jns     short loc_14003F787
0x14003f77d  mov     edx, 6Dh ; 'm'
0x14003f782  jmp     loc_14003F8EA
0x14003f787  mov     rbx, [rbp+var_20]
0x14003f78b  mov     rax, [rbx]
0x14003f78e  mov     rdi, [rax+30h]
0x14003f792  mov     rcx, [rbp+string]; string
0x14003f796  call    cs:__imp_WindowsDeleteString
0x14003f79c  mov     [rbp+string], r15
0x14003f7a0  lea     rdx, [rbp+string]
0x14003f7a4  mov     rcx, rbx
0x14003f7a7  mov     rax, rdi
0x14003f7aa  call    _guard_dispatch_icall
0x14003f7af  mov     ebx, eax
0x14003f7b1  test    eax, eax
0x14003f7b3  jns     short loc_14003F7BF
0x14003f7b5  mov     edx, 6Eh ; 'n'
0x14003f7ba  jmp     loc_14003F8EA
0x14003f7bf  test    r14, r14
0x14003f7c2  jz      short loc_14003F7E1
0x14003f7c4  mov     rdx, r14; newString
0x14003f7c7  mov     rcx, [rbp+string]; string
0x14003f7cb  call    cs:__imp_WindowsDuplicateString
0x14003f7d1  mov     ebx, eax
0x14003f7d3  test    eax, eax
0x14003f7d5  jns     short loc_14003F7E1
0x14003f7d7  mov     edx, 77h ; 'w'
0x14003f7dc  jmp     loc_14003F8EA
0x14003f7e1  test    rsi, rsi
0x14003f7e4  jz      loc_14003F8DB
0x14003f7ea  mov     [rbp+var_38], r15
0x14003f7ee  mov     rcx, [rbp+var_20]
0x14003f7f2  mov     rax, [rcx]
0x14003f7f5  lea     rdx, [rbp+var_38]
0x14003f7f9  mov     rax, [rax+48h]
0x14003f7fd  call    _guard_dispatch_icall
0x14003f802  mov     ebx, eax
0x14003f804  test    eax, eax
0x14003f806  jns     short loc_14003F80F
0x14003f808  mov     edx, 7Dh ; '}'
0x14003f80d  jmp     short loc_14003F84D
0x14003f80f  mov     [rbp+var_40], r15b
0x14003f813  mov     rbx, [rbp+var_38]
0x14003f817  mov     rax, [rbx]
0x14003f81a  mov     rdi, [rax+40h]
0x14003f81e  lea     rdx, off_14006F218; "xms_tdbr"
0x14003f825  lea     rcx, [rbp+var_60]
0x14003f829  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003f82e  nop
0x14003f82f  lea     r8, [rbp+var_40]
0x14003f833  mov     rdx, [rax+18h]
0x14003f837  mov     rcx, rbx
0x14003f83a  mov     rax, rdi
0x14003f83d  call    _guard_dispatch_icall
0x14003f842  mov     ebx, eax
0x14003f844  test    eax, eax
0x14003f846  jns     short loc_14003F852
0x14003f848  mov     edx, 80h
0x14003f84d  mov     r9d, ebx
0x14003f850  jmp     short loc_14003F894
0x14003f852  cmp     [rbp+var_40], r15b
0x14003f856  jz      short loc_14003F8C1
0x14003f858  mov     rbx, [rbp+var_38]
0x14003f85c  mov     rax, [rbx]
0x14003f85f  mov     rdi, [rax+30h]
0x14003f863  lea     rdx, off_14006F218; "xms_tdbr"
0x14003f86a  lea     rcx, [rbp+var_60]
0x14003f86e  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x14003f873  nop
0x14003f874  mov     r8, rsi
0x14003f877  mov     rdx, [rax+18h]
0x14003f87b  mov     rcx, rbx
0x14003f87e  mov     rax, rdi
0x14003f881  call    _guard_dispatch_icall
0x14003f886  mov     ebx, eax
0x14003f888  test    eax, eax
0x14003f88a  jns     short loc_14003F8C1
0x14003f88c  mov     r9d, eax; char *
0x14003f88f  mov     edx, 84h; void *
0x14003f894  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f89b  mov     rcx, [rbp+28h]; this
0x14003f89f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f8a4  nop
0x14003f8a5  mov     rcx, [rbp+var_38]
0x14003f8a9  test    rcx, rcx
0x14003f8ac  jz      short loc_14003F8BF
0x14003f8ae  mov     [rbp+var_38], r15
0x14003f8b2  mov     rax, [rcx]
0x14003f8b5  mov     rax, [rax+10h]
0x14003f8b9  call    _guard_dispatch_icall
0x14003f8be  nop
0x14003f8bf  jmp     short loc_14003F8FE
0x14003f8c1  mov     rcx, [rbp+var_38]
0x14003f8c5  test    rcx, rcx
0x14003f8c8  jz      short loc_14003F8DB
0x14003f8ca  mov     [rbp+var_38], r15
0x14003f8ce  mov     rax, [rcx]
0x14003f8d1  mov     rax, [rax+10h]
0x14003f8d5  call    _guard_dispatch_icall
0x14003f8da  nop
0x14003f8db  mov     ebx, r15d
0x14003f8de  jmp     short loc_14003F8FE
0x14003f8e0  mov     ebx, 80004005h
0x14003f8e5  mov     edx, 72h ; 'r'; void *
0x14003f8ea  mov     rcx, [rbp+28h]; this
0x14003f8ee  mov     r9d, ebx; char *
0x14003f8f1  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003f8f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f8fd  nop
0x14003f8fe  mov     rcx, [rbp+string]; string
0x14003f902  call    cs:__imp_WindowsDeleteString
0x14003f908  mov     [rbp+string], r15
0x14003f90c  mov     rcx, [rbp+var_20]
0x14003f910  test    rcx, rcx
0x14003f913  jz      short loc_14003F926
0x14003f915  mov     [rbp+var_20], r15
0x14003f919  mov     rax, [rcx]
0x14003f91c  mov     rax, [rax+10h]
0x14003f920  call    _guard_dispatch_icall
0x14003f925  nop
0x14003f926  mov     rcx, [rbp+var_18]
0x14003f92a  test    rcx, rcx
0x14003f92d  jz      short loc_14003F940
0x14003f92f  mov     [rbp+var_18], r15
0x14003f933  mov     rdx, [rcx]
0x14003f936  mov     rax, [rdx+10h]
0x14003f93a  call    _guard_dispatch_icall
0x14003f93f  nop
0x14003f940  mov     eax, ebx
0x14003f942  mov     rcx, [rbp+var_8]
0x14003f946  xor     rcx, rsp; StackCookie
0x14003f949  call    __security_check_cookie
0x14003f94e  mov     rbx, [rsp+80h+arg_18]
0x14003f956  add     rsp, 80h
0x14003f95d  pop     r15
0x14003f95f  pop     r14
0x14003f961  pop     rdi
0x14003f962  pop     rsi
0x14003f963  pop     rbp
0x14003f964  retn
```
