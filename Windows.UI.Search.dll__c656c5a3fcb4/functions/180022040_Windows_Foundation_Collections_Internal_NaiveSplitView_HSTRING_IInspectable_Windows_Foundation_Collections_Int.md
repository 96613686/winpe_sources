# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x180022040`
- end: `0x1800220f6`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021fc0`

## callees

- `0x180018bf0`
- `0x180022040`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800220c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800220dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800220c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800220dd`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(
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
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v12 = 0;
  v7 = 0;
  for ( i = 0; v7 >= 0 && (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * i + 16);
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
0x180022040  mov     [rsp+arg_8], rbx
0x180022045  push    rbp
0x180022046  push    rsi
0x180022047  push    rdi
0x180022048  push    r14
0x18002204a  push    r15
0x18002204c  sub     rsp, 20h
0x180022050  mov     rsi, r8
0x180022053  mov     r15, rdx
0x180022056  mov     r14, rcx
0x180022059  mov     byte ptr [r8], 0
0x18002205d  mov     rax, [rcx+28h]
0x180022061  mov     ebp, [rax+0Ch]
0x180022064  mov     [rsp+48h+arg_0], 0
0x180022069  xor     ebx, ebx
0x18002206b  xor     edi, edi
0x18002206d  test    ebx, ebx
0x18002206f  js      short loc_1800220E3
0x180022071  cmp     edi, ebp
0x180022073  jnb     short loc_1800220E3
0x180022075  mov     rax, [r14+28h]
0x180022079  mov     rcx, [rax+rdi*8+10h]
0x18002207e  mov     [rsp+48h+string], 0
0x180022087  mov     rax, [rcx]
0x18002208a  lea     rdx, [rsp+48h+string]
0x18002208f  mov     rax, [rax+30h]
0x180022093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022098  mov     ebx, eax
0x18002209a  test    eax, eax
0x18002209c  js      short loc_1800220BD
0x18002209e  lea     r9, [rsp+48h+arg_0]
0x1800220a3  mov     r8, [rsp+48h+string]
0x1800220a8  mov     rdx, r15
0x1800220ab  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x1800220b0  mov     ebx, eax
0x1800220b2  test    eax, eax
0x1800220b4  js      short loc_1800220BD
0x1800220b6  cmp     [rsp+48h+arg_0], 0
0x1800220bb  jnz     short loc_1800220D5
0x1800220bd  mov     rcx, [rsp+48h+string]; string
0x1800220c2  call    cs:__imp_WindowsDeleteString
0x1800220c8  mov     [rsp+48h+string], 0
0x1800220d1  inc     edi
0x1800220d3  jmp     short loc_18002206D
0x1800220d5  mov     byte ptr [rsi], 1
0x1800220d8  mov     rcx, [rsp+48h+string]; string
0x1800220dd  call    cs:__imp_WindowsDeleteString
0x1800220e3  mov     eax, ebx
0x1800220e5  mov     rbx, [rsp+48h+arg_8]
0x1800220ea  add     rsp, 20h
0x1800220ee  pop     r15
0x1800220f0  pop     r14
0x1800220f2  pop     rdi
0x1800220f3  pop     rsi
0x1800220f4  pop     rbp
0x1800220f5  retn
```
