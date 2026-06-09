# DeviceConfiguration::EnumeratePrinters(ulong,ulong,ulong *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180016284`
- end: `0x180016400`
- name: `?EnumeratePrinters@DeviceConfiguration@@YAJKKPEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(DWORD Flags, __int64, DWORD *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180010e44`
- `0x1800153bc`
- `0x18001596c`

## callees

- `0x180002b28`
- `0x18000aeac`
- `0x18000d868`
- `0x18000f9ec`
- `0x18001616c`
- `0x180016284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162eb`
- `WINSPOOL!EnumPrintersW` at `0x1800162dd`
- `WINSPOOL!EnumPrintersW` at `0x180016371`
- `WINSPOOL!EnumPrintersW` at `0x1800162dd`
- `WINSPOOL!EnumPrintersW` at `0x180016371`

## string_xrefs

- `0x180016391`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\util.cpp`
- `0x1800163d5`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\util.cpp`
- `0x1800163b2`: `No printers are installed`
- `0x1800163b9`: `DeviceConfiguration::EnumeratePrinters`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::EnumeratePrinters(DWORD Flags, __int64 a2, DWORD *a3, __int64 a4)
{
  BOOL v7; // eax
  LPBYTE v8; // rdx
  __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  BYTE *v11; // rax
  size_t v12; // rbx
  BOOL v13; // eax
  const char *v14; // r9
  __int64 result; // rax
  const char *cbBuf; // [rsp+20h] [rbp-38h]
  const char *pcbNeeded; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD v19; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcReturned; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  v19 = 0;
  pcReturned = 0;
  v7 = EnumPrintersW(Flags, 0, 2u, 0, 0, &v19, &pcReturned);
  try
  {
    if ( v7 )
    {
      if ( !v19 )
      {
        DeviceConfigurationTelemetry::WriteDbgTraceInfo(
          "DeviceConfiguration::EnumeratePrinters",
          L"No printers are installed");
        return 0;
      }
    }
    else if ( GetLastError() == 122 )
    {
      v8 = *(LPBYTE *)a4;
      v9 = *(_QWORD *)(a4 + 8);
      v10 = v9 - *(_QWORD *)a4;
      if ( v19 < v10 )
      {
        v11 = &v8[v19];
LABEL_10:
        *(_QWORD *)(a4 + 8) = v11;
        goto LABEL_11;
      }
      if ( v19 > v10 )
      {
        if ( (unsigned __int64)v19 <= *(_QWORD *)(a4 + 16) - (_QWORD)v8 )
        {
          v12 = v19 - v10;
          memset_0(*(void **)(a4 + 8), 0, v12);
          v11 = (BYTE *)(v12 + v9);
          goto LABEL_10;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a4, v19);
      }
LABEL_11:
      v13 = EnumPrintersW(Flags, 0, 2u, *(LPBYTE *)a4, v19, &v19, &pcReturned);
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0x13,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\util.cpp",
        (const char *)!v13,
        (bool)"EnumPrinters (with buffer) failed!",
        pcbNeeded);
      *a3 = pcReturned;
      return 0;
    }
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x1C,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\util.cpp",
      "EnumPrinters (no buffer) failed!",
      cbBuf);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x21,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\util.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180016284  mov     rax, rsp
