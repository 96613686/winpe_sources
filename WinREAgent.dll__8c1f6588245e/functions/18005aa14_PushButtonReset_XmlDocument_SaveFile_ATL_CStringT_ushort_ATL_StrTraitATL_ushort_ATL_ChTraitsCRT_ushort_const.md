# PushButtonReset::XmlDocument::SaveFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18005aa14`
- end: `0x18005ab5b`
- name: `?SaveFile@XmlDocument@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800528ac`

## callees

- `0x180005cc0`
- `0x180037344`
- `0x18005a498`
- `0x18005aa14`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005aa2b`
- `OLEAUT32!__imp_SysAllocString` at `0x18005aa2b`

## string_xrefs

- `0x18005aa63`: `base\reset\util\src\xml.cpp`
- `0x18005ab17`: `base\reset\util\src\xml.cpp`
- `0x18005aa4f`: `Failed to allocate path`
- `0x18005aa6a`: `PushButtonReset::XmlDocument::SaveFile`
- `0x18005ab1e`: `PushButtonReset::XmlDocument::SaveFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PushButtonReset::XmlDocument::SaveFile(__int64 a1, const OLECHAR **a2)
{
  BSTR v4; // rax
  __int64 v6; // rax
  int v7; // ebx
  void **v8; // [rsp+40h] [rbp-30h] BYREF
  BSTR v9; // [rsp+48h] [rbp-28h] BYREF
  __int128 v10; // [rsp+50h] [rbp-20h] BYREF
  __int64 v11; // [rsp+60h] [rbp-10h]

  v4 = SysAllocString(*a2);
  v8 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v9 = v4;
  if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v8) )
  {
    v10 = 0;
    LOWORD(v10) = 8;
    *((_QWORD *)&v10 + 1) = *(_QWORD *)((__int64 (__fastcall *)(void ***))v8[4])(&v8);
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    v11 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 528LL))(v6, &v10);
    if ( v7 < 0 )
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v7,
        "PushButtonReset::XmlDocument::SaveFile",
        "base\\reset\\util\\src\\xml.cpp",
        255,
        L"Failed to save document to %s",
        *a2);
    v8 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v9);
    return (unsigned int)v7;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlDocument::SaveFile",
      "base\\reset\\util\\src\\xml.cpp",
      248,
      L"Failed to allocate path");
    v8 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v9);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18005aa14  push    rbp
0x18005aa16  push    rbx
0x18005aa17  push    rsi
0x18005aa18  push    rdi
0x18005aa19  push    r14
0x18005aa1b  mov     rbp, rsp
0x18005aa1e  sub     rsp, 70h
0x18005aa22  mov     rdi, rdx
0x18005aa25  mov     rbx, rcx
0x18005aa28  mov     rcx, [rdx]; psz
0x18005aa2b  call    cs:__imp_SysAllocString
0x18005aa31  lea     r14, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005aa38  mov     [rbp+var_30], r14
0x18005aa3c  mov     [rbp+var_28], rax
0x18005aa40  lea     rcx, [rbp+var_30]
0x18005aa44  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005aa49  cmp     qword ptr [rax], 0
0x18005aa4d  jnz     short loc_18005AA99
0x18005aa4f  lea     rax, aFailedToAlloca_19; "Failed to allocate path"
0x18005aa56  mov     [rsp+70h+var_48], rax
0x18005aa5b  mov     [rsp+70h+var_50], 0F8h
0x18005aa63  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005aa6a  lea     r8, aPushbuttonrese_59; "PushButtonReset::XmlDocument::SaveFile"
0x18005aa71  mov     edx, 8007000Eh
0x18005aa76  mov     ecx, 2
0x18005aa7b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005aa80  nop
0x18005aa81  mov     [rbp+var_30], r14
0x18005aa85  lea     rcx, [rbp+var_28]
0x18005aa89  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005aa8e  nop
0x18005aa8f  mov     eax, 8007000Eh
0x18005aa94  jmp     loc_18005AB50
0x18005aa99  xorps   xmm0, xmm0
0x18005aa9c  xor     esi, esi
0x18005aa9e  movups  [rbp+var_20], xmm0
0x18005aaa2  lea     eax, [rsi+8]
0x18005aaa5  mov     word ptr [rbp+var_20], ax
0x18005aaa9  mov     rax, [rbp+var_30]
0x18005aaad  lea     rcx, [rbp+var_30]
0x18005aab1  mov     rax, [rax+20h]
0x18005aab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aaba  mov     rcx, [rax]
0x18005aabd  mov     qword ptr [rbp+var_20+8], rcx
0x18005aac1  mov     rax, [rbx]
0x18005aac4  mov     rcx, rbx
0x18005aac7  mov     rax, [rax+18h]
0x18005aacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aad0  mov     r8, rax
0x18005aad3  movups  xmm0, [rbp+var_20]
0x18005aad7  movaps  [rbp+var_20], xmm0
0x18005aadb  mov     [rbp+var_10], rsi
0x18005aadf  mov     rcx, [rax]
0x18005aae2  mov     rax, [rcx+210h]
0x18005aae9  lea     rdx, [rbp+var_20]
0x18005aaed  mov     rcx, r8
0x18005aaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aaf5  mov     ebx, eax
0x18005aaf7  test    eax, eax
0x18005aaf9  jns     short loc_18005AB40
0x18005aafb  mov     rcx, [rdi]
0x18005aafe  mov     [rsp+70h+var_40], rcx
0x18005ab03  lea     rax, aFailedToSaveDo; "Failed to save document to %s"
0x18005ab0a  mov     [rsp+70h+var_48], rax
0x18005ab0f  mov     [rsp+70h+var_50], 0FFh
0x18005ab17  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005ab1e  lea     r8, aPushbuttonrese_59; "PushButtonReset::XmlDocument::SaveFile"
0x18005ab25  mov     edx, ebx
0x18005ab27  lea     ecx, [rsi+2]
0x18005ab2a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005ab2f  nop
0x18005ab30  mov     [rbp+var_30], r14
0x18005ab34  lea     rcx, [rbp+var_28]
0x18005ab38  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ab3d  nop
0x18005ab3e  jmp     short loc_18005AB4E
0x18005ab40  mov     [rbp+var_30], r14
0x18005ab44  lea     rcx, [rbp+var_28]
0x18005ab48  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ab4d  nop
0x18005ab4e  mov     eax, ebx
0x18005ab50  add     rsp, 70h
0x18005ab54  pop     r14
0x18005ab56  pop     rdi
0x18005ab57  pop     rsi
0x18005ab58  pop     rbx
0x18005ab59  pop     rbp
0x18005ab5a  retn
```
