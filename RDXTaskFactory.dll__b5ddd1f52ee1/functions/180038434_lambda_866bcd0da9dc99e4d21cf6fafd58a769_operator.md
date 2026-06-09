# _lambda_866bcd0da9dc99e4d21cf6fafd58a769_::operator()

- ea: `0x180038434`
- end: `0x180038589`
- name: `_lambda_866bcd0da9dc99e4d21cf6fafd58a769_::operator()`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003a290`

## callees

- `0x180003390`
- `0x18001ff9c`
- `0x180038434`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18003849f`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18003852a`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18003849f`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18003852a`

## string_xrefs

- `0x1800384c2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003854d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
void __fastcall lambda_866bcd0da9dc99e4d21cf6fafd58a769_::operator()(
        __int64 *a1,
        char a2,
        char a3,
        unsigned __int8 a4,
        unsigned __int8 a5)
{
  int v7; // edi
  __int64 v8; // rcx
  LONG v9; // eax
  signed int v10; // ebx
  int **v11; // r14
  int v12; // eax
  __int64 v13; // rcx
  LONG v14; // eax
  signed int v15; // ebx
  int **v16; // rsi
  _BYTE setPacket[24]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v7 = -2147467259;
  if ( a2 )
  {
    v8 = *a1;
    *(_QWORD *)&setPacket[16] = 0;
    *(_QWORD *)&setPacket[8] = 0;
    *(_DWORD *)setPacket = 16;
    *(_DWORD *)&setPacket[4] = 24;
    *(_QWORD *)&setPacket[8] = *(_QWORD *)(v8 + 20);
    *(_DWORD *)&setPacket[16] = *(_DWORD *)(v8 + 28);
    *(_DWORD *)&setPacket[20] = a4;
    v9 = DisplayConfigSetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)setPacket);
    v10 = v9;
    if ( v9 )
    {
      v11 = (int **)a1[1];
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF2,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v10,
          *(int *)setPacket);
      if ( **v11 >= 0 )
      {
        v12 = -2147467259;
        if ( v10 < 0 )
          v12 = v10;
        **v11 = v12;
      }
    }
  }
  if ( a3 )
  {
    v13 = *a1;
    *(_QWORD *)&setPacket[16] = 0;
    *(_QWORD *)&setPacket[8] = 0;
    *(_DWORD *)setPacket = 10;
    *(_DWORD *)&setPacket[4] = 24;
    *(_QWORD *)&setPacket[8] = *(_QWORD *)(v13 + 20);
    *(_DWORD *)&setPacket[16] = *(_DWORD *)(v13 + 28);
    *(_DWORD *)&setPacket[20] = a5;
    v14 = DisplayConfigSetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)setPacket);
    v15 = v14;
    if ( v14 )
    {
      v16 = (int **)a1[1];
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB00,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v15,
          *(int *)setPacket);
      if ( **v16 >= 0 )
      {
        if ( v15 < 0 )
          v7 = v15;
        **v16 = v7;
      }
    }
  }
}

