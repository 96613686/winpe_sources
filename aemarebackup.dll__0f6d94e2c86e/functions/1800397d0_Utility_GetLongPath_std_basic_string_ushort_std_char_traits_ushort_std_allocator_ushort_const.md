# Utility::GetLongPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800397d0`
- end: `0x180039902`
- name: `?GetLongPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180042ddc`

## callees

- `0x180004ea0`
- `0x180011fcc`
- `0x1800134b8`
- `0x18002cd04`
- `0x1800397d0`
- `0x180044a1c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039809`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039809`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003984d`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180039885`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003984d`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180039885`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Utility::GetLongPath(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  const WCHAR *v4; // rcx
  WCHAR *v5; // rdx
  const WCHAR *v6; // rcx
  WCHAR *v7; // rdx
  LPWSTR lpszLongPath[2]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cchBuffer[4]; // [rsp+40h] [rbp-20h]

  v2 = a2;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v4 = (const WCHAR *)a2;
  else
    v4 = *(const WCHAR **)a2;
  if ( GetFileAttributesW(v4) == -1 )
  {
    std::wstring::wstring(a1, v2);
  }
  else
  {
    std::wstring::wstring(lpszLongPath, 260, 0);
    v5 = (WCHAR *)lpszLongPath;
    if ( *(_QWORD *)&cchBuffer[2] > 7u )
      v5 = lpszLongPath[0];
    if ( *(_QWORD *)(v2 + 24) <= 7u )
      v6 = (const WCHAR *)v2;
    else
      v6 = *(const WCHAR **)v2;
    if ( GetLongPathNameW(v6, v5, 0x104u) > 0x104 )
    {
      std::wstring::resize(lpszLongPath);
      v7 = (WCHAR *)lpszLongPath;
      if ( *(_QWORD *)&cchBuffer[2] > 7u )
        v7 = lpszLongPath[0];
      if ( *(_QWORD *)(v2 + 24) > 7u )
        v2 = *(_QWORD *)v2;
      GetLongPathNameW((LPCWSTR)v2, v7, cchBuffer[0]);
    }
    std::wstring::resize(lpszLongPath);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)lpszLongPath;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cchBuffer;
    *(_QWORD *)cchBuffer = 0;
    *(_QWORD *)&cchBuffer[2] = 7;
    LOWORD(lpszLongPath[0]) = 0;
    std::wstring::~wstring((char **)lpszLongPath);
  }
  return a1;
}

```

## disassembly

```asm
0x1800397d0  mov     [rsp-8+arg_10], rbx
0x1800397d5  mov     [rsp-8+arg_18], rdi
0x1800397da  push    rbp
0x1800397db  mov     rbp, rsp
0x1800397de  sub     rsp, 60h
0x1800397e2  mov     rax, cs:__security_cookie
0x1800397e9  xor     rax, rsp
0x1800397ec  mov     [rbp+var_10], rax
0x1800397f0  mov     rbx, rdx
0x1800397f3  mov     rdi, rcx
0x1800397f6  mov     [rbp+var_38], rcx
0x1800397fa  cmp     qword ptr [rdx+18h], 7
0x1800397ff  jbe     short loc_180039806
0x180039801  mov     rcx, [rdx]
0x180039804  jmp     short loc_180039809
0x180039806  mov     rcx, rbx; lpFileName
0x180039809  call    cs:__imp_GetFileAttributesW
0x18003980f  cmp     eax, 0FFFFFFFFh
0x180039812  jz      loc_1800398D6
0x180039818  xor     r8d, r8d
0x18003981b  mov     edx, 104h
0x180039820  lea     rcx, [rbp+lpszLongPath]
0x180039824  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180039829  nop
0x18003982a  lea     rdx, [rbp+lpszLongPath]
0x18003982e  cmp     qword ptr [rbp+cchBuffer+8], 7
0x180039833  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x180039838  cmp     qword ptr [rbx+18h], 7
0x18003983d  jbe     short loc_180039844
0x18003983f  mov     rcx, [rbx]
0x180039842  jmp     short loc_180039847
0x180039844  mov     rcx, rbx; lpszShortPath
0x180039847  mov     r8d, 104h; cchBuffer
0x18003984d  call    cs:__imp_GetLongPathNameW
0x180039853  cmp     eax, 104h
0x180039858  jbe     short loc_18003988B
0x18003985a  lea     edx, [rax+1]
0x18003985d  lea     rcx, [rbp+lpszLongPath]; Src
0x180039861  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180039866  lea     rdx, [rbp+lpszLongPath]
0x18003986a  cmp     qword ptr [rbp+cchBuffer+8], 7
0x18003986f  cmova   rdx, [rbp+lpszLongPath]; lpszLongPath
0x180039874  cmp     qword ptr [rbx+18h], 7
0x180039879  jbe     short loc_18003987E
0x18003987b  mov     rbx, [rbx]
0x18003987e  mov     r8d, [rbp+cchBuffer]; cchBuffer
0x180039882  mov     rcx, rbx; lpszShortPath
0x180039885  call    cs:__imp_GetLongPathNameW
0x18003988b  mov     edx, eax
0x18003988d  lea     rcx, [rbp+lpszLongPath]; Src
0x180039891  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180039896  mov     qword ptr [rdi+10h], 0
0x18003989e  mov     qword ptr [rdi+18h], 0
0x1800398a6  movups  xmm0, xmmword ptr [rbp+lpszLongPath]
0x1800398aa  movups  xmmword ptr [rdi], xmm0
0x1800398ad  movups  xmm1, xmmword ptr [rbp+cchBuffer]
0x1800398b1  movups  xmmword ptr [rdi+10h], xmm1
0x1800398b5  mov     qword ptr [rbp+cchBuffer], 0
0x1800398bd  mov     qword ptr [rbp+cchBuffer+8], 7
0x1800398c5  xor     ecx, ecx
0x1800398c7  mov     word ptr [rbp+lpszLongPath], cx
0x1800398cb  lea     rcx, [rbp+lpszLongPath]
0x1800398cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800398d4  jmp     short loc_1800398E1
0x1800398d6  mov     rdx, rbx
0x1800398d9  mov     rcx, rdi
0x1800398dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800398e1  mov     rax, rdi
0x1800398e4  mov     rcx, [rbp+var_10]
0x1800398e8  xor     rcx, rsp; StackCookie
0x1800398eb  call    __security_check_cookie
0x1800398f0  lea     r11, [rsp+60h+var_s0]
0x1800398f5  mov     rbx, [r11+20h]
0x1800398f9  mov     rdi, [r11+28h]
0x1800398fd  mov     rsp, r11
0x180039900  pop     rbp
0x180039901  retn
```
