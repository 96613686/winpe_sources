# Windows::UI::Composition::InteropVisual::Api::GetVisualCollection(Windows::UI::Composition::IVisualCollection * *)

- ea: `0x1800392b0`
- end: `0x18003957f`
- name: `?GetVisualCollection@Api@InteropVisual@Composition@UI@Windows@@UEAAJPEAPEAUIVisualCollection@345@@Z`
- size: `719`
- prototype: `__int64 __fastcall(Windows::UI::Composition::InteropVisual::Api *__hidden this, struct Windows::UI::Composition::IVisualCollection **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000f810`
- `0x180010f00`
- `0x180012da0`
- `0x180013528`
- `0x18001358c`
- `0x180036f90`
- `0x1800392b0`
- `0x180039590`
- `0x1800e77ac`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800392e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800392e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003932c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003932c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393d5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003941c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180039432`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003941c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180039432`

## string_xrefs

- `0x18003940e`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180039424`: `The given object has already been closed / disposed and may no longer be used.`
- `0x1800394e4`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::InteropVisual::Api::GetVisualCollection(
        Windows::UI::Composition::InteropVisual::Api *this,
        struct Windows::UI::Composition::IVisualCollection **a2)
{
  volatile signed __int32 *v2; // r14
  __int64 v3; // rbx
  int v6; // ecx
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  Windows::UI::Composition::VisualCollection *v9; // rax
  __int64 v10; // rsi
  Microsoft::WRL2::NestableRuntimeClass *v11; // rcx
  __int64 v12; // r14
  int v13; // edi
  Microsoft::WRL2::ContextSession *v14; // rcx
  _QWORD *v15; // r8
  char v17; // al
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rcx
  struct Windows::UI::Composition::IVisualCollection *v21; // rcx
  unsigned int v22; // edx
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a2 = 0;
  v2 = (volatile signed __int32 *)((char *)this - 336);
  v3 = *((_QWORD *)this - 39);
  if ( *(_DWORD *)(v3 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
  v6 = *(_DWORD *)(v3 + 64);
  if ( v6 != *(_DWORD *)(v3 + 68) + *(_DWORD *)(v3 + 72) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v3 + 64) = v6 + 1;
  if ( (v2[12] & 2) == 0 )
  {
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v3);
    return 2147483667LL;
  }
  if ( *((_BYTE *)this + 24) )
  {
    v19 = -2147024891;
    v22 = 721;
    goto LABEL_33;
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, 0xB0u);
  if ( v8 )
  {
    v9 = (Windows::UI::Composition::VisualCollection *)memset_0(v8, 0, 0xB0u);
    if ( v9 )
      v10 = Windows::UI::Composition::VisualCollection::VisualCollection(v9);
    else
      v10 = 0;
    *(_QWORD *)(v10 + 8) = &Windows::UI::Composition::VisualCollection::s_InterfaceType;
    if ( *(volatile signed __int32 **)(v10 + 168) != v2 )
    {
      if ( v2 && _InterlockedIncrement(v2 + 4) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 80LL))(v2);
      v11 = *(Microsoft::WRL2::NestableRuntimeClass **)(v10 + 168);
      *(_QWORD *)(v10 + 168) = v2;
      if ( v11 )
        Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v11);
    }
    v12 = *((_QWORD *)v2 + 3);
    *(_QWORD *)(v10 + 24) = v12;
    if ( v12 == v10 )
      goto LABEL_26;
    if ( _InterlockedIncrement((volatile signed __int32 *)(v12 + 16)) == 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 80LL))(v12);
    v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 24) + 56LL) + 40LL);
    if ( v13 == GetCurrentThreadId() )
    {
      v14 = 0;
    }
    else
    {
      Microsoft::WRL2::ContextSession::BeginApiEntry(*(Microsoft::WRL2::ContextSession **)(v12 + 24));
      v14 = *(Microsoft::WRL2::ContextSession **)(v12 + 24);
      if ( (*(_BYTE *)(v12 + 48) & 2) == 0 )
      {
        Microsoft::WRL2::ContextSession::EndApiEntry(v14);
        RoOriginateErrorW(
          2147483667LL,
          0,
          L"The given object has already been closed / disposed and may no longer be used.");
LABEL_26:
        v17 = *(_BYTE *)(v10 + 49);
        *(_BYTE *)(v10 + 48) = 31;
        *(_BYTE *)(v10 + 49) ^= (*(_BYTE *)(v12 + 49) ^ v17) & 1;
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(v12 + 408) + 32LL)
                                                                          + 24LL))(
                *(_QWORD *)(*(_QWORD *)(v12 + 408) + 32LL),
                *(unsigned int *)(*(_QWORD *)(v12 + 408) + 64LL),
                v10,
                v10 + 136);
        v19 = v18;
        if ( v18 >= 0 )
        {
          Windows::UI::Composition::CompositorCommon::MarkDirty((Windows::UI::Composition::CompositorCommon *)v12);
          *(_DWORD *)(v10 + 140) |= 1u;
          v20 = (v10 + 144) & -(__int64)(v10 != 0);
          if ( v20 )
            v21 = (struct Windows::UI::Composition::IVisualCollection *)(v20 + 8);
          else
            v21 = 0;
          *a2 = v21;
          v19 = 0;
          goto LABEL_30;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
          (const char *)(unsigned int)v18,
          v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_32;
      }
    }
    v15 = *(_QWORD **)(v12 + 40);
    if ( *v15 != v12 + 32 )
      __fastfail(3u);
    *(_QWORD *)(v10 + 32) = v12 + 32;
    *(_QWORD *)(v10 + 40) = v15;
    *v15 = v10 + 32;
    *(_QWORD *)(v12 + 40) = v10 + 32;
    if ( v14 )
      Microsoft::WRL2::ContextSession::EndApiEntry(v14);
    goto LABEL_26;
  }
  v19 = -2147024882;
LABEL_32:
  v22 = 725;
LABEL_33:
  DoStackCaptureDirect(v19, v22);
LABEL_30:
  Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v3);
  return v19;
}

```

