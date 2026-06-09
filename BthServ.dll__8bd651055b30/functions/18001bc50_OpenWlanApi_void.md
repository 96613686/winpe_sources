# OpenWlanApi(void)

- ea: `0x18001bc50`
- end: `0x18001bf44`
- name: `?OpenWlanApi@@YAHXZ`
- size: `756`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001afc0`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001b73c`
- `0x18001bc50`
- `0x18001bf4c`
- `0x18001c2e4`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001becf`
- `wlanapi!WlanFreeMemory` at `0x18001becf`
- `wlanapi!WlanRegisterNotification` at `0x18001be6f`
- `wlanapi!WlanRegisterNotification` at `0x18001be6f`
- `wlanapi!WlanEnumInterfaces` at `0x18001bd64`
- `wlanapi!WlanEnumInterfaces` at `0x18001bd64`
- `wlanapi!WlanOpenHandle` at `0x18001bce3`
- `wlanapi!WlanOpenHandle` at `0x18001bce3`

## pseudocode

```c
__int64 OpenWlanApi(void)
{
  unsigned int v0; // edi
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  DWORD v5; // r9d
  _BYTE *v6; // rcx
  DWORD dwNumberOfItems; // ecx
  bool v8; // dl
  int pCallbackContext; // [rsp+20h] [rbp-38h]
  int pReserved; // [rsp+28h] [rbp-30h]
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+38h] BYREF
  DWORD pdwPrevNotifSource; // [rsp+98h] [rbp+40h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+A0h] [rbp+48h] BYREF
  void *phClientHandle; // [rsp+A8h] [rbp+50h] BYREF

  v0 = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  phClientHandle = 0;
  pdwPrevNotifSource = 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  *((_QWORD *)pInterfaceGuid + 12) = phClientHandle;
  if ( v5 )
  {
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        pCallbackContext,
        pReserved,
        28,
        (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
    }
    *((_QWORD *)pInterfaceGuid + 12) = 0;
    goto LABEL_44;
  }
  if ( !WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList) )
  {
    dwNumberOfItems = ppInterfaceList->dwNumberOfItems;
    *((_DWORD *)pInterfaceGuid + 28) = ppInterfaceList->dwNumberOfItems;
    if ( dwNumberOfItems == 1 )
    {
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      *(GUID *)pInterfaceGuid = ppInterfaceList->InterfaceInfo[0].InterfaceGuid;
      *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
      ProcessNotification();
    }
    if ( WlanRegisterNotification(
           *((HANDLE *)pInterfaceGuid + 12),
           0x18u,
           1,
           AutoConfigNotificationCallback,
           0,
           0,
           &pdwPrevNotifSource) )
    {
      v6 = WPP_GLOBAL_Control;
      LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( !(_BYTE)v3 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_45;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        pCallbackContext,
        pReserved,
        31,
        (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
    }
    else
    {
      v0 = 1;
    }
LABEL_44:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v6 = WPP_GLOBAL_Control;
  LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      pCallbackContext,
      pReserved,
      29,
      (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
    goto LABEL_44;
  }
LABEL_45:
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    v6 = WPP_GLOBAL_Control;
    ppInterfaceList = 0;
  }
  if ( !v0 )
  {
    CloseWlanApi();
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v1;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v6 + 2),
      v3,
      v4,
      *((_QWORD *)v6 + 5),
      pCallbackContext,
      pReserved,
      32,
      (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
  }
  return v0;
}

```

## disassembly

```asm
0x18001bc50  push    rbp
0x18001bc52  push    rbx
0x18001bc53  push    rdi
0x18001bc54  push    r13
0x18001bc56  push    r14
0x18001bc58  push    r15
0x18001bc5a  mov     rbp, rsp
0x18001bc5d  sub     rsp, 58h
0x18001bc61  xor     edi, edi
0x18001bc63  mov     [rbp+pdwNegotiatedVersion], 0
0x18001bc6a  mov     [rbp+ppInterfaceList], rdi
0x18001bc6e  mov     [rbp+phClientHandle], rdi
0x18001bc72  mov     [rbp+arg_8], 0
0x18001bc79  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc80  lea     r14, WPP_GLOBAL_Control
0x18001bc87  lea     ebx, [rdi+1]
0x18001bc8a  cmp     rcx, r14
0x18001bc8d  jz      short loc_18001BC99
0x18001bc8f  cmp     byte ptr [rcx+19h], 4
0x18001bc93  jb      short loc_18001BC99
0x18001bc95  mov     dl, bl
0x18001bc97  jmp     short loc_18001BC9B
0x18001bc99  xor     dl, dl
0x18001bc9b  lea     r15, WPP_RECORDER_INITIALIZED
0x18001bca2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bca9  lea     r13, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001bcb0  setnz   r8b
0x18001bcb4  test    dl, dl
0x18001bcb6  jnz     short loc_18001BCBD
0x18001bcb8  test    r8b, r8b
0x18001bcbb  jz      short loc_18001BCD6
0x18001bcbd  mov     r9, [rcx+28h]
0x18001bcc1  mov     rcx, [rcx+10h]
0x18001bcc5  mov     [rsp+58h+var_20], r13
0x18001bcca  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Bh
0x18001bcd1  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001bcd6  xor     edx, edx; pReserved
0x18001bcd8  lea     r9, [rbp+phClientHandle]; phClientHandle
0x18001bcdc  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18001bce0  lea     ecx, [rdx+2]; dwClientVersion
0x18001bce3  call    cs:__imp_WlanOpenHandle
0x18001bce9  mov     rcx, [rbp+phClientHandle]
0x18001bced  mov     r9d, eax
0x18001bcf0  mov     rax, cs:pInterfaceGuid
0x18001bcf7  mov     [rax+60h], rcx
0x18001bcfb  test    r9d, r9d
0x18001bcfe  jz      short loc_18001BD5A
0x18001bd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd07  cmp     rcx, r14
0x18001bd0a  jz      short loc_18001BD16
0x18001bd0c  cmp     byte ptr [rcx+19h], 3
0x18001bd10  jb      short loc_18001BD16
0x18001bd12  mov     dl, bl
0x18001bd14  jmp     short loc_18001BD18
0x18001bd16  xor     dl, dl
0x18001bd18  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bd1f  setnz   r8b
0x18001bd23  test    dl, dl
0x18001bd25  jnz     short loc_18001BD2C
0x18001bd27  test    r8b, r8b
0x18001bd2a  jz      short loc_18001BD4A
0x18001bd2c  mov     [rsp+58h+var_10], r9d
0x18001bd31  mov     r9, [rcx+28h]
0x18001bd35  mov     rcx, [rcx+10h]
0x18001bd39  mov     [rsp+58h+var_20], r13
0x18001bd3e  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Ch
0x18001bd45  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001bd4a  mov     rax, cs:pInterfaceGuid
0x18001bd51  mov     [rax+60h], rdi
0x18001bd55  jmp     loc_18001BEBC
0x18001bd5a  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18001bd5e  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x18001bd62  xor     edx, edx; pReserved
0x18001bd64  call    cs:__imp_WlanEnumInterfaces
0x18001bd6a  test    eax, eax
0x18001bd6c  jz      short loc_18001BDC0
0x18001bd6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd75  cmp     rcx, r14
0x18001bd78  jz      short loc_18001BD84
0x18001bd7a  cmp     byte ptr [rcx+19h], 3
0x18001bd7e  jb      short loc_18001BD84
0x18001bd80  mov     dl, bl
0x18001bd82  jmp     short loc_18001BD86
0x18001bd84  xor     dl, dl
0x18001bd86  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bd8d  setnz   r8b
0x18001bd91  test    dl, dl
0x18001bd93  jnz     short loc_18001BD9E
0x18001bd95  test    r8b, r8b
0x18001bd98  jz      loc_18001BEC3
0x18001bd9e  mov     [rsp+58h+var_10], eax
0x18001bda2  mov     [rsp+58h+var_20], r13
0x18001bda7  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Dh
0x18001bdae  mov     r9, [rcx+28h]
0x18001bdb2  mov     rcx, [rcx+10h]
0x18001bdb6  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001bdbb  jmp     loc_18001BEBC
0x18001bdc0  mov     rax, [rbp+ppInterfaceList]
0x18001bdc4  mov     ecx, [rax]
0x18001bdc6  mov     rax, cs:pInterfaceGuid
0x18001bdcd  mov     [rax+70h], ecx
0x18001bdd0  cmp     ecx, ebx
0x18001bdd2  jnz     short loc_18001BE42
0x18001bdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bddb  cmp     rcx, r14
0x18001bdde  jz      short loc_18001BDEA
0x18001bde0  cmp     byte ptr [rcx+19h], 4
0x18001bde4  jb      short loc_18001BDEA
0x18001bde6  mov     dl, bl
0x18001bde8  jmp     short loc_18001BDEC
0x18001bdea  xor     dl, dl
0x18001bdec  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bdf3  setnz   r8b
0x18001bdf7  test    dl, dl
0x18001bdf9  jnz     short loc_18001BE00
0x18001bdfb  test    r8b, r8b
0x18001bdfe  jz      short loc_18001BE19
0x18001be00  mov     r9, [rcx+28h]
0x18001be04  mov     rcx, [rcx+10h]
0x18001be08  mov     [rsp+58h+var_20], r13
0x18001be0d  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Eh
0x18001be14  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001be19  mov     rax, [rbp+ppInterfaceList]
0x18001be1d  movups  xmm0, xmmword ptr [rax+8]
0x18001be21  mov     rax, cs:pInterfaceGuid
0x18001be28  movdqu  xmmword ptr [rax], xmm0
0x18001be2c  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001be31  mov     cl, al
0x18001be33  mov     rax, cs:pInterfaceGuid
0x18001be3a  mov     [rax+78h], cl
0x18001be3d  call    ?ProcessNotification@@YAXXZ; ProcessNotification(void)
0x18001be42  mov     rcx, cs:pInterfaceGuid
0x18001be49  lea     rax, [rbp+arg_8]
0x18001be4d  mov     [rsp+58h+pdwPrevNotifSource], rax; pdwPrevNotifSource
0x18001be52  lea     r9, ?AutoConfigNotificationCallback@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18001be59  mov     [rsp+58h+pReserved], rdi; pReserved
0x18001be5e  mov     r8d, ebx; bIgnoreDuplicate
0x18001be61  mov     edx, 18h; dwNotifSource
0x18001be66  mov     [rsp+58h+pCallbackContext], rdi; pCallbackContext
0x18001be6b  mov     rcx, [rcx+60h]; hClientHandle
0x18001be6f  call    cs:__imp_WlanRegisterNotification
0x18001be75  test    eax, eax
0x18001be77  jz      short loc_18001BEBA
0x18001be79  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be80  cmp     rcx, r14
0x18001be83  jz      short loc_18001BE8F
0x18001be85  cmp     byte ptr [rcx+19h], 3
0x18001be89  jb      short loc_18001BE8F
0x18001be8b  mov     dl, bl
0x18001be8d  jmp     short loc_18001BE91
0x18001be8f  xor     dl, dl
0x18001be91  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001be98  setnz   r8b
0x18001be9c  test    dl, dl
0x18001be9e  jnz     short loc_18001BEA5
0x18001bea0  test    r8b, r8b
0x18001bea3  jz      short loc_18001BEC3
0x18001bea5  mov     [rsp+58h+var_10], eax
0x18001bea9  mov     [rsp+58h+var_20], r13
0x18001beae  mov     word ptr [rsp+58h+pdwPrevNotifSource], 1Fh
0x18001beb5  jmp     loc_18001BDAE
0x18001beba  mov     edi, ebx
0x18001bebc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bec3  mov     rax, [rbp+ppInterfaceList]
0x18001bec7  test    rax, rax
0x18001beca  jz      short loc_18001BEE4
0x18001becc  mov     rcx, rax; pMemory
0x18001becf  call    cs:__imp_WlanFreeMemory
0x18001bed5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bedc  mov     [rbp+ppInterfaceList], 0
0x18001bee4  test    edi, edi
0x18001bee6  jnz     short loc_18001BEF4
0x18001bee8  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001beed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bef4  cmp     rcx, r14
0x18001bef7  jz      short loc_18001BEFF
0x18001bef9  cmp     byte ptr [rcx+19h], 4
0x18001befd  jnb     short loc_18001BF01
0x18001beff  xor     bl, bl
0x18001bf01  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bf08  setnz   r8b
0x18001bf0c  test    bl, bl
0x18001bf0e  jnz     short loc_18001BF15
0x18001bf10  test    r8b, r8b
0x18001bf13  jz      short loc_18001BF34
0x18001bf15  mov     r9, [rcx+28h]
0x18001bf19  mov     dl, bl
0x18001bf1b  mov     rcx, [rcx+10h]
0x18001bf1f  mov     [rsp+58h+var_10], edi
0x18001bf23  mov     [rsp+58h+var_20], r13
0x18001bf28  mov     word ptr [rsp+58h+pdwPrevNotifSource], 20h ; ' '
0x18001bf2f  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001bf34  mov     eax, edi
0x18001bf36  add     rsp, 58h
0x18001bf3a  pop     r15
0x18001bf3c  pop     r14
0x18001bf3e  pop     r13
0x18001bf40  pop     rdi
0x18001bf41  pop     rbx
0x18001bf42  pop     rbp
0x18001bf43  retn
```
