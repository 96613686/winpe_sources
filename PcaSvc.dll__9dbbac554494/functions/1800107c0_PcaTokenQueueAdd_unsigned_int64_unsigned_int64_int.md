# PcaTokenQueueAdd(unsigned __int64,unsigned __int64 *,int)

- ea: `0x1800107c0`
- end: `0x180010b14`
- name: `?PcaTokenQueueAdd@@YAK_KPEA_KH@Z`
- size: `852`
- prototype: `__int64 __fastcall(char *, unsigned __int64 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180007720`
- `0x180010688`

## callees

- `0x18000eda0`
- `0x1800107c0`
- `0x180012920`
- `0x180056262`
- `0x18007a9cf`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180010a2f`
- `ntdll!RtlReAllocateHeap` at `0x180010a4a`
- `ntdll!RtlReAllocateHeap` at `0x180010a2f`
- `ntdll!RtlReAllocateHeap` at `0x180010a4a`
- `ntdll!RtlAllocateHeap` at `0x18001096c`
- `ntdll!RtlAllocateHeap` at `0x1800109fd`
- `ntdll!RtlAllocateHeap` at `0x18001096c`
- `ntdll!RtlAllocateHeap` at `0x1800109fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001084a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001084a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010af6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800108c8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800108c8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800108f9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800108f9`

## string_xrefs

- `0x180010836`: `PcaTokenQueueAdd`
- `0x180010829`: `Failed to add token to queue [%d]`
- `0x180010ae4`: `Failed to delete token process one timer [%d]`
- `0x180010b00`: `Failed to create token queue timer [%d]`

## pseudocode

```c
__int64 __fastcall PcaTokenQueueAdd(char *a1, unsigned __int64 *a2, int a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 *v8; // r14
  char *v9; // rcx
  char *v10; // rbx
  unsigned int v11; // ebx
  unsigned __int64 *v13; // r15
  void *v14; // rdx
  unsigned __int64 v15; // r14
  unsigned __int128 v16; // rax
  size_t v17; // rbp
  void *v18; // r8
  void *v19; // rcx
  PVOID v20; // rax
  PVOID v21; // rsi
  unsigned __int64 v22; // rbx
  __int64 v23; // rsi
  unsigned __int64 v24; // rsi
  unsigned __int128 v25; // rax
  size_t v26; // rbp
  void *v27; // r8
  void *v28; // rcx
  PVOID v29; // rax
  PVOID Heap; // rbx
  unsigned __int64 v31; // rax
  DWORD LastError; // eax
  __int64 DueTime; // [rsp+20h] [rbp-68h]

  if ( a1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)a1);
    v6 = *((_QWORD *)a1 + 7);
    v7 = *((_QWORD *)a1 + 8);
    if ( v6 )
    {
      if ( v6 < v7 )
      {
        v8 = (unsigned __int64 *)(a1 + 48);
LABEL_5:
        if ( is_mul_ok(*v8, 0)
          && (v9 = (char *)*((_QWORD *)a1 + 10), v10 = v9, (v31 = *v8, is_mul_ok(*v8, 1u)) && &v9[v31] >= v9) )
        {
          if ( is_mul_ok(*((_QWORD *)a1 + 7), *v8) )
          {
            memmove_0(&v9[v31], v9, *((_QWORD *)a1 + 7) * *v8);
            *(_QWORD *)v10 = *a2;
            ++*((_QWORD *)a1 + 7);
            goto LABEL_15;
          }
          v11 = -2147483637;
        }
        else
        {
          v11 = -1073741675;
        }
        goto LABEL_8;
      }
      v22 = v6 + 1;
      if ( v22 > v7 )
      {
        v23 = *((_QWORD *)a1 + 9) - 1LL;
        if ( v23 + v22 >= v22 )
        {
          v8 = (unsigned __int64 *)(a1 + 48);
          if ( is_mul_ok(v7, *((_QWORD *)a1 + 6)) )
          {
            v24 = (v23 + v22) & ~v23;
            v25 = v24 * (unsigned __int128)*v8;
            v26 = v24 * *v8;
            if ( is_mul_ok(v24, *v8) )
            {
              v27 = (void *)*((_QWORD *)a1 + 10);
              v28 = (void *)*((_QWORD *)a1 + 5);
              if ( v27 )
              {
                Heap = RtlReAllocateHeap(v28, DWORD2(v25), v27, v24 * *v8);
              }
              else
              {
                v29 = RtlAllocateHeap(v28, DWORD2(v25), v24 * *v8);
                Heap = v29;
                if ( v29 )
                  memset_0(v29, 0, v26);
              }
              if ( Heap )
              {
                *((_QWORD *)a1 + 10) = Heap;
                *((_QWORD *)a1 + 8) = v24;
                goto LABEL_5;
              }
              goto LABEL_44;
            }
          }
        }
        goto LABEL_13;
      }
      v11 = -1073741811;
    }
    else
    {
      if ( v7 )
      {
        v13 = (unsigned __int64 *)(a1 + 48);
      }
      else
      {
        if ( !*((_QWORD *)a1 + 9) )
          goto LABEL_13;
        v13 = (unsigned __int64 *)(a1 + 48);
        if ( !is_mul_ok(0, *((_QWORD *)a1 + 6)) )
          goto LABEL_13;
        v15 = *((_QWORD *)a1 + 9) & ~(*((_QWORD *)a1 + 9) - 1LL);
        v16 = v15 * (unsigned __int128)*v13;
        v17 = v15 * *v13;
        if ( !is_mul_ok(v15, *v13) )
          goto LABEL_13;
        v18 = (void *)*((_QWORD *)a1 + 10);
        v19 = (void *)*((_QWORD *)a1 + 5);
        if ( v18 )
        {
          v21 = RtlReAllocateHeap(v19, DWORD2(v16), v18, v15 * *v13);
        }
        else
        {
          v20 = RtlAllocateHeap(v19, DWORD2(v16), v15 * *v13);
          v21 = v20;
          if ( v20 )
            memset_0(v20, 0, v17);
        }
        if ( !v21 )
        {
LABEL_44:
          v11 = -1073741801;
          goto LABEL_14;
        }
        *((_QWORD *)a1 + 10) = v21;
        *((_QWORD *)a1 + 8) = v15;
      }
      if ( !is_mul_ok(*v13, 0) )
      {
LABEL_13:
        v11 = -1073741675;
        goto LABEL_14;
      }
      v11 = 0;
      **((_QWORD **)a1 + 10) = *a2;
      ++*((_QWORD *)a1 + 7);
    }
