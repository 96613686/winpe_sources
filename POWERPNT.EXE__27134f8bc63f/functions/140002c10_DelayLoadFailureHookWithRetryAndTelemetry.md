# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x140002c10`
- end: `0x140002d81`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140001540`
- `0x140002ac0`
- `0x140002b84`
- `0x140002c10`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x140002ca5`
- `KERNEL32!LoadLibraryExA` at `0x140002ca5`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x140002d32`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x140002d75`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x140002d32`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x140002d75`

## pseudocode

```c
HMODULE __fastcall DelayLoadFailureHookWithRetryAndTelemetry(int a1, struct DelayLoadInfo *a2)
{
  unsigned int v3; // ebx
  HMODULE Library; // rsi
  const char **p_szDll; // rdi
  const char *v6; // r8
  const char *v8; // r8
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  if ( a1 != 3 )
    return 0;
  ++g_retryDelayLoadStatistics;
  v3 = 1;
  while ( 1 )
  {
    if ( g_retryDelayLoadTestHook )
      g_retryDelayLoadTestHook(v3, 50, 0);
    if ( _pfnDliNotifyHook2 )
    {
      Library = (HMODULE)_pfnDliNotifyHook2(1u, a2);
      p_szDll = &a2->szDll;
      if ( Library )
        break;
    }
    p_szDll = &a2->szDll;
    if ( !*a2->szDll )
      __fastfail(5u);
    Library = LoadLibraryExA(a2->szDll, 0, 0x1000u);
    if ( Library )
      break;
    std::chrono::steady_clock::now(&v10);
    v9 = v10;
    if ( v3 )
    {
      if ( v10 >= 0x7FFFFFFFFFFFFFFFLL - 10000000LL * v3 )
        v9 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v9 = 10000000LL * v3 + v10;
    }
    std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(&v9);
    if ( ++v3 > 0x32 )
    {
      ++dword_140005728;
      v6 = &byte_140003677;
      if ( *p_szDll )
        v6 = *p_szDll;
      strncpy_s(Destination, 0x64u, v6, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  ++dword_140005724;
  v8 = &byte_140003677;
  if ( *p_szDll )
    v8 = *p_szDll;
  strncpy_s(byte_14000572C, 0x64u, v8, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x140002c10  mov     [rsp+arg_0], rbx
0x140002c15  push    rbp
0x140002c16  push    rsi
0x140002c17  push    rdi
0x140002c18  push    r14
0x140002c1a  push    r15
0x140002c1c  sub     rsp, 20h
0x140002c20  mov     rbp, rdx
0x140002c23  cmp     ecx, 3
0x140002c26  jnz     loc_140002D38
0x140002c2c  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x140002c32  mov     ebx, 1
0x140002c37  mov     r15, 7FFFFFFFFFFFFFFFh
0x140002c41  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x140002c48  test    rax, rax
0x140002c4b  jz      short loc_140002C5D
0x140002c4d  xor     r8d, r8d
0x140002c50  mov     edx, 32h ; '2'
0x140002c55  mov     ecx, ebx
0x140002c57  call    cs:__guard_dispatch_icall_fptr
0x140002c5d  mov     rax, cs:__pfnDliNotifyHook2
0x140002c64  test    rax, rax
0x140002c67  jz      short loc_140002C87
0x140002c69  mov     rdx, rbp
0x140002c6c  mov     ecx, 1
0x140002c71  call    cs:__guard_dispatch_icall_fptr
0x140002c77  mov     rsi, rax
0x140002c7a  lea     rdi, [rbp+18h]
0x140002c7e  test    rax, rax
0x140002c81  jnz     loc_140002D4B
0x140002c87  lea     rdi, [rbp+18h]
0x140002c8b  mov     rax, [rdi]
0x140002c8e  cmp     byte ptr [rax], 0
0x140002c91  jnz     short loc_140002C9A
0x140002c93  mov     ecx, 5
0x140002c98  int     29h; Win8: RtlFailFast(ecx)
0x140002c9a  xor     edx, edx; hFile
0x140002c9c  mov     r8d, 1000h; dwFlags
0x140002ca2  mov     rcx, rax; lpLibFileName
0x140002ca5  call    cs:__imp_LoadLibraryExA
0x140002cab  mov     rsi, rax
0x140002cae  test    rax, rax
0x140002cb1  jnz     loc_140002D4B
0x140002cb7  lea     rcx, [rsp+48h+arg_18]
0x140002cbc  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x140002cc1  mov     rax, [rsp+48h+arg_18]
0x140002cc6  mov     [rsp+48h+arg_10], rax
0x140002ccb  mov     ecx, ebx
0x140002ccd  test    ebx, ebx
0x140002ccf  jz      short loc_140002CF3
0x140002cd1  imul    rdx, rcx, 989680h
0x140002cd8  mov     rcx, r15
0x140002cdb  sub     rcx, rdx
0x140002cde  cmp     rax, rcx
0x140002ce1  jge     short loc_140002CEE
0x140002ce3  lea     rcx, [rdx+rax]
0x140002ce7  mov     [rsp+48h+arg_10], rcx
0x140002cec  jmp     short loc_140002CF3
0x140002cee  mov     [rsp+48h+arg_10], r15
0x140002cf3  lea     rcx, [rsp+48h+arg_10]
0x140002cf8  call    ??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x140002cfd  inc     ebx
0x140002cff  cmp     ebx, 32h ; '2'
0x140002d02  jbe     loc_140002C41
0x140002d08  inc     cs:dword_140005728
0x140002d0e  mov     rax, [rdi]
0x140002d11  lea     r8, byte_140003677
0x140002d18  test    rax, rax
0x140002d1b  cmovnz  r8, rax; Source
0x140002d1f  mov     edx, 64h ; 'd'; SizeInBytes
0x140002d24  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140002d2b  lea     rcx, Destination; Destination
0x140002d32  call    cs:__imp_strncpy_s
0x140002d38  xor     eax, eax
0x140002d3a  mov     rbx, [rsp+48h+arg_0]
0x140002d3f  add     rsp, 20h
0x140002d43  pop     r15
0x140002d45  pop     r14
0x140002d47  pop     rdi
0x140002d48  pop     rsi
0x140002d49  pop     rbp
0x140002d4a  retn
0x140002d4b  inc     cs:dword_140005724
0x140002d51  mov     rax, [rdi]
0x140002d54  lea     r8, byte_140003677
0x140002d5b  test    rax, rax
0x140002d5e  cmovnz  r8, rax; Source
0x140002d62  mov     edx, 64h ; 'd'; SizeInBytes
0x140002d67  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140002d6e  lea     rcx, byte_14000572C; Destination
0x140002d75  call    cs:__imp_strncpy_s
0x140002d7b  mov     rax, rsi
0x140002d7e  jmp     short loc_140002D3A
```
