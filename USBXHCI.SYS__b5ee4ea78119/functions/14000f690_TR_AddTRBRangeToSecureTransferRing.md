# TR_AddTRBRangeToSecureTransferRing

- ea: `0x14000f690`
- end: `0x14000f9df`
- name: `TR_AddTRBRangeToSecureTransferRing`
- size: `847`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140007160`
- `0x14000d8d0`
- `0x14000ed00`

## callees

- `0x140005d48`
- `0x14000f690`
- `0x14001bb78`
- `0x14001c178`
- `0x140046070`
- `0x14004bd2c`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000f84e`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14000f84e`

## string_xrefs

- `0x14000f93a`: `BUGBUG: Link TRB in last segment does not point back to itself`

## pseudocode

```c
void __fastcall TR_AddTRBRangeToSecureTransferRing(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _OWORD *a6)
{
  bool v6; // zf
  unsigned int v7; // edi
  _QWORD *v9; // rsi
  unsigned int v11; // r13d
  __int64 v12; // r15
  __int64 v13; // r14
  _OWORD *v14; // rax
  int v15; // r14d
  _QWORD *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned int v20; // r13d
  _QWORD *i; // r14
  __int64 v22; // rax
  int v23; // edx
  int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+70h] [rbp+8h] BYREF

  v6 = *(_BYTE *)(a1 + 288) == 0;
  v7 = a4;
  v25 = 0;
  v9 = (_QWORD *)a2;
  if ( !v6 )
  {
    v11 = 0;
    v12 = *(_QWORD *)(a1 + 312);
    if ( !a2 || (v13 = *(_QWORD *)a2, *(_QWORD *)a2 == a2) )
      v13 = a3;
    *(_QWORD *)(v12 + 24) = *(_QWORD *)(a1 + 296);
    *(_DWORD *)(v12 + 32) = 44;
    if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 2) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 32) + 24LL))(a1, v12);
    *(_QWORD *)(v12 + 72) = *(_QWORD *)(v13 + 24);
    v14 = a6;
    *(_DWORD *)(v12 + 80) = v7;
    *(_OWORD *)(v12 + 40) = *v14;
    *(_OWORD *)(v12 + 56) = v14[1];
    if ( v9 )
    {
      for ( i = (_QWORD *)*v9; v9 != i; v7 = 0 )
      {
        do
        {
          if ( v7 > *(_DWORD *)(a1 + 196) )
            break;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_qiD(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 72LL), a2, a3, 25, v24, i[2], i[3], v7);
          }
          v22 = v11++;
          a2 = i[2] + 16LL * v7;
          *(_OWORD *)(v12 + 16 * v22 + 88) = *(_OWORD *)a2;
          if ( v11 == *(_DWORD *)(a1 + 320) )
            break;
          ++v7;
        }
        while ( (*(_DWORD *)(a2 + 12) & 0xFC00) != 0x1800 );
        i = (_QWORD *)*i;
      }
    }
    v15 = a5;
LABEL_8:
    v16 = (_QWORD *)(a3 + 24);
    while ( 1 )
    {
      if ( v7 == v15 )
        goto LABEL_15;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qiD(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 72LL), a2, a3, 26, v24, *(_QWORD *)(a3 + 16), *v16, v7);
      v17 = v7++;
      a2 = *(_QWORD *)(a3 + 16) + 16 * v17;
      v18 = v11++;
      *(_OWORD *)(v12 + 16 * v18 + 88) = *(_OWORD *)a2;
      if ( v11 == *(_DWORD *)(a1 + 320) )
      {
        if ( v7 != v15 )
        {
          Debug_FreAssertMsg(
            "BUGBUG: Current TRB Index does not match expected value",
            0,
            "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\tr.c",
            2319);
          return;
        }
LABEL_15:
        *(_DWORD *)(v12 + 84) = v11;
        v19 = 0;
        v20 = 16 * v11;
        if ( v20 + 88 >= v20 )
          v19 = v20 + 88;
        if ( (int)SecureChannel_SendRequestSynchronously(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 112LL), v12, v19, &v25, 4) >= 0
          && v25 < 0
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL);
          LOBYTE(v23) = 2;
          WPP_RECORDER_SF_ddL(
            *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
            v23,
            14,
            27,
            (__int64)WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids,
            *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
            *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
            v25);
        }
        return;
      }
      if ( (*(_DWORD *)(a2 + 12) & 0xFC00) != 0x1800 )
        goto LABEL_8;
      if ( *(_QWORD *)a2 != *v16 )
        break;
      v7 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (unsigned int)"onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\tr.c",
        a4);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
}

