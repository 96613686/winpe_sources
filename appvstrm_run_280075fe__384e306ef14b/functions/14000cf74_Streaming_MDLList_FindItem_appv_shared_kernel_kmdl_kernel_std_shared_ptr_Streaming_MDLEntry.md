# Streaming::MDLList::FindItem(appv::shared::kernel::kmdl *,kernel_std::shared_ptr<Streaming::MDLEntry> &)

- ea: `0x14000cf74`
- end: `0x14000d04e`
- name: `?FindItem@MDLList@Streaming@@QEAAJPEAVkmdl@kernel@shared@appv@@AEAV?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@@Z`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d0c8`
- `0x1400115cc`

## callees

- `0x140003bd8`
- `0x14000cf74`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d007`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d031`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d007`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d031`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cffb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d025`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cffb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d025`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000cfab`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000cfab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf92`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf92`

## pseudocode

```c
__int64 __fastcall Streaming::MDLList::FindItem(__int64 a1, __int64 a2, _QWORD *a3)
{
  bool v3; // di
  _QWORD *i; // rdx
  struct _ERESOURCE *v8; // rcx
  struct _ERESOURCE *v10; // rcx

  v3 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 8), 1u) == 1;
  }
  for ( i = *(_QWORD **)(a1 + 48); i != (_QWORD *)(a1 + 24); i = (_QWORD *)i[3] )
  {
    if ( *(_QWORD *)*i == a2 )
    {
      *a3 = *i;
      kernel_std::detail::shared_count::operator=(a3 + 1, i + 1);
      if ( v3 )
      {
        v8 = *(struct _ERESOURCE **)(a1 + 8);
        if ( v8 )
        {
          ExReleaseResourceLite(v8);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
  }
  if ( v3 )
  {
    v10 = *(struct _ERESOURCE **)(a1 + 8);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x14000cf74  push    rbx
0x14000cf76  push    rbp
0x14000cf77  push    rsi
0x14000cf78  push    rdi
0x14000cf79  push    r14
0x14000cf7b  sub     rsp, 20h
0x14000cf7f  xor     dil, dil
0x14000cf82  mov     rsi, r8
0x14000cf85  cmp     qword ptr [rcx+8], 0
0x14000cf8a  mov     rbp, rdx
0x14000cf8d  mov     rbx, rcx
0x14000cf90  jz      short loc_14000CFC2
0x14000cf92  call    cs:__imp_KeEnterCriticalRegion
0x14000cf99  nop     dword ptr [rax+rax+00h]
0x14000cf9e  mov     rcx, [rbx+8]; Resource
0x14000cfa2  mov     r14d, 1
0x14000cfa8  mov     dl, r14b; Wait
0x14000cfab  call    cs:__imp_ExAcquireResourceSharedLite
0x14000cfb2  nop     dword ptr [rax+rax+00h]
0x14000cfb7  cmp     al, r14b
0x14000cfba  movzx   edi, dil
0x14000cfbe  cmovz   edi, r14d
0x14000cfc2  mov     rdx, [rbx+30h]
0x14000cfc6  lea     rcx, [rbx+18h]
0x14000cfca  cmp     rdx, rcx
0x14000cfcd  jz      short loc_14000D017
0x14000cfcf  mov     rax, [rdx]
0x14000cfd2  cmp     [rax], rbp
0x14000cfd5  jz      short loc_14000CFDD
0x14000cfd7  mov     rdx, [rdx+18h]
0x14000cfdb  jmp     short loc_14000CFCA
0x14000cfdd  add     rdx, 8
0x14000cfe1  mov     [rsi], rax
0x14000cfe4  lea     rcx, [rsi+8]
0x14000cfe8  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x14000cfed  test    dil, dil
0x14000cff0  jz      short loc_14000D013
0x14000cff2  mov     rcx, [rbx+8]; Resource
0x14000cff6  test    rcx, rcx
0x14000cff9  jz      short loc_14000D013
0x14000cffb  call    cs:__imp_ExReleaseResourceLite
0x14000d002  nop     dword ptr [rax+rax+00h]
0x14000d007  call    cs:__imp_KeLeaveCriticalRegion
0x14000d00e  nop     dword ptr [rax+rax+00h]
0x14000d013  xor     eax, eax
0x14000d015  jmp     short loc_14000D042
0x14000d017  test    dil, dil
0x14000d01a  jz      short loc_14000D03D
0x14000d01c  mov     rcx, [rbx+8]; Resource
0x14000d020  test    rcx, rcx
0x14000d023  jz      short loc_14000D03D
0x14000d025  call    cs:__imp_ExReleaseResourceLite
0x14000d02c  nop     dword ptr [rax+rax+00h]
0x14000d031  call    cs:__imp_KeLeaveCriticalRegion
0x14000d038  nop     dword ptr [rax+rax+00h]
0x14000d03d  mov     eax, 0C0000225h
0x14000d042  add     rsp, 20h
0x14000d046  pop     r14
0x14000d048  pop     rdi
0x14000d049  pop     rsi
0x14000d04a  pop     rbp
0x14000d04b  pop     rbx
0x14000d04c  retn
```
