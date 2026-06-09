# CWcnConnectionEngine::WaitForPbc(void)

- ea: `0x180078b20`
- end: `0x180078e88`
- name: `?WaitForPbc@CWcnConnectionEngine@@AEAAJXZ`
- size: `872`
- prototype: `__int64 __fastcall(CWcnConnectionEngine *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x18001d3a4`
- `0x18001d4d4`
- `0x180076f84`
- `0x180076fe0`
- `0x180077cc8`
- `0x180078970`
- `0x180078b20`
- `0x1800792c0`
- `0x180088304`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180078e30`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180078e30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180078d7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180078d7a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180078b92`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180078b92`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180078e26`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180078e26`
- `wlanapi!WlanInternalScan` at `0x180078cd1`
- `wlanapi!WlanInternalScan` at `0x180078cd1`
- `wlanapi!WlanRegisterNotification` at `0x180078c17`
- `wlanapi!WlanRegisterNotification` at `0x180078c17`
- `wlanapi!WlanScan` at `0x180078c99`
- `wlanapi!WlanScan` at `0x180078c99`

## pseudocode

```c
__int64 __fastcall CWcnConnectionEngine::WaitForPbc(CWcnConnectionEngine *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // ebx
  PVOID *v7; // r10
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // r14d
  signed int v11; // eax
  unsigned int v12; // ecx
  _QWORD *v13; // r8
  __int64 v14; // rdx
  int State; // eax
  int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // r10
  DWORD pdwNegotiatedVersion; // [rsp+68h] [rbp+10h] BYREF
  void *phClientHandle; // [rsp+70h] [rbp+18h] BYREF

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 35, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, Indent);
  }
  v4 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    else
      v5 = v4;
    v6 = v5 | 0x80000000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v8 = 36;
LABEL_11:
    WPP_SF_Dd(v7[2], v8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, (unsigned int)v4, v6);
LABEL_55:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  v4 = WlanRegisterNotification(phClientHandle, 8u, 0, CWcnConnectionEngine::WlanNotificationCallbackThunk, this, 0, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v9 = (unsigned __int16)v4 | 0x80070000;
    else
      v9 = v4;
    v6 = v9 | 0x80000000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v8 = 37;
    goto LABEL_11;
  }
  v10 = 0;
  (***((void (__fastcall ****)(_QWORD, __int64))this + 20))(*((_QWORD *)this + 20), 2);
  while ( 1 )
  {
    if ( (++v10 & 3) != 0 )
    {
      v11 = WlanScan(phClientHandle, (const GUID *)((char *)this + 44), (const PDOT11_SSID)((char *)this + 60), 0, 0);
      if ( v11 )
      {
        v12 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v14 = 38;
LABEL_35:
          WPP_SF__guid_Dd(v13[2], v14, v13, (char *)this + 44, v11, v12 | 0x80000000);
        }
      }
    }
    else
    {
      v11 = WlanInternalScan((char *)this + 44, 0);
      if ( v11 )
      {
        v12 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v14 = 39;
          goto LABEL_35;
        }
      }
    }
    State = CWcnConnectionEngine::WaitForNextState(this, 0x7530u);
    v6 = State;
    if ( State != -2147023436 && State < 0 )
      goto LABEL_55;
    v16 = CWcnConnectionEngine::CheckForNetworksWithPbc(this, phClientHandle, 0);
    v6 = v16;
    if ( v16 < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 40;
        goto LABEL_54;
      }
      goto LABEL_56;
    }
    if ( !v16 )
      goto LABEL_47;
    v16 = CWcnConnectionEngine::CheckForNetworksWithPbc(this, phClientHandle, 1);
    v6 = v16;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
LABEL_47:
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const unsigned __int16 *))(**((_QWORD **)this + 14) + 24LL))(
              *((_QWORD *)this + 14),
              0,
              0,
              &qword_180098990);
      v6 = v16;
      if ( v16 >= 0 )
        goto LABEL_55;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 42;
        goto LABEL_54;
      }
      goto LABEL_56;
    }
    if ( !WaitForSingleObject(*((HANDLE *)this + 3), 0x1F4u) )
    {
      v6 = -2147023673;
      goto LABEL_55;
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 41;
LABEL_54:
    WPP_SF_d(v7[2], v17, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, (unsigned int)v16);
    goto LABEL_55;
  }
