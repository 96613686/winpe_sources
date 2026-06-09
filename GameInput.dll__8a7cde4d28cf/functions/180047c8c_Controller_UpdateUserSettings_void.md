# Controller::UpdateUserSettings(void)

- ea: `0x180047c8c`
- end: `0x180047d26`
- name: `?UpdateUserSettings@Controller@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(Controller *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800465e0`
- `0x1800469c0`

## callees

- `0x180047104`
- `0x180047c8c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047cef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047cc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047cc9`

## pseudocode

```c
void __fastcall Controller::UpdateUserSettings(Controller *this)
{
  __int64 v2; // rcx
  struct Windows::System::IUser *v3; // rcx
  struct Windows::System::IUser *v4; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 9) )
  {
    v2 = *((_QWORD *)this + 5);
    v4 = 0;
    if ( (*(int (__fastcall **)(__int64, struct Windows::System::IUser **))(*(_QWORD *)v2 + 112LL))(v2, &v4) >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
      UpdateUserSettings(
        *((struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate **)this + 8),
        *((struct Windows::System::Internal::ISignInStateManager **)this + 9),
        v4);
      if ( this != (Controller *)-80LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
    }
    v3 = v4;
    if ( v4 )
    {
      v4 = 0;
      (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
}

```

## disassembly

```asm
0x180047c8c  mov     [rsp+arg_8], rbx
0x180047c91  push    rdi
0x180047c92  sub     rsp, 20h
0x180047c96  cmp     qword ptr [rcx+48h], 0
0x180047c9b  mov     rbx, rcx
0x180047c9e  jz      short loc_180047D1A
0x180047ca0  mov     rcx, [rcx+28h]
0x180047ca4  lea     rdx, [rsp+28h+arg_0]
0x180047ca9  mov     [rsp+28h+arg_0], 0
0x180047cb2  mov     rax, [rcx]
0x180047cb5  mov     rax, [rax+70h]
0x180047cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cbe  test    eax, eax
0x180047cc0  js      short loc_180047CFB
0x180047cc2  lea     rdi, [rbx+50h]
0x180047cc6  mov     rcx, rdi; lpCriticalSection
0x180047cc9  call    cs:__imp_EnterCriticalSection
0x180047cd0  nop     dword ptr [rax+rax+00h]
0x180047cd5  mov     r8, [rsp+28h+arg_0]; struct Windows::System::IUser *
0x180047cda  mov     rdx, [rbx+48h]; struct Windows::System::Internal::ISignInStateManager *
0x180047cde  mov     rcx, [rbx+40h]; struct Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *
0x180047ce2  call    ?UpdateUserSettings@@YAJPEAUIGipGameControllerProviderPrivate@Internal@Input@Gaming@Windows@@PEAUISignInStateManager@2System@5@PEAUIUser@75@@Z; UpdateUserSettings(Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate *,Windows::System::Internal::ISignInStateManager *,Windows::System::IUser *)
0x180047ce7  test    rdi, rdi
0x180047cea  jz      short loc_180047CFB
0x180047cec  mov     rcx, rdi; lpCriticalSection
0x180047cef  call    cs:__imp_LeaveCriticalSection
0x180047cf6  nop     dword ptr [rax+rax+00h]
0x180047cfb  mov     rcx, [rsp+28h+arg_0]
0x180047d00  test    rcx, rcx
0x180047d03  jz      short loc_180047D1A
0x180047d05  mov     [rsp+28h+arg_0], 0
0x180047d0e  mov     rax, [rcx]
0x180047d11  mov     rax, [rax+10h]
0x180047d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d1a  mov     rbx, [rsp+28h+arg_8]
0x180047d1f  add     rsp, 20h
0x180047d23  pop     rdi
0x180047d24  retn
```
