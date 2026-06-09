# DIGEST_CONTEXT_CACHE_ENTRY::~DIGEST_CONTEXT_CACHE_ENTRY(void)

- ea: `0x18000482c`
- end: `0x180004887`
- name: `??1DIGEST_CONTEXT_CACHE_ENTRY@@EEAA@XZ`
- size: `91`
- prototype: `void __fastcall(DIGEST_CONTEXT_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004890`

## callees

- `0x18000482c`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x18000487b`
- `SspiCli!DeleteSecurityContext` at `0x18000487b`
- `iisutil!WriteRefTraceLogEx` at `0x180004872`
- `iisutil!WriteRefTraceLogEx` at `0x180004872`

## pseudocode

```c
void __fastcall DIGEST_CONTEXT_CACHE_ENTRY::~DIGEST_CONTEXT_CACHE_ENTRY(DIGEST_CONTEXT_CACHE_ENTRY *this)
{
  struct _SecHandle *v1; // rbx
  __int64 v2; // rax

  v1 = (struct _SecHandle *)((char *)this + 24);
  *((_DWORD *)this + 2) = 1715684164;
  *(_QWORD *)this = &DIGEST_CONTEXT_CACHE_ENTRY::`vftable';
  if ( this != (DIGEST_CONTEXT_CACHE_ENTRY *)-24LL )
  {
    v2 = *((_QWORD *)this + 5);
    if ( v2 )
    {
      if ( *(_QWORD *)(v2 + 80) )
        WriteRefTraceLogEx(*(_QWORD *)(v2 + 80), 0, v1->dwLower, *((_QWORD *)this + 4), 0, 0);
    }
    DeleteSecurityContext(v1);
  }
}

```

## disassembly

```asm
0x18000482c  push    rbx
0x18000482e  sub     rsp, 30h
0x180004832  lea     rbx, [rcx+18h]
0x180004836  mov     dword ptr [rcx+8], 66434344h
0x18000483d  xor     edx, edx
0x18000483f  lea     rax, ??_7DIGEST_CONTEXT_CACHE_ENTRY@@6B@; const DIGEST_CONTEXT_CACHE_ENTRY::`vftable'
0x180004846  mov     [rcx], rax
0x180004849  test    rbx, rbx
0x18000484c  jz      short loc_180004881
0x18000484e  mov     rax, [rcx+28h]
0x180004852  test    rax, rax
0x180004855  jz      short loc_180004878
0x180004857  cmp     [rax+50h], rdx
0x18000485b  jz      short loc_180004878
0x18000485d  mov     r9, [rcx+20h]
0x180004861  mov     rcx, [rax+50h]
0x180004865  mov     r8, [rbx]
0x180004868  mov     [rsp+38h+var_10], rdx
0x18000486d  mov     [rsp+38h+var_18], rdx
0x180004872  call    cs:__imp_WriteRefTraceLogEx
0x180004878  mov     rcx, rbx; phContext
0x18000487b  call    cs:__imp_DeleteSecurityContext
0x180004881  add     rsp, 30h
0x180004885  pop     rbx
0x180004886  retn
```
