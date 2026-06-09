# CAVIStream::CS::ReadPalette(long,long,tagRGBQUAD *)

- ea: `0x18000b368`
- end: `0x18000b5ac`
- name: `?ReadPalette@CS@CAVIStream@@AEAAXJJPEAUtagRGBQUAD@@@Z`
- size: `580`
- prototype: `void __fastcall(CAVIStream::CS *this, int, int, struct tagRGBQUAD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b0f0`

## callees

- `0x18000b368`
- `0x180014880`
- `0x1800152e4`
- `0x180017365`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b397`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b397`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b595`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b595`
- `WINMM!mmioSeek` at `0x18000b457`
- `WINMM!mmioSeek` at `0x18000b457`

## pseudocode

```c
void __fastcall CAVIStream::CS::ReadPalette(CAVIStream::CS *this, int a2, int a3, struct tagRGBQUAD *a4)
{
  __int64 v4; // rsi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int *v9; // r15
  int v10; // ebp
  __int64 v11; // r8
  __int64 i; // rdx
  LONG v13; // ebp
  int v14; // r14d
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // ebp
  __int64 v18; // r8
  int v19; // eax
  int Sample; // eax
  unsigned int v21; // edi

  v4 = *((_QWORD *)this + 1);
  v8 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 272) + 1264LL);
  EnterCriticalSection(v8);
  v9 = *(int **)(v4 + 1336);
  v10 = 0;
  if ( a3 <= a2 )
    v10 = a3;
  if ( v10 <= 0 )
  {
    v11 = 256;
    if ( (unsigned int)v9[8] < 0x100 )
      v11 = (unsigned int)v9[8];
    memmove_0(a4, (char *)v9 + *v9, 4 * v11);
    v10 = -1;
  }
  for ( i = (unsigned int)(v10 + 1); ; i = v21 + 1 )
  {
    Sample = StreamFindSample(*(_QWORD *)(v4 + 1400), i, 65);
    v21 = Sample;
    if ( Sample < 0 || Sample > a2 || Sample == v10 )
      break;
    if ( Sample > *(_DWORD *)(v4 + 92) )
    {
      v13 = StreamFindSample(*(_QWORD *)(v4 + 1400), (unsigned int)Sample, 8256);
      v14 = StreamFindSample(*(_QWORD *)(v4 + 1400), v21, 4160);
      if ( v14 > 8 * v9[8] + 4 )
        break;
      v15 = *(_QWORD *)(v4 + 296);
      v16 = *(_QWORD *)(v15 + 16);
      if ( v16 )
        *(_DWORD *)(v16 + 372) = v13;
      else
        mmioSeek(*(HMMIO *)(v15 + 8), v13, 0);
      for ( ; v14 >= 4; v14 += -4 - 4 * v17 )
      {
        if ( (unsigned int)shfileRead(*(_QWORD *)(v4 + 296), byte_18001E6C0, 4) != 4 )
          break;
        v17 = 256;
        if ( byte_18001E6C1 )
          v17 = (unsigned __int8)byte_18001E6C1;
        if ( v17 > (unsigned int)v9[8]
          || v17 + (unsigned __int8)byte_18001E6C0[0] > v9[8]
          || (unsigned int)shfileRead(*(_QWORD *)(v4 + 296), &dword_18001E6C4, (unsigned int)(4 * v17)) != 4 * v17 )
        {
          break;
        }
        v18 = 0;
        if ( v17 )
        {
          do
          {
            *(_BYTE *)(v4 + 4LL * (int)(v18 + (unsigned __int8)byte_18001E6C0[0]) + 310) = byte_18001E6C0[4 * v18 + 4];
            *(_BYTE *)(v4 + 4LL * (int)(v18 + (unsigned __int8)byte_18001E6C0[0]) + 309) = byte_18001E6C0[4 * v18 + 5];
            *(_BYTE *)(v4 + 4LL * (int)(v18 + (unsigned __int8)byte_18001E6C0[0]) + 308) = byte_18001E6C0[4 * v18 + 6];
            v19 = v18 + (unsigned __int8)byte_18001E6C0[0];
            v18 = (unsigned int)(v18 + 1);
            *(_BYTE *)(v4 + 4LL * v19 + 311) = 0;
          }
          while ( (int)v18 < v17 );
        }
      }
    }
    v10 = v21;
  }
  if ( v8 )
    LeaveCriticalSection(v8);
}

```

