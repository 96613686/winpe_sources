# UtilIsInteractiveDesktop(void)

- ea: `0x18001c04c`
- end: `0x18001c379`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `813`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c26c`
- `0x18002f34c`

## callees

- `0x180004bb4`
- `0x18001c04c`
- `0x18001c5ec`
- `0x18001c650`
- `0x18001fe24`
- `0x180038f78`
- `0x180053a38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c319`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c32d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c319`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c32d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c361`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c361`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c1a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c1a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c09c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ff`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c0d7`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c1ca`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c21e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c2dc`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c0d7`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c1ca`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c21e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001c2dc`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18001c093`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18001c093`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18001c0a4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18001c0a4`

## pseudocode

```c
__int64 UtilIsInteractiveDesktop(void)
{
  void *v0; // rbx
  PVOID v1; // rsi
  unsigned int v2; // r14d
  HWINSTA ProcessWindowStation; // r15
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v6; // r12
  DWORD LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // eax
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  SIZE_T v12; // rax
  unsigned __int64 v13; // kr00_8
  __int64 unique_for; // rax
  DWORD nLengthNeeded; // [rsp+70h] [rbp+40h] BYREF
  PVOID pvInfo; // [rsp+78h] [rbp+48h] BYREF
  char v18; // [rsp+80h] [rbp+50h] BYREF

  v0 = 0;
  v1 = 0;
  pvInfo = 0;
  v2 = 0;
  nLengthNeeded = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  ProcessWindowStation = GetProcessWindowStation();
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v6 = ThreadDesktop;
  if ( !ProcessWindowStation || !ThreadDesktop )
    goto LABEL_41;
  nLengthNeeded = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      v8 = 10;
LABEL_11:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, LastError);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v9 = nLengthNeeded + 1;
  if ( nLengthNeeded == -1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_41;
    v11 = 11;
    goto LABEL_16;
  }
  v13 = v9;
  v12 = 2LL * v9;
  if ( !is_mul_ok(v13, 2u) )
    v12 = -1;
  v0 = HeapAlloc(g_hWerheap, 0, v12);
  if ( !v0 )
    goto LABEL_41;
  if ( GetUserObjectInformationW(ProcessWindowStation, 2, v0, nLengthNeeded, &nLengthNeeded) )
  {
    nLengthNeeded = 0;
    if ( !GetUserObjectInformationW(v6, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = 13;
        goto LABEL_11;
      }
      goto LABEL_41;
    }
    if ( nLengthNeeded )
    {
      unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&pvInfo, unique_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
      v1 = pvInfo;
      if ( !pvInfo )
        goto LABEL_43;
      if ( GetUserObjectInformationW(v6, 2, pvInfo, nLengthNeeded, &nLengthNeeded) )
      {
        if ( !(unsigned int)_o__wcsicmp(v0, L"WinSta0") && !(unsigned int)_o__wcsicmp(v1, L"default") )
          v2 = 1;
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = 15;
        goto LABEL_11;
      }
      goto LABEL_41;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_41;
    v11 = 14;
LABEL_16:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    LastError = GetLastError();
    v8 = 12;
    goto LABEL_11;
  }
LABEL_41:
  if ( v1 )
    HeapFree(g_hWerheap, 0, v1);
LABEL_43:
  if ( v0 )
    HeapFree(g_hWerheap, 0, v0);
  return v2;
}

```

## disassembly

