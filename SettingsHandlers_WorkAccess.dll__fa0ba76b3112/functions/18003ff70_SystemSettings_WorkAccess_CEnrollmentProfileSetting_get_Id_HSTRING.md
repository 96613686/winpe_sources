# SystemSettings::WorkAccess::CEnrollmentProfileSetting::get_Id(HSTRING__ * *)

- ea: `0x18003ff70`
- end: `0x18004003a`
- name: `?get_Id@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `202`
- prototype: `int(SystemSettings::WorkAccess::CEnrollmentProfileSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x18003ff70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003fff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003fff9`

## string_xrefs

- `0x18003ffcc`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003ff97`: `SystemSettings_WorkAccess_EnrollmentListSettings_%ws`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentProfileSetting::get_Id(
        SystemSettings::WorkAccess::CEnrollmentProfileSetting *this,
        HSTRING *a2)
{
  HRESULT String; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  WCHAR sourceString[264]; // [rsp+20h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  *a2 = 0;
  String = StringCchPrintfW(
             sourceString,
             0x104u,
             L"SystemSettings_WorkAccess_EnrollmentListSettings_%ws",
             *((_QWORD *)this + 35));
  if ( String < 0 )
  {
    v4 = 304;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
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
    v4 = 306;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18003ff70  mov     [rsp+arg_10], rbx
0x18003ff75  mov     [rsp+arg_18], rsi
0x18003ff7a  push    rdi
0x18003ff7b  sub     rsp, 240h
0x18003ff82  mov     rax, cs:__security_cookie
0x18003ff89  xor     rax, rsp
0x18003ff8c  mov     [rsp+248h+var_18], rax
0x18003ff94  mov     rdi, rdx
0x18003ff97  lea     r8, aSystemsettings_1; "SystemSettings_WorkAccess_EnrollmentLis"...
0x18003ff9e  xor     esi, esi
0x18003ffa0  mov     [rdx], rsi
0x18003ffa3  mov     edx, 104h; unsigned __int64
0x18003ffa8  mov     r9, [rcx+118h]
0x18003ffaf  lea     rcx, [rsp+248h+sourceString]; unsigned __int16 *
0x18003ffb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ffb9  mov     ebx, eax
0x18003ffbb  test    eax, eax
0x18003ffbd  jns     short loc_18003FFDF
0x18003ffbf  mov     edx, 130h; void *
0x18003ffc4  mov     rcx, [rsp+248h]; this
0x18003ffcc  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003ffd3  mov     r9d, ebx; char *
0x18003ffd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ffdb  mov     eax, ebx
0x18003ffdd  jmp     short loc_180040014
0x18003ffdf  lea     rax, [rsp+248h+sourceString]
0x18003ffe4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003ffe8  inc     rdx; length
0x18003ffeb  cmp     [rax+rdx*2], si
0x18003ffef  jnz     short loc_18003FFE8
0x18003fff1  mov     r8, rdi; string
0x18003fff4  lea     rcx, [rsp+248h+sourceString]; sourceString
0x18003fff9  call    cs:__imp_WindowsCreateString
0x180040000  nop     dword ptr [rax+rax+00h]
0x180040005  mov     ebx, eax
0x180040007  test    eax, eax
0x180040009  jns     short loc_180040012
0x18004000b  mov     edx, 132h
0x180040010  jmp     short loc_18003FFC4
0x180040012  xor     eax, eax
0x180040014  mov     rcx, [rsp+248h+var_18]
0x18004001c  xor     rcx, rsp; StackCookie
0x18004001f  call    __security_check_cookie
0x180040024  lea     r11, [rsp+248h+var_8]
0x18004002c  mov     rbx, [r11+20h]
0x180040030  mov     rsi, [r11+28h]
0x180040034  mov     rsp, r11
0x180040037  pop     rdi
0x180040038  retn
```
