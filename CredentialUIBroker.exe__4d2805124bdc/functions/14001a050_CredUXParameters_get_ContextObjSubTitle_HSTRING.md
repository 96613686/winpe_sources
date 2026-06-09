# CredUXParameters::get_ContextObjSubTitle(HSTRING__ * *)

- ea: `0x14001a050`
- end: `0x14001a09a`
- name: `?get_ContextObjSubTitle@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a050`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a069`

## string_xrefs

- `0x14001a07a`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_ContextObjSubTitle(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 30);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A5,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a050  push    rbx; int
0x14001a052  sub     rsp, 20h
0x14001a056  mov     qword ptr [rdx], 0
0x14001a05d  mov     rcx, [rcx+0F0h]; string
0x14001a064  test    rcx, rcx
0x14001a067  jz      short loc_14001A092
0x14001a069  call    cs:__imp_WindowsDuplicateString
0x14001a06f  mov     ebx, eax
0x14001a071  test    eax, eax
0x14001a073  jns     short loc_14001A092
0x14001a075  mov     rcx, [rsp+28h]; this
0x14001a07a  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a081  mov     r9d, eax; char *
0x14001a084  mov     edx, 1A5h; void *
0x14001a089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a08e  mov     eax, ebx
0x14001a090  jmp     short loc_14001A094
0x14001a092  xor     eax, eax
0x14001a094  add     rsp, 20h
0x14001a098  pop     rbx
0x14001a099  retn
```
