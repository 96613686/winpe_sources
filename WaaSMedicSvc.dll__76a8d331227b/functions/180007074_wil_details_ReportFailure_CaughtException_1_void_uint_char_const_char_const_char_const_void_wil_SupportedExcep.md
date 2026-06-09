# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180007074`
- end: `0x1800071bf`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a8f8`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x18000300c`
- `0x18000306c`
- `0x180004ebc`
- `0x180007074`
- `0x18000bd40`
- `0x18000d010`

## string_xrefs

- `0x180007134`: `onecore\enduser\windowsupdate\undocked\stubdlls\dllexports.cpp`
- `0x18000718d`: `onecore\enduser\windowsupdate\undocked\stubdlls\dllexports.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  __int64 v8; // rcx
  unsigned __int64 *v9; // rax
  __m128i v10; // xmm0
  int v11; // esi
  int v13; // r9d
  int v14; // [rsp+20h] [rbp-E0h]
  _BYTE v15[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v19[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v15[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v19[v8] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v18, &v19[v8], 2048 - v8, v15),
        v10 = (__m128i)*v9,
        LODWORD(v9) = *((_DWORD *)v9 + 2),
        v11 = _mm_cvtsi128_si32(v10),
        v16 = v10.m128i_i64[0],
        v17 = (int)v9,
        v11 >= 0) )
  {
    LODWORD(v16) = -2147024322;
    HIDWORD(v16) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v17 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      71,
      (int)"onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\dllexports.cpp",
      v13,
      v14,
      a6,
      (__int64)&v16,
      (__int64)v19);
  }
  wil::details::ReportFailure_Base<1,0>(a1, 71, "onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\dllexports.cpp");
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007074  mov     [rsp-8+arg_8], rbx
0x180007079  mov     [rsp-8+arg_10], rsi
0x18000707e  push    rbp
0x18000707f  push    rdi
0x180007080  push    r14
0x180007082  lea     rbp, [rsp-0F90h]
0x18000708a  mov     eax, 1090h
0x18000708f  call    _alloca_probe
0x180007094  sub     rsp, rax
0x180007097  mov     rax, cs:__security_cookie
0x18000709e  xor     rax, rsp
0x1800070a1  mov     [rbp+0FA0h+var_20], rax
0x1800070a8  mov     rdi, [rbp+0FA0h+arg_28]
0x1800070af  mov     rbx, rcx
0x1800070b2  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1800070b6  xor     edx, edx; Val
0x1800070b8  mov     r8d, 1000h; Size
0x1800070be  call    memset_0
0x1800070c3  xor     r14d, r14d
0x1800070c6  lea     rax, [rbp+0FA0h+var_1020]
0x1800070ca  mov     [rsp+10A0h+var_1050], r14b
0x1800070cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800070d3  inc     rcx
0x1800070d6  cmp     [rax+rcx*2], r14w
0x1800070db  jnz     short loc_1800070D3
0x1800070dd  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800070e4  test    rax, rax
0x1800070e7  jz      loc_18000717B
0x1800070ed  mov     r8d, 800h
0x1800070f3  lea     rdx, [rbp+0FA0h+var_1020]
0x1800070f7  sub     r8, rcx
0x1800070fa  lea     rdx, [rdx+rcx*2]
0x1800070fe  lea     rcx, [rsp+10A0h+var_1038]
0x180007103  lea     r9, [rsp+10A0h+var_1050]
0x180007108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000710d  movsd   xmm0, qword ptr [rax]
0x180007111  mov     eax, [rax+8]
0x180007114  movd    esi, xmm0
0x180007118  movsd   [rsp+10A0h+var_1048], xmm0
0x18000711e  mov     [rsp+10A0h+var_1040], eax
0x180007122  test    esi, esi
0x180007124  jns     short loc_18000717B
0x180007126  lea     rax, [rbp+0FA0h+var_1020]
0x18000712a  mov     edx, 47h ; 'G'
0x18000712f  mov     [rsp+10A0h+var_1068], rax
0x180007134  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x18000713b  lea     rax, [rsp+10A0h+var_1048]
0x180007140  mov     rcx, rbx
0x180007143  mov     [rsp+10A0h+var_1070], rax
0x180007148  mov     [rsp+10A0h+var_1078], rdi
0x18000714d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007152  mov     eax, esi
0x180007154  mov     rcx, [rbp+0FA0h+var_20]
0x18000715b  xor     rcx, rsp; StackCookie
0x18000715e  call    __security_check_cookie
0x180007163  lea     r11, [rsp+10A0h+var_10]
0x18000716b  mov     rbx, [r11+28h]
0x18000716f  mov     rsi, [r11+30h]
0x180007173  mov     rsp, r11
0x180007176  pop     r14
0x180007178  pop     rdi
0x180007179  pop     rbp
0x18000717a  retn
0x18000717b  mov     ecx, 8007023Eh; this
0x180007180  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x180007184  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007189  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x18000718d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\undock"...
0x180007194  lea     rax, [rbp+0FA0h+var_1020]
0x180007198  mov     [rsp+10A0h+var_1040], r14d
0x18000719d  mov     [rsp+10A0h+var_1068], rax
0x1800071a2  mov     edx, 47h ; 'G'
0x1800071a7  lea     rax, [rsp+10A0h+var_1048]
0x1800071ac  mov     rcx, rbx
0x1800071af  mov     [rsp+10A0h+var_1070], rax
0x1800071b4  mov     [rsp+10A0h+var_1078], rdi
0x1800071b9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
