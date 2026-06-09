# FwRule::get_ServiceName(ushort * *)

- ea: `0x180019090`
- end: `0x1800191ce`
- name: `?get_ServiceName@FwRule@@UEAAJPEAPEAG@Z`
- size: `318`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180019090`
- `0x18003336c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800190cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800190cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001915e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001915e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800191a8`
- `OLEAUT32!__imp_SysAllocString` at `0x180019124`
- `OLEAUT32!__imp_SysAllocString` at `0x180019124`
- `fwbase!FwReportErrorAsWinError` at `0x18001914c`
- `fwbase!FwReportErrorAsWinError` at `0x18001914c`
- `fwbase!FwReportReturnError` at `0x180019198`
- `fwbase!FwReportReturnError` at `0x1800191bd`
- `fwbase!FwReportReturnError` at `0x180019198`
- `fwbase!FwReportReturnError` at `0x1800191bd`

## string_xrefs

- `0x180019145`: `FwRule::get_ServiceName`
- `0x18001918f`: `FwRule::get_ServiceName`
- `0x1800191b6`: `FwRule::get_ServiceName`

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
0x180019090  mov     [rsp+arg_8], rbp
0x180019095  mov     [rsp+arg_10], rsi
0x18001909a  push    rdi
0x18001909b  sub     rsp, 20h
0x18001909f  mov     rsi, rdx
0x1800190a2  mov     rbp, rcx
0x1800190a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190ac  lea     rax, WPP_GLOBAL_Control
0x1800190b3  cmp     rcx, rax
0x1800190b6  jz      short loc_1800190C2
0x1800190b8  test    byte ptr [rcx+1Ch], 8
0x1800190bc  jnz     loc_180019170
0x1800190c2  lea     rcx, [rbp+10h]; lpCriticalSection
0x1800190c6  mov     [rsp+28h+arg_0], rbx
0x1800190cb  call    cs:__imp_EnterCriticalSection
0x1800190d2  nop     dword ptr [rax+rax+00h]
0x1800190d7  test    rsi, rsi
0x1800190da  jz      loc_18001918A
0x1800190e0  mov     rax, [rbp+50h]
0x1800190e4  xor     edx, edx
0x1800190e6  mov     ebx, edx
0x1800190e8  test    rax, rax
0x1800190eb  jz      short loc_1800190F9
0x1800190ed  mov     rcx, [rax+118h]; psz
0x1800190f4  test    rcx, rcx
0x1800190f7  jnz     short loc_180019124
0x1800190f9  mov     [rsi], rdx
0x1800190fc  lea     rcx, [rbp+10h]; lpCriticalSection
0x180019100  call    cs:__imp_LeaveCriticalSection
0x180019107  nop     dword ptr [rax+rax+00h]
0x18001910c  mov     eax, ebx
0x18001910e  mov     rbx, [rsp+28h+arg_0]
0x180019113  mov     rbp, [rsp+28h+arg_8]
0x180019118  mov     rsi, [rsp+28h+arg_10]
0x18001911d  add     rsp, 20h
0x180019121  pop     rdi
0x180019122  retn
0x180019124  call    cs:__imp_SysAllocString
0x18001912b  nop     dword ptr [rax+rax+00h]
0x180019130  mov     [rsi], rax
0x180019133  test    rax, rax
0x180019136  jnz     short loc_1800190FC
0x180019138  mov     r8d, 8
0x18001913e  lea     rdx, aSysallocstring; "SysAllocString"
0x180019145  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x18001914c  call    cs:__imp_FwReportErrorAsWinError
0x180019153  nop     dword ptr [rax+rax+00h]
0x180019158  mov     ebx, eax
0x18001915a  lea     rcx, [rbp+10h]; lpCriticalSection
0x18001915e  call    cs:__imp_LeaveCriticalSection
0x180019165  nop     dword ptr [rax+rax+00h]
0x18001916a  test    ebx, ebx
0x18001916c  jns     short loc_18001910C
0x18001916e  jmp     short loc_1800191B4
0x180019170  mov     rcx, [rcx+10h]
0x180019174  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18001917b  mov     edx, 13h
0x180019180  call    WPP_SF_
0x180019185  jmp     loc_1800190C2
0x18001918a  mov     ebx, 80004003h
0x18001918f  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x180019196  mov     edx, ebx
0x180019198  call    cs:__imp_FwReportReturnError
0x18001919f  nop     dword ptr [rax+rax+00h]
0x1800191a4  lea     rcx, [rbp+10h]; lpCriticalSection
0x1800191a8  call    cs:__imp_LeaveCriticalSection
0x1800191af  nop     dword ptr [rax+rax+00h]
0x1800191b4  mov     edx, ebx
0x1800191b6  lea     rcx, aFwruleGetServi; "FwRule::get_ServiceName"
0x1800191bd  call    cs:__imp_FwReportReturnError
0x1800191c4  nop     dword ptr [rax+rax+00h]
0x1800191c9  jmp     loc_18001910E
```
