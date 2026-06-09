# SetupPlatform::GetSetupPlatformVersion(ushort const *,ulong *,ulong *,ulong *)

- ea: `0x180030ed0`
- end: `0x1800311b8`
- name: `?GetSetupPlatformVersion@SetupPlatform@@YAJPEBGPEAK11@Z`
- size: `744`
- prototype: `__int64 __fastcall(SetupPlatform *this, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180031bc4`

## callees

- `0x18000638c`
- `0x18002ec30`
- `0x18002fdfc`
- `0x180030d20`
- `0x180030d30`
- `0x180030ed0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030fc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800310df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003115e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030fc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800310df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003115e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031187`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003116c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031195`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800310ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003116c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031195`
- `WDSCORE!CurrentIP` at `0x180030f49`
- `WDSCORE!CurrentIP` at `0x180031051`
- `WDSCORE!CurrentIP` at `0x180030f49`
- `WDSCORE!CurrentIP` at `0x180031051`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800310cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180030faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800310cb`

## string_xrefs

- `0x180030f28`: `SetupPlatform.dll`
- `0x180030f55`: `SetupPlatform::GetSetupPlatformVersion: Failed to build path to platform binary. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall SetupPlatform::GetSetupPlatformVersion(
        SetupPlatform *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v7; // rax
  signed int v8; // esi
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  const WCHAR *v15; // rax
  signed int LastError; // eax
  bool v17; // sf
  signed int v18; // eax
  DWORD v19; // edi
  __int64 v20; // rbx
  const char *v21; // rax
  struct tagLOG_PARTIAL_MSG *v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  void *v27; // rbx
  HANDLE ProcessHeap; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  void **v31; // [rsp+60h] [rbp-20h] BYREF
  LPVOID FixedFileInfo; // [rsp+68h] [rbp-18h]
  void **v33; // [rsp+70h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-8h]

  if ( !this || !a2 || !a3 )
    return 2147942487LL;
  lpMem = 0;
  v33 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v7 = RAII::CAutoCleanupBase<unsigned short *>::operator&(&v33);
  v8 = BuildPathHr(this, L"SetupPlatform.dll", v7);
  if ( v8 >= 0 )
  {
    v15 = (const WCHAR *)((__int64 (__fastcall *)(void ***))v33[4])(&v33);
    FixedFileInfo = (LPVOID)GetFixedFileInfo(v15);
    v31 = &RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable';
    if ( RAII::CAutoCleanupBase<tagVS_FIXEDFILEINFO *>::operator->(&v31) )
    {
      *(_DWORD *)a2 = *(unsigned __int16 *)(((__int64 (__fastcall *)(void ***))v31[3])(&v31) + 10);
      *a3 = *(unsigned __int16 *)(((__int64 (__fastcall *)(void ***))v31[3])(&v31) + 8);
      v31 = &RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable';
      v27 = FixedFileInfo;
      if ( FixedFileInfo )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v27);
        FixedFileInfo = 0;
      }
      v33 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
      v29 = lpMem;
      if ( lpMem )
      {
        v30 = GetProcessHeap();
        HeapFree(v30, 0, v29);
      }
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError < 0;
      if ( LastError > 0 )
        v17 = 1;
      if ( v17 )
      {
        v18 = GetLastError();
        v8 = v18;
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      v19 = GetLastError();
      v20 = CurrentIP();
      v21 = (const char *)((__int64 (__fastcall *)(void ***))v33[4])(&v33);
      v22 = ConstructPartialMsgW(
              0x2000000,
              "SetupPlatform::GetSetupPlatformVersion: Failed get file info for [%s]. hr = 0x%x",
              v21,
              v8);
      WdsSetupLogMessageW(
        v22,
        0,
        L"D",
        0,
        97,
        L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
        L"SetupPlatform::GetSetupPlatformVersion",
        v20,
        v19,
        0,
        0);
      v31 = &RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable';
      v23 = FixedFileInfo;
      if ( FixedFileInfo )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v23);
        FixedFileInfo = 0;
      }
      v33 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
      v25 = lpMem;
      if ( lpMem )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(
            0x2000000,
            "SetupPlatform::GetSetupPlatformVersion: Failed to build path to platform binary. hr = 0x%x",
            v8);
    WdsSetupLogMessageW(
      v11,
      0,
      L"D",
      0,
      89,
      L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
      L"SetupPlatform::GetSetupPlatformVersion",
      v10,
      v9,
      0,
      0);
    v33 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v12);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030ed0  push    rbp
