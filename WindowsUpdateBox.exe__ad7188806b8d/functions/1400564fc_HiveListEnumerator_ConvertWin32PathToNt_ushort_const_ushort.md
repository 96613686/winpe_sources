# HiveListEnumerator::ConvertWin32PathToNt(ushort const *,ushort * *)

- ea: `0x1400564fc`
- end: `0x140056990`
- name: `?ConvertWin32PathToNt@HiveListEnumerator@@SA_NPEBGPEAPEAG@Z`
- size: `1172`
- prototype: `char __fastcall(WCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140059484`

## callees

- `0x140002116`
- `0x140028144`
- `0x140055c20`
- `0x140055d10`
- `0x1400564fc`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14005694b`
- `KERNEL32!HeapFree` at `0x14005694b`
- `KERNEL32!GetProcessHeap` at `0x140056937`
- `KERNEL32!GetProcessHeap` at `0x140056937`
- `KERNEL32!QueryDosDeviceW` at `0x14005657a`
- `KERNEL32!QueryDosDeviceW` at `0x14005657a`
- `KERNEL32!GetLastError` at `0x140056591`
- `KERNEL32!GetLastError` at `0x14005659f`
- `KERNEL32!GetLastError` at `0x140056881`
- `KERNEL32!GetLastError` at `0x14005688f`
- `KERNEL32!GetLastError` at `0x140056591`
- `KERNEL32!GetLastError` at `0x14005659f`
- `KERNEL32!GetLastError` at `0x140056881`
- `KERNEL32!GetLastError` at `0x14005688f`
- `KERNEL32!SetLastError` at `0x140056624`
- `KERNEL32!SetLastError` at `0x140056918`
- `KERNEL32!SetLastError` at `0x140056624`
- `KERNEL32!SetLastError` at `0x140056918`
- `ntdll!RtlFreeHeap` at `0x140056822`
- `ntdll!RtlFreeHeap` at `0x140056822`
- `ntdll!RtlAllocateHeap` at `0x1400566d4`
- `ntdll!RtlAllocateHeap` at `0x1400566d4`
- `WDSCORE!WdsSetupLogMessageW` at `0x140056616`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005690a`
- `WDSCORE!WdsSetupLogMessageW` at `0x140056616`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005690a`
- `WDSCORE!CurrentIP` at `0x1400565ad`
- `WDSCORE!CurrentIP` at `0x14005689d`
- `WDSCORE!CurrentIP` at `0x1400565ad`
- `WDSCORE!CurrentIP` at `0x14005689d`

## string_xrefs

- `0x1400565e7`: `HiveListEnumerator::ConvertWin32PathToNt`
- `0x1400568db`: `HiveListEnumerator::ConvertWin32PathToNt`
- `0x1400568b7`: `BuildPath failed for %s and %s. GLE: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall HiveListEnumerator::ConvertWin32PathToNt(WCHAR *a1, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // rbx
  DWORD LastError; // esi
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  bool v9; // zf
  const char *v10; // r15
  const char *v11; // r12
  int v12; // r14d
  __int64 v13; // rdi
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  size_t v17; // r13
  wchar_t *Heap; // rsi
  HRESULT v19; // eax
  unsigned __int16 v20; // bx
  HRESULT v21; // eax
  size_t v22; // rcx
  STRSAFE_LPWSTR v23; // rdx
  size_t v24; // r8
  signed __int64 v25; // r12
  wchar_t v26; // ax
  STRSAFE_LPWSTR v27; // rax
  signed int v28; // eax
  DWORD v29; // esi
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  void *v33; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v35; // [rsp+38h] [rbp-D0h]
  DWORD v36; // [rsp+38h] [rbp-D0h]
  STRSAFE_LPWSTR pszDest; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 **v38; // [rsp+70h] [rbp-98h] BYREF
  size_t cchDest; // [rsp+78h] [rbp-90h] BYREF
  void **v40; // [rsp+80h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-80h]
  __int64 v42; // [rsp+90h] [rbp-78h]
  WCHAR DeviceName[8]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR TargetPath[264]; // [rsp+A8h] [rbp-60h] BYREF

  v42 = -2;
  v2 = a2;
  v38 = a2;
  wcscpy(DeviceName, L"?:");
  DeviceName[0] = *a1;
  memset_0(TargetPath, 0, 0x208u);
  if ( !QueryDosDeviceW(DeviceName, TargetPath, 0x104u) )
  {
    LastError = GetLastError();
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(50331648, "QueryDosDevice failed for %s. GLE: %u", (const char *)DeviceName, LastError);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      324,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"HiveListEnumerator::ConvertWin32PathToNt",
      v6,
      v5,
      0,
      0);
    SetLastError(LastError);
    return 0;
  }
  TargetPath[259] = 0;
  v9 = a1 + 2 == 0;
  v10 = (const char *)(a1 + 2);
  v11 = v10;
  pszDest = 0;
  cchDest = 0;
  v12 = 0;
  if ( v9 )
  {
    NtCurrentTeb()->LastErrorValue = 87;
    goto LABEL_40;
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( TargetPath[v14] );
  do
    ++v13;
  while ( *(_WORD *)&v10[2 * v13] );
  if ( (_DWORD)v14 )
  {
    if ( TargetPath[(unsigned int)(v14 - 1)] == 92 )
    {
      v11 = v10 + 2;
      if ( *(_WORD *)v10 != 92 )
        v11 = v10;
      v15 = v13 - 1;
      if ( *(_WORD *)v10 != 92 )
        v15 = v13;
      LODWORD(v13) = v15;
    }
    else if ( *(_WORD *)v10 != 92 )
    {
      v12 = 1;
    }
  }
  v16 = (unsigned int)(v14 + v12 + v13 + 1);
  v17 = (unsigned int)v16;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v16);
  if ( Heap )
  {
    v19 = StringCchCopyNExW(Heap, v17, TargetPath, (unsigned int)v14, &pszDest, &cchDest, v35);
    v20 = v19;
    if ( v19 < 0 )
      goto LABEL_38;
    if ( v12 )
    {
      v21 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v36);
      v20 = v21;
      if ( v21 < 0 )
        goto LABEL_38;
    }
    v22 = cchDest;
    if ( cchDest - 1 > 0x7FFFFFFE )
    {
      v20 = 87;
      v28 = -2147024809;
      if ( cchDest )
        goto LABEL_37;
    }
    else
    {
      if ( (unsigned int)v13 > 0x7FFFFFFE )
      {
        v20 = 87;
LABEL_37:
        *pszDest = 0;
LABEL_38:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        NtCurrentTeb()->LastErrorValue = v20;
        goto LABEL_19;
      }
      v23 = pszDest;
      if ( cchDest )
      {
        v24 = (unsigned int)v13 - cchDest;
        v25 = v11 - (const char *)pszDest;
        do
        {
          if ( !(v24 + v22) )
            break;
          v26 = *(STRSAFE_LPWSTR)((char *)v23 + v25);
          if ( !v26 )
            break;
          *v23++ = v26;
          --v22;
        }
        while ( v22 );
      }
      v27 = v23 - 1;
      if ( v22 )
        v27 = v23;
      *v27 = 0;
      v28 = v22 == 0 ? 0x8007007A : 0;
    }
    v20 = v28;
    if ( v28 >= 0 )
    {
      NtCurrentTeb()->LastErrorValue = 0;
      v2 = v38;
      goto LABEL_41;
    }
    goto LABEL_38;
  }
  NtCurrentTeb()->LastErrorValue = 8;
