# UniDrvUI::BBidiInitInstallOptions(UniDrvUI::_COMMONINFO *)

- ea: `0x18010e178`
- end: `0x18010e3df`
- name: `?BBidiInitInstallOptions@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z`
- size: `615`
- prototype: `__int64 __fastcall(UniDrvUI **this, struct UniDrvUI::_COMMONINFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180128d10`

## callees

- `0x180107214`
- `0x18010e178`
- `0x18010e3e8`
- `0x18010e98c`
- `0x1801276c8`
- `0x180127978`
- `0x180127ba4`
- `0x180127ce8`
- `0x180127da4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18010e1bd`
- `KERNEL32!GetLastError` at `0x18010e208`
- `KERNEL32!GetLastError` at `0x18010e31a`
- `KERNEL32!GetLastError` at `0x18010e1bd`
- `KERNEL32!GetLastError` at `0x18010e208`
- `KERNEL32!GetLastError` at `0x18010e31a`
- `KERNEL32!LocalFree` at `0x18010e346`
- `KERNEL32!LocalFree` at `0x18010e355`
- `KERNEL32!LocalFree` at `0x18010e3a4`
- `KERNEL32!LocalFree` at `0x18010e346`
- `KERNEL32!LocalFree` at `0x18010e355`
- `KERNEL32!LocalFree` at `0x18010e3a4`
- `KERNEL32!LocalAlloc` at `0x18010e251`
- `KERNEL32!LocalAlloc` at `0x18010e28b`
- `KERNEL32!LocalAlloc` at `0x18010e2b4`
- `KERNEL32!LocalAlloc` at `0x18010e251`
- `KERNEL32!LocalAlloc` at `0x18010e28b`
- `KERNEL32!LocalAlloc` at `0x18010e2b4`
- `ole32!CoInitializeEx` at `0x18010e198`
- `ole32!CoInitializeEx` at `0x18010e198`
- `ole32!CoUninitialize` at `0x18010e3bf`
- `ole32!CoUninitialize` at `0x18010e3bf`
- `ole32!CoTaskMemFree` at `0x18010e377`
- `ole32!CoTaskMemFree` at `0x18010e388`
- `ole32!CoTaskMemFree` at `0x18010e377`
- `ole32!CoTaskMemFree` at `0x18010e388`

## string_xrefs

- `0x18010e1cc`: `BBidiInitInstallOptions:CoInitializeEx failed %d\n`
- `0x18010e217`: `Failed to BBidiInitInstallOptions %d \n`
- `0x18010e1d3`: `UniDrvUI::BBidiInitInstallOptions`
- `0x18010e21e`: `UniDrvUI::BBidiInitInstallOptions`
- `0x18010e330`: `UniDrvUI::BBidiInitInstallOptions`

## pseudocode

