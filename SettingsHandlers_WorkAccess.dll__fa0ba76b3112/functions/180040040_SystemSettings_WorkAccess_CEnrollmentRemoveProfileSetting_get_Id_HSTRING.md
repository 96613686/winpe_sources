# SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::get_Id(HSTRING__ * *)

- ea: `0x180040040`
- end: `0x18004010a`
- name: `?get_Id@CEnrollmentRemoveProfileSetting@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `202`
- prototype: `int(SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x180040040`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800400c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800400c9`

## string_xrefs

- `0x18004009c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x180040067`: `SystemSettings_Workplace_CEnrollmentRemoveProfileSetting_%ws`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::get_Id(
        SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *this,
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
             L"SystemSettings_Workplace_CEnrollmentRemoveProfileSetting_%ws",
             *((_QWORD *)this + 27));
  if ( String < 0 )
  {
    v4 = 585;
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
    v4 = 587;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180040040  mov     [rsp+arg_10], rbx
0x180040045  mov     [rsp+arg_18], rsi
0x18004004a  push    rdi
0x18004004b  sub     rsp, 240h
0x180040052  mov     rax, cs:__security_cookie
0x180040059  xor     rax, rsp
0x18004005c  mov     [rsp+248h+var_18], rax
0x180040064  mov     rdi, rdx
0x180040067  lea     r8, aSystemsettings_14; "SystemSettings_Workplace_CEnrollmentRem"...
0x18004006e  xor     esi, esi
0x180040070  mov     [rdx], rsi
0x180040073  mov     edx, 104h; unsigned __int64
0x180040078  mov     r9, [rcx+0D8h]
0x18004007f  lea     rcx, [rsp+248h+sourceString]; unsigned __int16 *
0x180040084  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040089  mov     ebx, eax
0x18004008b  test    eax, eax
0x18004008d  jns     short loc_1800400AF
0x18004008f  mov     edx, 249h; void *
0x180040094  mov     rcx, [rsp+248h]; this
0x18004009c  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x1800400a3  mov     r9d, ebx; char *
0x1800400a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800400ab  mov     eax, ebx
0x1800400ad  jmp     short loc_1800400E4
0x1800400af  lea     rax, [rsp+248h+sourceString]
0x1800400b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800400b8  inc     rdx; length
0x1800400bb  cmp     [rax+rdx*2], si
0x1800400bf  jnz     short loc_1800400B8
0x1800400c1  mov     r8, rdi; string
0x1800400c4  lea     rcx, [rsp+248h+sourceString]; sourceString
0x1800400c9  call    cs:__imp_WindowsCreateString
0x1800400d0  nop     dword ptr [rax+rax+00h]
0x1800400d5  mov     ebx, eax
0x1800400d7  test    eax, eax
0x1800400d9  jns     short loc_1800400E2
0x1800400db  mov     edx, 24Bh
0x1800400e0  jmp     short loc_180040094
0x1800400e2  xor     eax, eax
0x1800400e4  mov     rcx, [rsp+248h+var_18]
0x1800400ec  xor     rcx, rsp; StackCookie
0x1800400ef  call    __security_check_cookie
0x1800400f4  lea     r11, [rsp+248h+var_8]
0x1800400fc  mov     rbx, [r11+20h]
0x180040100  mov     rsi, [r11+28h]
0x180040104  mov     rsp, r11
0x180040107  pop     rdi
0x180040108  retn
```
