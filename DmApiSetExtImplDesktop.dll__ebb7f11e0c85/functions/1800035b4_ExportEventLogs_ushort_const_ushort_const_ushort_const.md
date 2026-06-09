# ExportEventLogs(ushort const *,ushort const *,ushort const *)

- ea: `0x1800035b4`
- end: `0x180003678`
- name: `?ExportEventLogs@@YAJPEBG00@Z`
- size: `196`
- prototype: `signed int __fastcall(const unsigned __int16 *, LPCWSTR Path, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800071d0`

## callees

- `0x1800035b4`
- `0x180004e04`
- `0x1800053c8`
- `0x180009f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000363a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000363a`
- `wevtapi!EvtExportLog` at `0x18000362a`
- `wevtapi!EvtExportLog` at `0x18000362a`

## string_xrefs

- `0x1800035f9`: `admin\dm\dmapisetextimpl\desktopdll\dmapisetextimplcsp.cpp`

## pseudocode

```c
signed int __fastcall ExportEventLogs(const unsigned __int16 *a1, LPCWSTR Path, const unsigned __int16 *a3)
{
  int v4; // eax
  int v5; // ebx
  signed int result; // eax
  DWORD Flags; // [rsp+20h] [rbp-238h]
  WCHAR TargetFilePath[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v4 = StringCchPrintfW(TargetFilePath, 0x104u, a1, a3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( EvtExportLog(0, Path, L"*", TargetFilePath, 0x2001u) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"admin\\dm\\dmapisetextimpl\\desktopdll\\dmapisetextimplcsp.cpp",
      (const char *)(unsigned int)v4,
      Flags);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800035b4  mov     [rsp+arg_18], rbx
0x1800035b9  push    rdi
0x1800035ba  sub     rsp, 250h
0x1800035c1  mov     rax, cs:__security_cookie
0x1800035c8  xor     rax, rsp
0x1800035cb  mov     [rsp+258h+var_18], rax
0x1800035d3  mov     r9, r8
0x1800035d6  mov     rdi, rdx
0x1800035d9  mov     r8, rcx; unsigned __int16 *
0x1800035dc  mov     edx, 104h; unsigned __int64
0x1800035e1  lea     rcx, [rsp+258h+TargetFilePath]; unsigned __int16 *
0x1800035e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800035eb  mov     ebx, eax
0x1800035ed  test    eax, eax
0x1800035ef  jns     short loc_180003611
0x1800035f1  mov     rcx, [rsp+258h]; this
0x1800035f9  lea     r8, aAdminDmDmapise; "admin\\dm\\dmapisetextimpl\\desktopdll"...
0x180003600  mov     r9d, eax; char *
0x180003603  mov     edx, 0B4h; void *
0x180003608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000360d  mov     eax, ebx
0x18000360f  jmp     short loc_180003656
0x180003611  lea     r9, [rsp+258h+TargetFilePath]; TargetFilePath
0x180003616  mov     [rsp+258h+Flags], 2001h; Flags
0x18000361e  lea     r8, Query; "*"
0x180003625  mov     rdx, rdi; Path
0x180003628  xor     ecx, ecx; Session
0x18000362a  call    cs:__imp_EvtExportLog
0x180003631  nop     dword ptr [rax+rax+00h]
0x180003636  test    eax, eax
0x180003638  jnz     short loc_180003654
0x18000363a  call    cs:__imp_GetLastError
0x180003641  nop     dword ptr [rax+rax+00h]
0x180003646  test    eax, eax
0x180003648  jle     short loc_180003656
0x18000364a  movzx   eax, ax
0x18000364d  or      eax, 80070000h
0x180003652  jmp     short loc_180003656
0x180003654  xor     eax, eax
0x180003656  mov     rcx, [rsp+258h+var_18]
0x18000365e  xor     rcx, rsp; StackCookie
0x180003661  call    __security_check_cookie
0x180003666  mov     rbx, [rsp+258h+arg_18]
0x18000366e  add     rsp, 250h
0x180003675  pop     rdi
0x180003676  retn
```
