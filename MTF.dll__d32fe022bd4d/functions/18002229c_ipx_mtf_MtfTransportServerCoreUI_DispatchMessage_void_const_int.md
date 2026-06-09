# ipx::mtf::MtfTransportServerCoreUI::_DispatchMessage(void const *,int)

- ea: `0x18002229c`
- end: `0x1800224d6`
- name: `?_DispatchMessage@MtfTransportServerCoreUI@mtf@ipx@@IEAAJPEBXH@Z`
- size: `570`
- prototype: `__int64 __fastcall(ipx::mtf::MtfTransportServerCoreUI *__hidden this, const void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800224e0`

## callees

- `0x180006074`
- `0x18002229c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180022399`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180022399`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ipx::mtf::MtfTransportServerCoreUI::_DispatchMessage(
        ipx::mtf::MtfTransportServerCoreUI *this,
        _DWORD *a2,
        unsigned int a3)
{
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int v9; // ebx
  char v10; // al
  HRESULT v11; // eax
  unsigned int v12; // esi
  LPSTREAM v13; // rcx
  int v14; // eax
  LPSTREAM v15; // rcx
  int v16; // eax
  LPSTREAM v17; // rcx
  LPSTREAM v18; // rcx
  int v19; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPSTREAM ppstm; // [rsp+68h] [rbp+38h] BYREF

  if ( a3 < 0x18 )
    return 0;
  if ( *((_DWORD *)this + 53) != 1 )
  {
    v7 = 1116;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)0x8000FFFFLL,
      v19);
    return 2147549183LL;
  }
  if ( ((*((_DWORD *)this + 55) - 512) & 0xFFFFFEFF) != 0 )
  {
    v7 = 1118;
    goto LABEL_5;
  }
  if ( a3 != a2[4] )
  {
    v8 = 1123;
LABEL_11:
    v9 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)0x80004005LL,
      v19);
    return v9;
  }
  if ( !*((_BYTE *)a2 + 21) )
  {
    v8 = 1126;
    goto LABEL_11;
  }
  v10 = *((_BYTE *)a2 + 20);
  if ( v10 == 1 )
    return (*(__int64 (__fastcall **)(ipx::mtf::MtfTransportServerCoreUI *, _QWORD, _DWORD *))(*(_QWORD *)this + 24LL))(
             this,
             0,
             a2);
  if ( v10 == 2 )
    return (*(__int64 (__fastcall **)(ipx::mtf::MtfTransportServerCoreUI *, _DWORD *))(*(_QWORD *)this + 32LL))(
             this,
             a2);
  if ( v10 != 3 )
    return 2147549183LL;
  ppstm = 0;
  v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(LPSTREAM, char *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
            ppstm,
            (char *)a2 + 24,
            a3 - 24,
            0);
    v12 = v14;
    if ( v14 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
      v12 = v16;
      if ( v16 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(ipx::mtf::MtfTransportServerCoreUI *, _DWORD *, _QWORD, LPSTREAM))(*(_QWORD *)this + 40LL))(
               this,
               a2,
               (unsigned int)a2[3],
               ppstm);
        v18 = ppstm;
        ppstm = 0;
        if ( v18 )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v18 + 16LL))(v18);
        return v9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47A,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v16,
        v19);
      v17 = ppstm;
      ppstm = 0;
      if ( v17 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v17 + 16LL))(v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x477,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v14,
        v19);
      v15 = ppstm;
      ppstm = 0;
      if ( v15 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x473,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)(unsigned int)v11,
      v19);
    v13 = ppstm;
    ppstm = 0;
    if ( v13 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return v12;
}

```

## disassembly

