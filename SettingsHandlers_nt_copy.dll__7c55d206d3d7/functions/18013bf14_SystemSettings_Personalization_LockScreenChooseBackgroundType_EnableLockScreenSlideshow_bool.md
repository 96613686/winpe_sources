# SystemSettings::Personalization::LockScreenChooseBackgroundType::EnableLockScreenSlideshow(bool)

- ea: `0x18013bf14`
- end: `0x18013c0fa`
- name: `?EnableLockScreenSlideshow@LockScreenChooseBackgroundType@Personalization@SystemSettings@@AEAAJ_N@Z`
- size: `486`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::LockScreenChooseBackgroundType *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18013bc40`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180041004`
- `0x18004e7c0`
- `0x18004e918`
- `0x18013bf14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18013bf56`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18013bf56`
- `USER32!SystemParametersInfoW` at `0x18013bfbe`
- `USER32!SystemParametersInfoW` at `0x18013c029`
- `USER32!SystemParametersInfoW` at `0x18013bfbe`
- `USER32!SystemParametersInfoW` at `0x18013c029`
- `SHLWAPI!SHDeleteValueW` at `0x18013c072`
- `SHLWAPI!SHDeleteValueW` at `0x18013c072`
- `SHLWAPI!SHSetValueW` at `0x18013c0a8`
- `SHLWAPI!SHSetValueW` at `0x18013c0a8`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18013bfdf`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18013c04a`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18013bfdf`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18013c04a`

## pseudocode

```c
int __fastcall SystemSettings::Personalization::LockScreenChooseBackgroundType::EnableLockScreenSlideshow(
        SystemSettings::Personalization::LockScreenChooseBackgroundType *this,
        unsigned __int8 a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // r9d
  int BOOLWithREGSAM; // eax
  int v5; // ecx
  unsigned int v6; // eax
  unsigned int pvData; // [rsp+20h] [rbp-88h]
  int v9; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v10[3]; // [rsp+34h] [rbp-74h] BYREF
  struct _SYSTEM_POWER_CAPABILITIES spc; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v2 = a2;
  if ( a2 )
  {
    RegDeleteKeyValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"SCRNSAVE.EXE");
    v9 = 0;
    BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
                       L"SlideshowAutoLock",
                       v3,
                       &v9);
    v5 = BOOLWithREGSAM;
    if ( BOOLWithREGSAM < 0 )
    {
      if ( (BOOLWithREGSAM & 0x1FFF0000) == 0x70000 )
        v5 = (unsigned __int16)BOOLWithREGSAM;
      if ( v5 != 2 )
        goto LABEL_9;
    }
    else if ( !v9 )
    {
      goto LABEL_9;
    }
    SystemParametersInfoW(0xA9u, 1u, 0, 1u);
LABEL_9:
    memset_0(&spc, 0, sizeof(spc));
    if ( GetPwrCapabilities(&spc) && !spc.spare2[2] )
      SHRegSetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"DelayLockInterval", 0);
    goto LABEL_15;
  }
  SystemParametersInfoW(0xA9u, 0, 0, 1u);
  memset_0(&spc, 0, sizeof(spc));
  if ( GetPwrCapabilities(&spc) && !spc.spare2[2] )
    SHDeleteValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"DelayLockInterval");
LABEL_15:
  v10[0] = v2;
  v6 = SHSetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
         L"SlideshowEnabled",
         4u,
         v10,
         4u);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x14F,
             (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\lockscreen.cpp",
             (const char *)v6,
             pvData);
  else
    return 0;
}

