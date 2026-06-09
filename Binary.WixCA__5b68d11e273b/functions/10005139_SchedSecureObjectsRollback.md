# SchedSecureObjectsRollback

- ea: `0x10005139`
- end: `0x1000530d`
- name: `SchedSecureObjectsRollback`
- size: `468`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10003e3c`
- `0x10003e9c`
- `0x100042be`
- `0x10005139`
- `0x1000995c`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e2ae`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ed03`

## string_xrefs

- `0x10005199`: `failed to open view on SecureObjects table`
- `0x1000526f`: `failed to get Component attributes for secure object`
- `0x10005143`: `SchedSecureObjectsRollback`
- `0x10005261`: `failed to get target path of object '%ls' in order to schedule rollback`
- `0x1000524a`: `Failed to store ACL rollback information with error 0x%x - continuing`
- `0x100052a3`: `failed while looping through all objects to schedule rollback for`

## pseudocode

```c
int __stdcall SchedSecureObjectsRollback(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  int v3; // eax
  int v4; // ebx
  int v5; // esi
  LPCWSTR pObjectName; // [esp+8h] [ebp-14h] BYREF
  DWORD pcchValueBuf; // [esp+Ch] [ebp-10h] BYREF
  MSIHANDLE hAny; // [esp+10h] [ebp-Ch] BYREF
  LPCWSTR lpString2; // [esp+14h] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+18h] [ebp-4h] BYREF

  v1 = 0;
  pcchValueBuf = 0;
  lpString2 = 0;
  pObjectName = 0;
  hAny = 0;
  hRecord = 0;
  v2 = sub_1000D51F(hInstall, (int)"SchedSecureObjectsRollback");
  if ( v2 >= 0 )
  {
    v2 = sub_1000ED03(off_10033010, &hAny);
    if ( v2 >= 0 )
    {
      while ( 1 )
      {
        if ( hRecord )
          MsiCloseHandle(hRecord);
        hRecord = 0;
        v3 = sub_1000E2AE(hAny, &hRecord);
        if ( v3 )
          break;
        v2 = sub_1000E9ED(hRecord, 2u, (DWORD)&lpString2);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to get object table");
          goto LABEL_23;
        }
        v4 = sub_10003E3C(lpString2);
        if ( !v4 )
        {
          v2 = -2147024809;
          sub_1000DA66(-2147024809, "unknown SecureObject.Table: %ls");
          goto LABEL_23;
        }
        hInstall = 0;
        v2 = sub_1000E8E1(hRecord, 7u, (int)&hInstall);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to get Component attributes for secure object");
          goto LABEL_23;
        }
        if ( (hInstall & 0x100) == 0 )
        {
          v2 = sub_1000E9ED(hRecord, 1u, (DWORD)&pcchValueBuf);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed to get name of object");
            goto LABEL_23;
          }
          v2 = sub_10003E9C(v4, (LPCWSTR)pcchValueBuf, (DWORD)&pObjectName);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed to get target path of object '%ls' in order to schedule rollback");
            goto LABEL_23;
          }
          if ( sub_100042BE(pObjectName, lpString2) < 0 )
            sub_1000D9AB(2, "Failed to store ACL rollback information with error 0x%x - continuing");
        }
      }
      v2 = v3 != -2147024637 ? v3 : 0;
      if ( v2 < 0 )
        sub_1000DA66(v2, "failed while looping through all objects to schedule rollback for");
    }
    else
    {
      sub_1000DA66(v2, "failed to open view on SecureObjects table");
    }
  }
  else
  {
    sub_1000DA66(v2, "failed to initialize");
  }
LABEL_23:
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpString2 )
    sub_1000A952(lpString2);
  if ( pObjectName )
    sub_1000A952(pObjectName);
  if ( v2 < 0 )
    v1 = 1603;
  v5 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v5;
}

