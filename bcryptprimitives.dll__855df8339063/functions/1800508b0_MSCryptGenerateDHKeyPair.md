# MSCryptGenerateDHKeyPair

- ea: `0x1800508b0`
- end: `0x180050ab0`
- name: `MSCryptGenerateDHKeyPair`
- size: `512`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x1800508b0`
- `0x180050ab8`
- `0x180058288`

## string_xrefs

- `0x180050972`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x1800509b2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x1800509d0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180050a76`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptGenerateDHKeyPair(__int64 a1, __int64 *a2, unsigned int a3, int a4)
{
  int v5; // ebx
  int v6; // r8d
  __int64 v8; // rax
  int v9; // r8d
  __int64 v10; // rdi
  int v11; // ecx
  __int64 v12; // rax
  int v13; // r8d
  __int64 v14[3]; // [rsp+40h] [rbp-18h] BYREF
  int v15; // [rsp+60h] [rbp+8h] BYREF

  v14[0] = 0;
  v15 = 0;
  if ( a1 && a2 && !a4 )
  {
    v5 = ValidateDHAlgorithm(a1, a3, &v15, v14);
    if ( v5 >= 0 )
    {
      v8 = SafeAllocaAllocateFromHeap(40);
      v10 = v8;
      if ( v8 )
      {
        *(_QWORD *)(v8 + 8) = 0;
        *(_QWORD *)(v8 + 16) = 0;
        *(_QWORD *)(v8 + 24) = 0;
        *(_QWORD *)(v8 + 32) = 0;
        *(_DWORD *)v8 = 40;
        *(_DWORD *)(v8 + 4) = 1297304409;
        *(_DWORD *)(v8 + 8) = *(_DWORD *)(v14[0] + 8);
        v11 = v15;
        *(_DWORD *)(v8 + 12) = v15;
        v12 = SymCryptDlgroupAllocate((unsigned int)(8 * v11), 0);
        *(_QWORD *)(v10 + 24) = v12;
        if ( v12 )
        {
          *(_QWORD *)(v10 + 32) = 0;
          *a2 = v10;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v13,
              (unsigned int)"Status",
              23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
              218);
          MSCryptFree(v10);
          return (unsigned int)-1073741801;
        }
      }
      else
      {
        v5 = -1073741801;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)WPP_GLOBAL_Control,
            v9,
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
            199);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v6,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
        186);
    }
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
        178);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800508b0  mov     r11, rsp
