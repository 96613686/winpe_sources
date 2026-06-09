# CredUXParameters::_SetupErrorText(CredUXParametersBlob const *)

- ea: `0x140018888`
- end: `0x140018943`
- name: `?_SetupErrorText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(CredUXParameters *__hidden this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140006f10`
- `0x14000eaac`
- `0x1400136fc`
- `0x140018888`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018904`

## string_xrefs

- `0x1400188d7`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupErrorText(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v4; // rax
  const unsigned __int16 **v5; // rdx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, _QWORD, char *); // rdi
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( *((_DWORD *)a2 + 6) )
  {
    v4 = *((_QWORD *)a2 + 2);
    if ( !v4 || IsWideStringEmpty(*(const unsigned __int16 *const *)(v4 + 80)) )
    {
      v9 = *((_QWORD *)this + 24);
      if ( v9 )
      {
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v9 + 88LL);
        WindowsDeleteString(*((HSTRING *)this + 17));
        *((_QWORD *)this + 17) = 0;
        v6 = v10(v9, *((unsigned int *)a2 + 6), (char *)this + 136);
        if ( v6 < 0 )
        {
          v7 = 586;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((CredUXParameters *)((char *)this + 136), v5);
      if ( v6 < 0 )
      {
        v7 = 582;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
          (const char *)(unsigned int)v6,
          v11);
        return (unsigned int)v6;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018888  push    rbx
0x14001888a  push    rsi
0x14001888b  push    rdi
0x14001888c  push    r14
0x14001888e  sub     rsp, 28h
0x140018892  cmp     dword ptr [rdx+18h], 0
0x140018896  mov     rsi, rdx
0x140018899  mov     rbx, rcx
0x14001889c  jz      loc_140018937
0x1400188a2  mov     rax, [rdx+10h]
0x1400188a6  test    rax, rax
0x1400188a9  jz      short loc_1400188EA
0x1400188ab  lea     rdx, [rax+50h]
0x1400188af  mov     rcx, [rdx]; unsigned __int16 *
0x1400188b2  call    ?IsWideStringEmpty@@YA_NQEBG@Z; IsWideStringEmpty(ushort const * const)
0x1400188b7  test    al, al
0x1400188b9  jnz     short loc_1400188EA
0x1400188bb  lea     rcx, [rbx+88h]
0x1400188c2  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400188c7  mov     ebx, eax
0x1400188c9  test    eax, eax
0x1400188cb  jns     short loc_140018937
0x1400188cd  mov     edx, 246h; void *
0x1400188d2  mov     rcx, [rsp+48h]; this
0x1400188d7  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400188de  mov     r9d, ebx; char *
0x1400188e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400188e6  mov     eax, ebx
0x1400188e8  jmp     short loc_140018939
0x1400188ea  mov     r14, [rbx+0C0h]
0x1400188f1  test    r14, r14
0x1400188f4  jz      short loc_140018937
0x1400188f6  mov     rax, [r14]
0x1400188f9  mov     rcx, [rbx+88h]; string
0x140018900  mov     rdi, [rax+58h]
0x140018904  call    cs:__imp_WindowsDeleteString
0x14001890a  mov     qword ptr [rbx+88h], 0
0x140018915  lea     r8, [rbx+88h]
0x14001891c  mov     edx, [rsi+18h]
0x14001891f  mov     rcx, r14
0x140018922  mov     rax, rdi
0x140018925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001892a  mov     ebx, eax
0x14001892c  test    eax, eax
0x14001892e  jns     short loc_140018937
0x140018930  mov     edx, 24Ah
0x140018935  jmp     short loc_1400188D2
0x140018937  xor     eax, eax
0x140018939  add     rsp, 28h
0x14001893d  pop     r14
0x14001893f  pop     rdi
0x140018940  pop     rsi
0x140018941  pop     rbx
0x140018942  retn
```
