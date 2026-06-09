# RetailDemoUserAgent::SuppressWindowsUpdateNotifications(void)

- ea: `0x180041148`
- end: `0x1800412c9`
- name: `?SuppressWindowsUpdateNotifications@RetailDemoUserAgent@@AEAAJXZ`
- size: `385`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180040500`

## callees

- `0x18000aa7c`
- `0x180041148`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800411a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004124f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800411a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004124f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800411d6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041281`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800411d6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041281`

## string_xrefs

- `0x1800411f7`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800412a2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180041193`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x1800411cc`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x180041245`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x180041277`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`

## pseudocode

```c
__int64 __fastcall RetailDemoUserAgent::SuppressWindowsUpdateNotifications(RetailDemoUserAgent *this)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int lpData; // [rsp+20h] [rbp-38h]
  int lpDataa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+64h] [rbp+Ch]
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  Data = 0;
  pvData = 1;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
          L"IsExpedited",
          0x10u,
          0,
          &pvData,
          &pcbData)
    && !pvData )
  {
    goto LABEL_7;
  }
  v1 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
         L"IsExpedited",
         4u,
         &Data,
         4u);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x976,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)v2,
      lpData);
    return v2;
  }
  else
  {
LABEL_7:
    pvData = 1;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
            L"RestartNotificationsAllowed2",
            0x10u,
            0,
            &pvData,
            &pcbData)
      && !pvData )
    {
      return 0;
    }
    v4 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
           L"RestartNotificationsAllowed2",
           4u,
           &Data,
           4u);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x980,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)v5,
        lpDataa);
      return v5;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180041148  mov     r11, rsp
0x18004114b  mov     [r11+8], rcx
0x18004114f  push    rbx
0x180041150  push    rsi
0x180041151  push    r15
0x180041153  sub     rsp, 40h
0x180041157  mov     [rsp+58h+Data], 0
0x18004115f  mov     [rsp+58h+pvData], 1
0x180041167  mov     esi, 4
0x18004116c  mov     [rsp+58h+arg_8], esi
0x180041170  lea     rax, [r11+10h]
0x180041174  mov     [r11-28h], rax
0x180041178  lea     rax, [r11+8]
0x18004117c  mov     [r11-30h], rax
0x180041180  mov     qword ptr [r11-38h], 0
0x180041188  lea     r9d, [rsi+0Ch]; dwFlags
0x18004118c  lea     r8, aIsexpedited; "IsExpedited"
0x180041193  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x18004119a  mov     r15, 0FFFFFFFF80000002h
0x1800411a1  mov     rcx, r15; hkey
0x1800411a4  call    cs:__imp_RegGetValueW
0x1800411aa  test    eax, eax
0x1800411ac  jnz     short loc_1800411B4
0x1800411ae  cmp     [rsp+58h+pvData], eax
0x1800411b2  jz      short loc_18004120F
0x1800411b4  mov     [rsp+58h+cbData], esi; cbData
0x1800411b8  lea     rax, [rsp+58h+Data]
0x1800411bd  mov     [rsp+58h+lpData], rax; int
0x1800411c2  mov     r9d, esi; dwType
0x1800411c5  lea     r8, aIsexpedited; "IsExpedited"
0x1800411cc  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x1800411d3  mov     rcx, r15; hKey
0x1800411d6  call    cs:__imp_RegSetKeyValueW
0x1800411dc  mov     ebx, eax
0x1800411de  test    eax, eax
0x1800411e0  jle     short loc_1800411EB
0x1800411e2  movzx   ebx, ax
0x1800411e5  or      ebx, 80070000h
0x1800411eb  test    ebx, ebx
0x1800411ed  jns     short loc_18004120F
0x1800411ef  mov     rcx, [rsp+58h]; this
0x1800411f4  mov     r9d, ebx; char *
0x1800411f7  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800411fe  mov     edx, 976h; void *
0x180041203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041208  mov     eax, ebx
0x18004120a  jmp     loc_1800412BF
0x18004120f  mov     [rsp+58h+pvData], 1
0x180041217  mov     [rsp+58h+arg_8], esi
0x18004121b  lea     rax, [rsp+58h+arg_8]
0x180041220  mov     [rsp+58h+pcbData], rax; pcbData
0x180041225  lea     rax, [rsp+58h+pvData]
0x18004122a  mov     qword ptr [rsp+58h+cbData], rax; pvData
0x18004122f  mov     [rsp+58h+lpData], 0; pdwType
0x180041238  mov     r9d, 10h; dwFlags
0x18004123e  lea     r8, aRestartnotific; "RestartNotificationsAllowed2"
0x180041245  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x18004124c  mov     rcx, r15; hkey
0x18004124f  call    cs:__imp_RegGetValueW
0x180041255  test    eax, eax
0x180041257  jnz     short loc_18004125F
0x180041259  cmp     [rsp+58h+pvData], eax
0x18004125d  jz      short loc_1800412B7
0x18004125f  mov     [rsp+58h+cbData], esi; cbData
0x180041263  lea     rax, [rsp+58h+Data]
0x180041268  mov     [rsp+58h+lpData], rax; int
0x18004126d  mov     r9d, esi; dwType
0x180041270  lea     r8, aRestartnotific; "RestartNotificationsAllowed2"
0x180041277  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x18004127e  mov     rcx, r15; hKey
0x180041281  call    cs:__imp_RegSetKeyValueW
0x180041287  mov     ebx, eax
0x180041289  test    eax, eax
0x18004128b  jle     short loc_180041296
0x18004128d  movzx   ebx, ax
0x180041290  or      ebx, 80070000h
0x180041296  test    ebx, ebx
0x180041298  jns     short loc_1800412B7
0x18004129a  mov     rcx, [rsp+58h]; this
0x18004129f  mov     r9d, ebx; char *
0x1800412a2  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800412a9  mov     edx, 980h; void *
0x1800412ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800412b3  mov     eax, ebx
0x1800412b5  jmp     short loc_1800412BF
0x1800412b7  xor     eax, eax
0x1800412b9  jmp     short loc_1800412BF
0x1800412bb  mov     eax, [rsp+58h+pvData]
0x1800412bf  add     rsp, 40h
0x1800412c3  pop     r15
0x1800412c5  pop     rsi
0x1800412c6  pop     rbx
0x1800412c7  retn
```
