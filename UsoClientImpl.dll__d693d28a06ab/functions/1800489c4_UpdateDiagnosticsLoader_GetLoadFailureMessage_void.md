# UpdateDiagnosticsLoader::GetLoadFailureMessage(void)

- ea: `0x1800489c4`
- end: `0x180048b02`
- name: `?GetLoadFailureMessage@UpdateDiagnosticsLoader@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180048fe4`

## callees

- `0x180009380`
- `0x18002f1f0`
- `0x1800338a4`
- `0x1800489c4`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048a1c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048a1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ad4`

## string_xrefs

- `0x180048a42`: `UPDIAG.DLL: `
- `0x180048ab7`: `!UPDIAG.DLL\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdateDiagnosticsLoader::GetLoadFailureMessage(__int64 a1)
{
  _WORD *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // rax
  HLOCAL v5; // rcx
  bool v6; // zf
  _OWORD Src[2]; // [rsp+48h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF

  hMem = 0;
  if ( FormatMessageW(0x1300u, 0, 0x485u, 0x400u, (LPWSTR)&hMem, 0, 0) && (v2 = hMem) != 0 )
  {
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,wchar_t const *>(Src);
    v3 = -1;
    do
      ++v3;
    while ( v2[v3] );
    v4 = std::wstring::append(Src);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v4;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v4 + 16);
    *(_WORD *)v4 = 0;
    *(_QWORD *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 7;
    std::wstring::~wstring(Src);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a1);
  }
  v5 = hMem;
  v6 = hMem == 0;
  hMem = 0;
  if ( !v6 )
    LocalFree(v5);
  return a1;
}

```

## disassembly

```asm
0x1800489c4  mov     r11, rsp
0x1800489c7  mov     [r11+10h], rbx
0x1800489cb  mov     [r11+18h], rsi
0x1800489cf  mov     [r11+20h], rdi
0x1800489d3  push    rbp
0x1800489d4  mov     rbp, rsp
0x1800489d7  sub     rsp, 80h
0x1800489de  mov     rax, cs:__security_cookie
0x1800489e5  xor     rax, rsp
0x1800489e8  mov     [rbp+var_10], rax
0x1800489ec  mov     rbx, rcx
0x1800489ef  mov     [rbp+hMem], rcx
0x1800489f3  xor     esi, esi
0x1800489f5  mov     [rbp+hMem], rsi
0x1800489f9  mov     [r11-58h], rsi
0x1800489fd  mov     [rsp+80h+nSize], esi; nSize
0x180048a01  lea     rax, [rbp+hMem]
0x180048a05  mov     [r11-68h], rax
0x180048a09  xor     edx, edx; lpSource
0x180048a0b  mov     ecx, 1300h; dwFlags
0x180048a10  mov     r9d, 400h; dwLanguageId
0x180048a16  mov     r8d, 485h; dwMessageId
0x180048a1c  call    cs:__imp_FormatMessageW
0x180048a22  test    eax, eax
0x180048a24  jz      short loc_180048AA3
0x180048a26  mov     rdi, [rbp+hMem]
0x180048a2a  test    rdi, rdi
0x180048a2d  jz      short loc_180048AA3
0x180048a2f  xorps   xmm0, xmm0
0x180048a32  movups  [rbp+Src], xmm0
0x180048a36  xorps   xmm1, xmm1
0x180048a39  movdqu  [rbp+var_28], xmm1
0x180048a3e  lea     r8d, [rsi+0Ch]
0x180048a42  lea     rdx, aUpdiagDll_0; "UPDIAG.DLL: "
0x180048a49  lea     rcx, [rbp+Src]
0x180048a4d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180048a52  nop
0x180048a53  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048a57  inc     r8
0x180048a5a  cmp     [rdi+r8*2], si
0x180048a5f  jnz     short loc_180048A57
0x180048a61  mov     rdx, rdi
0x180048a64  lea     rcx, [rbp+Src]; Src
0x180048a68  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180048a6d  xorps   xmm0, xmm0
0x180048a70  movups  xmmword ptr [rbx], xmm0
0x180048a73  mov     [rbx+10h], rsi
0x180048a77  mov     [rbx+18h], rsi
0x180048a7b  movups  xmm0, xmmword ptr [rax]
0x180048a7e  movups  xmmword ptr [rbx], xmm0
0x180048a81  movups  xmm1, xmmword ptr [rax+10h]
0x180048a85  movups  xmmword ptr [rbx+10h], xmm1
0x180048a89  mov     [rax], si
0x180048a8c  mov     [rax+10h], rsi
0x180048a90  mov     qword ptr [rax+18h], 7
0x180048a98  lea     rcx, [rbp+Src]; void *
0x180048a9c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048aa1  jmp     short loc_180048AC7
0x180048aa3  xorps   xmm0, xmm0
0x180048aa6  movups  xmmword ptr [rbx], xmm0
0x180048aa9  mov     [rbx+10h], rsi
0x180048aad  mov     [rbx+18h], rsi
0x180048ab1  mov     r8d, 0Ch
0x180048ab7  lea     rdx, aUpdiagDll; "!UPDIAG.DLL\n"
0x180048abe  mov     rcx, rbx
0x180048ac1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180048ac6  nop
0x180048ac7  mov     rcx, [rbp+hMem]; hMem
0x180048acb  test    rcx, rcx
0x180048ace  mov     [rbp+hMem], rsi
0x180048ad2  jz      short loc_180048ADA
0x180048ad4  call    cs:__imp_LocalFree
0x180048ada  mov     rax, rbx
0x180048add  mov     rcx, [rbp+var_10]
0x180048ae1  xor     rcx, rsp; StackCookie
0x180048ae4  call    __security_check_cookie
0x180048ae9  lea     r11, [rsp+80h+var_s0]
0x180048af1  mov     rbx, [r11+18h]
0x180048af5  mov     rsi, [r11+20h]
0x180048af9  mov     rdi, [r11+28h]
0x180048afd  mov     rsp, r11
0x180048b00  pop     rbp
0x180048b01  retn
```
