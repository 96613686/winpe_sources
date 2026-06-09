# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x180016480`
- end: `0x180016536`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@EU?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001031c`

## callees

- `0x1800120fc`
- `0x180016480`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001651d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001651d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(
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
0x180016480  mov     [rsp+arg_8], rbx
0x180016485  push    rbp
0x180016486  push    rsi
0x180016487  push    rdi
0x180016488  push    r14
0x18001648a  push    r15
0x18001648c  sub     rsp, 20h
0x180016490  mov     rsi, r8
0x180016493  mov     r15, rdx
0x180016496  mov     r14, rcx
0x180016499  mov     byte ptr [r8], 0
0x18001649d  mov     rax, [rcx+28h]
0x1800164a1  mov     ebp, [rax+0Ch]
0x1800164a4  mov     [rsp+48h+arg_0], 0
0x1800164a9  xor     ebx, ebx
0x1800164ab  xor     edi, edi
0x1800164ad  test    ebx, ebx
0x1800164af  js      short loc_180016523
0x1800164b1  cmp     edi, ebp
0x1800164b3  jnb     short loc_180016523
0x1800164b5  mov     rax, [r14+28h]
0x1800164b9  mov     rcx, [rax+rdi*8+10h]
0x1800164be  mov     [rsp+48h+string], 0
0x1800164c7  mov     rax, [rcx]
0x1800164ca  lea     rdx, [rsp+48h+string]
0x1800164cf  mov     rax, [rax+30h]
0x1800164d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d8  mov     ebx, eax
0x1800164da  test    eax, eax
0x1800164dc  js      short loc_1800164FD
0x1800164de  lea     r9, [rsp+48h+arg_0]
0x1800164e3  mov     r8, [rsp+48h+string]
0x1800164e8  mov     rdx, r15
0x1800164eb  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x1800164f0  mov     ebx, eax
0x1800164f2  test    eax, eax
0x1800164f4  js      short loc_1800164FD
0x1800164f6  cmp     [rsp+48h+arg_0], 0
0x1800164fb  jnz     short loc_180016515
0x1800164fd  mov     rcx, [rsp+48h+string]; string
0x180016502  call    cs:__imp_WindowsDeleteString
0x180016508  mov     [rsp+48h+string], 0
0x180016511  inc     edi
0x180016513  jmp     short loc_1800164AD
0x180016515  mov     byte ptr [rsi], 1
0x180016518  mov     rcx, [rsp+48h+string]; string
0x18001651d  call    cs:__imp_WindowsDeleteString
0x180016523  mov     eax, ebx
0x180016525  mov     rbx, [rsp+48h+arg_8]
0x18001652a  add     rsp, 20h
0x18001652e  pop     r15
0x180016530  pop     r14
0x180016532  pop     rdi
0x180016533  pop     rsi
0x180016534  pop     rbp
0x180016535  retn
```