```

## disassembly

```asm
0x180038434  push    rbp
0x180038436  push    rbx
0x180038437  push    rsi
0x180038438  push    rdi
0x180038439  push    r14
0x18003843b  push    r15
0x18003843d  mov     rbp, rsp
0x180038440  sub     rsp, 48h
0x180038444  mov     rax, cs:__security_cookie
0x18003844b  xor     rax, rsp
0x18003844e  mov     [rbp+var_10], rax
0x180038452  mov     r15b, r8b
0x180038455  mov     rsi, rcx
0x180038458  mov     edi, 80004005h
0x18003845d  test    dl, dl
0x18003845f  jz      loc_1800384E7
0x180038465  mov     rcx, [rcx]
0x180038468  mov     qword ptr [rbp+setPacket+10h], 0
0x180038470  mov     qword ptr [rbp+setPacket+8], 0
0x180038478  mov     dword ptr [rbp+setPacket], 10h
0x18003847f  mov     dword ptr [rbp+setPacket+4], 18h
0x180038486  mov     rax, [rcx+14h]
0x18003848a  mov     qword ptr [rbp+setPacket+8], rax
0x18003848e  mov     eax, [rcx+1Ch]
0x180038491  lea     rcx, [rbp+setPacket]; setPacket
0x180038495  mov     dword ptr [rbp+setPacket+10h], eax
0x180038498  movzx   eax, r9b
0x18003849c  mov     dword ptr [rbp+setPacket+14h], eax
0x18003849f  call    cs:__imp_DisplayConfigSetDeviceInfo
0x1800384a5  mov     ebx, eax
0x1800384a7  test    eax, eax
0x1800384a9  jz      short loc_1800384E7
0x1800384ab  mov     r14, [rsi+8]
0x1800384af  jle     short loc_1800384BA
0x1800384b1  movzx   ebx, ax
0x1800384b4  or      ebx, 80070000h
0x1800384ba  test    ebx, ebx
0x1800384bc  jns     short loc_1800384D6
0x1800384be  mov     rcx, [rbp+30h]; this
0x1800384c2  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800384c9  mov     r9d, ebx; char *
0x1800384cc  mov     edx, 0AF2h; void *
0x1800384d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800384d6  mov     rcx, [r14]
0x1800384d9  cmp     dword ptr [rcx], 0
0x1800384dc  jl      short loc_1800384E7
0x1800384de  test    ebx, ebx
0x1800384e0  mov     eax, edi
0x1800384e2  cmovs   eax, ebx
0x1800384e5  mov     [rcx], eax
0x1800384e7  test    r15b, r15b
0x1800384ea  jz      loc_180038570
0x1800384f0  mov     rcx, [rsi]
0x1800384f3  mov     qword ptr [rbp+setPacket+10h], 0
0x1800384fb  mov     qword ptr [rbp+setPacket+8], 0
0x180038503  mov     dword ptr [rbp+setPacket], 0Ah
0x18003850a  mov     dword ptr [rbp+setPacket+4], 18h
0x180038511  mov     rax, [rcx+14h]
0x180038515  mov     qword ptr [rbp+setPacket+8], rax
0x180038519  mov     eax, [rcx+1Ch]
0x18003851c  lea     rcx, [rbp+setPacket]; setPacket
0x180038520  mov     dword ptr [rbp+setPacket+10h], eax
0x180038523  movzx   eax, [rbp+arg_20]
0x180038527  mov     dword ptr [rbp+setPacket+14h], eax
0x18003852a  call    cs:__imp_DisplayConfigSetDeviceInfo
0x180038530  mov     ebx, eax
0x180038532  test    eax, eax
0x180038534  jz      short loc_180038570
0x180038536  mov     rsi, [rsi+8]
0x18003853a  jle     short loc_180038545
0x18003853c  movzx   ebx, ax
0x18003853f  or      ebx, 80070000h
0x180038545  test    ebx, ebx
0x180038547  jns     short loc_180038561
0x180038549  mov     rcx, [rbp+30h]; this
0x18003854d  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038554  mov     r9d, ebx; char *
0x180038557  mov     edx, 0B00h; void *
0x18003855c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038561  mov     rax, [rsi]
0x180038564  cmp     dword ptr [rax], 0
0x180038567  jl      short loc_180038570
0x180038569  test    ebx, ebx
0x18003856b  cmovs   edi, ebx
0x18003856e  mov     [rax], edi
0x180038570  mov     rcx, [rbp+var_10]
0x180038574  xor     rcx, rsp; StackCookie
0x180038577  call    __security_check_cookie
0x18003857c  add     rsp, 48h
0x180038580  pop     r15
0x180038582  pop     r14
0x180038584  pop     rdi
0x180038585  pop     rsi
0x180038586  pop     rbx
0x180038587  pop     rbp
0x180038588  retn
```
