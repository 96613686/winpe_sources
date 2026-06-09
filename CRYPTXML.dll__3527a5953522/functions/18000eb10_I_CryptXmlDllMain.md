# I_CryptXmlDllMain

- ea: `0x18000eb10`
- end: `0x18000edc2`
- name: `I_CryptXmlDllMain`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015c70`

## callees

- `0x18000eb10`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18000ebc7`
- `ntdll!RtlImageNtHeader` at `0x18000ebc7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ebae`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ebae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ed70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ed70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ecf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed9e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000eb96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000eb96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec83`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ec83`

## pseudocode

```c
__int64 __fastcall I_CryptXmlDllMain(HMODULE a1, int a2)
{
  unsigned int v2; // edi
  char *v3; // rbx
  char *v4; // rbx
  PIMAGE_NT_HEADERS v6; // rax
  __int64 SizeOfStackCommit; // rdi
  __int64 GuaranteedStackBytes; // rax
  unsigned int v9; // edx
  HANDLE v10; // rax
  unsigned int v11; // edx
  unsigned int i; // esi
  __int64 v13; // r14
  __int64 v14; // rax
  HMODULE v15; // rcx
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rax
  HMODULE v21; // rcx
  void *v22; // rbx
  HANDLE v23; // rax

  if ( a2 )
  {
    if ( a2 != 1 )
      return 1;
    DisableThreadLibraryCalls(a1);
    v6 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
    if ( NtCurrentPeb()->BeingDebugged || !v6 )
    {
      SizeOfStackCommit = 0;
    }
    else
    {
      if ( v6->OptionalHeader.SizeOfStackReserve - v6->OptionalHeader.SizeOfStackCommit < 0x3000 )
      {
        g_ulMaxStackAllocSize = 0;
LABEL_13:
        GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
        g_ulAdditionalProbeSize = GuaranteedStackBytes;
        if ( !GuaranteedStackBytes )
        {
          g_ulAdditionalProbeSize = 12288;
          goto LABEL_8;
        }
        if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
        {
LABEL_8:
          g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
          g_pfnFree = (__int64)SafeAllocaFreeToHeap;
          InitializeCriticalSection(&g_csCryptXmlCriticalSection);
          return 1;
        }
LABEL_22:
        g_ulAdditionalProbeSize = -9;
        goto LABEL_8;
      }
      SizeOfStackCommit = v6->OptionalHeader.SizeOfStackCommit;
    }
    g_ulMaxStackAllocSize = SizeOfStackCommit;
    if ( !v6 )
      goto LABEL_22;
    goto LABEL_13;
  }
  DeleteCriticalSection(&g_csCryptXmlCriticalSection);
  v2 = 0;
  v3 = (char *)qword_180022FD8;
  if ( qword_180022FD8 )
  {
    v11 = dword_180022FC0;
    for ( i = 0; i < v11; ++i )
    {
      v13 = 8LL * i;
      v14 = *(_QWORD *)&v3[v13];
      if ( v14 )
      {
        v15 = *(HMODULE *)(v14 + 80);
        if ( v15 )
        {
          FreeLibrary(v15);
          v16 = *(void **)((char *)qword_180022FD8 + v13);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 8u, v16);
          v11 = dword_180022FC0;
          v3 = (char *)qword_180022FD8;
        }
      }
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 8u, v3);
  }
  v4 = (char *)lpMem;
  if ( lpMem )
  {
    v9 = dword_180022FE0;
    if ( dword_180022FE0 )
    {
      do
      {
        v19 = 8LL * v2;
        v20 = *(_QWORD *)&v4[v19];
        if ( v20 )
        {
          v21 = *(HMODULE *)(v20 + 16);
          if ( v21 )
          {
            FreeLibrary(v21);
            v22 = *(void **)((char *)lpMem + v19);
            v23 = GetProcessHeap();
            HeapFree(v23, 8u, v22);
            v9 = dword_180022FE0;
            v4 = (char *)lpMem;
          }
        }
        ++v2;
      }
      while ( v2 < v9 );
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 8u, v4);
  }
  return 1;
}

```

## disassembly