```c
__int64 __fastcall UniDrvUI::BBidiInitInstallOptions(UniDrvUI **this, struct UniDrvUI::_COMMONINFO *a2)
{
  struct UniDrvUI::_BIDIMAP_INFO *v3; // r9
  HRESULT v4; // r12d
  DWORD LastError; // eax
  struct UniDrvUI::_COMMONINFO *v7; // rdi
  unsigned int InfoFromSnapshot; // eax
  struct PSUI::_BIDI_FEATUREOPTION **v9; // r8
  struct UniDrvUI::_BIDI_FEATUREOPTION **v10; // r13
  unsigned int v11; // esi
  __int64 v12; // rbp
  DWORD v13; // eax
  struct UniDrvUI::_BIDI_INFO **v14; // r14
  int i; // eax
  __int64 v16; // r8
  UniDrvUI *v17; // rbx
  __int64 v18; // r8
  void **v19; // r9
  UniDrvUI *v20; // rcx
  unsigned int SingleRequest; // eax
  struct UniDrvUI::_BIDI_INFO *v22; // rdx
  DWORD v23; // eax
  int j; // r14d
  __int64 v25; // rbx
  struct UniDrvUI::_BIDI_FEATUREOPTION **v26[2]; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)v26 = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    LastError = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::BBidiInitInstallOptions",
      L"BBidiInitInstallOptions:CoInitializeEx failed %d\n",
      LastError);
    return 0;
  }
  v7 = 0;
  InfoFromSnapshot = UniDrvUI::BBidiGetInfoFromSnapshot(this[4], this, (struct UniDrvUI::_COMMONINFO *)v26, v3);
  v10 = v26[1];
  v11 = InfoFromSnapshot;
  v12 = LODWORD(v26[0]);
  if ( InfoFromSnapshot )
  {
    if ( 8 * (unsigned __int64)LODWORD(v26[0]) > 0xFFFFFFFF
      || (v14 = (struct UniDrvUI::_BIDI_INFO **)LocalAlloc(0x40u, (unsigned int)(8 * LODWORD(v26[0])))) == 0 )
    {
      v11 = 0;
      goto LABEL_23;
    }
    for ( i = 0; i < (int)v12; v14[v16] = *(struct UniDrvUI::_BIDI_INFO **)v10[v16] )
      v16 = i++;
    v17 = (UniDrvUI *)LocalAlloc(0x40u, 0x20u);
    if ( v17
      && (unsigned __int64)(32 * v12) <= 0xFFFFFFFF
      && (v7 = (struct UniDrvUI::_COMMONINFO *)LocalAlloc(0x40u, (unsigned int)(32 * v12))) != 0 )
    {
      if ( !UniDrvUI::BBidiInitialize(v17, (struct UniDrvUI::_BIDI_INFO *)(unsigned int)v12, v18, v19)
        || ((v20 = this[3], (int)v12 <= 1)
          ? (SingleRequest = UniDrvUI::BBidiGetSingleRequest(
                               v20,
                               (const unsigned __int16 *)v17,
                               *v14,
                               (unsigned __int16 *)v7))
          : (SingleRequest = UniDrvUI::BBidiGetMultipleRequests(
                               v20,
                               (const unsigned __int16 *)v17,
                               (struct UniDrvUI::_BIDI_INFO *)v14,
                               (unsigned __int16 **const)v7)),
            v11 = SingleRequest,
            UniDrvUI::BidiReleaseInterfaces(v17, v22),
            v11) )
      {
        v11 = UniDrvUI::BBidiMapOutputToOptions(
                (UniDrvUI *)this,
                v7,
                (struct UniDrvUI::_BIDI_OUTPUT *)(unsigned int)v12,
                (__int64)v10);
      }
    }
    else
    {
      v23 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::BBidiInitInstallOptions",
        L"Failed to alloc memory for pBidiInfo or pBidiOutput: %d\n",
        v23);
      v11 = 0;
      if ( !v17 )
      {
LABEL_21:
        LocalFree(v14);
        goto LABEL_23;
      }
    }
    LocalFree(v17);
    goto LABEL_21;
  }
  v13 = GetLastError();
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::BBidiInitInstallOptions",
    L"Failed to BBidiInitInstallOptions %d \n",
    v13);
LABEL_23:
  for ( j = 0; j < (int)v12; ++j )
  {
    v25 = 32LL * j;
    CoTaskMemFree(*(LPVOID *)((char *)v7 + v25));
    CoTaskMemFree(*(LPVOID *)((char *)v7 + v25 + 16));
  }
  if ( v7 )
    LocalFree(v7);
  PSUI::BidiFreeMapInfo((PSUI *)(unsigned int)v12, v10, v9);
  if ( v4 >= 0 )
    CoUninitialize();
  return v11;
}

```

## disassembly

