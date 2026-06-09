# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,1>::Initialize(HSTRING__ * const &,XWinRT::detail::GitStorageType<IInspectable> const &)

- ea: `0x18005d050`
- end: `0x18005d128`
- name: `?Initialize@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$00@Internal@Collections@Foundation@Windows@@AEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIInspectable@@@detail@XWinRT@@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005dcf4`

## callees

- `0x1800595b4`
- `0x18005d050`
- `0x18005f030`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d110`

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
0x18005d050  mov     [rsp+arg_0], rbx
0x18005d055  mov     [rsp+arg_10], rsi
0x18005d05a  push    rdi
0x18005d05b  sub     rsp, 40h
0x18005d05f  mov     rsi, r8
0x18005d062  mov     rax, rdx
0x18005d065  mov     rdi, rcx
0x18005d068  lea     rdx, [rsp+48h+newString]; newString
0x18005d06d  mov     rcx, [rax]; string
0x18005d070  call    cs:__imp_WindowsDuplicateString
0x18005d076  mov     ebx, eax
0x18005d078  test    eax, eax
0x18005d07a  jns     short loc_18005D08A
0x18005d07c  mov     [rsp+48h+newString], 0
0x18005d085  jmp     loc_18005D10B
0x18005d08a  mov     qword ptr [rsp+48h+var_28], 0
0x18005d093  mov     byte ptr [rsp+48h+var_28+8], 0
0x18005d098  movups  xmm0, xmmword ptr [rsi]
0x18005d09b  movdqu  [rsp+48h+var_18], xmm0
0x18005d0a1  lea     rdx, [rsp+48h+var_18]
0x18005d0a6  lea     rcx, [rsp+48h+var_28]
0x18005d0ab  call    ??$Construct@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAJPEAV?$GitStorageType@UIInspectable@@@detail@1@V231@@Z; XWinRT::InterfaceLifetimeTraits::Construct<IInspectable>(XWinRT::detail::GitStorageType<IInspectable> *,XWinRT::detail::GitStorageType<IInspectable>)
0x18005d0b0  mov     ebx, eax
0x18005d0b2  test    eax, eax
0x18005d0b4  jns     short loc_18005D0BC
0x18005d0b6  xor     ecx, ecx
0x18005d0b8  xor     al, al
0x18005d0ba  jmp     short loc_18005D0EE
0x18005d0bc  mov     rcx, [rdi+40h]
0x18005d0c0  mov     rax, [rsp+48h+newString]
0x18005d0c5  mov     [rdi+40h], rax
0x18005d0c9  mov     [rsp+48h+newString], rcx
0x18005d0ce  movups  xmm1, xmmword ptr [rdi+48h]
0x18005d0d2  movaps  xmm0, [rsp+48h+var_28]
0x18005d0d7  movdqu  xmmword ptr [rdi+48h], xmm0
0x18005d0dc  movdqa  xmm0, xmm1
0x18005d0e0  psrldq  xmm0, 8
0x18005d0e5  movd    eax, xmm0
0x18005d0e9  movq    rcx, xmm1; void *
0x18005d0ee  test    al, al
0x18005d0f0  jz      short loc_18005D0F9
0x18005d0f2  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIInspectable@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<IInspectable>::ReferencedGitCookie::Release(void)
0x18005d0f7  jmp     short loc_18005D10B
0x18005d0f9  test    rcx, rcx
0x18005d0fc  jz      short loc_18005D10B
0x18005d0fe  mov     rax, [rcx]
0x18005d101  mov     rax, [rax+10h]
0x18005d105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d10a  nop
0x18005d10b  mov     rcx, [rsp+48h+newString]; string
0x18005d110  call    cs:__imp_WindowsDeleteString
0x18005d116  mov     eax, ebx
0x18005d118  mov     rbx, [rsp+48h+arg_0]
0x18005d11d  mov     rsi, [rsp+48h+arg_10]
0x18005d122  add     rsp, 40h
0x18005d126  pop     rdi
0x18005d127  retn
```
