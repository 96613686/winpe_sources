# SuplNode::GetBinaryRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x180117fbc`
- end: `0x180118182`
- name: `?GetBinaryRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `454`
- prototype: `int(SuplNode *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18011885c`

## callees

- `0x1800a98c0`
- `0x1800aa594`
- `0x180117fbc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801180eb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801180eb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180118151`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180118151`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180118100`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180118100`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011811f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011811f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118148`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118022`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011806d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801180c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011806d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801180c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180118094`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180118094`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011815a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011815a`

## pseudocode

```c
__int64 __fastcall SuplNode::GetBinaryRegValue(
        SuplNode *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *a5)
{
  BYTE *v6; // rsi
  SAFEARRAY *v7; // rdi
  LSTATUS v8; // eax
  int v9; // ebx
  bool v10; // cc
  SAFEARRAY *v11; // rax
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  void *ppvData; // [rsp+40h] [rbp-20h] BYREF
  DWORD Type; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  hKey = 0;
  v6 = 0;
  cbData = 4;
  Type = 0;
  rgsabound = 0;
  ppvData = 0;
  v7 = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_2;
  v10 = v8 <= 0;
  if ( v8 )
    goto LABEL_4;
  v8 = RegQueryValueExW(hKey, a4, 0, &Type, 0, &cbData);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_2;
  v10 = v8 <= 0;
  if ( v8 )
    goto LABEL_4;
  if ( Type != 3 )
  {
LABEL_2:
    v9 = -2046820350;
    goto LABEL_17;
  }
  if ( !cbData )
    goto LABEL_17;
  v6 = (BYTE *)LocalAlloc(v8 + 64, cbData);
  if ( !v6 )
    goto LABEL_11;
  v8 = RegQueryValueExW(hKey, a4, 0, &Type, v6, &cbData);
  v9 = v8;
  v10 = v8 <= 0;
  if ( v8 )
  {
LABEL_4:
    if ( !v10 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_17;
  }
  rgsabound.cElements = cbData;
  rgsabound.lLbound = 0;
  v11 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v7 = v11;
  if ( !v11 )
  {
LABEL_11:
    v9 = -2147024882;
    goto LABEL_17;
  }
  v9 = SafeArrayAccessData(v11, &ppvData);
  if ( v9 >= 0 )
  {
    memcpy_0(ppvData, v6, cbData);
    v9 = SafeArrayUnaccessData(v7);
    if ( v9 >= 0 )
    {
      a5->llVal = (LONGLONG)v7;
      v7 = 0;
      ppvData = 0;
      a5->vt = 8209;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  SafeArrayDestroy(v7);
  LocalFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180117fbc  mov     [rsp-28h+arg_0], rbx
0x180117fc1  push    rbp
0x180117fc2  push    rsi
0x180117fc3  push    rdi
0x180117fc4  push    r14
0x180117fc6  push    r15
0x180117fc8  mov     rbp, rsp
0x180117fcb  sub     rsp, 60h
0x180117fcf  mov     rax, cs:__security_cookie
0x180117fd6  xor     rax, rsp
0x180117fd9  mov     [rbp+var_8], rax
0x180117fdd  mov     r14, [rbp+arg_20]
0x180117fe1  lea     rcx, [rbp+hKey]
0x180117fe5  mov     [rsp+60h+phkResult], rcx; phkResult
0x180117fea  mov     r15, r9
0x180117fed  mov     rdx, r8; lpSubKey
0x180117ff0  mov     [rbp+hKey], 0
0x180117ff8  xor     esi, esi
0x180117ffa  mov     [rbp+cbData], 4
0x180118001  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180118008  mov     [rbp+Type], 0
0x18011800f  mov     r9d, 20019h; samDesired
0x180118015  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x180118019  xor     r8d, r8d; ulOptions
0x18011801c  mov     [rbp+ppvData], rsi
0x180118020  xor     edi, edi
0x180118022  call    cs:__imp_RegOpenKeyExW
0x180118028  mov     ebx, eax
0x18011802a  cmp     eax, 2
0x18011802d  jnz     short loc_180118039
0x18011802f  mov     ebx, 86000002h
0x180118034  jmp     loc_18011813F
0x180118039  test    eax, eax
0x18011803b  jz      short loc_180118051
0x18011803d  jle     loc_18011813F
0x180118043  movzx   ebx, ax
0x180118046  or      ebx, 80070000h
0x18011804c  jmp     loc_18011813F
0x180118051  mov     rcx, [rbp+hKey]; hKey
0x180118055  lea     rax, [rbp+cbData]
0x180118059  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18011805e  lea     r9, [rbp+Type]; lpType
0x180118062  xor     r8d, r8d; lpReserved
0x180118065  mov     [rsp+60h+phkResult], rsi; lpData
0x18011806a  mov     rdx, r15; lpValueName
0x18011806d  call    cs:__imp_RegQueryValueExW
0x180118073  mov     ebx, eax
0x180118075  cmp     eax, 2
0x180118078  jz      short loc_18011802F
0x18011807a  test    eax, eax
0x18011807c  jnz     short loc_18011803D
0x18011807e  cmp     [rbp+Type], 3
0x180118082  jnz     short loc_18011802F
0x180118084  mov     eax, [rbp+cbData]
0x180118087  test    eax, eax
0x180118089  jz      loc_18011813F
0x18011808f  mov     edx, eax; uBytes
0x180118091  lea     ecx, [rbx+40h]; uFlags
0x180118094  call    cs:__imp_LocalAlloc
0x18011809a  mov     rsi, rax
0x18011809d  test    rax, rax
0x1801180a0  jnz     short loc_1801180AC
0x1801180a2  mov     ebx, 8007000Eh
0x1801180a7  jmp     loc_18011813F
0x1801180ac  mov     rcx, [rbp+hKey]; hKey
0x1801180b0  lea     rax, [rbp+cbData]
0x1801180b4  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1801180b9  lea     r9, [rbp+Type]; lpType
0x1801180bd  xor     r8d, r8d; lpReserved
0x1801180c0  mov     [rsp+60h+phkResult], rsi; lpData
0x1801180c5  mov     rdx, r15; lpValueName
0x1801180c8  call    cs:__imp_RegQueryValueExW
0x1801180ce  mov     ebx, eax
0x1801180d0  test    eax, eax
0x1801180d2  jnz     loc_18011803D
0x1801180d8  mov     eax, [rbp+cbData]
0x1801180db  lea     ecx, [rbx+11h]; vt
0x1801180de  lea     r8, [rbp+rgsabound]; rgsabound
0x1801180e2  mov     [rbp+rgsabound.cElements], eax
0x1801180e5  lea     edx, [rbx+1]; cDims
0x1801180e8  mov     [rbp+rgsabound.lLbound], edi
0x1801180eb  call    cs:__imp_SafeArrayCreate
0x1801180f1  mov     rdi, rax
0x1801180f4  test    rax, rax
0x1801180f7  jz      short loc_1801180A2
0x1801180f9  lea     rdx, [rbp+ppvData]; ppvData
0x1801180fd  mov     rcx, rax; psa
0x180118100  call    cs:__imp_SafeArrayAccessData
0x180118106  mov     ebx, eax
0x180118108  test    eax, eax
0x18011810a  js      short loc_18011813F
0x18011810c  mov     r8d, [rbp+cbData]; Size
0x180118110  mov     rdx, rsi; Src
0x180118113  mov     rcx, [rbp+ppvData]; void *
0x180118117  call    memcpy_0
0x18011811c  mov     rcx, rdi; psa
0x18011811f  call    cs:__imp_SafeArrayUnaccessData
0x180118125  mov     ebx, eax
0x180118127  test    eax, eax
0x180118129  js      short loc_18011813F
0x18011812b  mov     [r14+8], rdi
0x18011812f  xor     edi, edi
0x180118131  mov     [rbp+ppvData], 0
0x180118139  mov     word ptr [r14], 2011h
0x18011813f  mov     rcx, [rbp+hKey]; hKey
0x180118143  test    rcx, rcx
0x180118146  jz      short loc_18011814E
0x180118148  call    cs:__imp_RegCloseKey
0x18011814e  mov     rcx, rdi; psa
0x180118151  call    cs:__imp_SafeArrayDestroy
0x180118157  mov     rcx, rsi; hMem
0x18011815a  call    cs:__imp_LocalFree
0x180118160  mov     eax, ebx
0x180118162  mov     rcx, [rbp+var_8]
0x180118166  xor     rcx, rsp; StackCookie
0x180118169  call    __security_check_cookie
0x18011816e  mov     rbx, [rsp+60h+arg_0]
0x180118176  add     rsp, 60h
0x18011817a  pop     r15
0x18011817c  pop     r14
0x18011817e  pop     rdi
0x18011817f  pop     rsi
0x180118180  pop     rbp
0x180118181  retn
```
