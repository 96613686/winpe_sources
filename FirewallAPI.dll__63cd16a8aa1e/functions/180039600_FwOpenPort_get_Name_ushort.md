# FwOpenPort::get_Name(ushort * *)

- ea: `0x180039600`
- end: `0x1800396c0`
- name: `?get_Name@FwOpenPort@@UEAAJPEAPEAG@Z`
- size: `192`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003969a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003969a`
- `OLEAUT32!__imp_SysAllocString` at `0x180039665`
- `OLEAUT32!__imp_SysAllocString` at `0x180039665`
- `fwbase!FwReportErrorAsWinError` at `0x180039685`
- `fwbase!FwReportErrorAsWinError` at `0x180039685`
- `fwbase!FwResolveIndirectString` at `0x180039648`
- `fwbase!FwResolveIndirectString` at `0x180039648`
- `fwbase!FwReportReturnError` at `0x18003962c`
- `fwbase!FwReportReturnError` at `0x1800396ad`
- `fwbase!FwReportReturnError` at `0x18003962c`
- `fwbase!FwReportReturnError` at `0x1800396ad`

## string_xrefs

- `0x180039625`: `FwOpenPort::get_Name`
- `0x18003967e`: `FwOpenPort::get_Name`
- `0x1800396a6`: `FwOpenPort::get_Name`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Name(FwOpenPort *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  const OLECHAR *v8; // rcx
  unsigned __int16 *v9; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPort::get_Name", v5);
    goto LABEL_12;
  }
  v6 = *((_QWORD *)this + 9);
  if ( v6 )
  {
    v7 = FwResolveIndirectString(v6 + 24);
    v4 = v7;
    if ( v7 < 0 )
    {
      v5 = (unsigned int)v7;
      goto LABEL_3;
    }
    v8 = *(const OLECHAR **)(*((_QWORD *)this + 9) + 24LL);
    if ( v8 )
    {
      v9 = SysAllocString(v8);
      *a2 = v9;
      if ( !v9 )
        v4 = FwReportErrorAsWinError("FwOpenPort::get_Name", "SysAllocString", 8);
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    v4 = 0;
    *a2 = 0;
  }
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Name", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039600  push    rbx
0x180039602  push    rbp
0x180039603  push    rsi
0x180039604  push    rdi
0x180039605  sub     rsp, 28h
0x180039609  mov     rsi, rcx
0x18003960c  mov     rdi, rdx
0x18003960f  add     rcx, 10h; lpCriticalSection
0x180039613  call    cs:__imp_EnterCriticalSection
0x180039619  test    rdi, rdi
0x18003961c  jnz     short loc_180039634
0x18003961e  mov     ebx, 80004003h
0x180039623  mov     edx, ebx
0x180039625  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x18003962c  call    cs:__imp_FwReportReturnError
0x180039632  jmp     short loc_180039696
0x180039634  mov     rcx, [rsi+48h]
0x180039638  test    rcx, rcx
0x18003963b  jnz     short loc_180039644
0x18003963d  xor     ebx, ebx
0x18003963f  mov     [rdi], rbx
0x180039642  jmp     short loc_180039696
0x180039644  add     rcx, 18h
0x180039648  call    cs:__imp_FwResolveIndirectString
0x18003964e  mov     ebx, eax
0x180039650  test    eax, eax
0x180039652  jns     short loc_180039658
0x180039654  mov     edx, eax
0x180039656  jmp     short loc_180039625
0x180039658  mov     rax, [rsi+48h]
0x18003965c  mov     rcx, [rax+18h]; psz
0x180039660  test    rcx, rcx
0x180039663  jz      short loc_18003968F
0x180039665  call    cs:__imp_SysAllocString
0x18003966b  mov     [rdi], rax
0x18003966e  test    rax, rax
0x180039671  jnz     short loc_180039696
0x180039673  lea     r8d, [rax+8]
0x180039677  lea     rdx, aSysallocstring; "SysAllocString"
0x18003967e  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x180039685  call    cs:__imp_FwReportErrorAsWinError
0x18003968b  mov     ebx, eax
0x18003968d  jmp     short loc_180039696
0x18003968f  mov     qword ptr [rdi], 0
0x180039696  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003969a  call    cs:__imp_LeaveCriticalSection
0x1800396a0  test    ebx, ebx
0x1800396a2  jns     short loc_1800396B5
0x1800396a4  mov     edx, ebx
0x1800396a6  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x1800396ad  call    cs:__imp_FwReportReturnError
0x1800396b3  mov     ebx, eax
0x1800396b5  mov     eax, ebx
0x1800396b7  add     rsp, 28h
0x1800396bb  pop     rdi
0x1800396bc  pop     rsi
0x1800396bd  pop     rbp
0x1800396be  pop     rbx
0x1800396bf  retn
```
