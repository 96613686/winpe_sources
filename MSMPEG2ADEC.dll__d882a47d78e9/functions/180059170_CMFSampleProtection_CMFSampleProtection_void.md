# CMFSampleProtection::~CMFSampleProtection(void)

- ea: `0x180059170`
- end: `0x1800592bb`
- name: `??1CMFSampleProtection@@QEAA@XZ`
- size: `331`
- prototype: `void __fastcall(CMFSampleProtection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d760`

## callees

- `0x180059170`
- `0x1800592d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005928d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005928d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800592af`

## pseudocode

```c
void __fastcall CMFSampleProtection::~CMFSampleProtection(CMFSampleProtection *this)
{
  unsigned int i; // ebx
  char *v3; // r8
  char *v4; // r9
  unsigned __int8 j; // dl
  char *v6; // r8
  char *v7; // r9
  unsigned __int8 k; // dl
  char *v9; // r8
  char *v10; // r9
  unsigned __int8 m; // dl
  int v12; // [rsp+30h] [rbp+8h]

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
  v3 = (char *)this + 36;
  v12 = -1749680893;
  if ( this != (CMFSampleProtection *)-36LL )
  {
    v4 = (char *)this + 56;
    if ( (char *)this + 56 >= (char *)this + 36 )
    {
      for ( j = 0; v3 < v4; ++v3 )
      {
        *v3 = *((_BYTE *)&v12 + j);
        j = (j + 1) & 3;
      }
    }
  }
  v6 = (char *)this + 64;
  v12 = -1749680893;
  if ( this != (CMFSampleProtection *)-64LL )
  {
    v7 = (char *)this + 336;
    if ( (char *)this + 336 >= (char *)this + 64 )
    {
      for ( k = 0; v6 < v7; ++v6 )
      {
        *v6 = *((_BYTE *)&v12 + k);
        k = (k + 1) & 3;
      }
    }
  }
  v9 = (char *)this + 372;
  v12 = -1749680893;
  if ( this != (CMFSampleProtection *)-372LL )
  {
    v10 = (char *)this + 388;
    if ( (char *)this + 388 >= (char *)this + 372 )
    {
      for ( m = 0; v9 < v10; ++v9 )
      {
        *v9 = *((_BYTE *)&v12 + m);
        m = (m + 1) & 3;
      }
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
0x180059170  mov     [rsp+arg_8], rbx
0x180059175  mov     [rsp+arg_10], rsi
0x18005917a  push    rdi
0x18005917b  sub     rsp, 20h
0x18005917f  mov     rdi, rcx
0x180059182  lea     rax, ??_7CMFSampleProtection@@6B@; const CMFSampleProtection::`vftable'
0x180059189  mov     [rcx], rax
0x18005918c  xor     esi, esi
0x18005918e  cmp     dword ptr [rcx+184h], 3
0x180059195  jnz     short loc_1800591B5
0x180059197  mov     ebx, esi
0x180059199  nop     dword ptr [rax+00000000h]
0x1800591a0  mov     edx, ebx; unsigned int
0x1800591a2  mov     rcx, rdi; this
0x1800591a5  call    ?Clean@CMFSampleProtection@@QEAAJK@Z; CMFSampleProtection::Clean(ulong)
0x1800591aa  test    eax, eax
0x1800591ac  js      short loc_1800591B5
0x1800591ae  inc     ebx
0x1800591b0  cmp     ebx, 10h
0x1800591b3  jb      short loc_1800591A0
0x1800591b5  mov     [rdi+264h], esi
0x1800591bb  lea     r8, [rdi+24h]
0x1800591bf  mov     [rsp+28h+arg_0], 97B5FD03h
0x1800591c7  test    r8, r8
0x1800591ca  jz      short loc_1800591F8
0x1800591cc  lea     r9, [r8+14h]
0x1800591d0  cmp     r9, r8
0x1800591d3  jb      short loc_1800591F8
0x1800591d5  xor     dl, dl
0x1800591d7  cmp     r8, r9
0x1800591da  jnb     short loc_1800591F8
0x1800591dc  nop     dword ptr [rax+00h]
0x1800591e0  movzx   eax, dl
0x1800591e3  movzx   ecx, byte ptr [rsp+rax+28h+arg_0]
0x1800591e8  mov     [r8], cl
0x1800591eb  inc     dl
0x1800591ed  and     dl, 3
0x1800591f0  inc     r8
0x1800591f3  cmp     r8, r9
0x1800591f6  jb      short loc_1800591E0
0x1800591f8  lea     r8, [rdi+40h]
0x1800591fc  mov     [rsp+28h+arg_0], 97B5FD03h
0x180059204  test    r8, r8
0x180059207  jz      short loc_180059238
0x180059209  lea     r9, [r8+110h]
0x180059210  cmp     r9, r8
0x180059213  jb      short loc_180059238
0x180059215  xor     dl, dl
0x180059217  cmp     r8, r9
0x18005921a  jnb     short loc_180059238
0x18005921c  nop     dword ptr [rax+00h]
0x180059220  movzx   eax, dl
0x180059223  movzx   ecx, byte ptr [rsp+rax+28h+arg_0]
0x180059228  mov     [r8], cl
0x18005922b  inc     dl
0x18005922d  and     dl, 3
0x180059230  inc     r8
0x180059233  cmp     r8, r9
0x180059236  jb      short loc_180059220
0x180059238  lea     r8, [rdi+174h]
0x18005923f  mov     [rsp+28h+arg_0], 97B5FD03h
0x180059247  test    r8, r8
0x18005924a  jz      short loc_180059278
0x18005924c  lea     r9, [r8+10h]
0x180059250  cmp     r9, r8
0x180059253  jb      short loc_180059278
0x180059255  xor     dl, dl
0x180059257  cmp     r8, r9
0x18005925a  jnb     short loc_180059278
0x18005925c  nop     dword ptr [rax+00h]
0x180059260  movzx   eax, dl
0x180059263  movzx   ecx, byte ptr [rsp+rax+28h+arg_0]
0x180059268  mov     [r8], cl
0x18005926b  inc     dl
0x18005926d  and     dl, 3
0x180059270  inc     r8
0x180059273  cmp     r8, r9
0x180059276  jb      short loc_180059260
0x180059278  mov     [rdi+184h], rsi
0x18005927f  mov     [rdi+258h], rsi
0x180059286  lea     rcx, [rdi+2C0h]; lpCriticalSection
0x18005928d  call    cs:__imp_DeleteCriticalSection
0x180059294  nop     dword ptr [rax+rax+00h]
0x180059299  lea     rcx, [rdi+268h]
0x1800592a0  mov     rbx, [rsp+28h+arg_8]
0x1800592a5  mov     rsi, [rsp+28h+arg_10]
0x1800592aa  add     rsp, 20h
0x1800592ae  pop     rdi
0x1800592af  jmp     cs:__imp_DeleteCriticalSection
```