```asm
0x18010e178  push    rbx
0x18010e17a  push    rbp
0x18010e17b  push    rsi
0x18010e17c  push    rdi
0x18010e17d  push    r12
0x18010e17f  push    r13
0x18010e181  push    r14
0x18010e183  push    r15
0x18010e185  sub     rsp, 38h
0x18010e189  mov     r15, rcx
0x18010e18c  xorps   xmm0, xmm0
0x18010e18f  xor     ecx, ecx; pvReserved
0x18010e191  xor     edx, edx; dwCoInit
0x18010e193  movups  xmmword ptr [rsp+78h+var_58], xmm0; struct UniDrvUI::_BIDI_FEATUREOPTION **
0x18010e198  call    cs:__imp_CoInitializeEx
0x18010e19f  nop     dword ptr [rax+rax+00h]
0x18010e1a4  mov     r12d, eax
0x18010e1a7  mov     eax, 80000000h
0x18010e1ac  lea     edx, [r12+rax]
0x18010e1b0  test    eax, edx
0x18010e1b2  jnz     short loc_18010E1E6
0x18010e1b4  cmp     r12d, 80010106h
0x18010e1bb  jz      short loc_18010E1E6
0x18010e1bd  call    cs:__imp_GetLastError
0x18010e1c4  nop     dword ptr [rax+rax+00h]
0x18010e1c9  mov     r8d, eax
0x18010e1cc  lea     rdx, aBbidiinitinsta; "BBidiInitInstallOptions:CoInitializeEx "...
0x18010e1d3  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x18010e1da  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e1df  xor     eax, eax
0x18010e1e1  jmp     loc_18010E3CD
0x18010e1e6  mov     rcx, [r15+20h]; this
0x18010e1ea  lea     r8, [rsp+78h+var_58]; struct UniDrvUI::_COMMONINFO *
0x18010e1ef  mov     rdx, r15; void *
0x18010e1f2  xor     edi, edi
0x18010e1f4  call    ?BBidiGetInfoFromSnapshot@UniDrvUI@@YAHPEAXPEAU_COMMONINFO@1@PEAU_BIDIMAP_INFO@1@@Z; UniDrvUI::BBidiGetInfoFromSnapshot(void *,UniDrvUI::_COMMONINFO *,UniDrvUI::_BIDIMAP_INFO *)
0x18010e1f9  mov     r13, [rsp+78h+var_58+8]
0x18010e1fe  mov     esi, eax
0x18010e200  mov     ebp, dword ptr [rsp+78h+var_58]
0x18010e204  test    eax, eax
0x18010e206  jnz     short loc_18010E22F
0x18010e208  call    cs:__imp_GetLastError
0x18010e20f  nop     dword ptr [rax+rax+00h]
0x18010e214  mov     r8d, eax
0x18010e217  lea     rdx, aFailedToBbidii; "Failed to BBidiInitInstallOptions %d \n"
0x18010e21e  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x18010e225  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e22a  jmp     loc_18010E365
0x18010e22f  lea     rax, ds:0[rbp*8]
0x18010e237  mov     ecx, 0FFFFFFFFh
0x18010e23c  mov     rsi, rbp
0x18010e23f  cmp     rax, rcx
0x18010e242  ja      loc_18010E363
0x18010e248  mov     ebx, 40h ; '@'
0x18010e24d  mov     edx, eax; uBytes
0x18010e24f  mov     ecx, ebx; uFlags
0x18010e251  call    cs:__imp_LocalAlloc
0x18010e258  nop     dword ptr [rax+rax+00h]
0x18010e25d  mov     r14, rax
0x18010e260  test    rax, rax
0x18010e263  jz      loc_18010E363
0x18010e269  xor     eax, eax
0x18010e26b  test    ebp, ebp
0x18010e26d  jle     short loc_18010E284
0x18010e26f  movsxd  r8, eax
0x18010e272  inc     eax
0x18010e274  mov     rcx, [r13+r8*8+0]
0x18010e279  mov     rdx, [rcx]
0x18010e27c  mov     [r14+r8*8], rdx
0x18010e280  cmp     eax, ebp
0x18010e282  jl      short loc_18010E26F
0x18010e284  mov     edx, 20h ; ' '; uBytes
0x18010e289  mov     ecx, ebx; uFlags
0x18010e28b  call    cs:__imp_LocalAlloc
0x18010e292  nop     dword ptr [rax+rax+00h]
0x18010e297  mov     rbx, rax
0x18010e29a  test    rax, rax
0x18010e29d  jz      short loc_18010E31A
0x18010e29f  shl     rsi, 5
0x18010e2a3  mov     eax, 0FFFFFFFFh
0x18010e2a8  cmp     rsi, rax
0x18010e2ab  ja      short loc_18010E31A
0x18010e2ad  mov     edx, esi; uBytes
0x18010e2af  mov     ecx, 40h ; '@'; uFlags
0x18010e2b4  call    cs:__imp_LocalAlloc
0x18010e2bb  nop     dword ptr [rax+rax+00h]
0x18010e2c0  mov     rdi, rax
0x18010e2c3  test    rax, rax
0x18010e2c6  jz      short loc_18010E31A
0x18010e2c8  mov     edx, ebp; struct UniDrvUI::_BIDI_INFO *
0x18010e2ca  mov     rcx, rbx; this
0x18010e2cd  call    ?BBidiInitialize@UniDrvUI@@YAHPEAU_BIDI_INFO@1@K@Z; UniDrvUI::BBidiInitialize(UniDrvUI::_BIDI_INFO *,ulong)
0x18010e2d2  test    eax, eax
0x18010e2d4  jz      short loc_18010E305
0x18010e2d6  mov     rcx, [r15+18h]; this
0x18010e2da  mov     r9, rdi; unsigned __int16 *
0x18010e2dd  mov     rdx, rbx; unsigned __int16 *
0x18010e2e0  cmp     ebp, 1
0x18010e2e3  jle     short loc_18010E2EF
0x18010e2e5  mov     r8, r14; struct UniDrvUI::_BIDI_INFO *
0x18010e2e8  call    ?BBidiGetMultipleRequests@UniDrvUI@@YAHPEBGPEAU_BIDI_INFO@1@QEAPEAGPEAU_BIDI_OUTPUT@1@@Z; UniDrvUI::BBidiGetMultipleRequests(ushort const *,UniDrvUI::_BIDI_INFO *,ushort * * const,UniDrvUI::_BIDI_OUTPUT *)
0x18010e2ed  jmp     short loc_18010E2F7
0x18010e2ef  mov     r8, [r14]; struct UniDrvUI::_BIDI_INFO *
0x18010e2f2  call    ?BBidiGetSingleRequest@UniDrvUI@@YAHPEBGPEAU_BIDI_INFO@1@PEAGPEAU_BIDI_OUTPUT@1@@Z; UniDrvUI::BBidiGetSingleRequest(ushort const *,UniDrvUI::_BIDI_INFO *,ushort *,UniDrvUI::_BIDI_OUTPUT *)
0x18010e2f7  mov     rcx, rbx; this
0x18010e2fa  mov     esi, eax
0x18010e2fc  call    ?BidiReleaseInterfaces@UniDrvUI@@YAXPEAU_BIDI_INFO@1@@Z; UniDrvUI::BidiReleaseInterfaces(UniDrvUI::_BIDI_INFO *)
0x18010e301  test    esi, esi
0x18010e303  jz      short loc_18010E343
0x18010e305  mov     r9, r13; unsigned int
0x18010e308  mov     r8d, ebp; struct UniDrvUI::_BIDI_OUTPUT *
0x18010e30b  mov     rdx, rdi; struct UniDrvUI::_COMMONINFO *
0x18010e30e  mov     rcx, r15; this
0x18010e311  call    ?BBidiMapOutputToOptions@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_BIDI_OUTPUT@1@KPEAPEAU_BIDI_FEATUREOPTION@1@@Z; UniDrvUI::BBidiMapOutputToOptions(UniDrvUI::_COMMONINFO *,UniDrvUI::_BIDI_OUTPUT *,ulong,UniDrvUI::_BIDI_FEATUREOPTION * *)
0x18010e316  mov     esi, eax
0x18010e318  jmp     short loc_18010E343
0x18010e31a  call    cs:__imp_GetLastError
0x18010e321  nop     dword ptr [rax+rax+00h]
0x18010e326  mov     r8d, eax
0x18010e329  lea     rdx, aFailedToAllocM; "Failed to alloc memory for pBidiInfo or"...
0x18010e330  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x18010e337  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010e33c  xor     esi, esi
0x18010e33e  test    rbx, rbx
0x18010e341  jz      short loc_18010E352
0x18010e343  mov     rcx, rbx; hMem
0x18010e346  call    cs:__imp_LocalFree
0x18010e34d  nop     dword ptr [rax+rax+00h]
0x18010e352  mov     rcx, r14; hMem
0x18010e355  call    cs:__imp_LocalFree
0x18010e35c  nop     dword ptr [rax+rax+00h]
0x18010e361  jmp     short loc_18010E365
0x18010e363  xor     esi, esi
0x18010e365  xor     r14d, r14d
0x18010e368  test    ebp, ebp
0x18010e36a  jle     short loc_18010E39C
0x18010e36c  movsxd  rbx, r14d
0x18010e36f  shl     rbx, 5
0x18010e373  mov     rcx, [rbx+rdi]; pv
0x18010e377  call    cs:__imp_CoTaskMemFree
0x18010e37e  nop     dword ptr [rax+rax+00h]
0x18010e383  mov     rcx, [rbx+rdi+10h]; pv
0x18010e388  call    cs:__imp_CoTaskMemFree
0x18010e38f  nop     dword ptr [rax+rax+00h]
0x18010e394  inc     r14d
0x18010e397  cmp     r14d, ebp
0x18010e39a  jl      short loc_18010E36C
0x18010e39c  test    rdi, rdi
0x18010e39f  jz      short loc_18010E3B0
0x18010e3a1  mov     rcx, rdi; hMem
0x18010e3a4  call    cs:__imp_LocalFree
0x18010e3ab  nop     dword ptr [rax+rax+00h]
0x18010e3b0  mov     rdx, r13; int
0x18010e3b3  mov     ecx, ebp; this
0x18010e3b5  call    ?BidiFreeMapInfo@PSUI@@YAXHPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BidiFreeMapInfo(int,PSUI::_BIDI_FEATUREOPTION * *)
0x18010e3ba  test    r12d, r12d
0x18010e3bd  js      short loc_18010E3CB
0x18010e3bf  call    cs:__imp_CoUninitialize
0x18010e3c6  nop     dword ptr [rax+rax+00h]
0x18010e3cb  mov     eax, esi
0x18010e3cd  add     rsp, 38h
0x18010e3d1  pop     r15
0x18010e3d3  pop     r14
0x18010e3d5  pop     r13
0x18010e3d7  pop     r12
0x18010e3d9  pop     rdi
0x18010e3da  pop     rsi
0x18010e3db  pop     rbp
0x18010e3dc  pop     rbx
0x18010e3dd  retn
```
