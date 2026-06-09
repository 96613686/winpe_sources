# BCryptIumBuildClaimAttributes

- ea: `0x1400123a4`
- end: `0x1400124e0`
- name: `BCryptIumBuildClaimAttributes`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140012ee8`

## callees

- `0x14001212c`
- `0x1400123a4`
- `0x140012de0`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012453`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012453`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400124cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400124cb`

## string_xrefs

- `0x1400124bc`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumBuildClaimAttributes(__int64 a1, _QWORD *a2, unsigned int *a3, int a4)
{
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  _DWORD *v14; // rax
  unsigned int v16; // [rsp+70h] [rbp+18h] BYREF

  v16 = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids,
      "BCryptIumBuildClaimAttributes");
  if ( !a3 )
  {
    v9 = -1073741811;
    v10 = 332;
LABEL_19:
    v12 = v9;
    goto LABEL_20;
  }
  if ( a2 )
    *a2 = 0;
  v11 = BCryptIumSerializePublicKey(a1, 0, &v16);
  v9 = v11;
  if ( v11 < 0 )
  {
    v10 = 347;
LABEL_10:
    v12 = (unsigned int)v11;
LABEL_20:
    VBS_ATTEST_TRACE_ERROR_IN(
      v12,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v10);
    goto LABEL_21;
  }
  v13 = v16 + 12;
  if ( v16 >= 0xFFFFFFF4 )
  {
    *a3 = -1;
    v10 = 354;
    v9 = -1073741675;
    goto LABEL_19;
  }
  v9 = 0;
  *a3 = v13;
  if ( a2 )
  {
    v14 = LocalAlloc(0, v13);
    v8 = v14;
    if ( !v14 )
    {
      v9 = -1073741801;
      v10 = 365;
      goto LABEL_19;
    }
    *v14 = 0;
    v14[1] = a4;
    v14[2] = v16;
    v11 = BCryptIumSerializePublicKey(a1, v14 + 3, &v16);
    v9 = v11;
    if ( v11 < 0 )
    {
      v10 = 379;
      goto LABEL_10;
    }
    v8[2] = v16;
    *a2 = v8;
    v8 = 0;
  }
LABEL_21:
  LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x1400123a4  push    rbx
0x1400123a6  push    rbp
0x1400123a7  push    rsi
0x1400123a8  push    rdi
0x1400123a9  push    r14
0x1400123ab  push    r15
0x1400123ad  sub     rsp, 28h
0x1400123b1  mov     r15d, r9d
0x1400123b4  mov     [rsp+58h+arg_10], 0
0x1400123bc  mov     r14, r8
0x1400123bf  mov     rsi, rdx
0x1400123c2  mov     rbp, rcx
0x1400123c5  xor     edi, edi
0x1400123c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123ce  lea     rax, WPP_GLOBAL_Control
0x1400123d5  cmp     rcx, rax
0x1400123d8  jz      short loc_1400123FA
0x1400123da  test    byte ptr [rcx+1Ch], 4
0x1400123de  jz      short loc_1400123FA
0x1400123e0  mov     rcx, [rcx+10h]
0x1400123e4  lea     edx, [rdi+0Ah]
0x1400123e7  lea     r9, aBcryptiumbuild; "BCryptIumBuildClaimAttributes"
0x1400123ee  lea     r8, WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids
0x1400123f5  call    WPP_SF_s
0x1400123fa  test    r14, r14
0x1400123fd  jnz     short loc_14001240F
0x1400123ff  mov     ebx, 0C000000Dh
0x140012404  mov     r8d, 14Ch
0x14001240a  jmp     loc_1400124BA
0x14001240f  test    rsi, rsi
0x140012412  jz      short loc_140012417
0x140012414  mov     [rsi], rdi
0x140012417  lea     r8, [rsp+58h+arg_10]
0x14001241c  xor     edx, edx
0x14001241e  mov     rcx, rbp
0x140012421  call    BCryptIumSerializePublicKey
0x140012426  mov     ebx, eax
0x140012428  test    eax, eax
0x14001242a  jns     short loc_140012439
0x14001242c  mov     r8d, 15Bh
0x140012432  mov     ecx, eax
0x140012434  jmp     loc_1400124BC
0x140012439  mov     eax, [rsp+58h+arg_10]
0x14001243d  add     eax, 0Ch
0x140012440  cmp     eax, 0Ch
0x140012443  jb      short loc_1400124A8
0x140012445  xor     ebx, ebx
0x140012447  mov     [r14], eax
0x14001244a  test    rsi, rsi
0x14001244d  jz      short loc_1400124C8
0x14001244f  mov     edx, eax; uBytes
0x140012451  xor     ecx, ecx; uFlags
0x140012453  call    cs:__imp_LocalAlloc
0x140012459  mov     rdi, rax
0x14001245c  test    rax, rax
0x14001245f  jnz     short loc_14001246E
0x140012461  mov     ebx, 0C0000017h
0x140012466  mov     r8d, 16Dh
0x14001246c  jmp     short loc_1400124BA
0x14001246e  mov     [rax], ebx
0x140012470  lea     rdx, [rdi+0Ch]
0x140012474  mov     [rax+4], r15d
0x140012478  lea     r8, [rsp+58h+arg_10]
0x14001247d  mov     eax, [rsp+58h+arg_10]
0x140012481  mov     rcx, rbp
0x140012484  mov     [rdi+8], eax
0x140012487  call    BCryptIumSerializePublicKey
0x14001248c  mov     ebx, eax
0x14001248e  test    eax, eax
0x140012490  jns     short loc_14001249A
0x140012492  mov     r8d, 17Bh
0x140012498  jmp     short loc_140012432
0x14001249a  mov     eax, [rsp+58h+arg_10]
0x14001249e  mov     [rdi+8], eax
0x1400124a1  mov     [rsi], rdi
0x1400124a4  xor     edi, edi
0x1400124a6  jmp     short loc_1400124C8
0x1400124a8  mov     dword ptr [r14], 0FFFFFFFFh
0x1400124af  mov     r8d, 162h
0x1400124b5  mov     ebx, 0C0000095h
0x1400124ba  mov     ecx, ebx
0x1400124bc  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400124c3  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400124c8  mov     rcx, rdi; hMem
0x1400124cb  call    cs:__imp_LocalFree
0x1400124d1  mov     eax, ebx
0x1400124d3  add     rsp, 28h
0x1400124d7  pop     r15
0x1400124d9  pop     r14
0x1400124db  pop     rdi
0x1400124dc  pop     rsi
0x1400124dd  pop     rbp
0x1400124de  pop     rbx
0x1400124df  retn
```
