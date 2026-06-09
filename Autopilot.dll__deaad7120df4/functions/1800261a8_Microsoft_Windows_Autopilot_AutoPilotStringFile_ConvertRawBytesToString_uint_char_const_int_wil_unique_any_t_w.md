# Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x1800261a8`
- end: `0x180026350`
- name: `?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte, HSTRING *string)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024878`
- `0x180025e74`
- `0x180026358`

## callees

- `0x180010744`
- `0x180010764`
- `0x1800261a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180026320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180026320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002626e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002626e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180026242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800261df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800262b5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800261df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800262b5`

## string_xrefs

- `0x1800261fa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180026289`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800261a8  push    rbp
0x1800261aa  push    rbx
0x1800261ab  push    rsi
0x1800261ac  push    rdi
0x1800261ad  push    r12
0x1800261af  push    r13
0x1800261b1  push    r14
0x1800261b3  push    r15
0x1800261b5  mov     rbp, rsp
0x1800261b8  sub     rsp, 48h
0x1800261bc  xor     ebx, ebx
0x1800261be  mov     rsi, r9
0x1800261c1  mov     r9d, r8d; cbMultiByte
0x1800261c4  mov     [rsp+48h+cchWideChar], ebx; cchWideChar
0x1800261c8  mov     r15d, r8d
0x1800261cb  mov     [rbp+bufferHandle], rbx
0x1800261cf  mov     r8, rdx; lpMultiByteStr
0x1800261d2  mov     [rsp+48h+lpWideCharStr], rbx; int
0x1800261d7  mov     r12, rdx
0x1800261da  mov     r13d, ecx
0x1800261dd  xor     edx, edx; dwFlags
0x1800261df  call    cs:__imp_MultiByteToWideChar
0x1800261e6  nop     dword ptr [rax+rax+00h]
0x1800261eb  mov     edi, eax
0x1800261ed  test    eax, eax
0x1800261ef  jnz     short loc_180026224
0x1800261f1  mov     edx, 0DCh; void *
0x1800261f6  mov     rcx, [rbp+40h]; this
0x1800261fa  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026201  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026206  mov     ebx, eax
0x180026208  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002620c  test    rcx, rcx
0x18002620f  jz      short loc_18002621D
0x180026211  call    cs:__imp_WindowsDeleteStringBuffer
0x180026218  nop     dword ptr [rax+rax+00h]
0x18002621d  mov     eax, ebx
0x18002621f  jmp     loc_18002633E
0x180026224  mov     r14, [rbp+bufferHandle]
0x180026228  mov     [rbp+charBuffer], rbx
0x18002622c  test    r14, r14
0x18002622f  jz      short loc_18002625C
0x180026231  call    cs:__imp_GetLastError
0x180026238  nop     dword ptr [rax+rax+00h]
0x18002623d  mov     rcx, r14; bufferHandle
0x180026240  mov     ebx, eax
0x180026242  call    cs:__imp_WindowsDeleteStringBuffer
0x180026249  nop     dword ptr [rax+rax+00h]
0x18002624e  mov     ecx, ebx; dwErrCode
0x180026250  call    cs:__imp_SetLastError
0x180026257  nop     dword ptr [rax+rax+00h]
0x18002625c  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180026260  mov     [rbp+bufferHandle], 0
0x180026268  lea     rdx, [rbp+charBuffer]; charBuffer
0x18002626c  mov     ecx, edi; length
0x18002626e  call    cs:__imp_WindowsPreallocateStringBuffer
0x180026275  nop     dword ptr [rax+rax+00h]
0x18002627a  mov     ebx, eax
0x18002627c  test    eax, eax
0x18002627e  jns     short loc_18002629D
0x180026280  mov     edx, 0E4h; void *
0x180026285  mov     rcx, [rbp+40h]; this
0x180026289  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026290  mov     r9d, ebx; char *
0x180026293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026298  jmp     loc_180026208
0x18002629d  mov     rax, [rbp+charBuffer]
0x1800262a1  mov     r9d, r15d; cbMultiByte
0x1800262a4  mov     [rsp+48h+cchWideChar], edi; cchWideChar
0x1800262a8  mov     r8, r12; lpMultiByteStr
0x1800262ab  xor     edx, edx; dwFlags
0x1800262ad  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x1800262b2  mov     ecx, r13d; CodePage
0x1800262b5  call    cs:__imp_MultiByteToWideChar
0x1800262bc  nop     dword ptr [rax+rax+00h]
0x1800262c1  test    eax, eax
0x1800262c3  jnz     short loc_1800262CF
0x1800262c5  mov     edx, 0E8h
0x1800262ca  jmp     loc_1800261F6
0x1800262cf  cmp     edi, eax
0x1800262d1  jz      short loc_1800262DF
0x1800262d3  mov     ebx, 8000FFFFh
0x1800262d8  mov     edx, 0E9h
0x1800262dd  jmp     short loc_180026285
0x1800262df  mov     rdi, [rsi]
0x1800262e2  test    rdi, rdi
0x1800262e5  jz      short loc_180026312
0x1800262e7  call    cs:__imp_GetLastError
0x1800262ee  nop     dword ptr [rax+rax+00h]
0x1800262f3  mov     rcx, rdi; string
0x1800262f6  mov     ebx, eax
0x1800262f8  call    cs:__imp_WindowsDeleteString
0x1800262ff  nop     dword ptr [rax+rax+00h]
0x180026304  mov     ecx, ebx; dwErrCode
0x180026306  call    cs:__imp_SetLastError
0x18002630d  nop     dword ptr [rax+rax+00h]
0x180026312  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180026316  mov     rdx, rsi; string
0x180026319  mov     qword ptr [rsi], 0
0x180026320  call    cs:__imp_WindowsPromoteStringBuffer
0x180026327  nop     dword ptr [rax+rax+00h]
0x18002632c  mov     ebx, eax
0x18002632e  test    eax, eax
0x180026330  jns     short loc_18002633C
0x180026332  mov     edx, 0EBh
0x180026337  jmp     loc_180026285
0x18002633c  xor     eax, eax
0x18002633e  add     rsp, 48h
0x180026342  pop     r15
0x180026344  pop     r14
0x180026346  pop     r13
0x180026348  pop     r12
0x18002634a  pop     rdi
0x18002634b  pop     rsi
0x18002634c  pop     rbx
0x18002634d  pop     rbp
0x18002634e  retn
```
