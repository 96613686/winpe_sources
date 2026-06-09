# GetOfflineStackFromWindir(ushort const *,ushort * *)

- ea: `0x180073ad4`
- end: `0x180073db6`
- name: `?GetOfflineStackFromWindir@@YAJPEBGPEAPEAG@Z`
- size: `738`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180073de0`

## callees

- `0x180026e00`
- `0x18002d2b0`
- `0x1800423e0`
- `0x18004f580`
- `0x180073ad4`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180073b73`
- `KERNEL32!GetLastError` at `0x180073b73`
- `KERNEL32!GetProcAddress` at `0x180073b57`
- `KERNEL32!GetProcAddress` at `0x180073c31`
- `KERNEL32!GetProcAddress` at `0x180073c52`
- `KERNEL32!GetProcAddress` at `0x180073c7c`
- `KERNEL32!GetProcAddress` at `0x180073ca6`
- `KERNEL32!GetProcAddress` at `0x180073b57`
- `KERNEL32!GetProcAddress` at `0x180073c31`
- `KERNEL32!GetProcAddress` at `0x180073c52`
- `KERNEL32!GetProcAddress` at `0x180073c7c`
- `KERNEL32!GetProcAddress` at `0x180073ca6`
- `KERNEL32!FreeLibrary` at `0x180073bc4`
- `KERNEL32!FreeLibrary` at `0x180073bc4`

## string_xrefs

