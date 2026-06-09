# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004508`
- end: `0x14000457e`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002bc0`
- `0x140004694`

## callees

- `0x140004508`
- `0x1400045e8`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  size_t *v6; // r8
  __int64 v7; // r10
  size_t v9; // [rsp+20h] [rbp-18h]

  v4 = 260;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? (size_t *)0x80070057LL : 0LL;
  if ( v4 )
  {
    v7 = (260 - v4) & -(__int64)(v4 != 0);
    LODWORD(v6) = StringCopyWorkerW(&a1[v7], 260 - v7, v6, a3, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004508  mov     [rsp+arg_0], rbx
0x14000450d  push    rdi
0x14000450e  sub     rsp, 30h
0x140004512  mov     edx, 104h
0x140004517  mov     rbx, r8
0x14000451a  mov     r9d, edx
0x14000451d  mov     r11, rcx
0x140004520  mov     rax, rcx
0x140004523  xor     edi, edi
0x140004525  cmp     [rax], di
0x140004528  jz      short loc_140004534
0x14000452a  add     rax, 2
0x14000452e  sub     r9, 1
0x140004532  jnz     short loc_140004525
0x140004534  mov     rax, r9
0x140004537  mov     rcx, rdx
0x14000453a  neg     rax
0x14000453d  mov     rax, r9
0x140004540  sbb     r8d, r8d
0x140004543  sub     rcx, r9
0x140004546  not     r8d
0x140004549  and     r8d, 80070057h; pcchNewDestLength
0x140004550  neg     rax
0x140004553  sbb     r10, r10
0x140004556  and     r10, rcx
0x140004559  test    r9, r9
0x14000455c  jz      short loc_140004570
0x14000455e  sub     rdx, r10; cchDest
0x140004561  lea     rcx, [r11+r10*2]; pszDest
0x140004565  mov     r9, rbx; pszSrc
0x140004568  call    StringCopyWorkerW
0x14000456d  mov     r8d, eax
0x140004570  mov     rbx, [rsp+38h+arg_0]
0x140004575  mov     eax, r8d
0x140004578  add     rsp, 30h
0x14000457c  pop     rdi
0x14000457d  retn
```
