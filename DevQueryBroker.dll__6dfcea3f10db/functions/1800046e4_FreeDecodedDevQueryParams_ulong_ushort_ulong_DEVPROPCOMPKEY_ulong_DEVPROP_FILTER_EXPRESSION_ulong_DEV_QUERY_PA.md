# FreeDecodedDevQueryParams(ulong,ushort * *,ulong,_DEVPROPCOMPKEY *,ulong,_DEVPROP_FILTER_EXPRESSION *,ulong,_DEV_QUERY_PARAMETER *,ushort *)

- ea: `0x1800046e4`
- end: `0x180004809`
- name: `?FreeDecodedDevQueryParams@@YAXKPEAPEAGKPEAU_DEVPROPCOMPKEY@@KPEAU_DEVPROP_FILTER_EXPRESSION@@KPEAU_DEV_QUERY_PARAMETER@@PEAG@Z`
- size: `293`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **, unsigned int, struct _DEVPROPCOMPKEY *, unsigned int, struct _DEVPROP_FILTER_EXPRESSION *Block, unsigned int, struct _DEV_QUERY_PARAMETER *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x1800046e4`

## import_xrefs

- `msvcrt!_aligned_free` at `0x180004723`
- `msvcrt!_aligned_free` at `0x180004733`
- `msvcrt!_aligned_free` at `0x180004755`
- `msvcrt!_aligned_free` at `0x180004765`
- `msvcrt!_aligned_free` at `0x180004788`
- `msvcrt!_aligned_free` at `0x180004798`
- `msvcrt!_aligned_free` at `0x1800047ac`
- `msvcrt!_aligned_free` at `0x1800047cd`
- `msvcrt!_aligned_free` at `0x1800047e1`
- `msvcrt!_aligned_free` at `0x1800047f4`
- `msvcrt!_aligned_free` at `0x180004723`
- `msvcrt!_aligned_free` at `0x180004733`
- `msvcrt!_aligned_free` at `0x180004755`
- `msvcrt!_aligned_free` at `0x180004765`
- `msvcrt!_aligned_free` at `0x180004788`
- `msvcrt!_aligned_free` at `0x180004798`
- `msvcrt!_aligned_free` at `0x1800047ac`
- `msvcrt!_aligned_free` at `0x1800047cd`
- `msvcrt!_aligned_free` at `0x1800047e1`
- `msvcrt!_aligned_free` at `0x1800047f4`

## pseudocode

```c
void __fastcall FreeDecodedDevQueryParams(
        unsigned int a1,
        unsigned __int16 **a2,
        unsigned int a3,
        struct _DEVPROPCOMPKEY *a4,
        unsigned int a5,
        struct _DEVPROP_FILTER_EXPRESSION *Block,
        unsigned int a7,
        struct _DEV_QUERY_PARAMETER *a8,
        unsigned __int16 *a9)
{
  __int64 i; // rbx
  unsigned __int16 *v14; // rcx
  unsigned int j; // ebx
  WCHAR *LocaleName; // rcx
  unsigned int k; // ebx
  __int64 v18; // rsi
  PVOID Buffer; // rcx
  WCHAR *v20; // rcx
  __int64 m; // rbx
  void *v22; // rcx

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      v14 = a2[i];
      if ( v14 )
        _aligned_free(v14);
    }
    _aligned_free(a2);
  }
  if ( a4 )
  {
    for ( j = 0; j < a3; ++j )
    {
      LocaleName = (WCHAR *)a4[j].LocaleName;
      if ( LocaleName )
        _aligned_free(LocaleName);
    }
    _aligned_free(a4);
  }
  for ( k = 0; k < a5; ++k )
  {
    v18 = k;
    Buffer = Block[v18].Property.Buffer;
    if ( Buffer )
      _aligned_free(Buffer);
    v20 = (WCHAR *)Block[v18].Property.CompKey.LocaleName;
    if ( v20 )
      _aligned_free(v20);
  }
  if ( Block )
    _aligned_free(Block);
  for ( m = 0; (unsigned int)m < a7; m = (unsigned int)(m + 1) )
  {
    v22 = (void *)*((_QWORD *)a8 + 5 * m + 4);
    if ( v22 )
      _aligned_free(v22);
  }
  if ( a8 )
    _aligned_free(a8);
  if ( a9 )
    _aligned_free(a9);
}

