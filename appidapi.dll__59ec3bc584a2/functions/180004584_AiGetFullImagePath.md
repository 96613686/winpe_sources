# AiGetFullImagePath

- ea: `0x180004584`
- end: `0x18000497a`
- name: `AiGetFullImagePath`
- size: `1014`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180004f4c`
- `0x1800061c8`

## callees

- `0x180003fd4`
- `0x180004584`
- `0x180009562`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047df`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800046eb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800047c7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800046eb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800047c7`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800045ee`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800045ee`
- `ntdll!NtQueryInformationFile` at `0x180004664`
- `ntdll!NtQueryInformationFile` at `0x180004664`
- `ntdll!NtQueryObject` at `0x18000486f`
- `ntdll!NtQueryObject` at `0x18000486f`
- `ntdll!RtlFreeHeap` at `0x180004633`
- `ntdll!RtlFreeHeap` at `0x1800046bf`
- `ntdll!RtlFreeHeap` at `0x18000478b`
- `ntdll!RtlFreeHeap` at `0x180004840`
- `ntdll!RtlFreeHeap` at `0x1800048d3`
- `ntdll!RtlFreeHeap` at `0x1800048eb`
- `ntdll!RtlFreeHeap` at `0x18000490f`
- `ntdll!RtlFreeHeap` at `0x180004936`
- `ntdll!RtlFreeHeap` at `0x18000495d`
- `ntdll!RtlFreeHeap` at `0x180004633`
- `ntdll!RtlFreeHeap` at `0x1800046bf`
- `ntdll!RtlFreeHeap` at `0x18000478b`
- `ntdll!RtlFreeHeap` at `0x180004840`
- `ntdll!RtlFreeHeap` at `0x1800048d3`
- `ntdll!RtlFreeHeap` at `0x1800048eb`
- `ntdll!RtlFreeHeap` at `0x18000490f`
- `ntdll!RtlFreeHeap` at `0x180004936`
- `ntdll!RtlFreeHeap` at `0x18000495d`

## pseudocode

```c
__int64 __fastcall AiGetFullImagePath(
        HANDLE FileHandle,
        PVOID *a2,
        __int64 a3,
        unsigned __int16 *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  unsigned int *v9; // rsi
  const void **v10; // r13
  DWORD v11; // r15d
  int v12; // ebx
  unsigned int *v13; // rax
  ULONG FinalPathNameByHandleW; // eax
  PVOID v15; // r8
  WCHAR *v16; // rax
  unsigned __int16 v17; // ax
  _WORD *v18; // rax
  unsigned __int16 v19; // ax
  WCHAR *v20; // rax
  ULONG v21; // eax
  unsigned int v22; // ecx
  DWORD LastError; // eax
  NTSTATUS v24; // eax
  unsigned int v25; // eax
  unsigned __int16 v26; // ax
  void *v27; // rax
  void *v28; // r8
  void *v29; // r8
  __int64 FsInformation; // [rsp+30h] [rbp-28h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-20h] BYREF
  char v34; // [rsp+A8h] [rbp+50h]
  ULONG Length; // [rsp+B0h] [rbp+58h] BYREF
  DWORD cchFilePath; // [rsp+B8h] [rbp+60h]

  Length = 0;
  FsInformation = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v9 = 0;
  v10 = 0;
  IoStatusBlock = 0;
  if ( a4 )
    *((_QWORD *)a4 + 1) = 0;
  if ( a2 )
    *a2 = 0;
  v11 = 8;
  v12 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
  if ( v12 >= 0 )
  {
    if ( a5 )
      *a5 = FsInformation;
    if ( a6 )
      *a6 = HIDWORD(FsInformation);
    Length = 528;
    do
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      v13 = (unsigned int *)AiAlloc(Length);
      v9 = v13;
      if ( !v13 )
        goto LABEL_45;
      v12 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v13, Length, FileNameInformation);
      Length = *v9 + 8;
    }
    while ( v12 == -2147483643 );
    if ( v12 < 0 )
      goto LABEL_46;
    if ( *v9 > 0xFFFD )
    {
LABEL_15:
      v12 = -1073741811;
      goto LABEL_46;
    }
    if ( a2 )
    {
      v34 = 0;
LABEL_18:
      FinalPathNameByHandleW = 260;
      Length = 260;
      while ( 1 )
      {
        v15 = *a2;
        cchFilePath = FinalPathNameByHandleW + 1;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        v16 = (WCHAR *)AiAlloc(2LL * cchFilePath);
        *a2 = v16;
        if ( !v16 )
          goto LABEL_45;
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, v16, cchFilePath, v11);
        Length = FinalPathNameByHandleW;
        if ( FinalPathNameByHandleW < cchFilePath )
        {
          if ( FinalPathNameByHandleW )
            break;
          if ( !v34 )
          {
            v34 = 1;
            v11 |= 1u;
            goto LABEL_18;
          }
LABEL_32:
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError )
            v12 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_46;
        }
      }
    }
    if ( (FsInformation & 0x1000000000LL) != 0 )
    {
      v17 = *(_WORD *)v9 + 2;
      *(_WORD *)a3 = v17;
      *(_WORD *)(a3 + 2) = v17;
      v18 = (_WORD *)AiAlloc(v17);
      *(_QWORD *)(a3 + 8) = v18;
      if ( v18 )
      {
        *v18 = 92;
        memcpy_0((void *)(*(_QWORD *)(a3 + 8) + 2LL), v9 + 1, *v9);
        if ( a4 )
        {
          *(_DWORD *)a4 = 0;
          *((_QWORD *)a4 + 1) = 0;
        }
        goto LABEL_46;
      }
    }
    else
    {
      Length = 260;
      while ( 1 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(a3 + 8));
        v19 = 2 * (Length + 1);
        *(_WORD *)(a3 + 2) = v19;
        v20 = (WCHAR *)AiAlloc(v19);
        *(_QWORD *)(a3 + 8) = v20;
        if ( !v20 )
          break;
        v21 = GetFinalPathNameByHandleW(FileHandle, v20, *(unsigned __int16 *)(a3 + 2) >> 1, 2u);
        v22 = *(unsigned __int16 *)(a3 + 2) >> 1;
        Length = v21;
        if ( v21 < v22 )
        {
          if ( !v21 )
            goto LABEL_32;
          *(_WORD *)a3 = 2 * v21;
          if ( !a4 )
            goto LABEL_46;
          if ( *v9 < 2 && *((_WORD *)v9 + 2) != 92 )
          {
            v12 = -1073741790;
            goto LABEL_46;
          }
          Length = 536;
          while ( 1 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            v10 = (const void **)AiAlloc(Length);
            if ( !v10 )
              goto LABEL_45;
            v24 = NtQueryObject(FileHandle, ObjectNameInformation, v10, Length, &Length);
            v12 = v24;
            if ( v24 != -2147483643 )
            {
              if ( v24 < 0 )
                goto LABEL_46;
              v25 = *(unsigned __int16 *)v10;
              if ( *v9 >= v25 )
                goto LABEL_15;
              v26 = v25 - *(_WORD *)v9;
              *a4 = v26;
              a4[1] = v26;
              v27 = (void *)AiAlloc(v26);
              *((_QWORD *)a4 + 1) = v27;
              if ( !v27 )
                goto LABEL_45;
              memcpy_0(v27, v10[1], *a4);
              goto LABEL_46;
            }
          }
        }
      }
    }
