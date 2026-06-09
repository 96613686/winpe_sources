# DMrcInit(void)

- ea: `0x180003fc0`
- end: `0x180004197`
- name: `?DMrcInit@@YAKXZ`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011540`
- `0x18001162c`

## callees

- `0x180003fc0`
- `0x180004320`
- `0x180004d08`
- `0x180004d70`
- `0x180004dec`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004008`
- `KERNEL32!EnterCriticalSection` at `0x180004008`
- `KERNEL32!LeaveCriticalSection` at `0x18000407e`
- `KERNEL32!LeaveCriticalSection` at `0x18000407e`
- `ADVAPI32!EventRegister` at `0x18000413d`
- `ADVAPI32!EventRegister` at `0x18000413d`
- `ADVAPI32!EventSetInformation` at `0x18000415c`
- `ADVAPI32!EventSetInformation` at `0x18000415c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000405f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000405f`

## pseudocode

```c
__int64 __fastcall DMrcInit(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r8
  struct _MRC_STRUCT **v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_START_INITIALIZE, a3, 1, &ProviderId);
  EnterCriticalSection(&g_Crit);
  if ( qword_18001EAA8 && qword_18001EAA8 != -1 )
  {
    v3 = 0;
    ++qword_18001EAA8;
    goto LABEL_9;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Device Metadata",
         0,
         0x20019u,
         &g_MrcSystemKey) )
  {
    v3 = 8;
LABEL_8:
    MrcExit();
    goto LABEL_9;
  }
  ProviderId = (GUID)*((_OWORD *)off_18001E2A8 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18001E2C8 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18001E2A0, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_18001E2A8, (unsigned __int16)*off_18001E2A8);
  v3 = DataInit(v6);
  if ( v3 )
    goto LABEL_8;
  dword_18001EAA0 |= 1u;
  if ( !g_pmrc )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  qword_18001EAA8 = 1;
LABEL_9:
  LeaveCriticalSection(&g_Crit);
  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_STOP_INITIALIZE, v4, 1, &ProviderId);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180003fc0  push    rbx
0x180003fc2  sub     rsp, 50h
0x180003fc6  mov     rax, cs:__security_cookie
0x180003fcd  xor     rax, rsp
0x180003fd0  mov     [rsp+58h+var_18], rax
0x180003fd5  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x180003fdc  jz      short loc_180004001
0x180003fde  lea     rax, [rsp+58h+ProviderId]
0x180003fe3  mov     r9d, 1
0x180003fe9  lea     rdx, DMRC_START_INITIALIZE
0x180003ff0  mov     [rsp+58h+phkResult], rax
0x180003ff5  lea     rcx, userpnp_Context
0x180003ffc  call    McGenEventWrite_EventWriteTransfer
0x180004001  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004008  call    cs:__imp_EnterCriticalSection
0x18000400e  mov     rax, cs:qword_18001EAA8
0x180004015  test    rax, rax
0x180004018  jz      short loc_18000403C
0x18000401a  mov     rax, cs:qword_18001EAA8
0x180004021  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004025  jnb     short loc_18000403C
0x180004027  mov     rax, cs:qword_18001EAA8
0x18000402e  xor     ebx, ebx
0x180004030  inc     rax
0x180004033  mov     cs:qword_18001EAA8, rax
0x18000403a  jmp     short loc_180004077
0x18000403c  lea     rax, ?g_MrcSystemKey@@3PEAUHKEY__@@EA; HKEY__ * g_MrcSystemKey
0x180004043  mov     r9d, 20019h; samDesired
0x180004049  xor     r8d, r8d; ulOptions
0x18000404c  mov     [rsp+58h+phkResult], rax; phkResult
0x180004051  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004058  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000405f  call    cs:__imp_RegOpenKeyExW
0x180004065  test    eax, eax
0x180004067  jz      loc_1800040F6
0x18000406d  mov     ebx, 8
0x180004072  call    _MrcExit
0x180004077  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000407e  call    cs:__imp_LeaveCriticalSection
0x180004084  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x18000408b  jz      short loc_1800040B0
0x18000408d  lea     rax, [rsp+58h+ProviderId]
0x180004092  mov     r9d, 1
0x180004098  lea     rdx, DMRC_STOP_INITIALIZE
0x18000409f  mov     [rsp+58h+phkResult], rax
0x1800040a4  lea     rcx, userpnp_Context
0x1800040ab  call    McGenEventWrite_EventWriteTransfer
0x1800040b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040b7  lea     rax, WPP_GLOBAL_Control
0x1800040be  cmp     rcx, rax
0x1800040c1  jz      short loc_1800040E1
0x1800040c3  test    byte ptr [rcx+1Ch], 8
0x1800040c7  jz      short loc_1800040E1
0x1800040c9  mov     rcx, [rcx+10h]
0x1800040cd  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x1800040d4  mov     edx, 0Ah
0x1800040d9  mov     r9d, ebx
0x1800040dc  call    WPP_SF_d
0x1800040e1  mov     eax, ebx
0x1800040e3  mov     rcx, [rsp+58h+var_18]
0x1800040e8  xor     rcx, rsp; StackCookie
0x1800040eb  call    __security_check_cookie
0x1800040f0  add     rsp, 50h
0x1800040f4  pop     rbx
0x1800040f5  retn
0x1800040f6  cmp     cs:RegHandle, 0
0x1800040fe  mov     rax, cs:off_18001E2A8
0x180004105  movups  xmm0, xmmword ptr [rax-10h]
0x180004109  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000410f  jz      short loc_180004118
0x180004111  mov     ecx, 5
0x180004116  int     29h; Win8: RtlFailFast(ecx)
0x180004118  xorps   xmm0, xmm0
0x18000411b  lea     r9, RegHandle; RegHandle
0x180004122  lea     r8, dword_18001E2A0; CallbackContext
0x180004129  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004130  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x180004135  movdqu  cs:xmmword_18001E2C8, xmm0
0x18000413d  call    cs:__imp_EventRegister
0x180004143  test    eax, eax
0x180004145  jnz     short loc_180004162
0x180004147  mov     r8, cs:off_18001E2A8
0x18000414e  lea     edx, [rax+2]
0x180004151  mov     rcx, cs:RegHandle
0x180004158  movzx   r9d, word ptr [r8]
0x18000415c  call    cs:__imp_EventSetInformation
0x180004162  call    ?DataInit@@YAKPEAPEAU_MRC_STRUCT@@@Z; DataInit(_MRC_STRUCT * *)
0x180004167  mov     ebx, eax
0x180004169  test    eax, eax
0x18000416b  jnz     loc_180004072
0x180004171  or      cs:dword_18001EAA0, 1
0x180004178  cmp     cs:?g_pmrc@@3PEAU_MRC_STRUCT@@EA, 0; _MRC_STRUCT * g_pmrc
0x180004180  jnz     short loc_180004187
0x180004182  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004187  mov     cs:qword_18001EAA8, 1
0x180004192  jmp     loc_180004077
```
