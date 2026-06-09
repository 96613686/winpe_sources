# CredUXParameters::get_MessageText(HSTRING__ * *)

- ea: `0x14001a560`
- end: `0x14001a5a7`
- name: `?get_MessageText@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a560`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a576`

## string_xrefs

- `0x14001a587`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_MessageText(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 12);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAF,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a560  push    rbx; int
0x14001a562  sub     rsp, 20h
0x14001a566  mov     qword ptr [rdx], 0
0x14001a56d  mov     rcx, [rcx+60h]; string
0x14001a571  test    rcx, rcx
0x14001a574  jz      short loc_14001A59F
0x14001a576  call    cs:__imp_WindowsDuplicateString
0x14001a57c  mov     ebx, eax
0x14001a57e  test    eax, eax
0x14001a580  jns     short loc_14001A59F
0x14001a582  mov     rcx, [rsp+28h]; this
0x14001a587  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a58e  mov     r9d, eax; char *
0x14001a591  mov     edx, 0AFh; void *
0x14001a596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a59b  mov     eax, ebx
0x14001a59d  jmp     short loc_14001A5A1
0x14001a59f  xor     eax, eax
0x14001a5a1  add     rsp, 20h
0x14001a5a5  pop     rbx
0x14001a5a6  retn
```