LABEL_19:
  v2 = v38;
LABEL_40:
  Heap = 0;
LABEL_41:
  lpMem = Heap;
  v40 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v38 = 0;
  if ( (unsigned __int8)RAII::CAutoCleanupBase<_EVENT_TRACE_PROPERTIES * *>::operator==(&v40, &v38) )
  {
    v29 = GetLastError();
    v30 = GetLastError();
    v31 = CurrentIP();
    v32 = ConstructPartialMsgW(50331648, "BuildPath failed for %s and %s. GLE: %u", (const char *)TargetPath, v10, v29);
    WdsSetupLogMessageW(
      v32,
      0,
      L"D",
      0,
      335,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"HiveListEnumerator::ConvertWin32PathToNt",
      v31,
      v30,
      0,
      0);
    SetLastError(v29);
    v40 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    v33 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v33);
    }
    return 0;
  }
  *v2 = (unsigned __int16 *)lpMem;
  return 1;
}

```

## disassembly

```asm
0x1400564fc  mov     rax, rsp
0x1400564ff  push    rbp
0x140056500  push    rsi
0x140056501  push    rdi
0x140056502  push    r12
0x140056504  push    r13
0x140056506  push    r14
0x140056508  push    r15
0x14005650a  lea     rbp, [rax-1F8h]
0x140056511  sub     rsp, 2C0h
0x140056518  mov     [rbp+1F0h+var_268], 0FFFFFFFFFFFFFFFEh
0x140056520  mov     [rax+18h], rbx
0x140056524  mov     rax, cs:__security_cookie
0x14005652b  xor     rax, rsp
0x14005652e  mov     [rbp+1F0h+var_40], rax
0x140056535  mov     rbx, rdx
0x140056538  mov     [rsp+2F0h+var_288], rdx
0x14005653d  mov     r15, rcx
0x140056540  mov     eax, dword ptr cs:asc_140091B74; "?:"
0x140056546  mov     dword ptr [rbp+1F0h+DeviceName], eax
0x140056549  movzx   eax, word ptr cs:asc_140091B74+4; ""
0x140056550  mov     [rbp+1F0h+var_25C], ax
0x140056554  movzx   eax, word ptr [rcx]
0x140056557  mov     [rbp+1F0h+DeviceName], ax
0x14005655b  xor     edx, edx; Val
0x14005655d  mov     r8d, 208h; Size
0x140056563  lea     rcx, [rbp+1F0h+TargetPath]; void *
0x140056567  call    memset_0
0x14005656c  mov     r8d, 104h; ucchMax
0x140056572  lea     rdx, [rbp+1F0h+TargetPath]; lpTargetPath
0x140056576  lea     rcx, [rbp+1F0h+DeviceName]; lpDeviceName
0x14005657a  call    cs:__imp_QueryDosDeviceW
0x140056581  nop     dword ptr [rax+rax+00h]
0x140056586  xor     r13d, r13d
0x140056589  test    eax, eax
0x14005658b  jnz     loc_140056637
0x140056591  call    cs:__imp_GetLastError
0x140056598  nop     dword ptr [rax+rax+00h]
0x14005659d  mov     esi, eax
0x14005659f  call    cs:__imp_GetLastError
0x1400565a6  nop     dword ptr [rax+rax+00h]
0x1400565ab  mov     edi, eax
0x1400565ad  call    cs:__imp_CurrentIP
0x1400565b4  nop     dword ptr [rax+rax+00h]
0x1400565b9  mov     rbx, rax
0x1400565bc  mov     r9d, esi
0x1400565bf  lea     r8, [rbp+1F0h+DeviceName]
0x1400565c3  lea     rdx, aQuerydosdevice; "QueryDosDevice failed for %s. GLE: %u"
0x1400565ca  mov     ecx, 3000000h; unsigned int
0x1400565cf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400565d4  mov     [rsp+50h], r13d
0x1400565d9  mov     qword ptr [rsp+2F0h+var_2A8], r13
0x1400565de  mov     dword ptr [rsp+2F0h+var_2B0], edi
0x1400565e2  mov     qword ptr [rsp+2F0h+var_2B8], rbx
0x1400565e7  lea     rcx, aHivelistenumer; "HiveListEnumerator::ConvertWin32PathToN"...
0x1400565ee  mov     [rsp+2F0h+var_2C0], rcx
0x1400565f3  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1400565fa  mov     [rsp+2F0h+pcchRemaining], rcx
0x1400565ff  mov     dword ptr [rsp+2F0h+ppszDestEnd], 144h
0x140056607  xor     r9d, r9d
0x14005660a  lea     r8, aD; "D"
0x140056611  xor     edx, edx
0x140056613  mov     rcx, rax
0x140056616  call    cs:__imp_WdsSetupLogMessageW
0x14005661d  nop     dword ptr [rax+rax+00h]
0x140056622  mov     ecx, esi; dwErrCode
0x140056624  call    cs:__imp_SetLastError
0x14005662b  nop     dword ptr [rax+rax+00h]
0x140056630  xor     al, al
0x140056632  jmp     loc_140056965
0x140056637  mov     [rbp+1F0h+var_4A], r13w
0x14005663f  add     r15, 4
0x140056643  mov     r12, r15
0x140056646  mov     [rsp+2F0h+pszDest], r13
0x14005664b  mov     [rsp+2F0h+cchDest], r13
0x140056650  mov     r14d, r13d
0x140056653  mov     r8d, 1
0x140056659  jz      loc_140056842
0x14005665f  lea     rax, [rbp+1F0h+TargetPath]
0x140056663  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140056667  mov     rbx, rdi
0x14005666a  inc     rbx
0x14005666d  cmp     [rax+rbx*2], r13w
0x140056672  jnz     short loc_14005666A
0x140056674  inc     rdi
0x140056677  cmp     [r15+rdi*2], r13w
0x14005667c  jnz     short loc_140056674
0x14005667e  test    ebx, ebx
0x140056680  jz      short loc_1400566AF
0x140056682  lea     eax, [rbx-1]
0x140056685  mov     edx, 5Ch ; '\'
0x14005668a  cmp     dx, [rbp+rax*2+1F0h+TargetPath]
0x14005668f  jnz     short loc_1400566A7
0x140056691  lea     r12, [r15+2]
0x140056695  cmp     dx, [r15]
0x140056699  cmovnz  r12, r15
0x14005669d  lea     eax, [rdi-1]
0x1400566a0  cmovnz  eax, edi
0x1400566a3  mov     edi, eax
0x1400566a5  jmp     short loc_1400566AF
0x1400566a7  cmp     dx, [r15]
0x1400566ab  cmovnz  r14d, r8d
0x1400566af  lea     ecx, [rdi+1]
0x1400566b2  add     ecx, r14d
0x1400566b5  add     ecx, ebx
0x1400566b7  mov     r13d, ecx
0x1400566ba  lea     r8, ds:0[rcx*2]; Size
0x1400566c2  mov     rcx, gs:60h
0x1400566cb  mov     edx, 8; Flags
0x1400566d0  mov     rcx, [rcx+30h]; HeapHandle
0x1400566d4  call    cs:__imp_RtlAllocateHeap
0x1400566db  nop     dword ptr [rax+rax+00h]
0x1400566e0  mov     rsi, rax
0x1400566e3  test    rax, rax
0x1400566e6  jnz     short loc_140056705
0x1400566e8  mov     rax, gs:30h
0x1400566f1  mov     dword ptr [rax+68h], 8
0x1400566f8  xor     r13d, r13d
0x1400566fb  mov     rbx, [rsp+2F0h+var_288]
0x140056700  jmp     loc_140056852
0x140056705  mov     r9d, ebx; cchToCopy
0x140056708  lea     rax, [rsp+2F0h+cchDest]
0x14005670d  mov     [rsp+2F0h+pcchRemaining], rax; pcchRemaining
0x140056712  lea     rax, [rsp+2F0h+pszDest]
0x140056717  mov     [rsp+2F0h+ppszDestEnd], rax; ppszDestEnd
0x14005671c  lea     r8, [rbp+1F0h+TargetPath]; pszSrc
0x140056720  mov     rdx, r13; cchDest
0x140056723  mov     rcx, rsi; pszDest
0x140056726  call    StringCchCopyNExW
0x14005672b  mov     ebx, eax
0x14005672d  xor     r13d, r13d
0x140056730  test    eax, eax
0x140056732  js      loc_140056810
0x140056738  test    r14d, r14d
0x14005673b  jz      short loc_140056775
0x14005673d  lea     rax, [rsp+2F0h+cchDest]
0x140056742  mov     [rsp+2F0h+pcchRemaining], rax; pcchRemaining
0x140056747  lea     rax, [rsp+2F0h+pszDest]
0x14005674c  mov     [rsp+2F0h+ppszDestEnd], rax; ppszDestEnd
0x140056751  lea     r9d, [r13+1]; cchToCopy
0x140056755  lea     r8, pszSrc; "\\"
0x14005675c  mov     rdx, [rsp+2F0h+cchDest]; cchDest
0x140056761  mov     rcx, [rsp+2F0h+pszDest]; pszDest
0x140056766  call    StringCchCopyNExW
0x14005676b  mov     ebx, eax
0x14005676d  test    eax, eax
0x14005676f  js      loc_140056810
0x140056775  mov     rcx, [rsp+2F0h+cchDest]
0x14005677a  lea     rax, [rcx-1]
0x14005677e  mov     edx, 7FFFFFFEh
0x140056783  cmp     rax, rdx
0x140056786  ja      short loc_1400567FB
0x140056788  cmp     edi, edx
0x14005678a  jbe     short loc_140056793
0x14005678c  mov     ebx, 80070057h
0x140056791  jmp     short loc_140056807
0x140056793  mov     rdx, [rsp+2F0h+pszDest]
0x140056798  test    rcx, rcx
0x14005679b  jz      short loc_1400567C6
0x14005679d  mov     r8d, edi
0x1400567a0  sub     r8, rcx
0x1400567a3  sub     r12, rdx
0x1400567a6  lea     rax, [r8+rcx]
0x1400567aa  test    rax, rax
0x1400567ad  jz      short loc_1400567C6
0x1400567af  movzx   eax, word ptr [rdx+r12]
0x1400567b4  test    ax, ax
0x1400567b7  jz      short loc_1400567C6
0x1400567b9  mov     [rdx], ax
0x1400567bc  add     rdx, 2
0x1400567c0  sub     rcx, 1
0x1400567c4  jnz     short loc_1400567A6
0x1400567c6  lea     rax, [rdx-2]
0x1400567ca  test    rcx, rcx
0x1400567cd  cmovnz  rax, rdx
0x1400567d1  mov     [rax], r13w
0x1400567d5  neg     rcx
0x1400567d8  sbb     eax, eax
0x1400567da  not     eax
0x1400567dc  and     eax, 8007007Ah
0x1400567e1  mov     ebx, eax
0x1400567e3  test    eax, eax
0x1400567e5  js      short loc_140056810
0x1400567e7  mov     rax, gs:30h
0x1400567f0  mov     [rax+68h], r13d
0x1400567f4  mov     rbx, [rsp+2F0h+var_288]
0x1400567f9  jmp     short loc_140056855
0x1400567fb  mov     ebx, 80070057h
0x140056800  mov     eax, ebx
0x140056802  test    rcx, rcx
0x140056805  jz      short loc_1400567E1
0x140056807  mov     rax, [rsp+2F0h+pszDest]
0x14005680c  mov     [rax], r13w
0x140056810  mov     rcx, gs:60h
0x140056819  mov     r8, rsi; P
0x14005681c  xor     edx, edx; Flags
0x14005681e  mov     rcx, [rcx+30h]; HeapHandle
0x140056822  call    cs:__imp_RtlFreeHeap
0x140056829  nop     dword ptr [rax+rax+00h]
0x14005682e  movzx   ecx, bx
0x140056831  mov     rax, gs:30h
0x14005683a  mov     [rax+68h], ecx
0x14005683d  jmp     loc_1400566FB
0x140056842  mov     rax, gs:30h
0x14005684b  mov     dword ptr [rax+68h], 57h ; 'W'
0x140056852  mov     rsi, r13
0x140056855  mov     [rbp+1F0h+lpMem], rsi
0x140056859  lea     r14, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x140056860  mov     [rsp+2F0h+var_278], r14
0x140056865  mov     [rsp+2F0h+var_288], r13
0x14005686a  lea     rdx, [rsp+2F0h+var_288]
0x14005686f  lea     rcx, [rsp+2F0h+var_278]
0x140056874  call    ??8?$CAutoCleanupBase@PEAPEAU_EVENT_TRACE_PROPERTIES@@@RAII@@UEBA_NAEBQEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; RAII::CAutoCleanupBase<_EVENT_TRACE_PROPERTIES * *>::operator==(_EVENT_TRACE_PROPERTIES * * const &)
0x140056879  test    al, al
0x14005687b  jz      loc_14005695C
0x140056881  call    cs:__imp_GetLastError
0x140056888  nop     dword ptr [rax+rax+00h]
0x14005688d  mov     esi, eax
0x14005688f  call    cs:__imp_GetLastError
0x140056896  nop     dword ptr [rax+rax+00h]
0x14005689b  mov     edi, eax
0x14005689d  call    cs:__imp_CurrentIP
0x1400568a4  nop     dword ptr [rax+rax+00h]
0x1400568a9  mov     rbx, rax
0x1400568ac  mov     dword ptr [rsp+2F0h+ppszDestEnd], esi
0x1400568b0  mov     r9, r15
0x1400568b3  lea     r8, [rbp+1F0h+TargetPath]
0x1400568b7  lea     rdx, aBuildpathFaile; "BuildPath failed for %s and %s. GLE: %u"
0x1400568be  mov     ecx, 3000000h; unsigned int
0x1400568c3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400568c8  mov     [rsp+50h], r13d
0x1400568cd  mov     qword ptr [rsp+2F0h+var_2A8], r13
0x1400568d2  mov     dword ptr [rsp+2F0h+var_2B0], edi
0x1400568d6  mov     qword ptr [rsp+2F0h+var_2B8], rbx
0x1400568db  lea     rcx, aHivelistenumer; "HiveListEnumerator::ConvertWin32PathToN"...
0x1400568e2  mov     [rsp+2F0h+var_2C0], rcx
0x1400568e7  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1400568ee  mov     [rsp+2F0h+pcchRemaining], rcx
0x1400568f3  mov     dword ptr [rsp+2F0h+ppszDestEnd], 14Fh
0x1400568fb  xor     r9d, r9d
0x1400568fe  lea     r8, aD; "D"
0x140056905  xor     edx, edx
0x140056907  mov     rcx, rax
0x14005690a  call    cs:__imp_WdsSetupLogMessageW
0x140056911  nop     dword ptr [rax+rax+00h]
0x140056916  mov     ecx, esi; dwErrCode
0x140056918  call    cs:__imp_SetLastError
0x14005691f  nop     dword ptr [rax+rax+00h]
0x140056924  nop
0x140056925  mov     [rsp+2F0h+var_278], r14
0x14005692a  mov     rbx, [rbp+1F0h+lpMem]
0x14005692e  test    rbx, rbx
0x140056931  jz      loc_140056630
0x140056937  call    cs:__imp_GetProcessHeap
0x14005693e  nop     dword ptr [rax+rax+00h]
0x140056943  mov     r8, rbx; lpMem
0x140056946  xor     edx, edx; dwFlags
0x140056948  mov     rcx, rax; hHeap
0x14005694b  call    cs:__imp_HeapFree
0x140056952  nop     dword ptr [rax+rax+00h]
0x140056957  jmp     loc_140056630
0x14005695c  mov     rcx, [rbp+1F0h+lpMem]
0x140056960  mov     [rbx], rcx
0x140056963  mov     al, 1
0x140056965  mov     rcx, [rbp+1F0h+var_40]
0x14005696c  xor     rcx, rsp; StackCookie
0x14005696f  call    __security_check_cookie
0x140056974  mov     rbx, [rsp+2F0h+arg_10]
0x14005697c  add     rsp, 2C0h
0x140056983  pop     r15
0x140056985  pop     r14
0x140056987  pop     r13
0x140056989  pop     r12
0x14005698b  pop     rdi
0x14005698c  pop     rsi
0x14005698d  pop     rbp
0x14005698e  retn
```
