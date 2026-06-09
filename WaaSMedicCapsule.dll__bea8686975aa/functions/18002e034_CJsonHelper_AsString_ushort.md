# CJsonHelper::AsString(ushort * *)

- ea: `0x18002e034`
- end: `0x18002e28e`
- name: `?AsString@CJsonHelper@@QEAAJPEAPEAG@Z`
- size: `602`
- prototype: `int(CJsonHelper *__hidden this, unsigned __int16 **)`
- caller_count: `22`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000d170`
- `0x18002e4c4`
- `0x18002e66c`
- `0x18002e814`
- `0x180038150`
- `0x18003b290`
- `0x18003c4e0`
- `0x18003efa0`
- `0x1800405a0`
- `0x1800412d0`
- `0x1800433f0`
- `0x180044320`
- `0x1800463c0`
- `0x18004b760`
- `0x18004dba0`
- `0x18004e930`
- `0x18004f290`
- `0x18004fc40`
- `0x180050ce0`
- `0x1800517a0`
- `0x180053870`
- `0x1800552d0`

## callees

- `0x180009a54`
- `0x180024ff0`
- `0x18002e034`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e1bb`

## string_xrefs

- `0x18002e060`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18002e0ae`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18002e10e`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18002e176`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18002e1d9`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`
- `0x18002e24d`: `onecore\enduser\waasmedic\lib\util\jsonhelper.cpp`

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
0x18002e034  mov     [rsp-18h+arg_0], rbx
0x18002e039  mov     [rsp-18h+arg_18], rsi
0x18002e03e  push    rbp
0x18002e03f  push    rdi
0x18002e040  push    r14; int
0x18002e042  mov     rbp, rsp
0x18002e045  sub     rsp, 20h
0x18002e049  mov     rsi, rdx
0x18002e04c  xor     r14d, r14d
0x18002e04f  test    rdx, rdx
0x18002e052  jnz     short loc_18002E074
0x18002e054  mov     rcx, [rbp+18h]; this
0x18002e058  mov     ebx, 80004003h
0x18002e05d  mov     r9d, ebx; char *
0x18002e060  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e067  lea     edx, [rsi+45h]; void *
0x18002e06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e06f  jmp     loc_18002E279
0x18002e074  mov     [rdx], r14
0x18002e077  mov     [rbp+arg_8], r14
0x18002e07b  mov     r9, [rcx+8]
0x18002e07f  test    r9, r9
0x18002e082  jz      short loc_18002E0DF
0x18002e084  mov     rax, [r9]
0x18002e087  lea     r8, [rbp+arg_8]
0x18002e08b  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18002e092  mov     rcx, r9
0x18002e095  mov     rax, [rax]
0x18002e098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e09d  mov     ebx, eax
0x18002e09f  test    eax, eax
0x18002e0a1  jns     loc_18002E13F
0x18002e0a7  mov     rcx, [rbp+18h]; this
0x18002e0ab  mov     r9d, eax; char *
0x18002e0ae  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e0b5  mov     edx, 4Bh ; 'K'; void *
0x18002e0ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e0bf  nop
0x18002e0c0  mov     rcx, [rbp+arg_8]
0x18002e0c4  test    rcx, rcx
0x18002e0c7  jz      short loc_18002E0DA
0x18002e0c9  mov     [rbp+arg_8], r14
0x18002e0cd  mov     rax, [rcx]
0x18002e0d0  mov     rax, [rax+10h]
0x18002e0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0d9  nop
0x18002e0da  jmp     loc_18002E279
0x18002e0df  mov     rcx, [rcx]
0x18002e0e2  test    rcx, rcx
0x18002e0e5  jz      loc_18002E241
0x18002e0eb  mov     rax, [rcx]
0x18002e0ee  lea     r8, [rbp+arg_8]
0x18002e0f2  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18002e0f9  mov     rax, [rax]
0x18002e0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e101  mov     ebx, eax
0x18002e103  test    eax, eax
0x18002e105  jns     short loc_18002E13F
0x18002e107  mov     rcx, [rbp+18h]; this
0x18002e10b  mov     r9d, eax; char *
0x18002e10e  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e115  mov     edx, 4Fh ; 'O'; void *
0x18002e11a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e11f  nop
0x18002e120  mov     rcx, [rbp+arg_8]
0x18002e124  test    rcx, rcx
0x18002e127  jz      short loc_18002E13A
0x18002e129  mov     [rbp+arg_8], r14
0x18002e12d  mov     rax, [rcx]
0x18002e130  mov     rax, [rax+10h]
0x18002e134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e139  nop
0x18002e13a  jmp     loc_18002E279
0x18002e13f  mov     [rbp+string], r14
0x18002e143  mov     rdi, [rbp+arg_8]
0x18002e147  mov     rax, [rdi]
0x18002e14a  mov     rbx, [rax+38h]
0x18002e14e  xor     ecx, ecx; string
0x18002e150  call    cs:__imp_WindowsDeleteString
0x18002e156  mov     [rbp+string], r14
0x18002e15a  lea     rdx, [rbp+string]
0x18002e15e  mov     rcx, rdi
0x18002e161  mov     rax, rbx
0x18002e164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e169  mov     ebx, eax
0x18002e16b  test    eax, eax
0x18002e16d  jns     short loc_18002E1B5
0x18002e16f  mov     rcx, [rbp+18h]; this
0x18002e173  mov     r9d, eax; char *
0x18002e176  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e17d  mov     edx, 57h ; 'W'; void *
0x18002e182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e187  nop
0x18002e188  mov     rcx, [rbp+string]; string
0x18002e18c  call    cs:__imp_WindowsDeleteString
0x18002e192  mov     [rbp+string], r14
0x18002e196  mov     rcx, [rbp+arg_8]
0x18002e19a  test    rcx, rcx
0x18002e19d  jz      short loc_18002E1B0
0x18002e19f  mov     [rbp+arg_8], r14
0x18002e1a3  mov     rax, [rcx]
0x18002e1a6  mov     rax, [rax+10h]
0x18002e1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1af  nop
0x18002e1b0  jmp     loc_18002E279
0x18002e1b5  xor     edx, edx; length
0x18002e1b7  mov     rcx, [rbp+string]; string
0x18002e1bb  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e1c1  mov     rdx, rsi; unsigned __int16 *
0x18002e1c4  mov     rcx, rax; this
0x18002e1c7  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x18002e1cc  mov     ebx, eax
0x18002e1ce  test    eax, eax
0x18002e1d0  jns     short loc_18002E215
0x18002e1d2  mov     rcx, [rbp+18h]; this
0x18002e1d6  mov     r9d, eax; char *
0x18002e1d9  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e1e0  mov     edx, 58h ; 'X'; void *
0x18002e1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e1ea  nop
0x18002e1eb  mov     rcx, [rbp+string]; string
0x18002e1ef  call    cs:__imp_WindowsDeleteString
0x18002e1f5  mov     [rbp+string], r14
0x18002e1f9  mov     rcx, [rbp+arg_8]
0x18002e1fd  test    rcx, rcx
0x18002e200  jz      short loc_18002E213
0x18002e202  mov     [rbp+arg_8], r14
0x18002e206  mov     rax, [rcx]
0x18002e209  mov     rax, [rax+10h]
0x18002e20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e212  nop
0x18002e213  jmp     short loc_18002E279
0x18002e215  mov     rcx, [rbp+string]; string
0x18002e219  call    cs:__imp_WindowsDeleteString
0x18002e21f  mov     [rbp+string], r14
0x18002e223  mov     rcx, [rbp+arg_8]
0x18002e227  test    rcx, rcx
0x18002e22a  jz      short loc_18002E23D
0x18002e22c  mov     [rbp+arg_8], r14
0x18002e230  mov     rax, [rcx]
0x18002e233  mov     rax, [rax+10h]
0x18002e237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e23c  nop
0x18002e23d  xor     eax, eax
0x18002e23f  jmp     short loc_18002E27B
0x18002e241  mov     rcx, [rbp+18h]; this
0x18002e245  mov     ebx, 80004003h
0x18002e24a  mov     r9d, ebx; char *
0x18002e24d  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002e254  mov     edx, 53h ; 'S'; void *
0x18002e259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e25e  nop
0x18002e25f  mov     rcx, [rbp+arg_8]
0x18002e263  test    rcx, rcx
0x18002e266  jz      short loc_18002E279
0x18002e268  mov     [rbp+arg_8], r14
0x18002e26c  mov     rax, [rcx]
0x18002e26f  mov     rax, [rax+10h]
0x18002e273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e278  nop
0x18002e279  mov     eax, ebx
0x18002e27b  mov     rbx, [rsp+20h+arg_0]
0x18002e280  mov     rsi, [rsp+20h+arg_18]
0x18002e285  add     rsp, 20h
0x18002e289  pop     r14
0x18002e28b  pop     rdi
0x18002e28c  pop     rbp
0x18002e28d  retn
```
