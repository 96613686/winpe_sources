# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x1800055d0`
- end: `0x180005873`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `675`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180005000`
- `0x1800052b0`
- `0x180006510`
- `0x18002ee48`
- `0x18003501c`
- `0x1800351f8`
- `0x1800353d4`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x180010a90`
- `0x180017fb8`
- `0x180018170`
- `0x180042912`
- `0x180042950`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180005600`
- `msvcrt!_ui64tow_s` at `0x180005600`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180005795`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180005795`

## string_xrefs

- `0x1800056cf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000574f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180005772`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800057b1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800057d2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        unsigned __int64 a2)
{
  size_t v3; // r9
  wchar_t *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rbp
  unsigned __int64 v7; // rdi
  const wchar_t *v8; // rsi
  size_t v9; // rdx
  HRESULT v10; // edi
  size_t *v11; // r8
  __int64 v12; // r11
  void *v14; // rax
  void *v15; // rsi
  wchar_t *v16; // rdx
  wchar_t *v17; // rcx
  __int64 v18; // r8
  wchar_t v19; // ax
  size_t v20; // [rsp+20h] [rbp-78h]
  int v21; // [rsp+20h] [rbp-78h]
  size_t pcchDestLength; // [rsp+30h] [rbp-68h] BYREF
  wchar_t Buffer[20]; // [rsp+38h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !_ui64tow_s(a2, Buffer, 0x11u, 16) )
  {
    v4 = Buffer;
    v5 = 0;
    v6 = 0;
    while ( *v4 )
    {
      if ( (unsigned __int64)++v5 >= 0x7FFFFFFF )
      {
        v10 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          v20);
        return (unsigned int)v10;
      }
      if ( *v4 == 94 )
        ++v6;
      ++v4;
    }
    v7 = v6 + v5 + *((_QWORD *)this + 65) + 1LL;
    if ( v7 > *((_QWORD *)this + 66) )
    {
      v14 = (void *)SRCache_AllocStringBuffer((unsigned int)v7);
      v15 = v14;
      if ( !v14 )
      {
        v10 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v20);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x136,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v21);
        return (unsigned int)v10;
      }
      memcpy_0(v14, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
        this,
        v15);
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v7;
    }
    v8 = (const wchar_t *)*((_QWORD *)this + 67);
    if ( v6 )
    {
      v16 = Buffer;
      v17 = (wchar_t *)&v8[*((_QWORD *)this + 65)];
      if ( v5 )
      {
        v18 = v5;
        do
        {
          if ( *v16 == 94 )
            *v17++ = 94;
          v19 = *v16++;
          *v17++ = v19;
          --v18;
        }
        while ( v18 );
      }
      *v17 = 0;
    }
    else
    {
      v9 = *((_QWORD *)this + 66);
      pcchDestLength = 0;
      v10 = StringValidateDestAndLengthW(v8, v9, &pcchDestLength, v3);
      if ( v10 >= 0 )
        v10 = StringCopyWorkerW((STRSAFE_LPWSTR)&v8[pcchDestLength], v12 - pcchDestLength, v11, Buffer, v20);
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v10,
          v20);
        return (unsigned int)v10;
      }
    }
    *((_QWORD *)this + 65) += v5;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x166,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8000FFFFLL,
    v20);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800055d0  push    r14
0x1800055d2  sub     rsp, 90h
0x1800055d9  mov     rax, cs:__security_cookie
0x1800055e0  xor     rax, rsp
0x1800055e3  mov     [rsp+98h+var_38], rax
0x1800055e8  mov     rax, rdx
0x1800055eb  mov     r9d, 10h; Radix
0x1800055f1  mov     r14, rcx
0x1800055f4  lea     rdx, [rsp+98h+Buffer]; Buffer
0x1800055f9  mov     rcx, rax; Value
0x1800055fc  lea     r8d, [r9+1]; BufferCount
0x180005600  call    cs:__imp__ui64tow_s
0x180005607  nop     dword ptr [rax+rax+00h]
0x18000560c  test    eax, eax
0x18000560e  jnz     loc_18000576A
0x180005614  mov     [rsp+98h+arg_10], rbx
0x18000561c  lea     rax, [rsp+98h+Buffer]
0x180005621  mov     [rsp+98h+var_10], rbp
0x180005629  mov     [rsp+98h+var_20], rdi
0x18000562e  mov     [rsp+98h+var_28], r15
0x180005633  xor     r15d, r15d
0x180005636  mov     ebx, r15d
0x180005639  mov     ebp, r15d
0x18000563c  nop     dword ptr [rax+00h]
0x180005640  movzx   ecx, word ptr [rax]
0x180005643  test    cx, cx
0x180005646  jz      short loc_180005668
0x180005648  inc     rbx
0x18000564b  cmp     rbx, 7FFFFFFFh
0x180005652  jnb     loc_180005747
0x180005658  cmp     cx, 5Eh ; '^'
0x18000565c  jz      loc_18000571F
0x180005662  add     rax, 2
0x180005666  jmp     short loc_180005640
0x180005668  mov     rdi, [r14+208h]
0x18000566f  inc     rdi
0x180005672  mov     [rsp+98h+var_18], rsi
0x18000567a  add     rdi, rbx
0x18000567d  add     rdi, rbp
0x180005680  cmp     rdi, [r14+210h]
0x180005687  ja      loc_180005793
0x18000568d  mov     rsi, [r14+218h]
0x180005694  test    rbp, rbp
0x180005697  jnz     loc_180005825
0x18000569d  mov     r11, [r14+210h]
0x1800056a4  lea     r8, [rsp+98h+pcchDestLength]; pcchDestLength
0x1800056a9  mov     rdx, r11; cchDest
0x1800056ac  mov     [rsp+98h+pcchDestLength], r15
0x1800056b1  mov     rcx, rsi; pszDest
0x1800056b4  call    StringValidateDestAndLengthW
0x1800056b9  mov     edi, eax
0x1800056bb  test    eax, eax
0x1800056bd  jns     short loc_180005727
0x1800056bf  test    edi, edi
0x1800056c1  jns     loc_180005864
0x1800056c7  mov     rcx, [rsp+98h]; this
0x1800056cf  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800056d6  mov     r9d, edi; char *
0x1800056d9  mov     edx, 139h; void *
0x1800056de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056e3  mov     rsi, [rsp+98h+var_18]
0x1800056eb  mov     r15, [rsp+98h+var_28]
0x1800056f0  mov     eax, edi
0x1800056f2  mov     rdi, [rsp+98h+var_20]
0x1800056f7  mov     rbp, [rsp+98h+var_10]
0x1800056ff  mov     rbx, [rsp+98h+arg_10]
0x180005707  mov     rcx, [rsp+98h+var_38]
0x18000570c  xor     rcx, rsp; StackCookie
0x18000570f  call    __security_check_cookie
0x180005714  add     rsp, 90h
0x18000571b  pop     r14
0x18000571d  retn
0x18000571f  inc     rbp
0x180005722  jmp     loc_180005662
0x180005727  mov     rax, [rsp+98h+pcchDestLength]
0x18000572c  lea     r9, [rsp+98h+Buffer]; pszSrc
0x180005731  sub     r11, rax
0x180005734  mov     rdx, r11; cchDest
0x180005737  lea     rcx, [rsi+rax*2]; pszDest
0x18000573b  call    StringCopyWorkerW
0x180005740  mov     edi, eax
0x180005742  jmp     loc_1800056BF
0x180005747  mov     rcx, [rsp+98h]; this
0x18000574f  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005756  mov     edi, 80070057h
0x18000575b  mov     edx, 135h; void *
0x180005760  mov     r9d, edi; char *
0x180005763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005768  jmp     short loc_1800056EB
0x18000576a  mov     rcx, [rsp+98h]; this
0x180005772  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005779  mov     r9d, 8000FFFFh; char *
0x18000577f  mov     edx, 166h; void *
0x180005784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005789  mov     eax, 8000FFFFh
0x18000578e  jmp     loc_180005707
0x180005793  mov     ecx, edi
0x180005795  call    cs:__imp_SRCache_AllocStringBuffer
0x18000579c  nop     dword ptr [rax+rax+00h]
0x1800057a1  mov     rsi, rax
0x1800057a4  test    rax, rax
0x1800057a7  jnz     short loc_1800057EB
0x1800057a9  mov     rcx, [rsp+98h]; this
0x1800057b1  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800057b8  mov     edi, 8007000Eh
0x1800057bd  mov     edx, 193h; void *
0x1800057c2  mov     r9d, edi; char *
0x1800057c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057ca  mov     rcx, [rsp+98h]; this
0x1800057d2  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800057d9  mov     r9d, edi; char *
0x1800057dc  mov     edx, 136h; void *
0x1800057e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057e6  jmp     loc_1800056E3
0x1800057eb  mov     r8, [r14+210h]
0x1800057f2  mov     rcx, rsi; void *
0x1800057f5  mov     rdx, [r14+218h]; Src
0x1800057fc  add     r8, r8; Size
0x1800057ff  call    memcpy_0
0x180005804  mov     rdx, rsi
0x180005807  mov     rcx, r14
0x18000580a  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x18000580f  mov     rax, [r14]
0x180005812  mov     [r14+218h], rax
0x180005819  mov     [r14+210h], rdi
0x180005820  jmp     loc_18000568D
0x180005825  mov     rax, [r14+208h]
0x18000582c  lea     rdx, [rsp+98h+Buffer]
0x180005831  lea     rcx, [rsi+rax*2]
0x180005835  test    rbx, rbx
0x180005838  jz      short loc_180005860
0x18000583a  mov     r8, rbx
0x18000583d  cmp     word ptr [rdx], 5Eh ; '^'
0x180005841  jnz     short loc_18000584C
0x180005843  mov     word ptr [rcx], 5Eh ; '^'
0x180005848  add     rcx, 2
0x18000584c  movzx   eax, word ptr [rdx]
0x18000584f  add     rdx, 2
0x180005853  mov     [rcx], ax
0x180005856  add     rcx, 2
0x18000585a  sub     r8, 1
0x18000585e  jnz     short loc_18000583D
0x180005860  mov     [rcx], r15w
0x180005864  add     [r14+208h], rbx
0x18000586b  mov     edi, r15d
0x18000586e  jmp     loc_1800056E3
```
