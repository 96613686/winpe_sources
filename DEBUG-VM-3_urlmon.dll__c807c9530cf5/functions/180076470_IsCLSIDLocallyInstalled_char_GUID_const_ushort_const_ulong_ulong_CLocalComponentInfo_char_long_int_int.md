# IsCLSIDLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,long *,int,int *)

- ea: `0x180076470`
- end: `0x180076793`
- name: `?IsCLSIDLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0PEAJHPEAH@Z`
- size: `803`
- prototype: `int(char *, struct _GUID *const, const unsigned __int16 *, unsigned int, unsigned int, struct CLocalComponentInfo *, char *, int *, int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180076078`

## callees

- `0x180030880`
- `0x1800763a8`
- `0x180076470`
- `0x18007679c`
- `0x180077584`
- `0x18009de50`
- `0x1800c8cd4`
- `0x1800c92ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076506`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076553`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800765c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800765f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076678`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076506`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076553`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800765c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800765f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076678`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007662c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800766b6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007662c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800766b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076773`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076773`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800764d3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800764d3`

## string_xrefs

- `0x1800764f8`: `CLSID`

## pseudocode

```c
__int64 __fastcall IsCLSIDLocallyInstalled(
        char *a1,
        struct _GUID *const a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        struct CLocalComponentInfo *a6,
        char *lpSubKey,
        int *hkey,
        int a9,
        int *phkResult)
{
  int *v10; // r14
  char *v11; // rsi
  int *v12; // rdi
  HRESULT v15; // ebx
  struct CLocalComponentInfo *pvData; // rdi
  unsigned int v17; // r15d
  int v18; // eax
  HKEY v19; // rcx
  const char *v20; // r8
  unsigned int v21; // r9d
  unsigned int v22; // edx
  LPOLESTR lpsz; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD pdwType; // [rsp+90h] [rbp+40h] BYREF
  int v27; // [rsp+94h] [rbp+44h]
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  int v29; // [rsp+A4h] [rbp+54h]

  v29 = HIDWORD(a3);
  v27 = HIDWORD(a1);
  v10 = phkResult;
  v11 = 0;
  v12 = hkey;
  lpSubKey = 0;
  lpsz = 0;
  *phkResult = 0;
  pdwType = 0;
  hKey = 0;
  pcbData = 260;
  if ( v12 )
    *v12 = -2147467259;
  v15 = StringFromCLSID(a2, &lpsz);
  if ( v15 >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey) )
    {
      v15 = Unicode2Ansi(lpsz);
      if ( v15 < 0 )
      {
        v11 = lpSubKey;
        goto LABEL_31;
      }
      phkResult = 0;
      hkey = 0;
      v11 = lpSubKey;
      if ( !RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, (PHKEY)&phkResult) )
      {
        if ( v12 )
          *v12 = 0;
        pvData = a6;
        v17 = a5;
        v18 = CheckInstalledVersionHint((HKEY)phkResult, a6, a4, a5);
        v15 = v18;
        if ( v18 >= 0 )
        {
          if ( v18 == 1 )
            *v10 = 1;
          goto LABEL_19;
        }
        lpSubKey = 0;
        if ( !RegOpenKeyExA((HKEY)phkResult, "AppID", 0, 0x20019u, (PHKEY)&lpSubKey) )
        {
          v19 = (HKEY)lpSubKey;
          v15 = 0;
LABEL_18:
          RegCloseKey(v19);
LABEL_19:
          RegCloseKey((HKEY)phkResult);
          goto LABEL_31;
        }
        if ( RegOpenKeyExA((HKEY)phkResult, "InProcServer32", 0, 0x20019u, (PHKEY)&hkey) )
        {
          if ( RegOpenKeyExA((HKEY)phkResult, "LocalServer32", 0, 0x20019u, (PHKEY)&hkey) )
          {
            v15 = 1;
            goto LABEL_19;
          }
          pcbData = 260;
          if ( RegGetValueA((HKEY)hkey, 0, 0, 0xFFFFu, &pdwType, pvData, &pcbData) )
            goto LABEL_16;
          GetEXEName((char *)pvData, v22);
        }
        else
        {
          pcbData = 260;
          if ( RegGetValueA((HKEY)hkey, 0, 0, 0xFFFFu, &pdwType, pvData, &pcbData) )
            goto LABEL_16;
        }
        if ( SearchPathA_Wrap(0, (const char *)pvData, v20, v21, (LPSTR)pvData, (LPSTR *)pvData + 33) )
        {
          v15 = LocalVersionOK((HKEY)phkResult, pvData, a2, a4, v17, a9);
          if ( v15 == 1 )
            *v10 = 1;
          if ( *((_DWORD *)pvData + 77) )
            v15 = NeedForceLanguageCheck((HKEY)phkResult, pvData);
          goto LABEL_17;
        }
LABEL_16:
        v15 = 1;
LABEL_17:
        v19 = (HKEY)hkey;
        goto LABEL_18;
      }
    }
    v15 = 1;
  }
LABEL_31:
  if ( lpsz )
    operator delete(lpsz);
  if ( v11 )
    operator delete(v11);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180076470  mov     [rsp-38h+arg_8], rbx
0x180076475  mov     qword ptr [rsp-38h+arg_10], r8
0x18007647a  mov     qword ptr [rsp-38h+pdwType], rcx
0x18007647f  push    rbp
0x180076480  push    rsi
0x180076481  push    rdi
0x180076482  push    r12
0x180076484  push    r13
0x180076486  push    r14
0x180076488  push    r15
0x18007648a  mov     rbp, rsp
0x18007648d  sub     rsp, 50h
0x180076491  mov     r14, [rbp+arg_48]
0x180076498  xor     esi, esi
0x18007649a  mov     rdi, [rbp+hkey]
0x18007649e  mov     r13d, r9d
0x1800764a1  mov     [rbp+lpSubKey], rsi
0x1800764a5  mov     r12, rdx
0x1800764a8  mov     [rbp+lpsz], rsi
0x1800764ac  mov     dword ptr [r14], 0
0x1800764b3  mov     [rbp+pdwType], esi
0x1800764b6  mov     [rbp+hKey], rsi
0x1800764ba  mov     [rbp+arg_10], 104h
0x1800764c1  test    rdi, rdi
0x1800764c4  jz      short loc_1800764CC
0x1800764c6  mov     dword ptr [rdi], 80004005h
0x1800764cc  lea     rdx, [rbp+lpsz]; lplpsz
0x1800764d0  mov     rcx, r12; rclsid
0x1800764d3  call    cs:__imp_StringFromCLSID
0x1800764d9  mov     ebx, eax
0x1800764db  test    eax, eax
0x1800764dd  js      loc_18007674F
0x1800764e3  lea     rax, [rbp+hKey]
0x1800764e7  mov     r15d, 20019h
0x1800764ed  mov     r9d, r15d; samDesired
0x1800764f0  mov     [rsp+50h+phkResult], rax; phkResult
0x1800764f5  xor     r8d, r8d; ulOptions
0x1800764f8  lea     rdx, aClsid_3; "CLSID"
0x1800764ff  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180076506  call    cs:__imp_RegOpenKeyExA
0x18007650c  test    eax, eax
0x18007650e  jnz     loc_18007674A
0x180076514  mov     rcx, [rbp+lpsz]; lpWideCharStr
0x180076518  lea     rdx, [rbp+lpSubKey]
0x18007651c  call    Unicode2Ansi
0x180076521  mov     ebx, eax
0x180076523  test    eax, eax
0x180076525  js      loc_180076744
0x18007652b  mov     rcx, [rbp+hKey]; hKey
0x18007652f  lea     rax, [rbp+arg_48]
0x180076536  mov     [rbp+arg_48], rsi
0x18007653d  mov     r9d, r15d; samDesired
0x180076540  mov     [rbp+hkey], rsi
0x180076544  xor     r8d, r8d; ulOptions
0x180076547  mov     rsi, [rbp+lpSubKey]
0x18007654b  mov     rdx, rsi; lpSubKey
0x18007654e  mov     [rsp+50h+phkResult], rax; phkResult
0x180076553  call    cs:__imp_RegOpenKeyExA
0x180076559  test    eax, eax
0x18007655b  jnz     loc_18007674A
0x180076561  test    rdi, rdi
0x180076564  jz      short loc_180076568
0x180076566  mov     [rdi], eax
0x180076568  mov     rdi, [rbp+arg_28]
0x18007656c  mov     r8d, r13d; unsigned int
0x18007656f  mov     r15d, [rbp+arg_20]
0x180076573  mov     rdx, rdi; struct CLocalComponentInfo *
0x180076576  mov     rcx, [rbp+arg_48]; hKey
0x18007657d  mov     r9d, r15d; unsigned int
0x180076580  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x180076585  mov     ebx, eax
0x180076587  test    eax, eax
0x180076589  js      short loc_18007659C
0x18007658b  cmp     eax, 1
0x18007658e  jnz     loc_180076649
0x180076594  mov     [r14], eax
0x180076597  jmp     loc_180076649
0x18007659c  mov     rcx, [rbp+arg_48]; hKey
0x1800765a3  lea     rax, [rbp+lpSubKey]
0x1800765a7  mov     ebx, 20019h
0x1800765ac  mov     [rbp+lpSubKey], 0
0x1800765b4  mov     r9d, ebx; samDesired
0x1800765b7  mov     [rsp+50h+phkResult], rax; phkResult
0x1800765bc  xor     r8d, r8d; ulOptions
0x1800765bf  lea     rdx, aAppid; "AppID"
0x1800765c6  call    cs:__imp_RegOpenKeyExA
0x1800765cc  test    eax, eax
0x1800765ce  jnz     short loc_1800765D8
0x1800765d0  mov     rcx, [rbp+lpSubKey]
0x1800765d4  xor     ebx, ebx
0x1800765d6  jmp     short loc_180076643
0x1800765d8  mov     rcx, [rbp+arg_48]; hKey
0x1800765df  lea     rax, [rbp+hkey]
0x1800765e3  mov     r9d, ebx; samDesired
0x1800765e6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800765eb  xor     r8d, r8d; ulOptions
0x1800765ee  lea     rdx, aInprocserver32_0; "InProcServer32"
0x1800765f5  call    cs:__imp_RegOpenKeyExA
0x1800765fb  test    eax, eax
0x1800765fd  jnz     short loc_18007665B
0x1800765ff  mov     rcx, [rbp+hkey]; hkey
0x180076603  lea     rax, [rbp+arg_10]
0x180076607  mov     [rsp+50h+pcbData], rax; pcbData
0x18007660c  mov     r9d, 0FFFFh; dwFlags
0x180076612  lea     rax, [rbp+pdwType]
0x180076616  mov     [rsp+50h+pvData], rdi; pvData
0x18007661b  xor     r8d, r8d; lpValue
0x18007661e  mov     [rsp+50h+phkResult], rax; pdwType
0x180076623  xor     edx, edx; lpSubKey
0x180076625  mov     [rbp+arg_10], 104h
0x18007662c  call    cs:__imp_RegGetValueA
0x180076632  test    eax, eax
0x180076634  jz      loc_1800766CC
0x18007663a  mov     ebx, 1
0x18007663f  mov     rcx, [rbp+hkey]; hKey
0x180076643  call    cs:__imp_RegCloseKey
0x180076649  mov     rcx, [rbp+arg_48]; hKey
0x180076650  call    cs:__imp_RegCloseKey
0x180076656  jmp     loc_18007674F
0x18007665b  mov     rcx, [rbp+arg_48]; hKey
0x180076662  lea     rax, [rbp+hkey]
0x180076666  mov     r9d, ebx; samDesired
0x180076669  mov     [rsp+50h+phkResult], rax; phkResult
0x18007666e  xor     r8d, r8d; ulOptions
0x180076671  lea     rdx, aLocalserver32_0; "LocalServer32"
0x180076678  call    cs:__imp_RegOpenKeyExA
0x18007667e  test    eax, eax
0x180076680  jz      short loc_180076689
0x180076682  mov     ebx, 1
0x180076687  jmp     short loc_180076649
0x180076689  mov     rcx, [rbp+hkey]; hkey
0x18007668d  lea     rax, [rbp+arg_10]
0x180076691  mov     [rsp+50h+pcbData], rax; pcbData
0x180076696  mov     r9d, 0FFFFh; dwFlags
0x18007669c  lea     rax, [rbp+pdwType]
0x1800766a0  mov     [rsp+50h+pvData], rdi; pvData
0x1800766a5  xor     r8d, r8d; lpValue
0x1800766a8  mov     [rsp+50h+phkResult], rax; pdwType
0x1800766ad  xor     edx, edx; lpSubKey
0x1800766af  mov     [rbp+arg_10], 104h
0x1800766b6  call    cs:__imp_RegGetValueA
0x1800766bc  test    eax, eax
0x1800766be  jnz     loc_18007663A
0x1800766c4  mov     rcx, rdi; char *
0x1800766c7  call    ?GetEXEName@@YAHPEADI@Z; GetEXEName(char *,uint)
0x1800766cc  lea     rax, [rdi+108h]
0x1800766d3  mov     rdx, rdi; char *
0x1800766d6  mov     [rsp+50h+pvData], rax; LPSTR *
0x1800766db  xor     ecx, ecx; char *
0x1800766dd  mov     [rsp+50h+phkResult], rdi; LPSTR
0x1800766e2  call    ?SearchPathA_Wrap@@YAKPEBD00KPEADPEAPEAD@Z; SearchPathA_Wrap(char const *,char const *,char const *,ulong,char *,char * *)
0x1800766e7  test    eax, eax
0x1800766e9  jz      loc_18007663A
0x1800766ef  mov     eax, [rbp+arg_40]
0x1800766f5  mov     r9d, r13d; unsigned int
0x1800766f8  mov     rcx, [rbp+arg_48]; hKey
0x1800766ff  mov     r8, r12; struct _GUID *
0x180076702  mov     dword ptr [rsp+50h+pvData], eax; int
0x180076706  mov     rdx, rdi; struct CLocalComponentInfo *
0x180076709  mov     dword ptr [rsp+50h+phkResult], r15d; unsigned int
0x18007670e  call    ?LocalVersionOK@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@PEAU_GUID@@KKH@Z; LocalVersionOK(HKEY__ *,CLocalComponentInfo *,_GUID *,ulong,ulong,int)
0x180076713  mov     ebx, eax
0x180076715  cmp     eax, 1
0x180076718  jnz     short loc_180076721
0x18007671a  mov     dword ptr [r14], 1
0x180076721  cmp     dword ptr [rdi+134h], 0
0x180076728  jz      loc_18007663F
0x18007672e  mov     rcx, [rbp+arg_48]; HKEY
0x180076735  mov     rdx, rdi; struct CLocalComponentInfo *
0x180076738  call    ?NeedForceLanguageCheck@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@@Z; NeedForceLanguageCheck(HKEY__ *,CLocalComponentInfo *)
0x18007673d  mov     ebx, eax
0x18007673f  jmp     loc_18007663F
0x180076744  mov     rsi, [rbp+lpSubKey]
0x180076748  jmp     short loc_18007674F
0x18007674a  mov     ebx, 1
0x18007674f  mov     rcx, [rbp+lpsz]; void *
0x180076753  test    rcx, rcx
0x180076756  jz      short loc_18007675D
0x180076758  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007675d  test    rsi, rsi
0x180076760  jz      short loc_18007676A
0x180076762  mov     rcx, rsi; void *
0x180076765  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007676a  mov     rcx, [rbp+hKey]; hKey
0x18007676e  test    rcx, rcx
0x180076771  jz      short loc_180076779
0x180076773  call    cs:__imp_RegCloseKey
0x180076779  mov     eax, ebx
0x18007677b  mov     rbx, [rsp+50h+arg_8]
0x180076783  add     rsp, 50h
0x180076787  pop     r15
0x180076789  pop     r14
0x18007678b  pop     r13
0x18007678d  pop     r12
0x18007678f  pop     rdi
0x180076790  pop     rsi
0x180076791  pop     rbp
0x180076792  retn
```
