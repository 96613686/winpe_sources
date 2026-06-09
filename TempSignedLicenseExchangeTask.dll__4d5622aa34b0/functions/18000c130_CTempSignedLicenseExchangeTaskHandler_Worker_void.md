# CTempSignedLicenseExchangeTaskHandler::Worker(void)

- ea: `0x18000c130`
- end: `0x18000c377`
- name: `?Worker@CTempSignedLicenseExchangeTaskHandler@@EEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CTempSignedLicenseExchangeTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001fd8`
- `0x180002e30`
- `0x18000c130`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c1c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c1c4`

## string_xrefs

- `0x18000c15c`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\tempsignedlicenseexchangetask.cpp`
- `0x18000c270`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\tempsignedlicenseexchangetask.cpp`
- `0x18000c2ee`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\tempsignedlicenseexchangetask.cpp`
- `0x18000c363`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\tempsignedlicenseexchangetask.cpp`
- `0x18000c14f`: `CTempSignedLicenseExchangeTaskHandler::Worker`
- `0x18000c263`: `CTempSignedLicenseExchangeTaskHandler::Worker`
- `0x18000c2e1`: `CTempSignedLicenseExchangeTaskHandler::Worker`
- `0x18000c356`: `CTempSignedLicenseExchangeTaskHandler::Worker`

## pseudocode

```c
__int64 __fastcall CTempSignedLicenseExchangeTaskHandler::Worker(CTempSignedLicenseExchangeTaskHandler *this)
{
  HRESULT v2; // ebx
  LPVOID v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  LPVOID v6; // rcx
  __int64 v8; // [rsp+28h] [rbp-28h]
  LPVOID ppv; // [rsp+70h] [rbp+20h] BYREF
  __int64 v10; // [rsp+78h] [rbp+28h] BYREF

  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\tempsignedlicenseexchangetask.cpp",
    0x6Eu,
    "CTempSignedLicenseExchangeTaskHandler::Worker",
    L"Starting TSL exchange pass");
  ppv = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) == 1 )
  {
    v2 = 0;
  }
  else
  {
    v3 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
    v2 = CoCreateInstance(&CLSID_ApplicationLicenseManager, 0, 4u, &GUID_90e2000c_b946_42fa_892f_94506f30ca4f, &ppv);
    if ( v2 < 0 )
      goto LABEL_15;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    v10 = 0;
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &GUID_0000013d_0000_0000_c000_000000000046, &v10) >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64, __int64, _DWORD, int, _QWORD, int))(*(_QWORD *)v10 + 32LL))(
             v10,
             ppv,
             0xFFFFFFFFLL,
             0xFFFFFFFFLL,
             -1,
             0,
             4,
             0,
             2048);
      if ( v4 < 0 )
      {
        LODWORD(v8) = v4;
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\tempsignedlicenseexchangetask.cpp",
          0x7Fu,
          "CTempSignedLicenseExchangeTaskHandler::Worker",
          L"Unable to set proxy blanket, this may not go well.  0x%08x",
          v8);
      }
    }
    v5 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 88LL))(ppv, 4);
    if ( StoreAppsAreDisabled() )
    {
      v2 = -1073740956;
LABEL_15:
      LODWORD(v8) = v2;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\tempsignedlicenseexchangetask.cpp",
        0x98u,
        "CTempSignedLicenseExchangeTaskHandler::Worker",
        L"Failed to do TSL exchange licenses, 0x%08x",
        v8);
      goto LABEL_16;
    }
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 88LL))(ppv, 7);
  }
  if ( v2 < 0 )
    goto LABEL_15;
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\tempsignedlicenseexchangetask.cpp",
    0x94u,
    "CTempSignedLicenseExchangeTaskHandler::Worker",
    L"Finished TSL exchange pass");
