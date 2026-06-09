# Windows::Graphics::Capture::Server::CaptureWindowFilter::RemoveWindow(Windows::Internal::ApplicationModel::WindowManagement::WindowId)

- ea: `0x18001e4e0`
- end: `0x18001e55c`
- name: `?RemoveWindow@CaptureWindowFilter@Server@Capture@Graphics@Windows@@UEAAJUWindowId@WindowManagement@ApplicationModel@Internal@5@@Z`
- size: `124`
- prototype: `int __high(struct Windows::Internal::ApplicationModel::WindowManagement::WindowId)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001e4e0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e4fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e4fb`

## string_xrefs

- `0x18001e52b`: `onecoreuap\windows\dwm\capture\svc\dll\capturewindowfilter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureWindowFilter::RemoveWindow(
        RTL_SRWLOCK *a1,
        unsigned int a2)
{
  RTL_SRWLOCK *v4; // rdi
  PVOID Ptr; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1 + 4;
  AcquireSRWLockExclusive(a1 + 4);
  v11 = v4;
  Ptr = a1[3].Ptr;
  if ( Ptr && (v6 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)Ptr + 56LL))(Ptr, a2), v7 = v6, v6 < 0) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturewindowfilter.cpp",
      (const char *)(unsigned int)v6,
      v9);
  else
    v7 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return v7;
}

```

## disassembly

```asm
0x18001e4e0  mov     [rsp+arg_8], rbx
0x18001e4e5  mov     [rsp+arg_10], rsi
0x18001e4ea  push    rdi; int
0x18001e4eb  sub     rsp, 20h
0x18001e4ef  mov     ebx, edx
0x18001e4f1  mov     rsi, rcx
0x18001e4f4  lea     rdi, [rcx+20h]
0x18001e4f8  mov     rcx, rdi; SRWLock
0x18001e4fb  call    cs:__imp_AcquireSRWLockExclusive
0x18001e501  mov     [rsp+28h+arg_0], rdi
0x18001e506  mov     rcx, [rsi+18h]
0x18001e50a  test    rcx, rcx
0x18001e50d  jz      short loc_18001E53E
0x18001e50f  mov     rax, [rcx]
0x18001e512  mov     edx, ebx
0x18001e514  mov     rax, [rax+38h]
0x18001e518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e51d  mov     ebx, eax
0x18001e51f  test    eax, eax
0x18001e521  jns     short loc_18001E53E
0x18001e523  mov     rcx, [rsp+28h]; this
0x18001e528  mov     r9d, eax; char *
0x18001e52b  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e532  mov     edx, 2Dh ; '-'; void *
0x18001e537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e53c  jmp     short loc_18001E540
0x18001e53e  xor     ebx, ebx
0x18001e540  lea     rcx, [rsp+28h+arg_0]
0x18001e545  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e54a  mov     eax, ebx
0x18001e54c  mov     rbx, [rsp+28h+arg_8]
0x18001e551  mov     rsi, [rsp+28h+arg_10]
0x18001e556  add     rsp, 20h
0x18001e55a  pop     rdi
0x18001e55b  retn
```
