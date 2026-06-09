# CMFSampleProtection::~CMFSampleProtection(void)

- ea: `0x18003137c`
- end: `0x1800314da`
- name: `??1CMFSampleProtection@@QEAA@XZ`
- size: `350`
- prototype: `void __fastcall(CMFSampleProtection *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ffac`
- `0x18006be5c`
- `0x1800961a7`

## callees

- `0x18003137c`
- `0x18004a5d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031438`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031438`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFSampleProtection::~CMFSampleProtection(CMFSampleProtection *this)
{
  _BYTE *v2; // rdx
  _BYTE *v3; // rdx
  _BYTE *v4; // rdx
  unsigned __int8 v5; // r8
  unsigned __int8 v6; // r8
  unsigned __int8 v7; // r8
  unsigned int i; // edi
  int v9; // [rsp+30h] [rbp+8h]

  *(_QWORD *)this = &CMFSampleProtection::`vftable';
  if ( *((_DWORD *)this + 97) == 3 )
  {
    for ( i = 0; i < 0x10; ++i )
    {
      if ( (int)CMFSampleProtection::Clean(this, i) < 0 )
        break;
    }
  }
  *((_DWORD *)this + 153) = 0;
  v2 = (char *)this + 36;
  v9 = -1749680893;
  if ( this != (CMFSampleProtection *)-36LL && (char *)this + 56 >= (char *)this + 36 )
  {
    v5 = 0;
    while ( v2 < (_BYTE *)this + 56 )
    {
      *v2 = *((_BYTE *)&v9 + v5);
      v5 = (v5 + 1) & 3;
      ++v2;
    }
  }
  v3 = (char *)this + 64;
  v9 = -1749680893;
  if ( this != (CMFSampleProtection *)-64LL && (char *)this + 336 >= (char *)this + 64 )
  {
    v6 = 0;
    while ( v3 < (_BYTE *)this + 336 )
    {
      *v3 = *((_BYTE *)&v9 + v6);
      v6 = (v6 + 1) & 3;
      ++v3;
    }
  }
  v4 = (char *)this + 372;
  v9 = -1749680893;
  if ( this != (CMFSampleProtection *)-372LL && (char *)this + 388 >= (char *)this + 372 )
  {
    v7 = 0;
    while ( v4 < (_BYTE *)this + 388 )
    {
      *v4 = *((_BYTE *)&v9 + v7);
      v7 = (v7 + 1) & 3;
      ++v4;
    }
  }
  *(_QWORD *)((char *)this + 388) = 0;
  *((_QWORD *)this + 75) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
}

```

## disassembly

```asm
0x18003137c  mov     [rsp+arg_8], rbx
0x180031381  push    rdi
0x180031382  sub     rsp, 20h
0x180031386  mov     rbx, rcx
0x180031389  lea     rax, ??_7CMFSampleProtection@@6B@; const CMFSampleProtection::`vftable'
0x180031390  mov     [rcx], rax
0x180031393  cmp     dword ptr [rcx+184h], 3
0x18003139a  jz      loc_1800314BA
0x1800313a0  mov     dword ptr [rbx+264h], 0
0x1800313aa  lea     rdx, [rbx+24h]
0x1800313ae  mov     r10d, 97B5FD03h
0x1800313b4  mov     [rsp+28h+arg_0], r10d
0x1800313b9  test    rdx, rdx
0x1800313bc  jz      short loc_1800313CB
0x1800313be  lea     r9, [rdx+14h]
0x1800313c2  cmp     r9, rdx
0x1800313c5  jnb     loc_180031451
0x1800313cb  lea     rdx, [rbx+40h]
0x1800313cf  mov     [rsp+28h+arg_0], r10d
0x1800313d4  test    rdx, rdx
0x1800313d7  jz      short loc_1800313E9
0x1800313d9  lea     r9, [rdx+110h]
0x1800313e0  cmp     r9, rdx
0x1800313e3  jnb     loc_180031474
0x1800313e9  lea     rdx, [rbx+174h]
0x1800313f0  mov     [rsp+28h+arg_0], r10d
0x1800313f5  test    rdx, rdx
0x1800313f8  jz      short loc_180031407
0x1800313fa  lea     r9, [rdx+10h]
0x1800313fe  cmp     r9, rdx
0x180031401  jnb     loc_180031497
0x180031407  mov     qword ptr [rbx+184h], 0
0x180031412  mov     qword ptr [rbx+258h], 0
0x18003141d  lea     rcx, [rbx+2C0h]; lpCriticalSection
0x180031424  call    cs:__imp_DeleteCriticalSection
0x18003142b  nop     dword ptr [rax+rax+00h]
0x180031430  nop
0x180031431  lea     rcx, [rbx+268h]; lpCriticalSection
0x180031438  call    cs:__imp_DeleteCriticalSection
0x18003143f  nop     dword ptr [rax+rax+00h]
0x180031444  nop
0x180031445  mov     rbx, [rsp+28h+arg_8]
0x18003144a  add     rsp, 20h
0x18003144e  pop     rdi
0x18003144f  retn
0x180031451  xor     r8b, r8b
0x180031454  jmp     short loc_18003146A
0x180031456  movzx   eax, r8b
0x18003145a  mov     cl, byte ptr [rsp+rax+28h+arg_0]
0x18003145e  mov     [rdx], cl
0x180031460  inc     r8b
0x180031463  and     r8b, 3
0x180031467  inc     rdx
0x18003146a  cmp     rdx, r9
0x18003146d  jb      short loc_180031456
0x18003146f  jmp     loc_1800313CB
0x180031474  xor     r8b, r8b
0x180031477  jmp     short loc_18003148D
0x180031479  movzx   eax, r8b
0x18003147d  mov     cl, byte ptr [rsp+rax+28h+arg_0]
0x180031481  mov     [rdx], cl
0x180031483  inc     r8b
0x180031486  and     r8b, 3
0x18003148a  inc     rdx
0x18003148d  cmp     rdx, r9
0x180031490  jb      short loc_180031479
0x180031492  jmp     loc_1800313E9
0x180031497  xor     r8b, r8b
0x18003149a  jmp     short loc_1800314B0
0x18003149c  movzx   eax, r8b
0x1800314a0  mov     cl, byte ptr [rsp+rax+28h+arg_0]
0x1800314a4  mov     [rdx], cl
0x1800314a6  inc     r8b
0x1800314a9  and     r8b, 3
0x1800314ad  inc     rdx
0x1800314b0  cmp     rdx, r9
0x1800314b3  jb      short loc_18003149C
0x1800314b5  jmp     loc_180031407
0x1800314ba  xor     edi, edi
0x1800314bc  mov     edx, edi; unsigned int
0x1800314be  mov     rcx, rbx; this
0x1800314c1  call    ?Clean@CMFSampleProtection@@QEAAJK@Z; CMFSampleProtection::Clean(ulong)
0x1800314c6  test    eax, eax
0x1800314c8  js      loc_1800313A0
0x1800314ce  inc     edi
0x1800314d0  cmp     edi, 10h
0x1800314d3  jb      short loc_1800314BC
0x1800314d5  jmp     loc_1800313A0
```
