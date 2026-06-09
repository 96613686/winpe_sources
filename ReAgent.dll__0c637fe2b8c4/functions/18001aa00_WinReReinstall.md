# WinReReinstall

- ea: `0x18001aa00`
- end: `0x18001ab1b`
- name: `WinReReinstall`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000ed74`
- `0x1800193e8`
- `0x18001aa00`
- `0x18001fd7c`
- `0x180023fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001aa86`
- `KERNEL32!GetLastError` at `0x18001aad2`
- `KERNEL32!GetLastError` at `0x18001aa86`
- `KERNEL32!GetLastError` at `0x18001aad2`

## string_xrefs

- `0x18001aa20`: `Enter WinReReinstall`
- `0x18001aa3c`: ` (WinRE) WinReReinstall() Invalid parameters`
- `0x18001aa8c`: ` (WinRE) WinReReinstall() failed to uninstall internal. Error: 0x%08x`
- `0x18001aad8`: ` (WinRE) WinReReinstallfailed to install on target OS. Error: 0x%08x`
- `0x18001aae1`: ` (WinRE) WinReReinstall() The system partition has enough free space`
- `0x18001aaf4`: `Exit WinReReinstall return value: %d`

## pseudocode

```c
__int64 __fastcall WinReReinstall(struct _GUID *a1)
{
  unsigned int v2; // edi
  DWORD LastError; // eax
  DWORD v4; // eax
  union _ULARGE_INTEGER v6; // [rsp+78h] [rbp+10h] BYREF

  v2 = 0;
  v6.QuadPart = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReReinstall");
  if ( !(unsigned int)winreIsWinPE() || a1 )
  {
    if ( (unsigned int)WinReIsInstalledOnSystemPartitionInternal(a1, &v6) )
    {
      if ( v6.QuadPart >= 0x3200000 )
      {
        UnattendLogW(0, L" (WinRE) WinReReinstall() The system partition has enough free space");
      }
      else
      {
        if ( !(unsigned int)winreUnInstallInternal(a1, 1, 1) )
        {
          LastError = GetLastError();
          UnattendLogW(1, L" (WinRE) WinReReinstall() failed to uninstall internal. Error: 0x%08x", LastError);
          goto LABEL_13;
        }
        if ( !(unsigned int)WinReInstallOnTargetOSInternal(0, 0, a1, 0, 0, 1, 0, 0, 0, 0, 0) )
        {
          v4 = GetLastError();
          UnattendLogW(1, L" (WinRE) WinReReinstallfailed to install on target OS. Error: 0x%08x", v4);
          goto LABEL_13;
        }
      }
    }
    v2 = 1;
    goto LABEL_13;
  }
  UnattendLogW(1, L" (WinRE) WinReReinstall() Invalid parameters");
LABEL_13:
  UnattendLogW(0, L"Exit WinReReinstall return value: %d", v2);
  UnattendFinalizeLog();
  return v2;
}

```

## disassembly

```asm
0x18001aa00  mov     [rsp+arg_0], rbx
0x18001aa05  mov     [rsp+arg_10], rsi
0x18001aa0a  push    rdi
0x18001aa0b  sub     rsp, 60h
0x18001aa0f  mov     rsi, rcx
0x18001aa12  xor     edi, edi
0x18001aa14  xor     ecx, ecx
0x18001aa16  mov     [rsp+68h+arg_8], rdi
0x18001aa1b  call    UnattendInitializeLogEx2
0x18001aa20  lea     rdx, aEnterWinrerein; "Enter WinReReinstall"
0x18001aa27  xor     ecx, ecx
0x18001aa29  call    UnattendLogW
0x18001aa2e  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18001aa33  test    eax, eax
0x18001aa35  jz      short loc_18001AA50
0x18001aa37  test    rsi, rsi
0x18001aa3a  jnz     short loc_18001AA50
0x18001aa3c  lea     rdx, aWinreWinrerein_2; " (WinRE) WinReReinstall() Invalid param"...
0x18001aa43  lea     ecx, [rdi+1]
0x18001aa46  call    UnattendLogW
0x18001aa4b  jmp     loc_18001AAF1
0x18001aa50  lea     rdx, [rsp+68h+arg_8]
0x18001aa55  mov     rcx, rsi
0x18001aa58  call    WinReIsInstalledOnSystemPartitionInternal
0x18001aa5d  mov     ebx, 1
0x18001aa62  test    eax, eax
0x18001aa64  jz      loc_18001AAEF
0x18001aa6a  cmp     [rsp+68h+arg_8], 3200000h
0x18001aa73  jnb     short loc_18001AAE1
0x18001aa75  mov     r8d, ebx; int
0x18001aa78  mov     edx, ebx; int
0x18001aa7a  mov     rcx, rsi; struct _GUID *
0x18001aa7d  call    ?winreUnInstallInternal@@YAKPEAU_GUID@@HH@Z; winreUnInstallInternal(_GUID *,int,int)
0x18001aa82  test    eax, eax
0x18001aa84  jnz     short loc_18001AA9F
0x18001aa86  call    cs:__imp_GetLastError
0x18001aa8c  lea     rdx, aWinreWinrerein; " (WinRE) WinReReinstall() failed to uni"...
0x18001aa93  mov     r8d, eax
0x18001aa96  mov     ecx, ebx
0x18001aa98  call    UnattendLogW
0x18001aa9d  jmp     short loc_18001AAF1
0x18001aa9f  mov     [rsp+68h+var_18], rdi
0x18001aaa4  xor     r9d, r9d
0x18001aaa7  mov     [rsp+68h+var_20], rdi
0x18001aaac  mov     r8, rsi
0x18001aaaf  mov     [rsp+68h+var_28], rdi
0x18001aab4  xor     edx, edx
0x18001aab6  mov     [rsp+68h+var_30], edi
0x18001aaba  xor     ecx, ecx
0x18001aabc  mov     [rsp+68h+var_38], edi
0x18001aac0  mov     [rsp+68h+var_40], ebx
0x18001aac4  mov     [rsp+68h+var_48], rdi
0x18001aac9  call    ?WinReInstallOnTargetOSInternal@@YAKHPEAHPEAU_GUID@@HPEBGHKW4_WINRE_PARTITION_LOCATION@@20PEAUPartitionNode@@@Z; WinReInstallOnTargetOSInternal(int,int *,_GUID *,int,ushort const *,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,int *,PartitionNode *)
0x18001aace  test    eax, eax
0x18001aad0  jnz     short loc_18001AAEF
0x18001aad2  call    cs:__imp_GetLastError
0x18001aad8  lea     rdx, aWinreWinrerein_0; " (WinRE) WinReReinstallfailed to instal"...
0x18001aadf  jmp     short loc_18001AA93
0x18001aae1  lea     rdx, aWinreWinrerein_1; " (WinRE) WinReReinstall() The system pa"...
0x18001aae8  xor     ecx, ecx
0x18001aaea  call    UnattendLogW
0x18001aaef  mov     edi, ebx
0x18001aaf1  mov     r8d, edi
0x18001aaf4  lea     rdx, aExitWinrereins; "Exit WinReReinstall return value: %d"
0x18001aafb  xor     ecx, ecx
0x18001aafd  call    UnattendLogW
0x18001ab02  call    UnattendFinalizeLog
0x18001ab07  lea     r11, [rsp+68h+var_8]
0x18001ab0c  mov     eax, edi
0x18001ab0e  mov     rbx, [r11+10h]
0x18001ab12  mov     rsi, [r11+20h]
0x18001ab16  mov     rsp, r11
0x18001ab19  pop     rdi
0x18001ab1a  retn
```
