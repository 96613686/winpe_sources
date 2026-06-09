# SlideshowModeControl::StartInternal(void)

- ea: `0x18003b7e0`
- end: `0x18003b9fe`
- name: `?StartInternal@SlideshowModeControl@@AEAAXXZ`
- size: `542`
- prototype: `void __fastcall(SlideshowModeControl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180058440`

## callees

- `0x18001f078`
- `0x18003b7e0`
- `0x180058350`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003b81c`
- `KERNEL32!GetLastError` at `0x18003b81c`
- `KERNEL32!CreateMutexW` at `0x18003b806`
- `KERNEL32!CreateMutexW` at `0x18003b806`
- `USER32!GetSystemMetrics` at `0x18003b86f`
- `USER32!GetSystemMetrics` at `0x18003b86f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b7f4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8a7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8c6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8e8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b907`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b92b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b94c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b971`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b996`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b9bb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b9f1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b7f4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8a7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8c6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b8e8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b907`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b92b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b94c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b971`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b996`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b9bb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b9f1`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003b816`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003b816`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18003b864`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18003b888`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18003b864`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18003b888`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SlideshowModeControl::StartInternal(SlideshowModeControl *this, int a2)
{
  Base *v3; // rcx
  unsigned int v4; // r8d
  SlideshowModeControl *v5; // rcx
  int SystemMetrics; // eax
  unsigned int v7; // r8d
  __int64 v8; // rcx
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  int v24; // edx
  int v25; // eax
  int v26; // edx
  int v27; // eax
  int v28; // edx
  int v29; // eax
  SlideshowModeControl *v30; // rcx
  unsigned __int16 ErrorString; // ax
  SlideshowModeControl *v32; // rcx
  _BYTE v33[24]; // [rsp+20h] [rbp-18h] BYREF
  HANDLE MutexW; // [rsp+40h] [rbp+8h] BYREF

  try
  {
    if ( !*((_BYTE *)this + 48) )
      Base::Throw((Base *)0x80004005LL, a2);
    MutexW = CreateMutexW(0, 0, L"WindowsPhotoGallerySlideshow");
    if ( !MutexW )
      Base::ThrowLastError(v3);
    if ( GetLastError() == 183 )
    {
      ATL::CHandle::Close((ATL::CHandle *)&MutexW);
      SlideshowModeControl::ShowErrorMessage(v5, 0x2B1Du, 0);
      ATL::CHandle::Close((ATL::CHandle *)&MutexW);
    }
    else
    {
      if ( !*((_BYTE *)this + 185) )
        Sqm::Increment((Sqm *)0x5E1, 1u, v4);
      SystemMetrics = GetSystemMetrics(4096);
      v8 = 1775;
      if ( !SystemMetrics )
        v8 = 1776;
      Sqm::Increment((Sqm *)v8, 1u, v7);
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 40LL))(*((_QWORD *)this + 18));
      if ( v9 < 0 )
        Base::Throw((Base *)(unsigned int)v9, v10);
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 48LL))(*((_QWORD *)this + 18));
      if ( v11 < 0 )
        Base::Throw((Base *)(unsigned int)v11, v12);
      v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 168LL))(*((_QWORD *)this + 17));
      if ( v13 < 0 )
        Base::Throw((Base *)(unsigned int)v13, v14);
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21));
      if ( v15 < 0 )
        Base::Throw((Base *)(unsigned int)v15, v16);
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 19) + 24LL))(*((_QWORD *)this + 19), 1);
      if ( v17 < 0 )
        Base::Throw((Base *)(unsigned int)v17, v18);
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 19) + 32LL))(*((_QWORD *)this + 19), 0);
      if ( v19 < 0 )
        Base::Throw((Base *)(unsigned int)v19, v20);
      LOBYTE(v20) = *((_BYTE *)this + 184);
      v21 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 20) + 32LL))(*((_QWORD *)this + 20), v20);
      if ( v21 < 0 )
        Base::Throw((Base *)(unsigned int)v21, v22);
      LOBYTE(v22) = *((_BYTE *)this + 185);
      v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 20) + 24LL))(*((_QWORD *)this + 20), v22);
      if ( v23 < 0 )
        Base::Throw((Base *)(unsigned int)v23, v24);
      v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 20) + 40LL))(
              *((_QWORD *)this + 20),
              *((unsigned int *)this + 47));
      if ( v25 < 0 )
        Base::Throw((Base *)(unsigned int)v25, v26);
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 64LL))(*((_QWORD *)this + 18));
      if ( v27 < 0 || (v27 = *((_DWORD *)this + 48), v27 < 0) )
        Base::Throw((Base *)(unsigned int)v27, v28);
      else
        ATL::CHandle::Close((ATL::CHandle *)&MutexW);
    }
  }
  catch ( Base::Exception v33 )
  {
    v29 = Base::Exception::operator long(v33);
    ErrorString = SlideshowModeControl::GetErrorString(v30, v29);
    SlideshowModeControl::ShowErrorMessage(v32, ErrorString, 1);
    Base::Exception::~Exception((Base::Exception *)v33);
  }
}

```

