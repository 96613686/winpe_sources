# AipExpandEnvironment(void * *)

- ea: `0x180009540`
- end: `0x180009649`
- name: `?AipExpandEnvironment@@YAKPEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d8fc`

## callees

- `0x180009540`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800095e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800095e4`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000959e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000960e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000959e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000960e`
- `ntdll!RtlDestroyEnvironment` at `0x18000961b`
- `ntdll!RtlDestroyEnvironment` at `0x18000961b`
- `ntdll!RtlCreateEnvironmentEx` at `0x18000962a`
- `ntdll!RtlCreateEnvironmentEx` at `0x18000962a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800095b0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800095b0`

## pseudocode

```c
__int64 __fastcall AipExpandEnvironment(void **a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  bool v7; // zf
  NTSTATUS Environment; // eax
  HLOCAL v9; // rbx
  ULONG v10; // edi
  __int64 v12; // rsi
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  v2 = (__int64)*a1;
  v3 = 0;
  v4 = v2;
  v13 = 0;
  do
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(v4 + 2 * v5) );
    v6 = v5 + 1;
    v3 += v6;
    v7 = *(_WORD *)(v4 + 2 * v6) == 0;
    v4 += 2 * v6;
  }
  while ( !v7 );
  Environment = RtlExpandEnvironmentStrings(v2, v2, v3 + 1, 0, 0, &v13);
  if ( Environment == -1073741789 )
  {
    v12 = v13;
    v9 = LocalAlloc(0x40u, 2 * v13);
    if ( !v9 )
    {
      v10 = 8;
      goto LABEL_8;
    }
    Environment = RtlExpandEnvironmentStrings(*a1, *a1, v3 + 1, v9, v12, &v13);
    if ( Environment >= 0 )
    {
      RtlDestroyEnvironment((PWSTR)*a1);
      Environment = RtlCreateEnvironmentEx(v9, a1, 0);
      if ( Environment >= 0 )
      {
        v10 = 0;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = RtlNtStatusToDosErrorNoTeb(Environment);
LABEL_8:
  LocalFree(v9);
  return v10;
}

```

## disassembly

```asm
0x180009540  mov     [rsp+arg_10], rbx
0x180009545  push    rbp
0x180009546  push    rdi
0x180009547  push    r14
0x180009549  sub     rsp, 30h
0x18000954d  xor     ebp, ebp
0x18000954f  mov     r14, rcx
0x180009552  mov     rcx, [rcx]
0x180009555  mov     edi, ebp
0x180009557  mov     rdx, rcx
0x18000955a  mov     [rsp+48h+arg_0], rbp
0x18000955f  nop
0x180009560  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009567  inc     rax
0x18000956a  cmp     [rdx+rax*2], bp
0x18000956e  jnz     short loc_180009567
0x180009570  inc     rax
0x180009573  add     rdi, rax
0x180009576  cmp     [rdx+rax*2], bp
0x18000957a  lea     rdx, [rdx+rax*2]
0x18000957e  jnz     short loc_180009560
0x180009580  lea     rax, [rsp+48h+arg_0]
0x180009585  mov     [rsp+48h+arg_8], rsi
0x18000958a  mov     [rsp+48h+var_20], rax
0x18000958f  lea     r8, [rdi+1]
0x180009593  xor     r9d, r9d
0x180009596  mov     [rsp+48h+var_28], rbp
0x18000959b  mov     rdx, rcx
0x18000959e  call    cs:__imp_RtlExpandEnvironmentStrings
0x1800095a4  cmp     eax, 0C0000023h
0x1800095a9  jz      short loc_1800095D6
0x1800095ab  mov     rbx, rbp
0x1800095ae  mov     ecx, eax; Status
0x1800095b0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800095b6  mov     edi, eax
0x1800095b8  mov     rcx, rbx; hMem
0x1800095bb  call    cs:__imp_LocalFree
0x1800095c1  mov     rsi, [rsp+48h+arg_8]
0x1800095c6  mov     eax, edi
0x1800095c8  mov     rbx, [rsp+48h+arg_10]
0x1800095cd  add     rsp, 30h
0x1800095d1  pop     r14
0x1800095d3  pop     rdi
0x1800095d4  pop     rbp
0x1800095d5  retn
0x1800095d6  mov     rsi, [rsp+48h+arg_0]
0x1800095db  mov     ecx, 40h ; '@'; uFlags
0x1800095e0  lea     rdx, [rsi+rsi]; uBytes
0x1800095e4  call    cs:__imp_LocalAlloc
0x1800095ea  mov     rbx, rax
0x1800095ed  test    rax, rax
0x1800095f0  jz      short loc_18000963F
0x1800095f2  mov     rcx, [r14]
0x1800095f5  lea     rax, [rsp+48h+arg_0]
0x1800095fa  mov     [rsp+48h+var_20], rax
0x1800095ff  lea     r8, [rdi+1]
0x180009603  mov     rdx, rcx
0x180009606  mov     [rsp+48h+var_28], rsi
0x18000960b  mov     r9, rbx
0x18000960e  call    cs:__imp_RtlExpandEnvironmentStrings
0x180009614  test    eax, eax
0x180009616  js      short loc_1800095AE
0x180009618  mov     rcx, [r14]; Environment
0x18000961b  call    cs:__imp_RtlDestroyEnvironment
0x180009621  xor     r8d, r8d
0x180009624  mov     rdx, r14
0x180009627  mov     rcx, rbx
0x18000962a  call    cs:__imp_RtlCreateEnvironmentEx
0x180009630  test    eax, eax
0x180009632  js      loc_1800095AE
0x180009638  mov     edi, ebp
0x18000963a  jmp     loc_1800095B8
0x18000963f  mov     edi, 8
0x180009644  jmp     loc_1800095B8
```
