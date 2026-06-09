# SecureChannel_SendRequestSynchronously

- ea: `0x14001c178`
- end: `0x14001c4cc`
- name: `SecureChannel_SendRequestSynchronously`
- size: `852`
- prototype: ``
- caller_count: `46`
- callee_count: `11`
- tags: ``

## callers

- `0x140005be4`
- `0x14000d26c`
- `0x14000d4d4`
- `0x14000f690`
- `0x14001a214`
- `0x14001be40`
- `0x14001c040`
- `0x14001f87c`
- `0x140023678`
- `0x14002b19c`
- `0x14002c1dc`
- `0x1400389a4`
- `0x1400390ac`
- `0x1400392d4`
- `0x140039674`
- `0x14003978c`
- `0x14003f594`
- `0x14003f744`
- `0x14003f8e0`
- `0x14003faa0`
- `0x14003fbb8`
- `0x14003fcd8`
- `0x14003fe0c`
- `0x1400462f0`
- `0x14004649c`
- `0x1400465d4`
- `0x1400466f0`
- `0x140046814`
- `0x140046a90`
- `0x140046be4`
- `0x140047040`
- `0x1400471b8`
- `0x1400472e8`
- `0x14004743c`
- `0x140047508`
- `0x140047718`
- `0x140049de0`
- `0x140049ec8`
- `0x14004bb04`
- `0x14004dbec`
- `0x140056908`
- `0x1400766d8`
- `0x14007720c`
- `0x14007db68`
- `0x140080624`
- `0x140083aa8`

## callees

- `0x140010d40`
- `0x1400110e0`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001c178`
- `0x14001c4d4`
- `0x14001c554`
- `0x1400569f0`
- `0x140056acc`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001c427`
- `ntoskrnl!KeBugCheckEx` at `0x14001c427`
- `ntoskrnl!EtwActivityIdControl` at `0x14001c221`
- `ntoskrnl!EtwActivityIdControl` at `0x14001c221`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c2a4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001c2a4`
- `HAL!KeQueryPerformanceCounter` at `0x14001c260`
- `HAL!KeQueryPerformanceCounter` at `0x14001c342`
- `HAL!KeQueryPerformanceCounter` at `0x14001c260`
- `HAL!KeQueryPerformanceCounter` at `0x14001c342`

## pseudocode

```c
__int64 __fastcall SecureChannel_SendRequestSynchronously(__int64 a1, GUID *a2, int a3, __int64 a4, int a5)
{
  int v6; // edx
  signed __int32 v9; // ecx
  unsigned int Data1; // eax
  __int64 v11; // rax
  char v12; // r12
  LARGE_INTEGER PerformanceCounter; // rbx
  int v14; // edx
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // r14d
  unsigned int v19; // edi
  LARGE_INTEGER v20; // rax
  int v21; // ecx
  __int64 v23; // rcx
  __int128 *BugCheckParameter4; // [rsp+20h] [rbp-71h]
  char v25; // [rsp+50h] [rbp-41h]
  unsigned int v26; // [rsp+54h] [rbp-3Dh]
  signed __int32 v27; // [rsp+58h] [rbp-39h]
  __int128 v28; // [rsp+80h] [rbp-11h] BYREF
  int v29; // [rsp+90h] [rbp-1h]
  int v30; // [rsp+94h] [rbp+3h]
  GUID v31; // [rsp+98h] [rbp+7h] BYREF

  v29 = 0;
  v6 = 0;
  v25 = 0;
  v28 = 0;
  v31 = 0;
  v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 1u);
  Data1 = a2[2].Data1;
  a2[1].Data1 = v9;
  v27 = v9;
  v26 = Data1;
  v31 = GUID_NULL;
  if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 2) != 0 )
  {
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v11 )
    {
      EtwActivityIdControl(3u, a2);
      v9 = v27;
    }
    v31 = *a2;
    if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 2) != 0 )
      McTemplateK0qqqq_EtwWriteTransfer(v9, v6, (_DWORD)a2, a2[2].Data1, a3, a5, v9);
    v12 = 1;
    PerformanceCounter = KeQueryPerformanceCounter(0);
  }
  else
  {
    PerformanceCounter.QuadPart = 0;
    v12 = 0;
  }
  *(_QWORD *)&v28 = 1;
  v30 = 0;
  *((_QWORD *)&v28 + 1) = a2;
  v29 = a3;
  if ( KeGetCurrentIrql() == 2 )
  {
    v23 = *(_QWORD *)(a1 + 8);
    if ( !*(_QWORD *)(v23 + 8) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(v23 + 16), v14, 19, 13, (__int64)WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids);
      }
      KeBugCheckEx(0x144u, 4u, 0, 2u, 3u);
    }
    Controller_LowerAndTrackIrql(*(_QWORD *)(v23 + 8));
    v25 = 1;
  }
  BugCheckParameter4 = &v28;
  v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64))(WdfFunctions_01033 + 3592))(
          WdfDriverGlobals,
          *(_QWORD *)a1,
          0,
          6078464);
  if ( v25 )
    Controller_RaiseAndTrackIrql(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL));
  if ( v18 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
      v15,
      19,
      14,
      (__int64)WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids,
      v18);
  }
  else
  {
    if ( !a5 )
      goto LABEL_14;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DP(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL), v15, v16, v17, (unsigned int)&v28, a5, 0);
    v18 = -1073741306;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = v26;
    WPP_RECORDER_SF_Ld(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL), v15, v16, v17, (_DWORD)BugCheckParameter4, v26, v18);
    goto LABEL_15;
  }
