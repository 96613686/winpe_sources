# CFileStream::EnsureBuffersValid(void)

- ea: `0x180016510`
- end: `0x1800166e5`
- name: `?EnsureBuffersValid@CFileStream@@AEAAHXZ`
- size: `469`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800091d0`
- `0x180009750`
- `0x180016738`

## callees

- `0x180001048`
- `0x180001054`
- `0x180016510`
- `0x1800166ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016642`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016642`

## pseudocode

```c
__int64 __fastcall CFileStream::EnsureBuffersValid(CFileStream *this)
{
  int v1; // eax
  unsigned int v3; // esi
  char *v4; // r9
  int v5; // edi
  __int64 v6; // r15
  unsigned int v7; // r8d
  __int64 v8; // r14
  char *v9; // rbp
  char *v10; // r13
  unsigned int v11; // eax
  void *v12; // rax
  HANDLE EventW; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // r9
  __int64 v16; // r8
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned int v21; // [rsp+60h] [rbp+8h]
  __int64 v22; // [rsp+68h] [rbp+10h]
  char *v23; // [rsp+70h] [rbp+18h]

  v1 = *((_DWORD *)this + 94);
  if ( !v1 )
    return 0;
  if ( v1 == 3 )
  {
    *((_DWORD *)this + 90) = 2;
    v3 = 0x40000;
  }
  else
  {
    v3 = 0x10000;
    if ( v1 == 2 )
      *((_DWORD *)this + 90) = 4;
    else
      *((_DWORD *)this + 90) = 1;
  }
  v4 = (char *)this + 8;
  v23 = (char *)this + 8;
  v5 = 0;
  v6 = v3;
  do
  {
    v7 = *(_DWORD *)this;
    v8 = 88LL * v5;
    v22 = *((_QWORD *)this + 48);
    v21 = *(_DWORD *)this;
    v9 = &v4[v8];
    v10 = &v4[v8 + 36];
    if ( *(_DWORD *)((char *)this + v8 + 8) != 2 )
    {
      if ( v7 == *(_DWORD *)v10
        && v3 == *(unsigned int *)v10
               + *((unsigned int *)v9 + 6)
               - 1LL
               - (*(unsigned int *)v10 + (unsigned __int64)*((unsigned int *)v9 + 6) - 1) % *(unsigned int *)v10 )
      {
        v6 = v3;
        goto LABEL_16;
      }
      CFileBuffer::FreeMemory((CFileBuffer *)&v4[v8]);
      v7 = v21;
      v6 = v3;
    }
    *(_DWORD *)v10 = v7;
    *((_DWORD *)v9 + 7) = 0;
    *((_QWORD *)v9 + 10) = v22;
    *(_DWORD *)((char *)this + v8 + 8) = 0;
    *((_DWORD *)v9 + 1) = 0;
    v11 = v3 + v7 - ((unsigned __int64)v7 + v6 - 1) % v7 - 1;
    *((_DWORD *)v9 + 6) = v11;
    v12 = operator new[](v11);
    *((_QWORD *)v9 + 2) = v12;
    if ( !v12 )
      return 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)((char *)this + v8 + 80) = EventW;
    if ( !EventW )
    {
      operator delete(*(void **)((char *)this + v8 + 24), v14);
      return 0;
    }
    v15 = *(unsigned int *)v10;
    v16 = *(_QWORD *)((char *)this + v8 + 24);
    v17 = v15 + v16 - (v16 + v15 - 1) % v15 - 1;
    v18 = *((unsigned int *)v9 + 6) - v17;
    *((_QWORD *)v9 + 1) = v17;
    v19 = (v18 + v16) % v15;
    v4 = (char *)this + 8;
    *((_DWORD *)v9 + 6) = v18 + v16 - v19;
LABEL_16:
    ++v5;
  }
  while ( v5 < *((_DWORD *)this + 90) );
  while ( v5 < 4 )
  {
    CFileBuffer::FreeMemory((CFileBuffer *)&v4[88 * v5]);
    v4 = v23;
    ++v5;
  }
  return 1;
}

```

## disassembly