```

## disassembly

```asm
0x14000f690  push    rbx
0x14000f692  push    rbp
0x14000f693  push    rsi
0x14000f694  push    rdi
0x14000f695  sub     rsp, 48h
0x14000f699  cmp     byte ptr [rcx+120h], 0
0x14000f6a0  mov     edi, r9d
0x14000f6a3  mov     rbp, r8
0x14000f6a6  mov     [rsp+68h+arg_0], 0
0x14000f6ae  mov     rsi, rdx
0x14000f6b1  mov     rbx, rcx
0x14000f6b4  jnz     short loc_14000F6C0
0x14000f6b6  add     rsp, 48h
0x14000f6ba  pop     rdi
0x14000f6bb  pop     rsi
0x14000f6bc  pop     rbp
0x14000f6bd  pop     rbx
0x14000f6be  retn
0x14000f6c0  mov     [rsp+68h+arg_8], r12
0x14000f6c5  mov     [rsp+68h+arg_10], r13
0x14000f6cd  xor     r13d, r13d
0x14000f6d0  mov     [rsp+68h+arg_18], r14
0x14000f6d8  mov     [rsp+68h+var_28], r15
0x14000f6dd  mov     r15, [rcx+138h]
0x14000f6e4  test    rsi, rsi
0x14000f6e7  jnz     loc_14000F811
0x14000f6ed  mov     r14, rbp
0x14000f6f0  mov     rax, [rcx+128h]
0x14000f6f7  mov     [r15+18h], rax
0x14000f6fb  mov     dword ptr [r15+20h], 2Ch ; ','
0x14000f703  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 2
0x14000f70a  jz      short loc_14000F71C
0x14000f70c  mov     rax, [rcx+20h]
0x14000f710  mov     rdx, r15
0x14000f713  mov     rax, [rax+18h]
0x14000f717  call    _guard_dispatch_icall
0x14000f71c  mov     rax, [r14+18h]
0x14000f720  lea     r12, WPP_RECORDER_INITIALIZED
0x14000f727  mov     [r15+48h], rax
0x14000f72b  mov     rax, [rsp+68h+arg_28]
0x14000f733  mov     [r15+50h], edi
0x14000f737  movups  xmm0, xmmword ptr [rax]
0x14000f73a  movups  xmmword ptr [r15+28h], xmm0
0x14000f73f  movups  xmm1, xmmword ptr [rax+10h]
0x14000f743  movups  xmmword ptr [r15+38h], xmm1
0x14000f748  test    rsi, rsi
0x14000f74b  jnz     loc_14000F861
0x14000f751  mov     r14d, [rsp+68h+arg_20]
0x14000f759  lea     rsi, [rbp+18h]
0x14000f75d  cmp     edi, r14d
0x14000f760  jz      short loc_14000F7AD
0x14000f762  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000f769  jz      short loc_14000F77D
0x14000f76b  mov     rax, cs:WPP_GLOBAL_Control
0x14000f772  cmp     word ptr [rax+48h], 0
0x14000f777  jnz     loc_14000F8FF
0x14000f77d  mov     edx, edi
0x14000f77f  inc     edi
0x14000f781  shl     rdx, 4
0x14000f785  add     rdx, [rbp+10h]
0x14000f789  mov     eax, r13d
0x14000f78c  inc     r13d
0x14000f78f  add     rax, rax
0x14000f792  movups  xmm0, xmmword ptr [rdx]
0x14000f795  movups  xmmword ptr [r15+rax*8+58h], xmm0
0x14000f79b  cmp     r13d, [rbx+140h]
0x14000f7a2  jnz     short loc_14000F822
0x14000f7a4  cmp     edi, r14d
0x14000f7a7  jnz     loc_14000F968
0x14000f7ad  mov     [r15+54h], r13d
0x14000f7b1  lea     r9, [rsp+68h+arg_0]
0x14000f7b6  mov     rax, [rbx+28h]
0x14000f7ba  xor     r8d, r8d
0x14000f7bd  shl     r13d, 4
0x14000f7c1  mov     rdx, r15
0x14000f7c4  mov     dword ptr [rsp+68h+var_48], 4
0x14000f7cc  mov     rcx, [rax+70h]
0x14000f7d0  lea     eax, [r13+58h]
0x14000f7d4  cmp     eax, r13d
0x14000f7d7  cmovnb  r8d, eax
0x14000f7db  call    SecureChannel_SendRequestSynchronously
0x14000f7e0  test    eax, eax
0x14000f7e2  js      short loc_14000F7F2
0x14000f7e4  mov     r8d, [rsp+68h+arg_0]
0x14000f7e9  test    r8d, r8d
0x14000f7ec  js      loc_14000F988
0x14000f7f2  mov     r14, [rsp+68h+arg_18]
0x14000f7fa  mov     r13, [rsp+68h+arg_10]
0x14000f802  mov     r12, [rsp+68h+arg_8]
0x14000f807  mov     r15, [rsp+68h+var_28]
0x14000f80c  jmp     loc_14000F6B6
0x14000f811  mov     r14, [rdx]
0x14000f814  cmp     r14, rsi
0x14000f817  jnz     loc_14000F6F0
0x14000f81d  jmp     loc_14000F6ED
0x14000f822  mov     eax, [rdx+0Ch]
0x14000f825  and     eax, 0FC00h
0x14000f82a  cmp     eax, 1800h
0x14000f82f  jnz     loc_14000F759
0x14000f835  mov     rax, [rsi]
0x14000f838  cmp     [rdx], rax
0x14000f83b  jz      loc_14000F92C
0x14000f841  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000f848  jnz     loc_14000F933
0x14000f84e  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14000f855  nop     dword ptr [rax+rax+00h]
0x14000f85a  test    al, al
0x14000f85c  jnz     short loc_14000F7F2
0x14000f85e  int     3; Trap to Debugger
0x14000f85f  jmp     short loc_14000F7F2
0x14000f861  mov     r14, [rsi]
0x14000f864  cmp     rsi, r14
0x14000f867  jz      loc_14000F751
0x14000f86d  nop     dword ptr [rax]
0x14000f870  cmp     edi, [rbx+0C4h]
0x14000f876  ja      short loc_14000F8C5
0x14000f878  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000f87f  jz      short loc_14000F88F
0x14000f881  mov     rax, cs:WPP_GLOBAL_Control
0x14000f888  cmp     word ptr [rax+48h], 0
0x14000f88d  jnz     short loc_14000F8D4
0x14000f88f  mov     eax, r13d
0x14000f892  inc     r13d
0x14000f895  add     rax, rax
0x14000f898  mov     edx, edi
0x14000f89a  shl     rdx, 4
0x14000f89e  add     rdx, [r14+10h]
0x14000f8a2  movups  xmm0, xmmword ptr [rdx]
0x14000f8a5  movups  xmmword ptr [r15+rax*8+58h], xmm0
0x14000f8ab  cmp     r13d, [rbx+140h]
0x14000f8b2  jz      short loc_14000F8C5
0x14000f8b4  mov     eax, [rdx+0Ch]
0x14000f8b7  inc     edi
0x14000f8b9  and     eax, 0FC00h
0x14000f8be  cmp     eax, 1800h
0x14000f8c3  jnz     short loc_14000F870
0x14000f8c5  mov     r14, [r14]
0x14000f8c8  xor     edi, edi
0x14000f8ca  cmp     rsi, r14
0x14000f8cd  jnz     short loc_14000F870
0x14000f8cf  jmp     loc_14000F751
0x14000f8d4  mov     rax, [r14+18h]
0x14000f8d8  mov     r9d, 19h
0x14000f8de  mov     rcx, [rbx+28h]
0x14000f8e2  mov     dword ptr [rsp+68h+var_30], edi
0x14000f8e6  mov     [rsp+68h+var_38], rax
0x14000f8eb  mov     rax, [r14+10h]
0x14000f8ef  mov     rcx, [rcx+48h]
0x14000f8f3  mov     [rsp+68h+var_40], rax
0x14000f8f8  call    WPP_RECORDER_SF_qiD
0x14000f8fd  jmp     short loc_14000F88F
0x14000f8ff  mov     rax, [rsi]
0x14000f902  mov     r9d, 1Ah
0x14000f908  mov     rcx, [rbx+28h]
0x14000f90c  mov     dword ptr [rsp+68h+var_30], edi
0x14000f910  mov     [rsp+68h+var_38], rax
0x14000f915  mov     rax, [rbp+10h]
0x14000f919  mov     rcx, [rcx+48h]
0x14000f91d  mov     [rsp+68h+var_40], rax
0x14000f922  call    WPP_RECORDER_SF_qiD
0x14000f927  jmp     loc_14000F77D
0x14000f92c  xor     edi, edi
0x14000f92e  jmp     loc_14000F75D
0x14000f933  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f93a  lea     rax, aBugbugLinkTrbI; "BUGBUG: Link TRB in last segment does n"...
0x14000f941  mov     [rsp+68h+var_30], rax
0x14000f946  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14000f94d  mov     dword ptr [rsp+68h+var_38], 8FCh
0x14000f955  mov     [rsp+68h+var_40], r8
0x14000f95a  mov     rcx, [rcx+40h]
0x14000f95e  call    WPP_RECORDER_SF_sds
0x14000f963  jmp     loc_14000F84E
0x14000f968  mov     r9d, 90Fh
0x14000f96e  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14000f975  xor     edx, edx
0x14000f977  lea     rcx, aBugbugCurrentT; "BUGBUG: Current TRB Index does not matc"...
0x14000f97e  call    Debug_FreAssertMsg
0x14000f983  jmp     loc_14000F7F2
0x14000f988  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000f98f  jz      loc_14000F7F2
0x14000f995  mov     rax, [rbx+30h]
0x14000f999  mov     r9d, 1Bh
0x14000f99f  mov     rcx, [rbx+38h]
0x14000f9a3  mov     dword ptr [rsp+68h+var_30], r8d
0x14000f9a8  mov     r8d, 0Eh
0x14000f9ae  movzx   edx, byte ptr [rax+8Fh]
0x14000f9b5  mov     eax, [rcx+98h]
0x14000f9bb  mov     rcx, [rcx+50h]
0x14000f9bf  mov     dword ptr [rsp+68h+var_38], eax
0x14000f9c3  lea     rax, WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids
0x14000f9ca  mov     dword ptr [rsp+68h+var_40], edx
0x14000f9ce  mov     dl, 2
0x14000f9d0  mov     [rsp+68h+var_48], rax
0x14000f9d5  call    WPP_RECORDER_SF_ddL
0x14000f9da  jmp     loc_14000F7F2
```
