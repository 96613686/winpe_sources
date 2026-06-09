# StartConnection(int,ushort *,int)

- ea: `0x14000e904`
- end: `0x14000eb49`
- name: `?StartConnection@@YAJHPEAGH@Z`
- size: `581`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e730`
- `0x14000e8a0`

## callees

- `0x14000a9c4`
- `0x14000aab8`
- `0x14000e6a0`
- `0x14000e904`
- `0x140015240`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000e998`
- `KERNEL32!HeapAlloc` at `0x14000e9e7`
- `KERNEL32!HeapAlloc` at `0x14000e998`
- `KERNEL32!HeapAlloc` at `0x14000e9e7`
- `KERNEL32!GetProcessHeap` at `0x14000e985`
- `KERNEL32!GetProcessHeap` at `0x14000e9d6`
- `KERNEL32!GetProcessHeap` at `0x14000eaf9`
- `KERNEL32!GetProcessHeap` at `0x14000eb12`
- `KERNEL32!GetProcessHeap` at `0x14000e985`
- `KERNEL32!GetProcessHeap` at `0x14000e9d6`
- `KERNEL32!GetProcessHeap` at `0x14000eaf9`
- `KERNEL32!GetProcessHeap` at `0x14000eb12`
- `KERNEL32!HeapFree` at `0x14000eb07`
- `KERNEL32!HeapFree` at `0x14000eb20`
- `KERNEL32!HeapFree` at `0x14000eb07`
- `KERNEL32!HeapFree` at `0x14000eb20`
- `OLEAUT32!__imp_SysFreeString` at `0x14000eb2a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000eb2a`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e925`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e96a`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e925`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e96a`
- `SHELL32!ShellExecuteW` at `0x14000eac2`
- `SHELL32!ShellExecuteW` at `0x14000eac2`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000ea1c`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000ea1c`

## string_xrefs

- `0x14000e9c5`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ea3c`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000eaed`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`

## pseudocode

```c
__int64 __fastcall StartConnection(int a1, unsigned __int16 *a2, int a3)
{
  UINT v6; // edi
  const wchar_t *v7; // rdx
  unsigned __int16 *v8; // rbx
  UINT v9; // eax
  UINT v10; // ecx
  __int64 v11; // rcx
  unsigned __int64 v12; // r15
  SIZE_T v13; // rdi
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  unsigned __int16 *v17; // rbp
  unsigned int v18; // edi
  HANDLE v19; // rax
  WCHAR *v20; // rax
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  CEventLogger *v22; // rcx
  WCHAR *lpDirectory; // rsi
  const struct _EVENT_DESCRIPTOR *v24; // rdx
  CEventLogger *v25; // rcx
  signed int v26; // eax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  signed int v29; // eax
  const struct _EVENT_DESCRIPTOR *v30; // rdx
  CEventLogger *v31; // rcx
  const struct _EVENT_DESCRIPTOR *v32; // rdx
  CEventLogger *v33; // rcx
  HANDLE v34; // rax
  HANDLE v35; // rax
  BSTR pbstr; // [rsp+78h] [rbp+20h] BYREF

  v6 = SysStringLen(a2);
  pbstr = 0;
  if ( a3 )
  {
    v7 = L"-SolicitedIMLegacy ";
  }
  else
  {
    v7 = L"-RAConnectionStringOffer ";
    if ( !a1 )
      v7 = L"-RAConnectionStringAsk ";
  }
  ATL::CComBSTR::operator=(&pbstr, v7);
  v8 = pbstr;
  v9 = SysStringLen(pbstr);
  v10 = v9 + v6 + 2;
  if ( !a3 )
    v10 = v9;
  v11 = v10 + 2;
  v12 = (unsigned int)v11;
  v13 = 2 * v11;
  ProcessHeap = GetProcessHeap();
  v17 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v13);
  if ( !v17 )
  {
    v18 = -2147024882;
    CEventLogger::LogError(
      v16,
      v15,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0xE9u,
      L"StartConnection",
      0x8007000E);
    goto LABEL_24;
  }
  v19 = GetProcessHeap();
  v20 = (WCHAR *)HeapAlloc(v19, 8u, 0x208u);
  lpDirectory = v20;
  if ( !v20 )
  {
    v18 = -2147024882;
    CEventLogger::LogError(
      v22,
      v21,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0xEAu,
      L"StartConnection",
      0x8007000E);
    goto LABEL_22;
  }
  if ( !SHGetSpecialFolderPathW(0, v20, 37, 1) )
  {
    CEventLogger::LogError(
      v25,
      v24,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0xEFu,
      L"StartConnection",
      0);
    v18 = -2147467259;
    goto LABEL_22;
  }
  v26 = StringCchCopyW(v17, v12, v8);
  v18 = v26;
  if ( a3 )
  {
    if ( v26 < 0 )
    {
      CEventLogger::LogError(
        v28,
        v27,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0xF6u,
        L"StartConnection",
        v26);
      goto LABEL_22;
    }
    v29 = StringCchCatW(v17, v12, a2);
    v18 = v29;
    if ( v29 < 0 )
    {
      CEventLogger::LogError(
        v31,
        v30,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0xF7u,
        L"StartConnection",
        v29);
      goto LABEL_22;
    }
LABEL_20:
    if ( (__int64)ShellExecuteW(0, 0, L"msra.exe", v17, lpDirectory, 1) <= 32 )
    {
      v18 = -2147467259;
      CEventLogger::LogError(
        v33,
        v32,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x111u,
        L"StartConnection",
        0x80004005);
    }
    goto LABEL_22;
  }
  if ( v26 >= 0 )
    goto LABEL_20;
  CEventLogger::LogError(
    v28,
    v27,
    L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
    0xFBu,
    L"StartConnection",
    v26);
