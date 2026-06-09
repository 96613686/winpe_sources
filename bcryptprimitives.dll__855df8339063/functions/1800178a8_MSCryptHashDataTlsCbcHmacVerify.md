# MSCryptHashDataTlsCbcHmacVerify

- ea: `0x1800178a8`
- end: `0x1800179f0`
- name: `MSCryptHashDataTlsCbcHmacVerify`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800173f0`

## callees

- `0x18000ee60`
- `0x180016d30`
- `0x180016d60`
- `0x1800178a8`
- `0x1800179f8`
- `0x180018590`

## string_xrefs

- `0x1800179c3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptHashDataTlsCbcHmacVerify(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  int v5; // esi
  __int64 v6; // rdi
  __int64 v7; // rbx
  unsigned int v8; // ebx
  __int64 v10; // rdi
  __int64 v11; // rbx

  switch ( *(_DWORD *)(a1 + 8) )
  {
    case 0x20009:
      v6 = a1 + 208;
      v7 = a1 + 128;
      v5 = SymCryptTlsCbcHmacVerify(
             (unsigned int)&SymCryptHmacSha1Algorithm_default,
             (int)a1 + 128,
             (int)a1 + 208,
             a2,
             a3);
      SymCryptHmacSha1Init(v6, v7);
      return v5 != 0 ? 0xC0000001 : 0;
    case 0x2000B:
      v10 = a1 + 208;
      v11 = a1 + 128;
      v5 = SymCryptTlsCbcHmacVerify(
             (unsigned int)&SymCryptHmacSha256Algorithm_default,
             (int)a1 + 128,
             (int)a1 + 208,
             a2,
             a3);
      SymCryptHmacSha256Init(v10, v11);
      return v5 != 0 ? 0xC0000001 : 0;
    case 0x2000C:
      v3 = a1 + 272;
      v4 = a1 + 128;
      v5 = SymCryptTlsCbcHmacVerify(
             (unsigned int)&SymCryptHmacSha384Algorithm_default,
             (int)a1 + 128,
             (int)a1 + 272,
             a2,
             a3);
      SymCryptHmacSha512Init(v3, v4);
      return v5 != 0 ? 0xC0000001 : 0;
  }
  v8 = -1073741637;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      228);
  return v8;
}

```

## disassembly

```asm
0x1800178a8  mov     [rsp+arg_0], rbx
0x1800178ad  mov     [rsp+arg_8], rsi
0x1800178b2  push    rdi
0x1800178b3  sub     rsp, 40h
0x1800178b7  mov     r9d, [rcx+8]
0x1800178bb  sub     r9d, 20009h
0x1800178c2  jz      short loc_180017912
0x1800178c4  sub     r9d, 2
0x1800178c8  jz      loc_180017967
0x1800178ce  cmp     r9d, 1
0x1800178d2  jnz     loc_1800179A1
0x1800178d8  lea     rdi, [rcx+110h]
0x1800178df  mov     eax, r8d
0x1800178e2  lea     rbx, [rcx+80h]
0x1800178e9  mov     [rsp+48h+var_28], rax
0x1800178ee  mov     r9, rdx
0x1800178f1  lea     rcx, SymCryptHmacSha384Algorithm_default
0x1800178f8  mov     r8, rdi
0x1800178fb  mov     rdx, rbx
0x1800178fe  call    SymCryptTlsCbcHmacVerify
0x180017903  mov     rdx, rbx
0x180017906  mov     rcx, rdi
0x180017909  mov     esi, eax
0x18001790b  call    SymCryptHmacSha512Init
0x180017910  jmp     short loc_18001794A
0x180017912  lea     rdi, [rcx+0D0h]
0x180017919  mov     eax, r8d
0x18001791c  lea     rbx, [rcx+80h]
0x180017923  mov     [rsp+48h+var_28], rax
0x180017928  mov     r9, rdx
0x18001792b  lea     rcx, SymCryptHmacSha1Algorithm_default
0x180017932  mov     r8, rdi
0x180017935  mov     rdx, rbx
0x180017938  call    SymCryptTlsCbcHmacVerify
0x18001793d  mov     rdx, rbx
0x180017940  mov     rcx, rdi
0x180017943  mov     esi, eax
0x180017945  call    SymCryptHmacSha1Init
0x18001794a  neg     esi
0x18001794c  sbb     ebx, ebx
0x18001794e  and     ebx, 0C0000001h
0x180017954  mov     rsi, [rsp+48h+arg_8]
0x180017959  mov     eax, ebx
0x18001795b  mov     rbx, [rsp+48h+arg_0]
0x180017960  add     rsp, 40h
0x180017964  pop     rdi
0x180017965  retn
0x180017967  lea     rdi, [rcx+0D0h]
0x18001796e  mov     eax, r8d
0x180017971  lea     rbx, [rcx+80h]
0x180017978  mov     [rsp+48h+var_28], rax
0x18001797d  mov     r9, rdx
0x180017980  lea     rcx, SymCryptHmacSha256Algorithm_default
0x180017987  mov     r8, rdi
0x18001798a  mov     rdx, rbx
0x18001798d  call    SymCryptTlsCbcHmacVerify
0x180017992  mov     rdx, rbx
0x180017995  mov     rcx, rdi
0x180017998  mov     esi, eax
0x18001799a  call    SymCryptHmacSha256Init
0x18001799f  jmp     short loc_18001794A
0x1800179a1  mov     ebx, 0C00000BBh
0x1800179a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179ad  lea     rax, WPP_GLOBAL_Control
0x1800179b4  cmp     rcx, rax
0x1800179b7  jz      short loc_180017954
0x1800179b9  test    byte ptr [rcx+1Ch], 1
0x1800179bd  jz      short loc_180017954
0x1800179bf  mov     rcx, [rcx+10h]
0x1800179c3  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800179ca  mov     [rsp+48h+var_18], 8E4h
0x1800179d2  lea     r9, aStatus; "Status"
0x1800179d9  mov     [rsp+48h+var_20], rax
0x1800179de  mov     dword ptr [rsp+48h+var_28], 0C00000BBh
0x1800179e6  call    WPP_SF_sDsd
0x1800179eb  jmp     loc_180017954
```
