# VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort(ushort const *)

- ea: `0x180037f28`
- end: `0x1800380c3`
- name: `?ValidateVirtualPrinterPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG@Z`
- size: `411`
- prototype: `void __fastcall(VirtualMon::VirtualPrinterInstaller *this, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003666c`

## callees

- `0x180003254`
- `0x1800080f8`
- `0x18001cfb4`
- `0x18002f194`
- `0x180037f28`
- `0x1800380cc`
- `0x180038174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fe8`
- `ext-ms-win-printer-winspool-l1-1-4!EnumPortsW` at `0x180037f7d`
- `ext-ms-win-printer-winspool-l1-1-4!EnumPortsW` at `0x180037fde`
- `ext-ms-win-printer-winspool-l1-1-4!EnumPortsW` at `0x180037f7d`
- `ext-ms-win-printer-winspool-l1-1-4!EnumPortsW` at `0x180037fde`

## string_xrefs

- `0x18003808d`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x18003809f`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800380b1`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180037f41`: `VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort`
- `0x180038049`: `VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort`
- `0x180038079`: `VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort(
        VirtualMon::VirtualPrinterInstaller *this,
        char *a2)
{
  const char *v3; // r9
  char v4; // bl
  BYTE *v6; // rdi
  const char *v7; // r9
  int v9; // edx
  char *v10; // rcx
  char *v11; // r9
  int v12; // r8d
  int v13; // eax
  int pcbNeeded; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  VirtualMon::VirtualPrinterInstaller *cbBuf; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcReturned; // [rsp+60h] [rbp+18h] BYREF
  BYTE *v18; // [rsp+68h] [rbp+20h] BYREF

  cbBuf = this;
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort",
    L"PortName: %ws",
    a2);
  pcReturned = 0;
  LODWORD(cbBuf) = 0;
  v4 = 1;
  if ( EnumPortsW(0, 2u, 0, 0, (LPDWORD)&cbBuf, &pcReturned) || GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v3);
  v6 = (BYTE *)operator new[]((unsigned int)cbBuf);
  v18 = v6;
  if ( !EnumPortsW(0, 2u, v6, (DWORD)cbBuf, (LPDWORD)&cbBuf, &pcReturned) && GetLastError() )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      v7);
  v9 = 0;
  if ( pcReturned )
  {
    while ( 1 )
    {
      v10 = *(char **)&v6[32 * v9];
      v11 = (char *)(a2 - v10);
      do
      {
        v12 = *(unsigned __int16 *)&v11[(_QWORD)v10];
        v13 = *(unsigned __int16 *)v10 - v12;
        if ( v13 )
          break;
        v10 += 2;
      }
      while ( v12 );
      if ( !v13 )
        break;
      if ( ++v9 >= pcReturned )
        goto LABEL_17;
    }
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort",
      L"Port Found");
  }
  else
  {
LABEL_17:
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInstaller::ValidateVirtualPrinterPort",
      L"Port not found");
    v4 = 0;
  }
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      (const char *)0x704,
      pcbNeeded);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v18);
}

