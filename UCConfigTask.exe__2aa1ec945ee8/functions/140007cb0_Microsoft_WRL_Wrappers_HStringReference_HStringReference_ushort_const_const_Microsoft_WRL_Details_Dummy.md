# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x140007cb0`
- end: `0x140007d07`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `87`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007d10`
- `0x140007d90`
- `0x140007ef4`

## callees

- `0x140007cb0`
- `0x140007eac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007d00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007d00`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  unsigned __int64 v3; // r9
  const WCHAR *v4; // rdx

  a1[1].Reserved.Reserved1 = 0;
  v3 = -1;
  v4 = *a2;
  do
    ++v3;
  while ( v4[v3] );
  if ( v3 > 0xFFFFFFFF || (int)v3 + 1 < (unsigned int)v3 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x140007D06LL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(a1, v4, v3 + 1, v3);
  return a1;
}

```

## disassembly

```asm
0x140007cb0  push    rbx
0x140007cb2  sub     rsp, 20h
0x140007cb6  xor     eax, eax
0x140007cb8  mov     rbx, rcx
0x140007cbb  mov     [rcx+18h], rax
0x140007cbf  or      r9, 0FFFFFFFFFFFFFFFFh
0x140007cc3  mov     rdx, [rdx]; sourceString
0x140007cc6  inc     r9; unsigned int
0x140007cc9  cmp     [rdx+r9*2], ax
0x140007cce  jnz     short loc_140007CC6
0x140007cd0  mov     eax, 0FFFFFFFFh
0x140007cd5  cmp     r9, rax
0x140007cd8  ja      short loc_140007CF1
0x140007cda  lea     r8d, [r9+1]; unsigned int
0x140007cde  cmp     r8d, r9d
0x140007ce1  jb      short loc_140007CF1
0x140007ce3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140007ce8  mov     rax, rbx
0x140007ceb  add     rsp, 20h
0x140007cef  pop     rbx
0x140007cf0  retn
0x140007cf1  xor     r9d, r9d; lpArguments
0x140007cf4  xor     r8d, r8d; nNumberOfArguments
0x140007cf7  mov     ecx, 80070216h; dwExceptionCode
0x140007cfc  lea     edx, [r9+1]; dwExceptionFlags
0x140007d00  call    cs:__imp_RaiseException
```
