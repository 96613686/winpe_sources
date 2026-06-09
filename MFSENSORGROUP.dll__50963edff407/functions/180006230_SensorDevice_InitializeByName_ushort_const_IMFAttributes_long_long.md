# SensorDevice::InitializeByName(ushort const *,IMFAttributes *,long,long *)

- ea: `0x180006230`
- end: `0x18000674f`
- name: `?InitializeByName@SensorDevice@@UEAAJPEBGPEAUIMFAttributes@@JPEAJ@Z`
- size: `1311`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, LPCWSTR pszDeviceInterface, struct IMFAttributes *, int, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config`

## callees

- `0x180003ac0`
- `0x180005b90`
- `0x180005fa0`
- `0x180006230`
- `0x180007908`
- `0x18000c8b0`
- `0x18001ce24`
- `0x1800261a8`
- `0x180044f30`
- `0x180045900`
- `0x18004a638`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006724`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006724`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006274`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006274`
- `MFPlat!MFCreateAttributes` at `0x180006375`
- `MFPlat!MFCreateAttributes` at `0x1800063df`
- `MFPlat!MFCreateAttributes` at `0x180006375`
- `MFPlat!MFCreateAttributes` at `0x1800063df`

## pseudocode

```c
__int64 __fastcall SensorDevice::InitializeByName(
        SensorDevice *this,
        LPCWSTR pszDeviceInterface,
        struct IMFAttributes *a3,
        int a4,
        int *a5)
{
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  struct IMFAttributesVtbl *lpVtbl; // rax
  _DWORD *v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  unsigned int *v18; // [rsp+28h] [rbp-D8h]
  BYTE v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v20[4]; // [rsp+44h] [rbp-BCh] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-B0h] BYREF
  struct IMFMediaSource *v23; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v25; // [rsp+68h] [rbp-98h] BYREF
  BYTE PropertyBuffer[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszDeviceInterfacea[264]; // [rsp+80h] [rbp-80h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v23 = 0;
  v24 = 0;
  ppMFAttributes = 0;
  *(_OWORD *)PropertyBuffer = 0;
  v19[0] = 0;
  v22 = 0;
  memset_0(pszDeviceInterfacea, 0, 0x208u);
  if ( !pszDeviceInterface )
  {
    v9 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 25;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v9);
      goto LABEL_50;
    }
    goto LABEL_58;
  }
  if ( *((_QWORD *)this + 10) )
  {
    v9 = -1072871856;
    if ( g_wppLevels )
    {
      v10 = 26;
      goto LABEL_4;
    }
LABEL_58:
    if ( !byte_18008D62D )
      goto LABEL_63;
    v16 = 38;
    goto LABEL_62;
  }
  v11 = FSGetUniqueSymbolicName(pszDeviceInterface, pszDeviceInterfacea, 0x104u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_50;
    v12 = 27;
LABEL_49:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v11);
    goto LABEL_50;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qSSqd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (__int64)pszDeviceInterface,
      (__int64)pszDeviceInterfacea,
      (char)a3,
      a4);
  if ( a3 )
  {
    lpVtbl = a3->lpVtbl;
    *(_DWORD *)v20 = 0;
    v11 = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned __int8 *))lpVtbl->GetCount)(a3, v20);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v12 = 30;
      goto LABEL_49;
    }
    v11 = MFCreateAttributes(&ppMFAttributes, *(_DWORD *)v20 + 1);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v12 = 31;
      goto LABEL_49;
    }
    v11 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a3->lpVtbl->CopyAllItems)(
            a3,
            ppMFAttributes);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v12 = 32;
      goto LABEL_49;
    }
  }
  else
  {
    v11 = MFCreateAttributes(&ppMFAttributes, 1u);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v12 = 29;
      goto LABEL_49;
    }
  }
  v14 = (_DWORD *)((char *)this + 208);
  *(_DWORD *)v20 = 0;
  if ( this == (SensorDevice *)-208LL )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
        0,
        -2147467261);
    *v14 = 0;
  }
  else
  {
    *v14 = 0;
    if ( (int)FSGetDeviceInterfaceRegistryEntry2(pszDeviceInterfacea, L"FSSensorOrientation", v20, 4u, &v25, v18) >= 0
      && (!*(_DWORD *)v20 || *(_DWORD *)v20 == 90 || *(_DWORD *)v20 == 180 || *(_DWORD *)v20 == 270) )
    {
      *v14 = *(_DWORD *)v20;
    }
  }
  if ( (int)FSGetDeviceNodeProperty(
              pszDeviceInterfacea,
              (DEVPROPKEY *)&DEVPKEY_Device_ContainerId,
              PropertyBuffer,
              0x10u,
              &v22) >= 0 )
    ((void (__fastcall *)(IMFAttributes *, __int64 *, BYTE *))ppMFAttributes->lpVtbl->SetGUID)(
      ppMFAttributes,
      MF_SENSORDEVICE_CONTAINER_ID,
      PropertyBuffer);
  if ( (int)FSGetDeviceNodeProperty(
              pszDeviceInterfacea,
              (DEVPROPKEY *)&DEVPKEY_Device_InLocalMachineContainer,
              v19,
              1u,
              &v22) >= 0 )
    ((void (__fastcall *)(IMFAttributes *, __int64 *, bool))ppMFAttributes->lpVtbl->SetUINT32)(
      ppMFAttributes,
      MF_SENSORDEVICE_IN_LOCALMACHINE_CONTAINER,
      v19[0] == 0xFF);
  v11 = SensorDevice::GatherRSMT(this, pszDeviceInterfacea, ppMFAttributes, &v23);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_50;
    v12 = 33;
    goto LABEL_49;
  }
  v11 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, struct IUnknown **))v23->lpVtbl->QueryInterface)(
          v23,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v24);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_50;
    v12 = 34;
    goto LABEL_49;
  }
  v11 = SensorDevice::InternalInitialize(this, v24, pszDeviceInterfacea, ppMFAttributes, a4, a5);
  v9 = v11;
  if ( v11 < 0 && g_wppLevels )
  {
    v12 = 35;
    goto LABEL_49;
  }
