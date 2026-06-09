# UniDrvUI::BBidiInitInstallOptions(UniDrvUI::_COMMONINFO *)

- ea: `0x18010942c`
- end: `0x1801096ee`
- name: `?BBidiInitInstallOptions@UniDrvUI@@YAHPEAU_COMMONINFO@1@@Z`
- size: `706`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801231e4`

## callees

- `0x180102674`
- `0x18010942c`
- `0x1801096f4`
- `0x180109c54`
- `0x180121d98`
- `0x180121fa8`
- `0x180122038`
- `0x18012224c`
- `0x180122384`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180109472`
- `KERNEL32!GetLastError` at `0x1801094b3`
- `KERNEL32!GetLastError` at `0x180109655`
- `KERNEL32!GetLastError` at `0x180109472`
- `KERNEL32!GetLastError` at `0x1801094b3`
- `KERNEL32!GetLastError` at `0x180109655`
- `KERNEL32!LocalFree` at `0x18010967b`
- `KERNEL32!LocalFree` at `0x180109684`
- `KERNEL32!LocalFree` at `0x1801096be`
- `KERNEL32!LocalFree` at `0x18010967b`
- `KERNEL32!LocalFree` at `0x180109684`
- `KERNEL32!LocalFree` at `0x1801096be`
- `KERNEL32!LocalAlloc` at `0x1801094f6`
- `KERNEL32!LocalAlloc` at `0x180109531`
- `KERNEL32!LocalAlloc` at `0x180109559`
- `KERNEL32!LocalAlloc` at `0x18010959c`
- `KERNEL32!LocalAlloc` at `0x1801094f6`
- `KERNEL32!LocalAlloc` at `0x180109531`
- `KERNEL32!LocalAlloc` at `0x180109559`
- `KERNEL32!LocalAlloc` at `0x18010959c`
- `ole32!CoInitializeEx` at `0x18010944c`
- `ole32!CoInitializeEx` at `0x18010944c`
- `ole32!CoUninitialize` at `0x1801096d5`
- `ole32!CoUninitialize` at `0x1801096d5`
- `ole32!CoTaskMemFree` at `0x18010969f`
- `ole32!CoTaskMemFree` at `0x1801096aa`
- `ole32!CoTaskMemFree` at `0x18010969f`
- `ole32!CoTaskMemFree` at `0x1801096aa`

## string_xrefs

- `0x180109482`: `UniDrvUI::BBidiInitInstallOptions`
- `0x1801094c3`: `UniDrvUI::BBidiInitInstallOptions`
- `0x180109665`: `UniDrvUI::BBidiInitInstallOptions`
- `0x18010947b`: `BBidiInitInstallOptions:CoInitializeEx failed %d\n`
- `0x1801094bc`: `Failed to BBidiInitInstallOptions %d \n`

## pseudocode

