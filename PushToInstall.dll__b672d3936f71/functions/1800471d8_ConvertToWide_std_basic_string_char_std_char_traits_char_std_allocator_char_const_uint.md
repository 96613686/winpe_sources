# ConvertToWide(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint)

- ea: `0x1800471d8`
- end: `0x180047305`
- name: `?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z`
- size: `301`
- prototype: `void *__fastcall(void *Src, LPCCH lpMultiByteStr, UINT CodePage)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800374d4`

## callees

- `0x180030a68`
- `0x180030ca4`
- `0x1800471d8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047264`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800472d6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047264`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800472d6`

## string_xrefs

- `0x1800472f0`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall ConvertToWide(void *Src, LPCCH lpMultiByteStr, UINT CodePage)
{
  LPCCH v4; // rdi
  LPCCH v6; // rax
  const CHAR *v7; // r8
  int v8; // eax
  _WORD *v9; // rcx
  WCHAR *lpWideCharStr; // rax
  int v11; // r9d
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = lpMultiByteStr;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( *((_QWORD *)lpMultiByteStr + 2) )
  {
    v6 = *((_QWORD *)lpMultiByteStr + 3) <= 0xFu ? lpMultiByteStr : *(LPCCH *)lpMultiByteStr;
    if ( *v6 )
    {
      v7 = *((_QWORD *)lpMultiByteStr + 3) <= 0xFu ? lpMultiByteStr : *(const CHAR **)lpMultiByteStr;
      v8 = MultiByteToWideChar(CodePage, 0, v7, *((_DWORD *)lpMultiByteStr + 4), 0, 0);
      if ( v8 )
      {
        if ( (unsigned __int64)v8 > *((_QWORD *)Src + 2) )
        {
          std::wstring::append(Src);
        }
        else
        {
          *((_QWORD *)Src + 2) = v8;
          if ( *((_QWORD *)Src + 3) <= 7u )
            v9 = Src;
          else
            v9 = *(_WORD **)Src;
          v9[v8] = 0;
        }
        if ( *((_QWORD *)Src + 3) <= 7u )
          lpWideCharStr = (WCHAR *)Src;
        else
          lpWideCharStr = *(WCHAR **)Src;
        v11 = *((_DWORD *)v4 + 4);
        if ( *((_QWORD *)v4 + 3) > 0xFu )
          v4 = *(LPCCH *)v4;
        if ( !MultiByteToWideChar(CodePage, 0, v4, v11, lpWideCharStr, *((_DWORD *)Src + 4)) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x13D,
            (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
            v12);
      }
    }
  }
  return Src;
}

```

## disassembly

```asm
0x1800471d8  mov     [rsp+arg_10], rbx
0x1800471dd  mov     [rsp+arg_0], rcx
0x1800471e2  push    rbp
0x1800471e3  push    rsi
0x1800471e4  push    rdi
0x1800471e5  sub     rsp, 30h
0x1800471e9  mov     ebp, r8d
0x1800471ec  mov     rdi, rdx
0x1800471ef  mov     rbx, rcx
0x1800471f2  mov     ecx, 1
0x1800471f7  mov     [rsp+48h+arg_8], ecx
0x1800471fb  xorps   xmm0, xmm0
0x1800471fe  movups  xmmword ptr [rbx], xmm0
0x180047201  mov     qword ptr [rbx+10h], 0
0x180047209  mov     qword ptr [rbx+18h], 7
0x180047211  xor     eax, eax
0x180047213  mov     [rbx], ax
0x180047216  mov     [rsp+48h+arg_8], ecx
0x18004721a  cmp     [rdx+10h], rax
0x18004721e  jz      loc_1800472E0
0x180047224  cmp     qword ptr [rdx+18h], 0Fh
0x180047229  jbe     short loc_180047230
0x18004722b  mov     rax, [rdx]
0x18004722e  jmp     short loc_180047233
0x180047230  mov     rax, rdi
0x180047233  cmp     byte ptr [rax], 0
0x180047236  jz      loc_1800472E0
0x18004723c  cmp     qword ptr [rdx+18h], 0Fh
0x180047241  jbe     short loc_180047248
0x180047243  mov     r8, [rdx]
0x180047246  jmp     short loc_18004724B
0x180047248  mov     r8, rdi; lpMultiByteStr
0x18004724b  mov     [rsp+48h+cchWideChar], 0; cchWideChar
0x180047253  mov     [rsp+48h+lpWideCharStr], 0; lpWideCharStr
0x18004725c  mov     r9d, [rdx+10h]; cbMultiByte
0x180047260  xor     edx, edx; dwFlags
0x180047262  mov     ecx, ebp; CodePage
0x180047264  call    cs:__imp_MultiByteToWideChar
0x18004726a  test    eax, eax
0x18004726c  jz      short loc_1800472E0
0x18004726e  movsxd  rdx, eax
0x180047271  cmp     rdx, [rbx+10h]
0x180047275  ja      short loc_180047292
0x180047277  mov     [rbx+10h], rdx
0x18004727b  cmp     qword ptr [rbx+18h], 7
0x180047280  jbe     short loc_180047287
0x180047282  mov     rcx, [rbx]
0x180047285  jmp     short loc_18004728A
0x180047287  mov     rcx, rbx
0x18004728a  xor     eax, eax
0x18004728c  mov     [rcx+rdx*2], ax
0x180047290  jmp     short loc_1800472A1
0x180047292  xor     r8d, r8d
0x180047295  sub     rdx, [rbx+10h]
0x180047299  mov     rcx, rbx; Src
0x18004729c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800472a1  mov     ecx, [rbx+10h]
0x1800472a4  cmp     qword ptr [rbx+18h], 7
0x1800472a9  jbe     short loc_1800472B0
0x1800472ab  mov     rax, [rbx]
0x1800472ae  jmp     short loc_1800472B3
0x1800472b0  mov     rax, rbx
0x1800472b3  mov     r9d, [rdi+10h]; cbMultiByte
0x1800472b7  cmp     qword ptr [rdi+18h], 0Fh
0x1800472bc  jbe     short loc_1800472C1
0x1800472be  mov     rdi, [rdi]
0x1800472c1  mov     rsi, [rsp+48h]
0x1800472c6  mov     [rsp+48h+cchWideChar], ecx; cchWideChar
0x1800472ca  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x1800472cf  mov     r8, rdi; lpMultiByteStr
0x1800472d2  xor     edx, edx; dwFlags
0x1800472d4  mov     ecx, ebp; CodePage
0x1800472d6  call    cs:__imp_MultiByteToWideChar
0x1800472dc  test    eax, eax
0x1800472de  jz      short loc_1800472F0
0x1800472e0  mov     rax, rbx
0x1800472e3  mov     rbx, [rsp+48h+arg_10]
0x1800472e8  add     rsp, 30h
0x1800472ec  pop     rdi
0x1800472ed  pop     rsi
0x1800472ee  pop     rbp
0x1800472ef  retn
0x1800472f0  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800472f7  mov     edx, 13Dh; void *
0x1800472fc  mov     rcx, rsi; this
0x1800472ff  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
