# SuspendImpersonationScope::~SuspendImpersonationScope(void)

- ea: `0x180036af4`
- end: `0x180036b6e`
- name: `??1SuspendImpersonationScope@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(SuspendImpersonationScope *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036bfc`
- `0x18004dc7e`

## callees

- `0x18002f280`
- `0x18002fbb4`
- `0x180030a68`
- `0x180036af4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180036b08`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180036b08`

## pseudocode

```c
void __fastcall SuspendImpersonationScope::~SuspendImpersonationScope(SuspendImpersonationScope *this)
{
  void *v2; // rdx
  const char *v3; // r9
  signed int LastError; // eax
  int v5; // edx
  unsigned int v6; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !SetThreadToken(0, v2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\inc\\RAIIhelpers.h",
      v3);
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( *((_QWORD *)this + 1) )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(this) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v5, v6);
      __debugbreak();
    }
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180036af4  push    rbx
0x180036af6  sub     rsp, 20h
0x180036afa  mov     rbx, rcx
0x180036afd  mov     rdx, [rcx+8]; Token
0x180036b01  test    rdx, rdx
0x180036b04  jz      short loc_180036B12
0x180036b06  xor     ecx, ecx; Thread
0x180036b08  call    cs:__imp_SetThreadToken
0x180036b0e  test    eax, eax
0x180036b10  jz      short loc_180036B57
0x180036b12  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180036b19  mov     [rbx], rax
0x180036b1c  cmp     qword ptr [rbx+8], 0
0x180036b21  jz      short loc_180036B37
0x180036b23  mov     rcx, rbx
0x180036b26  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180036b2b  test    al, al
0x180036b2d  jz      short loc_180036B3D
0x180036b2f  mov     qword ptr [rbx+8], 0
0x180036b37  add     rsp, 20h
0x180036b3b  pop     rbx
0x180036b3c  retn
0x180036b3d  call    cs:__imp_GetLastError
0x180036b43  test    eax, eax
0x180036b45  jle     short loc_180036B4F
0x180036b47  movzx   eax, ax
0x180036b4a  or      eax, 80070000h
0x180036b4f  mov     ecx, eax; this
0x180036b51  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180036b56  int     3; Trap to Debugger
0x180036b57  mov     rcx, [rsp+28h]; this
0x180036b5c  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\inc\\RAI"...
0x180036b63  mov     edx, 0BFh; void *
0x180036b68  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
