# CSebHelper::_GetWnfStateName(_GUID,_WNF_STATE_NAME *,_GUID *)

- ea: `0x1800656a8`
- end: `0x180065a58`
- name: `?_GetWnfStateName@CSebHelper@@CAJU_GUID@@PEAU_WNF_STATE_NAME@@PEAU2@@Z`
- size: `944`
- prototype: `__int64 __fastcall(struct _GUID *, struct _WNF_STATE_NAME *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065278`

## callees

- `0x180003a60`
- `0x180004912`
- `0x180051420`
- `0x1800656a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800658af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006597a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800658af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006597a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800659f9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800659f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800656f8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180065835`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800656f8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180065835`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18006592f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800659cb`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18006592f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800659cb`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800657ac`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180065872`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800657ac`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180065872`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180065713`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180065713`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x180065733`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x180065733`

## string_xrefs

- `0x180065a03`: `GetNetworkAccountBindingDeviceInterfacePath retured error`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSebHelper::_GetWnfStateName(struct _GUID *a1, struct _WNF_STATE_NAME *a2, struct _GUID *a3)
{
  int v5; // ebx
  int NetworkAccountIdBoundToInterfaceId; // eax
  int NetworkAccountBindingDeviceInterfacePath; // eax
  int ObjectProperties; // eax
  GUID *v9; // rcx
  GUID v10; // xmm0
  int v11; // eax
  struct _WNF_STATE_NAME *v12; // rax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPKEY v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+6Ch] [rbp-94h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+8Ch] [rbp-74h]
  __int64 v24; // [rsp+90h] [rbp-70h]
  GUID rguid; // [rsp+98h] [rbp-68h] BYREF
  OLECHAR v26[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[40]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR v28[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v29[528]; // [rsp+1A0h] [rbp+A0h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = -2147024809;
  if ( StringFromGUID2(a1, sz, 40) )
  {
    NetworkAccountIdBoundToInterfaceId = GetNetworkAccountIdBoundToInterfaceId(sz, 40, v26);
    v5 = NetworkAccountIdBoundToInterfaceId;
    if ( NetworkAccountIdBoundToInterfaceId < 0 )
    {
      LogSmsRouterError(
        "CSebHelper::_GetWnfStateName",
        0x13Au,
        NetworkAccountIdBoundToInterfaceId,
        "GetNetworkAccountIdBoundToInterfaceId returned");
    }
    else
    {
      NetworkAccountBindingDeviceInterfacePath = GetNetworkAccountBindingDeviceInterfacePath(v26, 260, v29);
      v5 = NetworkAccountBindingDeviceInterfacePath;
      if ( NetworkAccountBindingDeviceInterfacePath < 0 )
      {
        LogSmsRouterError(
          "CSebHelper::_GetWnfStateName",
          0x131u,
          NetworkAccountBindingDeviceInterfacePath,
          "GetNetworkAccountBindingDeviceInterfacePath retured error");
      }
      else
      {
        v18 = DEVPKEY_Device_ContainerId;
        v15 = 0;
        v17 = 0;
        v19 = 0;
        v20 = 0;
        ObjectProperties = DevGetObjectProperties(1, v29, 0, 1, &v18, &v15, &v17);
        v5 = ObjectProperties;
        if ( ObjectProperties < 0 )
        {
          LogSmsRouterError(
            "CSebHelper::_GetWnfStateName",
            0x12Cu,
            ObjectProperties,
            "DevGetObjectProperties DEVPKEY_Device_ContainerId returned error");
        }
        else
        {
          rguid = 0;
          if ( v15 == 1 && *(_DWORD *)(v17 + 32) == 13 )
          {
            v9 = *(GUID **)(v17 + 40);
            if ( v9 )
            {
              v10 = *v9;
              v14 = 0;
              rguid = v10;
              v16 = 0;
              v22 = 108;
              v23 = 0;
              v21 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
              v24 = 0;
              if ( StringFromGUID2(&rguid, v28, 40) )
              {
                v11 = DevGetObjectProperties(2, v28, 0, 1, &v21, &v14, &v16);
                v5 = v11;
                if ( v11 < 0 )
                {
                  LogSmsRouterError(
                    "CSebHelper::_GetWnfStateName",
                    0x110u,
                    v11,
                    "DevGetObjectProperties DEVPKEY_DeviceContainer_DCA_WnfStateName ");
                  v5 = 0;
                  *a2 = (struct _WNF_STATE_NAME)WNF_SEB_MBAE_NOTIFICATION_RECEIVED;
                }
                else
                {
                  if ( v14 == 1 )
                  {
                    if ( *(_DWORD *)(v16 + 32) == 4099 )
                    {
                      v12 = *(struct _WNF_STATE_NAME **)(v16 + 40);
                      if ( v12 )
                      {
                        *a2 = *v12;
                      }
                      else
                      {
                        *a2 = 0;
                        *(_DWORD *)_o__errno() = 22;
                        invalid_parameter_noinfo();
                        v5 = -2147467259;
                        LogSmsRouterError(
                          "CSebHelper::_GetWnfStateName",
                          0xF3u,
                          -2147467259,
                          "memcpy_s pWnfStateName failed");
                      }
                    }
                    else if ( *(_DWORD *)(v16 + 32) )
                    {
                      v5 = -2147024809;
                      LogSmsRouterError(
                        "CSebHelper::_GetWnfStateName",
                        0x106u,
                        -2147024809,
                        "DevGetObjectProperties DEVPKEY_DeviceContainer_DCA_WnfStateName returned invalid parameters");
                    }
                    else
                    {
                      LogSmsRouterError(
                        "CSebHelper::_GetWnfStateName",
                        0xFAu,
                        v11,
                        "DevGetObjectProperties DEVPKEY_DeviceContainer_DCA_WnfStateName returned EMPTY");
                      v5 = 0;
                      *a2 = (struct _WNF_STATE_NAME)WNF_SEB_MBAE_NOTIFICATION_RECEIVED;
                    }
                  }
                  DevFreeObjectProperties(v14, v16);
                }
              }
              else
              {
                v5 = -2147467259;
                LogSmsRouterError("CSebHelper::_GetWnfStateName", 0x119u, -2147467259, "StringFromGUID2 returned error");
              }
            }
            else
            {
              *(_DWORD *)_o__errno() = 22;
              invalid_parameter_noinfo();
              v5 = -2147467259;
              LogSmsRouterError(
                "CSebHelper::_GetWnfStateName",
                0x11Fu,
                -2147467259,
                "memcpy_s Container Id GUID failed");
            }
          }
          else
          {
            v5 = -2147024809;
            LogSmsRouterError(
              "CSebHelper::_GetWnfStateName",
              0x126u,
              -2147024809,
              "DevGetObjectProperties DEVPKEY_Device_ContainerId returned invalid parameters");
          }
          DevFreeObjectProperties(v15, v17);
        }
        if ( v5 >= 0 )
          return (unsigned int)CLSIDFromString(v26, a3);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800656a8  mov     [rsp-8+arg_18], rbx
0x1800656ad  push    rbp
0x1800656ae  push    rsi
0x1800656af  push    r14
0x1800656b1  lea     rbp, [rsp-2C0h]
0x1800656b9  sub     rsp, 3C0h
0x1800656c0  mov     rax, cs:__security_cookie
0x1800656c7  xor     rax, rsp
0x1800656ca  mov     [rbp+2D0h+var_20], rax
0x1800656d1  mov     r14, r8
0x1800656d4  mov     rsi, rdx
0x1800656d7  test    rdx, rdx
0x1800656da  jz      loc_180065A30
0x1800656e0  test    r8, r8
0x1800656e3  jz      loc_180065A30
0x1800656e9  mov     r8d, 28h ; '('; cchMax
0x1800656ef  lea     rdx, [rbp+2D0h+sz]; lpsz
0x1800656f3  mov     ebx, 80070057h
0x1800656f8  call    cs:__imp_StringFromGUID2
0x1800656fe  test    eax, eax
0x180065700  jz      loc_180065A2C
0x180065706  lea     r8, [rbp+2D0h+var_320]
0x18006570a  mov     edx, 28h ; '('
0x18006570f  lea     rcx, [rbp+2D0h+sz]
0x180065713  call    cs:__imp_GetNetworkAccountIdBoundToInterfaceId
0x180065719  mov     ebx, eax
0x18006571b  test    eax, eax
0x18006571d  js      loc_180065A11
0x180065723  lea     r8, [rbp+2D0h+var_230]
0x18006572a  mov     edx, 104h
0x18006572f  lea     rcx, [rbp+2D0h+var_320]
0x180065733  call    cs:__imp_GetNetworkAccountBindingDeviceInterfacePath
0x180065739  mov     ebx, eax
0x18006573b  test    eax, eax
0x18006573d  js      loc_180065A03
0x180065743  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180065749  lea     rdx, [rbp+2D0h+var_230]
0x180065750  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180065757  mov     [rsp+3D0h+var_368], eax
0x18006575b  mov     r9d, 1
0x180065761  lea     rax, [rsp+3D0h+var_380]
0x180065766  mov     [rsp+3D0h+var_38C], 0
0x18006576e  mov     [rsp+3D0h+var_3A0], rax
0x180065773  xor     r8d, r8d
0x180065776  lea     rax, [rsp+3D0h+var_38C]
0x18006577b  mov     [rsp+3D0h+var_380], 0
0x180065784  mov     [rsp+3D0h+var_3A8], rax
0x180065789  mov     ecx, r9d
0x18006578c  lea     rax, [rsp+3D0h+var_378]
0x180065791  mov     [rsp+3D0h+var_364], 0
0x180065799  mov     [rsp+3D0h+var_3B0], rax
0x18006579e  movups  [rsp+3D0h+var_378], xmm0
0x1800657a3  mov     [rsp+3D0h+var_360], 0
0x1800657ac  call    cs:__imp_DevGetObjectProperties
0x1800657b2  mov     ebx, eax
0x1800657b4  test    eax, eax
0x1800657b6  js      loc_1800659D3
0x1800657bc  cmp     [rsp+3D0h+var_38C], 1
0x1800657c1  xorps   xmm0, xmm0
0x1800657c4  movups  xmmword ptr [rbp+2D0h+rguid.Data1], xmm0
0x1800657c8  jnz     loc_1800659A2
0x1800657ce  mov     rax, [rsp+3D0h+var_380]
0x1800657d3  cmp     dword ptr [rax+20h], 0Dh
0x1800657d7  jnz     loc_1800659A2
0x1800657dd  mov     rcx, [rax+28h]
0x1800657e1  test    rcx, rcx
0x1800657e4  jz      loc_18006597A
0x1800657ea  movups  xmm0, xmmword ptr [rcx]
0x1800657ed  mov     eax, cs:dword_18007C310
0x1800657f3  lea     rdx, [rbp+2D0h+var_280]; lpsz
0x1800657f7  mov     r8d, 28h ; '('; cchMax
0x1800657fd  mov     [rsp+3D0h+var_390], 0
0x180065805  movdqu  xmmword ptr [rbp+2D0h+rguid.Data1], xmm0
0x18006580a  lea     rcx, [rbp+2D0h+rguid]; rguid
0x18006580e  mov     [rsp+3D0h+var_388], 0
0x180065817  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x18006581e  mov     [rbp+2D0h+var_348], eax
0x180065821  mov     [rbp+2D0h+var_344], 0
0x180065828  movups  [rsp+3D0h+var_358], xmm0
0x18006582d  mov     [rbp+2D0h+var_340], 0
0x180065835  call    cs:__imp_StringFromGUID2
0x18006583b  test    eax, eax
0x18006583d  jz      loc_180065963
0x180065843  lea     rax, [rsp+3D0h+var_388]
0x180065848  mov     r9d, 1
0x18006584e  mov     [rsp+3D0h+var_3A0], rax
0x180065853  lea     rdx, [rbp+2D0h+var_280]
0x180065857  lea     rax, [rsp+3D0h+var_390]
0x18006585c  xor     r8d, r8d
0x18006585f  mov     [rsp+3D0h+var_3A8], rax
0x180065864  lea     rax, [rsp+3D0h+var_358]
0x180065869  lea     ecx, [r9+1]
0x18006586d  mov     [rsp+3D0h+var_3B0], rax
0x180065872  call    cs:__imp_DevGetObjectProperties
0x180065878  mov     ebx, eax
0x18006587a  test    eax, eax
0x18006587c  js      loc_18006593A
0x180065882  cmp     [rsp+3D0h+var_390], 1
0x180065887  jnz     loc_180065926
0x18006588d  mov     rax, [rsp+3D0h+var_388]
0x180065892  cmp     dword ptr [rax+20h], 1003h
0x180065899  jnz     short loc_1800658D7
0x18006589b  mov     rax, [rax+28h]
0x18006589f  test    rax, rax
0x1800658a2  jz      short loc_1800658AC
0x1800658a4  mov     rax, [rax]
0x1800658a7  mov     [rsi], rax
0x1800658aa  jmp     short loc_180065926
0x1800658ac  mov     [rsi], rax
0x1800658af  call    cs:__imp__o__errno
0x1800658b5  mov     dword ptr [rax], 16h
0x1800658bb  call    _invalid_parameter_noinfo
0x1800658c0  mov     r8d, 80004005h
0x1800658c6  lea     r9, aMemcpySPwnfsta; "memcpy_s pWnfStateName failed"
0x1800658cd  mov     ebx, r8d
0x1800658d0  mov     edx, 0F3h
0x1800658d5  jmp     short loc_18006591A
0x1800658d7  cmp     dword ptr [rax+20h], 0
0x1800658db  jnz     short loc_180065906
0x1800658dd  lea     r9, aDevgetobjectpr_1; "DevGetObjectProperties DEVPKEY_DeviceCo"...
0x1800658e4  mov     r8d, ebx; int
0x1800658e7  mov     edx, 0FAh; unsigned int
0x1800658ec  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x1800658f3  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800658f8  mov     rax, cs:WNF_SEB_MBAE_NOTIFICATION_RECEIVED
0x1800658ff  xor     ebx, ebx
0x180065901  mov     [rsi], rax
0x180065904  jmp     short loc_180065926
0x180065906  mov     ebx, 80070057h
0x18006590b  lea     r9, aDevgetobjectpr_3; "DevGetObjectProperties DEVPKEY_DeviceCo"...
0x180065912  mov     r8d, ebx; int
0x180065915  mov     edx, 106h; unsigned int
0x18006591a  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x180065921  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180065926  mov     rdx, [rsp+3D0h+var_388]
0x18006592b  mov     ecx, [rsp+3D0h+var_390]
0x18006592f  call    cs:__imp_DevFreeObjectProperties
0x180065935  jmp     loc_1800659C2
0x18006593a  lea     r9, aDevgetobjectpr_2; "DevGetObjectProperties DEVPKEY_DeviceCo"...
0x180065941  mov     r8d, ebx; int
0x180065944  mov     edx, 110h; unsigned int
0x180065949  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x180065950  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180065955  mov     rax, cs:WNF_SEB_MBAE_NOTIFICATION_RECEIVED
0x18006595c  xor     ebx, ebx
0x18006595e  mov     [rsi], rax
0x180065961  jmp     short loc_1800659C2
0x180065963  mov     r8d, 80004005h
0x180065969  lea     r9, aStringfromguid; "StringFromGUID2 returned error"
0x180065970  mov     ebx, r8d
0x180065973  mov     edx, 119h
0x180065978  jmp     short loc_1800659B6
0x18006597a  call    cs:__imp__o__errno
0x180065980  mov     dword ptr [rax], 16h
0x180065986  call    _invalid_parameter_noinfo
0x18006598b  mov     r8d, 80004005h
0x180065991  lea     r9, aMemcpySContain; "memcpy_s Container Id GUID failed"
0x180065998  mov     ebx, r8d
0x18006599b  mov     edx, 11Fh
0x1800659a0  jmp     short loc_1800659B6
0x1800659a2  mov     ebx, 80070057h
0x1800659a7  lea     r9, aDevgetobjectpr_0; "DevGetObjectProperties DEVPKEY_Device_C"...
0x1800659ae  mov     r8d, ebx; int
0x1800659b1  mov     edx, 126h; unsigned int
0x1800659b6  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x1800659bd  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800659c2  mov     rdx, [rsp+3D0h+var_380]
0x1800659c7  mov     ecx, [rsp+3D0h+var_38C]
0x1800659cb  call    cs:__imp_DevFreeObjectProperties
0x1800659d1  jmp     short loc_1800659EE
0x1800659d3  lea     r9, aDevgetobjectpr_4; "DevGetObjectProperties DEVPKEY_Device_C"...
0x1800659da  mov     r8d, eax; int
0x1800659dd  mov     edx, 12Ch; unsigned int
0x1800659e2  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x1800659e9  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800659ee  test    ebx, ebx
0x1800659f0  js      short loc_180065A2C
0x1800659f2  mov     rdx, r14; pclsid
0x1800659f5  lea     rcx, [rbp+2D0h+var_320]; lpsz
0x1800659f9  call    cs:__imp_CLSIDFromString
0x1800659ff  mov     ebx, eax
0x180065a01  jmp     short loc_180065A2C
0x180065a03  lea     r9, aGetnetworkacco_1; "GetNetworkAccountBindingDeviceInterface"...
0x180065a0a  mov     edx, 131h
0x180065a0f  jmp     short loc_180065A1D
0x180065a11  lea     r9, aGetnetworkacco_2; "GetNetworkAccountIdBoundToInterfaceId r"...
0x180065a18  mov     edx, 13Ah; unsigned int
0x180065a1d  mov     r8d, eax; int
0x180065a20  lea     rcx, aCsebhelperGetw; "CSebHelper::_GetWnfStateName"
0x180065a27  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180065a2c  mov     eax, ebx
0x180065a2e  jmp     short loc_180065A35
0x180065a30  mov     eax, 80070057h
0x180065a35  mov     rcx, [rbp+2D0h+var_20]
0x180065a3c  xor     rcx, rsp; StackCookie
0x180065a3f  call    __security_check_cookie
0x180065a44  mov     rbx, [rsp+3D0h+arg_18]
0x180065a4c  add     rsp, 3C0h
0x180065a53  pop     r14
0x180065a55  pop     rsi
0x180065a56  pop     rbp
0x180065a57  retn
```
