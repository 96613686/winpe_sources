# ReadInIndex

- ea: `0x18000b25c`
- end: `0x18000b35f`
- name: `ReadInIndex`
- size: `259`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a060`

## callees

- `0x18000b25c`
- `0x180014880`
- `0x180014eec`
- `0x180015108`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b333`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b333`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000b28d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000b28d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b32a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b33c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b32a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b33c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000b284`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000b284`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b345`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b345`

## pseudocode

```c
__int64 __fastcall ReadInIndex(__int64 a1, unsigned int a2, int a3, int a4)
{
  unsigned int v6; // r14d
  HGLOBAL v9; // rax
  _DWORD *v10; // rdi
  __int64 v11; // rax
  int v12; // ebx
  unsigned int v13; // ebp
  __int64 v14; // rax
  HGLOBAL v15; // rax
  HGLOBAL v16; // rax

  v6 = 0;
  v9 = GlobalAlloc(0x42u, 0x8000u);
  v10 = GlobalLock(v9);
  if ( v10 )
  {
    v11 = IndexCreate();
    *(_QWORD *)(a1 + 1248) = v11;
    if ( v11 )
    {
      if ( a2 )
      {
        v12 = a3;
        if ( (*(_BYTE *)(a1 + 92) & 0x20) == 0 )
          v12 = -1;
        while ( 1 )
        {
          v13 = a2;
          if ( a2 > 0x8000 )
            v13 = 0x8000;
          if ( (unsigned int)shfileRead(*(_QWORD *)(a1 + 664), v10, v13) != v13 )
            break;
          if ( v12 == -1 )
            v12 = a3 - v10[2] + 4;
          v14 = IndexAddFileIndex(*(LPCVOID *)(a1 + 1248), a4);
          *(_QWORD *)(a1 + 1248) = v14;
          if ( !v14 )
            break;
          a2 -= v13;
          if ( !a2 )
            goto LABEL_13;
        }
      }
      else
      {
LABEL_13:
        v6 = 1;
      }
    }
    v15 = GlobalHandle(v10);
    GlobalUnlock(v15);
    v16 = GlobalHandle(v10);
    GlobalFree(v16);
  }
  return v6;
}

```

## disassembly

```asm
0x18000b25c  push    rbx
0x18000b25e  push    rbp
0x18000b25f  push    rsi
0x18000b260  push    rdi
0x18000b261  push    r12
0x18000b263  push    r13
0x18000b265  push    r14
0x18000b267  push    r15
0x18000b269  sub     rsp, 38h
0x18000b26d  mov     esi, edx
0x18000b26f  mov     r15, rcx
0x18000b272  xor     r14d, r14d
0x18000b275  mov     edx, 8000h; dwBytes
0x18000b27a  mov     r13d, r9d
0x18000b27d  mov     r12d, r8d
0x18000b280  lea     ecx, [r14+42h]; uFlags
0x18000b284  call    cs:__imp_GlobalAlloc
0x18000b28a  mov     rcx, rax; hMem
0x18000b28d  call    cs:__imp_GlobalLock
0x18000b293  mov     rdi, rax
0x18000b296  test    rax, rax
0x18000b299  jz      loc_18000B34B
0x18000b29f  call    IndexCreate
0x18000b2a4  mov     [r15+4E0h], rax
0x18000b2ab  test    rax, rax
0x18000b2ae  jz      short loc_18000B327
0x18000b2b0  test    esi, esi
0x18000b2b2  jz      short loc_18000B321
0x18000b2b4  test    byte ptr [r15+5Ch], 20h
0x18000b2b9  lea     eax, [r14-1]
0x18000b2bd  mov     ebx, r12d
0x18000b2c0  cmovz   ebx, eax
0x18000b2c3  mov     rcx, [r15+298h]
0x18000b2ca  mov     eax, 8000h
0x18000b2cf  cmp     esi, eax
0x18000b2d1  mov     ebp, esi
0x18000b2d3  mov     rdx, rdi
0x18000b2d6  cmova   ebp, eax
0x18000b2d9  mov     r8d, ebp
0x18000b2dc  call    shfileRead
0x18000b2e1  cmp     eax, ebp
0x18000b2e3  jnz     short loc_18000B327
0x18000b2e5  movsxd  r8, ebp
0x18000b2e8  shr     r8, 4
0x18000b2ec  cmp     ebx, 0FFFFFFFFh
0x18000b2ef  jnz     short loc_18000B2FA
0x18000b2f1  mov     ebx, r12d
0x18000b2f4  sub     ebx, [rdi+8]
0x18000b2f7  add     ebx, 4
0x18000b2fa  mov     rcx, [r15+4E0h]; pMem
0x18000b301  mov     r9d, ebx
0x18000b304  mov     rdx, rdi
0x18000b307  mov     [rsp+78h+var_58], r13d; int
0x18000b30c  call    IndexAddFileIndex
0x18000b311  mov     [r15+4E0h], rax
0x18000b318  test    rax, rax
0x18000b31b  jz      short loc_18000B327
0x18000b31d  sub     esi, ebp
0x18000b31f  jnz     short loc_18000B2C3
0x18000b321  mov     r14d, 1
0x18000b327  mov     rcx, rdi; pMem
0x18000b32a  call    cs:__imp_GlobalHandle
0x18000b330  mov     rcx, rax; hMem
0x18000b333  call    cs:__imp_GlobalUnlock
0x18000b339  mov     rcx, rdi; pMem
0x18000b33c  call    cs:__imp_GlobalHandle
0x18000b342  mov     rcx, rax; hMem
0x18000b345  call    cs:__imp_GlobalFree
0x18000b34b  mov     eax, r14d
0x18000b34e  add     rsp, 38h
0x18000b352  pop     r15
0x18000b354  pop     r14
0x18000b356  pop     r13
0x18000b358  pop     r12
0x18000b35a  pop     rdi
0x18000b35b  pop     rsi
0x18000b35c  pop     rbp
0x18000b35d  pop     rbx
0x18000b35e  retn
```
