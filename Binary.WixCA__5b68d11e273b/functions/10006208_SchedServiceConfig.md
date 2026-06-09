# SchedServiceConfig

- ea: `0x10006208`
- end: `0x1000660f`
- name: `SchedServiceConfig`
- size: `1031`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x10006208`
- `0x1000995c`
- `0x10009980`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e070`
- `0x1000e2ae`
- `0x1000e78c`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ec26`
- `0x1000ed03`
- `0x1000f1d7`
- `0x1000f269`
- `0x1000f88b`

## string_xrefs

- `0x10006213`: `SchedServiceConfig`
- `0x1000629b`: `Failed to open view on ServiceConfig table.`
- `0x10006550`: `Failed to get component name`
- `0x10006540`: `Failed to get install state for Component: %ls`
- `0x10006536`: `Failed to get name of service.`
- `0x10006528`: `Failed to get ServiceConfig.NewService.`
- `0x1000651e`: `Failed to add NewService data to CustomActionData`
- `0x100064f6`: `failed to get reset period in days between service restart attempts.`
- `0x100064e2`: `failed to get command line to run on service failure.`
- `0x100064d8`: `failed to get message to send to users when server reboots due to service failure.`
- `0x1000657a`: `RollbackServiceConfig`
- `0x1000658a`: `failed to schedule RollbackServiceConfig action`
- `0x10006595`: `ExecServiceConfig`
- `0x100065a5`: `failed to schedule ExecServiceConfig action`

## pseudocode

```c
int __stdcall SchedServiceConfig(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // ebx
  signed int v3; // esi
  int v4; // eax
  signed int ComponentStateW; // eax
  bool v6; // sf
  int v7; // eax
  int v8; // eax
  int v9; // ebx
  int v10; // esi
  INSTALLSTATE piInstalled; // [esp+Ch] [ebp-20h] BYREF
  INSTALLSTATE piAction; // [esp+10h] [ebp-1Ch] BYREF
  LPCWSTR lpString; // [esp+14h] [ebp-18h] BYREF
  MSIHANDLE hAny; // [esp+18h] [ebp-14h] BYREF
  int v16; // [esp+1Ch] [ebp-10h] BYREF
  LPCWSTR szValue; // [esp+20h] [ebp-Ch] BYREF
  MSIHANDLE hRecord; // [esp+24h] [ebp-8h] BYREF
  LPCWSTR szComponent; // [esp+28h] [ebp-4h] BYREF

  v1 = 0;
  lpString = 0;
  v2 = 0;
  szValue = 0;
  hAny = 0;
  hRecord = 0;
  szComponent = 0;
  v16 = 0;
  v3 = sub_1000D51F(hInstall, (int)"SchedServiceConfig");
  if ( v3 >= 0 )
  {
    v3 = sub_1000F88B(&lpString);
    if ( v3 >= 0 )
    {
      v3 = sub_1000F269(lpString, (int)&szValue);
      if ( v3 >= 0 )
      {
        if ( hAny )
          MsiCloseHandle(hAny);
        v3 = sub_1000ED03(off_1003301C, &hAny);
        if ( v3 >= 0 )
        {
          while ( 1 )
          {
            if ( hRecord )
              MsiCloseHandle(hRecord);
            hRecord = 0;
            v4 = sub_1000E2AE(hAny, &hRecord);
            if ( v4 )
              break;
            piInstalled = INSTALLSTATE_UNKNOWN;
            piAction = INSTALLSTATE_UNKNOWN;
            v3 = sub_1000E9ED(hRecord, 2u, (DWORD)&szComponent);
            if ( v3 < 0 )
            {
              sub_1000DA66(v3, "Failed to get component name");
              goto LABEL_59;
            }
            ComponentStateW = MsiGetComponentStateW(hInstall, szComponent, &piInstalled, &piAction);
            v3 = ComponentStateW;
            v6 = ComponentStateW < 0;
            if ( ComponentStateW > 0 )
            {
              v3 = (unsigned __int16)ComponentStateW | 0x80070000;
              v6 = 1;
            }
            if ( v6 )
            {
              sub_1000DA66(v3, "Failed to get install state for Component: %ls");
              goto LABEL_59;
            }
            if ( sub_1000EC26(piInstalled, piAction) )
            {
              v3 = sub_1000E78C(hRecord, 1u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "Failed to get name of service.");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "Failed to add name to CustomActionData.");
                goto LABEL_59;
              }
              v3 = sub_1000E8E1(hRecord, 3u, (int)&v16);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "Failed to get ServiceConfig.NewService.");
                goto LABEL_59;
              }
              v3 = sub_1000F1D7(v16 != 0, &szValue);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "Failed to add NewService data to CustomActionData");
                goto LABEL_59;
              }
              v3 = sub_1000E9ED(hRecord, 4u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get first failure action type");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E9ED(hRecord, 5u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get second failure action type");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E9ED(hRecord, 6u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get third failure action type");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E8E1(hRecord, 7u, (int)&v16);
              v7 = v3 != 1 ? v16 : 0;
              v16 = v7;
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get reset period in days between service restart attempts.");
                goto LABEL_59;
              }
              v3 = sub_1000F1D7(v7, &szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E8E1(hRecord, 8u, (int)&v16);
              v8 = v3 != 1 ? v16 : 0;
              v16 = v8;
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get server restart delay value.");
                goto LABEL_59;
              }
              v3 = sub_1000F1D7(v8, &szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E78C(hRecord, 9u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get command line to run on service failure.");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_38;
              v3 = sub_1000E9ED(hRecord, 0xAu, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get message to send to users when server reboots due to service failure.");
                goto LABEL_59;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
              {
LABEL_38:
                sub_1000DA66(v3, "failed to add data to CustomActionData");
                goto LABEL_59;
              }
              ++v2;
            }
          }
          v3 = v4 != -2147024637 ? v4 : 0;
          if ( v3 >= 0 )
          {
            if ( v2 )
            {
              v9 = 1000 * v2;
              v3 = sub_1000E070(L"RollbackServiceConfig", lpString, v9);
              if ( v3 >= 0 )
              {
                v3 = sub_1000E070(L"ExecServiceConfig", szValue, v9);
                if ( v3 < 0 )
                  sub_1000DA66(v3, "failed to schedule ExecServiceConfig action");
              }
              else
              {
                sub_1000DA66(v3, "failed to schedule RollbackServiceConfig action");
              }
            }
          }
          else
          {
            sub_1000DA66(v3, "failed while looping through all objects to secure");
          }
        }
        else
        {
          sub_1000DA66(v3, "Failed to open view on ServiceConfig table.");
        }
      }
      else
      {
        sub_1000DA66(v3, "Failed to add encoding key to CustomActionData.");
      }
    }
    else
    {
      sub_1000DA66(v3, "Failed to get encoding key.");
    }
  }
  else
  {
    sub_1000DA66(v3, "Failed to initialize.");
  }
