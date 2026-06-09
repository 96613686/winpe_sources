# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x180048f40`
- end: `0x180049031`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180048e10`

## callees

- `0x18003a818`
- `0x180048f40`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048fff`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rax
  char v4; // di
  int v5; // ebx
  __int64 v9; // rsi
  unsigned int v10; // ebp
  __int64 v11; // r14
  __int64 v12; // rcx
  int v13; // eax
  char v15; // [rsp+60h] [rbp+8h] BYREF
  HSTRING string; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v4 = 0;
  v5 = 0;
  v15 = 0;
  v9 = 0;
  v10 = *(_DWORD *)(v3 + 12);
  while ( v5 >= 0 )
  {
    if ( (unsigned int)v9 >= v10 )
      goto LABEL_9;
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v9 + 16);
    string = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 48LL))(v11, &string);
    if ( v5 >= 0 )
    {
      v13 = XWinRT::StringEquals::operator()(v12, a2, string, &v15);
      v4 = v15;
      v5 = v13;
      if ( v13 >= 0 )
      {
        if ( v15 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 56LL))(v11, a3);
          WindowsDeleteString(string);
          if ( v5 < 0 )
            break;
LABEL_9:
          if ( v4 )
            return (unsigned int)v5;
          v5 = -2147483637;
          break;
        }
      }
    }
    WindowsDeleteString(string);
    v9 = (unsigned int)(v9 + 1);
    string = 0;
  }
  *a3 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180048f40  mov     [rsp+arg_8], rbx
0x180048f45  push    rbp
0x180048f46  push    rsi
0x180048f47  push    rdi
0x180048f48  push    r12
0x180048f4a  push    r13
0x180048f4c  push    r14
0x180048f4e  push    r15
0x180048f50  sub     rsp, 20h
0x180048f54  mov     rax, [rcx+28h]
0x180048f58  xor     dil, dil
0x180048f5b  xor     ebx, ebx
0x180048f5d  mov     [rsp+58h+arg_0], dil
0x180048f62  mov     r15, r8
0x180048f65  mov     r12, rdx
0x180048f68  mov     r13, rcx
0x180048f6b  xor     esi, esi
0x180048f6d  mov     ebp, [rax+0Ch]
0x180048f70  test    ebx, ebx
0x180048f72  js      loc_180049013
0x180048f78  cmp     esi, ebp
0x180048f7a  jnb     loc_180049009
0x180048f80  mov     rax, [r13+28h]
0x180048f84  lea     rdx, [rsp+58h+string]
0x180048f89  mov     r14, [rax+rsi*8+10h]
0x180048f8e  mov     [rsp+58h+string], 0
0x180048f97  mov     rcx, r14
0x180048f9a  mov     rax, [r14]
0x180048f9d  mov     rax, [rax+30h]
0x180048fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fa6  mov     ebx, eax
0x180048fa8  test    eax, eax
0x180048faa  js      short loc_180048FCE
0x180048fac  mov     r8, [rsp+58h+string]
0x180048fb1  lea     r9, [rsp+58h+arg_0]
0x180048fb6  mov     rdx, r12
0x180048fb9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x180048fbe  mov     dil, [rsp+58h+arg_0]
0x180048fc3  mov     ebx, eax
0x180048fc5  test    eax, eax
0x180048fc7  js      short loc_180048FCE
0x180048fc9  test    dil, dil
0x180048fcc  jnz     short loc_180048FE6
0x180048fce  mov     rcx, [rsp+58h+string]; string
0x180048fd3  call    cs:__imp_WindowsDeleteString
0x180048fd9  inc     esi
0x180048fdb  mov     [rsp+58h+string], 0
0x180048fe4  jmp     short loc_180048F70
0x180048fe6  mov     rax, [r14]
0x180048fe9  mov     rdx, r15
0x180048fec  mov     rcx, r14
0x180048fef  mov     rax, [rax+38h]
0x180048ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ff8  mov     rcx, [rsp+58h+string]; string
0x180048ffd  mov     ebx, eax
0x180048fff  call    cs:__imp_WindowsDeleteString
0x180049005  test    ebx, ebx
0x180049007  js      short loc_180049013
0x180049009  test    dil, dil
0x18004900c  jnz     short loc_18004901A
0x18004900e  mov     ebx, 8000000Bh
0x180049013  mov     qword ptr [r15], 0
0x18004901a  mov     eax, ebx
0x18004901c  mov     rbx, [rsp+58h+arg_8]
0x180049021  add     rsp, 20h
0x180049025  pop     r15
0x180049027  pop     r14
0x180049029  pop     r13
0x18004902b  pop     r12
0x18004902d  pop     rdi
0x18004902e  pop     rsi
0x18004902f  pop     rbp
0x180049030  retn
```
