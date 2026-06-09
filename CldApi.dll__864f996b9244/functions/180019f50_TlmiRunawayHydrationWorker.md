# TlmiRunawayHydrationWorker

- ea: `0x180019f50`
- end: `0x18001a397`
- name: `TlmiRunawayHydrationWorker`
- size: `1095`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800022ee`
- `0x1800196e4`
- `0x180019e70`
- `0x180019f50`
- `0x18001be5c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019fff`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019fff`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a04f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a04f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001a1e7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001a350`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001a1e7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001a350`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a210`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a284`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a323`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a363`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a210`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a284`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a323`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18001a363`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001a0c2`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001a0c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019f7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a1f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019f7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a1f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a1c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a0f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a109`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a0f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a1d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019fcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019fe7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019fcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019fe7`

## pseudocode

```c
__int64 __fastcall TlmiRunawayHydrationWorker(PVOID Parameter)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  _QWORD *v3; // rax
  const void **v4; // rdi
  _QWORD *inserted; // rbx
  unsigned int v6; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  LPVOID v9; // rax
  void *v10; // rsi
  void *v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  PVOID v18; // r15
  PVOID v19; // r14
  int v20; // r12d
  DWORD v21; // esi
  DWORD v22; // r13d
  PVOID v23; // rbx
  unsigned int v24; // edi
  char v25; // al
  _DWORD *i; // rax
  BOOLEAN v27; // dl
  DWORD v29; // [rsp+20h] [rbp-49h]
  __int64 v30; // [rsp+28h] [rbp-41h]
  __int128 v31; // [rsp+30h] [rbp-39h] BYREF
  int Buffer; // [rsp+40h] [rbp-29h] BYREF
  __int128 v33; // [rsp+48h] [rbp-21h]
  unsigned __int8 NewElement; // [rsp+D8h] [rbp+6Fh] BYREF
  int v35; // [rsp+E0h] [rbp+77h]
  DWORD TickCount; // [rsp+E8h] [rbp+7Fh]

  v30 = 0;
  v35 = 780000;
  TickCount = GetTickCount();
  v29 = TickCount;
  while ( byte_180028930 )
  {
    if ( NtCurrentPeb()->Ldr->ShutdownInProgress )
      break;
    *((_QWORD *)&v31 + 1) = &v31;
    *(_QWORD *)&v31 = &v31;
    if ( WaitForSingleObject(qword_180028A40, 0xFFFFFFFF) || WaitForSingleObject(qword_180028A48, 0xEA60u) != 258 )
      break;
    RtlAcquireSRWLockExclusive(&qword_1800289B8);
    if ( (__int128 *)xmmword_180028A30 != &xmmword_180028A30 )
    {
      v31 = xmmword_180028A30;
      *(_QWORD *)(xmmword_180028A30 + 8) = &v31;
      **((_QWORD **)&xmmword_180028A30 + 1) = &v31;
    }
    *((_QWORD *)&xmmword_180028A30 + 1) = &xmmword_180028A30;
    *(_QWORD *)&xmmword_180028A30 = &xmmword_180028A30;
    RtlReleaseSRWLockExclusive(&qword_1800289B8);
    while ( 1 )
    {
      v1 = (_QWORD *)v31;
      if ( (__int128 *)v31 == &v31 )
        break;
      memset_0(&Buffer, 0, 0x50u);
      NewElement = 0;
      v2 = *v1;
      if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v3 = (_QWORD *)v1[1], (_QWORD *)*v3 != v1) )
        __fastfail(3u);
      *v3 = v2;
      v4 = (const void **)(v1 - 3);
      *(_QWORD *)(v2 + 8) = v3;
      Buffer = *((_DWORD *)v1 - 5);
      v33 = *((_OWORD *)v1 - 1);
      inserted = RtlInsertElementGenericTableAvl(&stru_1800289C8, &Buffer, 0x50u, &NewElement);
      if ( inserted )
      {
        if ( !NewElement )
          goto LABEL_17;
        v6 = *((unsigned __int16 *)v4 + 5);
        ProcessHeap = GetProcessHeap();
        inserted[2] = HeapAlloc(ProcessHeap, 0, v6);
        v8 = GetProcessHeap();
        v9 = HeapAlloc(v8, 0, v6);
        v10 = (void *)inserted[2];
        inserted[4] = v9;
        if ( v10 )
        {
          if ( v9 )
          {
            memcpy_0(v10, v4[2], v6);
            v11 = (void *)inserted[4];
            *((_WORD *)inserted + 4) = *((_WORD *)v4 + 4);
            *((_WORD *)inserted + 5) = *((_WORD *)v4 + 5);
            memcpy_0(v11, v4[2], v6);
            v12 = inserted[4];
            *((_WORD *)inserted + 12) = *((_WORD *)v4 + 4);
            *((_WORD *)inserted + 13) = *((_WORD *)v4 + 5);
            TlmiRemoveUsername(v12);
LABEL_17:
            ++*((_DWORD *)inserted + 10);
            inserted[6] += v4[5];
            ++*((_DWORD *)inserted + 14);
            inserted[8] += v4[5];
            v13 = *((_DWORD *)inserted + 18);
            if ( v13 <= *(_DWORD *)v4 )
              v13 = *(_DWORD *)v4;
            *((_DWORD *)inserted + 18) = v13;
            goto LABEL_20;
          }
          v15 = GetProcessHeap();
          HeapFree(v15, 0, v10);
        }
        v16 = (void *)inserted[4];
        if ( v16 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v16);
        }
        RtlDeleteElementGenericTableAvl(&stru_1800289C8, &Buffer);
      }
