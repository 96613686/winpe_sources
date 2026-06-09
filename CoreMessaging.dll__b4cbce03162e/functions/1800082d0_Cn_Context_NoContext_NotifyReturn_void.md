# Cn::Context::NoContext_NotifyReturn(void *)

- ea: `0x1800082d0`
- end: `0x18000834e`
- name: `?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z`
- size: `126`
- prototype: `void __fastcall(Cn::Context *__hidden this, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c50`
- `0x180007f88`
- `0x180008160`
- `0x18001ebcc`
- `0x18001f3b0`
- `0x18001f9b0`
- `0x180020550`

## callees

- `0x1800082d0`
- `0x18008ae1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008318`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000832a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000832a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000830e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000830e`

## pseudocode

```c
void __fastcall Cn::Context::NoContext_NotifyReturn(Cn::Context *this, void *a2)
{
  __int64 v2; // rbx
  int v5; // r8d
  const char16_t *v6; // rcx

  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
    v5 = *(_DWORD *)(v2 + 60);
    *(_DWORD *)(v2 + 60) = v5 + 1;
    if ( !v5 )
    {
      *(_QWORD *)(v2 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v2 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, this) )
      CFlat::Abandonment::Fail(v6);
  }
  *((_QWORD *)this + 2) = a2;
}

```

## disassembly

```asm
0x1800082d0  mov     [rsp+arg_0], rbx
0x1800082d5  mov     [rsp+arg_8], rsi
0x1800082da  push    rdi
0x1800082db  sub     rsp, 20h
0x1800082df  mov     rbx, [rcx+58h]
0x1800082e3  mov     rsi, rdx
0x1800082e6  mov     rdi, rcx
0x1800082e9  test    rbx, rbx
0x1800082ec  jz      short loc_180008334
0x1800082ee  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800082f2  call    cs:__imp_EnterCriticalSection
0x1800082f8  mov     r8d, [rbx+3Ch]
0x1800082fc  lea     eax, [r8+1]
0x180008300  mov     [rbx+3Ch], eax
0x180008303  test    r8d, r8d
0x180008306  jnz     short loc_180008321
0x180008308  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000830e  call    cs:__imp_TlsGetValue
0x180008314  mov     [rbx+40h], rax
0x180008318  call    cs:__imp_GetCurrentThreadId
0x18000831e  mov     [rbx+48h], eax
0x180008321  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180008327  mov     rdx, rdi; lpTlsValue
0x18000832a  call    cs:__imp_TlsSetValue
0x180008330  test    eax, eax
0x180008332  jz      short loc_180008348
0x180008334  mov     rbx, [rsp+28h+arg_0]
0x180008339  mov     [rdi+10h], rsi
0x18000833d  mov     rsi, [rsp+28h+arg_8]
0x180008342  add     rsp, 20h
0x180008346  pop     rdi
0x180008347  retn
0x180008348  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
```
