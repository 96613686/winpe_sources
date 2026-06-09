# winreLoadSoftwareHive

- ea: `0x180040c28`
- end: `0x180040e4b`
- name: `winreLoadSoftwareHive`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int16 *, PHKEY phkResult)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callers

- `0x1800407ac`
- `0x180040960`
- `0x180040e54`
- `0x180040ff0`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180040c28`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180040db4`
- `ADVAPI32!RegCreateKeyExW` at `0x180040e04`
- `ADVAPI32!RegCreateKeyExW` at `0x180040db4`
- `ADVAPI32!RegCreateKeyExW` at `0x180040e04`
- `ADVAPI32!RegLoadKeyW` at `0x180040d60`
- `ADVAPI32!RegLoadKeyW` at `0x180040d60`

## string_xrefs

- `0x180040cd2`: `System32\config\SOFTWARE`
- `0x180040d31`: `winreLoadSoftwareHive: Failed to construct path to SOFTWARE hive in [%s]: 0x%x`
- `0x180040dc0`: `winreLoadSoftwareHive: Failed to open mount point key: 0x%x`
- `0x180040e10`: `winreLoadSoftwareHive: Failed to open SOFTWARE hive: 0x%x`

## pseudocode

```c
__int64 __fastcall winreLoadSoftwareHive(unsigned __int16 *a1, PHKEY phkResult)
{
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const unsigned __int16 *v7; // r8
  unsigned int KeyW; // eax
  unsigned int Key; // eax
  unsigned int v10; // eax
  unsigned __int64 v12; // [rsp+50h] [rbp-288h] BYREF
  WCHAR File[304]; // [rsp+60h] [rbp-278h] BYREF

  if ( a1 )
  {
    memset_0(File, 0, 0x25Eu);
    v12 = 0;
    v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v12);
    if ( v4 >= 0 )
    {
      if ( !v12 || (v7 = L"%s\\%s", a1[v12 - 1] == 92) )
        v7 = L"%s%s";
      v4 = StringCchPrintfW(File, 0x12Eu, v7, a1, L"System32\\config\\SOFTWARE");
      if ( v4 >= 0 )
      {
LABEL_17:
        KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"$WINRE$SOFTWARE", File);
        v4 = KeyW;
        if ( KeyW )
        {
          UnattendLogW(1, L"winreLoadSoftwareHive: Failed to load [%s]: 0x%x", File, KeyW);
        }
        else
        {
          Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"$WINRE$SOFTWARE", 0, 0, 4u, 0xF003Fu, 0, phkResult, 0);
          v4 = Key;
          if ( Key )
            UnattendLogW(1, L"winreLoadSoftwareHive: Failed to open mount point key: 0x%x", Key);
        }
        return (unsigned int)v4;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 15;
        goto LABEL_13;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 14;
LABEL_13:
        WPP_SF_d(v5[2], v6, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v4);
      }
    }
    v4 = (unsigned __int16)v4;
    if ( (_WORD)v4 )
    {
      UnattendLogW(
        1,
        L"winreLoadSoftwareHive: Failed to construct path to SOFTWARE hive in [%s]: 0x%x",
        a1,
        (unsigned __int16)v4);
      return (unsigned int)v4;
    }
    goto LABEL_17;
  }
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE", 0, 0, 4u, 0xF003Fu, 0, phkResult, 0);
  v4 = v10;
  if ( v10 )
    UnattendLogW(1, L"winreLoadSoftwareHive: Failed to open SOFTWARE hive: 0x%x", v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180040c28  mov     [rsp+arg_10], rbx
0x180040c2d  mov     [rsp+arg_18], rsi
0x180040c32  push    rdi
0x180040c33  sub     rsp, 2D0h
0x180040c3a  mov     rax, cs:__security_cookie
0x180040c41  xor     rax, rsp
0x180040c44  mov     [rsp+2D8h+var_18], rax
0x180040c4c  mov     rsi, rdx
0x180040c4f  mov     rdi, rcx
0x180040c52  test    rcx, rcx
0x180040c55  jz      loc_180040DC9
0x180040c5b  xor     edx, edx; Val
0x180040c5d  lea     rcx, [rsp+2D8h+File]; void *
0x180040c62  mov     r8d, 25Eh; Size
0x180040c68  call    memset_0
0x180040c6d  lea     r8, [rsp+2D8h+var_288]; unsigned __int64 *
0x180040c72  mov     [rsp+2D8h+var_288], 0
0x180040c7b  mov     edx, 7FFFFFFFh; unsigned __int64
0x180040c80  mov     rcx, rdi; unsigned __int16 *
0x180040c83  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180040c88  mov     ebx, eax
0x180040c8a  test    eax, eax
0x180040c8c  jns     short loc_180040CB2
0x180040c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c95  lea     rax, WPP_GLOBAL_Control
0x180040c9c  cmp     rcx, rax
0x180040c9f  jz      loc_180040D27
0x180040ca5  test    byte ptr [rcx+1Ch], 2
0x180040ca9  jz      short loc_180040D27
0x180040cab  mov     edx, 0Eh
0x180040cb0  jmp     short loc_180040D14
0x180040cb2  mov     rax, [rsp+2D8h+var_288]
0x180040cb7  test    rax, rax
0x180040cba  jz      short loc_180040CCB
0x180040cbc  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180040cc2  lea     r8, aSS_1; "%s\\%s"
0x180040cc9  jnz     short loc_180040CD2
0x180040ccb  lea     r8, aSS_2; "%s%s"
0x180040cd2  lea     rax, aSystem32Config_0; "System32\\config\\SOFTWARE"
0x180040cd9  mov     r9, rdi
0x180040cdc  mov     edx, 12Eh; unsigned __int64
0x180040ce1  mov     qword ptr [rsp+2D8h+dwOptions], rax
0x180040ce6  lea     rcx, [rsp+2D8h+File]; unsigned __int16 *
0x180040ceb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040cf0  mov     ebx, eax
0x180040cf2  test    eax, eax
0x180040cf4  jns     short loc_180040D4A
0x180040cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180040cfd  lea     rax, WPP_GLOBAL_Control
0x180040d04  cmp     rcx, rax
0x180040d07  jz      short loc_180040D27
0x180040d09  test    byte ptr [rcx+1Ch], 2
0x180040d0d  jz      short loc_180040D27
0x180040d0f  mov     edx, 0Fh
0x180040d14  mov     rcx, [rcx+10h]
0x180040d18  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180040d1f  mov     r9d, ebx
0x180040d22  call    WPP_SF_d
0x180040d27  movzx   ebx, bx
0x180040d2a  test    ebx, ebx
0x180040d2c  jz      short loc_180040D4A
0x180040d2e  mov     r9d, ebx
0x180040d31  lea     rdx, aWinreloadsoftw_2; "winreLoadSoftwareHive: Failed to constr"...
0x180040d38  mov     r8, rdi
0x180040d3b  mov     ecx, 1
0x180040d40  call    UnattendLogW
0x180040d45  jmp     loc_180040E24
0x180040d4a  mov     rdi, 0FFFFFFFF80000002h
0x180040d51  lea     r8, [rsp+2D8h+File]; lpFile
0x180040d56  mov     rcx, rdi; hKey
0x180040d59  lea     rdx, aWinreSoftware; "$WINRE$SOFTWARE"
0x180040d60  call    cs:__imp_RegLoadKeyW
0x180040d66  mov     ebx, eax
0x180040d68  test    eax, eax
0x180040d6a  jz      short loc_180040D7D
0x180040d6c  mov     r9d, eax
0x180040d6f  lea     r8, [rsp+2D8h+File]
0x180040d74  lea     rdx, aWinreloadsoftw_1; "winreLoadSoftwareHive: Failed to load ["...
0x180040d7b  jmp     short loc_180040D3B
0x180040d7d  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x180040d86  lea     rdx, aWinreSoftware; "$WINRE$SOFTWARE"
0x180040d8d  mov     [rsp+2D8h+phkResult], rsi; phkResult
0x180040d92  xor     r9d, r9d; lpClass
0x180040d95  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040d9e  xor     r8d, r8d; Reserved
0x180040da1  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x180040da9  mov     rcx, rdi; hKey
0x180040dac  mov     [rsp+2D8h+dwOptions], 4; dwOptions
0x180040db4  call    cs:__imp_RegCreateKeyExW
0x180040dba  mov     ebx, eax
0x180040dbc  test    eax, eax
0x180040dbe  jz      short loc_180040E24
0x180040dc0  lea     rdx, aWinreloadsoftw; "winreLoadSoftwareHive: Failed to open m"...
0x180040dc7  jmp     short loc_180040E17
0x180040dc9  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x180040dd2  lea     rdx, aSoftware; "SOFTWARE"
0x180040dd9  mov     [rsp+2D8h+phkResult], rsi; phkResult
0x180040dde  xor     r9d, r9d; lpClass
0x180040de1  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040dea  xor     r8d, r8d; Reserved
0x180040ded  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x180040df5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040dfc  mov     [rsp+2D8h+dwOptions], 4; dwOptions
0x180040e04  call    cs:__imp_RegCreateKeyExW
0x180040e0a  mov     ebx, eax
0x180040e0c  test    eax, eax
0x180040e0e  jz      short loc_180040E24
0x180040e10  lea     rdx, aWinreloadsoftw_0; "winreLoadSoftwareHive: Failed to open S"...
0x180040e17  mov     r8d, eax
0x180040e1a  mov     ecx, 1
0x180040e1f  call    UnattendLogW
0x180040e24  mov     eax, ebx
0x180040e26  mov     rcx, [rsp+2D8h+var_18]
0x180040e2e  xor     rcx, rsp; StackCookie
0x180040e31  call    __security_check_cookie
0x180040e36  lea     r11, [rsp+2D8h+var_8]
0x180040e3e  mov     rbx, [r11+20h]
0x180040e42  mov     rsi, [r11+28h]
0x180040e46  mov     rsp, r11
0x180040e49  pop     rdi
0x180040e4a  retn
```
