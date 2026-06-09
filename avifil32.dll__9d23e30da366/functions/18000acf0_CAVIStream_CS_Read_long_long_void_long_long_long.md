# CAVIStream::CS::Read(long,long,void *,long,long *,long *)

- ea: `0x18000acf0`
- end: `0x18000b017`
- name: `?Read@CS@CAVIStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `807`
- prototype: `__int64 __fastcall(CAVIStream::CS *this, unsigned int, unsigned int, void *, int, int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000acf0`
- `0x18000ccf0`
- `0x1800152e4`
- `0x1800153d4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ae99`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aefe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ae99`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000aefe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ae2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ae2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ae90`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aea2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aef5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000af07`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ae90`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aea2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000aef5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000af07`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ae22`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ae22`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aeab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000af10`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000aeab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000af10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000add6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afe3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000affe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000add6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afe3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000affe`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::Read(
        CAVIStream::CS *this,
        unsigned int a2,
        unsigned int a3,
        void *a4,
        int a5,
        int *a6,
        int *a7)
{
  __int64 v7; // rsi
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  __int64 v12; // rcx
  unsigned int v13; // edi
  int v15; // r15d
  __int64 v16; // r13
  int v17; // edi
  HGLOBAL v18; // rax
  const void *v19; // r14
  int i; // ebp
  HGLOBAL v21; // rax
  HGLOBAL v22; // rax
  int v23; // r8d
  HGLOBAL v24; // rax
  HGLOBAL v25; // rax
  __int64 v26; // rcx
  int Sample; // eax

  v7 = *((_QWORD *)this + 1);
  v11 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v7 + 272) + 1264LL);
  EnterCriticalSection(v11);
  v12 = *(_QWORD *)(v7 + 288);
  if ( v12 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *, int, int *, int *))(*(_QWORD *)v12 + 64LL))(
            v12,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7);
    if ( v11 )
      LeaveCriticalSection(v11);
    return v13;
  }
  if ( (signed int)a2 < *(_DWORD *)(v7 + 92) )
    goto LABEL_10;
  if ( a2 == *(_DWORD *)(v7 + 92) && *(_DWORD *)(v7 + 64) == 1935960438 )
  {
    v15 = *(_DWORD *)(v7 + 100);
    if ( v15 )
    {
      v16 = *(_QWORD *)(v7 + 1336);
      v17 = *(unsigned __int16 *)(v16 + 8)
          * (((*(_DWORD *)(v16 + 4) * (unsigned int)*(unsigned __int16 *)(v16 + 14) + 31) >> 3) & 0xFFFC);
      if ( v17 < 0 )
      {
LABEL_10:
        if ( v11 )
          LeaveCriticalSection(v11);
        return 2147762282LL;
      }
      if ( a4 && a5 )
      {
        if ( a5 < v17 )
        {
          if ( a6 )
            *a6 = v17;
          goto LABEL_51;
        }
        v18 = GlobalAlloc(2u, v17);
        v19 = GlobalLock(v18);
        if ( !v19 )
        {
          if ( v11 )
            LeaveCriticalSection(v11);
          return 2147762279LL;
        }
        for ( i = a2 - v15; ; ++i )
        {
          if ( i > *(_DWORD *)(v7 + 92) )
          {
            v21 = GlobalHandle(v19);
            GlobalUnlock(v21);
            v22 = GlobalHandle(v19);
            GlobalFree(v22);
            goto LABEL_27;
          }
          if ( (int)StreamRead(*(struct STREAMINDEX **)(v7 + 1400), v17) < 0 )
            break;
          DecodeRle(v16, a4, v19, (unsigned int)v17);
        }
        v24 = GlobalHandle(v19);
        GlobalUnlock(v24);
        v25 = GlobalHandle(v19);
        GlobalFree(v25);
        goto LABEL_33;
      }
      if ( a6 )
        *a6 = v17;
LABEL_55:
      if ( v11 )
        LeaveCriticalSection(v11);
      return 0;
    }
  }
  v17 = StreamRead(*(struct STREAMINDEX **)(v7 + 1400), a5);
  if ( v17 >= 0 )
  {
LABEL_27:
    if ( a6 )
      *a6 = v17;
    if ( a7 )
    {
      v23 = *(_DWORD *)(*(_QWORD *)(v7 + 1400) + 40LL);
      if ( v23 )
        *a7 = v17 / v23;
      else
        *a7 = 1;
    }
    goto LABEL_55;
  }
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a5 )
  {
    v26 = *(_QWORD *)(v7 + 1400);
    if ( a5 < *(_DWORD *)(v26 + 40) )
    {
LABEL_51:
      if ( v11 )
        LeaveCriticalSection(v11);
      return 2147762292LL;
    }
    Sample = StreamFindSample(v26, a2, 4100);
    if ( a5 < Sample )
    {
      if ( a6 )
        *a6 = Sample;
      goto LABEL_51;
    }
LABEL_33:
    if ( v11 )
      LeaveCriticalSection(v11);
    return 2147762285LL;
  }
  if ( v11 )
    LeaveCriticalSection(v11);
  return 2147762375LL;
}

