# RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)

- ea: `0x1800262a4`
- end: `0x1800264d7`
- name: `?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z`
- size: `563`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *const)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800262a4`
- `0x180029548`
- `0x1800a5228`

## callees

- `0x18000cc8c`
- `0x18001cff8`
- `0x1800203c8`
- `0x180020c0c`
- `0x1800254ac`
- `0x180026278`
- `0x1800262a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026423`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026423`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180026368`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180026368`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026449`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002630d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800263c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002630d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800263c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegWow64Helpers::DeleteTree(HKEY a1, const unsigned __int16 *a2)
{
  HKEY *v4; // rax
  unsigned int v5; // r8d
  int v6; // ebx
  char v7; // r12
  HKEY v8; // r14
  WCHAR *v9; // rbx
  LSTATUS v10; // eax
  signed int v11; // edi
  int v12; // edi
  WCHAR *v14; // rbx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int lpReserved; // [rsp+20h] [rbp-38h]
  int lpReserveda; // [rsp+20h] [rbp-38h]
  HKEY hKey[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  DWORD cchName; // [rsp+A0h] [rbp+48h] BYREF
  DWORD cchValueName; // [rsp+A8h] [rbp+50h] BYREF
  WCHAR *v23; // [rsp+B0h] [rbp+58h] BYREF
  WCHAR *v24; // [rsp+B8h] [rbp+60h] BYREF

  hKey[0] = 0;
  if ( a2 && *a2 )
  {
    v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
    v6 = RegWow64Helpers::OpenKey(a1, a2, v5, 0xF003Fu, v4);
    if ( v6 < 0 )
    {
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
      return (unsigned int)v6;
    }
    v7 = 1;
    v8 = hKey[0];
  }
  else
  {
    v8 = a1;
    v7 = 0;
  }
  v9 = (WCHAR *)CoTaskMemAlloc(0x200u);
  v23 = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\internal\\base\\inc\\flighting\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserved);
LABEL_28:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
    goto LABEL_29;
  }
  while ( 1 )
  {
    cchName = 256;
    v10 = RegEnumKeyExW(v8, 0, v9, &cchName, 0, 0, 0, 0);
    v11 = v10;
    if ( v10 == 259 )
      break;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v11 < 0 )
    {
LABEL_14:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
      v6 = v11;
      goto LABEL_29;
    }
    v12 = RegWow64Helpers::DeleteTree(v8, v9);
    if ( v12 < 0 )
    {
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
      return (unsigned int)v12;
    }
  }
  v14 = (WCHAR *)CoTaskMemAlloc(0x7FFFu);
  v24 = v14;
  if ( !v14 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\internal\\base\\inc\\flighting\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserveda);
LABEL_27:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v24);
    goto LABEL_28;
  }
  while ( 1 )
  {
    cchValueName = 0x3FFF;
    v15 = RegEnumValueW(v8, 0, v14, &cchValueName, 0, 0, 0, 0);
    v11 = v15;
    if ( v15 == 259 )
      break;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
    {
      v16 = RegDeleteValueW(v8, v14);
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 >= 0 )
        continue;
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v24);
    goto LABEL_14;
  }
  if ( v7 )
  {
    v6 = RegWow64Helpers::DeleteKey(a1, a2);
    if ( v6 < 0 )
      goto LABEL_27;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v24);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800262a4  push    rbp
0x1800262a6  push    rbx
0x1800262a7  push    rsi
0x1800262a8  push    rdi
0x1800262a9  push    r12
0x1800262ab  push    r13
0x1800262ad  push    r14
0x1800262af  push    r15
0x1800262b1  mov     rbp, rsp
0x1800262b4  sub     rsp, 58h
0x1800262b8  mov     rsi, rdx
0x1800262bb  mov     r15, rcx
0x1800262be  xor     r13d, r13d
0x1800262c1  mov     [rbp+hKey], r13
0x1800262c5  test    rdx, rdx
0x1800262c8  jz      short loc_180026302
0x1800262ca  cmp     [rdx], r13w
0x1800262ce  jz      short loc_180026302
0x1800262d0  lea     rcx, [rbp+hKey]
0x1800262d4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800262d9  mov     [rsp+58h+lpReserved], rax; PHKEY
0x1800262de  mov     r9d, 0F003Fh; unsigned int
0x1800262e4  mov     rdx, rsi; unsigned __int16 *
0x1800262e7  mov     rcx, r15; HKEY
0x1800262ea  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x1800262ef  mov     ebx, eax
0x1800262f1  test    eax, eax
0x1800262f3  js      loc_18002649A
0x1800262f9  mov     r12b, 1
0x1800262fc  mov     r14, [rbp+hKey]
0x180026300  jmp     short loc_180026308
0x180026302  mov     r14, r15
0x180026305  mov     r12b, r13b
0x180026308  mov     ecx, 200h; cb
0x18002630d  call    cs:__imp_CoTaskMemAlloc
0x180026313  mov     rbx, rax
0x180026316  mov     [rbp+arg_10], rax
0x18002631a  test    rax, rax
0x18002631d  jnz     short loc_180026341
0x18002631f  mov     rcx, [rbp+40h]; this
0x180026323  mov     ebx, 8007000Eh
0x180026328  mov     r9d, ebx; char *
0x18002632b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\flighting"...
0x180026332  mov     edx, 232h; void *
0x180026337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002633c  jmp     loc_180026490
0x180026341  mov     [rbp+cchName], 100h
0x180026348  mov     [rsp+58h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002634d  mov     [rsp+58h+lpcchClass], r13; lpcchClass
0x180026352  mov     [rsp+58h+lpClass], r13; lpClass
0x180026357  mov     [rsp+58h+lpReserved], r13; int
0x18002635c  lea     r9, [rbp+cchName]; lpcchName
0x180026360  mov     r8, rbx; lpName
0x180026363  xor     edx, edx; dwIndex
0x180026365  mov     rcx, r14; hKey
0x180026368  call    cs:__imp_RegEnumKeyExW
0x18002636e  mov     edi, eax
0x180026370  cmp     eax, 103h
0x180026375  jz      short loc_1800263C3
0x180026377  test    eax, eax
0x180026379  jle     short loc_180026384
0x18002637b  movzx   edi, ax
0x18002637e  or      edi, 80070000h
0x180026384  test    edi, edi
0x180026386  js      short loc_1800263B3
0x180026388  mov     rdx, rbx; unsigned __int16 *
0x18002638b  mov     rcx, r14; HKEY
0x18002638e  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x180026393  mov     edi, eax
0x180026395  test    eax, eax
0x180026397  jns     short loc_180026341
0x180026399  lea     rcx, [rbp+arg_10]
0x18002639d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800263a2  nop
0x1800263a3  lea     rcx, [rbp+hKey]
0x1800263a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800263ac  mov     eax, edi
0x1800263ae  jmp     loc_1800264C6
0x1800263b3  lea     rcx, [rbp+arg_10]
0x1800263b7  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800263bc  mov     ebx, edi
0x1800263be  jmp     loc_18002649A
0x1800263c3  mov     ecx, 7FFFh; cb
0x1800263c8  call    cs:__imp_CoTaskMemAlloc
0x1800263ce  mov     rbx, rax
0x1800263d1  mov     [rbp+arg_18], rax
0x1800263d5  test    rax, rax
0x1800263d8  jnz     short loc_1800263FC
0x1800263da  mov     rcx, [rbp+40h]; this
0x1800263de  mov     ebx, 8007000Eh
0x1800263e3  mov     r9d, ebx; char *
0x1800263e6  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\flighting"...
0x1800263ed  mov     edx, 255h; void *
0x1800263f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263f7  jmp     loc_180026486
0x1800263fc  mov     [rbp+cchValueName], 3FFFh
0x180026403  mov     [rsp+58h+lpftLastWriteTime], r13; lpcbData
0x180026408  mov     [rsp+58h+lpcchClass], r13; lpData
0x18002640d  mov     [rsp+58h+lpClass], r13; lpType
0x180026412  mov     [rsp+58h+lpReserved], r13; lpReserved
0x180026417  lea     r9, [rbp+cchValueName]; lpcchValueName
0x18002641b  mov     r8, rbx; lpValueName
0x18002641e  xor     edx, edx; dwIndex
0x180026420  mov     rcx, r14; hKey
0x180026423  call    cs:__imp_RegEnumValueW
0x180026429  mov     edi, eax
0x18002642b  cmp     eax, 103h
0x180026430  jz      short loc_180026470
0x180026432  test    eax, eax
0x180026434  jle     short loc_18002643F
0x180026436  movzx   edi, ax
0x180026439  or      edi, 80070000h
0x18002643f  test    edi, edi
0x180026441  js      short loc_180026462
0x180026443  mov     rdx, rbx; lpValueName
0x180026446  mov     rcx, r14; hKey
0x180026449  call    cs:__imp_RegDeleteValueW
0x18002644f  mov     edi, eax
0x180026451  test    eax, eax
0x180026453  jle     short loc_18002645E
0x180026455  movzx   edi, ax
0x180026458  or      edi, 80070000h
0x18002645e  test    edi, edi
0x180026460  jns     short loc_1800263FC
0x180026462  lea     rcx, [rbp+arg_18]
0x180026466  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18002646b  jmp     loc_1800263B3
0x180026470  test    r12b, r12b
0x180026473  jz      short loc_1800264A7
0x180026475  mov     rdx, rsi; unsigned __int16 *
0x180026478  mov     rcx, r15; HKEY
0x18002647b  call    ?DeleteKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteKey(HKEY__ * const,ushort const * const)
0x180026480  mov     ebx, eax
0x180026482  test    eax, eax
0x180026484  jns     short loc_1800264A7
0x180026486  lea     rcx, [rbp+arg_18]
0x18002648a  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18002648f  nop
0x180026490  lea     rcx, [rbp+arg_10]
0x180026494  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180026499  nop
0x18002649a  lea     rcx, [rbp+hKey]
0x18002649e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800264a3  mov     eax, ebx
0x1800264a5  jmp     short loc_1800264C6
0x1800264a7  lea     rcx, [rbp+arg_18]
0x1800264ab  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800264b0  nop
0x1800264b1  lea     rcx, [rbp+arg_10]
0x1800264b5  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800264ba  nop
0x1800264bb  lea     rcx, [rbp+hKey]
0x1800264bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800264c4  xor     eax, eax
0x1800264c6  add     rsp, 58h
0x1800264ca  pop     r15
0x1800264cc  pop     r14
0x1800264ce  pop     r13
0x1800264d0  pop     r12
0x1800264d2  pop     rdi
0x1800264d3  pop     rsi
0x1800264d4  pop     rbx
0x1800264d5  pop     rbp
0x1800264d6  retn
```
