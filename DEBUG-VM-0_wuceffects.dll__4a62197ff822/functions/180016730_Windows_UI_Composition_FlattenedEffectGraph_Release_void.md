# Windows::UI::Composition::FlattenedEffectGraph::Release(void)

- ea: `0x180016730`
- end: `0x18001682e`
- name: `?Release@FlattenedEffectGraph@Composition@UI@Windows@@UEAAKXZ`
- size: `254`
- prototype: `unsigned int __fastcall(Windows::UI::Composition::FlattenedEffectGraph *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800269e0`

## callees

- `0x180016730`
- `0x18002b594`
- `0x18002e010`

## string_xrefs

- `0x1800167b8`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800167d6`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800167f4`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180016812`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::FlattenedEffectGraph::Release(
        Windows::UI::Composition::FlattenedEffectGraph *this)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( v2 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v4);
  if ( !v2 )
  {
    if ( _InterlockedAdd((volatile signed __int32 *)this + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    (*(void (__fastcall **)(Windows::UI::Composition::FlattenedEffectGraph *))(*(_QWORD *)this + 24LL))(this);
    v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
    if ( v2 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    if ( !v2 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)this + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v4);
      (*(void (__fastcall **)(Windows::UI::Composition::FlattenedEffectGraph *, __int64))(*(_QWORD *)this + 16LL))(
        this,
        1);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016730  mov     [rsp+arg_0], rbx
0x180016735  mov     [rsp+arg_8], rsi
0x18001673a  push    rdi; int
0x18001673b  sub     rsp, 20h
0x18001673f  mov     esi, 0FFFFFFFFh
0x180016744  mov     rdi, rcx
0x180016747  mov     ebx, esi
0x180016749  lock xadd [rcx+8], ebx
0x18001674e  dec     ebx
0x180016750  cmp     ebx, esi
0x180016752  jl      short loc_1800167B3
0x180016754  test    ebx, ebx
0x180016756  jz      short loc_18001676A
0x180016758  mov     rsi, [rsp+28h+arg_8]
0x18001675d  mov     eax, ebx
0x18001675f  mov     rbx, [rsp+28h+arg_0]
0x180016764  add     rsp, 20h
0x180016768  pop     rdi
0x180016769  retn
0x18001676a  lock add dword ptr [rdi+8], 1
0x18001676f  jle     short loc_1800167D1
0x180016771  mov     rax, [rdi]
0x180016774  mov     rcx, rdi
0x180016777  mov     rax, [rax+18h]
0x18001677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016780  mov     ebx, esi
0x180016782  lock xadd [rdi+8], ebx
0x180016787  dec     ebx
0x180016789  cmp     ebx, esi
0x18001678b  jl      short loc_1800167EF
0x18001678d  test    ebx, ebx
0x18001678f  jnz     short loc_180016758
0x180016791  lock xadd [rdi+8], esi
0x180016796  dec     esi
0x180016798  cmp     esi, 0FFFFFFFFh
0x18001679b  jl      short loc_18001680D
0x18001679d  mov     rcx, [rdi]
0x1800167a0  mov     edx, 1
0x1800167a5  mov     rax, [rcx+10h]
0x1800167a9  mov     rcx, rdi
0x1800167ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167b1  jmp     short loc_180016758
0x1800167b3  mov     rcx, [rsp+28h]; this
0x1800167b8  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800167bf  mov     r9d, 8007029Ch; char *
0x1800167c5  mov     edx, 26h ; '&'; void *
0x1800167ca  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800167cf  jmp     short loc_180016754
0x1800167d1  mov     rcx, [rsp+28h]; this
0x1800167d6  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800167dd  mov     r9d, 8007029Ch; char *
0x1800167e3  mov     edx, 18h; void *
0x1800167e8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800167ed  jmp     short loc_180016771
0x1800167ef  mov     rcx, [rsp+28h]; this
0x1800167f4  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800167fb  mov     r9d, 8007029Ch; char *
0x180016801  mov     edx, 26h ; '&'; void *
0x180016806  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001680b  jmp     short loc_18001678D
0x18001680d  mov     rcx, [rsp+28h]; this
0x180016812  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x180016819  mov     r9d, 8007029Ch; char *
0x18001681f  mov     edx, 26h ; '&'; void *
0x180016824  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180016829  jmp     loc_18001679D
```
