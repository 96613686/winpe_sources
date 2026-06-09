# CModule::DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18004f354`
- end: `0x18004f6d7`
- name: `?DllMain@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `899`
- prototype: `int(CModule *__hidden this, HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004f2b8`

## callees

- `0x18004f354`
- `0x18004f874`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f459`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f4ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f459`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f4ca`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18004f415`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18004f415`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f3e3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f606`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f3e3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f606`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f42c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f42c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f41b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f61c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f65e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f6af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f41b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f61c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f65e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f6af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f646`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f646`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f62d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f66f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f6c0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f62d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f66f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004f6c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004f53c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004f53c`

## pseudocode

```c
__int64 __fastcall CModule::DllMain(CModule *this, HINSTANCE a2, int a3, void *a4)
{
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *i; // rbx
  HANDLE v9; // rax
  WCHAR *v10; // rdi
  unsigned int v11; // ebp
  DWORD ModuleFileNameW; // eax
  DWORD v13; // ecx
  bool v14; // zf
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // r14
  DWORD v18; // ebx
  DWORD v19; // eax
  DWORD v20; // ecx
  __int64 v21; // rcx
  int j; // eax
  unsigned int v23; // ebx
  WCHAR *v24; // r14
  UINT v25; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // r9d
  unsigned int v30; // r8d
  HANDLE v31; // rax
  WCHAR *v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  WCHAR *v35; // rax
  HANDLE v36; // rax
  WCHAR *v37; // rax
  DWORD flOldProtect; // [rsp+70h] [rbp+18h] BYREF

  if ( !a3 )
  {
    if ( !a4 )
    {
      v6 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
      for ( i = (_QWORD *)qword_180339940; i != (_QWORD *)qword_180339948; ++i )
        VirtualFree((LPVOID)(*i & 0xFFFFFFFFFFFF0000uLL), 0, 0x8000u);
      if ( g_TableAndSize )
        VirtualFree((LPVOID)((unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL), 0, 0x8000u);
    }
    return 1;
  }
  if ( a3 != 1 )
    return 1;
  DeviceConfiguration::CheckDeveloperModeEnabledState((DeviceConfiguration *)&qword_180339978);
  flOldProtect = 0;
  VirtualProtect(&g_TableAndSize, 8u, 2u, &flOldProtect);
  v9 = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(v9, 0, 0x208u);
  if ( !v10 )
    return 0;
  v11 = 260;
  while ( 1 )
  {
    if ( v11 >= 2 )
    {
      ModuleFileNameW = GetModuleFileNameW(0, v10, v11 - 2);
      v13 = ModuleFileNameW;
      LODWORD(qword_180339B18) = ModuleFileNameW;
      if ( ModuleFileNameW != v11 - 2 )
        break;
    }
    v11 += 260;
    v36 = GetProcessHeap();
    v37 = (WCHAR *)HeapReAlloc(v36, 0, v10, 2LL * v11);
    if ( !v37 )
    {
LABEL_39:
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v10);
      return 0;
    }
    v10 = v37;
  }
  if ( ModuleFileNameW )
  {
    do
    {
      if ( v10[v13] == 92 )
        break;
      v14 = v13-- == 1;
      LODWORD(qword_180339B18) = v13;
    }
    while ( !v14 );
  }
  v15 = v13 + 1;
  LODWORD(qword_180339B18) = v15;
  v10[v15] = 0;
  v16 = qword_180339B18 + 1;
  LODWORD(qword_180339B18) = qword_180339B18 + 1;
  while ( 1 )
  {
    if ( v11 - v16 >= 2 )
    {
      v17 = v16;
      v18 = v11 - v16 - 2;
      v19 = GetModuleFileNameW(a2, &v10[v16], v18);
      v20 = v19;
      HIDWORD(qword_180339B18) = v19;
      if ( v19 != v18 )
        break;
    }
    v11 += 260;
    v34 = GetProcessHeap();
    v35 = (WCHAR *)HeapReAlloc(v34, 0, v10, 2LL * v11);
    if ( !v35 )
      goto LABEL_39;
    v10 = v35;
    v16 = qword_180339B18;
  }
  if ( v19 )
  {
    do
    {
      if ( v10[v17 + v20] == 92 )
        break;
      v14 = v20-- == 1;
      HIDWORD(qword_180339B18) = v20;
    }
    while ( !v14 );
  }
  v21 = v20 + 1;
  HIDWORD(qword_180339B18) = v21;
  v10[v17 + v21] = 0;
  for ( j = ++HIDWORD(qword_180339B18); ; j = HIDWORD(qword_180339B18) )
  {
    v23 = v11 - j - qword_180339B18;
    if ( v23 >= 2 )
    {
      v24 = &v10[(unsigned int)(qword_180339B18 + j)];
      v25 = v23 - 2;
      SystemDirectoryW = GetSystemDirectoryW(v24, v25);
      LODWORD(qword_180339B20) = SystemDirectoryW;
      if ( SystemDirectoryW < v25 )
        break;
    }
    v11 += 260;
    v31 = GetProcessHeap();
    v32 = (WCHAR *)HeapReAlloc(v31, 0, v10, 2LL * v11);
    if ( !v32 )
      goto LABEL_39;
    v10 = v32;
  }
  if ( v24[SystemDirectoryW] || SystemDirectoryW <= 1 )
  {
    *v24 = 0;
    LODWORD(qword_180339B20) = 1;
    v29 = 1;
  }
  else
  {
    v27 = SystemDirectoryW - 1;
    LODWORD(qword_180339B20) = SystemDirectoryW - 1;
    if ( v24[v27] != 92 )
    {
      LODWORD(qword_180339B20) = SystemDirectoryW;
      v24[SystemDirectoryW] = 92;
      LODWORD(v27) = qword_180339B20;
    }
    v28 = (unsigned int)(v27 + 1);
    LODWORD(qword_180339B20) = v28;
    v24[v28] = 0;
    LODWORD(qword_180339B20) = qword_180339B20 + 1;
    v29 = qword_180339B20;
  }
  lpMem = v10;
  *(&lpMem + 1) = &v10[(unsigned int)qword_180339B18];
  v30 = HIDWORD(qword_180339B18);
  qword_180339B10 = (__int64)&v10[(unsigned int)qword_180339B18 + (unsigned __int64)HIDWORD(qword_180339B18)];
  if ( (unsigned int)qword_180339B18 >= HIDWORD(qword_180339B18) )
    v30 = qword_180339B18;
  if ( v30 < v29 )
    v30 = v29;
  HIDWORD(qword_180339B20) = v30;
  return 1;
}

```

## disassembly

```asm
0x18004f354  mov     [rsp+arg_8], rbx
0x18004f359  push    rbp
0x18004f35a  push    rsi
0x18004f35b  push    rdi
0x18004f35c  push    r12
0x18004f35e  push    r13
0x18004f360  push    r14
0x18004f362  push    r15
0x18004f364  sub     rsp, 20h
0x18004f368  mov     r15, rdx
0x18004f36b  xor     r12d, r12d
0x18004f36e  test    r8d, r8d
0x18004f371  jz      short loc_18004F393
0x18004f373  cmp     r8d, 1
0x18004f377  jz      short loc_18004F3EF
0x18004f379  mov     eax, 1
0x18004f37e  mov     rbx, [rsp+58h+arg_8]
0x18004f383  add     rsp, 20h
0x18004f387  pop     r15
0x18004f389  pop     r14
0x18004f38b  pop     r13
0x18004f38d  pop     r12
0x18004f38f  pop     rdi
0x18004f390  pop     rsi
0x18004f391  pop     rbp
0x18004f392  retn
0x18004f393  test    r9, r9
0x18004f396  jnz     short loc_18004F379
0x18004f398  mov     rbx, qword ptr cs:lpMem
0x18004f39f  test    rbx, rbx
0x18004f3a2  jz      short loc_18004F3B8
0x18004f3a4  call    cs:__imp_GetProcessHeap
0x18004f3aa  mov     r8, rbx; lpMem
0x18004f3ad  xor     edx, edx; dwFlags
0x18004f3af  mov     rcx, rax; hHeap
0x18004f3b2  call    cs:__imp_HeapFree
0x18004f3b8  mov     rbx, cs:qword_180339940
0x18004f3bf  mov     rdi, 0FFFFFFFFFFFF0000h
0x18004f3c6  mov     esi, 8000h
0x18004f3cb  cmp     rbx, cs:qword_180339948
0x18004f3d2  jz      loc_18004F5EE
0x18004f3d8  mov     rcx, [rbx]
0x18004f3db  and     rcx, rdi; lpAddress
0x18004f3de  mov     r8d, esi; dwFreeType
0x18004f3e1  xor     edx, edx; dwSize
0x18004f3e3  call    cs:__imp_VirtualFree
0x18004f3e9  add     rbx, 8
0x18004f3ed  jmp     short loc_18004F3CB
0x18004f3ef  lea     rcx, qword_180339978; this
0x18004f3f6  call    ?CheckDeveloperModeEnabledState@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::CheckDeveloperModeEnabledState(void)
0x18004f3fb  mov     [rsp+58h+flOldProtect], r12d
0x18004f400  lea     r9, [rsp+58h+flOldProtect]; lpflOldProtect
0x18004f405  mov     edx, 8; dwSize
0x18004f40a  lea     r8d, [rdx-6]; flNewProtect
0x18004f40e  lea     rcx, ?g_TableAndSize@@3_KA; lpAddress
0x18004f415  call    cs:__imp_VirtualProtect
0x18004f41b  call    cs:__imp_GetProcessHeap
0x18004f421  mov     rcx, rax; hHeap
0x18004f424  xor     edx, edx; dwFlags
0x18004f426  mov     r8d, 208h; dwBytes
0x18004f42c  call    cs:__imp_HeapAlloc
0x18004f432  mov     rdi, rax
0x18004f435  test    rax, rax
0x18004f438  jz      loc_18004F64C
0x18004f43e  mov     esi, 104h
0x18004f443  mov     ebp, esi
0x18004f445  cmp     ebp, 2
0x18004f448  jb      loc_18004F6A8
0x18004f44e  lea     ebx, [rbp-2]
0x18004f451  mov     r8d, ebx; nSize
0x18004f454  mov     rdx, rdi; lpFilename
0x18004f457  xor     ecx, ecx; hModule
0x18004f459  call    cs:__imp_GetModuleFileNameW
0x18004f45f  mov     ecx, eax
0x18004f461  mov     dword ptr cs:qword_180339B18, eax
0x18004f467  cmp     eax, ebx
0x18004f469  jz      loc_18004F6A8
0x18004f46f  mov     r13d, 5Ch ; '\'
0x18004f475  test    eax, eax
0x18004f477  jz      short loc_18004F48D
0x18004f479  mov     eax, ecx
0x18004f47b  cmp     [rdi+rax*2], r13w
0x18004f480  jz      short loc_18004F48D
0x18004f482  add     ecx, 0FFFFFFFFh
0x18004f485  mov     dword ptr cs:qword_180339B18, ecx
0x18004f48b  jnz     short loc_18004F479
0x18004f48d  mov     esi, 1
0x18004f492  add     ecx, esi
0x18004f494  mov     dword ptr cs:qword_180339B18, ecx
0x18004f49a  mov     [rdi+rcx*2], r12w
0x18004f49f  mov     eax, dword ptr cs:qword_180339B18
0x18004f4a5  add     eax, esi
0x18004f4a7  mov     dword ptr cs:qword_180339B18, eax
0x18004f4ad  mov     ebx, ebp
0x18004f4af  sub     ebx, eax
0x18004f4b1  cmp     ebx, 2
0x18004f4b4  jb      loc_18004F653
0x18004f4ba  mov     r14d, eax
0x18004f4bd  add     ebx, 0FFFFFFFEh
0x18004f4c0  lea     rdx, [rdi+r14*2]; lpFilename
0x18004f4c4  mov     r8d, ebx; nSize
0x18004f4c7  mov     rcx, r15; hModule
0x18004f4ca  call    cs:__imp_GetModuleFileNameW
0x18004f4d0  mov     ecx, eax
0x18004f4d2  mov     dword ptr cs:qword_180339B18+4, eax
0x18004f4d8  cmp     eax, ebx
0x18004f4da  jz      loc_18004F653
0x18004f4e0  test    eax, eax
0x18004f4e2  jz      short loc_18004F4FB
0x18004f4e4  mov     eax, ecx
0x18004f4e6  add     rax, r14
0x18004f4e9  cmp     [rdi+rax*2], r13w
0x18004f4ee  jz      short loc_18004F4FB
0x18004f4f0  add     ecx, 0FFFFFFFFh
0x18004f4f3  mov     dword ptr cs:qword_180339B18+4, ecx
0x18004f4f9  jnz     short loc_18004F4E4
0x18004f4fb  add     ecx, esi
0x18004f4fd  mov     dword ptr cs:qword_180339B18+4, ecx
0x18004f503  add     rcx, r14
0x18004f506  mov     [rdi+rcx*2], r12w
0x18004f50b  mov     eax, dword ptr cs:qword_180339B18+4
0x18004f511  add     eax, esi
0x18004f513  mov     dword ptr cs:qword_180339B18+4, eax
0x18004f519  mov     ebx, ebp
0x18004f51b  sub     ebx, eax
0x18004f51d  mov     ecx, dword ptr cs:qword_180339B18
0x18004f523  sub     ebx, ecx
0x18004f525  cmp     ebx, 2
0x18004f528  jb      loc_18004F611
0x18004f52e  add     eax, ecx
0x18004f530  lea     r14, [rdi+rax*2]
0x18004f534  add     ebx, 0FFFFFFFEh
0x18004f537  mov     edx, ebx; uSize
0x18004f539  mov     rcx, r14; lpBuffer
0x18004f53c  call    cs:__imp_GetSystemDirectoryW
0x18004f542  mov     edx, eax
0x18004f544  mov     dword ptr cs:qword_180339B20, edx
0x18004f54a  cmp     eax, ebx
0x18004f54c  jnb     loc_18004F611
0x18004f552  cmp     [r14+rdx*2], r12w
0x18004f557  jnz     loc_18004F696
0x18004f55d  cmp     edx, esi
0x18004f55f  jbe     loc_18004F696
0x18004f565  lea     ecx, [rdx-1]
0x18004f568  mov     dword ptr cs:qword_180339B20, ecx
0x18004f56e  cmp     [r14+rcx*2], r13w
0x18004f573  jz      short loc_18004F586
0x18004f575  mov     dword ptr cs:qword_180339B20, edx
0x18004f57b  mov     [r14+rdx*2], r13w
0x18004f580  mov     ecx, dword ptr cs:qword_180339B20
0x18004f586  add     ecx, esi
0x18004f588  mov     dword ptr cs:qword_180339B20, ecx
0x18004f58e  mov     [r14+rcx*2], r12w
0x18004f593  mov     eax, dword ptr cs:qword_180339B20
0x18004f599  add     eax, esi
0x18004f59b  mov     dword ptr cs:qword_180339B20, eax
0x18004f5a1  mov     r9d, eax
0x18004f5a4  mov     qword ptr cs:lpMem, rdi
0x18004f5ab  mov     edx, dword ptr cs:qword_180339B18
0x18004f5b1  lea     rax, [rdi+rdx*2]
0x18004f5b5  mov     qword ptr cs:lpMem+8, rax
0x18004f5bc  mov     r8d, dword ptr cs:qword_180339B18+4
0x18004f5c3  lea     rcx, [rdx+r8]
0x18004f5c7  lea     rcx, [rdi+rcx*2]
0x18004f5cb  mov     cs:qword_180339B10, rcx
0x18004f5d2  cmp     edx, r8d
0x18004f5d5  cmovnb  r8d, edx
0x18004f5d9  cmp     r8d, r9d
0x18004f5dc  cmovb   r8d, r9d
0x18004f5e0  mov     dword ptr cs:qword_180339B20+4, r8d
0x18004f5e7  mov     eax, esi
0x18004f5e9  jmp     loc_18004F37E
0x18004f5ee  mov     rcx, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x18004f5f5  test    rcx, rcx
0x18004f5f8  jz      loc_18004F379
0x18004f5fe  and     rcx, rdi; lpAddress
0x18004f601  mov     r8d, esi; dwFreeType
0x18004f604  xor     edx, edx; dwSize
0x18004f606  call    cs:__imp_VirtualFree
0x18004f60c  jmp     loc_18004F379
0x18004f611  add     ebp, 104h
0x18004f617  mov     ebx, ebp
0x18004f619  add     rbx, rbx
0x18004f61c  call    cs:__imp_GetProcessHeap
0x18004f622  mov     rcx, rax; hHeap
0x18004f625  mov     r9, rbx; dwBytes
0x18004f628  mov     r8, rdi; lpMem
0x18004f62b  xor     edx, edx; dwFlags
0x18004f62d  call    cs:__imp_HeapReAlloc
0x18004f633  test    rax, rax
0x18004f636  jnz     short loc_18004F688
0x18004f638  call    cs:__imp_GetProcessHeap
0x18004f63e  mov     rcx, rax; hHeap
0x18004f641  mov     r8, rdi; lpMem
0x18004f644  xor     edx, edx; dwFlags
0x18004f646  call    cs:__imp_HeapFree
0x18004f64c  xor     eax, eax
0x18004f64e  jmp     loc_18004F37E
0x18004f653  add     ebp, 104h
0x18004f659  mov     ebx, ebp
0x18004f65b  add     rbx, rbx
0x18004f65e  call    cs:__imp_GetProcessHeap
0x18004f664  mov     rcx, rax; hHeap
0x18004f667  mov     r9, rbx; dwBytes
0x18004f66a  mov     r8, rdi; lpMem
0x18004f66d  xor     edx, edx; dwFlags
0x18004f66f  call    cs:__imp_HeapReAlloc
0x18004f675  test    rax, rax
0x18004f678  jz      short loc_18004F638
0x18004f67a  mov     rdi, rax
0x18004f67d  mov     eax, dword ptr cs:qword_180339B18
0x18004f683  jmp     loc_18004F4AD
0x18004f688  mov     rdi, rax
0x18004f68b  mov     eax, dword ptr cs:qword_180339B18+4
0x18004f691  jmp     loc_18004F519
0x18004f696  mov     [r14], r12w
0x18004f69a  mov     dword ptr cs:qword_180339B20, esi
0x18004f6a0  mov     r9d, esi
0x18004f6a3  jmp     loc_18004F5A4
0x18004f6a8  add     ebp, esi
0x18004f6aa  mov     ebx, ebp
0x18004f6ac  add     rbx, rbx
0x18004f6af  call    cs:__imp_GetProcessHeap
0x18004f6b5  mov     rcx, rax; hHeap
0x18004f6b8  mov     r9, rbx; dwBytes
0x18004f6bb  mov     r8, rdi; lpMem
0x18004f6be  xor     edx, edx; dwFlags
0x18004f6c0  call    cs:__imp_HeapReAlloc
0x18004f6c6  test    rax, rax
0x18004f6c9  jz      loc_18004F638
0x18004f6cf  mov     rdi, rax
0x18004f6d2  jmp     loc_18004F445
```
