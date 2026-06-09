# CredUXParameters::get_OkButtonText(HSTRING__ * *)

- ea: `0x14001a5b0`
- end: `0x14001a5f7`
- name: `?get_OkButtonText@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a5b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a5c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a5c6`

## string_xrefs

- `0x14001a5d7`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_OkButtonText(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 13);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB9,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a5b0  push    rbx; int
0x14001a5b2  sub     rsp, 20h
0x14001a5b6  mov     qword ptr [rdx], 0
0x14001a5bd  mov     rcx, [rcx+68h]; string
0x14001a5c1  test    rcx, rcx
0x14001a5c4  jz      short loc_14001A5EF
0x14001a5c6  call    cs:__imp_WindowsDuplicateString
0x14001a5cc  mov     ebx, eax
0x14001a5ce  test    eax, eax
0x14001a5d0  jns     short loc_14001A5EF
0x14001a5d2  mov     rcx, [rsp+28h]; this
0x14001a5d7  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a5de  mov     r9d, eax; char *
0x14001a5e1  mov     edx, 0B9h; void *
0x14001a5e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a5eb  mov     eax, ebx
0x14001a5ed  jmp     short loc_14001A5F1
0x14001a5ef  xor     eax, eax
0x14001a5f1  add     rsp, 20h
0x14001a5f5  pop     rbx
0x14001a5f6  retn
```
