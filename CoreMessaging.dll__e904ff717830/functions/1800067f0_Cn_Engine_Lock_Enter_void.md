# Cn::Engine::Lock::Enter(void)

- ea: `0x1800067f0`
- end: `0x18000682f`
- name: `?Enter@Lock@Engine@Cn@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(Cn::Engine::Lock *__hidden this)`
- caller_count: `160`
- callee_count: `1`
- tags: ``

## callers

- `0x180006054`
- `0x180006880`
- `0x180008354`
- `0x180014140`
- `0x18001d848`
- `0x180022c58`
- `0x1800235f8`
- `0x180024448`
- `0x1800244b0`
- `0x180024778`
- `0x180024928`
- `0x18003afa0`
- `0x180048470`
- `0x1800486f0`
- `0x180048810`
- `0x180048930`
- `0x180049e7c`
- `0x18004a850`
- `0x18004ac98`
- `0x18004b320`
- `0x18004bc84`
- `0x18004c11c`
- `0x18004ec18`
- `0x18004f538`
- `0x18005c190`
- `0x18007c630`
- `0x18007cd90`
- `0x180081c94`
- `0x180085348`
- `0x18008b904`
- `0x18008ccd0`
- `0x180090410`
- `0x180090a8c`
- `0x180090ddc`
- `0x180090e98`
- `0x180091270`
- `0x18009169c`
- `0x180091764`
- `0x180091a84`
- `0x180091b8c`
- `0x180091c98`
- `0x180091d4c`
- `0x180091e90`
- `0x1800925a8`
- `0x180092928`
- `0x180092a8c`
- `0x180092c8c`
- `0x180092e38`
- `0x180092fb0`
- `0x180093118`

## callees

- `0x1800067f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006820`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006816`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006816`

## pseudocode

```c
void __fastcall Cn::Engine::Lock::Enter(Cn::Engine::Lock *this)
{
  int v2; // ecx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = *((_DWORD *)this + 15);
  *((_DWORD *)this + 15) = v2 + 1;
  if ( !v2 )
  {
    *((_QWORD *)this + 8) = TlsGetValue(Cn::Context::s_tlsStorage);
    *((_DWORD *)this + 18) = GetCurrentThreadId();
  }
}

```

## disassembly

```asm
0x1800067f0  push    rbx
0x1800067f2  sub     rsp, 20h
0x1800067f6  mov     rbx, rcx
0x1800067f9  add     rcx, 10h; lpCriticalSection
0x1800067fd  call    cs:__imp_EnterCriticalSection
0x180006803  mov     ecx, [rbx+3Ch]
0x180006806  lea     eax, [rcx+1]
0x180006809  mov     [rbx+3Ch], eax
0x18000680c  test    ecx, ecx
0x18000680e  jnz     short loc_180006829
0x180006810  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180006816  call    cs:__imp_TlsGetValue
0x18000681c  mov     [rbx+40h], rax
0x180006820  call    cs:__imp_GetCurrentThreadId
0x180006826  mov     [rbx+48h], eax
0x180006829  add     rsp, 20h
0x18000682d  pop     rbx
0x18000682e  retn
```
