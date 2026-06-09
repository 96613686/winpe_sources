# CAVIStream::CS::ReadFormat(long,void *,long *)

- ea: `0x18000b0f0`
- end: `0x18000b255`
- name: `?ReadFormat@CS@CAVIStream@@UEAAJJPEAXPEAJ@Z`
- size: `357`
- prototype: `__int64 __fastcall(CAVIStream::CS *this, unsigned int, char *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b0f0`
- `0x18000b368`
- `0x1800152e4`
- `0x180017365`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b11d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b11d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b14f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b229`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b240`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b14f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b229`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b240`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::ReadFormat(CAVIStream::CS *this, unsigned int a2, char *a3, int *a4)
{
  __int64 v4; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // ecx
  int v11; // eax
  int Sample; // eax
  int v14; // r8d
  int v15; // ebp
  unsigned int *v16; // r15
  unsigned int v17; // eax
  const void *v18; // rdx
  size_t v19; // r8
  char *v20; // rcx
  int v21; // ecx
  int v22; // eax

  v4 = *((_QWORD *)this + 1);
  v9 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 272) + 1264LL);
  EnterCriticalSection(v9);
  if ( !a4 || (v10 = *(_DWORD *)(v4 + 1344), v10 < 0) )
  {
LABEL_6:
    if ( v9 )
      LeaveCriticalSection(v9);
    return 2147762282LL;
  }
  if ( !a3 || (v11 = *a4) == 0 )
  {
    *a4 = v10;
    goto LABEL_30;
  }
  if ( v11 < 0 )
    goto LABEL_6;
  if ( *(_DWORD *)(v4 + 64) != 1935960438 || (*(_DWORD *)(v4 + 72) & 0x10000) == 0 )
  {
    v18 = *(const void **)(v4 + 1336);
    if ( v11 >= v10 )
      v11 = *(_DWORD *)(v4 + 1344);
    v20 = a3;
    v19 = v11;
    goto LABEL_24;
  }
  Sample = StreamFindSample(*(_QWORD *)(v4 + 1400), a2, 68);
  v14 = *(_DWORD *)(v4 + 304);
  v15 = 0;
  if ( Sample >= 0 )
    v15 = Sample;
  if ( v15 != v14 )
  {
    CAVIStream::CS::ReadPalette(this, v15, v14, (struct tagRGBQUAD *)(v4 + 308));
    *(_DWORD *)(v4 + 304) = v15;
  }
  v16 = *(unsigned int **)(v4 + 1336);
  v17 = *v16;
  if ( *v16 >= *a4 )
    v17 = *a4;
  memmove_0(a3, v16, v17);
  if ( *a4 > *v16 )
  {
    v18 = (const void *)(v4 + 308);
    v19 = 4LL * v16[8];
    if ( v19 >= *a4 - *v16 )
      v19 = *a4 - *v16;
    v20 = &a3[*v16];
LABEL_24:
    memmove_0(v20, v18, v19);
  }
  v21 = *(_DWORD *)(v4 + 1344);
  v22 = *a4;
  *a4 = v21;
  if ( v22 < v21 )
  {
    if ( v9 )
      LeaveCriticalSection(v9);
    return 2147762292LL;
  }
LABEL_30:
  if ( v9 )
    LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x18000b0f0  push    rbx
