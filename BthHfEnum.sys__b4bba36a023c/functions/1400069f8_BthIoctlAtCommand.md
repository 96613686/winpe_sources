# BthIoctlAtCommand

- ea: `0x1400069f8`
- end: `0x140006c8d`
- name: `BthIoctlAtCommand`
- size: `661`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400069f8`
- `0x14000aac0`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BthIoctlAtCommand(__int64 a1, __int64 a2)
{
  int v4; // r15d
  __int64 v5; // r12
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rax
  int *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+50h] BYREF
  unsigned int *v19; // [rsp+98h] [rbp+58h] BYREF

  v19 = 0;
  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned int **, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a2,
         56,
         &v19,
         &v17);
  if ( v4 >= 0 )
  {
    v5 = 0;
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           a1,
           off_1400220B0);
    v7 = *v19;
    if ( *v19 == 11 )
    {
      v18 = v19[1];
      _InterlockedExchange((volatile __int32 *)(v6 + 268), 0x7FFFFFFF);
      v8 = *(_QWORD *)(v6 + 320);
      *(_DWORD *)(v6 + 276) = v18;
      if ( !v8 )
        goto LABEL_12;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             v8,
             off_140022100)
         + 8;
      v10 = (int *)&v18;
      v11 = 2228255;
    }
    else if ( v7 == 10 )
    {
      v18 = v19[1];
      _InterlockedExchange((volatile __int32 *)(v6 + 272), 0x7FFFFFFF);
      v12 = *(_QWORD *)(v6 + 320);
      *(_DWORD *)(v6 + 280) = v18;
      if ( !v12 )
        goto LABEL_12;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             v12,
             off_140022100)
         + 12;
      v10 = (int *)&v18;
      v11 = 2228263;
    }
    else
    {
      if ( v7 != 7 )
        goto LABEL_12;
      v13 = *(_QWORD *)(v6 + 320);
      *(_DWORD *)(v6 + 284) = 1;
      if ( !v13 )
        goto LABEL_12;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             v13,
             off_140022100)
         + 4;
      v10 = (int *)(v6 + 284);
      v11 = 2228283;
    }
    WdfIoQueueFindAndCompleteStatusIoctlRequest(*(_QWORD *)(v6 + 152), *(_QWORD *)(v6 + 320), v11, v10, v9);
LABEL_12:
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1072))(WdfDriverGlobals, a1);
    while ( 1 )
    {
      v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01015 + 1080))(
              WdfDriverGlobals,
              a1,
              v5,
              1);
      v5 = v14;
      if ( !v14 )
        break;
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              v14,
              off_1400220D8);
      if ( *(_QWORD *)(v15 + 88) )
        (*(void (__fastcall **)(_QWORD, _QWORD, unsigned int *, __int64))(v15 + 88))(
          *(_QWORD *)(v15 + 64),
          v7,
          v19,
          v17);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1088))(WdfDriverGlobals, a1);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
    WdfDriverGlobals,
    a2,
    (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400069f8  mov     [rsp-38h+arg_0], rbx
0x1400069fd  push    rbp
0x1400069fe  push    rsi
0x1400069ff  push    rdi
0x140006a00  push    r12
0x140006a02  push    r13
0x140006a04  push    r14
0x140006a06  push    r15
0x140006a08  mov     rbp, rsp
0x140006a0b  sub     rsp, 40h
0x140006a0f  mov     rax, cs:WdfFunctions_01015
0x140006a16  lea     r9, [rbp+arg_18]
0x140006a1a  mov     rsi, rcx
0x140006a1d  mov     [rbp+arg_18], 0
0x140006a25  lea     rcx, [rbp+var_10]
0x140006a29  mov     [rbp+var_10], 0
0x140006a31  mov     [rsp+40h+var_20], rcx
0x140006a36  mov     r8d, 38h ; '8'
0x140006a3c  mov     rax, [rax+868h]
0x140006a43  mov     r13, rdx
0x140006a46  mov     rcx, cs:WdfDriverGlobals
0x140006a4d  call    _guard_dispatch_icall
0x140006a52  mov     r15d, eax
0x140006a55  test    eax, eax
0x140006a57  js      loc_140006C51
0x140006a5d  mov     rcx, cs:WdfFunctions_01015
0x140006a64  mov     rdx, rsi
0x140006a67  mov     r8, cs:off_1400220B0
0x140006a6e  xor     r12d, r12d
0x140006a71  mov     rax, [rcx+650h]
0x140006a78  mov     rcx, cs:WdfDriverGlobals
0x140006a7f  call    _guard_dispatch_icall
0x140006a84  mov     rcx, [rbp+arg_18]
0x140006a88  mov     rbx, rax
0x140006a8b  mov     edi, [rcx]
0x140006a8d  mov     eax, [rcx+4]
0x140006a90  cmp     edi, 0Bh
0x140006a93  jnz     short loc_140006AF0
0x140006a95  mov     [rbp+arg_10], eax
0x140006a98  mov     eax, 7FFFFFFFh
0x140006a9d  xchg    eax, [rbx+10Ch]
0x140006aa3  mov     rdx, [rbx+140h]
0x140006aaa  mov     ecx, [rbp+arg_10]
0x140006aad  mov     [rbx+114h], ecx
0x140006ab3  test    rdx, rdx
0x140006ab6  jz      loc_140006BB2
0x140006abc  mov     rax, cs:WdfFunctions_01015
0x140006ac3  mov     r8, cs:off_140022100
0x140006aca  mov     rcx, cs:WdfDriverGlobals
0x140006ad1  mov     rax, [rax+650h]
0x140006ad8  call    _guard_dispatch_icall
0x140006add  add     rax, 8
0x140006ae1  lea     r9, [rbp+arg_10]
0x140006ae5  mov     r8d, 22001Fh
0x140006aeb  jmp     loc_140006B9A
0x140006af0  cmp     edi, 0Ah
0x140006af3  jnz     short loc_140006B4D
0x140006af5  mov     [rbp+arg_10], eax
0x140006af8  mov     eax, 7FFFFFFFh
0x140006afd  xchg    eax, [rbx+110h]
0x140006b03  mov     rdx, [rbx+140h]
0x140006b0a  mov     eax, [rbp+arg_10]
0x140006b0d  mov     [rbx+118h], eax
0x140006b13  test    rdx, rdx
0x140006b16  jz      loc_140006BB2
0x140006b1c  mov     rax, cs:WdfFunctions_01015
0x140006b23  mov     r8, cs:off_140022100
0x140006b2a  mov     rcx, cs:WdfDriverGlobals
0x140006b31  mov     rax, [rax+650h]
0x140006b38  call    _guard_dispatch_icall
0x140006b3d  add     rax, 0Ch
0x140006b41  lea     r9, [rbp+arg_10]
0x140006b45  mov     r8d, 220027h
0x140006b4b  jmp     short loc_140006B9A
0x140006b4d  cmp     edi, 7
0x140006b50  jnz     short loc_140006BB2
0x140006b52  mov     rdx, [rbx+140h]
0x140006b59  lea     r14, [rbx+11Ch]
0x140006b60  mov     dword ptr [r14], 1
0x140006b67  test    rdx, rdx
0x140006b6a  jz      short loc_140006BB2
0x140006b6c  mov     rax, cs:WdfFunctions_01015
0x140006b73  mov     r8, cs:off_140022100
0x140006b7a  mov     rcx, cs:WdfDriverGlobals
0x140006b81  mov     rax, [rax+650h]
0x140006b88  call    _guard_dispatch_icall
0x140006b8d  add     rax, 4
0x140006b91  mov     r9, r14
0x140006b94  mov     r8d, 22003Bh
0x140006b9a  mov     rdx, [rbx+140h]
0x140006ba1  mov     rcx, [rbx+98h]
0x140006ba8  mov     [rsp+40h+var_20], rax
0x140006bad  call    WdfIoQueueFindAndCompleteStatusIoctlRequest
0x140006bb2  mov     rax, cs:WdfFunctions_01015
0x140006bb9  mov     rdx, rsi
0x140006bbc  mov     rcx, cs:WdfDriverGlobals
0x140006bc3  mov     rax, [rax+430h]
0x140006bca  call    _guard_dispatch_icall
0x140006bcf  mov     rax, cs:WdfFunctions_01015
0x140006bd6  mov     r9d, 1
0x140006bdc  mov     rcx, cs:WdfDriverGlobals
0x140006be3  mov     r8, r12
0x140006be6  mov     rdx, rsi
0x140006be9  mov     rax, [rax+438h]
0x140006bf0  call    _guard_dispatch_icall
0x140006bf5  mov     rcx, cs:WdfDriverGlobals
0x140006bfc  mov     r12, rax
0x140006bff  test    rax, rax
0x140006c02  mov     rax, cs:WdfFunctions_01015
0x140006c09  jz      short loc_140006C42
0x140006c0b  mov     r8, cs:off_1400220D8
0x140006c12  mov     rdx, r12
0x140006c15  mov     rax, [rax+650h]
0x140006c1c  call    _guard_dispatch_icall
0x140006c21  mov     r10, [rax+58h]
0x140006c25  test    r10, r10
0x140006c28  jz      short loc_140006BCF
0x140006c2a  mov     rcx, [rax+40h]
0x140006c2e  mov     edx, edi
0x140006c30  mov     r9, [rbp+var_10]
0x140006c34  mov     rax, r10
0x140006c37  mov     r8, [rbp+arg_18]
0x140006c3b  call    _guard_dispatch_icall
0x140006c40  jmp     short loc_140006BCF
0x140006c42  mov     rax, [rax+440h]
0x140006c49  mov     rdx, rsi
0x140006c4c  call    _guard_dispatch_icall
0x140006c51  mov     rax, cs:WdfFunctions_01015
0x140006c58  mov     r8d, r15d
0x140006c5b  mov     rcx, cs:WdfDriverGlobals
0x140006c62  mov     rdx, r13
0x140006c65  mov     rax, [rax+838h]
0x140006c6c  call    _guard_dispatch_icall
0x140006c71  mov     rbx, [rsp+40h+arg_0]
0x140006c79  mov     eax, r15d
0x140006c7c  add     rsp, 40h
0x140006c80  pop     r15
0x140006c82  pop     r14
0x140006c84  pop     r13
0x140006c86  pop     r12
0x140006c88  pop     rdi
0x140006c89  pop     rsi
0x140006c8a  pop     rbp
0x140006c8b  retn
```