## disassembly

```asm
0x18000b368  push    rbx
0x18000b36a  push    rbp
0x18000b36b  push    rsi
0x18000b36c  push    rdi
0x18000b36d  push    r12
0x18000b36f  push    r13
0x18000b371  push    r14
0x18000b373  push    r15
0x18000b375  sub     rsp, 28h
0x18000b379  mov     rsi, [rcx+8]
0x18000b37d  mov     r14, r9
0x18000b380  mov     edi, r8d
0x18000b383  mov     r13d, edx
0x18000b386  mov     rbx, [rsi+110h]
0x18000b38d  add     rbx, 4F0h
0x18000b394  mov     rcx, rbx; lpCriticalSection
0x18000b397  call    cs:__imp_EnterCriticalSection
0x18000b39d  mov     r15, [rsi+538h]
0x18000b3a4  xor     ebp, ebp
0x18000b3a6  cmp     edi, r13d
0x18000b3a9  cmovle  ebp, edi
0x18000b3ac  test    ebp, ebp
0x18000b3ae  jg      short loc_18000B3D4
0x18000b3b0  movsxd  rdx, dword ptr [r15]
0x18000b3b3  mov     r8d, 100h
0x18000b3b9  cmp     [r15+20h], r8d
0x18000b3bd  mov     rcx, r14; void *
0x18000b3c0  cmovb   r8d, [r15+20h]
0x18000b3c5  add     rdx, r15; Src
0x18000b3c8  shl     r8, 2; Size
0x18000b3cc  call    memmove_0
0x18000b3d1  or      ebp, 0FFFFFFFFh
0x18000b3d4  lea     edx, [rbp+1]
0x18000b3d7  jmp     loc_18000B571
0x18000b3dc  cmp     edi, r13d
0x18000b3df  jg      loc_18000B58D
0x18000b3e5  cmp     edi, ebp
0x18000b3e7  jz      loc_18000B58D
0x18000b3ed  cmp     edi, [rsi+5Ch]
0x18000b3f0  jle     loc_18000B56C
0x18000b3f6  mov     rcx, [rsi+578h]
0x18000b3fd  mov     r8d, 2040h
0x18000b403  mov     edx, edi
0x18000b405  call    StreamFindSample
0x18000b40a  mov     rcx, [rsi+578h]
0x18000b411  mov     r8d, 1040h
0x18000b417  mov     edx, edi
0x18000b419  mov     ebp, eax
0x18000b41b  call    StreamFindSample
0x18000b420  mov     ecx, [r15+20h]
0x18000b424  mov     r14d, eax
0x18000b427  lea     ecx, ds:4[rcx*8]
0x18000b42e  cmp     eax, ecx
0x18000b430  jg      loc_18000B58D
0x18000b436  mov     r9, [rsi+128h]
0x18000b43d  mov     rcx, [r9+10h]
0x18000b441  test    rcx, rcx
0x18000b444  jz      short loc_18000B44E
0x18000b446  mov     [rcx+174h], ebp
0x18000b44c  jmp     short loc_18000B45D
0x18000b44e  mov     rcx, [r9+8]; hmmio
0x18000b452  xor     r8d, r8d; iOrigin
0x18000b455  mov     edx, ebp; lOffset
0x18000b457  call    cs:__imp_mmioSeek
0x18000b45d  cmp     r14d, 4
0x18000b461  jl      loc_18000B56C
0x18000b467  lea     r9, byte_18001E6C0
0x18000b46e  mov     rcx, [rsi+128h]
0x18000b475  mov     r8d, 4
0x18000b47b  mov     rdx, r9
0x18000b47e  call    shfileRead
0x18000b483  cmp     eax, 4
0x18000b486  jnz     loc_18000B56C
0x18000b48c  movzx   eax, cs:byte_18001E6C1
0x18000b493  mov     ebp, 100h
0x18000b498  test    al, al
0x18000b49a  jz      short loc_18000B49E
0x18000b49c  mov     ebp, eax
0x18000b49e  cmp     ebp, [r15+20h]
0x18000b4a2  ja      loc_18000B56C
0x18000b4a8  movzx   eax, cs:byte_18001E6C0
0x18000b4af  add     eax, ebp
0x18000b4b1  cmp     eax, [r15+20h]
0x18000b4b5  jg      loc_18000B56C
0x18000b4bb  mov     rcx, [rsi+128h]
0x18000b4c2  lea     r12d, ds:0[rbp*4]
0x18000b4ca  mov     r8d, r12d
0x18000b4cd  lea     rdx, dword_18001E6C4
0x18000b4d4  call    shfileRead
0x18000b4d9  cmp     eax, r12d
0x18000b4dc  jnz     loc_18000B56C
0x18000b4e2  xor     r8d, r8d
0x18000b4e5  lea     r9, byte_18001E6C0
0x18000b4ec  test    ebp, ebp
0x18000b4ee  jz      short loc_18000B557
0x18000b4f0  movzx   eax, cs:byte_18001E6C0
0x18000b4f7  add     eax, r8d
0x18000b4fa  movsxd  rcx, eax
0x18000b4fd  mov     al, [r9+r8*4+4]
0x18000b502  mov     [rsi+rcx*4+136h], al
0x18000b509  movzx   eax, cs:byte_18001E6C0
0x18000b510  add     eax, r8d
0x18000b513  movsxd  rcx, eax
0x18000b516  mov     al, [r9+r8*4+5]
0x18000b51b  mov     [rsi+rcx*4+135h], al
0x18000b522  movzx   eax, cs:byte_18001E6C0
0x18000b529  add     eax, r8d
0x18000b52c  movsxd  rcx, eax
0x18000b52f  mov     al, [r9+r8*4+6]
0x18000b534  mov     [rsi+rcx*4+134h], al
0x18000b53b  movzx   eax, cs:byte_18001E6C0
0x18000b542  add     eax, r8d
0x18000b545  inc     r8d
0x18000b548  cdqe
0x18000b54a  mov     byte ptr [rsi+rax*4+137h], 0
0x18000b552  cmp     r8d, ebp
0x18000b555  jl      short loc_18000B4F0
0x18000b557  mov     eax, 0FFFFFFFCh
0x18000b55c  sub     eax, r12d
0x18000b55f  add     r14d, eax
0x18000b562  cmp     r14d, 4
0x18000b566  jge     loc_18000B46E
0x18000b56c  mov     ebp, edi
0x18000b56e  lea     edx, [rdi+1]
0x18000b571  mov     rcx, [rsi+578h]
0x18000b578  mov     r8d, 41h ; 'A'
0x18000b57e  call    StreamFindSample
0x18000b583  mov     edi, eax
0x18000b585  test    eax, eax
0x18000b587  jns     loc_18000B3DC
0x18000b58d  test    rbx, rbx
0x18000b590  jz      short loc_18000B59B
0x18000b592  mov     rcx, rbx; lpCriticalSection
0x18000b595  call    cs:__imp_LeaveCriticalSection
0x18000b59b  add     rsp, 28h
0x18000b59f  pop     r15
0x18000b5a1  pop     r14
0x18000b5a3  pop     r13
0x18000b5a5  pop     r12
0x18000b5a7  pop     rdi
0x18000b5a8  pop     rsi
0x18000b5a9  pop     rbp
0x18000b5aa  pop     rbx
0x18000b5ab  retn
```
