# Windows::Graphics::Capture::Server::CaptureWindowFilter::AddWindow(Windows::Internal::ApplicationModel::WindowManagement::WindowId)

- ea: `0x18001e450`
- end: `0x18001e4cc`
- name: `?AddWindow@CaptureWindowFilter@Server@Capture@Graphics@Windows@@UEAAJUWindowId@WindowManagement@ApplicationModel@Internal@5@@Z`
- size: `124`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001e450`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e46b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e46b`

## string_xrefs

- `0x18001e49b`: `onecoreuap\windows\dwm\capture\svc\dll\capturewindowfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureWindowFilter::AddWindow(RTL_SRWLOCK *a1, unsigned int a2)
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
  if ( Ptr && (v6 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)Ptr + 48LL))(Ptr, a2), v7 = v6, v6 < 0) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
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
0x18001e450  mov     [rsp+arg_8], rbx
0x18001e455  mov     [rsp+arg_10], rsi
0x18001e45a  push    rdi; int
0x18001e45b  sub     rsp, 20h
0x18001e45f  mov     ebx, edx
0x18001e461  mov     rsi, rcx
0x18001e464  lea     rdi, [rcx+20h]
0x18001e468  mov     rcx, rdi; SRWLock
0x18001e46b  call    cs:__imp_AcquireSRWLockExclusive
0x18001e471  mov     [rsp+28h+arg_0], rdi
0x18001e476  mov     rcx, [rsi+18h]
0x18001e47a  test    rcx, rcx
0x18001e47d  jz      short loc_18001E4AE
0x18001e47f  mov     rax, [rcx]
0x18001e482  mov     edx, ebx
0x18001e484  mov     rax, [rax+30h]
0x18001e488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e48d  mov     ebx, eax
0x18001e48f  test    eax, eax
0x18001e491  jns     short loc_18001E4AE
0x18001e493  mov     rcx, [rsp+28h]; this
0x18001e498  mov     r9d, eax; char *
0x18001e49b  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001e4a2  mov     edx, 20h ; ' '; void *
0x18001e4a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4ac  jmp     short loc_18001E4B0
0x18001e4ae  xor     ebx, ebx
0x18001e4b0  lea     rcx, [rsp+28h+arg_0]
0x18001e4b5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e4ba  mov     eax, ebx
0x18001e4bc  mov     rbx, [rsp+28h+arg_8]
0x18001e4c1  mov     rsi, [rsp+28h+arg_10]
0x18001e4c6  add     rsp, 20h
0x18001e4ca  pop     rdi
0x18001e4cb  retn
```
