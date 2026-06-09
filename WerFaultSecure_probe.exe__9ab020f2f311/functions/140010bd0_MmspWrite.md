# MmspWrite

- ea: `0x140010bd0`
- end: `0x140010e0d`
- name: `MmspWrite`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000e598`
- `0x1400106cc`
- `0x140010bd0`
- `0x14001130c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140011632`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140011632`

## pseudocode

```c
__int64 __fastcall MmspWrite(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  unsigned int v6; // r13d
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r14
  __int64 result; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdx
  int v15; // r8d
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned __int64 *v18; // rax
  unsigned __int64 v19; // r14
  unsigned __int64 v20; // [rsp+38h] [rbp-60h]
  unsigned __int64 *v21; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+10h]
  unsigned int v23; // [rsp+B0h] [rbp+18h]
  unsigned __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v23 = a3;
  v22 = a2;
  v6 = a3;
  v7 = 0;
  v8 = 0;
  v20 = 0;
  v21 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = *(_QWORD *)(a1 + 24);
  v24 = v9;
  v10 = v9;
  while ( v6 )
  {
    result = MmspMapRange(a1, &v21, &v24, v6);
    if ( (int)result < 0 )
      return result;
    v12 = *v21;
    v13 = *v21 + v21[2] - 1;
    v14 = v10 + v6 - 1;
    if ( (v10 < *v21 || v10 > v13) && (v14 < v12 || v14 > v13) && (v12 < v10 || v12 > v14) && (v13 < v10 || v13 > v14) )
    {
      v15 = 0;
    }
    else
    {
      v15 = 1;
      v7 = v10;
      if ( v10 <= v12 )
        v7 = *v21;
      v16 = v10 + v6;
      if ( v14 >= v13 )
        v16 = *v21 + v21[2];
      v8 = v16 - 1;
      v20 = v8;
    }
    if ( !v15 || v7 != v9 || v7 < v12 || v7 > v8 )
      return 2147942887LL;
    v24 = v8 - v7;
    v17 = v8 - v7 + 1;
    if ( v17 < v24 )
      return 2147942934LL;
    v24 = v17;
    if ( HIDWORD(v17) )
      return 2147942934LL;
    if ( !(_DWORD)v17 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)v17 > v6 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)v17 > v23 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = v21;
    if ( v7 < *v21 )
      return 2147942934LL;
    v19 = v7 - *v21;
    if ( v19 >= *(_QWORD *)(a1 + 16) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = v21;
    }
    memcpy_0((void *)(v19 + v18[1]), (const void *)(v22 + v23 - (unsigned __int64)v6), (unsigned int)v17);
    v6 -= v17;
    a3 = v23;
    if ( v6 >= v23 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      a3 = v23;
    }
    v9 += (unsigned int)v17;
    v24 = v9;
    v10 = v9;
    if ( a4 )
      *a4 += v17;
    v8 = v20;
  }
  *(_QWORD *)(a1 + 24) = v9;
  if ( __PAIR64__(*(_DWORD *)(a1 + 28), v9) > *(_QWORD *)(a1 + 32) )
    *(_QWORD *)(a1 + 32) = v10;
  if ( a4 && a3 != *a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x140010bd0  mov     rax, rsp
0x140010bd3  mov     [rax+18h], r8d
0x140010bd7  mov     [rax+10h], rdx
0x140010bdb  push    rbx
0x140010bdc  push    rsi
0x140010bdd  push    rdi
0x140010bde  push    r12
0x140010be0  push    r13
0x140010be2  push    r14
0x140010be4  push    r15
0x140010be6  sub     rsp, 60h
0x140010bea  mov     r15, r9
0x140010bed  mov     rsi, rcx
0x140010bf0  mov     r13d, r8d
0x140010bf3  xor     r12d, r12d
0x140010bf6  xor     ebx, ebx
0x140010bf8  mov     [rsp+98h+var_60], rbx
0x140010bfd  mov     [rax+8], rbx
0x140010c01  test    r9, r9
0x140010c04  jz      short loc_140010C09
0x140010c06  mov     [r9], ebx
0x140010c09  mov     rdi, [rcx+18h]
0x140010c0d  mov     [rsp+98h+arg_18], rdi
0x140010c15  mov     r14, rdi
0x140010c18  test    r13d, r13d
0x140010c1b  jz      loc_140010DD3
0x140010c21  mov     r9d, r13d
0x140010c24  lea     r8, [rsp+98h+arg_18]
0x140010c2c  lea     rdx, [rsp+98h+arg_0]
0x140010c34  mov     rcx, rsi
0x140010c37  call    MmspMapRange
0x140010c3c  test    eax, eax
0x140010c3e  js      loc_140010DFD
0x140010c44  mov     rax, [rsp+98h+arg_0]
0x140010c4c  mov     rcx, [rax]
0x140010c4f  mov     r10, [rax+10h]
0x140010c53  add     r10, rcx
0x140010c56  lea     rax, [r10-1]
0x140010c5a  mov     r9d, r13d
0x140010c5d  add     r9, r14
0x140010c60  lea     rdx, [r9-1]
0x140010c64  cmp     r14, rcx
0x140010c67  jb      short loc_140010C6E
0x140010c69  cmp     r14, rax
0x140010c6c  jbe     short loc_140010C8C
0x140010c6e  cmp     rdx, rcx
0x140010c71  jb      short loc_140010C78
0x140010c73  cmp     rdx, rax
0x140010c76  jbe     short loc_140010C8C
0x140010c78  cmp     rcx, r14
0x140010c7b  jb      short loc_140010C82
0x140010c7d  cmp     rcx, rdx
0x140010c80  jbe     short loc_140010C8C
0x140010c82  cmp     rax, r14
0x140010c85  jb      short loc_140010CB0
0x140010c87  cmp     rax, rdx
0x140010c8a  ja      short loc_140010CB0
0x140010c8c  mov     r8d, 1
0x140010c92  mov     r12, r14
0x140010c95  cmp     r14, rcx
0x140010c98  cmovbe  r12, rcx
0x140010c9c  mov     rbx, r9
0x140010c9f  cmp     rdx, rax
0x140010ca2  cmovnb  rbx, r10
0x140010ca6  dec     rbx
0x140010ca9  mov     [rsp+98h+var_60], rbx
0x140010cae  jmp     short loc_140010CB3
0x140010cb0  xor     r8d, r8d
0x140010cb3  test    r8d, r8d
0x140010cb6  jz      loc_140010DCC
0x140010cbc  cmp     r12, rdi
0x140010cbf  jnz     loc_140010DCC
0x140010cc5  cmp     r12, rcx
0x140010cc8  jb      loc_140010DCC
0x140010cce  cmp     r12, rbx
0x140010cd1  ja      loc_140010DCC
0x140010cd7  mov     rax, rbx
0x140010cda  sub     rax, r12
0x140010cdd  mov     [rsp+98h+arg_18], rax
0x140010ce5  lea     rbx, [rax+1]
0x140010ce9  cmp     rbx, rax
0x140010cec  jb      loc_140010DC5
0x140010cf2  mov     [rsp+98h+arg_18], rbx
0x140010cfa  mov     rax, rbx
0x140010cfd  shr     rax, 20h
0x140010d01  test    eax, eax
0x140010d03  jnz     loc_140010DC5
0x140010d09  test    ebx, ebx
0x140010d0b  jnz     short loc_140010D12
0x140010d0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010d12  cmp     ebx, r13d
0x140010d15  jbe     short loc_140010D1C
0x140010d17  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010d1c  cmp     ebx, [rsp+98h+arg_10]
0x140010d23  jbe     short loc_140010D2A
0x140010d25  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010d2a  mov     rax, [rsp+98h+arg_0]
0x140010d32  cmp     r12, [rax]
0x140010d35  jb      loc_140010DC5
0x140010d3b  mov     r14, r12
0x140010d3e  sub     r14, [rax]
0x140010d41  cmp     r14, [rsi+10h]
0x140010d45  jb      short loc_140010D54
0x140010d47  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010d4c  mov     rax, [rsp+98h+arg_0]
0x140010d54  mov     rcx, [rax+8]
0x140010d58  add     rcx, r14; void *
0x140010d5b  mov     [rsp+98h+var_40], rcx
0x140010d60  mov     r14d, ebx
0x140010d63  mov     edx, [rsp+98h+arg_10]
0x140010d6a  mov     eax, r13d
0x140010d6d  sub     rdx, rax
0x140010d70  add     rdx, [rsp+98h+arg_8]; Src
0x140010d78  mov     r8d, ebx; Size
0x140010d7b  call    memcpy_0
0x140010d80  nop
0x140010d81  sub     r13d, ebx
0x140010d84  mov     r8d, [rsp+98h+arg_10]
0x140010d8c  cmp     r13d, r8d
0x140010d8f  jb      short loc_140010D9E
0x140010d91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010d96  mov     r8d, [rsp+98h+arg_10]
0x140010d9e  add     rdi, r14
0x140010da1  mov     [rsp+98h+arg_18], rdi
0x140010da9  mov     r14, rdi
0x140010dac  test    r15, r15
0x140010daf  jz      short loc_140010DB4
0x140010db1  add     [r15], ebx
0x140010db4  mov     rbx, [rsp+98h+var_60]
0x140010db9  jmp     loc_140010C18
0x140010dbe  mov     eax, 800705AFh
0x140010dc3  jmp     short loc_140010DFD
0x140010dc5  mov     eax, 80070216h
0x140010dca  jmp     short loc_140010DFD
0x140010dcc  mov     eax, 800701E7h
0x140010dd1  jmp     short loc_140010DFD
0x140010dd3  mov     [rsi+18h], rdi
0x140010dd7  mov     eax, [rsi+1Ch]
0x140010dda  cmp     eax, [rsi+24h]
0x140010ddd  jb      short loc_140010DEC
0x140010ddf  ja      short loc_140010DE8
0x140010de1  mov     eax, edi
0x140010de3  cmp     eax, [rsi+20h]
0x140010de6  jbe     short loc_140010DEC
0x140010de8  mov     [rsi+20h], r14
0x140010dec  test    r15, r15
0x140010def  jz      short loc_140010DFB
0x140010df1  cmp     r8d, [r15]
0x140010df4  jz      short loc_140010DFB
0x140010df6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140010dfb  xor     eax, eax
0x140010dfd  add     rsp, 60h
0x140010e01  pop     r15
0x140010e03  pop     r14
0x140010e05  pop     r13
0x140010e07  pop     r12
0x140010e09  pop     rdi
0x140010e0a  pop     rsi
0x140010e0b  pop     rbx
0x140010e0c  retn
0x1400115b2  push    rbp
0x1400115b4  sub     rsp, 20h
0x1400115b8  mov     rbp, rdx
0x1400115bb  mov     rax, [rcx]
0x1400115be  mov     edx, [rax]
0x1400115c0  mov     eax, [rbp+0B8h]
0x1400115c6  mov     [rbp+40h], rax
0x1400115ca  mov     [rbp+50h], rcx
0x1400115ce  mov     [rbp+20h], edx
0x1400115d1  mov     rax, [rbp+50h]
0x1400115d5  mov     rcx, [rax]
0x1400115d8  mov     [rbp+30h], rcx
0x1400115dc  mov     qword ptr [rbp+48h], 0
0x1400115e4  mov     eax, [rbp+20h]
0x1400115e7  cmp     eax, 0C0000006h
0x1400115ec  jz      short loc_1400115F8
0x1400115ee  mov     eax, [rbp+20h]
0x1400115f1  cmp     eax, 0C0000005h
0x1400115f6  jnz     short loc_14001164F
0x1400115f8  mov     rax, [rbp+30h]
0x1400115fc  cmp     qword ptr [rax+20h], 1
0x140011601  jnz     short loc_14001164F
0x140011603  mov     rax, [rbp+30h]
0x140011607  mov     rcx, [rbp+58h]; lpAddress
0x14001160b  cmp     [rax+28h], rcx
0x14001160f  jb      short loc_14001164F
0x140011611  mov     rdx, [rbp+40h]
0x140011615  add     rdx, rcx
0x140011618  mov     rax, [rbp+30h]
0x14001161c  cmp     [rax+28h], rdx
0x140011620  jnb     short loc_14001164F
0x140011622  mov     r9d, 4; flProtect
0x140011628  mov     r8d, 1000h; flAllocationType
0x14001162e  mov     rdx, [rbp+40h]; dwSize
0x140011632  call    cs:__imp_VirtualAlloc
0x140011638  mov     [rbp+48h], rax
0x14001163c  mov     rax, [rbp+48h]
0x140011640  neg     rax
0x140011643  sbb     ecx, ecx
0x140011645  and     ecx, 0FFFFFFFEh
0x140011648  inc     ecx
0x14001164a  mov     [rbp+28h], ecx
0x14001164d  jmp     short loc_140011656
0x14001164f  mov     dword ptr [rbp+28h], 0
0x140011656  mov     eax, [rbp+28h]
0x140011659  add     rsp, 20h
0x14001165d  pop     rbp
0x14001165e  retn
```