0x1800508b3  mov     [r11+10h], rbx
0x1800508b7  mov     [r11+18h], rsi
0x1800508bb  push    rdi
0x1800508bc  sub     rsp, 50h
0x1800508c0  mov     qword ptr [r11-18h], 0
0x1800508c8  mov     eax, r8d
0x1800508cb  mov     [rsp+58h+arg_0], 0
0x1800508d3  mov     rsi, rdx
0x1800508d6  test    rcx, rcx
0x1800508d9  jz      loc_180050988
0x1800508df  test    rdx, rdx
0x1800508e2  jz      loc_180050988
0x1800508e8  test    r9d, r9d
0x1800508eb  jnz     loc_180050988
0x1800508f1  lea     r9, [r11-18h]
0x1800508f5  mov     edx, eax
0x1800508f7  lea     r8, [r11+8]
0x1800508fb  call    ValidateDHAlgorithm
0x180050900  mov     ebx, eax
0x180050902  test    eax, eax
0x180050904  jns     short loc_180050936
0x180050906  mov     rdx, cs:WPP_GLOBAL_Control
0x18005090d  lea     rcx, WPP_GLOBAL_Control
0x180050914  cmp     rdx, rcx
0x180050917  jz      short loc_180050923
0x180050919  test    byte ptr [rdx+1Ch], 1
0x18005091d  jnz     loc_1800509C8
0x180050923  mov     rsi, [rsp+58h+arg_10]
0x180050928  mov     eax, ebx
0x18005092a  mov     rbx, [rsp+58h+arg_8]
0x18005092f  add     rsp, 50h
0x180050933  pop     rdi
0x180050934  retn
0x180050936  mov     ecx, 28h ; '('
0x18005093b  call    SafeAllocaAllocateFromHeap
0x180050940  mov     rdi, rax
0x180050943  test    rax, rax
0x180050946  jnz     loc_1800509F5
0x18005094c  mov     ebx, 0C0000017h
0x180050951  mov     rdx, cs:WPP_GLOBAL_Control
0x180050958  lea     rcx, WPP_GLOBAL_Control
0x18005095f  cmp     rdx, rcx
0x180050962  jz      short loc_180050923
0x180050964  test    byte ptr [rdx+1Ch], 1
0x180050968  jz      short loc_180050923
0x18005096a  mov     [rsp+58h+var_28], 4C7h
0x180050972  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180050979  mov     [rsp+58h+var_30], rax
0x18005097e  mov     [rsp+58h+var_38], 0C0000017h
0x180050986  jmp     short loc_1800509E0
0x180050988  mov     ebx, 0C000000Dh
0x18005098d  mov     rdx, cs:WPP_GLOBAL_Control
0x180050994  lea     rcx, WPP_GLOBAL_Control
0x18005099b  cmp     rdx, rcx
0x18005099e  jz      short loc_180050923
0x1800509a0  test    byte ptr [rdx+1Ch], 1
0x1800509a4  jz      loc_180050923
0x1800509aa  mov     [rsp+58h+var_28], 4B2h
0x1800509b2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800509b9  mov     [rsp+58h+var_30], rax
0x1800509be  mov     [rsp+58h+var_38], 0C000000Dh
0x1800509c6  jmp     short loc_1800509E0
0x1800509c8  mov     [rsp+58h+var_28], 4BAh
0x1800509d0  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800509d7  mov     [rsp+58h+var_30], rax
0x1800509dc  mov     [rsp+58h+var_38], ebx
0x1800509e0  mov     rcx, [rdx+10h]
0x1800509e4  lea     r9, aStatus; "Status"
0x1800509eb  call    WPP_SF_sDsd
0x1800509f0  jmp     loc_180050923
0x1800509f5  mov     qword ptr [rax+8], 0
0x1800509fd  xor     edx, edx
0x1800509ff  mov     qword ptr [rax+10h], 0
0x180050a07  mov     qword ptr [rax+18h], 0
0x180050a0f  mov     qword ptr [rax+20h], 0
0x180050a17  mov     dword ptr [rax], 28h ; '('
0x180050a1d  mov     dword ptr [rax+4], 4D534B59h
0x180050a24  mov     rax, [rsp+58h+var_18]
0x180050a29  mov     ecx, [rax+8]
0x180050a2c  mov     [rdi+8], ecx
0x180050a2f  mov     ecx, [rsp+58h+arg_0]
0x180050a33  mov     [rdi+0Ch], ecx
0x180050a36  shl     ecx, 3
0x180050a39  call    SymCryptDlgroupAllocate
0x180050a3e  mov     [rdi+18h], rax
0x180050a42  test    rax, rax
0x180050a45  jnz     short loc_180050AA0
0x180050a47  mov     rdx, cs:WPP_GLOBAL_Control
0x180050a4e  lea     rcx, WPP_GLOBAL_Control
0x180050a55  cmp     rdx, rcx
0x180050a58  jz      short loc_180050A60
0x180050a5a  test    byte ptr [rdx+1Ch], 1
0x180050a5e  jnz     short loc_180050A72
0x180050a60  mov     rcx, rdi
0x180050a63  call    MSCryptFree
0x180050a68  mov     ebx, 0C0000017h
0x180050a6d  jmp     loc_180050923
0x180050a72  mov     rcx, [rdx+10h]
0x180050a76  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180050a7d  mov     [rsp+58h+var_28], 4DAh
0x180050a85  lea     r9, aStatus; "Status"
0x180050a8c  mov     [rsp+58h+var_30], rax
0x180050a91  mov     [rsp+58h+var_38], 0C0000017h
0x180050a99  call    WPP_SF_sDsd
0x180050a9e  jmp     short loc_180050A60
0x180050aa0  mov     qword ptr [rdi+20h], 0
0x180050aa8  mov     [rsi], rdi
0x180050aab  jmp     loc_180050923
```
