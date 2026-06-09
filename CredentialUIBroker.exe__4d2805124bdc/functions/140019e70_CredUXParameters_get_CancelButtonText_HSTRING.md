# CredUXParameters::get_CancelButtonText(HSTRING__ * *)

- ea: `0x140019e70`
- end: `0x140019eb7`
- name: `?get_CancelButtonText@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x140019e70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140019e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140019e86`

## string_xrefs

- `0x140019e97`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_CancelButtonText(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 10);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9B,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x140019e70  push    rbx; int
0x140019e72  sub     rsp, 20h
0x140019e76  mov     qword ptr [rdx], 0
0x140019e7d  mov     rcx, [rcx+50h]; string
0x140019e81  test    rcx, rcx
0x140019e84  jz      short loc_140019EAF
0x140019e86  call    cs:__imp_WindowsDuplicateString
0x140019e8c  mov     ebx, eax
0x140019e8e  test    eax, eax
0x140019e90  jns     short loc_140019EAF
0x140019e92  mov     rcx, [rsp+28h]; this
0x140019e97  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140019e9e  mov     r9d, eax; char *
0x140019ea1  mov     edx, 9Bh; void *
0x140019ea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019eab  mov     eax, ebx
0x140019ead  jmp     short loc_140019EB1
0x140019eaf  xor     eax, eax
0x140019eb1  add     rsp, 20h
0x140019eb5  pop     rbx
0x140019eb6  retn
```
