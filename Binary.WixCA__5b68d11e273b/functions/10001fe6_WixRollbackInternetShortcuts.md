# WixRollbackInternetShortcuts

- ea: `0x10001fe6`
- end: `0x100020f7`
- name: `WixRollbackInternetShortcuts`
- size: `273`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x10001fe6`
- `0x1000a952`
- `0x1000b453`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000e662`
- `0x1000ef44`
- `0x1000efcc`

## string_xrefs

- `0x1000209a`: `failed to read shortcut attributes from custom action data`
- `0x10001ff0`: `WixRemoveInternetShortcuts`
- `0x1000200f`: `failed to initialize WixRemoveInternetShortcuts`
- `0x100020bb`: `failed to read shortcut path from custom action data for rollback`
- `0x100020ab`: `failed to delete file '%ls'`
- `0x100020a1`: `failed to skip shortcut target from custom action data for rollback`

## pseudocode

```c
int __stdcall WixRollbackInternetShortcuts(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  _WORD *v3; // eax
  signed int v4; // eax
  int v6; // [esp+8h] [ebp-10h] BYREF
  DWORD pcchValueBuf; // [esp+Ch] [ebp-Ch] BYREF
  wchar_t SubStr[2]; // [esp+10h] [ebp-8h] BYREF
  LPCWSTR lpFileName; // [esp+14h] [ebp-4h] BYREF

  v1 = 0;
  *(_DWORD *)SubStr = 0;
  pcchValueBuf = 0;
  lpFileName = 0;
  v6 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixRemoveInternetShortcuts");
  if ( v2 >= 0 )
  {
    v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
    if ( v2 >= 0 )
    {
      v3 = (_WORD *)pcchValueBuf;
      *(_DWORD *)SubStr = pcchValueBuf;
      if ( !pcchValueBuf )
        goto LABEL_19;
      while ( *v3 )
      {
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to read shortcut path from custom action data for rollback");
          break;
        }
        v4 = sub_1000B453(lpFileName);
        v2 = v4;
        if ( v4 < 0 )
        {
          sub_1000DA66(v4, "failed to delete file '%ls'");
          break;
        }
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to skip shortcut target from custom action data for rollback");
          break;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&v6);
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to read shortcut attributes from custom action data");
          break;
        }
        v3 = *(_WORD **)SubStr;
        if ( !*(_DWORD *)SubStr )
          break;
      }
    }
    else
    {
      sub_1000DA66(v2, "failed to get CustomActionData");
    }
  }
  else
  {
    sub_1000DA66(v2, "failed to initialize WixRemoveInternetShortcuts");
  }
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
LABEL_19:
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10001fe6  push    ebp
0x10001fe7  mov     ebp, esp
0x10001fe9  sub     esp, 10h
0x10001fec  push    esi
0x10001fed  push    edi
0x10001fee  xor     edi, edi
0x10001ff0  push    offset aWixremoveinter; "WixRemoveInternetShortcuts"
0x10001ff5  push    [ebp+hInstall]; hInstall
0x10001ff8  mov     dword ptr [ebp+SubStr], edi
0x10001ffb  mov     [ebp+pcchValueBuf], edi
0x10001ffe  mov     [ebp+lpFileName], edi
0x10002001  mov     [ebp+var_10], edi
0x10002004  call    sub_1000D51F
0x10002009  mov     esi, eax
0x1000200b  test    esi, esi
0x1000200d  jns     short loc_10002019
0x1000200f  push    offset aFailedToInitia_5; "failed to initialize WixRemoveInternetS"...
0x10002014  jmp     loc_100020C0
0x10002019  lea     eax, [ebp+pcchValueBuf]
0x1000201c  push    eax; pcchValueBuf
0x1000201d  push    offset aCustomactionda; "CustomActionData"
0x10002022  call    sub_1000E662
0x10002027  mov     esi, eax
0x10002029  test    esi, esi
0x1000202b  jns     short loc_10002037
0x1000202d  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10002032  jmp     loc_100020C0
0x10002037  mov     eax, [ebp+pcchValueBuf]
0x1000203a  mov     dword ptr [ebp+SubStr], eax
0x1000203d  test    eax, eax
0x1000203f  jz      loc_100020D5
0x10002045  cmp     [eax], di
0x10002048  jz      short loc_100020C8
0x1000204a  lea     eax, [ebp+lpFileName]
0x1000204d  push    eax; int
0x1000204e  lea     eax, [ebp+SubStr]
0x10002051  push    eax; SubStr
0x10002052  call    sub_1000EFCC
0x10002057  mov     esi, eax
0x10002059  test    esi, esi
0x1000205b  js      short loc_100020BB
0x1000205d  push    [ebp+lpFileName]; lpFileName
0x10002060  call    sub_1000B453
0x10002065  mov     esi, eax
0x10002067  test    esi, esi
0x10002069  js      short loc_100020A8
0x1000206b  lea     eax, [ebp+lpFileName]
0x1000206e  push    eax; int
0x1000206f  lea     eax, [ebp+SubStr]
0x10002072  push    eax; SubStr
0x10002073  call    sub_1000EFCC
0x10002078  mov     esi, eax
0x1000207a  test    esi, esi
0x1000207c  js      short loc_100020A1
0x1000207e  lea     eax, [ebp+var_10]
0x10002081  push    eax; int
0x10002082  lea     eax, [ebp+SubStr]
0x10002085  push    eax; SubStr
0x10002086  call    sub_1000EF44
0x1000208b  mov     esi, eax
0x1000208d  test    esi, esi
0x1000208f  js      short loc_1000209A
0x10002091  mov     eax, dword ptr [ebp+SubStr]
0x10002094  test    eax, eax
0x10002096  jnz     short loc_10002045
0x10002098  jmp     short loc_100020C8
0x1000209a  push    offset aFailedToReadSh_1; "failed to read shortcut attributes from"...
0x1000209f  jmp     short loc_100020C0
0x100020a1  push    offset aFailedToSkipSh; "failed to skip shortcut target from cus"...
0x100020a6  jmp     short loc_100020C0
0x100020a8  push    [ebp+lpFileName]
0x100020ab  push    offset aFailedToDelete; "failed to delete file '%ls'"
0x100020b0  push    esi
0x100020b1  call    sub_1000DA66
0x100020b6  add     esp, 0Ch
0x100020b9  jmp     short loc_100020C8
0x100020bb  push    offset aFailedToReadSh_4; "failed to read shortcut path from custo"...
0x100020c0  push    esi
0x100020c1  call    sub_1000DA66
0x100020c6  pop     ecx
0x100020c7  pop     ecx
0x100020c8  cmp     [ebp+pcchValueBuf], edi
0x100020cb  jz      short loc_100020D5
0x100020cd  push    [ebp+pcchValueBuf]
0x100020d0  call    sub_1000A952
0x100020d5  cmp     [ebp+lpFileName], edi
0x100020d8  jz      short loc_100020E2
0x100020da  push    [ebp+lpFileName]
0x100020dd  call    sub_1000A952
0x100020e2  test    esi, esi
0x100020e4  jns     short loc_100020EB
0x100020e6  mov     edi, 643h
0x100020eb  push    edi
0x100020ec  call    sub_1000D4AE
0x100020f1  pop     edi
0x100020f2  pop     esi
0x100020f3  leave
0x100020f4  retn    4
```
