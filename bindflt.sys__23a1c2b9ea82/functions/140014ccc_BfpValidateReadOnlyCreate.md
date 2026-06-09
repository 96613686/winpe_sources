# BfpValidateReadOnlyCreate

- ea: `0x140014ccc`
- end: `0x140014e93`
- name: `BfpValidateReadOnlyCreate`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400157a0`

## callees

- `0x140002740`
- `0x140003304`
- `0x140014ccc`

## string_xrefs

- `0x140014d09`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140014d81`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140014e5e`: `onecore\base\fs\wci\bindflt\filter\create.c`

## pseudocode

```c
char __fastcall BfpValidateReadOnlyCreate(__int64 a1, char a2)
{
  __int64 v2; // r8
  int v5; // edx
  int v6; // ecx
  __int64 v8; // r8
  int v9; // r9d
  char v10; // [rsp+30h] [rbp-38h]

  v2 = *(_QWORD *)(a1 + 16);
  v5 = 1179817;
  v6 = *(_DWORD *)(*(_QWORD *)(v2 + 24) + 16LL);
  if ( (v6 | 0x1200A9) != 0x1200A9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 3;
      WPP_RECORDER_SF_sDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        5,
        16,
        (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
        206,
        v6);
    }
    return 0;
  }
  if ( *(_BYTE *)(v2 + 35) )
  {
    if ( *(_BYTE *)(v2 + 35) == 1 )
      goto LABEL_9;
    if ( *(_BYTE *)(v2 + 35) != 2 )
    {
      if ( *(_BYTE *)(v2 + 35) == 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v5) = 3;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v5,
            5,
            18,
            (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
            232);
        }
        *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) ^= 0x2000000u;
LABEL_9:
        if ( !a2 )
        {
          v8 = *(_QWORD *)(a1 + 16);
          v5 = *(unsigned __int16 *)(v8 + 42);
          if ( (v5 & 1) == 0 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)(v8 + 8) + 80LL) & 0x2000000) != 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v9 = 19;
                v10 = 11;
LABEL_22:
                LOBYTE(v5) = 3;
                WPP_RECORDER_SF_sD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v5,
                  5,
                  v9,
                  (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
                  v10);
                return 0;
              }
              return 0;
            }
            *(_WORD *)(v8 + 42) = v5 | 1;
          }
        }
        return 1;
      }
      if ( (unsigned int)*(unsigned __int8 *)(v2 + 35) - 4 >= 2 )
        return 0;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = 17;
    v10 = -35;
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x140014ccc  push    rbx
0x140014cce  push    rbp
0x140014ccf  push    rsi
0x140014cd0  push    rdi
0x140014cd1  push    r14
0x140014cd3  sub     rsp, 40h
0x140014cd7  mov     r8, [rcx+10h]
0x140014cdb  mov     rbp, rcx
0x140014cde  mov     r14b, dl
0x140014ce1  mov     edx, 1200A9h
0x140014ce6  mov     rax, [r8+18h]
0x140014cea  mov     ecx, [rax+10h]
0x140014ced  mov     eax, ecx
0x140014cef  or      eax, edx
0x140014cf1  cmp     eax, edx
0x140014cf3  jnz     short loc_140014D6D
0x140014cf5  movzx   eax, byte ptr [r8+23h]
0x140014cfa  test    eax, eax
0x140014cfc  jz      loc_140014E3C
0x140014d02  lea     rbx, WPP_RECORDER_INITIALIZED
0x140014d09  lea     rdi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140014d10  lea     rsi, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x140014d17  sub     eax, 1
0x140014d1a  jz      short loc_140014D40
0x140014d1c  sub     eax, 1
0x140014d1f  jz      loc_140014E3C
0x140014d25  sub     eax, 1
0x140014d28  jnz     short loc_140014D57
0x140014d2a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140014d31  jnz     loc_140014DBF
0x140014d37  mov     rax, [rbp+10h]
0x140014d3b  btc     dword ptr [rax+20h], 19h
0x140014d40  test    r14b, r14b
0x140014d43  jz      loc_140014DF2
0x140014d49  mov     al, 1
0x140014d4b  add     rsp, 40h
0x140014d4f  pop     r14
0x140014d51  pop     rdi
0x140014d52  pop     rsi
0x140014d53  pop     rbp
0x140014d54  pop     rbx
0x140014d55  retn
0x140014d57  sub     eax, 1
0x140014d5a  jz      loc_140014E3C
0x140014d60  cmp     eax, 1
0x140014d63  jz      loc_140014E3C
0x140014d69  xor     al, al
0x140014d6b  jmp     short loc_140014D4B
0x140014d6d  lea     rbx, WPP_RECORDER_INITIALIZED
0x140014d74  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140014d7b  jz      short loc_140014D69
0x140014d7d  mov     [rsp+68h+var_30], ecx
0x140014d81  lea     rdi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140014d88  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d8f  lea     rsi, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x140014d96  mov     r9d, 10h
0x140014d9c  mov     dword ptr [rsp+68h+var_38], 1CEh
0x140014da4  mov     [rsp+68h+var_40], rdi
0x140014da9  mov     dl, 3
0x140014dab  mov     [rsp+68h+var_48], rsi
0x140014db0  mov     rcx, [rcx+40h]
0x140014db4  lea     r8d, [r9-0Bh]
0x140014db8  call    WPP_RECORDER_SF_sDD
0x140014dbd  jmp     short loc_140014D69
0x140014dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dc6  mov     r9d, 12h
0x140014dcc  mov     dword ptr [rsp+68h+var_38], 1E8h
0x140014dd4  mov     dl, 3
0x140014dd6  mov     [rsp+68h+var_40], rdi
0x140014ddb  mov     [rsp+68h+var_48], rsi
0x140014de0  mov     rcx, [rcx+40h]
0x140014de4  lea     r8d, [r9-0Dh]
0x140014de8  call    WPP_RECORDER_SF_sD
0x140014ded  jmp     loc_140014D37
0x140014df2  mov     r8, [rbp+10h]
0x140014df6  movzx   edx, word ptr [r8+2Ah]
0x140014dfb  test    dl, 1
0x140014dfe  jnz     loc_140014D49
0x140014e04  mov     rax, [r8+8]
0x140014e08  test    dword ptr [rax+50h], 2000000h
0x140014e0f  jz      short loc_140014E2E
0x140014e11  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140014e18  jz      loc_140014D69
0x140014e1e  mov     r9d, 13h
0x140014e24  mov     dword ptr [rsp+68h+var_38], 20Bh
0x140014e2c  jmp     short loc_140014E6C
0x140014e2e  or      dx, 1
0x140014e32  mov     [r8+2Ah], dx
0x140014e37  jmp     loc_140014D49
0x140014e3c  lea     rbx, WPP_RECORDER_INITIALIZED
0x140014e43  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140014e4a  jz      loc_140014D69
0x140014e50  mov     r9d, 11h
0x140014e56  mov     dword ptr [rsp+68h+var_38], 1DDh
0x140014e5e  lea     rdi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140014e65  lea     rsi, WPP_48a527b79fd4344d8b4157379f595642_Traceguids
0x140014e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e73  mov     r8d, 5
0x140014e79  mov     [rsp+68h+var_40], rdi
0x140014e7e  mov     dl, 3
0x140014e80  mov     [rsp+68h+var_48], rsi
0x140014e85  mov     rcx, [rcx+40h]
0x140014e89  call    WPP_RECORDER_SF_sD
0x140014e8e  jmp     loc_140014D69
```
