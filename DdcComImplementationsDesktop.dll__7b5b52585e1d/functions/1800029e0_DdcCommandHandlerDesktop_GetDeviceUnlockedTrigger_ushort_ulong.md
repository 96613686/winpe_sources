# DdcCommandHandlerDesktop::GetDeviceUnlockedTrigger(ushort *,ulong *)

- ea: `0x1800029e0`
- end: `0x180002bc2`
- name: `?GetDeviceUnlockedTrigger@DdcCommandHandlerDesktop@@UEAAJPEAGPEAK@Z`
- size: `482`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktop *this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800016b0`
- `0x180002134`
- `0x1800026ac`
- `0x1800029e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002b63`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002b63`

## string_xrefs

- `0x180002ad9`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::GetDeviceUnlockedTrigger(
        DdcCommandHandlerDesktop *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  int v7; // ecx
  _OWORD v9[14]; // [rsp+30h] [rbp-D0h] BYREF

  v9[0] = *(_OWORD *)L"<SessionStateChangeTrigger><StateChange>SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[1] = *(_OWORD *)L"StateChangeTrigger><StateChange>SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[2] = *(_OWORD *)L"ngeTrigger><StateChange>SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[3] = *(_OWORD *)L"er><StateChange>SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[4] = *(_OWORD *)L"eChange>SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[5] = *(_OWORD *)L"SessionUnlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[6] = *(_OWORD *)L"nlock</StateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[7] = *(_OWORD *)L"tateChange></SessionStateChangeTrigger><LogonTrigger />";
  v9[8] = *(_OWORD *)L"ge></SessionStateChangeTrigger><LogonTrigger />";
  v9[9] = *(_OWORD *)L"sionStateChangeTrigger><LogonTrigger />";
  v9[10] = *(_OWORD *)L"eChangeTrigger><LogonTrigger />";
  v9[11] = *(_OWORD *)L"rigger><LogonTrigger />";
  v9[12] = *(_OWORD *)L"LogonTrigger />";
  v9[13] = *(_OWORD *)L"gger />";
  if ( a2 )
  {
    if ( a3 )
    {
      if ( *a3 >= 0x100 )
      {
        memset_0(a2, 0, *a3);
        if ( (unsigned int)_o_wcscpy_s(a2, *a3, v9) )
        {
          v5 = -2147467259;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v7,
              v6,
              -2147467259,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddc"
                            "commandhandlerdesktop.cpp",
              74,
              (__int64)"CBR(wcscpy_s(pwszTrigger, *pcchTrigger, c_pwszTrigger) == 0)");
        }
        else
        {
          v5 = 0;
          *a3 = 112;
        }
      }
      else
      {
        v5 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)this,
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddcco"
                          "mmandhandlerdesktop.cpp",
            70,
            (__int64)"CBR(*pcchTrigger >= 256)");
      }
    }
    else
    {
      v5 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)this,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomm"
                        "andhandlerdesktop.cpp",
          69,
          (__int64)"CPR(pcchTrigger)");
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        68,
        (__int64)"CPR(pwszTrigger)");
  }
  return v5;
}

