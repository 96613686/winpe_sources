# WsmGetServiceKeyName

- ea: `0x140059ffc`
- end: `0x14005a3b8`
- name: `WsmGetServiceKeyName`
- size: `956`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14005aa68`
- `0x14005b208`

## callees

- `0x140028144`
- `0x140055d10`
- `0x140059c90`
- `0x140059ffc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14005a36c`
- `KERNEL32!HeapFree` at `0x14005a391`
- `KERNEL32!HeapFree` at `0x14005a36c`
- `KERNEL32!HeapFree` at `0x14005a391`
- `KERNEL32!GetProcessHeap` at `0x14005a358`
- `KERNEL32!GetProcessHeap` at `0x14005a37d`
- `KERNEL32!GetProcessHeap` at `0x14005a358`
- `KERNEL32!GetProcessHeap` at `0x14005a37d`
- `KERNEL32!GetLastError` at `0x14005a039`
- `KERNEL32!GetLastError` at `0x14005a281`
- `KERNEL32!GetLastError` at `0x14005a29f`
- `KERNEL32!GetLastError` at `0x14005a2d1`
- `KERNEL32!GetLastError` at `0x14005a039`
- `KERNEL32!GetLastError` at `0x14005a281`
- `KERNEL32!GetLastError` at `0x14005a29f`
- `KERNEL32!GetLastError` at `0x14005a2d1`
- `ntdll!RtlFreeHeap` at `0x14005a24e`
- `ntdll!RtlFreeHeap` at `0x14005a24e`
- `ntdll!RtlAllocateHeap` at `0x14005a11a`
- `ntdll!RtlAllocateHeap` at `0x14005a11a`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005a0af`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005a347`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005a0af`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005a347`
- `WDSCORE!CurrentIP` at `0x14005a047`
- `WDSCORE!CurrentIP` at `0x14005a2df`
- `WDSCORE!CurrentIP` at `0x14005a047`
- `WDSCORE!CurrentIP` at `0x14005a2df`

## string_xrefs

- `0x14005a072`: `WsmGetServiceKeyName`
- `0x14005a305`: `WsmGetServiceKeyName`
- `0x14005a056`: `WsmGetServiceKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x`
- `0x14005a1c6`: `Services\WinSetupMon`
- `0x14005a2ee`: `WsmGetServiceKeyName: Failed to build service key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsmGetServiceKeyName(const WCHAR *a1, wchar_t **a2)
{
  int CurrentControlSetKeyName; // eax
  wchar_t *v4; // r15
  signed int v5; // esi
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int v9; // edi
  __int64 v10; // rbx
  wchar_t *Heap; // r14
  HRESULT v12; // eax
  unsigned __int16 v13; // bx
  HRESULT v14; // eax
  size_t v15; // rcx
  STRSAFE_LPWSTR v16; // rdx
  size_t v17; // r8
  signed __int64 v18; // r9
  wchar_t v19; // ax
  STRSAFE_LPWSTR v20; // rax
  signed int v21; // eax
  signed int v22; // eax
  bool v23; // sf
  signed int v24; // eax
  int v25; // r13d
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  HANDLE ProcessHeap; // rax
  DWORD v31; // [rsp+30h] [rbp-30h]
  DWORD v32; // [rsp+30h] [rbp-30h]
  STRSAFE_LPWSTR pszDest; // [rsp+B0h] [rbp+50h] BYREF
  size_t cchDest; // [rsp+B8h] [rbp+58h] BYREF

  pszDest = 0;
  CurrentControlSetKeyName = WsmGetCurrentControlSetKeyName(a1, (LPVOID *)&pszDest);
  v4 = pszDest;
  v5 = CurrentControlSetKeyName;
  if ( CurrentControlSetKeyName < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000,
           "WsmGetServiceKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x",
           (const char *)a1,
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      450,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetServiceKeyName",
      v7,
      LastError,
      0,
      0);
    goto LABEL_38;
  }
  pszDest = 0;
  v9 = 0;
  cchDest = 0;
  if ( v4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v4[v10] );
    if ( (_DWORD)v10 && v4[(unsigned int)(v10 - 1)] != 92 )
      v9 = 1;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v10 + v9 + 21));
    if ( !Heap )
    {
      NtCurrentTeb()->LastErrorValue = 8;
      goto LABEL_29;
    }
    v12 = StringCchCopyNExW(Heap, (unsigned int)(v10 + v9 + 21), v4, (unsigned int)v10, &pszDest, &cchDest, v31);
    v13 = v12;
    if ( v12 < 0 )
      goto LABEL_27;
    if ( v9 )
    {
      v14 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v32);
      v13 = v14;
      if ( v14 < 0 )
        goto LABEL_27;
    }
    v15 = cchDest;
    if ( cchDest - 1 > 0x7FFFFFFE )
    {
      v13 = 87;
      v21 = -2147024809;
      if ( cchDest )
      {
        *pszDest = 0;
LABEL_27:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        NtCurrentTeb()->LastErrorValue = v13;
        goto LABEL_29;
      }
    }
    else
    {
      v16 = pszDest;
      if ( cchDest )
      {
        v17 = 20 - cchDest;
        v18 = (char *)L"Services\\WinSetupMon" - (char *)pszDest;
        do
        {
          if ( !(v17 + v15) )
            break;
          v19 = *(STRSAFE_LPWSTR)((char *)v16 + v18);
          if ( !v19 )
            break;
          *v16++ = v19;
          --v15;
        }
        while ( v15 );
      }
      v20 = v16 - 1;
      if ( v15 )
        v20 = v16;
      *v20 = 0;
      v21 = v15 == 0 ? 0x8007007A : 0;
    }
    v13 = v21;
    if ( v21 >= 0 )
    {
      v5 = 0;
      NtCurrentTeb()->LastErrorValue = 0;
LABEL_35:
      *a2 = Heap;
      goto LABEL_38;
    }
    goto LABEL_27;
  }
  NtCurrentTeb()->LastErrorValue = 87;
