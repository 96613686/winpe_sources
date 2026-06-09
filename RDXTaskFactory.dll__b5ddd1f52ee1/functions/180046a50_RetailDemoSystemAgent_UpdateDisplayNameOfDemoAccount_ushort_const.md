# RetailDemoSystemAgent::UpdateDisplayNameOfDemoAccount(ushort const *)

- ea: `0x180046a50`
- end: `0x180046bf7`
- name: `?UpdateDisplayNameOfDemoAccount@RetailDemoSystemAgent@@UEAAJPEBG@Z`
- size: `423`
- prototype: `__int64 __fastcall(RetailDemoSystemAgent *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003390`
- `0x180003e00`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18001ff9c`
- `0x1800349cc`
- `0x18003decc`
- `0x180040694`
- `0x180046a50`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046ace`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046ace`
- `samcli!NetUserSetInfo` at `0x180046b34`
- `samcli!NetUserSetInfo` at `0x180046b34`

## string_xrefs

- `0x180046ac0`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180046afc`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`
- `0x180046b48`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`
- `0x180046bb5`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall RetailDemoSystemAgent::UpdateDisplayNameOfDemoAccount(
        RetailDemoSystemAgent *this,
        const unsigned __int16 *a2)
{
  int ValueW; // ebx
  bool v4; // sf
  DWORD v6; // eax
  _QWORD *v7; // rax
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE buf[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR username[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(username, 0, 0x202u);
  pcbData[0] = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Account",
             2u,
             0,
             username,
             pcbData);
  if ( ValueW )
  {
    username[0] = 0;
    v4 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  v4 = ValueW < 0;
LABEL_5:
  if ( v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
      (const char *)(unsigned int)ValueW,
      pdwType);
    return ValueW;
  }
  else
  {
    *(_QWORD *)buf = a2;
    v6 = NetUserSetInfo(0, username, 0x3F3u, buf, 0);
    if ( v6 )
    {
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x5B,
               (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
               (const char *)v6,
               pdwTypea);
    }
    else
    {
      v7 = wil::MakeAndInitializeOrThrow<RetailDemoUserAgent,>(v16);
      if ( *v7 )
      {
        v8 = *v7 + 72LL;
        *(_QWORD *)pcbData = v8;
      }
      else
      {
        *(_QWORD *)pcbData = 0;
        v8 = 0;
      }
      *v7 = 0;
      Microsoft::WRL::ComPtr<RetailDemoUserAgent>::InternalRelease(v16);
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 176LL))(v8);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
          (const char *)(unsigned int)v9,
          pdwTypea);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pcbData, v10, v11);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180046a50  mov     [rsp-8+arg_0], rbx
