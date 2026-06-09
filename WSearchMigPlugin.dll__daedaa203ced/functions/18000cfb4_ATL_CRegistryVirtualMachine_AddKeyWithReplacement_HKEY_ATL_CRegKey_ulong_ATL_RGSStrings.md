# ATL::CRegistryVirtualMachine::AddKeyWithReplacement(HKEY__ *,ATL::CRegKey &,ulong,ATL::RGSStrings *)

- ea: `0x18000cfb4`
- end: `0x18000d112`
- name: `?AddKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAVCRegKey@2@KPEAURGSStrings@2@@Z`
- size: `350`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *this, HKEY, HKEY *, int, struct ATL::RGSStrings *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012b04`

## callees

- `0x18000cfb4`
- `0x18000d790`
- `0x18000fa28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d00a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d0e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d100`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d00a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d0e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d100`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d0b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d0b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegistryVirtualMachine::AddKeyWithReplacement(
        ATL::CRegistryVirtualMachine *this,
        HKEY a2,
        HKEY *a3,
        int a4,
        struct ATL::RGSStrings *a5)
{
  int StringAtLoc; // ebx
  WCHAR *v9; // rbx
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  const WCHAR *v12; // rdx
  LSTATUS Key; // ecx
  unsigned int v14; // edi
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-28h] BYREF
  void *Block[4]; // [rsp+58h] [rbp-20h] BYREF

  lpSubKey = 0;
  Block[0] = 0;
  Block[1] = 0;
  StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                  (_DWORD)this,
                  (_DWORD)a5,
                  a4,
                  (unsigned int)Block,
                  (__int64)&lpSubKey);
  if ( StringAtLoc >= 0 )
  {
    v9 = (WCHAR *)Block[0];
    v10 = (const WCHAR *)Block[0];
    Block[0] = 0;
    if ( lpSubKey )
      v10 = lpSubKey;
    v11 = RegOpenKeyExW(a2, v10, 0, 0x2001Fu, (PHKEY)Block);
    if ( !v11 )
    {
      if ( *a3 )
        v11 = RegCloseKey(*a3);
      *a3 = (HKEY)Block[0];
      if ( !v11 )
        goto LABEL_17;
    }
    v12 = v9;
    if ( lpSubKey )
      v12 = lpSubKey;
    LODWORD(lpSubKey) = 0;
    Block[0] = 0;
    Key = RegCreateKeyExW(a2, v12, 0, 0, 0, 0x2001Fu, 0, (PHKEY)Block, (LPDWORD)&lpSubKey);
    if ( Key )
      goto LABEL_20;
    if ( *a3 )
      Key = RegCloseKey(*a3);
    *a3 = (HKEY)Block[0];
    if ( Key )
    {
LABEL_20:
      v14 = ATL::AtlHresultFromWin32(Key);
      if ( v9 )
        free(v9);
      return v14;
    }
    else
    {
LABEL_17:
      if ( v9 )
        free(v9);
      return 0;
    }
  }
  else
  {
    if ( Block[0] )
      free(Block[0]);
    return (unsigned int)StringAtLoc;
  }
}

