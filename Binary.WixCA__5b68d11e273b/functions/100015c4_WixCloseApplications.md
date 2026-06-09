# WixCloseApplications

- ea: `0x100015c4`
- end: `0x1000196c`
- name: `WixCloseApplications`
- size: `936`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update`

## callees

- `0x100012eb`
- `0x10001416`
- `0x10001515`
- `0x100015c4`
- `0x1000995c`
- `0x1000996e`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e070`
- `0x1000e2ae`
- `0x1000e78c`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ed03`
- `0x1000f1d7`
- `0x1000f269`

## string_xrefs

- `0x10001631`: `failed to open view on WixCloseApplication table`

## pseudocode

```c
int __stdcall WixCloseApplications(MSIHANDLE hInstall)
{
  int v1; // ebx
  int v2; // edi
  int v3; // esi
  int v4; // eax
  MSICONDITION v5; // eax
  char v6; // al
  const WCHAR *v7; // eax
  int v8; // eax
  int v9; // esi
  int v11; // [esp+Ch] [ebp-2Ch] BYREF
  DWORD pcchValueBuf; // [esp+10h] [ebp-28h] BYREF
  LPCWSTR szValue; // [esp+14h] [ebp-24h] BYREF
  LPCWSTR szCondition; // [esp+18h] [ebp-20h] BYREF
  LPCWSTR szName; // [esp+1Ch] [ebp-1Ch] BYREF
  DWORD dwMilliseconds; // [esp+20h] [ebp-18h] BYREF
  MSIHANDLE hAny; // [esp+24h] [ebp-14h] BYREF
  LPCWSTR v18; // [esp+28h] [ebp-10h] BYREF
  int v19; // [esp+2Ch] [ebp-Ch] BYREF
  LPCWSTR lpString; // [esp+30h] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+34h] [ebp-4h] BYREF

  v1 = 0;
  pcchValueBuf = 0;
  v2 = 0;
  lpString = 0;
  szValue = 0;
  szCondition = 0;
  szName = 0;
  v19 = 0;
  dwMilliseconds = 0;
  v11 = 0;
  hAny = 0;
  hRecord = 0;
  v18 = 0;
  v3 = sub_1000D51F(hInstall, (int)"WixCloseApplications");
  if ( v3 >= 0 )
  {
    v3 = sub_1000ED03(szQuery, &hAny);
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
        v3 = sub_1000E9ED(hRecord, 1u, (DWORD)&pcchValueBuf);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get id from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E9ED(hRecord, 4u, (DWORD)&szCondition);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get condition from WixCloseApplication table");
          goto LABEL_62;
        }
        if ( szCondition && *szCondition )
        {
          v5 = MsiEvaluateConditionW(hInstall, szCondition);
          if ( v5 == MSICONDITION_ERROR )
          {
            v3 = -2147024809;
            sub_1000DA66(-2147024809, "failed to process condition for WixCloseApplication '%ls'");
            goto LABEL_62;
          }
          if ( v5 == MSICONDITION_FALSE )
            continue;
        }
        v3 = sub_1000E78C(hRecord, 2u, (DWORD)&lpString);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get target from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E78C(hRecord, 3u, (DWORD)&szValue);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get description from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E8E1(hRecord, 5u, (int)&v19);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get attributes from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E78C(hRecord, 6u, (DWORD)&szName);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get property from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E8E1(hRecord, 7u, (int)&v11);
        if ( v3 == 1 )
        {
          v11 = 0;
          v3 = 0;
        }
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get terminate exit-code from WixCloseApplication table");
          goto LABEL_62;
        }
        v3 = sub_1000E8E1(hRecord, 8u, (int)&dwMilliseconds);
        if ( v3 == 1 )
        {
          dwMilliseconds = 5000;
          v3 = 0;
        }
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "failed to get timeout from WixCloseApplication table");
          goto LABEL_62;
        }
        v6 = v19;
        if ( (v19 & 0x40) != 0 )
        {
          v7 = szValue;
          if ( !szValue )
            v7 = &dword_100226F0;
          v8 = sub_100012EB((int)lpString, v7);
          v3 = v8;
          if ( v8 == -2147023294 )
            goto LABEL_62;
          if ( v8 < 0 )
          {
            sub_1000DA66(v8, "Failure while prompting user to continue to close application.");
            goto LABEL_62;
          }
          v6 = v19;
        }
        if ( (v6 & 1) != 0 )
        {
          sub_10001416((int)lpString, 16, dwMilliseconds);
          v6 = v19;
        }
        if ( (v6 & 8) != 0 )
        {
          sub_10001416((int)lpString, 17, dwMilliseconds);
          v6 = v19;
        }
        if ( (v6 & 0x36) != 0 )
        {
          v3 = sub_1000F269(lpString, (int)&v18);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to add target data to CustomActionData");
            goto LABEL_62;
          }
          v3 = sub_1000F1D7(v19, &v18);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to add attribute data to CustomActionData");
            goto LABEL_62;
          }
          v3 = sub_1000F1D7(dwMilliseconds, &v18);
          if ( v3 < 0 || (v3 = sub_1000F1D7(v11, &v18), v3 < 0) )
          {
            sub_1000DA66(v3, "failed to add timeout data to CustomActionData");
            goto LABEL_62;
          }
        }
        if ( szName && *szName )
          sub_10001515((int)lpString, szName);
        ++v2;
      }
      v3 = v4 != -2147024637 ? v4 : 0;
      if ( v3 >= 0 )
      {
        if ( !v18 )
          goto LABEL_64;
        if ( *v18 )
        {
          v3 = sub_1000E070(L"WixCloseApplicationsDeferred", v18, 500 * v2);
          if ( v3 < 0 )
            sub_1000DA66(v3, "failed to schedule WixCloseApplicationsDeferred action");
        }
      }
      else
      {
        sub_1000DA66(v3, "failed while looping through all apps to close");
      }
    }
    else
    {
      sub_1000DA66(v3, "failed to open view on WixCloseApplication table");
    }
  }
  else
  {
    sub_1000DA66(v3, "failed to initialize");
  }
