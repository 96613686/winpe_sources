# ConvertWideToUtf8(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004730c`
- end: `0x180047442`
- name: `?ConvertWideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `310`
- prototype: `void *__fastcall(void *Src, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800354bc`

## callees

- `0x180030a68`
- `0x18004730c`
- `0x180049350`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180047396`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180047413`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180047396`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180047413`

## string_xrefs

- `0x18004742d`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall ConvertWideToUtf8(void *Src, LPCWCH lpWideCharStr)
{
  LPCWCH v2; // rdi
  LPCWCH v4; // rax
  const WCHAR *v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  _BYTE *v8; // rax
  CHAR *lpMultiByteStr; // rax
  int v10; // r9d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = lpWideCharStr;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 15;
  *(_BYTE *)Src = 0;
  if ( *((_QWORD *)lpWideCharStr + 2) )
  {
    v4 = *((_QWORD *)lpWideCharStr + 3) <= 7u ? lpWideCharStr : *(LPCWCH *)lpWideCharStr;
    if ( *v4 )
    {
      v5 = *((_QWORD *)lpWideCharStr + 3) <= 7u ? lpWideCharStr : *(const WCHAR **)lpWideCharStr;
      v6 = WideCharToMultiByte(0xFDE9u, 0, v5, *((_DWORD *)lpWideCharStr + 4), 0, 0, 0, 0);
      if ( v6 )
      {
        v7 = v6;
        if ( (unsigned __int64)v6 > *((_QWORD *)Src + 2) )
        {
          std::string::append(Src, v6 - *((_QWORD *)Src + 2), 0);
        }
        else
        {
          *((_QWORD *)Src + 2) = v6;
          if ( *((_QWORD *)Src + 3) <= 0xFu )
            v8 = Src;
          else
            v8 = *(_BYTE **)Src;
          v8[v7] = 0;
        }
        if ( *((_QWORD *)Src + 3) <= 0xFu )
          lpMultiByteStr = (CHAR *)Src;
        else
          lpMultiByteStr = *(CHAR **)Src;
        v10 = *((_DWORD *)v2 + 4);
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(LPCWCH *)v2;
        if ( !WideCharToMultiByte(0xFDE9u, 0, v2, v10, lpMultiByteStr, *((_DWORD *)Src + 4), 0, 0) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x14C,
            (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
            v11);
      }
    }
  }
  return Src;
}

```

## disassembly

```asm
0x18004730c  mov     [rsp+arg_10], rbx
0x180047311  mov     [rsp+arg_0], rcx
0x180047316  push    rbp
0x180047317  push    rsi
0x180047318  push    rdi
0x180047319  sub     rsp, 40h
0x18004731d  mov     rdi, rdx
0x180047320  mov     rbx, rcx
0x180047323  mov     eax, 1
0x180047328  mov     [rsp+58h+arg_8], eax
0x18004732c  xorps   xmm0, xmm0
0x18004732f  movups  xmmword ptr [rcx], xmm0
0x180047332  xor     ebp, ebp
0x180047334  mov     [rcx+10h], rbp
0x180047338  mov     qword ptr [rcx+18h], 0Fh
0x180047340  mov     [rcx], bpl
0x180047343  mov     [rsp+58h+arg_8], eax
0x180047347  cmp     [rdx+10h], rbp
0x18004734b  jz      loc_18004741D
0x180047351  cmp     qword ptr [rdx+18h], 7
0x180047356  jbe     short loc_18004735D
0x180047358  mov     rax, [rdx]
0x18004735b  jmp     short loc_180047360
0x18004735d  mov     rax, rdi
0x180047360  cmp     [rax], bp
0x180047363  jz      loc_18004741D
0x180047369  cmp     qword ptr [rdx+18h], 7
0x18004736e  jbe     short loc_180047375
0x180047370  mov     r8, [rdx]
0x180047373  jmp     short loc_180047378
0x180047375  mov     r8, rdi; lpWideCharStr
0x180047378  mov     [rsp+58h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18004737d  mov     [rsp+58h+lpDefaultChar], rbp; lpDefaultChar
0x180047382  mov     [rsp+58h+cbMultiByte], ebp; cbMultiByte
0x180047386  mov     [rsp+58h+lpMultiByteStr], rbp; lpMultiByteStr
0x18004738b  mov     r9d, [rdx+10h]; cchWideChar
0x18004738f  xor     edx, edx; dwFlags
0x180047391  mov     ecx, 0FDE9h; CodePage
0x180047396  call    cs:__imp_WideCharToMultiByte
0x18004739c  test    eax, eax
0x18004739e  jz      short loc_18004741D
0x1800473a0  movsxd  rdx, eax
0x1800473a3  cmp     rdx, [rbx+10h]
0x1800473a7  ja      short loc_1800473C2
0x1800473a9  mov     [rbx+10h], rdx
0x1800473ad  cmp     qword ptr [rbx+18h], 0Fh
0x1800473b2  jbe     short loc_1800473B9
0x1800473b4  mov     rax, [rbx]
0x1800473b7  jmp     short loc_1800473BC
0x1800473b9  mov     rax, rbx
0x1800473bc  mov     [rdx+rax], bpl
0x1800473c0  jmp     short loc_1800473D1
0x1800473c2  sub     rdx, [rbx+10h]; Size
0x1800473c6  xor     r8d, r8d; char
0x1800473c9  mov     rcx, rbx; Src
0x1800473cc  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1800473d1  mov     ecx, [rbx+10h]
0x1800473d4  cmp     qword ptr [rbx+18h], 0Fh
0x1800473d9  jbe     short loc_1800473E0
0x1800473db  mov     rax, [rbx]
0x1800473de  jmp     short loc_1800473E3
0x1800473e0  mov     rax, rbx
0x1800473e3  mov     r9d, [rdi+10h]; cchWideChar
0x1800473e7  cmp     qword ptr [rdi+18h], 7
0x1800473ec  jbe     short loc_1800473F1
0x1800473ee  mov     rdi, [rdi]
0x1800473f1  mov     rsi, [rsp+58h]
0x1800473f6  mov     [rsp+58h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x1800473fb  mov     [rsp+58h+lpDefaultChar], rbp; lpDefaultChar
0x180047400  mov     [rsp+58h+cbMultiByte], ecx; cbMultiByte
0x180047404  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x180047409  mov     r8, rdi; lpWideCharStr
0x18004740c  xor     edx, edx; dwFlags
0x18004740e  mov     ecx, 0FDE9h; CodePage
0x180047413  call    cs:__imp_WideCharToMultiByte
0x180047419  test    eax, eax
0x18004741b  jz      short loc_18004742D
0x18004741d  mov     rax, rbx
0x180047420  mov     rbx, [rsp+58h+arg_10]
0x180047425  add     rsp, 40h
0x180047429  pop     rdi
0x18004742a  pop     rsi
0x18004742b  pop     rbp
0x18004742c  retn
0x18004742d  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180047434  mov     edx, 14Ch; void *
0x180047439  mov     rcx, rsi; this
0x18004743c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
