# Windows::UI::Composition::Traverser::FindSourceFlatteningEffect(Windows::Graphics::Effects::IGraphicsEffectSource const *)

- ea: `0x1800042ac`
- end: `0x180004372`
- name: `?FindSourceFlatteningEffect@Traverser@Composition@UI@Windows@@AEAAPEAUIGraphicsEffect@Effects@Graphics@4@PEBUIGraphicsEffectSource@674@@Z`
- size: `198`
- prototype: `struct Windows::Graphics::Effects::IGraphicsEffect *__fastcall(Windows::UI::Composition::Traverser *__hidden this, const struct Windows::Graphics::Effects::IGraphicsEffectSource *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005440`

## callees

- `0x1800042ac`
- `0x18001eaa0`
- `0x18002e010`

## string_xrefs

- `0x18000430f`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Windows::Graphics::Effects::IGraphicsEffect *__fastcall Windows::UI::Composition::Traverser::FindSourceFlatteningEffect(
        Windows::UI::Composition::Traverser *this,
        const struct Windows::Graphics::Effects::IGraphicsEffectSource *a2)
{
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  int v6; // eax
  const struct Windows::Graphics::Effects::IGraphicsEffectSource *v7; // rcx
  __int64 v8; // rbx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  const struct Windows::Graphics::Effects::IGraphicsEffectSource *v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = (__int64 *)*((_QWORD *)this + 15);
  v4 = (__int64 *)*((_QWORD *)this + 16);
  while ( 1 )
  {
    if ( v3 == v4 )
      return 0;
    v11 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct Windows::Graphics::Effects::IGraphicsEffectSource **))(*(_QWORD *)(*v3 + 16) + 56LL))(
           *v3 + 16,
           0,
           &v11);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v6,
        v9);
    v7 = v11;
    if ( v11 == a2 )
      break;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(const struct Windows::Graphics::Effects::IGraphicsEffectSource *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    ++v3;
  }
  v8 = *v3;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(const struct Windows::Graphics::Effects::IGraphicsEffectSource *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return (struct Windows::Graphics::Effects::IGraphicsEffect *)v8;
}

```

## disassembly

```asm
0x1800042ac  mov     [rsp+arg_8], rbx
0x1800042b1  mov     [rsp+arg_10], rsi
0x1800042b6  push    rdi; int
0x1800042b7  sub     rsp, 20h
0x1800042bb  mov     rsi, rdx
0x1800042be  mov     rbx, [rcx+78h]
0x1800042c2  mov     rdi, [rcx+80h]
0x1800042c9  cmp     rbx, rdi
0x1800042cc  jnz     short loc_1800042E0
0x1800042ce  xor     eax, eax
0x1800042d0  mov     rbx, [rsp+28h+arg_8]
0x1800042d5  mov     rsi, [rsp+28h+arg_10]
0x1800042da  add     rsp, 20h
0x1800042de  pop     rdi
0x1800042df  retn
0x1800042e0  mov     [rsp+28h+arg_0], 0
0x1800042e9  mov     rcx, [rbx]
0x1800042ec  add     rcx, 10h
0x1800042f0  mov     rax, [rcx]
0x1800042f3  lea     r8, [rsp+28h+arg_0]
0x1800042f8  xor     edx, edx
0x1800042fa  mov     rax, [rax+38h]
0x1800042fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004303  mov     rcx, [rsp+28h]; this
0x180004308  test    eax, eax
0x18000430a  jns     short loc_180004321
0x18000430c  mov     r9d, eax; char *
0x18000430f  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180004316  mov     edx, 181h; void *
0x18000431b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180004321  mov     rcx, [rsp+28h+arg_0]
0x180004326  cmp     rcx, rsi
0x180004329  jnz     short loc_18000434E
0x18000432b  mov     rbx, [rbx]
0x18000432e  test    rcx, rcx
0x180004331  jz      short loc_180004349
0x180004333  mov     [rsp+28h+arg_0], 0
0x18000433c  mov     rdx, [rcx]
0x18000433f  mov     rax, [rdx+10h]
0x180004343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004348  nop
0x180004349  mov     rax, rbx
0x18000434c  jmp     short loc_1800042D0
0x18000434e  test    rcx, rcx
0x180004351  jz      short loc_180004369
0x180004353  mov     [rsp+28h+arg_0], 0
0x18000435c  mov     rax, [rcx]
0x18000435f  mov     rax, [rax+10h]
0x180004363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004368  nop
0x180004369  add     rbx, 8
0x18000436d  jmp     loc_1800042C9
```
