# SchedXmlConfig

- ea: `0x10009693`
- end: `0x10009956`
- name: `SchedXmlConfig`
- size: `707`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x100083f0`
- `0x1000852f`
- `0x100085c9`
- `0x100086c2`
- `0x10008a71`
- `0x10009693`
- `0x1000a63e`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e070`
- `0x1000e13e`
- `0x1000ec26`
- `0x1000ec82`
- `0x1000ece0`
- `0x1000f1d7`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x1000973e`
- `KERNEL32!lstrcmpW` at `0x1000973e`

## string_xrefs

- `0x100098d5`: `failed to write Preserve Date indicator to custom action data`
- `0x100098e3`: `failed to copy file name`
- `0x100098ce`: `failed to write change data`
- `0x1000969d`: `SchedXmlConfig`
- `0x100096e7`: `failed to read XmlConfig table`
- `0x1000971f`: `failed to process XmlConfig changes`
- `0x100098b4`: `Invalid flag configuration.  Cannot delete a fragment node.`
- `0x100098dc`: `failed to write action indicator custom action data`
- `0x10009901`: `ExecXmlConfig`
- `0x10009911`: `failed to schedule ExecXmlConfig action`

## pseudocode

```c
int __stdcall SchedXmlConfig(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  int v3; // eax
  LPVOID i; // ebx
  int v5; // ecx
  int v6; // eax
  int v7; // eax
  int v9; // [esp-8h] [ebp-28h]
  wchar_t Str[2]; // [esp+8h] [ebp-18h] BYREF
  int v11; // [esp+Ch] [ebp-14h]
  int v12; // [esp+10h] [ebp-10h]
  LPVOID lpMem; // [esp+14h] [ebp-Ch] BYREF
  LPCWSTR szValue; // [esp+18h] [ebp-8h] BYREF
  LPCWSTR lpString1; // [esp+1Ch] [ebp-4h] BYREF
  MSIHANDLE hInstalla; // [esp+28h] [ebp+8h]

  v1 = 0;
  lpString1 = 0;
  v12 = 0;
  lpMem = 0;
  *(_DWORD *)Str = 0;
  szValue = 0;
  v11 = 0;
  v2 = sub_1000D51F(hInstall, (int)"SchedXmlConfig");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_51;
  }
  v3 = sub_100086C2((int *)&lpMem, Str);
  v2 = v3;
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "%s");
    sub_1000E13E(25540, v2, INSTALLMESSAGE_ERROR, 0);
    goto LABEL_51;
  }
  v2 = sub_100085C9(&lpMem);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to process XmlConfig changes");
    goto LABEL_51;
  }
  for ( i = lpMem; i; i = (LPVOID)*((_DWORD *)i + 343) )
  {
    if ( !lpString1 || lstrcmpW(lpString1, (LPCWSTR)i + 152) )
    {
      v2 = sub_1000A63E((int)&lpString1, (LPCWSTR)i + 152, 0);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "failed to copy file name");
        goto LABEL_51;
      }
      v12 = 1;
    }
    hInstalla = 0;
    if ( (*((_DWORD *)i + 338) & 0x100) != 0
      && (sub_1000EC26(*((_DWORD *)i + 74), *((_DWORD *)i + 75))
       || sub_1000EC82(*((_DWORD *)i + 74), *((_DWORD *)i + 75)))
      || (*((_DWORD *)i + 338) & 0x200) != 0 && sub_1000ECE0(*((_DWORD *)i + 74), *((_DWORD *)i + 75)) )
    {
      v5 = *((_DWORD *)i + 338);
      if ( (*((_BYTE *)i + 1352) & 0x11) == 0x11 )
      {
        v9 = 6;
LABEL_27:
        v6 = v9;
        hInstalla = v9;
        goto LABEL_30;
      }
      if ( (v5 & 0x21) == 0x21 )
      {
        v9 = 7;
        goto LABEL_27;
      }
      if ( (v5 & 0x22) == 0x22 )
      {
        v9 = 5;
        goto LABEL_27;
      }
      if ( (v5 & 0x12) == 0x12 )
      {
        v9 = 3;
        goto LABEL_27;
      }
      if ( (v5 & 0x14) == 0x14 )
      {
        v9 = 4;
        goto LABEL_27;
      }
      if ( (v5 & 0x24) == 0x24 )
      {
        v2 = -2147024809;
        sub_1000DA66(-2147024809, "Invalid flag configuration.  Cannot delete a fragment node.");
        goto LABEL_51;
      }
    }
    v6 = 0;
