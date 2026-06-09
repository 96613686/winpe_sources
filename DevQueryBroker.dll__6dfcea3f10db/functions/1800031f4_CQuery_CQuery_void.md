# CQuery::~CQuery(void)

- ea: `0x1800031f4`
- end: `0x180003326`
- name: `??1CQuery@@QEAA@XZ`
- size: `306`
- prototype: `void __fastcall(CQuery *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000314c`
- `0x18000383c`

## callees

- `0x1800031f4`
- `0x180003da4`

## import_xrefs

- `msvcrt!free` at `0x180003233`
- `msvcrt!free` at `0x180003244`
- `msvcrt!free` at `0x18000326c`
- `msvcrt!free` at `0x18000327d`
- `msvcrt!free` at `0x1800032a5`
- `msvcrt!free` at `0x1800032b9`
- `msvcrt!free` at `0x1800032ca`
- `msvcrt!free` at `0x1800032f0`
- `msvcrt!free` at `0x180003301`
- `msvcrt!free` at `0x180003310`
- `msvcrt!free` at `0x180003233`
- `msvcrt!free` at `0x180003244`
- `msvcrt!free` at `0x18000326c`
- `msvcrt!free` at `0x18000327d`
- `msvcrt!free` at `0x1800032a5`
- `msvcrt!free` at `0x1800032b9`
- `msvcrt!free` at `0x1800032ca`
- `msvcrt!free` at `0x1800032f0`
- `msvcrt!free` at `0x180003301`
- `msvcrt!free` at `0x180003310`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003212`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003212`

## pseudocode

```c
void __fastcall CQuery::~CQuery(CQuery *this)
{
  __int64 i; // rdi
  void *v3; // rcx
  unsigned int j; // edi
  void *v5; // rcx
  unsigned int k; // edi
  __int64 v7; // rsi
  void *v8; // rcx
  void *v9; // rcx
  __int64 m; // rdi
  void *v11; // rcx
  void *v12; // rcx

  CQuery::Stop((struct _RTL_CRITICAL_SECTION *)this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  if ( *((_QWORD *)this + 5) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 8); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)this + 5) + 8 * i);
      if ( v3 )
        free(v3);
    }
    free(*((void **)this + 5));
  }
  if ( *((_QWORD *)this + 10) )
  {
    for ( j = 0; j < *((_DWORD *)this + 19); ++j )
    {
      v5 = *(void **)(32LL * j + *((_QWORD *)this + 10) + 24);
      if ( v5 )
        free(v5);
    }
    free(*((void **)this + 10));
  }
  if ( *((_QWORD *)this + 12) )
  {
    for ( k = 0; k < *((_DWORD *)this + 22); ++k )
    {
      v7 = 56LL * k;
      v8 = *(void **)(*((_QWORD *)this + 12) + v7 + 48);
      if ( v8 )
        free(v8);
      v9 = *(void **)(v7 + *((_QWORD *)this + 12) + 32);
      if ( v9 )
        free(v9);
    }
    free(*((void **)this + 12));
  }
  if ( *((_QWORD *)this + 14) )
  {
    for ( m = 0; (unsigned int)m < *((_DWORD *)this + 26); m = (unsigned int)(m + 1) )
    {
      v11 = *(void **)(*((_QWORD *)this + 14) + 40 * m + 32);
      if ( v11 )
        free(v11);
    }
    free(*((void **)this + 14));
  }
  v12 = (void *)*((_QWORD *)this + 3);
  if ( v12 )
    free(v12);
}

```

## disassembly

