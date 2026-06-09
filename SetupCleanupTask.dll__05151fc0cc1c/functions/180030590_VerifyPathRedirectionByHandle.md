# VerifyPathRedirectionByHandle

- ea: `0x180030590`
- end: `0x18003093b`
- name: `VerifyPathRedirectionByHandle`
- size: `939`
- prototype: `_BOOL8 __fastcall(char *, const wchar_t *, BOOL *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting`

## callers

- `0x18002e578`

## callees

- `0x180002ec3`
- `0x18002d974`
- `0x18002da5c`
- `0x18002edf0`
- `0x18002eed8`
- `0x18002ef7c`
- `0x1800303c4`
- `0x180030590`
- `0x1800322ea`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800308ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800308ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003086f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003086f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003089e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003089e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800308e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800308f7`
- `ntdll!RtlFreeHeap` at `0x1800307c6`
- `ntdll!RtlFreeHeap` at `0x1800307c6`
- `ntdll!RtlAllocateHeap` at `0x1800306ff`
- `ntdll!RtlAllocateHeap` at `0x1800306ff`

## pseudocode

```c
_BOOL8 __fastcall VerifyPathRedirectionByHandle(char *a1, const wchar_t *a2, BOOL *a3, _QWORD *a4)
{
  DWORD LastError; // esi
  _QWORD *v5; // r13
  WCHAR *Heap; // rdi
  __int64 v7; // rax
  wchar_t *v8; // rbx
  const wchar_t *v9; // rax
  WCHAR *v10; // r15
  int v11; // r12d
  __int64 v12; // rsi
  __int64 v13; // r14
  int v14; // eax
  const wchar_t *v15; // r13
  __int64 v16; // rcx
  HRESULT v17; // eax
  unsigned __int16 v18; // si
  HRESULT v19; // eax
  HRESULT v20; // eax
  WCHAR *v21; // r12
  HANDLE v22; // rax
  HANDLE ProcessHeap; // rax
  void *v24; // r14
  BOOL v25; // edi
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  DWORD v31; // [rsp+30h] [rbp-59h]
  DWORD v32; // [rsp+30h] [rbp-59h]
  size_t pcchRemaining; // [rsp+40h] [rbp-49h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-41h] BYREF
  __int64 v35; // [rsp+50h] [rbp-39h]
  __int64 v36; // [rsp+58h] [rbp-31h]
  size_t cchDest; // [rsp+60h] [rbp-29h]
  _QWORD *v38; // [rsp+68h] [rbp-21h]
  HANDLE hFile; // [rsp+70h] [rbp-19h]
  BOOL *v40; // [rsp+78h] [rbp-11h]
  wchar_t String2[8]; // [rsp+80h] [rbp-9h] BYREF

  LastError = 0;
  v38 = a4;
  v40 = a3;
  hFile = a1;
  v35 = 0;
  v5 = a4;
  v36 = 0;
  Heap = (WCHAR *)a2;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a2 || !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  wcscpy(String2, L"\\\\?\\");
  if ( !wcsncmp_0(a2, String2, 4u) )
  {
    v10 = 0;
    v8 = 0;
    goto LABEL_32;
  }
  v7 = FormFullPathName(Heap);
  v8 = (wchar_t *)v7;
  if ( !v7 )
    return 0;
  v9 = (const wchar_t *)FormLongPathName(v7);
  v10 = (WCHAR *)v9;
  if ( !v9 )
  {
LABEL_29:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    return 0;
  }
  if ( !wcsncmp_0(v9, String2, 4u) )
  {
    Heap = v10;
LABEL_32:
    v21 = 0;
    goto LABEL_33;
  }
  pszDest = 0;
  pcchRemaining = 0;
  v11 = 0;
  v12 = -1;
  do
    ++v12;
  while ( String2[v12] );
  v13 = -1;
  do
    ++v13;
  while ( v8[v13] );
  if ( (_DWORD)v12 && String2[(unsigned int)(v12 - 1)] == 92 )
  {
    v14 = v13 - 1;
    v15 = v8 + 1;
    if ( *v8 != 92 )
    {
      v14 = v13;
      v15 = v8;
    }
    LODWORD(v13) = v14;
  }
  else
  {
    v15 = v8;
    if ( (_DWORD)v12 && *v8 != 92 )
      v11 = 1;
  }
  v16 = (unsigned int)(v12 + v11 + v13 + 1);
  cchDest = (unsigned int)v16;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v16);
  if ( !Heap )
  {
    NtCurrentTeb()->LastErrorValue = 8;
LABEL_28:
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v10);
    goto LABEL_29;
  }
  v17 = StringCchCopyNExW(Heap, cchDest, String2, (unsigned int)v12, &pszDest, &pcchRemaining, v31);
  v18 = v17;
  if ( v17 < 0
    || v11
    && (v19 = StringCchCopyNExW(pszDest, pcchRemaining, L"\\", 1u, &pszDest, &pcchRemaining, v32), v18 = v19, v19 < 0)
    || (v20 = StringCchCopyNW(pszDest, pcchRemaining, v15, (unsigned int)v13), v18 = v20, v20 < 0) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    NtCurrentTeb()->LastErrorValue = v18;
    goto LABEL_28;
  }
  LastError = 0;
  v5 = v38;
  v21 = Heap;
  NtCurrentTeb()->LastErrorValue = 0;
