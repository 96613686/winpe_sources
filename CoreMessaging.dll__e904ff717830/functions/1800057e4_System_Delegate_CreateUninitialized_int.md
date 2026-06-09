# System::Delegate::CreateUninitialized(int)

- ea: `0x1800057e4`
- end: `0x180005848`
- name: `?CreateUninitialized@Delegate@System@@KAPEAXH@Z`
- size: `100`
- prototype: `void *__fastcall(int)`
- caller_count: `23`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005790`
- `0x18002fcf8`
- `0x180033124`
- `0x1800352c8`
- `0x18003bdf8`
- `0x180047d50`
- `0x180048278`
- `0x18004833c`
- `0x180048e68`
- `0x180049c44`
- `0x18004ebb4`
- `0x180052b9c`
- `0x18006d9a0`
- `0x180083b30`
- `0x180087344`
- `0x180088080`
- `0x18008dd58`
- `0x18008de1c`
- `0x180091130`
- `0x18009b9d4`
- `0x1800a76e8`
- `0x1800b12d4`
- `0x1800b5b30`

## callees

- `0x1800057e4`
- `0x18008ae1c`
- `0x1800a1f68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005822`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005822`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000580c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000580c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID __fastcall System::Delegate::CreateUninitialized(const char16_t *a1)
{
  __int64 v1; // rbx
  LPVOID Value; // rax
  LPVOID result; // rax

  if ( (int)a1 < 1 )
    CFlat::Abandonment::Fail(a1);
  v1 = 24LL * (int)a1 + 40;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  ++*((_DWORD *)Value + 16);
  result = HeapAlloc(*((HANDLE *)Value + 7), 8u, v1);
  if ( !result )
    Cn::Process::NotifyOutOfMemory(v1);
  return result;
}

```

## disassembly

```asm
0x1800057e4  push    rbx
0x1800057e6  sub     rsp, 20h
0x1800057ea  cmp     ecx, 1
0x1800057ed  jl      short loc_180005833
0x1800057ef  cmp     ecx, 7FFFFFFFh
0x1800057f5  ja      short loc_180005839
0x1800057f7  movsxd  rax, ecx
0x1800057fa  lea     rcx, [rax+rax*2]
0x1800057fe  lea     rbx, ds:28h[rcx*8]
0x180005806  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000580c  call    cs:__imp_TlsGetValue
0x180005812  nop
0x180005813  inc     dword ptr [rax+40h]
0x180005816  mov     r8, rbx; dwBytes
0x180005819  mov     edx, 8; dwFlags
0x18000581e  mov     rcx, [rax+38h]; hHeap
0x180005822  call    cs:__imp_HeapAlloc
0x180005828  test    rax, rax
0x18000582b  jz      short loc_18000583F
0x18000582d  add     rsp, 20h
0x180005831  pop     rbx
0x180005832  retn
0x180005833  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180005839  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000583f  mov     rcx, rbx; unsigned __int64
0x180005842  call    ?NotifyOutOfMemory@Process@Cn@@SAX_K@Z; Cn::Process::NotifyOutOfMemory(unsigned __int64)
```