```asm
0x1800031f4  mov     [rsp+arg_0], rbx
0x1800031f9  mov     [rsp+arg_8], rsi
0x1800031fe  push    rdi
0x1800031ff  sub     rsp, 20h
0x180003203  mov     rbx, rcx
0x180003206  call    ?Stop@CQuery@@QEAAXXZ; CQuery::Stop(void)
0x18000320b  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180003212  call    cs:__imp_DeleteCriticalSection
0x180003218  cmp     qword ptr [rbx+28h], 0
0x18000321d  jz      short loc_18000324A
0x18000321f  xor     edi, edi
0x180003221  cmp     [rbx+20h], edi
0x180003224  jbe     short loc_180003240
0x180003226  mov     rax, [rbx+28h]
0x18000322a  mov     rcx, [rax+rdi*8]; Block
0x18000322e  test    rcx, rcx
0x180003231  jz      short loc_180003239
0x180003233  call    cs:__imp_free
0x180003239  inc     edi
0x18000323b  cmp     edi, [rbx+20h]
0x18000323e  jb      short loc_180003226
0x180003240  mov     rcx, [rbx+28h]; Block
0x180003244  call    cs:__imp_free
0x18000324a  cmp     qword ptr [rbx+50h], 0
0x18000324f  jz      short loc_180003283
0x180003251  xor     edi, edi
0x180003253  cmp     [rbx+4Ch], edi
0x180003256  jbe     short loc_180003279
0x180003258  mov     rax, [rbx+50h]
0x18000325c  mov     ecx, edi
0x18000325e  shl     rcx, 5
0x180003262  mov     rcx, [rcx+rax+18h]; Block
0x180003267  test    rcx, rcx
0x18000326a  jz      short loc_180003272
0x18000326c  call    cs:__imp_free
0x180003272  inc     edi
0x180003274  cmp     edi, [rbx+4Ch]
0x180003277  jb      short loc_180003258
0x180003279  mov     rcx, [rbx+50h]; Block
0x18000327d  call    cs:__imp_free
0x180003283  cmp     qword ptr [rbx+60h], 0
0x180003288  jz      short loc_1800032D0
0x18000328a  xor     edi, edi
0x18000328c  cmp     [rbx+58h], edi
0x18000328f  jbe     short loc_1800032C6
0x180003291  mov     eax, edi
0x180003293  imul    rsi, rax, 38h ; '8'
0x180003297  mov     rax, [rbx+60h]
0x18000329b  mov     rcx, [rax+rsi+30h]; Block
0x1800032a0  test    rcx, rcx
0x1800032a3  jz      short loc_1800032AB
0x1800032a5  call    cs:__imp_free
0x1800032ab  mov     rax, [rbx+60h]
0x1800032af  mov     rcx, [rsi+rax+20h]; Block
0x1800032b4  test    rcx, rcx
0x1800032b7  jz      short loc_1800032BF
0x1800032b9  call    cs:__imp_free
0x1800032bf  inc     edi
0x1800032c1  cmp     edi, [rbx+58h]
0x1800032c4  jb      short loc_180003291
0x1800032c6  mov     rcx, [rbx+60h]; Block
0x1800032ca  call    cs:__imp_free
0x1800032d0  cmp     qword ptr [rbx+70h], 0
0x1800032d5  jz      short loc_180003307
0x1800032d7  xor     edi, edi
0x1800032d9  cmp     [rbx+68h], edi
0x1800032dc  jbe     short loc_1800032FD
0x1800032de  mov     rax, [rbx+70h]
0x1800032e2  lea     rcx, [rdi+rdi*4]
0x1800032e6  mov     rcx, [rax+rcx*8+20h]; Block
0x1800032eb  test    rcx, rcx
0x1800032ee  jz      short loc_1800032F6
0x1800032f0  call    cs:__imp_free
0x1800032f6  inc     edi
0x1800032f8  cmp     edi, [rbx+68h]
0x1800032fb  jb      short loc_1800032DE
0x1800032fd  mov     rcx, [rbx+70h]; Block
0x180003301  call    cs:__imp_free
0x180003307  mov     rcx, [rbx+18h]; Block
0x18000330b  test    rcx, rcx
0x18000330e  jz      short loc_180003316
0x180003310  call    cs:__imp_free
0x180003316  mov     rbx, [rsp+28h+arg_0]
0x18000331b  mov     rsi, [rsp+28h+arg_8]
0x180003320  add     rsp, 20h
0x180003324  pop     rdi
0x180003325  retn
```