```asm
0x18001c04c  push    rbp
0x18001c04e  push    rbx
0x18001c04f  push    rsi
0x18001c050  push    rdi
0x18001c051  push    r12
0x18001c053  push    r14
0x18001c055  push    r15
0x18001c057  mov     rbp, rsp
0x18001c05a  sub     rsp, 30h
0x18001c05e  xor     ebx, ebx
0x18001c060  xor     esi, esi
0x18001c062  mov     [rbp+pvInfo], rsi
0x18001c066  xor     r14d, r14d
0x18001c069  mov     [rbp+nLengthNeeded], ebx
0x18001c06c  call    IsGetThreadDesktopPresent
0x18001c071  test    al, al
0x18001c073  jz      loc_18001C339
0x18001c079  call    IsGetThreadDesktopPresent
0x18001c07e  test    al, al
0x18001c080  jz      loc_18001C339
0x18001c086  call    IsGetThreadDesktopPresent
0x18001c08b  test    al, al
0x18001c08d  jz      loc_18001C339
0x18001c093  call    cs:__imp_GetProcessWindowStation
0x18001c099  mov     r15, rax
0x18001c09c  call    cs:__imp_GetCurrentThreadId
0x18001c0a2  mov     ecx, eax; dwThreadId
0x18001c0a4  call    cs:__imp_GetThreadDesktop
0x18001c0aa  mov     r12, rax
0x18001c0ad  test    r15, r15
0x18001c0b0  jz      loc_18001C339
0x18001c0b6  test    rax, rax
0x18001c0b9  jz      loc_18001C339
0x18001c0bf  lea     rax, [rbp+nLengthNeeded]
0x18001c0c3  mov     [rbp+nLengthNeeded], ebx
0x18001c0c6  xor     r9d, r9d; nLength
0x18001c0c9  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001c0ce  xor     r8d, r8d; pvInfo
0x18001c0d1  lea     edx, [rbx+2]; nIndex
0x18001c0d4  mov     rcx, r15; hObj
0x18001c0d7  call    cs:__imp_GetUserObjectInformationW
0x18001c0dd  test    eax, eax
0x18001c0df  jnz     short loc_18001C138
0x18001c0e1  call    cs:__imp_GetLastError
0x18001c0e7  cmp     eax, 7Ah ; 'z'
0x18001c0ea  jz      short loc_18001C138
0x18001c0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0f3  lea     rax, WPP_GLOBAL_Control
0x18001c0fa  cmp     rcx, rax
0x18001c0fd  jz      loc_18001C339
0x18001c103  lea     edi, [rbx+1]
0x18001c106  test    [rcx+1Ch], dil
0x18001c10a  jz      loc_18001C339
0x18001c110  call    cs:__imp_GetLastError
0x18001c116  lea     edx, [rbx+0Ah]
0x18001c119  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c120  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18001c127  mov     r9d, eax
0x18001c12a  mov     rcx, [rcx+10h]
0x18001c12e  call    WPP_SF_d
0x18001c133  jmp     loc_18001C339
0x18001c138  mov     eax, [rbp+nLengthNeeded]
0x18001c13b  mov     edi, 1
0x18001c140  inc     eax
0x18001c142  cmp     eax, edi
0x18001c144  jnb     short loc_18001C17F
0x18001c146  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c14d  lea     rax, WPP_GLOBAL_Control
0x18001c154  cmp     rcx, rax
0x18001c157  jz      loc_18001C339
0x18001c15d  test    [rcx+1Ch], dil
0x18001c161  jz      loc_18001C339
0x18001c167  lea     edx, [rdi+0Ah]
0x18001c16a  mov     rcx, [rcx+10h]
0x18001c16e  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18001c175  call    WPP_SF_
0x18001c17a  jmp     loc_18001C339
0x18001c17f  mov     ecx, eax
0x18001c181  mov     eax, 2
0x18001c186  mul     rcx
0x18001c189  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c190  cmovb   rax, rcx
0x18001c194  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001c19b  mov     r8, rax; dwBytes
0x18001c19e  xor     edx, edx; dwFlags
0x18001c1a0  call    cs:__imp_HeapAlloc
0x18001c1a6  mov     rbx, rax
0x18001c1a9  test    rax, rax
0x18001c1ac  jz      loc_18001C339
0x18001c1b2  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001c1b6  lea     rax, [rbp+nLengthNeeded]
0x18001c1ba  mov     r8, rbx; pvInfo
0x18001c1bd  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001c1c2  mov     edx, 2; nIndex
0x18001c1c7  mov     rcx, r15; hObj
0x18001c1ca  call    cs:__imp_GetUserObjectInformationW
0x18001c1d0  test    eax, eax
0x18001c1d2  jnz     short loc_18001C205
0x18001c1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1db  lea     rax, WPP_GLOBAL_Control
0x18001c1e2  cmp     rcx, rax
0x18001c1e5  jz      loc_18001C339
0x18001c1eb  test    [rcx+1Ch], dil
0x18001c1ef  jz      loc_18001C339
0x18001c1f5  call    cs:__imp_GetLastError
0x18001c1fb  mov     edx, 0Ch
0x18001c200  jmp     loc_18001C119
0x18001c205  xor     r9d, r9d; nLength
0x18001c208  mov     [rbp+nLengthNeeded], esi
0x18001c20b  lea     rax, [rbp+nLengthNeeded]
0x18001c20f  xor     r8d, r8d; pvInfo
0x18001c212  mov     rcx, r12; hObj
0x18001c215  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001c21a  lea     edx, [r9+2]; nIndex
0x18001c21e  call    cs:__imp_GetUserObjectInformationW
0x18001c224  test    eax, eax
0x18001c226  jnz     short loc_18001C264
0x18001c228  call    cs:__imp_GetLastError
0x18001c22e  cmp     eax, 7Ah ; 'z'
0x18001c231  jz      short loc_18001C264
0x18001c233  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c23a  lea     rax, WPP_GLOBAL_Control
0x18001c241  cmp     rcx, rax
0x18001c244  jz      loc_18001C339
0x18001c24a  test    [rcx+1Ch], dil
0x18001c24e  jz      loc_18001C339
0x18001c254  call    cs:__imp_GetLastError
0x18001c25a  mov     edx, 0Dh
0x18001c25f  jmp     loc_18001C119
0x18001c264  mov     eax, [rbp+nLengthNeeded]
0x18001c267  cmp     eax, edi
0x18001c269  jnb     short loc_18001C296
0x18001c26b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c272  lea     rax, WPP_GLOBAL_Control
0x18001c279  cmp     rcx, rax
0x18001c27c  jz      loc_18001C339
0x18001c282  test    [rcx+1Ch], dil
0x18001c286  jz      loc_18001C339
0x18001c28c  mov     edx, 0Eh
0x18001c291  jmp     loc_18001C16A
0x18001c296  lea     edx, [rax+1]
0x18001c299  lea     rcx, [rbp+arg_10]
0x18001c29d  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18001c2a2  mov     rdx, rax
0x18001c2a5  lea     rcx, [rbp+pvInfo]
0x18001c2a9  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18001c2ae  lea     rcx, [rbp+arg_10]; void *
0x18001c2b2  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18001c2b7  mov     rsi, [rbp+pvInfo]
0x18001c2bb  test    rsi, rsi
0x18001c2be  jz      loc_18001C350
0x18001c2c4  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001c2c8  lea     rax, [rbp+nLengthNeeded]
0x18001c2cc  mov     r8, rsi; pvInfo
0x18001c2cf  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001c2d4  mov     edx, 2; nIndex
0x18001c2d9  mov     rcx, r12; hObj
0x18001c2dc  call    cs:__imp_GetUserObjectInformationW
0x18001c2e2  test    eax, eax
0x18001c2e4  jnz     short loc_18001C30F
0x18001c2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2ed  lea     rax, WPP_GLOBAL_Control
0x18001c2f4  cmp     rcx, rax
0x18001c2f7  jz      short loc_18001C339
0x18001c2f9  test    [rcx+1Ch], dil
0x18001c2fd  jz      short loc_18001C339
0x18001c2ff  call    cs:__imp_GetLastError
0x18001c305  mov     edx, 0Fh
0x18001c30a  jmp     loc_18001C119
0x18001c30f  lea     rdx, aWinsta0; "WinSta0"
0x18001c316  mov     rcx, rbx
0x18001c319  call    cs:__imp__o__wcsicmp
0x18001c31f  test    eax, eax
0x18001c321  jnz     short loc_18001C339
0x18001c323  lea     rdx, aDefault; "default"
0x18001c32a  mov     rcx, rsi
0x18001c32d  call    cs:__imp__o__wcsicmp
0x18001c333  test    eax, eax
0x18001c335  cmovz   r14d, edi
0x18001c339  test    rsi, rsi
0x18001c33c  jz      short loc_18001C350
0x18001c33e  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001c345  mov     r8, rsi; lpMem
0x18001c348  xor     edx, edx; dwFlags
0x18001c34a  call    cs:__imp_HeapFree
0x18001c350  test    rbx, rbx
0x18001c353  jz      short loc_18001C367
0x18001c355  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001c35c  mov     r8, rbx; lpMem
0x18001c35f  xor     edx, edx; dwFlags
0x18001c361  call    cs:__imp_HeapFree
0x18001c367  mov     eax, r14d
0x18001c36a  add     rsp, 30h
0x18001c36e  pop     r15
0x18001c370  pop     r14
0x18001c372  pop     r12
0x18001c374  pop     rdi
0x18001c375  pop     rsi
0x18001c376  pop     rbx
0x18001c377  pop     rbp
0x18001c378  retn
```
