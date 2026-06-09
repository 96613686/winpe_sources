# PinCachePresentPin

- ea: `0x18002a814`
- end: `0x18002a9c8`
- name: `PinCachePresentPin`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002b1a4`

## callees

- `0x18000de80`
- `0x180029fcc`
- `0x18002a814`
- `0x18002a9d0`
- `0x18002b730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a978`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a8a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a96a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a8a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a96a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a8ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a8ba`

## pseudocode

```c
__int64 __fastcall PinCachePresentPin(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // esi
  _BYTE *v7; // rdx
  _BYTE *v10; // rdi
  __int64 v11; // r12
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  HANDLE v14; // rax
  SIZE_T v15; // r8
  _BYTE *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  __int128 v23; // [rsp+30h] [rbp-40h] BYREF
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int128 v25; // [rsp+50h] [rbp-20h]
  _BYTE *v26; // [rsp+60h] [rbp-10h]
  unsigned int v27; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int dwBytes; // [rsp+C8h] [rbp+58h] BYREF
  int dwBytes_4; // [rsp+CCh] [rbp+5Ch]

  dwBytes_4 = HIDWORD(a4);
  v5 = 0;
  dwBytes = 0;
  v7 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a2 - 1 <= 7 )
  {
    v10 = 0;
    if ( !a1 || (v11 = *(_QWORD *)(a1 + 8LL * (a2 - 1))) == 0 )
    {
LABEL_12:
      v12 = -2146434961;
LABEL_13:
      if ( v10 )
      {
        v18 = v5;
        v19 = v10;
        if ( v5 )
        {
          do
          {
            *v19++ = 0;
            --v18;
          }
          while ( v18 );
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
        v7 = v26;
      }
      goto LABEL_18;
    }
    v12 = PinCacheQuery(a1, a2, a3, 0, &dwBytes, &v27, v23, *((_QWORD *)&v23 + 1), v24, *((_QWORD *)&v24 + 1), v25);
    if ( v12 )
      goto LABEL_9;
    v13 = dwBytes;
    v14 = GetProcessHeap();
    v15 = v13;
    v12 = 8;
    v16 = HeapAlloc(v14, 8u, v15);
    v10 = v16;
    if ( !v16 )
      return v12;
    v12 = PinCacheQuery(a1, a2, a3, v16, &dwBytes, &v27, v23, *((_QWORD *)&v23 + 1), v24, *((_QWORD *)&v24 + 1), v25);
    if ( v12 )
    {
LABEL_9:
      v5 = dwBytes;
    }
    else
    {
      v5 = dwBytes;
      HIDWORD(v23) = dwBytes;
      *(_QWORD *)&v23 = __PAIR64__(v27, a2);
      *(_QWORD *)&v24 = v10;
      v17 = VerifyCachedPinCallback(&v23, a5);
      v7 = v26;
      v12 = v17;
      if ( !v26 )
        goto LABEL_11;
      v12 = I_CommitPinToCache(v11, (_DWORD)v26, DWORD2(v25), a3, 1);
    }
    v7 = v26;
LABEL_11:
    if ( v12 != 4306 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v12 = 160;
LABEL_18:
  if ( v7 )
  {
    v21 = DWORD2(v25);
    if ( DWORD2(v25) )
    {
      do
      {
        *v7++ = 0;
        --v21;
      }
      while ( v21 );
      v7 = v26;
    }
    CspFreeH(v7);
  }
  return v12;
}

```

## disassembly

