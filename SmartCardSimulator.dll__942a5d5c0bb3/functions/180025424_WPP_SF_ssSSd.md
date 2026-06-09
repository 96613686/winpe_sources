# WPP_SF_ssSSd

- ea: `0x180025424`
- end: `0x180025545`
- name: `WPP_SF_ssSSd`
- size: `289`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800203c8`

## callees

- `0x180025424`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002552a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002552a`

## string_xrefs

- `0x1800254fd`: `VGidsSimulatorCreate`

## pseudocode

```c
ULONG WPP_SF_ssSSd(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        const wchar_t *a6,
        const wchar_t *a7,
        ...)
{
  const wchar_t *v7; // r8
  __int64 v8; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r10
  const wchar_t *v13; // rdx
  bool v14; // zf
  __int64 v15; // rcx
  __int64 v16; // rax
  va_list va; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va, a7);
  v7 = a7;
  v8 = -1;
  v10 = 10;
  if ( a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a7[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v13 = a6;
  if ( !a7 )
    v7 = L"NULL";
  v14 = a6 == 0;
  if ( a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a6[v15] );
    v10 = 2 * v15 + 2;
    v14 = a6 == 0;
  }
  if ( v14 )
    v13 = L"NULL";
  if ( a4 )
  {
    do
      ++v8;
    while ( a4[v8] );
    v16 = v8 + 1;
  }
  else
  {
    v16 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids,
           0x1Fu,
           a4,
           v16,
           "VGidsSimulatorCreate",
           21,
           v13,
           v10,
           v7,
           v12,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x180025424  mov     [rsp+arg_0], rbx
0x180025429  mov     [rsp+arg_8], rsi
0x18002542e  push    rdi
0x18002542f  sub     rsp, 80h
0x180025436  mov     r8, [rsp+88h+arg_30]
0x18002543e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025442  xor     esi, esi
0x180025444  mov     r11, rcx
0x180025447  mov     ecx, 0Ah
0x18002544c  test    r8, r8
0x18002544f  jz      short loc_180025468
0x180025451  mov     rdx, rax
0x180025454  inc     rdx
0x180025457  cmp     [r8+rdx*2], si
0x18002545c  jnz     short loc_180025454
0x18002545e  lea     r10, ds:2[rdx*2]
0x180025466  jmp     short loc_18002546B
0x180025468  mov     r10, rcx
0x18002546b  mov     rdx, [rsp+88h+arg_28]
0x180025473  lea     rbx, aNull_0; "NULL"
0x18002547a  test    r8, r8
0x18002547d  cmovz   r8, rbx
0x180025481  test    rdx, rdx
0x180025484  jz      short loc_18002549D
0x180025486  mov     rcx, rax
0x180025489  inc     rcx
0x18002548c  cmp     [rdx+rcx*2], si
0x180025490  jnz     short loc_180025489
0x180025492  lea     rcx, ds:2[rcx*2]
0x18002549a  test    rdx, rdx
0x18002549d  cmovz   rdx, rbx
0x1800254a1  test    r9, r9
0x1800254a4  jz      short loc_1800254B4
0x1800254a6  inc     rax
0x1800254a9  cmp     [r9+rax], sil
0x1800254ad  jnz     short loc_1800254A6
0x1800254af  inc     rax
0x1800254b2  jmp     short loc_1800254B9
0x1800254b4  mov     eax, 5
0x1800254b9  mov     [rsp+88h+var_18], rsi
0x1800254be  lea     rbx, aNull; "NULL"
0x1800254c5  mov     [rsp+88h+var_20], 4
0x1800254ce  test    r9, r9
0x1800254d1  mov     edi, 1Fh
0x1800254d6  cmovz   r9, rbx
0x1800254da  lea     rbx, [rsp+88h+arg_38]
0x1800254e2  mov     [rsp+88h+var_28], rbx
0x1800254e7  mov     [rsp+88h+var_30], r10
0x1800254ec  mov     [rsp+88h+var_38], r8
0x1800254f1  lea     r8, WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids; MessageGuid
0x1800254f8  mov     [rsp+88h+var_40], rcx
0x1800254fd  lea     rcx, aVgidssimulator_3; "VGidsSimulatorCreate"
0x180025504  mov     [rsp+88h+var_48], rdx
0x180025509  lea     edx, [rdi+0Ch]; MessageFlags
0x18002550c  mov     [rsp+88h+var_50], 15h
0x180025515  mov     [rsp+88h+var_58], rcx
0x18002551a  mov     rcx, r11; LoggerHandle
0x18002551d  mov     [rsp+88h+var_60], rax
0x180025522  mov     [rsp+88h+var_68], r9
0x180025527  mov     r9d, edi; MessageNumber
0x18002552a  call    cs:__imp_TraceMessage
0x180025530  lea     r11, [rsp+88h+var_8]
0x180025538  mov     rbx, [r11+10h]
0x18002553c  mov     rsi, [r11+18h]
0x180025540  mov     rsp, r11
0x180025543  pop     rdi
0x180025544  retn
```
