# Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)

- ea: `0x180039138`
- end: `0x18003929b`
- name: `?RuntimeClassInitialize@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z`
- size: `355`
- prototype: `int(Windows::UI::Composition::CompositionAnimation *__hidden this, struct Windows::UI::Composition::Compositor *)`
- caller_count: `13`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800336e8`
- `0x180037da0`
- `0x1800afd98`
- `0x1800efc54`
- `0x18011fbf8`
- `0x18011fcec`
- `0x18011fde0`
- `0x180121434`
- `0x180121528`
- `0x18012161c`
- `0x18014c7e0`
- `0x18014d180`
- `0x18014d860`

## callees

- `0x180012da0`
- `0x18001358c`
- `0x180036f90`
- `0x180039138`
- `0x180039590`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003917a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003917a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800391c0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800391c0`

## string_xrefs

- `0x1800391b2`: `The given object has already been closed / disposed and may no longer be used.`
- `0x18003924c`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x180039265`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimation.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(
        Windows::UI::Composition::CompositionAnimation *this,
        struct Windows::UI::Composition::Compositor *a2)
{
  int v4; // ebx
  Microsoft::WRL2::ContextSession *v5; // rcx
  struct Windows::UI::Composition::Compositor **v6; // r8
  char v7; // al
  int v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-18h]
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_QWORD *)this + 3) = a2;
  if ( a2 == this )
    goto LABEL_12;
  if ( _InterlockedIncrement((volatile signed __int32 *)a2 + 4) == 1 )
    (*(void (__fastcall **)(struct Windows::UI::Composition::Compositor *))(*(_QWORD *)a2 + 80LL))(a2);
  v4 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 56LL) + 40LL);
  if ( v4 == GetCurrentThreadId() )
  {
    v5 = 0;
  }
  else
  {
    Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3));
    v5 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)a2 + 3);
    if ( (*((_BYTE *)a2 + 48) & 2) == 0 )
    {
      Microsoft::WRL2::ContextSession::EndApiEntry(v5);
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
      goto LABEL_12;
    }
  }
  v6 = (struct Windows::UI::Composition::Compositor **)*((_QWORD *)a2 + 5);
  if ( *v6 != (struct Windows::UI::Composition::Compositor *)((char *)a2 + 32) )
    __fastfail(3u);
  *((_QWORD *)this + 4) = (char *)a2 + 32;
  *((_QWORD *)this + 5) = v6;
  *v6 = (Windows::UI::Composition::CompositionAnimation *)((char *)this + 32);
  *((_QWORD *)a2 + 5) = (char *)this + 32;
  if ( v5 )
    Microsoft::WRL2::ContextSession::EndApiEntry(v5);
LABEL_12:
  v7 = *((_BYTE *)this + 49);
  *((_BYTE *)this + 48) = 31;
  *((_BYTE *)this + 49) ^= (*((_BYTE *)a2 + 49) ^ v7) & 1;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Windows::UI::Composition::CompositionAnimation *, char *))(**(_QWORD **)(*((_QWORD *)a2 + 51) + 32LL) + 24LL))(
         *(_QWORD *)(*((_QWORD *)a2 + 51) + 32LL),
         *(unsigned int *)(*((_QWORD *)a2 + 51) + 64LL),
         this,
         (char *)this + 136);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v8,
      v11);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimation.cpp",
      (const char *)v9,
      v12);
    return v9;
  }
  else
  {
    Windows::UI::Composition::CompositorCommon::MarkDirty(a2);
    *((_DWORD *)this + 35) |= 1u;
    result = 0;
    *((_DWORD *)this + 78) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180039138  mov     [rsp+arg_0], rbx
0x18003913d  mov     [rsp+arg_8], rsi
0x180039142  push    rdi
0x180039143  sub     rsp, 30h
0x180039147  mov     [rcx+18h], rdx
0x18003914b  mov     rdi, rdx
0x18003914e  mov     rsi, rcx
0x180039151  cmp     rdx, rcx
0x180039154  jz      loc_1800391E3
0x18003915a  mov     eax, 1
0x18003915f  lock xadd [rdx+10h], eax
0x180039164  inc     eax
0x180039166  cmp     eax, 1
0x180039169  jz      loc_18003927D
0x18003916f  mov     rax, [rdi+18h]
0x180039173  mov     rcx, [rax+38h]
0x180039177  mov     ebx, [rcx+28h]
0x18003917a  call    cs:__imp_GetCurrentThreadId
0x180039180  cmp     ebx, eax
0x180039182  jnz     short loc_18003919A
0x180039184  xor     ecx, ecx; this
0x180039186  lea     rdx, [rdi+20h]
0x18003918a  mov     r8, [rdx+8]
0x18003918e  cmp     [r8], rdx
0x180039191  jz      short loc_1800391C8
0x180039193  mov     ecx, 3
0x180039198  int     29h; Win8: RtlFailFast(ecx)
0x18003919a  mov     rcx, [rdi+18h]; this
0x18003919e  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1800391a3  test    byte ptr [rdi+30h], 2
0x1800391a7  mov     rcx, [rdi+18h]; this
0x1800391ab  jnz     short loc_180039186
0x1800391ad  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800391b2  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800391b9  xor     edx, edx
0x1800391bb  mov     ecx, 80000013h
0x1800391c0  call    cs:__imp_RoOriginateErrorW
0x1800391c6  jmp     short loc_1800391E3
0x1800391c8  lea     rax, [rsi+20h]
0x1800391cc  mov     [rax], rdx
0x1800391cf  mov     [rax+8], r8
0x1800391d3  mov     [r8], rax
0x1800391d6  mov     [rdx+8], rax
0x1800391da  test    rcx, rcx
0x1800391dd  jnz     loc_180039291
0x1800391e3  mov     al, [rsi+31h]
0x1800391e6  lea     r9, [rsi+88h]
0x1800391ed  mov     byte ptr [rsi+30h], 1Fh
0x1800391f1  mov     r8, rsi
0x1800391f4  xor     al, [rdi+31h]
0x1800391f7  and     al, 1
0x1800391f9  xor     [rsi+31h], al
0x1800391fc  mov     rdx, [rdi+198h]
0x180039203  mov     rcx, [rdx+20h]
0x180039207  mov     edx, [rdx+40h]
0x18003920a  mov     rax, [rcx]
0x18003920d  mov     rax, [rax+18h]
0x180039211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039216  mov     ebx, eax
0x180039218  test    eax, eax
0x18003921a  js      short loc_180039247
0x18003921c  mov     rcx, rdi; this
0x18003921f  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x180039224  or      dword ptr [rsi+8Ch], 1
0x18003922b  xor     eax, eax
0x18003922d  mov     dword ptr [rsi+138h], 1
0x180039237  mov     rbx, [rsp+38h+arg_0]
0x18003923c  mov     rsi, [rsp+38h+arg_8]
0x180039241  add     rsp, 30h
0x180039245  pop     rdi
0x180039246  retn
0x180039247  mov     rcx, [rsp+38h]; this
0x18003924c  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180039253  mov     r9d, ebx; char *
0x180039256  mov     edx, 55h ; 'U'; void *
0x18003925b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039260  mov     rcx, [rsp+38h]; this
0x180039265  lea     r8, aOnecoreuapWind_155; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18003926c  mov     r9d, ebx; char *
0x18003926f  mov     edx, 3Dh ; '='; void *
0x180039274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039279  mov     eax, ebx
0x18003927b  jmp     short loc_180039237
0x18003927d  mov     rax, [rdx]
0x180039280  mov     rcx, rdi
0x180039283  mov     rax, [rax+50h]
0x180039287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003928c  jmp     loc_18003916F
0x180039291  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180039296  jmp     loc_1800391E3
```
