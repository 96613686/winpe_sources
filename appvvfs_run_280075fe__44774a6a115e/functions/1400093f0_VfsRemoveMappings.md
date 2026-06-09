# VfsRemoveMappings

- ea: `0x1400093f0`
- end: `0x140009474`
- name: `VfsRemoveMappings`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005888`
- `0x140009d44`

## callees

- `0x140008a04`
- `0x1400093f0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000945c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000945c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009450`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009450`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009411`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009411`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009400`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009400`

## pseudocode

```c
void __fastcall VfsRemoveMappings(PERESOURCE *a1)
{
  struct _ERESOURCE *v1; // rbx
  _QWORD **v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax

  v1 = *a1;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v1, 1u);
  v3 = (_QWORD **)(a1 + 1);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    VfsDeleteMappingPrefixTable(v4);
  }
  ExReleaseResourceLite(*a1);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400093f0  mov     [rsp+arg_0], rbx
0x1400093f5  push    rdi
0x1400093f6  sub     rsp, 20h
0x1400093fa  mov     rbx, [rcx]
0x1400093fd  mov     rdi, rcx
0x140009400  call    cs:__imp_KeEnterCriticalRegion
0x140009407  nop     dword ptr [rax+rax+00h]
0x14000940c  mov     dl, 1; Wait
0x14000940e  mov     rcx, rbx; Resource
0x140009411  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140009418  nop     dword ptr [rax+rax+00h]
0x14000941d  lea     rbx, [rdi+8]
0x140009421  mov     rcx, [rbx]; Entry
0x140009424  cmp     rcx, rbx
0x140009427  jz      short loc_14000944D
0x140009429  cmp     [rcx+8], rbx
0x14000942d  jnz     short loc_140009446
0x14000942f  mov     rax, [rcx]
0x140009432  cmp     [rax+8], rcx
0x140009436  jnz     short loc_140009446
0x140009438  mov     [rbx], rax
0x14000943b  mov     [rax+8], rbx
0x14000943f  call    VfsDeleteMappingPrefixTable
0x140009444  jmp     short loc_140009421
0x140009446  mov     ecx, 3
0x14000944b  int     29h; Win8: RtlFailFast(ecx)
0x14000944d  mov     rcx, [rdi]; Resource
0x140009450  call    cs:__imp_ExReleaseResourceLite
0x140009457  nop     dword ptr [rax+rax+00h]
0x14000945c  call    cs:__imp_KeLeaveCriticalRegion
0x140009463  nop     dword ptr [rax+rax+00h]
0x140009468  mov     rbx, [rsp+28h+arg_0]
0x14000946d  add     rsp, 20h
0x140009471  pop     rdi
0x140009472  retn
```