```c
__int64 __fastcall UniDrvUI::BBidiInitInstallOptions(UniDrvUI **this, struct UniDrvUI::_COMMONINFO *a2)
{
  struct UniDrvUI::_BIDIMAP_INFO *v3; // r9
  HRESULT v4; // r15d
  DWORD LastError; // eax
  unsigned __int16 *v7; // r14
  unsigned int InfoFromSnapshot; // eax
  struct PSUI::_BIDI_FEATUREOPTION **v9; // r8
  __int64 v10; // rsi
  unsigned int v11; // edi
  DWORD v12; // eax
  struct UniDrvUI::_BIDI_INFO **v13; // r12
  int v14; // r9d
  struct UniDrvUI::_BIDI_FEATUREOPTION **v15; // rax
  __int64 v16; // r8
  HLOCAL v17; // rbx
  struct UniDrvUI::_BIDI_INFO *v18; // rdx
  void **v19; // r9
  int v20; // edi
  const struct _GUID *v21; // rax
  void **v22; // r9
  const struct _GUID *v23; // rbp
  UniDrvUI *v24; // rcx
  unsigned int SingleRequest; // eax
  struct UniDrvUI::_BIDI_INFO *v26; // rdx
  DWORD v27; // eax
  int i; // ebp
  __int64 v29; // rbx
  struct UniDrvUI::_BIDI_FEATUREOPTION **v30[2]; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)v30 = 0;
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
  InfoFromSnapshot = UniDrvUI::BBidiGetInfoFromSnapshot(this[4], this, (struct UniDrvUI::_COMMONINFO *)v30, v3);
  v10 = LODWORD(v30[0]);
  v11 = InfoFromSnapshot;
  if ( InfoFromSnapshot )
  {
    if ( 8 * (unsigned __int64)LODWORD(v30[0]) > 0xFFFFFFFF
      || (v13 = (struct UniDrvUI::_BIDI_INFO **)LocalAlloc(0x40u, (unsigned int)(8 * LODWORD(v30[0])))) == 0 )
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
        v13[v16] = *(struct UniDrvUI::_BIDI_INFO **)v15[v16];
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
                  SingleRequest = UniDrvUI::BBidiGetSingleRequest(
                                    v24,
                                    (const unsigned __int16 *)v17,
                                    *v13,
                                    v7,
                                    (struct UniDrvUI::_BIDI_OUTPUT *)v30[0]);
                else
                  SingleRequest = UniDrvUI::BBidiGetMultipleRequests(
                                    v24,
                                    (const unsigned __int16 *)v17,
                                    (struct UniDrvUI::_BIDI_INFO *)v13,
                                    (unsigned __int16 **const)v7,
                                    (struct UniDrvUI::_BIDI_OUTPUT *)v30[0]);
                v11 = SingleRequest;
                UniDrvUI::BidiReleaseInterfaces((UniDrvUI *)v17, v26);
                if ( !v11 )
                  goto LABEL_30;
                goto LABEL_27;
              }
            }
          }
        }
      }
      UniDrvUI::BidiReleaseInterfaces((UniDrvUI *)v17, v18);
LABEL_27:
      v11 = UniDrvUI::BBidiMapOutputToOptions(
              (UniDrvUI *)this,
              (struct UniDrvUI::_COMMONINFO *)v7,
              (struct UniDrvUI::_BIDI_OUTPUT *)(unsigned int)v10,
              (unsigned int)v30[1],
              v30[0]);
    }
    else
    {
      v27 = GetLastError();
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::BBidiInitInstallOptions",
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
    "UniDrvUI::BBidiInitInstallOptions",
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
0x18010942c  push    rbx
0x18010942e  push    rbp
0x18010942f  push    rsi
0x180109430  push    rdi
0x180109431  push    r12
0x180109433  push    r13
0x180109435  push    r14
0x180109437  push    r15
0x180109439  sub     rsp, 38h
0x18010943d  mov     r13, rcx
0x180109440  xorps   xmm0, xmm0
0x180109443  xor     ecx, ecx; pvReserved
0x180109445  xor     edx, edx; dwCoInit
0x180109447  movups  xmmword ptr [rsp+78h+var_58], xmm0; struct UniDrvUI::_BIDI_FEATUREOPTION **
0x18010944c  call    cs:__imp_CoInitializeEx
0x180109452  mov     r15d, eax
0x180109455  mov     [rsp+78h+arg_8], eax
0x18010945c  mov     eax, 80000000h
0x180109461  lea     edx, [r15+rax]
0x180109465  test    eax, edx
0x180109467  jnz     short loc_180109495
0x180109469  cmp     r15d, 80010106h
0x180109470  jz      short loc_180109495
0x180109472  call    cs:__imp_GetLastError
0x180109478  mov     r8d, eax
0x18010947b  lea     rdx, aBbidiinitinsta; "BBidiInitInstallOptions:CoInitializeEx "...
0x180109482  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x180109489  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010948e  xor     eax, eax
0x180109490  jmp     loc_1801096DD
0x180109495  mov     rcx, [r13+20h]; this
0x180109499  lea     r8, [rsp+78h+var_58]; struct UniDrvUI::_COMMONINFO *
0x18010949e  mov     rdx, r13; void *
0x1801094a1  xor     r14d, r14d
0x1801094a4  call    ?BBidiGetInfoFromSnapshot@UniDrvUI@@YAHPEAXPEAU_COMMONINFO@1@PEAU_BIDIMAP_INFO@1@@Z; UniDrvUI::BBidiGetInfoFromSnapshot(void *,UniDrvUI::_COMMONINFO *,UniDrvUI::_BIDIMAP_INFO *)
0x1801094a9  mov     esi, dword ptr [rsp+78h+var_58]
0x1801094ad  mov     edi, eax
0x1801094af  test    eax, eax
0x1801094b1  jnz     short loc_1801094D4
0x1801094b3  call    cs:__imp_GetLastError
0x1801094b9  mov     r8d, eax
0x1801094bc  lea     rdx, aFailedToBbidii; "Failed to BBidiInitInstallOptions %d \n"
0x1801094c3  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x1801094ca  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801094cf  jmp     loc_18010968E
0x1801094d4  lea     rax, ds:0[rsi*8]
0x1801094dc  mov     ecx, 0FFFFFFFFh
0x1801094e1  mov     rdi, rsi
0x1801094e4  cmp     rax, rcx
0x1801094e7  ja      loc_18010968C
0x1801094ed  mov     ebp, 40h ; '@'
0x1801094f2  mov     edx, eax; uBytes
0x1801094f4  mov     ecx, ebp; uFlags
0x1801094f6  call    cs:__imp_LocalAlloc
0x1801094fc  mov     r12, rax
0x1801094ff  test    rax, rax
0x180109502  jz      loc_18010968C
0x180109508  xor     r9d, r9d
0x18010950b  test    esi, esi
0x18010950d  jle     short loc_18010952A
0x18010950f  mov     rax, [rsp+78h+var_58+8]
0x180109514  movsxd  r8, r9d
0x180109517  inc     r9d
0x18010951a  mov     rcx, [rax+r8*8]
0x18010951e  mov     rdx, [rcx]
0x180109521  mov     [r12+r8*8], rdx
0x180109525  cmp     r9d, esi
0x180109528  jl      short loc_180109514
0x18010952a  mov     edx, 20h ; ' '; uBytes
0x18010952f  mov     ecx, ebp; uFlags
0x180109531  call    cs:__imp_LocalAlloc
0x180109537  mov     rbx, rax
0x18010953a  test    rax, rax
0x18010953d  jz      loc_180109655
0x180109543  shl     rdi, 5
0x180109547  mov     eax, 0FFFFFFFFh
0x18010954c  cmp     rdi, rax
0x18010954f  ja      loc_180109655
0x180109555  mov     edx, edi; uBytes
0x180109557  mov     ecx, ebp; uFlags
0x180109559  call    cs:__imp_LocalAlloc
0x18010955f  mov     r14, rax
0x180109562  test    rax, rax
0x180109565  jz      loc_180109655
0x18010956b  xor     r15d, r15d
0x18010956e  mov     rdi, rsi
0x180109571  test    esi, esi
0x180109573  jz      loc_1801095F9
0x180109579  mov     r8, rbx; struct _GUID *
0x18010957c  lea     rdx, IID_IBidiSpl; struct _GUID *
0x180109583  lea     rcx, CLSID_BidiSpl; this
0x18010958a  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x18010958f  test    eax, eax
0x180109591  jz      short loc_1801095F9
0x180109593  mov     rdx, rsi
0x180109596  mov     ecx, ebp; uFlags
0x180109598  shl     rdx, 3; uBytes
0x18010959c  call    cs:__imp_LocalAlloc
0x1801095a2  mov     rbp, rax
0x1801095a5  test    rax, rax
0x1801095a8  jz      short loc_1801095F9
0x1801095aa  mov     [rbx+8], rax
0x1801095ae  cmp     esi, 1
0x1801095b1  jbe     short loc_1801095CA
0x1801095b3  lea     r8, [rbx+10h]; struct _GUID *
0x1801095b7  lea     rdx, IID_IBidiRequestContainer; struct _GUID *
0x1801095be  lea     rcx, CLSID_BidiRequestContainer; this
0x1801095c5  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x1801095ca  mov     r8, rbp; struct _GUID *
0x1801095cd  lea     rdx, IID_IBidiRequest; struct _GUID *
0x1801095d4  lea     rcx, CLSID_BidiRequest; this
0x1801095db  call    ?BBidiGetInterfaces@UniDrvUI@@YAHAEBU_GUID@@PEBU2@PEAPEAX@Z; UniDrvUI::BBidiGetInterfaces(_GUID const &,_GUID const *,void * *)
0x1801095e0  mov     r15d, eax
0x1801095e3  test    eax, eax
0x1801095e5  jz      short loc_1801095F9
0x1801095e7  inc     dword ptr [rbx+18h]
0x1801095ea  mov     eax, 0FFFFFFFFh
0x1801095ef  add     rbp, 8
0x1801095f3  add     edi, eax
0x1801095f5  jnz     short loc_1801095CA
0x1801095f7  jmp     short loc_180109606
0x1801095f9  mov     rcx, rbx; this
0x1801095fc  call    ?BidiReleaseInterfaces@UniDrvUI@@YAXPEAU_BIDI_INFO@1@@Z; UniDrvUI::BidiReleaseInterfaces(UniDrvUI::_BIDI_INFO *)
0x180109601  test    r15d, r15d
0x180109604  jz      short loc_180109636
0x180109606  mov     rcx, [r13+18h]; this
0x18010960a  mov     r9, r14; unsigned __int16 *
0x18010960d  mov     rdx, rbx; unsigned __int16 *
0x180109610  cmp     esi, 1
0x180109613  jle     short loc_18010961F
0x180109615  mov     r8, r12; struct UniDrvUI::_BIDI_INFO *
0x180109618  call    ?BBidiGetMultipleRequests@UniDrvUI@@YAHPEBGPEAU_BIDI_INFO@1@QEAPEAGPEAU_BIDI_OUTPUT@1@@Z; UniDrvUI::BBidiGetMultipleRequests(ushort const *,UniDrvUI::_BIDI_INFO *,ushort * * const,UniDrvUI::_BIDI_OUTPUT *)
0x18010961d  jmp     short loc_180109628
0x18010961f  mov     r8, [r12]; struct UniDrvUI::_BIDI_INFO *
0x180109623  call    ?BBidiGetSingleRequest@UniDrvUI@@YAHPEBGPEAU_BIDI_INFO@1@PEAGPEAU_BIDI_OUTPUT@1@@Z; UniDrvUI::BBidiGetSingleRequest(ushort const *,UniDrvUI::_BIDI_INFO *,ushort *,UniDrvUI::_BIDI_OUTPUT *)
0x180109628  mov     rcx, rbx; this
0x18010962b  mov     edi, eax
0x18010962d  call    ?BidiReleaseInterfaces@UniDrvUI@@YAXPEAU_BIDI_INFO@1@@Z; UniDrvUI::BidiReleaseInterfaces(UniDrvUI::_BIDI_INFO *)
0x180109632  test    edi, edi
0x180109634  jz      short loc_18010964B
0x180109636  mov     r9, [rsp+78h+var_58+8]; unsigned int
0x18010963b  mov     r8d, esi; struct UniDrvUI::_BIDI_OUTPUT *
0x18010963e  mov     rdx, r14; struct UniDrvUI::_COMMONINFO *
0x180109641  mov     rcx, r13; this
0x180109644  call    ?BBidiMapOutputToOptions@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_BIDI_OUTPUT@1@KPEAPEAU_BIDI_FEATUREOPTION@1@@Z; UniDrvUI::BBidiMapOutputToOptions(UniDrvUI::_COMMONINFO *,UniDrvUI::_BIDI_OUTPUT *,ulong,UniDrvUI::_BIDI_FEATUREOPTION * *)
0x180109649  mov     edi, eax
0x18010964b  mov     r15d, [rsp+78h+arg_8]
0x180109653  jmp     short loc_180109678
0x180109655  call    cs:__imp_GetLastError
0x18010965b  mov     r8d, eax
0x18010965e  lea     rdx, aFailedToAllocM; "Failed to alloc memory for pBidiInfo or"...
0x180109665  lea     rcx, aUnidrvuiBbidii; "UniDrvUI::BBidiInitInstallOptions"
0x18010966c  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180109671  xor     edi, edi
0x180109673  test    rbx, rbx
0x180109676  jz      short loc_180109681
0x180109678  mov     rcx, rbx; hMem
0x18010967b  call    cs:__imp_LocalFree
0x180109681  mov     rcx, r12; hMem
0x180109684  call    cs:__imp_LocalFree
0x18010968a  jmp     short loc_18010968E
0x18010968c  xor     edi, edi
0x18010968e  xor     ebp, ebp
0x180109690  test    esi, esi
0x180109692  jle     short loc_1801096B6
0x180109694  movsxd  rbx, ebp
0x180109697  shl     rbx, 5
0x18010969b  mov     rcx, [rbx+r14]; pv
0x18010969f  call    cs:__imp_CoTaskMemFree
0x1801096a5  mov     rcx, [rbx+r14+10h]; pv
0x1801096aa  call    cs:__imp_CoTaskMemFree
0x1801096b0  inc     ebp
0x1801096b2  cmp     ebp, esi
0x1801096b4  jl      short loc_180109694
0x1801096b6  test    r14, r14
0x1801096b9  jz      short loc_1801096C4
0x1801096bb  mov     rcx, r14; hMem
0x1801096be  call    cs:__imp_LocalFree
0x1801096c4  mov     rdx, [rsp+78h+var_58+8]; int
0x1801096c9  mov     ecx, esi; this
0x1801096cb  call    ?BidiFreeMapInfo@PSUI@@YAXHPEAPEAU_BIDI_FEATUREOPTION@1@@Z; PSUI::BidiFreeMapInfo(int,PSUI::_BIDI_FEATUREOPTION * *)
0x1801096d0  test    r15d, r15d
0x1801096d3  js      short loc_1801096DB
0x1801096d5  call    cs:__imp_CoUninitialize
0x1801096db  mov     eax, edi
0x1801096dd  add     rsp, 38h
0x1801096e1  pop     r15
0x1801096e3  pop     r14
0x1801096e5  pop     r13
0x1801096e7  pop     r12
0x1801096e9  pop     rdi
0x1801096ea  pop     rsi
0x1801096eb  pop     rbp
0x1801096ec  pop     rbx
0x1801096ed  retn
```
