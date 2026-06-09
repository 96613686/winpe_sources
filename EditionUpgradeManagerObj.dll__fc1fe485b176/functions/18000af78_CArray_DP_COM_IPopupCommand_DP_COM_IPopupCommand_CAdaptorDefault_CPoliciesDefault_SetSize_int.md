# CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18000af78`
- end: `0x18000b09c`
- name: `?SetSize@?$CArray@V?$DP_COM@UIPopupCommand@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `292`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a4c0`
- `0x18000a6d0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000af78`
- `0x18002295c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b04d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b04d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b085`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000afbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000afbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b03f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b03f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b077`

## pseudocode

```c
__int64 __fastcall CArray<DP_COM<IPopupCommand>,DP_COM<IPopupCommand>,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r15
  void *v10; // r12
  int v11; // ebx
  _QWORD *v12; // r14
  void *v13; // r14
  HANDLE ProcessHeap; // rax
  void *v15; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_20:
    v8 = 0;
    goto LABEL_21;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = v3;
    v10 = v3;
    if ( (int)v2 < *(_DWORD *)(a1 + 4) )
    {
      v11 = v2;
      do
      {
        v12 = (_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * v11);
        if ( v12 && *v12 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 16LL))(*v12);
          *v12 = 0;
        }
        ++v11;
      }
      while ( v11 < *(_DWORD *)(a1 + 4) );
    }
    v13 = *(void **)(a1 + 8);
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *(_QWORD *)(a1 + 8) = 0;
    }
    v15 = 0;
    if ( v9 )
      v15 = v10;
    *(_QWORD *)(a1 + 8) = v15;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_20;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, 8 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 8LL * v5);
    goto LABEL_9;
  }
  v8 = -2147024882;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x18000af78  push    rbx
0x18000af7a  push    rbp
0x18000af7b  push    rsi
0x18000af7c  push    rdi
0x18000af7d  push    r12
0x18000af7f  push    r14
0x18000af81  push    r15
0x18000af83  sub     rsp, 20h
0x18000af87  movsxd  rsi, edx
0x18000af8a  xor     ebx, ebx
0x18000af8c  mov     rdi, rcx
0x18000af8f  cmp     [rcx], esi
0x18000af91  jz      loc_18000B069
0x18000af97  mov     ebp, [rcx+4]
0x18000af9a  cmp     esi, ebp
0x18000af9c  cmovl   ebp, esi
0x18000af9f  test    edx, edx
0x18000afa1  jle     short loc_18000AFF5
0x18000afa3  xor     ecx, ecx
0x18000afa5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000afaa  mov     rbx, rsi
0x18000afad  shl     rbx, 3
0x18000afb1  call    cs:__imp_GetProcessHeap
0x18000afb7  mov     r8, rbx; dwBytes
0x18000afba  xor     edx, edx; dwFlags
0x18000afbc  mov     rcx, rax; hHeap
0x18000afbf  call    cs:__imp_HeapAlloc
0x18000afc5  mov     rbx, rax
0x18000afc8  test    rax, rax
0x18000afcb  jnz     short loc_18000AFDE
0x18000afcd  mov     edi, 8007000Eh
0x18000afd2  mov     ecx, edi
0x18000afd4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000afd9  jmp     loc_18000B06B
0x18000afde  test    ebp, ebp
0x18000afe0  jz      short loc_18000AFF5
0x18000afe2  mov     rdx, [rdi+8]; Src
0x18000afe6  mov     rcx, rax; void *
0x18000afe9  movsxd  r8, ebp
0x18000afec  shl     r8, 3; Size
0x18000aff0  call    memcpy_0
0x18000aff5  mov     r15, rbx
0x18000aff8  mov     r12, rbx
0x18000affb  cmp     esi, [rdi+4]
0x18000affe  jge     short loc_18000B034
0x18000b000  mov     ebx, esi
0x18000b002  mov     rcx, [rdi+8]
0x18000b006  movsxd  rax, ebx
0x18000b009  lea     r14, [rcx+rax*8]
0x18000b00d  test    r14, r14
0x18000b010  jz      short loc_18000B02D
0x18000b012  mov     rcx, [r14]
0x18000b015  test    rcx, rcx
0x18000b018  jz      short loc_18000B02D
0x18000b01a  mov     rax, [rcx]
0x18000b01d  mov     rax, [rax+10h]
0x18000b021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b026  mov     qword ptr [r14], 0
0x18000b02d  inc     ebx
0x18000b02f  cmp     ebx, [rdi+4]
0x18000b032  jl      short loc_18000B002
0x18000b034  mov     r14, [rdi+8]
0x18000b038  xor     ebx, ebx
0x18000b03a  test    r14, r14
0x18000b03d  jz      short loc_18000B057
0x18000b03f  call    cs:__imp_GetProcessHeap
0x18000b045  mov     r8, r14; lpMem
0x18000b048  xor     edx, edx; dwFlags
0x18000b04a  mov     rcx, rax; hHeap
0x18000b04d  call    cs:__imp_HeapFree
0x18000b053  mov     [rdi+8], rbx
0x18000b057  xor     eax, eax
0x18000b059  test    r15, r15
0x18000b05c  cmovnz  rax, r12
0x18000b060  mov     [rdi+8], rax
0x18000b064  mov     [rdi+4], ebp
0x18000b067  mov     [rdi], esi
0x18000b069  xor     edi, edi
0x18000b06b  mov     ecx, edi
0x18000b06d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b072  test    rbx, rbx
0x18000b075  jz      short loc_18000B08B
0x18000b077  call    cs:__imp_GetProcessHeap
0x18000b07d  mov     r8, rbx; lpMem
0x18000b080  xor     edx, edx; dwFlags
0x18000b082  mov     rcx, rax; hHeap
0x18000b085  call    cs:__imp_HeapFree
0x18000b08b  mov     eax, edi
0x18000b08d  add     rsp, 20h
0x18000b091  pop     r15
0x18000b093  pop     r14
0x18000b095  pop     r12
0x18000b097  pop     rdi
0x18000b098  pop     rsi
0x18000b099  pop     rbp
0x18000b09a  pop     rbx
0x18000b09b  retn
```
