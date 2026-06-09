# Mpeg2DemuxTrace::CeHomeETWProvider::CeHomeETWProvider(ulong,ulong,ulong,ulong)

- ea: `0x180010870`
- end: `0x180010b1f`
- name: `??0CeHomeETWProvider@Mpeg2DemuxTrace@@IEAA@KKKK@Z`
- size: `687`
- prototype: `__int64 __fastcall(Mpeg2DemuxTrace::CeHomeETWProvider *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800103c8`

## callees

- `0x180001460`
- `0x180010870`
- `0x180012a58`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010908`
- `KERNEL32!GetProcAddress` at `0x18001091c`
- `KERNEL32!GetProcAddress` at `0x180010931`
- `KERNEL32!GetProcAddress` at `0x180010946`
- `KERNEL32!GetProcAddress` at `0x18001095b`
- `KERNEL32!GetProcAddress` at `0x180010970`
- `KERNEL32!GetProcAddress` at `0x180010985`
- `KERNEL32!GetProcAddress` at `0x18001099a`
- `KERNEL32!GetProcAddress` at `0x1800109af`
- `KERNEL32!GetProcAddress` at `0x180010908`
- `KERNEL32!GetProcAddress` at `0x18001091c`
- `KERNEL32!GetProcAddress` at `0x180010931`
- `KERNEL32!GetProcAddress` at `0x180010946`
- `KERNEL32!GetProcAddress` at `0x18001095b`
- `KERNEL32!GetProcAddress` at `0x180010970`
- `KERNEL32!GetProcAddress` at `0x180010985`
- `KERNEL32!GetProcAddress` at `0x18001099a`
- `KERNEL32!GetProcAddress` at `0x1800109af`
- `KERNEL32!LoadLibraryW` at `0x1800108eb`
- `KERNEL32!LoadLibraryW` at `0x1800108eb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800108e0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800108e0`

## string_xrefs

- `0x1800108ac`: `%SystemRoot%\ehome\ehTrace.dll`

## pseudocode

```c
Mpeg2DemuxTrace::CeHomeETWProvider *__fastcall Mpeg2DemuxTrace::CeHomeETWProvider::CeHomeETWProvider(
        Mpeg2DemuxTrace::CeHomeETWProvider *this)
{
  FARPROC *v1; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  FARPROC v8; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rax
  HMODULE v17; // rcx
  FARPROC v18; // rax
  HMODULE v19; // rcx
  FARPROC v20; // rax
  Mpeg2DemuxTrace::CeHomeETWProvider *result; // rax
  WCHAR Dst[128]; // [rsp+20h] [rbp-118h] BYREF

  v1 = (FARPROC *)((char *)this + 8);
  *(_QWORD *)this = &Mpeg2DemuxTrace::CeHomeETWProvider::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  ExpandEnvironmentStringsW(L"%SystemRoot%\\ehome\\ehTrace.dll", Dst, 0x80u);
  LibraryW = LoadLibraryW(Dst);
  v1[9] = (FARPROC)LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "ehRegisterTraceGUIDs");
    v5 = (HMODULE)v1[9];
    *v1 = ProcAddress;
    v6 = GetProcAddress(v5, "ehRegisterCounterGUID");
    v7 = (HMODULE)v1[9];
    v1[1] = v6;
    v8 = GetProcAddress(v7, "ehUnregisterTraceGUIDs");
    v9 = (HMODULE)v1[9];
    v1[2] = v8;
    v10 = GetProcAddress(v9, "ehUnregisterCounterGUIDs");
    v11 = (HMODULE)v1[9];
    v1[3] = v10;
    v12 = GetProcAddress(v11, "ehAllocateEventBuffer");
    v13 = (HMODULE)v1[9];
    v1[4] = v12;
    v14 = GetProcAddress(v13, "ehFreeEventBuffer");
    v15 = (HMODULE)v1[9];
    v1[5] = v14;
    v16 = GetProcAddress(v15, "ehIsTraceEnabled");
    v17 = (HMODULE)v1[9];
    v1[6] = v16;
    v18 = GetProcAddress(v17, "ehTraceCounter");
    v19 = (HMODULE)v1[9];
    v1[7] = v18;
    v20 = GetProcAddress(v19, "ehTraceEvent");
    v1[8] = v20;
    if ( !*v1 || !v1[1] || !v1[2] || !v1[3] || !v1[4] || !v1[5] || !v1[6] || !v1[7] || !v20 )
      Mpeg2DemuxTrace::CeHomeETWDLL::UnloadeHomeETWDll((Mpeg2DemuxTrace::CeHomeETWDLL *)v1);
  }
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 15) = v1;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = (char *)this + 96;
  *((_QWORD *)this + 16) = &Mpeg2DemuxTrace::CErrorEvents::`vftable';
  *((_QWORD *)this + 17) = &Mpeg2DemuxTrace::CErrorEvent::`vftable';
  *((_QWORD *)this + 22) = &Mpeg2DemuxTrace::CErrorEvent::`vftable';
  *((_QWORD *)this + 27) = &Mpeg2DemuxTrace::CErrorEvent::`vftable';
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 14) = (char *)this + 88;
  *((_QWORD *)this + 32) = &Mpeg2DemuxTrace::CTeHomeETWEvent<EH_PBDA_TAG_EVENT>::`vftable';
  result = this;
  *((_DWORD *)this + 38) = 1;
  *((_WORD *)this + 78) = 60;
  *((_DWORD *)this + 40) = 17;
  *((_QWORD *)this + 21) = (char *)this + 104;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 1;
  *((_WORD *)this + 98) = 20;
  *((_DWORD *)this + 50) = 19;
  *((_QWORD *)this + 26) = (char *)this + 104;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 1;
  *((_WORD *)this + 118) = 40;
  *((_DWORD *)this + 60) = 18;
  *((_QWORD *)this + 31) = (char *)this + 104;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 68) = 1;
  *((_WORD *)this + 138) = 60;
  *((_DWORD *)this + 70) = 8;
  *((_QWORD *)this + 36) = (char *)this + 104;
  return result;
}

```