LABEL_59:
  if ( szComponent )
    sub_1000A952(szComponent);
  if ( szValue )
    sub_1000A952(szValue);
  if ( lpString )
    sub_1000A952(lpString);
  if ( v3 < 0 )
    v1 = 1603;
  v10 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v10;
}

```

## disassembly

```asm
0x10006208  push    ebp
0x10006209  mov     ebp, esp
0x1000620b  sub     esp, 20h
0x1000620e  push    ebx
0x1000620f  push    esi
0x10006210  push    edi
0x10006211  xor     edi, edi
0x10006213  push    offset aSchedserviceco_0; "SchedServiceConfig"
0x10006218  push    [ebp+hInstall]; hInstall
0x1000621b  mov     [ebp+lpString], edi
0x1000621e  mov     ebx, edi
0x10006220  mov     [ebp+szValue], edi
0x10006223  mov     [ebp+hAny], edi
0x10006226  mov     [ebp+hRecord], edi
0x10006229  mov     [ebp+szComponent], edi
0x1000622c  mov     [ebp+var_10], edi
0x1000622f  call    sub_1000D51F
0x10006234  mov     esi, eax
0x10006236  test    esi, esi
0x10006238  jns     short loc_10006244
0x1000623a  push    offset aFailedToInitia_1; "Failed to initialize."
0x1000623f  jmp     loc_100065AA
0x10006244  lea     eax, [ebp+lpString]
0x10006247  push    eax
0x10006248  call    sub_1000F88B
0x1000624d  mov     esi, eax
0x1000624f  test    esi, esi
0x10006251  jns     short loc_1000625D
0x10006253  push    offset aFailedToGetEnc; "Failed to get encoding key."
0x10006258  jmp     loc_100065AA
0x1000625d  lea     eax, [ebp+szValue]
0x10006260  push    eax; int
0x10006261  push    [ebp+lpString]; lpString
0x10006264  call    sub_1000F269
0x10006269  mov     esi, eax
0x1000626b  test    esi, esi
0x1000626d  jns     short loc_10006279
0x1000626f  push    offset aFailedToAddEnc; "Failed to add encoding key to CustomAct"...
0x10006274  jmp     loc_100065AA
0x10006279  cmp     [ebp+hAny], ebx
0x1000627c  jz      short loc_10006286
0x1000627e  push    [ebp+hAny]; hAny
0x10006281  call    MsiCloseHandle
0x10006286  lea     eax, [ebp+hAny]
0x10006289  push    eax; phView
0x1000628a  push    off_1003301C; szQuery
0x10006290  call    sub_1000ED03
0x10006295  mov     esi, eax
0x10006297  test    esi, esi
0x10006299  jns     short loc_100062A5
0x1000629b  push    offset aFailedToOpenVi_5; "Failed to open view on ServiceConfig ta"...
0x100062a0  jmp     loc_100065AA
0x100062a5  cmp     [ebp+hRecord], edi
0x100062a8  jz      short loc_100062B2
0x100062aa  push    [ebp+hRecord]; hAny
0x100062ad  call    MsiCloseHandle
0x100062b2  lea     eax, [ebp+hRecord]
0x100062b5  mov     [ebp+hRecord], edi
0x100062b8  push    eax; phRecord
0x100062b9  push    [ebp+hAny]; hView
0x100062bc  call    sub_1000E2AE
0x100062c1  test    eax, eax
0x100062c3  jnz     loc_10006557
0x100062c9  or      [ebp+piInstalled], 0FFFFFFFFh
0x100062cd  lea     eax, [ebp+szComponent]
0x100062d0  or      [ebp+piAction], 0FFFFFFFFh
0x100062d4  push    eax; pcchValueBuf
0x100062d5  push    2; iField
0x100062d7  push    [ebp+hRecord]; hRecord
0x100062da  call    sub_1000E9ED
0x100062df  mov     esi, eax
0x100062e1  test    esi, esi
0x100062e3  js      loc_10006550
0x100062e9  lea     eax, [ebp+piAction]
0x100062ec  push    eax; piAction
0x100062ed  lea     eax, [ebp+piInstalled]
0x100062f0  push    eax; piInstalled
0x100062f1  push    [ebp+szComponent]; szComponent
0x100062f4  push    [ebp+hInstall]; hInstall
0x100062f7  call    MsiGetComponentStateW
0x100062fc  mov     esi, eax
0x100062fe  test    esi, esi
0x10006300  jle     short loc_1000630D
0x10006302  movzx   esi, si
0x10006305  or      esi, 80070000h
0x1000630b  test    esi, esi
0x1000630d  js      loc_1000653D
0x10006313  push    [ebp+piAction]
0x10006316  push    [ebp+piInstalled]
0x10006319  call    sub_1000EC26
0x1000631e  test    eax, eax
0x10006320  jz      short loc_100062A5
0x10006322  lea     eax, [ebp+szComponent]
0x10006325  push    eax; pcchResultBuf
0x10006326  push    1; iField
0x10006328  push    [ebp+hRecord]; hRecord
0x1000632b  call    sub_1000E78C
0x10006330  mov     esi, eax
0x10006332  test    esi, esi
0x10006334  js      loc_10006536
0x1000633a  lea     eax, [ebp+szValue]
0x1000633d  push    eax; int
0x1000633e  push    [ebp+szComponent]; lpString
0x10006341  call    sub_1000F269
0x10006346  mov     esi, eax
0x10006348  test    esi, esi
0x1000634a  js      loc_1000652F
0x10006350  lea     eax, [ebp+var_10]
0x10006353  push    eax; int
0x10006354  push    3; iField
0x10006356  push    [ebp+hRecord]; hRecord
0x10006359  call    sub_1000E8E1
0x1000635e  mov     esi, eax
0x10006360  test    esi, esi
0x10006362  js      loc_10006528
0x10006368  lea     eax, [ebp+szValue]
0x1000636b  push    eax
0x1000636c  xor     eax, eax
0x1000636e  cmp     [ebp+var_10], eax
0x10006371  setnz   al
0x10006374  push    eax
0x10006375  call    sub_1000F1D7
0x1000637a  mov     esi, eax
0x1000637c  test    esi, esi
0x1000637e  js      loc_1000651E
0x10006384  lea     eax, [ebp+szComponent]
0x10006387  push    eax; pcchValueBuf
0x10006388  push    4; iField
0x1000638a  push    [ebp+hRecord]; hRecord
0x1000638d  call    sub_1000E9ED
0x10006392  mov     esi, eax
0x10006394  test    esi, esi
0x10006396  js      loc_10006514
0x1000639c  lea     eax, [ebp+szValue]
0x1000639f  push    eax; int
0x100063a0  push    [ebp+szComponent]; lpString
0x100063a3  call    sub_1000F269
0x100063a8  mov     esi, eax
0x100063aa  test    esi, esi
0x100063ac  js      loc_100064CE
0x100063b2  lea     eax, [ebp+szComponent]
0x100063b5  push    eax; pcchValueBuf
0x100063b6  push    5; iField
0x100063b8  push    [ebp+hRecord]; hRecord
0x100063bb  call    sub_1000E9ED
0x100063c0  mov     esi, eax
0x100063c2  test    esi, esi
0x100063c4  js      loc_1000650A
0x100063ca  lea     eax, [ebp+szValue]
0x100063cd  push    eax; int
0x100063ce  push    [ebp+szComponent]; lpString
0x100063d1  call    sub_1000F269
0x100063d6  mov     esi, eax
0x100063d8  test    esi, esi
0x100063da  js      loc_100064CE
0x100063e0  lea     eax, [ebp+szComponent]
0x100063e3  push    eax; pcchValueBuf
0x100063e4  push    6; iField
0x100063e6  push    [ebp+hRecord]; hRecord
0x100063e9  call    sub_1000E9ED
0x100063ee  mov     esi, eax
0x100063f0  test    esi, esi
0x100063f2  js      loc_10006500
0x100063f8  lea     eax, [ebp+szValue]
0x100063fb  push    eax; int
0x100063fc  push    [ebp+szComponent]; lpString
0x100063ff  call    sub_1000F269
0x10006404  mov     esi, eax
0x10006406  test    esi, esi
0x10006408  js      loc_100064CE
0x1000640e  lea     eax, [ebp+var_10]
0x10006411  push    eax; int
0x10006412  push    7; iField
0x10006414  push    [ebp+hRecord]; hRecord
0x10006417  call    sub_1000E8E1
0x1000641c  mov     esi, eax
0x1000641e  lea     eax, [esi-1]
0x10006421  neg     eax
0x10006423  sbb     eax, eax
0x10006425  and     eax, [ebp+var_10]
0x10006428  mov     [ebp+var_10], eax
0x1000642b  test    esi, esi
0x1000642d  js      loc_100064F6
0x10006433  lea     ecx, [ebp+szValue]
0x10006436  push    ecx
0x10006437  push    eax
0x10006438  call    sub_1000F1D7
0x1000643d  mov     esi, eax
0x1000643f  test    esi, esi
0x10006441  js      loc_100064CE
0x10006447  lea     eax, [ebp+var_10]
0x1000644a  push    eax; int
0x1000644b  push    8; iField
0x1000644d  push    [ebp+hRecord]; hRecord
0x10006450  call    sub_1000E8E1
0x10006455  mov     esi, eax
0x10006457  lea     eax, [esi-1]
0x1000645a  neg     eax
0x1000645c  sbb     eax, eax
0x1000645e  and     eax, [ebp+var_10]
0x10006461  mov     [ebp+var_10], eax
0x10006464  test    esi, esi
0x10006466  js      loc_100064EC
0x1000646c  lea     ecx, [ebp+szValue]
0x1000646f  push    ecx
0x10006470  push    eax
0x10006471  call    sub_1000F1D7
0x10006476  mov     esi, eax
0x10006478  test    esi, esi
0x1000647a  js      short loc_100064CE
0x1000647c  lea     eax, [ebp+szComponent]
0x1000647f  push    eax; pcchResultBuf
0x10006480  push    9; iField
0x10006482  push    [ebp+hRecord]; hRecord
0x10006485  call    sub_1000E78C
0x1000648a  mov     esi, eax
0x1000648c  test    esi, esi
0x1000648e  js      short loc_100064E2
0x10006490  lea     eax, [ebp+szValue]
0x10006493  push    eax; int
0x10006494  push    [ebp+szComponent]; lpString
0x10006497  call    sub_1000F269
0x1000649c  mov     esi, eax
0x1000649e  test    esi, esi
0x100064a0  js      short loc_100064CE
0x100064a2  lea     eax, [ebp+szComponent]
0x100064a5  push    eax; pcchValueBuf
0x100064a6  push    0Ah; iField
0x100064a8  push    [ebp+hRecord]; hRecord
0x100064ab  call    sub_1000E9ED
0x100064b0  mov     esi, eax
0x100064b2  test    esi, esi
0x100064b4  js      short loc_100064D8
0x100064b6  lea     eax, [ebp+szValue]
0x100064b9  push    eax; int
0x100064ba  push    [ebp+szComponent]; lpString
0x100064bd  call    sub_1000F269
0x100064c2  mov     esi, eax
0x100064c4  test    esi, esi
0x100064c6  js      short loc_100064CE
0x100064c8  inc     ebx
0x100064c9  jmp     loc_100062A5
0x100064ce  push    offset aFailedToAddDat_1; "failed to add data to CustomActionData"
0x100064d3  jmp     loc_100065AA
0x100064d8  push    offset aFailedToGetMes; "failed to get message to send to users "...
0x100064dd  jmp     loc_100065AA
0x100064e2  push    offset aFailedToGetCom_3; "failed to get command line to run on se"...
0x100064e7  jmp     loc_100065AA
0x100064ec  push    offset aFailedToGetSer_1; "failed to get server restart delay valu"...
0x100064f1  jmp     loc_100065AA
0x100064f6  push    offset aFailedToGetRes; "failed to get reset period in days betw"...
0x100064fb  jmp     loc_100065AA
0x10006500  push    offset aFailedToGetThi; "failed to get third failure action type"
0x10006505  jmp     loc_100065AA
0x1000650a  push    offset aFailedToGetSec_2; "failed to get second failure action typ"...
0x1000650f  jmp     loc_100065AA
0x10006514  push    offset aFailedToGetFir; "failed to get first failure action type"
0x10006519  jmp     loc_100065AA
0x1000651e  push    offset aFailedToAddNew; "Failed to add NewService data to Custom"...
0x10006523  jmp     loc_100065AA
0x10006528  push    offset aFailedToGetSer_2; "Failed to get ServiceConfig.NewService."
0x1000652d  jmp     short loc_100065AA
0x1000652f  push    offset aFailedToAddNam; "Failed to add name to CustomActionData."
0x10006534  jmp     short loc_100065AA
0x10006536  push    offset aFailedToGetNam_0; "Failed to get name of service."
0x1000653b  jmp     short loc_100065AA
0x1000653d  push    [ebp+szComponent]
0x10006540  push    offset aFailedToGetIns_0; "Failed to get install state for Compone"...
0x10006545  push    esi
0x10006546  call    sub_1000DA66
0x1000654b  add     esp, 0Ch
0x1000654e  jmp     short loc_100065B2
0x10006550  push    offset aFailedToGetCom_4; "Failed to get component name"
0x10006555  jmp     short loc_100065AA
0x10006557  lea     esi, [eax+7FF8FEFDh]
0x1000655d  neg     esi
0x1000655f  sbb     esi, esi
0x10006561  and     esi, eax
0x10006563  jge     short loc_1000656C
0x10006565  push    offset aFailedWhileLoo_2; "failed while looping through all object"...
0x1000656a  jmp     short loc_100065AA
0x1000656c  test    ebx, ebx
0x1000656e  jz      short loc_100065B2
0x10006570  imul    ebx, 3E8h
0x10006576  push    ebx; iValue
0x10006577  push    [ebp+lpString]; szValue
0x1000657a  push    offset aRollbackservic_1; "RollbackServiceConfig"
0x1000657f  call    sub_1000E070
0x10006584  mov     esi, eax
0x10006586  test    esi, esi
0x10006588  jns     short loc_10006591
0x1000658a  push    offset aFailedToSchedu_3; "failed to schedule RollbackServiceConfi"...
0x1000658f  jmp     short loc_100065AA
0x10006591  push    ebx; iValue
0x10006592  push    [ebp+szValue]; szValue
0x10006595  push    offset aExecservicecon_1; "ExecServiceConfig"
0x1000659a  call    sub_1000E070
0x1000659f  mov     esi, eax
0x100065a1  test    esi, esi
0x100065a3  jns     short loc_100065B2
  ... truncated ...
```
