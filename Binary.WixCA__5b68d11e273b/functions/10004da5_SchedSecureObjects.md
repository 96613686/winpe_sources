# SchedSecureObjects

- ea: `0x10004da5`
- end: `0x10005139`
- name: `SchedSecureObjects`
- size: `916`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x10003e3c`
- `0x10003e9c`
- `0x10004da5`
- `0x1000995c`
- `0x10009980`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e070`
- `0x1000e2ae`
- `0x1000e78c`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ec26`
- `0x1000ed03`
- `0x1000f18d`
- `0x1000f269`

## string_xrefs

- `0x10004e2a`: `failed to open view on SecureObjects table`
- `0x10005050`: `failed to get Component attributes for secure object`
- `0x10005049`: `failed to get target path of object '%ls'`
- `0x1000503f`: `failed to get Component name for secure object`
- `0x10005038`: `failed to get install state for Component: %ls`
- `0x10005013`: `failed to get domain for user to configure object`
- `0x10005009`: `failed to get user to configure object`
- `0x10004fff`: `failed to get permission to configure object`

## pseudocode

```c
int __stdcall SchedSecureObjects(MSIHANDLE hInstall)
{
  int v1; // ebx
  int v2; // edi
  signed int v3; // esi
  int v4; // eax
  int v5; // ebx
  signed int ComponentStateW; // eax
  int v7; // esi
  int v8; // eax
  int v9; // esi
  INSTALLSTATE piInstalled; // [esp+Ch] [ebp-2Ch] BYREF
  INSTALLSTATE piAction; // [esp+10h] [ebp-28h] BYREF
  int v13; // [esp+14h] [ebp-24h] BYREF
  LPCWSTR lpString; // [esp+18h] [ebp-20h] BYREF
  int v15; // [esp+1Ch] [ebp-1Ch]
  DWORD pcchValueBuf; // [esp+20h] [ebp-18h] BYREF
  MSIHANDLE hAny; // [esp+24h] [ebp-14h] BYREF
  LPCWSTR lpString2; // [esp+28h] [ebp-10h] BYREF
  LPCWSTR szValue; // [esp+2Ch] [ebp-Ch] BYREF
  LPCWSTR szComponent; // [esp+30h] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+34h] [ebp-4h] BYREF

  v1 = 0;
  pcchValueBuf = 0;
  v2 = 0;
  szComponent = 0;
  lpString2 = 0;
  lpString = 0;
  hAny = 0;
  hRecord = 0;
  szValue = 0;
  v15 = 0;
  v3 = sub_1000D51F(hInstall, (int)"SchedSecureObjects");
  if ( v3 >= 0 )
  {
    if ( sub_1000F18D(L"SecureObjects") )
    {
      sub_1000D9AB(2, "SecureObjects table doesn't exist, so there are no objects to secure.");
    }
    else
    {
      v3 = sub_1000ED03(off_10033010, &hAny);
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
          v3 = sub_1000E9ED(hRecord, 2u, (DWORD)&lpString2);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to get object table");
            goto LABEL_52;
          }
          v5 = sub_10003E3C(lpString2);
          if ( !v5 )
          {
            v3 = -2147024809;
            sub_1000DA66(-2147024809, "unknown SecureObject.Table: %ls");
            goto LABEL_52;
          }
          v13 = 0;
          v3 = sub_1000E8E1(hRecord, 7u, (int)&v13);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to get Component attributes for secure object");
            goto LABEL_52;
          }
          if ( (v13 & 0x100) != 0 )
          {
            v1 = v15;
          }
          else
          {
            v3 = sub_1000E9ED(hRecord, 1u, (DWORD)&pcchValueBuf);
            if ( v3 < 0 )
              goto LABEL_36;
            v3 = sub_10003E9C(v5, (LPCWSTR)pcchValueBuf, (DWORD)&lpString);
            if ( v3 < 0 )
            {
              sub_1000DA66(v3, "failed to get target path of object '%ls'");
              goto LABEL_52;
            }
            v3 = sub_1000E9ED(hRecord, 6u, (DWORD)&szComponent);
            if ( v3 < 0 )
            {
              sub_1000DA66(v3, "failed to get Component name for secure object");
              goto LABEL_52;
            }
            ComponentStateW = MsiGetComponentStateW(hInstall, szComponent, &piInstalled, &piAction);
            v2 = ComponentStateW;
            v7 = (unsigned __int16)ComponentStateW;
            if ( ComponentStateW > 0 )
              ComponentStateW = (unsigned __int16)ComponentStateW | 0x80070000;
            if ( ComponentStateW < 0 )
            {
              if ( v2 > 0 )
                v3 = v7 | 0x80070000;
              else
                v3 = v2;
              sub_1000DA66(v3, "failed to get install state for Component: %ls");
              goto LABEL_52;
            }
            v8 = sub_1000EC26(piInstalled, piAction);
            v1 = v15;
            if ( v8 )
            {
              v3 = sub_1000F269(lpString, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_32;
              v3 = sub_1000E9ED(hRecord, 1u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
LABEL_36:
                sub_1000DA66(v3, "failed to get name of object");
                goto LABEL_52;
              }
              v3 = sub_1000F269(lpString2, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_32;
              v3 = sub_1000E78C(hRecord, 3u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get domain for user to configure object");
                goto LABEL_52;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_32;
              v3 = sub_1000E78C(hRecord, 4u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get user to configure object");
                goto LABEL_52;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
                goto LABEL_32;
              v3 = sub_1000E9ED(hRecord, 5u, (DWORD)&szComponent);
              if ( v3 < 0 )
              {
                sub_1000DA66(v3, "failed to get permission to configure object");
                goto LABEL_52;
              }
              v3 = sub_1000F269(szComponent, (int)&szValue);
              if ( v3 < 0 )
              {
LABEL_32:
                sub_1000DA66(v3, "failed to add data to CustomActionData");
                goto LABEL_52;
              }
              v15 = ++v1;
            }
          }
        }
        v3 = v4 != -2147024637 ? v4 : 0;
        if ( v3 >= 0 )
        {
          if ( szValue )
          {
            if ( *szValue )
            {
              v3 = sub_1000E070(L"ExecSecureObjects", szValue, 1000 * v1);
              if ( v3 < 0 )
                sub_1000DA66(v3, "failed to schedule ExecSecureObjects action");
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
        sub_1000DA66(v3, "failed to open view on SecureObjects table");
      }
    }
  }
  else
  {
    sub_1000DA66(v3, "failed to initialize");
  }
LABEL_52:
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( szValue )
    sub_1000A952(szValue);
  if ( szComponent )
    sub_1000A952(szComponent);
  if ( lpString2 )
    sub_1000A952(lpString2);
  if ( lpString )
    sub_1000A952(lpString);
  if ( v3 < 0 )
    v2 = 1603;
  v9 = sub_1000D4AE(v2);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v9;
}

```

## disassembly

```asm
0x10004da5  push    ebp
0x10004da6  mov     ebp, esp
0x10004da8  sub     esp, 2Ch
0x10004dab  push    ebx
0x10004dac  xor     eax, eax
0x10004dae  push    esi
0x10004daf  push    edi
0x10004db0  push    offset aSchedsecureobj_1; "SchedSecureObjects"
0x10004db5  push    [ebp+hInstall]; hInstall
0x10004db8  mov     ebx, eax
0x10004dba  mov     [ebp+pcchValueBuf], eax
0x10004dbd  mov     edi, eax
0x10004dbf  mov     [ebp+szComponent], eax
0x10004dc2  mov     [ebp+lpString2], eax
0x10004dc5  mov     [ebp+lpString], eax
0x10004dc8  mov     [ebp+hAny], eax
0x10004dcb  mov     [ebp+hRecord], eax
0x10004dce  mov     [ebp+szValue], eax
0x10004dd1  mov     [ebp+var_1C], ebx
0x10004dd4  call    sub_1000D51F
0x10004dd9  mov     esi, eax
0x10004ddb  test    esi, esi
0x10004ddd  jns     short loc_10004DE9
0x10004ddf  push    offset aFailedToInitia_2; "failed to initialize"
0x10004de4  jmp     loc_100050B6
0x10004de9  push    offset aSecureobjects; "SecureObjects"
0x10004dee  call    sub_1000F18D
0x10004df3  test    eax, eax
0x10004df5  jz      short loc_10004E08
0x10004df7  push    offset aSecureobjectsT; "SecureObjects table doesn't exist, so t"...
0x10004dfc  push    2
0x10004dfe  call    sub_1000D9AB
0x10004e03  jmp     loc_100050BC
0x10004e08  cmp     [ebp+hAny], ebx
0x10004e0b  jz      short loc_10004E15
0x10004e0d  push    [ebp+hAny]; hAny
0x10004e10  call    MsiCloseHandle
0x10004e15  lea     eax, [ebp+hAny]
0x10004e18  push    eax; phView
0x10004e19  push    off_10033010; szQuery
0x10004e1f  call    sub_1000ED03
0x10004e24  mov     esi, eax
0x10004e26  test    esi, esi
0x10004e28  jns     short loc_10004E37
0x10004e2a  push    offset aFailedToOpenVi_4; "failed to open view on SecureObjects ta"...
0x10004e2f  jmp     loc_100050B6
0x10004e34  mov     ebx, [ebp+var_1C]
0x10004e37  cmp     [ebp+hRecord], 0
0x10004e3b  jz      short loc_10004E45
0x10004e3d  push    [ebp+hRecord]; hAny
0x10004e40  call    MsiCloseHandle
0x10004e45  and     [ebp+hRecord], 0
0x10004e49  lea     eax, [ebp+hRecord]
0x10004e4c  push    eax; phRecord
0x10004e4d  push    [ebp+hAny]; hView
0x10004e50  call    sub_1000E2AE
0x10004e55  test    eax, eax
0x10004e57  jnz     loc_10005076
0x10004e5d  lea     eax, [ebp+lpString2]
0x10004e60  push    eax; pcchValueBuf
0x10004e61  push    2; iField
0x10004e63  push    [ebp+hRecord]; hRecord
0x10004e66  call    sub_1000E9ED
0x10004e6b  mov     esi, eax
0x10004e6d  test    esi, esi
0x10004e6f  js      loc_1000506F
0x10004e75  push    [ebp+lpString2]; lpString2
0x10004e78  call    sub_10003E3C
0x10004e7d  mov     ebx, eax
0x10004e7f  test    ebx, ebx
0x10004e81  jz      loc_10005057
0x10004e87  and     [ebp+var_24], 0
0x10004e8b  lea     eax, [ebp+var_24]
0x10004e8e  push    eax; int
0x10004e8f  push    7; iField
0x10004e91  push    [ebp+hRecord]; hRecord
0x10004e94  call    sub_1000E8E1
0x10004e99  mov     esi, eax
0x10004e9b  test    esi, esi
0x10004e9d  js      loc_10005050
0x10004ea3  test    [ebp+var_24], 100h
0x10004eaa  jnz     short loc_10004E34
0x10004eac  lea     eax, [ebp+pcchValueBuf]
0x10004eaf  push    eax; pcchValueBuf
0x10004eb0  push    1; iField
0x10004eb2  push    [ebp+hRecord]; hRecord
0x10004eb5  call    sub_1000E9ED
0x10004eba  mov     esi, eax
0x10004ebc  test    esi, esi
0x10004ebe  js      loc_1000501D
0x10004ec4  lea     eax, [ebp+lpString]
0x10004ec7  push    eax; pcchPathBuf
0x10004ec8  push    [ebp+pcchValueBuf]; szValue
0x10004ecb  push    ebx; int
0x10004ecc  call    sub_10003E9C
0x10004ed1  mov     esi, eax
0x10004ed3  test    esi, esi
0x10004ed5  js      loc_10005046
0x10004edb  lea     eax, [ebp+szComponent]
0x10004ede  push    eax; pcchValueBuf
0x10004edf  push    6; iField
0x10004ee1  push    [ebp+hRecord]; hRecord
0x10004ee4  call    sub_1000E9ED
0x10004ee9  mov     esi, eax
0x10004eeb  test    esi, esi
0x10004eed  js      loc_1000503F
0x10004ef3  lea     eax, [ebp+piAction]
0x10004ef6  push    eax; piAction
0x10004ef7  lea     eax, [ebp+piInstalled]
0x10004efa  push    eax; piInstalled
0x10004efb  push    [ebp+szComponent]; szComponent
0x10004efe  push    [ebp+hInstall]; hInstall
0x10004f01  call    MsiGetComponentStateW
0x10004f06  mov     edi, eax
0x10004f08  movzx   esi, di
0x10004f0b  test    edi, edi
0x10004f0d  jg      short loc_10004F11
0x10004f0f  jmp     short loc_10004F18
0x10004f11  mov     eax, esi
0x10004f13  or      eax, 80070000h
0x10004f18  test    eax, eax
0x10004f1a  js      loc_10005027
0x10004f20  push    [ebp+piAction]
0x10004f23  push    [ebp+piInstalled]
0x10004f26  call    sub_1000EC26
0x10004f2b  mov     ebx, [ebp+var_1C]
0x10004f2e  test    eax, eax
0x10004f30  jz      loc_10004E37
0x10004f36  lea     eax, [ebp+szValue]
0x10004f39  push    eax; int
0x10004f3a  push    [ebp+lpString]; lpString
0x10004f3d  call    sub_1000F269
0x10004f42  mov     esi, eax
0x10004f44  test    esi, esi
0x10004f46  js      loc_10004FF5
0x10004f4c  lea     eax, [ebp+szComponent]
0x10004f4f  push    eax; pcchValueBuf
0x10004f50  push    1; iField
0x10004f52  push    [ebp+hRecord]; hRecord
0x10004f55  call    sub_1000E9ED
0x10004f5a  mov     esi, eax
0x10004f5c  test    esi, esi
0x10004f5e  js      loc_1000501D
0x10004f64  lea     eax, [ebp+szValue]
0x10004f67  push    eax; int
0x10004f68  push    [ebp+lpString2]; lpString
0x10004f6b  call    sub_1000F269
0x10004f70  mov     esi, eax
0x10004f72  test    esi, esi
0x10004f74  js      short loc_10004FF5
0x10004f76  lea     eax, [ebp+szComponent]
0x10004f79  push    eax; pcchResultBuf
0x10004f7a  push    3; iField
0x10004f7c  push    [ebp+hRecord]; hRecord
0x10004f7f  call    sub_1000E78C
0x10004f84  mov     esi, eax
0x10004f86  test    esi, esi
0x10004f88  js      loc_10005013
0x10004f8e  lea     eax, [ebp+szValue]
0x10004f91  push    eax; int
0x10004f92  push    [ebp+szComponent]; lpString
0x10004f95  call    sub_1000F269
0x10004f9a  mov     esi, eax
0x10004f9c  test    esi, esi
0x10004f9e  js      short loc_10004FF5
0x10004fa0  lea     eax, [ebp+szComponent]
0x10004fa3  push    eax; pcchResultBuf
0x10004fa4  push    4; iField
0x10004fa6  push    [ebp+hRecord]; hRecord
0x10004fa9  call    sub_1000E78C
0x10004fae  mov     esi, eax
0x10004fb0  test    esi, esi
0x10004fb2  js      short loc_10005009
0x10004fb4  lea     eax, [ebp+szValue]
0x10004fb7  push    eax; int
0x10004fb8  push    [ebp+szComponent]; lpString
0x10004fbb  call    sub_1000F269
0x10004fc0  mov     esi, eax
0x10004fc2  test    esi, esi
0x10004fc4  js      short loc_10004FF5
0x10004fc6  lea     eax, [ebp+szComponent]
0x10004fc9  push    eax; pcchValueBuf
0x10004fca  push    5; iField
0x10004fcc  push    [ebp+hRecord]; hRecord
0x10004fcf  call    sub_1000E9ED
0x10004fd4  mov     esi, eax
0x10004fd6  test    esi, esi
0x10004fd8  js      short loc_10004FFF
0x10004fda  lea     eax, [ebp+szValue]
0x10004fdd  push    eax; int
0x10004fde  push    [ebp+szComponent]; lpString
0x10004fe1  call    sub_1000F269
0x10004fe6  mov     esi, eax
0x10004fe8  test    esi, esi
0x10004fea  js      short loc_10004FF5
0x10004fec  inc     ebx
0x10004fed  mov     [ebp+var_1C], ebx
0x10004ff0  jmp     loc_10004E37
0x10004ff5  push    offset aFailedToAddDat_1; "failed to add data to CustomActionData"
0x10004ffa  jmp     loc_100050B6
0x10004fff  push    offset aFailedToGetPer; "failed to get permission to configure o"...
0x10005004  jmp     loc_100050B6
0x10005009  push    offset aFailedToGetUse; "failed to get user to configure object"
0x1000500e  jmp     loc_100050B6
0x10005013  push    offset aFailedToGetDom; "failed to get domain for user to config"...
0x10005018  jmp     loc_100050B6
0x1000501d  push    offset aFailedToGetNam; "failed to get name of object"
0x10005022  jmp     loc_100050B6
0x10005027  test    edi, edi
0x10005029  jg      short loc_1000502F
0x1000502b  mov     esi, edi
0x1000502d  jmp     short loc_10005035
0x1000502f  or      esi, 80070000h
0x10005035  push    [ebp+szComponent]
0x10005038  push    offset aFailedToGetIns; "failed to get install state for Compone"...
0x1000503d  jmp     short loc_10005064
0x1000503f  push    offset aFailedToGetCom_1; "failed to get Component name for secure"...
0x10005044  jmp     short loc_100050B6
0x10005046  push    [ebp+pcchValueBuf]
0x10005049  push    offset aFailedToGetTar_1; "failed to get target path of object '%l"...
0x1000504e  jmp     short loc_10005064
0x10005050  push    offset aFailedToGetCom_2; "failed to get Component attributes for "...
0x10005055  jmp     short loc_100050B6
0x10005057  push    [ebp+lpString2]
0x1000505a  mov     esi, 80070057h
0x1000505f  push    offset aUnknownSecureo; "unknown SecureObject.Table: %ls"
0x10005064  push    esi
0x10005065  call    sub_1000DA66
0x1000506a  add     esp, 0Ch
0x1000506d  jmp     short loc_100050BE
0x1000506f  push    offset aFailedToGetObj; "failed to get object table"
0x10005074  jmp     short loc_100050B6
0x10005076  lea     esi, [eax+7FF8FEFDh]
0x1000507c  neg     esi
0x1000507e  sbb     esi, esi
0x10005080  and     esi, eax
0x10005082  jge     short loc_1000508B
0x10005084  push    offset aFailedWhileLoo_2; "failed while looping through all object"...
0x10005089  jmp     short loc_100050B6
0x1000508b  mov     ecx, [ebp+szValue]
0x1000508e  test    ecx, ecx
0x10005090  jz      short loc_100050BE
0x10005092  xor     eax, eax
0x10005094  cmp     [ecx], ax
0x10005097  jz      short loc_100050BE
0x10005099  imul    eax, ebx, 3E8h
0x1000509f  push    eax; iValue
0x100050a0  push    ecx; szValue
0x100050a1  push    offset aExecsecureobje_4; "ExecSecureObjects"
0x100050a6  call    sub_1000E070
0x100050ab  mov     esi, eax
0x100050ad  test    esi, esi
0x100050af  jns     short loc_100050BE
0x100050b1  push    offset aFailedToSchedu_2; "failed to schedule ExecSecureObjects ac"...
0x100050b6  push    esi
0x100050b7  call    sub_1000DA66
0x100050bc  pop     ecx
0x100050bd  pop     ecx
0x100050be  cmp     [ebp+pcchValueBuf], 0
0x100050c2  jz      short loc_100050CC
0x100050c4  push    [ebp+pcchValueBuf]
0x100050c7  call    sub_1000A952
0x100050cc  mov     ecx, [ebp+szValue]
0x100050cf  test    ecx, ecx
0x100050d1  jz      short loc_100050D9
0x100050d3  push    ecx
0x100050d4  call    sub_1000A952
0x100050d9  cmp     [ebp+szComponent], 0
0x100050dd  jz      short loc_100050E7
0x100050df  push    [ebp+szComponent]
0x100050e2  call    sub_1000A952
0x100050e7  cmp     [ebp+lpString2], 0
0x100050eb  jz      short loc_100050F5
0x100050ed  push    [ebp+lpString2]
0x100050f0  call    sub_1000A952
0x100050f5  cmp     [ebp+lpString], 0
0x100050f9  jz      short loc_10005103
0x100050fb  push    [ebp+lpString]
0x100050fe  call    sub_1000A952
0x10005103  test    esi, esi
0x10005105  jns     short loc_1000510C
0x10005107  mov     edi, 643h
0x1000510c  push    edi
0x1000510d  call    sub_1000D4AE
0x10005112  cmp     [ebp+hRecord], 0
0x10005116  mov     esi, eax
0x10005118  jz      short loc_10005122
0x1000511a  push    [ebp+hRecord]; hAny
0x1000511d  call    MsiCloseHandle
0x10005122  cmp     [ebp+hAny], 0
0x10005126  jz      short loc_10005130
0x10005128  push    [ebp+hAny]; hAny
0x1000512b  call    MsiCloseHandle
0x10005130  pop     edi
0x10005131  mov     eax, esi
0x10005133  pop     esi
0x10005134  pop     ebx
0x10005135  leave
0x10005136  retn    4
```
