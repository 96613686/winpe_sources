# Windows::UI::Composition::KeyFrameAnimation::RuntimeClassInitialize(Windows::UI::Composition::Compositor *,DCOMPOSITION_EXPRESSION_TYPE)

- ea: `0x1800397bc`
- end: `0x18003994b`
- name: `?RuntimeClassInitialize@KeyFrameAnimation@Composition@UI@Windows@@QEAAJPEAVCompositor@234@W4DCOMPOSITION_EXPRESSION_TYPE@@@Z`
- size: `399`
- prototype: `int __high(struct Windows::UI::Composition::Compositor *, enum DCOMPOSITION_EXPRESSION_TYPE)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180035640`
- `0x1800a8c4c`
- `0x1800ab13c`
- `0x1800abe6c`
- `0x1800b10cc`
- `0x1800b92e8`
- `0x180120ed8`
- `0x180121810`

## callees

- `0x18000f850`
- `0x180012da0`
- `0x18001358c`
- `0x180036f90`
- `0x180039590`
- `0x1800397bc`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003983e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003983e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180039884`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180039884`

## string_xrefs

- `0x180039876`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180039912`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x18003992b`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimation.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::KeyFrameAnimation::RuntimeClassInitialize(__int64 a1, __int64 a2, int a3)
{
  int v5; // ebx
  Microsoft::WRL2::ContextSession *v6; // rcx
  _QWORD *v7; // r8
  char v8; // al
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 2500000;
  *(_DWORD *)(a1 + 432) = a3;
  *(_QWORD *)(a1 + 480) = 0;
  *(_DWORD *)(a1 + 476) = 0;
  *(_DWORD *)(a1 + 488) = 1065353216;
  *(_DWORD *)(a1 + 500) = 0;
  *(_QWORD *)(a1 + 24) = a2;
  if ( a2 == a1 )
    goto LABEL_10;
  Microsoft::WRL2::NestableRuntimeClass::InternalAddRef((Microsoft::WRL2::NestableRuntimeClass *)a2);
  v5 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + 56LL) + 40LL);
  if ( v5 == GetCurrentThreadId() )
  {
    v6 = 0;
  }
  else
  {
    Microsoft::WRL2::ContextSession::BeginApiEntry(*(Microsoft::WRL2::ContextSession **)(a2 + 24));
    v6 = *(Microsoft::WRL2::ContextSession **)(a2 + 24);
    if ( (*(_BYTE *)(a2 + 48) & 2) == 0 )
    {
      Microsoft::WRL2::ContextSession::EndApiEntry(v6);
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
      goto LABEL_10;
    }
  }
  v7 = *(_QWORD **)(a2 + 40);
  if ( *v7 != a2 + 32 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 32) = a2 + 32;
  *(_QWORD *)(a1 + 40) = v7;
  *v7 = a1 + 32;
  *(_QWORD *)(a2 + 40) = a1 + 32;
  if ( v6 )
    Microsoft::WRL2::ContextSession::EndApiEntry(v6);
