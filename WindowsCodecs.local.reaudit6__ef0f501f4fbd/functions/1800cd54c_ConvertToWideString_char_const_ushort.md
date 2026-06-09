# ConvertToWideString(char const *,ushort * *)

- ea: `0x1800cd54c`
- end: `0x1800cd674`
- name: `?ConvertToWideString@@YAJPEBDPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cd3a0`

## callees

- `0x180042ae8`
- `0x18004aad8`
- `0x1800bd9d4`
- `0x1800cd54c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd5e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd655`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd58f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd609`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd58f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd609`

## pseudocode

```c
__int64 __fastcall ConvertToWideString(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // ebx
  int v5; // eax
  int cchWideChar; // ebp
  signed int LastError; // eax
  ULONGLONG pullResult; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  if ( lpMultiByteStr )
  {
    v4 = -2147467259;
    v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
    cchWideChar = v5;
    if ( v5 )
    {
      pullResult = 0;
      v4 = ULongLongMult(v5, 2u, &pullResult);
      if ( v4 >= 0 )
      {
        v4 = CoTaskMemAllocWithInit(pullResult, (void **)a2);
        if ( v4 >= 0 )
        {
          SetLastError(0);
          v4 = 0;
          if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, -1, *a2, cchWideChar) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            if ( v4 >= 0 )
              v4 = -2003292268;
            if ( (_DWORD)g_doStackCaptures )
              DoStackCapture(v4);
          }
          if ( v4 < 0 )
          {
            CoTaskMemFree(*a2);
            *a2 = 0;
          }
        }
      }
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cd54c  push    rbx
0x1800cd54e  push    rbp
0x1800cd54f  push    rsi
0x1800cd550  push    rdi
0x1800cd551  sub     rsp, 38h
0x1800cd555  mov     qword ptr [rdx], 0
0x1800cd55c  mov     rdi, rdx
0x1800cd55f  mov     rsi, rcx
0x1800cd562  test    rcx, rcx
0x1800cd565  jnz     short loc_1800CD56E
0x1800cd567  xor     ebx, ebx
0x1800cd569  jmp     loc_1800CD668
0x1800cd56e  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x1800cd576  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800cd57a  mov     r8, rsi; lpMultiByteStr
0x1800cd57d  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x1800cd586  xor     edx, edx; dwFlags
0x1800cd588  xor     ecx, ecx; CodePage
0x1800cd58a  mov     ebx, 80004005h
0x1800cd58f  call    cs:__imp_MultiByteToWideChar
0x1800cd596  nop     dword ptr [rax+rax+00h]
0x1800cd59b  movsxd  rbp, eax
0x1800cd59e  test    eax, eax
0x1800cd5a0  jz      loc_1800CD668
0x1800cd5a6  mov     rcx, rbp; ullMultiplicand
0x1800cd5a9  mov     [rsp+58h+pullResult], 0
0x1800cd5b2  lea     r8, [rsp+58h+pullResult]; pullResult
0x1800cd5b7  mov     edx, 2; ullMultiplier
0x1800cd5bc  call    ULongLongMult
0x1800cd5c1  mov     ebx, eax
0x1800cd5c3  test    eax, eax
0x1800cd5c5  js      loc_1800CD668
0x1800cd5cb  mov     rcx, [rsp+58h+pullResult]; Size
0x1800cd5d0  mov     rdx, rdi; void **
0x1800cd5d3  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800cd5d8  mov     ebx, eax
0x1800cd5da  test    eax, eax
0x1800cd5dc  js      loc_1800CD668
0x1800cd5e2  xor     ecx, ecx; dwErrCode
0x1800cd5e4  call    cs:__imp_SetLastError
0x1800cd5eb  nop     dword ptr [rax+rax+00h]
0x1800cd5f0  mov     rax, [rdi]
0x1800cd5f3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800cd5f7  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x1800cd5fb  mov     r8, rsi; lpMultiByteStr
0x1800cd5fe  xor     edx, edx; dwFlags
0x1800cd600  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x1800cd605  xor     ecx, ecx; CodePage
0x1800cd607  xor     ebx, ebx
0x1800cd609  call    cs:__imp_MultiByteToWideChar
0x1800cd610  nop     dword ptr [rax+rax+00h]
0x1800cd615  test    eax, eax
0x1800cd617  jnz     short loc_1800CD64E
0x1800cd619  call    cs:__imp_GetLastError
0x1800cd620  nop     dword ptr [rax+rax+00h]
0x1800cd625  mov     ebx, eax
0x1800cd627  test    eax, eax
0x1800cd629  jle     short loc_1800CD634
0x1800cd62b  movzx   ebx, ax
0x1800cd62e  or      ebx, 80070000h
0x1800cd634  test    ebx, ebx
0x1800cd636  mov     eax, 88982F94h
0x1800cd63b  cmovns  ebx, eax
0x1800cd63e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cd645  jz      short loc_1800CD64E
0x1800cd647  mov     ecx, ebx; int
0x1800cd649  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cd64e  test    ebx, ebx
0x1800cd650  jns     short loc_1800CD668
0x1800cd652  mov     rcx, [rdi]; pv
0x1800cd655  call    cs:__imp_CoTaskMemFree
0x1800cd65c  nop     dword ptr [rax+rax+00h]
0x1800cd661  mov     qword ptr [rdi], 0
0x1800cd668  mov     eax, ebx
0x1800cd66a  add     rsp, 38h
0x1800cd66e  pop     rdi
0x1800cd66f  pop     rsi
0x1800cd670  pop     rbp
0x1800cd671  pop     rbx
0x1800cd672  retn
```
