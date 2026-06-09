# FwOpenPort::get_Name(ushort * *)

- ea: `0x18003c150`
- end: `0x18003c23b`
- name: `?get_Name@FwOpenPort@@UEAAJPEAPEAG@Z`
- size: `235`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003c150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c163`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c208`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c208`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c1c7`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c1c7`
- `fwbase!FwReportErrorAsWinError` at `0x18003c1ed`
- `fwbase!FwReportErrorAsWinError` at `0x18003c1ed`
- `fwbase!FwResolveIndirectString` at `0x18003c1a4`
- `fwbase!FwResolveIndirectString` at `0x18003c1a4`
- `fwbase!FwReportReturnError` at `0x18003c182`
- `fwbase!FwReportReturnError` at `0x18003c221`
- `fwbase!FwReportReturnError` at `0x18003c182`
- `fwbase!FwReportReturnError` at `0x18003c221`

## string_xrefs

- `0x18003c17b`: `FwOpenPort::get_Name`
- `0x18003c1e6`: `FwOpenPort::get_Name`
- `0x18003c21a`: `FwOpenPort::get_Name`

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
0x18003c150  push    rbx
0x18003c152  push    rbp
0x18003c153  push    rsi
0x18003c154  push    rdi
0x18003c155  sub     rsp, 28h
0x18003c159  mov     rsi, rcx
0x18003c15c  mov     rdi, rdx
0x18003c15f  add     rcx, 10h; lpCriticalSection
0x18003c163  call    cs:__imp_EnterCriticalSection
0x18003c16a  nop     dword ptr [rax+rax+00h]
0x18003c16f  test    rdi, rdi
0x18003c172  jnz     short loc_18003C190
0x18003c174  mov     ebx, 80004003h
0x18003c179  mov     edx, ebx
0x18003c17b  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x18003c182  call    cs:__imp_FwReportReturnError
0x18003c189  nop     dword ptr [rax+rax+00h]
0x18003c18e  jmp     short loc_18003C204
0x18003c190  mov     rcx, [rsi+48h]
0x18003c194  test    rcx, rcx
0x18003c197  jnz     short loc_18003C1A0
0x18003c199  xor     ebx, ebx
0x18003c19b  mov     [rdi], rbx
0x18003c19e  jmp     short loc_18003C204
0x18003c1a0  add     rcx, 18h
0x18003c1a4  call    cs:__imp_FwResolveIndirectString
0x18003c1ab  nop     dword ptr [rax+rax+00h]
0x18003c1b0  mov     ebx, eax
0x18003c1b2  test    eax, eax
0x18003c1b4  jns     short loc_18003C1BA
0x18003c1b6  mov     edx, eax
0x18003c1b8  jmp     short loc_18003C17B
0x18003c1ba  mov     rax, [rsi+48h]
0x18003c1be  mov     rcx, [rax+18h]; psz
0x18003c1c2  test    rcx, rcx
0x18003c1c5  jz      short loc_18003C1FD
0x18003c1c7  call    cs:__imp_SysAllocString
0x18003c1ce  nop     dword ptr [rax+rax+00h]
0x18003c1d3  mov     [rdi], rax
0x18003c1d6  test    rax, rax
0x18003c1d9  jnz     short loc_18003C204
0x18003c1db  lea     r8d, [rax+8]
0x18003c1df  lea     rdx, aSysallocstring; "SysAllocString"
0x18003c1e6  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x18003c1ed  call    cs:__imp_FwReportErrorAsWinError
0x18003c1f4  nop     dword ptr [rax+rax+00h]
0x18003c1f9  mov     ebx, eax
0x18003c1fb  jmp     short loc_18003C204
0x18003c1fd  mov     qword ptr [rdi], 0
0x18003c204  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003c208  call    cs:__imp_LeaveCriticalSection
0x18003c20f  nop     dword ptr [rax+rax+00h]
0x18003c214  test    ebx, ebx
0x18003c216  jns     short loc_18003C22F
0x18003c218  mov     edx, ebx
0x18003c21a  lea     rcx, aFwopenportGetN; "FwOpenPort::get_Name"
0x18003c221  call    cs:__imp_FwReportReturnError
0x18003c228  nop     dword ptr [rax+rax+00h]
0x18003c22d  mov     ebx, eax
0x18003c22f  mov     eax, ebx
0x18003c231  add     rsp, 28h
0x18003c235  pop     rdi
0x18003c236  pop     rsi
0x18003c237  pop     rbp
0x18003c238  pop     rbx
0x18003c239  retn
```
