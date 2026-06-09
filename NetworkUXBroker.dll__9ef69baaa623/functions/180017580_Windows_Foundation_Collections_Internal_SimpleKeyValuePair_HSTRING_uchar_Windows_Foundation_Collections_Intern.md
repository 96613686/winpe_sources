# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>::Make(HSTRING__ * const &,uchar const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0> * *)

- ea: `0x180017580`
- end: `0x18001761a`
- name: `?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBEPEAPEAV12345@@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015550`
- `0x18001a420`

## callees

- `0x180010544`
- `0x180016fa8`
- `0x180017580`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800175c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800175c0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>::Make(
        HSTRING *a1,
        char *a2,
        _QWORD *a3)
{
  __int64 v6; // rdi
  HRESULT v7; // ebx
  HSTRING v8; // rcx
  char v9; // dl
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF
  HSTRING newString; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>::permission>(
    &v11,
    a2);
  v6 = v11;
  if ( v11 )
  {
    v7 = WindowsDuplicateString(*a1, &newString);
    if ( v7 >= 0 )
    {
      v9 = *a2;
      v7 = 0;
      v8 = *(HSTRING *)(v6 + 32);
      *(_QWORD *)(v6 + 32) = newString;
      *(_BYTE *)(v6 + 40) = v9;
    }
    else
    {
      v8 = 0;
    }
    newString = v8;
    WindowsDeleteString(v8);
    if ( v7 >= 0 )
    {
      v11 = 0;
      *a3 = v6;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,0>>::InternalRelease(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017580  mov     [rsp+arg_0], rbx
0x180017585  push    rsi
0x180017586  push    rdi
0x180017587  push    r14
0x180017589  sub     rsp, 20h
0x18001758d  mov     rbx, rcx
0x180017590  mov     qword ptr [r8], 0
0x180017597  lea     rcx, [rsp+38h+arg_10]
0x18001759c  mov     rsi, r8
0x18001759f  mov     r14, rdx
0x1800175a2  call    ??$Make@V?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@@12@$$QEAUpermission@?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>::permission>(Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>::permission &&)
0x1800175a7  mov     rdi, [rsp+38h+arg_10]
0x1800175ac  test    rdi, rdi
0x1800175af  jnz     short loc_1800175B8
0x1800175b1  mov     ebx, 8007000Eh
0x1800175b6  jmp     short loc_180017600
0x1800175b8  mov     rcx, [rbx]; string
0x1800175bb  lea     rdx, [rsp+38h+newString]; newString
0x1800175c0  call    cs:__imp_WindowsDuplicateString
0x1800175c6  mov     ebx, eax
0x1800175c8  test    eax, eax
0x1800175ca  jns     short loc_1800175D0
0x1800175cc  xor     ecx, ecx
0x1800175ce  jmp     short loc_1800175E5
0x1800175d0  mov     dl, [r14]
0x1800175d3  xor     ebx, ebx
0x1800175d5  mov     rcx, [rdi+20h]; string
0x1800175d9  mov     rax, [rsp+38h+newString]
0x1800175de  mov     [rdi+20h], rax
0x1800175e2  mov     [rdi+28h], dl
0x1800175e5  mov     [rsp+38h+newString], rcx
0x1800175ea  call    cs:__imp_WindowsDeleteString
0x1800175f0  test    ebx, ebx
0x1800175f2  js      short loc_180017600
0x1800175f4  mov     [rsp+38h+arg_10], 0
0x1800175fd  mov     [rsi], rdi
0x180017600  lea     rcx, [rsp+38h+arg_10]
0x180017605  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@E@3456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,0>>::InternalRelease(void)
0x18001760a  mov     eax, ebx
0x18001760c  mov     rbx, [rsp+38h+arg_0]
0x180017611  add     rsp, 20h
0x180017615  pop     r14
0x180017617  pop     rdi
0x180017618  pop     rsi
0x180017619  retn
```
