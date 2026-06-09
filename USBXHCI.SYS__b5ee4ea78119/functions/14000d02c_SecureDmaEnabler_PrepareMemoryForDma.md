# SecureDmaEnabler_PrepareMemoryForDma

- ea: `0x14000d02c`
- end: `0x14000d186`
- name: `SecureDmaEnabler_PrepareMemoryForDma`
- size: `346`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140006e40`
- `0x14000cce0`
- `0x14000ea20`

## callees

- `0x14000d02c`
- `0x140010d40`
- `0x1400110e0`
- `0x14001ac48`
- `0x14001ad0c`

## import_xrefs

- `ntoskrnl!VslCreateSecureSection` at `0x14000d0d3`
- `ntoskrnl!VslCreateSecureSection` at `0x14000d0d3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d098`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d098`

## pseudocode

```c
__int64 __fastcall SecureDmaEnabler_PrepareMemoryForDma(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4,
        int a5,
        _OWORD *a6,
        __int64 a7)
{
  bool v7; // zf
  _QWORD *v9; // rsi
  int v10; // edi
  char v11; // bp
  _QWORD *v12; // rbx
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  v7 = *a2 == 0;
  v9 = a2;
  v17 = 0;
  if ( v7 )
  {
    v11 = 0;
    v12 = (_QWORD *)(a1 + 8);
    if ( KeGetCurrentIrql() == 2 )
    {
      Controller_LowerAndTrackIrql(*v12);
      v11 = 1;
    }
    v10 = VslCreateSecureSection(&v17, *(_QWORD *)(*v12 + 1072LL), v9, 4, 1);
    if ( v11 )
      Controller_RaiseAndTrackIrql(*v12);
    if ( v10 >= 0 )
    {
      v14 = (__int64)a6;
      v15 = a7;
      *a6 = 0;
      *(_OWORD *)(v14 + 16) = 0;
      *(_DWORD *)(v14 + 8) = a4;
      *(_DWORD *)v15 = 1;
      *(_QWORD *)(v15 + 16) = *((unsigned int *)v9 + 11);
      *(_DWORD *)(v15 + 24) = *(_DWORD *)(v14 + 8);
      *(_DWORD *)(v14 + 12) = a5;
      *(_QWORD *)(v14 + 16) = v17;
      *(_DWORD *)v14 = 1;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*v12 + 72LL),
        v13,
        18,
        17,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
        v10);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        (_DWORD)a2,
        18,
        16,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids);
    }
    return (unsigned int)-1073741637;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000d02c  mov     r11, rsp
0x14000d02f  mov     [r11+8], rbx
0x14000d033  mov     [r11+18h], rbp
0x14000d037  push    rsi
0x14000d038  push    rdi
0x14000d039  push    r14
0x14000d03b  sub     rsp, 30h
0x14000d03f  cmp     qword ptr [rdx], 0
0x14000d043  mov     r14d, r9d
0x14000d046  mov     rsi, rdx
0x14000d049  mov     qword ptr [r11+10h], 0
0x14000d051  jz      short loc_14000D091
0x14000d053  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d05a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d061  jz      short loc_14000D087
0x14000d063  mov     rcx, [rcx+8]
0x14000d067  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x14000d06e  mov     r9d, 10h
0x14000d074  mov     [r11-28h], rax
0x14000d078  mov     dl, 2
0x14000d07a  mov     rcx, [rcx+48h]
0x14000d07e  lea     r8d, [r9+2]
0x14000d082  call    WPP_RECORDER_SF_
0x14000d087  mov     edi, 0C00000BBh
0x14000d08c  jmp     loc_14000D170
0x14000d091  xor     bpl, bpl
0x14000d094  lea     rbx, [rcx+8]
0x14000d098  call    cs:__imp_KeGetCurrentIrql
0x14000d09f  nop     dword ptr [rax+rax+00h]
0x14000d0a4  cmp     al, 2
0x14000d0a6  jnz     short loc_14000D0B3
0x14000d0a8  mov     rcx, [rbx]
0x14000d0ab  call    Controller_LowerAndTrackIrql
0x14000d0b0  mov     bpl, 1
0x14000d0b3  mov     rdx, [rbx]
0x14000d0b6  lea     rcx, [rsp+48h+arg_8]
0x14000d0bb  mov     r9d, 4
0x14000d0c1  mov     dword ptr [rsp+48h+var_28], 1
0x14000d0c9  mov     r8, rsi
0x14000d0cc  mov     rdx, [rdx+430h]
0x14000d0d3  call    cs:__imp_VslCreateSecureSection
0x14000d0da  nop     dword ptr [rax+rax+00h]
0x14000d0df  mov     edi, eax
0x14000d0e1  test    bpl, bpl
0x14000d0e4  jz      short loc_14000D0EE
0x14000d0e6  mov     rcx, [rbx]
0x14000d0e9  call    Controller_RaiseAndTrackIrql
0x14000d0ee  test    edi, edi
0x14000d0f0  jns     short loc_14000D12C
0x14000d0f2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d0f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d100  jz      short loc_14000D170
0x14000d102  mov     rcx, [rbx]
0x14000d105  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x14000d10c  mov     r9d, 11h
0x14000d112  mov     [rsp+48h+var_20], edi
0x14000d116  mov     dl, 2
0x14000d118  mov     [rsp+48h+var_28], rax
0x14000d11d  mov     rcx, [rcx+48h]
0x14000d121  lea     r8d, [r9+1]
0x14000d125  call    WPP_RECORDER_SF_d
0x14000d12a  jmp     short loc_14000D170
0x14000d12c  mov     rdx, [rsp+48h+arg_28]
0x14000d131  xorps   xmm0, xmm0
0x14000d134  mov     rcx, [rsp+48h+arg_30]
0x14000d13c  movups  xmmword ptr [rdx], xmm0
0x14000d13f  movups  xmmword ptr [rdx+10h], xmm0
0x14000d143  mov     [rdx+8], r14d
0x14000d147  mov     dword ptr [rcx], 1
0x14000d14d  mov     eax, [rsi+2Ch]
0x14000d150  mov     [rcx+10h], rax
0x14000d154  mov     eax, [rdx+8]
0x14000d157  mov     [rcx+18h], eax
0x14000d15a  mov     eax, [rsp+48h+arg_20]
0x14000d15e  mov     [rdx+0Ch], eax
0x14000d161  mov     rax, [rsp+48h+arg_8]
0x14000d166  mov     [rdx+10h], rax
0x14000d16a  mov     dword ptr [rdx], 1
0x14000d170  mov     rbx, [rsp+48h+arg_0]
0x14000d175  mov     eax, edi
0x14000d177  mov     rbp, [rsp+48h+arg_10]
0x14000d17c  add     rsp, 30h
0x14000d180  pop     r14
0x14000d182  pop     rdi
0x14000d183  pop     rsi
0x14000d184  retn
```
