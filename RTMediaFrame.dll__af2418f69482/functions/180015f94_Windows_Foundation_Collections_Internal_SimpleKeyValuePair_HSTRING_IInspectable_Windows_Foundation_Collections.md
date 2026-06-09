# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,1>::Initialize(HSTRING__ * const &,XWinRT::detail::GitStorageType<IInspectable> const &)

- ea: `0x180015f94`
- end: `0x18001606c`
- name: `?Initialize@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$00@Internal@Collections@Foundation@Windows@@AEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIInspectable@@@detail@XWinRT@@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015e6c`

## callees

- `0x180015f94`
- `0x1800210b0`
- `0x18003d210`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015fb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015fb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016054`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,1>::Initialize(
        __int64 a1,
        HSTRING *a2,
        __int128 *a3)
{
  HRESULT v5; // ebx
  void *v6; // rcx
  char v7; // al
  HSTRING v8; // rcx
  __m128i v9; // xmm1
  __int128 v11; // [rsp+20h] [rbp-28h] BYREF
  __int128 v12; // [rsp+30h] [rbp-18h] BYREF
  HSTRING newString; // [rsp+58h] [rbp+10h] BYREF

  v5 = WindowsDuplicateString(*a2, &newString);
  if ( v5 >= 0 )
  {
    *(_QWORD *)&v11 = 0;
    BYTE8(v11) = 0;
    v12 = *a3;
    v5 = XWinRT::InterfaceLifetimeTraits::Construct<IInspectable>(&v11, &v12);
    if ( v5 >= 0 )
    {
      v8 = *(HSTRING *)(a1 + 64);
      *(_QWORD *)(a1 + 64) = newString;
      newString = v8;
      v9 = *(__m128i *)(a1 + 72);
      *(_OWORD *)(a1 + 72) = v11;
      v7 = _mm_cvtsi128_si32(_mm_srli_si128(v9, 8));
      v6 = (void *)v9.m128i_i64[0];
    }
    else
    {
      v6 = 0;
      v7 = 0;
    }
    if ( v7 )
    {
      XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(v6);
    }
    else if ( v6 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  else
  {
    newString = 0;
  }
  WindowsDeleteString(newString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015f94  mov     [rsp+arg_0], rbx
0x180015f99  mov     [rsp+arg_10], rsi
0x180015f9e  push    rdi
0x180015f9f  sub     rsp, 40h
0x180015fa3  mov     rsi, r8
0x180015fa6  mov     rax, rdx
0x180015fa9  mov     rdi, rcx
0x180015fac  lea     rdx, [rsp+48h+newString]; newString
0x180015fb1  mov     rcx, [rax]; string
0x180015fb4  call    cs:__imp_WindowsDuplicateString
0x180015fba  mov     ebx, eax
0x180015fbc  test    eax, eax
0x180015fbe  jns     short loc_180015FCE
0x180015fc0  mov     [rsp+48h+newString], 0
0x180015fc9  jmp     loc_18001604F
0x180015fce  mov     qword ptr [rsp+48h+var_28], 0
0x180015fd7  mov     byte ptr [rsp+48h+var_28+8], 0
0x180015fdc  movups  xmm0, xmmword ptr [rsi]
0x180015fdf  movdqu  [rsp+48h+var_18], xmm0
0x180015fe5  lea     rdx, [rsp+48h+var_18]
0x180015fea  lea     rcx, [rsp+48h+var_28]
0x180015fef  call    ??$Construct@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAJPEAV?$GitStorageType@UIInspectable@@@detail@1@V231@@Z; XWinRT::InterfaceLifetimeTraits::Construct<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *,XWinRT::detail::GitStorageType<IInspectable>)
0x180015ff4  mov     ebx, eax
0x180015ff6  test    eax, eax
0x180015ff8  jns     short loc_180016000
0x180015ffa  xor     ecx, ecx
0x180015ffc  xor     al, al
0x180015ffe  jmp     short loc_180016032
0x180016000  mov     rcx, [rdi+40h]
0x180016004  mov     rax, [rsp+48h+newString]
0x180016009  mov     [rdi+40h], rax
0x18001600d  mov     [rsp+48h+newString], rcx
0x180016012  movups  xmm1, xmmword ptr [rdi+48h]
0x180016016  movaps  xmm0, [rsp+48h+var_28]
0x18001601b  movdqu  xmmword ptr [rdi+48h], xmm0
0x180016020  movdqa  xmm0, xmm1
0x180016024  psrldq  xmm0, 8
0x180016029  movd    eax, xmm0
0x18001602d  movq    rcx, xmm1; void *
0x180016032  test    al, al
0x180016034  jz      short loc_18001603D
0x180016036  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18001603b  jmp     short loc_18001604F
0x18001603d  test    rcx, rcx
0x180016040  jz      short loc_18001604F
0x180016042  mov     rax, [rcx]
0x180016045  mov     rax, [rax+10h]
0x180016049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604e  nop
0x18001604f  mov     rcx, [rsp+48h+newString]; string
0x180016054  call    cs:__imp_WindowsDeleteString
0x18001605a  mov     eax, ebx
0x18001605c  mov     rbx, [rsp+48h+arg_0]
0x180016061  mov     rsi, [rsp+48h+arg_10]
0x180016066  add     rsp, 40h
0x18001606a  pop     rdi
0x18001606b  retn
```