```asm
0x18002229c  mov     [rsp-18h+arg_0], rbx
0x1800222a1  mov     [rsp-18h+arg_8], rsi
0x1800222a6  push    rbp
0x1800222a7  push    rdi
0x1800222a8  push    r14
0x1800222aa  mov     rbp, rsp
0x1800222ad  sub     rsp, 30h
0x1800222b1  mov     r14d, r8d
0x1800222b4  mov     rbx, rdx
0x1800222b7  mov     rdi, rcx
0x1800222ba  cmp     r8d, 18h
0x1800222be  jnb     short loc_1800222C4
0x1800222c0  xor     eax, eax
0x1800222c2  jmp     short loc_1800222F1
0x1800222c4  mov     edx, 1; fDeleteOnRelease
0x1800222c9  cmp     [rcx+0D4h], edx
0x1800222cf  jz      short loc_180022304
0x1800222d1  mov     edx, 45Ch; void *
0x1800222d6  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800222dd  mov     r9d, 8000FFFFh; char *
0x1800222e3  mov     rcx, [rbp+18h]; this
0x1800222e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800222ec  mov     eax, 8000FFFFh
0x1800222f1  mov     rbx, [rsp+30h+arg_0]
0x1800222f6  mov     rsi, [rsp+30h+arg_8]
0x1800222fb  add     rsp, 30h
0x1800222ff  pop     r14
0x180022301  pop     rdi
0x180022302  pop     rbp
0x180022303  retn
0x180022304  mov     eax, [rcx+0DCh]
0x18002230a  sub     eax, 200h
0x18002230f  test    eax, 0FFFFFEFFh
0x180022314  jz      short loc_18002231D
0x180022316  mov     edx, 45Eh
0x18002231b  jmp     short loc_1800222D6
0x18002231d  cmp     r14d, [rbx+10h]
0x180022321  jz      short loc_180022344
0x180022323  mov     edx, 463h; void *
0x180022328  mov     ebx, 80004005h
0x18002232d  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180022334  mov     r9d, ebx; char *
0x180022337  mov     rcx, [rbp+18h]; this
0x18002233b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022340  mov     eax, ebx
0x180022342  jmp     short loc_1800222F1
0x180022344  cmp     byte ptr [rbx+15h], 0
0x180022348  jnz     short loc_180022351
0x18002234a  mov     edx, 466h
0x18002234f  jmp     short loc_180022328
0x180022351  mov     al, [rbx+14h]
0x180022354  cmp     al, dl
0x180022356  jnz     short loc_18002236B
0x180022358  mov     rax, [rcx]
0x18002235b  mov     r8, rbx
0x18002235e  xor     edx, edx
0x180022360  mov     rax, [rax+18h]
0x180022364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022369  jmp     short loc_1800222F1
0x18002236b  cmp     al, 2
0x18002236d  jnz     short loc_180022383
0x18002236f  mov     rax, [rcx]
0x180022372  mov     rdx, rbx
0x180022375  mov     rax, [rax+20h]
0x180022379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002237e  jmp     loc_1800222F1
0x180022383  cmp     al, 3
0x180022385  jnz     loc_1800222EC
0x18002238b  mov     [rbp+ppstm], 0
0x180022393  lea     r8, [rbp+ppstm]; ppstm
0x180022397  xor     ecx, ecx; hGlobal
0x180022399  call    cs:__imp_CreateStreamOnHGlobal
0x18002239f  mov     esi, eax
0x1800223a1  test    eax, eax
0x1800223a3  jns     short loc_1800223E3
0x1800223a5  mov     rcx, [rbp+18h]; this
0x1800223a9  mov     r9d, eax; char *
0x1800223ac  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800223b3  mov     edx, 473h; void *
0x1800223b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800223bd  nop
0x1800223be  mov     rcx, [rbp+ppstm]
0x1800223c2  mov     [rbp+ppstm], 0
0x1800223ca  test    rcx, rcx
0x1800223cd  jz      short loc_1800223DC
0x1800223cf  mov     rax, [rcx]
0x1800223d2  mov     rax, [rax+10h]
0x1800223d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223db  nop
0x1800223dc  mov     eax, esi
0x1800223de  jmp     loc_1800222F1
0x1800223e3  mov     rcx, [rbp+ppstm]
0x1800223e7  mov     rax, [rcx]
0x1800223ea  lea     r8d, [r14-18h]
0x1800223ee  lea     rdx, [rbx+18h]
0x1800223f2  xor     r9d, r9d
0x1800223f5  mov     rax, [rax+20h]
0x1800223f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223fe  mov     esi, eax
0x180022400  test    eax, eax
0x180022402  jns     short loc_18002243D
0x180022404  mov     rcx, [rbp+18h]; this
0x180022408  mov     r9d, eax; char *
0x18002240b  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180022412  mov     edx, 477h; void *
0x180022417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002241c  nop
0x18002241d  mov     rcx, [rbp+ppstm]
0x180022421  mov     [rbp+ppstm], 0
0x180022429  test    rcx, rcx
0x18002242c  jz      short loc_18002243B
0x18002242e  mov     rax, [rcx]
0x180022431  mov     rax, [rax+10h]
0x180022435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002243a  nop
0x18002243b  jmp     short loc_1800223DC
0x18002243d  mov     rcx, [rbp+ppstm]
0x180022441  xor     edx, edx
0x180022443  mov     rax, [rcx]
0x180022446  xor     r9d, r9d
0x180022449  xor     r8d, r8d
0x18002244c  mov     rax, [rax+28h]
0x180022450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022455  mov     esi, eax
0x180022457  test    eax, eax
0x180022459  jns     short loc_180022497
0x18002245b  mov     rcx, [rbp+18h]; this
0x18002245f  mov     r9d, eax; char *
0x180022462  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180022469  mov     edx, 47Ah; void *
0x18002246e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022473  nop
0x180022474  mov     rcx, [rbp+ppstm]
0x180022478  mov     [rbp+ppstm], 0
0x180022480  test    rcx, rcx
0x180022483  jz      short loc_180022492
0x180022485  mov     rax, [rcx]
0x180022488  mov     rax, [rax+10h]
0x18002248c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022491  nop
0x180022492  jmp     loc_1800223DC
0x180022497  mov     rax, [rdi]
0x18002249a  mov     r9, [rbp+ppstm]
0x18002249e  mov     r8d, [rbx+0Ch]
0x1800224a2  mov     rdx, rbx
0x1800224a5  mov     rcx, rdi
0x1800224a8  mov     rax, [rax+28h]
0x1800224ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224b1  mov     ebx, eax
0x1800224b3  mov     rcx, [rbp+ppstm]
0x1800224b7  mov     [rbp+ppstm], 0
0x1800224bf  test    rcx, rcx
0x1800224c2  jz      short loc_1800224D1
0x1800224c4  mov     rdx, [rcx]
0x1800224c7  mov     rax, [rdx+10h]
0x1800224cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d0  nop
0x1800224d1  jmp     loc_180022340
```