```

## disassembly

```asm
0x180037f28  mov     [rsp+cbBuf], rcx
0x180037f2d  push    rbx
0x180037f2e  push    rsi
0x180037f2f  push    rdi
0x180037f30  sub     rsp, 30h
0x180037f34  mov     rsi, rdx
0x180037f37  mov     r8, rdx
0x180037f3a  lea     rdx, aPortnameWs; "PortName: %ws"
0x180037f41  lea     rcx, aVirtualmonVirt_12; "VirtualMon::VirtualPrinterInstaller::Va"...
0x180037f48  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037f4d  mov     [rsp+48h+arg_10], 0
0x180037f55  mov     dword ptr [rsp+48h+cbBuf], 0
0x180037f5d  lea     rax, [rsp+48h+arg_10]
0x180037f62  mov     [rsp+48h+pcReturned], rax; pcReturned
0x180037f67  lea     rax, [rsp+48h+cbBuf]
0x180037f6c  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180037f71  xor     r9d, r9d; cbBuf
0x180037f74  xor     r8d, r8d; pPort
0x180037f77  lea     edx, [r9+2]; Level
0x180037f7b  xor     ecx, ecx; pName
0x180037f7d  call    cs:__imp_EnumPortsW
0x180037f83  mov     ebx, 1
0x180037f88  test    eax, eax
0x180037f8a  jnz     short loc_180037F9B
0x180037f8c  call    cs:__imp_GetLastError
0x180037f92  cmp     eax, 7Ah ; 'z'
0x180037f95  jnz     short loc_180037F9B
0x180037f97  xor     al, al
0x180037f99  jmp     short loc_180037F9D
0x180037f9b  mov     al, bl
0x180037f9d  mov     rcx, [rsp+48h]; this
0x180037fa2  test    al, al
0x180037fa4  jnz     loc_18003809F
0x180037faa  mov     ecx, dword ptr [rsp+48h+cbBuf]; unsigned __int64
0x180037fae  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180037fb3  mov     rdi, rax
0x180037fb6  mov     [rsp+48h+arg_18], rax
0x180037fbb  lea     rax, [rsp+48h+arg_10]
0x180037fc0  mov     [rsp+48h+pcReturned], rax; pcReturned
0x180037fc5  lea     rax, [rsp+48h+cbBuf]
0x180037fca  mov     [rsp+48h+pcbNeeded], rax; int
0x180037fcf  mov     r9d, dword ptr [rsp+48h+cbBuf]; cbBuf
0x180037fd4  mov     r8, rdi; pPort
0x180037fd7  mov     edx, 2; Level
0x180037fdc  xor     ecx, ecx; pName
0x180037fde  call    cs:__imp_EnumPortsW
0x180037fe4  test    eax, eax
0x180037fe6  jnz     short loc_180037FF6
0x180037fe8  call    cs:__imp_GetLastError
0x180037fee  test    eax, eax
0x180037ff0  jz      short loc_180037FF6
0x180037ff2  mov     al, bl
0x180037ff4  jmp     short loc_180037FF8
0x180037ff6  xor     al, al
0x180037ff8  mov     rcx, [rsp+48h]; this
0x180037ffd  test    al, al
0x180037fff  jnz     loc_1800380B1
0x180038005  xor     edx, edx
0x180038007  mov     r10d, [rsp+48h+arg_10]
0x18003800c  test    r10d, r10d
0x18003800f  jz      short loc_180038042
0x180038011  mov     eax, edx
0x180038013  shl     rax, 5
0x180038017  mov     rcx, [rax+rdi]
0x18003801b  mov     r9, rsi
0x18003801e  sub     r9, rcx
0x180038021  movzx   eax, word ptr [rcx]
0x180038024  movzx   r8d, word ptr [rcx+r9]
0x180038029  sub     eax, r8d
0x18003802c  jnz     short loc_180038037
0x18003802e  add     rcx, 2
0x180038032  test    r8d, r8d
0x180038035  jnz     short loc_180038021
0x180038037  test    eax, eax
0x180038039  jz      short loc_180038072
0x18003803b  add     edx, ebx
0x18003803d  cmp     edx, r10d
0x180038040  jb      short loc_180038011
0x180038042  lea     rdx, aPortNotFound; "Port not found"
0x180038049  lea     rcx, aVirtualmonVirt_12; "VirtualMon::VirtualPrinterInstaller::Va"...
0x180038050  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180038055  xor     bl, bl
0x180038057  mov     rcx, [rsp+48h]; this
0x18003805c  test    bl, bl
0x18003805e  jz      short loc_180038087
0x180038060  lea     rcx, [rsp+48h+arg_18]
0x180038065  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003806a  add     rsp, 30h
0x18003806e  pop     rdi
0x18003806f  pop     rsi
0x180038070  pop     rbx
0x180038071  retn
0x180038072  lea     rdx, aPortFound; "Port Found"
0x180038079  lea     rcx, aVirtualmonVirt_12; "VirtualMon::VirtualPrinterInstaller::Va"...
0x180038080  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180038085  jmp     short loc_180038057
0x180038087  mov     r9d, 704h; char *
0x18003808d  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180038094  mov     edx, 173h; void *
0x180038099  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003809f  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800380a6  mov     edx, 15Ah; void *
0x1800380ab  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800380b1  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800380b8  mov     edx, 160h; void *
0x1800380bd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
