# CredUXParameters::get_FooterTileLink(HSTRING__ * *)

- ea: `0x14001a240`
- end: `0x14001a28a`
- name: `?get_FooterTileLink@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a259`

## string_xrefs

- `0x14001a26a`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_FooterTileLink(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 35);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1DD,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a240  push    rbx; int
0x14001a242  sub     rsp, 20h
0x14001a246  mov     qword ptr [rdx], 0
0x14001a24d  mov     rcx, [rcx+118h]; string
0x14001a254  test    rcx, rcx
0x14001a257  jz      short loc_14001A282
0x14001a259  call    cs:__imp_WindowsDuplicateString
0x14001a25f  mov     ebx, eax
0x14001a261  test    eax, eax
0x14001a263  jns     short loc_14001A282
0x14001a265  mov     rcx, [rsp+28h]; this
0x14001a26a  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a271  mov     r9d, eax; char *
0x14001a274  mov     edx, 1DDh; void *
0x14001a279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a27e  mov     eax, ebx
0x14001a280  jmp     short loc_14001A284
0x14001a282  xor     eax, eax
0x14001a284  add     rsp, 20h
0x14001a288  pop     rbx
0x14001a289  retn
```