## disassembly

```asm
0x180010870  mov     [rsp+arg_8], rbx
0x180010875  mov     [rsp+arg_10], rsi
0x18001087a  push    rdi
0x18001087b  sub     rsp, 130h
0x180010882  mov     rax, cs:__security_cookie
0x180010889  xor     rax, rsp
0x18001088c  mov     [rsp+138h+var_18], rax
0x180010894  lea     rdi, [rcx+8]
0x180010898  xor     esi, esi
0x18001089a  lea     rax, ??_7CeHomeETWProvider@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CeHomeETWProvider::`vftable'
0x1800108a1  mov     rbx, rcx
0x1800108a4  mov     [rcx], rax
0x1800108a7  lea     rdx, [rsp+138h+Dst]; lpDst
0x1800108ac  lea     rcx, Src; "%SystemRoot%\\ehome\\ehTrace.dll"
0x1800108b3  mov     [rdi], rsi
0x1800108b6  mov     r8d, 80h; nSize
0x1800108bc  mov     [rdi+8], rsi
0x1800108c0  mov     [rdi+10h], rsi
0x1800108c4  mov     [rdi+18h], rsi
0x1800108c8  mov     [rdi+20h], rsi
0x1800108cc  mov     [rdi+28h], rsi
0x1800108d0  mov     [rdi+30h], rsi
0x1800108d4  mov     [rdi+38h], rsi
0x1800108d8  mov     [rdi+40h], rsi
0x1800108dc  mov     [rdi+48h], rsi
0x1800108e0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800108e6  lea     rcx, [rsp+138h+Dst]; lpLibFileName
0x1800108eb  call    cs:__imp_LoadLibraryW
0x1800108f1  mov     [rdi+48h], rax
0x1800108f5  test    rax, rax
0x1800108f8  jz      loc_1800109F5
0x1800108fe  lea     rdx, aEhregistertrac; "ehRegisterTraceGUIDs"
0x180010905  mov     rcx, rax; hModule
0x180010908  call    cs:__imp_GetProcAddress
0x18001090e  mov     rcx, [rdi+48h]; hModule
0x180010912  lea     rdx, aEhregistercoun; "ehRegisterCounterGUID"
0x180010919  mov     [rdi], rax
0x18001091c  call    cs:__imp_GetProcAddress
0x180010922  mov     rcx, [rdi+48h]; hModule
0x180010926  lea     rdx, aEhunregistertr; "ehUnregisterTraceGUIDs"
0x18001092d  mov     [rdi+8], rax
0x180010931  call    cs:__imp_GetProcAddress
0x180010937  mov     rcx, [rdi+48h]; hModule
0x18001093b  lea     rdx, aEhunregisterco; "ehUnregisterCounterGUIDs"
0x180010942  mov     [rdi+10h], rax
0x180010946  call    cs:__imp_GetProcAddress
0x18001094c  mov     rcx, [rdi+48h]; hModule
0x180010950  lea     rdx, aEhallocateeven; "ehAllocateEventBuffer"
0x180010957  mov     [rdi+18h], rax
0x18001095b  call    cs:__imp_GetProcAddress
0x180010961  mov     rcx, [rdi+48h]; hModule
0x180010965  lea     rdx, aEhfreeeventbuf; "ehFreeEventBuffer"
0x18001096c  mov     [rdi+20h], rax
0x180010970  call    cs:__imp_GetProcAddress
0x180010976  mov     rcx, [rdi+48h]; hModule
0x18001097a  lea     rdx, aEhistraceenabl; "ehIsTraceEnabled"
0x180010981  mov     [rdi+28h], rax
0x180010985  call    cs:__imp_GetProcAddress
0x18001098b  mov     rcx, [rdi+48h]; hModule
0x18001098f  lea     rdx, aEhtracecounter; "ehTraceCounter"
0x180010996  mov     [rdi+30h], rax
0x18001099a  call    cs:__imp_GetProcAddress
0x1800109a0  mov     rcx, [rdi+48h]; hModule
0x1800109a4  lea     rdx, aEhtraceevent; "ehTraceEvent"
0x1800109ab  mov     [rdi+38h], rax
0x1800109af  call    cs:__imp_GetProcAddress
0x1800109b5  mov     [rdi+40h], rax
0x1800109b9  cmp     [rdi], rsi
0x1800109bc  jz      short loc_1800109ED
0x1800109be  cmp     [rdi+8], rsi
0x1800109c2  jz      short loc_1800109ED
0x1800109c4  cmp     [rdi+10h], rsi
0x1800109c8  jz      short loc_1800109ED
0x1800109ca  cmp     [rdi+18h], rsi
0x1800109ce  jz      short loc_1800109ED
0x1800109d0  cmp     [rdi+20h], rsi
0x1800109d4  jz      short loc_1800109ED
0x1800109d6  cmp     [rdi+28h], rsi
0x1800109da  jz      short loc_1800109ED
0x1800109dc  cmp     [rdi+30h], rsi
0x1800109e0  jz      short loc_1800109ED
0x1800109e2  cmp     [rdi+38h], rsi
0x1800109e6  jz      short loc_1800109ED
0x1800109e8  test    rax, rax
0x1800109eb  jnz     short loc_1800109F5
0x1800109ed  mov     rcx, rdi; this
0x1800109f0  call    ?UnloadeHomeETWDll@CeHomeETWDLL@Mpeg2DemuxTrace@@AEAAXXZ; Mpeg2DemuxTrace::CeHomeETWDLL::UnloadeHomeETWDll(void)
0x1800109f5  lea     rdx, [rbx+68h]
0x1800109f9  mov     [rbx+90h], rsi
0x180010a00  lea     rax, [rbx+60h]
0x180010a04  mov     [rdx+10h], rdi
0x180010a08  mov     [rax], esi
0x180010a0a  lea     rcx, [rbx+58h]
0x180010a0e  mov     [rdx], rax
0x180010a11  lea     rax, ??_7CErrorEvents@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CErrorEvents::`vftable'
0x180010a18  mov     [rbx+80h], rax
0x180010a1f  lea     rax, ??_7CErrorEvent@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CErrorEvent::`vftable'
0x180010a26  mov     [rbx+88h], rax
0x180010a2d  lea     rax, ??_7CErrorEvent@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CErrorEvent::`vftable'
0x180010a34  mov     [rbx+0B0h], rax
0x180010a3b  lea     rax, ??_7CErrorEvent@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CErrorEvent::`vftable'
0x180010a42  mov     [rbx+0D8h], rax
0x180010a49  lea     rax, ??_7?$CTeHomeETWEvent@UEH_PBDA_TAG_EVENT@@@Mpeg2DemuxTrace@@6B@; const Mpeg2DemuxTrace::CTeHomeETWEvent<EH_PBDA_TAG_EVENT>::`vftable'
0x180010a50  mov     [rcx], esi
0x180010a52  mov     [rdx+8], rcx
0x180010a56  mov     ecx, 1
0x180010a5b  mov     [rbx+100h], rax
0x180010a62  mov     rax, rbx
0x180010a65  mov     [rbx+98h], ecx
0x180010a6b  mov     word ptr [rbx+9Ch], 3Ch ; '<'
0x180010a74  mov     dword ptr [rbx+0A0h], 11h
0x180010a7e  mov     [rbx+0A8h], rdx
0x180010a85  mov     [rbx+0B8h], rsi
0x180010a8c  mov     [rbx+0C0h], ecx
0x180010a92  mov     word ptr [rbx+0C4h], 14h
0x180010a9b  mov     dword ptr [rbx+0C8h], 13h
0x180010aa5  mov     [rbx+0D0h], rdx
0x180010aac  mov     [rbx+0E0h], rsi
0x180010ab3  mov     [rbx+0E8h], ecx
0x180010ab9  mov     word ptr [rbx+0ECh], 28h ; '('
0x180010ac2  mov     dword ptr [rbx+0F0h], 12h
0x180010acc  mov     [rbx+0F8h], rdx
0x180010ad3  mov     [rbx+108h], rsi
0x180010ada  mov     [rbx+110h], ecx
0x180010ae0  mov     word ptr [rbx+114h], 3Ch ; '<'
0x180010ae9  mov     dword ptr [rbx+118h], 8
0x180010af3  mov     [rbx+120h], rdx
0x180010afa  mov     rcx, [rsp+138h+var_18]
0x180010b02  xor     rcx, rsp; StackCookie
0x180010b05  call    __security_check_cookie
0x180010b0a  lea     r11, [rsp+138h+var_8]
0x180010b12  mov     rbx, [r11+18h]
0x180010b16  mov     rsi, [r11+20h]
0x180010b1a  mov     rsp, r11
0x180010b1d  pop     rdi
0x180010b1e  retn
```
