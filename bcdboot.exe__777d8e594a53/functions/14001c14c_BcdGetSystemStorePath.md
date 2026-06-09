# BcdGetSystemStorePath

- ea: `0x14001c14c`
- end: `0x14001c3a1`
- name: `BcdGetSystemStorePath`
- size: `597`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400045c8`
- `0x14001a964`
- `0x14001b1f4`
- `0x14001b764`

## callees

- `0x1400133e4`
- `0x14001c14c`
- `0x14001c3a8`
- `0x14001c458`
- `0x140020678`
- `0x140027010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14001c20b`
- `msvcrt!wcscpy_s` at `0x14001c332`
- `msvcrt!wcscpy_s` at `0x14001c20b`
- `msvcrt!wcscpy_s` at `0x14001c332`
- `msvcrt!wcscat_s` at `0x14001c21e`
- `msvcrt!wcscat_s` at `0x14001c341`
- `msvcrt!wcscat_s` at `0x14001c21e`
- `msvcrt!wcscat_s` at `0x14001c341`
- `ntdll!RtlAllocateHeap` at `0x14001c1ea`
- `ntdll!RtlAllocateHeap` at `0x14001c314`
- `ntdll!RtlAllocateHeap` at `0x14001c1ea`
- `ntdll!RtlAllocateHeap` at `0x14001c314`
- `ntdll!RtlFreeHeap` at `0x14001c361`
- `ntdll!RtlFreeHeap` at `0x14001c382`
- `ntdll!RtlFreeHeap` at `0x14001c361`
- `ntdll!RtlFreeHeap` at `0x14001c382`

## string_xrefs

- `0x14001c254`: `Failed to get system store path. Status: %x`
- `0x14001c280`: `System store path: %s`
- `0x14001c211`: `system32\config\BootBCD`
- `0x14001c227`: `Using cached BCD path: %s`

## pseudocode

```c
__int64 __fastcall BcdGetSystemStorePath(wchar_t **a1)
{
  wchar_t *v2; // rsi
  int FirmwareType; // edx
  char v4; // al
  const wchar_t *v5; // rbp
  rsize_t v6; // rbx
  wchar_t *Heap; // rax
  wchar_t *v8; // rdi
  int v9; // ebx
  int v10; // edx
  const wchar_t *v11; // rbp
  int SystemPartition; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // r14d
  wchar_t *v16; // rax
  wchar_t *Source; // [rsp+58h] [rbp+10h] BYREF
  __int64 v19; // [rsp+60h] [rbp+18h] BYREF

  v19 = 0;
  v2 = 0;
  Source = 0;
  FirmwareType = BiGetFirmwareType(&v19);
  if ( (v19 & 0x10000) != 0 )
  {
    Source = 0;
    if ( (int)BiLookupNtdllProcedureAddress("RtlIsStateSeparationEnabled") >= 0 )
      v4 = ((__int64 (*)(void))Source)();
    else
      v4 = 0;
    v5 = L"\\OSDataRoot\\Windows\\";
    if ( !v4 )
      v5 = L"\\SystemRoot\\";
    v6 = v4 != 0 ? 44LL : 36LL;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v6);
    v8 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    wcscpy_s(Heap, v6, v5);
    wcscat_s(v8, v6, L"system32\\config\\BootBCD");
    BiLogMessage(2, L"Using cached BCD path: %s", v8);
    v9 = 0;
    goto LABEL_23;
  }
  v10 = FirmwareType - 1;
  if ( v10 )
  {
    if ( (unsigned int)(v10 - 1) >= 2 )
    {
      v9 = -1073741637;
      BiLogMessage(4, L"Failed to get system store path. Status: %x", 3221225659LL);
      return (unsigned int)v9;
    }
    v11 = L"\\EFI\\Microsoft\\Boot\\BCD";
  }
  else
  {
    v11 = L"\\Boot\\BCD";
  }
  BiLogMessage(2, L"System store path: %s", v11);
  SystemPartition = BiGetSystemPartition(&Source);
  v9 = SystemPartition;
  if ( SystemPartition >= 0 )
  {
    v2 = Source;
    BiLogMessage(2, L"System partition: %s", Source);
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v11[v14] );
    do
      ++v13;
    while ( v2[v13] );
    v15 = v14 + v13 + 1;
    v16 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v15);
    v8 = v16;
    if ( v16 )
    {
      wcscpy_s(v16, v15, v2);
      wcscat_s(v8, v15, v11);
LABEL_23:
      *a1 = v8;
      goto LABEL_24;
    }
    v9 = -1073741801;
  }
  else
  {
    v8 = 0;
    BiLogMessage(4, L"Failed to get system partition. Status: %x", (unsigned int)SystemPartition);
    v2 = Source;
  }
