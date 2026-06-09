# SessionFontSet::InitializeCacheState(bool,SessionFontSet::CacheState &,void (*)(void *,uchar))

- ea: `0x1800698bc`
- end: `0x180069a18`
- name: `?InitializeCacheState@SessionFontSet@@AEAAX_NAEAUCacheState@1@P6AXPEAXE@Z@Z`
- size: `348`
- prototype: `void __fastcall(PVOID Context, bool, struct SessionFontSet::CacheState *, void (*)(void *, unsigned __int8))`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800696cc`

## callees

- `0x180010338`
- `0x1800698bc`
- `0x18006c6b4`
- `0x180076ca4`
- `0x18009372c`
- `0x180096b38`
- `0x180096cdc`
- `0x1800b726c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800699ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800699ff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18006998d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18006998d`

## string_xrefs

- `0x18006992b`: `usrCache`
- `0x180069938`: `sysCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SessionFontSet::InitializeCacheState(
        char *Context,
        bool a2,
        struct SessionFontSet::CacheState *a3,
        void (*a4)(void *, unsigned __int8))
{
  const char *v8; // rdx
  EventTag *v9; // rcx
  __int64 *v10; // rax
  void *v11; // rax
  EventTag *v12; // rax
  EventTag *v13; // rax
  void *v14; // [rsp+30h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-10h] BYREF
  void *phNewWaitObject; // [rsp+80h] [rbp+30h] BYREF

  if ( *(_QWORD *)a3 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 64LL))(*(_QWORD *)a3) )
    {
      SessionFontSet::UpdateCacheState(Context, a2, a3, a4);
    }
    else
    {
      LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (struct Lock *)(Context + 112));
      if ( a2 )
      {
        v8 = "usrCache";
        v9 = (EventTag *)&v14;
      }
      else
      {
        v8 = "sysCache";
        v9 = (EventTag *)v16;
      }
      v10 = (__int64 *)EventTag::EventTag(v9, (const char (*)[9])v8);
      EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag>(
        (__int64)Context,
        *v10,
        1953066601);
      phNewWaitObject = 0;
      v11 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 72LL))(*(_QWORD *)a3);
      if ( !RegisterWaitForSingleObject(&phNewWaitObject, v11, a4, Context, 0xFFFFFFFF, 8u) )
      {
        if ( a2 )
        {
          v12 = EventTag::EventTag((EventTag *)v16, (const char (*)[9])"usr_init");
          EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogAndThrowLastError(
            Context,
            *(_QWORD *)v12,
            197);
        }
        v13 = EventTag::EventTag((EventTag *)v16, (const char (*)[9])"sys_init");
        EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogAndThrowLastError(
          Context,
          *(_QWORD *)v13,
          201);
      }
      v14 = phNewWaitObject;
      ScopedHandle<WaitHandlePolicy,void *>::operator=((char *)a3 + 16, &v14);
      ScopedHandle<WaitHandlePolicy,void *>::~ScopedHandle<WaitHandlePolicy,void *>(&v14);
      LeaveCriticalSection(lpCriticalSection);
    }
  }
  else
  {
    *((_DWORD *)a3 + 8) = -2147418113;
  }
}

