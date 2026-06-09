# Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1800253d4`
- end: `0x180025536`
- name: `?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte, HSTRING *string)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023cb0`
- `0x1800250d8`
- `0x18002553c`

## callees

- `0x1800105d4`
- `0x1800105f4`
- `0x1800253d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800254e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025464`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025464`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002550d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002550d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002547c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002547c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180025437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002545c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180025437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002545c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254f1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002540b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800254ba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002540b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800254ba`

## string_xrefs

- `0x180025420`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180025491`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
        UINT CodePage,
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        HSTRING *string)
{
  int cchWideChar; // edi
  const char *v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // ebx
  __int64 v13; // rdx
  int v14; // eax
  HSTRING v15; // rdi
  DWORD LastError; // ebx
  HSTRING_BUFFER v17; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-28h]
  HSTRING_BUFFER bufferHandle; // [rsp+30h] [rbp-18h] BYREF
  WCHAR *charBuffer; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  bufferHandle = 0;
  cchWideChar = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( cchWideChar )
  {
    charBuffer = 0;
    bufferHandle = 0;
    v11 = WindowsPreallocateStringBuffer(cchWideChar, &charBuffer, &bufferHandle);
    if ( v11 >= 0 )
    {
      v14 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, cbMultiByte, charBuffer, cchWideChar);
      if ( !v14 )
      {
        v10 = 232;
        goto LABEL_3;
      }
      if ( cchWideChar == v14 )
      {
        v15 = *string;
        if ( *string )
        {
          LastError = GetLastError();
          WindowsDeleteString(v15);
          SetLastError(LastError);
        }
        v17 = bufferHandle;
        *string = 0;
        v11 = WindowsPromoteStringBuffer(v17, string);
        if ( v11 >= 0 )
          return 0;
        v13 = 235;
      }
      else
      {
        v11 = -2147418113;
        v13 = 233;
      }
    }
    else
    {
      v13 = 228;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
      (const char *)(unsigned int)v11,
      lpWideCharStr);
    goto LABEL_4;
  }
  v10 = 220;
LABEL_3:
  v11 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
          v9);
LABEL_4:
  if ( bufferHandle )
    WindowsDeleteStringBuffer(bufferHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800253d4  push    rbp
0x1800253d6  push    rbx
0x1800253d7  push    rsi
0x1800253d8  push    rdi
0x1800253d9  push    r12
0x1800253db  push    r13
0x1800253dd  push    r14
0x1800253df  push    r15
0x1800253e1  mov     rbp, rsp
0x1800253e4  sub     rsp, 48h
0x1800253e8  xor     ebx, ebx
0x1800253ea  mov     rsi, r9
0x1800253ed  mov     r9d, r8d; cbMultiByte
0x1800253f0  mov     [rsp+48h+cchWideChar], ebx; cchWideChar
0x1800253f4  mov     r15d, r8d
0x1800253f7  mov     [rbp+bufferHandle], rbx
0x1800253fb  mov     r8, rdx; lpMultiByteStr
0x1800253fe  mov     [rsp+48h+lpWideCharStr], rbx; int
0x180025403  mov     r12, rdx
0x180025406  mov     r13d, ecx
0x180025409  xor     edx, edx; dwFlags
0x18002540b  call    cs:__imp_MultiByteToWideChar
0x180025411  mov     edi, eax
0x180025413  test    eax, eax
0x180025415  jnz     short loc_180025444
0x180025417  mov     edx, 0DCh; void *
0x18002541c  mov     rcx, [rbp+40h]; this
0x180025420  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025427  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002542c  mov     ebx, eax
0x18002542e  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180025432  test    rcx, rcx
0x180025435  jz      short loc_18002543D
0x180025437  call    cs:__imp_WindowsDeleteStringBuffer
0x18002543d  mov     eax, ebx
0x18002543f  jmp     loc_180025525
0x180025444  mov     r14, [rbp+bufferHandle]
0x180025448  mov     [rbp+charBuffer], rbx
0x18002544c  test    r14, r14
0x18002544f  jz      short loc_18002546A
0x180025451  call    cs:__imp_GetLastError
0x180025457  mov     rcx, r14; bufferHandle
0x18002545a  mov     ebx, eax
0x18002545c  call    cs:__imp_WindowsDeleteStringBuffer
0x180025462  mov     ecx, ebx; dwErrCode
0x180025464  call    cs:__imp_SetLastError
0x18002546a  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18002546e  mov     [rbp+bufferHandle], 0
0x180025476  lea     rdx, [rbp+charBuffer]; charBuffer
0x18002547a  mov     ecx, edi; length
0x18002547c  call    cs:__imp_WindowsPreallocateStringBuffer
0x180025482  mov     ebx, eax
0x180025484  test    eax, eax
0x180025486  jns     short loc_1800254A2
0x180025488  mov     edx, 0E4h; void *
0x18002548d  mov     rcx, [rbp+40h]; this
0x180025491  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025498  mov     r9d, ebx; char *
0x18002549b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800254a0  jmp     short loc_18002542E
0x1800254a2  mov     rax, [rbp+charBuffer]
0x1800254a6  mov     r9d, r15d; cbMultiByte
0x1800254a9  mov     [rsp+48h+cchWideChar], edi; cchWideChar
0x1800254ad  mov     r8, r12; lpMultiByteStr
0x1800254b0  xor     edx, edx; dwFlags
0x1800254b2  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x1800254b7  mov     ecx, r13d; CodePage
0x1800254ba  call    cs:__imp_MultiByteToWideChar
0x1800254c0  test    eax, eax
0x1800254c2  jnz     short loc_1800254CE
0x1800254c4  mov     edx, 0E8h
0x1800254c9  jmp     loc_18002541C
0x1800254ce  cmp     edi, eax
0x1800254d0  jz      short loc_1800254DE
0x1800254d2  mov     ebx, 8000FFFFh
0x1800254d7  mov     edx, 0E9h
0x1800254dc  jmp     short loc_18002548D
0x1800254de  mov     rdi, [rsi]
0x1800254e1  test    rdi, rdi
0x1800254e4  jz      short loc_1800254FF
0x1800254e6  call    cs:__imp_GetLastError
0x1800254ec  mov     rcx, rdi; string
0x1800254ef  mov     ebx, eax
0x1800254f1  call    cs:__imp_WindowsDeleteString
0x1800254f7  mov     ecx, ebx; dwErrCode
0x1800254f9  call    cs:__imp_SetLastError
0x1800254ff  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180025503  mov     rdx, rsi; string
0x180025506  mov     qword ptr [rsi], 0
0x18002550d  call    cs:__imp_WindowsPromoteStringBuffer
0x180025513  mov     ebx, eax
0x180025515  test    eax, eax
0x180025517  jns     short loc_180025523
0x180025519  mov     edx, 0EBh
0x18002551e  jmp     loc_18002548D
0x180025523  xor     eax, eax
0x180025525  add     rsp, 48h
0x180025529  pop     r15
0x18002552b  pop     r14
0x18002552d  pop     r13
0x18002552f  pop     r12
0x180025531  pop     rdi
0x180025532  pop     rsi
0x180025533  pop     rbx
0x180025534  pop     rbp
0x180025535  retn
```
