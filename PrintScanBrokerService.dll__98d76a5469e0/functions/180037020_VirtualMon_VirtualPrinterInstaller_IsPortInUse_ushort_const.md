# VirtualMon::VirtualPrinterInstaller::IsPortInUse(ushort const *)

- ea: `0x180037020`
- end: `0x1800370e1`
- name: `?IsPortInUse@VirtualPrinterInstaller@VirtualMon@@AEAA_NPEBG@Z`
- size: `193`
- prototype: `bool __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180037210`

## callees

- `0x1800230fc`
- `0x180036834`
- `0x180037020`
- `0x180038174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037092`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037092`

## string_xrefs

- `0x18003703a`: `VirtualMon::VirtualPrinterInstaller::IsPortInUse`
- `0x1800370bb`: `VirtualMon::VirtualPrinterInstaller::IsPortInUse`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall VirtualMon::VirtualPrinterInstaller::IsPortInUse(
        VirtualMon::VirtualPrinterInstaller *this,
        const unsigned __int16 *a2)
{
  char v4; // si
  __int64 v5; // rbx
  DWORD v6; // edi
  __int128 v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]
  DWORD v10; // [rsp+80h] [rbp+18h] BYREF

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInstaller::IsPortInUse", L"Port: %s", a2);
  v10 = 0;
  v8 = 0;
  v9 = 0;
  VirtualMon::VirtualPrinterInstaller::EnumeratePrinters((__int64)this, &v10, (__int64)&v8);
  v4 = 0;
  v5 = v8;
  v6 = 0;
  if ( v10 )
  {
    while ( (unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v5 + 24)) )
    {
      ++v6;
      v5 += 136;
      if ( v6 >= v10 )
        goto LABEL_6;
    }
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::IsPortInUse",
      L"Found Printer using port: %ws",
      *(_QWORD *)(v5 + 8));
    v4 = 1;
  }
LABEL_6:
  std::vector<unsigned char>::_Tidy(&v8);
  return v4;
}

```

## disassembly

```asm
0x180037020  push    rbx
0x180037022  push    rsi
0x180037023  push    rdi
0x180037024  push    r14
0x180037026  sub     rsp, 48h
0x18003702a  mov     r14, rdx
0x18003702d  mov     rbx, rcx
0x180037030  mov     r8, rdx
0x180037033  lea     rdx, aPortS; "Port: %s"
0x18003703a  lea     rcx, aVirtualmonVirt_6; "VirtualMon::VirtualPrinterInstaller::Is"...
0x180037041  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037046  mov     [rsp+68h+arg_10], 0
0x180037051  xorps   xmm0, xmm0
0x180037054  movdqu  [rsp+68h+var_48], xmm0
0x18003705a  mov     [rsp+68h+var_38], 0
0x180037063  lea     r8, [rsp+68h+var_48]
0x180037068  lea     rdx, [rsp+68h+arg_10]
0x180037070  mov     rcx, rbx
0x180037073  call    ?EnumeratePrinters@VirtualPrinterInstaller@VirtualMon@@AEAAXAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VirtualMon::VirtualPrinterInstaller::EnumeratePrinters(ulong &,std::vector<uchar> &)
0x180037078  xor     sil, sil
0x18003707b  mov     rbx, qword ptr [rsp+68h+var_48]
0x180037080  xor     edi, edi
0x180037082  cmp     [rsp+68h+arg_10], edi
0x180037089  jbe     short loc_1800370CA
0x18003708b  mov     rdx, [rbx+18h]
0x18003708f  mov     rcx, r14
0x180037092  call    cs:__imp__o__wcsicmp
0x180037098  test    eax, eax
0x18003709a  jz      short loc_1800370B0
0x18003709c  inc     edi
0x18003709e  add     rbx, 88h
0x1800370a5  cmp     edi, [rsp+68h+arg_10]
0x1800370ac  jb      short loc_18003708B
0x1800370ae  jmp     short loc_1800370CA
0x1800370b0  mov     r8, [rbx+8]
0x1800370b4  lea     rdx, aFoundPrinterUs; "Found Printer using port: %ws"
0x1800370bb  lea     rcx, aVirtualmonVirt_6; "VirtualMon::VirtualPrinterInstaller::Is"...
0x1800370c2  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800370c7  mov     sil, 1
0x1800370ca  lea     rcx, [rsp+68h+var_48]
0x1800370cf  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800370d4  mov     al, sil
0x1800370d7  add     rsp, 48h
0x1800370db  pop     r14
0x1800370dd  pop     rdi
0x1800370de  pop     rsi
0x1800370df  pop     rbx
0x1800370e0  retn
```