LABEL_45:
    v12 = -1073741801;
  }
LABEL_46:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v12 < 0 )
  {
    v28 = *(void **)(a3 + 8);
    if ( v28 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
      *(_QWORD *)(a3 + 8) = 0;
    }
    if ( a4 )
    {
      v29 = (void *)*((_QWORD *)a4 + 1);
      if ( v29 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
        *((_QWORD *)a4 + 1) = 0;
      }
    }
    if ( a2 && *a2 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a2);
      *a2 = 0;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004584  mov     [rsp-40h+FileHandle], rcx
0x180004589  push    rbp
0x18000458a  push    rbx
0x18000458b  push    rsi
0x18000458c  push    rdi
0x18000458d  push    r12
0x18000458f  push    r13
0x180004591  push    r14
0x180004593  push    r15
0x180004595  mov     rbp, rsp
0x180004598  sub     rsp, 58h
0x18000459c  mov     rax, rcx
0x18000459f  xorps   xmm0, xmm0
0x1800045a2  xor     ecx, ecx
0x1800045a4  mov     rdi, r9
0x1800045a7  mov     [rbp+Length], ecx
0x1800045aa  mov     r14, r8
0x1800045ad  mov     [rbp+FsInformation], rcx
0x1800045b1  mov     r12, rdx
0x1800045b4  mov     [r8+8], rcx
0x1800045b8  mov     esi, ecx
0x1800045ba  mov     r13d, ecx
0x1800045bd  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800045c1  test    r9, r9
0x1800045c4  jz      short loc_1800045CA
0x1800045c6  mov     [r9+8], rcx
0x1800045ca  test    r12, r12
0x1800045cd  jz      short loc_1800045D2
0x1800045cf  mov     [rdx], rcx
0x1800045d2  mov     r15d, 8
0x1800045d8  mov     [rsp+58h+FsInformationClass], 4; FsInformationClass
0x1800045e0  mov     r9d, r15d; Length
0x1800045e3  lea     r8, [rbp+FsInformation]; FsInformation
0x1800045e7  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1800045eb  mov     rcx, rax; FileHandle
0x1800045ee  call    cs:__imp_NtQueryVolumeInformationFile
0x1800045f4  mov     ebx, eax
0x1800045f6  test    eax, eax
0x1800045f8  js      loc_1800048C1
0x1800045fe  mov     rcx, [rbp+arg_20]
0x180004602  test    rcx, rcx
0x180004605  jz      short loc_18000460C
0x180004607  mov     eax, dword ptr [rbp+FsInformation]
0x18000460a  mov     [rcx], eax
0x18000460c  mov     rcx, [rbp+arg_28]
0x180004610  test    rcx, rcx
0x180004613  jz      short loc_18000461A
0x180004615  mov     eax, dword ptr [rbp+FsInformation+4]
0x180004618  mov     [rcx], eax
0x18000461a  mov     [rbp+Length], 210h
0x180004621  mov     rcx, gs:60h
0x18000462a  mov     r8, rsi; P
0x18000462d  xor     edx, edx; Flags
0x18000462f  mov     rcx, [rcx+30h]; HeapHandle
0x180004633  call    cs:__imp_RtlFreeHeap
0x180004639  mov     ecx, [rbp+Length]
0x18000463c  call    AiAlloc
0x180004641  mov     rsi, rax
0x180004644  test    rax, rax
0x180004647  jz      loc_1800048BC
0x18000464d  mov     r9d, [rbp+Length]; Length
0x180004651  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180004655  mov     rcx, [rbp+FileHandle]; FileHandle
0x180004659  mov     r8, rax; FileInformation
0x18000465c  mov     [rsp+58h+FsInformationClass], 9; FileInformationClass
0x180004664  call    cs:__imp_NtQueryInformationFile
0x18000466a  mov     ebx, eax
0x18000466c  mov     eax, [rsi]
0x18000466e  add     eax, r15d
0x180004671  mov     [rbp+Length], eax
0x180004674  cmp     ebx, 80000005h
0x18000467a  jz      short loc_180004621
0x18000467c  test    ebx, ebx
0x18000467e  js      loc_1800048C1
0x180004684  cmp     dword ptr [rsi], 0FFFDh
0x18000468a  jbe     short loc_180004696
0x18000468c  mov     ebx, 0C000000Dh
0x180004691  jmp     loc_1800048C1
0x180004696  test    r12, r12
0x180004699  jz      short loc_180004712
0x18000469b  mov     [rbp+arg_8], r13b
0x18000469f  mov     eax, 104h
0x1800046a4  mov     [rbp+Length], eax
0x1800046a7  mov     rcx, gs:60h
0x1800046b0  inc     eax
0x1800046b2  mov     r8, [r12]; P
0x1800046b6  xor     edx, edx; Flags
0x1800046b8  mov     [rbp+cchFilePath], eax
0x1800046bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800046bf  call    cs:__imp_RtlFreeHeap
0x1800046c5  mov     ecx, [rbp+cchFilePath]
0x1800046c8  add     rcx, rcx
0x1800046cb  call    AiAlloc
0x1800046d0  mov     [r12], rax
0x1800046d4  test    rax, rax
0x1800046d7  jz      loc_1800048BC
0x1800046dd  mov     r8d, [rbp+cchFilePath]; cchFilePath
0x1800046e1  mov     r9d, r15d; dwFlags
0x1800046e4  mov     rcx, [rbp+FileHandle]; hFile
0x1800046e8  mov     rdx, rax; lpszFilePath
0x1800046eb  call    cs:__imp_GetFinalPathNameByHandleW
0x1800046f1  mov     [rbp+Length], eax
0x1800046f4  cmp     eax, [rbp+cchFilePath]
0x1800046f7  jnb     short loc_1800046A7
0x1800046f9  test    eax, eax
0x1800046fb  jnz     short loc_180004712
0x1800046fd  cmp     [rbp+arg_8], r13b
0x180004701  jnz     loc_1800047DF
0x180004707  lea     ecx, [rax+1]
0x18000470a  mov     [rbp+arg_8], cl
0x18000470d  or      r15d, ecx
0x180004710  jmp     short loc_18000469F
0x180004712  test    byte ptr [rbp+FsInformation+4], 10h
0x180004716  mov     r15d, 2
0x18000471c  jz      short loc_180004771
0x18000471e  movzx   eax, word ptr [rsi]
0x180004721  add     ax, r15w
0x180004725  movzx   ecx, ax
0x180004728  mov     [r14], cx
0x18000472c  mov     [r14+2], cx
0x180004731  call    AiAlloc
0x180004736  mov     [r14+8], rax
0x18000473a  test    rax, rax
0x18000473d  jz      loc_1800048BC
0x180004743  mov     word ptr [rax], 5Ch ; '\'
0x180004748  lea     rdx, [rsi+4]; Src
0x18000474c  mov     rcx, [r14+8]
0x180004750  mov     r8d, [rsi]; Size
0x180004753  add     rcx, r15; void *
0x180004756  call    memcpy_0
0x18000475b  test    rdi, rdi
0x18000475e  jz      loc_1800048C1
0x180004764  xor     eax, eax
0x180004766  mov     [rdi], eax
0x180004768  mov     [rdi+8], rax
0x18000476c  jmp     loc_1800048C1
0x180004771  mov     [rbp+Length], 104h
0x180004778  mov     rcx, gs:60h
0x180004781  xor     edx, edx; Flags
0x180004783  mov     r8, [r14+8]; P
0x180004787  mov     rcx, [rcx+30h]; HeapHandle
0x18000478b  call    cs:__imp_RtlFreeHeap
0x180004791  movzx   eax, word ptr [rbp+Length]
0x180004795  inc     ax
0x180004798  add     ax, ax
0x18000479b  movzx   ecx, ax
0x18000479e  mov     [r14+2], cx
0x1800047a3  call    AiAlloc
0x1800047a8  mov     [r14+8], rax
0x1800047ac  test    rax, rax
0x1800047af  jz      loc_1800048BC
0x1800047b5  movzx   r8d, word ptr [r14+2]
0x1800047ba  mov     r9d, r15d; dwFlags
0x1800047bd  mov     rcx, [rbp+FileHandle]; hFile
0x1800047c1  mov     rdx, rax; lpszFilePath
0x1800047c4  shr     r8d, 1; cchFilePath
0x1800047c7  call    cs:__imp_GetFinalPathNameByHandleW
0x1800047cd  movzx   ecx, word ptr [r14+2]
0x1800047d2  shr     ecx, 1
0x1800047d4  mov     [rbp+Length], eax
0x1800047d7  cmp     eax, ecx
0x1800047d9  jnb     short loc_180004778
0x1800047db  test    eax, eax
0x1800047dd  jnz     short loc_1800047FD
0x1800047df  call    cs:__imp_GetLastError
0x1800047e5  mov     ebx, eax
0x1800047e7  test    eax, eax
0x1800047e9  jz      loc_1800048C1
0x1800047ef  movzx   ebx, ax
0x1800047f2  or      ebx, 80070000h
0x1800047f8  jmp     loc_1800048C1
0x1800047fd  add     ax, ax
0x180004800  mov     [r14], ax
0x180004804  test    rdi, rdi
0x180004807  jz      loc_1800048C1
0x18000480d  cmp     [rsi], r15d
0x180004810  jnb     short loc_180004827
0x180004812  mov     eax, 5Ch ; '\'
0x180004817  cmp     [rsi+4], ax
0x18000481b  jz      short loc_180004827
0x18000481d  mov     ebx, 0C0000022h
0x180004822  jmp     loc_1800048C1
0x180004827  mov     [rbp+Length], 218h
0x18000482e  mov     rcx, gs:60h
0x180004837  mov     r8, r13; P
0x18000483a  xor     edx, edx; Flags
0x18000483c  mov     rcx, [rcx+30h]; HeapHandle
0x180004840  call    cs:__imp_RtlFreeHeap
0x180004846  mov     ecx, [rbp+Length]
0x180004849  call    AiAlloc
0x18000484e  mov     r13, rax
0x180004851  test    rax, rax
0x180004854  jz      short loc_1800048BC
0x180004856  mov     r9d, [rbp+Length]; ObjectInformationLength
0x18000485a  lea     rax, [rbp+Length]
0x18000485e  mov     rcx, [rbp+FileHandle]; Handle
0x180004862  mov     r8, r13; ObjectInformation
0x180004865  mov     edx, 1; ObjectInformationClass
0x18000486a  mov     qword ptr [rsp+58h+FsInformationClass], rax; ReturnLength
0x18000486f  call    cs:__imp_NtQueryObject
0x180004875  mov     ebx, eax
0x180004877  cmp     eax, 80000005h
0x18000487c  jz      short loc_18000482E
0x18000487e  test    eax, eax
0x180004880  js      short loc_1800048C1
0x180004882  movzx   eax, word ptr [r13+0]
0x180004887  cmp     [rsi], eax
0x180004889  jnb     loc_18000468C
0x18000488f  sub     ax, [rsi]
0x180004892  movzx   ecx, ax
0x180004895  mov     [rdi], cx
0x180004898  mov     [rdi+2], cx
0x18000489c  call    AiAlloc
0x1800048a1  mov     [rdi+8], rax
0x1800048a5  test    rax, rax
0x1800048a8  jz      short loc_1800048BC
0x1800048aa  movzx   r8d, word ptr [rdi]; Size
0x1800048ae  mov     rcx, rax; void *
0x1800048b1  mov     rdx, [r13+8]; Src
0x1800048b5  call    memcpy_0
0x1800048ba  jmp     short loc_1800048C1
0x1800048bc  mov     ebx, 0C0000017h
0x1800048c1  mov     rcx, gs:60h
0x1800048ca  mov     r8, rsi; P
0x1800048cd  xor     edx, edx; Flags
0x1800048cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800048d3  call    cs:__imp_RtlFreeHeap
0x1800048d9  mov     rcx, gs:60h
0x1800048e2  mov     r8, r13; P
0x1800048e5  xor     edx, edx; Flags
0x1800048e7  mov     rcx, [rcx+30h]; HeapHandle
0x1800048eb  call    cs:__imp_RtlFreeHeap
0x1800048f1  xor     esi, esi
0x1800048f3  test    ebx, ebx
0x1800048f5  jns     short loc_180004967
0x1800048f7  mov     r8, [r14+8]; P
0x1800048fb  test    r8, r8
0x1800048fe  jz      short loc_180004919
0x180004900  mov     rcx, gs:60h
0x180004909  xor     edx, edx; Flags
0x18000490b  mov     rcx, [rcx+30h]; HeapHandle
0x18000490f  call    cs:__imp_RtlFreeHeap
0x180004915  mov     [r14+8], rsi
0x180004919  test    rdi, rdi
0x18000491c  jz      short loc_180004940
0x18000491e  mov     r8, [rdi+8]; P
0x180004922  test    r8, r8
0x180004925  jz      short loc_180004940
0x180004927  mov     rcx, gs:60h
0x180004930  xor     edx, edx; Flags
0x180004932  mov     rcx, [rcx+30h]; HeapHandle
0x180004936  call    cs:__imp_RtlFreeHeap
0x18000493c  mov     [rdi+8], rsi
0x180004940  test    r12, r12
0x180004943  jz      short loc_180004967
0x180004945  mov     r8, [r12]; P
0x180004949  test    r8, r8
0x18000494c  jz      short loc_180004967
0x18000494e  mov     rcx, gs:60h
0x180004957  xor     edx, edx; Flags
0x180004959  mov     rcx, [rcx+30h]; HeapHandle
0x18000495d  call    cs:__imp_RtlFreeHeap
0x180004963  mov     [r12], rsi
0x180004967  mov     eax, ebx
0x180004969  add     rsp, 58h
0x18000496d  pop     r15
0x18000496f  pop     r14
0x180004971  pop     r13
0x180004973  pop     r12
0x180004975  pop     rdi
0x180004976  pop     rsi
0x180004977  pop     rbx
0x180004978  pop     rbp
0x180004979  retn
```
