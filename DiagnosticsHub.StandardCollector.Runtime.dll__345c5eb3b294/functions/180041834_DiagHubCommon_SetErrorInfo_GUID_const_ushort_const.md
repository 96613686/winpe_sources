# DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)

- ea: `0x180041834`
- end: `0x180041937`
- name: `?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z`
- size: `259`
- prototype: `void __fastcall(DiagHubCommon *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `25`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004d10`
- `0x180004ed0`
- `0x180004fe0`
- `0x1800051c0`
- `0x1800052a0`
- `0x180005530`
- `0x1800062b0`
- `0x180006420`
- `0x180006544`
- `0x18000dd60`
- `0x18000fc68`
- `0x18000fec4`
- `0x18001c978`
- `0x18001ddc0`
- `0x18001e1b0`
- `0x18001f100`
- `0x18001f82c`
- `0x180020338`
- `0x180020ccc`
- `0x180022ae4`
- `0x18002a80c`
- `0x180032470`
- `0x1800352ec`
- `0x18004d131`
- `0x18004df7f`

## callees

- `0x180041834`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800418e8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800418e8`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18004186a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18004186a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall DiagHubCommon::SetErrorInfo(DiagHubCommon *this, const OLECHAR *a2, const unsigned __int16 *a3)
{
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *perrinfo; // [rsp+28h] [rbp-20h] BYREF

  if ( a2 )
  {
    pperrinfo = 0;
    if ( CreateErrorInfo(&pperrinfo) >= 0
      && (a2 == &word_180055D48
       || ((int (__fastcall *)(ICreateErrorInfo *, const OLECHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, a2) >= 0)
      && ((int (__fastcall *)(ICreateErrorInfo *, DiagHubCommon *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, this) >= 0 )
    {
      perrinfo = 0;
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
             &perrinfo) >= 0 )
        SetErrorInfo(0, perrinfo);
      if ( perrinfo )
        ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    }
    if ( pperrinfo )
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x180041834  test    rdx, rdx
0x180041837  jz      locret_180041936
0x18004183d  mov     [rsp+arg_10], rbx
0x180041842  push    rdi
0x180041843  sub     rsp, 40h
0x180041847  mov     rax, cs:__security_cookie
0x18004184e  xor     rax, rsp
0x180041851  mov     [rsp+48h+var_18], rax
0x180041856  mov     rbx, rdx
0x180041859  mov     rdi, rcx
0x18004185c  mov     [rsp+48h+pperrinfo], 0
0x180041865  lea     rcx, [rsp+48h+pperrinfo]; pperrinfo
0x18004186a  call    cs:__imp_CreateErrorInfo
0x180041870  test    eax, eax
0x180041872  js      loc_180041907
0x180041878  lea     rax, word_180055D48
0x18004187f  cmp     rbx, rax
0x180041882  jz      short loc_18004189D
0x180041884  mov     rcx, [rsp+48h+pperrinfo]
0x180041889  mov     rax, [rcx]
0x18004188c  mov     rdx, rbx
0x18004188f  mov     rax, [rax+28h]
0x180041893  call    cs:__guard_dispatch_icall_fptr
0x180041899  test    eax, eax
0x18004189b  js      short loc_180041907
0x18004189d  mov     rcx, [rsp+48h+pperrinfo]
0x1800418a2  mov     rax, [rcx]
0x1800418a5  mov     rdx, rdi
0x1800418a8  mov     rax, [rax+18h]
0x1800418ac  call    cs:__guard_dispatch_icall_fptr
0x1800418b2  test    eax, eax
0x1800418b4  js      short loc_180041907
0x1800418b6  mov     [rsp+48h+perrinfo], 0
0x1800418bf  mov     rcx, [rsp+48h+pperrinfo]
0x1800418c4  mov     rax, [rcx]
0x1800418c7  lea     r8, [rsp+48h+perrinfo]
0x1800418cc  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x1800418d3  mov     rax, [rax]
0x1800418d6  call    cs:__guard_dispatch_icall_fptr
0x1800418dc  nop
0x1800418dd  test    eax, eax
0x1800418df  js      short loc_1800418EF
0x1800418e1  mov     rdx, [rsp+48h+perrinfo]; perrinfo
0x1800418e6  xor     ecx, ecx; dwReserved
0x1800418e8  call    cs:__imp_SetErrorInfo
0x1800418ee  nop
0x1800418ef  mov     rcx, [rsp+48h+perrinfo]
0x1800418f4  test    rcx, rcx
0x1800418f7  jz      short loc_180041907
0x1800418f9  mov     rax, [rcx]
0x1800418fc  mov     rax, [rax+10h]
0x180041900  call    cs:__guard_dispatch_icall_fptr
0x180041906  nop
0x180041907  mov     rcx, [rsp+48h+pperrinfo]
0x18004190c  test    rcx, rcx
0x18004190f  jz      short loc_18004191F
0x180041911  mov     rax, [rcx]
0x180041914  mov     rax, [rax+10h]
0x180041918  call    cs:__guard_dispatch_icall_fptr
0x18004191e  nop
0x18004191f  mov     rcx, [rsp+48h+var_18]
0x180041924  xor     rcx, rsp; StackCookie
0x180041927  call    __security_check_cookie
0x18004192c  mov     rbx, [rsp+48h+arg_10]
0x180041931  add     rsp, 40h
0x180041935  pop     rdi
0x180041936  retn
```
