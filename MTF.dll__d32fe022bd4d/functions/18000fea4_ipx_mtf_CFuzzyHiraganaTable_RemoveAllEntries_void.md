# ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries(void)

- ea: `0x18000fea4`
- end: `0x18000ff2c`
- name: `?RemoveAllEntries@CFuzzyHiraganaTable@mtf@ipx@@QEAAXXZ`
- size: `136`
- prototype: `void __fastcall(ipx::mtf::CFuzzyHiraganaTable *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e690`
- `0x18000ecc8`
- `0x18000f570`

## callees

- `0x18000fea4`

## import_xrefs

- `msvcrt!free` at `0x18000ff0c`
- `msvcrt!free` at `0x18000ff0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fed7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fed7`

## pseudocode

```c
void __fastcall ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries(ipx::mtf::CFuzzyHiraganaTable *this)
{
  __int64 v1; // rsi
  void **i; // rdi
  __int64 v4; // r14
  __int64 j; // rbp
  OLECHAR *v6; // rcx
  void *v7; // rcx

  v1 = 0;
  for ( i = (void **)((char *)this + 24); (unsigned int)v1 < *((_DWORD *)this + 2); v1 = (unsigned int)(v1 + 1) )
  {
    v4 = 6 * v1;
    for ( j = 0; j != 5; ++j )
    {
      v6 = (OLECHAR *)*((_QWORD *)*i + v4 + j + 1);
      if ( v6 )
      {
        SysFreeString(v6);
        *((_QWORD *)*i + v4 + j + 1) = 0;
      }
    }
  }
  v7 = *i;
  *((_DWORD *)this + 9) = 0;
  if ( v7 )
  {
    free(v7);
    *i = 0;
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000fea4  push    rbx
0x18000fea6  push    rbp
0x18000fea7  push    rsi
0x18000fea8  push    rdi
0x18000fea9  push    r14
0x18000feab  sub     rsp, 20h
0x18000feaf  xor     esi, esi
0x18000feb1  lea     rdi, [rcx+18h]
0x18000feb5  mov     rbx, rcx
0x18000feb8  cmp     [rcx+8], esi
0x18000febb  jbe     short loc_18000FEFD
0x18000febd  lea     r14, [rsi+rsi*2]
0x18000fec1  add     r14, r14
0x18000fec4  xor     ebp, ebp
0x18000fec6  mov     rax, [rdi]
0x18000fec9  lea     rcx, [r14+rbp]
0x18000fecd  mov     rcx, [rax+rcx*8+8]; bstrString
0x18000fed2  test    rcx, rcx
0x18000fed5  jz      short loc_18000FEED
0x18000fed7  call    cs:__imp_SysFreeString
0x18000fedd  mov     rax, [rdi]
0x18000fee0  lea     rcx, [r14+rbp]
0x18000fee4  mov     qword ptr [rax+rcx*8+8], 0
0x18000feed  inc     rbp
0x18000fef0  cmp     rbp, 5
0x18000fef4  jnz     short loc_18000FEC6
0x18000fef6  inc     esi
0x18000fef8  cmp     esi, [rbx+8]
0x18000fefb  jb      short loc_18000FEBD
0x18000fefd  mov     rcx, [rdi]; Block
0x18000ff00  mov     dword ptr [rbx+24h], 0
0x18000ff07  test    rcx, rcx
0x18000ff0a  jz      short loc_18000FF19
0x18000ff0c  call    cs:__imp_free
0x18000ff12  mov     qword ptr [rdi], 0
0x18000ff19  mov     qword ptr [rbx+8], 0
0x18000ff21  add     rsp, 20h
0x18000ff25  pop     r14
0x18000ff27  pop     rdi
0x18000ff28  pop     rsi
0x18000ff29  pop     rbp
0x18000ff2a  pop     rbx
0x18000ff2b  retn
```