LABEL_14:
  v19 = v26;
LABEL_15:
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 24));
  if ( v12 )
  {
    v20 = KeQueryPerformanceCounter(0);
    if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 2) != 0 )
      McTemplateK0qqx_EtwWriteTransfer(
        v21,
        1000000000 * (v20.QuadPart - PerformanceCounter.QuadPart) % *(_QWORD *)(a1 + 16),
        (unsigned int)&v31,
        v19,
        v27,
        1000000000 * (v20.QuadPart - PerformanceCounter.QuadPart) / *(_QWORD *)(a1 + 16));
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14001c178  mov     [rsp-8+arg_10], rbx
0x14001c17d  push    rbp
0x14001c17e  push    rsi
0x14001c17f  push    rdi
0x14001c180  push    r12
0x14001c182  push    r13
0x14001c184  push    r14
0x14001c186  push    r15
0x14001c188  lea     rbp, [rsp-1Fh]
0x14001c18d  sub     rsp, 0B0h
0x14001c194  mov     rax, cs:__security_cookie
0x14001c19b  xor     rax, rsp
0x14001c19e  mov     [rbp+4Fh+var_38], rax
0x14001c1a2  xor     eax, eax
0x14001c1a4  xorps   xmm0, xmm0
0x14001c1a7  mov     rdi, rdx
0x14001c1aa  mov     [rbp+4Fh+var_50], eax
0x14001c1ad  xor     edx, edx
0x14001c1af  mov     [rbp+4Fh+var_68], eax
0x14001c1b2  mov     rsi, rcx
0x14001c1b5  mov     [rbp+4Fh+var_80], rdx
0x14001c1b9  lea     ecx, [rax+1]
0x14001c1bc  mov     [rbp+4Fh+var_90], dl
0x14001c1bf  mov     r13, r9
0x14001c1c2  mov     r14d, r8d
0x14001c1c5  movups  [rbp+4Fh+var_60], xmm0
0x14001c1c9  movups  [rbp+4Fh+var_78], xmm0
0x14001c1cd  movups  [rbp+4Fh+var_48], xmm0
0x14001c1d1  lock xadd [rsi+18h], ecx
0x14001c1d6  mov     eax, [rdi+20h]
0x14001c1d9  mov     r15d, [rbp+4Fh+arg_20]
0x14001c1dd  mov     [rdi+10h], ecx
0x14001c1e0  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 2
0x14001c1e7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001c1ee  mov     [rbp+4Fh+var_88], ecx
0x14001c1f1  mov     [rbp+4Fh+var_8C], eax
0x14001c1f4  movdqu  [rbp+4Fh+var_48], xmm0
0x14001c1f9  jz      loc_14001C3C8
0x14001c1ff  mov     rax, [rdi]
0x14001c202  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14001c209  jnz     short loc_14001C216
0x14001c20b  mov     rax, [rdi+8]
0x14001c20f  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14001c216  test    rax, rax
0x14001c219  jnz     short loc_14001C230
0x14001c21b  mov     rdx, rdi; ActivityId
0x14001c21e  lea     ecx, [rax+3]; ControlCode
0x14001c221  call    cs:__imp_EtwActivityIdControl
0x14001c228  nop     dword ptr [rax+rax+00h]
0x14001c22d  mov     ecx, [rbp+4Fh+var_88]
0x14001c230  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 2
0x14001c237  movups  xmm0, xmmword ptr [rdi]
0x14001c23a  movdqu  [rbp+4Fh+var_48], xmm0
0x14001c23f  jz      short loc_14001C25B
0x14001c241  mov     r9d, [rdi+20h]
0x14001c245  mov     r8, rdi
0x14001c248  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x14001c24c  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14001c251  mov     dword ptr [rsp+0E0h+BugCheckParameter4], r14d
0x14001c256  call    McTemplateK0qqqq_EtwWriteTransfer
0x14001c25b  xor     ecx, ecx; PerformanceFrequency
0x14001c25d  mov     r12b, 1
0x14001c260  call    cs:__imp_KeQueryPerformanceCounter
0x14001c267  nop     dword ptr [rax+rax+00h]
0x14001c26c  mov     rbx, rax
0x14001c26f  xor     edx, edx
0x14001c271  mov     qword ptr [rbp+4Fh+var_60], 1
0x14001c279  mov     [rbp+4Fh+var_4C], edx
0x14001c27c  mov     qword ptr [rbp+4Fh+var_60+8], rdi
0x14001c280  mov     [rbp+4Fh+var_50], r14d
0x14001c284  test    r13, r13
0x14001c287  jz      loc_14001C3D3
0x14001c28d  mov     qword ptr [rbp+4Fh+var_78], 1
0x14001c295  lea     rdi, [rbp+4Fh+var_78]
0x14001c299  mov     [rbp+4Fh+var_64], edx
0x14001c29c  mov     qword ptr [rbp+4Fh+var_78+8], r13
0x14001c2a0  mov     [rbp+4Fh+var_68], r15d
0x14001c2a4  call    cs:__imp_KeGetCurrentIrql
0x14001c2ab  nop     dword ptr [rax+rax+00h]
0x14001c2b0  cmp     al, 2
0x14001c2b2  jz      loc_14001C3AA
0x14001c2b8  mov     rax, cs:WdfFunctions_01033
0x14001c2bf  lea     rcx, [rbp+4Fh+var_80]
0x14001c2c3  mov     rdx, [rsi]
0x14001c2c6  xor     r8d, r8d
0x14001c2c9  mov     [rsp+0E0h+var_A8], rcx
0x14001c2ce  mov     r9d, 5CC000h
0x14001c2d4  mov     [rsp+0E0h+var_B0], r8
0x14001c2d9  lea     rcx, [rbp+4Fh+var_60]
0x14001c2dd  mov     rax, [rax+0E08h]
0x14001c2e4  mov     [rsp+0E0h+var_B8], rdi
0x14001c2e9  mov     [rsp+0E0h+BugCheckParameter4], rcx
0x14001c2ee  mov     rcx, cs:WdfDriverGlobals
0x14001c2f5  call    _guard_dispatch_icall
0x14001c2fa  cmp     [rbp+4Fh+var_90], 0
0x14001c2fe  mov     r14d, eax
0x14001c301  jz      short loc_14001C310
0x14001c303  mov     rcx, [rsi+8]
0x14001c307  mov     rcx, [rcx+8]
0x14001c30b  call    Controller_RaiseAndTrackIrql
0x14001c310  test    r14d, r14d
0x14001c313  js      loc_14001C434
0x14001c319  mov     rax, [rbp+4Fh+var_80]
0x14001c31d  mov     ecx, 0FFFFFFFFh
0x14001c322  cmp     rax, rcx
0x14001c325  ja      loc_14001C474
0x14001c32b  cmp     eax, r15d
0x14001c32e  jnz     loc_14001C474
0x14001c334  mov     edi, [rbp+4Fh+var_8C]
0x14001c337  lock dec dword ptr [rsi+18h]
0x14001c33b  test    r12b, r12b
0x14001c33e  jz      short loc_14001C37F
0x14001c340  xor     ecx, ecx; PerformanceFrequency
0x14001c342  call    cs:__imp_KeQueryPerformanceCounter
0x14001c349  nop     dword ptr [rax+rax+00h]
0x14001c34e  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 2
0x14001c355  jz      short loc_14001C37F
0x14001c357  sub     rax, rbx
0x14001c35a  lea     r8, [rbp+4Fh+var_48]
0x14001c35e  imul    rax, 3B9ACA00h
0x14001c365  mov     r9d, edi
0x14001c368  cqo
0x14001c36a  idiv    qword ptr [rsi+10h]
0x14001c36e  mov     [rsp+0E0h+var_B8], rax
0x14001c373  mov     eax, [rbp+4Fh+var_88]
0x14001c376  mov     dword ptr [rsp+0E0h+BugCheckParameter4], eax
0x14001c37a  call    McTemplateK0qqx_EtwWriteTransfer
0x14001c37f  mov     eax, r14d
0x14001c382  mov     rcx, [rbp+4Fh+var_38]
0x14001c386  xor     rcx, rsp; StackCookie
0x14001c389  call    __security_check_cookie
0x14001c38e  mov     rbx, [rsp+0E0h+arg_10]
0x14001c396  add     rsp, 0B0h
0x14001c39d  pop     r15
0x14001c39f  pop     r14
0x14001c3a1  pop     r13
0x14001c3a3  pop     r12
0x14001c3a5  pop     rdi
0x14001c3a6  pop     rsi
0x14001c3a7  pop     rbp
0x14001c3a8  retn
0x14001c3aa  mov     rcx, [rsi+8]
0x14001c3ae  mov     rax, [rcx+8]
0x14001c3b2  test    rax, rax
0x14001c3b5  jz      short loc_14001C3DB
0x14001c3b7  mov     rcx, rax
0x14001c3ba  call    Controller_LowerAndTrackIrql
0x14001c3bf  mov     [rbp+4Fh+var_90], 1
0x14001c3c3  jmp     loc_14001C2B8
0x14001c3c8  mov     rbx, rdx
0x14001c3cb  mov     r12b, dl
0x14001c3ce  jmp     loc_14001C271
0x14001c3d3  mov     rdi, rdx
0x14001c3d6  jmp     loc_14001C2A4
0x14001c3db  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001c3e2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001c3e9  jz      short loc_14001C40C
0x14001c3eb  mov     rcx, [rcx+10h]
0x14001c3ef  lea     rax, WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids
0x14001c3f6  mov     r9d, 0Dh
0x14001c3fc  mov     [rsp+0E0h+BugCheckParameter4], rax
0x14001c401  mov     dl, 2
0x14001c403  lea     r8d, [r9+6]
0x14001c407  call    WPP_RECORDER_SF_
0x14001c40c  mov     r9d, 2; BugCheckParameter3
0x14001c412  mov     [rsp+0E0h+BugCheckParameter4], 3; BugCheckParameter4
0x14001c41b  xor     r8d, r8d; BugCheckParameter2
0x14001c41e  mov     ecx, 144h; BugCheckCode
0x14001c423  lea     edx, [r9+2]; BugCheckParameter1
0x14001c427  call    cs:__imp_KeBugCheckEx
0x14001c434  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001c43b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001c442  jz      loc_14001C334
0x14001c448  mov     rcx, [rsi+8]
0x14001c44c  lea     rax, WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids
0x14001c453  mov     r9d, 0Eh
0x14001c459  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x14001c45e  mov     dl, 2
0x14001c460  mov     [rsp+0E0h+BugCheckParameter4], rax
0x14001c465  mov     rcx, [rcx+10h]
0x14001c469  lea     r8d, [r9+5]
0x14001c46d  call    WPP_RECORDER_SF_d
0x14001c472  jmp     short loc_14001C4A1
0x14001c474  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001c47b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001c482  jz      short loc_14001C49B
0x14001c484  mov     rcx, [rsi+8]
0x14001c488  mov     [rsp+0E0h+var_B0], rax
0x14001c48d  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14001c492  mov     rcx, [rcx+10h]
0x14001c496  call    WPP_RECORDER_SF_DP
0x14001c49b  mov     r14d, 0C0000206h
0x14001c4a1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001c4a8  jz      loc_14001C334
0x14001c4ae  mov     rcx, [rsi+8]
0x14001c4b2  mov     edi, [rbp+4Fh+var_8C]
0x14001c4b5  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x14001c4ba  mov     dword ptr [rsp+0E0h+var_B8], edi
0x14001c4be  mov     rcx, [rcx+10h]
0x14001c4c2  call    WPP_RECORDER_SF_Ld
0x14001c4c7  jmp     loc_14001C337
```
