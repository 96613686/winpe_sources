# ipx::mtf::SuggestionClientDCOMFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x18001d120`
- end: `0x18001d17d`
- name: `?_CreateIUnknownInstance@SuggestionClientDCOMFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `93`
- prototype: `int(ipx::mtf::SuggestionClientDCOMFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001fc4`
- `0x180006074`
- `0x1800140d4`
- `0x18001d120`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::SuggestionClientDCOMFactory::_CreateIUnknownInstance(
        ipx::mtf::SuggestionClientDCOMFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  struct IUnknown *v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D4,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  else
  {
    v5 = (struct IUnknown *)operator new(0xD0u);
    if ( v5 )
      v5 = (struct IUnknown *)ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient((__int64)v5, 1, 0);
    *a3 = v5;
    return 0;
  }
}

```

## disassembly

```asm
0x18001d120  push    rbx; int
0x18001d122  sub     rsp, 20h
0x18001d126  mov     rbx, r8
0x18001d129  test    rdx, rdx
0x18001d12c  jz      short loc_18001D150
0x18001d12e  mov     rcx, [rsp+28h]; this
0x18001d133  mov     ebx, 80070057h
0x18001d138  mov     r9d, ebx; char *
0x18001d13b  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001d142  mov     edx, 9D4h; void *
0x18001d147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d14c  mov     eax, ebx
0x18001d14e  jmp     short loc_18001D177
0x18001d150  mov     ecx, 0D0h; Size
0x18001d155  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d15a  mov     [rsp+28h+arg_8], rax
0x18001d15f  test    rax, rax
0x18001d162  jz      short loc_18001D172
0x18001d164  xor     r8d, r8d
0x18001d167  mov     dl, 1
0x18001d169  mov     rcx, rax
0x18001d16c  call    ??0CMtfSuggestionClient@mtf@ipx@@QEAA@W4MTFServerConnection@12@W4MTFClientType@12@@Z; ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(ipx::mtf::MTFServerConnection,ipx::mtf::MTFClientType)
0x18001d171  nop
0x18001d172  mov     [rbx], rax
0x18001d175  xor     eax, eax
0x18001d177  add     rsp, 20h
0x18001d17b  pop     rbx
0x18001d17c  retn
```
