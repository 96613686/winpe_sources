# Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)

- ea: `0x180013ac8`
- end: `0x180013b7a`
- name: `??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015f20`
- `0x1800160b8`

## callees

- `0x180013ac8`

## import_xrefs

- `msvcrt!ldiv` at `0x180013b3b`
- `msvcrt!ldiv` at `0x180013b3b`
- `msvcrt!towlower` at `0x180013b15`
- `msvcrt!towlower` at `0x180013b15`

## pseudocode

```c
__int64 __fastcall Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(__int64 a1, unsigned __int64 a2)
{
  __int64 v2; // rcx
  wint_t *v3; // rbx
  __int64 v4; // rdi
  int v5; // ebp
  unsigned __int64 v6; // rsi
  wint_t v7; // ax
  ldiv_t v9; // [rsp+30h] [rbp+8h]

  v2 = -1;
  v3 = (wint_t *)a2;
  v4 = 0;
  do
    ++v2;
  while ( *(_WORD *)(a2 + 2 * v2) );
  v5 = -2128831035;
  v6 = (unsigned __int64)(2 * v2 + 1) >> 1;
  if ( a2 > a2 + 2 * v2 )
    v6 = 0;
  if ( v6 )
  {
    do
    {
      v7 = towlower(*v3++);
      v5 = v7 ^ (16777619 * v5);
      ++v4;
    }
    while ( v4 != v6 );
  }
  v9 = ldiv(v5, 127773);
  return 16807 * v9.rem - 2836 * v9.quot + (16807 * v9.rem - 2836 * v9.quot < 0 ? 0x7FFFFFFF : 0);
}

```

## disassembly

```asm
0x180013ac8  mov     rax, rsp
0x180013acb  mov     [rax+10h], rbx
0x180013acf  mov     [rax+18h], rbp
0x180013ad3  mov     [rax+20h], rsi
0x180013ad7  mov     [rax+8], rcx
0x180013adb  push    rdi
0x180013adc  sub     rsp, 20h
0x180013ae0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013ae4  mov     rbx, rdx
0x180013ae7  xor     edi, edi
0x180013ae9  inc     rcx
0x180013aec  cmp     [rdx+rcx*2], di
0x180013af0  jnz     short loc_180013AE9
0x180013af2  lea     rsi, ds:1[rcx*2]
0x180013afa  mov     ebp, 811C9DC5h
0x180013aff  shr     rsi, 1
0x180013b02  lea     rax, [rdx+rcx*2]
0x180013b06  cmp     rdx, rax
0x180013b09  cmova   rsi, rdi
0x180013b0d  test    rsi, rsi
0x180013b10  jz      short loc_180013B34
0x180013b12  movzx   ecx, word ptr [rbx]; C
0x180013b15  call    cs:__imp_towlower
0x180013b1b  imul    rbp, 1000193h
0x180013b22  movzx   ecx, ax
0x180013b25  lea     rbx, [rbx+2]
0x180013b29  xor     rbp, rcx
0x180013b2c  inc     rdi
0x180013b2f  cmp     rdi, rsi
0x180013b32  jnz     short loc_180013B12
0x180013b34  mov     edx, 1F31Dh; Denominator
0x180013b39  mov     ecx, ebp; Numerator
0x180013b3b  call    cs:__imp_ldiv
0x180013b41  mov     [rsp+28h+arg_0], rax
0x180013b46  shr     rax, 20h
0x180013b4a  imul    ecx, eax, 41A7h
0x180013b50  imul    eax, dword ptr [rsp+28h+arg_0], 0B14h
0x180013b58  sub     ecx, eax
0x180013b5a  jns     short loc_180013B62
0x180013b5c  add     ecx, 7FFFFFFFh
0x180013b62  mov     rbx, [rsp+28h+arg_8]
0x180013b67  mov     rbp, [rsp+28h+arg_10]
0x180013b6c  mov     rsi, [rsp+28h+arg_18]
0x180013b71  movsxd  rax, ecx
0x180013b74  add     rsp, 20h
0x180013b78  pop     rdi
0x180013b79  retn
```
