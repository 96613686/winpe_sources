# CProviderRegistrationCache::FindProvFromGUID(_GUID const *,CProviderEntry * *)

- ea: `0x1800082b0`
- end: `0x18000834e`
- name: `?FindProvFromGUID@CProviderRegistrationCache@@QEAAJPEBU_GUID@@PEAPEAVCProviderEntry@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _GUID *, struct CProviderEntry **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002560`
- `0x1800030f0`
- `0x1800066f0`

## callees

- `0x1800082b0`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x18000830f`
- `RPCRT4!UuidEqual` at `0x18000830f`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::FindProvFromGUID(
        CProviderRegistrationCache *this,
        struct _GUID *a2,
        struct CProviderEntry **a3)
{
  __int64 v3; // rbx
  unsigned int i; // ebp
  RPC_STATUS Status; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  Status = 0;
  for ( i = -1073741275; (unsigned int)v3 < *((_DWORD *)this + 38); v3 = (unsigned int)(v3 + 1) )
  {
    if ( UuidEqual((UUID *)(*(_QWORD *)(8 * v3 + *((_QWORD *)this + 18)) + 8LL), a2, &Status) )
    {
      i = 0;
      *a3 = *(struct CProviderEntry **)(8 * v3 + *((_QWORD *)this + 18));
    }
  }
  return i;
}

```

## disassembly

```asm
0x1800082b0  mov     [rsp+arg_10], rbx
0x1800082b5  mov     [rsp+arg_18], rbp
0x1800082ba  push    rdi
0x1800082bb  push    r14
0x1800082bd  push    r15
0x1800082bf  sub     rsp, 20h
0x1800082c3  xor     ebx, ebx
0x1800082c5  mov     [rsp+38h+Status], 0
0x1800082cd  mov     r15, r8
0x1800082d0  mov     r14, rdx
0x1800082d3  mov     rdi, rcx
0x1800082d6  mov     ebp, 0C0000225h
0x1800082db  cmp     [rcx+98h], ebx
0x1800082e1  jbe     short loc_180008338
0x1800082e3  mov     [rsp+38h+arg_8], rsi
0x1800082e8  nop     dword ptr [rax+rax+00000000h]
0x1800082f0  mov     rax, [rdi+90h]
0x1800082f7  lea     rsi, ds:0[rbx*8]
0x1800082ff  lea     r8, [rsp+38h+Status]; Status
0x180008304  mov     rdx, r14; Uuid2
0x180008307  mov     rcx, [rsi+rax]
0x18000830b  add     rcx, 8; Uuid1
0x18000830f  call    cs:__imp_UuidEqual
0x180008315  test    eax, eax
0x180008317  jz      short loc_180008329
0x180008319  mov     rax, [rdi+90h]
0x180008320  xor     ebp, ebp
0x180008322  mov     rcx, [rsi+rax]
0x180008326  mov     [r15], rcx
0x180008329  inc     ebx
0x18000832b  cmp     ebx, [rdi+98h]
0x180008331  jb      short loc_1800082F0
0x180008333  mov     rsi, [rsp+38h+arg_8]
0x180008338  mov     rbx, [rsp+38h+arg_10]
0x18000833d  mov     eax, ebp
0x18000833f  mov     rbp, [rsp+38h+arg_18]
0x180008344  add     rsp, 20h
0x180008348  pop     r15
0x18000834a  pop     r14
0x18000834c  pop     rdi
0x18000834d  retn
```
