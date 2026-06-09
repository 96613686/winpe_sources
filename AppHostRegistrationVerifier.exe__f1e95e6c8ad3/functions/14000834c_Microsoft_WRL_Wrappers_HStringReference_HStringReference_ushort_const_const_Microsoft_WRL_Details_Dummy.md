# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x14000834c`
- end: `0x1400083a3`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `87`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400083ac`
- `0x140008450`
- `0x1400084f4`
- `0x140008594`
- `0x140008634`
- `0x1400086d4`
- `0x140008774`
- `0x14000bc30`
- `0x14000bef8`
- `0x14000c848`
- `0x14000eb7c`
- `0x14000f3b8`

## callees

- `0x14000834c`
- `0x14000ac20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000839c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000839c`

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
    JUMPOUT(0x1400083A2LL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(a1, v4, v3 + 1, v3);
  return a1;
}

```

## disassembly

```asm
0x14000834c  push    rbx
0x14000834e  sub     rsp, 20h
0x140008352  xor     eax, eax
0x140008354  mov     rbx, rcx
0x140008357  mov     [rcx+18h], rax
0x14000835b  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000835f  mov     rdx, [rdx]; sourceString
0x140008362  inc     r9; unsigned int
0x140008365  cmp     [rdx+r9*2], ax
0x14000836a  jnz     short loc_140008362
0x14000836c  mov     eax, 0FFFFFFFFh
0x140008371  cmp     r9, rax
0x140008374  ja      short loc_14000838D
0x140008376  lea     r8d, [r9+1]; unsigned int
0x14000837a  cmp     r8d, r9d
0x14000837d  jb      short loc_14000838D
0x14000837f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140008384  mov     rax, rbx
0x140008387  add     rsp, 20h
0x14000838b  pop     rbx
0x14000838c  retn
0x14000838d  xor     r9d, r9d; lpArguments
0x140008390  xor     r8d, r8d; nNumberOfArguments
0x140008393  mov     ecx, 80070216h; dwExceptionCode
0x140008398  lea     edx, [r9+1]; dwExceptionFlags
0x14000839c  call    cs:__imp_RaiseException
```
