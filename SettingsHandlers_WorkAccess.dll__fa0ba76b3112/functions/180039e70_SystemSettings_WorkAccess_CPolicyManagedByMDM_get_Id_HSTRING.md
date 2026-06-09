# SystemSettings::WorkAccess::CPolicyManagedByMDM::get_Id(HSTRING__ * *)

- ea: `0x180039e70`
- end: `0x180039f37`
- name: `?get_Id@CPolicyManagedByMDM@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `199`
- prototype: `int(SystemSettings::WorkAccess::CPolicyManagedByMDM *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x180039e70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ef6`

## string_xrefs

- `0x180039ec9`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180039e9b`: `SystemSettings_WorkAccess_MdmManagedPolicyList%ws`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CPolicyManagedByMDM::get_Id(
        SystemSettings::WorkAccess::CPolicyManagedByMDM *this,
        HSTRING *a2)
{
  HRESULT String; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  WCHAR sourceString[264]; // [rsp+20h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  String = StringCchPrintfW(
             sourceString,
             0x104u,
             L"SystemSettings_WorkAccess_MdmManagedPolicyList%ws",
             *((_QWORD *)this + 27));
  if ( String < 0 )
  {
    v4 = 1530;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)(unsigned int)String,
      *(int *)sourceString);
    return (unsigned int)String;
  }
  v6 = -1;
  do
    ++v6;
  while ( sourceString[v6] );
  String = WindowsCreateString(sourceString, v6, a2);
  if ( String < 0 )
  {
    v4 = 1532;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180039e70  mov     [rsp+arg_10], rbx
0x180039e75  mov     [rsp+arg_18], rsi
0x180039e7a  push    rdi
0x180039e7b  sub     rsp, 240h
0x180039e82  mov     rax, cs:__security_cookie
0x180039e89  xor     rax, rsp
0x180039e8c  mov     [rsp+248h+var_18], rax
0x180039e94  mov     r9, [rcx+0D8h]
0x180039e9b  lea     r8, aSystemsettings_15; "SystemSettings_WorkAccess_MdmManagedPol"...
0x180039ea2  mov     rdi, rdx
0x180039ea5  lea     rcx, [rsp+248h+sourceString]; unsigned __int16 *
0x180039eaa  mov     edx, 104h; unsigned __int64
0x180039eaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039eb4  xor     esi, esi
0x180039eb6  mov     ebx, eax
0x180039eb8  test    eax, eax
0x180039eba  jns     short loc_180039EDC
0x180039ebc  mov     edx, 5FAh; void *
0x180039ec1  mov     rcx, [rsp+248h]; this
0x180039ec9  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039ed0  mov     r9d, ebx; char *
0x180039ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ed8  mov     eax, ebx
0x180039eda  jmp     short loc_180039F11
0x180039edc  lea     rax, [rsp+248h+sourceString]
0x180039ee1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039ee5  inc     rdx; length
0x180039ee8  cmp     [rax+rdx*2], si
0x180039eec  jnz     short loc_180039EE5
0x180039eee  mov     r8, rdi; string
0x180039ef1  lea     rcx, [rsp+248h+sourceString]; sourceString
0x180039ef6  call    cs:__imp_WindowsCreateString
0x180039efd  nop     dword ptr [rax+rax+00h]
0x180039f02  mov     ebx, eax
0x180039f04  test    eax, eax
0x180039f06  jns     short loc_180039F0F
0x180039f08  mov     edx, 5FCh
0x180039f0d  jmp     short loc_180039EC1
0x180039f0f  xor     eax, eax
0x180039f11  mov     rcx, [rsp+248h+var_18]
0x180039f19  xor     rcx, rsp; StackCookie
0x180039f1c  call    __security_check_cookie
0x180039f21  lea     r11, [rsp+248h+var_8]
0x180039f29  mov     rbx, [r11+20h]
0x180039f2d  mov     rsi, [r11+28h]
0x180039f31  mov     rsp, r11
0x180039f34  pop     rdi
0x180039f35  retn
```
