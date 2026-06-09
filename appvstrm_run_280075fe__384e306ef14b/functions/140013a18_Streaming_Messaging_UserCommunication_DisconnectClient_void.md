# Streaming::Messaging::UserCommunication::DisconnectClient(void)

- ea: `0x140013a18`
- end: `0x140013ac4`
- name: `?DisconnectClient@UserCommunication@Messaging@Streaming@@QEAAXXZ`
- size: `172`
- prototype: `void __fastcall(Streaming::Messaging::UserCommunication *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001044`
- `0x140001104`
- `0x140013ed0`

## callees

- `0x140013a18`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013aa7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013aa7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013a9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013a9b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013a4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013a4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013a34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013a34`
- `FLTMGR!FltCloseClientPort` at `0x140013a7a`
- `FLTMGR!FltCloseClientPort` at `0x140013a7a`

## pseudocode

```c
void __fastcall Streaming::Messaging::UserCommunication::DisconnectClient(
        Streaming::Messaging::UserCommunication *this)
{
  bool v1; // si
  struct _ERESOURCE *v3; // rcx

  v1 = 0;
  if ( *((_QWORD *)this + 3) )
  {
    KeEnterCriticalRegion();
    v1 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 3), 1u) == 1;
  }
  if ( *((_QWORD *)this + 1) )
  {
    FltCloseClientPort(*((PFLT_FILTER *)Streaming::gStrmFltData + 1), (PFLT_PORT *)this + 1);
    *((_QWORD *)this + 1) = 0;
  }
  if ( v1 )
  {
    v3 = (struct _ERESOURCE *)*((_QWORD *)this + 3);
    if ( v3 )
    {
      ExReleaseResourceLite(v3);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x140013a18  mov     [rsp+arg_0], rbx
0x140013a1d  mov     [rsp+arg_8], rsi
0x140013a22  push    rdi
0x140013a23  sub     rsp, 20h
0x140013a27  xor     sil, sil
0x140013a2a  mov     rbx, rcx
0x140013a2d  cmp     qword ptr [rcx+18h], 0
0x140013a32  jz      short loc_140013A62
0x140013a34  call    cs:__imp_KeEnterCriticalRegion
0x140013a3b  nop     dword ptr [rax+rax+00h]
0x140013a40  mov     rcx, [rbx+18h]; Resource
0x140013a44  mov     edi, 1
0x140013a49  mov     dl, dil; Wait
0x140013a4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140013a53  nop     dword ptr [rax+rax+00h]
0x140013a58  cmp     al, dil
0x140013a5b  movzx   esi, sil
0x140013a5f  cmovz   esi, edi
0x140013a62  lea     rdi, [rbx+8]
0x140013a66  cmp     qword ptr [rdi], 0
0x140013a6a  jz      short loc_140013A8D
0x140013a6c  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140013a73  mov     rdx, rdi; ClientPort
0x140013a76  mov     rcx, [rcx+8]; Filter
0x140013a7a  call    cs:__imp_FltCloseClientPort
0x140013a81  nop     dword ptr [rax+rax+00h]
0x140013a86  mov     qword ptr [rdi], 0
0x140013a8d  test    sil, sil
0x140013a90  jz      short loc_140013AB3
0x140013a92  mov     rcx, [rbx+18h]; Resource
0x140013a96  test    rcx, rcx
0x140013a99  jz      short loc_140013AB3
0x140013a9b  call    cs:__imp_ExReleaseResourceLite
0x140013aa2  nop     dword ptr [rax+rax+00h]
0x140013aa7  call    cs:__imp_KeLeaveCriticalRegion
0x140013aae  nop     dword ptr [rax+rax+00h]
0x140013ab3  mov     rbx, [rsp+28h+arg_0]
0x140013ab8  mov     rsi, [rsp+28h+arg_8]
0x140013abd  add     rsp, 20h
0x140013ac1  pop     rdi
0x140013ac2  retn
```
