# Windows::Graphics::Capture::Server::CapturableItem::get_DisplayName(HSTRING__ * *)

- ea: `0x180018160`
- end: `0x1800181d9`
- name: `?get_DisplayName@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `121`
- prototype: `int(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005588`
- `0x18000907c`
- `0x180018160`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001817c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001817c`

## string_xrefs

- `0x1800181a8`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::get_DisplayName(RTL_SRWLOCK *this, HSTRING *a2)
{
  RTL_SRWLOCK *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp+8h] BYREF

  v4 = this + 8;
  AcquireSRWLockShared(this + 8);
  v10 = v4;
  v5 = (*(__int64 (__fastcall **)(PVOID, HSTRING *))(*(_QWORD *)this[3].Ptr + 48LL))(this[3].Ptr, a2);
  v6 = v5;
  if ( v5 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v5,
      v8);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return v6;
}

```

## disassembly

```asm
0x180018160  mov     [rsp+arg_8], rbx
0x180018165  mov     [rsp+arg_10], rsi
0x18001816a  push    rdi; int
0x18001816b  sub     rsp, 20h
0x18001816f  mov     rsi, rdx
0x180018172  mov     rdi, rcx
0x180018175  lea     rbx, [rcx+40h]
0x180018179  mov     rcx, rbx; SRWLock
0x18001817c  call    cs:__imp_AcquireSRWLockShared
0x180018182  mov     [rsp+28h+arg_0], rbx
0x180018187  mov     rcx, [rdi+18h]
0x18001818b  mov     rax, [rcx]
0x18001818e  mov     rdx, rsi
0x180018191  mov     rax, [rax+30h]
0x180018195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001819a  mov     ebx, eax
0x18001819c  test    eax, eax
0x18001819e  jns     short loc_1800181BB
0x1800181a0  mov     rcx, [rsp+28h]; this
0x1800181a5  mov     r9d, eax; char *
0x1800181a8  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800181af  mov     edx, 180h; void *
0x1800181b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181b9  jmp     short loc_1800181BD
0x1800181bb  xor     ebx, ebx
0x1800181bd  lea     rcx, [rsp+28h+arg_0]
0x1800181c2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800181c7  mov     eax, ebx
0x1800181c9  mov     rbx, [rsp+28h+arg_8]
0x1800181ce  mov     rsi, [rsp+28h+arg_10]
0x1800181d3  add     rsp, 20h
0x1800181d7  pop     rdi
0x1800181d8  retn
```
