# WixRegisterRestartResources

- ea: `0x100034ad`
- end: `0x1000380d`
- name: `WixRegisterRestartResources`
- size: `864`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10003447`
- `0x100034ad`
- `0x1000995c`
- `0x1000997a`
- `0x1000a952`
- `0x1000bd8b`
- `0x1000c0be`
- `0x1000c130`
- `0x1000c162`
- `0x1000c245`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e2ae`
- `0x1000e355`
- `0x1000e662`
- `0x1000e78c`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ed03`
- `0x1000f18d`

## string_xrefs

- `0x10003517`: `MsiRestartManagerSessionKey`
- `0x10003527`: `Failed to get the MsiRestartManagerSessionKey property.`
- `0x10003542`: `Failed to get the MsiRestartManagerSessionKey string length.`
- `0x1000354e`: `The MsiRestartManagerSessionKey property is not available to join.`
- `0x100035b7`: `Failed to open a view on the RestartResource table.`
- `0x10003767`: `Failed to get the Component_ field value.`
- `0x100036af`: `Registering service name %ls with the Restart Manager.`
- `0x100036d2`: `Failed to register the service name with the Restart Manager session.`

## pseudocode

```c
int __stdcall WixRegisterRestartResources(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  int v3; // eax
  int v4; // eax
  BOOL IsNull; // esi
  int v6; // eax
  int v7; // eax
  int v8; // esi
  int v10; // [esp+8h] [ebp-24h] BYREF
  int v11; // [esp+Ch] [ebp-20h] BYREF
  LPCWSTR szComponent; // [esp+10h] [ebp-1Ch] BYREF
  DWORD pcchValueBuf; // [esp+14h] [ebp-18h] BYREF
  DWORD v14; // [esp+18h] [ebp-14h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [esp+1Ch] [ebp-10h] BYREF
  MSIHANDLE hAny; // [esp+20h] [ebp-Ch] BYREF
  LPCWSTR lpString; // [esp+24h] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+28h] [ebp-4h] BYREF

  v1 = 0;
  hAny = 0;
  hRecord = 0;
  pcchValueBuf = 0;
  v11 = 0;
  lpCriticalSection = 0;
  v14 = 0;
  szComponent = 0;
  lpString = 0;
  v10 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixRegisterRestartResources");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "Failed to initialize.");
    goto LABEL_50;
  }
  if ( sub_1000F18D(L"WixRestartResource") )
  {
    sub_1000D9AB(
      2,
      "The RestartResource table does not exist; there are no resources to register with Restart Manager.");
    goto LABEL_50;
  }
  v2 = sub_1000E662(L"MsiRestartManagerSessionKey", (DWORD)&pcchValueBuf);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "Failed to get the MsiRestartManagerSessionKey property.");
    goto LABEL_50;
  }
  v2 = sub_10003447(pcchValueBuf, 33, &v11);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "Failed to get the MsiRestartManagerSessionKey string length.");
    goto LABEL_50;
  }
  if ( !v11 )
  {
    sub_1000D9AB(2, "The MsiRestartManagerSessionKey property is not available to join.");
    goto LABEL_50;
  }
  v3 = sub_1000C245(&lpCriticalSection, pcchValueBuf);
  if ( v3 == -2147024770 )
  {
    sub_1000D9AB(2, "The Restart Manager is not supported on this platform. Skipping.");
LABEL_13:
    v2 = 0;
    goto LABEL_50;
  }
  if ( v3 < 0 )
  {
    sub_1000D9AB(2, "Failed to join the existing Restart Manager session %ls.");
    goto LABEL_13;
  }
  if ( hAny )
    MsiCloseHandle(hAny);
  v2 = sub_1000ED03(off_10033008, &hAny);
  if ( v2 >= 0 )
  {
    while ( 1 )
    {
      if ( hRecord )
        MsiCloseHandle(hRecord);
      hRecord = 0;
      v4 = sub_1000E2AE(hAny, &hRecord);
      if ( v4 )
        break;
      v2 = sub_1000E9ED(hRecord, 1u, (DWORD)&v14);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "Failed to get the RestartResource field value.");
        goto LABEL_50;
      }
      v2 = sub_1000E9ED(hRecord, 2u, (DWORD)&szComponent);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "Failed to get the Component_ field value.");
        goto LABEL_50;
      }
      v2 = sub_1000E78C(hRecord, 3u, (DWORD)&lpString);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "Failed to get the Resource formatted field value.");
        goto LABEL_50;
      }
      v2 = sub_1000E8E1(hRecord, 4u, (int)&v10);
      if ( v2 < 0 )
      {
        sub_1000DA66(v2, "Failed to get the Attributes field value.");
        goto LABEL_50;
      }
      IsNull = MsiRecordIsNull(hRecord, 2u);
      v6 = sub_1000E355(szComponent);
      if ( IsNull || v6 )
      {
        switch ( v10 & 0xF )
        {
          case 1:
            sub_1000D9AB(1, "Registering file name %ls with the Restart Manager.");
            v2 = sub_1000BD8B(lpCriticalSection, lpString);
            if ( v2 < 0 )
            {
              sub_1000DA66(v2, "Failed to register the file name with the Restart Manager session.");
              goto LABEL_50;
            }
            break;
          case 2:
            sub_1000D9AB(1, "Registering process name %ls with the Restart Manager.");
            v7 = sub_1000C0BE(lpCriticalSection, lpString);
            v2 = v7;
            if ( v7 == -2147023728 )
            {
              sub_1000D9AB(
                2,
                "The process, %ls, could not be registered with the Restart Manager (probably because the setup is not el"
                "evated and the process is in another user context). A reboot may be requested later.");
            }
            else if ( v7 < 0 )
            {
              sub_1000DA66(v7, "Failed to register the process name with the Restart Manager session.");
              goto LABEL_50;
            }
            break;
          case 3:
            sub_1000D9AB(1, "Registering service name %ls with the Restart Manager.");
            v2 = sub_1000C130(lpCriticalSection, lpString);
            if ( v2 < 0 )
            {
              sub_1000DA66(v2, "Failed to register the service name with the Restart Manager session.");
              goto LABEL_50;
            }
            break;
          default:
            sub_1000D9AB(1, "The resource type %d for %ls is not supported and will not be registered.");
            break;
        }
      }
      else
      {
        sub_1000D9AB(1, "Skipping resource %ls.");
      }
    }
    v2 = v4 != -2147024637 ? v4 : 0;
    if ( v2 >= 0 )
    {
      v2 = sub_1000C162(lpCriticalSection);
      if ( v2 < 0 )
      {
        sub_1000D9AB(1, "Failed to register the resources with the Restart Manager.");
        v2 = 0;
      }
    }
    else
    {
      sub_1000DA66(v2, "Failed while looping through all rows to register resources.");
    }
  }
  else
  {
    sub_1000DA66(v2, "Failed to open a view on the RestartResource table.");
  }
