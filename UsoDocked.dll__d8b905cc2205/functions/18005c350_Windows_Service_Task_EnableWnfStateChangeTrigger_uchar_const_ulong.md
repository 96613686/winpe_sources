# Windows::Service::Task::EnableWnfStateChangeTrigger(uchar const *,ulong)

- ea: `0x18005c350`
- end: `0x18005c657`
- name: `?EnableWnfStateChangeTrigger@Task@Service@Windows@@QEAAXPEBEK@Z`
- size: `775`
- prototype: `void(Windows::Service::Task *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18005c2b0`

## callees

- `0x180008548`
- `0x1800209fc`
- `0x18005c350`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005c457`
- `OLEAUT32!__imp_VariantInit` at `0x18005c457`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4b0`
- `OLEAUT32!__imp_VariantClear` at `0x18005c577`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4b0`
- `OLEAUT32!__imp_VariantClear` at `0x18005c577`

## string_xrefs

- `0x18005c645`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005c5b2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c5c7`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c5dc`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c5f1`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c606`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c61b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005c630`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Windows::Service::Task::EnableWnfStateChangeTrigger(
        Windows::Service::Task *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v3; // rdi
  int v6; // eax
  int v7; // eax
  int i; // ebx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // [rsp+20h] [rbp-40h] BYREF
  __int64 v17; // [rsp+28h] [rbp-38h] BYREF
  __int64 *v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int16 v22; // [rsp+90h] [rbp+30h] BYREF
  int v23; // [rsp+A8h] [rbp+48h] BYREF

  v3 = a3;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, &v18);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v18 + 56))(v18, &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v7,
      v16);
  for ( i = 1; i <= v23; ++i )
  {
    v17 = 0;
    v9 = *v18;
    v17 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v9 + 64))(v18, (unsigned int)i, &v17);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v10,
        v16);
    v16 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v16);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v11,
        v16);
    if ( v16 == 12 )
    {
      v19 = 0;
      v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
              v17,
              &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f,
              &v19);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v12,
          v16);
      VariantInit(&pvarg);
      pvarg.vt = 27;
      v13 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v19 + 176LL))(v19, &pvarg.cyVal);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x138,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
          (const char *)(unsigned int)v13,
          v16);
      if ( *pvarg.bstrVal == 1
        && *(_DWORD *)(pvarg.llVal + 24) == (_DWORD)v3
        && !memcmp_0(a2, *(const void **)(pvarg.llVal + 16), v3) )
      {
        v22 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v17 + 144LL))(v17, &v22);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
            (const char *)(unsigned int)v14,
            v16);
        if ( !v22 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 152LL))(v17, 0xFFFFFFFFLL);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x141,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
              (const char *)(unsigned int)v15,
              v16);
          *((_BYTE *)this + 40) = 1;
        }
        VariantClear(&pvarg);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        break;
      }
      VariantClear(&pvarg);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
}

