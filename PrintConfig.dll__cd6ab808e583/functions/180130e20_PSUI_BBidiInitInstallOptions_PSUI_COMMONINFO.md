# PSUI::BBidiInitInstallOptions(PSUI::_COMMONINFO *)

- ea: `0x180130e20`
- end: `0x1801310e2`
- name: `?BBidiInitInstallOptions@PSUI@@YAHPEAU_COMMONINFO@1@@Z`
- size: `706`
- prototype: `__int64 __fastcall(PSUI *__hidden this, struct PSUI::_COMMONINFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801464b0`

## callees

- `0x180102674`
- `0x180109c54`
- `0x180121fa8`
- `0x180130e20`
- `0x1801310e8`
- `0x180145344`
- `0x180145554`
- `0x180145768`
- `0x1801458a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180130e66`
- `KERNEL32!GetLastError` at `0x180130ea7`
- `KERNEL32!GetLastError` at `0x180131049`
- `KERNEL32!GetLastError` at `0x180130e66`
- `KERNEL32!GetLastError` at `0x180130ea7`
- `KERNEL32!GetLastError` at `0x180131049`
- `KERNEL32!LocalFree` at `0x18013106f`
- `KERNEL32!LocalFree` at `0x180131078`
- `KERNEL32!LocalFree` at `0x1801310b2`
- `KERNEL32!LocalFree` at `0x18013106f`
- `KERNEL32!LocalFree` at `0x180131078`
- `KERNEL32!LocalFree` at `0x1801310b2`
- `KERNEL32!LocalAlloc` at `0x180130eea`
- `KERNEL32!LocalAlloc` at `0x180130f25`
- `KERNEL32!LocalAlloc` at `0x180130f4d`
- `KERNEL32!LocalAlloc` at `0x180130f90`
- `KERNEL32!LocalAlloc` at `0x180130eea`
- `KERNEL32!LocalAlloc` at `0x180130f25`
- `KERNEL32!LocalAlloc` at `0x180130f4d`
- `KERNEL32!LocalAlloc` at `0x180130f90`
- `ole32!CoInitializeEx` at `0x180130e40`
- `ole32!CoInitializeEx` at `0x180130e40`
- `ole32!CoUninitialize` at `0x1801310c9`
- `ole32!CoUninitialize` at `0x1801310c9`
- `ole32!CoTaskMemFree` at `0x180131093`
- `ole32!CoTaskMemFree` at `0x18013109e`
- `ole32!CoTaskMemFree` at `0x180131093`
- `ole32!CoTaskMemFree` at `0x18013109e`

## string_xrefs

- `0x180130e6f`: `BBidiInitInstallOptions:CoInitializeEx failed %d\n`
- `0x180130eb0`: `Failed to BBidiInitInstallOptions %d \n`
- `0x180130e76`: `PSUI::BBidiInitInstallOptions`
- `0x180130eb7`: `PSUI::BBidiInitInstallOptions`
- `0x180131059`: `PSUI::BBidiInitInstallOptions`

## pseudocode