LABEL_50:
  if ( v23 )
  {
    v15 = ((__int64 (__fastcall *)(struct IMFMediaSource *))v23->lpVtbl->Shutdown)(v23);
    if ( v15 < 0 )
    {
      if ( pszDeviceInterfacea[0] )
      {
        if ( byte_18008D62D )
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            37,
            (unsigned int)&WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            (_DWORD)this,
            v15,
            (__int64)pszDeviceInterfacea);
      }
      else if ( byte_18008D62D )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 36, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v15);
      }
    }
  }
  if ( v9 < 0 )
    goto LABEL_58;
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_63;
  v16 = 39;
LABEL_62:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v9);
LABEL_63:
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  if ( v24 )
    ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
  if ( v23 )
    ((void (__fastcall *)(struct IMFMediaSource *))v23->lpVtbl->Release)(v23);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006230  push    rbp
0x180006232  push    rbx
0x180006233  push    rsi
0x180006234  push    rdi
0x180006235  push    r12
0x180006237  push    r13
0x180006239  push    r14
0x18000623b  push    r15
0x18000623d  lea     rbp, [rsp-1A8h]
0x180006245  sub     rsp, 2A8h
0x18000624c  mov     rax, cs:__security_cookie
0x180006253  xor     rax, rsp
0x180006256  mov     [rbp+1E0h+var_50], rax
0x18000625d  mov     r12, [rbp+1E0h+arg_20]
0x180006264  mov     rsi, rcx
0x180006267  add     rcx, 20h ; ' '; lpCriticalSection
0x18000626b  mov     r15d, r9d
0x18000626e  mov     r14, r8
0x180006271  mov     rdi, rdx
0x180006274  call    cs:__imp_EnterCriticalSection
0x18000627a  xor     ebx, ebx
0x18000627c  lea     rcx, [rbp+1E0h+pszDeviceInterface]; void *
0x180006280  xorps   xmm0, xmm0
0x180006283  mov     [rsp+2E0h+var_288], rbx
0x180006288  xor     edx, edx; Val
0x18000628a  mov     [rsp+2E0h+var_280], rbx
0x18000628f  mov     r8d, 208h; Size
0x180006295  mov     [rsp+2E0h+ppMFAttributes], rbx
0x18000629a  movups  xmmword ptr [rsp+2E0h+PropertyBuffer], xmm0
0x18000629f  mov     [rsp+2E0h+var_2A0], bl
0x1800062a3  mov     [rsp+2E0h+var_290], ebx
0x1800062a7  call    memset_0
0x1800062ac  test    rdi, rdi
0x1800062af  jnz     short loc_1800062D4
0x1800062b1  mov     ebx, 80070057h
0x1800062b6  mov     edi, 1
0x1800062bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800062c2  jb      loc_18000669F
0x1800062c8  lea     edx, [rdi+18h]
0x1800062cb  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800062cf  jmp     loc_1800065F5
0x1800062d4  cmp     [rsi+50h], rbx
0x1800062d8  jz      short loc_1800062F6
0x1800062da  mov     ebx, 0C00D4650h
0x1800062df  mov     edi, 1
0x1800062e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800062eb  jb      loc_18000669F
0x1800062f1  lea     edx, [rdi+19h]
0x1800062f4  jmp     short loc_1800062CB
0x1800062f6  xor     r9d, r9d; unsigned int *
0x1800062f9  lea     rdx, [rbp+1E0h+pszDeviceInterface]; unsigned __int16 *
0x1800062fd  mov     r8d, 104h; unsigned int
0x180006303  mov     rcx, rdi; pszDeviceInterface
0x180006306  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x18000630b  xor     ecx, ecx
0x18000630d  mov     ebx, eax
0x18000630f  test    eax, eax
0x180006311  jns     short loc_18000632B
0x180006313  lea     edi, [rcx+1]
0x180006316  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18000631d  jb      loc_18000660F
0x180006323  lea     edx, [rcx+1Bh]
0x180006326  jmp     loc_1800065F1
0x18000632b  cmp     cs:byte_18008D62D, 8
0x180006332  jb      short loc_180006364
0x180006334  mov     rcx, cs:WPP_GLOBAL_Control
0x18000633b  lea     rax, [rbp+1E0h+pszDeviceInterface]
0x18000633f  mov     dword ptr [rsp+2E0h+var_2A8], r15d; char
0x180006344  mov     r9, rsi
0x180006347  mov     qword ptr [rsp+2E0h+var_2B0], r14; char
0x18000634c  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x180006351  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180006358  mov     [rsp+2E0h+var_2C0], rdi; __int64
0x18000635d  call    WPP_SF_qSSqd
0x180006362  xor     ecx, ecx
0x180006364  mov     edi, 1
0x180006369  test    r14, r14
0x18000636c  jnz     short loc_18000639C
0x18000636e  mov     edx, edi; cInitialSize
0x180006370  lea     rcx, [rsp+2E0h+ppMFAttributes]; ppMFAttributes
0x180006375  call    cs:__imp_MFCreateAttributes
0x18000637b  xor     ecx, ecx
0x18000637d  mov     ebx, eax
0x18000637f  test    eax, eax
0x180006381  jns     loc_180006436
0x180006387  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18000638e  jb      loc_18000660F
0x180006394  lea     edx, [rdi+1Ch]
0x180006397  jmp     loc_1800065F1
0x18000639c  mov     rax, [r14]
0x18000639f  lea     rdx, [rsp+2E0h+var_29C]
0x1800063a4  mov     dword ptr [rsp+2E0h+var_29C], ecx
0x1800063a8  mov     rcx, r14
0x1800063ab  mov     rax, [rax+0F0h]
0x1800063b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b7  mov     ebx, eax
0x1800063b9  test    eax, eax
0x1800063bb  jns     short loc_1800063D4
0x1800063bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800063c4  jb      loc_18000660F
0x1800063ca  mov     edx, 1Eh
0x1800063cf  jmp     loc_1800065F1
0x1800063d4  mov     edx, dword ptr [rsp+2E0h+var_29C]
0x1800063d8  lea     rcx, [rsp+2E0h+ppMFAttributes]; ppMFAttributes
0x1800063dd  inc     edx; cInitialSize
0x1800063df  call    cs:__imp_MFCreateAttributes
0x1800063e5  mov     ebx, eax
0x1800063e7  test    eax, eax
0x1800063e9  jns     short loc_180006402
0x1800063eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800063f2  jb      loc_18000660F
0x1800063f8  mov     edx, 1Fh
0x1800063fd  jmp     loc_1800065F1
0x180006402  mov     rax, [r14]
0x180006405  mov     rcx, r14
0x180006408  mov     rdx, [rsp+2E0h+ppMFAttributes]
0x18000640d  mov     rax, [rax+100h]
0x180006414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006419  xor     ecx, ecx
0x18000641b  mov     ebx, eax
0x18000641d  test    eax, eax
0x18000641f  jns     short loc_180006436
0x180006421  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180006428  jb      loc_18000660F
0x18000642e  lea     edx, [rcx+20h]
0x180006431  jmp     loc_1800065F1
0x180006436  lea     rbx, [rsi+0D0h]
0x18000643d  mov     dword ptr [rsp+2E0h+var_29C], ecx
0x180006441  test    rbx, rbx
0x180006444  jnz     short loc_18000647A
0x180006446  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18000644d  jb      short loc_180006476
0x18000644f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006456  lea     edx, [rbx+6Eh]
0x180006459  xor     r9d, r9d
0x18000645c  mov     dword ptr [rsp+2E0h+var_2C0], 80004003h
0x180006464  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000646b  mov     rcx, [rcx+10h]
0x18000646f  call    WPP_SF_qD
0x180006474  xor     ecx, ecx
0x180006476  mov     [rbx], ecx
0x180006478  jmp     short loc_1800064C2
0x18000647a  mov     [rbx], ecx
0x18000647c  lea     rax, [rsp+2E0h+var_278]
0x180006481  lea     rcx, [rbp+1E0h+pszDeviceInterface]; unsigned __int16 *
0x180006485  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x18000648a  mov     r9d, 4; unsigned int
0x180006490  lea     r8, [rsp+2E0h+var_29C]; unsigned __int8 *
0x180006495  lea     rdx, aFssensororient; "FSSensorOrientation"
0x18000649c  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x1800064a1  test    eax, eax
0x1800064a3  js      short loc_1800064C2
0x1800064a5  mov     eax, dword ptr [rsp+2E0h+var_29C]
0x1800064a9  test    eax, eax
0x1800064ab  jz      short loc_1800064C0
0x1800064ad  cmp     eax, 5Ah ; 'Z'
0x1800064b0  jz      short loc_1800064C0
0x1800064b2  cmp     eax, 0B4h
0x1800064b7  jz      short loc_1800064C0
0x1800064b9  cmp     eax, 10Eh
0x1800064be  jnz     short loc_1800064C2
0x1800064c0  mov     [rbx], eax
0x1800064c2  lea     rax, [rsp+2E0h+var_290]
0x1800064c7  mov     r9d, 10h; unsigned int
0x1800064cd  lea     r8, [rsp+2E0h+PropertyBuffer]; PropertyBuffer
0x1800064d2  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x1800064d7  lea     rdx, DEVPKEY_Device_ContainerId; PropertyKey
0x1800064de  lea     rcx, [rbp+1E0h+pszDeviceInterface]; pszDeviceInterface
0x1800064e2  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x1800064e7  test    eax, eax
0x1800064e9  js      short loc_18000650B
0x1800064eb  mov     rcx, [rsp+2E0h+ppMFAttributes]
0x1800064f0  lea     r8, [rsp+2E0h+PropertyBuffer]
0x1800064f5  lea     rdx, MF_SENSORDEVICE_CONTAINER_ID
0x1800064fc  mov     rax, [rcx]
0x1800064ff  mov     rax, [rax+0C0h]
0x180006506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650b  lea     rax, [rsp+2E0h+var_290]
0x180006510  mov     r9d, edi; unsigned int
0x180006513  lea     r8, [rsp+2E0h+var_2A0]; PropertyBuffer
0x180006518  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x18000651d  lea     rdx, DEVPKEY_Device_InLocalMachineContainer; PropertyKey
0x180006524  lea     rcx, [rbp+1E0h+pszDeviceInterface]; pszDeviceInterface
0x180006528  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18000652d  test    eax, eax
0x18000652f  js      short loc_18000655B
0x180006531  cmp     [rsp+2E0h+var_2A0], 0FFh
0x180006536  lea     rdx, MF_SENSORDEVICE_IN_LOCALMACHINE_CONTAINER
0x18000653d  mov     rcx, [rsp+2E0h+ppMFAttributes]
0x180006542  mov     rax, [rcx]
0x180006545  mov     rax, [rax+0A8h]
0x18000654c  jnz     short loc_180006553
0x18000654e  mov     r8d, edi
0x180006551  jmp     short loc_180006556
0x180006553  xor     r8d, r8d
0x180006556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655b  mov     r8, [rsp+2E0h+ppMFAttributes]; struct IMFAttributes *
0x180006560  lea     r9, [rsp+2E0h+var_288]; struct IMFMediaSource **
0x180006565  lea     rdx, [rbp+1E0h+pszDeviceInterface]; unsigned __int16 *
0x180006569  mov     rcx, rsi; this
0x18000656c  call    ?GatherRSMT@SensorDevice@@IEAAJPEBGPEAUIMFAttributes@@PEAPEAUIMFMediaSource@@@Z; SensorDevice::GatherRSMT(ushort const *,IMFAttributes *,IMFMediaSource * *)
0x180006571  mov     ebx, eax
0x180006573  test    eax, eax
0x180006575  jns     short loc_18000658B
0x180006577  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18000657e  jb      loc_18000660F
0x180006584  mov     edx, 21h ; '!'
0x180006589  jmp     short loc_1800065F1
0x18000658b  mov     rcx, [rsp+2E0h+var_288]
0x180006590  lea     r8, [rsp+2E0h+var_280]
0x180006595  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000659c  mov     rax, [rcx]
0x18000659f  mov     rax, [rax]
0x1800065a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a7  mov     ebx, eax
0x1800065a9  test    eax, eax
0x1800065ab  jns     short loc_1800065BD
0x1800065ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800065b4  jb      short loc_18000660F
0x1800065b6  mov     edx, 22h ; '"'
0x1800065bb  jmp     short loc_1800065F1
0x1800065bd  mov     r9, [rsp+2E0h+ppMFAttributes]; struct IMFAttributes *
0x1800065c2  lea     r8, [rbp+1E0h+pszDeviceInterface]; unsigned __int16 *
0x1800065c6  mov     rdx, [rsp+2E0h+var_280]; struct IUnknown *
0x1800065cb  mov     rcx, rsi; this
0x1800065ce  mov     [rsp+2E0h+var_2B8], r12; int *
0x1800065d3  mov     dword ptr [rsp+2E0h+var_2C0], r15d; int
0x1800065d8  call    ?InternalInitialize@SensorDevice@@IEAAJPEAUIUnknown@@PEBGPEAUIMFAttributes@@JPEAJ@Z; SensorDevice::InternalInitialize(IUnknown *,ushort const *,IMFAttributes *,long,long *)
0x1800065dd  mov     ebx, eax
0x1800065df  test    eax, eax
0x1800065e1  jns     short loc_18000660F
0x1800065e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800065ea  jb      short loc_18000660F
0x1800065ec  mov     edx, 23h ; '#'
0x1800065f1  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x1800065f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065fc  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180006603  mov     r9, rsi
0x180006606  mov     rcx, [rcx+10h]
0x18000660a  call    WPP_SF_qD
0x18000660f  mov     rcx, [rsp+2E0h+var_288]
0x180006614  xor     r15d, r15d
0x180006617  test    rcx, rcx
0x18000661a  jz      short loc_18000669B
0x18000661c  mov     rax, [rcx]
0x18000661f  mov     rax, [rax+60h]
0x180006623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006628  test    eax, eax
0x18000662a  jns     short loc_18000669B
0x18000662c  cmp     [rbp+1E0h+pszDeviceInterface], r15w
0x180006631  jnz     short loc_180006663
0x180006633  cmp     cs:byte_18008D62D, dil
0x18000663a  jb      short loc_18000669B
0x18000663c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006643  lea     edx, [r15+24h]
0x180006647  mov     r9, rsi
0x18000664a  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x18000664e  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180006655  mov     rcx, [rcx+0D8h]
0x18000665c  call    WPP_SF_qD
0x180006661  jmp     short loc_18000669B
0x180006663  cmp     cs:byte_18008D62D, dil
0x18000666a  jb      short loc_18000669B
0x18000666c  lea     rcx, [rbp+1E0h+pszDeviceInterface]
0x180006670  mov     edx, 25h ; '%'
0x180006675  mov     [rsp+2E0h+var_2B8], rcx
0x18000667a  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180006681  mov     rcx, cs:WPP_GLOBAL_Control
0x180006688  mov     r9, rsi
0x18000668b  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x18000668f  mov     rcx, [rcx+0D8h]
0x180006696  call    WPP_SF_qDS
0x18000669b  test    ebx, ebx
0x18000669d  jns     short loc_1800066AF
0x18000669f  cmp     cs:byte_18008D62D, dil
0x1800066a6  jb      short loc_1800066DE
0x1800066a8  mov     edx, 26h ; '&'
0x1800066ad  jmp     short loc_1800066BD
0x1800066af  cmp     cs:byte_18008D62D, 8
0x1800066b6  jb      short loc_1800066DE
0x1800066b8  mov     edx, 27h ; '''
0x1800066bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c4  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x1800066cb  mov     r9, rsi
0x1800066ce  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800066d2  mov     rcx, [rcx+0D8h]
0x1800066d9  call    WPP_SF_qD
0x1800066de  mov     rcx, [rsp+2E0h+ppMFAttributes]
0x1800066e3  test    rcx, rcx
0x1800066e6  jz      short loc_1800066F4
0x1800066e8  mov     rax, [rcx]
0x1800066eb  mov     rax, [rax+10h]
0x1800066ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f4  mov     rcx, [rsp+2E0h+var_280]
0x1800066f9  test    rcx, rcx
0x1800066fc  jz      short loc_18000670A
0x1800066fe  mov     rax, [rcx]
0x180006701  mov     rax, [rax+10h]
0x180006705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670a  mov     rcx, [rsp+2E0h+var_288]
  ... truncated ...
```
