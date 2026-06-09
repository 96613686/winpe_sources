# WcnWlanProfileSaveToWlan

- ea: `0x180079bb8`
- end: `0x180079ec2`
- name: `WcnWlanProfileSaveToWlan`
- size: `778`
- prototype: `__int64 __fastcall(LPCWSTR strProfileXml)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007972c`

## callees

- `0x18001d3a4`
- `0x180076f84`
- `0x180076fe0`
- `0x180079bb8`
- `0x180079ec8`
- `0x180088304`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x180079cce`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x180079cce`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180079e58`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180079e58`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180079d8c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180079d8c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180079c6d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180079c6d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180079e70`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180079e70`

## string_xrefs

- `0x180079c47`: `wszWlanXmlProfile`

## pseudocode

```c
__int64 __fastcall WcnWlanProfileSaveToWlan(LPCWSTR strProfileXml, _QWORD *a2)
{
  PVOID *v4; // r10
  signed int v5; // ebx
  const char *Indent; // rax
  __int64 v7; // r10
  signed int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // r10
  __int64 v12; // rdx
  unsigned int v13; // ebx
  char v14; // r14
  DWORD v15; // edi
  WLAN_INTERFACE_INFO *v16; // rsi
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // edx
  int v21; // r8d
  char v22; // r11
  const char *v23; // rax
  __int64 v24; // r10
  unsigned int v25; // eax
  __int64 v26; // r10
  void *phClientHandle; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwReasonCode; // [rsp+A0h] [rbp+50h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+A8h] [rbp+58h] BYREF

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  v5 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 10, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !strProfileXml )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 11, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, "wszWlanXmlProfile");
    return 2147500035LL;
  }
  v9 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v5 = v10 | 0x80000000;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v12 = 12;
    goto LABEL_16;
  }
  v9 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  if ( v9 )
  {
    if ( v9 > 0 )
      v13 = (unsigned __int16)v9 | 0x80070000;
    else
      v13 = v9;
    v5 = v13 | 0x80000000;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v12 = 13;
LABEL_16:
    WPP_SF_Dd(v11[2], v12, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, (unsigned int)v9, v5);
    goto LABEL_41;
  }
  v14 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  v15 = 0;
  if ( !ppInterfaceList->dwNumberOfItems )
    goto LABEL_38;
  do
  {
    v16 = &ppInterfaceList->InterfaceInfo[v15];
    if ( !a2 )
      goto LABEL_29;
    v17 = *a2 - *(_QWORD *)&v16->InterfaceGuid.Data1;
    if ( *a2 == *(_QWORD *)&v16->InterfaceGuid.Data1 )
      v17 = a2[1] - *(_QWORD *)v16->InterfaceGuid.Data4;
    if ( !v17 )
    {
LABEL_29:
      pdwReasonCode = 0;
      if ( !WlanSetProfile(phClientHandle, &v16->InterfaceGuid, 0, strProfileXml, 0, 1, 0, &pdwReasonCode) )
      {
        v14 = 1;
        goto LABEL_34;
      }
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v18 = (unsigned int)GetIndent(0);
        WPP_SF_sS_guid_d(*(_QWORD *)(v19 + 16), v20, v21, v18, (__int64)v16->strInterfaceDescription, (__int64)v16, v22);
LABEL_34:
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    ++v15;
  }
  while ( v15 < ppInterfaceList->dwNumberOfItems );
  if ( v14 )
  {
    v5 = 0;
    goto LABEL_42;
  }
LABEL_38:
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 4u )
  {
    v23 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v24 + 16), 15, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v23);
LABEL_41:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( ppInterfaceList )
  {
    WlanFreeMemory(ppInterfaceList);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)v11 + 25) >= 6u) )
  {
    v25 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v26 + 16), 16, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v25, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180079bb8  push    rbp
0x180079bba  push    rbx
0x180079bbb  push    rsi
0x180079bbc  push    rdi
0x180079bbd  push    r12
0x180079bbf  push    r14
0x180079bc1  push    r15
0x180079bc3  mov     rbp, rsp
0x180079bc6  sub     rsp, 50h
0x180079bca  mov     r15, rdx
0x180079bcd  mov     [rbp+phClientHandle], 0
0x180079bd5  mov     r12, rcx
0x180079bd8  mov     [rbp+pdwNegotiatedVersion], 0
0x180079bdf  mov     [rbp+ppInterfaceList], 0
0x180079be7  mov     r10, cs:WPP_GLOBAL_Control
0x180079bee  lea     rdi, WPP_GLOBAL_Control
0x180079bf5  lea     rsi, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180079bfc  mov     ebx, 1
0x180079c01  cmp     r10, rdi
0x180079c04  jz      short loc_180079C2D
0x180079c06  cmp     byte ptr [r10+19h], 6
0x180079c0b  jb      short loc_180079C2D
0x180079c0d  mov     ecx, ebx; int
0x180079c0f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079c14  mov     rcx, [r10+10h]
0x180079c18  lea     edx, [rbx+9]
0x180079c1b  mov     r9, rax
0x180079c1e  mov     r8, rsi
0x180079c21  call    WPP_SF_s
0x180079c26  mov     r10, cs:WPP_GLOBAL_Control
0x180079c2d  test    r12, r12
0x180079c30  jnz     short loc_180079C60
0x180079c32  cmp     r10, rdi
0x180079c35  jz      short loc_180079C56
0x180079c37  cmp     byte ptr [r10+19h], 2
0x180079c3c  jb      short loc_180079C56
0x180079c3e  mov     rcx, [r10+10h]
0x180079c42  lea     edx, [r12+0Bh]
0x180079c47  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x180079c4e  mov     r8, rsi
0x180079c51  call    WPP_SF_s
0x180079c56  mov     eax, 80004003h
0x180079c5b  jmp     loc_180079EB3
0x180079c60  xor     edx, edx; pReserved
0x180079c62  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180079c66  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180079c6a  lea     ecx, [rdx+2]; dwClientVersion
0x180079c6d  call    cs:__imp_WlanOpenHandle
0x180079c73  test    eax, eax
0x180079c75  jz      short loc_180079CC4
0x180079c77  jg      short loc_180079C7D
0x180079c79  mov     ebx, eax
0x180079c7b  jmp     short loc_180079C86
0x180079c7d  movzx   ebx, ax
0x180079c80  or      ebx, 80070000h
0x180079c86  or      ebx, 80000000h
0x180079c8c  mov     r10, cs:WPP_GLOBAL_Control
0x180079c93  cmp     r10, rdi
0x180079c96  jz      loc_180079E4F
0x180079c9c  cmp     byte ptr [r10+19h], 2
0x180079ca1  jb      loc_180079E4F
0x180079ca7  mov     edx, 0Ch
0x180079cac  mov     rcx, [r10+10h]
0x180079cb0  mov     r9d, eax
0x180079cb3  mov     r8, rsi
0x180079cb6  mov     dword ptr [rsp+50h+strAllUserProfileSecurity], ebx
0x180079cba  call    WPP_SF_Dd
0x180079cbf  jmp     loc_180079E48
0x180079cc4  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180079cc8  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x180079ccc  xor     edx, edx; pReserved
0x180079cce  call    cs:__imp_WlanEnumInterfaces
0x180079cd4  test    eax, eax
0x180079cd6  jz      short loc_180079D0F
0x180079cd8  jg      short loc_180079CDE
0x180079cda  mov     ebx, eax
0x180079cdc  jmp     short loc_180079CE7
0x180079cde  movzx   ebx, ax
0x180079ce1  or      ebx, 80070000h
0x180079ce7  or      ebx, 80000000h
0x180079ced  mov     r10, cs:WPP_GLOBAL_Control
0x180079cf4  cmp     r10, rdi
0x180079cf7  jz      loc_180079E4F
0x180079cfd  cmp     byte ptr [r10+19h], 2
0x180079d02  jb      loc_180079E4F
0x180079d08  mov     edx, 0Dh
0x180079d0d  jmp     short loc_180079CAC
0x180079d0f  mov     rax, [rbp+ppInterfaceList]
0x180079d13  xor     r14b, r14b
0x180079d16  mov     r10, cs:WPP_GLOBAL_Control
0x180079d1d  xor     edi, edi
0x180079d1f  cmp     [rax], edi
0x180079d21  jbe     loc_180079E1A
0x180079d27  mov     rsi, [rbp+ppInterfaceList]
0x180079d2b  add     rsi, 8
0x180079d2f  mov     eax, edi
0x180079d31  imul    rcx, rax, 214h
0x180079d38  add     rsi, rcx
0x180079d3b  test    r15, r15
0x180079d3e  jz      short loc_180079D59
0x180079d40  mov     rax, [r15]
0x180079d43  sub     rax, [rsi]
0x180079d46  jnz     short loc_180079D50
0x180079d48  mov     rax, [r15+8]
0x180079d4c  sub     rax, [rsi+8]
0x180079d50  test    rax, rax
0x180079d53  jnz     loc_180079DF5
0x180079d59  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180079d5d  lea     rax, [rbp+arg_10]
0x180079d61  mov     [rsp+50h+pdwReasonCode], rax; pdwReasonCode
0x180079d66  mov     r9, r12; strProfileXml
0x180079d69  mov     [rsp+50h+pReserved], 0; pReserved
0x180079d72  xor     r8d, r8d; dwFlags
0x180079d75  mov     [rsp+50h+bOverwrite], ebx; bOverwrite
0x180079d79  mov     rdx, rsi; pInterfaceGuid
0x180079d7c  mov     [rsp+50h+strAllUserProfileSecurity], 0; strAllUserProfileSecurity
0x180079d85  mov     [rbp+arg_10], 0
0x180079d8c  call    cs:__imp_WlanSetProfile
0x180079d92  mov     r11d, eax
0x180079d95  test    eax, eax
0x180079d97  jz      short loc_180079DEB
0x180079d99  mov     r10, cs:WPP_GLOBAL_Control
0x180079da0  lea     rax, WPP_GLOBAL_Control
0x180079da7  cmp     r10, rax
0x180079daa  jz      short loc_180079DF5
0x180079dac  cmp     byte ptr [r10+19h], 3
0x180079db1  jb      short loc_180079DF5
0x180079db3  test    r11d, r11d
0x180079db6  jle     short loc_180079DC3
0x180079db8  movzx   r11d, r11w
0x180079dbc  or      r11d, 80070000h
0x180079dc3  xor     ecx, ecx; int
0x180079dc5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079dca  mov     dword ptr [rsp+50h+pReserved], r11d
0x180079dcf  lea     rcx, [rsi+10h]
0x180079dd3  mov     qword ptr [rsp+50h+bOverwrite], rsi
0x180079dd8  mov     r9, rax
0x180079ddb  mov     [rsp+50h+strAllUserProfileSecurity], rcx
0x180079de0  mov     rcx, [r10+10h]
0x180079de4  call    WPP_SF_sS_guid_d
0x180079de9  jmp     short loc_180079DEE
0x180079deb  mov     r14b, bl
0x180079dee  mov     r10, cs:WPP_GLOBAL_Control
0x180079df5  mov     rax, [rbp+ppInterfaceList]
0x180079df9  add     edi, ebx
0x180079dfb  cmp     edi, [rax]
0x180079dfd  jb      loc_180079D27
0x180079e03  test    r14b, r14b
0x180079e06  jz      short loc_180079E13
0x180079e08  xor     ebx, ebx
0x180079e0a  lea     rdi, WPP_GLOBAL_Control
0x180079e11  jmp     short loc_180079E4F
0x180079e13  lea     rsi, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180079e1a  lea     rdi, WPP_GLOBAL_Control
0x180079e21  cmp     r10, rdi
0x180079e24  jz      short loc_180079E4F
0x180079e26  cmp     byte ptr [r10+19h], 4
0x180079e2b  jb      short loc_180079E4F
0x180079e2d  xor     ecx, ecx; int
0x180079e2f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079e34  mov     rcx, [r10+10h]
0x180079e38  mov     edx, 0Fh
0x180079e3d  mov     r9, rax
0x180079e40  mov     r8, rsi
0x180079e43  call    WPP_SF_s
0x180079e48  mov     r10, cs:WPP_GLOBAL_Control
0x180079e4f  mov     rcx, [rbp+ppInterfaceList]; pMemory
0x180079e53  test    rcx, rcx
0x180079e56  jz      short loc_180079E65
0x180079e58  call    cs:__imp_WlanFreeMemory
0x180079e5e  mov     r10, cs:WPP_GLOBAL_Control
0x180079e65  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180079e69  test    rcx, rcx
0x180079e6c  jz      short loc_180079E7D
0x180079e6e  xor     edx, edx; pReserved
0x180079e70  call    cs:__imp_WlanCloseHandle
0x180079e76  mov     r10, cs:WPP_GLOBAL_Control
0x180079e7d  cmp     r10, rdi
0x180079e80  jz      short loc_180079EB1
0x180079e82  test    ebx, ebx
0x180079e84  js      short loc_180079E8D
0x180079e86  cmp     byte ptr [r10+19h], 6
0x180079e8b  jb      short loc_180079EB1
0x180079e8d  or      ecx, 0FFFFFFFFh; int
0x180079e90  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079e95  mov     rcx, [r10+10h]
0x180079e99  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180079ea0  mov     edx, 10h
0x180079ea5  mov     dword ptr [rsp+50h+strAllUserProfileSecurity], ebx
0x180079ea9  mov     r9, rax
0x180079eac  call    WPP_SF_sd
0x180079eb1  mov     eax, ebx
0x180079eb3  add     rsp, 50h
0x180079eb7  pop     r15
0x180079eb9  pop     r14
0x180079ebb  pop     r12
0x180079ebd  pop     rdi
0x180079ebe  pop     rsi
0x180079ebf  pop     rbx
0x180079ec0  pop     rbp
0x180079ec1  retn
```
