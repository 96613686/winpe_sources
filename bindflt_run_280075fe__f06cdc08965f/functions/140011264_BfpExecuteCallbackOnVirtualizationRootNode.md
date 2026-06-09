# BfpExecuteCallbackOnVirtualizationRootNode

- ea: `0x140011264`
- end: `0x140011582`
- name: `BfpExecuteCallbackOnVirtualizationRootNode`
- size: `798`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010384`
- `0x140010898`
- `0x140010d64`

## callees

- `0x140001348`
- `0x140003304`
- `0x140004c70`
- `0x140011264`
- `0x140017bb8`
- `0x140019b40`
- `0x14001baf4`

## pseudocode

```c
__int64 __fastcall BfpExecuteCallbackOnVirtualizationRootNode(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, __int64, __int64),
        __int64 a4)
{
  __int64 v8; // rdx
  char v9; // bp
  int v10; // r9d
  int v11; // edx
  int v12; // ebx
  __int64 v13; // rdi
  bool v14; // zf
  __int64 v15; // rbx
  int v16; // esi
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  char v20; // al
  int v21; // edx
  char v23; // [rsp+30h] [rbp-78h]
  __int128 v24; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v25[11]; // [rsp+50h] [rbp-58h] BYREF

  v24 = 0;
  v9 = BfWalkContainerRootId(a2, &v24);
  if ( (_WORD)v24 )
  {
    v13 = *(_QWORD *)(a1 + 24);
    while ( 1 )
    {
      v14 = (*(_BYTE *)(v13 + 8) & 1) == 0;
      v15 = *(_QWORD *)v13;
      v25[0] = &v24;
      v25[1] = 0;
      if ( !v14 )
      {
        if ( v15 )
          v15 ^= v13;
        else
          v15 = 0;
      }
      v16 = *(_BYTE *)(v13 + 8) & 1;
      if ( !v15 )
        goto LABEL_40;
      do
      {
        v17 = BfpRBComparePathNodes((__int64)v25, v15);
        if ( v17 >= 0 )
        {
          if ( v17 <= 0 )
            break;
          v18 = *(_QWORD *)(v15 + 8);
        }
        else
        {
          v18 = *(_QWORD *)v15;
        }
        if ( v16 && v18 )
          v15 ^= v18;
        else
          v15 = v18;
      }
      while ( v15 );
      if ( !v15 )
        goto LABEL_40;
      v19 = *(_DWORD *)(v15 - 8);
      if ( (v19 & 2) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v8) = 2;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            8,
            71,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            235);
        }
        return (unsigned int)-1073741811;
      }
      if ( !v9 )
        break;
      v20 = BfWalkContainerRootId(a2, &v24);
      v13 = *(_QWORD *)(v15 - 8 + 80);
      v9 = v20;
      if ( BfpPathTreeEmpty(v13) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)-1073741275;
        v10 = 72;
        v23 = 17;
        goto LABEL_42;
      }
    }
    if ( v15 == 8 )
    {
LABEL_40:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)-1073741275;
      v10 = 73;
      v23 = 26;
      goto LABEL_42;
    }
    if ( (v19 & 1) != 0 )
    {
      v12 = a3(v13, v15, a4);
      if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          8,
          75,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          45,
          v12);
      }
      return (unsigned int)v12;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741275;
    v10 = 74;
    v23 = 33;
    goto LABEL_42;
  }
  v8 = *(_QWORD *)(a1 + 32);
  if ( !v8 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741275;
    v10 = 69;
    v23 = -67;
LABEL_42:
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      8,
      v10,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v23);
    return (unsigned int)-1073741275;
  }
  v12 = a3(0, v8 + 8, a4);
  if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      8,
      70,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      198,
      v12);
  }
  *(_QWORD *)(a1 + 32) = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140011264  push    rbx