LABEL_56:
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    ResetEvent(*((HANDLE *)this + 4));
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (v6 < 0 || *((_BYTE *)v7 + 25) >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 43, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v18, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180078b20  mov     rax, rsp
0x180078b23  mov     [rax+8], rbx
0x180078b27  mov     [rax+20h], rsi
0x180078b2b  push    r13
0x180078b2d  push    r14
0x180078b2f  push    r15
0x180078b31  sub     rsp, 40h
0x180078b35  mov     rsi, rcx
0x180078b38  mov     qword ptr [rax+18h], 0
0x180078b40  mov     dword ptr [rax+10h], 0
0x180078b47  mov     r10, cs:WPP_GLOBAL_Control
0x180078b4e  lea     r13, WPP_GLOBAL_Control
0x180078b55  cmp     r10, r13
0x180078b58  jz      short loc_180078B83
0x180078b5a  cmp     byte ptr [r10+19h], 6
0x180078b5f  jb      short loc_180078B83
0x180078b61  mov     ecx, 1; int
0x180078b66  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078b6b  mov     rcx, [r10+10h]
0x180078b6f  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180078b76  mov     edx, 23h ; '#'
0x180078b7b  mov     r9, rax
0x180078b7e  call    WPP_SF_s
0x180078b83  xor     edx, edx; pReserved
0x180078b85  lea     r9, [rsp+58h+phClientHandle]; phClientHandle
0x180078b8a  lea     r8, [rsp+58h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180078b8f  lea     ecx, [rdx+2]; dwClientVersion
0x180078b92  call    cs:__imp_WlanOpenHandle
0x180078b98  test    eax, eax
0x180078b9a  jz      short loc_180078BED
0x180078b9c  jg      short loc_180078BA2
0x180078b9e  mov     ebx, eax
0x180078ba0  jmp     short loc_180078BAB
0x180078ba2  movzx   ebx, ax
0x180078ba5  or      ebx, 80070000h
0x180078bab  or      ebx, 80000000h
0x180078bb1  mov     r10, cs:WPP_GLOBAL_Control
0x180078bb8  cmp     r10, r13
0x180078bbb  jz      loc_180078E1A
0x180078bc1  cmp     byte ptr [r10+19h], 2
0x180078bc6  jb      loc_180078E1A
0x180078bcc  mov     edx, 24h ; '$'
0x180078bd1  mov     rcx, [r10+10h]
0x180078bd5  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180078bdc  mov     r9d, eax
0x180078bdf  mov     dword ptr [rsp+58h+pCallbackContext], ebx
0x180078be3  call    WPP_SF_Dd
0x180078be8  jmp     loc_180078E13
0x180078bed  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x180078bf2  lea     r9, ?WlanNotificationCallbackThunk@CWcnConnectionEngine@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x180078bf9  xor     r8d, r8d; bIgnoreDuplicate
0x180078bfc  mov     [rsp+58h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x180078c05  mov     [rsp+58h+pReserved], 0; pReserved
0x180078c0e  mov     [rsp+58h+pCallbackContext], rsi; pCallbackContext
0x180078c13  lea     edx, [r8+8]; dwNotifSource
0x180078c17  call    cs:__imp_WlanRegisterNotification
0x180078c1d  test    eax, eax
0x180078c1f  jz      short loc_180078C5B
0x180078c21  jg      short loc_180078C27
0x180078c23  mov     ebx, eax
0x180078c25  jmp     short loc_180078C30
0x180078c27  movzx   ebx, ax
0x180078c2a  or      ebx, 80070000h
0x180078c30  or      ebx, 80000000h
0x180078c36  mov     r10, cs:WPP_GLOBAL_Control
0x180078c3d  cmp     r10, r13
0x180078c40  jz      loc_180078E1A
0x180078c46  cmp     byte ptr [r10+19h], 2
0x180078c4b  jb      loc_180078E1A
0x180078c51  mov     edx, 25h ; '%'
0x180078c56  jmp     loc_180078BD1
0x180078c5b  mov     rcx, [rsi+0A0h]
0x180078c62  xor     r14d, r14d
0x180078c65  mov     rax, [rcx]
0x180078c68  lea     edx, [r14+2]
0x180078c6c  mov     rax, [rax]
0x180078c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c74  lea     r15, [rsi+2Ch]
0x180078c78  inc     r14d
0x180078c7b  test    r14b, 3
0x180078c7f  jz      short loc_180078CCC
0x180078c81  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x180078c86  lea     r8, [rsi+3Ch]; pDot11Ssid
0x180078c8a  xor     r9d, r9d; pIeData
0x180078c8d  mov     [rsp+58h+pCallbackContext], 0; pReserved
0x180078c96  mov     rdx, r15; pInterfaceGuid
0x180078c99  call    cs:__imp_WlanScan
0x180078c9f  test    eax, eax
0x180078ca1  jz      short loc_180078D1C
0x180078ca3  jg      short loc_180078CA9
0x180078ca5  mov     ecx, eax
0x180078ca7  jmp     short loc_180078CB2
0x180078ca9  movzx   ecx, ax
0x180078cac  or      ecx, 80070000h
0x180078cb2  mov     r8, cs:WPP_GLOBAL_Control
0x180078cb9  cmp     r8, r13
0x180078cbc  jz      short loc_180078D1C
0x180078cbe  cmp     byte ptr [r8+19h], 3
0x180078cc3  jb      short loc_180078D1C
0x180078cc5  mov     edx, 26h ; '&'
0x180078cca  jmp     short loc_180078D02
0x180078ccc  xor     edx, edx
0x180078cce  mov     rcx, r15
0x180078cd1  call    cs:__imp_WlanInternalScan
0x180078cd7  test    eax, eax
0x180078cd9  jz      short loc_180078D1C
0x180078cdb  jg      short loc_180078CE1
0x180078cdd  mov     ecx, eax
0x180078cdf  jmp     short loc_180078CEA
0x180078ce1  movzx   ecx, ax
0x180078ce4  or      ecx, 80070000h
0x180078cea  mov     r8, cs:WPP_GLOBAL_Control
0x180078cf1  cmp     r8, r13
0x180078cf4  jz      short loc_180078D1C
0x180078cf6  cmp     byte ptr [r8+19h], 3
0x180078cfb  jb      short loc_180078D1C
0x180078cfd  mov     edx, 27h ; '''
0x180078d02  or      ecx, 80000000h
0x180078d08  mov     r9, r15
0x180078d0b  mov     dword ptr [rsp+58h+pReserved], ecx
0x180078d0f  mov     rcx, [r8+10h]
0x180078d13  mov     dword ptr [rsp+58h+pCallbackContext], eax
0x180078d17  call    WPP_SF__guid_Dd
0x180078d1c  mov     edx, 7530h; unsigned int
0x180078d21  mov     rcx, rsi; this
0x180078d24  call    ?WaitForNextState@CWcnConnectionEngine@@AEAAJK@Z; CWcnConnectionEngine::WaitForNextState(ulong)
0x180078d29  mov     ebx, eax
0x180078d2b  cmp     eax, 800705B4h
0x180078d30  jz      short loc_180078D3A
0x180078d32  test    eax, eax
0x180078d34  js      loc_180078E13
0x180078d3a  mov     rdx, [rsp+58h+phClientHandle]; void *
0x180078d3f  xor     r8d, r8d; int
0x180078d42  mov     rcx, rsi; this
0x180078d45  call    ?CheckForNetworksWithPbc@CWcnConnectionEngine@@AEAAJPEAXH@Z; CWcnConnectionEngine::CheckForNetworksWithPbc(void *,int)
0x180078d4a  mov     ebx, eax
0x180078d4c  test    eax, eax
0x180078d4e  js      loc_180078DE8
0x180078d54  jz      short loc_180078DAC
0x180078d56  mov     rdx, [rsp+58h+phClientHandle]; void *
0x180078d5b  mov     r8d, 1; int
0x180078d61  mov     rcx, rsi; this
0x180078d64  call    ?CheckForNetworksWithPbc@CWcnConnectionEngine@@AEAAJPEAXH@Z; CWcnConnectionEngine::CheckForNetworksWithPbc(void *,int)
0x180078d69  mov     ebx, eax
0x180078d6b  test    eax, eax
0x180078d6d  js      short loc_180078D92
0x180078d6f  jz      short loc_180078DAC
0x180078d71  mov     rcx, [rsi+18h]; hHandle
0x180078d75  mov     edx, 1F4h; dwMilliseconds
0x180078d7a  call    cs:__imp_WaitForSingleObject
0x180078d80  test    eax, eax
0x180078d82  jnz     loc_180078C78
0x180078d88  mov     ebx, 800704C7h
0x180078d8d  jmp     loc_180078E13
0x180078d92  mov     r10, cs:WPP_GLOBAL_Control
0x180078d99  cmp     r10, r13
0x180078d9c  jz      short loc_180078E1A
0x180078d9e  cmp     byte ptr [r10+19h], 2
0x180078da3  jb      short loc_180078E1A
0x180078da5  mov     edx, 29h ; ')'
0x180078daa  jmp     short loc_180078E00
0x180078dac  mov     rcx, [rsi+70h]
0x180078db0  lea     r9, qword_180098990
0x180078db7  xor     r8d, r8d
0x180078dba  xor     edx, edx
0x180078dbc  mov     rax, [rcx]
0x180078dbf  mov     rax, [rax+18h]
0x180078dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dc8  mov     ebx, eax
0x180078dca  test    eax, eax
0x180078dcc  jns     short loc_180078E13
0x180078dce  mov     r10, cs:WPP_GLOBAL_Control
0x180078dd5  cmp     r10, r13
0x180078dd8  jz      short loc_180078E1A
0x180078dda  cmp     byte ptr [r10+19h], 2
0x180078ddf  jb      short loc_180078E1A
0x180078de1  mov     edx, 2Ah ; '*'
0x180078de6  jmp     short loc_180078E00
0x180078de8  mov     r10, cs:WPP_GLOBAL_Control
0x180078def  cmp     r10, r13
0x180078df2  jz      short loc_180078E1A
0x180078df4  cmp     byte ptr [r10+19h], 2
0x180078df9  jb      short loc_180078E1A
0x180078dfb  mov     edx, 28h ; '('
0x180078e00  mov     rcx, [r10+10h]
0x180078e04  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180078e0b  mov     r9d, eax
0x180078e0e  call    WPP_SF_d
0x180078e13  mov     r10, cs:WPP_GLOBAL_Control
0x180078e1a  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x180078e1f  test    rcx, rcx
0x180078e22  jz      short loc_180078E3D
0x180078e24  xor     edx, edx; pReserved
0x180078e26  call    cs:__imp_WlanCloseHandle
0x180078e2c  mov     rcx, [rsi+20h]; hEvent
0x180078e30  call    cs:__imp_ResetEvent
0x180078e36  mov     r10, cs:WPP_GLOBAL_Control
0x180078e3d  cmp     r10, r13
0x180078e40  jz      short loc_180078E71
0x180078e42  test    ebx, ebx
0x180078e44  js      short loc_180078E4D
0x180078e46  cmp     byte ptr [r10+19h], 6
0x180078e4b  jb      short loc_180078E71
0x180078e4d  or      ecx, 0FFFFFFFFh; int
0x180078e50  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180078e55  mov     rcx, [r10+10h]
0x180078e59  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180078e60  mov     edx, 2Bh ; '+'
0x180078e65  mov     dword ptr [rsp+58h+pCallbackContext], ebx
0x180078e69  mov     r9, rax
0x180078e6c  call    WPP_SF_sd
0x180078e71  mov     rsi, [rsp+58h+arg_18]
0x180078e76  mov     eax, ebx
0x180078e78  mov     rbx, [rsp+58h+arg_0]
0x180078e7d  add     rsp, 40h
0x180078e81  pop     r15
0x180078e83  pop     r14
0x180078e85  pop     r13
0x180078e87  retn
```
