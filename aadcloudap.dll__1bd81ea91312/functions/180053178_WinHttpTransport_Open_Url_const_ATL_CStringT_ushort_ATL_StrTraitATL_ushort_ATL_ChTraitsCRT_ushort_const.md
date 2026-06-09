# WinHttpTransport::Open(Url const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180053178`
- end: `0x180053325`
- name: `?Open@WinHttpTransport@@AEAAJAEBVUrl@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180054230`

## callees

- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180053178`
- `0x180071e14`
- `0x1800a2d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005329c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005329c`
- `WINHTTP!WinHttpOpenRequest` at `0x180053282`
- `WINHTTP!WinHttpOpenRequest` at `0x180053282`

## string_xrefs

- `0x1800531a3`: `WinHttpTransport::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpTransport::Open(__int64 a1, __int64 a2, LPCWSTR *a3)
{
  DWORD dwFlags; // ebp
  LPCWSTR v7; // rbx
  signed int LastError; // eax
  unsigned int v9; // ebx
  const char *v11[6]; // [rsp+50h] [rbp-48h] BYREF
  int v12; // [rsp+A0h] [rbp+8h] BYREF
  LPCWSTR pwszObjectName; // [rsp+B8h] [rbp+20h] BYREF

  v12 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v11,
    (int)"winhttptransport.cpp",
    (int)"WinHttpTransport::Open",
    (int)&v12);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v12 = -2147187581;
LABEL_11:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws");
    goto LABEL_12;
  }
  dwFlags = 0;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 8) + 41LL) )
  {
    if ( *(_DWORD *)(a2 + 20) != 2 )
    {
      v12 = -2147187576;
      goto LABEL_11;
    }
    dwFlags = 0x800000;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &pwszObjectName,
    *(_QWORD *)(a2 + 72),
    (unsigned int)(*(_DWORD *)(a2 + 80) + *(_DWORD *)(a2 + 96)));
  v7 = pwszObjectName;
  *(_QWORD *)(a1 + 32) = WinHttpOpenRequest(*(HINTERNET *)(a1 + 24), *a3, pwszObjectName, 0, 0, 0, dwFlags);
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  if ( !*(_QWORD *)(a1 + 32) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = LastError;
    if ( LastError < 0 )
      goto LABEL_11;
  }
LABEL_12:
  v9 = v12;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v11);
  return v9;
}

```

## disassembly

```asm
0x180053178  mov     rax, rsp
0x18005317b  mov     [rax+10h], rbx
0x18005317f  mov     [rax+18h], rbp
0x180053183  push    rsi
0x180053184  push    r12
0x180053186  push    r14
0x180053188  sub     rsp, 80h
0x18005318f  mov     r14, r8
0x180053192  mov     rbx, rdx
0x180053195  mov     rsi, rcx
0x180053198  mov     dword ptr [rax+8], 0
0x18005319f  lea     r9, [rax+8]
0x1800531a3  lea     r8, aWinhttptranspo_4; "WinHttpTransport::Open"
0x1800531aa  lea     r12, aOnecoreuapDsEx_38+21h; "winhttptransport.cpp"
0x1800531b1  mov     rdx, r12
0x1800531b4  lea     rcx, [rax-48h]
0x1800531b8  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800531bd  nop
0x1800531be  cmp     qword ptr [rsi+18h], 0
0x1800531c3  jnz     short loc_1800531F6
0x1800531c5  mov     eax, 80048483h
0x1800531ca  mov     [rsp+98h+arg_0], eax
0x1800531d1  lea     rcx, base
0x1800531d8  mov     [rsp+98h+var_58], rcx
0x1800531dd  lea     rcx, aHresult; "HRESULT"
0x1800531e4  mov     [rsp+98h+var_60], rcx
0x1800531e9  mov     [rsp+98h+dwFlags], 0B7h
0x1800531f1  jmp     loc_1800532D9
0x1800531f6  xor     ebp, ebp
0x1800531f8  mov     rax, [rsi+8]
0x1800531fc  cmp     [rax+29h], bpl
0x180053200  jz      short loc_18005323E
0x180053202  cmp     dword ptr [rbx+14h], 2
0x180053206  jz      short loc_180053239
0x180053208  mov     eax, 80048488h
0x18005320d  mov     [rsp+98h+arg_0], eax
0x180053214  lea     rcx, base
0x18005321b  mov     [rsp+98h+var_58], rcx
0x180053220  lea     rcx, aHresult; "HRESULT"
0x180053227  mov     [rsp+98h+var_60], rcx
0x18005322c  mov     [rsp+98h+dwFlags], 0BEh
0x180053234  jmp     loc_1800532D9
0x180053239  mov     ebp, 800000h
0x18005323e  mov     r8d, [rbx+60h]
0x180053242  add     r8d, [rbx+50h]
0x180053246  mov     rdx, [rbx+48h]
0x18005324a  lea     rcx, [rsp+98h+pwszObjectName]
0x180053252  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x180053257  mov     rbx, [rsp+98h+pwszObjectName]
0x18005325f  mov     [rsp+98h+dwFlags], ebp; dwFlags
0x180053263  mov     [rsp+98h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18005326c  mov     [rsp+98h+pwszReferrer], 0; pwszReferrer
0x180053275  xor     r9d, r9d; pwszVersion
0x180053278  mov     r8, rbx; pwszObjectName
0x18005327b  mov     rdx, [r14]; pwszVerb
0x18005327e  mov     rcx, [rsi+18h]; hConnect
0x180053282  call    cs:__imp_WinHttpOpenRequest
0x180053288  mov     [rsi+20h], rax
0x18005328c  lea     rcx, [rbx-18h]; this
0x180053290  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053295  cmp     qword ptr [rsi+20h], 0
0x18005329a  jnz     short loc_1800532F9
0x18005329c  call    cs:__imp_GetLastError
0x1800532a2  test    eax, eax
0x1800532a4  jle     short loc_1800532AE
0x1800532a6  movzx   eax, ax
0x1800532a9  or      eax, 80070000h
0x1800532ae  mov     [rsp+98h+arg_0], eax
0x1800532b5  test    eax, eax
0x1800532b7  jns     short loc_1800532F9
0x1800532b9  lea     rcx, base
0x1800532c0  mov     [rsp+98h+var_58], rcx
0x1800532c5  lea     rcx, aHresult; "HRESULT"
0x1800532cc  mov     [rsp+98h+var_60], rcx
0x1800532d1  mov     [rsp+98h+dwFlags], 0CFh
0x1800532d9  mov     [rsp+98h+ppwszAcceptTypes], r12
0x1800532de  mov     r9d, 2
0x1800532e4  mov     dword ptr [rsp+98h+pwszReferrer], eax
0x1800532e8  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800532ef  xor     edx, edx
0x1800532f1  mov     ecx, r9d
0x1800532f4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800532f9  mov     ebx, [rsp+98h+arg_0]
0x180053300  lea     rcx, [rsp+98h+var_48]
0x180053305  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18005330a  mov     eax, ebx
0x18005330c  lea     r11, [rsp+98h+var_18]
0x180053314  mov     rbx, [r11+28h]
0x180053318  mov     rbp, [r11+30h]
0x18005331c  mov     rsp, r11
0x18005331f  pop     r14
0x180053321  pop     r12
0x180053323  pop     rsi
0x180053324  retn
```
