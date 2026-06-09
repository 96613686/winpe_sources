# PSUI::BBidiInitInstallOptions(PSUI::_COMMONINFO *)

- ea: `0x180136dc4`
- end: `0x18013702b`
- name: `?BBidiInitInstallOptions@PSUI@@YAHPEAU_COMMONINFO@1@@Z`
- size: `615`
- prototype: `__int64 __fastcall(PSUI **this, struct PSUI::_COMMONINFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18014cf54`

## callees

- `0x180107214`
- `0x18010e98c`
- `0x180136dc4`
- `0x180137034`
- `0x18014bc20`
- `0x18014be38`
- `0x18014c064`
- `0x18014c1a8`
- `0x18014c264`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180136e09`
- `KERNEL32!GetLastError` at `0x180136e54`
- `KERNEL32!GetLastError` at `0x180136f66`
- `KERNEL32!GetLastError` at `0x180136e09`
- `KERNEL32!GetLastError` at `0x180136e54`
- `KERNEL32!GetLastError` at `0x180136f66`
- `KERNEL32!LocalFree` at `0x180136f92`
- `KERNEL32!LocalFree` at `0x180136fa1`
- `KERNEL32!LocalFree` at `0x180136ff0`
- `KERNEL32!LocalFree` at `0x180136f92`
- `KERNEL32!LocalFree` at `0x180136fa1`
- `KERNEL32!LocalFree` at `0x180136ff0`
- `KERNEL32!LocalAlloc` at `0x180136e9d`
- `KERNEL32!LocalAlloc` at `0x180136ed7`
- `KERNEL32!LocalAlloc` at `0x180136f00`
- `KERNEL32!LocalAlloc` at `0x180136e9d`
- `KERNEL32!LocalAlloc` at `0x180136ed7`
- `KERNEL32!LocalAlloc` at `0x180136f00`
- `ole32!CoInitializeEx` at `0x180136de4`
- `ole32!CoInitializeEx` at `0x180136de4`
- `ole32!CoUninitialize` at `0x18013700b`
- `ole32!CoUninitialize` at `0x18013700b`
- `ole32!CoTaskMemFree` at `0x180136fc3`
- `ole32!CoTaskMemFree` at `0x180136fd4`
- `ole32!CoTaskMemFree` at `0x180136fc3`
- `ole32!CoTaskMemFree` at `0x180136fd4`

## string_xrefs

- `0x180136e18`: `BBidiInitInstallOptions:CoInitializeEx failed %d\n`
- `0x180136e63`: `Failed to BBidiInitInstallOptions %d \n`
- `0x180136e1f`: `PSUI::BBidiInitInstallOptions`
- `0x180136e6a`: `PSUI::BBidiInitInstallOptions`
- `0x180136f7c`: `PSUI::BBidiInitInstallOptions`

## pseudocode

```c
__int64 __fastcall PSUI::BBidiInitInstallOptions(PSUI **this, struct PSUI::_COMMONINFO *a2)
{
  struct PSUI::_BIDIMAP_INFO *v3; // r9
  HRESULT v4; // r12d
  DWORD LastError; // eax
  struct PSUI::_COMMONINFO *v7; // rdi
  unsigned int InfoFromSnapshot; // eax
  struct PSUI::_BIDI_FEATUREOPTION **v9; // r8
  struct PSUI::_BIDI_FEATUREOPTION **v10; // r13
  unsigned int v11; // esi
  __int64 v12; // rbp
  DWORD v13; // eax
  struct PSUI::_BIDI_INFO **v14; // r14
  int i; // eax
  __int64 v16; // r8
  PSUI *v17; // rbx
  __int64 v18; // r8
  void **v19; // r9
  PSUI *v20; // rcx
  unsigned int SingleRequest; // eax
  struct PSUI::_BIDI_INFO *v22; // rdx
  DWORD v23; // eax
  int j; // r14d
  __int64 v25; // rbx
  struct PSUI::_BIDI_FEATUREOPTION **v26[2]; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)v26 = 0;
  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    LastError = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "PSUI::BBidiInitInstallOptions",
      L"BBidiInitInstallOptions:CoInitializeEx failed %d\n",
      LastError);
    return 0;
  }
  v7 = 0;
  InfoFromSnapshot = PSUI::BBidiGetInfoFromSnapshot(this[4], this, (struct PSUI::_COMMONINFO *)v26, v3);
  v10 = v26[1];
  v11 = InfoFromSnapshot;
  v12 = LODWORD(v26[0]);
  if ( InfoFromSnapshot )
  {
    if ( 8 * (unsigned __int64)LODWORD(v26[0]) > 0xFFFFFFFF
      || (v14 = (struct PSUI::_BIDI_INFO **)LocalAlloc(0x40u, (unsigned int)(8 * LODWORD(v26[0])))) == 0 )
    {
      v11 = 0;
      goto LABEL_23;
    }
    for ( i = 0; i < (int)v12; v14[v16] = *(struct PSUI::_BIDI_INFO **)v10[v16] )
      v16 = i++;
    v17 = (PSUI *)LocalAlloc(0x40u, 0x20u);
    if ( v17
      && (unsigned __int64)(32 * v12) <= 0xFFFFFFFF
      && (v7 = (struct PSUI::_COMMONINFO *)LocalAlloc(0x40u, (unsigned int)(32 * v12))) != 0 )
    {
      if ( !PSUI::BBidiInitialize(v17, (struct PSUI::_BIDI_INFO *)(unsigned int)v12, v18, v19)
        || ((v20 = this[3], (int)v12 <= 1)
          ? (SingleRequest = PSUI::BBidiGetSingleRequest(
                               v20,
                               (const unsigned __int16 *)v17,
                               *v14,
                               (unsigned __int16 *)v7))
          : (SingleRequest = PSUI::BBidiGetMultipleRequests(
                               v20,
                               (const unsigned __int16 *)v17,
                               (struct PSUI::_BIDI_INFO *)v14,
                               (unsigned __int16 **const)v7)),
            v11 = SingleRequest,
            PSUI::BidiReleaseInterfaces(v17, v22),
            v11) )
      {
        v11 = PSUI::BBidiMapOutputToOptions(
                (PSUI *)this,
                v7,
                (struct PSUI::_BIDI_OUTPUT *)(unsigned int)v12,
                (__int64)v10);
      }
    }
    else
    {
      v23 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "PSUI::BBidiInitInstallOptions",
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
    "PSUI::BBidiInitInstallOptions",
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
0x180136dc4  push    rbx
0x180136dc6  push    rbp
0x180136dc7  push    rsi
0x180136dc8  push    rdi
0x180136dc9  push    r12
0x180136dcb  push    r13
0x180136dcd  push    r14
0x180136dcf  push    r15
0x180136dd1  sub     rsp, 38h
0x180136dd5  mov     r15, rcx
0x180136dd8  xorps   xmm0, xmm0
0x180136ddb  xor     ecx, ecx; pvReserved
0x180136ddd  xor     edx, edx; dwCoInit
0x180136ddf  movups  xmmword ptr [rsp+78h+var_58], xmm0; struct PSUI::_BIDI_FEATUREOPTION **
0x180136de4  call    cs:__imp_CoInitializeEx
0x180136deb  nop     dword ptr [rax+rax+00h]
0x180136df0  mov     r12d, eax
0x180136df3  mov     eax, 80000000h
0x180136df8  lea     edx, [r12+rax]
0x180136dfc  test    eax, edx
0x180136dfe  jnz     short loc_180136E32
0x180136e00  cmp     r12d, 80010106h
0x180136e07  jz      short loc_180136E32
0x180136e09  call    cs:__imp_GetLastError
0x180136e10  nop     dword ptr [rax+rax+00h]
0x180136e15  mov     r8d, eax
0x180136e18  lea     rdx, aBbidiinitinsta; "BBidiInitInstallOptions:CoInitializeEx "...
0x180136e1f  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180136e26  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180136e2b  xor     eax, eax
0x180136e2d  jmp     loc_180137019
0x180136e32  mov     rcx, [r15+20h]; this
0x180136e36  lea     r8, [rsp+78h+var_58]; struct PSUI::_COMMONINFO *
0x180136e3b  mov     rdx, r15; void *
0x180136e3e  xor     edi, edi
0x180136e40  call    ?BBidiGetInfoFromSnapshot@PSUI@@YAHPEAXPEAU_COMMONINFO@1@PEAU_BIDIMAP_INFO@1@@Z; PSUI::BBidiGetInfoFromSnapshot(void *,PSUI::_COMMONINFO *,PSUI::_BIDIMAP_INFO *)
0x180136e45  mov     r13, [rsp+78h+var_58+8]
0x180136e4a  mov     esi, eax
0x180136e4c  mov     ebp, dword ptr [rsp+78h+var_58]
0x180136e50  test    eax, eax
0x180136e52  jnz     short loc_180136E7B
0x180136e54  call    cs:__imp_GetLastError
0x180136e5b  nop     dword ptr [rax+rax+00h]
0x180136e60  mov     r8d, eax
0x180136e63  lea     rdx, aFailedToBbidii; "Failed to BBidiInitInstallOptions %d \n"
0x180136e6a  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180136e71  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180136e76  jmp     loc_180136FB1
0x180136e7b  lea     rax, ds:0[rbp*8]
0x180136e83  mov     ecx, 0FFFFFFFFh
0x180136e88  mov     rsi, rbp
0x180136e8b  cmp     rax, rcx
0x180136e8e  ja      loc_180136FAF
0x180136e94  mov     ebx, 40h ; '@'
0x180136e99  mov     edx, eax; uBytes
0x180136e9b  mov     ecx, ebx; uFlags
0x180136e9d  call    cs:__imp_LocalAlloc
0x180136ea4  nop     dword ptr [rax+rax+00h]
0x180136ea9  mov     r14, rax
0x180136eac  test    rax, rax
0x180136eaf  jz      loc_180136FAF
0x180136eb5  xor     eax, eax
0x180136eb7  test    ebp, ebp
0x180136eb9  jle     short loc_180136ED0
0x180136ebb  movsxd  r8, eax
0x180136ebe  inc     eax
0x180136ec0  mov     rcx, [r13+r8*8+0]
0x180136ec5  mov     rdx, [rcx]
0x180136ec8  mov     [r14+r8*8], rdx
0x180136ecc  cmp     eax, ebp
0x180136ece  jl      short loc_180136EBB
0x180136ed0  mov     edx, 20h ; ' '; uBytes
0x180136ed5  mov     ecx, ebx; uFlags
0x180136ed7  call    cs:__imp_LocalAlloc
0x180136ede  nop     dword ptr [rax+rax+00h]
0x180136ee3  mov     rbx, rax
0x180136ee6  test    rax, rax
0x180136ee9  jz      short loc_180136F66
0x180136eeb  shl     rsi, 5
0x180136eef  mov     eax, 0FFFFFFFFh
0x180136ef4  cmp     rsi, rax
0x180136ef7  ja      short loc_180136F66
0x180136ef9  mov     edx, esi; uBytes
0x180136efb  mov     ecx, 40h ; '@'; uFlags
0x180136f00  call    cs:__imp_LocalAlloc
0x180136f07  nop     dword ptr [rax+rax+00h]
0x180136f0c  mov     rdi, rax
0x180136f0f  test    rax, rax
0x180136f12  jz      short loc_180136F66
0x180136f14  mov     edx, ebp; struct PSUI::_BIDI_INFO *
0x180136f16  mov     rcx, rbx; this
0x180136f19  call    ?BBidiInitialize@PSUI@@YAHPEAU_BIDI_INFO@1@K@Z; PSUI::BBidiInitialize(PSUI::_BIDI_INFO *,ulong)
0x180136f1e  test    eax, eax
0x180136f20  jz      short loc_180136F51
0x180136f22  mov     rcx, [r15+18h]; this
0x180136f26  mov     r9, rdi; unsigned __int16 *
0x180136f29  mov     rdx, rbx; unsigned __int16 *
0x180136f2c  cmp     ebp, 1
0x180136f2f  jle     short loc_180136F3B
0x180136f31  mov     r8, r14; struct PSUI::_BIDI_INFO *
0x180136f34  call    ?BBidiGetMultipleRequests@PSUI@@YAHPEBGPEAU_BIDI_INFO@1@QEAPEAGPEAU_BIDI_OUTPUT@1@@Z; PSUI::BBidiGetMultipleRequests(ushort const *,PSUI::_BIDI_INFO *,ushort * * const,PSUI::_BIDI_OUTPUT *)
0x180136f39  jmp     short loc_180136F43
0x180136f3b  mov     r8, [r14]; struct PSUI::_BIDI_INFO *
0x180136f3e  call    ?BBidiGetSingleRequest@PSUI@@YAHPEBGPEAU_BIDI_INFO@1@PEAGPEAU_BIDI_OUTPUT@1@@Z; PSUI::BBidiGetSingleRequest(ushort const *,PSUI::_BIDI_INFO *,ushort *,PSUI::_BIDI_OUTPUT *)
0x180136f43  mov     rcx, rbx; this
0x180136f46  mov     esi, eax
0x180136f48  call    ?BidiReleaseInterfaces@PSUI@@YAXPEAU_BIDI_INFO@1@@Z; PSUI::BidiReleaseInterfaces(PSUI::_BIDI_INFO *)
0x180136f4d  test    esi, esi
0x180136f4f  jz      short loc_180136F8F
0x180136f51  mov     r9, r13; unsigned int
0x180136f54  mov     r8d, ebp; struct PSUI::_BIDI_OUTPUT *
0x180136f57  mov     rdx, rdi; struct PSUI::_COMMONINFO *
0x180136f5a  mov     rcx, r15; this
0x180136f5d  call    ?BBidiMapOutputToOptions@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_BIDI_OUTPUT@1@KPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BBidiMapOutputToOptions(PSUI::_COMMONINFO *,PSUI::_BIDI_OUTPUT *,ulong,PSUI::_BIDI_FEATUREOPTION * *)
0x180136f62  mov     esi, eax
0x180136f64  jmp     short loc_180136F8F
0x180136f66  call    cs:__imp_GetLastError
0x180136f6d  nop     dword ptr [rax+rax+00h]
0x180136f72  mov     r8d, eax
0x180136f75  lea     rdx, aFailedToAllocM; "Failed to alloc memory for pBidiInfo or"...
0x180136f7c  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180136f83  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180136f88  xor     esi, esi
0x180136f8a  test    rbx, rbx
0x180136f8d  jz      short loc_180136F9E
0x180136f8f  mov     rcx, rbx; hMem
0x180136f92  call    cs:__imp_LocalFree
0x180136f99  nop     dword ptr [rax+rax+00h]
0x180136f9e  mov     rcx, r14; hMem
0x180136fa1  call    cs:__imp_LocalFree
0x180136fa8  nop     dword ptr [rax+rax+00h]
0x180136fad  jmp     short loc_180136FB1
0x180136faf  xor     esi, esi
0x180136fb1  xor     r14d, r14d
0x180136fb4  test    ebp, ebp
0x180136fb6  jle     short loc_180136FE8
0x180136fb8  movsxd  rbx, r14d
0x180136fbb  shl     rbx, 5
0x180136fbf  mov     rcx, [rbx+rdi]; pv
0x180136fc3  call    cs:__imp_CoTaskMemFree
0x180136fca  nop     dword ptr [rax+rax+00h]
0x180136fcf  mov     rcx, [rbx+rdi+10h]; pv
0x180136fd4  call    cs:__imp_CoTaskMemFree
0x180136fdb  nop     dword ptr [rax+rax+00h]
0x180136fe0  inc     r14d
0x180136fe3  cmp     r14d, ebp
0x180136fe6  jl      short loc_180136FB8
0x180136fe8  test    rdi, rdi
0x180136feb  jz      short loc_180136FFC
0x180136fed  mov     rcx, rdi; hMem
0x180136ff0  call    cs:__imp_LocalFree
0x180136ff7  nop     dword ptr [rax+rax+00h]
0x180136ffc  mov     rdx, r13; int
0x180136fff  mov     ecx, ebp; this
0x180137001  call    ?BidiFreeMapInfo@PSUI@@YAXHPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BidiFreeMapInfo(int,PSUI::_BIDI_FEATUREOPTION * *)
0x180137006  test    r12d, r12d
0x180137009  js      short loc_180137017
0x18013700b  call    cs:__imp_CoUninitialize
0x180137012  nop     dword ptr [rax+rax+00h]
0x180137017  mov     eax, esi
0x180137019  add     rsp, 38h
0x18013701d  pop     r15
0x18013701f  pop     r14
0x180137021  pop     r13
0x180137023  pop     r12
0x180137025  pop     rdi
0x180137026  pop     rsi
0x180137027  pop     rbp
0x180137028  pop     rbx
0x180137029  retn
```
