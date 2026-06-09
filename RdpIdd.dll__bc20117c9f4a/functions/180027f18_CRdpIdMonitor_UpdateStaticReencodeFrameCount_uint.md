# CRdpIdMonitor::UpdateStaticReencodeFrameCount(uint)

- ea: `0x180027f18`
- end: `0x180027fb6`
- name: `?UpdateStaticReencodeFrameCount@CRdpIdMonitor@@QEAAXI@Z`
- size: `158`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b104`
- `0x180025f90`

## callees

- `0x18001ddf4`
- `0x180027f18`
- `0x18003f010`

## string_xrefs

- `0x180027f90`: `IddCxSwapChainUpdateStaticDesktopReencodeFrameCount failed`

## pseudocode

```c
void __fastcall CRdpIdMonitor::UpdateStaticReencodeFrameCount(CRdpIdMonitor *this, unsigned int a2)
{
  __int64 v2; // r8
  __int64 v3; // rdx
  unsigned int v4; // eax
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = a2;
  v3 = *((_QWORD *)this + 31);
  if ( v3 )
  {
    if ( IddClientVersionHigherThanFramework && (unsigned int)IddFunctionCount <= 0x26 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, wchar_t *))(WdfFunctions_02025 + 2128))(
        WdfDriverGlobals,
        *(_QWORD *)WdfDriverGlobals,
        IddFrameworkExtensionName);
      v4 = 0;
    }
    else
    {
      v4 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))qword_180057C40)(
             IddDriverGlobals,
             *(_QWORD *)(v3 + 32),
             v2);
    }
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x6CA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v4,
      (int)"IddCxSwapChainUpdateStaticDesktopReencodeFrameCount failed",
      v5);
  }
}

```

## disassembly

```asm
0x180027f18  sub     rsp, 38h
0x180027f1c  mov     r8d, edx
0x180027f1f  mov     rdx, [rcx+0F8h]
0x180027f26  test    rdx, rdx
0x180027f29  jz      loc_180027FB0
0x180027f2f  cmp     cs:IddClientVersionHigherThanFramework, 0
0x180027f36  jz      short loc_180027F74
0x180027f38  mov     r9d, 26h ; '&'
0x180027f3e  cmp     cs:IddFunctionCount, r9d
0x180027f45  ja      short loc_180027F74
0x180027f47  mov     rax, cs:WdfFunctions_02025
0x180027f4e  mov     rcx, cs:WdfDriverGlobals
0x180027f55  mov     r8, cs:IddFrameworkExtensionName
0x180027f5c  mov     byte ptr [rsp+38h+var_18], 0
0x180027f61  mov     rax, [rax+850h]
0x180027f68  mov     rdx, [rcx]
0x180027f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f70  xor     eax, eax
0x180027f72  jmp     short loc_180027F8B
0x180027f74  mov     rdx, [rdx+20h]
0x180027f78  mov     rcx, cs:IddDriverGlobals
0x180027f7f  mov     rax, cs:qword_180057C40
0x180027f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f8b  mov     rcx, [rsp+38h]; this
0x180027f90  lea     rdx, aIddcxswapchain; "IddCxSwapChainUpdateStaticDesktopReenco"...
0x180027f97  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180027f9c  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027fa3  mov     edx, 6CAh; void *
0x180027fa8  mov     r9d, eax; char *
0x180027fab  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027fb0  add     rsp, 38h
0x180027fb4  retn
```
