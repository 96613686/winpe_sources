# Utility::GetLongPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800cd0f8`
- end: `0x1800cd227`
- name: `?GetLongPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800ceeb4`

## callees

- `0x180005890`
- `0x18000faac`
- `0x18001c5f0`
- `0x1800ca464`
- `0x1800cd0f8`
- `0x1800d00c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cd131`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cd131`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800cd172`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800cd1aa`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800cd172`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800cd1aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Utility::GetLongPath(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  const WCHAR *v4; // rcx
  WCHAR *v5; // rdx
  const WCHAR *v6; // rcx
  DWORD LongPathNameW; // eax
  WCHAR *v8; // rdx
  LPWSTR lpszLongPath[2]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchBuffer[4]; // [rsp+40h] [rbp-20h]

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  if ( GetFileAttributesW(v4) == -1 )
  {
    std::wstring::wstring(a1, v2);
  }
  else
  {
    std::wstring::wstring(lpszLongPath, 260);
    v5 = (WCHAR *)lpszLongPath;
    if ( *(_QWORD *)&cchBuffer[2] > 7u )
      v5 = lpszLongPath[0];
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v6 = v2;
    else
      v6 = *(const WCHAR **)v2;
    LongPathNameW = GetLongPathNameW(v6, v5, 0x104u);
    if ( LongPathNameW > 0x104 )
    {
      std::wstring::resize(lpszLongPath, LongPathNameW + 1);
      v8 = (WCHAR *)lpszLongPath;
      if ( *(_QWORD *)&cchBuffer[2] > 7u )
        v8 = lpszLongPath[0];
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(const WCHAR **)v2;
      LongPathNameW = GetLongPathNameW(v2, v8, cchBuffer[0]);
    }
    std::wstring::resize(lpszLongPath, LongPathNameW);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)lpszLongPath;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cchBuffer;
    *(_QWORD *)cchBuffer = 0;
    *(_QWORD *)&cchBuffer[2] = 7;
    LOWORD(lpszLongPath[0]) = 0;
    std::wstring::_Tidy_deallocate(lpszLongPath);
  }
  return a1;
}

```

## disassembly

```asm
0x1800cd0f8  mov     [rsp-8+arg_10], rbx
0x1800cd0fd  mov     [rsp-8+arg_18], rdi
0x1800cd102  push    rbp
0x1800cd103  mov     rbp, rsp
0x1800cd106  sub     rsp, 60h
0x1800cd10a  mov     rax, cs:__security_cookie
0x1800cd111  xor     rax, rsp
0x1800cd114  mov     [rbp+var_10], rax
0x1800cd118  mov     rbx, rdx
0x1800cd11b  mov     rdi, rcx
0x1800cd11e  mov     [rbp+var_38], rcx
0x1800cd122  cmp     qword ptr [rdx+18h], 7
0x1800cd127  jbe     short loc_1800CD12E
0x1800cd129  mov     rcx, [rdx]
0x1800cd12c  jmp     short loc_1800CD131
0x1800cd12e  mov     rcx, rbx; lpFileName
0x1800cd131  call    cs:__imp_GetFileAttributesW
0x1800cd137  cmp     eax, 0FFFFFFFFh
0x1800cd13a  jz      loc_1800CD1FB
0x1800cd140  mov     edx, 104h
0x1800cd145  lea     rcx, [rbp+lpszLongPath]
0x1800cd149  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800cd14e  nop
0x1800cd14f  lea     rdx, [rbp+lpszLongPath]
0x1800cd153  cmp     qword ptr [rbp+cchBuffer+8], 7
0x1800cd158  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x1800cd15d  cmp     qword ptr [rbx+18h], 7
0x1800cd162  jbe     short loc_1800CD169
0x1800cd164  mov     rcx, [rbx]
0x1800cd167  jmp     short loc_1800CD16C
0x1800cd169  mov     rcx, rbx; lpszShortPath
0x1800cd16c  mov     r8d, 104h; cchBuffer
0x1800cd172  call    cs:__imp_GetLongPathNameW
0x1800cd178  cmp     eax, 104h
0x1800cd17d  jbe     short loc_1800CD1B0
0x1800cd17f  lea     edx, [rax+1]
0x1800cd182  lea     rcx, [rbp+lpszLongPath]
0x1800cd186  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cd18b  lea     rdx, [rbp+lpszLongPath]
0x1800cd18f  cmp     qword ptr [rbp+cchBuffer+8], 7
0x1800cd194  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x1800cd199  cmp     qword ptr [rbx+18h], 7
0x1800cd19e  jbe     short loc_1800CD1A3
0x1800cd1a0  mov     rbx, [rbx]
0x1800cd1a3  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x1800cd1a7  mov     rcx, rbx; lpszShortPath
0x1800cd1aa  call    cs:__imp_GetLongPathNameW
0x1800cd1b0  mov     edx, eax
0x1800cd1b2  lea     rcx, [rbp+lpszLongPath]
0x1800cd1b6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cd1bb  mov     qword ptr [rdi+10h], 0
0x1800cd1c3  mov     qword ptr [rdi+18h], 0
0x1800cd1cb  movups  xmm0, xmmword ptr [rbp+lpszLongPath]
0x1800cd1cf  movups  xmmword ptr [rdi], xmm0
0x1800cd1d2  movups  xmm1, xmmword ptr [rbp+cchBuffer]
0x1800cd1d6  movups  xmmword ptr [rdi+10h], xmm1
0x1800cd1da  mov     qword ptr [rbp+cchBuffer], 0
0x1800cd1e2  mov     qword ptr [rbp+cchBuffer+8], 7
0x1800cd1ea  xor     ecx, ecx
0x1800cd1ec  mov     word ptr [rbp+lpszLongPath], cx
0x1800cd1f0  lea     rcx, [rbp+lpszLongPath]
0x1800cd1f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd1f9  jmp     short loc_1800CD206
0x1800cd1fb  mov     rdx, rbx
0x1800cd1fe  mov     rcx, rdi
0x1800cd201  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800cd206  mov     rax, rdi
0x1800cd209  mov     rcx, [rbp+var_10]
0x1800cd20d  xor     rcx, rsp; StackCookie
0x1800cd210  call    __security_check_cookie
0x1800cd215  lea     r11, [rsp+60h+var_s0]
0x1800cd21a  mov     rbx, [r11+20h]
0x1800cd21e  mov     rdi, [r11+28h]
0x1800cd222  mov     rsp, r11
0x1800cd225  pop     rbp
0x1800cd226  retn
```
