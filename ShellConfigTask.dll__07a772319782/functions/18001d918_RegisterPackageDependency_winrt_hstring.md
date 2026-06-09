# RegisterPackageDependency(winrt::hstring)

- ea: `0x18001d918`
- end: `0x18001dac2`
- name: `?RegisterPackageDependency@@YAJUhstring@winrt@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180014f9c`

## callees

- `0x180003060`
- `0x180003078`
- `0x18000ab14`
- `0x18001d918`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dabb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dabb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d9de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da61`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18001d980`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18001d980`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x18001da3e`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x18001da3e`

## string_xrefs

- `0x18001d9c2`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall RegisterPackageDependency(volatile signed __int32 **a1)
{
  char *v2; // rdx
  int PackageDependency; // esi
  __int64 v4; // rdx
  volatile signed __int32 *v5; // rdi
  int v6; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rdi
  int v10; // eax
  HANDLE v11; // rax
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = 0;
  if ( *a1 )
    v2 = (char *)*((_QWORD *)*a1 + 2);
  else
    v2 = byte_180035C10;
  PackageDependency = TryCreatePackageDependency(0, v2, 0, 0);
  if ( PackageDependency < 0 )
  {
    v4 = 199;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
      (const char *)(unsigned int)PackageDependency,
      0);
    v5 = *a1;
    if ( !*a1 )
      return (unsigned int)PackageDependency;
    v6 = _InterlockedDecrement(v5 + 6);
    if ( !v6 )
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v5);
LABEL_10:
      *a1 = 0;
      return (unsigned int)PackageDependency;
    }
    if ( v6 >= 0 )
      goto LABEL_10;
LABEL_20:
    abort();
  }
  PackageDependency = AddPackageDependency(0, 0, 1, &v13);
  if ( PackageDependency < 0 )
  {
    v4 = 206;
    goto LABEL_6;
  }
  v9 = *a1;
  if ( *a1 )
  {
    v10 = _InterlockedDecrement(v9 + 6);
    if ( v10 )
    {
      if ( v10 < 0 )
        goto LABEL_20;
    }
    else
    {
      v11 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v11, 0, (LPVOID)v9);
    }
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d918  mov     [rsp-18h+arg_10], rbx
0x18001d91d  mov     [rsp-18h+arg_18], rsi
0x18001d922  push    rbp
0x18001d923  push    rdi
0x18001d924  push    r14
0x18001d926  mov     rbp, rsp
0x18001d929  sub     rsp, 60h
0x18001d92d  xor     r14d, r14d
0x18001d930  mov     [rbp+var_10], 1
0x18001d934  lea     rax, [rbp+lpMem]
0x18001d938  mov     [rbp+arg_8], r14
0x18001d93c  mov     [rbp+var_20], rax
0x18001d940  mov     rbx, rcx
0x18001d943  mov     rax, [rcx]
0x18001d946  mov     r8d, r14d
0x18001d949  mov     [rbp+lpMem], r14
0x18001d94d  mov     [rbp+var_18], r14
0x18001d951  test    rax, rax
0x18001d954  jz      short loc_18001D95C
0x18001d956  mov     rdx, [rax+10h]
0x18001d95a  jmp     short loc_18001D963
0x18001d95c  lea     rdx, byte_180035C10
0x18001d963  lea     rax, [rbp+var_18]
0x18001d967  xor     r9d, r9d
0x18001d96a  mov     [rsp+60h+var_28], rax
0x18001d96f  xor     ecx, ecx
0x18001d971  mov     [rsp+60h+var_30], r14d
0x18001d976  mov     [rsp+60h+var_38], r14
0x18001d97b  mov     [rsp+60h+var_40], r14d; int
0x18001d980  call    cs:__imp_TryCreatePackageDependency
0x18001d986  mov     esi, eax
0x18001d988  cmp     [rbp+var_10], r14b
0x18001d98c  jz      short loc_18001D9B5
0x18001d98e  mov     rdx, [rbp+var_20]
0x18001d992  mov     rcx, [rbp+var_18]
0x18001d996  mov     rdi, [rdx]
0x18001d999  mov     [rdx], rcx
0x18001d99c  test    rdi, rdi
0x18001d99f  jz      short loc_18001D9B5
0x18001d9a1  call    cs:__imp_GetProcessHeap
0x18001d9a7  mov     r8, rdi; lpMem
0x18001d9aa  xor     edx, edx; dwFlags
0x18001d9ac  mov     rcx, rax; hHeap
0x18001d9af  call    cs:__imp_HeapFree
0x18001d9b5  test    esi, esi
0x18001d9b7  jns     short loc_18001DA2B
0x18001d9b9  mov     edx, 0C7h; void *
0x18001d9be  mov     rcx, [rbp+18h]; this
0x18001d9c2  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001d9c9  mov     r9d, esi; char *
0x18001d9cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9d1  mov     rdi, [rbp+lpMem]
0x18001d9d5  mov     [rbp+lpMem], r14
0x18001d9d9  test    rdi, rdi
0x18001d9dc  jz      short loc_18001D9F2
0x18001d9de  call    cs:__imp_GetProcessHeap
0x18001d9e4  mov     r8, rdi; lpMem
0x18001d9e7  xor     edx, edx; dwFlags
0x18001d9e9  mov     rcx, rax; hHeap
0x18001d9ec  call    cs:__imp_HeapFree
0x18001d9f2  mov     rdi, [rbx]
0x18001d9f5  test    rdi, rdi
0x18001d9f8  jz      short loc_18001DA27
0x18001d9fa  or      eax, 0FFFFFFFFh
0x18001d9fd  lock xadd [rdi+18h], eax
0x18001da02  sub     eax, 1
0x18001da05  jnz     short loc_18001DA1C
0x18001da07  nop
0x18001da08  call    WINRT_IMPL_GetProcessHeap
0x18001da0d  mov     rcx, rax; hHeap
0x18001da10  mov     r8, rdi; lpMem
0x18001da13  xor     edx, edx; dwFlags
0x18001da15  call    WINRT_IMPL_HeapFree
0x18001da1a  jmp     short loc_18001DA24
0x18001da1c  test    eax, eax
0x18001da1e  js      loc_18001DABB
0x18001da24  mov     [rbx], r14
0x18001da27  mov     eax, esi
0x18001da29  jmp     short loc_18001DAA2
0x18001da2b  mov     rcx, [rbp+lpMem]
0x18001da2f  lea     r9, [rbp+arg_8]
0x18001da33  xor     edx, edx
0x18001da35  mov     qword ptr [rsp+60h+var_40], r14
0x18001da3a  lea     r8d, [rdx+1]
0x18001da3e  call    cs:__imp_AddPackageDependency
0x18001da44  mov     esi, eax
0x18001da46  test    eax, eax
0x18001da48  jns     short loc_18001DA54
0x18001da4a  mov     edx, 0CEh
0x18001da4f  jmp     loc_18001D9BE
0x18001da54  mov     rdi, [rbp+lpMem]
0x18001da58  mov     [rbp+lpMem], r14
0x18001da5c  test    rdi, rdi
0x18001da5f  jz      short loc_18001DA75
0x18001da61  call    cs:__imp_GetProcessHeap
0x18001da67  mov     r8, rdi; lpMem
0x18001da6a  xor     edx, edx; dwFlags
0x18001da6c  mov     rcx, rax; hHeap
0x18001da6f  call    cs:__imp_HeapFree
0x18001da75  mov     rdi, [rbx]
0x18001da78  test    rdi, rdi
0x18001da7b  jz      short loc_18001DAA0
0x18001da7d  or      eax, 0FFFFFFFFh
0x18001da80  lock xadd [rdi+18h], eax
0x18001da85  sub     eax, 1
0x18001da88  jnz     short loc_18001DAB7
0x18001da8a  nop
0x18001da8b  call    WINRT_IMPL_GetProcessHeap
0x18001da90  mov     rcx, rax; hHeap
0x18001da93  mov     r8, rdi; lpMem
0x18001da96  xor     edx, edx; dwFlags
0x18001da98  call    WINRT_IMPL_HeapFree
0x18001da9d  mov     [rbx], r14
0x18001daa0  xor     eax, eax
0x18001daa2  lea     r11, [rsp+60h+var_s0]
0x18001daa7  mov     rbx, [r11+30h]
0x18001daab  mov     rsi, [r11+38h]
0x18001daaf  mov     rsp, r11
0x18001dab2  pop     r14
0x18001dab4  pop     rdi
0x18001dab5  pop     rbp
0x18001dab6  retn
0x18001dab7  test    eax, eax
0x18001dab9  jns     short loc_18001DA9D
0x18001dabb  call    cs:__imp_abort
```
