# CryptXmlCNGCloseDigest(void *)

- ea: `0x1800122e0`
- end: `0x180012341`
- name: `?CryptXmlCNGCloseDigest@@YAJPEAX@Z`
- size: `97`
- prototype: `__int64 __fastcall(void *lpMem)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800122e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012315`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001232c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001232c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012309`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012309`
- `bcrypt!BCryptDestroyHash` at `0x1800122f2`
- `bcrypt!BCryptDestroyHash` at `0x1800122f2`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGCloseDigest(_QWORD *lpMem)
{
  void *v2; // rcx
  void *v3; // rcx
  HANDLE ProcessHeap; // rax

  v2 = (void *)lpMem[2];
  if ( v2 )
    BCryptDestroyHash(v2);
  v3 = (void *)lpMem[1];
  if ( v3 )
    BCryptCloseAlgorithmProvider(v3, 0);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 8u, lpMem);
  return 0;
}

```

## disassembly

```asm
0x1800122e0  push    rbx
0x1800122e2  sub     rsp, 20h
0x1800122e6  mov     rbx, rcx
0x1800122e9  mov     rcx, [rcx+10h]; hHash
0x1800122ed  test    rcx, rcx
0x1800122f0  jz      short loc_1800122FE
0x1800122f2  call    cs:__imp_BCryptDestroyHash
0x1800122f9  nop     dword ptr [rax+rax+00h]
0x1800122fe  mov     rcx, [rbx+8]; hAlgorithm
0x180012302  test    rcx, rcx
0x180012305  jz      short loc_180012315
0x180012307  xor     edx, edx; dwFlags
0x180012309  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180012310  nop     dword ptr [rax+rax+00h]
0x180012315  call    cs:__imp_GetProcessHeap
0x18001231c  nop     dword ptr [rax+rax+00h]
0x180012321  mov     r8, rbx; lpMem
0x180012324  mov     edx, 8; dwFlags
0x180012329  mov     rcx, rax; hHeap
0x18001232c  call    cs:__imp_HeapFree
0x180012333  nop     dword ptr [rax+rax+00h]
0x180012338  xor     eax, eax
0x18001233a  add     rsp, 20h
0x18001233e  pop     rbx
0x18001233f  retn
```
