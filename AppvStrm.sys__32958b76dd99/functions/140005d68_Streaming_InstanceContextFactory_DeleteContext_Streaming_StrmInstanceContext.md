# Streaming::InstanceContextFactory::DeleteContext(Streaming::StrmInstanceContext *)

- ea: `0x140005d68`
- end: `0x140005e36`
- name: `?DeleteContext@InstanceContextFactory@Streaming@@QEAAXPEAUStrmInstanceContext@2@@Z`
- size: `206`
- prototype: `void __fastcall(PERESOURCE *this, struct Streaming::StrmInstanceContext ***)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005640`

## callees

- `0x140005498`
- `0x140005d68`
- `0x140011bf8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005dea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005dea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005dde`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005dde`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005da1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005da1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005d89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005d89`

## pseudocode

```c
void __fastcall Streaming::InstanceContextFactory::DeleteContext(
        PERESOURCE *this,
        struct Streaming::StrmInstanceContext ***a2)
{
  bool v2; // si
  struct Streaming::StrmInstanceContext **v5; // rax
  struct Streaming::StrmInstanceContext **v6; // rcx
  struct _ERESOURCE *v7; // rcx
  struct Streaming::StrmInstanceContext **v8; // rax
  PERESOURCE *v9; // rcx

  if ( a2 )
  {
    v2 = 0;
    if ( this[3] )
    {
      KeEnterCriticalRegion();
      v2 = ExAcquireResourceExclusiveLite(this[3], 1u) == 1;
    }
    v5 = *a2;
    if ( (*a2)[1] != (struct Streaming::StrmInstanceContext *)a2
      || (v6 = a2[1], *v6 != (struct Streaming::StrmInstanceContext *)a2) )
    {
      __fastfail(3u);
    }
    *v6 = (struct Streaming::StrmInstanceContext *)v5;
    v5[1] = (struct Streaming::StrmInstanceContext *)v6;
    if ( v2 )
    {
      v7 = this[3];
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    v8 = a2[35];
    if ( v8 && *((_DWORD *)v8 + 2) )
    {
      v9 = (PERESOURCE *)a2[34];
      if ( v9 )
        Streaming::StreamingTargetFileCache::Clear(v9, (struct Streaming::StrmInstanceContext *)a2);
    }
    Streaming::StrmInstanceContext::~StrmInstanceContext((Streaming::StrmInstanceContext *)a2);
  }
}

```

## disassembly

```asm
0x140005d68  test    rdx, rdx
0x140005d6b  jz      locret_140005E2D
0x140005d71  push    rbx
0x140005d72  push    rbp
0x140005d73  push    rsi
0x140005d74  push    rdi
0x140005d75  sub     rsp, 28h
0x140005d79  xor     sil, sil
0x140005d7c  mov     rbx, rdx
0x140005d7f  cmp     qword ptr [rcx+18h], 0
0x140005d84  mov     rdi, rcx
0x140005d87  jz      short loc_140005DB7
0x140005d89  call    cs:__imp_KeEnterCriticalRegion
0x140005d90  nop     dword ptr [rax+rax+00h]
0x140005d95  mov     rcx, [rdi+18h]; Resource
0x140005d99  mov     ebp, 1
0x140005d9e  mov     dl, bpl; Wait
0x140005da1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005da8  nop     dword ptr [rax+rax+00h]
0x140005dad  cmp     al, bpl
0x140005db0  movzx   esi, sil
0x140005db4  cmovz   esi, ebp
0x140005db7  mov     rax, [rbx]
0x140005dba  cmp     [rax+8], rbx
0x140005dbe  jnz     short loc_140005E2F
0x140005dc0  mov     rcx, [rbx+8]
0x140005dc4  cmp     [rcx], rbx
0x140005dc7  jnz     short loc_140005E2F
0x140005dc9  mov     [rcx], rax
0x140005dcc  mov     [rax+8], rcx
0x140005dd0  test    sil, sil
0x140005dd3  jz      short loc_140005DF6
0x140005dd5  mov     rcx, [rdi+18h]; Resource
0x140005dd9  test    rcx, rcx
0x140005ddc  jz      short loc_140005DF6
0x140005dde  call    cs:__imp_ExReleaseResourceLite
0x140005de5  nop     dword ptr [rax+rax+00h]
0x140005dea  call    cs:__imp_KeLeaveCriticalRegion
0x140005df1  nop     dword ptr [rax+rax+00h]
0x140005df6  mov     rax, [rbx+118h]
0x140005dfd  test    rax, rax
0x140005e00  jz      short loc_140005E1D
0x140005e02  mov     eax, [rax+8]
0x140005e05  test    eax, eax
0x140005e07  jz      short loc_140005E1D
0x140005e09  mov     rcx, [rbx+110h]; this
0x140005e10  test    rcx, rcx
0x140005e13  jz      short loc_140005E1D
0x140005e15  mov     rdx, rbx; struct Streaming::StrmInstanceContext *
0x140005e18  call    ?Clear@StreamingTargetFileCache@Streaming@@QEAAXPEAUStrmInstanceContext@2@@Z; Streaming::StreamingTargetFileCache::Clear(Streaming::StrmInstanceContext *)
0x140005e1d  mov     rcx, rbx; this
0x140005e20  call    ??1StrmInstanceContext@Streaming@@QEAA@XZ; Streaming::StrmInstanceContext::~StrmInstanceContext(void)
0x140005e25  add     rsp, 28h
0x140005e29  pop     rdi
0x140005e2a  pop     rsi
0x140005e2b  pop     rbp
0x140005e2c  pop     rbx
0x140005e2d  retn
0x140005e2f  mov     ecx, 3
0x140005e34  int     29h; Win8: RtlFailFast(ecx)
```