LABEL_62:
  if ( v18 )
    sub_1000A952(v18);
LABEL_64:
  if ( szName )
    sub_1000A952(szName);
  if ( szCondition )
    sub_1000A952(szCondition);
  if ( szValue )
    sub_1000A952(szValue);
  if ( lpString )
    sub_1000A952(lpString);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v3 < 0 )
    v1 = (v3 != -2147023294) + 1602;
  v9 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v9;
}

```

## disassembly

```asm
0x100015c4  push    ebp
0x100015c5  mov     ebp, esp
0x100015c7  sub     esp, 2Ch
0x100015ca  push    ebx
0x100015cb  xor     ebx, ebx
0x100015cd  push    esi
0x100015ce  push    edi
0x100015cf  push    offset aWixcloseapplic_1; "WixCloseApplications"
0x100015d4  push    [ebp+hInstall]; hInstall
0x100015d7  mov     [ebp+pcchValueBuf], ebx
0x100015da  mov     edi, ebx
0x100015dc  mov     [ebp+lpString], ebx
0x100015df  mov     [ebp+szValue], ebx
0x100015e2  mov     [ebp+szCondition], ebx
0x100015e5  mov     [ebp+szName], ebx
0x100015e8  mov     [ebp+var_C], ebx
0x100015eb  mov     [ebp+dwMilliseconds], ebx
0x100015ee  mov     [ebp+var_2C], ebx
0x100015f1  mov     [ebp+hAny], ebx
0x100015f4  mov     [ebp+hRecord], ebx
0x100015f7  mov     [ebp+var_10], ebx
0x100015fa  call    sub_1000D51F
0x100015ff  mov     esi, eax
0x10001601  test    esi, esi
0x10001603  jns     short loc_1000160F
0x10001605  push    offset aFailedToInitia_2; "failed to initialize"
0x1000160a  jmp     loc_100018D4
0x1000160f  cmp     [ebp+hAny], ebx
0x10001612  jz      short loc_1000161C
0x10001614  push    [ebp+hAny]; hAny
0x10001617  call    MsiCloseHandle
0x1000161c  lea     eax, [ebp+hAny]
0x1000161f  push    eax; phView
0x10001620  push    szQuery; szQuery
0x10001626  call    sub_1000ED03
0x1000162b  mov     esi, eax
0x1000162d  test    esi, esi
0x1000162f  jns     short loc_1000163B
0x10001631  push    offset aFailedToOpenVi; "failed to open view on WixCloseApplicat"...
0x10001636  jmp     loc_100018D4
0x1000163b  cmp     [ebp+hRecord], ebx
0x1000163e  jz      short loc_10001648
0x10001640  push    [ebp+hRecord]; hAny
0x10001643  call    MsiCloseHandle
0x10001648  lea     eax, [ebp+hRecord]
0x1000164b  mov     [ebp+hRecord], ebx
0x1000164e  push    eax; phRecord
0x1000164f  push    [ebp+hAny]; hView
0x10001652  call    sub_1000E2AE
0x10001657  test    eax, eax
0x10001659  jnz     loc_10001896
0x1000165f  lea     eax, [ebp+pcchValueBuf]
0x10001662  push    eax; pcchValueBuf
0x10001663  push    1; iField
0x10001665  push    [ebp+hRecord]; hRecord
0x10001668  call    sub_1000E9ED
0x1000166d  mov     esi, eax
0x1000166f  test    esi, esi
0x10001671  js      loc_1000188F
0x10001677  lea     eax, [ebp+szCondition]
0x1000167a  push    eax; pcchValueBuf
0x1000167b  push    4; iField
0x1000167d  push    [ebp+hRecord]; hRecord
0x10001680  call    sub_1000E9ED
0x10001685  mov     esi, eax
0x10001687  test    esi, esi
0x10001689  js      loc_10001888
0x1000168f  mov     eax, [ebp+szCondition]
0x10001692  test    eax, eax
0x10001694  jz      short loc_100016B1
0x10001696  cmp     [eax], bx
0x10001699  jz      short loc_100016B1
0x1000169b  push    eax; szCondition
0x1000169c  push    [ebp+hInstall]; hInstall
0x1000169f  call    MsiEvaluateConditionW
0x100016a4  cmp     eax, 3
0x100016a7  jz      loc_10001821
0x100016ad  test    eax, eax
0x100016af  jz      short loc_1000163B
0x100016b1  lea     eax, [ebp+lpString]
0x100016b4  push    eax; pcchResultBuf
0x100016b5  push    2; iField
0x100016b7  push    [ebp+hRecord]; hRecord
0x100016ba  call    sub_1000E78C
0x100016bf  mov     esi, eax
0x100016c1  test    esi, esi
0x100016c3  js      loc_10001881
0x100016c9  lea     eax, [ebp+szValue]
0x100016cc  push    eax; pcchResultBuf
0x100016cd  push    3; iField
0x100016cf  push    [ebp+hRecord]; hRecord
0x100016d2  call    sub_1000E78C
0x100016d7  mov     esi, eax
0x100016d9  test    esi, esi
0x100016db  js      loc_1000187A
0x100016e1  lea     eax, [ebp+var_C]
0x100016e4  push    eax; int
0x100016e5  push    5; iField
0x100016e7  push    [ebp+hRecord]; hRecord
0x100016ea  call    sub_1000E8E1
0x100016ef  mov     esi, eax
0x100016f1  test    esi, esi
0x100016f3  js      loc_10001873
0x100016f9  lea     eax, [ebp+szName]
0x100016fc  push    eax; pcchResultBuf
0x100016fd  push    6; iField
0x100016ff  push    [ebp+hRecord]; hRecord
0x10001702  call    sub_1000E78C
0x10001707  mov     esi, eax
0x10001709  test    esi, esi
0x1000170b  js      loc_1000186C
0x10001711  lea     eax, [ebp+var_2C]
0x10001714  push    eax; int
0x10001715  push    7; iField
0x10001717  push    [ebp+hRecord]; hRecord
0x1000171a  call    sub_1000E8E1
0x1000171f  mov     esi, eax
0x10001721  cmp     esi, 1
0x10001724  jnz     short loc_1000172B
0x10001726  mov     [ebp+var_2C], ebx
0x10001729  mov     esi, ebx
0x1000172b  test    esi, esi
0x1000172d  js      loc_10001865
0x10001733  lea     eax, [ebp+dwMilliseconds]
0x10001736  push    eax; int
0x10001737  push    8; iField
0x10001739  push    [ebp+hRecord]; hRecord
0x1000173c  call    sub_1000E8E1
0x10001741  mov     esi, eax
0x10001743  cmp     esi, 1
0x10001746  jnz     short loc_10001751
0x10001748  mov     [ebp+dwMilliseconds], 1388h
0x1000174f  mov     esi, ebx
0x10001751  test    esi, esi
0x10001753  js      loc_1000185E
0x10001759  mov     eax, [ebp+var_C]
0x1000175c  test    al, 40h
0x1000175e  jz      short loc_1000178E
0x10001760  mov     eax, [ebp+szValue]
0x10001763  test    eax, eax
0x10001765  jnz     short loc_1000176C
0x10001767  mov     eax, offset dword_100226F0
0x1000176c  push    eax; szValue
0x1000176d  push    [ebp+lpString]; int
0x10001770  call    sub_100012EB
0x10001775  mov     esi, eax
0x10001777  cmp     esi, 80070642h
0x1000177d  jz      loc_100018DC
0x10001783  test    esi, esi
0x10001785  js      loc_1000183C
0x1000178b  mov     eax, [ebp+var_C]
0x1000178e  test    al, 1
0x10001790  jz      short loc_100017A2
0x10001792  push    [ebp+dwMilliseconds]; dwMilliseconds
0x10001795  push    10h; int
0x10001797  push    [ebp+lpString]; int
0x1000179a  call    sub_10001416
0x1000179f  mov     eax, [ebp+var_C]
0x100017a2  test    al, 8
0x100017a4  jz      short loc_100017B6
0x100017a6  push    [ebp+dwMilliseconds]; dwMilliseconds
0x100017a9  push    11h; int
0x100017ab  push    [ebp+lpString]; int
0x100017ae  call    sub_10001416
0x100017b3  mov     eax, [ebp+var_C]
0x100017b6  test    al, 36h
0x100017b8  jz      short loc_10001806
0x100017ba  lea     eax, [ebp+var_10]
0x100017bd  push    eax; int
0x100017be  push    [ebp+lpString]; lpString
0x100017c1  call    sub_1000F269
0x100017c6  mov     esi, eax
0x100017c8  test    esi, esi
0x100017ca  js      loc_10001857
0x100017d0  lea     eax, [ebp+var_10]
0x100017d3  push    eax
0x100017d4  push    [ebp+var_C]
0x100017d7  call    sub_1000F1D7
0x100017dc  mov     esi, eax
0x100017de  test    esi, esi
0x100017e0  js      short loc_10001850
0x100017e2  lea     eax, [ebp+var_10]
0x100017e5  push    eax
0x100017e6  push    [ebp+dwMilliseconds]
0x100017e9  call    sub_1000F1D7
0x100017ee  mov     esi, eax
0x100017f0  test    esi, esi
0x100017f2  js      short loc_10001846
0x100017f4  lea     eax, [ebp+var_10]
0x100017f7  push    eax
0x100017f8  push    [ebp+var_2C]
0x100017fb  call    sub_1000F1D7
0x10001800  mov     esi, eax
0x10001802  test    esi, esi
0x10001804  js      short loc_10001846
0x10001806  mov     eax, [ebp+szName]
0x10001809  test    eax, eax
0x1000180b  jz      short loc_1000181B
0x1000180d  cmp     [eax], bx
0x10001810  jz      short loc_1000181B
0x10001812  push    eax; szName
0x10001813  push    [ebp+lpString]; int
0x10001816  call    sub_10001515
0x1000181b  inc     edi
0x1000181c  jmp     loc_1000163B
0x10001821  push    [ebp+pcchValueBuf]
0x10001824  mov     esi, 80070057h
0x10001829  push    offset aFailedToProces_0; "failed to process condition for WixClos"...
0x1000182e  push    esi
0x1000182f  call    sub_1000DA66
0x10001834  add     esp, 0Ch
0x10001837  jmp     loc_100018DC
0x1000183c  push    offset aFailureWhilePr; "Failure while prompting user to continu"...
0x10001841  jmp     loc_100018D4
0x10001846  push    offset aFailedToAddTim; "failed to add timeout data to CustomAct"...
0x1000184b  jmp     loc_100018D4
0x10001850  push    offset aFailedToAddAtt; "failed to add attribute data to CustomA"...
0x10001855  jmp     short loc_100018D4
0x10001857  push    offset aFailedToAddTar; "failed to add target data to CustomActi"...
0x1000185c  jmp     short loc_100018D4
0x1000185e  push    offset aFailedToGetTim; "failed to get timeout from WixCloseAppl"...
0x10001863  jmp     short loc_100018D4
0x10001865  push    offset aFailedToGetTer; "failed to get terminate exit-code from "...
0x1000186a  jmp     short loc_100018D4
0x1000186c  push    offset aFailedToGetPro; "failed to get property from WixCloseApp"...
0x10001871  jmp     short loc_100018D4
0x10001873  push    offset aFailedToGetAtt; "failed to get attributes from WixCloseA"...
0x10001878  jmp     short loc_100018D4
0x1000187a  push    offset aFailedToGetDes; "failed to get description from WixClose"...
0x1000187f  jmp     short loc_100018D4
0x10001881  push    offset aFailedToGetTar; "failed to get target from WixCloseAppli"...
0x10001886  jmp     short loc_100018D4
0x10001888  push    offset aFailedToGetCon; "failed to get condition from WixCloseAp"...
0x1000188d  jmp     short loc_100018D4
0x1000188f  push    offset aFailedToGetIdF; "failed to get id from WixCloseApplicati"...
0x10001894  jmp     short loc_100018D4
0x10001896  lea     esi, [eax+7FF8FEFDh]
0x1000189c  neg     esi
0x1000189e  sbb     esi, esi
0x100018a0  and     esi, eax
0x100018a2  jge     short loc_100018AB
0x100018a4  push    offset aFailedWhileLoo; "failed while looping through all apps t"...
0x100018a9  jmp     short loc_100018D4
0x100018ab  mov     ecx, [ebp+var_10]
0x100018ae  test    ecx, ecx
0x100018b0  jz      short loc_100018E9
0x100018b2  cmp     [ecx], bx
0x100018b5  jz      short loc_100018DC
0x100018b7  imul    eax, edi, 1F4h
0x100018bd  push    eax; iValue
0x100018be  push    ecx; szValue
0x100018bf  push    offset aWixcloseapplic_2; "WixCloseApplicationsDeferred"
0x100018c4  call    sub_1000E070
0x100018c9  mov     esi, eax
0x100018cb  test    esi, esi
0x100018cd  jns     short loc_100018DC
0x100018cf  push    offset aFailedToSchedu_0; "failed to schedule WixCloseApplications"...
0x100018d4  push    esi
0x100018d5  call    sub_1000DA66
0x100018da  pop     ecx
0x100018db  pop     ecx
0x100018dc  mov     ecx, [ebp+var_10]
0x100018df  test    ecx, ecx
0x100018e1  jz      short loc_100018E9
0x100018e3  push    ecx
0x100018e4  call    sub_1000A952
0x100018e9  cmp     [ebp+szName], ebx
0x100018ec  jz      short loc_100018F6
0x100018ee  push    [ebp+szName]
0x100018f1  call    sub_1000A952
0x100018f6  cmp     [ebp+szCondition], ebx
0x100018f9  jz      short loc_10001903
0x100018fb  push    [ebp+szCondition]
0x100018fe  call    sub_1000A952
0x10001903  cmp     [ebp+szValue], ebx
0x10001906  jz      short loc_10001910
0x10001908  push    [ebp+szValue]
0x1000190b  call    sub_1000A952
0x10001910  cmp     [ebp+lpString], ebx
0x10001913  jz      short loc_1000191D
0x10001915  push    [ebp+lpString]
0x10001918  call    sub_1000A952
0x1000191d  cmp     [ebp+pcchValueBuf], ebx
0x10001920  jz      short loc_1000192A
0x10001922  push    [ebp+pcchValueBuf]
0x10001925  call    sub_1000A952
0x1000192a  test    esi, esi
0x1000192c  jns     short loc_1000193F
0x1000192e  xor     ebx, ebx
0x10001930  cmp     esi, 80070642h
0x10001936  setnz   bl
0x10001939  add     ebx, 642h
0x1000193f  push    ebx
0x10001940  call    sub_1000D4AE
0x10001945  cmp     [ebp+hRecord], 0
0x10001949  mov     esi, eax
0x1000194b  jz      short loc_10001955
0x1000194d  push    [ebp+hRecord]; hAny
0x10001950  call    MsiCloseHandle
0x10001955  cmp     [ebp+hAny], 0
  ... truncated ...
```
