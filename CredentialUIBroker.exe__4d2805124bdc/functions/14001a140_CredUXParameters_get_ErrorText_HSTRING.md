# CredUXParameters::get_ErrorText(HSTRING__ * *)

- ea: `0x14001a140`
- end: `0x14001a18a`
- name: `?get_ErrorText@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a140`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a159`

## string_xrefs

- `0x14001a16a`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_ErrorText(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 17);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD9,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a140  push    rbx; int
0x14001a142  sub     rsp, 20h
0x14001a146  mov     qword ptr [rdx], 0
0x14001a14d  mov     rcx, [rcx+88h]; string
0x14001a154  test    rcx, rcx
0x14001a157  jz      short loc_14001A182
0x14001a159  call    cs:__imp_WindowsDuplicateString
0x14001a15f  mov     ebx, eax
0x14001a161  test    eax, eax
0x14001a163  jns     short loc_14001A182
0x14001a165  mov     rcx, [rsp+28h]; this
0x14001a16a  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a171  mov     r9d, eax; char *
0x14001a174  mov     edx, 0D9h; void *
0x14001a179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a17e  mov     eax, ebx
0x14001a180  jmp     short loc_14001A184
0x14001a182  xor     eax, eax
0x14001a184  add     rsp, 20h
0x14001a188  pop     rbx
0x14001a189  retn
```