## disassembly

```asm
0x1800392b0  push    rbx
0x1800392b2  push    rsi
0x1800392b3  push    rdi
0x1800392b4  push    r14
0x1800392b6  push    r15
0x1800392b8  sub     rsp, 30h
0x1800392bc  mov     qword ptr [rdx], 0
0x1800392c3  lea     r14, [rcx-150h]
0x1800392ca  mov     rbx, [r14+18h]
0x1800392ce  mov     r15, rdx
0x1800392d1  mov     rdi, rcx
0x1800392d4  mov     eax, [rbx+5Ch]
0x1800392d7  test    eax, eax
0x1800392d9  jnz     loc_180039561
0x1800392df  mov     rcx, [rbx+38h]
0x1800392e3  add     rcx, 18h; lpCriticalSection
0x1800392e7  call    cs:__imp_EnterCriticalSection
0x1800392ed  mov     eax, [rbx+48h]
0x1800392f0  add     eax, [rbx+44h]
0x1800392f3  mov     ecx, [rbx+40h]
0x1800392f6  cmp     ecx, eax
0x1800392f8  jnz     loc_180039554
0x1800392fe  lea     eax, [rcx+1]
0x180039301  mov     [rbx+40h], eax
0x180039304  test    byte ptr [r14+30h], 2
0x180039309  jz      loc_180039424
0x18003930f  cmp     byte ptr [rdi+18h], 0
0x180039313  jnz     loc_180039520
0x180039319  call    cs:__imp_GetProcessHeap
0x18003931f  mov     edi, 0B0h
0x180039324  xor     edx, edx; dwFlags
0x180039326  mov     rcx, rax; hHeap
0x180039329  mov     r8d, edi; dwBytes
0x18003932c  call    cs:__imp_HeapAlloc
0x180039332  test    rax, rax
0x180039335  jz      loc_18003956E
0x18003933b  mov     r8d, edi; Size
0x18003933e  xor     edx, edx; Val
0x180039340  mov     rcx, rax; void *
0x180039343  call    memset_0
0x180039348  test    rax, rax
0x18003934b  jz      loc_180039519
0x180039351  mov     rcx, rax; this
0x180039354  call    ??0VisualCollection@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::VisualCollection::VisualCollection(void)
0x180039359  mov     rsi, rax
0x18003935c  lea     rax, ?s_InterfaceType@VisualCollection@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::VisualCollection::s_InterfaceType
0x180039363  mov     [rsi+8], rax
0x180039367  cmp     [rsi+0A8h], r14
0x18003936e  jz      short loc_1800393A3
0x180039370  test    r14, r14
0x180039373  jz      short loc_18003938B
0x180039375  mov     eax, 1
0x18003937a  lock xadd [r14+10h], eax
0x180039380  inc     eax
0x180039382  cmp     eax, 1
0x180039385  jz      loc_18003952C
0x18003938b  mov     rcx, [rsi+0A8h]; this
0x180039392  mov     [rsi+0A8h], r14
0x180039399  test    rcx, rcx
0x18003939c  jz      short loc_1800393A3
0x18003939e  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800393a3  mov     r14, [r14+18h]
0x1800393a7  mov     [rsi+18h], r14
0x1800393ab  cmp     r14, rsi
0x1800393ae  jz      loc_180039465
0x1800393b4  mov     eax, 1
0x1800393b9  lock xadd [r14+10h], eax
0x1800393bf  inc     eax
0x1800393c1  cmp     eax, 1
0x1800393c4  jz      loc_180039540
0x1800393ca  mov     rax, [r14+18h]
0x1800393ce  mov     rcx, [rax+38h]
0x1800393d2  mov     edi, [rcx+28h]
0x1800393d5  call    cs:__imp_GetCurrentThreadId
0x1800393db  cmp     edi, eax
0x1800393dd  jnz     short loc_1800393F5
0x1800393df  xor     ecx, ecx; this
0x1800393e1  lea     rdx, [r14+20h]
0x1800393e5  mov     r8, [rdx+8]
0x1800393e9  cmp     [r8], rdx
0x1800393ec  jz      short loc_18003944A
0x1800393ee  mov     ecx, 3
0x1800393f3  int     29h; Win8: RtlFailFast(ecx)
0x1800393f5  mov     rcx, [r14+18h]; this
0x1800393f9  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1800393fe  test    byte ptr [r14+30h], 2
0x180039403  mov     rcx, [r14+18h]; this
0x180039407  jnz     short loc_1800393E1
0x180039409  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18003940e  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180039415  xor     edx, edx
0x180039417  mov     ecx, 80000013h
0x18003941c  call    cs:__imp_RoOriginateErrorW
0x180039422  jmp     short loc_180039465
0x180039424  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18003942b  xor     edx, edx
0x18003942d  mov     ecx, 80000013h
0x180039432  call    cs:__imp_RoOriginateErrorW
0x180039438  mov     rcx, rbx; this
0x18003943b  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180039440  mov     eax, 80000013h
0x180039445  jmp     loc_1800394D3
0x18003944a  lea     rax, [rsi+20h]
0x18003944e  mov     [rax], rdx
0x180039451  mov     [rax+8], r8
0x180039455  mov     [r8], rax
0x180039458  mov     [rdx+8], rax
0x18003945c  test    rcx, rcx
0x18003945f  jnz     loc_180039575
0x180039465  mov     al, [rsi+31h]
0x180039468  lea     r9, [rsi+88h]
0x18003946f  mov     byte ptr [rsi+30h], 1Fh
0x180039473  mov     r8, rsi
0x180039476  xor     al, [r14+31h]
0x18003947a  and     al, 1
0x18003947c  xor     [rsi+31h], al
0x18003947f  mov     rdx, [r14+198h]
0x180039486  mov     rcx, [rdx+20h]
0x18003948a  mov     edx, [rdx+40h]
0x18003948d  mov     rax, [rcx]
0x180039490  mov     rax, [rax+18h]
0x180039494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039499  mov     edi, eax
0x18003949b  test    eax, eax
0x18003949d  js      short loc_1800394DF
0x18003949f  mov     rcx, r14; this
0x1800394a2  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x1800394a7  or      dword ptr [rsi+8Ch], 1
0x1800394ae  lea     rax, [rsi+90h]
0x1800394b5  neg     rsi
0x1800394b8  sbb     rcx, rcx
0x1800394bb  and     rcx, rax
0x1800394be  jz      short loc_180039515
0x1800394c0  add     rcx, 8
0x1800394c4  mov     [r15], rcx
0x1800394c7  xor     edi, edi
0x1800394c9  mov     rcx, rbx; this
0x1800394cc  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800394d1  mov     eax, edi
0x1800394d3  add     rsp, 30h
0x1800394d7  pop     r15
0x1800394d9  pop     r14
0x1800394db  pop     rdi
0x1800394dc  pop     rsi
0x1800394dd  pop     rbx
0x1800394de  retn
0x1800394df  mov     rcx, [rsp+58h]; this
0x1800394e4  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800394eb  mov     r9d, eax; char *
0x1800394ee  mov     edx, 55h ; 'U'; void *
0x1800394f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394f8  mov     rax, [rsi]
0x1800394fb  mov     rcx, rsi
0x1800394fe  mov     rax, [rax+10h]
0x180039502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039507  mov     edx, 2D5h; unsigned int
0x18003950c  mov     ecx, edi; int
0x18003950e  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180039513  jmp     short loc_1800394C9
0x180039515  xor     ecx, ecx
0x180039517  jmp     short loc_1800394C4
0x180039519  xor     esi, esi
0x18003951b  jmp     loc_18003935C
0x180039520  mov     edi, 80070005h
0x180039525  mov     edx, 2D1h
0x18003952a  jmp     short loc_18003950C
0x18003952c  mov     rax, [r14]
0x18003952f  mov     rcx, r14
0x180039532  mov     rax, [rax+50h]
0x180039536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003953b  jmp     loc_18003938B
0x180039540  mov     rax, [r14]
0x180039543  mov     rcx, r14
0x180039546  mov     rax, [rax+50h]
0x18003954a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003954f  jmp     loc_1800393CA
0x180039554  lea     rcx, aContextsession; "ContextSession begin counts"
0x18003955b  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180039561  lea     rcx, aContextsession_0; "ContextSession RIP"
0x180039568  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18003956e  mov     edi, 8007000Eh
0x180039573  jmp     short loc_180039507
0x180039575  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18003957a  jmp     loc_180039465
```
