# ShaderCache_CreateImpl

- ea: `0x18001f410`
- end: `0x18001f977`
- name: `ShaderCache_CreateImpl`
- size: `1383`
- prototype: `__int64 __fastcall(int *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001f360`

## callees

- `0x18001f410`
- `0x18001fa30`
- `0x18003c2cc`
- `0x18003d734`
- `0x18003f0bc`
- `0x180042f8c`
- `0x1800445b4`
- `0x1800445d4`
- `0x1800449f0`
- `0x180047ba0`
- `0x180051aec`
- `0x1800a6cd8`
- `0x1800a6d08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f70f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f70f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f5c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f6b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f71d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f5c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f6b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f71d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f454`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f862`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f454`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f862`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001f462`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001f462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f895`

## pseudocode

```c
__int64 __fastcall ShaderCache_CreateImpl(int *a1, _QWORD *a2)
{
  __int128 v3; // xmm6
  int v4; // ebx
  unsigned int v5; // r13d
  int v6; // edi
  __int64 v7; // rsi
  int v8; // eax
  bool v9; // r10
  int v11; // eax
  int v12; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // r15
  unsigned __int64 v17; // r14
  void *v18; // rax
  size_t v19; // r14
  SIZE_T v20; // r13
  LARGE_INTEGER v21; // rdx
  char *v22; // r13
  HANDLE v23; // rax
  LPVOID v24; // rax
  size_t v25; // r14
  _QWORD *v26; // rax
  HANDLE v27; // rax
  __int64 v28; // r8
  __int64 v29; // rcx
  double v30; // xmm6_8
  int v31; // [rsp+40h] [rbp-348h] BYREF
  int v32; // [rsp+48h] [rbp-340h]
  unsigned int v33; // [rsp+50h] [rbp-338h] BYREF
  LARGE_INTEGER v34; // [rsp+58h] [rbp-330h] BYREF
  int v35; // [rsp+60h] [rbp-328h]
  int v36; // [rsp+64h] [rbp-324h]
  int v37; // [rsp+68h] [rbp-320h]
  void *Src; // [rsp+70h] [rbp-318h]
  _QWORD *v39; // [rsp+78h] [rbp-310h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp-308h] BYREF
  LARGE_INTEGER Frequency; // [rsp+88h] [rbp-300h] BYREF
  __int128 v42; // [rsp+90h] [rbp-2F8h]
  _BYTE pExceptionObject[24]; // [rsp+A8h] [rbp-2E0h] BYREF
  _BYTE v44[24]; // [rsp+C0h] [rbp-2C8h] BYREF
  _BYTE v45[24]; // [rsp+D8h] [rbp-2B0h] BYREF
  _BYTE v46[16]; // [rsp+F0h] [rbp-298h] BYREF
  LARGE_INTEGER *v47; // [rsp+100h] [rbp-288h]
  __int64 v48; // [rsp+108h] [rbp-280h]
  int *v49; // [rsp+110h] [rbp-278h]
  __int64 v50; // [rsp+118h] [rbp-270h]
  unsigned int *v51; // [rsp+120h] [rbp-268h]
  __int64 v52; // [rsp+128h] [rbp-260h]
  _BYTE v53[528]; // [rsp+130h] [rbp-258h] BYREF

  v39 = a2;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v33 = *a1;
  v3 = *(_OWORD *)(a1 + 1);
  v31 = a1[5];
  v4 = a1[8];
  v32 = a1[9];
  v5 = v32;
  v6 = a1[10];
  v35 = a1[11];
  v36 = a1[12];
  v37 = a1[13];
  v7 = *((_QWORD *)a1 + 7);
  v8 = IsAppContainerPresent();
  v9 = v8 != 0;
  if ( v32 == 4 )
  {
    if ( !v8 )
    {
      v5 = 0;
      v32 = 0;
      goto LABEL_12;
    }
    v5 = 1;
    v32 = 1;
  }
  else if ( v32 != 1 )
  {
    goto LABEL_12;
  }
  if ( (*a1 & 1) == 0 )
  {
    if ( (unsigned int)(a1[8] - 2) <= 2 )
      goto LABEL_10;
    return 2147942487LL;
  }
  if ( a1[8] != 3 )
    return 2147942487LL;
LABEL_10:
  if ( (*a1 & 0x401) == 0x400 )
    return 2147942487LL;
LABEL_12:
  v11 = v35;
  if ( !v35 )
    v11 = 128;
  v35 = v11;
  v12 = v36;
  if ( !v36 )
    v12 = 0x10000;
  v36 = v12;
  v13 = v37;
  if ( !v37 )
    v13 = 16;
  v37 = v13;
  v42 = v3;
  if ( (int)GetStoragePath(v9, v5, v33, v53) < 0 )
  {
    Src = (void *)&qword_1800ACF70;
    if ( v5 == 1 )
      v5 = 0;
    v32 = v5;
  }
  else
  {
    Src = v53;
  }
  ProcessHeap = GetProcessHeap();
  v15 = HeapAlloc(ProcessHeap, 0, 0x368u);
  v16 = v15;
  if ( !v15 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_QWORD *)&v42 = v15;
  *(_OWORD *)v15 = 0;
  v15[2] = 0;
  v15[3] = 0;
  v17 = -1;
  v18 = Src;
  do
    ++v17;
  while ( *((_WORD *)Src + v17) );
  v34.QuadPart = 0x7FFFFFFFFFFFFFFELL;
  if ( v17 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v17 > 7 )
  {
    if ( (v17 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v21.QuadPart = v17 | 7;
      if ( (v17 | 7) < 0xA )
        v21.QuadPart = 10;
      v34 = v21;
      if ( (unsigned __int64)(v21.QuadPart + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v20 = 2 * (v21.QuadPart + 1);
      if ( !v20 )
      {
        v22 = 0;
LABEL_42:
        *v16 = v22;
        v16[2] = v17;
        v16[3] = v21.QuadPart;
        v25 = 2 * v17;
        memcpy_0(v22, v18, v25);
        *(_WORD *)&v22[v25] = 0;
        v5 = v32;
        goto LABEL_43;
      }
    }
    else
    {
      v20 = -2;
    }
    if ( v20 < 0x1000 )
    {
      v27 = GetProcessHeap();
      v22 = (char *)HeapAlloc(v27, 0, v20);
      if ( !v22 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v45);
        throw (std::bad_alloc *)v45;
      }
    }
    else
    {
      if ( v20 + 39 < v20 )
        std::_Throw_bad_array_new_length();
      v23 = GetProcessHeap();
      v24 = HeapAlloc(v23, 0, v20 + 39);
      if ( !v24 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v44);
        throw (std::bad_alloc *)v44;
      }
      v22 = (char *)(((unsigned __int64)v24 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v22 - 1) = v24;
    }
    v21 = v34;
    v18 = Src;
    goto LABEL_42;
  }
  v16[2] = v17;
  v16[3] = 7;
  v19 = 2 * v17;
  memcpy_0(v16, v18, v19);
  *(_WORD *)((char *)v16 + v19) = 0;
LABEL_43:
  if ( v16[3] <= 7u )
    v26 = v16;
  else
    v26 = (_QWORD *)*v16;
  *((_DWORD *)v16 + 8) = v33;
  *(_OWORD *)((char *)v16 + 36) = v3;
  *((_DWORD *)v16 + 13) = v31;
  v16[7] = v26;
  *((_DWORD *)v16 + 16) = v4;
  *((_DWORD *)v16 + 17) = v5;
  *((_DWORD *)v16 + 18) = v6;
  *((_DWORD *)v16 + 19) = v35;
  *((_DWORD *)v16 + 20) = v36;
  *((_DWORD *)v16 + 21) = v37;
  v16[11] = v7;
  HierarchicalCache::HierarchicalCache((HierarchicalCache *)(v16 + 14), (struct ShaderCacheDesc *)(v16 + 4));
  Smtx_lock_exclusive(&qword_1800C74A8);
  v29 = qword_1800C74B0;
  if ( *(__int64 **)(qword_1800C74B0 + 8) != &qword_1800C74B0 )
    __fastfail(3u);
  v16[12] = qword_1800C74B0;
  v16[13] = &qword_1800C74B0;
  *(_QWORD *)(v29 + 8) = v16 + 12;
  qword_1800C74B0 = (__int64)(v16 + 12);
  if ( (Microsoft_Windows_Direct3DShaderCacheEnableBits & 1) != 0 )
  {
    v33 = *((_DWORD *)v16 + 8);
    v31 = *((_DWORD *)v16 + 17);
    v34.QuadPart = (LONGLONG)v16;
    v47 = &v34;
    v48 = 8;
    v49 = &v31;
    v50 = 4;
    v51 = &v33;
    v52 = 4;
    McGenEventWrite_EventWriteTransfer(v29, EventCreateShaderCache, v28, 4, v46);
  }
  Smtx_unlock_exclusive(&qword_1800C74A8);
  v34.QuadPart = 0;
  QueryPerformanceCounter(&v34);
  v30 = (double)(v34.LowPart - PerformanceCount.LowPart) / (double)(int)Frequency.LowPart;
  EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 34));
  *((double *)v16 + 32) = v30 * 1000.0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 34));
  *v39 = v16;
  return 0;
}

