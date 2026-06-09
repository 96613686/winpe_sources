# GrowCompBitsBuffer

- ea: `0x180004050`
- end: `0x18000410a`
- name: `GrowCompBitsBuffer`
- size: `186`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000373c`

## callees

- `0x180004050`
- `0x18000f128`
- `0x18000f1c8`
- `0x180018992`

## pseudocode

```c
__int64 __fastcall GrowCompBitsBuffer(__int64 a1)
{
  int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // edi
  _BYTE *v5; // rax
  _BYTE *v6; // rsi
  _BYTE *v7; // rcx
  unsigned __int64 v8; // rcx
  __int64 result; // rax

  v2 = *(_DWORD *)(a1 + 1620);
  if ( !v2 )
    return 0;
  v3 = *(_DWORD *)(a1 + 1616);
  v4 = v3 + v2;
  if ( v3 + v2 < v3 )
    return 0;
  v5 = pMemAlloc(v4);
  v6 = v5;
  if ( !v5 )
    return 0;
  memcpy_0(v5, *(const void **)(a1 + 1600), *(unsigned int *)(a1 + 1616));
  v7 = *(_BYTE **)(a1 + 1600);
  *(_QWORD *)(a1 + 1592) += v6 - v7;
  pMemFree(v7);
  v8 = 4LL * *(unsigned int *)(a1 + 1692);
  *(_QWORD *)(a1 + 1600) = v6;
  if ( v8 > 0xFFFFFFFF || v4 < (unsigned int)v8 )
    return 0;
  *(_DWORD *)(a1 + 1616) = v4;
  result = 1;
  *(_QWORD *)(a1 + 1608) = &v6[v4 - (unsigned int)v8];
  return result;
}

```

## disassembly

```asm
0x180004050  mov     [rsp+arg_0], rbx
0x180004055  mov     [rsp+arg_8], rsi
0x18000405a  push    rdi
0x18000405b  sub     rsp, 20h
0x18000405f  mov     rbx, rcx
0x180004062  mov     ecx, [rcx+654h]
0x180004068  test    ecx, ecx
0x18000406a  jz      loc_1800040F7
0x180004070  mov     eax, [rbx+650h]
0x180004076  lea     edi, [rax+rcx]
0x180004079  cmp     edi, eax
0x18000407b  jb      short loc_1800040F7
0x18000407d  mov     ecx, edi; dwBytes
0x18000407f  call    pMemAlloc
0x180004084  mov     rsi, rax
0x180004087  test    rax, rax
0x18000408a  jz      short loc_1800040F7
0x18000408c  mov     r8d, [rbx+650h]; Size
0x180004093  mov     rcx, rax; void *
0x180004096  mov     rdx, [rbx+640h]; Src
0x18000409d  call    memcpy_0
0x1800040a2  mov     rcx, [rbx+640h]; lpMem
0x1800040a9  mov     rdx, rsi
0x1800040ac  sub     rdx, rcx
0x1800040af  add     [rbx+638h], rdx
0x1800040b6  call    pMemFree
0x1800040bb  mov     ecx, [rbx+69Ch]
0x1800040c1  mov     eax, 0FFFFFFFFh
0x1800040c6  shl     rcx, 2
0x1800040ca  mov     [rbx+640h], rsi
0x1800040d1  cmp     rcx, rax
0x1800040d4  ja      short loc_1800040F7
0x1800040d6  cmp     edi, ecx
0x1800040d8  jb      short loc_1800040F7
0x1800040da  mov     eax, edi
0x1800040dc  mov     [rbx+650h], edi
0x1800040e2  sub     eax, ecx
0x1800040e4  mov     ecx, eax
0x1800040e6  mov     eax, 1
0x1800040eb  add     rcx, rsi
0x1800040ee  mov     [rbx+648h], rcx
0x1800040f5  jmp     short loc_1800040F9
0x1800040f7  xor     eax, eax
0x1800040f9  mov     rbx, [rsp+28h+arg_0]
0x1800040fe  mov     rsi, [rsp+28h+arg_8]
0x180004103  add     rsp, 20h
0x180004107  pop     rdi
0x180004108  retn
```