## disassembly

```asm
0x18003b7e0  push    rbx
0x18003b7e2  sub     rsp, 30h
0x18003b7e6  mov     rbx, rcx
0x18003b7e9  cmp     byte ptr [rcx+30h], 0
0x18003b7ed  jnz     short loc_18003B7FB
0x18003b7ef  mov     ecx, 80004005h
0x18003b7f4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b7fa  nop
0x18003b7fb  lea     r8, aWindowsphotoga; "WindowsPhotoGallerySlideshow"
0x18003b802  xor     edx, edx; bInitialOwner
0x18003b804  xor     ecx, ecx; lpMutexAttributes
0x18003b806  call    cs:__imp_CreateMutexW
0x18003b80c  mov     [rsp+38h+arg_0], rax
0x18003b811  test    rax, rax
0x18003b814  jnz     short loc_18003B81C
0x18003b816  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18003b81c  call    cs:__imp_GetLastError
0x18003b822  cmp     eax, 0B7h
0x18003b827  jnz     short loc_18003B851
0x18003b829  lea     rcx, [rsp+38h+arg_0]; this
0x18003b82e  call    ?Close@CHandle@ATL@@QEAAXXZ; ATL::CHandle::Close(void)
0x18003b833  mov     edx, 2B1Dh; unsigned __int16
0x18003b838  xor     r8d, r8d; bool
0x18003b83b  call    ?ShowErrorMessage@SlideshowModeControl@@AEAAXG_N@Z; SlideshowModeControl::ShowErrorMessage(ushort,bool)
0x18003b840  nop
0x18003b841  lea     rcx, [rsp+38h+arg_0]; this
0x18003b846  call    ?Close@CHandle@ATL@@QEAAXXZ; ATL::CHandle::Close(void)
0x18003b84b  nop
0x18003b84c  jmp     loc_18003B9F8
0x18003b851  cmp     byte ptr [rbx+0B9h], 0
0x18003b858  jnz     short loc_18003B86A
0x18003b85a  mov     edx, 1
0x18003b85f  mov     ecx, 5E1h
0x18003b864  call    cs:__imp_?Increment@Sqm@@YAXKK@Z; Sqm::Increment(ulong,ulong)
0x18003b86a  mov     ecx, 1000h; nIndex
0x18003b86f  call    cs:__imp_GetSystemMetrics
0x18003b875  mov     edx, 1
0x18003b87a  test    eax, eax
0x18003b87c  mov     ecx, 6EFh
0x18003b881  jnz     short loc_18003B888
0x18003b883  mov     ecx, 6F0h
0x18003b888  call    cs:__imp_?Increment@Sqm@@YAXKK@Z; Sqm::Increment(ulong,ulong)
0x18003b88e  mov     rcx, [rbx+90h]
0x18003b895  mov     rax, [rcx]
0x18003b898  mov     rax, [rax+28h]
0x18003b89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a1  test    eax, eax
0x18003b8a3  jns     short loc_18003B8AD
0x18003b8a5  mov     ecx, eax
0x18003b8a7  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b8ad  mov     rcx, [rbx+90h]
0x18003b8b4  mov     rax, [rcx]
0x18003b8b7  mov     rax, [rax+30h]
0x18003b8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8c0  test    eax, eax
0x18003b8c2  jns     short loc_18003B8CC
0x18003b8c4  mov     ecx, eax
0x18003b8c6  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b8cc  mov     rcx, [rbx+88h]
0x18003b8d3  mov     rax, [rcx]
0x18003b8d6  mov     rax, [rax+0A8h]
0x18003b8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8e2  test    eax, eax
0x18003b8e4  jns     short loc_18003B8EE
0x18003b8e6  mov     ecx, eax
0x18003b8e8  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b8ee  mov     rcx, [rbx+0A8h]
0x18003b8f5  mov     rax, [rcx]
0x18003b8f8  mov     rax, [rax+30h]
0x18003b8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b901  test    eax, eax
0x18003b903  jns     short loc_18003B90D
0x18003b905  mov     ecx, eax
0x18003b907  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b90d  mov     rcx, [rbx+98h]
0x18003b914  mov     rax, [rcx]
0x18003b917  mov     edx, 1
0x18003b91c  mov     rax, [rax+18h]
0x18003b920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b925  test    eax, eax
0x18003b927  jns     short loc_18003B931
0x18003b929  mov     ecx, eax
0x18003b92b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b931  mov     rcx, [rbx+98h]
0x18003b938  mov     rax, [rcx]
0x18003b93b  xor     edx, edx
0x18003b93d  mov     rax, [rax+20h]
0x18003b941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b946  test    eax, eax
0x18003b948  jns     short loc_18003B952
0x18003b94a  mov     ecx, eax
0x18003b94c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b952  mov     rcx, [rbx+0A0h]
0x18003b959  mov     rax, [rcx]
0x18003b95c  mov     dl, [rbx+0B8h]
0x18003b962  mov     rax, [rax+20h]
0x18003b966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b96b  test    eax, eax
0x18003b96d  jns     short loc_18003B977
0x18003b96f  mov     ecx, eax
0x18003b971  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b977  mov     rcx, [rbx+0A0h]
0x18003b97e  mov     rax, [rcx]
0x18003b981  mov     dl, [rbx+0B9h]
0x18003b987  mov     rax, [rax+18h]
0x18003b98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b990  test    eax, eax
0x18003b992  jns     short loc_18003B99C
0x18003b994  mov     ecx, eax
0x18003b996  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b99c  mov     rcx, [rbx+0A0h]
0x18003b9a3  mov     rax, [rcx]
0x18003b9a6  mov     edx, [rbx+0BCh]
0x18003b9ac  mov     rax, [rax+28h]
0x18003b9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9b5  test    eax, eax
0x18003b9b7  jns     short loc_18003B9C1
0x18003b9b9  mov     ecx, eax
0x18003b9bb  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b9c1  mov     rcx, [rbx+90h]
0x18003b9c8  mov     rax, [rcx]
0x18003b9cb  mov     rax, [rax+40h]
0x18003b9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9d4  test    eax, eax
0x18003b9d6  js      short loc_18003B9EF
0x18003b9d8  mov     eax, [rbx+0C0h]
0x18003b9de  test    eax, eax
0x18003b9e0  js      short loc_18003B9EF
0x18003b9e2  lea     rcx, [rsp+38h+arg_0]; this
0x18003b9e7  call    ?Close@CHandle@ATL@@QEAAXXZ; ATL::CHandle::Close(void)
0x18003b9ec  nop
0x18003b9ed  jmp     short loc_18003B9F8
0x18003b9ef  mov     ecx, eax
0x18003b9f1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b9f7  nop
0x18003b9f8  add     rsp, 30h
0x18003b9fc  pop     rbx
0x18003b9fd  retn
```
