# MSCryptPqDsaOpenProvider

- ea: `0x18006b1b0`
- end: `0x18006b2b3`
- name: `MSCryptPqDsaOpenProvider`
- size: `259`
- prototype: `__int64 __fastcall(__int64 *, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800102a0`
- `0x18006b1b0`
- `0x18007f765`

## string_xrefs

- `0x18006b204`: `Composite-ML-DSA`
- `0x18006b28d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaOpenProvider(__int64 *a1, const wchar_t *a2, int a3)
{
  __int64 v6; // r9
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax

  if ( !a1 )
  {
    v6 = 539;
LABEL_15:
    v10 = -1073741811;
    v11 = 3221225485LL;
    goto LABEL_16;
  }
  if ( !a2 )
  {
    v6 = 546;
    goto LABEL_15;
  }
  if ( !wcscmp_0(a2, L"ML-DSA") )
  {
    v7 = &qword_1800876E0;
  }
  else
  {
    if ( wcscmp_0(a2, L"Composite-ML-DSA") )
    {
      v6 = 561;
      goto LABEL_15;
    }
    v7 = &qword_180087718;
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v6 = 568;
    goto LABEL_15;
  }
  v8 = SafeAllocaAllocateFromHeap(24);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -1073741801;
    v6 = 578;
    v11 = 3221225495LL;
LABEL_16:
    DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v6);
    return v10;
  }
  *(_QWORD *)(v8 + 8) = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_DWORD *)v8 = 24;
  *(_DWORD *)(v8 + 4) = 1297301836;
  v12 = *(_DWORD *)v7;
  *(_QWORD *)(v9 + 16) = v7;
  v10 = 0;
  *(_DWORD *)(v9 + 8) = v12;
  *a1 = v9;
  return v10;
}

```

## disassembly

```asm
0x18006b1b0  mov     [rsp+arg_0], rbx
0x18006b1b5  mov     [rsp+arg_8], rsi
0x18006b1ba  push    rdi
0x18006b1bb  sub     rsp, 20h
0x18006b1bf  mov     esi, r8d
0x18006b1c2  mov     rbx, rdx
0x18006b1c5  mov     rdi, rcx
0x18006b1c8  test    rcx, rcx
0x18006b1cb  jnz     short loc_18006B1D8
0x18006b1cd  mov     r9d, 21Bh
0x18006b1d3  jmp     loc_18006B283
0x18006b1d8  test    rbx, rbx
0x18006b1db  jnz     short loc_18006B1E8
0x18006b1dd  mov     r9d, 222h
0x18006b1e3  jmp     loc_18006B283
0x18006b1e8  lea     rdx, aMlDsa; "ML-DSA"
0x18006b1ef  mov     rcx, rbx; String1
0x18006b1f2  call    wcscmp_0
0x18006b1f7  test    eax, eax
0x18006b1f9  jnz     short loc_18006B204
0x18006b1fb  lea     rbx, qword_1800876E0
0x18006b202  jmp     short loc_18006B21E
0x18006b204  lea     rdx, aCompositeMlDsa; "Composite-ML-DSA"
0x18006b20b  mov     rcx, rbx; String1
0x18006b20e  call    wcscmp_0
0x18006b213  test    eax, eax
0x18006b215  jnz     short loc_18006B27D
0x18006b217  lea     rbx, qword_180087718
0x18006b21e  test    esi, 0FFFFFFFEh
0x18006b224  jz      short loc_18006B22E
0x18006b226  mov     r9d, 238h
0x18006b22c  jmp     short loc_18006B283
0x18006b22e  mov     esi, 18h
0x18006b233  mov     ecx, esi
0x18006b235  call    SafeAllocaAllocateFromHeap
0x18006b23a  mov     rcx, rax
0x18006b23d  test    rax, rax
0x18006b240  jnz     short loc_18006B254
0x18006b242  mov     ebx, 0C0000017h
0x18006b247  mov     r9d, 242h
0x18006b24d  mov     ecx, 0C0000017h
0x18006b252  jmp     short loc_18006B28D
0x18006b254  mov     qword ptr [rax+8], 0
0x18006b25c  mov     qword ptr [rax+10h], 0
0x18006b264  mov     [rax], esi
0x18006b266  mov     dword ptr [rax+4], 4D53414Ch
0x18006b26d  mov     eax, [rbx]
0x18006b26f  mov     [rcx+10h], rbx
0x18006b273  xor     ebx, ebx
0x18006b275  mov     [rcx+8], eax
0x18006b278  mov     [rdi], rcx
0x18006b27b  jmp     short loc_18006B2A0
0x18006b27d  mov     r9d, 231h
0x18006b283  mov     ebx, 0C000000Dh
0x18006b288  mov     ecx, 0C000000Dh
0x18006b28d  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b294  lea     rdx, aStatus_0; "status"
0x18006b29b  call    DebugTraceError
0x18006b2a0  mov     rsi, [rsp+28h+arg_8]
0x18006b2a5  mov     eax, ebx
0x18006b2a7  mov     rbx, [rsp+28h+arg_0]
0x18006b2ac  add     rsp, 20h
0x18006b2b0  pop     rdi
0x18006b2b1  retn
```
