# UsbDevice_DeviceResetCompletion

- ea: `0x140037320`
- end: `0x140037542`
- name: `UsbDevice_DeviceResetCompletion`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c264`
- `0x1400246f0`
- `0x140024f24`
- `0x140029840`
- `0x14002b2c0`
- `0x140037320`
- `0x14004fb08`
- `0x14004fd18`
- `0x1400599b0`

## string_xrefs

- `0x1400374f2`: `Reset Device Command failed`

## pseudocode

```c
__int64 __fastcall UsbDevice_DeviceResetCompletion(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v4; // rbx
  char v6; // r14
  int v8; // edx
  __int64 i; // rdi
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 j; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-68h]

  v4 = *(_QWORD *)(a1 + 48);
  v6 = a2;
  if ( a2 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(unsigned __int8 *)(v4 + 143);
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_dq(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
        v8,
        12,
        83,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(v4 + 143),
        *(_QWORD *)v4);
    }
    for ( i = 2; i != 32; ++i )
    {
      v10 = *(_QWORD *)(v4 + 8 * i + 176);
      if ( v10 )
        Endpoint_Disable(v10, 0);
    }
LABEL_19:
    *(_DWORD *)(v4 + 160) = 3;
    v16 = *(_QWORD *)(v4 + 432);
    *(_QWORD *)(v4 + 432) = 0;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             v16,
             0);
  }
  if ( *(_BYTE *)(a1 + 60) == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = *(unsigned __int8 *)(a1 + 61);
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_dq(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
        v11,
        12,
        84,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(a1 + 61),
        *(_QWORD *)v4);
    }
    if ( !(unsigned int)UsbDevice_GetEndpointState(v4, 1)
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_dLL(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
        *(unsigned __int8 *)(a1 + 61),
        v12,
        v13,
        v18,
        *(_BYTE *)(a1 + 61),
        *(_BYTE *)(a1 + 60),
        v6);
    }
    for ( j = 2; j != 32; ++j )
    {
      v15 = *(_QWORD *)(v4 + 8 * j + 176);
      if ( v15 )
        Endpoint_Disable(v15, 0);
    }
    goto LABEL_19;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dqLL(*(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL), *(unsigned __int8 *)(a1 + 61), a3, a4);
  Controller_HwVerifierBreakIfEnabled(
    *(_QWORD *)(v4 + 8),
    *(_QWORD *)v4,
    0,
    0x200000,
    (__int64)"Reset Device Command failed",
    a1 + 24,
    a3);
  return Controller_ReportFatalError(*(_QWORD *)(v4 + 8), 2, 4121, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x140037320  push    rbx
0x140037322  push    rbp
0x140037323  push    rsi
0x140037324  push    rdi
0x140037325  push    r14
0x140037327  push    r15
0x140037329  sub     rsp, 58h
0x14003732d  mov     rbx, [rcx+30h]
0x140037331  mov     ebp, 3
0x140037336  mov     r15, r8
0x140037339  mov     r14d, edx
0x14003733c  mov     rsi, rcx
0x14003733f  cmp     edx, ebp
0x140037341  jnz     short loc_1400373B0
0x140037343  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003734a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140037351  jz      short loc_140037389
0x140037353  mov     rax, [rbx]
0x140037356  lea     r9d, [rbp+50h]
0x14003735a  movzx   edx, byte ptr [rbx+8Fh]
0x140037361  lea     r8d, [rbp+9]
0x140037365  mov     rcx, [rbx+8]
0x140037369  mov     [rsp+88h+var_58], rax
0x14003736e  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x140037375  mov     dword ptr [rsp+88h+var_60], edx
0x140037379  mov     dl, 4
0x14003737b  mov     [rsp+88h+var_68], rax
0x140037380  mov     rcx, [rcx+48h]
0x140037384  call    WPP_RECORDER_SF_dq
0x140037389  mov     edi, 2
0x14003738e  mov     rcx, [rbx+rdi*8+0B0h]
0x140037396  test    rcx, rcx
0x140037399  jz      short loc_1400373A2
0x14003739b  xor     edx, edx
0x14003739d  call    Endpoint_Disable
0x1400373a2  inc     rdi
0x1400373a5  cmp     rdi, 20h ; ' '
0x1400373a9  jnz     short loc_14003738E
0x1400373ab  jmp     loc_14003745F
0x1400373b0  movzx   eax, byte ptr [rcx+3Ch]
0x1400373b4  cmp     al, 1
0x1400373b6  jnz     loc_14003749E
0x1400373bc  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400373c3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400373ca  jz      short loc_140037401
0x1400373cc  movzx   edx, byte ptr [rcx+3Dh]
0x1400373d0  mov     r9d, 54h ; 'T'
0x1400373d6  mov     rax, [rbx]
0x1400373d9  mov     rcx, [rbx+8]
0x1400373dd  mov     [rsp+88h+var_58], rax
0x1400373e2  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x1400373e9  mov     dword ptr [rsp+88h+var_60], edx
0x1400373ed  lea     r8d, [r9-48h]
0x1400373f1  mov     dl, 4
0x1400373f3  mov     [rsp+88h+var_68], rax
0x1400373f8  mov     rcx, [rcx+48h]
0x1400373fc  call    WPP_RECORDER_SF_dq
0x140037401  mov     edx, 1
0x140037406  mov     rcx, rbx
0x140037409  call    UsbDevice_GetEndpointState
0x14003740e  test    eax, eax
0x140037410  jnz     short loc_14003743D
0x140037412  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140037419  jz      short loc_14003743D
0x14003741b  mov     rcx, [rbx+8]
0x14003741f  movzx   eax, byte ptr [rsi+3Ch]
0x140037423  movzx   edx, byte ptr [rsi+3Dh]
0x140037427  mov     [rsp+88h+var_50], r14d
0x14003742c  mov     rcx, [rcx+48h]
0x140037430  mov     dword ptr [rsp+88h+var_58], eax
0x140037434  mov     dword ptr [rsp+88h+var_60], edx
0x140037438  call    WPP_RECORDER_SF_dLL
0x14003743d  mov     edi, 2
0x140037442  mov     rcx, [rbx+rdi*8+0B0h]
0x14003744a  test    rcx, rcx
0x14003744d  jz      short loc_140037456
0x14003744f  xor     edx, edx
0x140037451  call    Endpoint_Disable
0x140037456  inc     rdi
0x140037459  cmp     rdi, 20h ; ' '
0x14003745d  jnz     short loc_140037442
0x14003745f  mov     eax, 0A0h
0x140037464  mov     rcx, rbx
0x140037467  xor     r8d, r8d
0x14003746a  mov     [rbx+rax], ebp
0x14003746d  mov     rdx, [rbx+1B0h]
0x140037474  mov     qword ptr [rbx+1B0h], 0
0x14003747f  mov     rax, cs:WdfFunctions_01033
0x140037486  mov     rcx, cs:WdfDriverGlobals
0x14003748d  mov     rax, [rax+838h]
0x140037494  call    _guard_dispatch_icall
0x140037499  jmp     loc_140037534
0x14003749e  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400374a5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400374ac  jz      short loc_1400374D4
0x1400374ae  movzx   edx, byte ptr [rcx+3Dh]
0x1400374b2  mov     rcx, [rbx+8]
0x1400374b6  mov     [rsp+88h+var_48], r14d
0x1400374bb  mov     [rsp+88h+var_50], eax
0x1400374bf  mov     rax, [rbx]
0x1400374c2  mov     rcx, [rcx+48h]
0x1400374c6  mov     [rsp+88h+var_58], rax
0x1400374cb  mov     dword ptr [rsp+88h+var_60], edx
0x1400374cf  call    WPP_RECORDER_SF_dqLL
0x1400374d4  mov     rdx, [rbx]
0x1400374d7  lea     rax, [rsi+18h]
0x1400374db  mov     rcx, [rbx+8]
0x1400374df  mov     r9d, 200000h
0x1400374e5  mov     [rsp+88h+var_58], r15
0x1400374ea  xor     r8d, r8d
0x1400374ed  mov     [rsp+88h+var_60], rax
0x1400374f2  lea     rax, aResetDeviceCom; "Reset Device Command failed"
0x1400374f9  mov     [rsp+88h+var_68], rax
0x1400374fe  call    Controller_HwVerifierBreakIfEnabled
0x140037503  mov     rcx, [rbx+8]
0x140037507  xor     r9d, r9d
0x14003750a  mov     [rsp+88h+var_58], 0
0x140037513  mov     r8d, 1019h
0x140037519  mov     [rsp+88h+var_60], 0
0x140037522  mov     [rsp+88h+var_68], 0
0x14003752b  lea     edx, [r9+2]
0x14003752f  call    Controller_ReportFatalError
0x140037534  add     rsp, 58h
0x140037538  pop     r15
0x14003753a  pop     r14
0x14003753c  pop     rdi
0x14003753d  pop     rsi
0x14003753e  pop     rbp
0x14003753f  pop     rbx
0x140037540  retn
```
