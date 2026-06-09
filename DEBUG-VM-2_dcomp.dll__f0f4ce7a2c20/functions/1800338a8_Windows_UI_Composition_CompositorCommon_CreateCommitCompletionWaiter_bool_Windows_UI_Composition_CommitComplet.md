# Windows::UI::Composition::CompositorCommon::CreateCommitCompletionWaiter(bool,Windows::UI::Composition::CommitCompletionWaiter * *)

- ea: `0x1800338a8`
- end: `0x180033b5a`
- name: `?CreateCommitCompletionWaiter@CompositorCommon@Composition@UI@Windows@@QEAAJ_NPEAPEAVCommitCompletionWaiter@234@@Z`
- size: `690`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositorCommon *__hidden this, bool, struct Windows::UI::Composition::CommitCompletionWaiter **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180031e10`
- `0x1800b5810`

## callees

- `0x18000f810`
- `0x18001358c`
- `0x180014e80`
- `0x180033844`
- `0x1800338a8`
- `0x1800348d0`
- `0x180039590`
- `0x1800ced64`
- `0x1800e55cc`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033ad7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033ad7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033a4b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033b3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033b3f`

## string_xrefs

- `0x180033945`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x180033a80`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x180033aee`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositorCommon::CreateCommitCompletionWaiter(
        Windows::UI::Composition::CompositorCommon *this,
        char a2,
        struct Windows::UI::Composition::CommitCompletionWaiter **a3)
{
  unsigned int v6; // r14d
  void *v7; // rax
  Windows::UI::Composition::CommitCompletionWaiter *v8; // rax
  __int64 v9; // rbx
  int v10; // esi
  char v12; // bp
  __int64 i; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  HANDLE EventW; // rax
  const char *v17; // r9
  unsigned int LastError; // edi
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = *(_DWORD *)(*((_QWORD *)this + 55) + 388LL) - 1;
  if ( !a2 )
    v6 = *(_DWORD *)(*((_QWORD *)this + 55) + 388LL);
  v7 = DefaultHeap::Alloc(0xF0u);
  if ( !v7 )
  {
    v10 = -2147024882;
    goto LABEL_8;
  }
  v8 = (Windows::UI::Composition::CommitCompletionWaiter *)memset_0(v7, 0, 0xF0u);
  if ( v8 )
    v9 = Windows::UI::Composition::CommitCompletionWaiter::CommitCompletionWaiter(v8);
  else
    v9 = 0;
  *(_DWORD *)(v9 + 192) = v6;
  *(_QWORD *)(v9 + 8) = &Windows::UI::Composition::CommitCompletionWaiter::s_InterfaceType;
  v10 = Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(
          (Windows::UI::Composition::CompositionObject *)v9,
          this);
  if ( v10 < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD65,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      (const char *)(unsigned int)v10,
      v19);
    return (unsigned int)v10;
  }
  if ( *((_QWORD *)this + 126) )
    goto LABEL_11;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 126) = EventW;
  if ( EventW )
  {
    v10 = DirectComposition::CDevice::SetCommitCompletionEvent(*((DirectComposition::CDevice **)this + 55), EventW, 0);
    if ( v10 < 0 )
    {
      CloseHandle(*((HANDLE *)this + 126));
      v15 = 3448;
      *((_QWORD *)this + 126) = 0;
      goto LABEL_29;
    }
LABEL_11:
    v12 = *((_BYTE *)this + 1016) & 1;
    if ( v12 )
      goto LABEL_12;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), Windows::UI::Composition::CompositorCommon *))(**(_QWORD **)(*((_QWORD *)this + 55) + 648LL) + 272LL))(
            *(_QWORD *)(*((_QWORD *)this + 55) + 648LL),
            *((_QWORD *)this + 126),
            Windows::UI::Composition::CompositorCommon::CommitCompletionCallback,
            this);
    if ( v10 >= 0 )
    {
      *((_BYTE *)this + 1016) |= 1u;
LABEL_12:
      for ( i = *((_QWORD *)this + 125); i && *(_DWORD *)(i + 192) > v6; i = *(_QWORD *)(i + 176) )
        ;
      if ( i )
      {
        *(_QWORD *)(v9 + 184) = *(_QWORD *)(i + 184);
        *(_QWORD *)(i + 184) = v9;
      }
      else
      {
        *(_QWORD *)(v9 + 184) = *((_QWORD *)this + 124);
        *((_QWORD *)this + 124) = v9;
      }
      v14 = *(_QWORD *)(v9 + 184);
      *(_QWORD *)(v9 + 176) = i;
      if ( v14 )
        *(_QWORD *)(v14 + 176) = v9;
      else
        *((_QWORD *)this + 125) = v9;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      if ( a2 )
      {
        if ( !v12 )
          SetEvent(*((HANDLE *)this + 126));
      }
      else
      {
        Windows::UI::Composition::CompositorCommon::MarkDirty(this);
        *((_BYTE *)this + 1016) |= 2u;
      }
      *a3 = (struct Windows::UI::Composition::CommitCompletionWaiter *)v9;
      return 0;
    }
    v15 = 3458;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      (const char *)(unsigned int)v10,
      v19);
    if ( v9 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)v9);
    return (unsigned int)v10;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xD6F,
                (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
                v17);
  if ( v9 )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)v9);
  return LastError;
}

