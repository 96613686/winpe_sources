# STCheckNetworkQualification(ushort const *,NLM_NETWORK_CATEGORY,_GUID,int,int,int,int *,int *)

- ea: `0x180010120`
- end: `0x1800107e9`
- name: `?STCheckNetworkQualification@@YAJPEBGW4NLM_NETWORK_CATEGORY@@U_GUID@@HHHPEAH3@Z`
- size: `1737`
- prototype: `__int64 __fastcall(unsigned __int16 *, enum NLM_NETWORK_CATEGORY, struct _GUID *, int, int, int, int *, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b310`
- `0x18000b520`

## callees

- `0x180002440`
- `0x180002514`
- `0x18000a508`
- `0x18000a644`
- `0x18000a66c`
- `0x18000a778`
- `0x18000aa58`
- `0x18000b6c4`
- `0x18000b798`
- `0x18000e5c0`
- `0x18000e75c`
- `0x18000f650`
- `0x18000f89c`
- `0x180010120`
- `0x180010c28`
- `0x180010d3c`
- `0x180010f14`
- `0x18001380e`
- `0x180013840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800101e5`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800101e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001062a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001062a`

## pseudocode

```c
__int64 __fastcall STCheckNetworkQualification(
        unsigned __int16 *a1,
        enum NLM_NETWORK_CATEGORY a2,
        struct _GUID *a3,
        int a4,
        int a5,
        int a6,
        int *a7,
        int *a8)
{
  int v10; // r12d
  int v11; // edi
  int NetworkSizeFromRegistry; // ebx
  int NetworkQualificationFromRegistry; // eax
  int v14; // edx
  int v15; // r8d
  _QWORD *v16; // rcx
  int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned __int16 *v20; // r9
  __int64 v21; // r8
  unsigned __int16 *v22; // r9
  __int64 v23; // rcx
  int v24; // esi
  BOOL v25; // edi
  unsigned __int16 *v26; // r15
  __int64 *v27; // rdx
  int v28; // ecx
  unsigned int v29; // edx
  int v31; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  NLM_NETWORK_CATEGORY v33; // [rsp+38h] [rbp-C8h]
  int v34; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v36[8]; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v38; // [rsp+58h] [rbp-A8h]
  struct _GUID v39; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v33 = a2;
  v38 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  v10 = 0;
  *(_DWORD *)v36 = 0;
  v34 = 0;
  v11 = 0;
  v31 = 0;
  lpsz = 0;
  memset_0(SubKey, 0, 0x208u);
  v35 = 0;
  *(_DWORD *)Data = 0;
  *a7 = 0;
  if ( a8 )
    *a8 = 0;
  NetworkSizeFromRegistry = StringFromIID(a3, &lpsz);
  if ( NetworkSizeFromRegistry < 0 )
    goto LABEL_108;
  NetworkSizeFromRegistry = StringCchPrintfW(
                              SubKey,
                              0x104u,
                              L"%ws\\%ws\\%ws",
                              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup",
                              L"NetworkSetting",
                              lpsz);
  if ( NetworkSizeFromRegistry >= 0 )
  {
    NetworkQualificationFromRegistry = GetNetworkQualificationFromRegistry(SubKey, &v31, &v34);
    NetworkSizeFromRegistry = NetworkQualificationFromRegistry;
    if ( NetworkQualificationFromRegistry < 0 )
    {
      if ( NetworkQualificationFromRegistry == -2147024894 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, lpsz);
          v16 = WPP_GLOBAL_Control;
        }
        NetworkSizeFromRegistry = 0;
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v31, (__int64)lpsz);
        v16 = WPP_GLOBAL_Control;
      }
      v10 = 1;
    }
    if ( v34 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 )
        WPP_SF_(v16[2], 36, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
      *a7 = 0;
      goto LABEL_63;
    }
    NetworkSizeFromRegistry = IsNetworkCategoryQualified(v33, (int *)v36, &v35);
    if ( NetworkSizeFromRegistry < 0 || !*(_DWORD *)v36 )
    {
LABEL_74:
      v11 = v31;
      goto LABEL_75;
    }
    *(_QWORD *)v36 = 0;
    v17 = 1;
    NetworkSizeFromRegistry = GetNetworkSizeFromRegistry(SubKey, Data, v36);
    if ( NetworkSizeFromRegistry < 0 )
    {
      if ( NetworkSizeFromRegistry == -2147024894 )
        NetworkSizeFromRegistry = 0;
      goto LABEL_37;
    }
    if ( (unsigned int)IsNetworkSizeExpired(*(union _ULARGE_INTEGER *)v36, v33) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v19 = 38;
        goto LABEL_31;
      }
    }
    else
    {
      v17 = 0;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v19 = 37;
LABEL_31:
        WPP_SF_d(v18[2], v19, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
LABEL_37:
        v18 = WPP_GLOBAL_Control;
      }
    }
    if ( g_dwCurrentAutoSetupCount >= g_dwMaxAutoSetupCount )
    {
      v17 = 1;
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
      {
        WPP_SF_d(v18[2], 39, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
    }
    if ( NetworkSizeFromRegistry >= 0 )
    {
      if ( v17 )
      {
        if ( a4 )
        {
          if ( !a5 )
          {
            if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
              WPP_SF_(v18[2], 43, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
            *a8 = 1;
            goto LABEL_63;
          }
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
            WPP_SF_(v18[2], 41, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
          v39 = *a3;
          NetworkSizeFromRegistry = CNetworkHandler::GetNetworkSize(*(&Block + 1), &v39, (unsigned int *)Data);
          if ( NetworkSizeFromRegistry < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
            goto LABEL_63;
          }
        }
        else
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
            WPP_SF_(v18[2], 40, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
          NetworkSizeFromRegistry = CNetworkHandler::CalculateNetworkSize(*(&Block + 1));
          if ( NetworkSizeFromRegistry < 0 )
            goto LABEL_63;
          v39 = *a3;
          NetworkSizeFromRegistry = CNetworkHandler::GetNetworkSize(*(&Block + 1), &v39, (unsigned int *)Data);
          if ( NetworkSizeFromRegistry < 0 )
            goto LABEL_63;
        }
        NetworkSizeFromRegistry = SetNetworkSizeInRegistry(
                                    SubKey,
                                    (HKEY)*(unsigned int *)Data,
                                    *(_DWORD *)Data >= *((_DWORD *)&g_NetworkConfiguration + 4 * v33 + 1),
                                    v20);
        if ( NetworkSizeFromRegistry < 0 )
        {
LABEL_63:
          v11 = v31;
          goto LABEL_75;
        }
        v18 = WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)Data > *((_DWORD *)&g_NetworkConfiguration + 4 * v33 + 1) )
      {
        v35 = 2;
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          WPP_SF_d(v18[2], 45, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
      }
      else
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          WPP_SF_d(v18[2], 44, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
        *a7 = 1;
      }
      goto LABEL_63;
    }
    goto LABEL_74;
  }
LABEL_75:
  CoTaskMemFree(lpsz);
  if ( NetworkSizeFromRegistry >= 0 && a6 && (!a8 || !*a8) && (!v10 || v11 != *a7) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    NetworkSizeFromRegistry = SetNetworkQualificationInRegistry(SubKey, (HKEY)(unsigned int)*a7, v21, v22);
    if ( NetworkSizeFromRegistry >= 0 )
    {
      if ( v10 && v11 && !*a7 )
      {
        v24 = 1;
      }
      else
      {
        v25 = 0;
        v24 = 0;
        if ( !v10 )
        {
          v26 = v38;
LABEL_92:
          if ( *a7 )
          {
            if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) != 0 )
            {
              v27 = NetworkQualified;
LABEL_104:
              McTemplateU0z_EventWriteTransfer(v23, v27, v26);
            }
          }
          else if ( v35 == 1 )
          {
            if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) != 0 )
            {
              v27 = NetworkCategoryDisqualified;
              goto LABEL_104;
            }
          }
          else
          {
            if ( v35 != 2 )
            {
              if ( v35 != 3 || (Microsoft_Windows_NcdAutoSetupEnableBits & 1) == 0 )
                goto LABEL_105;
              v27 = NetworkDiscoveryDisqualified;
              goto LABEL_104;
            }
            if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) != 0 )
            {
              v27 = NetworkSizeDisqualified;
              goto LABEL_104;
            }
          }
LABEL_105:
          v28 = 0;
          v29 = v35;
          if ( *a7 )
            v29 = 0;
          LOBYTE(v28) = *a7 != 0;
          SqmNetworkQualification(v28, v29, *(unsigned int *)Data, v33, v24, v25);
          goto LABEL_108;
        }
      }
      v26 = v38;
      v34 = 0;
      *(_DWORD *)v36 = 0;
      CNetworkHandler::GetNetworkQualificationByName(*(&Block + 1), v38, &v34, (int *)v36);
      v25 = v34 != *(_DWORD *)v36;
      goto LABEL_92;
    }
  }