LABEL_10:
  v8 = *(_BYTE *)(a1 + 49);
  *(_BYTE *)(a1 + 48) = 31;
  *(_BYTE *)(a1 + 49) ^= (*(_BYTE *)(a2 + 49) ^ v8) & 1;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a2 + 408) + 32LL) + 24LL))(
         *(_QWORD *)(*(_QWORD *)(a2 + 408) + 32LL),
         *(unsigned int *)(*(_QWORD *)(a2 + 408) + 64LL),
         a1,
         a1 + 136);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v9,
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimation.cpp",
      (const char *)v10,
      v13);
  }
  else
  {
    Windows::UI::Composition::CompositorCommon::MarkDirty((Windows::UI::Composition::CompositorCommon *)a2);
    *(_DWORD *)(a1 + 140) |= 1u;
    v10 = 0;
    *(_DWORD *)(a1 + 312) = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x1800397bc  mov     [rsp+arg_0], rbx
0x1800397c1  mov     [rsp+arg_8], rsi
0x1800397c6  push    rdi
0x1800397c7  sub     rsp, 30h
0x1800397cb  mov     qword ptr [rcx+1B8h], 0
0x1800397d6  mov     rsi, rdx
0x1800397d9  mov     qword ptr [rcx+1C0h], 0
0x1800397e4  mov     rdi, rcx
0x1800397e7  mov     qword ptr [rcx+1C8h], 2625A0h
0x1800397f2  mov     [rcx+1B0h], r8d
0x1800397f9  mov     qword ptr [rcx+1E0h], 0
0x180039804  mov     dword ptr [rcx+1DCh], 0
0x18003980e  mov     dword ptr [rcx+1E8h], 3F800000h
0x180039818  mov     dword ptr [rcx+1F4h], 0
0x180039822  mov     [rcx+18h], rdx
0x180039826  cmp     rdx, rcx
0x180039829  jz      short loc_1800398A7
0x18003982b  mov     rcx, rdx; this
0x18003982e  call    ?InternalAddRef@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(void)
0x180039833  mov     rax, [rsi+18h]
0x180039837  mov     rcx, [rax+38h]
0x18003983b  mov     ebx, [rcx+28h]
0x18003983e  call    cs:__imp_GetCurrentThreadId
0x180039844  cmp     ebx, eax
0x180039846  jnz     short loc_18003985E
0x180039848  xor     ecx, ecx; this
0x18003984a  lea     rdx, [rsi+20h]
0x18003984e  mov     r8, [rdx+8]
0x180039852  cmp     [r8], rdx
0x180039855  jz      short loc_18003988C
0x180039857  mov     ecx, 3
0x18003985c  int     29h; Win8: RtlFailFast(ecx)
0x18003985e  mov     rcx, [rsi+18h]; this
0x180039862  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180039867  test    byte ptr [rsi+30h], 2
0x18003986b  mov     rcx, [rsi+18h]; this
0x18003986f  jnz     short loc_18003984A
0x180039871  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180039876  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18003987d  xor     edx, edx
0x18003987f  mov     ecx, 80000013h
0x180039884  call    cs:__imp_RoOriginateErrorW
0x18003988a  jmp     short loc_1800398A7
0x18003988c  lea     rax, [rdi+20h]
0x180039890  mov     [rax], rdx
0x180039893  mov     [rax+8], r8
0x180039897  mov     [r8], rax
0x18003989a  mov     [rdx+8], rax
0x18003989e  test    rcx, rcx
0x1800398a1  jnz     loc_180039941
0x1800398a7  mov     al, [rdi+31h]
0x1800398aa  lea     r9, [rdi+88h]
0x1800398b1  mov     byte ptr [rdi+30h], 1Fh
0x1800398b5  mov     r8, rdi
0x1800398b8  xor     al, [rsi+31h]
0x1800398bb  and     al, 1
0x1800398bd  xor     [rdi+31h], al
0x1800398c0  mov     rdx, [rsi+198h]
0x1800398c7  mov     rcx, [rdx+20h]
0x1800398cb  mov     edx, [rdx+40h]
0x1800398ce  mov     rax, [rcx]
0x1800398d1  mov     rax, [rax+18h]
0x1800398d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398da  mov     ebx, eax
0x1800398dc  test    eax, eax
0x1800398de  js      short loc_18003990D
0x1800398e0  mov     rcx, rsi; this
0x1800398e3  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x1800398e8  or      dword ptr [rdi+8Ch], 1
0x1800398ef  xor     ebx, ebx
0x1800398f1  mov     dword ptr [rdi+138h], 1
0x1800398fb  mov     rsi, [rsp+38h+arg_8]
0x180039900  mov     eax, ebx
0x180039902  mov     rbx, [rsp+38h+arg_0]
0x180039907  add     rsp, 30h
0x18003990b  pop     rdi
0x18003990c  retn
0x18003990d  mov     rcx, [rsp+38h]; this
0x180039912  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180039919  mov     r9d, ebx; char *
0x18003991c  mov     edx, 55h ; 'U'; void *
0x180039921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039926  mov     rcx, [rsp+38h]; this
0x18003992b  lea     r8, aOnecoreuapWind_155; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180039932  mov     r9d, ebx; char *
0x180039935  mov     edx, 3Dh ; '='; void *
0x18003993a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003993f  jmp     short loc_1800398FB
0x180039941  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180039946  jmp     loc_1800398A7
```