LABEL_30:
    *(_DWORD *)Str = (*((_DWORD *)i + 338) >> 12) & 1;
    if ( v6 )
    {
      if ( v12 )
      {
        v7 = sub_100083F0(lpString1, *((LPCWSTR *)i + 339), (int)&szValue);
        v2 = v7;
        if ( v7 < 0 )
        {
          sub_1000DA66(v7, "failed to begin file change for file: %ls");
          goto LABEL_51;
        }
        ++v11;
        v12 = 0;
      }
      v2 = sub_1000F1D7(hInstalla, &szValue);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "failed to write action indicator custom action data");
        goto LABEL_51;
      }
      v2 = sub_1000F1D7(*(_DWORD *)Str, &szValue);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "failed to write Preserve Date indicator to custom action data");
        goto LABEL_51;
      }
      v2 = sub_10008A71(i, hInstalla, &szValue);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "failed to write change data");
        goto LABEL_51;
      }
    }
  }
  v2 = v2 != -2147024637 ? v2 : 0;
  if ( v2 >= 0 )
  {
    if ( szValue )
    {
      if ( *szValue )
      {
        v2 = sub_1000E070(L"ExecXmlConfig", szValue, 1000 * v11);
        if ( v2 < 0 )
          sub_1000DA66(v2, "failed to schedule ExecXmlConfig action");
      }
    }
  }
  else
  {
    sub_1000DA66(v2, "failed while looping through all objects to secure");
  }
LABEL_51:
  if ( lpString1 )
    sub_1000A952(lpString1);
  if ( szValue )
    sub_1000A952(szValue);
  sub_1000852F(lpMem);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10009693  push    ebp
