# CMILRefCountBaseT<Windows::UI::Composition::IEffectInstance,CMilObjectDeleter>::InternalRelease(void)

- ea: `0x18001942c`
- end: `0x180019531`
- name: `?InternalRelease@?$CMILRefCountBaseT@UIEffectInstance@Composition@UI@Windows@@VCMilObjectDeleter@@@@IEAAKXZ`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019420`

## callees

- `0x18001942c`
- `0x18002b594`
- `0x18002e010`

## string_xrefs

- `0x1800194b5`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800194d3`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x1800194f4`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`
- `0x180019515`: `onecoreuap\windows\dwm\common\shared\refcountbase.cpp`

## pseudocode

```c
__int64 __fastcall CMILRefCountBaseT<Windows::UI::Composition::IEffectInstance,CMilObjectDeleter>::InternalRelease(
        volatile signed __int32 *a1)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = _InterlockedDecrement(a1 + 2);
  if ( v2 < -1 )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
      (const char *)0x8007029CLL,
      v4);
  if ( !v2 )
  {
    if ( _InterlockedAdd(a1 + 2, 1u) <= 0 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 112LL))(a1);
    v2 = _InterlockedDecrement(a1 + 2);
    if ( v2 < -1 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
        (const char *)0x8007029CLL,
        v4);
    if ( !v2 )
    {
      if ( _InterlockedDecrement(a1 + 2) < -1 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\shared\\refcountbase.cpp",
          (const char *)0x8007029CLL,
          v4);
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 104LL))(a1, 1);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001942c  mov     [rsp+arg_0], rbx
0x180019431  mov     [rsp+arg_8], rsi
0x180019436  push    rdi; int
0x180019437  sub     rsp, 20h
0x18001943b  or      esi, 0FFFFFFFFh
0x18001943e  mov     rdi, rcx
0x180019441  mov     ebx, esi
0x180019443  lock xadd [rcx+8], ebx
0x180019448  add     ebx, esi
0x18001944a  cmp     ebx, esi
0x18001944c  jl      short loc_1800194B0
0x18001944e  test    ebx, ebx
0x180019450  jnz     short loc_18001949E
0x180019452  lock add dword ptr [rdi+8], 1
0x180019457  jle     short loc_1800194CE
0x180019459  mov     rax, [rdi]
0x18001945c  mov     rcx, rdi
0x18001945f  mov     rax, [rax+70h]
0x180019463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019468  mov     ebx, esi
0x18001946a  lock xadd [rdi+8], ebx
0x18001946f  add     ebx, esi
0x180019471  cmp     ebx, esi
0x180019473  jl      short loc_1800194EF
0x180019475  test    ebx, ebx
0x180019477  jnz     short loc_18001949E
0x180019479  mov     eax, esi
0x18001947b  lock xadd [rdi+8], eax
0x180019480  add     eax, esi
0x180019482  cmp     eax, esi
0x180019484  jl      loc_180019510
0x18001948a  mov     rax, [rdi]
0x18001948d  mov     edx, 1
0x180019492  mov     rcx, rdi
0x180019495  mov     rax, [rax+68h]
0x180019499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001949e  mov     rsi, [rsp+28h+arg_8]
0x1800194a3  mov     eax, ebx
0x1800194a5  mov     rbx, [rsp+28h+arg_0]
0x1800194aa  add     rsp, 20h
0x1800194ae  pop     rdi
0x1800194af  retn
0x1800194b0  mov     rcx, [rsp+28h]; this
0x1800194b5  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800194bc  mov     r9d, 8007029Ch; char *
0x1800194c2  mov     edx, 26h ; '&'; void *
0x1800194c7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800194cc  jmp     short loc_18001944E
0x1800194ce  mov     rcx, [rsp+28h]; this
0x1800194d3  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800194da  mov     r9d, 8007029Ch; char *
0x1800194e0  mov     edx, 18h; void *
0x1800194e5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800194ea  jmp     loc_180019459
0x1800194ef  mov     rcx, [rsp+28h]; this
0x1800194f4  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x1800194fb  mov     r9d, 8007029Ch; char *
0x180019501  mov     edx, 26h ; '&'; void *
0x180019506  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001950b  jmp     loc_180019475
0x180019510  mov     rcx, [rsp+28h]; this
0x180019515  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\share"...
0x18001951c  mov     r9d, 8007029Ch; char *
0x180019522  mov     edx, 26h ; '&'; void *
0x180019527  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001952c  jmp     loc_18001948A
```