```asm
0x18000eb10  push    rdi
0x18000eb12  sub     rsp, 20h
0x18000eb16  mov     eax, edx
0x18000eb18  test    edx, edx
0x18000eb1a  jz      loc_18000EC7C
0x18000eb20  cmp     eax, 1
0x18000eb23  jz      loc_18000EBAE
0x18000eb29  test    edx, edx
0x18000eb2b  jnz     short loc_18000EBA2
0x18000eb2d  mov     [rsp+28h+arg_0], rbx
0x18000eb32  xor     edi, edi
0x18000eb34  mov     rbx, cs:qword_180022FD8
0x18000eb3b  mov     [rsp+28h+arg_8], rsi
0x18000eb40  test    rbx, rbx
0x18000eb43  jnz     loc_18000ECAD
0x18000eb49  mov     rbx, cs:lpMem
0x18000eb50  test    rbx, rbx
0x18000eb53  jnz     loc_18000EC46
0x18000eb59  mov     rbx, [rsp+28h+arg_0]
0x18000eb5e  mov     rsi, [rsp+28h+arg_8]
0x18000eb63  jmp     short loc_18000EBA2
0x18000eb65  add     rax, 8
0x18000eb69  cmp     rax, 8
0x18000eb6d  jb      loc_18000EC9D
0x18000eb73  lea     rax, SafeAllocaAllocateFromHeap
0x18000eb7a  mov     cs:g_pfnAllocate, rax
0x18000eb81  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x18000eb88  lea     rax, SafeAllocaFreeToHeap
0x18000eb8f  mov     cs:g_pfnFree, rax
0x18000eb96  call    cs:__imp_InitializeCriticalSection
0x18000eb9d  nop     dword ptr [rax+rax+00h]
0x18000eba2  mov     eax, 1
0x18000eba7  add     rsp, 20h
0x18000ebab  pop     rdi
0x18000ebac  retn
0x18000ebae  call    cs:__imp_DisableThreadLibraryCalls
0x18000ebb5  nop     dword ptr [rax+rax+00h]
0x18000ebba  mov     rcx, gs:60h
0x18000ebc3  mov     rcx, [rcx+10h]; BaseAddress
0x18000ebc7  call    cs:__imp_RtlImageNtHeader
0x18000ebce  nop     dword ptr [rax+rax+00h]
0x18000ebd3  mov     rcx, gs:60h
0x18000ebdc  mov     rdx, rax
0x18000ebdf  cmp     byte ptr [rcx+2], 0
0x18000ebe3  jz      short loc_18000EC26
0x18000ebe5  xor     edi, edi
0x18000ebe7  mov     cs:g_ulMaxStackAllocSize, rdi
0x18000ebee  test    rdx, rdx
0x18000ebf1  jz      loc_18000EC9D
0x18000ebf7  mov     rax, gs:30h
0x18000ec00  mov     eax, [rax+1748h]
0x18000ec06  mov     cs:g_ulAdditionalProbeSize, rax
0x18000ec0d  test    rax, rax
0x18000ec10  jnz     loc_18000EB65
0x18000ec16  mov     cs:g_ulAdditionalProbeSize, 3000h
0x18000ec21  jmp     loc_18000EB73
0x18000ec26  test    rdx, rdx
0x18000ec29  jz      short loc_18000EBE5
0x18000ec2b  mov     rax, [rax+60h]
0x18000ec2f  sub     rax, [rdx+68h]
0x18000ec33  cmp     rax, 3000h
0x18000ec39  jnb     short loc_18000EC94
0x18000ec3b  xor     edi, edi
0x18000ec3d  mov     cs:g_ulMaxStackAllocSize, rdi
0x18000ec44  jmp     short loc_18000EBF7
0x18000ec46  mov     edx, cs:dword_180022FE0
0x18000ec4c  test    edx, edx
0x18000ec4e  jnz     loc_18000ED54
0x18000ec54  call    cs:__imp_GetProcessHeap
0x18000ec5b  nop     dword ptr [rax+rax+00h]
0x18000ec60  mov     r8, rbx; lpMem
0x18000ec63  mov     edx, 8; dwFlags
0x18000ec68  mov     rcx, rax; hHeap
0x18000ec6b  call    cs:__imp_HeapFree
0x18000ec72  nop     dword ptr [rax+rax+00h]
0x18000ec77  jmp     loc_18000EB59
0x18000ec7c  lea     rcx, g_csCryptXmlCriticalSection; lpCriticalSection
0x18000ec83  call    cs:__imp_DeleteCriticalSection
0x18000ec8a  nop     dword ptr [rax+rax+00h]
0x18000ec8f  jmp     loc_18000EB2D
0x18000ec94  mov     rdi, [rdx+68h]
0x18000ec98  jmp     loc_18000EBE7
0x18000ec9d  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18000eca8  jmp     loc_18000EB73
0x18000ecad  mov     edx, cs:dword_180022FC0
0x18000ecb3  mov     esi, edi
0x18000ecb5  test    edx, edx
0x18000ecb7  jz      short loc_18000ED2C
0x18000ecb9  mov     [rsp+28h+arg_10], r14
0x18000ecbe  mov     eax, esi
0x18000ecc0  lea     r14, ds:0[rax*8]
0x18000ecc8  mov     rax, [r14+rbx]
0x18000eccc  test    rax, rax
0x18000eccf  jz      short loc_18000ED21
0x18000ecd1  mov     rcx, [rax+50h]; hLibModule
0x18000ecd5  test    rcx, rcx
0x18000ecd8  jz      short loc_18000ED21
0x18000ecda  call    cs:__imp_FreeLibrary
0x18000ece1  nop     dword ptr [rax+rax+00h]
0x18000ece6  mov     rax, cs:qword_180022FD8
0x18000eced  mov     rbx, [r14+rax]
0x18000ecf1  call    cs:__imp_GetProcessHeap
0x18000ecf8  nop     dword ptr [rax+rax+00h]
0x18000ecfd  mov     r8, rbx; lpMem
0x18000ed00  mov     edx, 8; dwFlags
0x18000ed05  mov     rcx, rax; hHeap
0x18000ed08  call    cs:__imp_HeapFree
0x18000ed0f  nop     dword ptr [rax+rax+00h]
0x18000ed14  mov     edx, cs:dword_180022FC0
0x18000ed1a  mov     rbx, cs:qword_180022FD8
0x18000ed21  inc     esi
0x18000ed23  cmp     esi, edx
0x18000ed25  jb      short loc_18000ECBE
0x18000ed27  mov     r14, [rsp+28h+arg_10]
0x18000ed2c  call    cs:__imp_GetProcessHeap
0x18000ed33  nop     dword ptr [rax+rax+00h]
0x18000ed38  mov     r8, rbx; lpMem
0x18000ed3b  mov     edx, 8; dwFlags
0x18000ed40  mov     rcx, rax; hHeap
0x18000ed43  call    cs:__imp_HeapFree
0x18000ed4a  nop     dword ptr [rax+rax+00h]
0x18000ed4f  jmp     loc_18000EB49
0x18000ed54  mov     eax, edi
0x18000ed56  lea     rsi, ds:0[rax*8]
0x18000ed5e  mov     rax, [rsi+rbx]
0x18000ed62  test    rax, rax
0x18000ed65  jz      short loc_18000EDB7
0x18000ed67  mov     rcx, [rax+10h]; hLibModule
0x18000ed6b  test    rcx, rcx
0x18000ed6e  jz      short loc_18000EDB7
0x18000ed70  call    cs:__imp_FreeLibrary
0x18000ed77  nop     dword ptr [rax+rax+00h]
0x18000ed7c  mov     rax, cs:lpMem
0x18000ed83  mov     rbx, [rsi+rax]
0x18000ed87  call    cs:__imp_GetProcessHeap
0x18000ed8e  nop     dword ptr [rax+rax+00h]
0x18000ed93  mov     r8, rbx; lpMem
0x18000ed96  mov     edx, 8; dwFlags
0x18000ed9b  mov     rcx, rax; hHeap
0x18000ed9e  call    cs:__imp_HeapFree
0x18000eda5  nop     dword ptr [rax+rax+00h]
0x18000edaa  mov     edx, cs:dword_180022FE0
0x18000edb0  mov     rbx, cs:lpMem
0x18000edb7  inc     edi
0x18000edb9  cmp     edi, edx
0x18000edbb  jb      short loc_18000ED54
0x18000edbd  jmp     loc_18000EC54
```