0x10009694  mov     ebp, esp
0x10009696  sub     esp, 18h
0x10009699  push    esi
0x1000969a  push    edi
0x1000969b  xor     edi, edi
0x1000969d  push    offset aSchedxmlconfig_0; "SchedXmlConfig"
0x100096a2  push    [ebp+hInstall]; hInstall
0x100096a5  mov     [ebp+lpString1], edi
0x100096a8  mov     [ebp+var_10], edi
0x100096ab  mov     [ebp+lpMem], edi
0x100096ae  mov     dword ptr [ebp+Str], edi
0x100096b1  mov     [ebp+szValue], edi
0x100096b4  mov     [ebp+var_14], edi
0x100096b7  call    sub_1000D51F
0x100096bc  mov     esi, eax
0x100096be  test    esi, esi
0x100096c0  jns     short loc_100096D4
0x100096c2  push    offset aFailedToInitia_2; "failed to initialize"
0x100096c7  push    esi
0x100096c8  call    sub_1000DA66
0x100096cd  pop     ecx
0x100096ce  pop     ecx
0x100096cf  jmp     loc_1000991F
0x100096d4  lea     eax, [ebp+Str]
0x100096d7  push    eax; Str
0x100096d8  lea     eax, [ebp+lpMem]
0x100096db  push    eax; int
0x100096dc  call    sub_100086C2
0x100096e1  mov     esi, eax
0x100096e3  test    esi, esi
0x100096e5  jns     short loc_10009710
0x100096e7  push    offset aFailedToReadXm_0; "failed to read XmlConfig table"
0x100096ec  push    offset aS_1; "%s"
0x100096f1  push    esi
0x100096f2  call    sub_1000DA66
0x100096f7  push    edi; int
0x100096f8  push    1000000h; eMessageType
0x100096fd  push    esi; int
0x100096fe  push    63C4h; iValue
0x10009703  call    sub_1000E13E
0x10009708  add     esp, 1Ch
0x1000970b  jmp     loc_1000991F
0x10009710  lea     eax, [ebp+lpMem]
0x10009713  push    eax
0x10009714  call    sub_100085C9
0x10009719  mov     esi, eax
0x1000971b  test    esi, esi
0x1000971d  jns     short loc_10009726
0x1000971f  push    offset aFailedToProces_6; "failed to process XmlConfig changes"
0x10009724  jmp     short loc_100096C7
0x10009726  push    ebx
0x10009727  mov     ebx, [ebp+lpMem]
0x1000972a  jmp     loc_10009890
0x1000972f  cmp     [ebp+lpString1], edi
0x10009732  jz      short loc_10009748
0x10009734  lea     eax, [ebx+130h]
0x1000973a  push    eax; lpString2
0x1000973b  push    [ebp+lpString1]; lpString1
0x1000973e  call    ds:lstrcmpW
0x10009744  test    eax, eax
0x10009746  jz      short loc_1000976A
0x10009748  push    edi; int
0x10009749  lea     eax, [ebx+130h]
0x1000974f  push    eax; lpString
0x10009750  lea     eax, [ebp+lpString1]
0x10009753  push    eax; int
0x10009754  call    sub_1000A63E
0x10009759  mov     esi, eax
0x1000975b  test    esi, esi
0x1000975d  js      loc_100098E3
0x10009763  mov     [ebp+var_10], 1
0x1000976a  test    dword ptr [ebx+548h], 100h
0x10009774  mov     [ebp+hInstall], edi
0x10009777  jz      short loc_100097A3
0x10009779  push    dword ptr [ebx+12Ch]
0x1000977f  push    dword ptr [ebx+128h]
0x10009785  call    sub_1000EC26
0x1000978a  test    eax, eax
0x1000978c  jnz     short loc_100097C4
0x1000978e  push    dword ptr [ebx+12Ch]
0x10009794  push    dword ptr [ebx+128h]
0x1000979a  call    sub_1000EC82
0x1000979f  test    eax, eax
0x100097a1  jnz     short loc_100097C4
0x100097a3  test    dword ptr [ebx+548h], 200h
0x100097ad  jz      short loc_1000981B
0x100097af  push    dword ptr [ebx+12Ch]
0x100097b5  push    dword ptr [ebx+128h]
0x100097bb  call    sub_1000ECE0
0x100097c0  test    eax, eax
0x100097c2  jz      short loc_1000981B
0x100097c4  mov     ecx, [ebx+548h]
0x100097ca  mov     eax, ecx
0x100097cc  and     eax, 11h
0x100097cf  cmp     al, 11h
0x100097d1  jnz     short loc_100097D7
0x100097d3  push    6
0x100097d5  jmp     short loc_10009809
0x100097d7  mov     eax, ecx
0x100097d9  and     eax, 21h
0x100097dc  cmp     al, 21h ; '!'
0x100097de  jnz     short loc_100097E4
0x100097e0  push    7
0x100097e2  jmp     short loc_10009809
0x100097e4  mov     eax, ecx
0x100097e6  and     eax, 22h
0x100097e9  cmp     al, 22h ; '"'
0x100097eb  jnz     short loc_100097F1
0x100097ed  push    5
0x100097ef  jmp     short loc_10009809
0x100097f1  mov     eax, ecx
0x100097f3  and     eax, 12h
0x100097f6  cmp     al, 12h
0x100097f8  jnz     short loc_100097FE
0x100097fa  push    3
0x100097fc  jmp     short loc_10009809
0x100097fe  mov     eax, ecx
0x10009800  and     eax, 14h
0x10009803  cmp     al, 14h
0x10009805  jnz     short loc_1000980F
0x10009807  push    4
0x10009809  pop     eax
0x1000980a  mov     [ebp+hInstall], eax
0x1000980d  jmp     short loc_1000981D
0x1000980f  and     ecx, 24h
0x10009812  cmp     cl, 24h ; '$'
0x10009815  jz      loc_100098AF
0x1000981b  mov     eax, edi
0x1000981d  mov     ecx, [ebx+548h]
0x10009823  shr     ecx, 0Ch
0x10009826  and     ecx, 1
0x10009829  mov     dword ptr [ebp+Str], ecx
0x1000982c  test    eax, eax
0x1000982e  jz      short loc_1000988A
0x10009830  cmp     [ebp+var_10], edi
0x10009833  jz      short loc_10009853
0x10009835  lea     eax, [ebp+szValue]
0x10009838  push    eax; int
0x10009839  push    dword ptr [ebx+54Ch]; szValue
0x1000983f  push    [ebp+lpString1]; lpFileName
0x10009842  call    sub_100083F0
0x10009847  mov     esi, eax
0x10009849  test    esi, esi
0x1000984b  js      short loc_100098BB
0x1000984d  inc     [ebp+var_14]
0x10009850  mov     [ebp+var_10], edi
0x10009853  lea     eax, [ebp+szValue]
0x10009856  push    eax
0x10009857  push    [ebp+hInstall]
0x1000985a  call    sub_1000F1D7
0x1000985f  mov     esi, eax
0x10009861  test    esi, esi
0x10009863  js      short loc_100098DC
0x10009865  lea     eax, [ebp+szValue]
0x10009868  push    eax
0x10009869  push    dword ptr [ebp+Str]
0x1000986c  call    sub_1000F1D7
0x10009871  mov     esi, eax
0x10009873  test    esi, esi
0x10009875  js      short loc_100098D5
0x10009877  lea     eax, [ebp+szValue]
0x1000987a  push    eax
0x1000987b  push    [ebp+hInstall]
0x1000987e  push    ebx
0x1000987f  call    sub_10008A71
0x10009884  mov     esi, eax
0x10009886  test    esi, esi
0x10009888  js      short loc_100098CE
0x1000988a  mov     ebx, [ebx+55Ch]
0x10009890  test    ebx, ebx
0x10009892  jnz     loc_1000972F
0x10009898  lea     eax, [esi+7FF8FEFDh]
0x1000989e  neg     eax
0x100098a0  sbb     eax, eax
0x100098a2  and     esi, eax
0x100098a4  mov     eax, esi
0x100098a6  jge     short loc_100098EA
0x100098a8  push    offset aFailedWhileLoo_2; "failed while looping through all object"...
0x100098ad  jmp     short loc_10009916
0x100098af  mov     esi, 80070057h
0x100098b4  push    offset aInvalidFlagCon; "Invalid flag configuration.  Cannot del"...
0x100098b9  jmp     short loc_10009916
0x100098bb  push    [ebp+lpString1]
0x100098be  push    offset aFailedToBeginF; "failed to begin file change for file: %"...
0x100098c3  push    esi
0x100098c4  call    sub_1000DA66
0x100098c9  add     esp, 0Ch
0x100098cc  jmp     short loc_1000991E
0x100098ce  push    offset aFailedToWriteC_1; "failed to write change data"
0x100098d3  jmp     short loc_10009916
0x100098d5  push    offset aFailedToWriteP; "failed to write Preserve Date indicator"...
0x100098da  jmp     short loc_10009916
0x100098dc  push    offset aFailedToWriteA_0; "failed to write action indicator custom"...
0x100098e1  jmp     short loc_10009916
0x100098e3  push    offset aFailedToCopyFi; "failed to copy file name"
0x100098e8  jmp     short loc_10009916
0x100098ea  mov     ecx, [ebp+szValue]
0x100098ed  test    ecx, ecx
0x100098ef  jz      short loc_1000991E
0x100098f1  mov     esi, eax
0x100098f3  cmp     [ecx], di
0x100098f6  jz      short loc_1000991E
0x100098f8  imul    eax, [ebp+var_14], 3E8h
0x100098ff  push    eax; iValue
0x10009900  push    ecx; szValue
0x10009901  push    offset aExecxmlconfig_1; "ExecXmlConfig"
0x10009906  call    sub_1000E070
0x1000990b  mov     esi, eax
0x1000990d  test    esi, esi
0x1000990f  jns     short loc_1000991E
0x10009911  push    offset aFailedToSchedu_8; "failed to schedule ExecXmlConfig action"
0x10009916  push    esi
0x10009917  call    sub_1000DA66
0x1000991c  pop     ecx
0x1000991d  pop     ecx
0x1000991e  pop     ebx
0x1000991f  cmp     [ebp+lpString1], edi
0x10009922  jz      short loc_1000992C
0x10009924  push    [ebp+lpString1]
0x10009927  call    sub_1000A952
0x1000992c  mov     ecx, [ebp+szValue]
0x1000992f  test    ecx, ecx
0x10009931  jz      short loc_10009939
0x10009933  push    ecx
0x10009934  call    sub_1000A952
0x10009939  push    [ebp+lpMem]; lpMem
0x1000993c  call    sub_1000852F
0x10009941  test    esi, esi
0x10009943  jns     short loc_1000994A
0x10009945  mov     edi, 643h
0x1000994a  push    edi
0x1000994b  call    sub_1000D4AE
0x10009950  pop     edi
0x10009951  pop     esi
0x10009952  leave
0x10009953  retn    4
```
