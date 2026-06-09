# Windows::WCP::Implementation::Rtl::DecompressManifest(ulong,Windows::Auto<_LBLOB> *,ulong *)

- ea: `0x18001c300`
- end: `0x18001c5a6`
- name: `?DecompressManifest@Rtl@Implementation@WCP@Windows@@YAJKPEAV?$Auto@U_LBLOB@@@4@PEAK@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c5b0`

## callees

- `0x180009820`
- `0x18000c890`
- `0x18000ca60`
- `0x18000cc90`
- `0x1800186e4`
- `0x180018f54`
- `0x18001c300`
- `0x180021f78`
- `0x18002203c`
- `0x18002d2b0`
- `0x18006e708`
- `0x18006e780`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c4ea`
- `KERNEL32!GetLastError` at `0x18001c580`
- `KERNEL32!GetLastError` at `0x18001c4ea`
- `KERNEL32!GetLastError` at `0x18001c580`
- `ntdll!RtlRaiseStatus` at `0x18001c4d4`
- `ntdll!RtlRaiseStatus` at `0x18001c599`
- `ntdll!RtlRaiseStatus` at `0x18001c4d4`
- `ntdll!RtlRaiseStatus` at `0x18001c599`

## string_xrefs

- `0x18001c32e`: `onecore\base\wcp\manifestcompression\manifest_compression.cpp`
- `0x18001c403`: `onecore\base\wcp\manifestcompression\manifest_compression.cpp`
- `0x18001c35d`: `Not-null check failed: pManifestContents`
- `0x18001c348`: `Windows::WCP::Implementation::Rtl::DecompressManifest`
- `0x18001c41d`: `Windows::WCP::Implementation::Rtl::DecompressManifest`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::DecompressManifest(
        __int64 a1,
        Windows::WCP::Implementation::Rtl *a2,
        _DWORD *a3)
{
  void *v5; // rdx
  Windows::Rtl *v6; // rcx
  _DWORD *v7; // r8
  int Dictionary; // ebx
  Windows::Rtl *v9; // rcx
  struct _LBLOB *v10; // r8
  int v11; // ebx
  NTSTATUS NtStatus; // eax
  signed int LastError; // eax
  struct Windows::Rtl::AutoDeltaBlob *v14; // [rsp+28h] [rbp-58h]
  unsigned int v15[4]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+40h] [rbp-40h]
  const char *v17; // [rsp+48h] [rbp-38h]
  _QWORD v18[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+60h] [rbp-20h]
  unsigned int v20; // [rsp+68h] [rbp-18h] BYREF

  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    v16 = 134;
    *(_QWORD *)v15 = "onecore\\base\\wcp\\manifestcompression\\manifest_compression.cpp";
    *(_QWORD *)&v15[2] = "Windows::WCP::Implementation::Rtl::DecompressManifest";
    v17 = "Not-null check failed: pManifestContents";
    RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( a3 )
    *a3 = 0;
  if ( Windows::WCP::Implementation::Rtl::IsManifestCompressed(a2, a2) )
  {
    Dictionary = Windows::Rtl::InitializeDeltaCompressor(v6, v5);
    if ( Dictionary >= 0 )
    {
      *(_OWORD *)v15 = 0;
      v16 = 0;
      Dictionary = LoadDictionary(1, v15);
      if ( Dictionary >= 0 )
      {
        v18[1] = 0;
        v18[0] = 0;
        v19 = 0;
        v11 = Windows::Rtl::DeltaDecompressBuffer(
                v9,
                (unsigned int)v15,
                v10,
                (unsigned __int64)a2,
                (struct _LBLOB *)v18,
                v14,
                *(struct Windows::Rtl::AutoDeltaBlob **)v15);
        if ( v11 < 0 )
        {
          v16 = 184;
          *(_QWORD *)v15 = "onecore\\base\\wcp\\manifestcompression\\manifest_compression.cpp";
          v17 = 0;
          *(_QWORD *)&v15[2] = "Windows::WCP::Implementation::Rtl::DecompressManifest";
          RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v11);
          Windows::Rtl::AutoDeltaBlob::Close((Windows::Rtl::AutoDeltaBlob *)v18);
          return (unsigned int)v11;
        }
        Dictionary = Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Assign(a2, v18);
        if ( Dictionary >= 0 )
        {
          if ( v19 )
          {
            if ( !qword_1800D2E08 )
            {
              v16 = 117;
              *(_QWORD *)v15 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
              v17 = "Not-null check failed: g_pfnDeltaFree";
              *(_QWORD *)&v15[2] = "Windows::Rtl::AutoDeltaBlob::Close";
              v20 = -1073741811;
              RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
              NtStatus = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v20);
              RtlRaiseStatus(NtStatus);
            }
            if ( !(unsigned int)((__int64 (*)(void))qword_1800D2E08)() )
            {
              if ( GetLastError() )
              {
                LastError = GetLastError();
                if ( !LastError )
                  RtlRaiseStatus(-1073741595);
              }
              else
              {
                LastError = 14077;
              }
              v16 = 118;
              *(_QWORD *)v15 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
              *(_QWORD *)&v15[2] = "Windows::Rtl::AutoDeltaBlob::Close";
              v17 = "g_pfnDeltaFree(t.Buffer)";
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              v20 = ConvertHResultToNtStatus((unsigned int)LastError);
              RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v20);
              Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn((Windows::ErrorHandling::Rtl::CVoidRaiseFrame *)&v20);
            }
          }
          return 0;
        }
        Windows::Rtl::AutoDeltaBlob::Close((Windows::Rtl::AutoDeltaBlob *)v18);
      }
    }
    return (unsigned int)Dictionary;
  }
  if ( v7 )
    *v7 = 1;
  return 0;
}

```