```

## disassembly

```asm
0x18000acf0  push    rbx
0x18000acf2  push    rbp
0x18000acf3  push    rsi
0x18000acf4  push    rdi
0x18000acf5  push    r12
0x18000acf7  push    r13
0x18000acf9  push    r14
0x18000acfb  push    r15
0x18000acfd  sub     rsp, 48h
0x18000ad01  mov     rsi, [rcx+8]
0x18000ad05  mov     r12, r9
0x18000ad08  mov     edi, r8d
0x18000ad0b  mov     ebp, edx
0x18000ad0d  mov     rbx, [rsi+110h]
0x18000ad14  add     rbx, 4F0h
0x18000ad1b  mov     rcx, rbx; lpCriticalSection
0x18000ad1e  call    cs:__imp_EnterCriticalSection
0x18000ad24  mov     rcx, [rsi+120h]
0x18000ad2b  test    rcx, rcx
0x18000ad2e  jz      short loc_18000AD80
0x18000ad30  mov     rdx, [rsp+88h+arg_30]
0x18000ad38  mov     r9, r12
0x18000ad3b  mov     rax, [rcx]
0x18000ad3e  mov     r8d, edi
0x18000ad41  mov     [rsp+88h+var_58], rdx
0x18000ad46  mov     rdx, [rsp+88h+arg_28]
0x18000ad4e  mov     [rsp+88h+var_60], rdx
0x18000ad53  mov     edx, [rsp+88h+arg_20]
0x18000ad5a  mov     rax, [rax+40h]
0x18000ad5e  mov     [rsp+88h+var_68], edx
0x18000ad62  mov     edx, ebp
0x18000ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad69  mov     edi, eax
0x18000ad6b  test    rbx, rbx
0x18000ad6e  jz      short loc_18000AD79
0x18000ad70  mov     rcx, rbx; lpCriticalSection
0x18000ad73  call    cs:__imp_LeaveCriticalSection
0x18000ad79  mov     eax, edi
0x18000ad7b  jmp     loc_18000B006
0x18000ad80  cmp     ebp, [rsi+5Ch]
0x18000ad83  jl      short loc_18000ADCE
0x18000ad85  jnz     loc_18000AF46
0x18000ad8b  cmp     dword ptr [rsi+40h], 73646976h
0x18000ad92  jnz     loc_18000AF46
0x18000ad98  mov     r15d, [rsi+64h]
0x18000ad9c  test    r15d, r15d
0x18000ad9f  jz      loc_18000AF46
0x18000ada5  mov     r13, [rsi+538h]
0x18000adac  movzx   edi, word ptr [r13+0Eh]
0x18000adb1  imul    edi, [r13+4]
0x18000adb6  movzx   eax, word ptr [r13+8]
0x18000adbb  add     edi, 1Fh
0x18000adbe  shr     edi, 3
0x18000adc1  and     edi, 0FFFCh
0x18000adc7  imul    edi, eax
0x18000adca  test    edi, edi
0x18000adcc  jns     short loc_18000ADE6
0x18000adce  test    rbx, rbx
0x18000add1  jz      short loc_18000ADDC
0x18000add3  mov     rcx, rbx; lpCriticalSection
0x18000add6  call    cs:__imp_LeaveCriticalSection
0x18000addc  mov     eax, 8004406Ah
0x18000ade1  jmp     loc_18000B006
0x18000ade6  test    r12, r12
0x18000ade9  jz      loc_18000AF2E
0x18000adef  mov     eax, [rsp+88h+arg_20]
0x18000adf6  test    eax, eax
0x18000adf8  jz      loc_18000AF2E
0x18000adfe  cmp     eax, edi
0x18000ae00  jge     short loc_18000AE1A
0x18000ae02  mov     rax, [rsp+88h+arg_28]
0x18000ae0a  test    rax, rax
0x18000ae0d  jz      loc_18000AFDB
0x18000ae13  mov     [rax], edi
0x18000ae15  jmp     loc_18000AFDB
0x18000ae1a  movsxd  rdx, edi; dwBytes
0x18000ae1d  mov     ecx, 2; uFlags
0x18000ae22  call    cs:__imp_GlobalAlloc
0x18000ae28  mov     rcx, rax; hMem
0x18000ae2b  call    cs:__imp_GlobalLock
0x18000ae31  mov     r14, rax
0x18000ae34  test    rax, rax
0x18000ae37  jnz     short loc_18000AE51
0x18000ae39  test    rbx, rbx
0x18000ae3c  jz      short loc_18000AE47
0x18000ae3e  mov     rcx, rbx; lpCriticalSection
0x18000ae41  call    cs:__imp_LeaveCriticalSection
0x18000ae47  mov     eax, 80044067h
0x18000ae4c  jmp     loc_18000B006
0x18000ae51  sub     ebp, r15d
0x18000ae54  jmp     short loc_18000AE88
0x18000ae56  mov     rcx, [rsi+578h]; struct STREAMINDEX *
0x18000ae5d  mov     r9, r14
0x18000ae60  mov     r8d, 1
0x18000ae66  mov     [rsp+88h+var_68], edi; int
0x18000ae6a  mov     edx, ebp
0x18000ae6c  call    StreamRead
0x18000ae71  test    eax, eax
0x18000ae73  js      short loc_18000AEF2
0x18000ae75  mov     r9d, edi
0x18000ae78  mov     r8, r14
0x18000ae7b  mov     rdx, r12
0x18000ae7e  mov     rcx, r13
0x18000ae81  call    DecodeRle
0x18000ae86  inc     ebp
0x18000ae88  cmp     ebp, [rsi+5Ch]
0x18000ae8b  jle     short loc_18000AE56
0x18000ae8d  mov     rcx, r14; pMem
0x18000ae90  call    cs:__imp_GlobalHandle
0x18000ae96  mov     rcx, rax; hMem
0x18000ae99  call    cs:__imp_GlobalUnlock
0x18000ae9f  mov     rcx, r14; pMem
0x18000aea2  call    cs:__imp_GlobalHandle
0x18000aea8  mov     rcx, rax; hMem
0x18000aeab  call    cs:__imp_GlobalFree
0x18000aeb1  mov     rax, [rsp+88h+arg_28]
0x18000aeb9  test    rax, rax
0x18000aebc  jz      short loc_18000AEC0
0x18000aebe  mov     [rax], edi
0x18000aec0  mov     rcx, [rsp+88h+arg_30]
0x18000aec8  test    rcx, rcx
0x18000aecb  jz      loc_18000AFF6
0x18000aed1  mov     rax, [rsi+578h]
0x18000aed8  mov     r8d, [rax+28h]
0x18000aedc  test    r8d, r8d
0x18000aedf  jz      loc_18000AFF0
0x18000aee5  mov     eax, edi
0x18000aee7  cdq
0x18000aee8  idiv    r8d
0x18000aeeb  mov     [rcx], eax
0x18000aeed  jmp     loc_18000AFF6
0x18000aef2  mov     rcx, r14; pMem
0x18000aef5  call    cs:__imp_GlobalHandle
0x18000aefb  mov     rcx, rax; hMem
0x18000aefe  call    cs:__imp_GlobalUnlock
0x18000af04  mov     rcx, r14; pMem
0x18000af07  call    cs:__imp_GlobalHandle
0x18000af0d  mov     rcx, rax; hMem
0x18000af10  call    cs:__imp_GlobalFree
0x18000af16  test    rbx, rbx
0x18000af19  jz      short loc_18000AF24
0x18000af1b  mov     rcx, rbx; lpCriticalSection
0x18000af1e  call    cs:__imp_LeaveCriticalSection
0x18000af24  mov     eax, 8004406Dh
0x18000af29  jmp     loc_18000B006
0x18000af2e  mov     rax, [rsp+88h+arg_28]
0x18000af36  test    rax, rax
0x18000af39  jz      loc_18000AFF6
0x18000af3f  mov     [rax], edi
0x18000af41  jmp     loc_18000AFF6
0x18000af46  mov     r14d, [rsp+88h+arg_20]
0x18000af4e  mov     r9, r12
0x18000af51  mov     rcx, [rsi+578h]; struct STREAMINDEX *
0x18000af58  mov     r8d, edi
0x18000af5b  mov     edx, ebp
0x18000af5d  mov     [rsp+88h+var_68], r14d; int
0x18000af62  call    StreamRead
0x18000af67  mov     edi, eax
0x18000af69  test    eax, eax
0x18000af6b  jns     loc_18000AEB1
0x18000af71  mov     rdi, [rsp+88h+arg_28]
0x18000af79  test    rdi, rdi
0x18000af7c  jz      short loc_18000AF84
0x18000af7e  mov     dword ptr [rdi], 0
0x18000af84  mov     rax, [rsp+88h+arg_30]
0x18000af8c  test    rax, rax
0x18000af8f  jz      short loc_18000AF97
0x18000af91  mov     dword ptr [rax], 0
0x18000af97  test    r14d, r14d
0x18000af9a  jnz     short loc_18000AFB1
0x18000af9c  test    rbx, rbx
0x18000af9f  jz      short loc_18000AFAA
0x18000afa1  mov     rcx, rbx; lpCriticalSection
0x18000afa4  call    cs:__imp_LeaveCriticalSection
0x18000afaa  mov     eax, 800440C7h
0x18000afaf  jmp     short loc_18000B006
0x18000afb1  mov     rcx, [rsi+578h]
0x18000afb8  cmp     r14d, [rcx+28h]
0x18000afbc  jl      short loc_18000AFDB
0x18000afbe  mov     r8d, 1004h
0x18000afc4  mov     edx, ebp
0x18000afc6  call    StreamFindSample
0x18000afcb  cmp     r14d, eax
0x18000afce  jge     loc_18000AF16
0x18000afd4  test    rdi, rdi
0x18000afd7  jz      short loc_18000AFDB
0x18000afd9  mov     [rdi], eax
0x18000afdb  test    rbx, rbx
0x18000afde  jz      short loc_18000AFE9
0x18000afe0  mov     rcx, rbx; lpCriticalSection
0x18000afe3  call    cs:__imp_LeaveCriticalSection
0x18000afe9  mov     eax, 80044074h
0x18000afee  jmp     short loc_18000B006
0x18000aff0  mov     dword ptr [rcx], 1
0x18000aff6  test    rbx, rbx
0x18000aff9  jz      short loc_18000B004
0x18000affb  mov     rcx, rbx; lpCriticalSection
0x18000affe  call    cs:__imp_LeaveCriticalSection
0x18000b004  xor     eax, eax
0x18000b006  add     rsp, 48h
0x18000b00a  pop     r15
0x18000b00c  pop     r14
0x18000b00e  pop     r13
0x18000b010  pop     r12
0x18000b012  pop     rdi
0x18000b013  pop     rsi
0x18000b014  pop     rbp
0x18000b015  pop     rbx
0x18000b016  retn
```