```asm
0x18002a814  mov     [rsp-38h+arg_8], rbx
0x18002a819  mov     [rsp-38h+dwBytes], r9
0x18002a81e  push    rbp
0x18002a81f  push    rsi
0x18002a820  push    rdi
0x18002a821  push    r12
0x18002a823  push    r13
0x18002a825  push    r14
0x18002a827  push    r15
0x18002a829  mov     rbp, rsp
0x18002a82c  sub     rsp, 70h
0x18002a830  xor     esi, esi
0x18002a832  xorps   xmm0, xmm0
0x18002a835  mov     r15d, edx
0x18002a838  mov     dword ptr [rbp+dwBytes], esi
0x18002a83b  xor     edx, edx
0x18002a83d  mov     [rbp+arg_0], esi
0x18002a840  mov     r13, r8
0x18002a843  mov     [rbp+var_10], rdx
0x18002a847  mov     r14, rcx
0x18002a84a  lea     eax, [r15-1]
0x18002a84e  movups  [rbp+var_40], xmm0
0x18002a852  movups  [rbp+var_30], xmm0
0x18002a856  movups  [rbp+var_20], xmm0
0x18002a85a  cmp     eax, 7
0x18002a85d  ja      loc_18002A984
0x18002a863  xor     edi, edi
0x18002a865  test    rcx, rcx
0x18002a868  jz      loc_18002A94B
0x18002a86e  lea     eax, [r15-1]
0x18002a872  mov     r12, [rcx+rax*8]
0x18002a876  test    r12, r12
0x18002a879  jz      loc_18002A94B
0x18002a87f  lea     rax, [rbp+arg_0]
0x18002a883  xor     r9d, r9d
0x18002a886  mov     [rsp+70h+var_48], rax
0x18002a88b  mov     edx, r15d
0x18002a88e  lea     rax, [rbp+dwBytes]
0x18002a892  mov     [rsp+70h+var_50], rax
0x18002a897  call    PinCacheQuery
0x18002a89c  mov     ebx, eax
0x18002a89e  test    eax, eax
0x18002a8a0  jnz     loc_18002A93C
0x18002a8a6  mov     ebx, dword ptr [rbp+dwBytes]
0x18002a8a9  call    cs:__imp_GetProcessHeap
0x18002a8af  mov     r8d, ebx; dwBytes
0x18002a8b2  lea     ebx, [rsi+8]
0x18002a8b5  mov     edx, ebx; dwFlags
0x18002a8b7  mov     rcx, rax; hHeap
0x18002a8ba  call    cs:__imp_HeapAlloc
0x18002a8c0  mov     rdi, rax
0x18002a8c3  test    rax, rax
0x18002a8c6  jz      loc_18002A9AE
0x18002a8cc  lea     rax, [rbp+arg_0]
0x18002a8d0  mov     r9, rdi
0x18002a8d3  mov     [rsp+70h+var_48], rax
0x18002a8d8  mov     r8, r13
0x18002a8db  lea     rax, [rbp+dwBytes]
0x18002a8df  mov     edx, r15d
0x18002a8e2  mov     rcx, r14
0x18002a8e5  mov     [rsp+70h+var_50], rax
0x18002a8ea  call    PinCacheQuery
0x18002a8ef  mov     ebx, eax
0x18002a8f1  test    eax, eax
0x18002a8f3  jnz     short loc_18002A93C
0x18002a8f5  mov     eax, [rbp+arg_0]
0x18002a8f8  lea     rcx, [rbp+var_40]
0x18002a8fc  mov     esi, dword ptr [rbp+dwBytes]
0x18002a8ff  mov     rdx, [rbp+arg_20]
0x18002a903  mov     dword ptr [rbp+var_40+4], eax
0x18002a906  mov     dword ptr [rbp+var_40+0Ch], esi
0x18002a909  mov     dword ptr [rbp+var_40], r15d
0x18002a90d  mov     qword ptr [rbp+var_30], rdi
0x18002a911  call    VerifyCachedPinCallback
0x18002a916  mov     rdx, [rbp+var_10]
0x18002a91a  mov     ebx, eax
0x18002a91c  test    rdx, rdx
0x18002a91f  jz      short loc_18002A943
0x18002a921  mov     r8d, dword ptr [rbp+var_20+8]
0x18002a925  mov     r9, r13
0x18002a928  mov     rcx, r12
0x18002a92b  mov     dword ptr [rsp+70h+var_50], 1
0x18002a933  call    I_CommitPinToCache
0x18002a938  mov     ebx, eax
0x18002a93a  jmp     short loc_18002A93F
0x18002a93c  mov     esi, dword ptr [rbp+dwBytes]
0x18002a93f  mov     rdx, [rbp+var_10]
0x18002a943  cmp     ebx, 10D2h
0x18002a949  jnz     short loc_18002A950
0x18002a94b  mov     ebx, 8010006Fh
0x18002a950  test    rdi, rdi
0x18002a953  jz      short loc_18002A989
0x18002a955  mov     ecx, esi
0x18002a957  mov     rax, rdi
0x18002a95a  test    esi, esi
0x18002a95c  jz      short loc_18002A96A
0x18002a95e  mov     byte ptr [rax], 0
0x18002a961  inc     rax
0x18002a964  sub     rcx, 1
0x18002a968  jnz     short loc_18002A95E
0x18002a96a  call    cs:__imp_GetProcessHeap
0x18002a970  mov     r8, rdi; lpMem
0x18002a973  xor     edx, edx; dwFlags
0x18002a975  mov     rcx, rax; hHeap
0x18002a978  call    cs:__imp_HeapFree
0x18002a97e  mov     rdx, [rbp+var_10]
0x18002a982  jmp     short loc_18002A989
0x18002a984  mov     ebx, 0A0h
0x18002a989  test    rdx, rdx
0x18002a98c  jz      short loc_18002A9AE
0x18002a98e  mov     eax, dword ptr [rbp+var_20+8]
0x18002a991  test    rax, rax
0x18002a994  jz      short loc_18002A9A6
0x18002a996  mov     byte ptr [rdx], 0
0x18002a999  inc     rdx
0x18002a99c  sub     rax, 1
0x18002a9a0  jnz     short loc_18002A996
0x18002a9a2  mov     rdx, [rbp+var_10]
0x18002a9a6  mov     rcx, rdx
0x18002a9a9  call    CspFreeH
0x18002a9ae  mov     eax, ebx
0x18002a9b0  mov     rbx, [rsp+70h+arg_8]
0x18002a9b8  add     rsp, 70h
0x18002a9bc  pop     r15
0x18002a9be  pop     r14
0x18002a9c0  pop     r13
0x18002a9c2  pop     r12
0x18002a9c4  pop     rdi
0x18002a9c5  pop     rsi
0x18002a9c6  pop     rbp
0x18002a9c7  retn
```
