# ImpersonateUserContext::~ImpersonateUserContext(void)

- ea: `0x18002e268`
- end: `0x18002e2d6`
- name: `??1ImpersonateUserContext@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(ImpersonateUserContext *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f800`
- `0x18004d243`

## callees

- `0x18002e268`
- `0x18002f280`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2bc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002e281`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002e281`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e289`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e289`

## pseudocode

```c
void __fastcall ImpersonateUserContext::~ImpersonateUserContext(ImpersonateUserContext *this)
{
  void *v2; // rdx
  bool v3; // zf
  signed int LastError; // eax
  int v5; // edx
  unsigned int v6; // r8d

  if ( *(_DWORD *)this )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
      SetThreadToken(0, v2);
    else
      RevertToSelf();
  }
  v3 = *((_QWORD *)this + 2) == 0;
  *((_QWORD *)this + 1) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( !v3 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((char *)this + 8) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v5, v6);
      JUMPOUT(0x18002E2D5LL);
    }
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18002e268  push    rbx
0x18002e26a  sub     rsp, 20h
0x18002e26e  cmp     dword ptr [rcx], 0
0x18002e271  mov     rbx, rcx
0x18002e274  jz      short loc_18002E28F
0x18002e276  mov     rdx, [rcx+10h]; Token
0x18002e27a  test    rdx, rdx
0x18002e27d  jz      short loc_18002E289
0x18002e27f  xor     ecx, ecx; Thread
0x18002e281  call    cs:__imp_SetThreadToken
0x18002e287  jmp     short loc_18002E28F
0x18002e289  call    cs:__imp_RevertToSelf
0x18002e28f  cmp     qword ptr [rbx+10h], 0
0x18002e294  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002e29b  mov     [rbx+8], rax
0x18002e29f  jz      short loc_18002E2B6
0x18002e2a1  lea     rcx, [rbx+8]
0x18002e2a5  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18002e2aa  test    al, al
0x18002e2ac  jz      short loc_18002E2BC
0x18002e2ae  mov     qword ptr [rbx+10h], 0
0x18002e2b6  add     rsp, 20h
0x18002e2ba  pop     rbx
0x18002e2bb  retn
0x18002e2bc  call    cs:__imp_GetLastError
0x18002e2c2  test    eax, eax
0x18002e2c4  jle     short loc_18002E2CE
0x18002e2c6  movzx   eax, ax
0x18002e2c9  or      eax, 80070000h
0x18002e2ce  mov     ecx, eax; this
0x18002e2d0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
