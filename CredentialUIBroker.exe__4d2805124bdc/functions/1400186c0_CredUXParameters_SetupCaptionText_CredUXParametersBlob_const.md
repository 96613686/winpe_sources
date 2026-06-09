# CredUXParameters::_SetupCaptionText(CredUXParametersBlob const *)

- ea: `0x1400186c0`
- end: `0x140018774`
- name: `?_SetupCaptionText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `180`
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
- `0x1400186c0`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018738`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018738`

## string_xrefs

- `0x14001870e`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupCaptionText(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v3; // rax
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, char *); // rdi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (*((_BYTE *)this + 72) & 1) == 0 )
  {
    v3 = *((_QWORD *)a2 + 2);
    if ( !v3 || IsWideStringEmpty(*(const unsigned __int16 *const *)(v3 + 24)) )
    {
      v7 = *((_QWORD *)this + 24);
      if ( v7 )
      {
        v8 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v7 + 48LL);
        WindowsDeleteString(*((HSTRING *)this + 11));
        *((_QWORD *)this + 11) = 0;
        v4 = v8(v7, (char *)this + 88);
        if ( v4 < 0 )
        {
          v5 = 603;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v4 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 88);
      if ( v4 < 0 )
      {
        v5 = 599;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v5,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
          (const char *)(unsigned int)v4,
          v9);
        return (unsigned int)v4;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400186c0  mov     [rsp+arg_0], rbx
0x1400186c5  mov     [rsp+arg_8], rsi
0x1400186ca  push    rdi; int
0x1400186cb  sub     rsp, 20h
0x1400186cf  test    byte ptr [rcx+48h], 1
0x1400186d3  mov     rbx, rcx
0x1400186d6  jnz     loc_140018762
0x1400186dc  mov     rax, [rdx+10h]
0x1400186e0  test    rax, rax
0x1400186e3  jz      short loc_140018721
0x1400186e5  lea     rdx, [rax+18h]
0x1400186e9  mov     rcx, [rdx]; unsigned __int16 *
0x1400186ec  call    ?IsWideStringEmpty@@YA_NQEBG@Z; IsWideStringEmpty(ushort const * const)
0x1400186f1  test    al, al
0x1400186f3  jnz     short loc_140018721
0x1400186f5  lea     rcx, [rbx+58h]
0x1400186f9  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400186fe  mov     ebx, eax
0x140018700  test    eax, eax
0x140018702  jns     short loc_140018762
0x140018704  mov     edx, 257h; void *
0x140018709  mov     rcx, [rsp+28h]; this
0x14001870e  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018715  mov     r9d, ebx; char *
0x140018718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001871d  mov     eax, ebx
0x14001871f  jmp     short loc_140018764
0x140018721  mov     rsi, [rbx+0C0h]
0x140018728  test    rsi, rsi
0x14001872b  jz      short loc_140018762
0x14001872d  mov     rax, [rsi]
0x140018730  mov     rcx, [rbx+58h]; string
0x140018734  mov     rdi, [rax+30h]
0x140018738  call    cs:__imp_WindowsDeleteString
0x14001873e  lea     rdx, [rbx+58h]
0x140018742  mov     qword ptr [rbx+58h], 0
0x14001874a  mov     rcx, rsi
0x14001874d  mov     rax, rdi
0x140018750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018755  mov     ebx, eax
0x140018757  test    eax, eax
0x140018759  jns     short loc_140018762
0x14001875b  mov     edx, 25Bh
0x140018760  jmp     short loc_140018709
0x140018762  xor     eax, eax
0x140018764  mov     rbx, [rsp+28h+arg_0]
0x140018769  mov     rsi, [rsp+28h+arg_8]
0x14001876e  add     rsp, 20h
0x140018772  pop     rdi
0x140018773  retn
```
