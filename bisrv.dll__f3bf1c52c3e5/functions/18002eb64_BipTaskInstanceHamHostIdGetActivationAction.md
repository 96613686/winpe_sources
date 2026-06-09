# BipTaskInstanceHamHostIdGetActivationAction

- ea: `0x18002eb64`
- end: `0x18002edd5`
- name: `BipTaskInstanceHamHostIdGetActivationAction`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800144f4`

## callees

- `0x18002eb64`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002eb86`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ec39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ec82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ecec`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002eb86`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ec39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ec82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002ecec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ec27`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ec4a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ed2b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ed50`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ec27`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ec4a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ed2b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ed50`
- `ntdll!TpPostWork` at `0x18002ecc6`
- `ntdll!TpPostWork` at `0x18002ecc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ec88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ecf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ec88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ecf2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002ed89`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002eda4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002ed89`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002eda4`

## pseudocode

```c
__int64 __fastcall BipTaskInstanceHamHostIdGetActivationAction(__int64 a1, _DWORD *a2)
{
  __int64 v2; // r13
  __int64 v3; // r15
  __int64 v6; // rdx
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // ecx
  unsigned int v11; // ebp
  char v12; // si
  unsigned int v13; // ebx
  __int64 v14; // rsi
  DWORD CurrentThreadId; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // r14d
  char v19; // cl
  int v20; // ebx
  int v21; // edi

  v2 = *(_QWORD *)(a1 + 64);
  v3 = a1 + 48;
  RtlAcquireSRWLockExclusive(a1 + 48);
  if ( (*(_DWORD *)(a1 + 136) & 0x4000) != 0 )
  {
    v12 = 0;
    *a2 = *(_DWORD *)(a1 + 284);
    v11 = 2;
    goto LABEL_18;
  }
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_DWORD *)(*(_QWORD *)(v6 + 72) + 24LL);
  if ( (v7 & 0x40) != 0 )
  {
    v8 = 1;
  }
  else if ( (v7 & 0x20) != 0 )
  {
    v8 = 2;
  }
  else
  {
    if ( (v7 & 0x80u) != 0 )
      goto LABEL_8;
    v8 = 0;
  }
  if ( (v7 & 0x8000000) != 0 || v8 != 1 )
  {
LABEL_8:
    v9 = *(_DWORD *)(v6 + 400);
    if ( (!v9 || v9 == 2) && *(_QWORD *)(v6 + 112) != v6 + 112 )
    {
      v10 = 20749;
LABEL_12:
      v11 = 1;
      v12 = 0;
      a2[1] = v10;
      goto LABEL_18;
    }
    if ( *(_QWORD *)(v6 + 144) != v6 + 144 )
    {
      v10 = 20750;
      goto LABEL_12;
    }
  }
  if ( *(_QWORD *)(a1 + 320) == -1 )
  {
    v12 = 1;
    a2[1] = 68097;
    v11 = 1;
  }
  else
  {
    v12 = 0;
    v11 = 0;
  }
LABEL_18:
  RtlReleaseSRWLockExclusive(v3);
  if ( v12 )
  {
    RtlAcquireSRWLockExclusive(v3);
    *(_DWORD *)(a1 + 136) |= 0x8000u;
    RtlReleaseSRWLockExclusive(v3);
    v13 = 1 << *(_DWORD *)(v2 + 64);
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( *(_DWORD *)(v14 + 4) >= v13 && IsDebuggerPresent() )
      BipSyncDebugPrintLockBug((struct _BI_LOCK *)(v2 + 56));
    RtlAcquireSRWLockExclusive(v2 + 56);
    CurrentThreadId = GetCurrentThreadId();
    *(_DWORD *)(v14 + 4) |= v13;
    *(_DWORD *)(v2 + 68) = CurrentThreadId;
    *(_DWORD *)(v2 + 504) |= 2u;
    v16 = *(_DWORD *)(v2 + 504);
    *(_DWORD *)(v14 + 8) |= v13;
    if ( (v16 & 1) == 0 )
    {
      v17 = *(_QWORD *)(v2 + 480);
      *(_DWORD *)(v2 + 504) = v16 | 1;
      TpPostWork(v17);
      v18 = 1 << dword_1800C4608;
      if ( *(_DWORD *)(v14 + 4) >= (unsigned int)(1 << dword_1800C4608) && IsDebuggerPresent() )
        BipSyncDebugPrintLockBug((struct _BI_LOCK *)&qword_1800C4600);
      RtlAcquireSRWLockExclusive(&qword_1800C4600);
      GetCurrentThreadId();
      v19 = dword_1800C4608;
      *(_DWORD *)(v14 + 4) |= v18;
      ++dword_1800C4650;
      v20 = ~(1 << v19);
      dword_1800C460C = 0;
      *(_DWORD *)(v14 + 8) = v20 & (*(_DWORD *)(v14 + 8) | v18);
      RtlReleaseSRWLockExclusive(&qword_1800C4600);
      *(_DWORD *)(v14 + 4) &= v20;
    }
    v21 = ~(1 << *(_DWORD *)(v2 + 64));
    *(_DWORD *)(v2 + 68) = 0;
    *(_DWORD *)(v14 + 8) &= v21;
    RtlReleaseSRWLockExclusive(v2 + 56);
    *(_DWORD *)(v14 + 4) &= v21;
  }
  return v11;
}

```