```c
__int64 __fastcall PSUI::BBidiInitInstallOptions(PSUI **this, struct PSUI::_COMMONINFO *a2)
{
  struct PSUI::_BIDIMAP_INFO *v3; // r9
  HRESULT v4; // r15d
  DWORD LastError; // eax
  unsigned __int16 *v7; // r14
  unsigned int InfoFromSnapshot; // eax
  struct PSUI::_BIDI_FEATUREOPTION **v9; // r8
  __int64 v10; // rsi
  unsigned int v11; // edi
  DWORD v12; // eax
  struct PSUI::_BIDI_INFO **v13; // r12
  int v14; // r9d
  struct PSUI::_BIDI_FEATUREOPTION **v15; // rax
  __int64 v16; // r8
  HLOCAL v17; // rbx
  struct PSUI::_BIDI_INFO *v18; // rdx
  void **v19; // r9
  int v20; // edi
  const struct _GUID *v21; // rax
  void **v22; // r9
  const struct _GUID *v23; // rbp
  PSUI *v24; // rcx
  unsigned int SingleRequest; // eax
  struct PSUI::_BIDI_INFO *v26; // rdx
  DWORD v27; // eax
  int i; // ebp
  __int64 v29; // rbx
  struct PSUI::_BIDI_FEATUREOPTION **v30[2]; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)v30 = 0;
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
  InfoFromSnapshot = PSUI::BBidiGetInfoFromSnapshot(this[4], this, (struct PSUI::_COMMONINFO *)v30, v3);
  v10 = LODWORD(v30[0]);
  v11 = InfoFromSnapshot;
  if ( InfoFromSnapshot )
  {
    if ( 8 * (unsigned __int64)LODWORD(v30[0]) > 0xFFFFFFFF
      || (v13 = (struct PSUI::_BIDI_INFO **)LocalAlloc(0x40u, (unsigned int)(8 * LODWORD(v30[0])))) == 0 )
    {
      v11 = 0;
      goto LABEL_33;
    }
    v14 = 0;
    if ( (int)v10 > 0 )
    {
      v15 = v30[1];
      do
      {
        v16 = v14++;
        v13[v16] = *(struct PSUI::_BIDI_INFO **)v15[v16];
      }
      while ( v14 < (int)v10 );
    }
    v17 = LocalAlloc(0x40u, 0x20u);
    if ( v17
      && (unsigned __int64)(32 * v10) <= 0xFFFFFFFF
      && (v7 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(32 * v10))) != 0 )
    {
      v20 = v10;
      if ( (_DWORD)v10 )
      {
        if ( (unsigned int)UniDrvUI::BBidiGetInterfaces(
                             (UniDrvUI *)&CLSID_BidiSpl,
                             &IID_IBidiSpl,
                             (const struct _GUID *)v17,
                             v19) )
        {
          v21 = (const struct _GUID *)LocalAlloc(0x40u, 8 * v10);
          v23 = v21;
          if ( v21 )
          {
            *((_QWORD *)v17 + 1) = v21;
            if ( (unsigned int)v10 > 1 )
              UniDrvUI::BBidiGetInterfaces(
                (UniDrvUI *)&CLSID_BidiRequestContainer,
                &IID_IBidiRequestContainer,
                (const struct _GUID *)v17 + 1,
                v22);
            while ( (unsigned int)UniDrvUI::BBidiGetInterfaces(
                                    (UniDrvUI *)&CLSID_BidiRequest,
                                    &IID_IBidiRequest,
                                    v23,
                                    v22) )
            {
              ++*((_DWORD *)v17 + 6);
              v23 = (const struct _GUID *)((char *)v23 + 8);
              if ( !--v20 )
              {
                v24 = this[3];
                if ( (int)v10 <= 1 )
                  SingleRequest = PSUI::BBidiGetSingleRequest(
                                    v24,
                                    (const unsigned __int16 *)v17,
                                    *v13,
                                    v7,
                                    (struct PSUI::_BIDI_OUTPUT *)v30[0]);
                else
                  SingleRequest = PSUI::BBidiGetMultipleRequests(
                                    v24,
                                    (const unsigned __int16 *)v17,
                                    (struct PSUI::_BIDI_INFO *)v13,
                                    (unsigned __int16 **const)v7,
                                    (struct PSUI::_BIDI_OUTPUT *)v30[0]);
                v11 = SingleRequest;
                PSUI::BidiReleaseInterfaces((PSUI *)v17, v26);
                if ( !v11 )
                  goto LABEL_30;
                goto LABEL_27;
              }
            }
          }
        }
      }
      PSUI::BidiReleaseInterfaces((PSUI *)v17, v18);
LABEL_27:
      v11 = PSUI::BBidiMapOutputToOptions(
              (PSUI *)this,
              (struct PSUI::_COMMONINFO *)v7,
              (struct PSUI::_BIDI_OUTPUT *)(unsigned int)v10,
              (unsigned int)v30[1],
              v30[0]);
    }
    else
    {
      v27 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "PSUI::BBidiInitInstallOptions",
        L"Failed to alloc memory for pBidiInfo or pBidiOutput: %d\n",
        v27);
      v11 = 0;
      if ( !v17 )
      {
LABEL_31:
        LocalFree(v13);
        goto LABEL_33;
      }
    }
LABEL_30:
    LocalFree(v17);
    goto LABEL_31;
  }
  v12 = GetLastError();
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "PSUI::BBidiInitInstallOptions",
    L"Failed to BBidiInitInstallOptions %d \n",
    v12);
LABEL_33:
  for ( i = 0; i < (int)v10; ++i )
  {
    v29 = 16LL * i;
    CoTaskMemFree(*(LPVOID *)&v7[v29]);
    CoTaskMemFree(*(LPVOID *)&v7[v29 + 8]);
  }
  if ( v7 )
    LocalFree(v7);
  PSUI::BidiFreeMapInfo((PSUI *)(unsigned int)v10, (int)v30[1], v9);
  if ( v4 >= 0 )
    CoUninitialize();
  return v11;
}

```

