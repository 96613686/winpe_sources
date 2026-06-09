# StorageReserveTelemetry::Internal::SRProvider::HeapifyTopTen(StorageReserveTelemetry::Internal::SRProvider::PathMapPair * const,BUCL::Rtl::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>> &)

- ea: `0x18002821c`
- end: `0x18002848b`
- name: `?HeapifyTopTen@SRProvider@Internal@StorageReserveTelemetry@@CAXQEAUPathMapPair@123@AEAV?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@Rtl@BUCL@@@Z`
- size: `623`
- prototype: `int __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002c9c4`

## callees

- `0x18002821c`
- `0x18002ceac`
- `0x18002cf48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800282f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002832b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800282f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002832b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800282ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028339`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800282ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028339`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002841b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002841b`

## pseudocode

```c
int __fastcall StorageReserveTelemetry::Internal::SRProvider::HeapifyTopTen(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3)
{
  void **v3; // rsi
  void **v4; // rdi
  void **process_heap_string_nothrow; // rax
  void **v6; // r12
  __int64 v7; // rdi
  void **v8; // r13
  int v9; // r15d
  __int64 v10; // r14
  unsigned __int64 v11; // r8
  void *v12; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  int v19; // ecx
  void *v20; // rbx
  HANDLE v21; // rax
  void **v22; // r15
  DWORD v23; // ebx
  HANDLE v24; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-58h] BYREF
  int v29; // [rsp+28h] [rbp-50h]
  __int64 v30; // [rsp+30h] [rbp-48h]
  __int64 v31; // [rsp+38h] [rbp-40h]
  LPVOID v32; // [rsp+40h] [rbp-38h]
  LPVOID v33; // [rsp+48h] [rbp-30h] BYREF
  void *v34; // [rsp+50h] [rbp-28h]
  LPVOID v35[4]; // [rsp+58h] [rbp-20h] BYREF

  v35[1] = (LPVOID)-2LL;
  v31 = a2;
  v30 = a1;
  v3 = 0;
  v4 = *(void ***)(a2 + 8);
  process_heap_string_nothrow = &v4[4 * *(_QWORD *)(a2 + 24)];
  v6 = 0;
  while ( v4 < process_heap_string_nothrow )
  {
    if ( *v4 != v4 )
    {
LABEL_6:
      v6 = v4;
      v3 = (void **)*v4;
      break;
    }
    v4 += 4;
  }
  while ( 1 )
  {
    v7 = ((__int64)v4 - *(_QWORD *)(a2 + 8)) >> 5;
    while ( 2 )
    {
      if ( !v6 )
        return (int)process_heap_string_nothrow;
      v8 = 0;
      if ( v3 != v6 )
        v8 = v3;
      v9 = 0;
      while ( 1 )
      {
        v10 = a1 + 16LL * (unsigned int)v9;
        LODWORD(process_heap_string_nothrow) = *(_DWORD *)(v10 + 8);
        if ( !(_DWORD)process_heap_string_nothrow )
          break;
        if ( (unsigned int)process_heap_string_nothrow < *((_DWORD *)v8 + 16) )
        {
          wil::make_process_heap_string_nothrow((wil *)&lpMem, &qword_18003A1F8, a3);
          process_heap_string_nothrow = (void **)wil::make_process_heap_string_nothrow(
                                                   (wil *)&v33,
                                                   (const unsigned __int16 *)v8[7],
                                                   v11);
          v32 = process_heap_string_nothrow;
          if ( &lpMem == process_heap_string_nothrow )
          {
            v12 = lpMem;
          }
          else
          {
            v12 = *process_heap_string_nothrow;
            if ( lpMem )
            {
              LastError = GetLastError();
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, lpMem);
              SetLastError(LastError);
              process_heap_string_nothrow = (void **)v32;
            }
            lpMem = v12;
            *process_heap_string_nothrow = 0;
          }
          v15 = v33;
          if ( v33 )
          {
            v16 = GetProcessHeap();
            LODWORD(process_heap_string_nothrow) = HeapFree(v16, 0, v15);
          }
          if ( !v12 )
            return (int)process_heap_string_nothrow;
          v29 = *((_DWORD *)v8 + 16);
          v17 = v30;
          do
          {
            v18 = v17 + 16LL * v9;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
              &lpMem,
              v18);
            v19 = *(_DWORD *)(v18 + 8);
            LODWORD(process_heap_string_nothrow) = v29;
            *(_DWORD *)(v18 + 8) = v29;
            v29 = v19;
            ++v9;
          }
          while ( v9 < 10 );
          v20 = lpMem;
          if ( lpMem )
          {
            v21 = GetProcessHeap();
            LODWORD(process_heap_string_nothrow) = HeapFree(v21, 0, v20);
          }
          a1 = v17;
          goto LABEL_29;
        }
        if ( ++v9 >= 10 )
          goto LABEL_30;
      }
      process_heap_string_nothrow = (void **)wil::make_process_heap_string_nothrow(
                                               (wil *)v35,
                                               (const unsigned __int16 *)v8[7],
                                               a3);
      v22 = process_heap_string_nothrow;
      if ( (void **)v10 != process_heap_string_nothrow )
      {
        v34 = *process_heap_string_nothrow;
        v32 = *(LPVOID *)v10;
        if ( v32 )
        {
          v23 = GetLastError();
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v32);
          SetLastError(v23);
        }
        LODWORD(process_heap_string_nothrow) = (_DWORD)v34;
        *(_QWORD *)v10 = v34;
        *v22 = 0;
      }
      v25 = v35[0];
      if ( v35[0] )
      {
        v26 = GetProcessHeap();
        LODWORD(process_heap_string_nothrow) = HeapFree(v26, 0, v25);
      }
      if ( !*(_QWORD *)v10 )
        return (int)process_heap_string_nothrow;
      LODWORD(process_heap_string_nothrow) = *((_DWORD *)v8 + 16);
      *(_DWORD *)(v10 + 8) = (_DWORD)process_heap_string_nothrow;
      a1 = v30;
LABEL_29:
      a2 = v31;
LABEL_30:
      v3 = (void **)*v3;
      if ( v3 )
      {
        if ( v3 != v6 )
          continue;
        v3 = 0;
      }
      break;
    }
    v6 = 0;
    v4 = (void **)(*(_QWORD *)(a2 + 8) + 32 * (v7 + 1));
    process_heap_string_nothrow = (void **)(*(_QWORD *)(a2 + 8) + 32LL * *(_QWORD *)(a2 + 24));
    while ( v4 < process_heap_string_nothrow )
    {
      if ( *v4 != v4 )
        goto LABEL_6;
      v4 += 4;
    }
  }
}

```