LABEL_24:
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v9 < 0 && v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001c14c  mov     rax, rsp
0x14001c14f  mov     [rax+8], rbx
0x14001c153  mov     [rax+20h], rbp
0x14001c157  push    rsi
0x14001c158  push    rdi
0x14001c159  push    r12
0x14001c15b  push    r14
0x14001c15d  push    r15
0x14001c15f  sub     rsp, 20h
0x14001c163  xor     r12d, r12d
0x14001c166  mov     r15, rcx
0x14001c169  lea     rcx, [rax+18h]
0x14001c16d  mov     [rax+18h], r12
0x14001c171  mov     esi, r12d
0x14001c174  mov     [rax+10h], r12
0x14001c178  call    BiGetFirmwareType
0x14001c17d  test    [rsp+48h+arg_10], 10000h
0x14001c186  mov     edx, eax
0x14001c188  jz      loc_14001C240
0x14001c18e  lea     rdx, [rsp+48h+Source]
0x14001c193  mov     [rsp+48h+Source], r12
0x14001c198  lea     rcx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x14001c19f  call    BiLookupNtdllProcedureAddress
0x14001c1a4  test    eax, eax
0x14001c1a6  jns     short loc_14001C1AD
0x14001c1a8  mov     al, r12b
0x14001c1ab  jmp     short loc_14001C1B7
0x14001c1ad  mov     rax, [rsp+48h+Source]
0x14001c1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c1b7  test    al, al
0x14001c1b9  lea     rcx, aSystemroot; "\\SystemRoot\\"
0x14001c1c0  lea     rbp, aOsdatarootWind; "\\OSDataRoot\\Windows\\"
0x14001c1c7  cmovz   rbp, rcx
0x14001c1cb  mov     rcx, gs:60h
0x14001c1d4  neg     al
0x14001c1d6  sbb     rbx, rbx
0x14001c1d9  xor     edx, edx; Flags
0x14001c1db  mov     rcx, [rcx+30h]; HeapHandle
0x14001c1df  and     ebx, 8
0x14001c1e2  add     rbx, 24h ; '$'
0x14001c1e6  lea     r8, [rbx+rbx]; Size
0x14001c1ea  call    cs:__imp_RtlAllocateHeap
0x14001c1f0  mov     rdi, rax
0x14001c1f3  test    rax, rax
0x14001c1f6  jnz     short loc_14001C202
0x14001c1f8  mov     ebx, 0C0000017h
0x14001c1fd  jmp     loc_14001C388
0x14001c202  mov     r8, rbp; Source
0x14001c205  mov     rdx, rbx; SizeInWords
0x14001c208  mov     rcx, rdi; Destination
0x14001c20b  call    cs:__imp_wcscpy_s
0x14001c211  lea     r8, aSystem32Config_0; "system32\\config\\BootBCD"
0x14001c218  mov     rdx, rbx; SizeInWords
0x14001c21b  mov     rcx, rdi; Destination
0x14001c21e  call    cs:__imp_wcscat_s
0x14001c224  mov     r8, rdi
0x14001c227  lea     rdx, aUsingCachedBcd; "Using cached BCD path: %s"
0x14001c22e  mov     ecx, 2
0x14001c233  call    BiLogMessage
0x14001c238  mov     ebx, r12d
0x14001c23b  jmp     loc_14001C347
0x14001c240  sub     edx, 1
0x14001c243  jz      short loc_14001C276
0x14001c245  sub     edx, 1
0x14001c248  jz      short loc_14001C26D
0x14001c24a  cmp     edx, 1
0x14001c24d  jz      short loc_14001C26D
0x14001c24f  mov     ebx, 0C00000BBh
0x14001c254  lea     rdx, aFailedToGetSys_1; "Failed to get system store path. Status"...
0x14001c25b  mov     r8d, ebx
0x14001c25e  mov     ecx, 4
0x14001c263  call    BiLogMessage
0x14001c268  jmp     loc_14001C388
0x14001c26d  lea     rbp, aEfiMicrosoftBo_2; "\\EFI\\Microsoft\\Boot\\BCD"
0x14001c274  jmp     short loc_14001C27D
0x14001c276  lea     rbp, aBootBcd_0; "\\Boot\\BCD"
0x14001c27d  mov     r8, rbp
0x14001c280  lea     rdx, aSystemStorePat; "System store path: %s"
0x14001c287  mov     ecx, 2
0x14001c28c  call    BiLogMessage
0x14001c291  lea     rcx, [rsp+48h+Source]
0x14001c296  call    BiGetSystemPartition
0x14001c29b  mov     ebx, eax
0x14001c29d  test    eax, eax
0x14001c29f  jns     short loc_14001C2C2
0x14001c2a1  mov     r8d, eax
0x14001c2a4  lea     rdx, aFailedToGetSys_0; "Failed to get system partition. Status:"...
0x14001c2ab  mov     ecx, 4
0x14001c2b0  mov     rdi, r12
0x14001c2b3  call    BiLogMessage
0x14001c2b8  mov     rsi, [rsp+48h+Source]
0x14001c2bd  jmp     loc_14001C34A
0x14001c2c2  mov     rsi, [rsp+48h+Source]
0x14001c2c7  lea     rdx, aSystemPartitio_2; "System partition: %s"
0x14001c2ce  mov     r8, rsi
0x14001c2d1  mov     ecx, 2
0x14001c2d6  call    BiLogMessage
0x14001c2db  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c2df  mov     rcx, rax
0x14001c2e2  inc     rcx
0x14001c2e5  cmp     [rbp+rcx*2+0], r12w
0x14001c2eb  jnz     short loc_14001C2E2
0x14001c2ed  inc     rax
0x14001c2f0  cmp     [rsi+rax*2], r12w
0x14001c2f5  jnz     short loc_14001C2ED
0x14001c2f7  lea     r14, [rax+1]
0x14001c2fb  xor     edx, edx; Flags
0x14001c2fd  add     r14, rcx
0x14001c300  mov     rcx, gs:60h
0x14001c309  mov     r14d, r14d
0x14001c30c  mov     rcx, [rcx+30h]; HeapHandle
0x14001c310  lea     r8, [r14+r14]; Size
0x14001c314  call    cs:__imp_RtlAllocateHeap
0x14001c31a  mov     rdi, rax
0x14001c31d  test    rax, rax
0x14001c320  jnz     short loc_14001C329
0x14001c322  mov     ebx, 0C0000017h
0x14001c327  jmp     short loc_14001C34A
0x14001c329  mov     r8, rsi; Source
0x14001c32c  mov     rdx, r14; SizeInWords
0x14001c32f  mov     rcx, rdi; Destination
0x14001c332  call    cs:__imp_wcscpy_s
0x14001c338  mov     r8, rbp; Source
0x14001c33b  mov     rdx, r14; SizeInWords
0x14001c33e  mov     rcx, rdi; Destination
0x14001c341  call    cs:__imp_wcscat_s
0x14001c347  mov     [r15], rdi
0x14001c34a  test    rsi, rsi
0x14001c34d  jz      short loc_14001C367
0x14001c34f  mov     rcx, gs:60h
0x14001c358  mov     r8, rsi; P
0x14001c35b  xor     edx, edx; Flags
0x14001c35d  mov     rcx, [rcx+30h]; HeapHandle
0x14001c361  call    cs:__imp_RtlFreeHeap
0x14001c367  test    ebx, ebx
0x14001c369  jns     short loc_14001C388
0x14001c36b  test    rdi, rdi
0x14001c36e  jz      short loc_14001C388
0x14001c370  mov     rcx, gs:60h
0x14001c379  mov     r8, rdi; P
0x14001c37c  xor     edx, edx; Flags
0x14001c37e  mov     rcx, [rcx+30h]; HeapHandle
0x14001c382  call    cs:__imp_RtlFreeHeap
0x14001c388  mov     rbp, [rsp+48h+arg_18]
0x14001c38d  mov     eax, ebx
0x14001c38f  mov     rbx, [rsp+48h+arg_0]
0x14001c394  add     rsp, 20h
0x14001c398  pop     r15
0x14001c39a  pop     r14
0x14001c39c  pop     r12
0x14001c39e  pop     rdi
0x14001c39f  pop     rsi
0x14001c3a0  retn
```
