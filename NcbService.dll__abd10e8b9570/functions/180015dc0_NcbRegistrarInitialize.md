# NcbRegistrarInitialize

- ea: `0x180015dc0`
- end: `0x180015fa5`
- name: `NcbRegistrarInitialize`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800159b8`

## callees

- `0x18000a0a0`
- `0x180015dc0`
- `0x1800176cc`
- `0x18001be60`
- `0x18001c500`
- `0x18001d09c`
- `0x1800214b4`
- `0x18002293c`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180015f50`
- `ntdll!RtlDeleteHashTable` at `0x180015f50`
- `ntdll!RtlCreateHashTable` at `0x180015e46`
- `ntdll!RtlCreateHashTable` at `0x180015e46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015e2a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015e2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f5d`
- `WS2_32!__imp_closesocket` at `0x180015f31`
- `WS2_32!__imp_closesocket` at `0x180015f31`
- `WS2_32!__imp_WSACleanup` at `0x180015f37`
- `WS2_32!__imp_WSACleanup` at `0x180015f37`

## pseudocode

```c
__int64 __fastcall NcbRegistrarInitialize(__int64 *a1)
{
  __int64 v1; // rdx
  char v2; // di
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  v10 = 0;
  g_NcbRegistrarIsAoacSystem = NcbRegistrarIsSystemAoacCapable();
  InitializeCriticalSection(&g_ControlChannelTriggerContextTableLock);
  v10 = g_ControlChannelTriggerContextTable;
  v2 = RtlCreateHashTable(&v10, 0, 0);
  if ( v2 )
  {
    v7 = NcbRegistrarpOpenControlSocket();
    v3 = v7;
    if ( v7 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v5 = 82;
    }
    else
    {
      v7 = NcbPolicyInitialize(v8, v1);
      v3 = v7;
      if ( !v7 )
      {
        g_RegistrarCallbackTable = (__int64)g_NcbRegistrarCallbackTable;
        NcbRegistrarReadSlotTestOverride();
        goto LABEL_23;
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v5 = 83;
    }
    v6 = v7;
    goto LABEL_10;
  }
  v3 = 8;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 81;
    v6 = 8;
LABEL_10:
    WPP_SF_d(v4[2], v5, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v6);
LABEL_23:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(v4, v1, L"NcbReg: Registrar initialization ended with", v3);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    if ( g_NcbControlSocket != -1 )
    {
      closesocket(g_NcbControlSocket);
      WSACleanup();
      g_NcbControlSocket = -1;
    }
    if ( v2 )
      RtlDeleteHashTable(g_ControlChannelTriggerContextTable);
    DeleteCriticalSection(&g_ControlChannelTriggerContextTableLock);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 84, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180015dc0  mov     [rsp+arg_8], rbx
0x180015dc5  mov     [rsp+arg_10], rbp
0x180015dca  mov     [rsp+arg_0], rcx
0x180015dcf  push    rdi
0x180015dd0  push    r14
0x180015dd2  push    r15
0x180015dd4  sub     rsp, 20h
0x180015dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ddf  lea     rbp, WPP_GLOBAL_Control
0x180015de6  lea     r14, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180015ded  cmp     rcx, rbp
0x180015df0  jz      short loc_180015E0F
0x180015df2  test    byte ptr [rcx+1Ch], 1
0x180015df6  jz      short loc_180015E0F
0x180015df8  cmp     byte ptr [rcx+19h], 6
0x180015dfc  jb      short loc_180015E0F
0x180015dfe  mov     rcx, [rcx+10h]
0x180015e02  mov     edx, 50h ; 'P'
0x180015e07  mov     r8, r14
0x180015e0a  call    WPP_SF_
0x180015e0f  mov     [rsp+38h+arg_0], 0
0x180015e18  call    NcbRegistrarIsSystemAoacCapable
0x180015e1d  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x180015e24  mov     cs:g_NcbRegistrarIsAoacSystem, al
0x180015e2a  call    cs:__imp_InitializeCriticalSection
0x180015e30  lea     r15, g_ControlChannelTriggerContextTable
0x180015e37  xor     r8d, r8d
0x180015e3a  xor     edx, edx
0x180015e3c  mov     [rsp+38h+arg_0], r15
0x180015e41  lea     rcx, [rsp+38h+arg_0]
0x180015e46  call    cs:__imp_RtlCreateHashTable
0x180015e4c  mov     dil, al
0x180015e4f  test    al, al
0x180015e51  jnz     short loc_180015E90
0x180015e53  mov     ebx, 8
0x180015e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e5f  cmp     rcx, rbp
0x180015e62  jz      loc_180015F01
0x180015e68  test    byte ptr [rcx+1Ch], 1
0x180015e6c  jz      loc_180015F01
0x180015e72  cmp     byte ptr [rcx+19h], 2
0x180015e76  jb      loc_180015F01
0x180015e7c  lea     edx, [rbx+49h]
0x180015e7f  mov     r9d, ebx
0x180015e82  mov     rcx, [rcx+10h]
0x180015e86  mov     r8, r14
0x180015e89  call    WPP_SF_d
0x180015e8e  jmp     short loc_180015EFA
0x180015e90  call    NcbRegistrarpOpenControlSocket
0x180015e95  mov     ebx, eax
0x180015e97  test    eax, eax
0x180015e99  jz      short loc_180015EBD
0x180015e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ea2  cmp     rcx, rbp
0x180015ea5  jz      short loc_180015F01
0x180015ea7  test    byte ptr [rcx+1Ch], 1
0x180015eab  jz      short loc_180015F01
0x180015ead  cmp     byte ptr [rcx+19h], 2
0x180015eb1  jb      short loc_180015F01
0x180015eb3  mov     edx, 52h ; 'R'
0x180015eb8  mov     r9d, eax
0x180015ebb  jmp     short loc_180015E82
0x180015ebd  call    NcbPolicyInitialize
0x180015ec2  mov     ebx, eax
0x180015ec4  test    eax, eax
0x180015ec6  jz      short loc_180015EE7
0x180015ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ecf  cmp     rcx, rbp
0x180015ed2  jz      short loc_180015F01
0x180015ed4  test    byte ptr [rcx+1Ch], 1
0x180015ed8  jz      short loc_180015F01
0x180015eda  cmp     byte ptr [rcx+19h], 2
0x180015ede  jb      short loc_180015F01
0x180015ee0  mov     edx, 53h ; 'S'
0x180015ee5  jmp     short loc_180015EB8
0x180015ee7  lea     rax, g_NcbRegistrarCallbackTable
0x180015eee  mov     cs:g_RegistrarCallbackTable, rax
0x180015ef5  call    NcbRegistrarReadSlotTestOverride
0x180015efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f01  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015f08  jz      short loc_180015F20
0x180015f0a  mov     r9d, ebx
0x180015f0d  lea     r8, aNcbregRegistra; "NcbReg: Registrar initialization ended "...
0x180015f14  call    McTemplateU0zq_EventWriteTransfer
0x180015f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f20  test    ebx, ebx
0x180015f22  jz      short loc_180015F6A
0x180015f24  mov     rcx, cs:g_NcbControlSocket; s
0x180015f2b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015f2f  jz      short loc_180015F48
0x180015f31  call    cs:__imp_closesocket
0x180015f37  call    cs:__imp_WSACleanup
0x180015f3d  mov     cs:g_NcbControlSocket, 0FFFFFFFFFFFFFFFFh
0x180015f48  test    dil, dil
0x180015f4b  jz      short loc_180015F56
0x180015f4d  mov     rcx, r15
0x180015f50  call    cs:__imp_RtlDeleteHashTable
0x180015f56  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x180015f5d  call    cs:__imp_DeleteCriticalSection
0x180015f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f6a  cmp     rcx, rbp
0x180015f6d  jz      short loc_180015F8F
0x180015f6f  test    byte ptr [rcx+1Ch], 1
0x180015f73  jz      short loc_180015F8F
0x180015f75  cmp     byte ptr [rcx+19h], 6
0x180015f79  jb      short loc_180015F8F
0x180015f7b  mov     rcx, [rcx+10h]
0x180015f7f  mov     edx, 54h ; 'T'
0x180015f84  mov     r9d, ebx
0x180015f87  mov     r8, r14
0x180015f8a  call    WPP_SF_d
0x180015f8f  mov     rbp, [rsp+38h+arg_10]
0x180015f94  mov     eax, ebx
0x180015f96  mov     rbx, [rsp+38h+arg_8]
0x180015f9b  add     rsp, 20h
0x180015f9f  pop     r15
0x180015fa1  pop     r14
0x180015fa3  pop     rdi
0x180015fa4  retn
```