0x180016287  mov     [rax+8], rbx
0x18001628b  mov     [rax+20h], rsi
0x18001628f  mov     [rax+10h], edx
0x180016292  push    rdi
0x180016293  push    r14
0x180016295  push    r15
0x180016297  sub     rsp, 40h
0x18001629b  mov     rdi, r9
0x18001629e  mov     r14, r8
0x1800162a1  mov     r15d, ecx
0x1800162a4  mov     dword ptr [r8], 0
0x1800162ab  mov     dword ptr [rax+10h], 0
0x1800162b2  mov     dword ptr [rax+18h], 0
0x1800162b9  lea     rax, [rax+18h]
0x1800162bd  mov     [rsp+58h+pcReturned], rax; pcReturned
0x1800162c2  lea     rax, [rsp+58h+arg_8]
0x1800162c7  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x1800162cc  mov     [rsp+58h+cbBuf], 0; char *
0x1800162d4  xor     r9d, r9d; pPrinterEnum
0x1800162d7  xor     edx, edx; Name
0x1800162d9  lea     r8d, [r9+2]; Level
0x1800162dd  call    cs:__imp_EnumPrintersW
0x1800162e3  test    eax, eax
0x1800162e5  jnz     loc_1800163AB
0x1800162eb  call    cs:__imp_GetLastError
0x1800162f1  cmp     eax, 7Ah ; 'z'
0x1800162f4  jnz     loc_1800163C9
0x1800162fa  mov     ebx, [rsp+58h+arg_8]
0x1800162fe  mov     rdx, [rdi]
0x180016301  mov     rsi, [rdi+8]
0x180016305  mov     rcx, rsi
0x180016308  sub     rcx, rdx
0x18001630b  cmp     rbx, rcx
0x18001630e  jnb     short loc_180016316
0x180016310  lea     rax, [rdx+rbx]
0x180016314  jmp     short loc_180016345
0x180016316  jbe     short loc_180016349
0x180016318  mov     rax, [rdi+10h]
0x18001631c  sub     rax, rdx
0x18001631f  cmp     rbx, rax
0x180016322  jbe     short loc_180016331
0x180016324  mov     rdx, rbx
0x180016327  mov     rcx, rdi
0x18001632a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001632f  jmp     short loc_180016349
0x180016331  sub     rbx, rcx
0x180016334  mov     r8, rbx; Size
0x180016337  xor     edx, edx; Val
0x180016339  mov     rcx, rsi; void *
0x18001633c  call    memset_0
0x180016341  lea     rax, [rbx+rsi]
0x180016345  mov     [rdi+8], rax
0x180016349  lea     rax, [rsp+58h+arg_10]
0x18001634e  mov     [rsp+58h+pcReturned], rax; pcReturned
0x180016353  lea     rax, [rsp+58h+arg_8]
0x180016358  mov     [rsp+58h+pcbNeeded], rax; char *
0x18001635d  mov     eax, [rsp+58h+arg_8]
0x180016361  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180016365  mov     r9, [rdi]; pPrinterEnum
0x180016368  xor     edx, edx; Name
0x18001636a  lea     r8d, [rdx+2]; Level
0x18001636e  mov     ecx, r15d; Flags
0x180016371  call    cs:__imp_EnumPrintersW
0x180016377  test    eax, eax
0x180016379  setz    al
0x18001637c  mov     rcx, [rsp+58h]; this
0x180016381  lea     rdx, aEnumprintersWi_0; "EnumPrinters (with buffer) failed!"
0x180016388  mov     qword ptr [rsp+58h+cbBuf], rdx; bool
0x18001638d  movzx   r9d, al; char *
0x180016391  lea     r8, aPrintscanPrint_4; "printscan\\print\\spooler\\configuratio"...
0x180016398  mov     edx, 13h; void *
0x18001639d  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800163a2  mov     eax, [rsp+58h+arg_10]
0x1800163a6  mov     [r14], eax
0x1800163a9  jmp     short loc_1800163C5
0x1800163ab  cmp     [rsp+58h+arg_8], 0
0x1800163b0  jnz     short loc_1800163C9
0x1800163b2  lea     rdx, aNoPrintersAreI; "No printers are installed"
0x1800163b9  lea     rcx, aDeviceconfigur_9; "DeviceConfiguration::EnumeratePrinters"
0x1800163c0  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800163c5  xor     eax, eax
0x1800163c7  jmp     short loc_1800163EB
0x1800163c9  mov     rcx, [rsp+58h]; this
0x1800163ce  lea     r9, aEnumprintersNo; "EnumPrinters (no buffer) failed!"
0x1800163d5  lea     r8, aPrintscanPrint_4; "printscan\\print\\spooler\\configuratio"...
0x1800163dc  mov     edx, 1Ch; void *
0x1800163e1  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800163e7  mov     eax, [rsp+58h+arg_8]
0x1800163eb  mov     rbx, [rsp+58h+arg_0]
0x1800163f0  mov     rsi, [rsp+58h+arg_18]
0x1800163f5  add     rsp, 40h
0x1800163f9  pop     r15
0x1800163fb  pop     r14
0x1800163fd  pop     rdi
0x1800163fe  retn
```
