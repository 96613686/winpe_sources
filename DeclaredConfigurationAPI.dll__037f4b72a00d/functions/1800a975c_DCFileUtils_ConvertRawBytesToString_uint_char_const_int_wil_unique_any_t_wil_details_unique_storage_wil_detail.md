# DCFileUtils::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1800a975c`
- end: `0x1800a98c4`
- name: `?ConvertRawBytesToString@DCFileUtils@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a98cc`

## callees

- `0x18000df6c`
- `0x18000e5d0`
- `0x1800117bc`
- `0x1800117dc`
- `0x1800a973c`
- `0x1800a975c`
- `0x1800a9c14`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a979b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a982e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a979b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800a982e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800a97cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800a97cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a97ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800a97ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9876`

## string_xrefs

- `0x1800a9805`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`
- `0x1800a983f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcfileutils.cpp`

## pseudocode

```c
__int64 __fastcall DCFileUtils::ConvertRawBytesToString(
        UINT CodePage,
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        HSTRING *a4)
{
  int cchWideChar; // esi
  const char *v9; // r9
  __int64 v10; // rdx
  HRESULT hstring_from_buffer_nothrow; // eax
  unsigned int LastError; // ebx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  HSTRING v16; // rbx
  int lpWideCharStr; // [rsp+20h] [rbp-30h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-20h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  bufferHandle = 0;
  cchWideChar = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !cchWideChar )
  {
    v10 = 41;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
                  v9);
    goto LABEL_17;
  }
  charBuffer = 0;
  bufferHandle = 0;
  hstring_from_buffer_nothrow = WindowsPreallocateStringBuffer(cchWideChar, &charBuffer, &bufferHandle);
  LastError = hstring_from_buffer_nothrow;
  if ( hstring_from_buffer_nothrow >= 0 )
  {
    v15 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, charBuffer, cchWideChar);
    if ( !v15 )
    {
      v10 = 53;
      goto LABEL_9;
    }
    if ( cchWideChar != v15 )
    {
      LastError = -2147418113;
      v13 = 54;
      v14 = 2147549183LL;
      goto LABEL_6;
    }
    v16 = *a4;
    if ( *a4 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v21);
      WindowsDeleteString(v16);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v21);
    }
    *a4 = 0;
    hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&bufferHandle, a4);
    LastError = hstring_from_buffer_nothrow;
    if ( hstring_from_buffer_nothrow >= 0 )
    {
      LastError = 0;
      goto LABEL_17;
    }
    v13 = 56;
  }
  else
  {
    v13 = 49;
  }
  v14 = (unsigned int)hstring_from_buffer_nothrow;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcfileutils.cpp",
    (const char *)v14,
    lpWideCharStr);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800a975c  push    rbp
0x1800a975e  push    rbx
0x1800a975f  push    rsi
0x1800a9760  push    rdi
0x1800a9761  push    r12
0x1800a9763  push    r14
0x1800a9765  push    r15
0x1800a9767  mov     rbp, rsp
0x1800a976a  sub     rsp, 50h
0x1800a976e  mov     rdi, r9
0x1800a9771  mov     [rsp+50h+cchWideChar], 0; cchWideChar
0x1800a9779  mov     r9d, r8d; cbMultiByte
0x1800a977c  mov     [rbp+bufferHandle], 0
0x1800a9784  mov     r14d, r8d
0x1800a9787  mov     [rsp+50h+lpWideCharStr], 0; int
0x1800a9790  mov     r8, rdx; lpMultiByteStr
0x1800a9793  mov     r15, rdx
0x1800a9796  xor     edx, edx; dwFlags
0x1800a9798  mov     r12d, ecx
0x1800a979b  call    cs:__imp_MultiByteToWideChar
0x1800a97a1  mov     esi, eax
0x1800a97a3  test    eax, eax
0x1800a97a5  jnz     short loc_1800A97AF
0x1800a97a7  lea     edx, [rax+29h]
0x1800a97aa  jmp     loc_1800A983B
0x1800a97af  mov     rbx, [rbp+bufferHandle]
0x1800a97b3  mov     [rbp+charBuffer], 0
0x1800a97bb  test    rbx, rbx
0x1800a97be  jz      short loc_1800A97DB
0x1800a97c0  lea     rcx, [rbp+var_10]; this
0x1800a97c4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a97c9  mov     rcx, rbx; bufferHandle
0x1800a97cc  call    cs:__imp_WindowsDeleteStringBuffer
0x1800a97d2  lea     rcx, [rbp+var_10]; this
0x1800a97d6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a97db  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800a97df  mov     [rbp+bufferHandle], 0
0x1800a97e7  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800a97eb  mov     ecx, esi; length
0x1800a97ed  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800a97f3  mov     ebx, eax
0x1800a97f5  test    eax, eax
0x1800a97f7  jns     short loc_1800A9816
0x1800a97f9  mov     edx, 31h ; '1'; void *
0x1800a97fe  mov     r9d, eax; char *
0x1800a9801  mov     rcx, [rbp+38h]; this
0x1800a9805  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a980c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9811  jmp     loc_1800A98AA
0x1800a9816  mov     rax, [rbp+charBuffer]
0x1800a981a  mov     r9d, r14d; cbMultiByte
0x1800a981d  mov     [rsp+50h+cchWideChar], esi; cchWideChar
0x1800a9821  mov     r8, r15; lpMultiByteStr
0x1800a9824  xor     edx, edx; dwFlags
0x1800a9826  mov     [rsp+50h+lpWideCharStr], rax; lpWideCharStr
0x1800a982b  mov     ecx, r12d; CodePage
0x1800a982e  call    cs:__imp_MultiByteToWideChar
0x1800a9834  test    eax, eax
0x1800a9836  jnz     short loc_1800A984F
0x1800a9838  lea     edx, [rax+35h]; void *
0x1800a983b  mov     rcx, [rbp+38h]; this
0x1800a983f  lea     r8, aOnecoreuapAdmi_44; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a9846  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a984b  mov     ebx, eax
0x1800a984d  jmp     short loc_1800A98AA
0x1800a984f  cmp     esi, eax
0x1800a9851  jz      short loc_1800A9862
0x1800a9853  mov     ebx, 8000FFFFh
0x1800a9858  mov     edx, 36h ; '6'
0x1800a985d  mov     r9d, ebx
0x1800a9860  jmp     short loc_1800A9801
0x1800a9862  mov     rbx, [rdi]
0x1800a9865  test    rbx, rbx
0x1800a9868  jz      short loc_1800A9885
0x1800a986a  lea     rcx, [rbp+var_10]; this
0x1800a986e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a9873  mov     rcx, rbx; string
0x1800a9876  call    cs:__imp_WindowsDeleteString
0x1800a987c  lea     rcx, [rbp+var_10]; this
0x1800a9880  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a9885  mov     rdx, rdi
0x1800a9888  mov     qword ptr [rdi], 0
0x1800a988f  lea     rcx, [rbp+bufferHandle]
0x1800a9893  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x1800a9898  mov     ebx, eax
0x1800a989a  test    eax, eax
0x1800a989c  jns     short loc_1800A98A8
0x1800a989e  mov     edx, 38h ; '8'
0x1800a98a3  jmp     loc_1800A97FE
0x1800a98a8  xor     ebx, ebx
0x1800a98aa  lea     rcx, [rbp+bufferHandle]
0x1800a98ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800a98b3  mov     eax, ebx
0x1800a98b5  add     rsp, 50h
0x1800a98b9  pop     r15
0x1800a98bb  pop     r14
0x1800a98bd  pop     r12
0x1800a98bf  pop     rdi
0x1800a98c0  pop     rsi
0x1800a98c1  pop     rbx
0x1800a98c2  pop     rbp
0x1800a98c3  retn
```
