# SessionFontSet::BeginBackgroundWork(TaggedLockHolder<SessionFontSet::MemberLockTag> const &,void *,uint,SessionFontSet::WaitType)

- ea: `0x180096248`
- end: `0x1800963f8`
- name: `?BeginBackgroundWork@SessionFontSet@@AEAA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@AEBV?$TaggedLockHolder@W4MemberLockTag@SessionFontSet@@@@PEAXIW4WaitType@1@@Z`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010130`
- `0x1800a80b0`

## callees

- `0x18000ff38`
- `0x18001035c`
- `0x180010388`
- `0x18006968c`
- `0x180096248`
- `0x180096400`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009634d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800963aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800963d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009634d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800963aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800963d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180096337`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180096337`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SessionFontSet::BeginBackgroundWork(__int64 a1, __int64 a2, ...)
{
  void *v4; // rbx
  void *v5; // rdi
  __int64 v6; // rsi
  int v7; // r12d
  MemorySection *v8; // r14
  int v9; // r12d
  void *v10; // rdx
  void *v11; // rax
  void *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 *v16; // rax
  void *v17; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+50h] BYREF
  va_list hObjecta; // [rsp+90h] [rbp+50h]
  __int64 v21; // [rsp+98h] [rbp+58h]
  __int64 v22; // [rsp+A0h] [rbp+60h]
  __int64 v23; // [rsp+A8h] [rbp+68h]
  va_list va1; // [rsp+B0h] [rbp+70h] BYREF

  va_start(va1, a2);
  va_start(hObjecta, a2);
  hObject = va_arg(va1, HANDLE);
  v21 = va_arg(va1, _QWORD);
  v22 = va_arg(va1, _QWORD);
  v23 = va_arg(va1, _QWORD);
  v4 = 0;
  v18[0] = 0;
  v5 = 0;
  v17 = 0;
  v6 = 0;
  v7 = *(_DWORD *)(a1 + 168);
  v8 = (MemorySection *)(a1 + 192);
  if ( !*(_QWORD *)(a1 + 192) )
  {
    v14 = Event::Create((HANDLE *)hObjecta, 1);
    ScopedHandle<EventHandlePolicy,void *>::operator=(v18, v14);
    if ( hObject )
      CloseHandle(hObject);
    v4 = (void *)v18[0];
  }
  v9 = v22 | v7;
  if ( (v9 & 1) != 0 )
  {
    v15 = Event::Create((HANDLE *)hObjecta, 1);
    ScopedHandle<EventHandlePolicy,void *>::operator=(&v17, v15);
    if ( hObject )
      CloseHandle(hObject);
    v16 = (__int64 *)CloneProcessHandle((HANDLE *)hObjecta, v21);
    v6 = *v16;
    *v16 = 0;
    if ( hObject )
      CloseHandle(hObject);
    v5 = v17;
  }
  if ( (_DWORD)v23 == 1 )
  {
    v10 = v5;
  }
  else
  {
    v10 = v4;
    if ( !v4 )
      v10 = *(void **)v8;
  }
  ServerCacheContext::CloneEventHandle(a2, v10, v21);
  *(_DWORD *)(a1 + 168) = v9;
  *(_QWORD *)(a1 + 200) = v6;
  if ( (void **)(a1 + 184) != &v17 )
  {
    MemorySection::~MemorySection((MemorySection *)(a1 + 184));
    v11 = v5;
    v5 = 0;
    *(_QWORD *)(a1 + 184) = v11;
  }
  if ( v4 )
  {
    if ( v8 != (MemorySection *)v18 )
    {
      MemorySection::~MemorySection(v8);
      v13 = v4;
      v4 = 0;
      *(_QWORD *)v8 = v13;
    }
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 176));
  }
  if ( v5 )
    CloseHandle(v5);
  if ( v4 )
    CloseHandle(v4);
  return a2;
}

```

## disassembly

