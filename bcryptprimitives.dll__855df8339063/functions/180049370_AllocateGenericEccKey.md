# AllocateGenericEccKey

- ea: `0x180049370`
- end: `0x1800494f5`
- name: `AllocateGenericEccKey`
- size: `389`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047c50`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x180049370`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004939d`
- `ntdll!RtlAllocateHeap` at `0x18004939d`

## string_xrefs

- `0x180049443`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800494a6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800494d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall AllocateGenericEccKey(_QWORD *a1, _DWORD *a2, int a3, __int64 a4)
{
  _OWORD *Heap; // rax
  int v9; // edx
  _OWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 result; // rax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
  v10 = Heap;
  if ( Heap )
  {
    *Heap = 0;
    Heap[1] = 0;
    *((_QWORD *)Heap + 4) = 0;
    *((_DWORD *)Heap + 2) = *(_DWORD *)(a4 + 8);
    *(_DWORD *)Heap = 40;
    *((_DWORD *)Heap + 1) = 1297304409;
    v11 = *(_QWORD *)(a4 + 16);
    if ( v11 )
    {
      if ( !a3 || a3 == *(_DWORD *)(*(_QWORD *)v11 + 12LL) )
      {
        *((_DWORD *)Heap + 8) |= 1u;
        *((_QWORD *)Heap + 2) = v11;
        goto LABEL_4;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          88);
    }
    else
    {
      if ( !a3 )
      {
LABEL_4:
        *a1 = Heap;
        result = 0;
        *a2 = 40;
        return result;
      }
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1640);
    }
    MSCryptFree(v10);
    return 3221225485LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        62);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x180049370  push    rbx
0x180049372  push    rsi
0x180049373  push    rdi
0x180049374  push    r14
0x180049376  push    r15
0x180049378  sub     rsp, 40h
0x18004937c  mov     r15, rcx
0x18004937f  mov     edi, r8d
0x180049382  mov     rcx, gs:60h
0x18004938b  mov     r14, rdx
0x18004938e  xor     edx, edx; Flags
0x180049390  mov     r8d, 28h ; '('; Size
0x180049396  mov     rsi, r9
0x180049399  mov     rcx, [rcx+30h]; HeapHandle
0x18004939d  call    cs:__imp_RtlAllocateHeap
0x1800493a4  nop     dword ptr [rax+rax+00h]
0x1800493a9  mov     rbx, rax
0x1800493ac  test    rax, rax
0x1800493af  jz      short loc_1800493FE
0x1800493b1  xor     eax, eax
0x1800493b3  xorps   xmm0, xmm0
0x1800493b6  movups  xmmword ptr [rbx], xmm0
0x1800493b9  movups  xmmword ptr [rbx+10h], xmm0
0x1800493bd  mov     [rbx+20h], rax
0x1800493c1  mov     eax, [rsi+8]
0x1800493c4  mov     [rbx+8], eax
0x1800493c7  mov     dword ptr [rbx], 28h ; '('
0x1800493cd  mov     dword ptr [rbx+4], 4D534B59h
0x1800493d4  mov     rcx, [rsi+10h]
0x1800493d8  test    rcx, rcx
0x1800493db  jnz     short loc_180049429
0x1800493dd  test    edi, edi
0x1800493df  jnz     loc_1800494D0
0x1800493e5  mov     [r15], rbx
0x1800493e8  xor     eax, eax
0x1800493ea  mov     dword ptr [r14], 28h ; '('
0x1800493f1  add     rsp, 40h
0x1800493f5  pop     r15
0x1800493f7  pop     r14
0x1800493f9  pop     rdi
0x1800493fa  pop     rsi
0x1800493fb  pop     rbx
0x1800493fc  retn
0x1800493fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180049405  lea     rax, WPP_GLOBAL_Control
0x18004940c  cmp     rcx, rax
0x18004940f  jz      short loc_180049417
0x180049411  test    byte ptr [rcx+1Ch], 1
0x180049415  jnz     short loc_18004943F
0x180049417  mov     eax, 0C0000017h
0x18004941c  add     rsp, 40h
0x180049420  pop     r15
0x180049422  pop     r14
0x180049424  pop     rdi
0x180049425  pop     rsi
0x180049426  pop     rbx
0x180049427  retn
0x180049429  test    edi, edi
0x18004942b  jz      short loc_180049435
0x18004942d  mov     rax, [rcx]
0x180049430  cmp     edi, [rax+0Ch]
0x180049433  jnz     short loc_18004946D
0x180049435  or      dword ptr [rbx+20h], 1
0x180049439  mov     [rbx+10h], rcx
0x18004943d  jmp     short loc_1800493E5
0x18004943f  mov     rcx, [rcx+10h]
0x180049443  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004944a  mov     [rsp+68h+var_38], 63Eh
0x180049452  lea     r9, aStatus; "Status"
0x180049459  mov     [rsp+68h+var_40], r8
0x18004945e  mov     [rsp+68h+var_48], 0C0000017h
0x180049466  call    WPP_SF_sDsd
0x18004946b  jmp     short loc_180049417
0x18004946d  mov     edi, 0C000000Dh
0x180049472  mov     rcx, cs:WPP_GLOBAL_Control
0x180049479  lea     rax, WPP_GLOBAL_Control
0x180049480  cmp     rcx, rax
0x180049483  jz      short loc_18004948B
0x180049485  test    byte ptr [rcx+1Ch], 1
0x180049489  jnz     short loc_1800494A2
0x18004948b  mov     rcx, rbx
0x18004948e  call    MSCryptFree
0x180049493  mov     eax, edi
0x180049495  add     rsp, 40h
0x180049499  pop     r15
0x18004949b  pop     r14
0x18004949d  pop     rdi
0x18004949e  pop     rsi
0x18004949f  pop     rbx
0x1800494a0  retn
0x1800494a2  mov     rcx, [rcx+10h]
0x1800494a6  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800494ad  mov     [rsp+68h+var_38], 658h
0x1800494b5  lea     r9, aStatus; "Status"
0x1800494bc  mov     [rsp+68h+var_40], r8
0x1800494c1  mov     [rsp+68h+var_48], 0C000000Dh
0x1800494c9  call    WPP_SF_sDsd
0x1800494ce  jmp     short loc_18004948B
0x1800494d0  mov     r9d, 668h
0x1800494d6  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800494dd  lea     rdx, aStatus; "Status"
0x1800494e4  mov     ecx, 0C000000Dh
0x1800494e9  mov     edi, 0C000000Dh
0x1800494ee  call    DebugTraceError
0x1800494f3  jmp     short loc_18004948B
```
