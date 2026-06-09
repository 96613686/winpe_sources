# CredUXParameters::get_ContextObjTitle(HSTRING__ * *)

- ea: `0x14001a0a0`
- end: `0x14001a0ea`
- name: `?get_ContextObjTitle@CredUXParameters@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(CredUXParameters *this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a0a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a0b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14001a0b9`

## string_xrefs

- `0x14001a0ca`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_ContextObjTitle(CredUXParameters *this, HSTRING *a2)
{
  HSTRING v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = (HSTRING)*((_QWORD *)this + 29);
  if ( !v2 )
    return 0;
  v3 = WindowsDuplicateString(v2, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19B,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a0a0  push    rbx; int
0x14001a0a2  sub     rsp, 20h
0x14001a0a6  mov     qword ptr [rdx], 0
0x14001a0ad  mov     rcx, [rcx+0E8h]; string
0x14001a0b4  test    rcx, rcx
0x14001a0b7  jz      short loc_14001A0E2
0x14001a0b9  call    cs:__imp_WindowsDuplicateString
0x14001a0bf  mov     ebx, eax
0x14001a0c1  test    eax, eax
0x14001a0c3  jns     short loc_14001A0E2
0x14001a0c5  mov     rcx, [rsp+28h]; this
0x14001a0ca  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a0d1  mov     r9d, eax; char *
0x14001a0d4  mov     edx, 19Bh; void *
0x14001a0d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a0de  mov     eax, ebx
0x14001a0e0  jmp     short loc_14001A0E4
0x14001a0e2  xor     eax, eax
0x14001a0e4  add     rsp, 20h
0x14001a0e8  pop     rbx
0x14001a0e9  retn
```
