# GetLastFailureAsHRESULT

- ea: `0x140006cc8`
- end: `0x140006d50`
- name: `GetLastFailureAsHRESULT`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001dec`
- `0x140003320`
- `0x140005eb0`
- `0x140006018`
- `0x140006334`
- `0x1400066e0`
- `0x1400068d4`
- `0x140007030`
- `0x1400075cc`
- `0x14000771c`
- `0x14000e674`
- `0x14000ef3c`

## callees

- `0x140006cc8`
- `0x140006d58`
- `0x140006de0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006cd7`
- `KERNEL32!GetLastError` at `0x140006cd7`
- `ntdll!RtlGetLastNtStatus` at `0x140006cdf`
- `ntdll!RtlGetLastNtStatus` at `0x140006cdf`

## pseudocode

```c
__int64 GetLastFailureAsHRESULT()
{
  signed int LastError; // edi
  unsigned int LastNtStatus; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned int v4; // esi
  signed int v5; // ebx

  LastError = GetLastError();
  LastNtStatus = RtlGetLastNtStatus();
  v4 = LastNtStatus;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  else
    v5 = LastError;
  if ( v5 >= 0 )
  {
    v5 = HRESULTFromNTSTATUS(LastNtStatus);
    if ( v5 >= 0 )
      v5 = -1073729531;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, (unsigned int)LastError, v4, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006cc8  mov     [rsp+arg_0], rbx
0x140006ccd  mov     [rsp+arg_8], rsi
0x140006cd2  push    rdi
0x140006cd3  sub     rsp, 30h
0x140006cd7  call    cs:__imp_GetLastError
0x140006cdd  mov     edi, eax
0x140006cdf  call    cs:__imp_RtlGetLastNtStatus
0x140006ce5  mov     esi, eax
0x140006ce7  test    edi, edi
0x140006ce9  jg      short loc_140006CEF
0x140006ceb  mov     ebx, edi
0x140006ced  jmp     short loc_140006CF8
0x140006cef  movzx   ebx, di
0x140006cf2  or      ebx, 80070000h
0x140006cf8  test    ebx, ebx
0x140006cfa  js      short loc_140006D0E
0x140006cfc  mov     ecx, esi
0x140006cfe  call    HRESULTFromNTSTATUS
0x140006d03  mov     ebx, eax
0x140006d05  test    eax, eax
0x140006d07  js      short loc_140006D0E
0x140006d09  mov     ebx, 0C0003005h
0x140006d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d15  lea     rax, WPP_GLOBAL_Control
0x140006d1c  cmp     rcx, rax
0x140006d1f  jz      short loc_140006D3E
0x140006d21  test    dword ptr [rcx+1Ch], 1000000h
0x140006d28  jz      short loc_140006D3E
0x140006d2a  mov     rcx, [rcx+10h]
0x140006d2e  mov     r9d, edi
0x140006d31  mov     [rsp+38h+var_10], ebx
0x140006d35  mov     [rsp+38h+var_18], esi
0x140006d39  call    WPP_SF_Ddd
0x140006d3e  mov     rsi, [rsp+38h+arg_8]
0x140006d43  mov     eax, ebx
0x140006d45  mov     rbx, [rsp+38h+arg_0]
0x140006d4a  add     rsp, 30h
0x140006d4e  pop     rdi
0x140006d4f  retn
```
