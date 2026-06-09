# LegacyActivationShim::Util::GetCLRMetaHost(ICLRMetaHost * *)

- ea: `0x140002dfc`
- end: `0x140002e87`
- name: `?GetCLRMetaHost@Util@LegacyActivationShim@@YAJPEAPEAUICLRMetaHost@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *this, struct ICLRMetaHost **, __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002c50`
- `0x140002f14`

## callees

- `0x140002bd8`
- `0x140002dfc`
- `0x140006590`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::GetCLRMetaHost(
        LegacyActivationShim::Util *this,
        struct ICLRMetaHost **a2,
        __int64 a3,
        void **a4)
{
  struct ICLRMetaHost *v4; // rax
  unsigned int v5; // ebx
  __int64 result; // rax
  struct _GUID v8; // [rsp+38h] [rbp+10h] BYREF

  v4 = LegacyActivationShim::Util::g_pCLRMetaHost;
  v5 = 0;
  if ( !LegacyActivationShim::Util::g_pCLRMetaHost )
  {
    *(_QWORD *)&v8.Data1 = 0;
    result = LegacyActivationShim::Util::CallCLRCreateInstance(
               (LegacyActivationShim::Util *)&CLSID_CLRMetaHost,
               (HINSTANCE *)&IID_ICLRMetaHost,
               &v8,
               a4);
    v5 = result;
    if ( (int)result < 0 )
      return result;
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&LegacyActivationShim::Util::g_pCLRMetaHost,
           *(signed __int64 *)&v8.Data1,
           0) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v8.Data1 + 16LL))(*(_QWORD *)&v8.Data1);
      v4 = LegacyActivationShim::Util::g_pCLRMetaHost;
    }
    else
    {
      v4 = LegacyActivationShim::Util::g_pCLRMetaHost;
      LegacyActivationShim::Util::g_hCLRMetaHost = (__int64)LegacyActivationShim::Util::g_pCLRMetaHost;
      byte_14000A0D8 = 1;
    }
  }
  *(_QWORD *)this = v4;
  return v5;
}

```

## disassembly

```asm
0x140002dfc  mov     [rsp+arg_0], rbx
0x140002e01  push    rdi
0x140002e02  sub     rsp, 20h
0x140002e06  mov     rax, cs:?g_pCLRMetaHost@Util@LegacyActivationShim@@3PEAUICLRMetaHost@@EA; ICLRMetaHost * LegacyActivationShim::Util::g_pCLRMetaHost
0x140002e0d  xor     ebx, ebx
0x140002e0f  mov     rdi, rcx
0x140002e12  test    rax, rax
0x140002e15  jnz     short loc_140002E77
0x140002e17  and     qword ptr [rsp+28h+arg_8.Data1], rbx
0x140002e1c  lea     r8, [rsp+28h+arg_8]; struct _GUID *
0x140002e21  lea     rdx, IID_ICLRMetaHost; struct _GUID *
0x140002e28  lea     rcx, CLSID_CLRMetaHost; this
0x140002e2f  call    ?CallCLRCreateInstance@Util@LegacyActivationShim@@YAJAEBU_GUID@@0PEAPEAX@Z; LegacyActivationShim::Util::CallCLRCreateInstance(_GUID const &,_GUID const &,void * *)
0x140002e34  mov     ebx, eax
0x140002e36  test    eax, eax
0x140002e38  js      short loc_140002E7C
0x140002e3a  mov     rcx, qword ptr [rsp+28h+arg_8.Data1]
0x140002e3f  xor     eax, eax
0x140002e41  lock cmpxchg cs:?g_pCLRMetaHost@Util@LegacyActivationShim@@3PEAUICLRMetaHost@@EA, rcx; ICLRMetaHost * LegacyActivationShim::Util::g_pCLRMetaHost
0x140002e4a  jnz     short loc_140002E63
0x140002e4c  mov     rax, cs:?g_pCLRMetaHost@Util@LegacyActivationShim@@3PEAUICLRMetaHost@@EA; ICLRMetaHost * LegacyActivationShim::Util::g_pCLRMetaHost
0x140002e53  mov     cs:?g_hCLRMetaHost@Util@LegacyActivationShim@@3V?$ZeroInitGlobalReleaseHolder@PEAUICLRMetaHost@@@12@A, rax; LegacyActivationShim::Util::ZeroInitGlobalReleaseHolder<ICLRMetaHost *> LegacyActivationShim::Util::g_hCLRMetaHost
0x140002e5a  mov     cs:byte_14000A0D8, 1
0x140002e61  jmp     short loc_140002E77
0x140002e63  mov     rax, [rcx]
0x140002e66  mov     rax, [rax+10h]
0x140002e6a  call    cs:__guard_dispatch_icall_fptr
0x140002e70  mov     rax, cs:?g_pCLRMetaHost@Util@LegacyActivationShim@@3PEAUICLRMetaHost@@EA; ICLRMetaHost * LegacyActivationShim::Util::g_pCLRMetaHost
0x140002e77  mov     [rdi], rax
0x140002e7a  mov     eax, ebx
0x140002e7c  mov     rbx, [rsp+28h+arg_0]
0x140002e81  add     rsp, 20h
0x140002e85  pop     rdi
0x140002e86  retn
```
