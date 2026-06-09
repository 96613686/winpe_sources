# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x18003c150`
- end: `0x18003c206`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c0d0`

## callees

- `0x18003a818`
- `0x18003c150`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1ed`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  unsigned int v6; // ebp
  int v7; // ebx
  __int64 i; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  char v12; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 12LL);
  v12 = 0;
  v7 = 0;
  for ( i = 0; v7 >= 0 && (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8 * i + 16);
    string = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 48LL))(v9, &string);
    if ( v7 >= 0 )
    {
      v7 = XWinRT::StringEquals::operator()(v10, a2, string, &v12);
      if ( v7 >= 0 )
      {
        if ( v12 )
        {
          *a3 = 1;
          WindowsDeleteString(string);
          return (unsigned int)v7;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003c150  mov     [rsp+arg_8], rbx
0x18003c155  push    rbp
0x18003c156  push    rsi
0x18003c157  push    rdi
0x18003c158  push    r14
0x18003c15a  push    r15
0x18003c15c  sub     rsp, 20h
0x18003c160  mov     rsi, r8
0x18003c163  mov     r15, rdx
0x18003c166  mov     r14, rcx
0x18003c169  mov     byte ptr [r8], 0
0x18003c16d  mov     rax, [rcx+48h]
0x18003c171  mov     ebp, [rax+0Ch]
0x18003c174  mov     [rsp+48h+arg_0], 0
0x18003c179  xor     ebx, ebx
0x18003c17b  xor     edi, edi
0x18003c17d  test    ebx, ebx
0x18003c17f  js      short loc_18003C1F3
0x18003c181  cmp     edi, ebp
0x18003c183  jnb     short loc_18003C1F3
0x18003c185  mov     rax, [r14+48h]
0x18003c189  mov     rcx, [rax+rdi*8+10h]
0x18003c18e  mov     [rsp+48h+string], 0
0x18003c197  mov     rax, [rcx]
0x18003c19a  lea     rdx, [rsp+48h+string]
0x18003c19f  mov     rax, [rax+30h]
0x18003c1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1a8  mov     ebx, eax
0x18003c1aa  test    eax, eax
0x18003c1ac  js      short loc_18003C1CD
0x18003c1ae  lea     r9, [rsp+48h+arg_0]
0x18003c1b3  mov     r8, [rsp+48h+string]
0x18003c1b8  mov     rdx, r15
0x18003c1bb  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18003c1c0  mov     ebx, eax
0x18003c1c2  test    eax, eax
0x18003c1c4  js      short loc_18003C1CD
0x18003c1c6  cmp     [rsp+48h+arg_0], 0
0x18003c1cb  jnz     short loc_18003C1E5
0x18003c1cd  mov     rcx, [rsp+48h+string]; string
0x18003c1d2  call    cs:__imp_WindowsDeleteString
0x18003c1d8  mov     [rsp+48h+string], 0
0x18003c1e1  inc     edi
0x18003c1e3  jmp     short loc_18003C17D
0x18003c1e5  mov     byte ptr [rsi], 1
0x18003c1e8  mov     rcx, [rsp+48h+string]; string
0x18003c1ed  call    cs:__imp_WindowsDeleteString
0x18003c1f3  mov     eax, ebx
0x18003c1f5  mov     rbx, [rsp+48h+arg_8]
0x18003c1fa  add     rsp, 20h
0x18003c1fe  pop     r15
0x18003c200  pop     r14
0x18003c202  pop     rdi
0x18003c203  pop     rsi
0x18003c204  pop     rbp
0x18003c205  retn
```
