# SrpCreatePluginFileName

- ea: `0x140024494`
- end: `0x140024529`
- name: `SrpCreatePluginFileName`
- size: `149`
- prototype: `NTSTATUS __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140021c3c`
- `0x140036380`

## callees

- `0x140001e4c`
- `0x140006a20`
- `0x140006f40`
- `0x140024494`

## import_xrefs

- `ntoskrnl!RtlCreateUnicodeString` at `0x1400244f0`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400244f0`

## string_xrefs

- `0x1400244ce`: `\SystemRoot\System32\AppLocker\plugin.%I64i.Policy`

## pseudocode

```c
NTSTATUS __fastcall SrpCreatePluginFileName(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  wchar_t pszDest[264]; // [rsp+20h] [rbp-228h] BYREF

  memset(pszDest, 0, 0x208u);
  result = RtlStringCchPrintfW(pszDest, 0x104u, L"\\SystemRoot\\System32\\AppLocker\\plugin.%I64i.Policy", a1);
  if ( result >= 0 )
    return RtlCreateUnicodeString(a2, pszDest) == 0 ? 0xC0000017 : 0;
  return result;
}

```

## disassembly

```asm
0x140024494  mov     [rsp+arg_10], rbx
0x140024499  push    rdi
0x14002449a  sub     rsp, 240h
0x1400244a1  mov     rax, cs:__security_cookie
0x1400244a8  xor     rax, rsp
0x1400244ab  mov     [rsp+248h+var_18], rax
0x1400244b3  mov     rdi, rdx
0x1400244b6  mov     rbx, rcx
0x1400244b9  xor     edx, edx; Val
0x1400244bb  lea     rcx, [rsp+248h+pszDest]; void *
0x1400244c0  mov     r8d, 208h; Size
0x1400244c6  call    memset
0x1400244cb  mov     r9, rbx
0x1400244ce  lea     r8, aSystemrootSyst_7; "\\SystemRoot\\System32\\AppLocker\\plug"...
0x1400244d5  mov     edx, 104h; cchDest
0x1400244da  lea     rcx, [rsp+248h+pszDest]; pszDest
0x1400244df  call    RtlStringCchPrintfW
0x1400244e4  test    eax, eax
0x1400244e6  js      short loc_140024507
0x1400244e8  lea     rdx, [rsp+248h+pszDest]; SourceString
0x1400244ed  mov     rcx, rdi; DestinationString
0x1400244f0  call    cs:__imp_RtlCreateUnicodeString
0x1400244f7  nop     dword ptr [rax+rax+00h]
0x1400244fc  neg     al
0x1400244fe  sbb     eax, eax
0x140024500  not     eax
0x140024502  and     eax, 0C0000017h
0x140024507  mov     rcx, [rsp+248h+var_18]
0x14002450f  xor     rcx, rsp; StackCookie
0x140024512  call    __security_check_cookie
0x140024517  mov     rbx, [rsp+248h+arg_10]
0x14002451f  add     rsp, 240h
0x140024526  pop     rdi
0x140024527  retn
```
