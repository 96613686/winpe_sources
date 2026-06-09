# KerbLoadECDHAlgorithmProviders(void)

- ea: `0x14001d390`
- end: `0x14001d40e`
- name: `?KerbLoadECDHAlgorithmProviders@@YAJXZ`
- size: `126`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140014d6c`

## callees

- `0x14001d390`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14001d3e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14001d3e2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14001d3c4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14001d3c4`

## pseudocode

```c
NTSTATUS KerbLoadECDHAlgorithmProviders(void)
{
  __int64 v0; // rbx
  __int64 v1; // rdi
  NTSTATUS result; // eax

  v0 = 0;
  while ( (unsigned int)v0 < 3 )
  {
    v1 = 9 * v0;
    result = BCryptOpenAlgorithmProvider(
               (BCRYPT_ALG_HANDLE *)&qword_1400520B0[9 * v0],
               (LPCWSTR)*(&KerbGlobalECCNamedCurves + 9 * v0 + 3),
               0,
               0);
    if ( result < 0 )
      return result;
    InitOnceExecuteOnce(&InitOnce, KerbInitECDHAlgOnceHandler, 0, 0);
    v0 = (unsigned int)(v0 + 1);
    *(&KerbGlobalECCNamedCurves + v1 + 6) = *(struct _KERB_ECC_CURVE_INFO near **)(qword_140052E78 + 8);
  }
  return 0;
}

```

## disassembly

```asm
0x14001d390  mov     [rsp+arg_0], rbx
0x14001d395  mov     [rsp+arg_8], rsi
0x14001d39a  push    rdi
0x14001d39b  sub     rsp, 20h
0x14001d39f  xor     ebx, ebx
0x14001d3a1  lea     rsi, ?KerbGlobalECCNamedCurves@@3PAU_KERB_ECC_CURVE_INFO@@A; _KERB_ECC_CURVE_INFO near * KerbGlobalECCNamedCurves
0x14001d3a8  cmp     ebx, 3
0x14001d3ab  jnb     short loc_14001D3FC
0x14001d3ad  lea     rdi, [rbx+rbx*8]
0x14001d3b1  xor     r9d, r9d; dwFlags
0x14001d3b4  mov     rdx, [rsi+rdi*8+18h]; pszAlgId
0x14001d3b9  lea     rcx, [rsi+20h]
0x14001d3bd  lea     rcx, [rcx+rdi*8]; phAlgorithm
0x14001d3c1  xor     r8d, r8d; pszImplementation
0x14001d3c4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001d3ca  test    eax, eax
0x14001d3cc  js      short loc_14001D3FE
0x14001d3ce  xor     r9d, r9d; Context
0x14001d3d1  lea     rdx, KerbInitECDHAlgOnceHandler; InitFn
0x14001d3d8  xor     r8d, r8d; Parameter
0x14001d3db  lea     rcx, InitOnce; InitOnce
0x14001d3e2  call    cs:__imp_InitOnceExecuteOnce
0x14001d3e8  mov     rax, cs:qword_140052E78
0x14001d3ef  inc     ebx
0x14001d3f1  mov     rcx, [rax+8]
0x14001d3f5  mov     [rsi+rdi*8+30h], rcx
0x14001d3fa  jmp     short loc_14001D3A8
0x14001d3fc  xor     eax, eax
0x14001d3fe  mov     rbx, [rsp+28h+arg_0]
0x14001d403  mov     rsi, [rsp+28h+arg_8]
0x14001d408  add     rsp, 20h
0x14001d40c  pop     rdi
0x14001d40d  retn
```