```

## disassembly

```asm
0x18005c350  mov     [rsp-28h+arg_8], rbx
0x18005c355  mov     [rsp-28h+arg_10], rsi
0x18005c35a  push    rbp
0x18005c35b  push    rdi
0x18005c35c  push    r12
0x18005c35e  push    r14
0x18005c360  push    r15
0x18005c362  mov     rbp, rsp
0x18005c365  sub     rsp, 60h
0x18005c369  mov     edi, r8d
0x18005c36c  mov     r14, rdx
0x18005c36f  mov     rsi, rcx
0x18005c372  xor     r15d, r15d
0x18005c375  mov     [rbp+var_30], r15
0x18005c379  mov     rcx, [rcx]
0x18005c37c  mov     rax, [rcx]
0x18005c37f  mov     [rbp+var_30], r15
0x18005c383  lea     rdx, [rbp+var_30]
0x18005c387  mov     rax, [rax+48h]
0x18005c38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c390  mov     rcx, [rbp+28h]; this
0x18005c394  test    eax, eax
0x18005c396  js      loc_18005C5D9
0x18005c39c  mov     [rbp+arg_18], r15d
0x18005c3a0  mov     rcx, [rbp+var_30]
0x18005c3a4  mov     rax, [rcx]
0x18005c3a7  lea     rdx, [rbp+arg_18]
0x18005c3ab  mov     rax, [rax+38h]
0x18005c3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3b4  mov     rcx, [rbp+28h]; this
0x18005c3b8  test    eax, eax
0x18005c3ba  js      loc_18005C5EE
0x18005c3c0  lea     r12d, [r15+1]
0x18005c3c4  mov     ebx, r12d
0x18005c3c7  cmp     [rbp+arg_18], r12d
0x18005c3cb  jl      loc_18005C4EF
0x18005c3d1  mov     [rbp+var_38], r15
0x18005c3d5  mov     rcx, [rbp+var_30]
0x18005c3d9  mov     rax, [rcx]
0x18005c3dc  mov     [rbp+var_38], r15
0x18005c3e0  lea     r8, [rbp+var_38]
0x18005c3e4  mov     edx, ebx
0x18005c3e6  mov     rax, [rax+40h]
0x18005c3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3ef  mov     rcx, [rbp+28h]; this
0x18005c3f3  test    eax, eax
0x18005c3f5  js      loc_18005C5C4
0x18005c3fb  mov     [rbp+var_40], r15d
0x18005c3ff  mov     rcx, [rbp+var_38]
0x18005c403  mov     rax, [rcx]
0x18005c406  lea     rdx, [rbp+var_40]
0x18005c40a  mov     rax, [rax+38h]
0x18005c40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c413  mov     rcx, [rbp+28h]; this
0x18005c417  test    eax, eax
0x18005c419  js      loc_18005C5AF
0x18005c41f  cmp     [rbp+var_40], 0Ch
0x18005c423  jnz     loc_18005C4CD
0x18005c429  mov     rcx, [rbp+var_38]
0x18005c42d  mov     [rbp+var_28], r15
0x18005c431  mov     rax, [rcx]
0x18005c434  lea     r8, [rbp+var_28]
0x18005c438  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x18005c43f  mov     rax, [rax]
0x18005c442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c447  mov     rcx, [rbp+28h]; this
0x18005c44b  test    eax, eax
0x18005c44d  js      loc_18005C642
0x18005c453  lea     rcx, [rbp+pvarg]; pvarg
0x18005c457  call    cs:__imp_VariantInit
0x18005c45d  nop
0x18005c45e  mov     eax, 1Bh
0x18005c463  mov     word ptr [rbp+pvarg], ax
0x18005c467  mov     rcx, [rbp+var_28]
0x18005c46b  mov     rax, [rcx]
0x18005c46e  lea     rdx, [rbp+pvarg+8]
0x18005c472  mov     rax, [rax+0B0h]
0x18005c479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c47e  mov     rcx, [rbp+28h]; this
0x18005c482  test    eax, eax
0x18005c484  js      loc_18005C62D
0x18005c48a  mov     rdx, qword ptr [rbp+pvarg+8]
0x18005c48e  cmp     [rdx], r12w
0x18005c492  jnz     short loc_18005C4AC
0x18005c494  cmp     [rdx+18h], edi
0x18005c497  jnz     short loc_18005C4AC
0x18005c499  mov     r8, rdi; Size
0x18005c49c  mov     rdx, [rdx+10h]; Buf2
0x18005c4a0  mov     rcx, r14; Buf1
0x18005c4a3  call    memcmp_0
0x18005c4a8  test    eax, eax
0x18005c4aa  jz      short loc_18005C51E
0x18005c4ac  lea     rcx, [rbp+pvarg]; pvarg
0x18005c4b0  call    cs:__imp_VariantClear
0x18005c4b6  nop
0x18005c4b7  mov     rcx, [rbp+var_28]
0x18005c4bb  test    rcx, rcx
0x18005c4be  jz      short loc_18005C4CD
0x18005c4c0  mov     rax, [rcx]
0x18005c4c3  mov     rax, [rax+10h]
0x18005c4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4cc  nop
0x18005c4cd  mov     rcx, [rbp+var_38]
0x18005c4d1  test    rcx, rcx
0x18005c4d4  jz      short loc_18005C4E3
0x18005c4d6  mov     rax, [rcx]
0x18005c4d9  mov     rax, [rax+10h]
0x18005c4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4e2  nop
0x18005c4e3  add     ebx, r12d
0x18005c4e6  cmp     ebx, [rbp+arg_18]
0x18005c4e9  jle     loc_18005C3D1
0x18005c4ef  mov     rcx, [rbp+var_30]
0x18005c4f3  test    rcx, rcx
0x18005c4f6  jz      short loc_18005C505
0x18005c4f8  mov     rax, [rcx]
0x18005c4fb  mov     rax, [rax+10h]
0x18005c4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c504  nop
0x18005c505  lea     r11, [rsp+60h+var_s0]
0x18005c50a  mov     rbx, [r11+38h]
0x18005c50e  mov     rsi, [r11+40h]
0x18005c512  mov     rsp, r11
0x18005c515  pop     r15
0x18005c517  pop     r14
0x18005c519  pop     r12
0x18005c51b  pop     rdi
0x18005c51c  pop     rbp
0x18005c51d  retn
0x18005c51e  mov     [rbp+arg_0], r15w
0x18005c523  mov     rcx, [rbp+var_38]
0x18005c527  mov     rax, [rcx]
0x18005c52a  lea     rdx, [rbp+arg_0]
0x18005c52e  mov     rax, [rax+90h]
0x18005c535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c53a  mov     rcx, [rbp+28h]; this
0x18005c53e  test    eax, eax
0x18005c540  js      loc_18005C603
0x18005c546  cmp     [rbp+arg_0], r15w
0x18005c54b  jnz     short loc_18005C573
0x18005c54d  mov     rcx, [rbp+var_38]
0x18005c551  mov     rax, [rcx]
0x18005c554  or      edx, 0FFFFFFFFh
0x18005c557  mov     rax, [rax+98h]
0x18005c55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c563  mov     rcx, [rbp+28h]; this
0x18005c567  test    eax, eax
0x18005c569  js      loc_18005C618
0x18005c56f  mov     [rsi+28h], r12b
0x18005c573  lea     rcx, [rbp+pvarg]; pvarg
0x18005c577  call    cs:__imp_VariantClear
0x18005c57d  nop
0x18005c57e  mov     rcx, [rbp+var_28]
0x18005c582  test    rcx, rcx
0x18005c585  jz      short loc_18005C594
0x18005c587  mov     rax, [rcx]
0x18005c58a  mov     rax, [rax+10h]
0x18005c58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c593  nop
0x18005c594  mov     rcx, [rbp+var_38]
0x18005c598  test    rcx, rcx
0x18005c59b  jz      short loc_18005C5AA
0x18005c59d  mov     rax, [rcx]
0x18005c5a0  mov     rax, [rax+10h]
0x18005c5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5a9  nop
0x18005c5aa  jmp     loc_18005C4EF
0x18005c5af  mov     r9d, eax; char *
0x18005c5b2  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c5b9  mov     edx, 131h; void *
0x18005c5be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c5c4  mov     r9d, eax; char *
0x18005c5c7  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c5ce  mov     edx, 12Eh; void *
0x18005c5d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c5d9  mov     r9d, eax; char *
0x18005c5dc  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c5e3  mov     edx, 126h; void *
0x18005c5e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c5ee  mov     r9d, eax; char *
0x18005c5f1  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c5f8  mov     edx, 129h; void *
0x18005c5fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c603  mov     r9d, eax; char *
0x18005c606  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c60d  mov     edx, 13Eh; void *
0x18005c612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c618  mov     r9d, eax; char *
0x18005c61b  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c622  mov     edx, 141h; void *
0x18005c627  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c62d  mov     r9d, eax; char *
0x18005c630  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005c637  mov     edx, 138h; void *
0x18005c63c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c642  mov     r9d, eax; char *
0x18005c645  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005c64c  mov     edx, 1CBEh; void *
0x18005c651  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
