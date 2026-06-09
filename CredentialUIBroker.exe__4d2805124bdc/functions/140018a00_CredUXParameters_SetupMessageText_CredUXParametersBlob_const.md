# CredUXParameters::_SetupMessageText(CredUXParametersBlob const *)

- ea: `0x140018a00`
- end: `0x140018aba`
- name: `?_SetupMessageText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(CredUXParameters *this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140006f10`
- `0x14000eaac`
- `0x1400136fc`
- `0x140018a00`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018a7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018a7e`

## string_xrefs

- `0x140018a4e`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupMessageText(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v3; // rax
  const unsigned __int16 **v4; // rdx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, char *); // rdi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (*((_BYTE *)this + 72) & 1) != 0 )
  {
    if ( (*((_BYTE *)this + 72) & 0x24) == 0 )
    {
      v8 = *((_QWORD *)this + 24);
      if ( v8 )
      {
        v9 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 56LL);
        WindowsDeleteString(*((HSTRING *)this + 12));
        *((_QWORD *)this + 12) = 0;
        v5 = v9(v8, (char *)this + 96);
        if ( v5 < 0 )
        {
          v6 = 622;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v3 = *((_QWORD *)a2 + 2);
    if ( v3 )
    {
      if ( !IsWideStringEmpty(*(const unsigned __int16 *const *)(v3 + 16)) )
      {
        v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((CredUXParameters *)((char *)this + 96), v4);
        if ( v5 < 0 )
        {
          v6 = 616;
LABEL_6:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v6,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
            (const char *)(unsigned int)v5,
            v10);
          return (unsigned int)v5;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018a00  mov     [rsp+arg_0], rbx
0x140018a05  mov     [rsp+arg_8], rsi
0x140018a0a  push    rdi; int
0x140018a0b  sub     rsp, 20h
0x140018a0f  test    byte ptr [rcx+48h], 1
0x140018a13  mov     rbx, rcx
0x140018a16  jnz     short loc_140018A61
0x140018a18  mov     rax, [rdx+10h]
0x140018a1c  test    rax, rax
0x140018a1f  jz      loc_140018AA8
0x140018a25  lea     rdx, [rax+10h]
0x140018a29  mov     rcx, [rdx]; unsigned __int16 *
0x140018a2c  call    ?IsWideStringEmpty@@YA_NQEBG@Z; IsWideStringEmpty(ushort const * const)
0x140018a31  test    al, al
0x140018a33  jnz     short loc_140018AA8
0x140018a35  lea     rcx, [rbx+60h]
0x140018a39  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140018a3e  mov     ebx, eax
0x140018a40  test    eax, eax
0x140018a42  jns     short loc_140018AA8
0x140018a44  mov     edx, 268h; void *
0x140018a49  mov     rcx, [rsp+28h]; this
0x140018a4e  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018a55  mov     r9d, ebx; char *
0x140018a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018a5d  mov     eax, ebx
0x140018a5f  jmp     short loc_140018AAA
0x140018a61  test    byte ptr [rcx+48h], 24h
0x140018a65  jnz     short loc_140018AA8
0x140018a67  mov     rsi, [rcx+0C0h]
0x140018a6e  test    rsi, rsi
0x140018a71  jz      short loc_140018AA8
0x140018a73  mov     rax, [rsi]
0x140018a76  mov     rcx, [rcx+60h]; string
0x140018a7a  mov     rdi, [rax+38h]
0x140018a7e  call    cs:__imp_WindowsDeleteString
0x140018a84  lea     rdx, [rbx+60h]
0x140018a88  mov     qword ptr [rbx+60h], 0
0x140018a90  mov     rcx, rsi
0x140018a93  mov     rax, rdi
0x140018a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a9b  mov     ebx, eax
0x140018a9d  test    eax, eax
0x140018a9f  jns     short loc_140018AA8
0x140018aa1  mov     edx, 26Eh
0x140018aa6  jmp     short loc_140018A49
0x140018aa8  xor     eax, eax
0x140018aaa  mov     rbx, [rsp+28h+arg_0]
0x140018aaf  mov     rsi, [rsp+28h+arg_8]
0x140018ab4  add     rsp, 20h
0x140018ab8  pop     rdi
0x140018ab9  retn
```
