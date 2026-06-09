# FwService::get_Name(ushort * *)

- ea: `0x180046d40`
- end: `0x180046db8`
- name: `?get_Name@FwService@@UEAAJPEAPEAG@Z`
- size: `120`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180046d40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180046d6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180046d6e`
- `fwbase!FwReportErrorAsWinError` at `0x180046d8e`
- `fwbase!FwReportErrorAsWinError` at `0x180046d8e`
- `fwbase!FwReportReturnError` at `0x180046d60`
- `fwbase!FwReportReturnError` at `0x180046da3`
- `fwbase!FwReportReturnError` at `0x180046d60`
- `fwbase!FwReportReturnError` at `0x180046da3`

## string_xrefs

- `0x180046d57`: `FwService::get_Name`
- `0x180046d87`: `FwService::get_Name`
- `0x180046d9c`: `FwService::get_Name`

## pseudocode

```c
__int64 __fastcall FwService::get_Name(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rax

  if ( !a2 )
  {
    v3 = -2147467261;
    FwReportReturnError("FwService::get_Name", 2147500035LL);
    return (unsigned int)FwReportReturnError("FwService::get_Name", v3);
  }
  v3 = 0;
  v4 = SysAllocString(this[4]);
  *a2 = v4;
  if ( !v4 )
  {
    v3 = FwReportErrorAsWinError("FwService::get_Name", "SysAllocString", 8);
    if ( (v3 & 0x80000000) != 0 )
      return (unsigned int)FwReportReturnError("FwService::get_Name", v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180046d40  mov     [rsp+arg_0], rbx
0x180046d45  push    rdi
0x180046d46  sub     rsp, 20h
0x180046d4a  mov     rdi, rdx
0x180046d4d  test    rdx, rdx
0x180046d50  jnz     short loc_180046D68
0x180046d52  mov     ebx, 80004003h
0x180046d57  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x180046d5e  mov     edx, ebx
0x180046d60  call    cs:__imp_FwReportReturnError
0x180046d66  jmp     short loc_180046D9A
0x180046d68  mov     rcx, [rcx+20h]; psz
0x180046d6c  xor     ebx, ebx
0x180046d6e  call    cs:__imp_SysAllocString
0x180046d74  mov     [rdi], rax
0x180046d77  test    rax, rax
0x180046d7a  jnz     short loc_180046DAB
0x180046d7c  lea     r8d, [rbx+8]
0x180046d80  lea     rdx, aSysallocstring; "SysAllocString"
0x180046d87  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x180046d8e  call    cs:__imp_FwReportErrorAsWinError
0x180046d94  mov     ebx, eax
0x180046d96  test    eax, eax
0x180046d98  jns     short loc_180046DAB
0x180046d9a  mov     edx, ebx
0x180046d9c  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x180046da3  call    cs:__imp_FwReportReturnError
0x180046da9  mov     ebx, eax
0x180046dab  mov     eax, ebx
0x180046dad  mov     rbx, [rsp+28h+arg_0]
0x180046db2  add     rsp, 20h
0x180046db6  pop     rdi
0x180046db7  retn
```
