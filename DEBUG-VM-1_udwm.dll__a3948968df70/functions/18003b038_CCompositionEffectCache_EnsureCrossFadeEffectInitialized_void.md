# CCompositionEffectCache::EnsureCrossFadeEffectInitialized(void)

- ea: `0x18003b038`
- end: `0x18003b0ba`
- name: `?EnsureCrossFadeEffectInitialized@CCompositionEffectCache@@AEAAXXZ`
- size: `130`
- prototype: `void __fastcall(CCompositionEffectCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b018`

## callees

- `0x18003b038`
- `0x18003c990`
- `0x1800ab1dc`
- `0x1800e05d4`

## import_xrefs

- `wuceffects!CreateCrossfadeEffectFactory` at `0x18003b06a`
- `wuceffects!CreateCrossfadeEffectFactory` at `0x18003b06a`

## string_xrefs

- `0x18003b0a8`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x18003b082`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x18003b089`: `CCompositionEffectCache::EnsureCrossFadeEffectInitialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCompositionEffectCache::EnsureCrossFadeEffectInitialized(CCompositionEffectCache *this)
{
  __int64 v2; // rcx
  int CrossfadeEffectFactory; // eax
  unsigned int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !CDesktopManager::IsWindowAnimationEnabled() )
    AssertW(
      0,
      L"CDesktopManager::IsWindowAnimationEnabled()",
      L"CCompositionEffectCache::EnsureCrossFadeEffectInitialized",
      L"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
      0x71u);
  if ( !*((_QWORD *)this + 8) )
  {
    v2 = *(_QWORD *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 40LL);
    *((_QWORD *)this + 8) = 0;
    CrossfadeEffectFactory = CreateCrossfadeEffectFactory(v2);
    if ( CrossfadeEffectFactory < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)CrossfadeEffectFactory,
        v4);
  }
}

```

## disassembly

```asm
0x18003b038  push    rbx
0x18003b03a  sub     rsp, 30h
0x18003b03e  mov     rbx, rcx
0x18003b041  call    ?IsWindowAnimationEnabled@CDesktopManager@@SA_NXZ; CDesktopManager::IsWindowAnimationEnabled(void)
0x18003b046  test    al, al
0x18003b048  jz      short loc_18003B07A
0x18003b04a  lea     rdx, [rbx+40h]
0x18003b04e  cmp     qword ptr [rdx], 0
0x18003b052  jnz     short loc_18003B074
0x18003b054  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003b05b  mov     rcx, [rax+30h]
0x18003b05f  mov     rcx, [rcx+28h]
0x18003b063  mov     qword ptr [rdx], 0
0x18003b06a  call    cs:__imp_CreateCrossfadeEffectFactory
0x18003b070  test    eax, eax
0x18003b072  js      short loc_18003B0A0
0x18003b074  add     rsp, 30h
0x18003b078  pop     rbx
0x18003b079  retn
0x18003b07a  mov     [rsp+38h+var_18], 71h ; 'q'; unsigned int
0x18003b082  lea     r9, aClientcoreWind; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18003b089  lea     r8, aCcompositionef_0; "CCompositionEffectCache::EnsureCrossFad"...
0x18003b090  lea     rdx, aCdesktopmanage; "CDesktopManager::IsWindowAnimationEnabl"...
0x18003b097  xor     ecx, ecx; unsigned __int16 *
0x18003b099  call    ?AssertW@@YAXPEBG000K@Z; AssertW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18003b09e  jmp     short loc_18003B04A
0x18003b0a0  mov     rcx, [rsp+38h]; this
0x18003b0a5  mov     r9d, eax; char *
0x18003b0a8  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18003b0af  mov     edx, 77h ; 'w'; void *
0x18003b0b4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
