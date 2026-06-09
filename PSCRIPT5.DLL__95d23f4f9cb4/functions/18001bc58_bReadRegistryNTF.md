# bReadRegistryNTF

- ea: `0x18001bc58`
- end: `0x18001bd98`
- name: `bReadRegistryNTF`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001af6c`

## callees

- `0x18001bc58`
- `0x18001bda0`
- `0x18001be9c`
- `0x18001c180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bd65`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bd7c`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bd65`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bd7c`
- `KERNEL32!LocalFree` at `0x18001bd45`
- `KERNEL32!LocalFree` at `0x18001bd45`
- `KERNEL32!LocalAlloc` at `0x18001bcbd`
- `KERNEL32!LocalAlloc` at `0x18001bcbd`

## pseudocode

```c
__int64 __fastcall bReadRegistryNTF(__int64 a1)
{
  __int64 v1; // rsi
  int v2; // ebp
  void **v4; // rdi
  __int64 v5; // rbx
  int v6; // r14d
  HLOCAL v7; // r15
  char GlyphSetEntry; // al
  void *v9; // rcx

  v1 = *(_QWORD *)(a1 + 3656);
  v2 = 0;
  v4 = (void **)(v1 + 40);
  *(_DWORD *)(v1 + 20) = 0;
  *(_QWORD *)(v1 + 40) = 0;
  *(_DWORD *)(v1 + 60) = 0;
  *(_QWORD *)(v1 + 80) = 0;
  v5 = *(_QWORD *)(a1 + 3648);
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 44) )
      v6 = v5 + *(_DWORD *)(v5 + 44);
    else
      v6 = 0;
    v7 = LocalAlloc(0x40u, 48 * *(_DWORD *)(v5 + 40));
    if ( !v7 )
    {
LABEL_13:
      *v4 = 0;
      return 0;
    }
    if ( *(int *)(v5 + 40) > 0 )
    {
      while ( (unsigned int)bStoreEntryData(v5, v6 + 32 * v2, (_DWORD)v7, v2, 7) )
      {
        if ( ++v2 >= *(_DWORD *)(v5 + 40) )
          goto LABEL_9;
      }
      LocalFree(v7);
      goto LABEL_13;
    }
LABEL_9:
    *(_DWORD *)(v1 + 20) = v2;
    *v4 = v7;
    GlyphSetEntry = pCreateGlyphSetEntry(*(_QWORD *)(a1 + 3648), 18, v1 + 60, v1 + 80);
    v9 = *v4;
    if ( !GlyphSetEntry )
    {
      vFreeDataEntry(v9);
      *v4 = 0;
      *(_DWORD *)(v1 + 20) = 0;
      return 0;
    }
    qsort(v9, *(int *)(v1 + 20), 0x30u, compare);
    qsort(*(void **)(v1 + 80), *(int *)(v1 + 60), 0x30u, compare);
  }
  return 1;
}

```

## disassembly

