# tlx::static_lazy<TridentHtmlManager,0,tlx::lazy_construct<TridentHtmlManager>>::~static_lazy<TridentHtmlManager,0,tlx::lazy_construct<TridentHtmlManager>>(void)

- ea: `0x1800075f4`
- end: `0x180007659`
- name: `??1?$static_lazy@VTridentHtmlManager@@$0A@V?$lazy_construct@VTridentHtmlManager@@@tlx@@@tlx@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a630`

## callees

- `0x1800075f4`
- `0x180007818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007648`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007648`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000761c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000761c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007634`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007634`

## pseudocode

```c
void __fastcall tlx::static_lazy<TridentHtmlManager,0,tlx::lazy_construct<TridentHtmlManager>>::~static_lazy<TridentHtmlManager,0,tlx::lazy_construct<TridentHtmlManager>>(
        LPINIT_ONCE lpInitOnce)
{
  TridentHtmlManager *v2; // rbx
  WINBOOL v3; // [rsp+30h] [rbp+8h] BYREF
  TridentHtmlManager *v4; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v4 = 0;
  InitOnceBeginInitialize(lpInitOnce, 0, &v3, (LPVOID *)&v4);
  v2 = v4;
  if ( v4 )
  {
    TridentHtmlManager::Uninitialize(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 8));
  }
  else
  {
    InitOnceComplete(lpInitOnce, 0, 0);
  }
}

```

## disassembly

```asm
0x1800075f4  mov     rax, rsp
0x1800075f7  mov     [rax+18h], rbx
0x1800075fb  push    rdi
0x1800075fc  sub     rsp, 20h
0x180007600  lea     r9, [rax+10h]; lpContext
0x180007604  mov     dword ptr [rax+8], 0
0x18000760b  lea     r8, [rax+8]; fPending
0x18000760f  mov     qword ptr [rax+10h], 0
0x180007617  xor     edx, edx; dwFlags
0x180007619  mov     rdi, rcx
0x18000761c  call    cs:__imp_InitOnceBeginInitialize
0x180007622  mov     rbx, [rsp+28h+arg_8]
0x180007627  test    rbx, rbx
0x18000762a  jnz     short loc_18000763C
0x18000762c  xor     r8d, r8d; lpContext
0x18000762f  xor     edx, edx; dwFlags
0x180007631  mov     rcx, rdi; lpInitOnce
0x180007634  call    cs:__imp_InitOnceComplete
0x18000763a  jmp     short loc_18000764E
0x18000763c  mov     rcx, rbx; this
0x18000763f  call    ?Uninitialize@TridentHtmlManager@@QEAAXXZ; TridentHtmlManager::Uninitialize(void)
0x180007644  lea     rcx, [rbx+8]; lpCriticalSection
0x180007648  call    cs:__imp_DeleteCriticalSection
0x18000764e  mov     rbx, [rsp+28h+arg_10]
0x180007653  add     rsp, 20h
0x180007657  pop     rdi
0x180007658  retn
```
