# NPDoStringParametersMatch(ushort const *,ushort const *,bool)

- ea: `0x140002590`
- end: `0x140002612`
- name: `?NPDoStringParametersMatch@@YA_NPEBG0_N@Z`
- size: `130`
- prototype: `bool __fastcall(PCWSTR SourceString, PCWSTR, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001580`
- `0x1400016a0`
- `0x140002138`
- `0x14000225c`
- `0x14000664c`

## callees

- `0x1400024e8`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400025bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400025db`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400025bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400025db`

## pseudocode

```c
bool __fastcall NPDoStringParametersMatch(PCWSTR SourceString, PCWSTR a2, char a3)
{
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = 0;
  RtlInitUnicodeString(&v6, a2);
  return NPCompareUnicodeString(&DestinationString, &v6, a3);
}

```

## disassembly

```asm
0x140002590  mov     [rsp+arg_10], rbx
0x140002595  push    rdi
0x140002596  sub     rsp, 50h
0x14000259a  mov     rax, cs:__security_cookie
0x1400025a1  xor     rax, rsp
0x1400025a4  mov     [rsp+58h+var_18], rax
0x1400025a9  mov     rbx, rdx
0x1400025ac  xorps   xmm0, xmm0
0x1400025af  mov     rdx, rcx; SourceString
0x1400025b2  mov     dil, r8b
0x1400025b5  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400025ba  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1400025bf  call    cs:__imp_RtlInitUnicodeString
0x1400025c6  nop     dword ptr [rax+rax+00h]
0x1400025cb  xorps   xmm0, xmm0
0x1400025ce  lea     rcx, [rsp+58h+var_38]; DestinationString
0x1400025d3  mov     rdx, rbx; SourceString
0x1400025d6  movups  xmmword ptr [rsp+58h+var_38.Length], xmm0
0x1400025db  call    cs:__imp_RtlInitUnicodeString
0x1400025e2  nop     dword ptr [rax+rax+00h]
0x1400025e7  mov     r8b, dil; bool
0x1400025ea  lea     rdx, [rsp+58h+var_38]; struct _UNICODE_STRING *
0x1400025ef  lea     rcx, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x1400025f4  call    ?NPCompareUnicodeString@@YA_NAEBU_UNICODE_STRING@@0_N@Z; NPCompareUnicodeString(_UNICODE_STRING const &,_UNICODE_STRING const &,bool)
0x1400025f9  mov     rcx, [rsp+58h+var_18]
0x1400025fe  xor     rcx, rsp; StackCookie
0x140002601  call    __security_check_cookie
0x140002606  mov     rbx, [rsp+58h+arg_10]
0x14000260b  add     rsp, 50h
0x14000260f  pop     rdi
0x140002610  retn
```
