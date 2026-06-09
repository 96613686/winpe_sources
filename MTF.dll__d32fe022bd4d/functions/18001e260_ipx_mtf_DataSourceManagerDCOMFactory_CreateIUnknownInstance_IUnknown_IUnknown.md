# ipx::mtf::DataSourceManagerDCOMFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x18001e260`
- end: `0x18001e2cb`
- name: `?_CreateIUnknownInstance@DataSourceManagerDCOMFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `107`
- prototype: `int(ipx::mtf::DataSourceManagerDCOMFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001fc4`
- `0x180006074`
- `0x1800140d4`
- `0x18001e260`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::DataSourceManagerDCOMFactory::_CreateIUnknownInstance(
        ipx::mtf::DataSourceManagerDCOMFactory *this,
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
      (void *)0x25,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\dsmanager.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  else
  {
    v5 = operator new(0xD0u);
    if ( v5 )
      v5 = (void *)ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient((__int64)v5, 1, 1);
    *a3 = (struct IUnknown *)(((unsigned __int64)v5 + 8) & -(__int64)(v5 != 0));
    return 0;
  }
}

```

## disassembly

```asm
0x18001e260  push    rbx; int
0x18001e262  sub     rsp, 20h
0x18001e266  mov     rbx, r8
0x18001e269  test    rdx, rdx
0x18001e26c  jz      short loc_18001E290
0x18001e26e  mov     rcx, [rsp+28h]; this
0x18001e273  mov     ebx, 80070057h
0x18001e278  mov     r9d, ebx; char *
0x18001e27b  lea     r8, aMincoreTextinp_4; "mincore\\textinput\\dev\\mtf\\client\\d"...
0x18001e282  mov     edx, 25h ; '%'; void *
0x18001e287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e28c  mov     eax, ebx
0x18001e28e  jmp     short loc_18001E2C5
0x18001e290  mov     ecx, 0D0h; Size
0x18001e295  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e29a  mov     [rsp+28h+arg_8], rax
0x18001e29f  test    rax, rax
0x18001e2a2  jz      short loc_18001E2B3
0x18001e2a4  mov     r8b, 1
0x18001e2a7  mov     dl, r8b
0x18001e2aa  mov     rcx, rax
0x18001e2ad  call    ??0CMtfSuggestionClient@mtf@ipx@@QEAA@W4MTFServerConnection@12@W4MTFClientType@12@@Z; ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(ipx::mtf::MTFServerConnection,ipx::mtf::MTFClientType)
0x18001e2b2  nop
0x18001e2b3  lea     rcx, [rax+8]
0x18001e2b7  neg     rax
0x18001e2ba  sbb     rax, rax
0x18001e2bd  and     rax, rcx
0x18001e2c0  mov     [rbx], rax
0x18001e2c3  xor     eax, eax
0x18001e2c5  add     rsp, 20h
0x18001e2c9  pop     rbx
0x18001e2ca  retn
```
