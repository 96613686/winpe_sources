# WPP_SF_ssSS

- ea: `0x1800251f8`
- end: `0x1800252f4`
- name: `WPP_SF_ssSS`
- size: `252`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800204b0`

## callees

- `0x1800251f8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800252e0`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800252e0`

## string_xrefs

- `0x1800252b3`: `VGidsSimulatorWriteProperties`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssSS(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        const wchar_t *a6,
        const wchar_t *a7)
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
           0x23u,
           a4,
           v16,
           "VGidsSimulatorWriteProperties",
           30,
           v13,
           v10,
           v7,
           v12,
           0);
}

```

## disassembly

```asm
0x1800251f8  mov     [rsp+arg_0], rbx
0x1800251fd  push    rdi
0x1800251fe  sub     rsp, 70h
0x180025202  mov     r8, [rsp+78h+arg_30]
0x18002520a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002520e  xor     edi, edi
0x180025210  mov     r11, rcx
0x180025213  mov     ecx, 0Ah
0x180025218  test    r8, r8
0x18002521b  jz      short loc_180025234
0x18002521d  mov     rdx, rax
0x180025220  inc     rdx
0x180025223  cmp     [r8+rdx*2], di
0x180025228  jnz     short loc_180025220
0x18002522a  lea     r10, ds:2[rdx*2]
0x180025232  jmp     short loc_180025237
0x180025234  mov     r10, rcx
0x180025237  mov     rdx, [rsp+78h+arg_28]
0x18002523f  lea     rbx, aNull_0; "NULL"
0x180025246  test    r8, r8
0x180025249  cmovz   r8, rbx
0x18002524d  test    rdx, rdx
0x180025250  jz      short loc_180025269
0x180025252  mov     rcx, rax
0x180025255  inc     rcx
0x180025258  cmp     [rdx+rcx*2], di
0x18002525c  jnz     short loc_180025255
0x18002525e  lea     rcx, ds:2[rcx*2]
0x180025266  test    rdx, rdx
0x180025269  cmovz   rdx, rbx
0x18002526d  test    r9, r9
0x180025270  jz      short loc_180025280
0x180025272  inc     rax
0x180025275  cmp     [r9+rax], dil
0x180025279  jnz     short loc_180025272
0x18002527b  inc     rax
0x18002527e  jmp     short loc_180025285
0x180025280  mov     eax, 5
0x180025285  mov     [rsp+78h+var_18], rdi
0x18002528a  lea     rbx, aNull; "NULL"
0x180025291  mov     [rsp+78h+var_20], r10
0x180025296  test    r9, r9
0x180025299  mov     [rsp+78h+var_28], r8
0x18002529e  lea     r8, WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids; MessageGuid
0x1800252a5  mov     [rsp+78h+var_30], rcx
0x1800252aa  cmovz   r9, rbx
0x1800252ae  mov     [rsp+78h+var_38], rdx
0x1800252b3  lea     rcx, aVgidssimulator_6; "VGidsSimulatorWriteProperties"
0x1800252ba  mov     [rsp+78h+var_40], 1Eh
0x1800252c3  mov     ebx, 23h ; '#'
0x1800252c8  mov     [rsp+78h+var_48], rcx
0x1800252cd  mov     rcx, r11; LoggerHandle
0x1800252d0  mov     [rsp+78h+var_50], rax
0x1800252d5  mov     [rsp+78h+var_58], r9
0x1800252da  mov     r9d, ebx; MessageNumber
0x1800252dd  lea     edx, [rbx+8]; MessageFlags
0x1800252e0  call    cs:__imp_TraceMessage
0x1800252e6  mov     rbx, [rsp+78h+arg_0]
0x1800252ee  add     rsp, 70h
0x1800252f2  pop     rdi
0x1800252f3  retn
```
