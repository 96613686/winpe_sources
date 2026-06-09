# ipx::mtf::CoreUIMessageSender::_EnsureEndPoint(void)

- ea: `0x180023c38`
- end: `0x180023e12`
- name: `?_EnsureEndPoint@CoreUIMessageSender@mtf@ipx@@IEAAJXZ`
- size: `474`
- prototype: `__int64 __fastcall(ipx::mtf::CoreUIMessageSender *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180020e50`
- `0x180023b50`

## callees

- `0x1800046d4`
- `0x180006074`
- `0x180023c38`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180023dec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180023dec`
- `CoreMessaging!CoreUICreate` at `0x180023c73`
- `CoreMessaging!CoreUICreate` at `0x180023c73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ipx::mtf::CoreUIMessageSender::_EnsureEndPoint(
        ipx::mtf::CoreUIMessageSender *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  char *v5; // rdi
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  unsigned int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // r8
  _QWORD *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  int v20; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  _QWORD *v22; // [rsp+60h] [rbp+28h] BYREF

  if ( !*((_QWORD *)this + 3) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE9,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      a4);
  if ( *((_QWORD *)this + 5) )
  {
    v5 = (char *)this + 48;
    if ( *((_QWORD *)this + 6) )
      goto LABEL_28;
  }
  else
  {
    v6 = CoreUICreate((char *)this + 40);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
        (const char *)(unsigned int)v6,
        v20);
      return v7;
    }
    v5 = (char *)this + 48;
  }
  v22 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), &v22);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = *((unsigned int *)this + 14);
    v13 = (_QWORD *)((char *)this + 8);
    v14 = *v22;
    if ( (_DWORD)v12 == 2 )
    {
      if ( *((_QWORD *)this + 4) >= 8u )
        v13 = (_QWORD *)*v13;
      v15 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, _QWORD, char *))(v14 + 32))(
              v22,
              v13,
              *((unsigned int *)this + 15),
              v5);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
          (const char *)(unsigned int)v15,
          v20);
        v16 = v22;
        v22 = 0;
        if ( v16 )
          (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
        return v7;
      }
    }
    else
    {
      if ( *((_QWORD *)this + 4) >= 8u )
        v13 = (_QWORD *)*v13;
      v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, __int64, char *))(v14 + 24))(v22, v13, v12, v5);
      v7 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
          (const char *)(unsigned int)v17,
          v20);
        v18 = v22;
        v22 = 0;
        if ( v18 )
          (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
        return v7;
      }
    }
    v19 = v22;
    v22 = 0;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
LABEL_28:
    *(_QWORD *)this = GetTickCount64();
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF3,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
    (const char *)(unsigned int)v9,
    v20);
  v11 = v22;
  v22 = 0;
  if ( v11 )
    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
  return v10;
}

