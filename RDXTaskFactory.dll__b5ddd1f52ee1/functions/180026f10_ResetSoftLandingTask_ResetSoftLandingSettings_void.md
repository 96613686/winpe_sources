# ResetSoftLandingTask::ResetSoftLandingSettings(void)

- ea: `0x180026f10`
- end: `0x180027035`
- name: `?ResetSoftLandingSettings@ResetSoftLandingTask@@AEAAXXZ`
- size: `293`
- prototype: `void(ResetSoftLandingTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026800`

## callees

- `0x18001094c`
- `0x18001f8d4`
- `0x180026f10`

## import_xrefs

- `SHCORE!SHDeleteKeyW` at `0x180026f2e`
- `SHCORE!SHDeleteKeyW` at `0x180026f2e`

## string_xrefs

- `0x180026f3d`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`
- `0x180026f73`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`
- `0x180026fa9`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`
- `0x180026fdf`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`
- `0x180027015`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\resetsoftlandingtask.cpp`

## pseudocode

```c
void __fastcall ResetSoftLandingTask::ResetSoftLandingSettings(ResetSoftLandingTask *this)
{
  LSTATUS v1; // eax
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = SHDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding");
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v1,
      v6);
  v2 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding",
         L"MaximumCreativeCount",
         2u);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v2,
      v6);
  v3 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding",
         L"CreativeCountInterval",
         5u);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v3,
      v6);
  v4 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding",
         L"LastCreativeExpirationTime",
         5u);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v4,
      v6);
  v5 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SoftLanding",
         L"VisibleExpiration",
         5u);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\resetsoftlandingtask.cpp",
      (const char *)(unsigned int)v5,
      v6);
}

```

## disassembly

```asm
0x180026f10  mov     [rsp+arg_0], rbx
0x180026f15  push    rdi; int
0x180026f16  sub     rsp, 20h
0x180026f1a  lea     rbx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026f21  mov     rdi, 0FFFFFFFF80000001h
0x180026f28  mov     rdx, rbx; pszSubKey
0x180026f2b  mov     rcx, rdi; hkey
0x180026f2e  call    cs:__imp_SHDeleteKeyW
0x180026f34  test    eax, eax
0x180026f36  jns     short loc_180026F52
0x180026f38  mov     rcx, [rsp+28h]; this
0x180026f3d  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026f44  mov     r9d, eax; char *
0x180026f47  mov     edx, 45h ; 'E'; void *
0x180026f4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026f52  mov     r9d, 2; unsigned int
0x180026f58  lea     r8, aMaximumcreativ; "MaximumCreativeCount"
0x180026f5f  mov     rdx, rbx; unsigned __int16 *
0x180026f62  mov     rcx, rdi; HKEY
0x180026f65  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180026f6a  test    eax, eax
0x180026f6c  jns     short loc_180026F88
0x180026f6e  mov     rcx, [rsp+28h]; this
0x180026f73  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026f7a  mov     r9d, eax; char *
0x180026f7d  mov     edx, 48h ; 'H'; void *
0x180026f82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026f88  mov     r9d, 5; unsigned int
0x180026f8e  lea     r8, aCreativecounti; "CreativeCountInterval"
0x180026f95  mov     rdx, rbx; unsigned __int16 *
0x180026f98  mov     rcx, rdi; HKEY
0x180026f9b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180026fa0  test    eax, eax
0x180026fa2  jns     short loc_180026FBE
0x180026fa4  mov     rcx, [rsp+28h]; this
0x180026fa9  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026fb0  mov     r9d, eax; char *
0x180026fb3  mov     edx, 49h ; 'I'; void *
0x180026fb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026fbe  mov     r9d, 5; unsigned int
0x180026fc4  lea     r8, aLastcreativeex; "LastCreativeExpirationTime"
0x180026fcb  mov     rdx, rbx; unsigned __int16 *
0x180026fce  mov     rcx, rdi; HKEY
0x180026fd1  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180026fd6  test    eax, eax
0x180026fd8  jns     short loc_180026FF4
0x180026fda  mov     rcx, [rsp+28h]; this
0x180026fdf  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180026fe6  mov     r9d, eax; char *
0x180026fe9  mov     edx, 4Ch ; 'L'; void *
0x180026fee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026ff4  mov     r9d, 5; unsigned int
0x180026ffa  lea     r8, aVisibleexpirat; "VisibleExpiration"
0x180027001  mov     rdx, rbx; unsigned __int16 *
0x180027004  mov     rcx, rdi; HKEY
0x180027007  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002700c  test    eax, eax
0x18002700e  jns     short loc_18002702A
0x180027010  mov     rcx, [rsp+28h]; this
0x180027015  lea     r8, aPcshellShellRe_23; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002701c  mov     r9d, eax; char *
0x18002701f  mov     edx, 4Dh ; 'M'; void *
0x180027024  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002702a  mov     rbx, [rsp+28h+arg_0]
0x18002702f  add     rsp, 20h
0x180027033  pop     rdi
0x180027034  retn
```
