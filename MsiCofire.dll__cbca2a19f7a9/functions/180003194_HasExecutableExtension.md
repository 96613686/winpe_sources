# HasExecutableExtension

- ea: `0x180003194`
- end: `0x18000329f`
- name: `HasExecutableExtension`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800033f4`

## callees

- `0x180003194`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003200`
- `msvcrt!_wcsicmp` at `0x180003214`
- `msvcrt!_wcsicmp` at `0x180003228`
- `msvcrt!_wcsicmp` at `0x18000323c`
- `msvcrt!_wcsicmp` at `0x180003250`
- `msvcrt!_wcsicmp` at `0x180003264`
- `msvcrt!_wcsicmp` at `0x18000327a`
- `msvcrt!_wcsicmp` at `0x180003200`
- `msvcrt!_wcsicmp` at `0x180003214`
- `msvcrt!_wcsicmp` at `0x180003228`
- `msvcrt!_wcsicmp` at `0x18000323c`
- `msvcrt!_wcsicmp` at `0x180003250`
- `msvcrt!_wcsicmp` at `0x180003264`
- `msvcrt!_wcsicmp` at `0x18000327a`

## pseudocode

```c
__int64 __fastcall HasExecutableExtension(_WORD *a1)
{
  _WORD *v2; // rax
  __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  const wchar_t *v5; // rbx
  unsigned int v6; // edi

  if ( !a1 )
    return 0;
  v2 = a1;
  v3 = 260;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v4 = (260 - v3) & -(__int64)(v3 != 0);
  if ( !v3 || v4 < 4 )
    return 0;
  v5 = &a1[v4 - 4];
  if ( !_wcsicmp(v5, L".exe") )
    return 1;
  if ( !_wcsicmp(v5, L".dll") )
    return 1;
  if ( !_wcsicmp(v5, L".rll") )
    return 1;
  if ( !_wcsicmp(v5, L".sys") )
    return 1;
  if ( !_wcsicmp(v5, L".ocx") )
    return 1;
  if ( !_wcsicmp(v5, L".olb") )
    return 1;
  v6 = 0;
  if ( !_wcsicmp(v5, L".tlb") )
    return 1;
  return v6;
}

```

## disassembly

```asm
0x180003194  mov     [rsp+arg_0], rbx
0x180003199  mov     [rsp+arg_8], rsi
0x18000319e  push    rdi
0x18000319f  sub     rsp, 20h
0x1800031a3  xor     esi, esi
0x1800031a5  mov     r8, rcx
0x1800031a8  test    rcx, rcx
0x1800031ab  jz      loc_18000328D
0x1800031b1  mov     r9d, 104h
0x1800031b7  mov     rax, rcx
0x1800031ba  mov     edx, r9d
0x1800031bd  cmp     [rax], si
0x1800031c0  jz      short loc_1800031CC
0x1800031c2  add     rax, 2
0x1800031c6  sub     rdx, 1
0x1800031ca  jnz     short loc_1800031BD
0x1800031cc  sub     r9, rdx
0x1800031cf  mov     rax, rdx
0x1800031d2  neg     rax
0x1800031d5  sbb     rcx, rcx
0x1800031d8  and     rcx, r9
0x1800031db  test    rdx, rdx
0x1800031de  jz      loc_18000328D
0x1800031e4  cmp     rcx, 4
0x1800031e8  jb      loc_18000328D
0x1800031ee  add     r8, 0FFFFFFFFFFFFFFF8h
0x1800031f2  lea     rdx, aExe; ".exe"
0x1800031f9  lea     rbx, [r8+rcx*2]
0x1800031fd  mov     rcx, rbx; String1
0x180003200  call    cs:__imp__wcsicmp
0x180003206  test    eax, eax
0x180003208  jz      short loc_180003284
0x18000320a  lea     rdx, aDll; ".dll"
0x180003211  mov     rcx, rbx; String1
0x180003214  call    cs:__imp__wcsicmp
0x18000321a  test    eax, eax
0x18000321c  jz      short loc_180003284
0x18000321e  lea     rdx, aRll; ".rll"
0x180003225  mov     rcx, rbx; String1
0x180003228  call    cs:__imp__wcsicmp
0x18000322e  test    eax, eax
0x180003230  jz      short loc_180003284
0x180003232  lea     rdx, aSys; ".sys"
0x180003239  mov     rcx, rbx; String1
0x18000323c  call    cs:__imp__wcsicmp
0x180003242  test    eax, eax
0x180003244  jz      short loc_180003284
0x180003246  lea     rdx, aOcx; ".ocx"
0x18000324d  mov     rcx, rbx; String1
0x180003250  call    cs:__imp__wcsicmp
0x180003256  test    eax, eax
0x180003258  jz      short loc_180003284
0x18000325a  lea     rdx, aOlb; ".olb"
0x180003261  mov     rcx, rbx; String1
0x180003264  call    cs:__imp__wcsicmp
0x18000326a  test    eax, eax
0x18000326c  jz      short loc_180003284
0x18000326e  lea     rdx, aTlb; ".tlb"
0x180003275  mov     rcx, rbx; String1
0x180003278  mov     edi, esi
0x18000327a  call    cs:__imp__wcsicmp
0x180003280  test    eax, eax
0x180003282  jnz     short loc_180003289
0x180003284  mov     edi, 1
0x180003289  mov     eax, edi
0x18000328b  jmp     short loc_18000328F
0x18000328d  xor     eax, eax
0x18000328f  mov     rbx, [rsp+28h+arg_0]
0x180003294  mov     rsi, [rsp+28h+arg_8]
0x180003299  add     rsp, 20h
0x18000329d  pop     rdi
0x18000329e  retn
```