```

## disassembly

```asm
0x10005139  push    ebp
0x1000513a  mov     ebp, esp
0x1000513c  sub     esp, 14h
0x1000513f  push    esi
0x10005140  push    edi
0x10005141  xor     edi, edi
0x10005143  push    offset aSchedsecureobj_2; "SchedSecureObjectsRollback"
0x10005148  push    [ebp+hInstall]; hInstall
0x1000514b  mov     [ebp+pcchValueBuf], edi
0x1000514e  mov     [ebp+lpString2], edi
0x10005151  mov     [ebp+pObjectName], edi
0x10005154  mov     [ebp+hAny], edi
0x10005157  mov     [ebp+hRecord], edi
0x1000515a  call    sub_1000D51F
0x1000515f  mov     esi, eax
0x10005161  test    esi, esi
0x10005163  jns     short loc_10005177
0x10005165  push    offset aFailedToInitia_2; "failed to initialize"
0x1000516a  push    esi
0x1000516b  call    sub_1000DA66
0x10005170  pop     ecx
0x10005171  pop     ecx
0x10005172  jmp     loc_100052B1
0x10005177  cmp     [ebp+hAny], edi
0x1000517a  jz      short loc_10005184
0x1000517c  push    [ebp+hAny]; hAny
0x1000517f  call    MsiCloseHandle
0x10005184  lea     eax, [ebp+hAny]
0x10005187  push    eax; phView
0x10005188  push    off_10033010; szQuery
0x1000518e  call    sub_1000ED03
0x10005193  mov     esi, eax
0x10005195  test    esi, esi
0x10005197  jns     short loc_100051A0
0x10005199  push    offset aFailedToOpenVi_4; "failed to open view on SecureObjects ta"...
0x1000519e  jmp     short loc_1000516A
0x100051a0  push    ebx
0x100051a1  cmp     [ebp+hRecord], edi
0x100051a4  jz      short loc_100051AE
0x100051a6  push    [ebp+hRecord]; hAny
0x100051a9  call    MsiCloseHandle
0x100051ae  lea     eax, [ebp+hRecord]
0x100051b1  mov     [ebp+hRecord], edi
0x100051b4  push    eax; phRecord
0x100051b5  push    [ebp+hAny]; hView
0x100051b8  call    sub_1000E2AE
0x100051bd  test    eax, eax
0x100051bf  jnz     loc_10005295
0x100051c5  lea     eax, [ebp+lpString2]
0x100051c8  push    eax; pcchValueBuf
0x100051c9  push    2; iField
0x100051cb  push    [ebp+hRecord]; hRecord
0x100051ce  call    sub_1000E9ED
0x100051d3  mov     esi, eax
0x100051d5  test    esi, esi
0x100051d7  js      loc_1000528E
0x100051dd  push    [ebp+lpString2]; lpString2
0x100051e0  call    sub_10003E3C
0x100051e5  mov     ebx, eax
0x100051e7  test    ebx, ebx
0x100051e9  jz      loc_10005276
0x100051ef  lea     eax, [ebp+hInstall]
0x100051f2  mov     [ebp+hInstall], edi
0x100051f5  push    eax; int
0x100051f6  push    7; iField
0x100051f8  push    [ebp+hRecord]; hRecord
0x100051fb  call    sub_1000E8E1
0x10005200  mov     esi, eax
0x10005202  test    esi, esi
0x10005204  js      short loc_1000526F
0x10005206  test    [ebp+hInstall], 100h
0x1000520d  jnz     short loc_100051A1
0x1000520f  lea     eax, [ebp+pcchValueBuf]
0x10005212  push    eax; pcchValueBuf
0x10005213  push    1; iField
0x10005215  push    [ebp+hRecord]; hRecord
0x10005218  call    sub_1000E9ED
0x1000521d  mov     esi, eax
0x1000521f  test    esi, esi
0x10005221  js      short loc_10005268
0x10005223  lea     eax, [ebp+pObjectName]
0x10005226  push    eax; pcchPathBuf
0x10005227  push    [ebp+pcchValueBuf]; szValue
0x1000522a  push    ebx; int
0x1000522b  call    sub_10003E9C
0x10005230  mov     esi, eax
0x10005232  test    esi, esi
0x10005234  js      short loc_1000525E
0x10005236  push    [ebp+lpString2]; lpString2
0x10005239  push    [ebp+pObjectName]; pObjectName
0x1000523c  call    sub_100042BE
0x10005241  test    eax, eax
0x10005243  jns     loc_100051A1
0x10005249  push    eax
0x1000524a  push    offset aFailedToStoreA; "Failed to store ACL rollback informatio"...
0x1000524f  push    2
0x10005251  call    sub_1000D9AB
0x10005256  add     esp, 0Ch
0x10005259  jmp     loc_100051A1
0x1000525e  push    [ebp+pcchValueBuf]
0x10005261  push    offset aFailedToGetTar_2; "failed to get target path of object '%l"...
0x10005266  jmp     short loc_10005283
0x10005268  push    offset aFailedToGetNam; "failed to get name of object"
0x1000526d  jmp     short loc_100052A8
0x1000526f  push    offset aFailedToGetCom_2; "failed to get Component attributes for "...
0x10005274  jmp     short loc_100052A8
0x10005276  push    [ebp+lpString2]
0x10005279  mov     esi, 80070057h
0x1000527e  push    offset aUnknownSecureo; "unknown SecureObject.Table: %ls"
0x10005283  push    esi
0x10005284  call    sub_1000DA66
0x10005289  add     esp, 0Ch
0x1000528c  jmp     short loc_100052B0
0x1000528e  push    offset aFailedToGetObj; "failed to get object table"
0x10005293  jmp     short loc_100052A8
0x10005295  lea     esi, [eax+7FF8FEFDh]
0x1000529b  neg     esi
0x1000529d  sbb     esi, esi
0x1000529f  and     esi, eax
0x100052a1  jge     short loc_100052B0
0x100052a3  push    offset aFailedWhileLoo_3; "failed while looping through all object"...
0x100052a8  push    esi
0x100052a9  call    sub_1000DA66
0x100052ae  pop     ecx
0x100052af  pop     ecx
0x100052b0  pop     ebx
0x100052b1  cmp     [ebp+pcchValueBuf], edi
0x100052b4  jz      short loc_100052BE
0x100052b6  push    [ebp+pcchValueBuf]
0x100052b9  call    sub_1000A952
0x100052be  cmp     [ebp+lpString2], edi
0x100052c1  jz      short loc_100052CB
0x100052c3  push    [ebp+lpString2]
0x100052c6  call    sub_1000A952
0x100052cb  cmp     [ebp+pObjectName], edi
0x100052ce  jz      short loc_100052D8
0x100052d0  push    [ebp+pObjectName]
0x100052d3  call    sub_1000A952
0x100052d8  test    esi, esi
0x100052da  jns     short loc_100052E1
0x100052dc  mov     edi, 643h
0x100052e1  push    edi
0x100052e2  call    sub_1000D4AE
0x100052e7  cmp     [ebp+hRecord], 0
0x100052eb  mov     esi, eax
0x100052ed  jz      short loc_100052F7
0x100052ef  push    [ebp+hRecord]; hAny
0x100052f2  call    MsiCloseHandle
0x100052f7  cmp     [ebp+hAny], 0
0x100052fb  jz      short loc_10005305
0x100052fd  push    [ebp+hAny]; hAny
0x10005300  call    MsiCloseHandle
0x10005305  pop     edi
0x10005306  mov     eax, esi
0x10005308  pop     esi
0x10005309  leave
0x1000530a  retn    4
```
