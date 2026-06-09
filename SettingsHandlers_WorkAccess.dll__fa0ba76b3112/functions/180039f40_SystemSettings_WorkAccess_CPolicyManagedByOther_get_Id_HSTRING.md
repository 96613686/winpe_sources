# SystemSettings::WorkAccess::CPolicyManagedByOther::get_Id(HSTRING__ * *)

- ea: `0x180039f40`
- end: `0x18003a007`
- name: `?get_Id@CPolicyManagedByOther@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `199`
- prototype: `int(SystemSettings::WorkAccess::CPolicyManagedByOther *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x180039f40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039fc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039fc6`

## string_xrefs

- `0x180039f99`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180039f6b`: `SystemSettings_WorkAccess_MdmManagedOtherList%ws`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CPolicyManagedByOther::get_Id(
        SystemSettings::WorkAccess::CPolicyManagedByOther *this,
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
             L"SystemSettings_WorkAccess_MdmManagedOtherList%ws",
             *((_QWORD *)this + 26));
  if ( String < 0 )
  {
    v4 = 1718;
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
    v4 = 1720;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180039f40  mov     [rsp+arg_10], rbx
0x180039f45  mov     [rsp+arg_18], rsi
0x180039f4a  push    rdi
0x180039f4b  sub     rsp, 240h
0x180039f52  mov     rax, cs:__security_cookie
0x180039f59  xor     rax, rsp
0x180039f5c  mov     [rsp+248h+var_18], rax
0x180039f64  mov     r9, [rcx+0D0h]
0x180039f6b  lea     r8, aSystemsettings_28; "SystemSettings_WorkAccess_MdmManagedOth"...
0x180039f72  mov     rdi, rdx
0x180039f75  lea     rcx, [rsp+248h+sourceString]; unsigned __int16 *
0x180039f7a  mov     edx, 104h; unsigned __int64
0x180039f7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039f84  xor     esi, esi
0x180039f86  mov     ebx, eax
0x180039f88  test    eax, eax
0x180039f8a  jns     short loc_180039FAC
0x180039f8c  mov     edx, 6B6h; void *
0x180039f91  mov     rcx, [rsp+248h]; this
0x180039f99  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180039fa0  mov     r9d, ebx; char *
0x180039fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fa8  mov     eax, ebx
0x180039faa  jmp     short loc_180039FE1
0x180039fac  lea     rax, [rsp+248h+sourceString]
0x180039fb1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039fb5  inc     rdx; length
0x180039fb8  cmp     [rax+rdx*2], si
0x180039fbc  jnz     short loc_180039FB5
0x180039fbe  mov     r8, rdi; string
0x180039fc1  lea     rcx, [rsp+248h+sourceString]; sourceString
0x180039fc6  call    cs:__imp_WindowsCreateString
0x180039fcd  nop     dword ptr [rax+rax+00h]
0x180039fd2  mov     ebx, eax
0x180039fd4  test    eax, eax
0x180039fd6  jns     short loc_180039FDF
0x180039fd8  mov     edx, 6B8h
0x180039fdd  jmp     short loc_180039F91
0x180039fdf  xor     eax, eax
0x180039fe1  mov     rcx, [rsp+248h+var_18]
0x180039fe9  xor     rcx, rsp; StackCookie
0x180039fec  call    __security_check_cookie
0x180039ff1  lea     r11, [rsp+248h+var_8]
0x180039ff9  mov     rbx, [r11+20h]
0x180039ffd  mov     rsi, [r11+28h]
0x18003a001  mov     rsp, r11
0x18003a004  pop     rdi
0x18003a005  retn
```
