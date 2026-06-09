# sub_18011CFFC

- ea: `0x18011cffc`
- end: `0x18011d54c`
- name: `sub_18011CFFC`
- size: `1360`
- prototype: `__int64 __usercall@<rax>(SC_HANDLE hSCManager@<rcx>, LPCWSTR lpServiceName@<rdx>, char)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, service_task`

## callers

- `0x18011c1fc`
- `0x18011cd14`

## callees

- `0x18001f1a4`
- `0x18003952c`
- `0x180059ef8`
- `0x18005a63c`
- `0x1800a2770`
- `0x1800e7fa4`
- `0x18011c000`
- `0x18011c0c8`
- `0x18011c998`
- `0x18011ca30`
- `0x18011cfc4`
- `0x18011cffc`
- `0x18011ea28`
- `0x180132494`
- `0x18015edd0`
- `0x1801b3cf0`
- `0x1801c5240`
- `0x1801c627e`
- `0x18020ae2c`
- `0x1802bd770`
- `0x1802bd9d4`
- `0x1802be5ec`
- `0x1802c01ec`
- `0x1802c0380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011d346`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011d487`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011d346`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18011d487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d0f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d38d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d0f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d38d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18011d0ad`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18011d0ad`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18011d2d4`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18011d42e`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18011d2d4`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18011d42e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18011d24f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18011d24f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18011d380`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18011d380`

## string_xrefs

- `0x18011d08f`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d110`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d12f`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d259`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d2b6`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d2e8`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d31e`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d359`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d3bc`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d413`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d44e`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d49a`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x18011d038`: `SLMTerminateSingleServiceActivity`

## pseudocode

```c
__int64 __fastcall sub_18011CFFC(SC_HANDLE hSCManager, LPCWSTR lpServiceName, __int64 a3, char a4, char a5)
{
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r8d
  SC_HANDLE v13; // rbx
  signed int LastError; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  char v17; // r15
  int v18; // eax
  DWORD v19; // eax
  void *v20; // rcx
  int v21; // eax
  DWORD v22; // eax
  int v24; // eax
  signed int v25; // eax
  __int64 v26; // rdx
  int v27; // ecx
  __int64 v28; // r9
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  SC_HANDLE hService; // [rsp+70h] [rbp-90h] BYREF
  SC_HANDLE v33; // [rsp+78h] [rbp-88h] BYREF
  SERVICE_NOTIFY_2W v34; // [rsp+80h] [rbp-80h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+D0h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v37[42]; // [rsp+140h] [rbp+40h] BYREF
  void *retaddr; // [rsp+2D8h] [rbp+1D8h]

  sub_18003952C(v37, "SLMTerminateSingleServiceActivity");
  v37[0] = off_1803F8C70;
  sub_18011C000(v37, a3, lpServiceName);
  hService = 0;
  v30 = 0;
  v31 = 0;
  v9 = sub_180059EF8(&v30, 0);
  if ( v9 < 0 )
    sub_180132494(
      retaddr,
      957,
      "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
      (unsigned int)v9);
  v33 = OpenServiceW(hSCManager, lpServiceName, 0xF01FFu);
  sub_18011CFC4(&hService, &v33);
  sub_1800A2770(&v33);
  if ( (_DWORD)v30 )
    sub_18005A63C(&v30);
  v13 = hService;
  if ( !hService )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    sub_18011EA28(retaddr, 968, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", v15);
    if ( (v15 & 0x80000000) != 0 )
      sub_18001F1A4(retaddr, 969, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", v15);
    if ( (byte_18056AF0B & 2) != 0 )
      sub_18011C998(&qword_180563000, &unk_180434AE0, v15, lpServiceName);
    sub_18011CA30(v15, v16, &unk_180434AE0, v15, lpServiceName);
    goto LABEL_55;
  }
  if ( a4 )
  {
    v17 = 1;
    if ( (byte_18056AF0B & 1) != 0 )
      sub_1802C0380(v11, (unsigned int)&unk_180456550, v12, (_DWORD)lpServiceName, a3, 1);
    sub_1802BD770(v11, v10, &unk_180456550);
LABEL_20:
    if ( !ChangeServiceConfigW(v13, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      sub_18020AE2C(retaddr, 991, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp");
    memset(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)SvchostPushServiceGlobals;
    v30 = 0;
    v31 = 0;
    v18 = sub_180059EF8(&v30, 0);
    if ( v18 < 0 )
      sub_180132494(
        retaddr,
        1001,
        "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
        (unsigned int)v18);
    v19 = NotifyServiceStatusChangeW(v13, 9u, &pNotifyBuffer);
    v20 = retaddr;
    if ( v19 )
      sub_1802C01EC(retaddr, 1002, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", v19);
    if ( (_DWORD)v30 )
      sub_18005A63C(&v30);
    v21 = sub_18011C0C8(v20);
    if ( v21 < 0 )
      sub_180132494(
        retaddr,
        1011,
        "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
        (unsigned int)v21);
    if ( WaitForSingleObjectEx(qword_18056B8E8, 0xEA60u, 1) == 258 )
      sub_18001F1A4(retaddr, 1014, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", 1053);
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v13, 1u, &ServiceStatus) )
    {
      v22 = GetLastError();
      if ( v22 - 1061 > 1 && (!a4 || v22 != 1052) )
        sub_18020AE2C(retaddr, 1027, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp");
    }
    memset(&v34, 0, sizeof(v34));
    v34.dwVersion = 2;
    v34.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)SvchostPushServiceGlobals;
    v30 = 0;
    v31 = 0;
    v24 = sub_180059EF8(&v30, 0);
    if ( v24 < 0 )
      sub_180132494(
        retaddr,
        1037,
        "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
        (unsigned int)v24);
    v25 = NotifyServiceStatusChangeW(v13, 1u, &v34);
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    if ( v25 < 0 )
      sub_180132494(
        retaddr,
        1038,
        "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
        (unsigned int)v25);
    if ( (_DWORD)v30 )
      sub_18005A63C(&v30);
    if ( WaitForSingleObjectEx(qword_18056B8E8, 0xEA60u, 1) == 258 )
      sub_18001F1A4(retaddr, 1042, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", 1053);
    if ( v34.ServiceStatus.dwCurrentState != 1 )
      sub_1801B3CF0(v13);
    if ( (byte_18056AF0B & 1) != 0 )
      sub_18015EDD0(v27, (unsigned int)&unk_1804571F0, 0, (_DWORD)lpServiceName, a3);
    sub_1800E7FA4(0, v26, &unk_1804571F0, 0, (_DWORD)lpServiceName, a3);
    LOBYTE(v28) = v17;
    sub_1802BE5EC(v37, a3, lpServiceName, v28);
    goto LABEL_55;
  }
  v17 = a5;
  if ( (byte_18056AF0B & 1) != 0 )
    sub_1802C0380(v11, (unsigned int)&unk_180455CA8, v12, (_DWORD)lpServiceName, a3, a5);
  sub_1802BD770(v11, v10, &unk_180455CA8);
  if ( a5 )
    goto LABEL_20;
LABEL_55:
  sub_1800A2770(&hService);
  return sub_1802BD9D4(v37);
}

```

## disassembly

```asm
0x18011cffc  mov     [rsp-8+arg_18], rbx
0x18011d001  push    rbp
0x18011d002  push    rsi
0x18011d003  push    rdi
0x18011d004  push    r12
0x18011d006  push    r13
0x18011d008  push    r14
0x18011d00a  push    r15
0x18011d00c  lea     rbp, [rsp-1A0h]
0x18011d014  sub     rsp, 2A0h
0x18011d01b  mov     rax, cs:__security_cookie
0x18011d022  xor     rax, rsp
0x18011d025  mov     [rbp+1D0h+var_40], rax
0x18011d02c  mov     r13b, r9b
0x18011d02f  mov     r14, r8
0x18011d032  mov     rsi, rdx
0x18011d035  mov     rbx, rcx
0x18011d038  lea     rdx, aSlmterminatesi; "SLMTerminateSingleServiceActivity"
0x18011d03f  lea     rcx, [rbp+1D0h+var_190]
0x18011d043  call    sub_18003952C
0x18011d048  lea     rax, off_1803F8C70
0x18011d04f  mov     [rbp+1D0h+var_190], rax
0x18011d053  mov     r8, rsi
0x18011d056  mov     rdx, r14
0x18011d059  lea     rcx, [rbp+1D0h+var_190]
0x18011d05d  call    sub_18011C000
0x18011d062  nop
0x18011d063  xor     r12d, r12d
0x18011d066  mov     [rsp+2D0h+hService], r12
0x18011d06b  mov     [rsp+2D0h+var_270], r12
0x18011d070  mov     [rsp+2D0h+var_268], r12
0x18011d075  xor     edx, edx
0x18011d077  lea     rcx, [rsp+2D0h+var_270]
0x18011d07c  call    sub_180059EF8
0x18011d081  mov     rcx, [rbp+1D8h]
0x18011d088  test    eax, eax
0x18011d08a  jns     short loc_18011D0A1
0x18011d08c  mov     r9d, eax
0x18011d08f  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d096  mov     edx, 3BDh
0x18011d09b  call    sub_180132494
0x18011d0a1  mov     r8d, 0F01FFh; dwDesiredAccess
0x18011d0a7  mov     rdx, rsi; lpServiceName
0x18011d0aa  mov     rcx, rbx; hSCManager
0x18011d0ad  call    cs:OpenServiceW
0x18011d0b3  mov     [rsp+2D0h+var_258], rax
0x18011d0b8  lea     rdx, [rsp+2D0h+var_258]
0x18011d0bd  lea     rcx, [rsp+2D0h+hService]
0x18011d0c2  call    sub_18011CFC4
0x18011d0c7  lea     rcx, [rsp+2D0h+var_258]
0x18011d0cc  call    sub_1800A2770
0x18011d0d1  nop
0x18011d0d2  cmp     dword ptr [rsp+2D0h+var_270], r12d
0x18011d0d7  jz      short loc_18011D0E3
0x18011d0d9  lea     rcx, [rsp+2D0h+var_270]
0x18011d0de  call    sub_18005A63C
0x18011d0e3  mov     rbx, [rsp+2D0h+hService]
0x18011d0e8  test    rbx, rbx
0x18011d0eb  jnz     loc_18011D17D
0x18011d0f1  call    cs:GetLastError
0x18011d0f7  mov     ebx, eax
0x18011d0f9  test    eax, eax
0x18011d0fb  jle     short loc_18011D106
0x18011d0fd  movzx   ebx, ax
0x18011d100  or      ebx, 80070000h
0x18011d106  mov     rcx, [rbp+1D8h]
0x18011d10d  mov     r9d, ebx
0x18011d110  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d117  mov     edx, 3C8h
0x18011d11c  call    sub_18011EA28
0x18011d121  mov     rcx, [rbp+1D8h]
0x18011d128  test    ebx, ebx
0x18011d12a  jns     short loc_18011D140
0x18011d12c  mov     r9d, ebx
0x18011d12f  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d136  mov     edx, 3C9h
0x18011d13b  call    sub_18001F1A4
0x18011d140  test    cs:byte_18056AF0B, 2
0x18011d147  jz      short loc_18011D162
0x18011d149  mov     r9, rsi
0x18011d14c  mov     r8d, ebx
0x18011d14f  lea     rdx, unk_180434AE0
0x18011d156  lea     rcx, qword_180563000
0x18011d15d  call    sub_18011C998
0x18011d162  mov     [rsp+2D0h+lpBinaryPathName], rsi
0x18011d167  mov     r9d, ebx
0x18011d16a  lea     r8, unk_180434AE0
0x18011d171  mov     ecx, ebx
0x18011d173  call    sub_18011CA30
0x18011d178  jmp     loc_18011D50E
0x18011d17d  mov     edi, 1
0x18011d182  test    r13b, r13b
0x18011d185  jz      short loc_18011D1C8
0x18011d187  mov     r15b, dil
0x18011d18a  test    cs:byte_18056AF0B, dil
0x18011d191  jz      short loc_18011D1AB
0x18011d193  mov     dword ptr [rsp+2D0h+lpLoadOrderGroup], edi
0x18011d197  mov     [rsp+2D0h+lpBinaryPathName], r14
0x18011d19c  mov     r9, rsi
0x18011d19f  lea     rdx, unk_180456550
0x18011d1a6  call    sub_1802C0380
0x18011d1ab  mov     byte ptr [rsp+2D0h+lpdwTagId], dil
0x18011d1b0  mov     [rsp+2D0h+lpLoadOrderGroup], r14
0x18011d1b5  mov     [rsp+2D0h+lpBinaryPathName], rsi
0x18011d1ba  lea     r8, unk_180456550
0x18011d1c1  call    sub_1802BD770
0x18011d1c6  jmp     short loc_18011D216
0x18011d1c8  movzx   r15d, [rbp+1D0h+arg_20]
0x18011d1d0  test    cs:byte_18056AF0B, dil
0x18011d1d7  jz      short loc_18011D1F2
0x18011d1d9  mov     dword ptr [rsp+2D0h+lpLoadOrderGroup], r15d
0x18011d1de  mov     [rsp+2D0h+lpBinaryPathName], r14
0x18011d1e3  mov     r9, rsi
0x18011d1e6  lea     rdx, unk_180455CA8
0x18011d1ed  call    sub_1802C0380
0x18011d1f2  mov     byte ptr [rsp+2D0h+lpdwTagId], r15b
0x18011d1f7  mov     [rsp+2D0h+lpLoadOrderGroup], r14
0x18011d1fc  mov     [rsp+2D0h+lpBinaryPathName], rsi
0x18011d201  lea     r8, unk_180455CA8
0x18011d208  call    sub_1802BD770
0x18011d20d  test    r15b, r15b
0x18011d210  jz      loc_18011D50E
0x18011d216  mov     r12, [rbp+1D8h]
0x18011d21d  xor     eax, eax
0x18011d21f  mov     [rsp+2D0h+lpDisplayName], rax; lpDisplayName
0x18011d224  mov     [rsp+2D0h+lpPassword], rax; lpPassword
0x18011d229  mov     [rsp+2D0h+lpServiceStartName], rax; lpServiceStartName
0x18011d22e  mov     [rsp+2D0h+lpDependencies], rax; lpDependencies
0x18011d233  mov     [rsp+2D0h+lpdwTagId], rax; lpdwTagId
0x18011d238  mov     [rsp+2D0h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x18011d23d  mov     [rsp+2D0h+lpBinaryPathName], rax; lpBinaryPathName
0x18011d242  or      edx, 0FFFFFFFFh; dwServiceType
0x18011d245  mov     r9d, edx; dwErrorControl
0x18011d248  lea     r8d, [rax+4]; dwStartType
0x18011d24c  mov     rcx, rbx; hService
0x18011d24f  call    cs:ChangeServiceConfigW
0x18011d255  test    eax, eax
0x18011d257  jnz     short loc_18011D26E
0x18011d259  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d260  mov     edx, 3DFh
0x18011d265  mov     rcx, r12
0x18011d268  call    sub_18020AE2C
0x18011d26e  xor     edx, edx; Val
0x18011d270  lea     r8d, [rdx+50h]; Size
0x18011d274  lea     rcx, [rbp+1D0h+pNotifyBuffer]; void *
0x18011d278  call    memset
0x18011d27d  mov     [rbp+1D0h+pNotifyBuffer.dwVersion], 2
0x18011d284  lea     rax, SvchostPushServiceGlobals
0x18011d28b  mov     [rbp+1D0h+pNotifyBuffer.pfnNotifyCallback], rax
0x18011d28f  xor     r12d, r12d
0x18011d292  mov     [rsp+2D0h+var_270], r12
0x18011d297  mov     [rsp+2D0h+var_268], r12
0x18011d29c  xor     edx, edx
0x18011d29e  lea     rcx, [rsp+2D0h+var_270]
0x18011d2a3  call    sub_180059EF8
0x18011d2a8  mov     rcx, [rbp+1D8h]
0x18011d2af  test    eax, eax
0x18011d2b1  jns     short loc_18011D2C8
0x18011d2b3  mov     r9d, eax
0x18011d2b6  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d2bd  mov     edx, 3E9h
0x18011d2c2  call    sub_180132494
0x18011d2c8  lea     r8, [rbp+1D0h+pNotifyBuffer]; pNotifyBuffer
0x18011d2cc  mov     edx, 9; dwNotifyMask
0x18011d2d1  mov     rcx, rbx; hService
0x18011d2d4  call    cs:NotifyServiceStatusChangeW
0x18011d2da  mov     rcx, [rbp+1D8h]
0x18011d2e1  test    eax, eax
0x18011d2e3  jz      short loc_18011D2FA
0x18011d2e5  mov     r9d, eax
0x18011d2e8  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d2ef  mov     edx, 3EAh
0x18011d2f4  call    sub_1802C01EC
0x18011d2fa  cmp     dword ptr [rsp+2D0h+var_270], r12d
0x18011d2ff  jz      short loc_18011D30B
0x18011d301  lea     rcx, [rsp+2D0h+var_270]
0x18011d306  call    sub_18005A63C
0x18011d30b  call    sub_18011C0C8
0x18011d310  mov     rcx, [rbp+1D8h]
0x18011d317  test    eax, eax
0x18011d319  jns     short loc_18011D330
0x18011d31b  mov     r9d, eax
0x18011d31e  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d325  mov     edx, 3F3h
0x18011d32a  call    sub_180132494
0x18011d330  mov     r12, [rbp+1D8h]
0x18011d337  mov     r8d, edi; bAlertable
0x18011d33a  mov     edx, 0EA60h; dwMilliseconds
0x18011d33f  mov     rcx, cs:qword_18056B8E8; hHandle
0x18011d346  call    cs:WaitForSingleObjectEx
0x18011d34c  cmp     eax, 102h
0x18011d351  jnz     short loc_18011D36C
0x18011d353  mov     r9d, 41Dh
0x18011d359  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d360  lea     edx, [r9-27h]
0x18011d364  mov     rcx, r12
0x18011d367  call    sub_18001F1A4
0x18011d36c  xorps   xmm0, xmm0
0x18011d36f  movups  xmmword ptr [rbp+1D0h+ServiceStatus.dwServiceType], xmm0
0x18011d373  movups  xmmword ptr [rbp+1D0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18011d377  lea     r8, [rbp+1D0h+ServiceStatus]; lpServiceStatus
0x18011d37b  mov     edx, edi; dwControl
0x18011d37d  mov     rcx, rbx; hService
0x18011d380  call    cs:ControlService
0x18011d386  xor     r12d, r12d
0x18011d389  test    eax, eax
0x18011d38b  jnz     short loc_18011D3CE
0x18011d38d  call    cs:GetLastError
0x18011d393  lea     ecx, [rax-425h]
0x18011d399  cmp     ecx, edi
0x18011d39b  jbe     short loc_18011D3AE
0x18011d39d  test    r13b, r13b
0x18011d3a0  jz      short loc_18011D3A9
0x18011d3a2  cmp     eax, 41Ch
0x18011d3a7  jz      short loc_18011D3AE
0x18011d3a9  mov     al, dil
0x18011d3ac  jmp     short loc_18011D3B1
0x18011d3ae  mov     al, r12b
0x18011d3b1  mov     rcx, [rbp+1D8h]
0x18011d3b8  test    al, al
0x18011d3ba  jz      short loc_18011D3CE
0x18011d3bc  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d3c3  mov     edx, 403h
0x18011d3c8  call    sub_18020AE2C
0x18011d3ce  xor     edx, edx; Val
0x18011d3d0  lea     r8d, [rdx+50h]; Size
0x18011d3d4  lea     rcx, [rbp+1D0h+var_250]; void *
0x18011d3d8  call    memset
0x18011d3dd  mov     [rbp+1D0h+var_250.dwVersion], 2
0x18011d3e4  lea     rax, SvchostPushServiceGlobals
0x18011d3eb  mov     [rbp+1D0h+var_250.pfnNotifyCallback], rax
0x18011d3ef  mov     [rsp+2D0h+var_270], r12
0x18011d3f4  mov     [rsp+2D0h+var_268], r12
0x18011d3f9  xor     edx, edx
0x18011d3fb  lea     rcx, [rsp+2D0h+var_270]
0x18011d400  call    sub_180059EF8
0x18011d405  mov     rcx, [rbp+1D8h]
0x18011d40c  test    eax, eax
0x18011d40e  jns     short loc_18011D425
0x18011d410  mov     r9d, eax
0x18011d413  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d41a  mov     edx, 40Dh
0x18011d41f  call    sub_180132494
0x18011d425  lea     r8, [rbp+1D0h+var_250]; pNotifyBuffer
0x18011d429  mov     edx, edi; dwNotifyMask
0x18011d42b  mov     rcx, rbx; hService
0x18011d42e  call    cs:NotifyServiceStatusChangeW
0x18011d434  test    eax, eax
0x18011d436  jle     short loc_18011D440
0x18011d438  movzx   eax, ax
0x18011d43b  or      eax, 80070000h
0x18011d440  mov     rcx, [rbp+1D8h]
0x18011d447  test    eax, eax
0x18011d449  jns     short loc_18011D460
0x18011d44b  mov     r9d, eax
0x18011d44e  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d455  mov     edx, 40Eh
0x18011d45a  call    sub_180132494
0x18011d460  cmp     dword ptr [rsp+2D0h+var_270], r12d
0x18011d465  jz      short loc_18011D471
0x18011d467  lea     rcx, [rsp+2D0h+var_270]
0x18011d46c  call    sub_18005A63C
0x18011d471  mov     r12, [rbp+1D8h]
0x18011d478  mov     r8d, edi; bAlertable
0x18011d47b  mov     edx, 0EA60h; dwMilliseconds
0x18011d480  mov     rcx, cs:qword_18056B8E8; hHandle
0x18011d487  call    cs:WaitForSingleObjectEx
0x18011d48d  cmp     eax, 102h
0x18011d492  jnz     short loc_18011D4AD
0x18011d494  mov     r9d, 41Dh
0x18011d49a  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x18011d4a1  lea     edx, [r9-0Bh]
0x18011d4a5  mov     rcx, r12
0x18011d4a8  call    sub_18001F1A4
0x18011d4ad  cmp     [rbp+1D0h+var_250.ServiceStatus.dwCurrentState], edi
0x18011d4b0  jz      short loc_18011D4C0
0x18011d4b2  mov     r8, r14
0x18011d4b5  mov     rdx, rsi
0x18011d4b8  mov     rcx, rbx; hService
0x18011d4bb  call    sub_1801B3CF0
0x18011d4c0  test    cs:byte_18056AF0B, dil
0x18011d4c7  jz      short loc_18011D4E0
0x18011d4c9  mov     [rsp+2D0h+lpBinaryPathName], r14
0x18011d4ce  mov     r9, rsi
0x18011d4d1  xor     r8d, r8d
0x18011d4d4  lea     rdx, unk_1804571F0
0x18011d4db  call    sub_18015EDD0
0x18011d4e0  mov     [rsp+2D0h+lpLoadOrderGroup], r14
0x18011d4e5  mov     [rsp+2D0h+lpBinaryPathName], rsi
0x18011d4ea  xor     r9d, r9d
0x18011d4ed  lea     r8, unk_1804571F0
0x18011d4f4  xor     ecx, ecx
0x18011d4f6  call    sub_1800E7FA4
0x18011d4fb  mov     r9b, r15b
0x18011d4fe  mov     r8, rsi
0x18011d501  mov     rdx, r14
0x18011d504  lea     rcx, [rbp+1D0h+var_190]
0x18011d508  call    sub_1802BE5EC
0x18011d50d  nop
0x18011d50e  lea     rcx, [rsp+2D0h+hService]
  ... truncated ...
```
