# ??$BuildThreadAttributeList@$01@Support@Manager@Container@@YAJQEAU_SECURITY_CAPABILITIES@@AEBU?$array@PEAX$01@utl@@AEBU?$array@_K$01@5@QEAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@_E$1?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z

- ea: `0x180111ab0`
- end: `0x180111d68`
- name: `??$BuildThreadAttributeList@$01@Support@Manager@Container@@YAJQEAU_SECURITY_CAPABILITIES@@AEBU?$array@PEAX$01@utl@@AEBU?$array@_K$01@5@QEAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@_E$1?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(PVOID lpValue, PVOID, PVOID, PVOID, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180111fb4`

## callees

- `0x180005704`
- `0x1800067cc`
- `0x18000da68`
- `0x18000da88`
- `0x180111ab0`
- `0x1801131a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111cdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111cf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180111cf7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180111adf`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180111b59`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180111adf`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180111b59`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111bc1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111c2c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111c6c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111cab`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111bc1`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111c2c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111c6c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180111cab`

## pseudocode

```c
__int64 __fastcall Container::Manager::Support::BuildThreadAttributeList<2>(
        PVOID lpValue,
        PVOID a2,
        PVOID a3,
        PVOID a4,
        char *a5)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v5; // rbx
  const char *v10; // r9
  unsigned int LastError; // edi
  size_t v12; // rdi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v13; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v14; // rsi
  const char *v15; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v16; // rdx
  const char *v17; // r9
  __int64 v18; // rdx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v19; // rdx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v20; // rdx
  Container::Manager::Support *v21; // rbp
  DWORD v22; // edi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v23; // rdx
  int cbSize; // [rsp+20h] [rbp-68h]
  ULONG_PTR Size; // [rsp+40h] [rbp-48h] BYREF
  char v27; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = 0;
  Size = 0;
  if ( InitializeProcThreadAttributeList(0, 4u, 0, &Size) || GetLastError() == 122 )
  {
    v12 = Size;
    v13 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( !v13 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)0x8007000ELL,
        cbSize);
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)LastError,
        cbSize);
      return LastError;
    }
    memset_0(v13, 0, v12);
    if ( InitializeProcThreadAttributeList(v14, 4u, 0, &Size) )
    {
      v5 = v14;
      goto LABEL_10;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x169,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                  v15);
    Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v14, v16);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x158,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                  v10);
  }
  if ( (LastError & 0x80000000) != 0 )
    goto LABEL_28;
LABEL_10:
  if ( !UpdateProcThreadAttribute(v5, 0, 0x20009u, lpValue, 0x18u, 0, 0) )
  {
    v18 = 417;
    goto LABEL_12;
  }
  if ( !UpdateProcThreadAttribute(v5, 0, 0x20002u, a2, 0x10u, 0, 0) )
  {
    v18 = 425;
    goto LABEL_12;
  }
  if ( !UpdateProcThreadAttribute(v5, 0, 0x2000Eu, a4, 4u, 0, 0) )
  {
    v18 = 433;
    goto LABEL_12;
  }
  if ( !UpdateProcThreadAttribute(v5, 0, 0x20007u, a3, 0x10u, 0, 0) )
  {
    v18 = 441;
LABEL_12:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v18,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                  v17);
    if ( v5 )
      Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v5, v19);
    return LastError;
  }
  if ( a5 == &v27 )
  {
    if ( v5 )
      Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v5, v20);
  }
  else
  {
    v21 = *(Container::Manager::Support **)a5;
    if ( *(_QWORD *)a5 )
    {
      v22 = GetLastError();
      Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v21, v23);
      SetLastError(v22);
    }
    *(_QWORD *)a5 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180111ab0  push    rbx
0x180111ab2  push    rbp
0x180111ab3  push    rsi
0x180111ab4  push    rdi
0x180111ab5  push    r12
0x180111ab7  push    r14
0x180111ab9  push    r15
0x180111abb  sub     rsp, 50h
0x180111abf  xor     ebx, ebx
0x180111ac1  mov     r12, r9
0x180111ac4  mov     r15, r8
0x180111ac7  mov     [rsp+88h+Size], rbx
0x180111acc  mov     r14, rdx
0x180111acf  lea     r9, [rsp+88h+Size]; lpSize
0x180111ad4  mov     rbp, rcx
0x180111ad7  xor     r8d, r8d; dwFlags
0x180111ada  lea     edx, [rbx+4]; dwAttributeCount
0x180111add  xor     ecx, ecx; lpAttributeList
0x180111adf  call    cs:__imp_InitializeProcThreadAttributeList
0x180111ae6  nop     dword ptr [rax+rax+00h]
0x180111aeb  test    eax, eax
0x180111aed  jnz     short loc_180111B1D
0x180111aef  call    cs:__imp_GetLastError
0x180111af6  nop     dword ptr [rax+rax+00h]
0x180111afb  cmp     eax, 7Ah ; 'z'
0x180111afe  jz      short loc_180111B1D
0x180111b00  mov     rcx, [rsp+88h]; this
0x180111b08  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111b0f  mov     edx, 158h; void *
0x180111b14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180111b19  mov     edi, eax
0x180111b1b  jmp     short loc_180111B8C
0x180111b1d  mov     rdi, [rsp+88h+Size]
0x180111b22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180111b29  mov     rcx, rdi; unsigned __int64
0x180111b2c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180111b31  mov     rsi, rax
0x180111b34  test    rax, rax
0x180111b37  jz      loc_180111D19
0x180111b3d  mov     r8, rdi; Size
0x180111b40  xor     edx, edx; Val
0x180111b42  mov     rcx, rax; void *
0x180111b45  call    memset_0
0x180111b4a  xor     r8d, r8d; dwFlags
0x180111b4d  lea     r9, [rsp+88h+Size]; lpSize
0x180111b52  mov     rcx, rsi; lpAttributeList
0x180111b55  lea     edx, [r8+4]; dwAttributeCount
0x180111b59  call    cs:__imp_InitializeProcThreadAttributeList
0x180111b60  nop     dword ptr [rax+rax+00h]
0x180111b65  test    eax, eax
0x180111b67  jnz     short loc_180111B95
0x180111b69  mov     rcx, [rsp+88h]; this
0x180111b71  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111b78  mov     edx, 169h; void *
0x180111b7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180111b82  mov     rcx, rsi; this
0x180111b85  mov     edi, eax
0x180111b87  call    ?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)
0x180111b8c  test    edi, edi
0x180111b8e  jns     short loc_180111B98
0x180111b90  jmp     loc_180111D3A
0x180111b95  mov     rbx, rsi
0x180111b98  mov     [rsp+88h+lpReturnSize], 0; lpReturnSize
0x180111ba1  mov     r9, rbp; lpValue
0x180111ba4  mov     [rsp+88h+lpPreviousValue], 0; lpPreviousValue
0x180111bad  xor     edx, edx; dwFlags
0x180111baf  mov     r8d, 20009h; Attribute
0x180111bb5  mov     [rsp+88h+cbSize], 18h; cbSize
0x180111bbe  mov     rcx, rbx; lpAttributeList
0x180111bc1  call    cs:__imp_UpdateProcThreadAttribute
0x180111bc8  nop     dword ptr [rax+rax+00h]
0x180111bcd  test    eax, eax
0x180111bcf  jnz     short loc_180111C02
0x180111bd1  mov     edx, 1A1h; void *
0x180111bd6  mov     rcx, [rsp+88h]; this
0x180111bde  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111be5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180111bea  mov     edi, eax
0x180111bec  test    rbx, rbx
0x180111bef  jz      loc_180111D56
0x180111bf5  mov     rcx, rbx; this
0x180111bf8  call    ?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)
0x180111bfd  jmp     loc_180111D56
0x180111c02  mov     [rsp+88h+lpReturnSize], 0; lpReturnSize
0x180111c0b  mov     edi, 10h
0x180111c10  mov     [rsp+88h+lpPreviousValue], 0; lpPreviousValue
0x180111c19  mov     r9, r14; lpValue
0x180111c1c  xor     edx, edx; dwFlags
0x180111c1e  mov     [rsp+88h+cbSize], rdi; cbSize
0x180111c23  mov     r8d, 20002h; Attribute
0x180111c29  mov     rcx, rbx; lpAttributeList
0x180111c2c  call    cs:__imp_UpdateProcThreadAttribute
0x180111c33  nop     dword ptr [rax+rax+00h]
0x180111c38  test    eax, eax
0x180111c3a  jnz     short loc_180111C43
0x180111c3c  mov     edx, 1A9h
0x180111c41  jmp     short loc_180111BD6
0x180111c43  mov     [rsp+88h+lpReturnSize], 0; lpReturnSize
0x180111c4c  mov     r9, r12; lpValue
0x180111c4f  mov     [rsp+88h+lpPreviousValue], 0; lpPreviousValue
0x180111c58  xor     edx, edx; dwFlags
0x180111c5a  mov     r8d, 2000Eh; Attribute
0x180111c60  mov     [rsp+88h+cbSize], 4; cbSize
0x180111c69  mov     rcx, rbx; lpAttributeList
0x180111c6c  call    cs:__imp_UpdateProcThreadAttribute
0x180111c73  nop     dword ptr [rax+rax+00h]
0x180111c78  test    eax, eax
0x180111c7a  jnz     short loc_180111C86
0x180111c7c  mov     edx, 1B1h
0x180111c81  jmp     loc_180111BD6
0x180111c86  mov     [rsp+88h+lpReturnSize], 0; lpReturnSize
0x180111c8f  mov     r9, r15; lpValue
0x180111c92  mov     [rsp+88h+lpPreviousValue], 0; lpPreviousValue
0x180111c9b  xor     edx, edx; dwFlags
0x180111c9d  mov     r8d, 20007h; Attribute
0x180111ca3  mov     [rsp+88h+cbSize], rdi; cbSize
0x180111ca8  mov     rcx, rbx; lpAttributeList
0x180111cab  call    cs:__imp_UpdateProcThreadAttribute
0x180111cb2  nop     dword ptr [rax+rax+00h]
0x180111cb7  test    eax, eax
0x180111cb9  jnz     short loc_180111CC5
0x180111cbb  mov     edx, 1B9h
0x180111cc0  jmp     loc_180111BD6
0x180111cc5  mov     rsi, [rsp+88h+arg_20]
0x180111ccd  lea     rax, [rsp+88h+var_40]
0x180111cd2  cmp     rsi, rax
0x180111cd5  jz      short loc_180111D08
0x180111cd7  mov     rbp, [rsi]
0x180111cda  test    rbp, rbp
0x180111cdd  jz      short loc_180111D03
0x180111cdf  call    cs:__imp_GetLastError
0x180111ce6  nop     dword ptr [rax+rax+00h]
0x180111ceb  mov     rcx, rbp; this
0x180111cee  mov     edi, eax
0x180111cf0  call    ?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)
0x180111cf5  mov     ecx, edi; dwErrCode
0x180111cf7  call    cs:__imp_SetLastError
0x180111cfe  nop     dword ptr [rax+rax+00h]
0x180111d03  mov     [rsi], rbx
0x180111d06  jmp     short loc_180111D15
0x180111d08  test    rbx, rbx
0x180111d0b  jz      short loc_180111D15
0x180111d0d  mov     rcx, rbx; this
0x180111d10  call    ?DeleteAndFreeProcThreadAttributeList@Support@Manager@Container@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)
0x180111d15  xor     eax, eax
0x180111d17  jmp     short loc_180111D58
0x180111d19  mov     rcx, [rsp+88h]; this
0x180111d21  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111d28  mov     edi, 8007000Eh
0x180111d2d  mov     edx, 160h; void *
0x180111d32  mov     r9d, edi; char *
0x180111d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111d3a  mov     rcx, [rsp+88h]; this
0x180111d42  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180111d49  mov     r9d, edi; char *
0x180111d4c  mov     edx, 199h; void *
0x180111d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111d56  mov     eax, edi
0x180111d58  add     rsp, 50h
0x180111d5c  pop     r15
0x180111d5e  pop     r14
0x180111d60  pop     r12
0x180111d62  pop     rdi
0x180111d63  pop     rsi
0x180111d64  pop     rbp
0x180111d65  pop     rbx
0x180111d66  retn
```
