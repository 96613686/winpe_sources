# USBSTOR_QueryGlobalFdoParams

- ea: `0x140026f6c`
- end: `0x1400274f8`
- name: `USBSTOR_QueryGlobalFdoParams`
- size: `1420`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140008590`

## callees

- `0x14000dc48`
- `0x1400105e8`
- `0x140010664`
- `0x140010da4`
- `0x140013950`
- `0x140013990`
- `0x140013d40`
- `0x14002239c`
- `0x140026f6c`
- `0x140027500`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400270df`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400271a3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140027243`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140027423`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400270df`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400271a3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140027243`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140027423`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140027044`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140027044`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272a7`

## pseudocode

```c
int __fastcall USBSTOR_QueryGlobalFdoParams(__int64 a1)
{
  int v1; // r15d
  _WORD *v3; // r14
  __int64 v4; // rsi
  __int64 v5; // rax
  unsigned int v6; // edi
  __int64 v7; // r9
  NTSTATUS RegistryValues; // r12d
  int v9; // edx
  int v10; // ecx
  NTSTATUS StateSeparationLocation; // eax
  unsigned int v12; // r13d
  unsigned int v13; // ebx
  unsigned int i; // edi
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned int j; // edi
  __int64 v20; // r8
  _WORD *v21; // rax
  __int16 v22; // cx
  __int16 v23; // cx
  __int64 v24; // rax
  unsigned int k; // ebx
  __int64 v26; // r8
  int v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+34h] [rbp-CCh] BYREF
  int v33; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+3Ch] [rbp-C4h]
  unsigned int v35; // [rsp+40h] [rbp-C0h]
  _WORD *v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v38[14]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v40[32]; // [rsp+110h] [rbp+10h] BYREF

  v1 = 0;
  v31 = 0;
  v3 = 0;
  v32 = 0;
  v33 = 0;
  v37 = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(v4 + 48);
  v6 = *(unsigned __int16 *)(v5 + 8);
  v7 = *(unsigned __int16 *)(v5 + 8);
  v34 = *(unsigned __int16 *)(v5 + 10);
  v35 = v6;
  v28 = v34;
  RtlStringCchPrintfW(pszDest, 0x20u, L"usbstor\\%04x%04x", v7, v28);
  LODWORD(v29) = v34;
  RegistryValues = RtlStringCchPrintfW(v40, 0x20u, L"USBSTOR:USB\\VID_%04X&PID_%04X", v6, v29);
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    StateSeparationLocation = USBSTOR_GetStateSeparationLocation(v10, v9, (unsigned int)pszDest, 64, (__int64)&v36);
    v3 = v36;
    RegistryValues = StateSeparationLocation;
  }
  if ( !*(_DWORD *)(v4 + 120) )
  {
    v31 = 0;
    memset(v38, 0, sizeof(v38));
    LODWORD(v38[1]) = 288;
    v38[2] = L"DriverFlags";
    LODWORD(v38[4]) = 67108868;
    v38[3] = &v31;
    LODWORD(v38[6]) = 4;
    v38[5] = &v31;
    HIDWORD(v30) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(2, pszDest, v38);
    if ( RegistryValues >= 0 && v31 < 4 )
      *(_DWORD *)(v4 + 120) = v31;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
  }
  memset(v38, 0, sizeof(v38));
  LODWORD(v38[6]) = 4;
  v38[2] = L"DeviceHackFlags";
  v12 = 15;
  LODWORD(v38[1]) = 288;
  v38[3] = &v32;
  v13 = 15;
  LODWORD(v38[4]) = 67108868;
  v38[5] = &v32;
  for ( i = 0; i < 5 && v13; ++i )
  {
    HIDWORD(v30) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(2, pszDest, v38);
    if ( RegistryValues >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 23, v15, pszDest, 0);
      }
      *(_DWORD *)(v4 + 132) = v32;
      break;
    }
    v16 = v13--;
    pszDest[v16] = 120;
  }
  if ( !v3 )
    goto LABEL_78;
  v17 = -1;
  do
    ++v17;
  while ( v3[v17] );
  v18 = (unsigned int)(v17 - 1);
  v32 = 0;
  for ( j = 0; j < 5 && (_DWORD)v18; ++j )
  {
    HIDWORD(v30) = 0;
    v1 = RtlQueryRegistryValuesEx(0, v3, v38);
    if ( v1 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 24, v20, v3, 0);
      }
      *(_DWORD *)(v4 + 132) += v32;
      break;
    }
    v3[v18] = 120;
    v18 = (unsigned int)(v18 - 1);
  }
  ExFreePoolWithTag(v3, 0);
  if ( v1 >= 0 )
  {
    RegistryValues = v1;
  }
  else
  {
LABEL_78:
    if ( RegistryValues < 0 )
    {
      if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
      {
        RegistryValues = (*(__int64 (__fastcall **)(wchar_t *, const wchar_t *, __int64 *))&WPP_MAIN_CB.DeviceType)(
                           v40,
                           L"USBSTOR",
                           &v37);
        if ( RegistryValues >= 0 )
          *(_DWORD *)(v4 + 132) = v37;
      }
    }
  }
  USBSTOR_GlobalSelectiveSuspendSetting(v4);
  if ( RegistryValues < 0 )
  {
    v21 = *(_WORD **)(v4 + 48);
    v22 = v21[4];
    if ( v22 == 3034 )
    {
      if ( v21[5] != 775 || v21[6] != 297 )
        goto LABEL_53;
    }
    else
    {
      if ( v22 != 1118 )
        goto LABEL_53;
      v23 = v21[5];
      if ( v23 != 2316 && v23 != 774 )
        goto LABEL_53;
    }
    *(_DWORD *)(v4 + 132) |= 0x800u;
  }
LABEL_53:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  memset(v38, 0, sizeof(v38));
  v38[2] = L"MaximumTransferLength";
  LODWORD(v38[1]) = 288;
  v38[3] = &v33;
  LODWORD(v38[4]) = 67108868;
  v38[5] = &v33;
  LODWORD(v30) = v34;
  LODWORD(v38[6]) = 4;
  LODWORD(v24) = RtlStringCchPrintfW(pszDest, 0x20u, L"usbstor\\%04x%04x", v35, v30);
  for ( k = 0; k < 5 && v12; ++k )
  {
    if ( (int)RtlQueryRegistryValuesEx(2, pszDest, v38) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 26, v26, pszDest, 0);
      }
      LODWORD(v24) = v33;
      *(_DWORD *)(v4 + 136) = v33;
      break;
    }
    v24 = v12--;
    pszDest[v24] = 120;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v24) = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      LODWORD(v24) = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
  }
  return v24;
}

```