```

## disassembly

```asm
0x18001f410  mov     [rsp+arg_10], rbx
0x18001f415  mov     [rsp+arg_18], rsi
0x18001f41a  push    rdi
0x18001f41b  push    r12
0x18001f41d  push    r13
0x18001f41f  push    r14
0x18001f421  push    r15
0x18001f423  sub     rsp, 360h
0x18001f42a  movaps  [rsp+388h+var_38], xmm6
0x18001f432  mov     rax, cs:__security_cookie
0x18001f439  xor     rax, rsp
0x18001f43c  mov     [rsp+388h+var_48], rax
0x18001f444  mov     [rsp+388h+var_310], rdx
0x18001f449  mov     r14, rcx
0x18001f44c  lea     rcx, [rsp+388h+PerformanceCount]; lpPerformanceCount
0x18001f454  call    cs:__imp_QueryPerformanceCounter
0x18001f45a  lea     rcx, [rsp+388h+Frequency]; lpFrequency
0x18001f462  call    cs:__imp_QueryPerformanceFrequency
0x18001f468  mov     eax, [r14]
0x18001f46b  mov     [rsp+388h+var_338], eax
0x18001f46f  movups  xmm6, xmmword ptr [r14+4]
0x18001f474  mov     eax, [r14+14h]
0x18001f478  mov     [rsp+388h+var_348], eax
0x18001f47c  mov     r15, [r14+18h]
0x18001f480  mov     ebx, [r14+20h]
0x18001f484  mov     r13d, [r14+24h]
0x18001f488  mov     [rsp+388h+var_340], r13d
0x18001f48d  mov     edi, [r14+28h]
0x18001f491  mov     eax, [r14+2Ch]
0x18001f495  mov     [rsp+388h+var_328], eax
0x18001f499  mov     ecx, [r14+30h]
0x18001f49d  mov     [rsp+388h+var_324], ecx
0x18001f4a1  mov     eax, [r14+34h]
0x18001f4a5  mov     [rsp+388h+var_320], eax
0x18001f4a9  mov     rsi, [r14+38h]
0x18001f4ad  call    ?IsAppContainerPresent@@YAHXZ; IsAppContainerPresent(void)
0x18001f4b2  test    eax, eax
0x18001f4b4  setnz   r10b
0x18001f4b8  cmp     r13d, 4
0x18001f4bc  jnz     short loc_18001F4DC
0x18001f4be  test    eax, eax
0x18001f4c0  jz      short loc_18001F4CF
0x18001f4c2  mov     r13d, 1
0x18001f4c8  mov     [rsp+388h+var_340], r13d
0x18001f4cd  jmp     short loc_18001F4E2
0x18001f4cf  xor     r12d, r12d
0x18001f4d2  mov     r13d, r12d
0x18001f4d5  mov     [rsp+388h+var_340], r12d
0x18001f4da  jmp     short loc_18001F51A
0x18001f4dc  cmp     r13d, 1
0x18001f4e0  jnz     short loc_18001F517
0x18001f4e2  mov     ecx, [r14]
0x18001f4e5  test    cl, 1
0x18001f4e8  jz      short loc_18001F4F3
0x18001f4ea  cmp     dword ptr [r14+20h], 3
0x18001f4ef  jnz     short loc_18001F50D
0x18001f4f1  jmp     short loc_18001F4FF
0x18001f4f3  mov     eax, [r14+20h]
0x18001f4f7  sub     eax, 2
0x18001f4fa  cmp     eax, 2
0x18001f4fd  ja      short loc_18001F50D
0x18001f4ff  and     ecx, 401h
0x18001f505  cmp     ecx, 400h
0x18001f50b  jnz     short loc_18001F517
0x18001f50d  mov     eax, 80070057h
0x18001f512  jmp     loc_18001F8D0
0x18001f517  xor     r12d, r12d
0x18001f51a  mov     ecx, 80h
0x18001f51f  mov     eax, [rsp+388h+var_328]
0x18001f523  test    eax, eax
0x18001f525  cmovz   eax, ecx
0x18001f528  mov     [rsp+388h+var_328], eax
0x18001f52c  mov     ecx, 10000h
0x18001f531  mov     eax, [rsp+388h+var_324]
0x18001f535  test    eax, eax
0x18001f537  cmovz   eax, ecx
0x18001f53a  mov     [rsp+388h+var_324], eax
0x18001f53e  mov     ecx, 10h
0x18001f543  mov     eax, [rsp+388h+var_320]
0x18001f547  test    eax, eax
0x18001f549  cmovz   eax, ecx
0x18001f54c  mov     [rsp+388h+var_320], eax
0x18001f550  movaps  [rsp+388h+var_2F8], xmm6
0x18001f558  mov     [rsp+388h+var_358], r15
0x18001f55d  lea     rax, [rsp+388h+var_2F8]
0x18001f565  mov     [rsp+388h+var_360], rax
0x18001f56a  lea     r9, [rsp+388h+var_258]
0x18001f572  mov     r8d, [rsp+388h+var_338]
0x18001f577  mov     edx, r13d
0x18001f57a  movzx   ecx, r10b
0x18001f57e  call    ?GetStoragePath@@YAJ_NW4ShaderCacheDiskMode@@W4ShaderCacheCreateFlags@@PEAGIU_GUID@@PEBG@Z; GetStoragePath(bool,ShaderCacheDiskMode,ShaderCacheCreateFlags,ushort *,uint,_GUID,ushort const *)
0x18001f583  test    eax, eax
0x18001f585  js      short loc_18001F596
0x18001f587  lea     r14, [rsp+388h+var_258]
0x18001f58f  mov     [rsp+388h+Src], r14
0x18001f594  jmp     short loc_18001F5AF
0x18001f596  lea     rax, qword_1800ACF70
0x18001f59d  mov     [rsp+388h+Src], rax
0x18001f5a2  cmp     r13d, 1
0x18001f5a6  cmovz   r13d, r12d
0x18001f5aa  mov     [rsp+388h+var_340], r13d
0x18001f5af  call    cs:__imp_GetProcessHeap
0x18001f5b5  mov     rcx, rax; hHeap
0x18001f5b8  xor     edx, edx; dwFlags
0x18001f5ba  mov     r8d, 368h; dwBytes
0x18001f5c0  call    cs:__imp_HeapAlloc
0x18001f5c6  mov     r15, rax
0x18001f5c9  test    rax, rax
0x18001f5cc  jz      loc_18001F902
0x18001f5d2  mov     qword ptr [rsp+388h+var_2F8], r15
0x18001f5da  xorps   xmm0, xmm0
0x18001f5dd  movups  xmmword ptr [rax], xmm0
0x18001f5e0  mov     [rax+10h], r12
0x18001f5e4  mov     [rax+18h], r12
0x18001f5e8  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001f5ef  mov     rax, [rsp+388h+Src]
0x18001f5f4  inc     r14
0x18001f5f7  cmp     word ptr [rax+r14*2], 0
0x18001f5fd  jnz     short loc_18001F5F4
0x18001f5ff  mov     rdx, 7FFFFFFFFFFFFFFEh
0x18001f609  mov     qword ptr [rsp+388h+var_330], rdx
0x18001f60e  cmp     r14, rdx
0x18001f611  ja      loc_18001F924
0x18001f617  cmp     r14, 7
0x18001f61b  ja      short loc_18001F644
0x18001f61d  mov     [r15+10h], r14
0x18001f621  mov     qword ptr [r15+18h], 7
0x18001f629  add     r14, r14
0x18001f62c  mov     r8, r14; Size
0x18001f62f  mov     rdx, rax; Src
0x18001f632  mov     rcx, r15; void *
0x18001f635  call    memcpy_0
0x18001f63a  mov     [r14+r15], r12w
0x18001f63f  jmp     loc_18001F703
0x18001f644  mov     rcx, r14
0x18001f647  or      rcx, 7
0x18001f64b  cmp     rcx, rdx
0x18001f64e  jbe     short loc_18001F673
0x18001f650  mov     r13, 0FFFFFFFFFFFFFFFEh
0x18001f657  cmp     r13, 1000h
0x18001f65e  jb      loc_18001F70F
0x18001f664  lea     rax, [r13+27h]
0x18001f668  cmp     rax, r13
0x18001f66b  jbe     loc_18001F929
0x18001f671  jmp     short loc_18001F6A9
0x18001f673  mov     rdx, rcx
0x18001f676  mov     r8d, 0Ah
0x18001f67c  cmp     rcx, r8
0x18001f67f  cmovb   rdx, r8
0x18001f683  mov     qword ptr [rsp+388h+var_330], rdx
0x18001f688  lea     r13, [rdx+1]
0x18001f68c  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18001f696  cmp     r13, rcx
0x18001f699  ja      loc_18001F92E
0x18001f69f  add     r13, r13
0x18001f6a2  jnz     short loc_18001F657
0x18001f6a4  mov     r13, r12
0x18001f6a7  jmp     short loc_18001F6DD
0x18001f6a9  call    cs:__imp_GetProcessHeap
0x18001f6af  mov     rcx, rax; hHeap
0x18001f6b2  lea     r8, [r13+27h]; dwBytes
0x18001f6b6  xor     edx, edx; dwFlags
0x18001f6b8  call    cs:__imp_HeapAlloc
0x18001f6be  test    rax, rax
0x18001f6c1  jz      loc_18001F933
0x18001f6c7  lea     r13, [rax+27h]
0x18001f6cb  and     r13, 0FFFFFFFFFFFFFFE0h
0x18001f6cf  mov     [r13-8], rax
0x18001f6d3  mov     rdx, qword ptr [rsp+388h+var_330]
0x18001f6d8  mov     rax, [rsp+388h+Src]
0x18001f6dd  mov     [r15], r13
0x18001f6e0  mov     [r15+10h], r14
0x18001f6e4  mov     [r15+18h], rdx
0x18001f6e8  add     r14, r14
0x18001f6eb  mov     r8, r14; Size
0x18001f6ee  mov     rdx, rax; Src
0x18001f6f1  mov     rcx, r13; void *
0x18001f6f4  call    memcpy_0
0x18001f6f9  mov     [r14+r13], r12w
0x18001f6fe  mov     r13d, [rsp+388h+var_340]
0x18001f703  cmp     qword ptr [r15+18h], 7
0x18001f708  jbe     short loc_18001F731
0x18001f70a  mov     rax, [r15]
0x18001f70d  jmp     short loc_18001F734
0x18001f70f  call    cs:__imp_GetProcessHeap
0x18001f715  mov     rcx, rax; hHeap
0x18001f718  mov     r8, r13; dwBytes
0x18001f71b  xor     edx, edx; dwFlags
0x18001f71d  call    cs:__imp_HeapAlloc
0x18001f723  mov     r13, rax
0x18001f726  test    rax, rax
0x18001f729  jz      loc_18001F954
0x18001f72f  jmp     short loc_18001F6D3
0x18001f731  mov     rax, r15
0x18001f734  mov     ecx, [rsp+388h+var_338]
0x18001f738  mov     [r15+20h], ecx
0x18001f73c  movups  xmmword ptr [r15+24h], xmm6
0x18001f741  mov     ecx, [rsp+388h+var_348]
0x18001f745  mov     [r15+34h], ecx
0x18001f749  mov     [r15+38h], rax
0x18001f74d  mov     [r15+40h], ebx
0x18001f751  mov     [r15+44h], r13d
0x18001f755  mov     [r15+48h], edi
0x18001f759  mov     eax, [rsp+388h+var_328]
0x18001f75d  mov     [r15+4Ch], eax
0x18001f761  mov     ecx, [rsp+388h+var_324]
0x18001f765  mov     [r15+50h], ecx
0x18001f769  mov     eax, [rsp+388h+var_320]
0x18001f76d  mov     [r15+54h], eax
0x18001f771  mov     [r15+58h], rsi
0x18001f775  lea     rdx, [r15+20h]; struct ShaderCacheDesc *
0x18001f779  lea     rcx, [r15+70h]; this
0x18001f77d  call    ??0HierarchicalCache@@QEAA@AEAUShaderCacheDesc@@@Z; HierarchicalCache::HierarchicalCache(ShaderCacheDesc &)
0x18001f782  lea     rcx, qword_1800C74A8; _Smtx_t *
0x18001f789  call    _Smtx_lock_exclusive
0x18001f78e  mov     rcx, cs:qword_1800C74B0
0x18001f795  lea     rdx, qword_1800C74B0
0x18001f79c  cmp     [rcx+8], rdx
0x18001f7a0  jz      short loc_18001F7A9
0x18001f7a2  mov     ecx, 3
0x18001f7a7  int     29h; Win8: RtlFailFast(ecx)
0x18001f7a9  lea     rax, [r15+60h]
0x18001f7ad  mov     [rax], rcx
0x18001f7b0  mov     [rax+8], rdx
0x18001f7b4  mov     [rcx+8], rax
0x18001f7b8  mov     cs:qword_1800C74B0, rax
0x18001f7bf  test    byte ptr cs:Microsoft_Windows_Direct3DShaderCacheEnableBits, 1
0x18001f7c6  jz      loc_18001F84B
0x18001f7cc  mov     eax, [r15+20h]
0x18001f7d0  mov     [rsp+388h+var_338], eax
0x18001f7d4  mov     eax, [r15+44h]
0x18001f7d8  mov     [rsp+388h+var_348], eax
0x18001f7dc  mov     qword ptr [rsp+388h+var_330], r15
0x18001f7e1  lea     rax, [rsp+388h+var_330]
0x18001f7e6  mov     [rsp+388h+var_288], rax
0x18001f7ee  mov     [rsp+388h+var_280], 8
0x18001f7fa  lea     rax, [rsp+388h+var_348]
0x18001f7ff  mov     [rsp+388h+var_278], rax
0x18001f807  mov     [rsp+388h+var_270], 4
0x18001f813  lea     rax, [rsp+388h+var_338]
0x18001f818  mov     [rsp+388h+var_268], rax
0x18001f820  mov     [rsp+388h+var_260], 4
0x18001f82c  lea     rax, [rsp+388h+var_298]
0x18001f834  mov     [rsp+388h+var_368], rax
0x18001f839  mov     r9d, 4
0x18001f83f  lea     rdx, EventCreateShaderCache
0x18001f846  call    McGenEventWrite_EventWriteTransfer
0x18001f84b  lea     rcx, qword_1800C74A8; _Smtx_t *
0x18001f852  call    _Smtx_unlock_exclusive
0x18001f857  nop
0x18001f858  mov     qword ptr [rsp+388h+var_330], r12
0x18001f85d  lea     rcx, [rsp+388h+var_330]; lpPerformanceCount
0x18001f862  call    cs:__imp_QueryPerformanceCounter
0x18001f868  mov     rax, qword ptr [rsp+388h+var_330]
0x18001f86d  sub     rax, qword ptr [rsp+388h+PerformanceCount]
0x18001f875  xorps   xmm6, xmm6
0x18001f878  cvtsi2sd xmm6, rax
0x18001f87d  xorps   xmm0, xmm0
0x18001f880  cvtsi2sd xmm0, qword ptr [rsp+388h+Frequency]
0x18001f88a  divsd   xmm6, xmm0
0x18001f88e  lea     rcx, [r15+110h]; lpCriticalSection
0x18001f895  call    cs:__imp_EnterCriticalSection
0x18001f89b  mulsd   xmm6, cs:__real@408f400000000000
0x18001f8a3  movsd   qword ptr [r15+100h], xmm6
0x18001f8ac  lea     rcx, [r15+110h]; lpCriticalSection
0x18001f8b3  call    cs:__imp_LeaveCriticalSection
0x18001f8b9  mov     rax, [rsp+388h+var_310]
0x18001f8be  mov     [rax], r15
0x18001f8c1  xor     eax, eax
0x18001f8c3  jmp     short loc_18001F8D0
0x18001f8c5  mov     eax, 8007000Eh
0x18001f8ca  jmp     short loc_18001F8D0
0x18001f8cc  mov     eax, [rsp+388h+var_348]
0x18001f8d0  mov     rcx, [rsp+388h+var_48]
0x18001f8d8  xor     rcx, rsp; StackCookie
0x18001f8db  call    __security_check_cookie
0x18001f8e0  lea     r11, [rsp+388h+var_28]
0x18001f8e8  mov     rbx, [r11+40h]
0x18001f8ec  mov     rsi, [r11+48h]
0x18001f8f0  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f8f5  mov     rsp, r11
0x18001f8f8  pop     r15
0x18001f8fa  pop     r14
0x18001f8fc  pop     r13
0x18001f8fe  pop     r12
0x18001f900  pop     rdi
0x18001f901  retn
0x18001f902  lea     rcx, [rsp+388h+pExceptionObject]; this
0x18001f90a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001f90f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001f916  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
0x18001f91e  call    _CxxThrowException_0
0x18001f924  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001f929  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18001f92e  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18001f933  lea     rcx, [rsp+388h+var_2C8]; this
0x18001f93b  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001f940  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001f947  lea     rcx, [rsp+388h+var_2C8]; pExceptionObject
0x18001f94f  call    _CxxThrowException_0
  ... truncated ...
```
