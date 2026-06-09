# DoFreeContextMemory

- ea: `0x1800170e0`
- end: `0x1800171e8`
- name: `DoFreeContextMemory`
- size: `264`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000b890`

## callees

- `0x1800170e0`
- `0x1800248e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180017169`
- `ntoskrnl!ExFreePoolWithTag` at `0x180017169`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180017146`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800171b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800171d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180017146`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800171b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800171d7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180017123`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180017123`

## pseudocode

```c
void __fastcall DoFreeContextMemory(_QWORD *P)
{
  __int64 v1; // rbx
  __int16 v3; // ax
  int v4; // ecx
  int v5; // eax
  int v6; // ecx
  ULONG v7; // edx

  v1 = P[1];
  v3 = *(_WORD *)(v1 + 24);
  if ( v3 == 32 )
  {
    if ( *P )
      ExFreeToNPagedLookasideList(&stru_18003F5C0, (PVOID)*P);
  }
  else if ( v3 == 64 && *P )
  {
    ExFreeToNPagedLookasideList(&stru_18003F7C0, (PVOID)*P);
  }
  v4 = *(unsigned __int8 *)(v1 + 27);
  if ( v4 == 1 )
  {
    v5 = *((_DWORD *)P + 18);
    if ( (v5 & 1) != 0 )
    {
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v1 + 192), P);
      return;
    }
    if ( (v5 & 8) == 0 )
    {
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v1 + 64), P);
      return;
    }
    v7 = *(_DWORD *)(v1 + 232);
LABEL_11:
    ExFreePoolWithTag(P, v7);
    return;
  }
  v6 = v4 - 2;
  if ( !v6 )
  {
    v7 = *(_DWORD *)(v1 + 32);
    goto LABEL_11;
  }
  if ( v6 == 1 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(v1 + 40))(P, *(unsigned __int16 *)(v1 + 24));
}

```

## disassembly

```asm
0x1800170e0  mov     [rsp+arg_0], rbx
0x1800170e5  push    rdi
0x1800170e6  sub     rsp, 20h
0x1800170ea  mov     rbx, [rcx+8]
0x1800170ee  mov     rdi, rcx
0x1800170f1  movzx   eax, word ptr [rbx+18h]
0x1800170f5  cmp     ax, 20h ; ' '
0x1800170f9  jz      loc_1800171C4
0x1800170ff  cmp     ax, 40h ; '@'
0x180017103  jz      loc_1800171A0
0x180017109  movzx   ecx, byte ptr [rbx+1Bh]
0x18001710d  cmp     ecx, 1
0x180017110  jnz     short loc_18001715E
0x180017112  mov     eax, [rdi+48h]
0x180017115  test    cl, al
0x180017117  jz      short loc_18001713B
0x180017119  lea     rcx, [rbx+0C0h]; Lookaside
0x180017120  mov     rdx, rdi; Entry
0x180017123  call    cs:__imp_ExFreeToPagedLookasideList
0x18001712a  nop     dword ptr [rax+rax+00h]
0x18001712f  mov     rbx, [rsp+28h+arg_0]
0x180017134  add     rsp, 20h
0x180017138  pop     rdi
0x180017139  retn
0x18001713b  test    al, 8
0x18001713d  jnz     short loc_180017198
0x18001713f  lea     rcx, [rbx+40h]; Lookaside
0x180017143  mov     rdx, rdi; Entry
0x180017146  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001714d  nop     dword ptr [rax+rax+00h]
0x180017152  mov     rbx, [rsp+28h+arg_0]
0x180017157  add     rsp, 20h
0x18001715b  pop     rdi
0x18001715c  retn
0x18001715e  sub     ecx, 2
0x180017161  jnz     short loc_180017177
0x180017163  mov     edx, [rbx+20h]; Tag
0x180017166  mov     rcx, rdi; P
0x180017169  call    cs:__imp_ExFreePoolWithTag
0x180017170  nop     dword ptr [rax+rax+00h]
0x180017175  jmp     short loc_18001712F
0x180017177  cmp     ecx, 1
0x18001717a  jnz     short loc_18001712F
0x18001717c  mov     rax, [rbx+28h]
0x180017180  mov     rcx, rdi
0x180017183  movzx   edx, word ptr [rbx+18h]
0x180017187  call    _guard_dispatch_icall
0x18001718c  mov     rbx, [rsp+28h+arg_0]
0x180017191  add     rsp, 20h
0x180017195  pop     rdi
0x180017196  retn
0x180017198  mov     edx, [rbx+0E8h]
0x18001719e  jmp     short loc_180017166
0x1800171a0  mov     rdx, [rcx]; Entry
0x1800171a3  test    rdx, rdx
0x1800171a6  jz      loc_180017109
0x1800171ac  lea     rcx, stru_18003F7C0; Lookaside
0x1800171b3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800171ba  nop     dword ptr [rax+rax+00h]
0x1800171bf  jmp     loc_180017109
0x1800171c4  mov     rdx, [rcx]; Entry
0x1800171c7  test    rdx, rdx
0x1800171ca  jz      loc_180017109
0x1800171d0  lea     rcx, stru_18003F5C0; Lookaside
0x1800171d7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800171de  nop     dword ptr [rax+rax+00h]
0x1800171e3  jmp     loc_180017109
```
