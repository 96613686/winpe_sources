# _CabUnzip

- ea: `0x18000ca5c`
- end: `0x18000cc47`
- name: `_CabUnzip`
- size: `491`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c398`

## callees

- `0x18000307c`
- `0x1800039d0`
- `0x180004dec`
- `0x18000c708`
- `0x18000ca5c`
- `0x18000ede8`
- `0x18000eed0`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000caf3`
- `KERNEL32!GetProcessHeap` at `0x18000cb17`
- `KERNEL32!GetProcessHeap` at `0x18000cbe2`
- `KERNEL32!GetProcessHeap` at `0x18000cbfb`
- `KERNEL32!GetProcessHeap` at `0x18000caf3`
- `KERNEL32!GetProcessHeap` at `0x18000cb17`
- `KERNEL32!GetProcessHeap` at `0x18000cbe2`
- `KERNEL32!GetProcessHeap` at `0x18000cbfb`
- `KERNEL32!HeapFree` at `0x18000cb01`
- `KERNEL32!HeapFree` at `0x18000cb25`
- `KERNEL32!HeapFree` at `0x18000cbf0`
- `KERNEL32!HeapFree` at `0x18000cc09`
- `KERNEL32!HeapFree` at `0x18000cb01`
- `KERNEL32!HeapFree` at `0x18000cb25`
- `KERNEL32!HeapFree` at `0x18000cbf0`
- `KERNEL32!HeapFree` at `0x18000cc09`
- `Cabinet!__imp_FDICopy` at `0x18000cb72`
- `Cabinet!__imp_FDICopy` at `0x18000cb72`

## pseudocode