```

## disassembly

```asm
0x1800029e0  mov     [rsp-8+arg_0], rbx
0x1800029e5  mov     [rsp-8+arg_18], rdi
0x1800029ea  push    rbp
0x1800029eb  lea     rbp, [rsp-20h]
0x1800029f0  sub     rsp, 120h
0x1800029f7  mov     rax, cs:__security_cookie
0x1800029fe  xor     rax, rsp
0x180002a01  mov     [rbp+20h+var_10], rax
0x180002a05  movaps  xmm0, xmmword ptr cs:aSessionstatech; "<SessionStateChangeTrigger><StateChange"...
0x180002a0c  mov     rdi, r8
0x180002a0f  movaps  xmm1, xmmword ptr cs:aSessionstatech+10h; "StateChangeTrigger><StateChange>Session"...
0x180002a16  mov     rbx, rdx
0x180002a19  movups  [rsp+120h+var_F0], xmm0
0x180002a1e  movaps  xmm0, xmmword ptr cs:aSessionstatech+20h; "ngeTrigger><StateChange>SessionUnlock</"...
0x180002a25  movups  [rsp+120h+var_E0], xmm1
0x180002a2a  movaps  xmm1, xmmword ptr cs:aSessionstatech+30h; "er><StateChange>SessionUnlock</StateCha"...
0x180002a31  movups  [rsp+120h+var_D0], xmm0
0x180002a36  movaps  xmm0, xmmword ptr cs:aSessionstatech+40h; "eChange>SessionUnlock</StateChange></Se"...
0x180002a3d  movups  [rsp+120h+var_C0], xmm1
0x180002a42  movaps  xmm1, xmmword ptr cs:aSessionstatech+50h; "SessionUnlock</StateChange></SessionSta"...
0x180002a49  movups  [rsp+120h+var_B0], xmm0
0x180002a4e  movaps  xmm0, xmmword ptr cs:aSessionstatech+60h; "nlock</StateChange></SessionStateChange"...
0x180002a55  movups  [rbp+20h+var_A0], xmm1
0x180002a59  movaps  xmm1, xmmword ptr cs:aSessionstatech+70h; "tateChange></SessionStateChangeTrigger>"...
0x180002a60  movups  [rbp+20h+var_90], xmm0
0x180002a64  movaps  xmm0, xmmword ptr cs:aSessionstatech+80h; "ge></SessionStateChangeTrigger><LogonTr"...
0x180002a6b  movups  [rbp+20h+var_80], xmm1
0x180002a6f  movaps  xmm1, xmmword ptr cs:aSessionstatech+90h; "sionStateChangeTrigger><LogonTrigger />"
0x180002a76  movups  [rbp+20h+var_70], xmm0
0x180002a7a  movaps  xmm0, xmmword ptr cs:aSessionstatech+0A0h; "eChangeTrigger><LogonTrigger />"
0x180002a81  movups  [rbp+20h+var_60], xmm1
0x180002a85  movaps  xmm1, xmmword ptr cs:aSessionstatech+0B0h; "rigger><LogonTrigger />"
0x180002a8c  movups  [rbp+20h+var_50], xmm0
0x180002a90  movaps  xmm0, xmmword ptr cs:aSessionstatech+0C0h; "LogonTrigger />"
0x180002a97  movups  [rbp+20h+var_40], xmm1
0x180002a9b  movaps  xmm1, xmmword ptr cs:aSessionstatech+0D0h; "gger />"
0x180002aa2  movups  [rbp+20h+var_30], xmm0
0x180002aa6  movups  [rbp+20h+var_20], xmm1
0x180002aaa  test    rdx, rdx
0x180002aad  jnz     short loc_180002AEA
0x180002aaf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002ab6  mov     r8d, 80070057h
0x180002abc  mov     ebx, r8d
0x180002abf  jz      loc_180002B9F
0x180002ac5  lea     rax, aCprPwsztrigger; "CPR(pwszTrigger)"
0x180002acc  mov     [rsp+120h+var_F8], rax
0x180002ad1  mov     [rsp+120h+var_100], 144h
0x180002ad9  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180002ae0  call    McTemplateU0dsqs_EventWriteTransfer
0x180002ae5  jmp     loc_180002B9F
0x180002aea  test    rdi, rdi
0x180002aed  jnz     short loc_180002B1B
0x180002aef  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002af6  mov     r8d, 80070057h
0x180002afc  mov     ebx, r8d
0x180002aff  jz      loc_180002B9F
0x180002b05  lea     rax, aCprPcchtrigger; "CPR(pcchTrigger)"
0x180002b0c  mov     [rsp+120h+var_F8], rax
0x180002b11  mov     [rsp+120h+var_100], 145h
0x180002b19  jmp     short loc_180002AD9
0x180002b1b  cmp     dword ptr [r8], 100h
0x180002b22  jnb     short loc_180002B4C
0x180002b24  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002b2b  mov     r8d, 80070057h
0x180002b31  mov     ebx, r8d
0x180002b34  jz      short loc_180002B9F
0x180002b36  lea     rax, aCbrPcchtrigger; "CBR(*pcchTrigger >= 256)"
0x180002b3d  mov     [rsp+120h+var_F8], rax
0x180002b42  mov     [rsp+120h+var_100], 146h
0x180002b4a  jmp     short loc_180002AD9
0x180002b4c  mov     r8d, [r8]; Size
0x180002b4f  xor     edx, edx; Val
0x180002b51  mov     rcx, rbx; void *
0x180002b54  call    memset_0
0x180002b59  mov     edx, [rdi]
0x180002b5b  lea     r8, [rsp+120h+var_F0]
0x180002b60  mov     rcx, rbx
0x180002b63  call    cs:__imp__o_wcscpy_s
0x180002b69  test    eax, eax
0x180002b6b  jz      short loc_180002B97
0x180002b6d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002b74  mov     ebx, 80004005h
0x180002b79  jz      short loc_180002B9F
0x180002b7b  lea     rax, aCbrWcscpySPwsz; "CBR(wcscpy_s(pwszTrigger, *pcchTrigger,"...
0x180002b82  mov     r8d, ebx
0x180002b85  mov     [rsp+120h+var_F8], rax
0x180002b8a  mov     [rsp+120h+var_100], 14Ah
0x180002b92  jmp     loc_180002AD9
0x180002b97  xor     ebx, ebx
0x180002b99  mov     dword ptr [rdi], 70h ; 'p'
0x180002b9f  mov     eax, ebx
0x180002ba1  mov     rcx, [rbp+20h+var_10]
0x180002ba5  xor     rcx, rsp; StackCookie
0x180002ba8  call    __security_check_cookie
0x180002bad  lea     r11, [rsp+120h+var_s0]
0x180002bb5  mov     rbx, [r11+10h]
0x180002bb9  mov     rdi, [r11+28h]
0x180002bbd  mov     rsp, r11
0x180002bc0  pop     rbp
0x180002bc1  retn
```
