# PrintCore::IppPrinterAttributesCache::GetV4DriverDirectoryPath(void)

- ea: `0x18003c1b8`
- end: `0x18003c2c4`
- name: `?GetV4DriverDirectoryPath@IppPrinterAttributesCache@PrintCore@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `268`
- prototype: `__int64 __fastcall(HANDLE *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800387b4`

## callees

- `0x180004804`
- `0x1800127c4`
- `0x180020e44`
- `0x180021348`
- `0x18003c1b8`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18003c1f6`
- `WINSPOOL!GetPrinterDataW` at `0x18003c269`
- `WINSPOOL!GetPrinterDataW` at `0x18003c1f6`
- `WINSPOOL!GetPrinterDataW` at `0x18003c269`

## string_xrefs

- `0x18003c1ec`: `PrintQueueV4DriverDirectory`
- `0x18003c25f`: `PrintQueueV4DriverDirectory`
- `0x18003c20b`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`
- `0x18003c27b`: `OneCoreUap\Internal\Printscan\inc\ippprinterattributescache.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintCore::IppPrinterAttributesCache::GetV4DriverDirectoryPath(HANDLE *a1, __int64 a2)
{
  DWORD PrinterDataW; // eax
  BYTE *v5; // rdi
  DWORD v6; // eax
  DWORD nSize; // [rsp+20h] [rbp-28h]
  DWORD nSizea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbNeeded; // [rsp+50h] [rbp+8h] BYREF
  BYTE *v12; // [rsp+60h] [rbp+18h] BYREF

  pcbNeeded = 0;
  PrinterDataW = GetPrinterDataW(*a1, (LPWSTR)L"PrintQueueV4DriverDirectory", 0, 0, 0, &pcbNeeded);
  if ( PrinterDataW != 234 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x29,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
      (const char *)PrinterDataW,
      nSize);
  v5 = (BYTE *)operator new[](saturated_mul((unsigned __int64)pcbNeeded >> 1, 2u));
  v12 = v5;
  v6 = GetPrinterDataW(*a1, (LPWSTR)L"PrintQueueV4DriverDirectory", 0, v5, pcbNeeded, &pcbNeeded);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2C,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\ippprinterattributescache.hxx",
      (const char *)v6,
      nSizea);
  std::wstring::wstring(a2, v5, &v5[2 * ((unsigned __int64)pcbNeeded >> 1) - 2]);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v12);
  return a2;
}

```

## disassembly

```asm
0x18003c1b8  mov     rax, rsp
0x18003c1bb  mov     [rax+10h], rbx
0x18003c1bf  mov     [rax+20h], rsi
0x18003c1c3  push    rdi
0x18003c1c4  sub     rsp, 40h
0x18003c1c8  mov     rbx, rdx
0x18003c1cb  mov     rsi, rcx
0x18003c1ce  mov     dword ptr [rax+8], 0
0x18003c1d5  lea     rax, [rax+8]
0x18003c1d9  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18003c1de  mov     [rsp+48h+nSize], 0; unsigned int
0x18003c1e6  xor     r9d, r9d; pData
0x18003c1e9  xor     r8d, r8d; pType
0x18003c1ec  lea     rdx, pValueName; "PrintQueueV4DriverDirectory"
0x18003c1f3  mov     rcx, [rcx]; hPrinter
0x18003c1f6  call    cs:__imp_GetPrinterDataW
0x18003c1fc  cmp     eax, 0EAh
0x18003c201  jz      short loc_18003C21D
0x18003c203  mov     rcx, [rsp+48h]; this
0x18003c208  mov     r9d, eax; char *
0x18003c20b  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x18003c212  mov     edx, 29h ; ')'; void *
0x18003c217  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c21d  mov     ecx, [rsp+48h+arg_0]
0x18003c221  shr     rcx, 1
0x18003c224  mov     eax, 2
0x18003c229  mul     rcx
0x18003c22c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c233  cmovb   rax, rcx
0x18003c237  mov     rcx, rax; unsigned __int64
0x18003c23a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c23f  mov     rdi, rax
0x18003c242  mov     [rsp+48h+arg_10], rax
0x18003c247  mov     ecx, [rsp+48h+arg_0]
0x18003c24b  lea     rax, [rsp+48h+arg_0]
0x18003c250  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18003c255  mov     [rsp+48h+nSize], ecx; unsigned int
0x18003c259  mov     r9, rdi; pData
0x18003c25c  xor     r8d, r8d; pType
0x18003c25f  lea     rdx, pValueName; "PrintQueueV4DriverDirectory"
0x18003c266  mov     rcx, [rsi]; hPrinter
0x18003c269  call    cs:__imp_GetPrinterDataW
0x18003c26f  mov     rcx, [rsp+48h]; this
0x18003c274  test    eax, eax
0x18003c276  jz      short loc_18003C28D
0x18003c278  mov     r9d, eax; char *
0x18003c27b  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\i"...
0x18003c282  mov     edx, 2Ch ; ','; void *
0x18003c287  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c28d  mov     eax, [rsp+48h+arg_0]
0x18003c291  shr     rax, 1
0x18003c294  dec     rax
0x18003c297  lea     r8, [rdi+rax*2]
0x18003c29b  mov     rdx, rdi
0x18003c29e  mov     rcx, rbx
0x18003c2a1  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18003c2a6  nop
0x18003c2a7  lea     rcx, [rsp+48h+arg_10]
0x18003c2ac  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003c2b1  mov     rax, rbx
0x18003c2b4  mov     rbx, [rsp+48h+arg_8]
0x18003c2b9  mov     rsi, [rsp+48h+arg_18]
0x18003c2be  add     rsp, 40h
0x18003c2c2  pop     rdi
0x18003c2c3  retn
```
