# GetOfflineStackFromWindir(ushort const *,ushort * *)

- ea: `0x180073d34`
- end: `0x180074016`
- name: `?GetOfflineStackFromWindir@@YAJPEBGPEAPEAG@Z`
- size: `738`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180074040`

## callees

- `0x180022ef0`
- `0x1800293a0`
- `0x18003f5f0`
- `0x18004c460`
- `0x180073d34`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180073dd3`
- `KERNEL32!GetLastError` at `0x180073dd3`
- `KERNEL32!GetProcAddress` at `0x180073db7`
- `KERNEL32!GetProcAddress` at `0x180073e91`
- `KERNEL32!GetProcAddress` at `0x180073eb2`
- `KERNEL32!GetProcAddress` at `0x180073edc`
- `KERNEL32!GetProcAddress` at `0x180073f06`
- `KERNEL32!GetProcAddress` at `0x180073db7`
- `KERNEL32!GetProcAddress` at `0x180073e91`
- `KERNEL32!GetProcAddress` at `0x180073eb2`
- `KERNEL32!GetProcAddress` at `0x180073edc`
- `KERNEL32!GetProcAddress` at `0x180073f06`
- `KERNEL32!FreeLibrary` at `0x180073e24`
- `KERNEL32!FreeLibrary` at `0x180073e24`

## string_xrefs

- `0x180073ed5`: `SssGetServicingStackFilePathLength`
- `0x180073eff`: `SssGetServicingStackFilePath`
- `0x180073fa3`: `wrpint.dll`
- `0x180073fe5`: `wrpint.dll`

## pseudocode

```c
__int64 __fastcall GetOfflineStackFromWindir(wchar_t *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  signed int SssFromTargetImage; // ebx
  signed int LastError; // eax
  const struct std::nothrow_t *v7; // rdx
  signed int v9; // eax
  unsigned __int16 *v10; // [rsp+40h] [rbp-39h] BYREF
  __int128 v11; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v12[8]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+27h] BYREF
  int v14; // [rsp+A8h] [rbp+2Fh] BYREF

  v11 = 0;
  memset(v12, 0, sizeof(v12));
  v4 = 0;
  v14 = 0;
  v10 = 0;
  v13 = 0;
  SssFromTargetImage = CbsOfflineUtil::CbsLoadSssFromTargetImage((CbsOfflineUtil *)&vCbsOfflineUtil, a1, &vhSsShimDll);
  if ( SssFromTargetImage < 0 )
  {
LABEL_8:
    if ( vpfnSssReleaseServicingStack )
      vpfnSssReleaseServicingStack(vShimCookie);
    if ( vhSsShimDll )
      FreeLibrary(vhSsShimDll);
    vpfnSssBindServicingStack = 0;
    vpfnSssReleaseServicingStack = 0;
    vpfnSssGetServicingStackFilePath = 0;
    vpfnSssGetServicingStackFilePathLength = 0;
    return (unsigned int)SssFromTargetImage;
  }
  vpfnSssBindServicingStack = (int (*)(const struct _SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS *, struct _SSS_SERVICING_STACK_COOKIE *, unsigned int *))GetProcAddress(vhSsShimDll, "SssBindServicingStack");
  if ( vpfnSssBindServicingStack
    && (vpfnSssPreloadDownlevelDependencies = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                vhSsShimDll,
                                                                                                "SssPreloadDownlevelDependencies"),
        (vpfnSssReleaseServicingStack = (__int64 (__fastcall *)(_QWORD))GetProcAddress(
                                                                          vhSsShimDll,
                                                                          "SssReleaseServicingStack")) != 0)
    && (vpfnSssGetServicingStackFilePathLength = (int (__high *)(unsigned int, struct _SSS_SERVICING_STACK_COOKIE, const unsigned __int16 *, unsigned __int64 *))GetProcAddress(vhSsShimDll, "SssGetServicingStackFilePathLength")) != 0
    && (vpfnSssGetServicingStackFilePath = (int (__high *)(unsigned int, struct _SSS_SERVICING_STACK_COOKIE, const unsigned __int16 *, unsigned __int64, unsigned __int16 *const, unsigned __int64 *))GetProcAddress(vhSsShimDll, "SssGetServicingStackFilePath")) != 0 )
  {
    *(_QWORD *)&v11 = 16;
    v12[4] = &v11;
    *((_QWORD *)&v11 + 1) = a1;
    v12[0] = 0x68400000040LL;
    SssFromTargetImage = ((__int64 (__fastcall *)(_QWORD *, void *, int *))vpfnSssBindServicingStack)(
                           v12,
                           &vShimCookie,
                           &v14);
    if ( !SssFromTargetImage
      && (!vpfnSssPreloadDownlevelDependencies
       || (SssFromTargetImage = vpfnSssPreloadDownlevelDependencies(
                                  (unsigned int)(SssFromTargetImage + 1),
                                  vShimCookie,
                                  0)) == 0) )
    {
      SssFromTargetImage = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, __int64 *))vpfnSssGetServicingStackFilePathLength)(
                             0,
                             vShimCookie,
                             L"wrpint.dll",
                             &v13);
      if ( !SssFromTargetImage )
      {
        v9 = SczAlloc(&v10, v13);
        v4 = v10;
        SssFromTargetImage = v9;
        if ( !v9 )
        {
          SssFromTargetImage = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, __int64, unsigned __int16 *, __int64 *))vpfnSssGetServicingStackFilePath)(
                                 0,
                                 vShimCookie,
                                 L"wrpint.dll",
                                 v13,
                                 v10,
                                 &v13);
          if ( !SssFromTargetImage )
          {
            *a2 = v4;
            return (unsigned int)SssFromTargetImage;
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    SssFromTargetImage = LastError;
    if ( LastError > 0 )
      SssFromTargetImage = (unsigned __int16)LastError | 0x80070000;
  }
  if ( SssFromTargetImage < 0 )
  {
    if ( v4 )
      operator delete(v4 - 4, v7);
    goto LABEL_8;
  }
  return (unsigned int)SssFromTargetImage;
}

```