LABEL_22:
  v34 = GetProcessHeap();
  HeapFree(v34, 0, v17);
  if ( lpDirectory )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, lpDirectory);
  }
LABEL_24:
  SysFreeString(v8);
  return v18;
}

```

## disassembly

```asm
0x14000e904  mov     [rsp+arg_0], rbx
0x14000e909  mov     [rsp+arg_8], rbp
0x14000e90e  push    rsi
0x14000e90f  push    rdi
0x14000e910  push    r12
0x14000e912  push    r14
0x14000e914  push    r15
0x14000e916  sub     rsp, 30h
0x14000e91a  mov     r14d, r8d
0x14000e91d  mov     r12, rdx
0x14000e920  mov     ebx, ecx
0x14000e922  mov     rcx, rdx; pbstr
0x14000e925  call    cs:__imp_SysStringLen
0x14000e92b  mov     edi, eax
0x14000e92d  mov     [rsp+58h+pbstr], 0
0x14000e936  test    r14d, r14d
0x14000e939  jz      short loc_14000E944
0x14000e93b  lea     rdx, aSolicitedimleg; "-SolicitedIMLegacy "
0x14000e942  jmp     short loc_14000E958
0x14000e944  lea     rdx, aRaconnectionst_0; "-RAConnectionStringOffer "
0x14000e94b  lea     rax, aRaconnectionst; "-RAConnectionStringAsk "
0x14000e952  test    ebx, ebx
0x14000e954  cmovz   rdx, rax
0x14000e958  lea     rcx, [rsp+58h+pbstr]
0x14000e95d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x14000e962  mov     rbx, [rsp+58h+pbstr]
0x14000e967  mov     rcx, rbx; pbstr
0x14000e96a  call    cs:__imp_SysStringLen
0x14000e970  lea     ecx, [rdi+2]
0x14000e973  add     ecx, eax
0x14000e975  test    r14d, r14d
0x14000e978  cmovz   ecx, eax
0x14000e97b  add     ecx, 2
0x14000e97e  mov     r15d, ecx
0x14000e981  lea     rdi, [rcx+rcx]
0x14000e985  call    cs:__imp_GetProcessHeap
0x14000e98b  mov     rcx, rax; hHeap
0x14000e98e  mov     r8, rdi; dwBytes
0x14000e991  mov     edi, 8
0x14000e996  mov     edx, edi; dwFlags
0x14000e998  call    cs:__imp_HeapAlloc
0x14000e99e  mov     rbp, rax
0x14000e9a1  test    rax, rax
0x14000e9a4  jnz     short loc_14000E9D6
0x14000e9a6  mov     edi, 8007000Eh
0x14000e9ab  mov     [rsp+58h+nShowCmd], 8007000Eh; unsigned int
0x14000e9b3  lea     rax, aStartconnectio; "StartConnection"
0x14000e9ba  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000e9bf  mov     r9d, 0E9h; unsigned int
0x14000e9c5  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000e9cc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e9d1  jmp     loc_14000EB27
0x14000e9d6  call    cs:__imp_GetProcessHeap
0x14000e9dc  mov     rcx, rax; hHeap
0x14000e9df  mov     r8d, 208h; dwBytes
0x14000e9e5  mov     edx, edi; dwFlags
0x14000e9e7  call    cs:__imp_HeapAlloc
0x14000e9ed  mov     rsi, rax
0x14000e9f0  test    rax, rax
0x14000e9f3  jnz     short loc_14000EA0D
0x14000e9f5  mov     edi, 8007000Eh
0x14000e9fa  mov     [rsp+58h+nShowCmd], 8007000Eh
0x14000ea02  mov     r9d, 0EAh
0x14000ea08  jmp     loc_14000EAE1
0x14000ea0d  mov     r9d, 1; fCreate
0x14000ea13  lea     r8d, [r9+24h]; csidl
0x14000ea17  mov     rdx, rsi; pszPath
0x14000ea1a  xor     ecx, ecx; hwnd
0x14000ea1c  call    cs:__imp_SHGetSpecialFolderPathW
0x14000ea22  test    eax, eax
0x14000ea24  jnz     short loc_14000EA52
0x14000ea26  mov     [rsp+58h+nShowCmd], eax; unsigned int
0x14000ea2a  lea     rax, aStartconnectio; "StartConnection"
0x14000ea31  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000ea36  mov     r9d, 0EFh; unsigned int
0x14000ea3c  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ea43  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ea48  mov     edi, 80004005h
0x14000ea4d  jmp     loc_14000EAF9
0x14000ea52  mov     r8, rbx; unsigned __int16 *
0x14000ea55  mov     rdx, r15; unsigned __int64
0x14000ea58  mov     rcx, rbp; unsigned __int16 *
0x14000ea5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ea60  mov     edi, eax
0x14000ea62  test    r14d, r14d
0x14000ea65  jz      short loc_14000EA97
0x14000ea67  test    eax, eax
0x14000ea69  jns     short loc_14000EA77
0x14000ea6b  mov     [rsp+58h+nShowCmd], eax
0x14000ea6f  mov     r9d, 0F6h
0x14000ea75  jmp     short loc_14000EAE1
0x14000ea77  mov     r8, r12; unsigned __int16 *
0x14000ea7a  mov     rdx, r15; unsigned __int64
0x14000ea7d  mov     rcx, rbp; unsigned __int16 *
0x14000ea80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ea85  mov     edi, eax
0x14000ea87  test    eax, eax
0x14000ea89  jns     short loc_14000EAA7
0x14000ea8b  mov     [rsp+58h+nShowCmd], eax
0x14000ea8f  mov     r9d, 0F7h
0x14000ea95  jmp     short loc_14000EAE1
0x14000ea97  test    eax, eax
0x14000ea99  jns     short loc_14000EAA7
0x14000ea9b  mov     [rsp+58h+nShowCmd], eax
0x14000ea9f  mov     r9d, 0FBh
0x14000eaa5  jmp     short loc_14000EAE1
0x14000eaa7  mov     [rsp+58h+nShowCmd], 1; nShowCmd
0x14000eaaf  mov     [rsp+58h+lpDirectory], rsi; lpDirectory
0x14000eab4  mov     r9, rbp; lpParameters
0x14000eab7  lea     r8, File; "msra.exe"
0x14000eabe  xor     edx, edx; lpOperation
0x14000eac0  xor     ecx, ecx; hwnd
0x14000eac2  call    cs:__imp_ShellExecuteW
0x14000eac8  cmp     rax, 20h ; ' '
0x14000eacc  jg      short loc_14000EAF9
0x14000eace  mov     edi, 80004005h
0x14000ead3  mov     [rsp+58h+nShowCmd], 80004005h; unsigned int
0x14000eadb  mov     r9d, 111h; unsigned int
0x14000eae1  lea     rax, aStartconnectio; "StartConnection"
0x14000eae8  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000eaed  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000eaf4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000eaf9  call    cs:__imp_GetProcessHeap
0x14000eaff  mov     rcx, rax; hHeap
0x14000eb02  mov     r8, rbp; lpMem
0x14000eb05  xor     edx, edx; dwFlags
0x14000eb07  call    cs:__imp_HeapFree
0x14000eb0d  test    rsi, rsi
0x14000eb10  jz      short loc_14000EB27
0x14000eb12  call    cs:__imp_GetProcessHeap
0x14000eb18  mov     rcx, rax; hHeap
0x14000eb1b  mov     r8, rsi; lpMem
0x14000eb1e  xor     edx, edx; dwFlags
0x14000eb20  call    cs:__imp_HeapFree
0x14000eb26  nop
0x14000eb27  mov     rcx, rbx; bstrString
0x14000eb2a  call    cs:__imp_SysFreeString
0x14000eb30  mov     eax, edi
0x14000eb32  mov     rbx, [rsp+58h+arg_0]
0x14000eb37  mov     rbp, [rsp+58h+arg_8]
0x14000eb3c  add     rsp, 30h
0x14000eb40  pop     r15
0x14000eb42  pop     r14
0x14000eb44  pop     r12
0x14000eb46  pop     rdi
0x14000eb47  pop     rsi
0x14000eb48  retn
```