- `0x180073c75`: `SssGetServicingStackFilePathLength`
- `0x180073c9f`: `SssGetServicingStackFilePath`
- `0x180073d43`: `wrpint.dll`
- `0x180073d85`: `wrpint.dll`

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
0x180073ad4  mov     [rsp-8+arg_10], rbx
0x180073ad9  mov     [rsp-8+arg_18], rsi
0x180073ade  push    rbp
0x180073adf  push    rdi
0x180073ae0  push    r14
0x180073ae2  lea     rbp, [rsp-47h]
0x180073ae7  sub     rsp, 0C0h
0x180073aee  mov     rax, cs:__security_cookie
0x180073af5  xor     rax, rsp
0x180073af8  mov     [rbp+57h+var_20], rax
0x180073afc  mov     r14, rdx
0x180073aff  mov     rsi, rcx
0x180073b02  xor     edx, edx; Val
0x180073b04  lea     rcx, [rbp+57h+var_70]; void *
0x180073b08  xorps   xmm0, xmm0
0x180073b0b  movups  [rbp+57h+var_88], xmm0
0x180073b0f  lea     r8d, [rdx+40h]; Size
0x180073b13  call    memset
0x180073b18  xor     edi, edi
0x180073b1a  mov     [rbp+57h+var_28], 0
0x180073b21  lea     r8, ?vhSsShimDll@@3PEAUHINSTANCE__@@EA; HINSTANCE *
0x180073b28  mov     [rbp+57h+var_90], rdi
0x180073b2c  mov     rdx, rsi; wchar_t *
0x180073b2f  mov     [rbp+57h+var_30], 0
0x180073b37  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x180073b3e  call    ?CbsLoadSssFromTargetImage@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUHINSTANCE__@@@Z; CbsOfflineUtil::CbsLoadSssFromTargetImage(wchar_t const *,HINSTANCE__ * *)
0x180073b43  mov     ebx, eax
0x180073b45  test    eax, eax
0x180073b47  js      short loc_180073BA0
0x180073b49  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073b50  lea     rdx, aSssbindservici; "SssBindServicingStack"
0x180073b57  call    cs:__imp_GetProcAddress
0x180073b5e  nop     dword ptr [rax+rax+00h]
0x180073b63  mov     cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, rax; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073b6a  test    rax, rax
0x180073b6d  jnz     loc_180073C23
0x180073b73  call    cs:__imp_GetLastError
0x180073b7a  nop     dword ptr [rax+rax+00h]
0x180073b7f  mov     ebx, eax
0x180073b81  test    eax, eax
0x180073b83  jle     short loc_180073B8E
0x180073b85  movzx   ebx, ax
0x180073b88  or      ebx, 80070000h
0x180073b8e  test    ebx, ebx
0x180073b90  jns     short loc_180073BFC
0x180073b92  test    rdi, rdi
0x180073b95  jz      short loc_180073BA0
0x180073b97  lea     rcx, [rdi-8]; void *
0x180073b9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073ba0  mov     rax, cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073ba7  test    rax, rax
0x180073baa  jz      short loc_180073BB8
0x180073bac  mov     rcx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bb8  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180073bbf  test    rcx, rcx
0x180073bc2  jz      short loc_180073BD0
0x180073bc4  call    cs:__imp_FreeLibrary
0x180073bcb  nop     dword ptr [rax+rax+00h]
0x180073bd0  mov     cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, 0; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073bdb  mov     cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA, 0; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073be6  mov     cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA, 0; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073bf1  mov     cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA, 0; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073bfc  mov     eax, ebx
0x180073bfe  mov     rcx, [rbp+57h+var_20]
0x180073c02  xor     rcx, rsp; StackCookie
0x180073c05  call    __security_check_cookie
0x180073c0a  lea     r11, [rsp+0D0h+var_10]
0x180073c12  mov     rbx, [r11+30h]
0x180073c16  mov     rsi, [r11+38h]
0x180073c1a  mov     rsp, r11
0x180073c1d  pop     r14
0x180073c1f  pop     rdi
0x180073c20  pop     rbp
0x180073c21  retn
0x180073c23  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073c2a  lea     rdx, aSsspreloaddown; "SssPreloadDownlevelDependencies"
0x180073c31  call    cs:__imp_GetProcAddress
0x180073c38  nop     dword ptr [rax+rax+00h]
0x180073c3d  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073c44  lea     rdx, aSssreleaseserv; "SssReleaseServicingStack"
0x180073c4b  mov     cs:?vpfnSssPreloadDownlevelDependencies@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA, rax; long (*vpfnSssPreloadDownlevelDependencies)(ulong,_SSS_SERVICING_STACK_COOKIE,ulong *)
0x180073c52  call    cs:__imp_GetProcAddress
0x180073c59  nop     dword ptr [rax+rax+00h]
0x180073c5e  mov     cs:?vpfnSssReleaseServicingStack@@3P6AXU_SSS_SERVICING_STACK_COOKIE@@@ZEA, rax; void (*vpfnSssReleaseServicingStack)(_SSS_SERVICING_STACK_COOKIE)
0x180073c65  test    rax, rax
0x180073c68  jz      loc_180073B73
0x180073c6e  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073c75  lea     rdx, aSssgetservicin; "SssGetServicingStackFilePathLength"
0x180073c7c  call    cs:__imp_GetProcAddress
0x180073c83  nop     dword ptr [rax+rax+00h]
0x180073c88  mov     cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA, rax; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073c8f  test    rax, rax
0x180073c92  jz      loc_180073B73
0x180073c98  mov     rcx, cs:?vhSsShimDll@@3PEAUHINSTANCE__@@EA; hModule
0x180073c9f  lea     rdx, aSssgetservicin_0; "SssGetServicingStackFilePath"
0x180073ca6  call    cs:__imp_GetProcAddress
0x180073cad  nop     dword ptr [rax+rax+00h]
0x180073cb2  mov     cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA, rax; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073cb9  test    rax, rax
0x180073cbc  jz      loc_180073B73
0x180073cc2  lea     rax, [rbp+57h+var_88]
0x180073cc6  mov     qword ptr [rbp+57h+var_88], 10h
0x180073cce  mov     [rbp+57h+var_50], rax
0x180073cd2  lea     r8, [rbp+57h+var_28]
0x180073cd6  mov     rax, cs:?vpfnSssBindServicingStack@@3P6AJPEBU_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS@@PEAU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA; long (*vpfnSssBindServicingStack)(_SSS_BIND_SERVICING_STACK_INPUT_PARAMETERS const *,_SSS_SERVICING_STACK_COOKIE *,ulong *)
0x180073cdd  lea     rdx, ?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073ce4  lea     rcx, [rbp+57h+var_70]
0x180073ce8  mov     qword ptr [rbp+57h+var_88+8], rsi
0x180073cec  mov     [rbp+57h+var_70], 40h ; '@'
0x180073cf3  mov     [rbp+57h+var_6C], 684h
0x180073cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cff  mov     ebx, eax
0x180073d01  test    eax, eax
0x180073d03  jnz     loc_180073B8E
0x180073d09  mov     rax, cs:?vpfnSssPreloadDownlevelDependencies@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEAK@ZEA; long (*vpfnSssPreloadDownlevelDependencies)(ulong,_SSS_SERVICING_STACK_COOKIE,ulong *)
0x180073d10  test    rax, rax
0x180073d13  jz      short loc_180073D31
0x180073d15  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073d1c  lea     ecx, [rbx+1]
0x180073d1f  xor     r8d, r8d
0x180073d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d27  mov     ebx, eax
0x180073d29  test    eax, eax
0x180073d2b  jnz     loc_180073B8E
0x180073d31  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073d38  lea     r9, [rbp+57h+var_30]
0x180073d3c  mov     rax, cs:?vpfnSssGetServicingStackFilePathLength@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBGPEA_K@ZEA; long (*vpfnSssGetServicingStackFilePathLength)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64 *)
0x180073d43  lea     r8, aWrpintDll; "wrpint.dll"
0x180073d4a  xor     ecx, ecx
0x180073d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d51  mov     ebx, eax
0x180073d53  test    eax, eax
0x180073d55  jnz     loc_180073B8E
0x180073d5b  mov     rdx, [rbp+57h+var_30]
0x180073d5f  lea     rcx, [rbp+57h+var_90]
0x180073d63  call    SczAlloc
0x180073d68  mov     rdi, [rbp+57h+var_90]
0x180073d6c  mov     ebx, eax
0x180073d6e  test    eax, eax
0x180073d70  jnz     loc_180073B8E
0x180073d76  mov     r9, [rbp+57h+var_30]
0x180073d7a  lea     rax, [rbp+57h+var_30]
0x180073d7e  mov     rdx, cs:?vShimCookie@@3U_SSS_SERVICING_STACK_COOKIE@@A; _SSS_SERVICING_STACK_COOKIE vShimCookie
0x180073d85  lea     r8, aWrpintDll; "wrpint.dll"
0x180073d8c  mov     [rsp+0D0h+var_A8], rax
0x180073d91  xor     ecx, ecx
0x180073d93  mov     rax, cs:?vpfnSssGetServicingStackFilePath@@3P6AJKU_SSS_SERVICING_STACK_COOKIE@@PEBG_KQEAGPEA_K@ZEA; long (*vpfnSssGetServicingStackFilePath)(ulong,_SSS_SERVICING_STACK_COOKIE,ushort const *,unsigned __int64,ushort * const,unsigned __int64 *)
0x180073d9a  mov     [rsp+0D0h+var_B0], rdi
0x180073d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073da4  mov     ebx, eax
0x180073da6  test    eax, eax
0x180073da8  jnz     loc_180073B8E
0x180073dae  mov     [r14], rdi
0x180073db1  jmp     loc_180073BFC
```