```

## disassembly

```asm
0x1800338a8  push    rbx
0x1800338aa  push    rbp
0x1800338ab  push    rsi
0x1800338ac  push    rdi
0x1800338ad  push    r12
0x1800338af  push    r14
0x1800338b1  push    r15
0x1800338b3  sub     rsp, 30h
0x1800338b7  mov     rax, [rcx+1B8h]
0x1800338be  test    dl, dl
0x1800338c0  mov     rdi, rcx
0x1800338c3  mov     ebx, 0F0h
0x1800338c8  mov     ecx, ebx; unsigned __int64
0x1800338ca  mov     r12, r8
0x1800338cd  mov     r15b, dl
0x1800338d0  mov     r9d, [rax+184h]
0x1800338d7  lea     r14d, [r9-1]
0x1800338db  cmovz   r14d, r9d
0x1800338df  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x1800338e4  test    rax, rax
0x1800338e7  jz      loc_180033A6C
0x1800338ed  mov     r8d, ebx; Size
0x1800338f0  xor     edx, edx; Val
0x1800338f2  mov     rcx, rax; void *
0x1800338f5  call    memset_0
0x1800338fa  test    rax, rax
0x1800338fd  jz      loc_180033B15
0x180033903  mov     rcx, rax; this
0x180033906  call    ??0CommitCompletionWaiter@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CommitCompletionWaiter::CommitCompletionWaiter(void)
0x18003390b  mov     rbx, rax
0x18003390e  lea     rax, ?s_InterfaceType@CommitCompletionWaiter@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::CommitCompletionWaiter::s_InterfaceType
0x180033915  mov     [rbx+0C0h], r14d
0x18003391c  mov     rdx, rdi; struct Windows::UI::Composition::Compositor *
0x18003391f  mov     [rbx+8], rax
0x180033923  mov     rcx, rbx; this
0x180033926  call    ?RuntimeClassInitialize@CompositionObject@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z; Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)
0x18003392b  mov     esi, eax
0x18003392d  test    eax, eax
0x18003392f  jns     short loc_18003396A
0x180033931  mov     rcx, [rbx]
0x180033934  mov     rax, [rcx+10h]
0x180033938  mov     rcx, rbx
0x18003393b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033940  mov     rcx, [rsp+68h]; this
0x180033945  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18003394c  mov     r9d, esi; char *
0x18003394f  mov     edx, 0D65h; void *
0x180033954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033959  mov     eax, esi
0x18003395b  add     rsp, 30h
0x18003395f  pop     r15
0x180033961  pop     r14
0x180033963  pop     r12
0x180033965  pop     rdi
0x180033966  pop     rsi
0x180033967  pop     rbp
0x180033968  pop     rbx
0x180033969  retn
0x18003396a  cmp     qword ptr [rdi+3F0h], 0
0x180033972  jz      loc_180033ACB
0x180033978  mov     bpl, [rdi+3F8h]
0x18003397f  and     bpl, 1
0x180033983  jz      short loc_1800339FF
0x180033985  mov     rcx, [rdi+3E8h]
0x18003398c  test    rcx, rcx
0x18003398f  jnz     loc_180033A53
0x180033995  test    rcx, rcx
0x180033998  jnz     loc_180033AA5
0x18003399e  mov     rax, [rdi+3E0h]
0x1800339a5  mov     [rbx+0B8h], rax
0x1800339ac  mov     [rdi+3E0h], rbx
0x1800339b3  mov     rax, [rbx+0B8h]
0x1800339ba  mov     [rbx+0B0h], rcx
0x1800339c1  test    rax, rax
0x1800339c4  jnz     loc_180033ABF
0x1800339ca  mov     [rdi+3E8h], rbx
0x1800339d1  mov     rax, [rbx]
0x1800339d4  mov     rcx, rbx
0x1800339d7  mov     rax, [rax+8]
0x1800339db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339e0  test    r15b, r15b
0x1800339e3  jnz     short loc_180033A3F
0x1800339e5  mov     rcx, rdi; this
0x1800339e8  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x1800339ed  or      byte ptr [rdi+3F8h], 2
0x1800339f4  mov     [r12], rbx
0x1800339f8  xor     eax, eax
0x1800339fa  jmp     loc_18003395B
0x1800339ff  mov     rax, [rdi+1B8h]
0x180033a06  lea     r8, ?CommitCompletionCallback@CompositorCommon@Composition@UI@Windows@@CAJPEAXK0@Z; Windows::UI::Composition::CompositorCommon::CommitCompletionCallback(void *,ulong,void *)
0x180033a0d  mov     rdx, [rdi+3F0h]
0x180033a14  mov     r9, rdi
0x180033a17  mov     rcx, [rax+288h]
0x180033a1e  mov     rax, [rcx]
0x180033a21  mov     rax, [rax+110h]
0x180033a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a2d  mov     esi, eax
0x180033a2f  test    eax, eax
0x180033a31  js      short loc_180033A76
0x180033a33  or      byte ptr [rdi+3F8h], 1
0x180033a3a  jmp     loc_180033985
0x180033a3f  test    bpl, bpl
0x180033a42  jnz     short loc_1800339F4
0x180033a44  mov     rcx, [rdi+3F0h]; hEvent
0x180033a4b  call    cs:__imp_SetEvent
0x180033a51  jmp     short loc_1800339F4
0x180033a53  cmp     [rcx+0C0h], r14d
0x180033a5a  jbe     loc_180033995
0x180033a60  mov     rcx, [rcx+0B0h]
0x180033a67  jmp     loc_18003398C
0x180033a6c  mov     esi, 8007000Eh
0x180033a71  jmp     loc_180033940
0x180033a76  mov     edx, 0D82h; void *
0x180033a7b  mov     rcx, [rsp+68h]; this
0x180033a80  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180033a87  mov     r9d, esi; char *
0x180033a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a8f  test    rbx, rbx
0x180033a92  jz      loc_180033959
0x180033a98  mov     rcx, rbx; this
0x180033a9b  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180033aa0  jmp     loc_180033959
0x180033aa5  mov     rax, [rcx+0B8h]
0x180033aac  mov     [rbx+0B8h], rax
0x180033ab3  mov     [rcx+0B8h], rbx
0x180033aba  jmp     loc_1800339B3
0x180033abf  mov     [rax+0B0h], rbx
0x180033ac6  jmp     loc_1800339D1
0x180033acb  xor     r9d, r9d; lpName
0x180033ace  xor     r8d, r8d; bInitialState
0x180033ad1  xor     ecx, ecx; lpEventAttributes
0x180033ad3  lea     edx, [r9+1]; bManualReset
0x180033ad7  call    cs:__imp_CreateEventW
0x180033add  mov     [rdi+3F0h], rax
0x180033ae4  test    rax, rax
0x180033ae7  jnz     short loc_180033B1C
0x180033ae9  mov     rcx, [rsp+68h]; this
0x180033aee  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180033af5  mov     edx, 0D6Fh; void *
0x180033afa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033aff  mov     edi, eax
0x180033b01  test    rbx, rbx
0x180033b04  jz      short loc_180033B0E
0x180033b06  mov     rcx, rbx; this
0x180033b09  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180033b0e  mov     eax, edi
0x180033b10  jmp     loc_18003395B
0x180033b15  xor     ebx, ebx
0x180033b17  jmp     loc_18003390E
0x180033b1c  mov     rcx, [rdi+1B8h]; this
0x180033b23  xor     r8d, r8d; bool
0x180033b26  mov     rdx, rax; void *
0x180033b29  call    ?SetCommitCompletionEvent@CDevice@DirectComposition@@QEAAJPEAX_N@Z; DirectComposition::CDevice::SetCommitCompletionEvent(void *,bool)
0x180033b2e  mov     esi, eax
0x180033b30  test    eax, eax
0x180033b32  jns     loc_180033978
0x180033b38  mov     rcx, [rdi+3F0h]; hObject
0x180033b3f  call    cs:__imp_CloseHandle
0x180033b45  mov     edx, 0D78h
0x180033b4a  mov     qword ptr [rdi+3F0h], 0
0x180033b55  jmp     loc_180033A7B
```
