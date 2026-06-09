# CredUXParameters::get_CaptionText(HSTRING__ * *)

- ea: `0x140019ec0`
- end: `0x140019f07`
- name: `?get_CaptionText@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x140019ec0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140019ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140019ed6`

## string_xrefs

- `0x140019ee7`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_CaptionText(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 11);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x140019ec0  push    rbx; int
0x140019ec2  sub     rsp, 20h
0x140019ec6  mov     qword ptr [rdx], 0
0x140019ecd  mov     rcx, [rcx+58h]; string
0x140019ed1  test    rcx, rcx
0x140019ed4  jz      short loc_140019EFF
0x140019ed6  call    cs:__imp_WindowsDuplicateString
0x140019edc  mov     ebx, eax
0x140019ede  test    eax, eax
0x140019ee0  jns     short loc_140019EFF
0x140019ee2  mov     rcx, [rsp+28h]; this
0x140019ee7  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140019eee  mov     r9d, eax; char *
0x140019ef1  mov     edx, 0A5h; void *
0x140019ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019efb  mov     eax, ebx
0x140019efd  jmp     short loc_140019F01
0x140019eff  xor     eax, eax
0x140019f01  add     rsp, 20h
0x140019f05  pop     rbx
0x140019f06  retn
```