```asm
0x180096248  mov     [rsp-38h+arg_8], rbx
0x18009624d  mov     [rsp-38h+arg_18], r9
0x180096252  mov     [rsp-38h+hObject], r8
0x180096257  push    rbp
0x180096258  push    rsi
0x180096259  push    rdi
0x18009625a  push    r12
0x18009625c  push    r13
0x18009625e  push    r14
0x180096260  push    r15
0x180096262  mov     rbp, rsp
0x180096265  sub     rsp, 40h
0x180096269  mov     r13, rdx
0x18009626c  mov     r15, rcx
0x18009626f  xor     ebx, ebx
0x180096271  mov     [rbp+var_10], rbx
0x180096275  xor     edi, edi
0x180096277  mov     [rbp+var_18], rdi
0x18009627b  xor     esi, esi
0x18009627d  mov     [rbp+arg_0], rsi
0x180096281  mov     r12d, [rcx+0A8h]
0x180096288  lea     r14, [rcx+0C0h]
0x18009628f  cmp     [r14], rsi
0x180096292  jz      loc_180096355
0x180096298  or      r12d, dword ptr [rbp+arg_20]
0x18009629c  test    r12b, 1
0x1800962a0  jnz     loc_180096387
0x1800962a6  cmp     dword ptr [rbp+arg_28], 1
0x1800962aa  jnz     loc_1800963E3
0x1800962b0  mov     rdx, rdi
0x1800962b3  mov     r8, [rbp+arg_18]
0x1800962b7  mov     rcx, r13
0x1800962ba  call    ?CloneEventHandle@ServerCacheContext@@SA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@PEAX0@Z; ServerCacheContext::CloneEventHandle(void *,void *)
0x1800962bf  mov     [r15+0A8h], r12d
0x1800962c6  mov     [r15+0C8h], rsi
0x1800962cd  lea     rsi, [r15+0B8h]
0x1800962d4  lea     rax, [rbp+var_18]
0x1800962d8  cmp     rsi, rax
0x1800962db  jz      short loc_1800962ED
0x1800962dd  mov     rcx, rsi; this
0x1800962e0  call    ??1MemorySection@@QEAA@XZ; MemorySection::~MemorySection(void)
0x1800962e5  mov     rax, rdi
0x1800962e8  xor     edi, edi
0x1800962ea  mov     [rsi], rax
0x1800962ed  test    rbx, rbx
0x1800962f0  jnz     short loc_180096317
0x1800962f2  test    rdi, rdi
0x1800962f5  jnz     short loc_18009633F
0x1800962f7  test    rbx, rbx
0x1800962fa  jnz     short loc_18009634A
0x1800962fc  mov     rax, r13
0x1800962ff  mov     rbx, [rsp+40h+arg_8]
0x180096307  add     rsp, 40h
0x18009630b  pop     r15
0x18009630d  pop     r14
0x18009630f  pop     r13
0x180096311  pop     r12
0x180096313  pop     rdi
0x180096314  pop     rsi
0x180096315  pop     rbp
0x180096316  retn
0x180096317  lea     rax, [rbp+var_10]
0x18009631b  cmp     r14, rax
0x18009631e  jz      short loc_180096330
0x180096320  mov     rcx, r14; this
0x180096323  call    ??1MemorySection@@QEAA@XZ; MemorySection::~MemorySection(void)
0x180096328  mov     rax, rbx
0x18009632b  xor     ebx, ebx
0x18009632d  mov     [r14], rax
0x180096330  mov     rcx, [r15+0B0h]; pwk
0x180096337  call    cs:__imp_SubmitThreadpoolWork
0x18009633d  jmp     short loc_1800962F2
0x18009633f  mov     rcx, rdi; hObject
0x180096342  call    cs:__imp_CloseHandle
0x180096348  jmp     short loc_1800962F7
0x18009634a  mov     rcx, rbx; hObject
0x18009634d  call    cs:__imp_CloseHandle
0x180096353  jmp     short loc_1800962FC
0x180096355  mov     edx, 1
0x18009635a  lea     rcx, [rbp+hObject]
0x18009635e  call    ?Create@Event@@SA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@W4ResetMode@1@_N@Z; Event::Create(Event::ResetMode,bool)
0x180096363  mov     rdx, rax
0x180096366  lea     rcx, [rbp+var_10]
0x18009636a  call    ??4?$ScopedHandle@UEventHandlePolicy@@PEAX@@QEAAAEAV0@$$QEAV0@@Z; ScopedHandle<EventHandlePolicy,void *>::operator=(ScopedHandle<EventHandlePolicy,void *> &&)
0x18009636f  mov     rcx, [rbp+hObject]; hObject
0x180096373  test    rcx, rcx
0x180096376  jz      short loc_18009637E
0x180096378  call    cs:__imp_CloseHandle
0x18009637e  mov     rbx, [rbp+var_10]
0x180096382  jmp     loc_180096298
0x180096387  mov     edx, 1
0x18009638c  lea     rcx, [rbp+hObject]
0x180096390  call    ?Create@Event@@SA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@W4ResetMode@1@_N@Z; Event::Create(Event::ResetMode,bool)
0x180096395  mov     rdx, rax
0x180096398  lea     rcx, [rbp+var_18]
0x18009639c  call    ??4?$ScopedHandle@UEventHandlePolicy@@PEAX@@QEAAAEAV0@$$QEAV0@@Z; ScopedHandle<EventHandlePolicy,void *>::operator=(ScopedHandle<EventHandlePolicy,void *> &&)
0x1800963a1  mov     rcx, [rbp+hObject]; hObject
0x1800963a5  test    rcx, rcx
0x1800963a8  jz      short loc_1800963B0
0x1800963aa  call    cs:__imp_CloseHandle
0x1800963b0  mov     rdx, [rbp+arg_18]
0x1800963b4  lea     rcx, [rbp+hObject]
0x1800963b8  call    ?CloneProcessHandle@@YA?AVWin32Handle@@PEAX@Z; CloneProcessHandle(void *)
0x1800963bd  mov     rsi, [rax]
0x1800963c0  mov     qword ptr [rax], 0
0x1800963c7  mov     [rbp+arg_0], rsi
0x1800963cb  mov     rcx, [rbp+hObject]; hObject
0x1800963cf  test    rcx, rcx
0x1800963d2  jz      short loc_1800963DA
0x1800963d4  call    cs:__imp_CloseHandle
0x1800963da  mov     rdi, [rbp+var_18]
0x1800963de  jmp     loc_1800962A6
0x1800963e3  test    rbx, rbx
0x1800963e6  mov     rdx, rbx
0x1800963e9  jnz     loc_1800962B3
0x1800963ef  mov     rdx, [r14]
0x1800963f2  jmp     loc_1800962B3
```
