# CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)

- ea: `0x180040f00`
- end: `0x1800411d4`
- name: `?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `724`
- prototype: `int(CbsOfflineUtil *__hidden this, const wchar_t *, struct ICbsSession **)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180040de0`
- `0x180041bc0`
- `0x180041c90`
- `0x180041d70`

## callees

- `0x180020dc0`
- `0x180023664`
- `0x18002d2b0`
- `0x180040f00`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040fee`
- `KERNEL32!GetLastError` at `0x180041038`
- `KERNEL32!GetLastError` at `0x180040fee`
- `KERNEL32!GetLastError` at `0x180041038`
- `KERNEL32!GetModuleHandleExW` at `0x180040f5b`
- `KERNEL32!GetModuleHandleExW` at `0x180040f81`
- `KERNEL32!GetModuleHandleExW` at `0x180040f9f`
- `KERNEL32!GetModuleHandleExW` at `0x180040f5b`
- `KERNEL32!GetModuleHandleExW` at `0x180040f81`
- `KERNEL32!GetModuleHandleExW` at `0x180040f9f`
- `KERNEL32!LoadLibraryExW` at `0x180040fcf`
- `KERNEL32!LoadLibraryExW` at `0x180040fcf`
- `KERNEL32!GetProcAddress` at `0x180041023`
- `KERNEL32!GetProcAddress` at `0x180041066`
- `KERNEL32!GetProcAddress` at `0x18004108e`
- `KERNEL32!GetProcAddress` at `0x180041023`
- `KERNEL32!GetProcAddress` at `0x180041066`
- `KERNEL32!GetProcAddress` at `0x18004108e`
- `ntdll!RtlRaiseStatus` at `0x1800410df`
- `ntdll!RtlRaiseStatus` at `0x1800410df`
- `OLE32!CoGetMalloc` at `0x1800410bf`
- `OLE32!CoGetMalloc` at `0x1800410bf`

## string_xrefs