```c
__int64 __fastcall CabUnzip(__int64 a1, const unsigned __int16 *a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v9; // rax
  CHAR *AnsiMuiSafePath; // r15
  unsigned int v11; // ebx
  CHAR *v12; // rdi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  unsigned __int16 *v15; // r14
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  void *v18; // rcx
  int v19; // ecx
  int v20; // ecx
  HANDLE v21; // rax
  HANDLE v22; // rax
  int v24; // ecx
  int v25; // ecx
  __int128 pvUser; // [rsp+40h] [rbp-58h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h]

  v27 = 0;
  pvUser = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3, a4);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v9 = (unsigned __int16 *)FSGetFileName(a2);
  AnsiMuiSafePath = (CHAR *)MemGetAnsiMuiSafePath(v9);
  if ( !AnsiMuiSafePath )
    return 8;
  v12 = 0;
  v13 = MemMallocAndCopy(a2);
  v14 = v13;
  if ( !v13 )
    goto LABEL_8;
  FSSplitFileName(v13);
  v15 = MemMallocAndCat(v14, L"\\", 0);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v14);
  if ( !v15 )
    goto LABEL_8;
  v12 = (CHAR *)MemGetAnsiMuiSafePath(v15);
  v17 = GetProcessHeap();
  HeapFree(v17, 0, v15);
  if ( !v12 )
    goto LABEL_8;
  v18 = *(void **)a1;
  v27 = a5;
  *(_QWORD *)&pvUser = a3;
  *((_QWORD *)&pvUser + 1) = a4;
  if ( FDICopy(v18, AnsiMuiSafePath, v12, 0, NotifyCallback, 0, &pvUser) )
  {
    v11 = 0;
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids,
      *(unsigned int *)(a1 + 8));
  v19 = *(_DWORD *)(a1 + 8);
  if ( v19 > 6 )
  {
    v24 = v19 - 7;
    if ( !v24 )
      goto LABEL_21;
    v25 = v24 - 1;
    if ( v25 )
    {
      if ( v25 != 3 )
        goto LABEL_21;
    }
    v11 = 1235;
  }
  else
  {
    if ( v19 == 6 || !v19 )
      goto LABEL_21;
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( v20 != 4 )
      {
LABEL_21:
        v11 = 13;
        goto LABEL_22;
      }
LABEL_8:
      v11 = 8;
      goto LABEL_22;
    }
    v11 = 2;
  }
LABEL_22:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, AnsiMuiSafePath);
  if ( v12 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x18000ca5c  push    rbx
0x18000ca5e  push    rbp
0x18000ca5f  push    rsi
0x18000ca60  push    rdi
0x18000ca61  push    r12
0x18000ca63  push    r14
0x18000ca65  push    r15
0x18000ca67  sub     rsp, 60h
0x18000ca6b  xor     eax, eax
0x18000ca6d  xorps   xmm0, xmm0
0x18000ca70  mov     [rsp+98h+var_48], rax
0x18000ca75  mov     r12, r9
0x18000ca78  mov     rbp, r8
0x18000ca7b  mov     rsi, rdx
0x18000ca7e  mov     rbx, rcx
0x18000ca81  movups  [rsp+98h+var_58], xmm0
0x18000ca86  test    rcx, rcx
0x18000ca89  jnz     short loc_18000CA90
0x18000ca8b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ca90  test    rbp, rbp
0x18000ca93  jnz     short loc_18000CA9A
0x18000ca95  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ca9a  mov     rcx, rsi
0x18000ca9d  call    FSGetFileName
0x18000caa2  mov     rcx, rax; unsigned __int16 *
0x18000caa5  call    MemGetAnsiMuiSafePath
0x18000caaa  mov     r15, rax
0x18000caad  test    rax, rax
0x18000cab0  jnz     short loc_18000CABA
0x18000cab2  lea     ebx, [rax+8]
0x18000cab5  jmp     loc_18000CC0F
0x18000caba  mov     rcx, rsi; unsigned __int16 *
0x18000cabd  xor     edi, edi
0x18000cabf  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000cac4  mov     rsi, rax
0x18000cac7  test    rax, rax
0x18000caca  jnz     short loc_18000CAD6
0x18000cacc  mov     ebx, 8
0x18000cad1  jmp     loc_18000CBE2
0x18000cad6  mov     rcx, rsi
0x18000cad9  call    FSSplitFileName
0x18000cade  lea     rdx, asc_180016E08; "\\"
0x18000cae5  mov     rcx, rsi; unsigned __int16 *
0x18000cae8  xor     r8d, r8d
0x18000caeb  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000caf0  mov     r14, rax
0x18000caf3  call    cs:__imp_GetProcessHeap
0x18000caf9  mov     r8, rsi; lpMem
0x18000cafc  xor     edx, edx; dwFlags
0x18000cafe  mov     rcx, rax; hHeap
0x18000cb01  call    cs:__imp_HeapFree
0x18000cb07  test    r14, r14
0x18000cb0a  jz      short loc_18000CACC
0x18000cb0c  mov     rcx, r14; unsigned __int16 *
0x18000cb0f  call    MemGetAnsiMuiSafePath
0x18000cb14  mov     rdi, rax
0x18000cb17  call    cs:__imp_GetProcessHeap
0x18000cb1d  mov     r8, r14; lpMem
0x18000cb20  xor     edx, edx; dwFlags
0x18000cb22  mov     rcx, rax; hHeap
0x18000cb25  call    cs:__imp_HeapFree
0x18000cb2b  test    rdi, rdi
0x18000cb2e  jz      short loc_18000CACC
0x18000cb30  mov     rax, [rsp+98h+arg_20]
0x18000cb38  xor     r9d, r9d; flags
0x18000cb3b  mov     rcx, [rbx]; hfdi
0x18000cb3e  mov     r8, rdi; pszCabPath
0x18000cb41  mov     [rsp+98h+var_48], rax
0x18000cb46  mov     rdx, r15; pszCabinet
0x18000cb49  lea     rax, [rsp+98h+var_58]
0x18000cb4e  mov     qword ptr [rsp+98h+var_58], rbp
0x18000cb53  mov     [rsp+98h+pvUser], rax; pvUser
0x18000cb58  lea     rax, NotifyCallback
0x18000cb5f  mov     [rsp+98h+pfnfdid], 0; pfnfdid
0x18000cb68  mov     [rsp+98h+pfnfdin], rax; pfnfdin
0x18000cb6d  mov     qword ptr [rsp+98h+var_58+8], r12
0x18000cb72  call    cs:__imp_FDICopy
0x18000cb78  test    eax, eax
0x18000cb7a  jz      short loc_18000CB80
0x18000cb7c  xor     ebx, ebx
0x18000cb7e  jmp     short loc_18000CBE2
0x18000cb80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb87  lea     rax, WPP_GLOBAL_Control
0x18000cb8e  cmp     rcx, rax
0x18000cb91  jz      short loc_18000CBB2
0x18000cb93  test    byte ptr [rcx+1Ch], 1
0x18000cb97  jz      short loc_18000CBB2
0x18000cb99  mov     r9d, [rbx+8]
0x18000cb9d  lea     r8, WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids
0x18000cba4  mov     rcx, [rcx+10h]
0x18000cba8  mov     edx, 0Bh
0x18000cbad  call    WPP_SF_d
0x18000cbb2  mov     ecx, [rbx+8]
0x18000cbb5  cmp     ecx, 6
0x18000cbb8  jg      short loc_18000CC27
0x18000cbba  jz      short loc_18000CBDD
0x18000cbbc  test    ecx, ecx
0x18000cbbe  jz      short loc_18000CBDD
0x18000cbc0  sub     ecx, 1
0x18000cbc3  jz      short loc_18000CC20
0x18000cbc5  sub     ecx, 1
0x18000cbc8  jz      short loc_18000CBDD
0x18000cbca  sub     ecx, 1
0x18000cbcd  jz      short loc_18000CBDD
0x18000cbcf  sub     ecx, 1
0x18000cbd2  jz      short loc_18000CBDD
0x18000cbd4  cmp     ecx, 1
0x18000cbd7  jz      loc_18000CACC
0x18000cbdd  mov     ebx, 0Dh
0x18000cbe2  call    cs:__imp_GetProcessHeap
0x18000cbe8  mov     r8, r15; lpMem
0x18000cbeb  xor     edx, edx; dwFlags
0x18000cbed  mov     rcx, rax; hHeap
0x18000cbf0  call    cs:__imp_HeapFree
0x18000cbf6  test    rdi, rdi
0x18000cbf9  jz      short loc_18000CC0F
0x18000cbfb  call    cs:__imp_GetProcessHeap
0x18000cc01  mov     r8, rdi; lpMem
0x18000cc04  xor     edx, edx; dwFlags
0x18000cc06  mov     rcx, rax; hHeap
0x18000cc09  call    cs:__imp_HeapFree
0x18000cc0f  mov     eax, ebx
0x18000cc11  add     rsp, 60h
0x18000cc15  pop     r15
0x18000cc17  pop     r14
0x18000cc19  pop     r12
0x18000cc1b  pop     rdi
0x18000cc1c  pop     rsi
0x18000cc1d  pop     rbp
0x18000cc1e  pop     rbx
0x18000cc1f  retn
0x18000cc20  mov     ebx, 2
0x18000cc25  jmp     short loc_18000CBE2
0x18000cc27  sub     ecx, 7
0x18000cc2a  jz      short loc_18000CBDD
0x18000cc2c  sub     ecx, 1
0x18000cc2f  jz      short loc_18000CC40
0x18000cc31  sub     ecx, 1
0x18000cc34  jz      short loc_18000CBDD
0x18000cc36  sub     ecx, 1
0x18000cc39  jz      short loc_18000CBDD
0x18000cc3b  cmp     ecx, 1
0x18000cc3e  jnz     short loc_18000CBDD
0x18000cc40  mov     ebx, 4D3h
0x18000cc45  jmp     short loc_18000CBE2
```