LABEL_14:
    if ( !v11 )
    {
LABEL_15:
      *a2 = 0;
      if ( a3 )
        PcapProcessOneTimerCallback(a1, 0);
      if ( *((_QWORD *)a1 + 7) && !*((_DWORD *)a1 + 28) )
      {
        v14 = (void *)*((_QWORD *)a1 + 13);
        if ( v14 )
        {
          if ( !DeleteTimerQueueTimer(0, v14, 0) )
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( LastError != 997 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"PcaTokenQueueAdd",
                406,
                (unsigned int)"Failed to delete token process one timer [%d]",
                LastError);
              goto LABEL_9;
            }
          }
          *((_QWORD *)a1 + 13) = 0;
        }
        if ( !CreateTimerQueueTimer((PHANDLE)a1 + 13, 0, PcapProcessOneTimerCallback, a1, 0x1F4u, 0x1F4u, 0) )
        {
          LODWORD(DueTime) = GetLastError();
          v11 = DueTime;
          AslLogCallPrintf(
            1,
            (unsigned int)"PcaTokenQueueAdd",
            422,
            (unsigned int)"Failed to create token queue timer [%d]",
            DueTime);
          goto LABEL_9;
        }
        *((_DWORD *)a1 + 28) = 1;
      }
      v11 = 0;
LABEL_9:
      LeaveCriticalSection((LPCRITICAL_SECTION)a1);
      return v11;
    }