- `0x180040f54`: `Cbscore.dll`
- `0x180040f73`: `cbs_unittests_offline.dll`
- `0x180040f98`: `servicing_unittests_offline.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  HMODULE *v3; // rsi
  int Malloc; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v11; // eax
  FARPROC v12; // rax
  FARPROC v13; // rax
  _QWORD *v14; // r14
  struct ICbsSession *v16; // [rsp+50h] [rbp-30h] BYREF
  LPMALLOC ppMalloc; // [rsp+58h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-20h] BYREF
  HMODULE v19; // [rsp+68h] [rbp-18h] BYREF
  HMODULE v20; // [rsp+70h] [rbp-10h] BYREF

  v3 = (HMODULE *)((char *)this + 8);
  ppMalloc = 0;
  v16 = 0;
  if ( *((_QWORD *)this + 1) )
    goto LABEL_20;
  phModule = 0;
  if ( GetModuleHandleExW(2u, L"Cbscore.dll", &phModule) )
  {
    v19 = 0;
    v20 = 0;
    if ( !GetModuleHandleExW(2u, L"cbs_unittests_offline.dll", &v19)
      && !GetModuleHandleExW(2u, L"servicing_unittests_offline.dll", &v20)
      && phModule != &_ImageBase )
    {
      Malloc = -2147024846;
      goto LABEL_27;
    }
  }
  Library = LoadLibraryExW(a2, 0, 8u);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(v3, Library);
  if ( !*v3 )
  {
    LastError = GetLastError();
    Malloc = LastError;
    if ( LastError > 0 )
      Malloc = (unsigned __int16)LastError | 0x80070000;
    if ( Malloc == -2147024770 )
      Malloc = -2147467263;
    goto LABEL_27;
  }
  ProcAddress = GetProcAddress(*v3, "CbsCoreInitialize");
  *((_QWORD *)this + 12) = ProcAddress;
  if ( ProcAddress )
  {
    v12 = GetProcAddress(*v3, "CbsCoreFinalize");
    *((_QWORD *)this + 13) = v12;
    if ( v12 )
    {
      if ( !g_TestMode )
      {
LABEL_20:
        v14 = (_QWORD *)((char *)this + 112);
        if ( *((_QWORD *)this + 14) )
          goto LABEL_25;
        Malloc = CoGetMalloc(1u, &ppMalloc);
        if ( Malloc >= 0 )
        {
          if ( *v14 )
            RtlRaiseStatus(-1073741595);
          Malloc = (*((__int64 (__fastcall **)(LPMALLOC, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), char *))this
                    + 12))(
                     ppMalloc,
                     &CCbsLogMonitorProvider::Init,
                     RtlFinalizeSmartLBlobUcsWritingContext,
                     CbsUtilInstanceCreated,
                     CbsUtilInstanceDestroyed,
                     RtlFinalizeSmartLBlobUcsWritingContext,
                     RtlFinalizeSmartLBlobUcsWritingContext,
                     (char *)this + 112);
          if ( Malloc >= 0 )
          {
LABEL_25:
            Malloc = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct ICbsSession **))(*(_QWORD *)*v14 + 24LL))(
                       *v14,
                       0,
                       &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
                       &v16);
            if ( Malloc >= 0 )
            {
              *a3 = v16;
              v16 = 0;
            }
          }
        }
        goto LABEL_27;
      }
      v13 = GetProcAddress(*v3, "SetTestMode");
      if ( v13 )
      {
        ((void (__fastcall *)(__int64))v13)(1);
        goto LABEL_20;
      }
    }
  }
  v11 = GetLastError();
  Malloc = v11;
  if ( v11 > 0 )
    Malloc = (unsigned __int16)v11 | 0x80070000;
LABEL_27:
  if ( v16 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( Malloc < 0 && *v3 && !*((_QWORD *)this + 14) )
  {
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(v3);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
  }
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x180040f00  push    rbp
0x180040f02  push    rbx
0x180040f03  push    rsi
0x180040f04  push    rdi
0x180040f05  push    r12
0x180040f07  push    r14
0x180040f09  push    r15
0x180040f0b  mov     rbp, rsp
0x180040f0e  sub     rsp, 80h
0x180040f15  mov     rax, cs:__security_cookie
0x180040f1c  xor     rax, rsp
0x180040f1f  mov     [rbp+var_8], rax
0x180040f23  xor     r12d, r12d
0x180040f26  lea     rsi, [rcx+8]
0x180040f2a  mov     r15, r8
0x180040f2d  mov     rbx, rdx
0x180040f30  mov     rdi, rcx
0x180040f33  mov     [rbp+ppMalloc], r12
0x180040f37  mov     [rbp+var_30], r12
0x180040f3b  cmp     [rsi], r12
0x180040f3e  jnz     loc_1800410A9
0x180040f44  lea     r14d, [r12+2]
0x180040f49  mov     [rbp+phModule], r12
0x180040f4d  mov     ecx, r14d; dwFlags
0x180040f50  lea     r8, [rbp+phModule]; phModule
0x180040f54  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x180040f5b  call    cs:__imp_GetModuleHandleExW
0x180040f62  nop     dword ptr [rax+rax+00h]
0x180040f67  test    eax, eax
0x180040f69  jz      short loc_180040FC6
0x180040f6b  lea     r8, [rbp+var_18]; phModule
0x180040f6f  mov     [rbp+var_18], r12
0x180040f73  lea     rdx, aCbsUnittestsOf; "cbs_unittests_offline.dll"
0x180040f7a  mov     [rbp+var_10], r12
0x180040f7e  mov     ecx, r14d; dwFlags
0x180040f81  call    cs:__imp_GetModuleHandleExW
0x180040f88  nop     dword ptr [rax+rax+00h]
0x180040f8d  test    eax, eax
0x180040f8f  jnz     short loc_180040FC6
0x180040f91  lea     r8, [rbp+var_10]; phModule
0x180040f95  mov     ecx, r14d; dwFlags
0x180040f98  lea     rdx, aServicingUnitt; "servicing_unittests_offline.dll"
0x180040f9f  call    cs:__imp_GetModuleHandleExW
0x180040fa6  nop     dword ptr [rax+rax+00h]
0x180040fab  test    eax, eax
0x180040fad  jnz     short loc_180040FC6
0x180040faf  lea     rax, __ImageBase
0x180040fb6  cmp     [rbp+phModule], rax
0x180040fba  jz      short loc_180040FC6
0x180040fbc  mov     ebx, 80070032h
0x180040fc1  jmp     loc_18004116A
0x180040fc6  xor     edx, edx; hFile
0x180040fc8  mov     rcx, rbx; lpLibFileName
0x180040fcb  lea     r8d, [rdx+8]; dwFlags
0x180040fcf  call    cs:__imp_LoadLibraryExW
0x180040fd6  nop     dword ptr [rax+rax+00h]
0x180040fdb  mov     rdx, rax
0x180040fde  mov     rcx, rsi
0x180040fe1  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180040fe6  mov     rcx, [rsi]; hModule
0x180040fe9  test    rcx, rcx
0x180040fec  jnz     short loc_18004101C
0x180040fee  call    cs:__imp_GetLastError
0x180040ff5  nop     dword ptr [rax+rax+00h]
0x180040ffa  mov     ebx, eax
0x180040ffc  test    eax, eax
0x180040ffe  jle     short loc_180041009
0x180041000  movzx   ebx, ax
0x180041003  or      ebx, 80070000h
0x180041009  cmp     ebx, 8007007Eh
0x18004100f  mov     eax, 80004001h
0x180041014  cmovz   ebx, eax
0x180041017  jmp     loc_18004116A
0x18004101c  lea     rdx, aCbscoreinitial; "CbsCoreInitialize"
0x180041023  call    cs:__imp_GetProcAddress
0x18004102a  nop     dword ptr [rax+rax+00h]
0x18004102f  mov     [rdi+60h], rax
0x180041033  test    rax, rax
0x180041036  jnz     short loc_18004105C
0x180041038  call    cs:__imp_GetLastError
0x18004103f  nop     dword ptr [rax+rax+00h]
0x180041044  mov     ebx, eax
0x180041046  test    eax, eax
0x180041048  jle     loc_18004116A
0x18004104e  movzx   ebx, ax
0x180041051  or      ebx, 80070000h
0x180041057  jmp     loc_18004116A
0x18004105c  mov     rcx, [rsi]; hModule
0x18004105f  lea     rdx, aCbscorefinaliz; "CbsCoreFinalize"
0x180041066  call    cs:__imp_GetProcAddress
0x18004106d  nop     dword ptr [rax+rax+00h]
0x180041072  mov     [rdi+68h], rax
0x180041076  test    rax, rax
0x180041079  jz      short loc_180041038
0x18004107b  cmp     cs:?g_TestMode@@3_NA, r12b; bool g_TestMode
0x180041082  jz      short loc_1800410A9
0x180041084  mov     rcx, [rsi]; hModule
0x180041087  lea     rdx, aSettestmode; "SetTestMode"
0x18004108e  call    cs:__imp_GetProcAddress
0x180041095  nop     dword ptr [rax+rax+00h]
0x18004109a  test    rax, rax
0x18004109d  jz      short loc_180041038
0x18004109f  mov     ecx, 1
0x1800410a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410a9  lea     r14, [rdi+70h]
0x1800410ad  cmp     [r14], r12
0x1800410b0  jnz     loc_18004113D
0x1800410b6  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x1800410ba  mov     ecx, 1; dwMemContext
0x1800410bf  call    cs:__imp_CoGetMalloc
0x1800410c6  nop     dword ptr [rax+rax+00h]
0x1800410cb  mov     ebx, eax
0x1800410cd  test    eax, eax
0x1800410cf  js      loc_18004116A
0x1800410d5  cmp     [r14], r12
0x1800410d8  jz      short loc_1800410EC
0x1800410da  mov     ecx, 0C00000E5h; Status
0x1800410df  call    cs:__imp_RtlRaiseStatus
0x1800410e6  nop     dword ptr [rax+rax+00h]
0x1800410eb  int     3; Trap to Debugger
0x1800410ec  mov     rcx, [rbp+ppMalloc]
0x1800410f0  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x1800410f7  mov     [rsp+80h+var_48], r14
0x1800410fc  lea     r9, CbsUtilInstanceCreated
0x180041103  mov     [rsp+80h+var_50], rax
0x180041108  lea     r8, RtlFinalizeSmartLBlobUcsWritingContext
0x18004110f  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x180041116  mov     [rsp+80h+var_58], rax
0x18004111b  lea     rdx, ?Init@CCbsLogMonitorProvider@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CCbsLogMonitorProvider::Init(void *,ILogContext *)
0x180041122  lea     rax, CbsUtilInstanceDestroyed
0x180041129  mov     [rsp+80h+var_60], rax
0x18004112e  mov     rax, [rdi+60h]
0x180041132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041137  mov     ebx, eax
0x180041139  test    eax, eax
0x18004113b  js      short loc_18004116A
0x18004113d  mov     rcx, [r14]
0x180041140  lea     r9, [rbp+var_30]
0x180041144  lea     r8, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed
0x18004114b  xor     edx, edx
0x18004114d  mov     rax, [rcx]
0x180041150  mov     rax, [rax+18h]
0x180041154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041159  mov     ebx, eax
0x18004115b  test    eax, eax
0x18004115d  js      short loc_18004116A
0x18004115f  mov     rax, [rbp+var_30]
0x180041163  mov     [r15], rax
0x180041166  mov     [rbp+var_30], r12
0x18004116a  mov     rcx, [rbp+var_30]
0x18004116e  test    rcx, rcx
0x180041171  jz      short loc_18004117F
0x180041173  mov     rax, [rcx]
0x180041176  mov     rax, [rax+10h]
0x18004117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004117f  mov     rcx, [rbp+ppMalloc]
0x180041183  test    rcx, rcx
0x180041186  jz      short loc_180041194
0x180041188  mov     rax, [rcx]
0x18004118b  mov     rax, [rax+10h]
0x18004118f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041194  test    ebx, ebx
0x180041196  jns     short loc_1800411B3
0x180041198  cmp     [rsi], r12
0x18004119b  jz      short loc_1800411B3
0x18004119d  cmp     [rdi+70h], r12
0x1800411a1  jnz     short loc_1800411B3
0x1800411a3  mov     rcx, rsi
0x1800411a6  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800411ab  mov     [rdi+60h], r12
0x1800411af  mov     [rdi+68h], r12
0x1800411b3  mov     eax, ebx
0x1800411b5  mov     rcx, [rbp+var_8]
0x1800411b9  xor     rcx, rsp; StackCookie
0x1800411bc  call    __security_check_cookie
0x1800411c1  add     rsp, 80h
0x1800411c8  pop     r15
0x1800411ca  pop     r14
0x1800411cc  pop     r12
0x1800411ce  pop     rdi
0x1800411cf  pop     rsi
0x1800411d0  pop     rbx
0x1800411d1  pop     rbp
0x1800411d2  retn
```