0x180046a55  mov     [rsp-8+arg_10], rdi
0x180046a5a  push    rbp
0x180046a5b  lea     rbp, [rsp-180h]
0x180046a63  sub     rsp, 280h
0x180046a6a  mov     rax, cs:__security_cookie
0x180046a71  xor     rax, rsp
0x180046a74  mov     [rbp+180h+var_10], rax
0x180046a7b  mov     rdi, rdx
0x180046a7e  mov     ebx, 202h
0x180046a83  mov     r8d, ebx; Size
0x180046a86  xor     edx, edx; Val
0x180046a88  lea     rcx, [rsp+280h+username]; void *
0x180046a8d  call    memset_0
0x180046a92  mov     [rsp+280h+var_240], ebx
0x180046a96  lea     rax, [rsp+280h+var_240]
0x180046a9b  mov     [rsp+280h+pcbData], rax; pcbData
0x180046aa0  lea     rax, [rsp+280h+username]
0x180046aa5  mov     [rsp+280h+pvData], rax; pvData
0x180046aaa  mov     [rsp+280h+pdwType], 0; int
0x180046ab3  mov     r9d, 2; dwFlags
0x180046ab9  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x180046ac0  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180046ac7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180046ace  call    cs:__imp_RegGetValueW
0x180046ad4  mov     ebx, eax
0x180046ad6  test    eax, eax
0x180046ad8  jz      short loc_180046AEE
0x180046ada  xor     eax, eax
0x180046adc  mov     [rsp+280h+username], ax
0x180046ae1  test    ebx, ebx
0x180046ae3  jle     short loc_180046AF0
0x180046ae5  movzx   ebx, bx
0x180046ae8  or      ebx, 80070000h
0x180046aee  test    ebx, ebx
0x180046af0  jns     short loc_180046B14
0x180046af2  mov     rcx, [rbp+188h]; this
0x180046af9  mov     r9d, ebx; char *
0x180046afc  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180046b03  mov     edx, 52h ; 'R'; void *
0x180046b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046b0d  mov     eax, ebx
0x180046b0f  jmp     loc_180046BD3
0x180046b14  mov     qword ptr [rsp+280h+buf], rdi
0x180046b19  mov     [rsp+280h+pdwType], 0; int
0x180046b22  lea     r9, [rsp+280h+buf]; buf
0x180046b27  mov     r8d, 3F3h; level
0x180046b2d  lea     rdx, [rsp+280h+username]; username
0x180046b32  xor     ecx, ecx; servername
0x180046b34  call    cs:__imp_NetUserSetInfo
0x180046b3a  test    eax, eax
0x180046b3c  jz      short loc_180046B5B
0x180046b3e  mov     rcx, [rbp+188h]; this
0x180046b45  mov     r9d, eax; char *
0x180046b48  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180046b4f  mov     edx, 5Bh ; '['; void *
0x180046b54  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046b59  jmp     short loc_180046BD3
0x180046b5b  lea     rcx, [rsp+280h+var_230]
0x180046b60  call    ??$MakeAndInitializeOrThrow@VRetailDemoUserAgent@@$$V@wil@@YA?AV?$ComPtr@VRetailDemoUserAgent@@@WRL@Microsoft@@XZ; wil::MakeAndInitializeOrThrow<RetailDemoUserAgent,>(void)
0x180046b65  mov     rbx, [rax]
0x180046b68  test    rbx, rbx
0x180046b6b  jz      short loc_180046B78
0x180046b6d  add     rbx, 48h ; 'H'
0x180046b71  mov     qword ptr [rsp+280h+var_240], rbx
0x180046b76  jmp     short loc_180046B83
0x180046b78  mov     qword ptr [rsp+280h+var_240], 0
0x180046b81  xor     ebx, ebx
0x180046b83  mov     qword ptr [rax], 0
0x180046b8a  lea     rcx, [rsp+280h+var_230]
0x180046b8f  call    ?InternalRelease@?$ComPtr@VRetailDemoUserAgent@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<RetailDemoUserAgent>::InternalRelease(void)
0x180046b94  nop
0x180046b95  mov     rax, [rbx]
0x180046b98  mov     rcx, rbx
0x180046b9b  mov     rax, [rax+0B0h]
0x180046ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ba7  mov     rcx, [rbp+188h]; this
0x180046bae  test    eax, eax
0x180046bb0  jns     short loc_180046BC7
0x180046bb2  mov     r9d, eax; char *
0x180046bb5  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180046bbc  mov     edx, 5Dh ; ']'; void *
0x180046bc1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046bc6  nop
0x180046bc7  lea     rcx, [rsp+280h+var_240]
0x180046bcc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046bd1  xor     eax, eax
0x180046bd3  mov     rcx, [rbp+180h+var_10]
0x180046bda  xor     rcx, rsp; StackCookie
0x180046bdd  call    __security_check_cookie
0x180046be2  lea     r11, [rsp+280h+var_s0]
0x180046bea  mov     rbx, [r11+10h]
0x180046bee  mov     rdi, [r11+20h]
0x180046bf2  mov     rsp, r11
0x180046bf5  pop     rbp
0x180046bf6  retn
```
