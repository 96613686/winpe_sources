# __acrt_getptd

- ea: `0x1800102a4`
- end: `0x180010378`
- name: `__acrt_getptd`
- size: `212`
- prototype: `__int64()`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c5a4`
- `0x18000e7a8`
- `0x1800134b0`
- `0x180014190`
- `0x180014700`
- `0x180014be0`
- `0x180018960`
- `0x18001b3f0`
- `0x18001b4a0`

## callees

- `0x18000e7c8`
- `0x18000fe3c`
- `0x180010004`
- `0x1800102a4`
- `0x1800120b0`
- `0x180013d4c`
- `0x180013d94`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800102b3`
- `KERNEL32!GetLastError` at `0x1800102b3`
- `KERNEL32!SetLastError` at `0x180010351`
- `KERNEL32!SetLastError` at `0x180010351`

## pseudocode

```c
__int64 _acrt_getptd()
{
  DWORD LastError; // eax
  DWORD v1; // ecx
  DWORD v2; // ebx
  LPVOID Value; // rax
  void *v4; // rdi
  unsigned __int64 v5; // rsi
  void *v6; // rax
  void *v7; // rcx
  __int64 result; // rax

  LastError = GetLastError();
  v1 = dword_18003D0D0;
  v2 = LastError;
  if ( dword_18003D0D0 == -1 )
  {
LABEL_6:
    if ( !_acrt_FlsSetValue(v1, (LPVOID)0xFFFFFFFFFFFFFFFFLL) )
      goto LABEL_4;
    v6 = calloc_base(1u, 0x3C8u);
    v4 = v6;
    if ( v6 )
    {
      if ( _acrt_FlsSetValue(dword_18003D0D0, v6) )
      {
        construct_ptd_array(v4);
        free_base(0);
        goto LABEL_13;
      }
      _acrt_FlsSetValue(dword_18003D0D0, 0);
      v7 = v4;
    }
    else
    {
      _acrt_FlsSetValue(dword_18003D0D0, 0);
      v7 = 0;
    }
    free_base(v7);
    goto LABEL_4;
  }
  Value = _acrt_FlsGetValue(dword_18003D0D0);
  v4 = Value;
  if ( !Value )
  {
    v1 = dword_18003D0D0;
    goto LABEL_6;
  }
  if ( Value == (LPVOID)-1LL )
  {
LABEL_4:
    v4 = 0;
    v5 = 0;
    goto LABEL_14;
  }
LABEL_13:
  v5 = (unsigned __int64)v4;
LABEL_14:
  SetLastError(v2);
  result = v5 & -(__int64)(v4 != 0);
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x1800102a4  mov     [rsp+arg_0], rbx
0x1800102a9  mov     [rsp+arg_8], rsi
0x1800102ae  push    rdi
0x1800102af  sub     rsp, 20h
0x1800102b3  call    cs:__imp_GetLastError
0x1800102b9  mov     ecx, cs:dword_18003D0D0
0x1800102bf  mov     ebx, eax
0x1800102c1  cmp     ecx, 0FFFFFFFFh
0x1800102c4  jz      short loc_1800102E5
0x1800102c6  call    __acrt_FlsGetValue
0x1800102cb  mov     rdi, rax
0x1800102ce  test    rax, rax
0x1800102d1  jz      short loc_1800102DF
0x1800102d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800102d7  jnz     short loc_18001034C
0x1800102d9  xor     edi, edi
0x1800102db  xor     esi, esi
0x1800102dd  jmp     short loc_18001034F
0x1800102df  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x1800102e5  or      rdx, 0FFFFFFFFFFFFFFFFh; lpTlsValue
0x1800102e9  call    __acrt_FlsSetValue
0x1800102ee  test    eax, eax
0x1800102f0  jz      short loc_1800102D9
0x1800102f2  mov     edx, 3C8h; Size
0x1800102f7  mov     ecx, 1; Count
0x1800102fc  call    _calloc_base
0x180010301  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x180010307  mov     rdi, rax
0x18001030a  test    rax, rax
0x18001030d  jnz     short loc_18001031F
0x18001030f  xor     edx, edx; lpTlsValue
0x180010311  call    __acrt_FlsSetValue
0x180010316  xor     ecx, ecx; Block
0x180010318  call    _free_base
0x18001031d  jmp     short loc_1800102D9
0x18001031f  mov     rdx, rdi; lpTlsValue
0x180010322  call    __acrt_FlsSetValue
0x180010327  test    eax, eax
0x180010329  jnz     short loc_18001033D
0x18001032b  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x180010331  xor     edx, edx; lpTlsValue
0x180010333  call    __acrt_FlsSetValue
0x180010338  mov     rcx, rdi
0x18001033b  jmp     short loc_180010318
0x18001033d  mov     rcx, rdi
0x180010340  call    construct_ptd_array
0x180010345  xor     ecx, ecx; Block
0x180010347  call    _free_base
0x18001034c  mov     rsi, rdi
0x18001034f  mov     ecx, ebx; dwErrCode
0x180010351  call    cs:__imp_SetLastError
0x180010357  neg     rdi
0x18001035a  sbb     rax, rax
0x18001035d  and     rax, rsi
0x180010360  jz      short loc_180010372
0x180010362  mov     rbx, [rsp+28h+arg_0]
0x180010367  mov     rsi, [rsp+28h+arg_8]
0x18001036c  add     rsp, 20h
0x180010370  pop     rdi
0x180010371  retn
0x180010372  call    abort
```
