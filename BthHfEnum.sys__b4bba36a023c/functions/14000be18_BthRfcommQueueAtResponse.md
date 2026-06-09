# BthRfcommQueueAtResponse

- ea: `0x14000be18`
- end: `0x14000bf9a`
- name: `BthRfcommQueueAtResponse`
- size: `386`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001bd0`
- `0x14000bfa0`

## callees

- `0x14000be18`
- `0x14000c190`
- `0x14001ae00`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14000bf1c`
- `HAL!KeQueryPerformanceCounter` at `0x14000bf1c`

## pseudocode

```c
__int64 __fastcall BthRfcommQueueAtResponse(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r14
  int v5; // ebx
  _OWORD *v6; // rax
  __int128 v8; // [rsp+40h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-30h]
  __int128 v10; // [rsp+60h] [rbp-20h]
  __int64 v11; // [rsp+70h] [rbp-10h]
  _OWORD *v12; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v13; // [rsp+B8h] [rbp+38h] BYREF

  v11 = 0;
  v13 = 0;
  v12 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  *(_QWORD *)&v9 = 0;
  v11 = 0;
  v8 = 0;
  LODWORD(v8) = 56;
  v10 = 0;
  *((_QWORD *)&v9 + 1) = 0x100000001LL;
  *(_QWORD *)&v10 = *(_QWORD *)(v4 + 200);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, _QWORD, __int64, __int64 *, _OWORD **))(WdfFunctions_01015 + 1536))(
         WdfDriverGlobals,
         &v8,
         512,
         0,
         64,
         &v13,
         &v12);
  if ( v5 >= 0 )
  {
    v6 = v12;
    *v12 = *a2;
    v6[1] = a2[1];
    v6[2] = a2[2];
    v6[3] = a2[3];
    *(LARGE_INTEGER *)v12 = KeQueryPerformanceCounter(0);
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 120))(
           WdfDriverGlobals,
           *(_QWORD *)(v4 + 200),
           v13);
    if ( v5 >= 0 )
      Bus_ProcessAtResponses(a1);
    else
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v13);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000be18  mov     [rsp-18h+arg_0], rbx
0x14000be1d  mov     [rsp-18h+arg_8], rsi
0x14000be22  push    rbp
0x14000be23  push    rdi
0x14000be24  push    r14
0x14000be26  mov     rbp, rsp
0x14000be29  sub     rsp, 80h
0x14000be30  mov     r8, cs:off_1400220B0
0x14000be37  xor     eax, eax
0x14000be39  xorps   xmm0, xmm0
0x14000be3c  mov     [rbp+var_10], rax
0x14000be40  mov     [rbp+arg_18], rax
0x14000be44  mov     rdi, rdx
0x14000be47  mov     [rbp+arg_10], rax
0x14000be4b  mov     rsi, rcx
0x14000be4e  mov     rax, cs:WdfFunctions_01015
0x14000be55  mov     rdx, rcx
0x14000be58  mov     rcx, cs:WdfDriverGlobals
0x14000be5f  movups  [rbp+var_40], xmm0
0x14000be63  movups  [rbp+var_30], xmm0
0x14000be67  movups  [rbp+var_20], xmm0
0x14000be6b  mov     rax, [rax+650h]
0x14000be72  call    _guard_dispatch_icall
0x14000be77  mov     r14, rax
0x14000be7a  lea     rdx, [rbp+var_40]
0x14000be7e  xor     eax, eax
0x14000be80  xorps   xmm0, xmm0
0x14000be83  movups  [rbp+var_30], xmm0
0x14000be87  mov     [rbp+var_10], rax
0x14000be8b  xor     r9d, r9d
0x14000be8e  movups  [rbp+var_40], xmm0
0x14000be92  mov     eax, 1
0x14000be97  mov     dword ptr [rbp+var_40], 38h ; '8'
0x14000be9e  movups  [rbp+var_20], xmm0
0x14000bea2  mov     dword ptr [rbp+var_30+8], eax
0x14000bea5  mov     r8d, 200h
0x14000beab  mov     dword ptr [rbp+var_30+0Ch], eax
0x14000beae  mov     rcx, [r14+0C8h]
0x14000beb5  mov     qword ptr [rbp+var_20], rcx
0x14000beb9  mov     rcx, cs:WdfFunctions_01015
0x14000bec0  mov     rax, [rcx+600h]
0x14000bec7  lea     rcx, [rbp+arg_10]
0x14000becb  mov     [rsp+80h+var_50], rcx
0x14000bed0  lea     rcx, [rbp+arg_18]
0x14000bed4  mov     [rsp+80h+var_58], rcx
0x14000bed9  mov     rcx, cs:WdfDriverGlobals
0x14000bee0  mov     [rsp+80h+var_60], 40h ; '@'
0x14000bee9  call    _guard_dispatch_icall
0x14000beee  mov     ebx, eax
0x14000bef0  test    eax, eax
0x14000bef2  js      loc_14000BF7F
0x14000bef8  movups  xmm0, xmmword ptr [rdi]
0x14000befb  mov     rax, [rbp+arg_10]
0x14000beff  xor     ecx, ecx; PerformanceFrequency
0x14000bf01  movups  xmmword ptr [rax], xmm0
0x14000bf04  movups  xmm1, xmmword ptr [rdi+10h]
0x14000bf08  movups  xmmword ptr [rax+10h], xmm1
0x14000bf0c  movups  xmm0, xmmword ptr [rdi+20h]
0x14000bf10  movups  xmmword ptr [rax+20h], xmm0
0x14000bf14  movups  xmm1, xmmword ptr [rdi+30h]
0x14000bf18  movups  xmmword ptr [rax+30h], xmm1
0x14000bf1c  call    cs:__imp_KeQueryPerformanceCounter
0x14000bf23  nop     dword ptr [rax+rax+00h]
0x14000bf28  mov     rcx, [rbp+arg_10]
0x14000bf2c  mov     [rcx], rax
0x14000bf2f  mov     rax, cs:WdfFunctions_01015
0x14000bf36  mov     r8, [rbp+arg_18]
0x14000bf3a  mov     rdx, [r14+0C8h]
0x14000bf41  mov     rcx, cs:WdfDriverGlobals
0x14000bf48  mov     rax, [rax+78h]
0x14000bf4c  call    _guard_dispatch_icall
0x14000bf51  mov     ebx, eax
0x14000bf53  test    eax, eax
0x14000bf55  jns     short loc_14000BF77
0x14000bf57  mov     rax, cs:WdfFunctions_01015
0x14000bf5e  mov     rdx, [rbp+arg_18]
0x14000bf62  mov     rcx, cs:WdfDriverGlobals
0x14000bf69  mov     rax, [rax+680h]
0x14000bf70  call    _guard_dispatch_icall
0x14000bf75  jmp     short loc_14000BF7F
0x14000bf77  mov     rcx, rsi
0x14000bf7a  call    Bus_ProcessAtResponses
0x14000bf7f  lea     r11, [rsp+80h+var_s0]
0x14000bf87  mov     eax, ebx
0x14000bf89  mov     rbx, [r11+20h]
0x14000bf8d  mov     rsi, [r11+28h]
0x14000bf91  mov     rsp, r11
0x14000bf94  pop     r14
0x14000bf96  pop     rdi
0x14000bf97  pop     rbp
0x14000bf98  retn
```
