# FveBackupMonitor::RegisterStartOfBackupMonitoring(_BACKUP_MONITOR_TYPE)

- ea: `0x180033a24`
- end: `0x180033b5d`
- name: `?RegisterStartOfBackupMonitoring@FveBackupMonitor@@SAJW4_BACKUP_MONITOR_TYPE@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003b560`

## callees

- `0x180009f60`
- `0x180033a24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033a7e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033b00`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033a7e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180033b00`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::RegisterStartOfBackupMonitoring(int a1)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 1;
  if ( a1 != 1 )
  {
    v2 = 0;
    if ( a1 != 3 )
      goto LABEL_10;
  }
  v3 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\BitLocker\\KeyBackupMonitor",
         L"IsKeyBackupMonitorStarted",
         4u,
         &Data,
         4u);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( !v2 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_929186be452536e5252128d48ffaedab_Traceguids, v2);
  if ( (v2 & 0x80000000) == 0 )
  {
LABEL_10:
    if ( (unsigned int)(a1 - 2) <= 1 )
    {
      v4 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\BitLocker\\KeyBackupMonitor",
             L"IsKeyBackupMonitorStartedLocal",
             4u,
             &Data,
             4u);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v2 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_929186be452536e5252128d48ffaedab_Traceguids, v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180033a24  mov     [rsp+arg_8], rbx
0x180033a29  mov     [rsp+arg_10], rdi
0x180033a2e  push    r14
0x180033a30  sub     rsp, 30h
0x180033a34  mov     [rsp+38h+Data], 1
0x180033a3c  mov     edi, ecx
0x180033a3e  lea     r14, WPP_GLOBAL_Control
0x180033a45  cmp     ecx, 1
0x180033a48  jz      short loc_180033A51
0x180033a4a  xor     ebx, ebx
0x180033a4c  cmp     ecx, 3
0x180033a4f  jnz     short loc_180033ACB
0x180033a51  lea     rax, [rsp+38h+Data]
0x180033a56  mov     [rsp+38h+cbData], 4; cbData
0x180033a5e  mov     r9d, 4; dwType
0x180033a64  mov     [rsp+38h+lpData], rax; lpData
0x180033a69  lea     r8, aIskeybackupmon; "IsKeyBackupMonitorStarted"
0x180033a70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033a77  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Bit"...
0x180033a7e  call    cs:__imp_RegSetKeyValueW
0x180033a85  nop     dword ptr [rax+rax+00h]
0x180033a8a  mov     ebx, eax
0x180033a8c  test    eax, eax
0x180033a8e  jle     short loc_180033A99
0x180033a90  movzx   ebx, ax
0x180033a93  or      ebx, 80070000h
0x180033a99  test    ebx, ebx
0x180033a9b  jz      short loc_180033ACB
0x180033a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033aa4  cmp     rcx, r14
0x180033aa7  jz      short loc_180033AC7
0x180033aa9  test    byte ptr [rcx+1Ch], 40h
0x180033aad  jz      short loc_180033AC7
0x180033aaf  mov     rcx, [rcx+10h]
0x180033ab3  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180033aba  mov     edx, 0Ah
0x180033abf  mov     r9d, ebx
0x180033ac2  call    WPP_SF_d
0x180033ac7  test    ebx, ebx
0x180033ac9  js      short loc_180033B49
0x180033acb  lea     eax, [rdi-2]
0x180033ace  cmp     eax, 1
0x180033ad1  ja      short loc_180033B49
0x180033ad3  lea     rax, [rsp+38h+Data]
0x180033ad8  mov     [rsp+38h+cbData], 4; cbData
0x180033ae0  mov     r9d, 4; dwType
0x180033ae6  mov     [rsp+38h+lpData], rax; lpData
0x180033aeb  lea     r8, aIskeybackupmon_0; "IsKeyBackupMonitorStartedLocal"
0x180033af2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033af9  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Bit"...
0x180033b00  call    cs:__imp_RegSetKeyValueW
0x180033b07  nop     dword ptr [rax+rax+00h]
0x180033b0c  mov     ebx, eax
0x180033b0e  test    eax, eax
0x180033b10  jle     short loc_180033B1B
0x180033b12  movzx   ebx, ax
0x180033b15  or      ebx, 80070000h
0x180033b1b  test    ebx, ebx
0x180033b1d  jz      short loc_180033B49
0x180033b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b26  cmp     rcx, r14
0x180033b29  jz      short loc_180033B49
0x180033b2b  test    byte ptr [rcx+1Ch], 40h
0x180033b2f  jz      short loc_180033B49
0x180033b31  mov     rcx, [rcx+10h]
0x180033b35  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180033b3c  mov     edx, 0Bh
0x180033b41  mov     r9d, ebx
0x180033b44  call    WPP_SF_d
0x180033b49  mov     rdi, [rsp+38h+arg_10]
0x180033b4e  mov     eax, ebx
0x180033b50  mov     rbx, [rsp+38h+arg_8]
0x180033b55  add     rsp, 30h
0x180033b59  pop     r14
0x180033b5b  retn
```