LABEL_8:
    AslLogCallPrintf(1, (unsigned int)"PcaTokenQueueAdd", 358, (unsigned int)"Failed to add token to queue [%d]", v11);
    goto LABEL_9;
  }
  return 13;
}

```

## disassembly

```asm
0x1800107c0  push    rbx
0x1800107c2  push    rbp
0x1800107c3  push    rsi
0x1800107c4  push    rdi
0x1800107c5  push    r12
0x1800107c7  push    r13
0x1800107c9  push    r14
0x1800107cb  push    r15
0x1800107cd  sub     rsp, 48h
0x1800107d1  xor     ebp, ebp
0x1800107d3  mov     r13d, r8d
0x1800107d6  mov     r12, rdx
0x1800107d9  mov     rdi, rcx
0x1800107dc  test    rcx, rcx
0x1800107df  jz      loc_180010AA7
0x1800107e5  call    cs:__imp_EnterCriticalSection
0x1800107eb  mov     rbx, [rdi+38h]
0x1800107ef  mov     rcx, [rdi+40h]
0x1800107f3  test    rbx, rbx
0x1800107f6  jz      short loc_180010863
0x1800107f8  cmp     rbx, rcx
0x1800107fb  jnb     loc_1800109A6
0x180010801  lea     r14, [rdi+30h]
0x180010805  xor     eax, eax
0x180010807  mul     qword ptr [r14]
0x18001080a  test    rdx, rdx
0x18001080d  jnz     short loc_180010820
0x18001080f  mov     rcx, [rdi+50h]
0x180010813  lea     rbx, [rcx+rax]
0x180010817  cmp     rbx, rcx
0x18001081a  jnb     loc_180010A55
0x180010820  mov     ebx, 0C0000095h
0x180010825  mov     dword ptr [rsp+88h+DueTime], ebx
0x180010829  lea     r9, aFailedToAddTok; "Failed to add token to queue [%d]"
0x180010830  mov     r8d, 166h
0x180010836  lea     rdx, aPcatokenqueuea; "PcaTokenQueueAdd"
0x18001083d  mov     ecx, 1
0x180010842  call    AslLogCallPrintf
0x180010847  mov     rcx, rdi; lpCriticalSection
0x18001084a  call    cs:__imp_LeaveCriticalSection
0x180010850  mov     eax, ebx
0x180010852  add     rsp, 48h
0x180010856  pop     r15
0x180010858  pop     r14
0x18001085a  pop     r13
0x18001085c  pop     r12
0x18001085e  pop     rdi
0x18001085f  pop     rsi
0x180010860  pop     rbp
0x180010861  pop     rbx
0x180010862  retn
0x180010863  cmp     rbx, rcx
0x180010866  jnb     loc_180010910
0x18001086c  lea     r15, [rdi+30h]
0x180010870  mov     rax, rbx
0x180010873  mul     qword ptr [r15]
0x180010876  test    rdx, rdx
0x180010879  jnz     short loc_18001088C
0x18001087b  mov     rcx, [rdi+50h]
0x18001087f  lea     rdx, [rcx+rax]
0x180010883  cmp     rdx, rcx
0x180010886  jnb     loc_180010ABB
0x18001088c  mov     ebx, 0C0000095h
0x180010891  test    ebx, ebx
0x180010893  jnz     short loc_180010825
0x180010895  mov     [r12], rbp
0x180010899  test    r13d, r13d
0x18001089c  jz      short loc_1800108A8
0x18001089e  xor     edx, edx; BOOLEAN
0x1800108a0  mov     rcx, rdi; PVOID
0x1800108a3  call    ?PcapProcessOneTimerCallback@@YAXPEAXE@Z; PcapProcessOneTimerCallback(void *,uchar)
0x1800108a8  cmp     [rdi+38h], rbp
0x1800108ac  jz      short loc_1800108B3
0x1800108ae  cmp     [rdi+70h], ebp
0x1800108b1  jz      short loc_1800108B7
0x1800108b3  mov     ebx, ebp
0x1800108b5  jmp     short loc_180010847
0x1800108b7  lea     rsi, [rdi+68h]
0x1800108bb  mov     rdx, [rsi]; Timer
0x1800108be  test    rdx, rdx
0x1800108c1  jz      short loc_1800108D9
0x1800108c3  xor     r8d, r8d; CompletionEvent
0x1800108c6  xor     ecx, ecx; TimerQueue
0x1800108c8  call    cs:__imp_DeleteTimerQueueTimer
0x1800108ce  test    eax, eax
0x1800108d0  jz      loc_180010ACD
0x1800108d6  mov     [rsi], rbp
0x1800108d9  mov     eax, 1F4h
0x1800108de  mov     [rsp+88h+Flags], ebp; Flags
0x1800108e2  mov     [rsp+88h+Period], eax; Period
0x1800108e6  lea     r8, ?PcapProcessOneTimerCallback@@YAXPEAXE@Z; Callback
0x1800108ed  mov     r9, rdi; Parameter
0x1800108f0  mov     dword ptr [rsp+88h+DueTime], eax; DueTime
0x1800108f4  xor     edx, edx; TimerQueue
0x1800108f6  mov     rcx, rsi; phNewTimer
0x1800108f9  call    cs:__imp_CreateTimerQueueTimer
0x1800108ff  test    eax, eax
0x180010901  jz      loc_180010AF6
0x180010907  mov     dword ptr [rdi+70h], 1
0x18001090e  jmp     short loc_1800108B3
0x180010910  lea     rdx, [rbx+1]; Flags
0x180010914  cmp     rdx, rcx
0x180010917  jbe     loc_180010AB1
0x18001091d  mov     r14, [rdi+48h]
0x180010921  dec     r14
0x180010924  lea     r8, [r14+rdx]
0x180010928  cmp     r8, rdx
0x18001092b  jb      loc_18001088C
0x180010931  lea     r15, [rdi+30h]
0x180010935  mov     rax, [r15]
0x180010938  mul     rcx
0x18001093b  test    rdx, rdx
0x18001093e  jnz     loc_18001088C
0x180010944  mov     rax, [r15]
0x180010947  not     r14
0x18001094a  and     r14, r8
0x18001094d  mul     r14
0x180010950  mov     rbp, rax
0x180010953  test    rdx, rdx
0x180010956  jnz     short loc_18001099F
0x180010958  mov     r8, [rdi+50h]; Ptr
0x18001095c  mov     rcx, [rdi+28h]; Heap
0x180010960  test    r8, r8
0x180010963  jnz     loc_180010A2C
0x180010969  mov     r8, rax; Size
0x18001096c  call    cs:__imp_RtlAllocateHeap
0x180010972  mov     rsi, rax
0x180010975  test    rax, rax
0x180010978  jz      short loc_180010987
0x18001097a  mov     r8, rbp; Size
0x18001097d  xor     edx, edx; Val
0x18001097f  mov     rcx, rax; void *
0x180010982  call    memset_0
0x180010987  xor     ebp, ebp
0x180010989  test    rsi, rsi
0x18001098c  jz      loc_180010A3D
0x180010992  mov     [rdi+50h], rsi
0x180010996  mov     [rdi+40h], r14
0x18001099a  jmp     loc_180010870
0x18001099f  xor     ebp, ebp
0x1800109a1  jmp     loc_18001088C
0x1800109a6  inc     rbx
0x1800109a9  cmp     rbx, rcx
0x1800109ac  jbe     loc_180010AB1
0x1800109b2  mov     rsi, [rdi+48h]
0x1800109b6  dec     rsi
0x1800109b9  lea     r8, [rsi+rbx]
0x1800109bd  cmp     r8, rbx
0x1800109c0  jb      loc_18001088C
0x1800109c6  lea     r14, [rdi+30h]
0x1800109ca  mov     rax, [r14]
0x1800109cd  mul     rcx
0x1800109d0  test    rdx, rdx
0x1800109d3  jnz     loc_18001088C
0x1800109d9  mov     rax, [r14]
0x1800109dc  not     rsi
0x1800109df  and     rsi, r8
0x1800109e2  mul     rsi
0x1800109e5  mov     rbp, rax
0x1800109e8  test    rdx, rdx
0x1800109eb  jnz     short loc_18001099F
0x1800109ed  mov     r8, [rdi+50h]; Ptr
0x1800109f1  mov     rcx, [rdi+28h]; Heap
0x1800109f5  test    r8, r8
0x1800109f8  jnz     short loc_180010A47
0x1800109fa  mov     r8, rax; Size
0x1800109fd  call    cs:__imp_RtlAllocateHeap
0x180010a03  mov     rbx, rax
0x180010a06  test    rax, rax
0x180010a09  jz      short loc_180010A18
0x180010a0b  mov     r8, rbp; Size
0x180010a0e  xor     edx, edx; Val
0x180010a10  mov     rcx, rax; void *
0x180010a13  call    memset_0
0x180010a18  xor     ebp, ebp
0x180010a1a  test    rbx, rbx
0x180010a1d  jz      short loc_180010A3D
0x180010a1f  mov     [rdi+50h], rbx
0x180010a23  mov     [rdi+40h], rsi
0x180010a27  jmp     loc_180010805
0x180010a2c  mov     r9, rbp; Size
0x180010a2f  call    cs:__imp_RtlReAllocateHeap
0x180010a35  mov     rsi, rax
0x180010a38  jmp     loc_180010987
0x180010a3d  mov     ebx, 0C0000017h
0x180010a42  jmp     loc_180010891
0x180010a47  mov     r9, rbp; Size
0x180010a4a  call    cs:__imp_RtlReAllocateHeap
0x180010a50  mov     rbx, rax
0x180010a53  jmp     short loc_180010A18
0x180010a55  mov     eax, 1
0x180010a5a  mul     qword ptr [r14]
0x180010a5d  test    rdx, rdx
0x180010a60  jnz     loc_180010820
0x180010a66  lea     r9, [rcx+rax]
0x180010a6a  cmp     r9, rcx
0x180010a6d  jb      loc_180010820
0x180010a73  mov     rax, [r14]
0x180010a76  mul     qword ptr [rdi+38h]
0x180010a7a  test    rdx, rdx
0x180010a7d  jnz     short loc_180010A9D
0x180010a7f  mov     r8, rax; Size
0x180010a82  mov     rdx, rbx; Src
0x180010a85  mov     rcx, r9; void *
0x180010a88  call    memmove_0
0x180010a8d  mov     rax, [r12]
0x180010a91  mov     [rbx], rax
0x180010a94  inc     qword ptr [rdi+38h]
0x180010a98  jmp     loc_180010895
0x180010a9d  mov     ebx, 8000000Bh
0x180010aa2  jmp     loc_180010825
0x180010aa7  mov     eax, 0Dh
0x180010aac  jmp     loc_180010852
0x180010ab1  mov     ebx, 0C000000Dh
0x180010ab6  jmp     loc_180010891
0x180010abb  mov     rax, [r12]
0x180010abf  mov     ebx, ebp
0x180010ac1  mov     [rdx], rax
0x180010ac4  inc     qword ptr [rdi+38h]
0x180010ac8  jmp     loc_180010891
0x180010acd  call    cs:__imp_GetLastError
0x180010ad3  mov     ebx, eax
0x180010ad5  cmp     eax, 3E5h
0x180010ada  jz      loc_1800108D6
0x180010ae0  mov     dword ptr [rsp+88h+DueTime], eax
0x180010ae4  lea     r9, aFailedToDelete_8; "Failed to delete token process one time"...
0x180010aeb  mov     r8d, 196h
0x180010af1  jmp     loc_180010836
0x180010af6  call    cs:__imp_GetLastError
0x180010afc  mov     dword ptr [rsp+88h+DueTime], eax
0x180010b00  lea     r9, aFailedToCreate_54; "Failed to create token queue timer [%d]"
0x180010b07  mov     ebx, eax
0x180010b09  mov     r8d, 1A6h
0x180010b0f  jmp     loc_180010836
```
