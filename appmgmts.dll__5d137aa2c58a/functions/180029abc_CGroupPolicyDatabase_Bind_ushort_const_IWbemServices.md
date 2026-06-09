# CGroupPolicyDatabase::Bind(ushort const *,IWbemServices * *)

- ea: `0x180029abc`
- end: `0x180029cb9`
- name: `?Bind@CGroupPolicyDatabase@@QEAAJPEBGPEAPEAUIWbemServices@@@Z`
- size: `509`
- prototype: `int __fastcall(CGroupPolicyDatabase *this, const unsigned __int16 *, struct IWbemServices **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029540`

## callees

- `0x180029abc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bb2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029afc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029afc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029b82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029b82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b58`
- `OLEAUT32!__imp_SysAllocString` at `0x180029c2f`
- `OLEAUT32!__imp_SysAllocString` at `0x180029c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180029c8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180029c8b`

## string_xrefs

- `0x180029aef`: `ole32.dll`
- `0x180029b0e`: `CoCreateInstance`

## pseudocode

```c
int __fastcall CGroupPolicyDatabase::Bind(
        CGroupPolicyDatabase *this,
        const unsigned __int16 *a2,
        struct IWbemServices **a3)
{
  HMODULE *v6; // rax
  HMODULE Library; // rax
  int result; // eax
  __int64 v9; // rax
  int v10; // ebx
  OLECHAR *v11; // rbx
  BSTR v12; // rax
  int v13; // edi
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  if ( g_Ole32Api )
  {
    v6 = &g_Ole32Api;
    *(_QWORD *)this = &g_Ole32Api;
LABEL_12:
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD))v6[2])(0, 0);
    goto LABEL_15;
  }
  Library = LoadLibraryExW(L"ole32.dll", 0, 0x800u);
  g_Ole32Api = Library;
  if ( Library )
  {
    *(&g_Ole32Api + 1) = (HMODULE)GetProcAddress(Library, "CoCreateInstance");
    if ( *(&g_Ole32Api + 1) )
    {
      *(_QWORD *)&xmmword_180037DF0 = GetProcAddress(g_Ole32Api, "CoInitializeEx");
      if ( (_QWORD)xmmword_180037DF0 )
      {
        *((_QWORD *)&xmmword_180037DF0 + 1) = GetProcAddress(g_Ole32Api, "CoUninitialize");
        if ( *((_QWORD *)&xmmword_180037DF0 + 1) )
        {
          v6 = &g_Ole32Api;
          goto LABEL_11;
        }
      }
    }
    if ( g_Ole32Api )
      FreeLibrary(g_Ole32Api);
  }
  v6 = 0;
  *(_OWORD *)&g_Ole32Api = 0;
  xmmword_180037DF0 = 0;
LABEL_11:
  *(_QWORD *)this = v6;
  if ( v6 )
    goto LABEL_12;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
LABEL_15:
  *((_DWORD *)this + 2) = result;
  if ( result >= 0 )
  {
    v9 = *(_QWORD *)this;
    v14 = 0;
    v10 = (*(__int64 (__fastcall **)(GUID *, _QWORD, __int64, GUID *, __int64 *))(v9 + 8))(
            &CLSID_WbemLocator,
            0,
            1,
            &IID_IWbemLocator,
            &v14);
    if ( v10 >= 0 )
    {
      v11 = 0;
      if ( a2 && (v12 = SysAllocString(a2), (v11 = v12) != 0) )
        v13 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IWbemServices **))(*(_QWORD *)v14 + 24LL))(
                v14,
                v12,
                0,
                0,
                0,
                0,
                0,
                0,
                a3);
      else
        v13 = -2147024882;
      SysFreeString(v11);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return v13;
    }
    else
    {
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029abc  mov     [rsp+arg_8], rbx
0x180029ac1  mov     [rsp+arg_10], rsi
0x180029ac6  push    rdi
0x180029ac7  sub     rsp, 50h
0x180029acb  cmp     qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A, 0; _OLE32_API g_Ole32Api
0x180029ad3  mov     rsi, r8
0x180029ad6  mov     rdi, rdx
0x180029ad9  mov     rbx, rcx
0x180029adc  jz      short loc_180029AED
0x180029ade  lea     rax, ?g_Ole32Api@@3U_OLE32_API@@A; _OLE32_API g_Ole32Api
0x180029ae5  mov     [rcx], rax
0x180029ae8  jmp     loc_180029BA3
0x180029aed  xor     edx, edx; hFile
0x180029aef  lea     rcx, aOle32Dll; "ole32.dll"
0x180029af6  mov     r8d, 800h; dwFlags
0x180029afc  call    cs:__imp_LoadLibraryExW
0x180029b02  mov     qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A, rax; _OLE32_API g_Ole32Api
0x180029b09  test    rax, rax
0x180029b0c  jz      short loc_180029B88
0x180029b0e  lea     rdx, aCocreateinstan; "CoCreateInstance"
0x180029b15  mov     rcx, rax; hModule
0x180029b18  call    cs:__imp_GetProcAddress
0x180029b1e  mov     qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A+8, rax; _OLE32_API g_Ole32Api
0x180029b25  test    rax, rax
0x180029b28  jz      short loc_180029B73
0x180029b2a  mov     rcx, qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A; hModule
0x180029b31  lea     rdx, aCoinitializeex; "CoInitializeEx"
0x180029b38  call    cs:__imp_GetProcAddress
0x180029b3e  mov     qword ptr cs:xmmword_180037DF0, rax
0x180029b45  test    rax, rax
0x180029b48  jz      short loc_180029B73
0x180029b4a  mov     rcx, qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A; hModule
0x180029b51  lea     rdx, aCouninitialize; "CoUninitialize"
0x180029b58  call    cs:__imp_GetProcAddress
0x180029b5e  mov     qword ptr cs:xmmword_180037DF0+8, rax
0x180029b65  test    rax, rax
0x180029b68  jz      short loc_180029B73
0x180029b6a  lea     rax, ?g_Ole32Api@@3U_OLE32_API@@A; _OLE32_API g_Ole32Api
0x180029b71  jmp     short loc_180029B9B
0x180029b73  mov     rax, qword ptr cs:?g_Ole32Api@@3U_OLE32_API@@A; _OLE32_API g_Ole32Api
0x180029b7a  test    rax, rax
0x180029b7d  jz      short loc_180029B88
0x180029b7f  mov     rcx, rax; hLibModule
0x180029b82  call    cs:__imp_FreeLibrary
0x180029b88  xorps   xmm0, xmm0
0x180029b8b  xor     eax, eax
0x180029b8d  movups  cs:?g_Ole32Api@@3U_OLE32_API@@A, xmm0; _OLE32_API g_Ole32Api
0x180029b94  movups  cs:xmmword_180037DF0, xmm0
0x180029b9b  mov     [rbx], rax
0x180029b9e  test    rax, rax
0x180029ba1  jz      short loc_180029BB2
0x180029ba3  mov     rax, [rax+10h]
0x180029ba7  xor     edx, edx
0x180029ba9  xor     ecx, ecx
0x180029bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb0  jmp     short loc_180029BC4
0x180029bb2  call    cs:__imp_GetLastError
0x180029bb8  test    eax, eax
0x180029bba  jle     short loc_180029BC4
0x180029bbc  movzx   eax, ax
0x180029bbf  or      eax, 80070000h
0x180029bc4  mov     [rbx+8], eax
0x180029bc7  test    eax, eax
0x180029bc9  js      loc_180029CA9
0x180029bcf  mov     rax, [rbx]
0x180029bd2  lea     rcx, [rsp+58h+arg_0]
0x180029bd7  xor     edx, edx
0x180029bd9  mov     [rsp+58h+arg_0], 0
0x180029be2  mov     [rsp+58h+var_38], rcx
0x180029be7  lea     r9, IID_IWbemLocator
0x180029bee  lea     rcx, CLSID_WbemLocator
0x180029bf5  mov     rax, [rax+8]
0x180029bf9  lea     r8d, [rdx+1]
0x180029bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c02  mov     ebx, eax
0x180029c04  test    eax, eax
0x180029c06  jns     short loc_180029C25
0x180029c08  mov     rcx, [rsp+58h+arg_0]
0x180029c0d  test    rcx, rcx
0x180029c10  jz      short loc_180029C1E
0x180029c12  mov     rdx, [rcx]
0x180029c15  mov     rax, [rdx+10h]
0x180029c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c1e  mov     eax, ebx
0x180029c20  jmp     loc_180029CA9
0x180029c25  xor     ebx, ebx
0x180029c27  test    rdi, rdi
0x180029c2a  jz      short loc_180029C83
0x180029c2c  mov     rcx, rdi; psz
0x180029c2f  call    cs:__imp_SysAllocString
0x180029c35  mov     rbx, rax
0x180029c38  test    rax, rax
0x180029c3b  jz      short loc_180029C83
0x180029c3d  mov     rcx, [rsp+58h+arg_0]
0x180029c42  xor     r9d, r9d
0x180029c45  mov     [rsp+58h+var_18], rsi
0x180029c4a  xor     r8d, r8d
0x180029c4d  mov     [rsp+58h+var_20], 0
0x180029c56  mov     rdx, rbx
0x180029c59  mov     [rsp+58h+var_28], 0
0x180029c62  mov     rax, [rcx]
0x180029c65  mov     [rsp+58h+var_30], 0
0x180029c6d  mov     [rsp+58h+var_38], 0
0x180029c76  mov     rax, [rax+18h]
0x180029c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c7f  mov     edi, eax
0x180029c81  jmp     short loc_180029C88
0x180029c83  mov     edi, 8007000Eh
0x180029c88  mov     rcx, rbx; bstrString
0x180029c8b  call    cs:__imp_SysFreeString
0x180029c91  mov     rcx, [rsp+58h+arg_0]
0x180029c96  test    rcx, rcx
0x180029c99  jz      short loc_180029CA7
0x180029c9b  mov     rax, [rcx]
0x180029c9e  mov     rax, [rax+10h]
0x180029ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ca7  mov     eax, edi
0x180029ca9  mov     rbx, [rsp+58h+arg_8]
0x180029cae  mov     rsi, [rsp+58h+arg_10]
0x180029cb3  add     rsp, 50h
0x180029cb7  pop     rdi
0x180029cb8  retn
```
