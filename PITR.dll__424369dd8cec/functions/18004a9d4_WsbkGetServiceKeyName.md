# WsbkGetServiceKeyName

- ea: `0x18004a9d4`
- end: `0x18004acc1`
- name: `WsbkGetServiceKeyName`
- size: `749`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18004a6d4`
- `0x18004acc8`
- `0x18004d2a8`

## callees

- `0x180009e04`
- `0x18003b7f4`
- `0x18003e128`
- `0x180049e58`
- `0x18004a9d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ac7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ac93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ac7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ac93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ac88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aca1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ac88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004abe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac08`
- `ntdll!RtlAllocateHeap` at `0x18004aad7`
- `ntdll!RtlAllocateHeap` at `0x18004aad7`
- `ntdll!RtlFreeHeap` at `0x18004ab9d`
- `ntdll!RtlFreeHeap` at `0x18004ab9d`
- `WDSCORE!CurrentIP` at `0x18004aa13`
- `WDSCORE!CurrentIP` at `0x18004ac10`
- `WDSCORE!CurrentIP` at `0x18004aa13`
- `WDSCORE!CurrentIP` at `0x18004ac10`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004aa75`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ac6f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004aa75`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ac6f`

## string_xrefs

- `0x18004aa38`: `WsbkGetServiceKeyName`
- `0x18004ac32`: `WsbkGetServiceKeyName`
- `0x18004ab5d`: `Services\WinSetupBak`
- `0x18004aa1c`: `WsbkGetServiceKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x`
- `0x18004ac19`: `WsbkGetServiceKeyName: Failed to build service key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsbkGetServiceKeyName(const WCHAR *a1, wchar_t **a2)
{
  int CurrentControlSetKeyName; // eax
  wchar_t *v5; // r14
  signed int v6; // esi
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  int v10; // esi
  __int64 v11; // rbx
  wchar_t *Heap; // rdi
  HRESULT v13; // eax
  unsigned __int16 v14; // bx
  HRESULT v15; // eax
  HRESULT v16; // eax
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  HANDLE ProcessHeap; // rax
  DWORD v25; // [rsp+30h] [rbp-30h]
  DWORD v26; // [rsp+30h] [rbp-30h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+B0h] [rbp+50h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+B8h] [rbp+58h] BYREF

  pszSrc = 0;
  CurrentControlSetKeyName = WsbkGetCurrentControlSetKeyName(a1, (LPVOID *)&pszSrc);
  v5 = (wchar_t *)pszSrc;
  v6 = CurrentControlSetKeyName;
  if ( CurrentControlSetKeyName < 0 )
  {
    LastError = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x2000000,
           "WsbkGetServiceKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x",
           (const char *)a1,
           v6);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      3016,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetServiceKeyName",
      v8,
      LastError,
      0,
      0);
    goto LABEL_27;
  }
  pszDest = 0;
  pszSrc = 0;
  if ( v5 )
  {
    v10 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v5[v11] );
    if ( (_DWORD)v11 && v5[(unsigned int)(v11 - 1)] != 92 )
      v10 = 1;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v11 + v10 + 21));
    if ( Heap )
    {
      v13 = StringCchCopyNExW(
              Heap,
              (unsigned int)(v11 + v10 + 21),
              v5,
              (unsigned int)v11,
              &pszDest,
              (size_t *)&pszSrc,
              v25);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( !v10
          || (v15 = StringCchCopyNExW(pszDest, (size_t)pszSrc, L"\\", 1u, &pszDest, (size_t *)&pszSrc, v26),
              v14 = v15,
              v15 >= 0) )
        {
          v16 = StringCchCopyNW(pszDest, (size_t)pszSrc, L"Services\\WinSetupBak", 0x14u);
          v14 = v16;
          if ( v16 >= 0 )
          {
            v6 = 0;
            NtCurrentTeb()->LastErrorValue = 0;
LABEL_24:
            *a2 = Heap;
            goto LABEL_27;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v14;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
  }
  Heap = 0;
  v17 = GetLastError();
  v18 = v17 < 0;
  if ( v17 > 0 )
    v18 = 1;
  if ( v18 )
  {
    v19 = GetLastError();
    v6 = v19;
    if ( v19 > 0 )
      v6 = (unsigned __int16)v19 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_24;
  }
  else
  {
    v6 = -2147467259;
  }
  v20 = GetLastError();
  v21 = CurrentIP();
  v22 = ConstructPartialMsgW(0x2000000, "WsbkGetServiceKeyName: Failed to build service key path; hr = 0x%x", v6);
  WdsSetupLogMessageW(
    v22,
    0,
    L"D",
    0,
    3023,
    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
    L"WsbkGetServiceKeyName",
    v21,
    v20,
    0,
    0);
LABEL_27:
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004a9d4  mov     [rsp-38h+arg_0], rbx
0x18004a9d9  push    rbp
0x18004a9da  push    rsi
0x18004a9db  push    rdi
0x18004a9dc  push    r12
0x18004a9de  push    r13
0x18004a9e0  push    r14
0x18004a9e2  push    r15
0x18004a9e4  mov     rbp, rsp
0x18004a9e7  sub     rsp, 60h
0x18004a9eb  mov     r12, rdx
0x18004a9ee  xor     r13d, r13d
0x18004a9f1  lea     rdx, [rbp+pszSrc]
0x18004a9f5  mov     [rbp+pszSrc], r13
0x18004a9f9  mov     r15, rcx
0x18004a9fc  call    WsbkGetCurrentControlSetKeyName
0x18004aa01  mov     r14, [rbp+pszSrc]
0x18004aa05  mov     esi, eax
0x18004aa07  test    eax, eax
0x18004aa09  jns     short loc_18004AA80
0x18004aa0b  call    cs:__imp_GetLastError
0x18004aa11  mov     edi, eax
0x18004aa13  call    cs:__imp_CurrentIP
0x18004aa19  mov     r9d, esi
0x18004aa1c  lea     rdx, aWsbkgetservice_1; "WsbkGetServiceKeyName: Failed to get cu"...
0x18004aa23  mov     r8, r15
0x18004aa26  mov     ecx, 2000000h; unsigned int
0x18004aa2b  mov     rbx, rax
0x18004aa2e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004aa33  mov     [rsp+60h+var_10], r13d
0x18004aa38  lea     rcx, aWsbkgetservice; "WsbkGetServiceKeyName"
0x18004aa3f  mov     [rsp+60h+var_18], r13
0x18004aa44  lea     r8, aD; "D"
0x18004aa4b  mov     [rsp+60h+var_20], edi
0x18004aa4f  xor     r9d, r9d
0x18004aa52  mov     [rsp+60h+var_28], rbx
0x18004aa57  xor     edx, edx
0x18004aa59  mov     [rsp+60h+var_30], rcx
0x18004aa5e  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004aa65  mov     [rsp+60h+pcchRemaining], rcx
0x18004aa6a  mov     rcx, rax
0x18004aa6d  mov     dword ptr [rsp+60h+ppszDestEnd], 0BC8h
0x18004aa75  call    cs:__imp_WdsSetupLogMessageW
0x18004aa7b  jmp     loc_18004AC8E
0x18004aa80  mov     [rbp+pszDest], r13
0x18004aa84  mov     [rbp+pszSrc], r13
0x18004aa88  test    r14, r14
0x18004aa8b  jz      loc_18004ABB4
0x18004aa91  mov     esi, r13d
0x18004aa94  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004aa98  inc     rbx
0x18004aa9b  cmp     [r14+rbx*2], r13w
0x18004aaa0  jnz     short loc_18004AA98
0x18004aaa2  mov     edx, 1
0x18004aaa7  test    ebx, ebx
0x18004aaa9  jz      short loc_18004AAB9
0x18004aaab  lea     ecx, [rbx-1]
0x18004aaae  lea     eax, [rdx+5Bh]
0x18004aab1  cmp     ax, [r14+rcx*2]
0x18004aab6  cmovnz  esi, edx
0x18004aab9  mov     rcx, gs:60h
0x18004aac2  lea     eax, [rsi+15h]
0x18004aac5  add     eax, ebx
0x18004aac7  mov     edx, 8; Flags
0x18004aacc  mov     r15d, eax
0x18004aacf  mov     rcx, [rcx+30h]; HeapHandle
0x18004aad3  lea     r8, [rax+rax]; Size
0x18004aad7  call    cs:__imp_RtlAllocateHeap
0x18004aadd  mov     rdi, rax
0x18004aae0  test    rax, rax
0x18004aae3  jnz     short loc_18004AAFA
0x18004aae5  mov     rax, gs:30h
0x18004aaee  mov     dword ptr [rax+68h], 8
0x18004aaf5  jmp     loc_18004ABC4
0x18004aafa  lea     rax, [rbp+pszSrc]
0x18004aafe  mov     r9d, ebx; cchToCopy
0x18004ab01  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x18004ab06  mov     r8, r14; pszSrc
0x18004ab09  lea     rax, [rbp+pszDest]
0x18004ab0d  mov     rdx, r15; cchDest
0x18004ab10  mov     rcx, rdi; pszDest
0x18004ab13  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x18004ab18  call    StringCchCopyNExW
0x18004ab1d  mov     ebx, eax
0x18004ab1f  test    eax, eax
0x18004ab21  js      short loc_18004AB8B
0x18004ab23  test    esi, esi
0x18004ab25  jz      short loc_18004AB59
0x18004ab27  mov     rdx, [rbp+pszSrc]; cchDest
0x18004ab2b  lea     rax, [rbp+pszSrc]
0x18004ab2f  mov     rcx, [rbp+pszDest]; pszDest
0x18004ab33  lea     r8, pszSrc; "\\"
0x18004ab3a  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x18004ab3f  mov     r9d, 1; cchToCopy
0x18004ab45  lea     rax, [rbp+pszDest]
0x18004ab49  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x18004ab4e  call    StringCchCopyNExW
0x18004ab53  mov     ebx, eax
0x18004ab55  test    eax, eax
0x18004ab57  js      short loc_18004AB8B
0x18004ab59  mov     rdx, [rbp+pszSrc]; cchDest
0x18004ab5d  lea     r8, aServicesWinset; "Services\\WinSetupBak"
0x18004ab64  mov     rcx, [rbp+pszDest]; pszDest
0x18004ab68  mov     r9d, 14h; cchToCopy
0x18004ab6e  call    StringCchCopyNW
0x18004ab73  mov     ebx, eax
0x18004ab75  test    eax, eax
0x18004ab77  js      short loc_18004AB8B
0x18004ab79  mov     rax, gs:30h
0x18004ab82  mov     esi, r13d
0x18004ab85  mov     [rax+68h], r13d
0x18004ab89  jmp     short loc_18004ABF7
0x18004ab8b  mov     rcx, gs:60h
0x18004ab94  mov     r8, rdi; P
0x18004ab97  xor     edx, edx; Flags
0x18004ab99  mov     rcx, [rcx+30h]; HeapHandle
0x18004ab9d  call    cs:__imp_RtlFreeHeap
0x18004aba3  mov     rax, gs:30h
0x18004abac  movzx   ecx, bx
0x18004abaf  mov     [rax+68h], ecx
0x18004abb2  jmp     short loc_18004ABC4
0x18004abb4  mov     rax, gs:30h
0x18004abbd  mov     dword ptr [rax+68h], 57h ; 'W'
0x18004abc4  mov     rdi, r13
0x18004abc7  mov     r15, r13
0x18004abca  call    cs:__imp_GetLastError
0x18004abd0  mov     ebx, 80070000h
0x18004abd5  test    eax, eax
0x18004abd7  jle     short loc_18004ABE0
0x18004abd9  movzx   eax, ax
0x18004abdc  or      eax, ebx
0x18004abde  test    eax, eax
0x18004abe0  jns     short loc_18004AC00
0x18004abe2  call    cs:__imp_GetLastError
0x18004abe8  mov     esi, eax
0x18004abea  test    eax, eax
0x18004abec  jle     short loc_18004ABF3
0x18004abee  movzx   esi, ax
0x18004abf1  or      esi, ebx
0x18004abf3  test    esi, esi
0x18004abf5  js      short loc_18004AC05
0x18004abf7  mov     [r12], rdi
0x18004abfb  jmp     loc_18004AC8E
0x18004ac00  mov     esi, 80004005h
0x18004ac05  mov     r12d, esi
0x18004ac08  call    cs:__imp_GetLastError
0x18004ac0e  mov     edi, eax
0x18004ac10  call    cs:__imp_CurrentIP
0x18004ac16  mov     r8d, esi
0x18004ac19  lea     rdx, aWsbkgetservice_0; "WsbkGetServiceKeyName: Failed to build "...
0x18004ac20  mov     ecx, 2000000h; unsigned int
0x18004ac25  mov     rbx, rax
0x18004ac28  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004ac2d  mov     [rsp+60h+var_10], r13d
0x18004ac32  lea     rcx, aWsbkgetservice; "WsbkGetServiceKeyName"
0x18004ac39  mov     [rsp+60h+var_18], r13
0x18004ac3e  lea     r8, aD; "D"
0x18004ac45  mov     [rsp+60h+var_20], edi
0x18004ac49  xor     r9d, r9d
0x18004ac4c  mov     [rsp+60h+var_28], rbx
0x18004ac51  xor     edx, edx
0x18004ac53  mov     [rsp+60h+var_30], rcx
0x18004ac58  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004ac5f  mov     [rsp+60h+pcchRemaining], rcx
0x18004ac64  mov     rcx, rax
0x18004ac67  mov     dword ptr [rsp+60h+ppszDestEnd], 0BCFh
0x18004ac6f  call    cs:__imp_WdsSetupLogMessageW
0x18004ac75  test    r15, r15
0x18004ac78  jz      short loc_18004AC8E
0x18004ac7a  call    cs:__imp_GetProcessHeap
0x18004ac80  mov     r8, r15; lpMem
0x18004ac83  xor     edx, edx; dwFlags
0x18004ac85  mov     rcx, rax; hHeap
0x18004ac88  call    cs:__imp_HeapFree
0x18004ac8e  test    r14, r14
0x18004ac91  jz      short loc_18004ACA7
0x18004ac93  call    cs:__imp_GetProcessHeap
0x18004ac99  mov     r8, r14; lpMem
0x18004ac9c  xor     edx, edx; dwFlags
0x18004ac9e  mov     rcx, rax; hHeap
0x18004aca1  call    cs:__imp_HeapFree
0x18004aca7  mov     rbx, [rsp+60h+arg_0]
0x18004acaf  mov     eax, esi
0x18004acb1  add     rsp, 60h
0x18004acb5  pop     r15
0x18004acb7  pop     r14
0x18004acb9  pop     r13
0x18004acbb  pop     r12
0x18004acbd  pop     rdi
0x18004acbe  pop     rsi
0x18004acbf  pop     rbp
0x18004acc0  retn
```
