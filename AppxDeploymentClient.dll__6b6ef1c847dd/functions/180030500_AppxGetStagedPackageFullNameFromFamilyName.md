# AppxGetStagedPackageFullNameFromFamilyName

- ea: `0x180030500`
- end: `0x180030c10`
- name: `AppxGetStagedPackageFullNameFromFamilyName`
- size: `1808`
- prototype: `__int64 __fastcall(__int64, __int64, UINT32 *, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000b614`
- `0x18000b644`
- `0x180017630`
- `0x180020d70`
- `0x180026e00`
- `0x180030500`
- `0x180031168`
- `0x180051870`
- `0x1800863b4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800305d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003071d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003075d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800308a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800305d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003071d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003075d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800308a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030b4c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003053e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003053e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800305eb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003067e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180030be5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800305eb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003067e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180030be5`

## pseudocode

```c
__int64 __fastcall AppxGetStagedPackageFullNameFromFamilyName(__int64 a1, __int64 a2, UINT32 *a3, _DWORD *a4)
{
  HSTRING v4; // r15
  int v8; // eax
  unsigned int v9; // ebx
  HSTRING v11; // r14
  __int64 v12; // r8
  int v13; // eax
  __int64 (__fastcall *v14)(HSTRING, HSTRING, __int64, __int64 *); // rdi
  HSTRING v15; // rbx
  int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, __int64 **); // rdi
  __int64 v20; // rax
  int v21; // eax
  __int64 *v22; // rsi
  __int64 (__fastcall *v23)(__int64 *, __int64 *); // rdi
  int v24; // eax
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rdi
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rdi
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, HSTRING, __int64 *); // rdi
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, __int64, __int64 *); // rdi
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, _QWORD, HSTRING *); // rdi
  int v40; // eax
  __int64 v41; // rdx
  HSTRING v42; // rsi
  __int64 (__fastcall *v43)(HSTRING, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  UINT32 v45; // ecx
  __int64 v46; // r9
  HSTRING v47; // [rsp+30h] [rbp-89h] BYREF
  char v48[8]; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v49; // [rsp+40h] [rbp-79h] BYREF
  __int64 v50; // [rsp+48h] [rbp-71h] BYREF
  __int64 v51; // [rsp+50h] [rbp-69h] BYREF
  __int64 v52; // [rsp+58h] [rbp-61h] BYREF
  __int64 v53; // [rsp+60h] [rbp-59h] BYREF
  HSTRING string; // [rsp+68h] [rbp-51h] BYREF
  __int64 v55; // [rsp+70h] [rbp-49h] BYREF
  __int64 v56; // [rsp+78h] [rbp-41h] BYREF
  __int64 v57; // [rsp+80h] [rbp-39h] BYREF
  UINT32 length; // [rsp+88h] [rbp-31h] BYREF
  int v59; // [rsp+8Ch] [rbp-2Dh] BYREF
  __int64 v60; // [rsp+90h] [rbp-29h] BYREF
  __int64 v61; // [rsp+98h] [rbp-21h] BYREF
  UINT32 *v62; // [rsp+A0h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v64; // [rsp+C0h] [rbp+7h]
  void *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = 0;
  v62 = a3;
  *a4 = 0;
  v8 = RoInitialize(1);
  v9 = v8;
  if ( v8 < 0 )
  {
    sub_18000B614(retaddr, 158, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v8);
    return v9;
  }
  *(_WORD *)(*(_QWORD *)&qword_1801534C8 + 8LL) = 257;
  sub_1800863B4(&string);
  v11 = string;
  if ( string )
  {
    string = 0;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a1 + 2 * v12) );
    v13 = sub_180031168(&string, a1, v12);
    v9 = v13;
    if ( v13 < 0 )
    {
      sub_18000B614(retaddr, 171, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v13);
      if ( string )
        WindowsDeleteString(string);
      if ( v11 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
      RoUninitialize();
      return v9;
    }
    v50 = 0;
    v49 = 0;
    v14 = *(__int64 (__fastcall **)(HSTRING, HSTRING, __int64, __int64 *))(*((_QWORD *)v11 + 2) + 104LL);
    sub_18000B644(&v50);
    v15 = string;
    v16 = v14(v11 + 4, string, 35, &v50);
    if ( v16 < 0 )
    {
      v17 = 178;
LABEL_15:
      sub_18000B614(retaddr, v17, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v16);
LABEL_16:
      sub_18000B644(&v49);
      sub_18000B644(&v50);
      if ( v15 )
        WindowsDeleteString(v15);
      if ( v11 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_20:
      RoUninitialize();
      return (unsigned int)v16;
    }
    v18 = v50;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v50 + 48LL);
    sub_18000B644(&v49);
    v16 = v19(v18, &v49);
    if ( v16 < 0 )
    {
      v17 = 179;
      goto LABEL_15;
    }
    v52 = 0;
    v51 = 0;
    v60 = 0;
    v47 = 0;
    v48[0] = 0;
    v20 = *v49;
    v53 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, char *))(v20 + 56))(v49, v48);
    v16 = v21;
    if ( v21 < 0 )
    {
      sub_18000B614(retaddr, 190, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v21);
      goto LABEL_79;
    }
    if ( !v48[0] )
    {
      WindowsDeleteString(v47);
      v47 = 0;
      sub_18000B644(&v51);
      sub_18000B644(&v52);
      sub_18000B644(&v53);
      sub_18000B644(&v49);
      sub_18000B644(&v50);
      if ( v15 )
        WindowsDeleteString(v15);
      if ( v11 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
      v16 = -2147024809;
      goto LABEL_20;
    }
    do
    {
      v22 = v49;
      v23 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(*v49 + 48);
      sub_18000B644(&v52);
      v24 = v23(v22, &v52);
      v16 = v24;
      if ( v24 < 0 )
      {
        v29 = 197;
        goto LABEL_41;
      }
      v25 = v52;
      v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL);
      sub_18000B644(&v51);
      v24 = v26(v25, &v51);
      v16 = v24;
      if ( v24 < 0 )
      {
        v29 = 199;
        goto LABEL_41;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 56LL))(v51, &v60);
      v16 = v24;
      if ( v24 < 0 )
      {
        v29 = 200;
        goto LABEL_41;
      }
      LOWORD(string) = HIWORD(v60);
      WORD1(string) = WORD2(v60);
      WORD2(string) = WORD1(v60);
      HIWORD(string) = v60;
      if ( string > v4 )
      {
        v27 = v51;
        v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 96LL);
        WindowsDeleteString(v47);
        v47 = 0;
        v24 = v28(v27, &v47);
        v16 = v24;
        if ( v24 < 0 )
        {
          v29 = 205;
LABEL_41:
          sub_18000B614(
            retaddr,
            v29,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v24);
          WindowsDeleteString(v47);
          v47 = 0;
          goto LABEL_80;
        }
        v4 = string;
      }
      v24 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v49 + 64))(v49, v48);
      v16 = v24;
      if ( v24 < 0 )
      {
        v29 = 210;
        goto LABEL_41;
      }
    }
    while ( v48[0] );
    v56 = 0;
    v55 = 0;
    v61 = 0;
    v64 = 0;
    sub_180020D70(&hstringHeader, L"Windows.Internal.StateRepository.Package");
    v30 = sub_180026E00(v64, &v56);
    v16 = v30;
    if ( v30 < 0 )
    {
      v31 = 224;
      goto LABEL_76;
    }
    v32 = v56;
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v56 + 176LL);
    sub_18000B644(&v55);
    v30 = v33(v32, v47, &v55);
    v16 = v30;
    if ( v30 < 0 )
    {
      v31 = 226;
      goto LABEL_76;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 1032LL))(v55, &v61);
    v16 = v30;
    if ( v30 < 0 )
    {
      v31 = 227;
      goto LABEL_76;
    }
    if ( v61 )
    {
      v34 = v56;
      v57 = 0;
      v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v56 + 264LL);
      sub_18000B644(&v57);
      v36 = v35(v34, v61, 8, &v57);
      v16 = v36;
      if ( v36 < 0 )
      {
        v37 = 236;
LABEL_55:
        sub_18000B614(retaddr, v37, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v36);
LABEL_56:
        sub_18000B644(&v57);
LABEL_78:
        sub_18000B644(&v55);
        sub_18000B644(&v56);
LABEL_79:
        WindowsDeleteString(v47);
        v47 = 0;
LABEL_80:
        sub_18000B644(&v51);
        sub_18000B644(&v52);
        sub_18000B644(&v53);
        goto LABEL_16;
      }
      v59 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v57 + 56LL))(v57, &v59);
      v16 = v36;
      if ( v36 < 0 )
      {
        v37 = 239;
        goto LABEL_55;
      }
      if ( !v59 )
      {
        sub_18000B644(&v57);
        sub_18000B644(&v55);
        sub_18000B644(&v56);
        WindowsDeleteString(v47);
        v47 = 0;
        sub_18000B644(&v51);
        sub_18000B644(&v52);
        sub_18000B644(&v53);
        sub_18000B644(&v49);
        sub_18000B644(&v50);
        if ( v15 )
          WindowsDeleteString(v15);
        if ( v11 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
        v16 = -2147023728;
        goto LABEL_20;
      }
      v38 = v57;
      string = 0;
      v39 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v57 + 48LL);
      sub_18000B644(&string);
      v40 = v39(v38, 0, &string);
      v16 = v40;
      if ( v40 < 0 )
      {
        v41 = 244;
LABEL_67:
        sub_18000B614(retaddr, v41, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v40);
        sub_18000B644(&string);
        goto LABEL_56;
      }
      v42 = string;
      v43 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 112LL);
      WindowsDeleteString(v47);
      v47 = 0;
      v40 = v43(v42, &v47);
      v16 = v40;
      if ( v40 < 0 )
      {
        v41 = 246;
        goto LABEL_67;
      }
      *a4 = 1;
      sub_18000B644(&string);
      sub_18000B644(&v57);
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v47, &length);
    v45 = length + 1;
    length = v45;
    if ( *v62 < v45 )
    {
      v16 = -2147024774;
      *v62 = v45;
      v46 = 2147942522LL;
      v31 = 258;
LABEL_77:
      sub_18000B614(retaddr, v31, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v46);
      goto LABEL_78;
    }
    if ( !a2 )
      goto LABEL_78;
    v30 = sub_180017630(a2, *v62, StringRawBuffer);
    v16 = v30;
    if ( v30 >= 0 )
      goto LABEL_78;
    v31 = 263;
LABEL_76:
    v46 = (unsigned int)v30;
    goto LABEL_77;
  }
  RoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x180030500  push    rbp
0x180030502  push    rbx
0x180030503  push    rsi
0x180030504  push    rdi
0x180030505  push    r12
0x180030507  push    r13
0x180030509  push    r14
0x18003050b  push    r15
0x18003050d  lea     rbp, [rsp-1Fh]
0x180030512  sub     rsp, 0D8h
0x180030519  mov     rax, cs:__security_cookie
0x180030520  xor     rax, rsp
0x180030523  mov     [rbp+57h+var_48], rax
0x180030527  xor     r15d, r15d
0x18003052a  mov     [rbp+57h+var_70], r8
0x18003052e  mov     rdi, rcx
0x180030531  mov     [r9], r15d
0x180030534  mov     r13, r9
0x180030537  mov     r12, rdx
0x18003053a  lea     ecx, [r15+1]
0x18003053e  call    cs:RoInitialize
0x180030544  mov     ebx, eax
0x180030546  test    eax, eax
0x180030548  jns     short loc_180030569
0x18003054a  mov     rcx, [rbp+5Fh]
0x18003054e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180030555  mov     r9d, eax
0x180030558  mov     edx, 9Eh
0x18003055d  call    sub_18000B614
0x180030562  mov     eax, ebx
0x180030564  jmp     loc_180030BF0
0x180030569  mov     rax, cs:qword_1801534C8
0x180030570  lea     rcx, [rbp+57h+string]
0x180030574  mov     word ptr [rax+8], 101h
0x18003057a  call    sub_1800863B4
0x18003057f  mov     r14, [rbp+57h+string]
0x180030583  test    r14, r14
0x180030586  jz      loc_180030BE5
0x18003058c  mov     [rbp+57h+string], r15
0x180030590  or      r8, 0FFFFFFFFFFFFFFFFh
0x180030594  inc     r8
0x180030597  cmp     [rdi+r8*2], r15w
0x18003059c  jnz     short loc_180030594
0x18003059e  mov     rdx, rdi
0x1800305a1  lea     rcx, [rbp+57h+string]
0x1800305a5  call    sub_180031168
0x1800305aa  mov     ebx, eax
0x1800305ac  test    eax, eax
0x1800305ae  jns     short loc_1800305F6
0x1800305b0  mov     rcx, [rbp+5Fh]
0x1800305b4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x1800305bb  mov     r9d, eax
0x1800305be  mov     edx, 0ABh
0x1800305c3  call    sub_18000B614
0x1800305c8  mov     rcx, [rbp+57h+string]; string
0x1800305cc  test    rcx, rcx
0x1800305cf  jz      short loc_1800305D7
0x1800305d1  call    cs:WindowsDeleteString
0x1800305d7  test    r14, r14
0x1800305da  jz      short loc_1800305EB
0x1800305dc  mov     rax, [r14]
0x1800305df  mov     rcx, r14
0x1800305e2  mov     rax, [rax+10h]
0x1800305e6  call    j__guard_dispatch_icall
0x1800305eb  call    cs:RoUninitialize
0x1800305f1  jmp     loc_180030562
0x1800305f6  mov     [rbp+57h+var_C8], r15
0x1800305fa  lea     rcx, [rbp+57h+var_C8]
0x1800305fe  mov     [rbp+57h+var_D0], r15
0x180030602  mov     rax, [r14+10h]
0x180030606  mov     rdi, [rax+68h]
0x18003060a  call    sub_18000B644
0x18003060f  mov     rbx, [rbp+57h+string]
0x180030613  lea     r9, [rbp+57h+var_C8]
0x180030617  mov     rdx, rbx
0x18003061a  lea     rcx, [r14+10h]
0x18003061e  mov     r8d, 23h ; '#'
0x180030624  mov     rax, rdi
0x180030627  call    j__guard_dispatch_icall
0x18003062c  mov     edi, eax
0x18003062e  test    eax, eax
0x180030630  jns     short loc_18003068B
0x180030632  mov     edx, 0B2h
0x180030637  mov     rcx, [rbp+5Fh]
0x18003063b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180030642  mov     r9d, edi
0x180030645  call    sub_18000B614
0x18003064a  lea     rcx, [rbp+57h+var_D0]
0x18003064e  call    sub_18000B644
0x180030653  lea     rcx, [rbp+57h+var_C8]
0x180030657  call    sub_18000B644
0x18003065c  test    rbx, rbx
0x18003065f  jz      short loc_18003066A
0x180030661  mov     rcx, rbx; string
0x180030664  call    cs:WindowsDeleteString
0x18003066a  test    r14, r14
0x18003066d  jz      short loc_18003067E
0x18003066f  mov     rax, [r14]
0x180030672  mov     rcx, r14
0x180030675  mov     rax, [rax+10h]
0x180030679  call    j__guard_dispatch_icall
0x18003067e  call    cs:RoUninitialize
0x180030684  mov     eax, edi
0x180030686  jmp     loc_180030BF0
0x18003068b  mov     rsi, [rbp+57h+var_C8]
0x18003068f  lea     rcx, [rbp+57h+var_D0]
0x180030693  mov     rax, [rsi]
0x180030696  mov     rdi, [rax+30h]
0x18003069a  call    sub_18000B644
0x18003069f  lea     rdx, [rbp+57h+var_D0]
0x1800306a3  mov     rcx, rsi
0x1800306a6  mov     rax, rdi
0x1800306a9  call    j__guard_dispatch_icall
0x1800306ae  mov     edi, eax
0x1800306b0  test    eax, eax
0x1800306b2  jns     short loc_1800306BE
0x1800306b4  mov     edx, 0B3h
0x1800306b9  jmp     loc_180030637
0x1800306be  mov     rcx, [rbp+57h+var_D0]
0x1800306c2  lea     rdx, [rsp+110h+var_D8]
0x1800306c7  mov     [rbp+57h+var_B8], r15
0x1800306cb  mov     [rbp+57h+var_C0], r15
0x1800306cf  mov     [rbp+57h+var_80], r15
0x1800306d3  mov     [rsp+110h+var_E0], r15
0x1800306d8  mov     [rsp+110h+var_D8], r15b
0x1800306dd  mov     rax, [rcx]
0x1800306e0  mov     [rbp+57h+var_B0], r15
0x1800306e4  mov     rax, [rax+38h]
0x1800306e8  call    j__guard_dispatch_icall
0x1800306ed  mov     edi, eax
0x1800306ef  test    eax, eax
0x1800306f1  jns     short loc_180030710
0x1800306f3  mov     rcx, [rbp+5Fh]
0x1800306f7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x1800306fe  mov     r9d, eax
0x180030701  mov     edx, 0BEh
0x180030706  call    sub_18000B614
0x18003070b  jmp     loc_180030BB5
0x180030710  mov     al, [rsp+110h+var_D8]
0x180030714  test    al, al
0x180030716  jnz     short loc_180030789
0x180030718  mov     rcx, [rsp+110h+var_E0]; string
0x18003071d  call    cs:WindowsDeleteString
0x180030723  lea     rcx, [rbp+57h+var_C0]
0x180030727  mov     [rsp+110h+var_E0], r15
0x18003072c  call    sub_18000B644
0x180030731  lea     rcx, [rbp+57h+var_B8]
0x180030735  call    sub_18000B644
0x18003073a  lea     rcx, [rbp+57h+var_B0]
0x18003073e  call    sub_18000B644
0x180030743  lea     rcx, [rbp+57h+var_D0]
0x180030747  call    sub_18000B644
0x18003074c  lea     rcx, [rbp+57h+var_C8]
0x180030750  call    sub_18000B644
0x180030755  test    rbx, rbx
0x180030758  jz      short loc_180030763
0x18003075a  mov     rcx, rbx; string
0x18003075d  call    cs:WindowsDeleteString
0x180030763  test    r14, r14
0x180030766  jz      short loc_180030777
0x180030768  mov     rax, [r14]
0x18003076b  mov     rcx, r14
0x18003076e  mov     rax, [rax+10h]
0x180030772  call    j__guard_dispatch_icall
0x180030777  mov     edi, 80070057h
0x18003077c  jmp     loc_18003067E
0x180030781  test    al, al
0x180030783  jz      loc_1800308D1
0x180030789  mov     rsi, [rbp+57h+var_D0]
0x18003078d  lea     rcx, [rbp+57h+var_B8]
0x180030791  mov     rax, [rsi]
0x180030794  mov     rdi, [rax+30h]
0x180030798  call    sub_18000B644
0x18003079d  lea     rdx, [rbp+57h+var_B8]
0x1800307a1  mov     rcx, rsi
0x1800307a4  mov     rax, rdi
0x1800307a7  call    j__guard_dispatch_icall
0x1800307ac  mov     edi, eax
0x1800307ae  test    eax, eax
0x1800307b0  js      loc_1800308CA
0x1800307b6  mov     rsi, [rbp+57h+var_B8]
0x1800307ba  lea     rcx, [rbp+57h+var_C0]
0x1800307be  mov     rax, [rsi]
0x1800307c1  mov     rdi, [rax+30h]
0x1800307c5  call    sub_18000B644
0x1800307ca  lea     rdx, [rbp+57h+var_C0]
0x1800307ce  mov     rcx, rsi
0x1800307d1  mov     rax, rdi
0x1800307d4  call    j__guard_dispatch_icall
0x1800307d9  mov     edi, eax
0x1800307db  test    eax, eax
0x1800307dd  js      loc_1800308C3
0x1800307e3  mov     rcx, [rbp+57h+var_C0]
0x1800307e7  lea     rdx, [rbp+57h+var_80]
0x1800307eb  mov     rax, [rcx]
0x1800307ee  mov     rax, [rax+38h]
0x1800307f2  call    j__guard_dispatch_icall
0x1800307f7  mov     edi, eax
0x1800307f9  test    eax, eax
0x1800307fb  js      loc_1800308BC
0x180030801  movzx   eax, word ptr [rbp+57h+var_80+6]
0x180030805  mov     word ptr [rbp+57h+string], ax
0x180030809  movzx   eax, word ptr [rbp+57h+var_80+4]
0x18003080d  mov     word ptr [rbp+57h+string+2], ax
0x180030811  movzx   eax, word ptr [rbp+57h+var_80+2]
0x180030815  mov     word ptr [rbp+57h+string+4], ax
0x180030819  movzx   eax, word ptr [rbp+57h+var_80]
0x18003081d  mov     word ptr [rbp+57h+string+6], ax
0x180030821  cmp     [rbp+57h+string], r15
0x180030825  jbe     short loc_180030860
0x180030827  mov     rsi, [rbp+57h+var_C0]
0x18003082b  mov     rcx, [rsp+110h+var_E0]; string
0x180030830  mov     rax, [rsi]
0x180030833  mov     rdi, [rax+60h]
0x180030837  call    cs:WindowsDeleteString
0x18003083d  lea     rdx, [rsp+110h+var_E0]
0x180030842  mov     [rsp+110h+var_E0], 0
0x18003084b  mov     rcx, rsi
0x18003084e  mov     rax, rdi
0x180030851  call    j__guard_dispatch_icall
0x180030856  mov     edi, eax
0x180030858  test    eax, eax
0x18003085a  js      short loc_180030884
0x18003085c  mov     r15, [rbp+57h+string]
0x180030860  mov     rcx, [rbp+57h+var_D0]
0x180030864  lea     rdx, [rsp+110h+var_D8]
0x180030869  mov     rax, [rcx]
0x18003086c  mov     rax, [rax+40h]
0x180030870  call    j__guard_dispatch_icall
0x180030875  mov     edi, eax
0x180030877  test    eax, eax
0x180030879  js      short loc_1800308B5
0x18003087b  mov     al, [rsp+110h+var_D8]
0x18003087f  jmp     loc_180030781
0x180030884  mov     edx, 0CDh
0x180030889  mov     rcx, [rbp+5Fh]
0x18003088d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180030894  mov     r9d, eax
0x180030897  call    sub_18000B614
0x18003089c  mov     rcx, [rsp+110h+var_E0]; string
0x1800308a1  call    cs:WindowsDeleteString
0x1800308a7  mov     [rsp+110h+var_E0], 0
0x1800308b0  jmp     loc_180030BC5
0x1800308b5  mov     edx, 0D2h
0x1800308ba  jmp     short loc_180030889
0x1800308bc  mov     edx, 0C8h
0x1800308c1  jmp     short loc_180030889
0x1800308c3  mov     edx, 0C7h
0x1800308c8  jmp     short loc_180030889
0x1800308ca  mov     edx, 0C5h
0x1800308cf  jmp     short loc_180030889
0x1800308d1  xor     r15d, r15d
0x1800308d4  lea     rdx, aWindowsInterna_0; "Windows.Internal.StateRepository.Packag"...
0x1800308db  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800308df  mov     [rbp+57h+var_98], r15
0x1800308e3  mov     [rbp+57h+var_A0], r15
0x1800308e7  mov     [rbp+57h+var_78], r15
0x1800308eb  lea     r9d, [r15+28h]
0x1800308ef  mov     [rbp+57h+var_50], r15
0x1800308f3  lea     r8d, [r15+29h]
0x1800308f7  call    sub_180020D70
0x1800308fc  mov     rcx, [rbp+57h+var_50]
0x180030900  lea     rdx, [rbp+57h+var_98]
0x180030904  call    sub_180026E00
0x180030909  mov     edi, eax
0x18003090b  test    eax, eax
0x18003090d  jns     short loc_180030919
0x18003090f  mov     edx, 0E0h
0x180030914  jmp     loc_180030B90
0x180030919  mov     rsi, [rbp+57h+var_98]
0x18003091d  lea     rcx, [rbp+57h+var_A0]
0x180030921  mov     rax, [rsi]
0x180030924  mov     rdi, [rax+0B0h]
0x18003092b  call    sub_18000B644
0x180030930  mov     rdx, [rsp+110h+var_E0]
0x180030935  lea     r8, [rbp+57h+var_A0]
0x180030939  mov     rcx, rsi
0x18003093c  mov     rax, rdi
0x18003093f  call    j__guard_dispatch_icall
0x180030944  mov     edi, eax
0x180030946  test    eax, eax
0x180030948  jns     short loc_180030954
0x18003094a  mov     edx, 0E2h
0x18003094f  jmp     loc_180030B90
0x180030954  mov     rcx, [rbp+57h+var_A0]
0x180030958  lea     rdx, [rbp+57h+var_78]
0x18003095c  mov     rax, [rcx]
0x18003095f  mov     rax, [rax+408h]
0x180030966  call    j__guard_dispatch_icall
0x18003096b  mov     edi, eax
0x18003096d  test    eax, eax
0x18003096f  jns     short loc_18003097B
0x180030971  mov     edx, 0E3h
0x180030976  jmp     loc_180030B90
0x18003097b  cmp     [rbp+57h+var_78], r15
0x18003097f  jz      loc_180030B3F
0x180030985  mov     rsi, [rbp+57h+var_98]
0x180030989  lea     rcx, [rbp+57h+var_90]
0x18003098d  mov     [rbp+57h+var_90], r15
0x180030991  mov     rax, [rsi]
  ... truncated ...
```