```

## disassembly

```asm
0x180023c38  push    rbp
0x180023c3a  push    rbx
0x180023c3b  push    rsi
0x180023c3c  push    rdi
0x180023c3d  mov     rbp, rsp
0x180023c40  sub     rsp, 38h
0x180023c44  mov     rbx, rcx
0x180023c47  mov     rcx, [rbp+20h]; this
0x180023c4b  cmp     qword ptr [rbx+18h], 0
0x180023c50  jz      loc_180023E00
0x180023c56  lea     rsi, [rbx+28h]
0x180023c5a  cmp     qword ptr [rsi], 0
0x180023c5e  jz      short loc_180023C70
0x180023c60  lea     rdi, [rbx+30h]
0x180023c64  cmp     qword ptr [rdi], 0
0x180023c68  jnz     loc_180023DEC
0x180023c6e  jmp     short loc_180023CA2
0x180023c70  mov     rcx, rsi
0x180023c73  call    cs:__imp_CoreUICreate
0x180023c79  mov     edi, eax
0x180023c7b  test    eax, eax
0x180023c7d  jns     short loc_180023C9E
0x180023c7f  mov     rcx, [rbp+20h]; this
0x180023c83  mov     r9d, eax; char *
0x180023c86  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023c8d  mov     edx, 0EFh; void *
0x180023c92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023c97  mov     eax, edi
0x180023c99  jmp     loc_180023DF7
0x180023c9e  lea     rdi, [rbx+30h]
0x180023ca2  mov     [rbp+arg_0], 0
0x180023caa  mov     rcx, [rsi]
0x180023cad  mov     rax, [rcx]
0x180023cb0  lea     rdx, [rbp+arg_0]
0x180023cb4  mov     rax, [rax+18h]
0x180023cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cbd  mov     esi, eax
0x180023cbf  test    eax, eax
0x180023cc1  jns     short loc_180023D01
0x180023cc3  mov     rcx, [rbp+20h]; this
0x180023cc7  mov     r9d, eax; char *
0x180023cca  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023cd1  mov     edx, 0F3h; void *
0x180023cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cdb  nop
0x180023cdc  mov     rcx, [rbp+arg_0]
0x180023ce0  mov     [rbp+arg_0], 0
0x180023ce8  test    rcx, rcx
0x180023ceb  jz      short loc_180023CFA
0x180023ced  mov     rax, [rcx]
0x180023cf0  mov     rax, [rax+10h]
0x180023cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cf9  nop
0x180023cfa  mov     eax, esi
0x180023cfc  jmp     loc_180023DF7
0x180023d01  mov     r8d, [rbx+38h]
0x180023d05  lea     rdx, [rbx+8]
0x180023d09  mov     rcx, [rbp+arg_0]
0x180023d0d  mov     rax, [rcx]
0x180023d10  cmp     r8d, 2
0x180023d14  jnz     short loc_180023D76
0x180023d16  cmp     qword ptr [rdx+18h], 8
0x180023d1b  jb      short loc_180023D20
0x180023d1d  mov     rdx, [rdx]
0x180023d20  mov     r9, rdi
0x180023d23  mov     r8d, [rbx+3Ch]
0x180023d27  mov     rax, [rax+20h]
0x180023d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d30  mov     edi, eax
0x180023d32  test    eax, eax
0x180023d34  jns     loc_180023DCE
0x180023d3a  mov     rcx, [rbp+20h]; this
0x180023d3e  mov     r9d, eax; char *
0x180023d41  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023d48  mov     edx, 0FAh; void *
0x180023d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d52  nop
0x180023d53  mov     rcx, [rbp+arg_0]
0x180023d57  mov     [rbp+arg_0], 0
0x180023d5f  test    rcx, rcx
0x180023d62  jz      short loc_180023D71
0x180023d64  mov     rax, [rcx]
0x180023d67  mov     rax, [rax+10h]
0x180023d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d70  nop
0x180023d71  jmp     loc_180023C97
0x180023d76  cmp     qword ptr [rdx+18h], 8
0x180023d7b  jb      short loc_180023D80
0x180023d7d  mov     rdx, [rdx]
0x180023d80  mov     r9, rdi
0x180023d83  mov     rax, [rax+18h]
0x180023d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d8c  mov     edi, eax
0x180023d8e  test    eax, eax
0x180023d90  jns     short loc_180023DCE
0x180023d92  mov     rcx, [rbp+20h]; this
0x180023d96  mov     r9d, eax; char *
0x180023d99  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023da0  mov     edx, 100h; void *
0x180023da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023daa  nop
0x180023dab  mov     rcx, [rbp+arg_0]
0x180023daf  mov     [rbp+arg_0], 0
0x180023db7  test    rcx, rcx
0x180023dba  jz      short loc_180023DC9
0x180023dbc  mov     rax, [rcx]
0x180023dbf  mov     rax, [rax+10h]
0x180023dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dc8  nop
0x180023dc9  jmp     loc_180023C97
0x180023dce  mov     rcx, [rbp+arg_0]
0x180023dd2  mov     [rbp+arg_0], 0
0x180023dda  test    rcx, rcx
0x180023ddd  jz      short loc_180023DEC
0x180023ddf  mov     rax, [rcx]
0x180023de2  mov     rax, [rax+10h]
0x180023de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023deb  nop
0x180023dec  call    cs:__imp_GetTickCount64
0x180023df2  mov     [rbx], rax
0x180023df5  xor     eax, eax
0x180023df7  add     rsp, 38h
0x180023dfb  pop     rdi
0x180023dfc  pop     rsi
0x180023dfd  pop     rbx
0x180023dfe  pop     rbp
0x180023dff  retn
0x180023e00  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023e07  mov     edx, 0E9h; void *
0x180023e0c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
