# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x18001aa10`
- end: `0x18001aac6`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a980`

## callees

- `0x180018bf0`
- `0x18001aa10`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aaad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aaad`

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
0x18001aa10  mov     [rsp+arg_8], rbx
0x18001aa15  push    rbp
0x18001aa16  push    rsi
0x18001aa17  push    rdi
0x18001aa18  push    r14
0x18001aa1a  push    r15
0x18001aa1c  sub     rsp, 20h
0x18001aa20  mov     rsi, r8
0x18001aa23  mov     r15, rdx
0x18001aa26  mov     r14, rcx
0x18001aa29  mov     byte ptr [r8], 0
0x18001aa2d  mov     rax, [rcx+48h]
0x18001aa31  mov     ebp, [rax+0Ch]
0x18001aa34  mov     [rsp+48h+arg_0], 0
0x18001aa39  xor     ebx, ebx
0x18001aa3b  xor     edi, edi
0x18001aa3d  test    ebx, ebx
0x18001aa3f  js      short loc_18001AAB3
0x18001aa41  cmp     edi, ebp
0x18001aa43  jnb     short loc_18001AAB3
0x18001aa45  mov     rax, [r14+48h]
0x18001aa49  mov     rcx, [rax+rdi*8+10h]
0x18001aa4e  mov     [rsp+48h+string], 0
0x18001aa57  mov     rax, [rcx]
0x18001aa5a  lea     rdx, [rsp+48h+string]
0x18001aa5f  mov     rax, [rax+30h]
0x18001aa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa68  mov     ebx, eax
0x18001aa6a  test    eax, eax
0x18001aa6c  js      short loc_18001AA8D
0x18001aa6e  lea     r9, [rsp+48h+arg_0]
0x18001aa73  mov     r8, [rsp+48h+string]
0x18001aa78  mov     rdx, r15
0x18001aa7b  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18001aa80  mov     ebx, eax
0x18001aa82  test    eax, eax
0x18001aa84  js      short loc_18001AA8D
0x18001aa86  cmp     [rsp+48h+arg_0], 0
0x18001aa8b  jnz     short loc_18001AAA5
0x18001aa8d  mov     rcx, [rsp+48h+string]; string
0x18001aa92  call    cs:__imp_WindowsDeleteString
0x18001aa98  mov     [rsp+48h+string], 0
0x18001aaa1  inc     edi
0x18001aaa3  jmp     short loc_18001AA3D
0x18001aaa5  mov     byte ptr [rsi], 1
0x18001aaa8  mov     rcx, [rsp+48h+string]; string
0x18001aaad  call    cs:__imp_WindowsDeleteString
0x18001aab3  mov     eax, ebx
0x18001aab5  mov     rbx, [rsp+48h+arg_8]
0x18001aaba  add     rsp, 20h
0x18001aabe  pop     r15
0x18001aac0  pop     r14
0x18001aac2  pop     rdi
0x18001aac3  pop     rsi
0x18001aac4  pop     rbp
0x18001aac5  retn
```
