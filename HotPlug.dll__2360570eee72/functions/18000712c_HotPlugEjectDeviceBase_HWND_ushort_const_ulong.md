# HotPlugEjectDeviceBase(HWND__ *,ushort const *,ulong)

- ea: `0x18000712c`
- end: `0x1800073a8`
- name: `?HotPlugEjectDeviceBase@@YAKPEAUHWND__@@PEBGK@Z`
- size: `636`
- prototype: `unsigned int __fastcall(HWND hWnd, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180007010`
- `0x1800073b0`
- `0x180007520`
- `0x180007c00`

## callees

- `0x180002d70`
- `0x180005234`
- `0x180005610`
- `0x180005b2c`
- `0x180006eac`
- `0x18000712c`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800071d9`
- `KERNEL32!LocalAlloc` at `0x1800071d9`
- `CFGMGR32!CM_Request_Device_Eject_ExW` at `0x1800071bf`
- `CFGMGR32!CM_Request_Device_Eject_ExW` at `0x1800071bf`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x180007192`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x180007192`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x180007228`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18000727c`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x180007228`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18000727c`
- `SETUPAPI!pSetupGuidFromString` at `0x180007295`
- `SETUPAPI!pSetupGuidFromString` at `0x180007295`

## pseudocode

```c
__int64 __fastcall HotPlugEjectDeviceBase(HWND hWnd, WCHAR *a2)
{
  const unsigned __int16 *v3; // rsi
  CONFIGRET DevNode_Registry_PropertyW; // ebx
  CONFIGRET v5; // eax
  char *v6; // rax
  char *v7; // rdi
  __int64 v8; // rcx
  _WORD *v9; // rax
  __int64 v10; // rdx
  _WORD *v11; // rcx
  enum _PNP_VETO_TYPE v12; // r8d
  WCHAR *v13; // r9
  DEVNODE pdnDevInst; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulLength; // [rsp+34h] [rbp-CCh] BYREF
  int Buffer; // [rsp+38h] [rbp-C8h] BYREF
  _PNP_VETO_TYPE pVetoType; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  GUID v21; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[76]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v23; // [rsp+BCh] [rbp-44h]
  WCHAR pszVetoName[264]; // [rsp+C0h] [rbp-40h] BYREF

  pdnDevInst = 0;
  pVetoType = PNP_VetoTypeUnknown;
  v3 = a2;
  Buffer = 0;
  pulLength = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  DevNode_Registry_PropertyW = CM_Locate_DevNodeW(&pdnDevInst, a2, 1u);
  if ( !DevNode_Registry_PropertyW )
  {
    v5 = CM_Request_Device_Eject_ExW(pdnDevInst, &pVetoType, pszVetoName, 0x104u, 0, 0);
    DevNode_Registry_PropertyW = v5;
    if ( v5 )
    {
      if ( v5 == 23 )
      {
        v12 = pVetoType;
        v13 = pszVetoName;
      }
      else
      {
        v13 = 0;
        v12 = PNP_VetoTypeUnknown;
      }
      HandleRemovalVeto(hWnd, v3, v12, v13);
    }
    else
    {
      v6 = (char *)LocalAlloc(0x40u, 0x1C8u);
      v7 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, 0x1C8u);
        Buffer = 0;
        pulLength = 4;
        DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 0x10u, 0, &Buffer, &pulLength, 0);
        if ( DevNode_Registry_PropertyW || (DWORD1(v20) = 1, (Buffer & 8) == 0) )
          DWORD1(v20) = 0;
        pulLength = 78;
        v21 = GUID_NULL;
        if ( !CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 9u, 0, v22, &pulLength, 0) )
        {
          v23 = 0;
          if ( (unsigned int)pSetupGuidFromString(v22, &v21) )
            v21 = GUID_NULL;
        }
        v8 = 2147483646;
        v9 = v7 + 16;
        v10 = 201;
        do
        {
          if ( !v8 )
            break;
          if ( !*v3 )
            break;
          *v9++ = *v3++;
          --v8;
          --v10;
        }
        while ( v10 );
        v11 = v9 - 1;
        if ( v10 )
          v11 = v9;
        *v11 = 0;
        *((_QWORD *)v7 + 53) = BuildFriendlyName(pdnDevInst);
        *((_DWORD *)v7 + 108) = Buffer;
        *(GUID *)(v7 + 436) = v21;
        LODWORD(v20) = 1;
        *(_QWORD *)v7 = &v19;
        *((_QWORD *)v7 + 1) = &v19;
        *(_QWORD *)&v19 = v7;
        *((_QWORD *)&v19 + 1) = v7;
        if ( !*((_QWORD *)&v20 + 1) )
          *((_QWORD *)&v20 + 1) = CreateDeviceImageList();
        HotPlugSafeRemovalNotificationBase((struct DEVICE_COLLECTION *)&v19);
        DeviceCollectionDestroy((struct DEVICE_COLLECTION *)&v19);
      }
      else
      {
        return 2;
      }
    }
  }
  return DevNode_Registry_PropertyW;
}