## disassembly

```asm
0x140026f6c  push    rbp
0x140026f6e  push    rbx
0x140026f6f  push    rsi
0x140026f70  push    rdi
0x140026f71  push    r12
0x140026f73  push    r13
0x140026f75  push    r14
0x140026f77  push    r15
0x140026f79  lea     rbp, [rsp-68h]
0x140026f7e  sub     rsp, 168h
0x140026f85  mov     rax, cs:__security_cookie
0x140026f8c  xor     rax, rsp
0x140026f8f  mov     [rbp+0A0h+var_50], rax
0x140026f93  xor     r15d, r15d
0x140026f96  mov     rbx, rcx
0x140026f99  mov     [rsp+1A0h+var_170], r15d
0x140026f9e  mov     r14d, r15d
0x140026fa1  mov     [rsp+1A0h+var_16C], r15d
0x140026fa6  mov     [rsp+1A0h+var_168], r15d
0x140026fab  mov     [rsp+1A0h+var_150], r15
0x140026fb0  mov     [rsp+1A0h+var_158], r15
0x140026fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140026fbc  lea     rax, WPP_GLOBAL_Control
0x140026fc3  lea     r13d, [r15+4]
0x140026fc7  cmp     rcx, rax
0x140026fca  jz      short loc_140026FEF
0x140026fcc  test    dword ptr [rcx+2Ch], 100h
0x140026fd3  jz      short loc_140026FEF
0x140026fd5  cmp     [rcx+29h], r13b
0x140026fd9  jb      short loc_140026FEF
0x140026fdb  mov     rcx, [rcx+18h]
0x140026fdf  lea     edx, [r15+15h]
0x140026fe3  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026fea  call    WPP_SF_
0x140026fef  mov     rsi, [rbx+40h]
0x140026ff3  lea     r8, aUsbstor04x04x; "usbstor\\%04x%04x"
0x140026ffa  mov     r12d, 20h ; ' '
0x140027000  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x140027004  mov     edx, r12d; cchDest
0x140027007  mov     rax, [rsi+30h]
0x14002700b  movzx   edi, word ptr [rax+8]
0x14002700f  movzx   ebx, word ptr [rax+0Ah]
0x140027013  mov     r9d, edi
0x140027016  mov     [rsp+1A0h+var_164], ebx
0x14002701a  mov     [rsp+1A0h+var_160], edi
0x14002701e  mov     dword ptr [rsp+1A0h+var_180], ebx
0x140027022  call    RtlStringCchPrintfW
0x140027027  mov     r9d, edi
0x14002702a  mov     dword ptr [rsp+1A0h+var_180], ebx
0x14002702e  lea     r8, aUsbstorUsbVid0; "USBSTOR:USB\\VID_%04X&PID_%04X"
0x140027035  mov     edx, r12d; cchDest
0x140027038  lea     rcx, [rbp+0A0h+var_90]; pszDest
0x14002703c  call    RtlStringCchPrintfW
0x140027041  mov     r12d, eax
0x140027044  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002704b  nop     dword ptr [rax+rax+00h]
0x140027050  test    al, al
0x140027052  jz      short loc_140027075
0x140027054  lea     rax, [rsp+1A0h+var_158]
0x140027059  mov     r9d, 40h ; '@'
0x14002705f  lea     r8, [rbp+0A0h+pszDest]
0x140027063  mov     [rsp+1A0h+var_180], rax
0x140027068  call    USBSTOR_GetStateSeparationLocation
0x14002706d  mov     r14, [rsp+1A0h+var_158]
0x140027072  mov     r12d, eax
0x140027075  mov     ebx, 70h ; 'p'
0x14002707a  mov     edi, 120h
0x14002707f  cmp     [rsi+78h], r15d
0x140027083  jnz     loc_14002713C
0x140027089  mov     r8d, ebx; Size
0x14002708c  mov     [rsp+1A0h+var_170], r15d
0x140027091  xor     edx, edx; Val
0x140027093  lea     rcx, [rsp+1A0h+var_140]; void *
0x140027098  call    memset
0x14002709d  lea     rax, aDriverflags; "DriverFlags"
0x1400270a4  mov     [rsp+1A0h+var_138], edi
0x1400270a8  mov     [rsp+1A0h+var_130], rax
0x1400270ad  lea     r8, [rsp+1A0h+var_140]
0x1400270b2  lea     rax, [rsp+1A0h+var_170]
0x1400270b7  mov     [rbp+0A0h+var_120], 4000004h
0x1400270be  mov     [rsp+1A0h+var_128], rax
0x1400270c3  lea     rdx, [rbp+0A0h+pszDest]
0x1400270c7  lea     rax, [rsp+1A0h+var_170]
0x1400270cc  mov     [rbp+0A0h+var_110], r13d
0x1400270d0  xor     r9d, r9d
0x1400270d3  mov     [rbp+0A0h+var_118], rax
0x1400270d7  lea     ecx, [rbx-6Eh]
0x1400270da  mov     [rsp+1A0h+var_180], r15
0x1400270df  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400270e6  nop     dword ptr [rax+rax+00h]
0x1400270eb  mov     r9d, [rsp+1A0h+var_170]
0x1400270f0  mov     r12d, eax
0x1400270f3  test    eax, eax
0x1400270f5  js      short loc_140027105
0x1400270f7  cmp     r9d, r13d
0x1400270fa  jnb     short loc_140027105
0x1400270fc  mov     [rsi+78h], r9d
0x140027100  mov     r9d, [rsp+1A0h+var_170]
0x140027105  mov     rcx, cs:WPP_GLOBAL_Control
0x14002710c  lea     rax, WPP_GLOBAL_Control
0x140027113  cmp     rcx, rax
0x140027116  jz      short loc_14002713C
0x140027118  test    dword ptr [rcx+2Ch], 100h
0x14002711f  jz      short loc_14002713C
0x140027121  cmp     [rcx+29h], r13b
0x140027125  jb      short loc_14002713C
0x140027127  mov     rcx, [rcx+18h]
0x14002712b  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027132  mov     edx, 16h
0x140027137  call    WPP_SF_d
0x14002713c  mov     r8, rbx; Size
0x14002713f  lea     rcx, [rsp+1A0h+var_140]; void *
0x140027144  xor     edx, edx; Val
0x140027146  call    memset
0x14002714b  lea     rax, aDevicehackflag; "DeviceHackFlags"
0x140027152  mov     [rbp+0A0h+var_110], r13d
0x140027156  mov     [rsp+1A0h+var_130], rax
0x14002715b  mov     r13d, 0Fh
0x140027161  lea     rax, [rsp+1A0h+var_16C]
0x140027166  mov     [rsp+1A0h+var_138], edi
0x14002716a  mov     [rsp+1A0h+var_128], rax
0x14002716f  mov     ebx, r13d
0x140027172  lea     rax, [rsp+1A0h+var_16C]
0x140027177  mov     [rbp+0A0h+var_120], 4000004h
0x14002717e  mov     [rbp+0A0h+var_118], rax
0x140027182  mov     edi, r15d
0x140027185  cmp     edi, 5
0x140027188  jnb     short loc_140027206
0x14002718a  test    ebx, ebx
0x14002718c  jz      short loc_140027206
0x14002718e  xor     r9d, r9d
0x140027191  mov     [rsp+1A0h+var_180], r15
0x140027196  lea     r8, [rsp+1A0h+var_140]
0x14002719b  lea     rdx, [rbp+0A0h+pszDest]
0x14002719f  lea     ecx, [r9+2]
0x1400271a3  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400271aa  nop     dword ptr [rax+rax+00h]
0x1400271af  mov     r12d, eax
0x1400271b2  test    eax, eax
0x1400271b4  jns     short loc_1400271C8
0x1400271b6  mov     eax, ebx
0x1400271b8  mov     ecx, 78h ; 'x'
0x1400271bd  dec     ebx
0x1400271bf  inc     edi
0x1400271c1  mov     [rbp+rax*2+0A0h+pszDest], cx
0x1400271c6  jmp     short loc_140027185
0x1400271c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400271cf  lea     rax, WPP_GLOBAL_Control
0x1400271d6  cmp     rcx, rax
0x1400271d9  jz      short loc_1400271FC
0x1400271db  test    dword ptr [rcx+2Ch], 100h
0x1400271e2  jz      short loc_1400271FC
0x1400271e4  cmp     byte ptr [rcx+29h], 4
0x1400271e8  jb      short loc_1400271FC
0x1400271ea  mov     rcx, [rcx+18h]
0x1400271ee  lea     r9, [rbp+0A0h+pszDest]
0x1400271f2  mov     edx, 17h
0x1400271f7  call    WPP_SF_S
0x1400271fc  mov     eax, [rsp+1A0h+var_16C]
0x140027200  mov     [rsi+84h], eax
0x140027206  test    r14, r14
0x140027209  jz      loc_1400272C3
0x14002720f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140027213  xor     ecx, ecx
0x140027215  inc     rax
0x140027218  cmp     [r14+rax*2], cx
0x14002721d  jnz     short loc_140027215
0x14002721f  lea     ebx, [rax-1]
0x140027222  mov     [rsp+1A0h+var_16C], ecx
0x140027226  mov     edi, ecx
0x140027228  cmp     edi, 5
0x14002722b  jnb     short loc_1400272A2
0x14002722d  test    ebx, ebx
0x14002722f  jz      short loc_1400272A2
0x140027231  mov     [rsp+1A0h+var_180], rcx
0x140027236  lea     r8, [rsp+1A0h+var_140]
0x14002723b  xor     ecx, ecx
0x14002723d  xor     r9d, r9d
0x140027240  mov     rdx, r14
0x140027243  call    cs:__imp_RtlQueryRegistryValuesEx
0x14002724a  nop     dword ptr [rax+rax+00h]
0x14002724f  mov     r15d, eax
0x140027252  test    eax, eax
0x140027254  jns     short loc_140027265
0x140027256  mov     word ptr [r14+rbx*2], 78h ; 'x'
0x14002725d  inc     edi
0x14002725f  dec     ebx
0x140027261  xor     ecx, ecx
0x140027263  jmp     short loc_140027228
0x140027265  mov     rcx, cs:WPP_GLOBAL_Control
0x14002726c  lea     rax, WPP_GLOBAL_Control
0x140027273  cmp     rcx, rax
0x140027276  jz      short loc_140027298
0x140027278  test    dword ptr [rcx+2Ch], 100h
0x14002727f  jz      short loc_140027298
0x140027281  cmp     byte ptr [rcx+29h], 4
0x140027285  jb      short loc_140027298
0x140027287  mov     rcx, [rcx+18h]
0x14002728b  mov     edx, 18h
0x140027290  mov     r9, r14
0x140027293  call    WPP_SF_S
0x140027298  mov     eax, [rsp+1A0h+var_16C]
0x14002729c  add     [rsi+84h], eax
0x1400272a2  xor     edx, edx; Tag
0x1400272a4  mov     rcx, r14; P
0x1400272a7  call    cs:__imp_ExFreePoolWithTag
0x1400272ae  nop     dword ptr [rax+rax+00h]
0x1400272b3  test    r15d, r15d
0x1400272b6  js      short loc_1400272C0
0x1400272b8  mov     r12d, r15d
0x1400272bb  xor     r15d, r15d
0x1400272be  jmp     short loc_1400272FA
0x1400272c0  xor     r15d, r15d
0x1400272c3  test    r12d, r12d
0x1400272c6  jns     short loc_1400272FA
0x1400272c8  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x1400272cf  test    rax, rax
0x1400272d2  jz      short loc_1400272FA
0x1400272d4  lea     r8, [rsp+1A0h+var_150]
0x1400272d9  lea     rdx, aUsbstor; "USBSTOR"
0x1400272e0  lea     rcx, [rbp+0A0h+var_90]
0x1400272e4  call    _guard_dispatch_icall
0x1400272e9  mov     r12d, eax
0x1400272ec  test    eax, eax
0x1400272ee  js      short loc_1400272FA
0x1400272f0  mov     eax, dword ptr [rsp+1A0h+var_150]
0x1400272f4  mov     [rsi+84h], eax
0x1400272fa  mov     rcx, rsi
0x1400272fd  call    USBSTOR_GlobalSelectiveSuspendSetting
0x140027302  test    r12d, r12d
0x140027305  jns     short loc_14002735B
0x140027307  mov     rax, [rsi+30h]
0x14002730b  mov     edx, 0BDAh
0x140027310  movzx   ecx, word ptr [rax+8]
0x140027314  cmp     cx, dx
0x140027317  jnz     short loc_140027331
0x140027319  mov     ecx, 307h
0x14002731e  cmp     [rax+0Ah], cx
0x140027322  jnz     short loc_14002735B
0x140027324  mov     ecx, 129h
0x140027329  cmp     [rax+0Ch], cx
0x14002732d  jnz     short loc_14002735B
0x14002732f  jmp     short loc_140027353
0x140027331  mov     edx, 45Eh
0x140027336  cmp     cx, dx
0x140027339  jnz     short loc_14002735B
0x14002733b  movzx   ecx, word ptr [rax+0Ah]
0x14002733f  mov     eax, 90Ch
0x140027344  cmp     cx, ax
0x140027347  jz      short loc_140027353
0x140027349  mov     eax, 306h
0x14002734e  cmp     cx, ax
0x140027351  jnz     short loc_14002735B
0x140027353  bts     dword ptr [rsi+84h], 0Bh
0x14002735b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027362  lea     r14, WPP_GLOBAL_Control
0x140027369  mov     edi, 100h
0x14002736e  cmp     rcx, r14
0x140027371  jz      short loc_14002739A
0x140027373  test    [rcx+2Ch], edi
0x140027376  jz      short loc_14002739A
0x140027378  cmp     byte ptr [rcx+29h], 4
0x14002737c  jb      short loc_14002739A
0x14002737e  mov     r9d, [rsi+84h]
0x140027385  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002738c  mov     rcx, [rcx+18h]
0x140027390  mov     edx, 19h
0x140027395  call    WPP_SF_d
0x14002739a  xor     edx, edx; Val
0x14002739c  lea     rcx, [rsp+1A0h+var_140]; void *
0x1400273a1  lea     r8d, [rdx+70h]; Size
0x1400273a5  call    memset
0x1400273aa  mov     r9d, [rsp+1A0h+var_160]
0x1400273af  lea     rax, aMaximumtransfe; "MaximumTransferLength"
0x1400273b6  mov     [rsp+1A0h+var_130], rax
0x1400273bb  lea     r8, aUsbstor04x04x; "usbstor\\%04x%04x"
0x1400273c2  lea     rax, [rsp+1A0h+var_168]
0x1400273c7  mov     [rsp+1A0h+var_138], 120h
0x1400273cf  mov     [rsp+1A0h+var_128], rax
0x1400273d4  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1400273d8  lea     rax, [rsp+1A0h+var_168]
0x1400273dd  mov     [rbp+0A0h+var_120], 4000004h
0x1400273e4  mov     [rbp+0A0h+var_118], rax
0x1400273e8  mov     edx, 20h ; ' '; cchDest
0x1400273ed  mov     eax, [rsp+1A0h+var_164]
0x1400273f1  mov     dword ptr [rsp+1A0h+var_180], eax
0x1400273f5  mov     [rbp+0A0h+var_110], 4
0x1400273fc  call    RtlStringCchPrintfW
0x140027401  mov     ebx, r15d
0x140027404  cmp     ebx, 5
0x140027407  jnb     short loc_14002747A
0x140027409  test    r13d, r13d
0x14002740c  jz      short loc_14002747A
0x14002740e  xor     r9d, r9d
0x140027411  mov     [rsp+1A0h+var_180], r15
0x140027416  lea     r8, [rsp+1A0h+var_140]
0x14002741b  lea     rdx, [rbp+0A0h+pszDest]
0x14002741f  lea     ecx, [r9+2]
0x140027423  call    cs:__imp_RtlQueryRegistryValuesEx
0x14002742a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
