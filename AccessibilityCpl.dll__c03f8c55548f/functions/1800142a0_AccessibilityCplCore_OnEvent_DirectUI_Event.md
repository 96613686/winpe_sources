# AccessibilityCplCore::OnEvent(DirectUI::Event *)

- ea: `0x1800142a0`
- end: `0x180014327`
- name: `?OnEvent@AccessibilityCplCore@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `135`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004e1c`
- `0x1800142a0`
- `0x18002e010`

## import_xrefs

- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x1800142b6`
- `DUI70!?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ` at `0x1800142ec`

## pseudocode

```c
void __fastcall AccessibilityCplCore::OnEvent(AccessibilityCplCore *this, struct DirectUI::Event *a2)
{
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v4 = DirectUI::Button::Click;
    if ( (unsigned __int8)operator==((char *)a2 + 8, &v4) )
      (*(void (__fastcall **)(AccessibilityCplCore *, struct DirectUI::Event *))(*(_QWORD *)this + 64LL))(this, a2);
  }
  if ( *((_DWORD *)a2 + 5) == 2 )
  {
    v4 = DirectUI::Combobox::SelectionChange;
    if ( (unsigned __int8)operator==((char *)a2 + 8, &v4) )
      (*(void (__fastcall **)(AccessibilityCplCore *, struct DirectUI::Event *))(*(_QWORD *)this + 64LL))(this, a2);
  }
}

```

## disassembly

```asm
0x1800142a0  mov     [rsp+arg_0], rbx
0x1800142a5  push    rdi
0x1800142a6  sub     rsp, 20h
0x1800142aa  cmp     dword ptr [rdx+14h], 1
0x1800142ae  mov     rbx, rdx
0x1800142b1  mov     rdi, rcx
0x1800142b4  jnz     short loc_1800142E6
0x1800142b6  mov     rax, cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x1800142bd  lea     rcx, [rdx+8]
0x1800142c1  lea     rdx, [rsp+28h+arg_8]
0x1800142c6  mov     [rsp+28h+arg_8], rax
0x1800142cb  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x1800142d0  test    al, al
0x1800142d2  jz      short loc_1800142E6
0x1800142d4  mov     rax, [rdi]
0x1800142d7  mov     rdx, rbx
0x1800142da  mov     rcx, rdi
0x1800142dd  mov     rax, [rax+40h]
0x1800142e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e6  cmp     dword ptr [rbx+14h], 2
0x1800142ea  jnz     short loc_18001431C
0x1800142ec  mov     rax, cs:__imp_?SelectionChange@Combobox@DirectUI@@SA?AVUID@@XZ; DirectUI::Combobox::SelectionChange(void)
0x1800142f3  lea     rcx, [rbx+8]
0x1800142f7  lea     rdx, [rsp+28h+arg_8]
0x1800142fc  mov     [rsp+28h+arg_8], rax
0x180014301  call    ??8@YA_NAEBVUID@@AEBQ6A?AV0@XZ@Z; operator==(UID const &,UID (*const &)(void))
0x180014306  test    al, al
0x180014308  jz      short loc_18001431C
0x18001430a  mov     rax, [rdi]
0x18001430d  mov     rdx, rbx
0x180014310  mov     rcx, rdi
0x180014313  mov     rax, [rax+40h]
0x180014317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431c  mov     rbx, [rsp+28h+arg_0]
0x180014321  add     rsp, 20h
0x180014325  pop     rdi
0x180014326  retn
```
