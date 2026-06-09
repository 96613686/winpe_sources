# CreateCLSIDRegKey

- ea: `0x180075d04`
- end: `0x180075f3c`
- name: `CreateCLSIDRegKey`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075ba0`

## callees

- `0x180015190`
- `0x180015e90`
- `0x180015ea8`
- `0x180015f08`
- `0x180075c94`
- `0x180075ce4`
- `0x180075d04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075d47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075d47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075e51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075eb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075ee1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075e51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075eb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180075ee1`

## string_xrefs

- `0x180075d4d`: `CLSID\{`
- `0x180075ecf`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall CreateCLSIDRegKey(unsigned int *a1, const BYTE *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  unsigned int v6; // ebx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  int v10; // [rsp+30h] [rbp-D0h]
  int v11; // [rsp+38h] [rbp-C8h]
  int v12; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v19; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v20[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[8]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Buffer[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[144]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Filename[264]; // [rsp+130h] [rbp+30h] BYREF

  GetModuleFileNameW(g_hInst, Filename, 0x104u);
  wcscpy(Buffer, L"CLSID\\{");
  memset_0(v23, 0, sizeof(v23));
  v17 = *((unsigned __int8 *)a1 + 15);
  v16 = *((unsigned __int8 *)a1 + 14);
  v15 = *((unsigned __int8 *)a1 + 13);
  v14 = *((unsigned __int8 *)a1 + 12);
  v13 = *((unsigned __int8 *)a1 + 11);
  v12 = *((unsigned __int8 *)a1 + 10);
  v11 = *((unsigned __int8 *)a1 + 9);
  v10 = *((unsigned __int8 *)a1 + 8);
  cbData = *((unsigned __int16 *)a1 + 3);
  lpData = *((unsigned __int16 *)a1 + 2);
  swprintf_s(
    &Buffer[7],
    0x49u,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    *a1,
    lpData,
    cbData,
    v10,
    v11,
    v12,
    v13,
    v14,
    v15,
    v16,
    v17);
  wcscat_s(Buffer, 0x50u, L"}");
  hKey = 0;
  CAutoHKey::CAutoHKey((CAutoHKey *)v20, HKEY_CLASSES_ROOT, Buffer, &hKey);
  if ( !hKey )
    goto LABEL_11;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)&a2[2 * v5] );
  if ( RegSetValueExW(hKey, 0, 0, 1u, a2, 2 * v5 + 2) )
  {
LABEL_11:
    CAutoHKey::~CAutoHKey((CAutoHKey *)v20);
    return 2147500037LL;
  }
  else
  {
    v19 = 0;
    CAutoHKey::CAutoHKey((CAutoHKey *)v21, hKey, L"InprocServer32", &v19);
    if ( !v19 )
      goto LABEL_9;
    do
      ++v4;
    while ( Filename[v4] );
    if ( RegSetValueExW(v19, 0, 0, 1u, (const BYTE *)Filename, 2 * v4 + 2)
      || (v6 = 0, RegSetValueExW(v19, L"ThreadingModel", 0, 1u, L"Both", 0xAu)) )
    {
LABEL_9:
      v6 = -2147467259;
    }
    CAutoHKey::~CAutoHKey((CAutoHKey *)v21);
    CAutoHKey::~CAutoHKey((CAutoHKey *)v20);
    return v6;
  }
}

```

## disassembly

```asm
0x180075d04  mov     [rsp-8+arg_10], rbx
0x180075d09  push    rbp
0x180075d0a  push    rsi
0x180075d0b  push    rdi
0x180075d0c  push    r14
0x180075d0e  push    r15
0x180075d10  lea     rbp, [rsp-250h]
0x180075d18  sub     rsp, 350h
0x180075d1f  mov     rax, cs:__security_cookie
0x180075d26  xor     rax, rsp
0x180075d29  mov     [rbp+270h+var_30], rax
0x180075d30  mov     r15, rdx
0x180075d33  mov     r14, rcx
0x180075d36  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x180075d3d  lea     rdx, [rbp+270h+Filename]; lpFilename
0x180075d41  mov     r8d, 104h; nSize
0x180075d47  call    cs:__imp_GetModuleFileNameW
0x180075d4d  movups  xmm0, xmmword ptr cs:aClsid; "CLSID\\{"
0x180075d54  xor     edx, edx; Val
0x180075d56  lea     rcx, [rbp+270h+var_2D0]; void *
0x180075d5a  mov     r8d, 90h; Size
0x180075d60  movdqu  xmmword ptr [rbp+270h+Buffer], xmm0
0x180075d65  call    memset_0
0x180075d6a  movzx   ecx, byte ptr [r14+0Eh]
0x180075d6f  movzx   edx, byte ptr [r14+0Dh]
0x180075d74  movzx   r8d, byte ptr [r14+0Ch]
0x180075d79  movzx   r9d, byte ptr [r14+0Bh]
0x180075d7e  movzx   eax, byte ptr [r14+0Fh]
0x180075d83  movzx   r10d, byte ptr [r14+0Ah]
0x180075d88  movzx   r11d, byte ptr [r14+9]
0x180075d8d  movzx   ebx, byte ptr [r14+8]
0x180075d92  movzx   edi, word ptr [r14+6]
0x180075d97  movzx   esi, word ptr [r14+4]
0x180075d9c  mov     [rsp+370h+var_308], eax
0x180075da0  mov     [rsp+370h+var_310], ecx
0x180075da4  lea     rcx, [rbp+270h+Buffer+0Eh]; Buffer
0x180075da8  mov     [rsp+370h+var_318], edx
0x180075dac  mov     edx, 49h ; 'I'; BufferCount
0x180075db1  mov     [rsp+370h+var_320], r8d
0x180075db6  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180075dbd  mov     [rsp+370h+var_328], r9d
0x180075dc2  mov     r9d, [r14]
0x180075dc5  mov     [rsp+370h+var_330], r10d
0x180075dca  mov     [rsp+370h+var_338], r11d
0x180075dcf  mov     [rsp+370h+var_340], ebx
0x180075dd3  mov     [rsp+370h+cbData], edi
0x180075dd7  mov     dword ptr [rsp+370h+lpData], esi
0x180075ddb  call    swprintf_s
0x180075de0  lea     r8, Source; "}"
0x180075de7  mov     edx, 50h ; 'P'; SizeInWords
0x180075dec  lea     rcx, [rbp+270h+Buffer]; Destination
0x180075df0  call    wcscat_s
0x180075df5  xor     edi, edi
0x180075df7  lea     r9, [rsp+370h+hKey]; HKEY *
0x180075dfc  lea     r8, [rbp+270h+Buffer]; unsigned __int16 *
0x180075e00  mov     [rsp+370h+hKey], rdi
0x180075e05  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x180075e0c  lea     rcx, [rbp+270h+var_2F0]; this
0x180075e10  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180075e15  mov     rcx, [rsp+370h+hKey]; hKey
0x180075e1a  test    rcx, rcx
0x180075e1d  jz      loc_180075F08
0x180075e23  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180075e27  mov     rax, rbx
0x180075e2a  inc     rax
0x180075e2d  cmp     [r15+rax*2], di
0x180075e32  jnz     short loc_180075E2A
0x180075e34  lea     eax, ds:2[rax*2]
0x180075e3b  mov     esi, 1
0x180075e40  mov     [rsp+370h+cbData], eax; cbData
0x180075e44  mov     r9d, esi; dwType
0x180075e47  xor     r8d, r8d; Reserved
0x180075e4a  mov     [rsp+370h+lpData], r15; lpData
0x180075e4f  xor     edx, edx; lpValueName
0x180075e51  call    cs:__imp_RegSetValueExW
0x180075e57  test    eax, eax
0x180075e59  jnz     loc_180075F08
0x180075e5f  mov     rdx, [rsp+370h+hKey]; HKEY
0x180075e64  lea     r9, [rsp+370h+var_2F8]; HKEY *
0x180075e69  lea     r8, aInprocserver32; "InprocServer32"
0x180075e70  mov     [rsp+370h+var_2F8], rdi
0x180075e75  lea     rcx, [rbp+270h+var_2E8]; this
0x180075e79  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180075e7e  mov     rcx, [rsp+370h+var_2F8]; hKey
0x180075e83  test    rcx, rcx
0x180075e86  jz      short loc_180075EED
0x180075e88  lea     rax, [rbp+270h+Filename]
0x180075e8c  inc     rbx
0x180075e8f  cmp     [rax+rbx*2], di
0x180075e93  jnz     short loc_180075E8C
0x180075e95  lea     eax, ds:2[rbx*2]
0x180075e9c  mov     r9d, esi; dwType
0x180075e9f  mov     [rsp+370h+cbData], eax; cbData
0x180075ea3  xor     r8d, r8d; Reserved
0x180075ea6  lea     rax, [rbp+270h+Filename]
0x180075eaa  xor     edx, edx; lpValueName
0x180075eac  mov     [rsp+370h+lpData], rax; lpData
0x180075eb1  call    cs:__imp_RegSetValueExW
0x180075eb7  test    eax, eax
0x180075eb9  jnz     short loc_180075EED
0x180075ebb  mov     rcx, [rsp+370h+var_2F8]; hKey
0x180075ec0  lea     rax, Data; "Both"
0x180075ec7  mov     [rsp+370h+cbData], 0Ah; cbData
0x180075ecf  lea     rdx, ValueName; "ThreadingModel"
0x180075ed6  mov     r9d, esi; dwType
0x180075ed9  mov     [rsp+370h+lpData], rax; lpData
0x180075ede  xor     r8d, r8d; Reserved
0x180075ee1  call    cs:__imp_RegSetValueExW
0x180075ee7  mov     ebx, edi
0x180075ee9  test    eax, eax
0x180075eeb  jz      short loc_180075EF2
0x180075eed  mov     ebx, 80004005h
0x180075ef2  lea     rcx, [rbp+270h+var_2E8]; this
0x180075ef6  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x180075efb  lea     rcx, [rbp+270h+var_2F0]; this
0x180075eff  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x180075f04  mov     eax, ebx
0x180075f06  jmp     short loc_180075F16
0x180075f08  lea     rcx, [rbp+270h+var_2F0]; this
0x180075f0c  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x180075f11  mov     eax, 80004005h
0x180075f16  mov     rcx, [rbp+270h+var_30]
0x180075f1d  xor     rcx, rsp; StackCookie
0x180075f20  call    __security_check_cookie
0x180075f25  mov     rbx, [rsp+370h+arg_10]
0x180075f2d  add     rsp, 350h
0x180075f34  pop     r15
0x180075f36  pop     r14
0x180075f38  pop     rdi
0x180075f39  pop     rsi
0x180075f3a  pop     rbp
0x180075f3b  retn
```
