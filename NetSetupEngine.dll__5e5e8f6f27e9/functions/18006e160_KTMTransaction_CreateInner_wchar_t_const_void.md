# KTMTransaction::CreateInner(wchar_t const *,void * *)

- ea: `0x18006e160`
- end: `0x18006e1db`
- name: `?CreateInner@KTMTransaction@@CAJPEB_WPEAPEAX@Z`
- size: `123`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006e200`
- `0x18006e3a0`

## callees

- `0x1800810d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006e188`
- `ntdll!RtlInitUnicodeString` at `0x18006e188`
- `ntdll!NtCreateTransaction` at `0x18006e1c2`
- `ntdll!NtCreateTransaction` at `0x18006e1c2`

## pseudocode

```c
__int64 __fastcall KTMTransaction::CreateInner(PCWSTR SourceString, void **a2)
{
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  return NtCreateTransaction(a2, 2031679, 0, 0, 0, 1, 0, 0, 0, &DestinationString);
}

```

## disassembly

```asm
0x18006e160  push    rbx
0x18006e162  sub     rsp, 70h
0x18006e166  mov     rax, cs:__security_cookie
0x18006e16d  xor     rax, rsp
0x18006e170  mov     [rsp+78h+var_18], rax
0x18006e175  mov     rbx, rdx
0x18006e178  xorps   xmm0, xmm0
0x18006e17b  mov     rdx, rcx; SourceString
0x18006e17e  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18006e183  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18006e188  call    cs:__imp_RtlInitUnicodeString
0x18006e18e  lea     rax, [rsp+78h+DestinationString]
0x18006e193  xor     r9d, r9d
0x18006e196  mov     [rsp+78h+var_30], rax
0x18006e19b  xor     r8d, r8d
0x18006e19e  xor     eax, eax
0x18006e1a0  mov     edx, 1F003Fh
0x18006e1a5  mov     [rsp+78h+var_38], rax
0x18006e1aa  mov     rcx, rbx
0x18006e1ad  mov     [rsp+78h+var_40], eax
0x18006e1b1  mov     [rsp+78h+var_48], eax
0x18006e1b5  mov     [rsp+78h+var_50], 1
0x18006e1bd  mov     [rsp+78h+var_58], rax
0x18006e1c2  call    cs:__imp_NtCreateTransaction
0x18006e1c8  mov     rcx, [rsp+78h+var_18]
0x18006e1cd  xor     rcx, rsp; StackCookie
0x18006e1d0  call    __security_check_cookie
0x18006e1d5  add     rsp, 70h
0x18006e1d9  pop     rbx
0x18006e1da  retn
```