0x180030ed2  push    rbx
0x180030ed3  push    rsi
0x180030ed4  push    rdi
0x180030ed5  push    r12
0x180030ed7  push    r13
0x180030ed9  push    r14
0x180030edb  mov     rbp, rsp
0x180030ede  sub     rsp, 80h
0x180030ee5  mov     rdi, r8
0x180030ee8  mov     r14, rdx
0x180030eeb  mov     rbx, rcx
0x180030eee  test    rcx, rcx
0x180030ef1  jz      loc_1800311A1
0x180030ef7  test    rdx, rdx
0x180030efa  jz      loc_1800311A1
0x180030f00  test    r8, r8
0x180030f03  jz      loc_1800311A1
0x180030f09  mov     [rbp+lpMem], 0
0x180030f11  lea     r12, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x180030f18  mov     [rbp+var_10], r12
0x180030f1c  lea     rcx, [rbp+var_10]
0x180030f20  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x180030f25  mov     r8, rax
0x180030f28  lea     rdx, aSetupplatformD; "SetupPlatform.dll"
0x180030f2f  mov     rcx, rbx
0x180030f32  call    BuildPathHr
0x180030f37  mov     esi, eax
0x180030f39  test    eax, eax
0x180030f3b  jns     loc_180030FDF
0x180030f41  call    cs:__imp_GetLastError
0x180030f47  mov     edi, eax
0x180030f49  call    cs:__imp_CurrentIP
0x180030f4f  mov     rbx, rax
0x180030f52  mov     r8d, esi
0x180030f55  lea     rdx, aSetupplatformG; "SetupPlatform::GetSetupPlatformVersion:"...
0x180030f5c  mov     ecx, 2000000h; unsigned int
0x180030f61  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180030f66  mov     [rsp+80h+var_30], 0
0x180030f6e  mov     [rsp+80h+var_38], 0
0x180030f77  mov     [rsp+80h+var_40], edi
0x180030f7b  mov     [rsp+80h+var_48], rbx
0x180030f80  lea     rcx, aSetupplatformG_1; "SetupPlatform::GetSetupPlatformVersion"
0x180030f87  mov     [rsp+80h+var_50], rcx
0x180030f8c  lea     rcx, aBaseNtsetupSet_5; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x180030f93  mov     [rsp+80h+var_58], rcx
0x180030f98  mov     [rsp+80h+var_60], 59h ; 'Y'
0x180030fa0  xor     r9d, r9d
0x180030fa3  lea     r8, aD_0; "D"
0x180030faa  xor     edx, edx
0x180030fac  mov     rcx, rax
0x180030faf  call    cs:__imp_WdsSetupLogMessageW
0x180030fb5  nop
0x180030fb6  mov     [rbp+var_10], r12
0x180030fba  mov     rbx, [rbp+lpMem]
0x180030fbe  test    rbx, rbx
0x180030fc1  jz      short loc_180030FD8
0x180030fc3  call    cs:__imp_GetProcessHeap
0x180030fc9  mov     r8, rbx; lpMem
0x180030fcc  xor     edx, edx; dwFlags
0x180030fce  mov     rcx, rax; hHeap
0x180030fd1  call    cs:__imp_HeapFree
0x180030fd7  nop
0x180030fd8  mov     eax, esi
0x180030fda  jmp     loc_1800311A6
0x180030fdf  mov     rax, [rbp+var_10]
0x180030fe3  lea     rcx, [rbp+var_10]
0x180030fe7  mov     rax, [rax+20h]
0x180030feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ff0  mov     rcx, rax; lpwstrFilename
0x180030ff3  call    GetFixedFileInfo
0x180030ff8  mov     [rbp+var_18], rax
0x180030ffc  lea     r13, ??_7?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@6B@; const RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable'
0x180031003  mov     [rbp+var_20], r13
0x180031007  lea     rcx, [rbp+var_20]
0x18003100b  call    ??C?$CAutoCleanupBase@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEBAQEAUtagVS_FIXEDFILEINFO@@XZ; RAII::CAutoCleanupBase<tagVS_FIXEDFILEINFO *>::operator->(void)
0x180031010  test    rax, rax
0x180031013  jnz     loc_180031122
0x180031019  call    cs:__imp_GetLastError
0x18003101f  mov     ebx, 80070000h
0x180031024  test    eax, eax
0x180031026  jle     short loc_18003102F
0x180031028  movzx   eax, ax
0x18003102b  or      eax, ebx
0x18003102d  test    eax, eax
0x18003102f  jns     short loc_180031044
0x180031031  call    cs:__imp_GetLastError
0x180031037  mov     esi, eax
0x180031039  test    eax, eax
0x18003103b  jle     short loc_180031049
0x18003103d  movzx   esi, ax
0x180031040  or      esi, ebx
0x180031042  jmp     short loc_180031049
0x180031044  mov     esi, 80004005h
0x180031049  call    cs:__imp_GetLastError
0x18003104f  mov     edi, eax
0x180031051  call    cs:__imp_CurrentIP
0x180031057  mov     rbx, rax
0x18003105a  mov     rcx, [rbp+var_10]
0x18003105e  mov     rax, [rcx+20h]
0x180031062  lea     rcx, [rbp+var_10]
0x180031066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003106b  mov     r8, rax
0x18003106e  mov     r9d, esi
0x180031071  lea     rdx, aSetupplatformG_0; "SetupPlatform::GetSetupPlatformVersion:"...
0x180031078  mov     ecx, 2000000h; unsigned int
0x18003107d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180031082  mov     [rsp+80h+var_30], 0
0x18003108a  mov     [rsp+80h+var_38], 0
0x180031093  mov     [rsp+80h+var_40], edi
0x180031097  mov     [rsp+80h+var_48], rbx
0x18003109c  lea     rcx, aSetupplatformG_1; "SetupPlatform::GetSetupPlatformVersion"
0x1800310a3  mov     [rsp+80h+var_50], rcx
0x1800310a8  lea     rcx, aBaseNtsetupSet_5; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1800310af  mov     [rsp+80h+var_58], rcx
0x1800310b4  mov     [rsp+80h+var_60], 61h ; 'a'
0x1800310bc  xor     r9d, r9d
0x1800310bf  lea     r8, aD_0; "D"
0x1800310c6  xor     edx, edx
0x1800310c8  mov     rcx, rax
0x1800310cb  call    cs:__imp_WdsSetupLogMessageW
0x1800310d1  nop
0x1800310d2  mov     [rbp+var_20], r13
0x1800310d6  mov     rbx, [rbp+var_18]
0x1800310da  test    rbx, rbx
0x1800310dd  jz      short loc_1800310FB
0x1800310df  call    cs:__imp_GetProcessHeap
0x1800310e5  mov     r8, rbx; lpMem
0x1800310e8  xor     edx, edx; dwFlags
0x1800310ea  mov     rcx, rax; hHeap
0x1800310ed  call    cs:__imp_HeapFree
0x1800310f3  mov     [rbp+var_18], 0
0x1800310fb  mov     [rbp+var_10], r12
0x1800310ff  mov     rbx, [rbp+lpMem]
0x180031103  test    rbx, rbx
0x180031106  jz      short loc_18003111D
0x180031108  call    cs:__imp_GetProcessHeap
0x18003110e  mov     r8, rbx; lpMem
0x180031111  xor     edx, edx; dwFlags
0x180031113  mov     rcx, rax; hHeap
0x180031116  call    cs:__imp_HeapFree
0x18003111c  nop
0x18003111d  jmp     loc_180030FD8
0x180031122  mov     rax, [rbp+var_20]
0x180031126  lea     rcx, [rbp+var_20]
0x18003112a  mov     rax, [rax+18h]
0x18003112e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031133  movzx   ecx, word ptr [rax+0Ah]
0x180031137  mov     [r14], ecx
0x18003113a  mov     rax, [rbp+var_20]
0x18003113e  lea     rcx, [rbp+var_20]
0x180031142  mov     rax, [rax+18h]
0x180031146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003114b  movzx   ecx, word ptr [rax+8]
0x18003114f  mov     [rdi], ecx
0x180031151  mov     [rbp+var_20], r13
0x180031155  mov     rbx, [rbp+var_18]
0x180031159  test    rbx, rbx
0x18003115c  jz      short loc_18003117A
0x18003115e  call    cs:__imp_GetProcessHeap
0x180031164  mov     r8, rbx; lpMem
0x180031167  xor     edx, edx; dwFlags
0x180031169  mov     rcx, rax; hHeap
0x18003116c  call    cs:__imp_HeapFree
0x180031172  mov     [rbp+var_18], 0
0x18003117a  mov     [rbp+var_10], r12
0x18003117e  mov     rbx, [rbp+lpMem]
0x180031182  test    rbx, rbx
0x180031185  jz      short loc_18003119C
0x180031187  call    cs:__imp_GetProcessHeap
0x18003118d  mov     r8, rbx; lpMem
0x180031190  xor     edx, edx; dwFlags
0x180031192  mov     rcx, rax; hHeap
0x180031195  call    cs:__imp_HeapFree
0x18003119b  nop
0x18003119c  jmp     loc_180030FD8
0x1800311a1  mov     eax, 80070057h
0x1800311a6  add     rsp, 80h
0x1800311ad  pop     r14
0x1800311af  pop     r13
0x1800311b1  pop     r12
0x1800311b3  pop     rdi
0x1800311b4  pop     rsi
0x1800311b5  pop     rbx
0x1800311b6  pop     rbp
0x1800311b7  retn
```
