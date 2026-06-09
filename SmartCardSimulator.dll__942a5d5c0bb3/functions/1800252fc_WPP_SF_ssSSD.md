# WPP_SF_ssSSD

- ea: `0x1800252fc`
- end: `0x18002541d`
- name: `WPP_SF_ssSSD`
- size: `289`
- prototype: `ULONG(TRACEHANDLE LoggerHandle, __int64, __int64, const char *, int, const wchar_t *, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020f0c`

## callees

- `0x1800252fc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180025402`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180025402`

## string_xrefs

- `0x1800253d5`: `GidsSimulatorManagerImpl::SimulatorCreate`

## pseudocode

```c
ULONG WPP_SF_ssSSD(
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
           0x27u,
           a4,
           v16,
           "GidsSimulatorManagerImpl::SimulatorCreate",
           42,
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
0x1800252fc  mov     [rsp+arg_0], rbx
0x180025301  mov     [rsp+arg_8], rsi
0x180025306  push    rdi
0x180025307  sub     rsp, 80h
0x18002530e  mov     r8, [rsp+88h+arg_30]
0x180025316  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002531a  xor     esi, esi
0x18002531c  mov     r11, rcx
0x18002531f  mov     ecx, 0Ah
0x180025324  test    r8, r8
0x180025327  jz      short loc_180025340
0x180025329  mov     rdx, rax
0x18002532c  inc     rdx
0x18002532f  cmp     [r8+rdx*2], si
0x180025334  jnz     short loc_18002532C
0x180025336  lea     r10, ds:2[rdx*2]
0x18002533e  jmp     short loc_180025343
0x180025340  mov     r10, rcx
0x180025343  mov     rdx, [rsp+88h+arg_28]
0x18002534b  lea     rbx, aNull_0; "NULL"
0x180025352  test    r8, r8
0x180025355  cmovz   r8, rbx
0x180025359  test    rdx, rdx
0x18002535c  jz      short loc_180025375
0x18002535e  mov     rcx, rax
0x180025361  inc     rcx
0x180025364  cmp     [rdx+rcx*2], si
0x180025368  jnz     short loc_180025361
0x18002536a  lea     rcx, ds:2[rcx*2]
0x180025372  test    rdx, rdx
0x180025375  cmovz   rdx, rbx
0x180025379  test    r9, r9
0x18002537c  jz      short loc_18002538C
0x18002537e  inc     rax
0x180025381  cmp     [r9+rax], sil
0x180025385  jnz     short loc_18002537E
0x180025387  inc     rax
0x18002538a  jmp     short loc_180025391
0x18002538c  mov     eax, 5
0x180025391  mov     [rsp+88h+var_18], rsi
0x180025396  lea     rbx, aNull; "NULL"
0x18002539d  mov     [rsp+88h+var_20], 4
0x1800253a6  test    r9, r9
0x1800253a9  mov     edi, 27h ; '''
0x1800253ae  cmovz   r9, rbx
0x1800253b2  lea     rbx, [rsp+88h+arg_38]
0x1800253ba  mov     [rsp+88h+var_28], rbx
0x1800253bf  mov     [rsp+88h+var_30], r10
0x1800253c4  mov     [rsp+88h+var_38], r8
0x1800253c9  lea     r8, WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids; MessageGuid
0x1800253d0  mov     [rsp+88h+var_40], rcx
0x1800253d5  lea     rcx, aGidssimulatorm; "GidsSimulatorManagerImpl::SimulatorCrea"...
0x1800253dc  mov     [rsp+88h+var_48], rdx
0x1800253e1  lea     edx, [rdi+4]; MessageFlags
0x1800253e4  mov     [rsp+88h+var_50], 2Ah ; '*'
0x1800253ed  mov     [rsp+88h+var_58], rcx
0x1800253f2  mov     rcx, r11; LoggerHandle
0x1800253f5  mov     [rsp+88h+var_60], rax
0x1800253fa  mov     [rsp+88h+var_68], r9
0x1800253ff  mov     r9d, edi; MessageNumber
0x180025402  call    cs:__imp_TraceMessage
0x180025408  lea     r11, [rsp+88h+var_8]
0x180025410  mov     rbx, [r11+10h]
0x180025414  mov     rsi, [r11+18h]
0x180025418  mov     rsp, r11
0x18002541b  pop     rdi
0x18002541c  retn
```