## disassembly

```asm
0x180130e20  push    rbx
0x180130e22  push    rbp
0x180130e23  push    rsi
0x180130e24  push    rdi
0x180130e25  push    r12
0x180130e27  push    r13
0x180130e29  push    r14
0x180130e2b  push    r15
0x180130e2d  sub     rsp, 38h
0x180130e31  mov     r13, rcx
0x180130e34  xorps   xmm0, xmm0
0x180130e37  xor     ecx, ecx; pvReserved
0x180130e39  xor     edx, edx; dwCoInit
0x180130e3b  movups  xmmword ptr [rsp+78h+var_58], xmm0; struct PSUI::_BIDI_FEATUREOPTION **
0x180130e40  call    cs:__imp_CoInitializeEx
0x180130e46  mov     r15d, eax
0x180130e49  mov     [rsp+78h+arg_8], eax
0x180130e50  mov     eax, 80000000h
0x180130e55  lea     edx, [r15+rax]
0x180130e59  test    eax, edx
0x180130e5b  jnz     short loc_180130E89
0x180130e5d  cmp     r15d, 80010106h
0x180130e64  jz      short loc_180130E89
0x180130e66  call    cs:__imp_GetLastError
0x180130e6c  mov     r8d, eax
0x180130e6f  lea     rdx, aBbidiinitinsta; "BBidiInitInstallOptions:CoInitializeEx "...
0x180130e76  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180130e7d  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180130e82  xor     eax, eax
0x180130e84  jmp     loc_1801310D1
0x180130e89  mov     rcx, [r13+20h]; this
0x180130e8d  lea     r8, [rsp+78h+var_58]; struct PSUI::_COMMONINFO *
0x180130e92  mov     rdx, r13; void *
0x180130e95  xor     r14d, r14d
0x180130e98  call    ?BBidiGetInfoFromSnapshot@PSUI@@YAHPEAXPEAU_COMMONINFO@1@PEAU_BIDIMAP_INFO@1@@Z; PSUI::BBidiGetInfoFromSnapshot(void *,PSUI::_COMMONINFO *,PSUI::_BIDIMAP_INFO *)
0x180130e9d  mov     esi, dword ptr [rsp+78h+var_58]
0x180130ea1  mov     edi, eax
0x180130ea3  test    eax, eax
0x180130ea5  jnz     short loc_180130EC8
0x180130ea7  call    cs:__imp_GetLastError
0x180130ead  mov     r8d, eax
0x180130eb0  lea     rdx, aFailedToBbidii; "Failed to BBidiInitInstallOptions %d \n"
0x180130eb7  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180130ebe  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180130ec3  jmp     loc_180131082
0x180130ec8  lea     rax, ds:0[rsi*8]
0x180130ed0  mov     ecx, 0FFFFFFFFh
0x180130ed5  mov     rdi, rsi
0x180130ed8  cmp     rax, rcx
0x180130edb  ja      loc_180131080
0x180130ee1  mov     ebp, 40h ; '@'
0x180130ee6  mov     edx, eax; uBytes
0x180130ee8  mov     ecx, ebp; uFlags
0x180130eea  call    cs:__imp_LocalAlloc
0x180130ef0  mov     r12, rax
0x180130ef3  test    rax, rax
0x180130ef6  jz      loc_180131080
0x180130efc  xor     r9d, r9d
0x180130eff  test    esi, esi
0x180130f01  jle     short loc_180130F1E
0x180130f03  mov     rax, [rsp+78h+var_58+8]
0x180130f08  movsxd  r8, r9d
0x180130f0b  inc     r9d
0x180130f0e  mov     rcx, [rax+r8*8]
0x180130f12  mov     rdx, [rcx]
0x180130f15  mov     [r12+r8*8], rdx
0x180130f19  cmp     r9d, esi
0x180130f1c  jl      short loc_180130F08
0x180130f1e  mov     edx, 20h ; ' '; uBytes
0x180130f23  mov     ecx, ebp; uFlags
0x180130f25  call    cs:__imp_LocalAlloc
0x180130f2b  mov     rbx, rax
0x180130f2e  test    rax, rax
0x180130f31  jz      loc_180131049
0x180130f37  shl     rdi, 5
0x180130f3b  mov     eax, 0FFFFFFFFh
0x180130f40  cmp     rdi, rax
0x180130f43  ja      loc_180131049
0x180130f49  mov     edx, edi; uBytes
0x180130f4b  mov     ecx, ebp; uFlags
0x180130f4d  call    cs:__imp_LocalAlloc
0x180130f53  mov     r14, rax
0x180130f56  test    rax, rax
0x180130f59  jz      loc_180131049
0x180130f5f  xor     r15d, r15d
0x180130f62  mov     rdi, rsi
0x180130f65  test    esi, esi
0x180130f67  jz      loc_180130FED
0x180130f6d  mov     r8, rbx; struct _GUID *
0x180130f70  lea     rdx, IID_IBidiSpl; struct _GUID *
0x180130f77  lea     rcx, CLSID_BidiSpl; this
0x180130f7e  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x180130f83  test    eax, eax
0x180130f85  jz      short loc_180130FED
0x180130f87  mov     rdx, rsi
0x180130f8a  mov     ecx, ebp; uFlags
0x180130f8c  shl     rdx, 3; uBytes
0x180130f90  call    cs:__imp_LocalAlloc
0x180130f96  mov     rbp, rax
0x180130f99  test    rax, rax
0x180130f9c  jz      short loc_180130FED
0x180130f9e  mov     [rbx+8], rax
0x180130fa2  cmp     esi, 1
0x180130fa5  jbe     short loc_180130FBE
0x180130fa7  lea     r8, [rbx+10h]; struct _GUID *
0x180130fab  lea     rdx, IID_IBidiRequestContainer; struct _GUID *
0x180130fb2  lea     rcx, CLSID_BidiRequestContainer; this
0x180130fb9  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x180130fbe  mov     r8, rbp; struct _GUID *
0x180130fc1  lea     rdx, IID_IBidiRequest; struct _GUID *
0x180130fc8  lea     rcx, CLSID_BidiRequest; this
0x180130fcf  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x180130fd4  mov     r15d, eax
0x180130fd7  test    eax, eax
0x180130fd9  jz      short loc_180130FED
0x180130fdb  inc     dword ptr [rbx+18h]
0x180130fde  mov     eax, 0FFFFFFFFh
0x180130fe3  add     rbp, 8
0x180130fe7  add     edi, eax
0x180130fe9  jnz     short loc_180130FBE
0x180130feb  jmp     short loc_180130FFA
0x180130fed  mov     rcx, rbx; this
0x180130ff0  call    ?BidiReleaseInterfaces@PSUI@@YAXPEAU_BIDI_INFO@1@@Z; PSUI::BidiReleaseInterfaces(PSUI::_BIDI_INFO *)
0x180130ff5  test    r15d, r15d
0x180130ff8  jz      short loc_18013102A
0x180130ffa  mov     rcx, [r13+18h]; this
0x180130ffe  mov     r9, r14; unsigned __int16 *
0x180131001  mov     rdx, rbx; unsigned __int16 *
0x180131004  cmp     esi, 1
0x180131007  jle     short loc_180131013
0x180131009  mov     r8, r12; struct PSUI::_BIDI_INFO *
0x18013100c  call    ?BBidiGetMultipleRequests@PSUI@@YAHPEBGPEAU_BIDI_INFO@1@QEAPEAGPEAU_BIDI_OUTPUT@1@@Z; PSUI::BBidiGetMultipleRequests(ushort const *,PSUI::_BIDI_INFO *,ushort * * const,PSUI::_BIDI_OUTPUT *)
0x180131011  jmp     short loc_18013101C
0x180131013  mov     r8, [r12]; struct PSUI::_BIDI_INFO *
0x180131017  call    ?BBidiGetSingleRequest@PSUI@@YAHPEBGPEAU_BIDI_INFO@1@PEAGPEAU_BIDI_OUTPUT@1@@Z; PSUI::BBidiGetSingleRequest(ushort const *,PSUI::_BIDI_INFO *,ushort *,PSUI::_BIDI_OUTPUT *)
0x18013101c  mov     rcx, rbx; this
0x18013101f  mov     edi, eax
0x180131021  call    ?BidiReleaseInterfaces@PSUI@@YAXPEAU_BIDI_INFO@1@@Z; PSUI::BidiReleaseInterfaces(PSUI::_BIDI_INFO *)
0x180131026  test    edi, edi
0x180131028  jz      short loc_18013103F
0x18013102a  mov     r9, [rsp+78h+var_58+8]; unsigned int
0x18013102f  mov     r8d, esi; struct PSUI::_BIDI_OUTPUT *
0x180131032  mov     rdx, r14; struct PSUI::_COMMONINFO *
0x180131035  mov     rcx, r13; this
0x180131038  call    ?BBidiMapOutputToOptions@PSUI@@YAHPEAU_COMMONINFO@1@PEAU_BIDI_OUTPUT@1@KPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BBidiMapOutputToOptions(PSUI::_COMMONINFO *,PSUI::_BIDI_OUTPUT *,ulong,PSUI::_BIDI_FEATUREOPTION * *)
0x18013103d  mov     edi, eax
0x18013103f  mov     r15d, [rsp+78h+arg_8]
0x180131047  jmp     short loc_18013106C
0x180131049  call    cs:__imp_GetLastError
0x18013104f  mov     r8d, eax
0x180131052  lea     rdx, aFailedToAllocM; "Failed to alloc memory for pBidiInfo or"...
0x180131059  lea     rcx, aPsuiBbidiiniti; "PSUI::BBidiInitInstallOptions"
0x180131060  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180131065  xor     edi, edi
0x180131067  test    rbx, rbx
0x18013106a  jz      short loc_180131075
0x18013106c  mov     rcx, rbx; hMem
0x18013106f  call    cs:__imp_LocalFree
0x180131075  mov     rcx, r12; hMem
0x180131078  call    cs:__imp_LocalFree
0x18013107e  jmp     short loc_180131082
0x180131080  xor     edi, edi
0x180131082  xor     ebp, ebp
0x180131084  test    esi, esi
0x180131086  jle     short loc_1801310AA
0x180131088  movsxd  rbx, ebp
0x18013108b  shl     rbx, 5
0x18013108f  mov     rcx, [rbx+r14]; pv
0x180131093  call    cs:__imp_CoTaskMemFree
0x180131099  mov     rcx, [rbx+r14+10h]; pv
0x18013109e  call    cs:__imp_CoTaskMemFree
0x1801310a4  inc     ebp
0x1801310a6  cmp     ebp, esi
0x1801310a8  jl      short loc_180131088
0x1801310aa  test    r14, r14
0x1801310ad  jz      short loc_1801310B8
0x1801310af  mov     rcx, r14; hMem
0x1801310b2  call    cs:__imp_LocalFree
0x1801310b8  mov     rdx, [rsp+78h+var_58+8]; int
0x1801310bd  mov     ecx, esi; this
0x1801310bf  call    ?BidiFreeMapInfo@PSUI@@YAXHPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BidiFreeMapInfo(int,PSUI::_BIDI_FEATUREOPTION * *)
0x1801310c4  test    r15d, r15d
0x1801310c7  js      short loc_1801310CF
0x1801310c9  call    cs:__imp_CoUninitialize
0x1801310cf  mov     eax, edi
0x1801310d1  add     rsp, 38h
0x1801310d5  pop     r15
0x1801310d7  pop     r14
0x1801310d9  pop     r13
0x1801310db  pop     r12
0x1801310dd  pop     rdi
0x1801310de  pop     rsi
0x1801310df  pop     rbp
0x1801310e0  pop     rbx
0x1801310e1  retn
```
