# CredUXParameters::get_FooterTileMessage(HSTRING__ * *)

- ea: `0x14001a290`
- end: `0x14001a2da`
- name: `?get_FooterTileMessage@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a290`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a2a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a2a9`

## string_xrefs

- `0x14001a2ba`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_FooterTileMessage(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 34);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D3,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a290  push    rbx; int
0x14001a292  sub     rsp, 20h
0x14001a296  mov     qword ptr [rdx], 0
0x14001a29d  mov     rcx, [rcx+110h]; string
0x14001a2a4  test    rcx, rcx
0x14001a2a7  jz      short loc_14001A2D2
0x14001a2a9  call    cs:__imp_WindowsDuplicateString
0x14001a2af  mov     ebx, eax
0x14001a2b1  test    eax, eax
0x14001a2b3  jns     short loc_14001A2D2
0x14001a2b5  mov     rcx, [rsp+28h]; this
0x14001a2ba  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a2c1  mov     r9d, eax; char *
0x14001a2c4  mov     edx, 1D3h; void *
0x14001a2c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a2ce  mov     eax, ebx
0x14001a2d0  jmp     short loc_14001A2D4
0x14001a2d2  xor     eax, eax
0x14001a2d4  add     rsp, 20h
0x14001a2d8  pop     rbx
0x14001a2d9  retn
```
