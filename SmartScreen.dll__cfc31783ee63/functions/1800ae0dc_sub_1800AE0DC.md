# sub_1800AE0DC

- ea: `0x1800ae0dc`
- end: `0x1800ae1b3`
- name: `sub_1800AE0DC`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18007fbb8`

## callees

- `0x180009534`
- `0x18000a69c`
- `0x1800106b8`
- `0x1800ae0dc`
- `0x1800fea68`
- `0x18013b890`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x1800ae0ff`
- `SHLWAPI!PathFindExtensionW` at `0x1800ae0ff`

## pseudocode

```c
__int64 __fastcall sub_1800AE0DC(const WCHAR *a1, __int64 a2)
{
  LPWSTR ExtensionW; // rbx
  __int64 v4; // rax
  __int64 v5; // r8
  __int128 *v6; // r9
  unsigned __int64 v7; // rdx
  __int64 v8; // rbx
  __int128 v10; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-20h]
  unsigned __int64 v12; // [rsp+40h] [rbp-18h]

  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  ExtensionW = PathFindExtensionW(a1);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v4 = sub_1800FEA68(ExtensionW);
  sub_180009534(&v10, ExtensionW, v4);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  if ( (__int128 *)a2 != &v10 )
  {
    v6 = &v10;
    if ( v12 > 7 )
      v6 = (__int128 *)v10;
    v7 = v11;
    if ( v11 > 7 )
    {
      _mm_lfence();
      LOBYTE(v5) = 0;
      sub_18000A69C(a2, v11, v5, v6);
    }
    else
    {
      *(_QWORD *)(a2 + 16) = v11;
      v8 = 2 * v7;
      sub_18013B890(a2, v6, 2 * v7);
      *(_WORD *)(v8 + a2) = 0;
    }
  }
  sub_1800106B8(&v10);
  return a2;
}

```

## disassembly

```asm
0x1800ae0dc  mov     [rsp+arg_0], rbx
0x1800ae0e1  mov     [rsp+arg_10], rsi
0x1800ae0e6  mov     [rsp+arg_8], rdx
0x1800ae0eb  push    rdi
0x1800ae0ec  sub     rsp, 50h
0x1800ae0f0  mov     rdi, rdx
0x1800ae0f3  xor     esi, esi
0x1800ae0f5  cmp     qword ptr [rcx+18h], 7
0x1800ae0fa  jbe     short loc_1800AE0FF
0x1800ae0fc  mov     rcx, [rcx]; pszPath
0x1800ae0ff  call    cs:PathFindExtensionW
0x1800ae105  mov     rbx, rax
0x1800ae108  xorps   xmm0, xmm0
0x1800ae10b  movups  [rsp+58h+var_30], xmm0
0x1800ae110  mov     [rsp+58h+var_20], rsi
0x1800ae115  mov     [rsp+58h+var_18], rsi
0x1800ae11a  mov     rcx, rax
0x1800ae11d  call    sub_1800FEA68
0x1800ae122  mov     r8, rax
0x1800ae125  mov     rdx, rbx
0x1800ae128  lea     rcx, [rsp+58h+var_30]
0x1800ae12d  call    sub_180009534
0x1800ae132  nop
0x1800ae133  xorps   xmm0, xmm0
0x1800ae136  movups  xmmword ptr [rdi], xmm0
0x1800ae139  mov     [rdi+10h], rsi
0x1800ae13d  mov     qword ptr [rdi+18h], 7
0x1800ae145  mov     [rdi], si
0x1800ae148  lea     rax, [rsp+58h+var_30]
0x1800ae14d  cmp     rdi, rax
0x1800ae150  jz      short loc_1800AE196
0x1800ae152  lea     r9, [rsp+58h+var_30]
0x1800ae157  cmp     [rsp+58h+var_18], 7
0x1800ae15d  cmova   r9, qword ptr [rsp+58h+var_30]
0x1800ae163  mov     rdx, [rsp+58h+var_20]
0x1800ae168  mov     rcx, rdi
0x1800ae16b  cmp     rdx, 7
0x1800ae16f  ja      short loc_1800AE18A
0x1800ae171  mov     [rdi+10h], rdx
0x1800ae175  lea     rbx, [rdx+rdx]
0x1800ae179  mov     r8, rbx
0x1800ae17c  mov     rdx, r9
0x1800ae17f  call    sub_18013B890
0x1800ae184  mov     [rbx+rdi], si
0x1800ae188  jmp     short loc_1800AE196
0x1800ae18a  lfence
0x1800ae18d  mov     r8b, sil
0x1800ae190  call    sub_18000A69C
0x1800ae195  nop
0x1800ae196  lea     rcx, [rsp+58h+var_30]
0x1800ae19b  call    sub_1800106B8
0x1800ae1a0  mov     rax, rdi
0x1800ae1a3  mov     rbx, [rsp+58h+arg_0]
0x1800ae1a8  mov     rsi, [rsp+58h+arg_10]
0x1800ae1ad  add     rsp, 50h
0x1800ae1b1  pop     rdi
0x1800ae1b2  retn
```