```

## disassembly

```asm
0x1800698bc  mov     [rsp-18h+arg_0], rbx
0x1800698c1  mov     [rsp-18h+arg_8], rsi
0x1800698c6  push    rbp
0x1800698c7  push    rdi
0x1800698c8  push    r14
0x1800698ca  mov     rbp, rsp
0x1800698cd  sub     rsp, 50h
0x1800698d1  mov     r14, r9
0x1800698d4  mov     rbx, r8
0x1800698d7  mov     sil, dl
0x1800698da  mov     rdi, rcx
0x1800698dd  mov     rcx, [r8]
0x1800698e0  test    rcx, rcx
0x1800698e3  jnz     short loc_1800698F2
0x1800698e5  mov     dword ptr [r8+20h], 8000FFFFh
0x1800698ed  jmp     loc_180069A05
0x1800698f2  mov     rax, [rcx]
0x1800698f5  mov     rax, [rax+40h]
0x1800698f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698fe  test    al, al
0x180069900  jz      short loc_180069918
0x180069902  mov     r9, r14; void (*)(void *, unsigned __int8)
0x180069905  mov     r8, rbx; struct SessionFontSet::CacheState *
0x180069908  mov     dl, sil; bool
0x18006990b  mov     rcx, rdi; Context
0x18006990e  call    ?UpdateCacheState@SessionFontSet@@AEAAX_NAEAUCacheState@1@P6AXPEAXE@Z@Z; SessionFontSet::UpdateCacheState(bool,SessionFontSet::CacheState &,void (*)(void *,uchar))
0x180069913  jmp     loc_180069A05
0x180069918  lea     rdx, [rdi+70h]; struct Lock *
0x18006991c  lea     rcx, [rbp+lpCriticalSection]; this
0x180069920  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x180069925  nop
0x180069926  test    sil, sil
0x180069929  jz      short loc_180069938
0x18006992b  lea     rdx, aUsrcache; "usrCache"
0x180069932  lea     rcx, [rbp+var_20]
0x180069936  jmp     short loc_180069943
0x180069938  lea     rdx, aSyscache; "sysCache"
0x18006993f  lea     rcx, [rbp+var_10]; this
0x180069943  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x180069948  mov     r8d, 74696E69h
0x18006994e  mov     rdx, [rax]
0x180069951  mov     rcx, rdi
0x180069954  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag>(EventTag,EventTag)
0x180069959  mov     [rbp+phNewWaitObject], 0
0x180069961  mov     rcx, [rbx]
0x180069964  mov     rax, [rcx]
0x180069967  mov     rax, [rax+48h]
0x18006996b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069970  mov     rdx, rax; hObject
0x180069973  mov     [rsp+50h+dwFlags], 8; dwFlags
0x18006997b  mov     [rsp+50h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180069983  mov     r9, rdi; Context
0x180069986  mov     r8, r14; Callback
0x180069989  lea     rcx, [rbp+phNewWaitObject]; phNewWaitObject
0x18006998d  call    cs:__imp_RegisterWaitForSingleObject
0x180069993  test    eax, eax
0x180069995  jnz     short loc_1800699DC
0x180069997  lea     rcx, [rbp+var_10]; this
0x18006999b  test    sil, sil
0x18006999e  jz      short loc_1800699BE
0x1800699a0  lea     rdx, aUsrInit; "usr_init"
0x1800699a7  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1800699ac  mov     r8d, 0C5h
0x1800699b2  mov     rdx, [rax]
0x1800699b5  mov     rcx, rdi
0x1800699b8  call    ?LogAndThrowLastError@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@I@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogAndThrowLastError(EventTag,uint)
0x1800699be  lea     rdx, aSysInit; "sys_init"
0x1800699c5  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1800699ca  mov     r8d, 0C9h
0x1800699d0  mov     rdx, [rax]
0x1800699d3  mov     rcx, rdi
0x1800699d6  call    ?LogAndThrowLastError@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@I@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogAndThrowLastError(EventTag,uint)
0x1800699dc  mov     rax, [rbp+phNewWaitObject]
0x1800699e0  mov     [rbp+var_20], rax
0x1800699e4  lea     rcx, [rbx+10h]
0x1800699e8  lea     rdx, [rbp+var_20]
0x1800699ec  call    ??4?$ScopedHandle@UWaitHandlePolicy@@PEAX@@QEAAAEAV0@$$QEAV0@@Z; ScopedHandle<WaitHandlePolicy,void *>::operator=(ScopedHandle<WaitHandlePolicy,void *> &&)
0x1800699f1  lea     rcx, [rbp+var_20]
0x1800699f5  call    ??1?$ScopedHandle@UWaitHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<WaitHandlePolicy,void *>::~ScopedHandle<WaitHandlePolicy,void *>(void)
0x1800699fa  nop
0x1800699fb  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800699ff  call    cs:__imp_LeaveCriticalSection
0x180069a05  mov     rbx, [rsp+50h+arg_0]
0x180069a0a  mov     rsi, [rsp+50h+arg_8]
0x180069a0f  add     rsp, 50h
0x180069a13  pop     r14
0x180069a15  pop     rdi
0x180069a16  pop     rbp
0x180069a17  retn
```
