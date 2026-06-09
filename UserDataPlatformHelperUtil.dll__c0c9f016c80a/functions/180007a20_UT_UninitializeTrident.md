# UT_UninitializeTrident

- ea: `0x180007a20`
- end: `0x180007a97`
- name: `UT_UninitializeTrident`
- size: `119`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007818`
- `0x180007a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007a6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007a6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007a48`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007a48`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007a83`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007a83`

## pseudocode

```c
void UT_UninitializeTrident()
{
  TridentHtmlManager *v0; // rbx
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  TridentHtmlManager *v2; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  InitOnceBeginInitialize(&g_trident, 0, &v1, (LPVOID *)&v2);
  v0 = v2;
  if ( !v2 )
  {
    byte_180011A50 = 0;
    InitializeCriticalSectionEx(&stru_180011A58, 0, 0);
    v0 = (TridentHtmlManager *)&byte_180011A50;
    InitOnceComplete(&g_trident, 0, &byte_180011A50);
  }
  TridentHtmlManager::Uninitialize(v0);
}

```

## disassembly

```asm
0x180007a20  mov     rax, rsp
0x180007a23  push    rbx
0x180007a24  sub     rsp, 20h
0x180007a28  lea     r9, [rax+10h]; lpContext
0x180007a2c  mov     dword ptr [rax+8], 0
0x180007a33  lea     r8, [rax+8]; fPending
0x180007a37  mov     qword ptr [rax+10h], 0
0x180007a3f  xor     edx, edx; dwFlags
0x180007a41  lea     rcx, ?g_trident@@3V?$static_lazy@VTridentHtmlManager@@$0A@V?$lazy_construct@VTridentHtmlManager@@@tlx@@@tlx@@A; lpInitOnce
0x180007a48  call    cs:__imp_InitOnceBeginInitialize
0x180007a4e  mov     rbx, [rsp+28h+arg_8]
0x180007a53  test    rbx, rbx
0x180007a56  jnz     short loc_180007A89
0x180007a58  xor     r8d, r8d; Flags
0x180007a5b  mov     cs:byte_180011A50, bl
0x180007a61  xor     edx, edx; dwSpinCount
0x180007a63  lea     rcx, stru_180011A58; lpCriticalSection
0x180007a6a  call    cs:__imp_InitializeCriticalSectionEx
0x180007a70  lea     rbx, byte_180011A50
0x180007a77  xor     edx, edx; dwFlags
0x180007a79  mov     r8, rbx; lpContext
0x180007a7c  lea     rcx, ?g_trident@@3V?$static_lazy@VTridentHtmlManager@@$0A@V?$lazy_construct@VTridentHtmlManager@@@tlx@@@tlx@@A; lpInitOnce
0x180007a83  call    cs:__imp_InitOnceComplete
0x180007a89  mov     rcx, rbx; this
0x180007a8c  call    ?Uninitialize@TridentHtmlManager@@QEAAXXZ; TridentHtmlManager::Uninitialize(void)
0x180007a91  add     rsp, 20h
0x180007a95  pop     rbx
0x180007a96  retn
```
