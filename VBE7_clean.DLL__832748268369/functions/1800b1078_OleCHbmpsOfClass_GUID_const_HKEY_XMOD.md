# OleCHbmpsOfClass(_GUID const &,HKEY__ *,XMOD *)

- ea: `0x1800b1078`
- end: `0x1800b12d9`
- name: `?OleCHbmpsOfClass@@YAXAEBU_GUID@@PEAUHKEY__@@PEAUXMOD@@@Z`
- size: `609`
- prototype: `void __fastcall(const struct _GUID *, HKEY, struct XMOD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ff44`
- `0x180081b04`

## callees

- `0x180058c14`
- `0x18005b228`
- `0x1800b01d8`
- `0x1800b061c`
- `0x1800b0cec`
- `0x1800b1078`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `ADVAPI32!RegOpenKeyA` at `0x1800b1146`
- `ADVAPI32!RegOpenKeyA` at `0x1800b1146`
- `ADVAPI32!RegCloseKey` at `0x1800b11a1`
- `ADVAPI32!RegCloseKey` at `0x1800b11a1`
- `ADVAPI32!RegQueryValueA` at `0x1800b1194`
- `ADVAPI32!RegQueryValueA` at `0x1800b11f1`
- `ADVAPI32!RegQueryValueA` at `0x1800b1235`
- `ADVAPI32!RegQueryValueA` at `0x1800b127a`
- `ADVAPI32!RegQueryValueA` at `0x1800b1194`
- `ADVAPI32!RegQueryValueA` at `0x1800b11f1`
- `ADVAPI32!RegQueryValueA` at `0x1800b1235`
- `ADVAPI32!RegQueryValueA` at `0x1800b127a`
- `ole32!CoIsOle1Class` at `0x1800b1122`
- `ole32!CoIsOle1Class` at `0x1800b1122`

## string_xrefs

- `0x1800b12a2`: `OLE2.DLL`
- `0x1800b1188`: `protocol\StdFileEditing\server`

## pseudocode

