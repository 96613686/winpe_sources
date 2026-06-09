# CJsonHelper::AsString(ushort * *)

- ea: `0x180033404`
- end: `0x18003365e`
- name: `?AsString@CJsonHelper@@QEAAJPEAPEAG@Z`
- size: `602`
- prototype: `int(CJsonHelper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180035140`

## callees

- `0x18000bbd4`
- `0x18002a32c`
- `0x180033404`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003358b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003358b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003355c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003355c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800335e9`

## string_xrefs

- `0x180033430`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18003347e`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x1800334de`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x180033546`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x1800335a9`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18003361d`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CJsonHelper::AsString(CJsonHelper *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // r9
  int v5; // eax
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rcx
  WaasMedic *StringRawBuffer; // rax
  unsigned __int16 **v15; // r8
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v23; // [rsp+48h] [rbp+28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
      (const char *)0x80004003LL,
      savedregs);
    return v3;
  }
  *a2 = 0;
  v23 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = (**v4)(*((_QWORD *)this + 1), &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v23);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
        (const char *)(unsigned int)v5,
        savedregs);
      v6 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      return v3;
    }
  }
  else
  {
    v7 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this;
    if ( !v7 )
    {
      v3 = -2147467261;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
        (const char *)0x80004003LL,
        savedregs);
      v20 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      return v3;
    }
    v8 = (**v7)(v7, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v23);
    v3 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
        (const char *)(unsigned int)v8,
        savedregs);
      v9 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return v3;
    }
  }
  string = 0;
  v10 = v23;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v12 = v11(v10, &string);
  v3 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
      (const char *)(unsigned int)v12,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    v13 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v3;
  }
  StringRawBuffer = (WaasMedic *)WindowsGetStringRawBuffer(string, 0);
  v16 = WaasMedic::SafeAllocString(StringRawBuffer, (const unsigned __int16 *)a2, v15);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\jsonhelper.cpp",
      (const char *)(unsigned int)v16,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v3;
  }
  WindowsDeleteString(string);
  string = 0;
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180033404  mov     [rsp-18h+arg_0], rbx
0x180033409  mov     [rsp-18h+arg_18], rsi
0x18003340e  push    rbp
0x18003340f  push    rdi
0x180033410  push    r14; int
0x180033412  mov     rbp, rsp
0x180033415  sub     rsp, 20h
0x180033419  mov     rsi, rdx
0x18003341c  xor     r14d, r14d
0x18003341f  test    rdx, rdx
0x180033422  jnz     short loc_180033444
0x180033424  mov     rcx, [rbp+18h]; this
0x180033428  mov     ebx, 80004003h
0x18003342d  mov     r9d, ebx; char *
0x180033430  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180033437  lea     edx, [rsi+45h]; void *
0x18003343a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003343f  jmp     loc_180033649
0x180033444  mov     [rdx], r14
0x180033447  mov     [rbp+arg_8], r14
0x18003344b  mov     r9, [rcx+8]
0x18003344f  test    r9, r9
0x180033452  jz      short loc_1800334AF
0x180033454  mov     rax, [r9]
0x180033457  lea     r8, [rbp+arg_8]
0x18003345b  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180033462  mov     rcx, r9
0x180033465  mov     rax, [rax]
0x180033468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003346d  mov     ebx, eax
0x18003346f  test    eax, eax
0x180033471  jns     loc_18003350F
0x180033477  mov     rcx, [rbp+18h]; this
0x18003347b  mov     r9d, eax; char *
0x18003347e  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180033485  mov     edx, 4Bh ; 'K'; void *
0x18003348a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003348f  nop
0x180033490  mov     rcx, [rbp+arg_8]
0x180033494  test    rcx, rcx
0x180033497  jz      short loc_1800334AA
0x180033499  mov     [rbp+arg_8], r14
0x18003349d  mov     rax, [rcx]
0x1800334a0  mov     rax, [rax+10h]
0x1800334a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334a9  nop
0x1800334aa  jmp     loc_180033649
0x1800334af  mov     rcx, [rcx]
0x1800334b2  test    rcx, rcx
0x1800334b5  jz      loc_180033611
0x1800334bb  mov     rax, [rcx]
0x1800334be  lea     r8, [rbp+arg_8]
0x1800334c2  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800334c9  mov     rax, [rax]
0x1800334cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334d1  mov     ebx, eax
0x1800334d3  test    eax, eax
0x1800334d5  jns     short loc_18003350F
0x1800334d7  mov     rcx, [rbp+18h]; this
0x1800334db  mov     r9d, eax; char *
0x1800334de  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800334e5  mov     edx, 4Fh ; 'O'; void *
0x1800334ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334ef  nop
0x1800334f0  mov     rcx, [rbp+arg_8]
0x1800334f4  test    rcx, rcx
0x1800334f7  jz      short loc_18003350A
0x1800334f9  mov     [rbp+arg_8], r14
0x1800334fd  mov     rax, [rcx]
0x180033500  mov     rax, [rax+10h]
0x180033504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033509  nop
0x18003350a  jmp     loc_180033649
0x18003350f  mov     [rbp+string], r14
0x180033513  mov     rdi, [rbp+arg_8]
0x180033517  mov     rax, [rdi]
0x18003351a  mov     rbx, [rax+38h]
0x18003351e  xor     ecx, ecx; string
0x180033520  call    cs:__imp_WindowsDeleteString
0x180033526  mov     [rbp+string], r14
0x18003352a  lea     rdx, [rbp+string]
0x18003352e  mov     rcx, rdi
0x180033531  mov     rax, rbx
0x180033534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033539  mov     ebx, eax
0x18003353b  test    eax, eax
0x18003353d  jns     short loc_180033585
0x18003353f  mov     rcx, [rbp+18h]; this
0x180033543  mov     r9d, eax; char *
0x180033546  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003354d  mov     edx, 57h ; 'W'; void *
0x180033552  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033557  nop
0x180033558  mov     rcx, [rbp+string]; string
0x18003355c  call    cs:__imp_WindowsDeleteString
0x180033562  mov     [rbp+string], r14
0x180033566  mov     rcx, [rbp+arg_8]
0x18003356a  test    rcx, rcx
0x18003356d  jz      short loc_180033580
0x18003356f  mov     [rbp+arg_8], r14
0x180033573  mov     rax, [rcx]
0x180033576  mov     rax, [rax+10h]
0x18003357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003357f  nop
0x180033580  jmp     loc_180033649
0x180033585  xor     edx, edx; length
0x180033587  mov     rcx, [rbp+string]; string
0x18003358b  call    cs:__imp_WindowsGetStringRawBuffer
0x180033591  mov     rdx, rsi; unsigned __int16 *
0x180033594  mov     rcx, rax; this
0x180033597  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x18003359c  mov     ebx, eax
0x18003359e  test    eax, eax
0x1800335a0  jns     short loc_1800335E5
0x1800335a2  mov     rcx, [rbp+18h]; this
0x1800335a6  mov     r9d, eax; char *
0x1800335a9  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800335b0  mov     edx, 58h ; 'X'; void *
0x1800335b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335ba  nop
0x1800335bb  mov     rcx, [rbp+string]; string
0x1800335bf  call    cs:__imp_WindowsDeleteString
0x1800335c5  mov     [rbp+string], r14
0x1800335c9  mov     rcx, [rbp+arg_8]
0x1800335cd  test    rcx, rcx
0x1800335d0  jz      short loc_1800335E3
0x1800335d2  mov     [rbp+arg_8], r14
0x1800335d6  mov     rax, [rcx]
0x1800335d9  mov     rax, [rax+10h]
0x1800335dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335e2  nop
0x1800335e3  jmp     short loc_180033649
0x1800335e5  mov     rcx, [rbp+string]; string
0x1800335e9  call    cs:__imp_WindowsDeleteString
0x1800335ef  mov     [rbp+string], r14
0x1800335f3  mov     rcx, [rbp+arg_8]
0x1800335f7  test    rcx, rcx
0x1800335fa  jz      short loc_18003360D
0x1800335fc  mov     [rbp+arg_8], r14
0x180033600  mov     rax, [rcx]
0x180033603  mov     rax, [rax+10h]
0x180033607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003360c  nop
0x18003360d  xor     eax, eax
0x18003360f  jmp     short loc_18003364B
0x180033611  mov     rcx, [rbp+18h]; this
0x180033615  mov     ebx, 80004003h
0x18003361a  mov     r9d, ebx; char *
0x18003361d  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180033624  mov     edx, 53h ; 'S'; void *
0x180033629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003362e  nop
0x18003362f  mov     rcx, [rbp+arg_8]
0x180033633  test    rcx, rcx
0x180033636  jz      short loc_180033649
0x180033638  mov     [rbp+arg_8], r14
0x18003363c  mov     rax, [rcx]
0x18003363f  mov     rax, [rax+10h]
0x180033643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033648  nop
0x180033649  mov     eax, ebx
0x18003364b  mov     rbx, [rsp+20h+arg_0]
0x180033650  mov     rsi, [rsp+20h+arg_18]
0x180033655  add     rsp, 20h
0x180033659  pop     r14
0x18003365b  pop     rdi
0x18003365c  pop     rbp
0x18003365d  retn
```
