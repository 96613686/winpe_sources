# Windows::WCP::Implementation::Rtl::DecompressManifest(ulong,Windows::Auto<_LBLOB> *,ulong *)

- ea: `0x18001dae0`
- end: `0x18001dd7d`
- name: `?DecompressManifest@Rtl@Implementation@WCP@Windows@@YAJKPEAV?$Auto@U_LBLOB@@@4@PEAK@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dd90`

## callees

- `0x1800021c8`
- `0x1800031e0`
- `0x180010e40`
- `0x180010f70`
- `0x18001c320`
- `0x18001dae0`
- `0x18001de30`
- `0x18001fcf4`
- `0x18001fd10`
- `0x18001fdbc`
- `0x1800293a0`
- `0x18006e930`
- `0x18006e9b0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001dc70`
- `KERNEL32!GetLastError` at `0x18001dd06`
- `KERNEL32!GetLastError` at `0x18001dc70`
- `KERNEL32!GetLastError` at `0x18001dd06`

## string_xrefs

- `0x18001db0e`: `onecore\base\wcp\manifestcompression\manifest_compression.cpp`
- `0x18001dbe3`: `onecore\base\wcp\manifestcompression\manifest_compression.cpp`
- `0x18001db3d`: `Not-null check failed: pManifestContents`
- `0x18001db28`: `Windows::WCP::Implementation::Rtl::DecompressManifest`
- `0x18001dbfd`: `Windows::WCP::Implementation::Rtl::DecompressManifest`

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
  signed int LastError; // eax
  int NtStatus; // eax
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
            if ( !qword_1800D4DE8 )
            {
              v16 = 117;
              *(_QWORD *)v15 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
              v17 = "Not-null check failed: g_pfnDeltaFree";
              *(_QWORD *)&v15[2] = "Windows::Rtl::AutoDeltaBlob::Close";
              v20 = -1073741811;
              RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
              NtStatus = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v20);
              INTERNAL_ERROR_ACTION(NtStatus);
              __debugbreak();
            }
            if ( !(unsigned int)qword_1800D4DE8() )
            {
              if ( GetLastError() )
              {
                LastError = GetLastError();
                if ( !LastError )
                {
                  INTERNAL_ERROR_ACTION(-1073741595);
                  JUMPOUT(0x18001DD7CLL);
                }
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
0x18001dae0  push    rbp
0x18001dae2  push    rsi
0x18001dae3  push    rdi
0x18001dae4  mov     rbp, rsp
0x18001dae7  sub     rsp, 80h
0x18001daee  mov     rax, cs:__security_cookie
0x18001daf5  xor     rax, rsp
0x18001daf8  mov     [rbp+var_10], rax
0x18001dafc  xor     esi, esi
0x18001dafe  mov     rdi, rdx
0x18001db01  test    r8, r8
0x18001db04  jz      short loc_18001DB09
0x18001db06  mov     [r8], esi
0x18001db09  test    rdi, rdi
0x18001db0c  jnz     short loc_18001DB57
0x18001db0e  lea     rax, aOnecoreBaseWcp_20; "onecore\\base\\wcp\\manifestcompression"...
0x18001db15  mov     [rbp+var_40], 86h
0x18001db1d  mov     qword ptr [rbp+var_50], rax
0x18001db21  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001db28  lea     rax, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::Deco"...
0x18001db2f  mov     r8d, 0C000000Dh
0x18001db35  mov     qword ptr [rbp+var_50+8], rax
0x18001db39  lea     rcx, [rbp+var_50]
0x18001db3d  lea     rax, aNotNullCheckFa_65; "Not-null check failed: pManifestContent"...
0x18001db44  mov     [rbp+var_38], rax
0x18001db48  call    RtlReportErrorOrigination
0x18001db4d  mov     eax, 0C000000Dh
0x18001db52  jmp     loc_18001DCEE
0x18001db57  test    r8, r8
0x18001db5a  jz      short loc_18001DB5F
0x18001db5c  mov     [r8], esi
0x18001db5f  mov     rcx, rdi; this
0x18001db62  mov     [rsp+80h+arg_0], rbx
0x18001db6a  call    ?IsManifestCompressed@Rtl@Implementation@WCP@Windows@@YA_NAEBU_LBLOB@@@Z; Windows::WCP::Implementation::Rtl::IsManifestCompressed(_LBLOB const &)
0x18001db6f  test    al, al
0x18001db71  jnz     short loc_18001DB88
0x18001db73  test    r8, r8
0x18001db76  jz      loc_18001DCE4
0x18001db7c  mov     dword ptr [r8], 1
0x18001db83  jmp     loc_18001DCE4
0x18001db88  call    ?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z; Windows::Rtl::InitializeDeltaCompressor(void *)
0x18001db8d  mov     ebx, eax
0x18001db8f  test    eax, eax
0x18001db91  js      loc_18001DC43
0x18001db97  xorps   xmm0, xmm0
0x18001db9a  lea     rdx, [rbp+var_50]
0x18001db9e  xor     eax, eax
0x18001dba0  mov     ecx, 1
0x18001dba5  movups  xmmword ptr [rbp+var_50], xmm0
0x18001dba9  mov     [rbp+var_40], rax
0x18001dbad  call    LoadDictionary
0x18001dbb2  mov     ebx, eax
0x18001dbb4  test    eax, eax
0x18001dbb6  js      loc_18001DC43
0x18001dbbc  lea     rax, [rbp+var_30]
0x18001dbc0  mov     [rbp+var_28], rsi
0x18001dbc4  mov     r9, rdi; unsigned __int64
0x18001dbc7  mov     [rsp+80h+var_60], rax; struct _LBLOB *
0x18001dbcc  lea     rdx, [rbp+var_50]; unsigned int
0x18001dbd0  mov     [rbp+var_30], rsi
0x18001dbd4  mov     [rbp+var_20], rsi
0x18001dbd8  call    ?DeltaDecompressBuffer@Rtl@Windows@@YAJKPEAU_LBLOB@@_K0PEAVAutoDeltaBlob@12@2@Z; Windows::Rtl::DeltaDecompressBuffer(ulong,_LBLOB *,unsigned __int64,_LBLOB *,Windows::Rtl::AutoDeltaBlob *,Windows::Rtl::AutoDeltaBlob *)
0x18001dbdd  mov     ebx, eax
0x18001dbdf  test    eax, eax
0x18001dbe1  jns     short loc_18001DC28
0x18001dbe3  lea     rax, aOnecoreBaseWcp_20; "onecore\\base\\wcp\\manifestcompression"...
0x18001dbea  mov     [rbp+var_40], 0B8h
0x18001dbf2  mov     qword ptr [rbp+var_50], rax
0x18001dbf6  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001dbfd  lea     rax, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::Deco"...
0x18001dc04  mov     [rbp+var_38], rsi
0x18001dc08  mov     r8d, ebx
0x18001dc0b  mov     qword ptr [rbp+var_50+8], rax
0x18001dc0f  lea     rcx, [rbp+var_50]
0x18001dc13  call    RtlReportErrorOrigination
0x18001dc18  lea     rcx, [rbp+var_30]; this
0x18001dc1c  call    ?Close@AutoDeltaBlob@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoDeltaBlob::Close(void)
0x18001dc21  mov     eax, ebx
0x18001dc23  jmp     loc_18001DCE6
0x18001dc28  lea     rdx, [rbp+var_30]
0x18001dc2c  mov     rcx, rdi
0x18001dc2f  call    ?Assign@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAJAEBU_LBLOB@@@Z; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Assign(_LBLOB const &)
0x18001dc34  mov     ebx, eax
0x18001dc36  test    eax, eax
0x18001dc38  jns     short loc_18001DC4A
0x18001dc3a  lea     rcx, [rbp+var_30]; this
0x18001dc3e  call    ?Close@AutoDeltaBlob@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoDeltaBlob::Close(void)
0x18001dc43  mov     eax, ebx
0x18001dc45  jmp     loc_18001DCE6
0x18001dc4a  mov     rcx, [rbp+var_20]
0x18001dc4e  test    rcx, rcx
0x18001dc51  jz      loc_18001DCE4
0x18001dc57  mov     rax, cs:qword_1800D4DE8
0x18001dc5e  test    rax, rax
0x18001dc61  jz      loc_18001DD1B
0x18001dc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc6c  test    eax, eax
0x18001dc6e  jnz     short loc_18001DCE4
0x18001dc70  call    cs:__imp_GetLastError
0x18001dc77  nop     dword ptr [rax+rax+00h]
0x18001dc7c  test    eax, eax
0x18001dc7e  jnz     loc_18001DD06
0x18001dc84  mov     eax, 36FDh
0x18001dc89  mov     [rbp+var_40], 76h ; 'v'
0x18001dc91  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001dc98  mov     qword ptr [rbp+var_50], rcx
0x18001dc9c  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoDeltaBlob::Close"
0x18001dca3  mov     qword ptr [rbp+var_50+8], rcx
0x18001dca7  lea     rcx, aGPfndeltafreeT; "g_pfnDeltaFree(t.Buffer)"
0x18001dcae  mov     [rbp+var_38], rcx
0x18001dcb2  test    eax, eax
0x18001dcb4  jle     short loc_18001DCBE
0x18001dcb6  movzx   eax, ax
0x18001dcb9  or      eax, 80070000h
0x18001dcbe  mov     ecx, eax
0x18001dcc0  call    ConvertHResultToNtStatus
0x18001dcc5  mov     r8d, eax
0x18001dcc8  mov     [rbp+var_18], eax
0x18001dccb  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001dcd2  lea     rcx, [rbp+var_50]
0x18001dcd6  call    RtlReportErrorOrigination
0x18001dcdb  lea     rcx, [rbp+var_18]; this
0x18001dcdf  call    ?ExitReturn@CVoidRaiseFrame@Rtl@ErrorHandling@Windows@@QEBAXXZ; Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(void)
0x18001dce4  xor     eax, eax
0x18001dce6  mov     rbx, [rsp+80h+arg_0]
0x18001dcee  mov     rcx, [rbp+var_10]
0x18001dcf2  xor     rcx, rsp; StackCookie
0x18001dcf5  call    __security_check_cookie
0x18001dcfa  add     rsp, 80h
0x18001dd01  pop     rdi
0x18001dd02  pop     rsi
0x18001dd03  pop     rbp
0x18001dd04  retn
0x18001dd06  call    cs:__imp_GetLastError
0x18001dd0d  nop     dword ptr [rax+rax+00h]
0x18001dd12  test    eax, eax
0x18001dd14  jz      short loc_18001DD72
0x18001dd16  jmp     loc_18001DC89
0x18001dd1b  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18001dd22  mov     [rbp+var_40], 75h ; 'u'
0x18001dd2a  mov     qword ptr [rbp+var_50], rcx
0x18001dd2e  lea     rax, aNotNullCheckFa_106; "Not-null check failed: g_pfnDeltaFree"
0x18001dd35  lea     rcx, aWindowsRtlAuto; "Windows::Rtl::AutoDeltaBlob::Close"
0x18001dd3c  mov     [rbp+var_38], rax
0x18001dd40  mov     qword ptr [rbp+var_50+8], rcx
0x18001dd44  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001dd4b  lea     rcx, [rbp+var_50]
0x18001dd4f  mov     [rbp+var_18], 0C000000Dh
0x18001dd56  mov     r8d, 0C000000Dh
0x18001dd5c  call    RtlReportErrorOrigination
0x18001dd61  lea     rcx, [rbp+var_18]
0x18001dd65  call    ?GetNtStatus@?$CBaseNtStatusCarryingFrame@UCVoidRaiseFrame@Rtl@ErrorHandling@Windows@@X@Rtl@ErrorHandling@Windows@@QEBAJXZ; Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(void)
0x18001dd6a  mov     ecx, eax; int
0x18001dd6c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18001dd71  int     3; Trap to Debugger
0x18001dd72  mov     ecx, 0C00000E5h; int
0x18001dd77  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