LABEL_33:
  GetFinalPathFlags(Heap);
  v24 = (void *)FormFinalPathNameByHandle(hFile);
  if ( v24 )
  {
    if ( v35 == -1 || v36 == -1 )
    {
      LastError = 775;
LABEL_44:
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v24);
      goto LABEL_45;
    }
    v25 = wcsicmp_0((const wchar_t *)v24 + v36, &Heap[v35]) == 0;
LABEL_39:
    *v40 = v25;
    if ( v5 )
    {
      if ( v25 )
      {
        *v5 = 0;
      }
      else
      {
        *v5 = v24;
        v24 = 0;
      }
    }
    if ( !v24 )
      goto LABEL_45;
    goto LABEL_44;
  }
  v25 = 0;
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_39;
LABEL_45:
  if ( v21 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v21);
  }
  if ( v10 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v10);
  }
  if ( v8 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v8);
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180030590  push    rbp
0x180030592  push    rbx
0x180030593  push    rsi
0x180030594  push    rdi
0x180030595  push    r12
0x180030597  push    r13
0x180030599  push    r14
0x18003059b  push    r15
0x18003059d  lea     rbp, [rsp-1Fh]
0x1800305a2  sub     rsp, 0A8h
0x1800305a9  mov     rax, cs:__security_cookie
0x1800305b0  xor     rax, rsp
0x1800305b3  mov     [rbp+57h+var_50], rax
0x1800305b7  xor     esi, esi
0x1800305b9  mov     [rbp+57h+var_78], r9
0x1800305bd  mov     rax, rcx
0x1800305c0  mov     [rbp+57h+var_68], r8
0x1800305c4  dec     rax
0x1800305c7  mov     [rbp+57h+hFile], rcx
0x1800305cb  mov     [rbp+57h+var_90], rsi
0x1800305cf  mov     r13, r9
0x1800305d2  mov     [rbp+57h+var_88], rsi
0x1800305d6  mov     rdi, rdx
0x1800305d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800305dd  ja      loc_18003090E
0x1800305e3  test    rdx, rdx
0x1800305e6  jz      loc_18003090E
0x1800305ec  test    r8, r8
0x1800305ef  jz      loc_18003090E
0x1800305f5  movsd   xmm0, qword ptr cs:asc_18003D740; "\\\\?\\"
0x1800305fd  lea     r14d, [rsi+4]
0x180030601  movzx   eax, word ptr cs:asc_18003D740+8; ""
0x180030608  lea     rdx, [rbp+57h+String2]; String2
0x18003060c  mov     r8d, r14d; MaxCount
0x18003060f  movsd   qword ptr [rbp+57h+String2], xmm0
0x180030614  mov     rcx, rdi; String1
0x180030617  mov     [rbp+57h+var_58], ax
0x18003061b  call    wcsncmp_0
0x180030620  test    eax, eax
0x180030622  jz      loc_18003080D
0x180030628  mov     rcx, rdi; lpFileName
0x18003062b  call    FormFullPathName
0x180030630  mov     rbx, rax
0x180030633  test    rax, rax
0x180030636  jz      loc_180030919
0x18003063c  mov     rcx, rax
0x18003063f  call    FormLongPathName
0x180030644  mov     r15, rax
0x180030647  test    rax, rax
0x18003064a  jz      loc_1800307EF
0x180030650  mov     r8d, r14d; MaxCount
0x180030653  lea     rdx, [rbp+57h+String2]; String2
0x180030657  mov     rcx, rax; String1
0x18003065a  call    wcsncmp_0
0x18003065f  test    eax, eax
0x180030661  jz      loc_180030808
0x180030667  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003066b  mov     [rbp+57h+pszDest], rsi
0x18003066f  mov     [rbp+57h+var_A0], rsi
0x180030673  lea     rcx, [rbp+57h+String2]
0x180030677  mov     r12d, esi
0x18003067a  xor     edx, edx
0x18003067c  mov     rsi, rax
0x18003067f  inc     rsi
0x180030682  cmp     [rcx+rsi*2], dx
0x180030686  jnz     short loc_18003067F
0x180030688  mov     r14, rax
0x18003068b  inc     r14
0x18003068e  cmp     [rbx+r14*2], dx
0x180030693  jnz     short loc_18003068B
0x180030695  mov     eax, 1
0x18003069a  lea     r8d, [rax+5Bh]
0x18003069e  test    esi, esi
0x1800306a0  jz      short loc_1800306CB
0x1800306a2  lea     eax, [rsi-1]
0x1800306a5  cmp     r8w, [rbp+rax*2+57h+String2]
0x1800306ab  jnz     short loc_1800306C6
0x1800306ad  cmp     r8w, [rbx]
0x1800306b1  lea     eax, [r14-1]
0x1800306b5  lea     r13, [rbx+2]
0x1800306b9  cmovnz  eax, r14d
0x1800306bd  cmovnz  r13, rbx
0x1800306c1  mov     r14d, eax
0x1800306c4  jmp     short loc_1800306DA
0x1800306c6  mov     eax, 1
0x1800306cb  mov     r13, rbx
0x1800306ce  test    esi, esi
0x1800306d0  jz      short loc_1800306DA
0x1800306d2  cmp     r8w, [rbx]
0x1800306d6  cmovnz  r12d, eax
0x1800306da  lea     ecx, [r14+1]
0x1800306de  mov     edx, 8; Flags
0x1800306e3  add     ecx, r12d
0x1800306e6  add     ecx, esi
0x1800306e8  mov     eax, ecx
0x1800306ea  mov     [rbp+57h+cchDest], rax
0x1800306ee  lea     r8, [rcx+rcx]; Size
0x1800306f2  mov     rcx, gs:60h
0x1800306fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800306ff  call    cs:__imp_RtlAllocateHeap
0x180030705  mov     rdi, rax
0x180030708  test    rax, rax
0x18003070b  jnz     short loc_180030722
0x18003070d  mov     rax, gs:30h
0x180030716  mov     dword ptr [rax+68h], 8
0x18003071d  jmp     loc_1800307DB
0x180030722  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180030726  lea     rax, [rbp+57h+var_A0]
0x18003072a  mov     [rsp+0E0h+pcchRemaining], rax; pcchRemaining
0x18003072f  lea     r8, [rbp+57h+String2]; pszSrc
0x180030733  lea     rax, [rbp+57h+pszDest]
0x180030737  mov     r9d, esi; cchToCopy
0x18003073a  mov     rcx, rdi; pszDest
0x18003073d  mov     [rsp+0E0h+ppszDestEnd], rax; ppszDestEnd
0x180030742  call    StringCchCopyNExW
0x180030747  mov     esi, eax
0x180030749  test    eax, eax
0x18003074b  js      short loc_1800307B4
0x18003074d  test    r12d, r12d
0x180030750  jz      short loc_180030784
0x180030752  mov     rdx, [rbp+57h+var_A0]; cchDest
0x180030756  lea     rax, [rbp+57h+var_A0]
0x18003075a  mov     rcx, [rbp+57h+pszDest]; pszDest
0x18003075e  lea     r8, pszSrc; "\\"
0x180030765  mov     [rsp+0E0h+pcchRemaining], rax; pcchRemaining
0x18003076a  mov     r9d, 1; cchToCopy
0x180030770  lea     rax, [rbp+57h+pszDest]
0x180030774  mov     [rsp+0E0h+ppszDestEnd], rax; ppszDestEnd
0x180030779  call    StringCchCopyNExW
0x18003077e  mov     esi, eax
0x180030780  test    eax, eax
0x180030782  js      short loc_1800307B4
0x180030784  mov     rdx, [rbp+57h+var_A0]; cchDest
0x180030788  mov     r8, r13; pszSrc
0x18003078b  mov     rcx, [rbp+57h+pszDest]; pszDest
0x18003078f  mov     r9d, r14d; cchToCopy
0x180030792  call    StringCchCopyNW
0x180030797  mov     esi, eax
0x180030799  test    eax, eax
0x18003079b  js      short loc_1800307B4
0x18003079d  mov     rax, gs:30h
0x1800307a6  xor     esi, esi
0x1800307a8  mov     r13, [rbp+57h+var_78]
0x1800307ac  mov     r12, rdi
0x1800307af  mov     [rax+68h], esi
0x1800307b2  jmp     short loc_180030816
0x1800307b4  mov     rcx, gs:60h
0x1800307bd  mov     r8, rdi; P
0x1800307c0  xor     edx, edx; Flags
0x1800307c2  mov     rcx, [rcx+30h]; HeapHandle
0x1800307c6  call    cs:__imp_RtlFreeHeap
0x1800307cc  mov     rax, gs:30h
0x1800307d5  movzx   ecx, si
0x1800307d8  mov     [rax+68h], ecx
0x1800307db  call    cs:__imp_GetProcessHeap
0x1800307e1  mov     r8, r15; lpMem
0x1800307e4  xor     edx, edx; dwFlags
0x1800307e6  mov     rcx, rax; hHeap
0x1800307e9  call    cs:__imp_HeapFree
0x1800307ef  call    cs:__imp_GetProcessHeap
0x1800307f5  mov     r8, rbx; lpMem
0x1800307f8  xor     edx, edx; dwFlags
0x1800307fa  mov     rcx, rax; hHeap
0x1800307fd  call    cs:__imp_HeapFree
0x180030803  jmp     loc_180030919
0x180030808  mov     rdi, r15
0x18003080b  jmp     short loc_180030813
0x18003080d  mov     r15, rsi
0x180030810  mov     rbx, rsi
0x180030813  mov     r12, rsi
0x180030816  lea     r8, [rbp+57h+var_88]
0x18003081a  mov     rcx, rdi; String1
0x18003081d  lea     rdx, [rbp+57h+var_90]
0x180030821  call    GetFinalPathFlags
0x180030826  mov     rcx, [rbp+57h+hFile]; hFile
0x18003082a  mov     edx, eax
0x18003082c  call    FormFinalPathNameByHandle
0x180030831  mov     r14, rax
0x180030834  test    rax, rax
0x180030837  jz      short loc_18003086D
0x180030839  mov     rax, [rbp+57h+var_90]
0x18003083d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030841  jz      short loc_180030866
0x180030843  mov     rcx, [rbp+57h+var_88]
0x180030847  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003084b  jz      short loc_180030866
0x18003084d  lea     rdx, [rdi+rax*2]; String2
0x180030851  lea     rcx, [r14+rcx*2]; String1
0x180030855  call    _wcsicmp_0
0x18003085a  xor     ecx, ecx
0x18003085c  test    eax, eax
0x18003085e  mov     edi, ecx
0x180030860  setz    dil
0x180030864  jmp     short loc_18003087D
0x180030866  mov     esi, 307h
0x18003086b  jmp     short loc_18003089E
0x18003086d  mov     edi, esi
0x18003086f  call    cs:__imp_GetLastError
0x180030875  xor     ecx, ecx
0x180030877  mov     esi, eax
0x180030879  test    eax, eax
0x18003087b  jnz     short loc_1800308B2
0x18003087d  mov     rax, [rbp+57h+var_68]
0x180030881  mov     [rax], edi
0x180030883  test    r13, r13
0x180030886  jz      short loc_180030899
0x180030888  test    edi, edi
0x18003088a  jnz     short loc_180030895
0x18003088c  mov     [r13+0], r14
0x180030890  mov     r14, rcx
0x180030893  jmp     short loc_180030899
0x180030895  mov     [r13+0], rcx
0x180030899  test    r14, r14
0x18003089c  jz      short loc_1800308B2
0x18003089e  call    cs:__imp_GetProcessHeap
0x1800308a4  mov     r8, r14; lpMem
0x1800308a7  xor     edx, edx; dwFlags
0x1800308a9  mov     rcx, rax; hHeap
0x1800308ac  call    cs:__imp_HeapFree
0x1800308b2  test    r12, r12
0x1800308b5  jz      short loc_1800308CB
0x1800308b7  call    cs:__imp_GetProcessHeap
0x1800308bd  mov     r8, r12; lpMem
0x1800308c0  xor     edx, edx; dwFlags
0x1800308c2  mov     rcx, rax; hHeap
0x1800308c5  call    cs:__imp_HeapFree
0x1800308cb  test    r15, r15
0x1800308ce  jz      short loc_1800308E4
0x1800308d0  call    cs:__imp_GetProcessHeap
0x1800308d6  mov     r8, r15; lpMem
0x1800308d9  xor     edx, edx; dwFlags
0x1800308db  mov     rcx, rax; hHeap
0x1800308de  call    cs:__imp_HeapFree
0x1800308e4  test    rbx, rbx
0x1800308e7  jz      short loc_1800308FD
0x1800308e9  call    cs:__imp_GetProcessHeap
0x1800308ef  mov     r8, rbx; lpMem
0x1800308f2  xor     edx, edx; dwFlags
0x1800308f4  mov     rcx, rax; hHeap
0x1800308f7  call    cs:__imp_HeapFree
0x1800308fd  mov     ecx, esi; dwErrCode
0x1800308ff  call    cs:__imp_SetLastError
0x180030905  xor     eax, eax
0x180030907  test    esi, esi
0x180030909  setz    al
0x18003090c  jmp     short loc_18003091B
0x18003090e  mov     ecx, 57h ; 'W'; dwErrCode
0x180030913  call    cs:__imp_SetLastError
0x180030919  xor     eax, eax
0x18003091b  mov     rcx, [rbp+57h+var_50]
0x18003091f  xor     rcx, rsp; StackCookie
0x180030922  call    __security_check_cookie
0x180030927  add     rsp, 0A8h
0x18003092e  pop     r15
0x180030930  pop     r14
0x180030932  pop     r13
0x180030934  pop     r12
0x180030936  pop     rdi
0x180030937  pop     rsi
0x180030938  pop     rbx
0x180030939  pop     rbp
0x18003093a  retn
```
