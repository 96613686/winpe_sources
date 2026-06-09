# ClassFactory::RegisterCoClass(ushort const *,ushort const *,ushort const *,_GUID const *)

- ea: `0x1800120ac`
- end: `0x18001240e`
- name: `?RegisterCoClass@ClassFactory@@CAJPEBG00PEBU_GUID@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(BYTE *lpData, BYTE *, BYTE *, UUID *Uuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f860`

## callees

- `0x1800021e0`
- `0x18000ab38`
- `0x180010144`
- `0x1800120ac`
- `0x1800130a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001229c`
- `ADVAPI32!RegCloseKey` at `0x180012392`
- `ADVAPI32!RegCloseKey` at `0x1800123a7`
- `ADVAPI32!RegCloseKey` at `0x1800123bc`
- `ADVAPI32!RegCloseKey` at `0x18001229c`
- `ADVAPI32!RegCloseKey` at `0x180012392`
- `ADVAPI32!RegCloseKey` at `0x1800123a7`
- `ADVAPI32!RegCloseKey` at `0x1800123bc`
- `ADVAPI32!RegOpenKeyExW` at `0x180012289`
- `ADVAPI32!RegOpenKeyExW` at `0x180012289`
- `ADVAPI32!RegSetValueExW` at `0x18001220f`
- `ADVAPI32!RegSetValueExW` at `0x18001225a`
- `ADVAPI32!RegSetValueExW` at `0x1800122ec`
- `ADVAPI32!RegSetValueExW` at `0x180012340`
- `ADVAPI32!RegSetValueExW` at `0x180012374`
- `ADVAPI32!RegSetValueExW` at `0x18001220f`
- `ADVAPI32!RegSetValueExW` at `0x18001225a`
- `ADVAPI32!RegSetValueExW` at `0x1800122ec`
- `ADVAPI32!RegSetValueExW` at `0x180012340`
- `ADVAPI32!RegSetValueExW` at `0x180012374`
- `ADVAPI32!RegCreateKeyW` at `0x1800121ba`
- `ADVAPI32!RegCreateKeyW` at `0x18001222a`
- `ADVAPI32!RegCreateKeyW` at `0x1800122b4`
- `ADVAPI32!RegCreateKeyW` at `0x18001230b`
- `ADVAPI32!RegCreateKeyW` at `0x1800121ba`
- `ADVAPI32!RegCreateKeyW` at `0x18001222a`
- `ADVAPI32!RegCreateKeyW` at `0x1800122b4`
- `ADVAPI32!RegCreateKeyW` at `0x18001230b`
- `RPCRT4!RpcStringFreeW` at `0x1800123d3`
- `RPCRT4!RpcStringFreeW` at `0x1800123d3`
- `RPCRT4!UuidToStringW` at `0x180012143`
- `RPCRT4!UuidToStringW` at `0x180012143`

## string_xrefs

