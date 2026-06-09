# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x18003c740`
- end: `0x18003c831`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c670`

## callees

- `0x18003a818`
- `0x18003c740`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7ff`

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
0x18003c740  mov     [rsp+arg_8], rbx
0x18003c745  push    rbp
0x18003c746  push    rsi
0x18003c747  push    rdi
0x18003c748  push    r12
0x18003c74a  push    r13
0x18003c74c  push    r14
0x18003c74e  push    r15
0x18003c750  sub     rsp, 20h
0x18003c754  mov     r15, r8
0x18003c757  mov     r12, rdx
0x18003c75a  mov     r13, rcx
0x18003c75d  xor     ebx, ebx
0x18003c75f  mov     rax, [rcx+48h]
0x18003c763  mov     ebp, [rax+0Ch]
0x18003c766  xor     dil, dil
0x18003c769  mov     [rsp+58h+arg_0], dil
0x18003c76e  xor     esi, esi
0x18003c770  test    ebx, ebx
0x18003c772  js      loc_18003C813
0x18003c778  cmp     esi, ebp
0x18003c77a  jnb     loc_18003C809
0x18003c780  mov     rax, [r13+48h]
0x18003c784  mov     r14, [rax+rsi*8+10h]
0x18003c789  mov     [rsp+58h+string], 0
0x18003c792  mov     rax, [r14]
0x18003c795  lea     rdx, [rsp+58h+string]
0x18003c79a  mov     rcx, r14
0x18003c79d  mov     rax, [rax+30h]
0x18003c7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7a6  mov     ebx, eax
0x18003c7a8  test    eax, eax
0x18003c7aa  js      short loc_18003C7CE
0x18003c7ac  lea     r9, [rsp+58h+arg_0]
0x18003c7b1  mov     r8, [rsp+58h+string]
0x18003c7b6  mov     rdx, r12
0x18003c7b9  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18003c7be  mov     ebx, eax
0x18003c7c0  mov     dil, [rsp+58h+arg_0]
0x18003c7c5  test    eax, eax
0x18003c7c7  js      short loc_18003C7CE
0x18003c7c9  test    dil, dil
0x18003c7cc  jnz     short loc_18003C7E6
0x18003c7ce  mov     rcx, [rsp+58h+string]; string
0x18003c7d3  call    cs:__imp_WindowsDeleteString
0x18003c7d9  mov     [rsp+58h+string], 0
0x18003c7e2  inc     esi
0x18003c7e4  jmp     short loc_18003C770
0x18003c7e6  mov     rax, [r14]
0x18003c7e9  mov     rdx, r15
0x18003c7ec  mov     rcx, r14
0x18003c7ef  mov     rax, [rax+38h]
0x18003c7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7f8  mov     ebx, eax
0x18003c7fa  mov     rcx, [rsp+58h+string]; string
0x18003c7ff  call    cs:__imp_WindowsDeleteString
0x18003c805  test    ebx, ebx
0x18003c807  js      short loc_18003C813
0x18003c809  test    dil, dil
0x18003c80c  jnz     short loc_18003C81A
0x18003c80e  mov     ebx, 8000000Bh
0x18003c813  mov     qword ptr [r15], 0
0x18003c81a  mov     eax, ebx
0x18003c81c  mov     rbx, [rsp+58h+arg_8]
0x18003c821  add     rsp, 20h
0x18003c825  pop     r15
0x18003c827  pop     r14
0x18003c829  pop     r13
0x18003c82b  pop     r12
0x18003c82d  pop     rdi
0x18003c82e  pop     rsi
0x18003c82f  pop     rbp
0x18003c830  retn
```
