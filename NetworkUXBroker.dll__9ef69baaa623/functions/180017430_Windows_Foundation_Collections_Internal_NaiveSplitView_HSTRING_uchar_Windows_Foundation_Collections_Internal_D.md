# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,uchar *)

- ea: `0x180017430`
- end: `0x18001751f`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@EU?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001039c`

## callees

- `0x1800120fc`
- `0x180017430`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174ef`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  int v6; // ebx
  unsigned int v7; // ebp
  char v8; // di
  __int64 v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rcx
  char v13; // [rsp+60h] [rbp+8h] BYREF
  HSTRING string; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v8 = 0;
  v13 = 0;
  v9 = 0;
  while ( v6 >= 0 )
  {
    if ( (unsigned int)v9 >= v7 )
      goto LABEL_9;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v9 + 16);
    string = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, &string);
    if ( v6 >= 0 )
    {
      v6 = XWinRT::StringEquals::operator()(v11, a2, string, &v13);
      v8 = v13;
      if ( v6 >= 0 )
      {
        if ( v13 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 56LL))(v10, a3);
          WindowsDeleteString(string);
          if ( v6 < 0 )
            break;
LABEL_9:
          if ( v8 )
            return (unsigned int)v6;
          v6 = -2147483637;
          break;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
    v9 = (unsigned int)(v9 + 1);
  }
  *a3 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017430  mov     [rsp+arg_8], rbx
0x180017435  push    rbp
0x180017436  push    rsi
0x180017437  push    rdi
0x180017438  push    r12
0x18001743a  push    r13
0x18001743c  push    r14
0x18001743e  push    r15
0x180017440  sub     rsp, 20h
0x180017444  mov     r15, r8
0x180017447  mov     r12, rdx
0x18001744a  mov     r13, rcx
0x18001744d  xor     ebx, ebx
0x18001744f  mov     rax, [rcx+28h]
0x180017453  mov     ebp, [rax+0Ch]
0x180017456  xor     dil, dil
0x180017459  mov     [rsp+58h+arg_0], dil
0x18001745e  xor     esi, esi
0x180017460  test    ebx, ebx
0x180017462  js      loc_180017503
0x180017468  cmp     esi, ebp
0x18001746a  jnb     loc_1800174F9
0x180017470  mov     rax, [r13+28h]
0x180017474  mov     r14, [rax+rsi*8+10h]
0x180017479  mov     [rsp+58h+string], 0
0x180017482  mov     rax, [r14]
0x180017485  lea     rdx, [rsp+58h+string]
0x18001748a  mov     rcx, r14
0x18001748d  mov     rax, [rax+30h]
0x180017491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017496  mov     ebx, eax
0x180017498  test    eax, eax
0x18001749a  js      short loc_1800174BE
0x18001749c  lea     r9, [rsp+58h+arg_0]
0x1800174a1  mov     r8, [rsp+58h+string]
0x1800174a6  mov     rdx, r12
0x1800174a9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x1800174ae  mov     ebx, eax
0x1800174b0  mov     dil, [rsp+58h+arg_0]
0x1800174b5  test    eax, eax
0x1800174b7  js      short loc_1800174BE
0x1800174b9  test    dil, dil
0x1800174bc  jnz     short loc_1800174D6
0x1800174be  mov     rcx, [rsp+58h+string]; string
0x1800174c3  call    cs:__imp_WindowsDeleteString
0x1800174c9  mov     [rsp+58h+string], 0
0x1800174d2  inc     esi
0x1800174d4  jmp     short loc_180017460
0x1800174d6  mov     rax, [r14]
0x1800174d9  mov     rdx, r15
0x1800174dc  mov     rcx, r14
0x1800174df  mov     rax, [rax+38h]
0x1800174e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174e8  mov     ebx, eax
0x1800174ea  mov     rcx, [rsp+58h+string]; string
0x1800174ef  call    cs:__imp_WindowsDeleteString
0x1800174f5  test    ebx, ebx
0x1800174f7  js      short loc_180017503
0x1800174f9  test    dil, dil
0x1800174fc  jnz     short loc_180017508
0x1800174fe  mov     ebx, 8000000Bh
0x180017503  xor     eax, eax
0x180017505  mov     [r15], al
0x180017508  mov     eax, ebx
0x18001750a  mov     rbx, [rsp+58h+arg_8]
0x18001750f  add     rsp, 20h
0x180017513  pop     r15
0x180017515  pop     r14
0x180017517  pop     r13
0x180017519  pop     r12
0x18001751b  pop     rdi
0x18001751c  pop     rsi
0x18001751d  pop     rbp
0x18001751e  retn
```