LABEL_108:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  return (unsigned int)NetworkSizeFromRegistry;
}

```

## disassembly

```asm
0x180010120  mov     [rsp-8+arg_18], rbx
0x180010125  push    rbp
0x180010126  push    rsi
0x180010127  push    rdi
0x180010128  push    r12
0x18001012a  push    r13
0x18001012c  push    r14
0x18001012e  push    r15
0x180010130  lea     rbp, [rsp-190h]
0x180010138  sub     rsp, 290h
0x18001013f  mov     rax, cs:__security_cookie
0x180010146  xor     rax, rsp
0x180010149  mov     [rbp+1C0h+var_40], rax
0x180010150  mov     r14, [rbp+1C0h+arg_30]
0x180010157  mov     r15d, r9d
0x18001015a  mov     r13, [rbp+1C0h+arg_38]
0x180010161  mov     rsi, r8
0x180010164  mov     [rsp+2C0h+var_288], edx
0x180010168  mov     [rsp+2C0h+var_268], rcx
0x18001016d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010174  lea     rax, WPP_GLOBAL_Control
0x18001017b  cmp     rcx, rax
0x18001017e  jz      short loc_18001019B
0x180010180  test    byte ptr [rcx+1Ch], 20h
0x180010184  jz      short loc_18001019B
0x180010186  mov     rcx, [rcx+10h]
0x18001018a  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010191  mov     edx, 21h ; '!'
0x180010196  call    WPP_SF_
0x18001019b  xor     r12d, r12d
0x18001019e  lea     rcx, [rsp+2C0h+SubKey]; void *
0x1800101a3  xor     edx, edx; Val
0x1800101a5  mov     dword ptr [rsp+2C0h+var_278], r12d
0x1800101aa  mov     r8d, 208h; Size
0x1800101b0  mov     [rsp+2C0h+var_284], r12d
0x1800101b5  mov     edi, r12d
0x1800101b8  mov     [rsp+2C0h+var_290], r12d
0x1800101bd  mov     [rsp+2C0h+lpsz], r12
0x1800101c2  call    memset_0
0x1800101c7  mov     [rsp+2C0h+var_280], r12d
0x1800101cc  mov     dword ptr [rsp+2C0h+Data], r12d
0x1800101d1  mov     [r14], r12d
0x1800101d4  test    r13, r13
0x1800101d7  jz      short loc_1800101DD
0x1800101d9  mov     [r13+0], r12d
0x1800101dd  lea     rdx, [rsp+2C0h+lpsz]; lplpsz
0x1800101e2  mov     rcx, rsi; rclsid
0x1800101e5  call    cs:__imp_StringFromIID
0x1800101eb  mov     ebx, eax
0x1800101ed  test    eax, eax
0x1800101ef  js      loc_18001078F
0x1800101f5  mov     rax, [rsp+2C0h+lpsz]
0x1800101fa  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010201  mov     qword ptr [rsp+2C0h+var_298], rax
0x180010206  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x18001020d  lea     rax, aNetworksetting; "NetworkSetting"
0x180010214  mov     edx, 104h; unsigned __int64
0x180010219  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x18001021e  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180010223  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010228  mov     ebx, eax
0x18001022a  test    eax, eax
0x18001022c  js      loc_18001061E
0x180010232  lea     r8, [rsp+2C0h+var_284]; int *
0x180010237  lea     rdx, [rsp+2C0h+var_290]; int *
0x18001023c  lea     rcx, [rsp+2C0h+SubKey]; lpSubKey
0x180010241  call    ?GetNetworkQualificationFromRegistry@@YAJPEBGPEAH1@Z; GetNetworkQualificationFromRegistry(ushort const *,int *,int *)
0x180010246  mov     ebx, eax
0x180010248  test    eax, eax
0x18001024a  js      short loc_18001028C
0x18001024c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010253  lea     rax, WPP_GLOBAL_Control
0x18001025a  cmp     rcx, rax
0x18001025d  jz      short loc_180010284
0x18001025f  test    byte ptr [rcx+1Ch], 8
0x180010263  jz      short loc_180010284
0x180010265  mov     rax, [rsp+2C0h+lpsz]
0x18001026a  mov     r9d, [rsp+2C0h+var_290]
0x18001026f  mov     rcx, [rcx+10h]
0x180010273  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180010278  call    WPP_SF_dS
0x18001027d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010284  mov     r12d, 1
0x18001028a  jmp     short loc_1800102D8
0x18001028c  cmp     eax, 80070002h
0x180010291  jnz     short loc_1800102D1
0x180010293  mov     rcx, cs:WPP_GLOBAL_Control
0x18001029a  lea     rax, WPP_GLOBAL_Control
0x1800102a1  cmp     rcx, rax
0x1800102a4  jz      short loc_1800102CD
0x1800102a6  test    byte ptr [rcx+1Ch], 8
0x1800102aa  jz      short loc_1800102CD
0x1800102ac  mov     r9, [rsp+2C0h+lpsz]
0x1800102b1  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800102b8  mov     rcx, [rcx+10h]
0x1800102bc  mov     edx, 23h ; '#'
0x1800102c1  call    WPP_SF_S
0x1800102c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102cd  mov     ebx, edi
0x1800102cf  jmp     short loc_1800102D8
0x1800102d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102d8  cmp     [rsp+2C0h+var_284], edi
0x1800102dc  jz      short loc_18001030D
0x1800102de  lea     r15, WPP_GLOBAL_Control
0x1800102e5  cmp     rcx, r15
0x1800102e8  jz      short loc_180010305
0x1800102ea  test    byte ptr [rcx+1Ch], 8
0x1800102ee  jz      short loc_180010305
0x1800102f0  mov     rcx, [rcx+10h]
0x1800102f4  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800102fb  mov     edx, 24h ; '$'
0x180010300  call    WPP_SF_
0x180010305  mov     [r14], edi
0x180010308  jmp     loc_180010583
0x18001030d  mov     ecx, [rsp+2C0h+var_288]; enum NLM_NETWORK_CATEGORY
0x180010311  lea     r8, [rsp+2C0h+var_280]; unsigned int *
0x180010316  lea     rdx, [rsp+2C0h+var_278]; int *
0x18001031b  call    ?IsNetworkCategoryQualified@@YAJW4NLM_NETWORK_CATEGORY@@PEAHPEAK@Z; IsNetworkCategoryQualified(NLM_NETWORK_CATEGORY,int *,ulong *)
0x180010320  mov     ebx, eax
0x180010322  test    eax, eax
0x180010324  js      loc_18001061A
0x18001032a  cmp     dword ptr [rsp+2C0h+var_278], edi
0x18001032e  jz      loc_18001061A
0x180010334  lea     r8, [rsp+2C0h+var_278]; LPBYTE
0x180010339  mov     qword ptr [rsp+2C0h+var_278], 0
0x180010342  lea     rdx, [rsp+2C0h+Data]; lpData
0x180010347  mov     edi, 1
0x18001034c  lea     rcx, [rsp+2C0h+SubKey]; lpSubKey
0x180010351  call    ?GetNetworkSizeFromRegistry@@YAJPEBGAEAKPEAT_ULARGE_INTEGER@@@Z; GetNetworkSizeFromRegistry(ushort const *,ulong &,_ULARGE_INTEGER *)
0x180010356  mov     ebx, eax
0x180010358  test    eax, eax
0x18001035a  js      short loc_1800103C3
0x18001035c  mov     edx, [rsp+2C0h+var_288]; enum NLM_NETWORK_CATEGORY
0x180010360  mov     rcx, qword ptr [rsp+2C0h+var_278]; union _ULARGE_INTEGER
0x180010365  call    ?IsNetworkSizeExpired@@YAHT_ULARGE_INTEGER@@W4NLM_NETWORK_CATEGORY@@@Z; IsNetworkSizeExpired(_ULARGE_INTEGER,NLM_NETWORK_CATEGORY)
0x18001036a  test    eax, eax
0x18001036c  jnz     short loc_1800103A3
0x18001036e  xor     edi, edi
0x180010370  mov     rcx, cs:WPP_GLOBAL_Control
0x180010377  lea     rax, WPP_GLOBAL_Control
0x18001037e  cmp     rcx, rax
0x180010381  jz      short loc_1800103DC
0x180010383  test    byte ptr [rcx+1Ch], 8
0x180010387  jz      short loc_1800103DC
0x180010389  lea     edx, [rdi+25h]
0x18001038c  mov     r9d, dword ptr [rsp+2C0h+Data]
0x180010391  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010398  mov     rcx, [rcx+10h]
0x18001039c  call    WPP_SF_d
0x1800103a1  jmp     short loc_1800103CE
0x1800103a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103aa  lea     rax, WPP_GLOBAL_Control
0x1800103b1  cmp     rcx, rax
0x1800103b4  jz      short loc_1800103DC
0x1800103b6  test    byte ptr [rcx+1Ch], 8
0x1800103ba  jz      short loc_1800103DC
0x1800103bc  mov     edx, 26h ; '&'
0x1800103c1  jmp     short loc_18001038C
0x1800103c3  xor     eax, eax
0x1800103c5  cmp     ebx, 80070002h
0x1800103cb  cmovz   ebx, eax
0x1800103ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103d5  lea     rax, WPP_GLOBAL_Control
0x1800103dc  mov     r9d, cs:?g_dwCurrentAutoSetupCount@@3KA; ulong g_dwCurrentAutoSetupCount
0x1800103e3  cmp     r9d, cs:?g_dwMaxAutoSetupCount@@3KA; ulong g_dwMaxAutoSetupCount
0x1800103ea  jb      short loc_180010416
0x1800103ec  mov     edi, 1
0x1800103f1  cmp     rcx, rax
0x1800103f4  jz      short loc_180010416
0x1800103f6  test    byte ptr [rcx+1Ch], 8
0x1800103fa  jz      short loc_180010416
0x1800103fc  mov     rcx, [rcx+10h]
0x180010400  lea     edx, [rdi+26h]
0x180010403  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18001040a  call    WPP_SF_d
0x18001040f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010416  test    ebx, ebx
0x180010418  js      loc_18001061A
0x18001041e  lea     rdx, ?g_NetworkConfiguration@@3PAUNETWORK_CONFIGURATION@@A; NETWORK_CONFIGURATION near * g_NetworkConfiguration
0x180010425  test    edi, edi
0x180010427  jz      loc_18001053D
0x18001042d  test    r15d, r15d
0x180010430  jnz     short loc_18001049A
0x180010432  lea     r15, WPP_GLOBAL_Control
0x180010439  cmp     rcx, r15
0x18001043c  jz      short loc_180010459
0x18001043e  test    byte ptr [rcx+1Ch], 8
0x180010442  jz      short loc_180010459
0x180010444  mov     rcx, [rcx+10h]
0x180010448  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18001044f  mov     edx, 28h ; '('
0x180010454  call    WPP_SF_
0x180010459  mov     rcx, qword ptr cs:Block+8; this
0x180010460  call    ?CalculateNetworkSize@CNetworkHandler@@QEAAJXZ; CNetworkHandler::CalculateNetworkSize(void)
0x180010465  mov     ebx, eax
0x180010467  test    eax, eax
0x180010469  js      loc_180010583
0x18001046f  movups  xmm0, xmmword ptr [rsi]
0x180010472  mov     rcx, qword ptr cs:Block+8; this
0x180010479  lea     r8, [rsp+2C0h+Data]; unsigned int *
0x18001047e  lea     rdx, [rsp+2C0h+var_260]; struct _GUID
0x180010483  movdqu  xmmword ptr [rsp+2C0h+var_260.Data1], xmm0
0x180010489  call    ?GetNetworkSize@CNetworkHandler@@QEAAJU_GUID@@PEAK@Z; CNetworkHandler::GetNetworkSize(_GUID,ulong *)
0x18001048e  mov     ebx, eax
0x180010490  test    eax, eax
0x180010492  js      loc_180010583
0x180010498  jmp     short loc_1800104F7
0x18001049a  cmp     [rbp+1C0h+arg_20], 0
0x1800104a1  jz      loc_1800105B5
0x1800104a7  lea     r15, WPP_GLOBAL_Control
0x1800104ae  cmp     rcx, r15
0x1800104b1  jz      short loc_1800104CE
0x1800104b3  test    byte ptr [rcx+1Ch], 8
0x1800104b7  jz      short loc_1800104CE
0x1800104b9  mov     rcx, [rcx+10h]
0x1800104bd  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800104c4  mov     edx, 29h ; ')'
0x1800104c9  call    WPP_SF_
0x1800104ce  movups  xmm0, xmmword ptr [rsi]
0x1800104d1  mov     rcx, qword ptr cs:Block+8; this
0x1800104d8  lea     r8, [rsp+2C0h+Data]; unsigned int *
0x1800104dd  lea     rdx, [rsp+2C0h+var_260]; struct _GUID
0x1800104e2  movdqu  xmmword ptr [rsp+2C0h+var_260.Data1], xmm0
0x1800104e8  call    ?GetNetworkSize@CNetworkHandler@@QEAAJU_GUID@@PEAK@Z; CNetworkHandler::GetNetworkSize(_GUID,ulong *)
0x1800104ed  mov     ebx, eax
0x1800104ef  test    eax, eax
0x1800104f1  js      loc_18001058C
0x1800104f7  mov     edx, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800104fb  lea     rcx, ?g_NetworkConfiguration@@3PAUNETWORK_CONFIGURATION@@A; NETWORK_CONFIGURATION near * g_NetworkConfiguration
0x180010502  movsxd  rax, [rsp+2C0h+var_288]
0x180010507  xor     r8d, r8d
0x18001050a  add     rax, rax
0x18001050d  cmp     edx, [rcx+rax*8+4]
0x180010511  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x180010516  setnb   r8b; int
0x18001051a  xor     edi, edi
0x18001051c  call    ?SetNetworkSizeInRegistry@@YAJPEBGKH@Z; SetNetworkSizeInRegistry(ushort const *,ulong,int)
0x180010521  mov     ebx, eax
0x180010523  test    eax, eax
0x180010525  js      short loc_180010583
0x180010527  mov     rcx, cs:WPP_GLOBAL_Control
0x18001052e  lea     rdx, ?g_NetworkConfiguration@@3PAUNETWORK_CONFIGURATION@@A; NETWORK_CONFIGURATION near * g_NetworkConfiguration
0x180010535  test    edi, edi
0x180010537  jnz     loc_18001061A
0x18001053d  movsxd  rax, [rsp+2C0h+var_288]
0x180010542  mov     r9d, dword ptr [rsp+2C0h+Data]
0x180010547  add     rax, rax
0x18001054a  cmp     r9d, [rdx+rax*8+4]
0x18001054f  ja      loc_1800105E6
0x180010555  lea     r15, WPP_GLOBAL_Control
0x18001055c  cmp     rcx, r15
0x18001055f  jz      short loc_18001057C
0x180010561  test    byte ptr [rcx+1Ch], 8
0x180010565  jz      short loc_18001057C
0x180010567  mov     rcx, [rcx+10h]
0x18001056b  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010572  mov     edx, 2Ch ; ','
0x180010577  call    WPP_SF_d
0x18001057c  mov     dword ptr [r14], 1
0x180010583  mov     edi, [rsp+2C0h+var_290]
0x180010587  jmp     loc_180010625
0x18001058c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010593  cmp     rcx, r15
0x180010596  jz      short loc_180010583
0x180010598  test    byte ptr [rcx+1Ch], 2
0x18001059c  jz      short loc_180010583
0x18001059e  mov     rcx, [rcx+10h]
0x1800105a2  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800105a9  mov     edx, 2Ah ; '*'
0x1800105ae  call    WPP_SF_
0x1800105b3  jmp     short loc_180010583
0x1800105b5  lea     r15, WPP_GLOBAL_Control
0x1800105bc  cmp     rcx, r15
0x1800105bf  jz      short loc_1800105DC
0x1800105c1  test    byte ptr [rcx+1Ch], 8
0x1800105c5  jz      short loc_1800105DC
0x1800105c7  mov     rcx, [rcx+10h]
0x1800105cb  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x1800105d2  mov     edx, 2Bh ; '+'
0x1800105d7  call    WPP_SF_
0x1800105dc  mov     dword ptr [r13+0], 1
0x1800105e4  jmp     short loc_180010583
0x1800105e6  mov     [rsp+2C0h+var_280], 2
0x1800105ee  lea     r15, WPP_GLOBAL_Control
0x1800105f5  cmp     rcx, r15
0x1800105f8  jz      short loc_180010583
0x1800105fa  test    byte ptr [rcx+1Ch], 8
0x1800105fe  jz      short loc_180010583
0x180010600  mov     rcx, [rcx+10h]
0x180010604  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18001060b  mov     edx, 2Dh ; '-'
0x180010610  call    WPP_SF_d
0x180010615  jmp     loc_180010583
0x18001061a  mov     edi, [rsp+2C0h+var_290]
0x18001061e  lea     r15, WPP_GLOBAL_Control
0x180010625  mov     rcx, [rsp+2C0h+lpsz]; pv
0x18001062a  call    cs:__imp_CoTaskMemFree
0x180010630  test    ebx, ebx
0x180010632  js      loc_18001078F
0x180010638  cmp     [rbp+1C0h+arg_28], 0
  ... truncated ...
```