```

## disassembly

```asm
0x18000712c  mov     [rsp-8+arg_10], rbx
0x180007131  mov     [rsp-8+arg_18], rsi
0x180007136  push    rbp
0x180007137  push    rdi
0x180007138  push    r14
0x18000713a  lea     rbp, [rsp-1E0h]
0x180007142  sub     rsp, 2E0h
0x180007149  mov     rax, cs:__security_cookie
0x180007150  xor     rax, rsp
0x180007153  mov     [rbp+1F0h+var_20], rax
0x18000715a  xor     r14d, r14d
0x18000715d  xorps   xmm0, xmm0
0x180007160  mov     rdi, rcx
0x180007163  mov     [rsp+2F0h+pdnDevInst], r14d
0x180007168  lea     rcx, [rsp+2F0h+pdnDevInst]; pdnDevInst
0x18000716d  mov     [rsp+2F0h+pVetoType], r14d
0x180007172  mov     rsi, rdx
0x180007175  mov     [rsp+2F0h+Buffer], r14d
0x18000717a  lea     r8d, [r14+1]; ulFlags
0x18000717e  mov     [rsp+2F0h+pulLength], r14d
0x180007183  movups  [rsp+2F0h+var_2B0], xmm0
0x180007188  movups  [rsp+2F0h+var_2A0], xmm0
0x18000718d  movups  [rsp+2F0h+var_290], xmm0
0x180007192  call    cs:__imp_CM_Locate_DevNodeW
0x180007198  mov     ebx, eax
0x18000719a  test    eax, eax
0x18000719c  jnz     loc_18000737F
0x1800071a2  mov     ecx, [rsp+2F0h+pdnDevInst]; dnDevInst
0x1800071a6  lea     r8, [rbp+1F0h+pszVetoName]; pszVetoName
0x1800071aa  mov     [rsp+2F0h+hMachine], r14; hMachine
0x1800071af  lea     rdx, [rsp+2F0h+pVetoType]; pVetoType
0x1800071b4  mov     r9d, 104h; ulNameLength
0x1800071ba  mov     [rsp+2F0h+ulFlags], r14d; ulFlags
0x1800071bf  call    cs:__imp_CM_Request_Device_Eject_ExW
0x1800071c5  mov     ebx, eax
0x1800071c7  test    eax, eax
0x1800071c9  jnz     loc_18000735E
0x1800071cf  mov     ebx, 1C8h
0x1800071d4  lea     ecx, [rax+40h]; uFlags
0x1800071d7  mov     edx, ebx; uBytes
0x1800071d9  call    cs:__imp_LocalAlloc
0x1800071df  mov     rdi, rax
0x1800071e2  test    rax, rax
0x1800071e5  jnz     short loc_1800071EF
0x1800071e7  lea     ebx, [rax+2]
0x1800071ea  jmp     loc_18000737F
0x1800071ef  mov     r8, rbx; Size
0x1800071f2  xor     edx, edx; Val
0x1800071f4  mov     rcx, rdi; void *
0x1800071f7  call    memset_0
0x1800071fc  mov     ecx, [rsp+2F0h+pdnDevInst]; dnDevInst
0x180007200  lea     rax, [rsp+2F0h+pulLength]
0x180007205  xor     r8d, r8d; pulRegDataType
0x180007208  mov     dword ptr [rsp+2F0h+hMachine], r14d; ulFlags
0x18000720d  lea     r9, [rsp+2F0h+Buffer]; Buffer
0x180007212  mov     [rsp+2F0h+Buffer], r14d
0x180007217  mov     [rsp+2F0h+pulLength], 4
0x18000721f  mov     qword ptr [rsp+2F0h+ulFlags], rax; pulLength
0x180007224  lea     edx, [r8+10h]; ulProperty
0x180007228  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x18000722e  mov     ebx, eax
0x180007230  test    eax, eax
0x180007232  jnz     short loc_180007243
0x180007234  test    byte ptr [rsp+2F0h+Buffer], 8
0x180007239  mov     dword ptr [rsp+2F0h+var_2A0+4], 1
0x180007241  jnz     short loc_180007248
0x180007243  mov     dword ptr [rsp+2F0h+var_2A0+4], r14d
0x180007248  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000724f  mov     ecx, [rsp+2F0h+pdnDevInst]; dnDevInst
0x180007253  lea     rax, [rsp+2F0h+pulLength]
0x180007258  xor     r8d, r8d; pulRegDataType
0x18000725b  mov     dword ptr [rsp+2F0h+hMachine], r14d; ulFlags
0x180007260  lea     r9, [rsp+2F0h+var_280]; Buffer
0x180007265  mov     [rsp+2F0h+pulLength], 4Eh ; 'N'
0x18000726d  movdqu  [rsp+2F0h+var_290], xmm0
0x180007273  mov     qword ptr [rsp+2F0h+ulFlags], rax; pulLength
0x180007278  lea     edx, [r8+9]; ulProperty
0x18000727c  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180007282  test    eax, eax
0x180007284  jnz     short loc_1800072AC
0x180007286  lea     rdx, [rsp+2F0h+var_290]
0x18000728b  mov     [rbp+1F0h+var_234], r14w
0x180007290  lea     rcx, [rsp+2F0h+var_280]
0x180007295  call    cs:__imp_pSetupGuidFromString
0x18000729b  test    eax, eax
0x18000729d  jz      short loc_1800072AC
0x18000729f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800072a6  movdqu  [rsp+2F0h+var_290], xmm0
0x1800072ac  mov     ecx, 7FFFFFFEh
0x1800072b1  lea     rax, [rdi+10h]
0x1800072b5  mov     edx, 0C9h
0x1800072ba  test    rcx, rcx
0x1800072bd  jz      short loc_1800072DE
0x1800072bf  movzx   r8d, word ptr [rsi]
0x1800072c3  test    r8w, r8w
0x1800072c7  jz      short loc_1800072DE
0x1800072c9  mov     [rax], r8w
0x1800072cd  add     rsi, 2
0x1800072d1  add     rax, 2
0x1800072d5  dec     rcx
0x1800072d8  sub     rdx, 1
0x1800072dc  jnz     short loc_1800072BA
0x1800072de  test    rdx, rdx
0x1800072e1  lea     rcx, [rax-2]
0x1800072e5  cmovnz  rcx, rax
0x1800072e9  mov     [rcx], r14w
0x1800072ed  mov     ecx, [rsp+2F0h+pdnDevInst]; dnDevInst
0x1800072f1  call    ?BuildFriendlyName@@YAPEAGK@Z; BuildFriendlyName(ulong)
0x1800072f6  mov     [rdi+1A8h], rax
0x1800072fd  mov     eax, [rsp+2F0h+Buffer]
0x180007301  mov     [rdi+1B0h], eax
0x180007307  lea     rax, [rsp+2F0h+var_2B0]
0x18000730c  movups  xmm0, [rsp+2F0h+var_290]
0x180007311  movdqu  xmmword ptr [rdi+1B4h], xmm0
0x180007319  mov     dword ptr [rsp+2F0h+var_2A0], 1
0x180007321  mov     [rdi], rax
0x180007324  lea     rax, [rsp+2F0h+var_2B0]
0x180007329  mov     [rdi+8], rax
0x18000732d  mov     qword ptr [rsp+2F0h+var_2B0], rdi
0x180007332  mov     qword ptr [rsp+2F0h+var_2B0+8], rdi
0x180007337  cmp     qword ptr [rsp+2F0h+var_2A0+8], r14
0x18000733c  jnz     short loc_180007348
0x18000733e  call    ?CreateDeviceImageList@@YAPEAU_IMAGELIST@@XZ; CreateDeviceImageList(void)
0x180007343  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x180007348  lea     rcx, [rsp+2F0h+var_2B0]; lpParam
0x18000734d  call    ?HotPlugSafeRemovalNotificationBase@@YAXPEAUDEVICE_COLLECTION@@@Z; HotPlugSafeRemovalNotificationBase(DEVICE_COLLECTION *)
0x180007352  lea     rcx, [rsp+2F0h+var_2B0]; struct DEVICE_COLLECTION *
0x180007357  call    ?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionDestroy(DEVICE_COLLECTION *)
0x18000735c  jmp     short loc_18000737F
0x18000735e  mov     rdx, rsi; unsigned __int16 *
0x180007361  mov     rcx, rdi; hWnd
0x180007364  cmp     eax, 17h
0x180007367  jnz     short loc_180007374
0x180007369  mov     r8d, [rsp+2F0h+pVetoType]
0x18000736e  lea     r9, [rbp+1F0h+pszVetoName]
0x180007372  jmp     short loc_18000737A
0x180007374  xor     r9d, r9d; unsigned __int16 *
0x180007377  xor     r8d, r8d; enum _PNP_VETO_TYPE
0x18000737a  call    ?HandleRemovalVeto@@YAKPEAUHWND__@@PEBGW4_PNP_VETO_TYPE@@1@Z; HandleRemovalVeto(HWND__ *,ushort const *,_PNP_VETO_TYPE,ushort const *)
0x18000737f  mov     eax, ebx
0x180007381  mov     rcx, [rbp+1F0h+var_20]
0x180007388  xor     rcx, rsp; StackCookie
0x18000738b  call    __security_check_cookie
0x180007390  lea     r11, [rsp+2F0h+var_10]
0x180007398  mov     rbx, [r11+30h]
0x18000739c  mov     rsi, [r11+38h]
0x1800073a0  mov     rsp, r11
0x1800073a3  pop     r14
0x1800073a5  pop     rdi
0x1800073a6  pop     rbp
0x1800073a7  retn
```