LABEL_50:
  if ( v14 )
    sub_1000A952(v14);
  if ( szComponent )
    sub_1000A952(szComponent);
  if ( lpString )
    sub_1000A952(lpString);
  if ( v2 < 0 )
    v1 = 1603;
  v8 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v8;
}

```

## disassembly

```asm
0x100034ad  push    ebp
0x100034ae  mov     ebp, esp
0x100034b0  sub     esp, 24h
0x100034b3  push    esi
0x100034b4  push    edi
0x100034b5  xor     edi, edi
0x100034b7  push    offset aWixregisterres_0; "WixRegisterRestartResources"
0x100034bc  push    [ebp+hInstall]; hInstall
0x100034bf  mov     [ebp+hAny], edi
0x100034c2  mov     [ebp+hRecord], edi
0x100034c5  mov     [ebp+pcchValueBuf], edi
0x100034c8  mov     [ebp+var_20], edi
0x100034cb  mov     [ebp+lpCriticalSection], edi
0x100034ce  mov     [ebp+var_14], edi
0x100034d1  mov     [ebp+szComponent], edi
0x100034d4  mov     [ebp+lpString], edi
0x100034d7  mov     [ebp+var_24], edi
0x100034da  call    sub_1000D51F
0x100034df  mov     esi, eax
0x100034e1  test    esi, esi
0x100034e3  jns     short loc_100034F7
0x100034e5  push    offset aFailedToInitia_1; "Failed to initialize."
0x100034ea  push    esi
0x100034eb  call    sub_1000DA66
0x100034f0  pop     ecx
0x100034f1  pop     ecx
0x100034f2  jmp     loc_100037B1
0x100034f7  push    offset aWixrestartreso; "WixRestartResource"
0x100034fc  call    sub_1000F18D
0x10003501  test    eax, eax
0x10003503  jz      short loc_10003513
0x10003505  push    offset aTheRestartreso; "The RestartResource table does not exis"...
0x1000350a  push    2
0x1000350c  call    sub_1000D9AB
0x10003511  jmp     short loc_100034F0
0x10003513  lea     eax, [ebp+pcchValueBuf]
0x10003516  push    eax; pcchValueBuf
0x10003517  push    offset aMsirestartmana; "MsiRestartManagerSessionKey"
0x1000351c  call    sub_1000E662
0x10003521  mov     esi, eax
0x10003523  test    esi, esi
0x10003525  jns     short loc_1000352E
0x10003527  push    offset aFailedToGetThe; "Failed to get the MsiRestartManagerSess"...
0x1000352c  jmp     short loc_100034EA
0x1000352e  lea     eax, [ebp+var_20]
0x10003531  push    eax
0x10003532  push    21h ; '!'
0x10003534  push    [ebp+pcchValueBuf]
0x10003537  call    sub_10003447
0x1000353c  mov     esi, eax
0x1000353e  test    esi, esi
0x10003540  jns     short loc_10003549
0x10003542  push    offset aFailedToGetThe_0; "Failed to get the MsiRestartManagerSess"...
0x10003547  jmp     short loc_100034EA
0x10003549  cmp     [ebp+var_20], edi
0x1000354c  jnz     short loc_10003555
0x1000354e  push    offset aTheMsirestartm; "The MsiRestartManagerSessionKey propert"...
0x10003553  jmp     short loc_1000350A
0x10003555  push    [ebp+pcchValueBuf]
0x10003558  lea     eax, [ebp+lpCriticalSection]
0x1000355b  push    eax
0x1000355c  call    sub_1000C245
0x10003561  cmp     eax, 8007007Eh
0x10003566  jnz     short loc_1000357D
0x10003568  push    offset aTheRestartMana; "The Restart Manager is not supported on"...
0x1000356d  push    2
0x1000356f  call    sub_1000D9AB
0x10003574  pop     ecx
0x10003575  pop     ecx
0x10003576  mov     esi, edi
0x10003578  jmp     loc_100037B1
0x1000357d  test    eax, eax
0x1000357f  jns     short loc_10003595
0x10003581  push    [ebp+pcchValueBuf]
0x10003584  push    offset aFailedToJoinTh; "Failed to join the existing Restart Man"...
0x10003589  push    2
0x1000358b  call    sub_1000D9AB
0x10003590  add     esp, 0Ch
0x10003593  jmp     short loc_10003576
0x10003595  cmp     [ebp+hAny], edi
0x10003598  jz      short loc_100035A2
0x1000359a  push    [ebp+hAny]; hAny
0x1000359d  call    MsiCloseHandle
0x100035a2  lea     eax, [ebp+hAny]
0x100035a5  push    eax; phView
0x100035a6  push    off_10033008; szQuery
0x100035ac  call    sub_1000ED03
0x100035b1  mov     esi, eax
0x100035b3  test    esi, esi
0x100035b5  jns     short loc_100035C1
0x100035b7  push    offset aFailedToOpenAV; "Failed to open a view on the RestartRes"...
0x100035bc  jmp     loc_100034EA
0x100035c1  push    ebx
0x100035c2  xor     ebx, ebx
0x100035c4  inc     ebx
0x100035c5  cmp     [ebp+hRecord], edi
0x100035c8  jz      short loc_100035D2
0x100035ca  push    [ebp+hRecord]; hAny
0x100035cd  call    MsiCloseHandle
0x100035d2  lea     eax, [ebp+hRecord]
0x100035d5  mov     [ebp+hRecord], edi
0x100035d8  push    eax; phRecord
0x100035d9  push    [ebp+hAny]; hView
0x100035dc  call    sub_1000E2AE
0x100035e1  test    eax, eax
0x100035e3  jnz     loc_1000377B
0x100035e9  lea     eax, [ebp+var_14]
0x100035ec  push    eax; pcchValueBuf
0x100035ed  push    ebx; iField
0x100035ee  push    [ebp+hRecord]; hRecord
0x100035f1  call    sub_1000E9ED
0x100035f6  mov     esi, eax
0x100035f8  test    esi, esi
0x100035fa  js      loc_10003771
0x10003600  lea     eax, [ebp+szComponent]
0x10003603  push    eax; pcchValueBuf
0x10003604  push    2; iField
0x10003606  push    [ebp+hRecord]; hRecord
0x10003609  call    sub_1000E9ED
0x1000360e  mov     esi, eax
0x10003610  test    esi, esi
0x10003612  js      loc_10003767
0x10003618  lea     eax, [ebp+lpString]
0x1000361b  push    eax; pcchResultBuf
0x1000361c  push    3; iField
0x1000361e  push    [ebp+hRecord]; hRecord
0x10003621  call    sub_1000E78C
0x10003626  mov     esi, eax
0x10003628  test    esi, esi
0x1000362a  js      loc_1000375D
0x10003630  lea     eax, [ebp+var_24]
0x10003633  push    eax; int
0x10003634  push    4; iField
0x10003636  push    [ebp+hRecord]; hRecord
0x10003639  call    sub_1000E8E1
0x1000363e  mov     esi, eax
0x10003640  test    esi, esi
0x10003642  js      loc_10003753
0x10003648  push    2; iField
0x1000364a  push    [ebp+hRecord]; hRecord
0x1000364d  call    MsiRecordIsNull
0x10003652  push    [ebp+szComponent]; szComponent
0x10003655  mov     esi, eax
0x10003657  call    sub_1000E355
0x1000365c  test    esi, esi
0x1000365e  jnz     short loc_1000367A
0x10003660  test    eax, eax
0x10003662  jnz     short loc_1000367A
0x10003664  push    [ebp+var_14]
0x10003667  push    offset aSkippingResour; "Skipping resource %ls."
0x1000366c  push    ebx
0x1000366d  call    sub_1000D9AB
0x10003672  add     esp, 0Ch
0x10003675  jmp     loc_100035C5
0x1000367a  mov     ecx, [ebp+var_24]
0x1000367d  and     ecx, 0Fh
0x10003680  mov     eax, ecx
0x10003682  sub     eax, 1
0x10003685  jz      loc_10003726
0x1000368b  sub     eax, 1
0x1000368e  jz      short loc_100036E2
0x10003690  sub     eax, 1
0x10003693  jz      short loc_100036AC
0x10003695  push    [ebp+var_14]
0x10003698  push    ecx
0x10003699  push    offset aTheResourceTyp; "The resource type %d for %ls is not sup"...
0x1000369e  push    ebx
0x1000369f  call    sub_1000D9AB
0x100036a4  add     esp, 10h
0x100036a7  jmp     loc_100035C5
0x100036ac  push    [ebp+lpString]
0x100036af  push    offset aRegisteringSer; "Registering service name %ls with the R"...
0x100036b4  push    ebx
0x100036b5  call    sub_1000D9AB
0x100036ba  add     esp, 0Ch
0x100036bd  push    [ebp+lpString]; lpString
0x100036c0  push    [ebp+lpCriticalSection]; lpCriticalSection
0x100036c3  call    sub_1000C130
0x100036c8  mov     esi, eax
0x100036ca  test    esi, esi
0x100036cc  jns     loc_100035C5
0x100036d2  push    offset aFailedToRegist; "Failed to register the service name wit"...
0x100036d7  push    esi
0x100036d8  call    sub_1000DA66
0x100036dd  jmp     loc_100037AE
0x100036e2  push    [ebp+lpString]
0x100036e5  push    offset aRegisteringPro; "Registering process name %ls with the R"...
0x100036ea  push    ebx
0x100036eb  call    sub_1000D9AB
0x100036f0  add     esp, 0Ch
0x100036f3  push    [ebp+lpString]
0x100036f6  push    [ebp+lpCriticalSection]
0x100036f9  call    sub_1000C0BE
0x100036fe  mov     esi, eax
0x10003700  cmp     esi, 80070490h
0x10003706  jnz     short loc_10003717
0x10003708  push    [ebp+lpString]
0x1000370b  push    offset aTheProcessLsCo; "The process, %ls, could not be register"...
0x10003710  push    2
0x10003712  jmp     loc_1000366D
0x10003717  test    esi, esi
0x10003719  jns     loc_100035C5
0x1000371f  push    offset aFailedToRegist_0; "Failed to register the process name wit"...
0x10003724  jmp     short loc_100036D7
0x10003726  push    [ebp+lpString]
0x10003729  push    offset aRegisteringFil; "Registering file name %ls with the Rest"...
0x1000372e  push    ebx
0x1000372f  call    sub_1000D9AB
0x10003734  add     esp, 0Ch
0x10003737  push    [ebp+lpString]; lpString
0x1000373a  push    [ebp+lpCriticalSection]; lpCriticalSection
0x1000373d  call    sub_1000BD8B
0x10003742  mov     esi, eax
0x10003744  test    esi, esi
0x10003746  jns     loc_100035C5
0x1000374c  push    offset aFailedToRegist_1; "Failed to register the file name with t"...
0x10003751  jmp     short loc_100036D7
0x10003753  push    offset aFailedToGetThe_1; "Failed to get the Attributes field valu"...
0x10003758  jmp     loc_100036D7
0x1000375d  push    offset aFailedToGetThe_2; "Failed to get the Resource formatted fi"...
0x10003762  jmp     loc_100036D7
0x10003767  push    offset aFailedToGetThe_3; "Failed to get the Component_ field valu"...
0x1000376c  jmp     loc_100036D7
0x10003771  push    offset aFailedToGetThe_4; "Failed to get the RestartResource field"...
0x10003776  jmp     loc_100036D7
0x1000377b  lea     esi, [eax+7FF8FEFDh]
0x10003781  neg     esi
0x10003783  sbb     esi, esi
0x10003785  and     esi, eax
0x10003787  jge     short loc_10003793
0x10003789  push    offset aFailedWhileLoo_0; "Failed while looping through all rows t"...
0x1000378e  jmp     loc_100036D7
0x10003793  push    [ebp+lpCriticalSection]; lpCriticalSection
0x10003796  call    sub_1000C162
0x1000379b  mov     esi, eax
0x1000379d  test    esi, esi
0x1000379f  jns     short loc_100037B0
0x100037a1  push    offset aFailedToRegist_2; "Failed to register the resources with t"...
0x100037a6  push    ebx
0x100037a7  call    sub_1000D9AB
0x100037ac  mov     esi, edi
0x100037ae  pop     ecx
0x100037af  pop     ecx
0x100037b0  pop     ebx
0x100037b1  cmp     [ebp+var_14], edi
0x100037b4  jz      short loc_100037BE
0x100037b6  push    [ebp+var_14]
0x100037b9  call    sub_1000A952
0x100037be  cmp     [ebp+szComponent], edi
0x100037c1  jz      short loc_100037CB
0x100037c3  push    [ebp+szComponent]
0x100037c6  call    sub_1000A952
0x100037cb  cmp     [ebp+lpString], edi
0x100037ce  jz      short loc_100037D8
0x100037d0  push    [ebp+lpString]
0x100037d3  call    sub_1000A952
0x100037d8  test    esi, esi
0x100037da  jns     short loc_100037E1
0x100037dc  mov     edi, 643h
0x100037e1  push    edi
0x100037e2  call    sub_1000D4AE
0x100037e7  cmp     [ebp+hRecord], 0
0x100037eb  mov     esi, eax
0x100037ed  jz      short loc_100037F7
0x100037ef  push    [ebp+hRecord]; hAny
0x100037f2  call    MsiCloseHandle
0x100037f7  cmp     [ebp+hAny], 0
0x100037fb  jz      short loc_10003805
0x100037fd  push    [ebp+hAny]; hAny
0x10003800  call    MsiCloseHandle
0x10003805  pop     edi
0x10003806  mov     eax, esi
0x10003808  pop     esi
0x10003809  leave
0x1000380a  retn    4
```
