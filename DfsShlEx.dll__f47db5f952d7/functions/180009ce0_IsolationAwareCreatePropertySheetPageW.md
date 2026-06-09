# IsolationAwareCreatePropertySheetPageW

- ea: `0x180009ce0`
- end: `0x180009dd1`
- name: `IsolationAwareCreatePropertySheetPageW`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008520`

## callees

- `0x180006dfc`
- `0x180008200`
- `0x180009ce0`
- `0x180009f9c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009dc3`
- `KERNEL32!SetLastError` at `0x180009dc3`
- `KERNEL32!DeactivateActCtx` at `0x180009db7`
- `KERNEL32!DeactivateActCtx` at `0x180009db7`
- `KERNEL32!GetLastError` at `0x180009da2`
- `KERNEL32!GetLastError` at `0x180009da2`

## string_xrefs

- `0x180009d38`: `CreatePropertySheetPageW`

## pseudocode

```c
__int64 __fastcall IsolationAwareCreatePropertySheetPageW(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v5; // rax
  int v6; // eax
  int v7; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( v3 )
    goto LABEL_8;
  v5 = PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("CreatePropertySheetPageW");
  if ( v5 )
  {
    `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn = v5;
LABEL_8:
    v6 = *(_DWORD *)(a1 + 4);
    if ( (v6 & 0x4000) == 0 && *(_DWORD *)a1 >= 0x60u )
    {
      *(_DWORD *)(a1 + 4) = v6 | 0x4000;
      *(_QWORD *)(a1 + 88) = WinbaseIsolationAwarePrivateT_UnPgpgk;
    }
    v2 = ((__int64 (__fastcall *)(__int64))`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(a1);
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v7 = 0;
      LastError = 0;
    }
    else
    {
      v7 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v7 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180009ce0  mov     rax, rsp
0x180009ce3  mov     [rax+10h], rbx
0x180009ce7  mov     [rax+18h], rsi
0x180009ceb  push    rdi
0x180009cec  sub     rsp, 30h
0x180009cf0  mov     rdi, rcx
0x180009cf3  xor     ebx, ebx
0x180009cf5  mov     [rax-18h], rbx
0x180009cf9  mov     rsi, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180009d00  mov     [rax+8], rbx
0x180009d04  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebx
0x180009d0a  jnz     short loc_180009D33
0x180009d0c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x180009d12  jnz     short loc_180009D33
0x180009d14  lea     rcx, [rax+8]; lpCookie
0x180009d18  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180009d1d  test    eax, eax
0x180009d1f  jnz     short loc_180009D33
0x180009d21  xor     eax, eax
0x180009d23  mov     rbx, [rsp+38h+arg_8]
0x180009d28  mov     rsi, [rsp+38h+arg_10]
0x180009d2d  add     rsp, 30h
0x180009d31  pop     rdi
0x180009d32  retn
0x180009d33  test    rsi, rsi
0x180009d36  jnz     short loc_180009D50
0x180009d38  lea     rcx, aCreateproperty; "CreatePropertySheetPageW"
0x180009d3f  call    PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180009d44  test    rax, rax
0x180009d47  jz      short loc_180009D88
0x180009d49  mov     cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA, rax; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180009d50  mov     eax, [rdi+4]
0x180009d53  mov     ecx, 4000h
0x180009d58  test    ecx, eax
0x180009d5a  jnz     short loc_180009D71
0x180009d5c  cmp     dword ptr [rdi], 60h ; '`'
0x180009d5f  jb      short loc_180009D71
0x180009d61  or      eax, ecx
0x180009d63  mov     [rdi+4], eax
0x180009d66  mov     rax, cs:WinbaseIsolationAwarePrivateT_UnPgpgk
0x180009d6d  mov     [rdi+58h], rax
0x180009d71  mov     rcx, rdi
0x180009d74  mov     rax, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180009d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d80  mov     rbx, rax
0x180009d83  mov     [rsp+38h+var_18], rax
0x180009d88  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180009d8f  jz      short loc_180009D9A
0x180009d91  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009d98  jnz     short loc_180009DC9
0x180009d9a  test    rbx, rbx
0x180009d9d  jnz     short loc_180009DAC
0x180009d9f  lea     esi, [rbx+1]
0x180009da2  call    cs:__imp_GetLastError
0x180009da8  mov     edi, eax
0x180009daa  jmp     short loc_180009DB0
0x180009dac  xor     esi, esi
0x180009dae  xor     edi, edi
0x180009db0  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180009db5  xor     ecx, ecx; dwFlags
0x180009db7  call    cs:__imp_DeactivateActCtx
0x180009dbd  test    esi, esi
0x180009dbf  jz      short loc_180009DC9
0x180009dc1  mov     ecx, edi; dwErrCode
0x180009dc3  call    cs:__imp_SetLastError
0x180009dc9  mov     rax, rbx
0x180009dcc  jmp     loc_180009D23
0x18000b11c  push    rbx
0x18000b11e  push    rbp
0x18000b11f  push    rdi
0x18000b120  sub     rsp, 20h
0x18000b124  mov     rbp, rdx
0x18000b127  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000b12e  jz      short loc_18000B139
0x18000b130  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b137  jnz     short loc_18000B16C
0x18000b139  cmp     qword ptr [rbp+20h], 0
0x18000b13e  jnz     short loc_18000B14F
0x18000b140  mov     edi, 1
0x18000b145  call    cs:__imp_GetLastError
0x18000b14b  mov     ebx, eax
0x18000b14d  jmp     short loc_18000B153
0x18000b14f  xor     edi, edi
0x18000b151  xor     ebx, ebx
0x18000b153  mov     rdx, [rbp+40h]; ulCookie
0x18000b157  xor     ecx, ecx; dwFlags
0x18000b159  call    cs:__imp_DeactivateActCtx
0x18000b15f  test    edi, edi
0x18000b161  jz      short loc_18000B16C
0x18000b163  mov     ecx, ebx; dwErrCode
0x18000b165  call    cs:__imp_SetLastError
0x18000b16b  nop
0x18000b16c  add     rsp, 20h
0x18000b170  pop     rdi
0x18000b171  pop     rbp
0x18000b172  pop     rbx
0x18000b173  retn
```
