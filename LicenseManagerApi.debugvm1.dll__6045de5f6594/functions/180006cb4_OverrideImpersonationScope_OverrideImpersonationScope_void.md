# OverrideImpersonationScope::~OverrideImpersonationScope(void)

- ea: `0x180006cb4`
- end: `0x180006d4d`
- name: `??1OverrideImpersonationScope@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(OverrideImpersonationScope *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010cc0`
- `0x1800122c9`
- `0x1800122ff`
- `0x1800123b5`

## callees

- `0x180006cb4`
- `0x18000bdc0`
- `0x18000e9c4`
- `0x18000ef94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006cce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006cda`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006cce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006cda`

## pseudocode

```c
void __fastcall OverrideImpersonationScope::~OverrideImpersonationScope(OverrideImpersonationScope *this)
{
  void *v2; // rdx
  const char *v3; // r8
  const char *v4; // r8
  signed int LastError; // eax
  int v6; // edx
  unsigned int v7; // r8d

  if ( *((_BYTE *)this + 16) )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      if ( !SetThreadToken(0, v2) )
        wil::details::in1diag3::_Throw_GetLastError(
          (wil::details::in1diag3 *)0x1E9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          v3);
    }
    else if ( !SetThreadToken(0, 0) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        (wil::details::in1diag3 *)0x1ED,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        v4);
    }
  }
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( *((_QWORD *)this + 1) )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(this) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v6, v7);
      __debugbreak();
    }
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180006cb4  push    rbx
0x180006cb6  sub     rsp, 20h
0x180006cba  mov     rbx, rcx
0x180006cbd  cmp     byte ptr [rcx+10h], 0
0x180006cc1  jz      short loc_180006CE4
0x180006cc3  mov     rdx, [rcx+8]; Token
0x180006cc7  xor     ecx, ecx; Thread
0x180006cc9  test    rdx, rdx
0x180006ccc  jz      short loc_180006CDA
0x180006cce  call    cs:__imp_SetThreadToken
0x180006cd4  test    eax, eax
0x180006cd6  jz      short loc_180006D29
0x180006cd8  jmp     short loc_180006CE4
0x180006cda  call    cs:__imp_SetThreadToken
0x180006ce0  test    eax, eax
0x180006ce2  jz      short loc_180006D3B
0x180006ce4  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180006ceb  mov     [rbx], rax
0x180006cee  cmp     qword ptr [rbx+8], 0
0x180006cf3  jz      short loc_180006D09
0x180006cf5  mov     rcx, rbx
0x180006cf8  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180006cfd  test    al, al
0x180006cff  jz      short loc_180006D0F
0x180006d01  mov     qword ptr [rbx+8], 0
0x180006d09  add     rsp, 20h
0x180006d0d  pop     rbx
0x180006d0e  retn
0x180006d0f  call    cs:__imp_GetLastError
0x180006d15  test    eax, eax
0x180006d17  jle     short loc_180006D21
0x180006d19  movzx   eax, ax
0x180006d1c  or      eax, 80070000h
0x180006d21  mov     ecx, eax; this
0x180006d23  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180006d28  int     3; Trap to Debugger
0x180006d29  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180006d30  mov     ecx, 1E9h; this
0x180006d35  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(uint,char const *)
0x180006d3b  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180006d42  mov     ecx, 1EDh; this
0x180006d47  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(uint,char const *)
```