LABEL_29:
  Heap = 0;
  v22 = GetLastError();
  v23 = v22 < 0;
  if ( v22 > 0 )
    v23 = 1;
  if ( v23 )
  {
    v24 = GetLastError();
    v5 = v24;
    if ( v24 > 0 )
      v5 = (unsigned __int16)v24 | 0x80070000;
    v25 = v5;
    if ( v5 >= 0 )
      goto LABEL_35;
  }
  else
  {
    v5 = -2147467259;
    v25 = -2147467259;
  }
  v26 = GetLastError();
  v27 = CurrentIP();
  v28 = ConstructPartialMsgW(0x2000000, "WsmGetServiceKeyName: Failed to build service key path; hr = 0x%x", v25);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    457,
    L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
    L"WsmGetServiceKeyName",
    v27,
    v26,
    0,
    0);
LABEL_38:
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140059ffc  mov     [rsp-38h+arg_0], rbx
0x14005a001  mov     [rsp-38h+arg_8], rdx
0x14005a006  push    rbp
0x14005a007  push    rsi
0x14005a008  push    rdi
0x14005a009  push    r12
0x14005a00b  push    r13
0x14005a00d  push    r14
0x14005a00f  push    r15
0x14005a011  mov     rbp, rsp
0x14005a014  sub     rsp, 60h
0x14005a018  xor     r13d, r13d
0x14005a01b  lea     rdx, [rbp+pszDest]
0x14005a01f  mov     [rbp+pszDest], r13
0x14005a023  mov     r14, rcx
0x14005a026  call    WsmGetCurrentControlSetKeyName
0x14005a02b  mov     r15, [rbp+pszDest]
0x14005a02f  mov     esi, eax
0x14005a031  test    eax, eax
0x14005a033  jns     loc_14005A0C0
0x14005a039  call    cs:__imp_GetLastError
0x14005a040  nop     dword ptr [rax+rax+00h]
0x14005a045  mov     edi, eax
0x14005a047  call    cs:__imp_CurrentIP
0x14005a04e  nop     dword ptr [rax+rax+00h]
0x14005a053  mov     r9d, esi
0x14005a056  lea     rdx, aWsmgetservicek_0; "WsmGetServiceKeyName: Failed to get cur"...
0x14005a05d  mov     r8, r14
0x14005a060  mov     ecx, 2000000h; unsigned int
0x14005a065  mov     rbx, rax
0x14005a068  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005a06d  mov     [rsp+60h+var_10], r13d
0x14005a072  lea     rcx, aWsmgetservicek_1; "WsmGetServiceKeyName"
0x14005a079  mov     [rsp+60h+var_18], r13
0x14005a07e  lea     r8, aD; "D"
0x14005a085  mov     [rsp+60h+var_20], edi
0x14005a089  xor     r9d, r9d
0x14005a08c  mov     [rsp+60h+var_28], rbx
0x14005a091  xor     edx, edx
0x14005a093  mov     [rsp+60h+var_30], rcx
0x14005a098  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005a09f  mov     [rsp+60h+pcchRemaining], rcx
0x14005a0a4  mov     rcx, rax
0x14005a0a7  mov     dword ptr [rsp+60h+ppszDestEnd], 1C2h
0x14005a0af  call    cs:__imp_WdsSetupLogMessageW
0x14005a0b6  nop     dword ptr [rax+rax+00h]
0x14005a0bb  jmp     loc_14005A378
0x14005a0c0  mov     [rbp+pszDest], r13
0x14005a0c4  mov     edi, r13d
0x14005a0c7  mov     [rbp+cchDest], r13
0x14005a0cb  test    r15, r15
0x14005a0ce  jz      loc_14005A26B
0x14005a0d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005a0d8  inc     rbx
0x14005a0db  cmp     [r15+rbx*2], r13w
0x14005a0e0  jnz     short loc_14005A0D8
0x14005a0e2  mov     r12d, 1
0x14005a0e8  test    ebx, ebx
0x14005a0ea  jz      short loc_14005A0FD
0x14005a0ec  lea     ecx, [rbx-1]
0x14005a0ef  lea     eax, [r12+5Bh]
0x14005a0f4  cmp     ax, [r15+rcx*2]
0x14005a0f9  cmovnz  edi, r12d
0x14005a0fd  mov     rcx, gs:60h
0x14005a106  lea     eax, [rdi+15h]
0x14005a109  add     eax, ebx
0x14005a10b  mov     edx, 8; Flags
0x14005a110  mov     esi, eax
0x14005a112  mov     rcx, [rcx+30h]; HeapHandle
0x14005a116  lea     r8, [rax+rax]; Size
0x14005a11a  call    cs:__imp_RtlAllocateHeap
0x14005a121  nop     dword ptr [rax+rax+00h]
0x14005a126  mov     r14, rax
0x14005a129  test    rax, rax
0x14005a12c  jnz     short loc_14005A143
0x14005a12e  mov     rax, gs:30h
0x14005a137  mov     dword ptr [rax+68h], 8
0x14005a13e  jmp     loc_14005A27B
0x14005a143  lea     rax, [rbp+cchDest]
0x14005a147  mov     r9d, ebx; cchToCopy
0x14005a14a  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x14005a14f  mov     r8, r15; pszSrc
0x14005a152  lea     rax, [rbp+pszDest]
0x14005a156  mov     rdx, rsi; cchDest
0x14005a159  mov     rcx, r14; pszDest
0x14005a15c  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x14005a161  call    StringCchCopyNExW
0x14005a166  mov     ebx, eax
0x14005a168  test    eax, eax
0x14005a16a  js      loc_14005A23C
0x14005a170  test    edi, edi
0x14005a172  jz      short loc_14005A1A7
0x14005a174  mov     rdx, [rbp+cchDest]; cchDest
0x14005a178  lea     rax, [rbp+cchDest]
0x14005a17c  mov     rcx, [rbp+pszDest]; pszDest
0x14005a180  lea     r8, pszSrc; "\\"
0x14005a187  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x14005a18c  mov     r9, r12; cchToCopy
0x14005a18f  lea     rax, [rbp+pszDest]
0x14005a193  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x14005a198  call    StringCchCopyNExW
0x14005a19d  mov     ebx, eax
0x14005a19f  test    eax, eax
0x14005a1a1  js      loc_14005A23C
0x14005a1a7  mov     rcx, [rbp+cchDest]
0x14005a1ab  lea     rax, [rcx-1]
0x14005a1af  cmp     rax, 7FFFFFFEh
0x14005a1b5  ja      short loc_14005A228
0x14005a1b7  mov     rdx, [rbp+pszDest]
0x14005a1bb  test    rcx, rcx
0x14005a1be  jz      short loc_14005A1F2
0x14005a1c0  mov     r8d, 14h
0x14005a1c6  lea     r9, aServicesWinset; "Services\\WinSetupMon"
0x14005a1cd  sub     r8, rcx
0x14005a1d0  sub     r9, rdx
0x14005a1d3  lea     rax, [r8+rcx]
0x14005a1d7  test    rax, rax
0x14005a1da  jz      short loc_14005A1F2
0x14005a1dc  movzx   eax, word ptr [r9+rdx]
0x14005a1e1  test    ax, ax
0x14005a1e4  jz      short loc_14005A1F2
0x14005a1e6  mov     [rdx], ax
0x14005a1e9  add     rdx, 2
0x14005a1ed  sub     rcx, r12
0x14005a1f0  jnz     short loc_14005A1D3
0x14005a1f2  test    rcx, rcx
0x14005a1f5  lea     rax, [rdx-2]
0x14005a1f9  cmovnz  rax, rdx
0x14005a1fd  neg     rcx
0x14005a200  mov     [rax], r13w
0x14005a204  sbb     eax, eax
0x14005a206  not     eax
0x14005a208  and     eax, 8007007Ah
0x14005a20d  mov     ebx, eax
0x14005a20f  test    eax, eax
0x14005a211  js      short loc_14005A23C
0x14005a213  mov     rax, gs:30h
0x14005a21c  mov     esi, r13d
0x14005a21f  mov     [rax+68h], r13d
0x14005a223  jmp     loc_14005A2BD
0x14005a228  mov     ebx, 80070057h
0x14005a22d  mov     eax, ebx
0x14005a22f  test    rcx, rcx
0x14005a232  jz      short loc_14005A20D
0x14005a234  mov     rax, [rbp+pszDest]
0x14005a238  mov     [rax], r13w
0x14005a23c  mov     rcx, gs:60h
0x14005a245  mov     r8, r14; P
0x14005a248  xor     edx, edx; Flags
0x14005a24a  mov     rcx, [rcx+30h]; HeapHandle
0x14005a24e  call    cs:__imp_RtlFreeHeap
0x14005a255  nop     dword ptr [rax+rax+00h]
0x14005a25a  mov     rax, gs:30h
0x14005a263  movzx   ecx, bx
0x14005a266  mov     [rax+68h], ecx
0x14005a269  jmp     short loc_14005A27B
0x14005a26b  mov     rax, gs:30h
0x14005a274  mov     dword ptr [rax+68h], 57h ; 'W'
0x14005a27b  mov     r14, r13
0x14005a27e  mov     r12, r13
0x14005a281  call    cs:__imp_GetLastError
0x14005a288  nop     dword ptr [rax+rax+00h]
0x14005a28d  mov     ebx, 80070000h
0x14005a292  test    eax, eax
0x14005a294  jle     short loc_14005A29D
0x14005a296  movzx   eax, ax
0x14005a299  or      eax, ebx
0x14005a29b  test    eax, eax
0x14005a29d  jns     short loc_14005A2C9
0x14005a29f  call    cs:__imp_GetLastError
0x14005a2a6  nop     dword ptr [rax+rax+00h]
0x14005a2ab  mov     esi, eax
0x14005a2ad  test    eax, eax
0x14005a2af  jle     short loc_14005A2B6
0x14005a2b1  movzx   esi, ax
0x14005a2b4  or      esi, ebx
0x14005a2b6  mov     r13d, esi
0x14005a2b9  test    esi, esi
0x14005a2bb  js      short loc_14005A2D1
0x14005a2bd  mov     rax, [rbp+arg_8]
0x14005a2c1  mov     [rax], r14
0x14005a2c4  jmp     loc_14005A378
0x14005a2c9  mov     esi, 80004005h
0x14005a2ce  mov     r13d, esi
0x14005a2d1  call    cs:__imp_GetLastError
0x14005a2d8  nop     dword ptr [rax+rax+00h]
0x14005a2dd  mov     edi, eax
0x14005a2df  call    cs:__imp_CurrentIP
0x14005a2e6  nop     dword ptr [rax+rax+00h]
0x14005a2eb  mov     r8d, r13d
0x14005a2ee  lea     rdx, aWsmgetservicek; "WsmGetServiceKeyName: Failed to build s"...
0x14005a2f5  mov     ecx, 2000000h; unsigned int
0x14005a2fa  mov     rbx, rax
0x14005a2fd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005a302  xor     r13d, r13d
0x14005a305  lea     rcx, aWsmgetservicek_1; "WsmGetServiceKeyName"
0x14005a30c  mov     [rsp+60h+var_10], r13d
0x14005a311  lea     r8, aD; "D"
0x14005a318  mov     [rsp+60h+var_18], r13
0x14005a31d  xor     r9d, r9d
0x14005a320  mov     [rsp+60h+var_20], edi
0x14005a324  xor     edx, edx
0x14005a326  mov     [rsp+60h+var_28], rbx
0x14005a32b  mov     [rsp+60h+var_30], rcx
0x14005a330  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005a337  mov     [rsp+60h+pcchRemaining], rcx
0x14005a33c  mov     rcx, rax
0x14005a33f  mov     dword ptr [rsp+60h+ppszDestEnd], 1C9h
0x14005a347  call    cs:__imp_WdsSetupLogMessageW
0x14005a34e  nop     dword ptr [rax+rax+00h]
0x14005a353  test    r12, r12
0x14005a356  jz      short loc_14005A378
0x14005a358  call    cs:__imp_GetProcessHeap
0x14005a35f  nop     dword ptr [rax+rax+00h]
0x14005a364  mov     r8, r12; lpMem
0x14005a367  xor     edx, edx; dwFlags
0x14005a369  mov     rcx, rax; hHeap
0x14005a36c  call    cs:__imp_HeapFree
0x14005a373  nop     dword ptr [rax+rax+00h]
0x14005a378  test    r15, r15
0x14005a37b  jz      short loc_14005A39D
0x14005a37d  call    cs:__imp_GetProcessHeap
0x14005a384  nop     dword ptr [rax+rax+00h]
0x14005a389  mov     r8, r15; lpMem
0x14005a38c  xor     edx, edx; dwFlags
0x14005a38e  mov     rcx, rax; hHeap
0x14005a391  call    cs:__imp_HeapFree
0x14005a398  nop     dword ptr [rax+rax+00h]
0x14005a39d  mov     rbx, [rsp+60h+arg_0]
0x14005a3a5  mov     eax, esi
0x14005a3a7  add     rsp, 60h
0x14005a3ab  pop     r15
0x14005a3ad  pop     r14
0x14005a3af  pop     r13
0x14005a3b1  pop     r12
0x14005a3b3  pop     rdi
0x14005a3b4  pop     rsi
0x14005a3b5  pop     rbp
0x14005a3b6  retn
```
