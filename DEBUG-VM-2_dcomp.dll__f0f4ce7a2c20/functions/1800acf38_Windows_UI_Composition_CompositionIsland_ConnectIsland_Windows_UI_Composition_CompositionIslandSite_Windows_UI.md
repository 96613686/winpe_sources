# Windows::UI::Composition::CompositionIsland::ConnectIsland(Windows::UI::Composition::CompositionIslandSite *,Windows::UI::Composition::CompositionIsland *)

- ea: `0x1800acf38`
- end: `0x1800ad07c`
- name: `?ConnectIsland@CompositionIsland@Composition@UI@Windows@@SAJPEAVCompositionIslandSite@234@PEAV1234@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct Windows::UI::Composition::CompositionIslandSite *, struct Windows::UI::Composition::CompositionIsland *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800acda0`

## callees

- `0x18002af9c`
- `0x180073388`
- `0x1800acf38`
- `0x1800ad138`
- `0x1800ad1c4`
- `0x1800f8e54`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800acf5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800acf5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad046`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acf62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acf62`

## string_xrefs

- `0x1800acf94`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`
- `0x1800ad06a`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`
- `0x1800acf80`: `Objects already connected.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionIsland::ConnectIsland(
        struct Windows::UI::Composition::CompositionIslandSite *a1,
        struct Windows::UI::Composition::CompositionIsland *a2)
{
  const char *v4; // r9
  __int64 v6; // rax
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = &Windows::UI::Composition::CompositionIsland::s_sharedLock;
  AcquireSRWLockExclusive(&Windows::UI::Composition::CompositionIsland::s_sharedLock);
  dword_1801E1458 = GetCurrentThreadId();
  if ( *((_DWORD *)a2 + 50) || *((_DWORD *)a1 + 49) )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x382,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
      (const char *)0x8007139FLL,
      (int)"Objects already connected.",
      v7);
    CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(&v9);
    return 2147947423LL;
  }
  else
  {
    if ( *((_BYTE *)a2 + 204) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
        v4);
    *((_DWORD *)a2 + 50) = 1;
    *((_DWORD *)a1 + 49) = 1;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionIslandSite>::operator=((char *)a2 + 232, a1);
    v6 = *((_QWORD *)a1 + 32);
    *((_QWORD *)a1 + 25) = a2;
    *((_QWORD *)a2 + 30) = v6;
    *((_QWORD *)a1 + 26) = *((_QWORD *)a2 + 60);
    (*(void (__fastcall **)(struct Windows::UI::Composition::CompositionIslandSite *))(*(_QWORD *)a1 + 272LL))(a1);
    *((_BYTE *)a2 + 376) = 0;
    Windows::UI::Composition::CompositionIslandSite::NotifyToIsland_ActualSizeChanged(a1, *((_QWORD *)a1 + 22));
    dword_1801E1458 = 0;
    ReleaseSRWLockExclusive(&Windows::UI::Composition::CompositionIsland::s_sharedLock);
    return 0;
  }
}

```

## disassembly

```asm
0x1800acf38  mov     [rsp+arg_0], rbx
0x1800acf3d  mov     [rsp+arg_10], rbp
0x1800acf42  push    rdi
0x1800acf43  sub     rsp, 30h
0x1800acf47  lea     rbp, ?s_sharedLock@CompositionIsland@Composition@UI@Windows@@2VCReadWriteLock@@A; CReadWriteLock Windows::UI::Composition::CompositionIsland::s_sharedLock
0x1800acf4e  mov     rdi, rcx
0x1800acf51  mov     rcx, rbp; SRWLock
0x1800acf54  mov     [rsp+38h+arg_8], rbp
0x1800acf59  mov     rbx, rdx
0x1800acf5c  call    cs:__imp_AcquireSRWLockExclusive
0x1800acf62  call    cs:__imp_GetCurrentThreadId
0x1800acf68  mov     cs:dword_1801E1458, eax
0x1800acf6e  cmp     dword ptr [rbx+0C8h], 0
0x1800acf75  jz      loc_1800AD053
0x1800acf7b  mov     rcx, [rsp+38h]; this
0x1800acf80  lea     rax, aObjectsAlready; "Objects already connected."
0x1800acf87  mov     ebx, 8007139Fh
0x1800acf8c  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800acf91  mov     r9d, ebx; char *
0x1800acf94  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800acf9b  mov     edx, 382h; void *
0x1800acfa0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800acfa5  lea     rcx, [rsp+38h+arg_8]
0x1800acfaa  call    ??1?$CWriteGuard@VCReadWriteLock@@@@QEAA@XZ; CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(void)
0x1800acfaf  mov     eax, ebx
0x1800acfb1  mov     rbx, [rsp+38h+arg_0]
0x1800acfb6  mov     rbp, [rsp+38h+arg_10]
0x1800acfbb  add     rsp, 30h
0x1800acfbf  pop     rdi
0x1800acfc0  retn
0x1800acfc1  cmp     byte ptr [rbx+0CCh], 0
0x1800acfc8  jnz     loc_1800AD065
0x1800acfce  mov     eax, 1
0x1800acfd3  lea     rcx, [rbx+0E8h]
0x1800acfda  mov     [rbx+0C8h], eax
0x1800acfe0  mov     rdx, rdi
0x1800acfe3  mov     [rdi+0C4h], eax
0x1800acfe9  call    ??4?$RefPtr@VCompositionIslandSite@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionIslandSite@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionIslandSite>::operator=(Windows::UI::Composition::CompositionIslandSite *)
0x1800acfee  mov     rax, [rdi+100h]
0x1800acff5  mov     rcx, rdi
0x1800acff8  mov     [rdi+0C8h], rbx
0x1800acfff  mov     [rbx+0F0h], rax
0x1800ad006  mov     rax, [rbx+1E0h]
0x1800ad00d  mov     [rdi+0D0h], rax
0x1800ad014  mov     rax, [rdi]
0x1800ad017  mov     rax, [rax+110h]
0x1800ad01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad023  mov     byte ptr [rbx+178h], 0
0x1800ad02a  mov     rcx, rdi
0x1800ad02d  mov     rdx, [rdi+0B0h]
0x1800ad034  call    ?NotifyToIsland_ActualSizeChanged@CompositionIslandSite@Composition@UI@Windows@@IEAAXUfloat2@Numerics@Foundation@4@@Z; Windows::UI::Composition::CompositionIslandSite::NotifyToIsland_ActualSizeChanged(Windows::Foundation::Numerics::float2)
0x1800ad039  mov     rcx, rbp; SRWLock
0x1800ad03c  mov     cs:dword_1801E1458, 0
0x1800ad046  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad04c  xor     eax, eax
0x1800ad04e  jmp     loc_1800ACFB1
0x1800ad053  cmp     dword ptr [rdi+0C4h], 0
0x1800ad05a  jnz     loc_1800ACF7B
0x1800ad060  jmp     loc_1800ACFC1
0x1800ad065  mov     rcx, [rsp+38h]; this
0x1800ad06a  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800ad071  mov     edx, 384h; void *
0x1800ad076  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