- `0x180012368`: `ThreadingModel`
- `0x18001221e`: `CLSID`
- `0x18001227b`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClassFactory::RegisterCoClass(const WCHAR *lpData, BYTE *a2, BYTE *a3, UUID *Uuid)
{
  int v7; // ebx
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  LSTATUS v10; // eax
  bool v11; // cc
  __int64 v12; // rdi
  __int64 v13; // rax
  const WCHAR *v14; // rsi
  __int64 v15; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  RPC_WSTR StringUuid; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+68h] [rbp-98h]
  __int16 v26; // [rsp+70h] [rbp-90h] BYREF

  phkResult = 0;
  hKey = 0;
  v21 = 0;
  v18 = 0;
  StringUuid = 0;
  v22[2] = 0;
  v23 = 512;
  lpSubKey = (LPCWSTR)&v26;
  v25 = 0;
  v26 = 0;
  if ( lpData && a2 && a3 )
  {
    v7 = UuidToStringW(Uuid, &StringUuid);
    if ( !v7 )
    {
      v7 = STRU::Copy((STRU *)v22, L"{", 0);
      if ( v7 >= 0 )
      {
        v7 = STRU::Append((STRU *)v22, StringUuid, 0, v8);
        if ( v7 >= 0 )
        {
          v7 = STRU::Append((STRU *)v22, L"}", 0, v9);
          if ( v7 >= 0 )
          {
            v10 = RegCreateKeyW(HKEY_CLASSES_ROOT, lpData, &phkResult);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v12 = -1;
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)&a2[2 * v13] );
            v10 = RegSetValueExW(phkResult, 0, 0, 1u, a2, 2 * v13 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegCreateKeyW(phkResult, L"CLSID", &hKey);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v14 = lpSubKey;
            v10 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)lpSubKey, 2 * v25 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &v21);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            RegCloseKey(hKey);
            hKey = 0;
            v10 = RegCreateKeyW(v21, v14, &hKey);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v15 = -1;
            do
              ++v15;
            while ( lpData[v15] );
            v10 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)lpData, 2 * v15 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegCreateKeyW(hKey, L"InProcServer32", &v18);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            do
              ++v12;
            while ( *(_WORD *)&a3[2 * v12] );
            v10 = RegSetValueExW(v18, 0, 0, 1u, a3, 2 * v12 + 2);
            v11 = v10 <= 0;
            if ( v10 || (v10 = RegSetValueExW(v18, L"ThreadingModel", 0, 1u, L"Both", 0xAu), v11 = v10 <= 0, v10) )
            {
LABEL_9:
              if ( v11 )
                v7 = v10;
              else
                v7 = (unsigned __int16)v10 | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800120ac  push    rbp
0x1800120ae  push    rbx
0x1800120af  push    rsi
0x1800120b0  push    rdi
0x1800120b1  push    r12
0x1800120b3  push    r13
0x1800120b5  push    r14
0x1800120b7  push    r15
0x1800120b9  lea     rbp, [rsp-188h]
0x1800120c1  sub     rsp, 288h
0x1800120c8  mov     rax, cs:__security_cookie
0x1800120cf  xor     rax, rsp
0x1800120d2  mov     [rbp+1C0h+var_50], rax
0x1800120d9  mov     r15, r8
0x1800120dc  mov     rsi, rdx
0x1800120df  mov     r14, rcx
0x1800120e2  xor     r12d, r12d
0x1800120e5  mov     [rsp+2C0h+phkResult], r12
0x1800120ea  mov     [rsp+2C0h+hKey], r12
0x1800120ef  mov     [rsp+2C0h+var_270], r12
0x1800120f4  mov     [rsp+2C0h+var_288], r12
0x1800120f9  mov     [rsp+2C0h+StringUuid], r12
0x1800120fe  mov     [rsp+2C0h+var_266], r12b
0x180012103  mov     [rsp+2C0h+var_264], 200h
0x18001210b  lea     rax, [rsp+2C0h+var_250]
0x180012110  mov     [rsp+2C0h+lpSubKey], rax
0x180012115  mov     [rsp+2C0h+var_258], r12d
0x18001211a  mov     [rsp+2C0h+var_250], r12w
0x180012120  test    rcx, rcx
0x180012123  jz      loc_180012383
0x180012129  test    rdx, rdx
0x18001212c  jz      loc_180012383
0x180012132  test    r8, r8
0x180012135  jz      loc_180012383
0x18001213b  lea     rdx, [rsp+2C0h+StringUuid]; StringUuid
0x180012140  mov     rcx, r9; Uuid
0x180012143  call    cs:__imp_UuidToStringW
0x180012149  mov     ebx, eax
0x18001214b  test    eax, eax
0x18001214d  jnz     loc_180012388
0x180012153  xor     r8d, r8d; unsigned int
0x180012156  lea     rdx, asc_180018CD8; "{"
0x18001215d  lea     rcx, [rsp+2C0h+var_268]; this
0x180012162  call    ?Copy@STRU@@QEAAJPEBGKK@Z; STRU::Copy(ushort const *,ulong,ulong)
0x180012167  mov     ebx, eax
0x180012169  test    eax, eax
0x18001216b  js      loc_180012388
0x180012171  xor     r8d, r8d; unsigned int
0x180012174  mov     rdx, [rsp+2C0h+StringUuid]; unsigned __int16 *
0x180012179  lea     rcx, [rsp+2C0h+var_268]; this
0x18001217e  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180012183  mov     ebx, eax
0x180012185  test    eax, eax
0x180012187  js      loc_180012388
0x18001218d  xor     r8d, r8d; unsigned int
0x180012190  lea     rdx, asc_180018CDC; "}"
0x180012197  lea     rcx, [rsp+2C0h+var_268]; this
0x18001219c  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x1800121a1  mov     ebx, eax
0x1800121a3  test    eax, eax
0x1800121a5  js      loc_180012388
0x1800121ab  lea     r8, [rsp+2C0h+phkResult]; phkResult
0x1800121b0  mov     rdx, r14; lpSubKey
0x1800121b3  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800121ba  call    cs:__imp_RegCreateKeyW
0x1800121c0  test    eax, eax
0x1800121c2  jz      short loc_1800121DB
0x1800121c4  jg      short loc_1800121CD
0x1800121c6  mov     ebx, eax
0x1800121c8  jmp     loc_180012388
0x1800121cd  movzx   ebx, ax
0x1800121d0  or      ebx, 80070000h
0x1800121d6  jmp     loc_180012388
0x1800121db  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800121df  mov     rax, rdi
0x1800121e2  inc     rax
0x1800121e5  cmp     [rsi+rax*2], r12w
0x1800121ea  jnz     short loc_1800121E2
0x1800121ec  lea     eax, ds:2[rax*2]
0x1800121f3  mov     [rsp+2C0h+cbData], eax; cbData
0x1800121f7  mov     [rsp+2C0h+lpData], rsi; lpData
0x1800121fc  mov     r13d, 1
0x180012202  mov     r9d, r13d; dwType
0x180012205  xor     r8d, r8d; Reserved
0x180012208  xor     edx, edx; lpValueName
0x18001220a  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18001220f  call    cs:__imp_RegSetValueExW
0x180012215  test    eax, eax
0x180012217  jnz     short loc_1800121C4
0x180012219  lea     r8, [rsp+2C0h+hKey]; phkResult
0x18001221e  lea     rdx, SubKey; "CLSID"
0x180012225  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18001222a  call    cs:__imp_RegCreateKeyW
0x180012230  test    eax, eax
0x180012232  jnz     short loc_1800121C4
0x180012234  mov     rsi, [rsp+2C0h+lpSubKey]
0x180012239  mov     eax, [rsp+2C0h+var_258]
0x18001223d  lea     eax, ds:2[rax*2]
0x180012244  mov     [rsp+2C0h+cbData], eax; cbData
0x180012248  mov     [rsp+2C0h+lpData], rsi; lpData
0x18001224d  mov     r9d, r13d; dwType
0x180012250  xor     r8d, r8d; Reserved
0x180012253  xor     edx, edx; lpValueName
0x180012255  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001225a  call    cs:__imp_RegSetValueExW
0x180012260  test    eax, eax
0x180012262  jnz     loc_1800121C4
0x180012268  lea     rax, [rsp+2C0h+var_270]
0x18001226d  mov     [rsp+2C0h+lpData], rax; phkResult
0x180012272  mov     r9d, 0F003Fh; samDesired
0x180012278  xor     r8d, r8d; ulOptions
0x18001227b  lea     rdx, SubKey; "CLSID"
0x180012282  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180012289  call    cs:__imp_RegOpenKeyExW
0x18001228f  test    eax, eax
0x180012291  jnz     loc_1800121C4
0x180012297  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001229c  call    cs:__imp_RegCloseKey
0x1800122a2  mov     [rsp+2C0h+hKey], r12
0x1800122a7  lea     r8, [rsp+2C0h+hKey]; phkResult
0x1800122ac  mov     rdx, rsi; lpSubKey
0x1800122af  mov     rcx, [rsp+2C0h+var_270]; hKey
0x1800122b4  call    cs:__imp_RegCreateKeyW
0x1800122ba  test    eax, eax
0x1800122bc  jnz     loc_1800121C4
0x1800122c2  mov     rax, rdi
0x1800122c5  inc     rax
0x1800122c8  cmp     [r14+rax*2], r12w
0x1800122cd  jnz     short loc_1800122C5
0x1800122cf  lea     eax, ds:2[rax*2]
0x1800122d6  mov     [rsp+2C0h+cbData], eax; cbData
0x1800122da  mov     [rsp+2C0h+lpData], r14; lpData
0x1800122df  mov     r9d, r13d; dwType
0x1800122e2  xor     r8d, r8d; Reserved
0x1800122e5  xor     edx, edx; lpValueName
0x1800122e7  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800122ec  call    cs:__imp_RegSetValueExW
0x1800122f2  test    eax, eax
0x1800122f4  jnz     loc_1800121C4
0x1800122fa  lea     r8, [rsp+2C0h+var_288]; phkResult
0x1800122ff  lea     rdx, aInprocserver32; "InProcServer32"
0x180012306  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001230b  call    cs:__imp_RegCreateKeyW
0x180012311  test    eax, eax
0x180012313  jnz     loc_1800121C4
0x180012319  inc     rdi
0x18001231c  cmp     [r15+rdi*2], r12w
0x180012321  jnz     short loc_180012319
0x180012323  lea     eax, ds:2[rdi*2]
0x18001232a  mov     [rsp+2C0h+cbData], eax; cbData
0x18001232e  mov     [rsp+2C0h+lpData], r15; lpData
0x180012333  mov     r9d, r13d; dwType
0x180012336  xor     r8d, r8d; Reserved
0x180012339  xor     edx, edx; lpValueName
0x18001233b  mov     rcx, [rsp+2C0h+var_288]; hKey
0x180012340  call    cs:__imp_RegSetValueExW
0x180012346  test    eax, eax
0x180012348  jnz     loc_1800121C4
0x18001234e  mov     [rsp+2C0h+cbData], 0Ah; cbData
0x180012356  lea     rax, Data; "Both"
0x18001235d  mov     [rsp+2C0h+lpData], rax; lpData
0x180012362  mov     r9d, r13d; dwType
0x180012365  xor     r8d, r8d; Reserved
0x180012368  lea     rdx, ValueName; "ThreadingModel"
0x18001236f  mov     rcx, [rsp+2C0h+var_288]; hKey
0x180012374  call    cs:__imp_RegSetValueExW
0x18001237a  test    eax, eax
0x18001237c  jz      short loc_180012388
0x18001237e  jmp     loc_1800121C4
0x180012383  mov     ebx, 80070057h
0x180012388  mov     rcx, [rsp+2C0h+var_288]; hKey
0x18001238d  test    rcx, rcx
0x180012390  jz      short loc_18001239D
0x180012392  call    cs:__imp_RegCloseKey
0x180012398  mov     [rsp+2C0h+var_288], r12
0x18001239d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800123a2  test    rcx, rcx
0x1800123a5  jz      short loc_1800123B2
0x1800123a7  call    cs:__imp_RegCloseKey
0x1800123ad  mov     [rsp+2C0h+hKey], r12
0x1800123b2  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x1800123b7  test    rcx, rcx
0x1800123ba  jz      short loc_1800123C7
0x1800123bc  call    cs:__imp_RegCloseKey
0x1800123c2  mov     [rsp+2C0h+phkResult], r12
0x1800123c7  cmp     [rsp+2C0h+StringUuid], r12
0x1800123cc  jz      short loc_1800123DE
0x1800123ce  lea     rcx, [rsp+2C0h+StringUuid]; String
0x1800123d3  call    cs:__imp_RpcStringFreeW
0x1800123d9  mov     [rsp+2C0h+StringUuid], r12
0x1800123de  lea     rcx, [rsp+2C0h+var_268]; this
0x1800123e3  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800123e8  nop
0x1800123e9  mov     eax, ebx
0x1800123eb  mov     rcx, [rbp+1C0h+var_50]
0x1800123f2  xor     rcx, rsp; StackCookie
0x1800123f5  call    __security_check_cookie
0x1800123fa  add     rsp, 288h
0x180012401  pop     r15
0x180012403  pop     r14
0x180012405  pop     r13
0x180012407  pop     r12
0x180012409  pop     rdi
0x18001240a  pop     rsi
0x18001240b  pop     rbx
0x18001240c  pop     rbp
0x18001240d  retn
```