LABEL_16:
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c130  mov     [rsp-18h+arg_10], rbx
0x18000c135  push    rbp
0x18000c136  push    rdi
0x18000c137  push    r14
0x18000c139  mov     rbp, rsp
0x18000c13c  sub     rsp, 50h
0x18000c140  mov     rdi, rcx
0x18000c143  lea     rax, aStartingTslExc; "Starting TSL exchange pass"
0x18000c14a  mov     [rsp+50h+ppv], rax; unsigned __int16 *
0x18000c14f  lea     r9, aCtempsignedlic; "CTempSignedLicenseExchangeTaskHandler::"...
0x18000c156  mov     r8d, 6Eh ; 'n'; unsigned int
0x18000c15c  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c163  lea     ecx, [r8-6Bh]; unsigned int
0x18000c167  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c16c  mov     [rbp+arg_0], 0
0x18000c174  mov     r14d, 1
0x18000c17a  mov     eax, r14d
0x18000c17d  lock cmpxchg [rdi+24h], r14d
0x18000c183  jnz     short loc_18000C189
0x18000c185  xor     ebx, ebx
0x18000c187  jmp     short loc_18000C1D4
0x18000c189  mov     rcx, [rbp+arg_0]
0x18000c18d  test    rcx, rcx
0x18000c190  jz      short loc_18000C1A7
0x18000c192  mov     [rbp+arg_0], 0
0x18000c19a  mov     rax, [rcx]
0x18000c19d  mov     rax, [rax+10h]
0x18000c1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a6  nop
0x18000c1a7  lea     rax, [rbp+arg_0]
0x18000c1ab  mov     [rsp+50h+ppv], rax; ppv
0x18000c1b0  lea     r9, _GUID_90e2000c_b946_42fa_892f_94506f30ca4f; riid
0x18000c1b7  xor     edx, edx; pUnkOuter
0x18000c1b9  lea     r8d, [rdx+4]; dwClsContext
0x18000c1bd  lea     rcx, CLSID_ApplicationLicenseManager; rclsid
0x18000c1c4  call    cs:__imp_CoCreateInstance
0x18000c1ca  mov     ebx, eax
0x18000c1cc  test    eax, eax
0x18000c1ce  js      loc_18000C2D1
0x18000c1d4  mov     eax, r14d
0x18000c1d7  lock cmpxchg [rdi+24h], r14d
0x18000c1dd  jz      loc_18000C29F
0x18000c1e3  mov     [rbp+arg_8], 0
0x18000c1eb  mov     rcx, [rbp+arg_0]
0x18000c1ef  mov     rax, [rcx]
0x18000c1f2  lea     r8, [rbp+arg_8]
0x18000c1f6  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x18000c1fd  mov     rax, [rax]
0x18000c200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c205  nop
0x18000c206  test    eax, eax
0x18000c208  js      short loc_18000C281
0x18000c20a  mov     rcx, [rbp+arg_8]
0x18000c20e  mov     rax, [rcx]
0x18000c211  mov     [rsp+50h+var_10], 800h
0x18000c219  mov     [rsp+50h+var_18], 0
0x18000c222  mov     [rsp+50h+var_20], 4
0x18000c22a  mov     dword ptr [rsp+50h+var_28], 0
0x18000c232  mov     [rsp+50h+ppv], 0FFFFFFFFFFFFFFFFh
0x18000c23b  or      r8d, 0FFFFFFFFh
0x18000c23f  mov     r9d, r8d
0x18000c242  mov     rdx, [rbp+arg_0]
0x18000c246  mov     rax, [rax+20h]
0x18000c24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24f  test    eax, eax
0x18000c251  jns     short loc_18000C281
0x18000c253  mov     dword ptr [rsp+50h+var_28], eax
0x18000c257  lea     rax, aUnableToSetPro; "Unable to set proxy blanket, this may n"...
0x18000c25e  mov     [rsp+50h+ppv], rax; unsigned __int16 *
0x18000c263  lea     r9, aCtempsignedlic; "CTempSignedLicenseExchangeTaskHandler::"...
0x18000c26a  mov     r8d, 7Fh; unsigned int
0x18000c270  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c277  lea     ecx, [r8-7Dh]; unsigned int
0x18000c27b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c280  nop
0x18000c281  mov     rcx, [rbp+arg_8]
0x18000c285  test    rcx, rcx
0x18000c288  jz      short loc_18000C29F
0x18000c28a  mov     [rbp+arg_8], 0
0x18000c292  mov     rax, [rcx]
0x18000c295  mov     rax, [rax+10h]
0x18000c299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29e  nop
0x18000c29f  mov     eax, r14d
0x18000c2a2  lock cmpxchg [rdi+24h], r14d
0x18000c2a8  jz      loc_18000C346
0x18000c2ae  mov     rcx, [rbp+arg_0]
0x18000c2b2  mov     rax, [rcx]
0x18000c2b5  mov     edx, 4
0x18000c2ba  mov     rax, [rax+58h]
0x18000c2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c3  call    ?StoreAppsAreDisabled@@YA_NXZ; StoreAppsAreDisabled(void)
0x18000c2c8  test    al, al
0x18000c2ca  jz      short loc_18000C32F
0x18000c2cc  mov     ebx, 0C0000364h
0x18000c2d1  mov     dword ptr [rsp+50h+var_28], ebx
0x18000c2d5  lea     rax, aFailedToDoTslE; "Failed to do TSL exchange licenses, 0x%"...
0x18000c2dc  mov     [rsp+50h+ppv], rax; unsigned __int16 *
0x18000c2e1  lea     r9, aCtempsignedlic; "CTempSignedLicenseExchangeTaskHandler::"...
0x18000c2e8  mov     r8d, 98h; unsigned int
0x18000c2ee  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c2f5  mov     ecx, r14d; unsigned int
0x18000c2f8  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c2fd  nop
0x18000c2fe  mov     rcx, [rbp+arg_0]
0x18000c302  test    rcx, rcx
0x18000c305  jz      short loc_18000C31C
0x18000c307  mov     [rbp+arg_0], 0
0x18000c30f  mov     rax, [rcx]
0x18000c312  mov     rax, [rax+10h]
0x18000c316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31b  nop
0x18000c31c  mov     eax, ebx
0x18000c31e  mov     rbx, [rsp+50h+arg_10]
0x18000c326  add     rsp, 50h
0x18000c32a  pop     r14
0x18000c32c  pop     rdi
0x18000c32d  pop     rbp
0x18000c32e  retn
0x18000c32f  mov     rcx, [rbp+arg_0]
0x18000c333  mov     rax, [rcx]
0x18000c336  mov     edx, 7
0x18000c33b  mov     rax, [rax+58h]
0x18000c33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c344  mov     ebx, eax
0x18000c346  test    ebx, ebx
0x18000c348  js      short loc_18000C2D1
0x18000c34a  lea     rax, aFinishedTslExc; "Finished TSL exchange pass"
0x18000c351  mov     [rsp+50h+ppv], rax; unsigned __int16 *
0x18000c356  lea     r9, aCtempsignedlic; "CTempSignedLicenseExchangeTaskHandler::"...
0x18000c35d  mov     r8d, 94h; unsigned int
0x18000c363  lea     rdx, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000c36a  mov     ecx, 3; unsigned int
0x18000c36f  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c374  jmp     short loc_18000C2FE
```