0x140011266  push    rbp
0x140011267  push    rsi
0x140011268  push    rdi
0x140011269  push    r12
0x14001126b  push    r13
0x14001126d  push    r14
0x14001126f  push    r15
0x140011271  sub     rsp, 68h
0x140011275  mov     r14, rdx
0x140011278  mov     rdi, rcx
0x14001127b  xorps   xmm0, xmm0
0x14001127e  lea     rdx, [rsp+0A8h+var_68]
0x140011283  mov     rcx, r14
0x140011286  mov     r15, r9
0x140011289  mov     r12, r8
0x14001128c  movups  [rsp+0A8h+var_68], xmm0
0x140011291  call    BfWalkContainerRootId
0x140011296  xor     r13d, r13d
0x140011299  mov     bpl, al
0x14001129c  cmp     word ptr [rsp+0A8h+var_68], r13w
0x1400112a2  jnz     loc_140011346
0x1400112a8  mov     rdx, [rdi+20h]
0x1400112ac  test    rdx, rdx
0x1400112af  jnz     short loc_1400112D6
0x1400112b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400112b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400112bf  jz      loc_140011569
0x1400112c5  lea     r9d, [r13+45h]
0x1400112c9  mov     dword ptr [rsp+0A8h+var_78], 0BBDh
0x1400112d1  jmp     loc_140011539
0x1400112d6  add     rdx, 8
0x1400112da  mov     r8, r15
0x1400112dd  xor     ecx, ecx
0x1400112df  mov     rax, r12
0x1400112e2  call    _guard_dispatch_icall
0x1400112e7  mov     ebx, eax
0x1400112e9  test    eax, eax
0x1400112eb  jns     short loc_14001133D
0x1400112ed  lea     rax, WPP_RECORDER_INITIALIZED
0x1400112f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400112fb  jz      short loc_14001133D
0x1400112fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140011304  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001130b  mov     [rsp+0A8h+var_70], ebx
0x14001130f  mov     r9d, 46h ; 'F'
0x140011315  mov     dword ptr [rsp+0A8h+var_78], 0BC6h
0x14001131d  mov     dl, 2
0x14001131f  mov     [rsp+0A8h+var_80], rax
0x140011324  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001132b  mov     rcx, [rcx+40h]
0x14001132f  lea     r8d, [r9-3Eh]
0x140011333  mov     [rsp+0A8h+var_88], rax
0x140011338  call    WPP_RECORDER_SF_sDd
0x14001133d  mov     [rdi+20h], r13
0x140011341  jmp     loc_14001156E
0x140011346  mov     rdi, [rdi+18h]
0x14001134a  test    byte ptr [rdi+8], 1
0x14001134e  lea     rax, [rsp+0A8h+var_68]
0x140011353  mov     rbx, [rdi]
0x140011356  xorps   xmm0, xmm0
0x140011359  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x14001135e  mov     [rsp+0A8h+var_58], rax
0x140011363  mov     byte ptr [rsp+0A8h+var_58+8], r13b
0x140011368  jz      short loc_140011377
0x14001136a  test    rbx, rbx
0x14001136d  jz      short loc_140011374
0x14001136f  xor     rbx, rdi
0x140011372  jmp     short loc_140011377
0x140011374  mov     rbx, r13
0x140011377  movzx   esi, byte ptr [rdi+8]
0x14001137b  and     esi, 1
0x14001137e  test    rbx, rbx
0x140011381  jz      loc_14001151B
0x140011387  mov     rdx, rbx
0x14001138a  lea     rcx, [rsp+0A8h+var_58]
0x14001138f  call    BfpRBComparePathNodes
0x140011394  test    eax, eax
0x140011396  jns     short loc_14001139D
0x140011398  mov     rax, [rbx]
0x14001139b  jmp     short loc_1400113A3
0x14001139d  jle     short loc_1400113B9
0x14001139f  mov     rax, [rbx+8]
0x1400113a3  test    esi, esi
0x1400113a5  jz      short loc_1400113B1
0x1400113a7  test    rax, rax
0x1400113aa  jz      short loc_1400113B1
0x1400113ac  xor     rbx, rax
0x1400113af  jmp     short loc_1400113B4
0x1400113b1  mov     rbx, rax
0x1400113b4  test    rbx, rbx
0x1400113b7  jnz     short loc_140011387
0x1400113b9  test    rbx, rbx
0x1400113bc  jz      loc_14001151B
0x1400113c2  lea     rsi, [rbx-8]
0x1400113c6  mov     eax, [rsi]
0x1400113c8  test    al, 2
0x1400113ca  jnz     loc_1400114C8
0x1400113d0  test    bpl, bpl
0x1400113d3  jz      short loc_140011420
0x1400113d5  lea     rdx, [rsp+0A8h+var_68]
0x1400113da  mov     rcx, r14
0x1400113dd  call    BfWalkContainerRootId
0x1400113e2  mov     rdi, [rsi+50h]
0x1400113e6  mov     bpl, al
0x1400113e9  mov     rcx, rdi
0x1400113ec  call    BfpPathTreeEmpty
0x1400113f1  test    al, al
0x1400113f3  jz      loc_14001134A
0x1400113f9  lea     rax, WPP_RECORDER_INITIALIZED
0x140011400  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011407  jz      loc_140011569
0x14001140d  mov     r9d, 48h ; 'H'
0x140011413  mov     dword ptr [rsp+0A8h+var_78], 0C11h
0x14001141b  jmp     loc_140011539
0x140011420  test    rsi, rsi
0x140011423  jz      loc_14001151B
0x140011429  test    al, 1
0x14001142b  jnz     short loc_140011454
0x14001142d  lea     rax, WPP_RECORDER_INITIALIZED
0x140011434  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001143b  jz      loc_140011569
0x140011441  mov     r9d, 4Ah ; 'J'
0x140011447  mov     dword ptr [rsp+0A8h+var_78], 0C21h
0x14001144f  jmp     loc_140011539
0x140011454  mov     r8, r15
0x140011457  mov     rdx, rbx
0x14001145a  mov     rcx, rdi
0x14001145d  mov     rax, r12
0x140011460  call    _guard_dispatch_icall
0x140011465  mov     ebx, eax
0x140011467  test    eax, eax
0x140011469  jns     loc_14001156E
0x14001146f  lea     rax, WPP_RECORDER_INITIALIZED
0x140011476  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001147d  jz      loc_14001156E
0x140011483  mov     rcx, cs:WPP_GLOBAL_Control
0x14001148a  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140011491  mov     [rsp+0A8h+var_70], ebx
0x140011495  mov     r9d, 4Bh ; 'K'
0x14001149b  mov     dword ptr [rsp+0A8h+var_78], 0C2Dh
0x1400114a3  mov     dl, 2
0x1400114a5  mov     [rsp+0A8h+var_80], rax
0x1400114aa  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x1400114b1  mov     rcx, [rcx+40h]
0x1400114b5  lea     r8d, [r9-43h]
0x1400114b9  mov     [rsp+0A8h+var_88], rax
0x1400114be  call    WPP_RECORDER_SF_sDd
0x1400114c3  jmp     loc_14001156E
0x1400114c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400114cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400114d6  jz      short loc_140011514
0x1400114d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114df  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400114e6  mov     r9d, 47h ; 'G'
0x1400114ec  mov     dword ptr [rsp+0A8h+var_78], 0BEBh
0x1400114f4  mov     [rsp+0A8h+var_80], rax
0x1400114f9  mov     dl, 2
0x1400114fb  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140011502  mov     rcx, [rcx+40h]
0x140011506  lea     r8d, [r9-3Fh]
0x14001150a  mov     [rsp+0A8h+var_88], rax
0x14001150f  call    WPP_RECORDER_SF_sD
0x140011514  mov     ebx, 0C000000Dh
0x140011519  jmp     short loc_14001156E
0x14001151b  lea     rax, WPP_RECORDER_INITIALIZED
0x140011522  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011529  jz      short loc_140011569
0x14001152b  mov     r9d, 49h ; 'I'
0x140011531  mov     dword ptr [rsp+0A8h+var_78], 0C1Ah
0x140011539  mov     rcx, cs:WPP_GLOBAL_Control
0x140011540  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140011547  mov     [rsp+0A8h+var_80], rax
0x14001154c  mov     r8d, 8
0x140011552  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140011559  mov     dl, 2
0x14001155b  mov     [rsp+0A8h+var_88], rax
0x140011560  mov     rcx, [rcx+40h]
0x140011564  call    WPP_RECORDER_SF_sD
0x140011569  mov     ebx, 0C0000225h
0x14001156e  mov     eax, ebx
0x140011570  add     rsp, 68h
0x140011574  pop     r15
0x140011576  pop     r14
0x140011578  pop     r13
0x14001157a  pop     r12
0x14001157c  pop     rdi
0x14001157d  pop     rsi
0x14001157e  pop     rbp
0x14001157f  pop     rbx
0x140011580  retn
```
