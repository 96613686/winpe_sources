# getStateString

- ea: `0x1800a1308`
- end: `0x1800a1556`
- name: `getStateString`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007f370`
- `0x1800ac970`

## callees

- `0x1800a1308`

## string_xrefs

- `0x1800a1361`: `ConfigRequest`
- `0x1800a1359`: `ConfigInprogress`
- `0x1800a1351`: `ConfigInProgressAsyncPending`
- `0x1800a1349`: `DeleteRequest`
- `0x1800a1371`: `DeleteInprogress`
- `0x1800a1422`: `CDNDownloadedCookConfigurationSuccess`
- `0x1800a1412`: `ConstructURIStorageSuccess`
- `0x1800a1402`: `ConfigCompletedSuccess`
- `0x1800a13fa`: `ConfigCompletedError`
- `0x1800a13f2`: `ConfigInfraError`
- `0x1800a13ea`: `ConfigCompletedSuccessNoRefresh`
- `0x1800a1432`: `ConfigCompletedErrorConflictsDetected`
- `0x1800a148d`: `ConfigCompletedErrorInstanceDataRequired`
- `0x1800a1485`: `DeleteCompletedSuccess`
- `0x1800a147d`: `DeleteCompletedError`
- `0x1800a1475`: `DeleteInfraError`
- `0x1800a146d`: `GetCompletedSuccess`
- `0x1800a1495`: `GetCompletedError`
- `0x1800a14d1`: `CDNDownloadFailedBitsCompleteError`
- `0x1800a1546`: `CDNDownloadFailedCreateBitsJob`
- `0x1800a152e`: `CDNDownloadedConfigurationError`
- `0x1800a1526`: `CDNDownloadedCookConfigurationError`
- `0x1800a151e`: `ConstructURIStorageError`

## pseudocode

```c
const wchar_t *__fastcall getStateString(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx

  if ( a1 <= 0x40 )
  {
    if ( a1 == 64 )
      return L"ConfigCompletedErrorConflictsDetected";
    if ( a1 > 0x20 )
    {
      v8 = a1 - 34;
      if ( !v8 )
        return L"CDNDownloadPendingRetry";
      v9 = v8 - 1;
      if ( !v9 )
        return L"CDNDownloadedCookConfigurationSuccess";
      v10 = v9 - 1;
      if ( !v10 )
        return L"CDNDownloadedParseDocumentSuccess";
      v11 = v10 - 4;
      if ( !v11 )
        return L"ConstructURIStorageSuccess";
      v12 = v11 - 1;
      if ( !v12 )
        return L"DocMissingInstanceData";
      v13 = v12 - 19;
      if ( !v13 )
        return L"ConfigCompletedSuccess";
      v14 = v13 - 1;
      if ( !v14 )
        return L"ConfigCompletedError";
      v15 = v14 - 1;
      if ( !v15 )
        return L"ConfigInfraError";
      if ( v15 == 1 )
        return L"ConfigCompletedSuccessNoRefresh";
    }
    else
    {
      if ( a1 == 32 )
        return L"CDNDownloaded";
      if ( a1 > 0xB )
      {
        v5 = a1 - 20;
        if ( !v5 )
          return L"GetRequest";
        v6 = v5 - 1;
        if ( !v6 )
          return L"GetInprogress";
        v7 = v6 - 9;
        if ( !v7 )
          return L"CDNDownload";
        if ( v7 == 1 )
          return L"CDNDownloading";
      }
      else
      {
        if ( a1 == 11 )
          return L"DeleteInprogress";
        if ( !a1 )
          return L"NotDefined";
        v1 = a1 - 1;
        if ( !v1 )
          return L"ConfigRequest";
        v2 = v1 - 1;
        if ( !v2 )
          return L"ConfigInprogress";
        v3 = v2 - 1;
        if ( !v3 )
          return L"ConfigInProgressAsyncPending";
        if ( v3 == 7 )
          return L"DeleteRequest";
      }
    }
    return L"invalid";
  }
  if ( a1 <= 0x5D )
  {
    if ( a1 == 93 )
      return L"CDNDownloadFailedBitsCompleteError";
    if ( a1 > 0x51 )
    {
      v20 = a1 - 82;
      if ( !v20 )
        return L"GetInfraError";
      v21 = v20 - 8;
      if ( !v21 )
        return L"CDNDownloadedParseDocumentError";
      v22 = v21 - 1;
      if ( !v22 )
        return L"CDNDownloadFailedBitsGenericError";
      if ( v22 == 1 )
        return L"CDNDownloadFailedBitsCancelled";
    }
    else
    {
      if ( a1 == 81 )
        return L"GetCompletedError";
      v16 = a1 - 67;
      if ( !v16 )
        return L"ConfigCompletedErrorInstanceDataRequired";
      v17 = v16 - 3;
      if ( !v17 )
        return L"DeleteCompletedSuccess";
      v18 = v17 - 1;
      if ( !v18 )
        return L"DeleteCompletedError";
      v19 = v18 - 1;
      if ( !v19 )
        return L"DeleteInfraError";
      if ( v19 == 8 )
        return L"GetCompletedSuccess";
    }
    return L"invalid";
  }
  v23 = a1 - 94;
  if ( !v23 )
    return L"CDNDownloadFailedAfterRetry";
  v24 = v23 - 1;
  if ( !v24 )
    return L"CDNDownloadFailedCreateBitsJob";
  v25 = v24 - 1;
  if ( !v25 )
    return L"CDNDownloadFailedWininetTimeout";
  v26 = v25 - 1;
  if ( !v26 )
    return L"CDNDownloadFailedWininetNameNotResolved";
  v27 = v26 - 1;
  if ( !v27 )
    return L"CDNDownloadedConfigurationError";
  v28 = v27 - 1;
  if ( !v28 )
    return L"CDNDownloadedCookConfigurationError";
  v29 = v28 - 3;
  if ( !v29 )
    return L"ConstructURIStorageError";
  v30 = v29 - 8;
  if ( !v30 )
    return L"ProcessOrchestrationInformationSuccess";
  if ( v30 != 1 )
    return L"invalid";
  return L"ProcessOrchestrationInformationFailure";
}