```asm
0x180016510  mov     [rsp+arg_18], rbx
0x180016515  push    rbp
0x180016516  push    rsi
0x180016517  push    rdi
0x180016518  push    r12
0x18001651a  push    r13
0x18001651c  push    r14
0x18001651e  push    r15
0x180016520  sub     rsp, 20h
0x180016524  mov     eax, [rcx+178h]
0x18001652a  mov     rbx, rcx
0x18001652d  test    eax, eax
0x18001652f  jz      loc_1800166CE
0x180016535  cmp     eax, 3
0x180016538  jnz     short loc_18001654B
0x18001653a  mov     dword ptr [rcx+168h], 2
0x180016544  mov     esi, 40000h
0x180016549  jmp     short loc_18001656B
0x18001654b  mov     esi, 10000h
0x180016550  cmp     eax, 2
0x180016553  jnz     short loc_180016561
0x180016555  mov     dword ptr [rcx+168h], 4
0x18001655f  jmp     short loc_18001656B
0x180016561  mov     dword ptr [rcx+168h], 1
0x18001656b  lea     r9, [rcx+8]
0x18001656f  mov     r12d, esi
0x180016572  mov     [rsp+58h+arg_10], r9
0x180016577  xor     edi, edi
0x180016579  mov     r15d, esi
0x18001657c  mov     r8d, [rbx]
0x18001657f  movsxd  rax, edi
0x180016582  imul    r14, rax, 58h ; 'X'
0x180016586  mov     rax, [rbx+180h]
0x18001658d  mov     [rsp+58h+arg_8], rax
0x180016592  mov     [rsp+58h+arg_0], r8d
0x180016597  cmp     dword ptr [r14+rbx+8], 2
0x18001659d  lea     rbp, [r14+r9]
0x1800165a1  lea     r13, [rbp+24h]
0x1800165a5  jz      short loc_1800165E3
0x1800165a7  cmp     r8d, [r13+0]
0x1800165ab  jnz     short loc_1800165D3
0x1800165ad  mov     ecx, [r13+0]
0x1800165b1  xor     edx, edx
0x1800165b3  mov     r8d, [rbp+18h]
0x1800165b7  dec     r8
0x1800165ba  add     r8, rcx
0x1800165bd  mov     rax, r8
0x1800165c0  div     rcx
0x1800165c3  sub     r8, rdx
0x1800165c6  cmp     r12, r8
0x1800165c9  jnz     short loc_1800165D3
0x1800165cb  mov     r15, r12
0x1800165ce  jmp     loc_180016692
0x1800165d3  mov     rcx, rbp; this
0x1800165d6  call    ?FreeMemory@CFileBuffer@@QEAAXXZ; CFileBuffer::FreeMemory(void)
0x1800165db  mov     r8d, [rsp+58h+arg_0]
0x1800165e0  mov     r15, r12
0x1800165e3  mov     ecx, r8d
0x1800165e6  lea     rax, [r15-1]
0x1800165ea  add     rax, rcx
0x1800165ed  mov     [r13+0], r8d
0x1800165f1  xor     edx, edx
0x1800165f3  mov     dword ptr [rbp+1Ch], 0
0x1800165fa  div     rcx
0x1800165fd  mov     rcx, [rsp+58h+arg_8]
0x180016602  sub     r8d, edx
0x180016605  mov     [rbp+50h], rcx
0x180016609  mov     dword ptr [r14+rbx+8], 0
0x180016612  mov     dword ptr [rbp+4], 0
0x180016619  lea     eax, [r8-1]
0x18001661d  add     eax, esi
0x18001661f  mov     ecx, eax; unsigned __int64
0x180016621  mov     [rbp+18h], eax
0x180016624  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016629  mov     [rbp+10h], rax
0x18001662d  test    rax, rax
0x180016630  jz      loc_1800166CE
0x180016636  xor     r9d, r9d; lpName
0x180016639  xor     r8d, r8d; bInitialState
0x18001663c  xor     ecx, ecx; lpEventAttributes
0x18001663e  lea     edx, [r9+1]; bManualReset
0x180016642  call    cs:__imp_CreateEventW
0x180016648  mov     [r14+rbx+50h], rax
0x18001664d  test    rax, rax
0x180016650  jz      short loc_1800166C4
0x180016652  mov     r9d, [r13+0]
0x180016656  xor     edx, edx
0x180016658  mov     r8, [r14+rbx+18h]
0x18001665d  mov     rcx, r8
0x180016660  lea     rax, [r9-1]
0x180016664  add     rax, r8
0x180016667  div     r9
0x18001666a  mov     eax, [rbp+18h]
0x18001666d  sub     rcx, rdx
0x180016670  xor     edx, edx
0x180016672  dec     rcx
0x180016675  add     rcx, r9
0x180016678  sub     rax, rcx
0x18001667b  mov     [rbp+8], rcx
0x18001667f  lea     rcx, [rax+r8]
0x180016683  mov     rax, rcx
0x180016686  div     r9
0x180016689  lea     r9, [rbx+8]
0x18001668d  sub     ecx, edx
0x18001668f  mov     [rbp+18h], ecx
0x180016692  inc     edi
0x180016694  cmp     edi, [rbx+168h]
0x18001669a  jl      loc_18001657C
0x1800166a0  jmp     short loc_1800166B8
0x1800166a2  movsxd  rcx, edi
0x1800166a5  imul    rcx, 58h ; 'X'
0x1800166a9  add     rcx, r9; this
0x1800166ac  call    ?FreeMemory@CFileBuffer@@QEAAXXZ; CFileBuffer::FreeMemory(void)
0x1800166b1  mov     r9, [rsp+58h+arg_10]
0x1800166b6  inc     edi
0x1800166b8  cmp     edi, 4
0x1800166bb  jl      short loc_1800166A2
0x1800166bd  mov     eax, 1
0x1800166c2  jmp     short loc_1800166D0
0x1800166c4  mov     rcx, [r14+rbx+18h]; void *
0x1800166c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800166ce  xor     eax, eax
0x1800166d0  mov     rbx, [rsp+58h+arg_18]
0x1800166d5  add     rsp, 20h
0x1800166d9  pop     r15
0x1800166db  pop     r14
0x1800166dd  pop     r13
0x1800166df  pop     r12
0x1800166e1  pop     rdi
0x1800166e2  pop     rsi
0x1800166e3  pop     rbp
0x1800166e4  retn
```
