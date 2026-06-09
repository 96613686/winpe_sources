# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,HSTRING__ * *)

- ea: `0x18001f960`
- end: `0x18001fa51`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAU1@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U73456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU7@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f830`
- `0x180062830`

## callees

- `0x18001cf00`
- `0x18001f960`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fa1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fa1f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
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
0x18001f960  mov     [rsp+arg_8], rbx
0x18001f965  push    rbp
0x18001f966  push    rsi
0x18001f967  push    rdi
0x18001f968  push    r12
0x18001f96a  push    r13
0x18001f96c  push    r14
0x18001f96e  push    r15
0x18001f970  sub     rsp, 20h
0x18001f974  mov     r15, r8
0x18001f977  mov     r12, rdx
0x18001f97a  mov     r13, rcx
0x18001f97d  xor     ebx, ebx
0x18001f97f  mov     rax, [rcx+28h]
0x18001f983  mov     ebp, [rax+0Ch]
0x18001f986  xor     dil, dil
0x18001f989  mov     [rsp+58h+arg_0], dil
0x18001f98e  xor     esi, esi
0x18001f990  test    ebx, ebx
0x18001f992  js      loc_18001FA33
0x18001f998  cmp     esi, ebp
0x18001f99a  jnb     loc_18001FA29
0x18001f9a0  mov     rax, [r13+28h]
0x18001f9a4  mov     r14, [rax+rsi*8+10h]
0x18001f9a9  mov     [rsp+58h+string], 0
0x18001f9b2  mov     rax, [r14]
0x18001f9b5  lea     rdx, [rsp+58h+string]
0x18001f9ba  mov     rcx, r14
0x18001f9bd  mov     rax, [rax+30h]
0x18001f9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9c6  mov     ebx, eax
0x18001f9c8  test    eax, eax
0x18001f9ca  js      short loc_18001F9EE
0x18001f9cc  lea     r9, [rsp+58h+arg_0]
0x18001f9d1  mov     r8, [rsp+58h+string]
0x18001f9d6  mov     rdx, r12
0x18001f9d9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18001f9de  mov     ebx, eax
0x18001f9e0  mov     dil, [rsp+58h+arg_0]
0x18001f9e5  test    eax, eax
0x18001f9e7  js      short loc_18001F9EE
0x18001f9e9  test    dil, dil
0x18001f9ec  jnz     short loc_18001FA06
0x18001f9ee  mov     rcx, [rsp+58h+string]; string
0x18001f9f3  call    cs:__imp_WindowsDeleteString
0x18001f9f9  mov     [rsp+58h+string], 0
0x18001fa02  inc     esi
0x18001fa04  jmp     short loc_18001F990
0x18001fa06  mov     rax, [r14]
0x18001fa09  mov     rdx, r15
0x18001fa0c  mov     rcx, r14
0x18001fa0f  mov     rax, [rax+38h]
0x18001fa13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa18  mov     ebx, eax
0x18001fa1a  mov     rcx, [rsp+58h+string]; string
0x18001fa1f  call    cs:__imp_WindowsDeleteString
0x18001fa25  test    ebx, ebx
0x18001fa27  js      short loc_18001FA33
0x18001fa29  test    dil, dil
0x18001fa2c  jnz     short loc_18001FA3A
0x18001fa2e  mov     ebx, 8000000Bh
0x18001fa33  mov     qword ptr [r15], 0
0x18001fa3a  mov     eax, ebx
0x18001fa3c  mov     rbx, [rsp+58h+arg_8]
0x18001fa41  add     rsp, 20h
0x18001fa45  pop     r15
0x18001fa47  pop     r14
0x18001fa49  pop     r13
0x18001fa4b  pop     r12
0x18001fa4d  pop     rdi
0x18001fa4e  pop     rsi
0x18001fa4f  pop     rbp
0x18001fa50  retn
```
