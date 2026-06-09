# ConfigInitialProtocols(void)

- ea: `0x180008390`
- end: `0x18000856a`
- name: `?ConfigInitialProtocols@@YAKXZ`
- size: `474`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e98`

## callees

- `0x180002274`
- `0x180008390`
- `0x180008b48`
- `0x180008e40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000852d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000852d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008463`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008463`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000853b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000853b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000842f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008491`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000842f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008551`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008551`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800083d9`

## string_xrefs

- `0x180008408`: `EpMapDisallowedProtocols`
- `0x1800083f8`: `EpMapInitialProtocols`

## pseudocode

```c
__int64 ConfigInitialProtocols(void)
{
  unsigned int v0; // ebx
  unsigned int i; // edi
  const WCHAR *v2; // r15
  unsigned __int64 v3; // r14
  HANDLE ProcessHeap; // rax
  BYTE *v5; // rsi
  const WCHAR *v6; // rcx
  __int64 v7; // r14
  DWORD v8; // edx
  __int64 ProtseqId; // rcx
  __int64 v10; // rcx
  HANDLE v11; // rax
  HANDLE v12; // rax
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Rpc", 0, 0x20019u, &hKey);
  if ( !v0 )
  {
    for ( i = 0; i < 2; ++i )
    {
      cbData = 0;
      v2 = L"EpMapDisallowedProtocols";
      if ( i )
        v2 = L"EpMapInitialProtocols";
      v0 = RegQueryValueExW(hKey, v2, 0, &Type, 0, &cbData);
      if ( !v0 )
      {
        if ( Type == 1 )
        {
          v3 = cbData + 2;
          ProcessHeap = GetProcessHeap();
          v5 = (BYTE *)HeapAlloc(ProcessHeap, 0, (unsigned int)v3);
          if ( !v5 )
          {
            v0 = 8;
            break;
          }
          v0 = RegQueryValueExW(hKey, v2, 0, &Type, v5, &cbData);
          if ( v0 )
          {
            v12 = GetProcessHeap();
            HeapFree(v12, 0, v5);
            break;
          }
          v6 = (const WCHAR *)v5;
          *(_WORD *)&v5[2 * (v3 >> 1) - 2] = 0;
          v7 = 0;
          v8 = cbData;
          if ( (cbData & 0xFFFFFFFE) != 0 )
          {
            do
            {
              if ( *(_WORD *)&v5[2 * v7] == 44 )
              {
                *(_WORD *)&v5[2 * v7] = 0;
                ProtseqId = (unsigned __int16)GetProtseqId(v6);
                if ( i )
                  DelayedUseProtseq(ProtseqId);
                else
                  DisableProtseq(ProtseqId);
                v8 = cbData;
                v7 = (unsigned int)(v7 + 1);
                v6 = (const WCHAR *)&v5[2 * (unsigned int)v7];
              }
              else
              {
                v7 = (unsigned int)(v7 + 1);
              }
            }
            while ( (unsigned int)v7 < v8 >> 1 );
          }
          v10 = (unsigned __int16)GetProtseqId(v6);
          if ( i )
            DelayedUseProtseq(v10);
          else
            DisableProtseq(v10);
          v11 = GetProcessHeap();
          HeapFree(v11, 0, v5);
        }
        else
        {
          v0 = 13;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180008390  mov     [rsp-28h+arg_18], rbx
0x180008395  push    rbp
0x180008396  push    rsi
0x180008397  push    rdi
0x180008398  push    r14
0x18000839a  push    r15
0x18000839c  mov     rbp, rsp
0x18000839f  sub     rsp, 30h
0x1800083a3  lea     rax, [rbp+hKey]
0x1800083a7  mov     [rbp+cbData], 0
0x1800083ae  mov     r9d, 20019h; samDesired
0x1800083b4  mov     [rsp+30h+phkResult], rax; phkResult
0x1800083b9  xor     r8d, r8d; ulOptions
0x1800083bc  mov     [rbp+Type], 0
0x1800083c3  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Rpc"
0x1800083ca  mov     [rbp+hKey], 0
0x1800083d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800083d9  call    cs:__imp_RegOpenKeyExW
0x1800083df  mov     ebx, eax
0x1800083e1  test    eax, eax
0x1800083e3  jnz     loc_180008548
0x1800083e9  xor     edi, edi
0x1800083eb  cmp     edi, 2
0x1800083ee  jnb     loc_180008548
0x1800083f4  mov     rcx, [rbp+hKey]; hKey
0x1800083f8  lea     rax, ValueName; "EpMapInitialProtocols"
0x1800083ff  test    edi, edi
0x180008401  mov     [rbp+cbData], 0
0x180008408  lea     r15, aEpmapdisallowe; "EpMapDisallowedProtocols"
0x18000840f  cmovnz  r15, rax
0x180008413  lea     r9, [rbp+Type]; lpType
0x180008417  lea     rax, [rbp+cbData]
0x18000841b  xor     r8d, r8d; lpReserved
0x18000841e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180008423  mov     rdx, r15; lpValueName
0x180008426  mov     [rsp+30h+phkResult], 0; lpData
0x18000842f  call    cs:__imp_RegQueryValueExW
0x180008435  mov     ebx, eax
0x180008437  test    eax, eax
0x180008439  jnz     loc_180008526
0x18000843f  cmp     [rbp+Type], 1
0x180008443  jz      short loc_18000844D
0x180008445  lea     ebx, [rax+0Dh]
0x180008448  jmp     loc_180008526
0x18000844d  mov     r14d, [rbp+cbData]
0x180008451  add     r14d, 2
0x180008455  call    cs:__imp_GetProcessHeap
0x18000845b  mov     r8d, r14d; dwBytes
0x18000845e  xor     edx, edx; dwFlags
0x180008460  mov     rcx, rax; hHeap
0x180008463  call    cs:__imp_HeapAlloc
0x180008469  mov     rsi, rax
0x18000846c  test    rax, rax
0x18000846f  jz      loc_180008543
0x180008475  mov     rcx, [rbp+hKey]; hKey
0x180008479  lea     rax, [rbp+cbData]
0x18000847d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180008482  lea     r9, [rbp+Type]; lpType
0x180008486  xor     r8d, r8d; lpReserved
0x180008489  mov     [rsp+30h+phkResult], rsi; lpData
0x18000848e  mov     rdx, r15; lpValueName
0x180008491  call    cs:__imp_RegQueryValueExW
0x180008497  mov     ebx, eax
0x180008499  test    eax, eax
0x18000849b  jnz     loc_18000852D
0x1800084a1  shr     r14, 1
0x1800084a4  mov     rcx, rsi; lpString2
0x1800084a7  mov     [rsi+r14*2-2], ax
0x1800084ad  xor     r14d, r14d
0x1800084b0  mov     edx, [rbp+cbData]
0x1800084b3  test    edx, 0FFFFFFFEh
0x1800084b9  jbe     short loc_1800084FA
0x1800084bb  cmp     word ptr [rsi+r14*2], 2Ch ; ','
0x1800084c1  jnz     short loc_1800084EE
0x1800084c3  xor     eax, eax
0x1800084c5  mov     [rsi+r14*2], ax
0x1800084ca  call    GetProtseqId
0x1800084cf  movzx   ecx, ax; unsigned __int16
0x1800084d2  test    edi, edi
0x1800084d4  jnz     short loc_1800084DD
0x1800084d6  call    ?DisableProtseq@@YAXG@Z; DisableProtseq(ushort)
0x1800084db  jmp     short loc_1800084E2
0x1800084dd  call    DelayedUseProtseq
0x1800084e2  mov     edx, [rbp+cbData]
0x1800084e5  inc     r14d
0x1800084e8  lea     rcx, [rsi+r14*2]
0x1800084ec  jmp     short loc_1800084F1
0x1800084ee  inc     r14d
0x1800084f1  mov     eax, edx
0x1800084f3  shr     eax, 1
0x1800084f5  cmp     r14d, eax
0x1800084f8  jb      short loc_1800084BB
0x1800084fa  call    GetProtseqId
0x1800084ff  movzx   ecx, ax; unsigned __int16
0x180008502  test    edi, edi
0x180008504  jnz     short loc_18000850D
0x180008506  call    ?DisableProtseq@@YAXG@Z; DisableProtseq(ushort)
0x18000850b  jmp     short loc_180008512
0x18000850d  call    DelayedUseProtseq
0x180008512  call    cs:__imp_GetProcessHeap
0x180008518  mov     r8, rsi; lpMem
0x18000851b  xor     edx, edx; dwFlags
0x18000851d  mov     rcx, rax; hHeap
0x180008520  call    cs:__imp_HeapFree
0x180008526  inc     edi
0x180008528  jmp     loc_1800083EB
0x18000852d  call    cs:__imp_GetProcessHeap
0x180008533  mov     r8, rsi; lpMem
0x180008536  xor     edx, edx; dwFlags
0x180008538  mov     rcx, rax; hHeap
0x18000853b  call    cs:__imp_HeapFree
0x180008541  jmp     short loc_180008548
0x180008543  mov     ebx, 8
0x180008548  mov     rcx, [rbp+hKey]; hKey
0x18000854c  test    rcx, rcx
0x18000854f  jz      short loc_180008557
0x180008551  call    cs:__imp_RegCloseKey
0x180008557  mov     eax, ebx
0x180008559  mov     rbx, [rsp+30h+arg_18]
0x18000855e  add     rsp, 30h
0x180008562  pop     r15
0x180008564  pop     r14
0x180008566  pop     rdi
0x180008567  pop     rsi
0x180008568  pop     rbp
0x180008569  retn
```
