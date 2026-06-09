# ipx::mtf::DataSourceManagerFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x18001e2e0`
- end: `0x18001e34a`
- name: `?_CreateIUnknownInstance@DataSourceManagerFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `106`
- prototype: `int(ipx::mtf::DataSourceManagerFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001fc4`
- `0x180006074`
- `0x1800140d4`
- `0x18001e2e0`

## pseudocode

```c
__int64 __fastcall ipx::mtf::DataSourceManagerFactory::_CreateIUnknownInstance(
        ipx::mtf::DataSourceManagerFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  void *v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\dsmanager.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  else
  {
    v5 = operator new(0xD0u);
    if ( v5 )
      v5 = (void *)ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient((__int64)v5, 0, 1);
    *a3 = (struct IUnknown *)(((unsigned __int64)v5 + 8) & -(__int64)(v5 != 0));
    return 0;
  }
}

```

## disassembly

```asm
0x18001e2e0  push    rbx; int
0x18001e2e2  sub     rsp, 20h
0x18001e2e6  mov     rbx, r8
0x18001e2e9  test    rdx, rdx
0x18001e2ec  jz      short loc_18001E310
0x18001e2ee  mov     rcx, [rsp+28h]; this
0x18001e2f3  mov     ebx, 80070057h
0x18001e2f8  mov     r9d, ebx; char *
0x18001e2fb  lea     r8, aMincoreTextinp_4; "mincore\\textinput\\dev\\mtf\\client\\d"...
0x18001e302  mov     edx, 1Bh; void *
0x18001e307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e30c  mov     eax, ebx
0x18001e30e  jmp     short loc_18001E344
0x18001e310  mov     ecx, 0D0h; Size
0x18001e315  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e31a  mov     [rsp+28h+arg_8], rax
0x18001e31f  test    rax, rax
0x18001e322  jz      short loc_18001E332
0x18001e324  mov     r8b, 1
0x18001e327  xor     edx, edx
0x18001e329  mov     rcx, rax
0x18001e32c  call    ??0CMtfSuggestionClient@mtf@ipx@@QEAA@W4MTFServerConnection@12@W4MTFClientType@12@@Z; ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(ipx::mtf::MTFServerConnection,ipx::mtf::MTFClientType)
0x18001e331  nop
0x18001e332  lea     rcx, [rax+8]
0x18001e336  neg     rax
0x18001e339  sbb     rax, rax
0x18001e33c  and     rax, rcx
0x18001e33f  mov     [rbx], rax
0x18001e342  xor     eax, eax
0x18001e344  add     rsp, 20h
0x18001e348  pop     rbx
0x18001e349  retn
```