```

## disassembly

```asm
0x18013bf14  mov     [rsp+arg_0], rbx
0x18013bf19  push    rsi
0x18013bf1a  sub     rsp, 0A0h
0x18013bf21  mov     rax, cs:__security_cookie
0x18013bf28  xor     rax, rsp
0x18013bf2b  mov     [rsp+0A8h+var_18], rax
0x18013bf33  movzx   ebx, dl
0x18013bf36  mov     rsi, 0FFFFFFFF80000001h
0x18013bf3d  test    dl, dl
0x18013bf3f  jz      loc_18013C019
0x18013bf45  lea     r8, aScrnsaveExe; "SCRNSAVE.EXE"
0x18013bf4c  mov     rcx, rsi; hKey
0x18013bf4f  lea     rdx, pszSubKey; "Control Panel\\Desktop"
0x18013bf56  call    cs:__imp_RegDeleteKeyValueW
0x18013bf5d  nop     dword ptr [rax+rax+00h]
0x18013bf62  lea     rax, [rsp+0A8h+var_78]
0x18013bf67  mov     [rsp+0A8h+var_78], 0
0x18013bf6f  lea     r8, aSlideshowautol; "SlideshowAutoLock"
0x18013bf76  mov     [rsp+0A8h+pvData], rax; int *
0x18013bf7b  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18013bf82  mov     rcx, rsi; HKEY
0x18013bf85  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18013bf8a  mov     ecx, eax
0x18013bf8c  test    eax, eax
0x18013bf8e  js      short loc_18013BF99
0x18013bf90  cmp     [rsp+0A8h+var_78], 0
0x18013bf95  jnz     short loc_18013BFAD
0x18013bf97  jmp     short loc_18013BFCA
0x18013bf99  and     eax, 1FFF0000h
0x18013bf9e  cmp     eax, 70000h
0x18013bfa3  jnz     short loc_18013BFA8
0x18013bfa5  movzx   ecx, cx
0x18013bfa8  cmp     ecx, 2
0x18013bfab  jnz     short loc_18013BFCA
0x18013bfad  mov     r9d, 1; fWinIni
0x18013bfb3  xor     r8d, r8d; pvParam
0x18013bfb6  mov     edx, r9d; uiParam
0x18013bfb9  mov     ecx, 0A9h; uiAction
0x18013bfbe  call    cs:__imp_SystemParametersInfoW
0x18013bfc5  nop     dword ptr [rax+rax+00h]
0x18013bfca  xor     edx, edx; Val
0x18013bfcc  lea     rcx, [rsp+0A8h+spc]; void *
0x18013bfd1  lea     r8d, [rdx+4Ch]; Size
0x18013bfd5  call    memset_0
0x18013bfda  lea     rcx, [rsp+0A8h+spc]; lpspc
0x18013bfdf  call    cs:__imp_GetPwrCapabilities
0x18013bfe6  nop     dword ptr [rax+rax+00h]
0x18013bfeb  test    al, al
0x18013bfed  jz      loc_18013C07E
0x18013bff3  cmp     [rsp+0A8h+spc.spare2+2], 0
0x18013bff8  jnz     loc_18013C07E
0x18013bffe  xor     r9d, r9d; unsigned int
0x18013c001  lea     r8, aDelaylockinter; "DelayLockInterval"
0x18013c008  lea     rdx, pszSubKey; "Control Panel\\Desktop"
0x18013c00f  mov     rcx, rsi; HKEY
0x18013c012  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18013c017  jmp     short loc_18013C07E
0x18013c019  mov     r9d, 1; fWinIni
0x18013c01f  xor     r8d, r8d; pvParam
0x18013c022  xor     edx, edx; uiParam
0x18013c024  mov     ecx, 0A9h; uiAction
0x18013c029  call    cs:__imp_SystemParametersInfoW
0x18013c030  nop     dword ptr [rax+rax+00h]
0x18013c035  xor     edx, edx; Val
0x18013c037  lea     rcx, [rsp+0A8h+spc]; void *
0x18013c03c  lea     r8d, [rdx+4Ch]; Size
0x18013c040  call    memset_0
0x18013c045  lea     rcx, [rsp+0A8h+spc]; lpspc
0x18013c04a  call    cs:__imp_GetPwrCapabilities
0x18013c051  nop     dword ptr [rax+rax+00h]
0x18013c056  test    al, al
0x18013c058  jz      short loc_18013C07E
0x18013c05a  cmp     [rsp+0A8h+spc.spare2+2], 0
0x18013c05f  jnz     short loc_18013C07E
0x18013c061  lea     r8, aDelaylockinter; "DelayLockInterval"
0x18013c068  mov     rcx, rsi; hkey
0x18013c06b  lea     rdx, pszSubKey; "Control Panel\\Desktop"
0x18013c072  call    cs:__imp_SHDeleteValueW
0x18013c079  nop     dword ptr [rax+rax+00h]
0x18013c07e  mov     r9d, 4; dwType
0x18013c084  mov     [rsp+0A8h+var_74], ebx
0x18013c088  lea     rax, [rsp+0A8h+var_74]
0x18013c08d  mov     [rsp+0A8h+cbData], r9d; cbData
0x18013c092  lea     r8, aSlideshowenabl_0; "SlideshowEnabled"
0x18013c099  mov     [rsp+0A8h+pvData], rax; unsigned int
0x18013c09e  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18013c0a5  mov     rcx, rsi; hkey
0x18013c0a8  call    cs:__imp_SHSetValueW
0x18013c0af  nop     dword ptr [rax+rax+00h]
0x18013c0b4  test    eax, eax
0x18013c0b6  jz      short loc_18013C0D6
0x18013c0b8  mov     rcx, [rsp+0A8h]; this
0x18013c0c0  lea     r8, aShellSystemset_10; "shell\\systemsettingsthreshold\\handler"...
0x18013c0c7  mov     r9d, eax; char *
0x18013c0ca  mov     edx, 14Fh; void *
0x18013c0cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013c0d4  jmp     short loc_18013C0D8
0x18013c0d6  xor     eax, eax
0x18013c0d8  mov     rcx, [rsp+0A8h+var_18]
0x18013c0e0  xor     rcx, rsp; StackCookie
0x18013c0e3  call    __security_check_cookie
0x18013c0e8  mov     rbx, [rsp+0A8h+arg_0]
0x18013c0f0  add     rsp, 0A0h
0x18013c0f7  pop     rsi
0x18013c0f8  retn
```