## disassembly

```asm
0x180073d34  mov     [rsp-8+arg_10], rbx
0x180073d39  mov     [rsp-8+arg_18], rsi
0x180073d3e  push    rbp
0x180073d3f  push    rdi
0x180073d40  push    r14
0x180073d42  lea     rbp, [rsp-47h]
0x180073d47  sub     rsp, 0C0h
0x180073d4e  mov     rax, cs:__security_cookie
0x180073d55  xor     rax, rsp
0x180073d58  mov     [rbp+57h+var_20], rax
0x180073d5c  mov     r14, rdx
0x180073d5f  mov     rsi, rcx
0x180073d62  xor     edx, edx; Val
0x180073d64  lea     rcx, [rbp+57h+var_70]; void *
0x180073d68  xorps   xmm0, xmm0
0x180073d6b  movups  [rbp+57h+var_88], xmm0
0x180073d6f  lea     r8d, [rdx+40h]; Size
0x180073d73  call    memset
0x180073d78  xor     edi, edi
0x180073d7a  mov     [rbp+57h+var_28], 0
0x180073d81  lea     r8, ?vhSsShimDll@@3PEAUHINSTANCE__@@EA; HINSTANCE *
0x180073d88  mov     [rbp+57h+var_90], rdi
0x180073d8c  mov     rdx, rsi; wchar_t *
0x180073d8f  mov     [rbp+57h+var_30], 0
0x180073d97  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x180073d9e  call    ?CbsLoadSssFromTargetImage@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUHINSTANCE__@@@Z; CbsOfflineUtil::CbsLoadSssFromTargetImage(wchar_t const *,HINSTANCE__ * *)
0x180073da3  mov     ebx, eax
0x180073da5  test    eax, eax
0x180073da7  js      short loc_180073E00
0x180073da9  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073db0  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x180073db7  call    cs:__imp_GetProcAddress
0x180073dbe  nop     dword ptr [rax+rax+00h]
0x180073dc3  mov     cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, rax; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073dca  test    rax, rax
0x180073dcd  jnz     loc_180073E83
0x180073dd3  call    cs:__imp_GetLastError
0x180073dda  nop     dword ptr [rax+rax+00h]
0x180073ddf  mov     ebx, eax
0x180073de1  test    eax, eax
0x180073de3  jle     short loc_180073DEE
0x180073de5  movzx   ebx, ax
0x180073de8  or      ebx, 80070000h
0x180073dee  test    ebx, ebx
0x180073df0  jns     short loc_180073E5C
0x180073df2  test    rdi, rdi
0x180073df5  jz      short loc_180073E00
0x180073df7  lea     rcx, [rdi-8]; void *
0x180073dfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073e00  mov     rax, cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073e07  test    rax, rax
0x180073e0a  jz      short loc_180073E18
0x180073e0c  mov     rcx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e18  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180073e1f  test    rcx, rcx
0x180073e22  jz      short loc_180073E30
0x180073e24  call    cs:__imp_FreeLibrary
0x180073e2b  nop     dword ptr [rax+rax+00h]
0x180073e30  mov     cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, 0; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073e3b  mov     cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA, 0; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073e46  mov     cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA, 0; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073e51  mov     cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA, 0; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073e5c  mov     eax, ebx
0x180073e5e  mov     rcx, [rbp+57h+var_20]
0x180073e62  xor     rcx, rsp; StackCookie
0x180073e65  call    __security_check_cookie
0x180073e6a  lea     r11, [rsp+0D0h+var_10]
0x180073e72  mov     rbx, [r11+30h]
0x180073e76  mov     rsi, [r11+38h]
0x180073e7a  mov     rsp, r11
0x180073e7d  pop     r14
0x180073e7f  pop     rdi
0x180073e80  pop     rbp
0x180073e81  retn
0x180073e83  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073e8a  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x180073e91  call    cs:__imp_GetProcAddress
0x180073e98  nop     dword ptr [rax+rax+00h]
0x180073e9d  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073ea4  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180073eab  mov     cs:?vpfnSssPreloadDownlevelDependencies@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, rax; long (*vpfnSssPreloadDownlevelDependencies)(ulong,_SSS_SERVICING_STACK_COOKIE,ulong *)
0x180073eb2  call    cs:__imp_GetProcAddress
0x180073eb9  nop     dword ptr [rax+rax+00h]
0x180073ebe  mov     cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA, rax; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073ec5  test    rax, rax
0x180073ec8  jz      loc_180073DD3
0x180073ece  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073ed5  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180073edc  call    cs:__imp_GetProcAddress
0x180073ee3  nop     dword ptr [rax+rax+00h]
0x180073ee8  mov     cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA, rax; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073eef  test    rax, rax
0x180073ef2  jz      loc_180073DD3
0x180073ef8  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073eff  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x180073f06  call    cs:__imp_GetProcAddress
0x180073f0d  nop     dword ptr [rax+rax+00h]
0x180073f12  mov     cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA, rax; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073f19  test    rax, rax
0x180073f1c  jz      loc_180073DD3
0x180073f22  lea     rax, [rbp+57h+var_88]
0x180073f26  mov     qword ptr [rbp+57h+var_88], 10h
0x180073f2e  mov     [rbp+57h+var_50], rax
0x180073f32  lea     r8, [rbp+57h+var_28]
0x180073f36  mov     rax, cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073f3d  lea     rdx, ?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073f44  lea     rcx, [rbp+57h+var_70]
0x180073f48  mov     qword ptr [rbp+57h+var_88+8], rsi
0x180073f4c  mov     [rbp+57h+var_70], 40h ; '@'
0x180073f53  mov     [rbp+57h+var_6C], 684h
0x180073f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f5f  mov     ebx, eax
0x180073f61  test    eax, eax
0x180073f63  jnz     loc_180073DEE
0x180073f69  mov     rax, cs:?vpfnSssPreloadDownlevelDependencies@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA; long (*vpfnSssPreloadDownlevelDependencies)(ulong,_SSS_SERVICING_STACK_COOKIE,ulong *)
0x180073f70  test    rax, rax
0x180073f73  jz      short loc_180073F91
0x180073f75  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073f7c  lea     ecx, [rbx+1]
0x180073f7f  xor     r8d, r8d
0x180073f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f87  mov     ebx, eax
0x180073f89  test    eax, eax
0x180073f8b  jnz     loc_180073DEE
0x180073f91  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073f98  lea     r9, [rbp+57h+var_30]
0x180073f9c  mov     rax, cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073fa3  lea     r8, aWrpintDll; "wrpint.dll"
0x180073faa  xor     ecx, ecx
0x180073fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fb1  mov     ebx, eax
0x180073fb3  test    eax, eax
0x180073fb5  jnz     loc_180073DEE
0x180073fbb  mov     rdx, [rbp+57h+var_30]
0x180073fbf  lea     rcx, [rbp+57h+var_90]
0x180073fc3  call    SczAlloc
0x180073fc8  mov     rdi, [rbp+57h+var_90]
0x180073fcc  mov     ebx, eax
0x180073fce  test    eax, eax
0x180073fd0  jnz     loc_180073DEE
0x180073fd6  mov     r9, [rbp+57h+var_30]
0x180073fda  lea     rax, [rbp+57h+var_30]
0x180073fde  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073fe5  lea     r8, aWrpintDll; "wrpint.dll"
0x180073fec  mov     [rsp+0D0h+var_A8], rax
0x180073ff1  xor     ecx, ecx
0x180073ff3  mov     rax, cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073ffa  mov     [rsp+0D0h+var_B0], rdi
0x180073fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074004  mov     ebx, eax
0x180074006  test    eax, eax
0x180074008  jnz     loc_180073DEE
0x18007400e  mov     [r14], rdi
0x180074011  jmp     loc_180073E5C
```