## disassembly

```asm
0x18001c300  push    rbp
0x18001c302  push    rsi
0x18001c303  push    rdi
0x18001c304  mov     rbp, rsp
0x18001c307  sub     rsp, 80h
0x18001c30e  mov     rax, cs:__security_cookie
0x18001c315  xor     rax, rsp
0x18001c318  mov     [rbp+var_10], rax
0x18001c31c  xor     esi, esi
0x18001c31e  mov     rdi, rdx
0x18001c321  test    r8, r8
0x18001c324  jz      short loc_18001C329
0x18001c326  mov     [r8], esi
0x18001c329  test    rdi, rdi
0x18001c32c  jnz     short loc_18001C377
0x18001c32e  lea     rax, aOnecoreBaseWcp_20; "onecore\\base\\wcp\\manifestcompression"...
0x18001c335  mov     [rbp+var_40], 86h
0x18001c33d  mov     qword ptr [rbp+var_50], rax
0x18001c341  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001c348  lea     rax, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::Deco"...
0x18001c34f  mov     r8d, 0C000000Dh
0x18001c355  mov     qword ptr [rbp+var_50+8], rax
0x18001c359  lea     rcx, [rbp+var_50]
0x18001c35d  lea     rax, aNotNullCheckFa_65; "Not-null check failed: pManifestContent"...
0x18001c364  mov     [rbp+var_38], rax
0x18001c368  call    RtlReportErrorOrigination
0x18001c36d  mov     eax, 0C000000Dh
0x18001c372  jmp     loc_18001C568
0x18001c377  test    r8, r8
0x18001c37a  jz      short loc_18001C37F
0x18001c37c  mov     [r8], esi
0x18001c37f  mov     rcx, rdi; this
0x18001c382  mov     [rsp+80h+arg_0], rbx
0x18001c38a  call    ?IsManifestCompressed@Rtl@Implementation@WCP@Windows@@YA_NAEBU_LBLOB@@@Z; Windows::WCP::Implementation::Rtl::IsManifestCompressed(_LBLOB const &)
0x18001c38f  test    al, al
0x18001c391  jnz     short loc_18001C3A8
0x18001c393  test    r8, r8
0x18001c396  jz      loc_18001C55E
0x18001c39c  mov     dword ptr [r8], 1
0x18001c3a3  jmp     loc_18001C55E
0x18001c3a8  call    ?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z; Windows::Rtl::InitializeDeltaCompressor(void *)
0x18001c3ad  mov     ebx, eax
0x18001c3af  test    eax, eax
0x18001c3b1  js      loc_18001C463
0x18001c3b7  xorps   xmm0, xmm0
0x18001c3ba  lea     rdx, [rbp+var_50]
0x18001c3be  xor     eax, eax
0x18001c3c0  mov     ecx, 1
0x18001c3c5  movups  xmmword ptr [rbp+var_50], xmm0
0x18001c3c9  mov     [rbp+var_40], rax
0x18001c3cd  call    LoadDictionary
0x18001c3d2  mov     ebx, eax
0x18001c3d4  test    eax, eax
0x18001c3d6  js      loc_18001C463
0x18001c3dc  lea     rax, [rbp+var_30]
0x18001c3e0  mov     [rbp+var_28], rsi
0x18001c3e4  mov     r9, rdi; unsigned __int64
0x18001c3e7  mov     [rsp+80h+var_60], rax; struct _LBLOB *
0x18001c3ec  lea     rdx, [rbp+var_50]; unsigned int
0x18001c3f0  mov     [rbp+var_30], rsi
0x18001c3f4  mov     [rbp+var_20], rsi
0x18001c3f8  call    ?DeltaDecompressBuffer@Rtl@Windows@@YAJKPEAU_LBLOB@@_K0PEAVAutoDeltaBlob@12@2@Z; Windows::Rtl::DeltaDecompressBuffer(ulong,_LBLOB *,unsigned __int64,_LBLOB *,Windows::Rtl::AutoDeltaBlob *,Windows::Rtl::AutoDeltaBlob *)
0x18001c3fd  mov     ebx, eax
0x18001c3ff  test    eax, eax
0x18001c401  jns     short loc_18001C448
0x18001c403  lea     rax, aOnecoreBaseWcp_20; "onecore\\base\\wcp\\manifestcompression"...
0x18001c40a  mov     [rbp+var_40], 0B8h
0x18001c412  mov     qword ptr [rbp+var_50], rax
0x18001c416  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001c41d  lea     rax, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::Deco"...
0x18001c424  mov     [rbp+var_38], rsi
0x18001c428  mov     r8d, ebx
0x18001c42b  mov     qword ptr [rbp+var_50+8], rax
0x18001c42f  lea     rcx, [rbp+var_50]
0x18001c433  call    RtlReportErrorOrigination
0x18001c438  lea     rcx, [rbp+var_30]; this
0x18001c43c  call    ?Close@AutoDeltaBlob@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoDeltaBlob::Close(void)
0x18001c441  mov     eax, ebx
0x18001c443  jmp     loc_18001C560
0x18001c448  lea     rdx, [rbp+var_30]
0x18001c44c  mov     rcx, rdi
0x18001c44f  call    ?Assign@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAJAEBU_LBLOB@@@Z; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Assign(_LBLOB const &)
0x18001c454  mov     ebx, eax
0x18001c456  test    eax, eax
0x18001c458  jns     short loc_18001C46A
0x18001c45a  lea     rcx, [rbp+var_30]; this
0x18001c45e  call    ?Close@AutoDeltaBlob@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoDeltaBlob::Close(void)
0x18001c463  mov     eax, ebx
0x18001c465  jmp     loc_18001C560
0x18001c46a  mov     rcx, [rbp+var_20]
0x18001c46e  test    rcx, rcx
0x18001c471  jz      loc_18001C55E
0x18001c477  mov     rax, cs:qword_1800D2E08
0x18001c47e  test    rax, rax
0x18001c481  jnz     short loc_18001C4E1
0x18001c483  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001c48a  mov     [rbp+var_40], 75h ; 'u'
0x18001c492  mov     qword ptr [rbp+var_50], rcx
0x18001c496  lea     rax, aNotNullCheckFa_106; "Not-null check failed: g_pfnDeltaFree"
0x18001c49d  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoDeltaBlob::Close"
0x18001c4a4  mov     [rbp+var_38], rax
0x18001c4a8  mov     qword ptr [rbp+var_50+8], rcx
0x18001c4ac  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001c4b3  lea     rcx, [rbp+var_50]
0x18001c4b7  mov     [rbp+var_18], 0C000000Dh
0x18001c4be  mov     r8d, 0C000000Dh
0x18001c4c4  call    RtlReportErrorOrigination
0x18001c4c9  lea     rcx, [rbp+var_18]
0x18001c4cd  call    ?GetNtStatus@?$CBaseNtStatusCarryingFrame@UCVoidRaiseFrame@Rtl@ErrorHandling@Windows@@X@Rtl@ErrorHandling@Windows@@QEBAJXZ; Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(void)
0x18001c4d2  mov     ecx, eax; Status
0x18001c4d4  call    cs:__imp_RtlRaiseStatus
0x18001c4db  nop     dword ptr [rax+rax+00h]
0x18001c4e0  int     3; Trap to Debugger
0x18001c4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4e6  test    eax, eax
0x18001c4e8  jnz     short loc_18001C55E
0x18001c4ea  call    cs:__imp_GetLastError
0x18001c4f1  nop     dword ptr [rax+rax+00h]
0x18001c4f6  test    eax, eax
0x18001c4f8  jnz     loc_18001C580
0x18001c4fe  mov     eax, 36FDh
0x18001c503  mov     [rbp+var_40], 76h ; 'v'
0x18001c50b  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001c512  mov     qword ptr [rbp+var_50], rcx
0x18001c516  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoDeltaBlob::Close"
0x18001c51d  mov     qword ptr [rbp+var_50+8], rcx
0x18001c521  lea     rcx, aGPfndeltafreeT; "g_pfnDeltaFree(t.Buffer)"
0x18001c528  mov     [rbp+var_38], rcx
0x18001c52c  test    eax, eax
0x18001c52e  jle     short loc_18001C538
0x18001c530  movzx   eax, ax
0x18001c533  or      eax, 80070000h
0x18001c538  mov     ecx, eax
0x18001c53a  call    ConvertHResultToNtStatus
0x18001c53f  mov     r8d, eax
0x18001c542  mov     [rbp+var_18], eax
0x18001c545  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001c54c  lea     rcx, [rbp+var_50]
0x18001c550  call    RtlReportErrorOrigination
0x18001c555  lea     rcx, [rbp+var_18]; this
0x18001c559  call    ?ExitReturn@CVoidRaiseFrame@Rtl@ErrorHandling@Windows@@QEBAXXZ; Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(void)
0x18001c55e  xor     eax, eax
0x18001c560  mov     rbx, [rsp+80h+arg_0]
0x18001c568  mov     rcx, [rbp+var_10]
0x18001c56c  xor     rcx, rsp; StackCookie
0x18001c56f  call    __security_check_cookie
0x18001c574  add     rsp, 80h
0x18001c57b  pop     rdi
0x18001c57c  pop     rsi
0x18001c57d  pop     rbp
0x18001c57e  retn
0x18001c580  call    cs:__imp_GetLastError
0x18001c587  nop     dword ptr [rax+rax+00h]
0x18001c58c  test    eax, eax
0x18001c58e  jnz     loc_18001C503
0x18001c594  mov     ecx, 0C00000E5h; Status
0x18001c599  call    cs:__imp_RtlRaiseStatus
0x18001c5a0  nop     dword ptr [rax+rax+00h]
0x18001c5a5  int     3; Trap to Debugger
```