LABEL_20:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
    }
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = GetTickCount();
    v22 = v21 - TickCount;
    v23 = RtlEnumerateGenericTableAvl(&stru_1800289C8, 1u);
    if ( v23 )
    {
      do
      {
        if ( *((int *)v23 + 10) > 50 || *((__int64 *)v23 + 6) > 786432000 )
          TlmiLogRunawayHydration(v23, 0, v21, 0);
        v24 = v35;
        *((_QWORD *)v23 + 6) = 0;
        *((_DWORD *)v23 + 10) = 0;
        if ( v22 > v24 )
        {
          if ( *((_DWORD *)v23 + 14) > v20 )
          {
            v20 = *((_DWORD *)v23 + 14);
            v18 = v23;
          }
          if ( *((_QWORD *)v23 + 8) > v30 )
          {
            v19 = v23;
            v30 = *((_QWORD *)v23 + 8);
          }
        }
        v23 = RtlEnumerateGenericTableAvl(&stru_1800289C8, 0);
      }
      while ( v23 );
      if ( v18 && v19 && (v24 == 780000 || v20 > 30 || v30 > 786432000) )
      {
        v25 = 1;
        goto LABEL_43;
      }
    }
    else
    {
      v24 = v35;
    }
    v25 = 0;
LABEL_43:
    if ( v22 > v24 )
    {
      if ( v25 )
      {
        TlmiLogRunawayHydration(v18, 1, v21, v24);
        if ( v18 != v19 )
          TlmiLogRunawayHydration(v19, 1, v21, v24);
      }
      TickCount = v21;
      v30 = 0;
      v35 = 4200000;
    }
    if ( v21 - v29 > 0x5265C0 )
    {
      for ( i = RtlEnumerateGenericTableAvl(&stru_1800289C8, 1u); i; i = RtlEnumerateGenericTableAvl(
                                                                           &stru_1800289C8,
                                                                           v27) )
      {
        if ( v21 - i[18] <= 0x5265C0 )
        {
          v27 = 0;
        }
        else
        {
          RtlDeleteElementGenericTableAvl(&stru_1800289C8, i);
          v27 = 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019f50  mov     [rsp-8+arg_0], rbx
0x180019f55  push    rbp
0x180019f56  push    rsi
0x180019f57  push    rdi
0x180019f58  push    r12
0x180019f5a  push    r13
0x180019f5c  push    r14
0x180019f5e  push    r15
0x180019f60  lea     rbp, [rsp-27h]
0x180019f65  sub     rsp, 90h
0x180019f6c  mov     edi, 0BE6E0h
0x180019f71  mov     [rbp+57h+var_98], 0
0x180019f79  mov     [rbp+57h+arg_10], edi
0x180019f7c  call    cs:__imp_GetTickCount
0x180019f82  mov     [rbp+57h+arg_18], eax
0x180019f85  mov     [rbp+57h+var_A0], eax
0x180019f88  lea     rbx, xmmword_180028A30
0x180019f8f  cmp     cs:byte_180028930, 0
0x180019f96  jz      loc_18001A37A
0x180019f9c  mov     rax, gs:60h
0x180019fa5  mov     rcx, [rax+18h]
0x180019fa9  cmp     byte ptr [rcx+48h], 0
0x180019fad  jnz     loc_18001A37A
0x180019fb3  mov     rcx, cs:qword_180028A40; hHandle
0x180019fba  lea     rax, [rbp+57h+var_90]
0x180019fbe  mov     qword ptr [rbp+57h+var_90+8], rax
0x180019fc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019fc5  lea     rax, [rbp+57h+var_90]
0x180019fc9  mov     qword ptr [rbp+57h+var_90], rax
0x180019fcd  call    cs:__imp_WaitForSingleObject
0x180019fd3  test    eax, eax
0x180019fd5  jnz     loc_18001A37A
0x180019fdb  mov     rcx, cs:qword_180028A48; hHandle
0x180019fe2  mov     edx, 0EA60h; dwMilliseconds
0x180019fe7  call    cs:__imp_WaitForSingleObject
0x180019fed  cmp     eax, 102h
0x180019ff2  jnz     loc_18001A37A
0x180019ff8  lea     rcx, qword_1800289B8
0x180019fff  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a005  mov     rax, qword ptr cs:xmmword_180028A30
0x18001a00c  lea     rcx, xmmword_180028A30
0x18001a013  cmp     rax, rcx
0x18001a016  jz      short loc_18001A03A
0x18001a018  movaps  xmm0, cs:xmmword_180028A30
0x18001a01f  lea     rcx, [rbp+57h+var_90]
0x18001a023  movdqu  [rbp+57h+var_90], xmm0
0x18001a028  mov     [rax+8], rcx
0x18001a02c  lea     rcx, [rbp+57h+var_90]
0x18001a030  mov     rax, qword ptr cs:xmmword_180028A30+8
0x18001a037  mov     [rax], rcx
0x18001a03a  lea     rcx, qword_1800289B8
0x18001a041  mov     qword ptr cs:xmmword_180028A30+8, rbx
0x18001a048  mov     qword ptr cs:xmmword_180028A30, rbx
0x18001a04f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a055  mov     rbx, qword ptr [rbp+57h+var_90]
0x18001a059  lea     rax, [rbp+57h+var_90]
0x18001a05d  cmp     rbx, rax
0x18001a060  jz      loc_18001A1EF
0x18001a066  xor     edx, edx; Val
0x18001a068  lea     rcx, [rbp+57h+Buffer]; void *
0x18001a06c  lea     r8d, [rdx+50h]; Size
0x18001a070  call    memset_0
0x18001a075  mov     [rbp+57h+NewElement], 0
0x18001a079  mov     rcx, [rbx]
0x18001a07c  cmp     [rcx+8], rbx
0x18001a080  jnz     loc_18001A373
0x18001a086  mov     rax, [rbx+8]
0x18001a08a  cmp     [rax], rbx
0x18001a08d  jnz     loc_18001A373
0x18001a093  mov     [rax], rcx
0x18001a096  lea     rdi, [rbx-18h]
0x18001a09a  mov     [rcx+8], rax
0x18001a09e  lea     r9, [rbp+57h+NewElement]; NewElement
0x18001a0a2  mov     eax, [rdi+4]
0x18001a0a5  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a0a9  mov     [rbp+57h+Buffer], eax
0x18001a0ac  lea     rcx, stru_1800289C8; Table
0x18001a0b3  movups  xmm0, xmmword ptr [rdi+8]
0x18001a0b7  mov     r8d, 50h ; 'P'; BufferSize
0x18001a0bd  movdqu  [rbp+57h+var_78], xmm0
0x18001a0c2  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18001a0c8  mov     rbx, rax
0x18001a0cb  test    rax, rax
0x18001a0ce  jz      loc_18001A192
0x18001a0d4  cmp     [rbp+57h+NewElement], 0
0x18001a0d8  jz      loc_18001A171
0x18001a0de  movzx   r14d, word ptr [rdi+0Ah]
0x18001a0e3  call    cs:__imp_GetProcessHeap
0x18001a0e9  mov     r8d, r14d; dwBytes
0x18001a0ec  xor     edx, edx; dwFlags
0x18001a0ee  mov     rcx, rax; hHeap
0x18001a0f1  call    cs:__imp_HeapAlloc
0x18001a0f7  mov     [rbx+10h], rax
0x18001a0fb  call    cs:__imp_GetProcessHeap
0x18001a101  mov     r8d, r14d; dwBytes
0x18001a104  xor     edx, edx; dwFlags
0x18001a106  mov     rcx, rax; hHeap
0x18001a109  call    cs:__imp_HeapAlloc
0x18001a10f  mov     rsi, [rbx+10h]
0x18001a113  mov     [rbx+20h], rax
0x18001a117  test    rsi, rsi
0x18001a11a  jz      loc_18001A1BF
0x18001a120  test    rax, rax
0x18001a123  jz      loc_18001A1AB
0x18001a129  mov     rdx, [rdi+10h]; Src
0x18001a12d  mov     r8d, r14d; Size
0x18001a130  mov     rcx, rsi; void *
0x18001a133  call    memcpy_0
0x18001a138  movzx   eax, word ptr [rdi+8]
0x18001a13c  mov     r8d, r14d; Size
0x18001a13f  mov     rcx, [rbx+20h]; void *
0x18001a143  mov     [rbx+8], ax
0x18001a147  movzx   eax, word ptr [rdi+0Ah]
0x18001a14b  mov     [rbx+0Ah], ax
0x18001a14f  mov     rdx, [rdi+10h]; Src
0x18001a153  call    memcpy_0
0x18001a158  movzx   edx, word ptr [rdi+8]
0x18001a15c  mov     rcx, [rbx+20h]
0x18001a160  mov     [rbx+18h], dx
0x18001a164  movzx   eax, word ptr [rdi+0Ah]
0x18001a168  mov     [rbx+1Ah], ax
0x18001a16c  call    TlmiRemoveUsername
0x18001a171  inc     dword ptr [rbx+28h]
0x18001a174  mov     rax, [rdi+28h]
0x18001a178  add     [rbx+30h], rax
0x18001a17c  inc     dword ptr [rbx+38h]
0x18001a17f  mov     rax, [rdi+28h]
0x18001a183  add     [rbx+40h], rax
0x18001a187  mov     eax, [rbx+48h]
0x18001a18a  cmp     eax, [rdi]
0x18001a18c  cmovbe  eax, [rdi]
0x18001a18f  mov     [rbx+48h], eax
0x18001a192  call    cs:__imp_GetProcessHeap
0x18001a198  mov     r8, rdi; lpMem
0x18001a19b  xor     edx, edx; dwFlags
0x18001a19d  mov     rcx, rax; hHeap
0x18001a1a0  call    cs:__imp_HeapFree
0x18001a1a6  jmp     loc_18001A055
0x18001a1ab  call    cs:__imp_GetProcessHeap
0x18001a1b1  mov     r8, rsi; lpMem
0x18001a1b4  xor     edx, edx; dwFlags
0x18001a1b6  mov     rcx, rax; hHeap
0x18001a1b9  call    cs:__imp_HeapFree
0x18001a1bf  mov     rbx, [rbx+20h]
0x18001a1c3  test    rbx, rbx
0x18001a1c6  jz      short loc_18001A1DC
0x18001a1c8  call    cs:__imp_GetProcessHeap
0x18001a1ce  mov     r8, rbx; lpMem
0x18001a1d1  xor     edx, edx; dwFlags
0x18001a1d3  mov     rcx, rax; hHeap
0x18001a1d6  call    cs:__imp_HeapFree
0x18001a1dc  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a1e0  lea     rcx, stru_1800289C8; Table
0x18001a1e7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001a1ed  jmp     short loc_18001A192
0x18001a1ef  xor     r15d, r15d
0x18001a1f2  xor     r14d, r14d
0x18001a1f5  xor     r12d, r12d
0x18001a1f8  call    cs:__imp_GetTickCount
0x18001a1fe  mov     dl, 1; Restart
0x18001a200  lea     rcx, stru_1800289C8; Table
0x18001a207  mov     r13d, eax
0x18001a20a  mov     esi, eax
0x18001a20c  sub     r13d, [rbp+57h+arg_18]
0x18001a210  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001a216  mov     rbx, rax
0x18001a219  test    rax, rax
0x18001a21c  jz      loc_18001A2B8
0x18001a222  cmp     dword ptr [rbx+28h], 32h ; '2'
0x18001a226  jg      short loc_18001A232
0x18001a228  cmp     qword ptr [rbx+30h], 2EE00000h
0x18001a230  jle     short loc_18001A242
0x18001a232  xor     edx, edx
0x18001a234  xor     r9d, r9d
0x18001a237  mov     r8d, esi
0x18001a23a  mov     rcx, rbx
0x18001a23d  call    TlmiLogRunawayHydration
0x18001a242  mov     edi, [rbp+57h+arg_10]
0x18001a245  mov     qword ptr [rbx+30h], 0
0x18001a24d  mov     dword ptr [rbx+28h], 0
0x18001a254  cmp     r13d, edi
0x18001a257  jbe     short loc_18001A27B
0x18001a259  cmp     [rbx+38h], r12d
0x18001a25d  jle     short loc_18001A266
0x18001a25f  mov     r12d, [rbx+38h]
0x18001a263  mov     r15, rbx
0x18001a266  mov     rax, [rbp+57h+var_98]
0x18001a26a  cmp     [rbx+40h], rax
0x18001a26e  jle     short loc_18001A27B
0x18001a270  mov     rax, [rbx+40h]
0x18001a274  mov     r14, rbx
0x18001a277  mov     [rbp+57h+var_98], rax
0x18001a27b  xor     edx, edx; Restart
0x18001a27d  lea     rcx, stru_1800289C8; Table
0x18001a284  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001a28a  mov     rbx, rax
0x18001a28d  test    rax, rax
0x18001a290  jnz     short loc_18001A222
0x18001a292  test    r15, r15
0x18001a295  jz      short loc_18001A2BB
0x18001a297  test    r14, r14
0x18001a29a  jz      short loc_18001A2BB
0x18001a29c  cmp     edi, 0BE6E0h
0x18001a2a2  jz      short loc_18001A2B4
0x18001a2a4  cmp     r12d, 1Eh
0x18001a2a8  jg      short loc_18001A2B4
0x18001a2aa  cmp     [rbp+57h+var_98], 2EE00000h
0x18001a2b2  jle     short loc_18001A2BB
0x18001a2b4  mov     al, 1
0x18001a2b6  jmp     short loc_18001A2BD
0x18001a2b8  mov     edi, [rbp+57h+arg_10]
0x18001a2bb  xor     al, al
0x18001a2bd  cmp     r13d, edi
0x18001a2c0  jbe     short loc_18001A303
0x18001a2c2  test    al, al
0x18001a2c4  jz      short loc_18001A2F1
0x18001a2c6  mov     edx, 1
0x18001a2cb  mov     r9d, edi
0x18001a2ce  mov     r8d, esi
0x18001a2d1  mov     rcx, r15
0x18001a2d4  call    TlmiLogRunawayHydration
0x18001a2d9  cmp     r15, r14
0x18001a2dc  jz      short loc_18001A2F1
0x18001a2de  mov     edx, 1
0x18001a2e3  mov     r9d, edi
0x18001a2e6  mov     r8d, esi
0x18001a2e9  mov     rcx, r14
0x18001a2ec  call    TlmiLogRunawayHydration
0x18001a2f1  mov     [rbp+57h+arg_18], esi
0x18001a2f4  mov     [rbp+57h+var_98], 0
0x18001a2fc  mov     [rbp+57h+arg_10], 401640h
0x18001a303  mov     eax, esi
0x18001a305  lea     rbx, xmmword_180028A30
0x18001a30c  sub     eax, [rbp+57h+var_A0]
0x18001a30f  cmp     eax, 5265C0h
0x18001a314  jbe     loc_180019F8F
0x18001a31a  mov     dl, 1; Restart
0x18001a31c  lea     rcx, stru_1800289C8; Table
0x18001a323  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001a329  lea     rbx, xmmword_180028A30
0x18001a330  test    rax, rax
0x18001a333  jz      loc_180019F8F
0x18001a339  mov     ecx, esi
0x18001a33b  sub     ecx, [rax+48h]
0x18001a33e  cmp     ecx, 5265C0h
0x18001a344  jbe     short loc_18001A35A
0x18001a346  mov     rdx, rax; Buffer
0x18001a349  lea     rcx, stru_1800289C8; Table
0x18001a350  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001a356  mov     dl, 1
0x18001a358  jmp     short loc_18001A35C
0x18001a35a  xor     dl, dl; Restart
0x18001a35c  lea     rcx, stru_1800289C8; Table
0x18001a363  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18001a369  test    rax, rax
0x18001a36c  jnz     short loc_18001A339
0x18001a36e  jmp     loc_180019F88
0x18001a373  mov     ecx, 3
0x18001a378  int     29h; Win8: RtlFailFast(ecx)
0x18001a37a  mov     rbx, [rsp+0C0h+arg_0]
0x18001a382  xor     eax, eax
0x18001a384  add     rsp, 90h
0x18001a38b  pop     r15
0x18001a38d  pop     r14
0x18001a38f  pop     r13
0x18001a391  pop     r12
0x18001a393  pop     rdi
0x18001a394  pop     rsi
0x18001a395  pop     rbp
0x18001a396  retn
```
