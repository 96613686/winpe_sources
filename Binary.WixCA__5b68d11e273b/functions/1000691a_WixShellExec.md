# WixShellExec

- ea: `0x1000691a`
- end: `0x100069b8`
- name: `WixShellExec`
- size: `158`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x10006753`
- `0x1000691a`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e3bd`

## pseudocode

```c
int __stdcall WixShellExec(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  LPCWSTR lpFile; // [esp+8h] [ebp-4h] BYREF

  v1 = 0;
  lpFile = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixShellExec");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_10;
  }
  v2 = sub_1000E3BD(L"WixShellExecTarget", (int)&lpFile);
  if ( v2 < 0 )
    goto LABEL_9;
  sub_1000D9AB(1, "WixShellExecTarget is %ls");
  if ( !lpFile || !*lpFile )
  {
    v2 = -2147024809;
LABEL_9:
    sub_1000DA66(v2, "failed to get WixShellExecTarget");
    goto LABEL_10;
  }
  v2 = sub_10006753(lpFile);
  if ( v2 < 0 )
    sub_1000DA66(v2, "failed to launch target");
LABEL_10:
  if ( lpFile )
    sub_1000A952(lpFile);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x1000691a  push    ebp
0x1000691b  mov     ebp, esp
0x1000691d  push    ecx
0x1000691e  push    esi
0x1000691f  push    edi
0x10006920  push    offset aWixshellexec_0; "WixShellExec"
0x10006925  push    [ebp+hInstall]; hInstall
0x10006928  xor     edi, edi
0x1000692a  mov     [ebp+lpFile], edi
0x1000692d  call    sub_1000D51F
0x10006932  mov     esi, eax
0x10006934  test    esi, esi
0x10006936  jns     short loc_1000693F
0x10006938  push    offset aFailedToInitia_2; "failed to initialize"
0x1000693d  jmp     short loc_1000698E
0x1000693f  lea     eax, [ebp+lpFile]
0x10006942  push    eax; int
0x10006943  push    offset aWixshellexecta; "WixShellExecTarget"
0x10006948  call    sub_1000E3BD
0x1000694d  mov     esi, eax
0x1000694f  test    esi, esi
0x10006951  js      short loc_10006989
0x10006953  push    [ebp+lpFile]
0x10006956  push    offset aWixshellexecta_0; "WixShellExecTarget is %ls"
0x1000695b  push    1
0x1000695d  call    sub_1000D9AB
0x10006962  mov     eax, [ebp+lpFile]
0x10006965  add     esp, 0Ch
0x10006968  test    eax, eax
0x1000696a  jz      short loc_10006984
0x1000696c  cmp     [eax], di
0x1000696f  jz      short loc_10006984
0x10006971  push    eax; lpFile
0x10006972  call    sub_10006753
0x10006977  mov     esi, eax
0x10006979  test    esi, esi
0x1000697b  jns     short loc_10006996
0x1000697d  push    offset aFailedToLaunch; "failed to launch target"
0x10006982  jmp     short loc_1000698E
0x10006984  mov     esi, 80070057h
0x10006989  push    offset aFailedToGetWix; "failed to get WixShellExecTarget"
0x1000698e  push    esi
0x1000698f  call    sub_1000DA66
0x10006994  pop     ecx
0x10006995  pop     ecx
0x10006996  cmp     [ebp+lpFile], edi
0x10006999  jz      short loc_100069A3
0x1000699b  push    [ebp+lpFile]
0x1000699e  call    sub_1000A952
0x100069a3  test    esi, esi
0x100069a5  jns     short loc_100069AC
0x100069a7  mov     edi, 643h
0x100069ac  push    edi
0x100069ad  call    sub_1000D4AE
0x100069b2  pop     edi
0x100069b3  pop     esi
0x100069b4  leave
0x100069b5  retn    4
```