0x18000b0f2  push    rbp
0x18000b0f3  push    rsi
0x18000b0f4  push    rdi
0x18000b0f5  push    r14
0x18000b0f7  push    r15
0x18000b0f9  sub     rsp, 28h
0x18000b0fd  mov     rdi, [rcx+8]
0x18000b101  mov     r15, rcx
0x18000b104  mov     rsi, r9
0x18000b107  mov     r14, r8
0x18000b10a  mov     ebp, edx
0x18000b10c  mov     rbx, [rdi+110h]
0x18000b113  add     rbx, 4F0h
0x18000b11a  mov     rcx, rbx; lpCriticalSection
0x18000b11d  call    cs:__imp_EnterCriticalSection
0x18000b123  test    rsi, rsi
0x18000b126  jz      short loc_18000B147
0x18000b128  mov     ecx, [rdi+540h]
0x18000b12e  test    ecx, ecx
0x18000b130  js      short loc_18000B147
0x18000b132  test    r14, r14
0x18000b135  jz      loc_18000B236
0x18000b13b  mov     eax, [rsi]
0x18000b13d  test    eax, eax
0x18000b13f  jz      loc_18000B236
0x18000b145  jns     short loc_18000B15F
0x18000b147  test    rbx, rbx
0x18000b14a  jz      short loc_18000B155
0x18000b14c  mov     rcx, rbx; lpCriticalSection
0x18000b14f  call    cs:__imp_LeaveCriticalSection
0x18000b155  mov     eax, 8004406Ah
0x18000b15a  jmp     loc_18000B248
0x18000b15f  cmp     dword ptr [rdi+40h], 73646976h
0x18000b166  jnz     loc_18000B1FC
0x18000b16c  test    dword ptr [rdi+48h], 10000h
0x18000b173  jz      loc_18000B1FC
0x18000b179  mov     rcx, [rdi+578h]
0x18000b180  mov     r8d, 44h ; 'D'
0x18000b186  mov     edx, ebp
0x18000b188  call    StreamFindSample
0x18000b18d  mov     r8d, [rdi+130h]; int
0x18000b194  xor     ebp, ebp
0x18000b196  test    eax, eax
0x18000b198  cmovns  ebp, eax
0x18000b19b  cmp     ebp, r8d
0x18000b19e  jz      short loc_18000B1B7
0x18000b1a0  lea     r9, [rdi+134h]; struct tagRGBQUAD *
0x18000b1a7  mov     edx, ebp; int
0x18000b1a9  mov     rcx, r15; this
0x18000b1ac  call    ?ReadPalette@CS@CAVIStream@@AEAAXJJPEAUtagRGBQUAD@@@Z; CAVIStream::CS::ReadPalette(long,long,tagRGBQUAD *)
0x18000b1b1  mov     [rdi+130h], ebp
0x18000b1b7  mov     r15, [rdi+538h]
0x18000b1be  mov     rcx, r14; void *
0x18000b1c1  mov     rdx, r15; Src
0x18000b1c4  mov     eax, [r15]
0x18000b1c7  cmp     eax, [rsi]
0x18000b1c9  cmovnb  eax, [rsi]
0x18000b1cc  mov     r8d, eax; Size
0x18000b1cf  call    memmove_0
0x18000b1d4  mov     eax, [rsi]
0x18000b1d6  cmp     eax, [r15]
0x18000b1d9  jbe     short loc_18000B213
0x18000b1db  sub     eax, [r15]
0x18000b1de  lea     rdx, [rdi+134h]
0x18000b1e5  mov     r8d, [r15+20h]
0x18000b1e9  mov     ecx, [r15]
0x18000b1ec  shl     r8, 2
0x18000b1f0  cmp     r8, rax
0x18000b1f3  cmovnb  r8, rax
0x18000b1f7  add     rcx, r14
0x18000b1fa  jmp     short loc_18000B20E
0x18000b1fc  mov     rdx, [rdi+538h]; Src
0x18000b203  cmp     eax, ecx
0x18000b205  cmovge  eax, ecx
0x18000b208  mov     rcx, r14; void *
0x18000b20b  movsxd  r8, eax; Size
0x18000b20e  call    memmove_0
0x18000b213  mov     ecx, [rdi+540h]
0x18000b219  mov     eax, [rsi]
0x18000b21b  mov     [rsi], ecx
0x18000b21d  cmp     eax, ecx
0x18000b21f  jge     short loc_18000B238
0x18000b221  test    rbx, rbx
0x18000b224  jz      short loc_18000B22F
0x18000b226  mov     rcx, rbx; lpCriticalSection
0x18000b229  call    cs:__imp_LeaveCriticalSection
0x18000b22f  mov     eax, 80044074h
0x18000b234  jmp     short loc_18000B248
0x18000b236  mov     [rsi], ecx
0x18000b238  test    rbx, rbx
0x18000b23b  jz      short loc_18000B246
0x18000b23d  mov     rcx, rbx; lpCriticalSection
0x18000b240  call    cs:__imp_LeaveCriticalSection
0x18000b246  xor     eax, eax
0x18000b248  add     rsp, 28h
0x18000b24c  pop     r15
0x18000b24e  pop     r14
0x18000b250  pop     rdi
0x18000b251  pop     rsi
0x18000b252  pop     rbp
0x18000b253  pop     rbx
0x18000b254  retn
```
