# ipx::mtf::SuggestionClientFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x18001d190`
- end: `0x18001d1ed`
- name: `?_CreateIUnknownInstance@SuggestionClientFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `93`
- prototype: `int(ipx::mtf::SuggestionClientFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001fc4`
- `0x180006074`
- `0x1800140d4`
- `0x18001d190`

## pseudocode

```c
__int64 __fastcall ipx::mtf::SuggestionClientFactory::_CreateIUnknownInstance(
        ipx::mtf::SuggestionClientFactory *this,
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
      (void *)0x9CB,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  else
  {
    v5 = (struct IUnknown *)operator new(0xD0u);
    if ( v5 )
      v5 = (struct IUnknown *)ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient((__int64)v5, 0, 0);
    *a3 = v5;
    return 0;
  }
}

```

## disassembly

```asm
0x18001d190  push    rbx; int
0x18001d192  sub     rsp, 20h
0x18001d196  mov     rbx, r8
0x18001d199  test    rdx, rdx
0x18001d19c  jz      short loc_18001D1C0
0x18001d19e  mov     rcx, [rsp+28h]; this
0x18001d1a3  mov     ebx, 80070057h
0x18001d1a8  mov     r9d, ebx; char *
0x18001d1ab  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001d1b2  mov     edx, 9CBh; void *
0x18001d1b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1bc  mov     eax, ebx
0x18001d1be  jmp     short loc_18001D1E7
0x18001d1c0  mov     ecx, 0D0h; Size
0x18001d1c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d1ca  mov     [rsp+28h+arg_8], rax
0x18001d1cf  test    rax, rax
0x18001d1d2  jz      short loc_18001D1E2
0x18001d1d4  xor     r8d, r8d
0x18001d1d7  xor     edx, edx
0x18001d1d9  mov     rcx, rax
0x18001d1dc  call    ??0CMtfSuggestionClient@mtf@ipx@@QEAA@W4MTFServerConnection@12@W4MTFClientType@12@@Z; ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(ipx::mtf::MTFServerConnection,ipx::mtf::MTFClientType)
0x18001d1e1  nop
0x18001d1e2  mov     [rbx], rax
0x18001d1e5  xor     eax, eax
0x18001d1e7  add     rsp, 20h
0x18001d1eb  pop     rbx
0x18001d1ec  retn
```