```c
void __fastcall OleCHbmpsOfClass(const struct _GUID *a1, HKEY a2, struct XMOD *a3)
{
  unsigned int v6; // eax
  HKEY v7; // rbx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS v10; // edi
  LSTATUS v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const CHAR **v15; // rdi
  const CHAR *v16; // rdx
  LONG cbData; // [rsp+20h] [rbp-E0h] BYREF
  LPCSTR lpSubKey; // [rsp+28h] [rbp-D8h] BYREF
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  CHAR Data[2064]; // [rsp+40h] [rbp-C0h] BYREF

  lpSubKey = 0;
  ProgIDFromCLSIDAnsi(a1, (char **)&lpSubKey);
  if ( lpSubKey )
  {
    if ( (int)RbyGetProfileStringSection(0x82Eu, (char *)lpSubKey, Data, 2056) > 0
      && (v6 = _IndexFromEntry(Data), (unsigned int)_FHbmpsOfBitmapFileIndex(Data, v6, a3)) )
    {
      ((void (__fastcall *)(LPMALLOC, LPCSTR))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, lpSubKey);
    }
    else if ( CoIsOle1Class(a1) )
    {
      v7 = phkResult;
      v8 = RegOpenKeyA(HKEY_CLASSES_ROOT, lpSubKey, &phkResult);
      v9 = phkResult;
      v10 = v8;
      if ( v8 )
        v9 = v7;
      phkResult = v9;
      ((void (__fastcall *)(LPMALLOC, LPCSTR))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, lpSubKey);
      if ( v10
        || (cbData = 2056, v11 = RegQueryValueA(phkResult, szEditSrv, Data, &cbData), RegCloseKey(phkResult), v11)
        || !(unsigned int)_FHbmpsOfIconFileIndex(Data, 0, a3) )
      {
LABEL_20:
        _FHbmpsOfIconFileIndex("OLE2.DLL", 0, a3);
      }
    }
    else
    {
      ((void (__fastcall *)(LPMALLOC, LPCSTR))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, lpSubKey);
      cbData = 2056;
      if ( RegQueryValueA(a2, "ToolboxBitmap32", Data, &cbData)
        || (v12 = _IndexFromEntry(Data), !(unsigned int)_FHbmpsOfBitmapFileIndex(Data, v12, a3)) )
      {
        cbData = 2056;
        if ( RegQueryValueA(a2, szDefaultIcon, Data, &cbData)
          || (v13 = _IndexFromEntry(Data), !(unsigned int)_FHbmpsOfIconFileIndex(Data, v13, a3)) )
        {
          v14 = 0;
          v15 = (const CHAR **)off_1803B15C0;
          while ( 1 )
          {
            v16 = *v15;
            cbData = 2056;
            if ( !RegQueryValueA(a2, v16, Data, &cbData) )
            {
              if ( (unsigned int)_FHbmpsOfIconFileIndex(Data, 0, a3) )
                break;
            }
            ++v14;
            ++v15;
            if ( v14 >= 4 )
              goto LABEL_20;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b1078  mov     [rsp-8+arg_18], rbx
0x1800b107d  push    rbp
0x1800b107e  push    rsi
0x1800b107f  push    rdi
0x1800b1080  push    r14
0x1800b1082  push    r15
0x1800b1084  lea     rbp, [rsp-760h]
0x1800b108c  mov     eax, 860h
0x1800b1091  call    _alloca_probe
0x1800b1096  sub     rsp, rax
0x1800b1099  mov     rax, cs:__security_cookie
0x1800b10a0  xor     rax, rsp
0x1800b10a3  mov     [rbp+780h+var_30], rax
0x1800b10aa  and     [rsp+880h+lpSubKey], 0
0x1800b10b0  mov     r14, rdx
0x1800b10b3  lea     rdx, [rsp+880h+lpSubKey]; char **
0x1800b10b8  mov     rsi, r8
0x1800b10bb  mov     rbx, rcx
0x1800b10be  call    ?ProgIDFromCLSIDAnsi@@YAJAEBU_GUID@@PEAPEAD@Z; ProgIDFromCLSIDAnsi(_GUID const &,char * *)
0x1800b10c3  mov     rdx, [rsp+880h+lpSubKey]; char *
0x1800b10c8  test    rdx, rdx
0x1800b10cb  jz      loc_1800B12B3
0x1800b10d1  mov     ecx, 82Eh; unsigned __int16
0x1800b10d6  lea     r8, [rsp+880h+Data]; char *
0x1800b10db  lea     r15d, [rcx-26h]
0x1800b10df  mov     r9d, r15d; int
0x1800b10e2  call    ?RbyGetProfileStringSection@@YAHGPEAD0H@Z; RbyGetProfileStringSection(ushort,char *,char *,int)
0x1800b10e7  test    eax, eax
0x1800b10e9  jle     short loc_1800B111F
0x1800b10eb  lea     rcx, [rsp+880h+Data]; char *
0x1800b10f0  call    ?_IndexFromEntry@@YAIPEAD@Z; _IndexFromEntry(char *)
0x1800b10f5  lea     rcx, [rsp+880h+Data]; char *
0x1800b10fa  mov     r8, rsi; struct XMOD *
0x1800b10fd  mov     edx, eax; unsigned int
0x1800b10ff  call    ?_FHbmpsOfBitmapFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfBitmapFileIndex(char const *,uint,XMOD *)
0x1800b1104  test    eax, eax
0x1800b1106  jz      short loc_1800B111F
0x1800b1108  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x1800b110f  mov     rdx, [rsp+880h+lpSubKey]
0x1800b1114  mov     rax, [rcx]
0x1800b1117  call    qword ptr [rax+28h]
0x1800b111a  jmp     loc_1800B12B3
0x1800b111f  mov     rcx, rbx; rclsid
0x1800b1122  call    cs:__imp_CoIsOle1Class
0x1800b1128  mov     rdx, [rsp+880h+lpSubKey]; lpSubKey
0x1800b112d  test    eax, eax
0x1800b112f  jz      loc_1800B11CB
0x1800b1135  mov     rbx, [rsp+880h+phkResult]
0x1800b113a  lea     r8, [rsp+880h+phkResult]; phkResult
0x1800b113f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800b1146  call    cs:__imp_RegOpenKeyA
0x1800b114c  mov     rcx, [rsp+880h+phkResult]
0x1800b1151  mov     rdx, [rsp+880h+lpSubKey]
0x1800b1156  test    eax, eax
0x1800b1158  mov     edi, eax
0x1800b115a  cmovnz  rcx, rbx
0x1800b115e  mov     [rsp+880h+phkResult], rcx
0x1800b1163  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x1800b116a  mov     r8, [rcx]
0x1800b116d  call    qword ptr [r8+28h]
0x1800b1171  test    edi, edi
0x1800b1173  jnz     loc_1800B12A2
0x1800b1179  mov     rcx, [rsp+880h+phkResult]; hKey
0x1800b117e  lea     r9, [rsp+880h+cbData]; lpcbData
0x1800b1183  lea     r8, [rsp+880h+Data]; lpData
0x1800b1188  lea     rdx, ?szEditSrv@@3PADA; "protocol\\StdFileEditing\\server"
0x1800b118f  mov     [rsp+880h+cbData], r15d
0x1800b1194  call    cs:__imp_RegQueryValueA
0x1800b119a  mov     rcx, [rsp+880h+phkResult]; hKey
0x1800b119f  mov     ebx, eax
0x1800b11a1  call    cs:__imp_RegCloseKey
0x1800b11a7  test    ebx, ebx
0x1800b11a9  jnz     loc_1800B12A2
0x1800b11af  lea     rcx, [rsp+880h+Data]; char *
0x1800b11b4  mov     r8, rsi; struct XMOD *
0x1800b11b7  xor     edx, edx; unsigned int
0x1800b11b9  call    ?_FHbmpsOfIconFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfIconFileIndex(char const *,uint,XMOD *)
0x1800b11be  test    eax, eax
0x1800b11c0  jnz     loc_1800B12B3
0x1800b11c6  jmp     loc_1800B12A2
0x1800b11cb  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x1800b11d2  mov     rax, [rcx]
0x1800b11d5  call    qword ptr [rax+28h]
0x1800b11d8  lea     r9, [rsp+880h+cbData]; lpcbData
0x1800b11dd  lea     r8, [rsp+880h+Data]; lpData
0x1800b11e2  lea     rdx, aToolboxbitmap3; "ToolboxBitmap32"
0x1800b11e9  mov     rcx, r14; hKey
0x1800b11ec  mov     [rsp+880h+cbData], r15d
0x1800b11f1  call    cs:__imp_RegQueryValueA
0x1800b11f7  test    eax, eax
0x1800b11f9  jnz     short loc_1800B121C
0x1800b11fb  lea     rcx, [rsp+880h+Data]; char *
0x1800b1200  call    ?_IndexFromEntry@@YAIPEAD@Z; _IndexFromEntry(char *)
0x1800b1205  lea     rcx, [rsp+880h+Data]; char *
0x1800b120a  mov     r8, rsi; struct XMOD *
0x1800b120d  mov     edx, eax; unsigned int
0x1800b120f  call    ?_FHbmpsOfBitmapFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfBitmapFileIndex(char const *,uint,XMOD *)
0x1800b1214  test    eax, eax
0x1800b1216  jnz     loc_1800B12B3
0x1800b121c  lea     r9, [rsp+880h+cbData]; lpcbData
0x1800b1221  lea     r8, [rsp+880h+Data]; lpData
0x1800b1226  lea     rdx, ?szDefaultIcon@@3PADA; "DefaultIcon"
0x1800b122d  mov     rcx, r14; hKey
0x1800b1230  mov     [rsp+880h+cbData], r15d
0x1800b1235  call    cs:__imp_RegQueryValueA
0x1800b123b  test    eax, eax
0x1800b123d  jnz     short loc_1800B125C
0x1800b123f  lea     rcx, [rsp+880h+Data]; char *
0x1800b1244  call    ?_IndexFromEntry@@YAIPEAD@Z; _IndexFromEntry(char *)
0x1800b1249  lea     rcx, [rsp+880h+Data]; char *
0x1800b124e  mov     r8, rsi; struct XMOD *
0x1800b1251  mov     edx, eax; unsigned int
0x1800b1253  call    ?_FHbmpsOfIconFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfIconFileIndex(char const *,uint,XMOD *)
0x1800b1258  test    eax, eax
0x1800b125a  jnz     short loc_1800B12B3
0x1800b125c  xor     ebx, ebx
0x1800b125e  lea     rdi, off_1803B15C0; "InprocServer32"
0x1800b1265  mov     rdx, [rdi]; lpSubKey
0x1800b1268  lea     r9, [rsp+880h+cbData]; lpcbData
0x1800b126d  lea     r8, [rsp+880h+Data]; lpData
0x1800b1272  mov     rcx, r14; hKey
0x1800b1275  mov     [rsp+880h+cbData], r15d
0x1800b127a  call    cs:__imp_RegQueryValueA
0x1800b1280  test    eax, eax
0x1800b1282  jnz     short loc_1800B1297
0x1800b1284  lea     rcx, [rsp+880h+Data]; char *
0x1800b1289  mov     r8, rsi; struct XMOD *
0x1800b128c  xor     edx, edx; unsigned int
0x1800b128e  call    ?_FHbmpsOfIconFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfIconFileIndex(char const *,uint,XMOD *)
0x1800b1293  test    eax, eax
0x1800b1295  jnz     short loc_1800B12B3
0x1800b1297  inc     ebx
0x1800b1299  add     rdi, 8
0x1800b129d  cmp     ebx, 4
0x1800b12a0  jb      short loc_1800B1265
0x1800b12a2  lea     rcx, aOle2Dll; "OLE2.DLL"
0x1800b12a9  mov     r8, rsi; struct XMOD *
0x1800b12ac  xor     edx, edx; unsigned int
0x1800b12ae  call    ?_FHbmpsOfIconFileIndex@@YAHPEBDIPEAUXMOD@@@Z; _FHbmpsOfIconFileIndex(char const *,uint,XMOD *)
0x1800b12b3  mov     rcx, [rbp+780h+var_30]
0x1800b12ba  xor     rcx, rsp; StackCookie
0x1800b12bd  call    __security_check_cookie
0x1800b12c2  mov     rbx, [rsp+880h+arg_18]
0x1800b12ca  add     rsp, 860h
0x1800b12d1  pop     r15
0x1800b12d3  pop     r14
0x1800b12d5  pop     rdi
0x1800b12d6  pop     rsi
0x1800b12d7  pop     rbp
0x1800b12d8  retn
```
