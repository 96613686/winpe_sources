# TmGetPublisherFromVersionInfo(uchar *,ulong,HSTRING__ * *)

- ea: `0x1800d0840`
- end: `0x1800d0958`
- name: `?TmGetPublisherFromVersionInfo@@YAJPEAEKPEAPEAUHSTRING__@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d6704`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18004e674`
- `0x1800d0840`
- `0x1800d09d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d090a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d090a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d0927`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800d08ba`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800d08ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1800d08c5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1800d08c5`

## string_xrefs

- `0x1800d088b`: `CompanyName`

## pseudocode

```c
__int64 __fastcall TmGetPublisherFromVersionInfo(unsigned __int8 *a1, unsigned int a2, HSTRING *a3)
{
  int StringFromVersionInfo; // edi
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-248h]
  int v9; // [rsp+20h] [rbp-248h]
  bool v10; // [rsp+28h] [rbp-240h]
  HSTRING string[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR psz[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *a3 = 0;
  psz[0] = 0;
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  StringFromVersionInfo = TmGetStringFromVersionInfo(a1, a2, L"CompanyName", psz, v8, v10);
  if ( StringFromVersionInfo < 0 || !psz[0] )
    return 0;
  StrTrimW(psz, L" \t");
  PathRemoveBlanksW(psz);
  string[0] = 0;
  v5 = Microsoft::WRL::Wrappers::HString::Set<260>(string, psz);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *a3 = string[0];
    string[0] = 0;
    WindowsDeleteString(0);
    return (unsigned int)StringFromVersionInfo;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\tmutils.cpp",
      (const char *)(unsigned int)v5,
      v9);
    WindowsDeleteString(string[0]);
    return v6;
  }
}

```

## disassembly

```asm
0x1800d0840  mov     [rsp+arg_8], rbx
0x1800d0845  mov     [rsp+arg_18], rsi
0x1800d084a  push    rdi
0x1800d084b  sub     rsp, 260h
0x1800d0852  mov     rax, cs:__security_cookie
0x1800d0859  xor     rax, rsp
0x1800d085c  mov     [rsp+268h+var_18], rax
0x1800d0864  xor     eax, eax
0x1800d0866  mov     qword ptr [r8], 0
0x1800d086d  mov     [rsp+268h+psz], ax
0x1800d0872  mov     rsi, r8
0x1800d0875  test    rcx, rcx
0x1800d0878  jz      loc_1800D0931
0x1800d087e  test    edx, edx
0x1800d0880  jz      loc_1800D0931
0x1800d0886  lea     r9, [rsp+268h+psz]; unsigned __int16 *
0x1800d088b  lea     r8, aCompanyname; "CompanyName"
0x1800d0892  call    ?TmGetStringFromVersionInfo@@YAJQEBEKPEAG1K_N@Z; TmGetStringFromVersionInfo(uchar const * const,ulong,ushort *,ushort *,ulong,bool)
0x1800d0897  mov     edi, eax
0x1800d0899  test    eax, eax
0x1800d089b  js      loc_1800D0931
0x1800d08a1  xor     ecx, ecx
0x1800d08a3  cmp     cx, [rsp+268h+psz]
0x1800d08a8  jz      loc_1800D0931
0x1800d08ae  lea     rdx, pszTrimChars; " \t"
0x1800d08b5  lea     rcx, [rsp+268h+psz]; psz
0x1800d08ba  call    cs:__imp_StrTrimW
0x1800d08c0  lea     rcx, [rsp+268h+psz]; pszPath
0x1800d08c5  call    cs:__imp_PathRemoveBlanksW
0x1800d08cb  lea     rdx, [rsp+268h+psz]
0x1800d08d0  mov     [rsp+268h+string], 0
0x1800d08d9  lea     rcx, [rsp+268h+string]
0x1800d08de  call    ??$Set@$0BAE@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HString::Set<260>(ushort (&)[260])
0x1800d08e3  mov     ebx, eax
0x1800d08e5  test    eax, eax
0x1800d08e7  jns     short loc_1800D0914
0x1800d08e9  mov     rcx, [rsp+268h]; this
0x1800d08f1  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d08f8  mov     r9d, eax; char *
0x1800d08fb  mov     edx, 42Eh; void *
0x1800d0900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0905  mov     rcx, [rsp+268h+string]; string
0x1800d090a  call    cs:__imp_WindowsDeleteString
0x1800d0910  mov     eax, ebx
0x1800d0912  jmp     short loc_1800D0933
0x1800d0914  mov     rax, [rsp+268h+string]
0x1800d0919  xor     ecx, ecx; string
0x1800d091b  mov     [rsi], rax
0x1800d091e  mov     [rsp+268h+string], 0
0x1800d0927  call    cs:__imp_WindowsDeleteString
0x1800d092d  mov     eax, edi
0x1800d092f  jmp     short loc_1800D0933
0x1800d0931  xor     eax, eax
0x1800d0933  mov     rcx, [rsp+268h+var_18]
0x1800d093b  xor     rcx, rsp; StackCookie
0x1800d093e  call    __security_check_cookie
0x1800d0943  lea     r11, [rsp+268h+var_8]
0x1800d094b  mov     rbx, [r11+18h]
0x1800d094f  mov     rsi, [r11+28h]
0x1800d0953  mov     rsp, r11
0x1800d0956  pop     rdi
0x1800d0957  retn
```