```

## disassembly

```asm
0x1800046e4  push    rbx
0x1800046e6  push    rbp
0x1800046e7  push    rsi
0x1800046e8  push    rdi
0x1800046e9  push    r12
0x1800046eb  push    r14
0x1800046ed  push    r15
0x1800046ef  sub     rsp, 20h
0x1800046f3  mov     rbp, [rsp+58h+Block]
0x1800046fb  mov     rdi, r9
0x1800046fe  mov     r15, [rsp+58h+arg_38]
0x180004706  mov     r12d, r8d
0x180004709  mov     rsi, rdx
0x18000470c  mov     r14d, ecx
0x18000470f  test    rdx, rdx
0x180004712  jz      short loc_180004739
0x180004714  xor     ebx, ebx
0x180004716  test    ecx, ecx
0x180004718  jz      short loc_180004730
0x18000471a  mov     rcx, [rsi+rbx*8]; Block
0x18000471e  test    rcx, rcx
0x180004721  jz      short loc_180004729
0x180004723  call    cs:__imp__aligned_free
0x180004729  inc     ebx
0x18000472b  cmp     ebx, r14d
0x18000472e  jb      short loc_18000471A
0x180004730  mov     rcx, rsi; Block
0x180004733  call    cs:__imp__aligned_free
0x180004739  test    rdi, rdi
0x18000473c  jz      short loc_18000476B
0x18000473e  xor     ebx, ebx
0x180004740  test    r12d, r12d
0x180004743  jz      short loc_180004762
0x180004745  mov     eax, ebx
0x180004747  shl     rax, 5
0x18000474b  mov     rcx, [rax+rdi+18h]; Block
0x180004750  test    rcx, rcx
0x180004753  jz      short loc_18000475B
0x180004755  call    cs:__imp__aligned_free
0x18000475b  inc     ebx
0x18000475d  cmp     ebx, r12d
0x180004760  jb      short loc_180004745
0x180004762  mov     rcx, rdi; Block
0x180004765  call    cs:__imp__aligned_free
0x18000476b  mov     edi, [rsp+58h+arg_20]
0x180004772  xor     ebx, ebx
0x180004774  test    edi, edi
0x180004776  jz      short loc_1800047A4
0x180004778  mov     eax, ebx
0x18000477a  imul    rsi, rax, 38h ; '8'
0x18000477e  mov     rcx, [rsi+rbp+30h]; Block
0x180004783  test    rcx, rcx
0x180004786  jz      short loc_18000478E
0x180004788  call    cs:__imp__aligned_free
0x18000478e  mov     rcx, [rsi+rbp+20h]; Block
0x180004793  test    rcx, rcx
0x180004796  jz      short loc_18000479E
0x180004798  call    cs:__imp__aligned_free
0x18000479e  inc     ebx
0x1800047a0  cmp     ebx, edi
0x1800047a2  jb      short loc_180004778
0x1800047a4  test    rbp, rbp
0x1800047a7  jz      short loc_1800047B2
0x1800047a9  mov     rcx, rbp; Block
0x1800047ac  call    cs:__imp__aligned_free
0x1800047b2  mov     edi, [rsp+58h+arg_30]
0x1800047b9  xor     ebx, ebx
0x1800047bb  test    edi, edi
0x1800047bd  jz      short loc_1800047D9
0x1800047bf  lea     rcx, [rbx+rbx*4]
0x1800047c3  mov     rcx, [r15+rcx*8+20h]; Block
0x1800047c8  test    rcx, rcx
0x1800047cb  jz      short loc_1800047D3
0x1800047cd  call    cs:__imp__aligned_free
0x1800047d3  inc     ebx
0x1800047d5  cmp     ebx, edi
0x1800047d7  jb      short loc_1800047BF
0x1800047d9  test    r15, r15
0x1800047dc  jz      short loc_1800047E7
0x1800047de  mov     rcx, r15; Block
0x1800047e1  call    cs:__imp__aligned_free
0x1800047e7  mov     rcx, [rsp+58h+arg_40]; Block
0x1800047ef  test    rcx, rcx
0x1800047f2  jz      short loc_1800047FA
0x1800047f4  call    cs:__imp__aligned_free
0x1800047fa  add     rsp, 20h
0x1800047fe  pop     r15
0x180004800  pop     r14
0x180004802  pop     r12
0x180004804  pop     rdi
0x180004805  pop     rsi
0x180004806  pop     rbp
0x180004807  pop     rbx
0x180004808  retn
```