## disassembly

```asm
0x18002821c  push    rbp
0x18002821e  push    rbx
0x18002821f  push    rsi
0x180028220  push    rdi
0x180028221  push    r12
0x180028223  push    r13
0x180028225  push    r14
0x180028227  push    r15
0x180028229  mov     rbp, rsp
0x18002822c  sub     rsp, 78h
0x180028230  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180028238  mov     [rbp+var_40], rdx
0x18002823c  mov     [rbp+var_48], rcx
0x180028240  xor     esi, esi
0x180028242  mov     rdi, [rdx+8]
0x180028246  mov     rax, [rdx+18h]
0x18002824a  shl     rax, 5
0x18002824e  add     rax, rdi
0x180028251  xor     r12d, r12d
0x180028254  jmp     short loc_18002825F
0x180028256  cmp     [rdi], rdi
0x180028259  jnz     short loc_180028266
0x18002825b  add     rdi, 20h ; ' '
0x18002825f  cmp     rdi, rax
0x180028262  jb      short loc_180028256
0x180028264  jmp     short loc_18002826C
0x180028266  mov     r12, rdi
0x180028269  mov     rsi, [rdi]
0x18002826c  sub     rdi, [rdx+8]
0x180028270  sar     rdi, 5
0x180028274  test    r12, r12
0x180028277  jz      loc_18002847A
0x18002827d  xor     r13d, r13d
0x180028280  cmp     rsi, r12
0x180028283  cmovnz  r13, rsi
0x180028287  xor     r15d, r15d
0x18002828a  mov     r14d, r15d
0x18002828d  shl     r14, 4
0x180028291  add     r14, rcx
0x180028294  mov     eax, [r14+8]
0x180028298  test    eax, eax
0x18002829a  jz      loc_1800283D4
0x1800282a0  cmp     eax, [r13+40h]
0x1800282a4  jb      short loc_1800282B4
0x1800282a6  inc     r15d
0x1800282a9  cmp     r15d, 0Ah
0x1800282ad  jl      short loc_18002828A
0x1800282af  jmp     loc_1800283A2
0x1800282b4  lea     rdx, qword_18003A1F8; unsigned __int16 *
0x1800282bb  lea     rcx, [rbp+lpMem]; this
0x1800282bf  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x1800282c4  mov     rdx, [r13+38h]; unsigned __int16 *
0x1800282c8  lea     rcx, [rbp+var_30]; this
0x1800282cc  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x1800282d1  mov     [rbp+var_38], rax
0x1800282d5  lea     rcx, [rbp+lpMem]
0x1800282d9  cmp     rcx, rax
0x1800282dc  jz      short loc_18002831E
0x1800282de  mov     r14, [rax]
0x1800282e1  cmp     [rbp+lpMem], 0
0x1800282e6  jz      short loc_180028311
0x1800282e8  call    cs:__imp_GetLastError
0x1800282ee  mov     ebx, eax
0x1800282f0  call    cs:__imp_GetProcessHeap
0x1800282f6  mov     rcx, rax; hHeap
0x1800282f9  mov     r8, [rbp+lpMem]; lpMem
0x1800282fd  xor     edx, edx; dwFlags
0x1800282ff  call    cs:__imp_HeapFree
0x180028305  mov     ecx, ebx; dwErrCode
0x180028307  call    cs:__imp_SetLastError
0x18002830d  mov     rax, [rbp+var_38]
0x180028311  mov     [rbp+lpMem], r14
0x180028315  mov     qword ptr [rax], 0
0x18002831c  jmp     short loc_180028322
0x18002831e  mov     r14, [rbp+lpMem]
0x180028322  mov     rbx, [rbp+var_30]
0x180028326  test    rbx, rbx
0x180028329  jz      short loc_18002833F
0x18002832b  call    cs:__imp_GetProcessHeap
0x180028331  mov     rcx, rax; hHeap
0x180028334  mov     r8, rbx; lpMem
0x180028337  xor     edx, edx; dwFlags
0x180028339  call    cs:__imp_HeapFree
0x18002833f  test    r14, r14
0x180028342  jz      loc_18002847A
0x180028348  mov     eax, [r13+40h]
0x18002834c  mov     [rbp+var_50], eax
0x18002834f  mov     r14, [rbp+var_48]
0x180028353  movsxd  rbx, r15d
0x180028356  shl     rbx, 4
0x18002835a  add     rbx, r14
0x18002835d  mov     rdx, rbx
0x180028360  lea     rcx, [rbp+lpMem]
0x180028364  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180028369  mov     ecx, [rbx+8]
0x18002836c  mov     eax, [rbp+var_50]
0x18002836f  mov     [rbx+8], eax
0x180028372  mov     [rbp+var_50], ecx
0x180028375  inc     r15d
0x180028378  cmp     r15d, 0Ah
0x18002837c  jl      short loc_180028353
0x18002837e  mov     rbx, [rbp+lpMem]
0x180028382  test    rbx, rbx
0x180028385  jz      short loc_18002839B
0x180028387  call    cs:__imp_GetProcessHeap
0x18002838d  mov     rcx, rax; hHeap
0x180028390  mov     r8, rbx; lpMem
0x180028393  xor     edx, edx; dwFlags
0x180028395  call    cs:__imp_HeapFree
0x18002839b  mov     rcx, r14
0x18002839e  mov     rdx, [rbp+var_40]
0x1800283a2  mov     rsi, [rsi]
0x1800283a5  test    rsi, rsi
0x1800283a8  jz      short loc_1800283B5
0x1800283aa  cmp     rsi, r12
0x1800283ad  jnz     loc_180028274
0x1800283b3  xor     esi, esi
0x1800283b5  xor     r12d, r12d
0x1800283b8  inc     rdi
0x1800283bb  shl     rdi, 5
0x1800283bf  add     rdi, [rdx+8]
0x1800283c3  mov     rax, [rdx+18h]
0x1800283c7  shl     rax, 5
0x1800283cb  add     rax, [rdx+8]
0x1800283cf  jmp     loc_180028470
0x1800283d4  mov     rdx, [r13+38h]; unsigned __int16 *
0x1800283d8  lea     rcx, [rbp+var_20]; this
0x1800283dc  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x1800283e1  mov     r15, rax
0x1800283e4  cmp     r14, rax
0x1800283e7  jz      short loc_18002842F
0x1800283e9  mov     rax, [rax]
0x1800283ec  mov     [rbp+var_28], rax
0x1800283f0  mov     rax, [r14]
0x1800283f3  mov     [rbp+var_38], rax
0x1800283f7  test    rax, rax
0x1800283fa  jz      short loc_180028421
0x1800283fc  call    cs:__imp_GetLastError
0x180028402  mov     ebx, eax
0x180028404  call    cs:__imp_GetProcessHeap
0x18002840a  mov     rcx, rax; hHeap
0x18002840d  mov     r8, [rbp+var_38]; lpMem
0x180028411  xor     edx, edx; dwFlags
0x180028413  call    cs:__imp_HeapFree
0x180028419  mov     ecx, ebx; dwErrCode
0x18002841b  call    cs:__imp_SetLastError
0x180028421  mov     rax, [rbp+var_28]
0x180028425  mov     [r14], rax
0x180028428  mov     qword ptr [r15], 0
0x18002842f  mov     rbx, [rbp+var_20]
0x180028433  test    rbx, rbx
0x180028436  jz      short loc_18002844C
0x180028438  call    cs:__imp_GetProcessHeap
0x18002843e  mov     rcx, rax; hHeap
0x180028441  mov     r8, rbx; lpMem
0x180028444  xor     edx, edx; dwFlags
0x180028446  call    cs:__imp_HeapFree
0x18002844c  cmp     qword ptr [r14], 0
0x180028450  jz      short loc_18002847A
0x180028452  mov     eax, [r13+40h]
0x180028456  mov     [r14+8], eax
0x18002845a  mov     rcx, [rbp+var_48]
0x18002845e  jmp     loc_18002839E
0x180028463  cmp     [rdi], rdi
0x180028466  jnz     loc_180028266
0x18002846c  add     rdi, 20h ; ' '
0x180028470  cmp     rdi, rax
0x180028473  jb      short loc_180028463
0x180028475  jmp     loc_18002826C
0x18002847a  add     rsp, 78h
0x18002847e  pop     r15
0x180028480  pop     r14
0x180028482  pop     r13
0x180028484  pop     r12
0x180028486  pop     rdi
0x180028487  pop     rsi
0x180028488  pop     rbx
0x180028489  pop     rbp
0x18002848a  retn
```
