# FwRule::get_ServiceName(ushort * *)

- ea: `0x180019d50`
- end: `0x180019e5d`
- name: `?get_ServiceName@FwRule@@UEAAJPEAPEAG@Z`
- size: `269`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180019d50`
- `0x18003104c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019d8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e43`
- `OLEAUT32!__imp_SysAllocString` at `0x180019dd7`
- `OLEAUT32!__imp_SysAllocString` at `0x180019dd7`
- `fwbase!FwReportErrorAsWinError` at `0x180019df9`
- `fwbase!FwReportErrorAsWinError` at `0x180019df9`
- `fwbase!FwReportReturnError` at `0x180019e39`
- `fwbase!FwReportReturnError` at `0x180019e52`
- `fwbase!FwReportReturnError` at `0x180019e39`
- `fwbase!FwReportReturnError` at `0x180019e52`

## string_xrefs

- `0x180019df2`: `FwRule::get_ServiceName`
- `0x180019e30`: `FwRule::get_ServiceName`
- `0x180019e4b`: `FwRule::get_ServiceName`

## pseudocode

```c
__int64 __fastcall FwRule::get_ServiceName(FwRule *this, unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const OLECHAR *v6; // rcx
  unsigned __int16 *v8; // rax

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    v4 = *((_QWORD *)this + 10);
    v5 = 0;
    if ( !v4 || (v6 = *(const OLECHAR **)(v4 + 280)) == 0 )
    {
      *a2 = 0;
LABEL_8:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      return v5;
    }
    v8 = SysAllocString(v6);
    *a2 = v8;
    if ( v8 )
      goto LABEL_8;
    v5 = FwReportErrorAsWinError("FwRule::get_ServiceName", "SysAllocString", 8);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( (v5 & 0x80000000) == 0 )
      return v5;
  }
  else
  {
    v5 = -2147467261;
    FwReportReturnError("FwRule::get_ServiceName", 2147500035LL);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  return FwReportReturnError("FwRule::get_ServiceName", v5);
}

```

## disassembly

```asm
0x180019d50  mov     [rsp+arg_8], rbp
0x180019d55  mov     [rsp+arg_10], rsi
0x180019d5a  push    rdi
0x180019d5b  sub     rsp, 20h
0x180019d5f  mov     rsi, rdx
0x180019d62  mov     rbp, rcx
0x180019d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d6c  lea     rax, WPP_GLOBAL_Control
0x180019d73  cmp     rcx, rax
0x180019d76  jz      short loc_180019D82
0x180019d78  test    byte ptr [rcx+1Ch], 8
0x180019d7c  jnz     loc_180019E11
0x180019d82  lea     rcx, [rbp+10h]; lpCriticalSection
0x180019d86  mov     [rsp+28h+arg_0], rbx
0x180019d8b  call    cs:__imp_EnterCriticalSection
0x180019d91  test    rsi, rsi
0x180019d94  jz      loc_180019E2B
0x180019d9a  mov     rax, [rbp+50h]
0x180019d9e  xor     edx, edx
0x180019da0  mov     ebx, edx
0x180019da2  test    rax, rax
0x180019da5  jz      short loc_180019DB3
0x180019da7  mov     rcx, [rax+118h]; psz
0x180019dae  test    rcx, rcx
0x180019db1  jnz     short loc_180019DD7
0x180019db3  mov     [rsi], rdx
0x180019db6  lea     rcx, [rbp+10h]; lpCriticalSection
0x180019dba  call    cs:__imp_LeaveCriticalSection
0x180019dc0  mov     eax, ebx
0x180019dc2  mov     rbx, [rsp+28h+arg_0]
0x180019dc7  mov     rbp, [rsp+28h+arg_8]
0x180019dcc  mov     rsi, [rsp+28h+arg_10]
0x180019dd1  add     rsp, 20h
0x180019dd5  pop     rdi
0x180019dd6  retn
0x180019dd7  call    cs:__imp_SysAllocString
0x180019ddd  mov     [rsi], rax
0x180019de0  test    rax, rax
0x180019de3  jnz     short loc_180019DB6
0x180019de5  mov     r8d, 8
0x180019deb  lea     rdx, aSysallocstring; "SysAllocString"
0x180019df2  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x180019df9  call    cs:__imp_FwReportErrorAsWinError
0x180019dff  mov     ebx, eax
0x180019e01  lea     rcx, [rbp+10h]; lpCriticalSection
0x180019e05  call    cs:__imp_LeaveCriticalSection
0x180019e0b  test    ebx, ebx
0x180019e0d  jns     short loc_180019DC0
0x180019e0f  jmp     short loc_180019E49
0x180019e11  mov     rcx, [rcx+10h]
0x180019e15  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180019e1c  mov     edx, 13h
0x180019e21  call    WPP_SF_
0x180019e26  jmp     loc_180019D82
0x180019e2b  mov     ebx, 80004003h
0x180019e30  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x180019e37  mov     edx, ebx
0x180019e39  call    cs:__imp_FwReportReturnError
0x180019e3f  lea     rcx, [rbp+10h]; lpCriticalSection
0x180019e43  call    cs:__imp_LeaveCriticalSection
0x180019e49  mov     edx, ebx
0x180019e4b  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x180019e52  call    cs:__imp_FwReportReturnError
0x180019e58  jmp     loc_180019DC2
```
