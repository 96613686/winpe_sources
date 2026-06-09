# SystemSettings::WorkAccess::CApplicationManagedByMDM::get_Id(HSTRING__ * *)

- ea: `0x180039da0`
- end: `0x180039e67`
- name: `?get_Id@CApplicationManagedByMDM@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `199`
- prototype: `int(SystemSettings::WorkAccess::CApplicationManagedByMDM *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x180039da0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e26`

## string_xrefs

- `0x180039df9`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180039dcb`: `SystemSettings_WorkAccess_AppManagedByMDMList%ws`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CApplicationManagedByMDM::get_Id(
        SystemSettings::WorkAccess::CApplicationManagedByMDM *this,
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
             L"SystemSettings_WorkAccess_AppManagedByMDMList%ws",
             *((_QWORD *)this + 27));
  if ( String < 0 )
  {
    v4 = 2114;
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
    v4 = 2116;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180039da0  mov     [rsp+arg_10], rbx
0x180039da5  mov     [rsp+arg_18], rsi
0x180039daa  push    rdi
0x180039dab  sub     rsp, 240h
0x180039db2  mov     rax, cs:__security_cookie
0x180039db9  xor     rax, rsp
0x180039dbc  mov     [rsp+248h+var_18], rax
0x180039dc4  mov     r9, [rcx+0D8h]
0x180039dcb  lea     r8, aSystemsettings_22; "SystemSettings_WorkAccess_AppManagedByM"...
0x180039dd2  mov     rdi, rdx
0x180039dd5  lea     rcx, [rsp+248h+sourceString]; unsigned __int16 *
0x180039dda  mov     edx, 104h; unsigned __int64
0x180039ddf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039de4  xor     esi, esi
0x180039de6  mov     ebx, eax
0x180039de8  test    eax, eax
0x180039dea  jns     short loc_180039E0C
0x180039dec  mov     edx, 842h; void *
0x180039df1  mov     rcx, [rsp+248h]; this
0x180039df9  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039e00  mov     r9d, ebx; char *
0x180039e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e08  mov     eax, ebx
0x180039e0a  jmp     short loc_180039E41
0x180039e0c  lea     rax, [rsp+248h+sourceString]
0x180039e11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039e15  inc     rdx; length
0x180039e18  cmp     [rax+rdx*2], si
0x180039e1c  jnz     short loc_180039E15
0x180039e1e  mov     r8, rdi; string
0x180039e21  lea     rcx, [rsp+248h+sourceString]; sourceString
0x180039e26  call    cs:__imp_WindowsCreateString
0x180039e2d  nop     dword ptr [rax+rax+00h]
0x180039e32  mov     ebx, eax
0x180039e34  test    eax, eax
0x180039e36  jns     short loc_180039E3F
0x180039e38  mov     edx, 844h
0x180039e3d  jmp     short loc_180039DF1
0x180039e3f  xor     eax, eax
0x180039e41  mov     rcx, [rsp+248h+var_18]
0x180039e49  xor     rcx, rsp; StackCookie
0x180039e4c  call    __security_check_cookie
0x180039e51  lea     r11, [rsp+248h+var_8]
0x180039e59  mov     rbx, [r11+20h]
0x180039e5d  mov     rsi, [r11+28h]
0x180039e61  mov     rsp, r11
0x180039e64  pop     rdi
0x180039e65  retn
```
