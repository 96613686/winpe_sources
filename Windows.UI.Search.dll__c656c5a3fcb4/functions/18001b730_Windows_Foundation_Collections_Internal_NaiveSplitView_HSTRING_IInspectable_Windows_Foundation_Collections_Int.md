# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x18001b730`
- end: `0x18001b821`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b5f0`

## callees

- `0x180018bf0`
- `0x18001b730`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b7ef`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
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
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 12LL);
  v8 = 0;
  v13 = 0;
  v9 = 0;
  while ( v6 >= 0 )
  {
    if ( (unsigned int)v9 >= v7 )
      goto LABEL_9;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8 * v9 + 16);
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
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 56LL))(v10, a3);
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
0x18001b730  mov     [rsp+arg_8], rbx
0x18001b735  push    rbp
0x18001b736  push    rsi
0x18001b737  push    rdi
0x18001b738  push    r12
0x18001b73a  push    r13
0x18001b73c  push    r14
0x18001b73e  push    r15
0x18001b740  sub     rsp, 20h
0x18001b744  mov     r15, r8
0x18001b747  mov     r12, rdx
0x18001b74a  mov     r13, rcx
0x18001b74d  xor     ebx, ebx
0x18001b74f  mov     rax, [rcx+48h]
0x18001b753  mov     ebp, [rax+0Ch]
0x18001b756  xor     dil, dil
0x18001b759  mov     [rsp+58h+arg_0], dil
0x18001b75e  xor     esi, esi
0x18001b760  test    ebx, ebx
0x18001b762  js      loc_18001B803
0x18001b768  cmp     esi, ebp
0x18001b76a  jnb     loc_18001B7F9
0x18001b770  mov     rax, [r13+48h]
0x18001b774  mov     r14, [rax+rsi*8+10h]
0x18001b779  mov     [rsp+58h+string], 0
0x18001b782  mov     rax, [r14]
0x18001b785  lea     rdx, [rsp+58h+string]
0x18001b78a  mov     rcx, r14
0x18001b78d  mov     rax, [rax+30h]
0x18001b791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b796  mov     ebx, eax
0x18001b798  test    eax, eax
0x18001b79a  js      short loc_18001B7BE
0x18001b79c  lea     r9, [rsp+58h+arg_0]
0x18001b7a1  mov     r8, [rsp+58h+string]
0x18001b7a6  mov     rdx, r12
0x18001b7a9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18001b7ae  mov     ebx, eax
0x18001b7b0  mov     dil, [rsp+58h+arg_0]
0x18001b7b5  test    eax, eax
0x18001b7b7  js      short loc_18001B7BE
0x18001b7b9  test    dil, dil
0x18001b7bc  jnz     short loc_18001B7D6
0x18001b7be  mov     rcx, [rsp+58h+string]; string
0x18001b7c3  call    cs:__imp_WindowsDeleteString
0x18001b7c9  mov     [rsp+58h+string], 0
0x18001b7d2  inc     esi
0x18001b7d4  jmp     short loc_18001B760
0x18001b7d6  mov     rax, [r14]
0x18001b7d9  mov     rdx, r15
0x18001b7dc  mov     rcx, r14
0x18001b7df  mov     rax, [rax+38h]
0x18001b7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e8  mov     ebx, eax
0x18001b7ea  mov     rcx, [rsp+58h+string]; string
0x18001b7ef  call    cs:__imp_WindowsDeleteString
0x18001b7f5  test    ebx, ebx
0x18001b7f7  js      short loc_18001B803
0x18001b7f9  test    dil, dil
0x18001b7fc  jnz     short loc_18001B80A
0x18001b7fe  mov     ebx, 8000000Bh
0x18001b803  mov     qword ptr [r15], 0
0x18001b80a  mov     eax, ebx
0x18001b80c  mov     rbx, [rsp+58h+arg_8]
0x18001b811  add     rsp, 20h
0x18001b815  pop     r15
0x18001b817  pop     r14
0x18001b819  pop     r13
0x18001b81b  pop     r12
0x18001b81d  pop     rdi
0x18001b81e  pop     rsi
0x18001b81f  pop     rbp
0x18001b820  retn
```