```

## disassembly

```asm
0x1800a1308  cmp     ecx, 40h ; '@'
0x1800a130b  ja      loc_1800A143A
0x1800a1311  jz      loc_1800A1432
0x1800a1317  cmp     ecx, 20h ; ' '
0x1800a131a  ja      loc_1800A13B9
0x1800a1320  jz      loc_1800A13B1
0x1800a1326  cmp     ecx, 0Bh
0x1800a1329  ja      short loc_1800A1379
0x1800a132b  jz      short loc_1800A1371
0x1800a132d  test    ecx, ecx
0x1800a132f  jz      short loc_1800A1369
0x1800a1331  sub     ecx, 1
0x1800a1334  jz      short loc_1800A1361
0x1800a1336  sub     ecx, 1
0x1800a1339  jz      short loc_1800A1359
0x1800a133b  sub     ecx, 1
0x1800a133e  jz      short loc_1800A1351
0x1800a1340  cmp     ecx, 7
0x1800a1343  jnz     loc_1800A1506
0x1800a1349  lea     rax, aDeleterequest; "DeleteRequest"
0x1800a1350  retn
0x1800a1351  lea     rax, aConfiginprogre; "ConfigInProgressAsyncPending"
0x1800a1358  retn
0x1800a1359  lea     rax, aConfiginprogre_0; "ConfigInprogress"
0x1800a1360  retn
0x1800a1361  lea     rax, aConfigrequest; "ConfigRequest"
0x1800a1368  retn
0x1800a1369  lea     rax, aNotdefined; "NotDefined"
0x1800a1370  retn
0x1800a1371  lea     rax, aDeleteinprogre; "DeleteInprogress"
0x1800a1378  retn
0x1800a1379  sub     ecx, 14h
0x1800a137c  jz      short loc_1800A13A9
0x1800a137e  sub     ecx, 1
0x1800a1381  jz      short loc_1800A13A1
0x1800a1383  sub     ecx, 9
0x1800a1386  jz      short loc_1800A1399
0x1800a1388  cmp     ecx, 1
0x1800a138b  jnz     loc_1800A1506
0x1800a1391  lea     rax, aCdndownloading; "CDNDownloading"
0x1800a1398  retn
0x1800a1399  lea     rax, aCdndownload; "CDNDownload"
0x1800a13a0  retn
0x1800a13a1  lea     rax, aGetinprogress; "GetInprogress"
0x1800a13a8  retn
0x1800a13a9  lea     rax, aGetrequest; "GetRequest"
0x1800a13b0  retn
0x1800a13b1  lea     rax, aCdndownloaded; "CDNDownloaded"
0x1800a13b8  retn
0x1800a13b9  sub     ecx, 22h ; '"'
0x1800a13bc  jz      short loc_1800A142A
0x1800a13be  sub     ecx, 1
0x1800a13c1  jz      short loc_1800A1422
0x1800a13c3  sub     ecx, 1
0x1800a13c6  jz      short loc_1800A141A
0x1800a13c8  sub     ecx, 4
0x1800a13cb  jz      short loc_1800A1412
0x1800a13cd  sub     ecx, 1
0x1800a13d0  jz      short loc_1800A140A
0x1800a13d2  sub     ecx, 13h
0x1800a13d5  jz      short loc_1800A1402
0x1800a13d7  sub     ecx, 1
0x1800a13da  jz      short loc_1800A13FA
0x1800a13dc  sub     ecx, 1
0x1800a13df  jz      short loc_1800A13F2
0x1800a13e1  cmp     ecx, 1
0x1800a13e4  jnz     loc_1800A1506
0x1800a13ea  lea     rax, aConfigcomplete_1; "ConfigCompletedSuccessNoRefresh"
0x1800a13f1  retn
0x1800a13f2  lea     rax, aConfiginfraerr; "ConfigInfraError"
0x1800a13f9  retn
0x1800a13fa  lea     rax, aConfigcomplete; "ConfigCompletedError"
0x1800a1401  retn
0x1800a1402  lea     rax, aConfigcomplete_0; "ConfigCompletedSuccess"
0x1800a1409  retn
0x1800a140a  lea     rax, aDocmissinginst; "DocMissingInstanceData"
0x1800a1411  retn
0x1800a1412  lea     rax, aConstructurist; "ConstructURIStorageSuccess"
0x1800a1419  retn
0x1800a141a  lea     rax, aCdndownloadedp_0; "CDNDownloadedParseDocumentSuccess"
0x1800a1421  retn
0x1800a1422  lea     rax, aCdndownloadedc_1; "CDNDownloadedCookConfigurationSuccess"
0x1800a1429  retn
0x1800a142a  lea     rax, aCdndownloadpen; "CDNDownloadPendingRetry"
0x1800a1431  retn
0x1800a1432  lea     rax, aConfigcomplete_2; "ConfigCompletedErrorConflictsDetected"
0x1800a1439  retn
0x1800a143a  cmp     ecx, 5Dh ; ']'
0x1800a143d  ja      loc_1800A14D9
0x1800a1443  jz      loc_1800A14D1
0x1800a1449  cmp     ecx, 51h ; 'Q'
0x1800a144c  ja      short loc_1800A149D
0x1800a144e  jz      short loc_1800A1495
0x1800a1450  sub     ecx, 43h ; 'C'
0x1800a1453  jz      short loc_1800A148D
0x1800a1455  sub     ecx, 3
0x1800a1458  jz      short loc_1800A1485
0x1800a145a  sub     ecx, 1
0x1800a145d  jz      short loc_1800A147D
0x1800a145f  sub     ecx, 1
0x1800a1462  jz      short loc_1800A1475
0x1800a1464  cmp     ecx, 8
0x1800a1467  jnz     loc_1800A1506
0x1800a146d  lea     rax, aGetcompletedsu; "GetCompletedSuccess"
0x1800a1474  retn
0x1800a1475  lea     rax, aDeleteinfraerr; "DeleteInfraError"
0x1800a147c  retn
0x1800a147d  lea     rax, aDeletecomplete; "DeleteCompletedError"
0x1800a1484  retn
0x1800a1485  lea     rax, aDeletecomplete_0; "DeleteCompletedSuccess"
0x1800a148c  retn
0x1800a148d  lea     rax, aConfigcomplete_3; "ConfigCompletedErrorInstanceDataRequire"...
0x1800a1494  retn
0x1800a1495  lea     rax, aGetcompleteder; "GetCompletedError"
0x1800a149c  retn
0x1800a149d  sub     ecx, 52h ; 'R'
0x1800a14a0  jz      short loc_1800A14C9
0x1800a14a2  sub     ecx, 8
0x1800a14a5  jz      short loc_1800A14C1
0x1800a14a7  sub     ecx, 1
0x1800a14aa  jz      short loc_1800A14B9
0x1800a14ac  cmp     ecx, 1
0x1800a14af  jnz     short loc_1800A1506
0x1800a14b1  lea     rax, aCdndownloadfai_2; "CDNDownloadFailedBitsCancelled"
0x1800a14b8  retn
0x1800a14b9  lea     rax, aCdndownloadfai_1; "CDNDownloadFailedBitsGenericError"
0x1800a14c0  retn
0x1800a14c1  lea     rax, aCdndownloadedp; "CDNDownloadedParseDocumentError"
0x1800a14c8  retn
0x1800a14c9  lea     rax, aGetinfraerror; "GetInfraError"
0x1800a14d0  retn
0x1800a14d1  lea     rax, aCdndownloadfai_5; "CDNDownloadFailedBitsCompleteError"
0x1800a14d8  retn
0x1800a14d9  sub     ecx, 5Eh ; '^'
0x1800a14dc  jz      short loc_1800A154E
0x1800a14de  sub     ecx, 1
0x1800a14e1  jz      short loc_1800A1546
0x1800a14e3  sub     ecx, 1
0x1800a14e6  jz      short loc_1800A153E
0x1800a14e8  sub     ecx, 1
0x1800a14eb  jz      short loc_1800A1536
0x1800a14ed  sub     ecx, 1
0x1800a14f0  jz      short loc_1800A152E
0x1800a14f2  sub     ecx, 1
0x1800a14f5  jz      short loc_1800A1526
0x1800a14f7  sub     ecx, 3
0x1800a14fa  jz      short loc_1800A151E
0x1800a14fc  sub     ecx, 8
0x1800a14ff  jz      short loc_1800A1516
0x1800a1501  cmp     ecx, 1
0x1800a1504  jz      short loc_1800A150E
0x1800a1506  lea     rax, aInvalid; "invalid"
0x1800a150d  retn
0x1800a150e  lea     rax, aProcessorchest_0; "ProcessOrchestrationInformationFailure"
0x1800a1515  retn
0x1800a1516  lea     rax, aProcessorchest; "ProcessOrchestrationInformationSuccess"
0x1800a151d  retn
0x1800a151e  lea     rax, aConstructurist_0; "ConstructURIStorageError"
0x1800a1525  retn
0x1800a1526  lea     rax, aCdndownloadedc; "CDNDownloadedCookConfigurationError"
0x1800a152d  retn
0x1800a152e  lea     rax, aCdndownloadedc_0; "CDNDownloadedConfigurationError"
0x1800a1535  retn
0x1800a1536  lea     rax, aCdndownloadfai_4; "CDNDownloadFailedWininetNameNotResolved"
0x1800a153d  retn
0x1800a153e  lea     rax, aCdndownloadfai; "CDNDownloadFailedWininetTimeout"
0x1800a1545  retn
0x1800a1546  lea     rax, aCdndownloadfai_0; "CDNDownloadFailedCreateBitsJob"
0x1800a154d  retn
0x1800a154e  lea     rax, aCdndownloadfai_3; "CDNDownloadFailedAfterRetry"
0x1800a1555  retn
```
