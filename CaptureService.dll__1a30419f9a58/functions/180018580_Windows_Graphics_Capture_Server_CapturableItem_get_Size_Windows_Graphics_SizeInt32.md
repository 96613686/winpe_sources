# Windows::Graphics::Capture::Server::CapturableItem::get_Size(Windows::Graphics::SizeInt32 *)

- ea: `0x180018580`
- end: `0x180018659`
- name: `?get_Size@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAUSizeInt32@45@@Z`
- size: `217`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, struct Windows::Graphics::SizeInt32 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180003b74`
- `0x180003c64`
- `0x180005588`
- `0x18000907c`
- `0x180018580`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001859c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001859c`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800185b6`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x180018602`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x180018635`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800185b6`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x180018602`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x180018635`

## string_xrefs

- `0x1800185e9`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::get_Size(
        RTL_SRWLOCK *this,
        struct Windows::Graphics::SizeInt32 *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 X; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+40h] [rbp+18h] BYREF

  v4 = this + 8;
  AcquireSRWLockShared(this + 8);
  v12 = v4;
  v5 = 0;
  if ( (unsigned __int8)IsSetThreadDpiAwarenessContextPresent() )
    v5 = SetThreadDpiAwarenessContext(-4);
  X = 0;
  v6 = (*(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)this[4].Ptr + 72LL))(this[4].Ptr, &X);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *(_DWORD *)a2 = (int)o_ceilf_0(*(float *)&X);
    *((_DWORD *)a2 + 1) = (int)o_ceilf_0(*((float *)&X + 1));
    if ( v5 )
      SetThreadDpiAwarenessContext(v5);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v6,
      v9);
    if ( v5 )
      SetThreadDpiAwarenessContext(v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180018580  mov     [rsp+arg_8], rbx
0x180018585  mov     [rsp+arg_18], rsi
0x18001858a  push    rdi; int
0x18001858b  sub     rsp, 20h
0x18001858f  mov     rsi, rdx
0x180018592  mov     rdi, rcx
0x180018595  lea     rbx, [rcx+40h]
0x180018599  mov     rcx, rbx; SRWLock
0x18001859c  call    cs:__imp_AcquireSRWLockShared
0x1800185a2  mov     [rsp+28h+arg_10], rbx
0x1800185a7  xor     ebx, ebx
0x1800185a9  call    IsSetThreadDpiAwarenessContextPresent
0x1800185ae  test    al, al
0x1800185b0  jz      short loc_1800185BF
0x1800185b2  lea     rcx, [rbx-4]
0x1800185b6  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800185bc  mov     rbx, rax
0x1800185bf  xor     eax, eax
0x1800185c1  mov     [rsp+28h+X], rax
0x1800185c6  mov     rcx, [rdi+20h]
0x1800185ca  mov     rdx, [rcx]
0x1800185cd  mov     rax, [rdx+48h]
0x1800185d1  lea     rdx, [rsp+28h+X]
0x1800185d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185db  mov     edi, eax
0x1800185dd  test    eax, eax
0x1800185df  jns     short loc_18001860A
0x1800185e1  mov     rcx, [rsp+28h]; this
0x1800185e6  mov     r9d, eax; char *
0x1800185e9  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800185f0  mov     edx, 197h; void *
0x1800185f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185fa  test    rbx, rbx
0x1800185fd  jz      short loc_18001863D
0x1800185ff  mov     rcx, rbx
0x180018602  call    cs:__imp_SetThreadDpiAwarenessContext
0x180018608  jmp     short loc_18001863D
0x18001860a  movss   xmm0, dword ptr [rsp+28h+X]; X
0x180018610  call    _o_ceilf_0
0x180018615  cvttss2si eax, xmm0
0x180018619  mov     [rsi], eax
0x18001861b  movss   xmm0, dword ptr [rsp+28h+X+4]; X
0x180018621  call    _o_ceilf_0
0x180018626  cvttss2si eax, xmm0
0x18001862a  mov     [rsi+4], eax
0x18001862d  test    rbx, rbx
0x180018630  jz      short loc_18001863B
0x180018632  mov     rcx, rbx
0x180018635  call    cs:__imp_SetThreadDpiAwarenessContext
0x18001863b  xor     edi, edi
0x18001863d  lea     rcx, [rsp+28h+arg_10]
0x180018642  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018647  mov     eax, edi
0x180018649  mov     rbx, [rsp+28h+arg_8]
0x18001864e  mov     rsi, [rsp+28h+arg_18]
0x180018653  add     rsp, 20h
0x180018657  pop     rdi
0x180018658  retn
```