```asm
0x18001bc58  push    rbx
0x18001bc5a  push    rbp
0x18001bc5b  push    rsi
0x18001bc5c  push    rdi
0x18001bc5d  push    r12
0x18001bc5f  push    r13
0x18001bc61  push    r14
0x18001bc63  push    r15
0x18001bc65  sub     rsp, 38h
0x18001bc69  mov     rsi, [rcx+0E48h]
0x18001bc70  xor     ebp, ebp
0x18001bc72  mov     r13, rcx
0x18001bc75  lea     rdi, [rsi+28h]
0x18001bc79  mov     [rsi+14h], ebp
0x18001bc7c  lea     r12, [rsi+3Ch]
0x18001bc80  mov     [rdi], rbp
0x18001bc83  mov     [r12], ebp
0x18001bc87  mov     [rsi+50h], rbp
0x18001bc8b  mov     rbx, [rcx+0E40h]
0x18001bc92  test    rbx, rbx
0x18001bc95  jz      loc_18001BD82
0x18001bc9b  cmp     [rbx+2Ch], ebp
0x18001bc9e  jz      short loc_18001BCA9
0x18001bca0  mov     r14d, [rbx+2Ch]
0x18001bca4  add     r14, rbx
0x18001bca7  jmp     short loc_18001BCAC
0x18001bca9  mov     r14, rbp
0x18001bcac  mov     eax, [rbx+28h]
0x18001bcaf  lea     ecx, [rax+rax*2]
0x18001bcb2  shl     ecx, 4
0x18001bcb5  movsxd  rdx, ecx; uBytes
0x18001bcb8  mov     ecx, 40h ; '@'; uFlags
0x18001bcbd  call    cs:__imp_LocalAlloc
0x18001bcc3  mov     r15, rax
0x18001bcc6  test    rax, rax
0x18001bcc9  jnz     short loc_18001BCD0
0x18001bccb  mov     rax, rbp
0x18001bcce  jmp     short loc_18001BD4D
0x18001bcd0  cmp     [rbx+28h], ebp
0x18001bcd3  jle     short loc_18001BD00
0x18001bcd5  movsxd  rdx, ebp
0x18001bcd8  mov     r9d, ebp
0x18001bcdb  shl     rdx, 5
0x18001bcdf  mov     r8, r15
0x18001bce2  add     rdx, r14
0x18001bce5  mov     [rsp+78h+var_58], 7
0x18001bced  mov     rcx, rbx
0x18001bcf0  call    bStoreEntryData
0x18001bcf5  test    eax, eax
0x18001bcf7  jz      short loc_18001BD42
0x18001bcf9  inc     ebp
0x18001bcfb  cmp     ebp, [rbx+28h]
0x18001bcfe  jl      short loc_18001BCD5
0x18001bd00  mov     [rsi+14h], ebp
0x18001bd03  lea     rbx, [rsi+50h]
0x18001bd07  mov     [rdi], r15
0x18001bd0a  mov     r9, rbx
0x18001bd0d  mov     rcx, [r13+0E40h]
0x18001bd14  mov     r8, r12
0x18001bd17  mov     edx, 12h
0x18001bd1c  call    pCreateGlyphSetEntry
0x18001bd21  mov     rcx, [rdi]; hMem
0x18001bd24  test    al, al
0x18001bd26  jnz     short loc_18001BD52
0x18001bd28  mov     edx, [rsi+14h]
0x18001bd2b  call    vFreeDataEntry
0x18001bd30  mov     qword ptr [rdi], 0
0x18001bd37  mov     dword ptr [rsi+14h], 0
0x18001bd3e  xor     eax, eax
0x18001bd40  jmp     short loc_18001BD87
0x18001bd42  mov     rcx, r15; hMem
0x18001bd45  call    cs:__imp_LocalFree
0x18001bd4b  xor     eax, eax
0x18001bd4d  mov     [rdi], rax
0x18001bd50  jmp     short loc_18001BD3E
0x18001bd52  movsxd  rdx, dword ptr [rsi+14h]; NumOfElements
0x18001bd56  lea     r9, compare; CompareFunction
0x18001bd5d  mov     esi, 30h ; '0'
0x18001bd62  mov     r8d, esi; SizeOfElements
0x18001bd65  call    cs:__imp_qsort
0x18001bd6b  movsxd  rdx, dword ptr [r12]; NumOfElements
0x18001bd6f  lea     r9, compare; CompareFunction
0x18001bd76  mov     rcx, [rbx]; Base
0x18001bd79  mov     r8d, esi; SizeOfElements
0x18001bd7c  call    cs:__imp_qsort
0x18001bd82  mov     eax, 1
0x18001bd87  add     rsp, 38h
0x18001bd8b  pop     r15
0x18001bd8d  pop     r14
0x18001bd8f  pop     r13
0x18001bd91  pop     r12
0x18001bd93  pop     rdi
0x18001bd94  pop     rsi
0x18001bd95  pop     rbp
0x18001bd96  pop     rbx
0x18001bd97  retn
```
