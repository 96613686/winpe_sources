# VirtualPrinterHelper::IsVirtualPrinter(ushort const *)

- ea: `0x18004d750`
- end: `0x18004d7cc`
- name: `?IsVirtualPrinter@VirtualPrinterHelper@@YA_NPEBG@Z`
- size: `124`
- prototype: `bool __fastcall(VirtualPrinterHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cfc4`
- `0x18004d518`

## callees

- `0x180012754`
- `0x1800213ac`
- `0x18004d750`
- `0x18004d7d4`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x18004d774`
- `WINSPOOL!OpenPrinterW` at `0x18004d774`

## pseudocode

```c
bool __fastcall VirtualPrinterHelper::IsVirtualPrinter(WCHAR *this, const unsigned __int16 *a2)
{
  bool v2; // bl
  int *v3; // r8
  int IsVirtualPrinterCommon; // eax
  struct _PRINTER_DEFAULTSW v6; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+58h] [rbp+10h] BYREF
  PrintCore *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  memset(&v6, 0, sizeof(v6));
  v2 = 0;
  if ( OpenPrinterW(this, (LPHANDLE)&v9, &v6) )
  {
    v8 = 0;
    IsVirtualPrinterCommon = PrintCore::IsVirtualPrinterCommon(v9, &v8, v3);
    v2 = v8 != 0;
    if ( IsVirtualPrinterCommon < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\VirtualPrinterHelper.h",
        (const char *)(unsigned int)IsVirtualPrinterCommon,
        (int)v6.pDatatype);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v9);
  return v2;
}

```

## disassembly

```asm
0x18004d750  mov     r11, rsp
0x18004d753  push    rbx
0x18004d754  sub     rsp, 40h
0x18004d758  xor     eax, eax
0x18004d75a  lea     r8, [r11-28h]; pDefault
0x18004d75e  xorps   xmm0, xmm0
0x18004d761  mov     [r11+18h], rax
0x18004d765  movups  xmmword ptr [rsp+48h+var_28.pDatatype], xmm0; int
0x18004d76a  lea     rdx, [r11+18h]; phPrinter
0x18004d76e  mov     [r11-18h], rax
0x18004d772  xor     bl, bl
0x18004d774  call    cs:__imp_OpenPrinterW
0x18004d77a  test    eax, eax
0x18004d77c  jz      short loc_18004D7BA
0x18004d77e  mov     rcx, [rsp+48h+arg_10]; this
0x18004d783  lea     rdx, [rsp+48h+arg_8]; void *
0x18004d788  mov     [rsp+48h+arg_8], 0
0x18004d790  call    ?IsVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsVirtualPrinterCommon(void *,int *)
0x18004d795  cmp     [rsp+48h+arg_8], 0
0x18004d79a  setnz   bl
0x18004d79d  test    eax, eax
0x18004d79f  jns     short loc_18004D7BA
0x18004d7a1  mov     rcx, [rsp+48h]; this
0x18004d7a6  lea     r8, aOnecoreuapPrin_35; "onecoreuap\\printscan\\print\\workflow"...
0x18004d7ad  mov     r9d, eax; char *
0x18004d7b0  mov     edx, 11h; void *
0x18004d7b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d7ba  lea     rcx, [rsp+48h+arg_10]
0x18004d7bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d7c4  mov     al, bl
0x18004d7c6  add     rsp, 40h
0x18004d7ca  pop     rbx
0x18004d7cb  retn
```