## disassembly

```asm
0x18002eb64  push    rbx
0x18002eb66  push    rbp
0x18002eb67  push    rsi
0x18002eb68  push    rdi
0x18002eb69  push    r12
0x18002eb6b  push    r13
0x18002eb6d  push    r14
0x18002eb6f  push    r15
0x18002eb71  sub     rsp, 28h
0x18002eb75  mov     r13, [rcx+40h]
0x18002eb79  lea     r15, [rcx+30h]
0x18002eb7d  mov     rbx, rcx
0x18002eb80  mov     r14, rdx
0x18002eb83  mov     rcx, r15
0x18002eb86  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002eb8c  test    dword ptr [rbx+88h], 4000h
0x18002eb96  mov     edi, 1
0x18002eb9b  jnz     loc_18002EDBF
0x18002eba1  mov     rdx, [rbx+40h]
0x18002eba5  mov     rax, [rdx+48h]
0x18002eba9  mov     ecx, [rax+18h]
0x18002ebac  test    cl, 40h
0x18002ebaf  jnz     short loc_18002EBF6
0x18002ebb1  test    cl, 20h
0x18002ebb4  jnz     short loc_18002EBFA
0x18002ebb6  test    cl, cl
0x18002ebb8  js      short loc_18002EBC6
0x18002ebba  xor     eax, eax
0x18002ebbc  bt      ecx, 1Bh
0x18002ebc0  jb      short loc_18002EBC6
0x18002ebc2  cmp     eax, edi
0x18002ebc4  jz      short loc_18002EC11
0x18002ebc6  mov     ecx, [rdx+190h]
0x18002ebcc  test    ecx, ecx
0x18002ebce  jz      short loc_18002EBD8
0x18002ebd0  sub     ecx, edi
0x18002ebd2  jz      short loc_18002EC01
0x18002ebd4  cmp     ecx, edi
0x18002ebd6  jnz     short loc_18002EC01
0x18002ebd8  lea     rax, [rdx+70h]
0x18002ebdc  cmp     [rax], rax
0x18002ebdf  jz      short loc_18002EC01
0x18002ebe1  mov     ecx, 510Dh
0x18002ebe6  mov     eax, 4
0x18002ebeb  mov     ebp, edi
0x18002ebed  xor     sil, sil
0x18002ebf0  mov     [rax+r14], ecx
0x18002ebf4  jmp     short loc_18002EC24
0x18002ebf6  mov     eax, edi
0x18002ebf8  jmp     short loc_18002EBBC
0x18002ebfa  mov     eax, 2
0x18002ebff  jmp     short loc_18002EBBC
0x18002ec01  lea     rax, [rdx+90h]
0x18002ec08  cmp     [rax], rax
0x18002ec0b  jnz     loc_18002ED6D
0x18002ec11  cmp     qword ptr [rbx+140h], 0FFFFFFFFFFFFFFFFh
0x18002ec19  jz      loc_18002ED77
0x18002ec1f  xor     sil, sil
0x18002ec22  xor     ebp, ebp
0x18002ec24  mov     rcx, r15
0x18002ec27  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ec2d  test    sil, sil
0x18002ec30  jz      loc_18002ED5A
0x18002ec36  mov     rcx, r15
0x18002ec39  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002ec3f  bts     dword ptr [rbx+88h], 0Fh
0x18002ec47  mov     rcx, r15
0x18002ec4a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ec50  mov     rax, gs:58h
0x18002ec59  lea     r15, [r13+38h]
0x18002ec5d  mov     ecx, [r15+8]
0x18002ec61  mov     ebx, edi
0x18002ec63  shl     ebx, cl
0x18002ec65  mov     ecx, cs:_tls_index
0x18002ec6b  mov     r12d, 4
0x18002ec71  mov     rsi, [rax+rcx*8]
0x18002ec75  cmp     [r12+rsi], ebx
0x18002ec79  jnb     loc_18002ED89
0x18002ec7f  mov     rcx, r15
0x18002ec82  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002ec88  call    cs:__imp_GetCurrentThreadId
0x18002ec8e  or      [r12+rsi], ebx
0x18002ec92  mov     [r15+0Ch], eax
0x18002ec96  or      dword ptr [r13+1F8h], 2
0x18002ec9e  mov     eax, [r13+1F8h]
0x18002eca5  mov     edx, 8
0x18002ecaa  or      [rdx+rsi], ebx
0x18002ecad  test    dil, al
0x18002ecb0  jnz     loc_18002ED3A
0x18002ecb6  mov     rcx, [r13+1E0h]
0x18002ecbd  or      eax, edi
0x18002ecbf  mov     [r13+1F8h], eax
0x18002ecc6  call    cs:__imp_TpPostWork
0x18002eccc  mov     ecx, cs:dword_1800C4608
0x18002ecd2  lea     r13, qword_1800C4600
0x18002ecd9  mov     r14d, edi
0x18002ecdc  shl     r14d, cl
0x18002ecdf  cmp     [r12+rsi], r14d
0x18002ece3  jnb     loc_18002EDA4
0x18002ece9  mov     rcx, r13
0x18002ecec  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002ecf2  call    cs:__imp_GetCurrentThreadId
0x18002ecf8  mov     ecx, cs:dword_1800C4608
0x18002ecfe  mov     ebx, edi
0x18002ed00  or      [r12+rsi], r14d
0x18002ed04  add     cs:dword_1800C4650, edi
0x18002ed0a  mov     eax, 8
0x18002ed0f  shl     ebx, cl
0x18002ed11  mov     rcx, r13
0x18002ed14  not     ebx
0x18002ed16  mov     cs:dword_1800C460C, 0
0x18002ed20  or      r14d, [rax+rsi]
0x18002ed24  and     r14d, ebx
0x18002ed27  mov     [rax+rsi], r14d
0x18002ed2b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ed31  and     [r12+rsi], ebx
0x18002ed35  mov     edx, 8
0x18002ed3a  mov     ecx, [r15+8]
0x18002ed3e  shl     edi, cl
0x18002ed40  mov     rcx, r15
0x18002ed43  not     edi
0x18002ed45  mov     dword ptr [r15+0Ch], 0
0x18002ed4d  and     [rdx+rsi], edi
0x18002ed50  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002ed56  and     [r12+rsi], edi
0x18002ed5a  mov     eax, ebp
0x18002ed5c  add     rsp, 28h
0x18002ed60  pop     r15
0x18002ed62  pop     r14
0x18002ed64  pop     r13
0x18002ed66  pop     r12
0x18002ed68  pop     rdi
0x18002ed69  pop     rsi
0x18002ed6a  pop     rbp
0x18002ed6b  pop     rbx
0x18002ed6c  retn
0x18002ed6d  mov     ecx, 510Eh
0x18002ed72  jmp     loc_18002EBE6
0x18002ed77  mov     sil, dil
0x18002ed7a  mov     dword ptr [r14+4], 10A01h
0x18002ed82  mov     ebp, edi
0x18002ed84  jmp     loc_18002EC24
0x18002ed89  call    cs:__imp_IsDebuggerPresent
0x18002ed8f  test    eax, eax
0x18002ed91  jz      loc_18002EC7F
0x18002ed97  mov     rcx, r15; struct _BI_LOCK *
0x18002ed9a  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002ed9f  jmp     loc_18002EC7F
0x18002eda4  call    cs:__imp_IsDebuggerPresent
0x18002edaa  test    eax, eax
0x18002edac  jz      loc_18002ECE9
0x18002edb2  mov     rcx, r13; struct _BI_LOCK *
0x18002edb5  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002edba  jmp     loc_18002ECE9
0x18002edbf  mov     eax, [rbx+11Ch]
0x18002edc5  xor     sil, sil
0x18002edc8  mov     [r14], eax
0x18002edcb  mov     ebp, 2
0x18002edd0  jmp     loc_18002EC24
```