```

## disassembly

```asm
0x18000cfb4  push    rbp
0x18000cfb6  push    rbx
0x18000cfb7  push    rdi
0x18000cfb8  push    r14
0x18000cfba  mov     rbp, rsp
0x18000cfbd  sub     rsp, 78h
0x18000cfc1  mov     r14, rdx
0x18000cfc4  mov     [rbp+lpSubKey], 0
0x18000cfcc  mov     eax, r9d
0x18000cfcf  mov     [rbp+Block], 0
0x18000cfd7  lea     rdx, [rbp+lpSubKey]
0x18000cfdb  mov     [rbp+var_18], 0
0x18000cfe3  mov     [rsp+78h+phkResult], rdx
0x18000cfe8  lea     r9, [rbp+Block]
0x18000cfec  mov     rdx, [rbp+arg_20]
0x18000cff0  mov     rdi, r8
0x18000cff3  mov     r8d, eax
0x18000cff6  call    ?GetStringAtLoc@CRegistryVirtualMachine@ATL@@QEAAJPEAURGSStrings@2@KAEAV?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@2@PEAPEA_W@Z; ATL::CRegistryVirtualMachine::GetStringAtLoc(ATL::RGSStrings *,ulong,ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>> &,wchar_t * *)
0x18000cffb  mov     ebx, eax
0x18000cffd  test    eax, eax
0x18000cfff  jns     short loc_18000D017
0x18000d001  mov     rcx, [rbp+Block]; Block
0x18000d005  test    rcx, rcx
0x18000d008  jz      short loc_18000D010
0x18000d00a  call    cs:__imp_free
0x18000d010  mov     eax, ebx
0x18000d012  jmp     loc_18000D108
0x18000d017  mov     rbx, [rbp+Block]
0x18000d01b  lea     rax, [rbp+Block]
0x18000d01f  cmp     [rbp+lpSubKey], 0
0x18000d024  mov     rdx, rbx
0x18000d027  mov     r9d, 2001Fh; samDesired
0x18000d02d  mov     [rbp+Block], 0
0x18000d035  cmovnz  rdx, [rbp+lpSubKey]; lpSubKey
0x18000d03a  mov     rcx, r14; hKey
0x18000d03d  xor     r8d, r8d; ulOptions
0x18000d040  mov     [rsp+78h+phkResult], rax; phkResult
0x18000d045  call    cs:__imp_RegOpenKeyExW
0x18000d04b  test    eax, eax
0x18000d04d  jnz     short loc_18000D068
0x18000d04f  mov     rcx, [rdi]; hKey
0x18000d052  test    rcx, rcx
0x18000d055  jz      short loc_18000D05D
0x18000d057  call    cs:__imp_RegCloseKey
0x18000d05d  mov     rcx, [rbp+Block]
0x18000d061  mov     [rdi], rcx
0x18000d064  test    eax, eax
0x18000d066  jz      short loc_18000D0DF
0x18000d068  cmp     [rbp+lpSubKey], 0
0x18000d06d  lea     rax, [rbp+lpSubKey]
0x18000d071  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18000d076  mov     rdx, rbx
0x18000d079  cmovnz  rdx, [rbp+lpSubKey]; lpSubKey
0x18000d07e  lea     rax, [rbp+Block]
0x18000d082  mov     [rsp+78h+var_40], rax; phkResult
0x18000d087  xor     r9d, r9d; lpClass
0x18000d08a  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000d093  xor     r8d, r8d; Reserved
0x18000d096  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18000d09e  mov     rcx, r14; hKey
0x18000d0a1  mov     dword ptr [rsp+78h+phkResult], 0; dwOptions
0x18000d0a9  mov     dword ptr [rbp+lpSubKey], 0
0x18000d0b0  mov     [rbp+Block], 0
0x18000d0b8  call    cs:__imp_RegCreateKeyExW
0x18000d0be  mov     ecx, eax; unsigned int
0x18000d0c0  test    eax, eax
0x18000d0c2  jnz     short loc_18000D0F1
0x18000d0c4  cmp     [rdi], rcx
0x18000d0c7  jz      short loc_18000D0D4
0x18000d0c9  mov     rcx, [rdi]; hKey
0x18000d0cc  call    cs:__imp_RegCloseKey
0x18000d0d2  mov     ecx, eax
0x18000d0d4  mov     rax, [rbp+Block]
0x18000d0d8  mov     [rdi], rax
0x18000d0db  test    ecx, ecx
0x18000d0dd  jnz     short loc_18000D0F1
0x18000d0df  test    rbx, rbx
0x18000d0e2  jz      short loc_18000D0ED
0x18000d0e4  mov     rcx, rbx; Block
0x18000d0e7  call    cs:__imp_free
0x18000d0ed  xor     eax, eax
0x18000d0ef  jmp     short loc_18000D108
0x18000d0f1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000d0f6  mov     edi, eax
0x18000d0f8  test    rbx, rbx
0x18000d0fb  jz      short loc_18000D106
0x18000d0fd  mov     rcx, rbx; Block
0x18000d100  call    cs:__imp_free
0x18000d106  mov     eax, edi
0x18000d108  add     rsp, 78h
0x18000d10c  pop     r14
0x18000d10e  pop     rdi
0x18000d10f  pop     rbx
0x18000d110  pop     rbp
0x18000d111  retn
```
