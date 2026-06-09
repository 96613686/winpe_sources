# AslpTelemetryProcessError

- ea: `0x18002cab0`
- end: `0x18002cc33`
- name: `AslpTelemetryProcessError`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002c4f4`

## callees

- `0x18001b970`
- `0x18002b538`
- `0x18002cab0`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x18002cbe6`
- `ntdll!RtlInitAnsiString` at `0x18002cbe6`
- `ntdll!RtlEnterCriticalSection` at `0x18002caea`
- `ntdll!RtlEnterCriticalSection` at `0x18002caea`
- `ntdll!RtlAllocateHeap` at `0x18002cb9b`
- `ntdll!RtlAllocateHeap` at `0x18002cb9b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002cc2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cad7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cad7`

## pseudocode

```c
NTSTATUS __fastcall AslpTelemetryProcessError(__int64 a1, __int64 a2, __int64 a3, DWORD a4)
{
  __int64 v5; // rdi
  DWORD v7; // ebp
  unsigned __int64 v8; // r9
  unsigned int v9; // r15d
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  SIZE_T v16; // rbp
  char *Heap; // rax
  const char *v18; // rdi
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-48h]
  unsigned __int64 v22; // [rsp+70h] [rbp+8h] BYREF
  __int64 v23; // [rsp+78h] [rbp+10h]
  DWORD CurrentThreadId; // [rsp+88h] [rbp+20h]

  CurrentThreadId = a4;
  v23 = a2;
  v5 = a2;
  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
  v8 = *(_QWORD *)(a1 + 192);
  if ( v8 )
  {
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = 0;
      if ( v10 < v8 )
      {
        v22 = 0;
        if ( (int)ULongLongMult(*(_QWORD *)(a1 + 184), v10, &v22) < 0
          || (v12 = *(_QWORD *)(a1 + 216), v11 = v12 + v22, v12 + v22 < v12) )
        {
          v11 = 0;
        }
      }
      if ( *(_DWORD *)v11 == v7 )
      {
        if ( !*(_QWORD *)(v11 + 32) )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_BYTE *)(v5 + v13) );
          if ( a3 )
          {
            v14 = -1;
            do
              ++v14;
            while ( *(_BYTE *)(a3 + v14) );
            v15 = (unsigned __int16)v14;
          }
          else
          {
            v15 = 16;
          }
          v16 = v15 + (unsigned __int16)v13 + 2LL;
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v16);
          v18 = Heap;
          if ( !Heap )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          if ( a3 )
          {
            v19 = RtlStringCchPrintfA(Heap, v16, "%s#%s", v23, a3);
          }
          else
          {
            LODWORD(v21) = 0;
            v19 = RtlStringCchPrintfA(Heap, v16, "%s#%d", v23, v21);
          }
          if ( v19 < 0 )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          RtlInitAnsiString((PANSI_STRING)(v11 + 24), v18);
          v5 = v23;
          v7 = CurrentThreadId;
        }
        ++*(_DWORD *)(v11 + 40);
      }
      v8 = *(_QWORD *)(a1 + 192);
      v10 = ++v9;
    }
    while ( v9 < v8 );
  }
  return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
}

```

## disassembly

```asm
0x18002cab0  mov     [rsp+arg_10], rbx
0x18002cab5  mov     [rsp+arg_18], r9d
0x18002caba  mov     [rsp+arg_8], rdx
0x18002cabf  push    rbp
0x18002cac0  push    rsi
0x18002cac1  push    rdi
0x18002cac2  push    r12
0x18002cac4  push    r13
0x18002cac6  push    r14
0x18002cac8  push    r15
0x18002caca  sub     rsp, 30h
0x18002cace  mov     r12, r8
0x18002cad1  mov     rdi, rdx
0x18002cad4  mov     rsi, rcx
0x18002cad7  call    cs:__imp_GetCurrentThreadId
0x18002cadd  lea     rcx, [rsi+58h]; CriticalSection
0x18002cae1  mov     [rsp+68h+arg_18], eax
0x18002cae8  mov     ebp, eax
0x18002caea  call    cs:__imp_RtlEnterCriticalSection
0x18002caf0  mov     r9, [rsi+0C0h]
0x18002caf7  test    r9, r9
0x18002cafa  jz      loc_18002CC11
0x18002cb00  xor     r15d, r15d
0x18002cb03  xor     ecx, ecx
0x18002cb05  xor     ebx, ebx
0x18002cb07  cmp     rcx, r9
0x18002cb0a  jnb     short loc_18002CB3F
0x18002cb0c  mov     rdx, rcx; unsigned __int64
0x18002cb0f  mov     [rsp+68h+arg_0], rbx
0x18002cb14  mov     rcx, [rsi+0B8h]; unsigned __int64
0x18002cb1b  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x18002cb20  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002cb25  test    eax, eax
0x18002cb27  js      short loc_18002CB3D
0x18002cb29  mov     rcx, [rsi+0D8h]
0x18002cb30  mov     rbx, [rsp+68h+arg_0]
0x18002cb35  add     rbx, rcx
0x18002cb38  cmp     rbx, rcx
0x18002cb3b  jnb     short loc_18002CB3F
0x18002cb3d  xor     ebx, ebx
0x18002cb3f  cmp     [rbx], ebp
0x18002cb41  jnz     loc_18002CBFB
0x18002cb47  cmp     qword ptr [rbx+20h], 0
0x18002cb4c  jnz     loc_18002CBF8
0x18002cb52  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002cb56  inc     rcx
0x18002cb59  cmp     byte ptr [rdi+rcx], 0
0x18002cb5d  jnz     short loc_18002CB56
0x18002cb5f  test    r12, r12
0x18002cb62  jz      short loc_18002CB77
0x18002cb64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cb68  inc     rax
0x18002cb6b  cmp     byte ptr [r12+rax], 0
0x18002cb70  jnz     short loc_18002CB68
0x18002cb72  movzx   edx, ax
0x18002cb75  jmp     short loc_18002CB7C
0x18002cb77  mov     edx, 10h
0x18002cb7c  movzx   ebp, cx
0x18002cb7f  mov     rcx, gs:60h
0x18002cb88  add     rbp, 2
0x18002cb8c  add     rbp, rdx
0x18002cb8f  mov     edx, 8; Flags
0x18002cb94  mov     r8, rbp; Size
0x18002cb97  mov     rcx, [rcx+30h]; HeapHandle
0x18002cb9b  call    cs:__imp_RtlAllocateHeap
0x18002cba1  mov     rdi, rax
0x18002cba4  test    rax, rax
0x18002cba7  jz      short loc_18002CC11
0x18002cba9  mov     r9, [rsp+68h+arg_8]
0x18002cbae  mov     rdx, rbp; unsigned __int64
0x18002cbb1  mov     rcx, rax; char *
0x18002cbb4  test    r12, r12
0x18002cbb7  jz      short loc_18002CBC7
0x18002cbb9  mov     [rsp+68h+var_48], r12
0x18002cbbe  lea     r8, aSS_0; "%s#%s"
0x18002cbc5  jmp     short loc_18002CBD6
0x18002cbc7  mov     dword ptr [rsp+68h+var_48], 0
0x18002cbcf  lea     r8, aSD_0; "%s#%d"
0x18002cbd6  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002cbdb  test    eax, eax
0x18002cbdd  js      short loc_18002CC11
0x18002cbdf  mov     rdx, rdi; SourceString
0x18002cbe2  lea     rcx, [rbx+18h]; DestinationString
0x18002cbe6  call    cs:__imp_RtlInitAnsiString
0x18002cbec  mov     rdi, [rsp+68h+arg_8]
0x18002cbf1  mov     ebp, [rsp+68h+arg_18]
0x18002cbf8  inc     dword ptr [rbx+28h]
0x18002cbfb  mov     r9, [rsi+0C0h]
0x18002cc02  inc     r15d
0x18002cc05  mov     ecx, r15d
0x18002cc08  cmp     rcx, r9
0x18002cc0b  jb      loc_18002CB05
0x18002cc11  lea     rcx, [rsi+58h]
0x18002cc15  mov     rbx, [rsp+68h+arg_10]
0x18002cc1d  add     rsp, 30h
0x18002cc21  pop     r15
0x18002cc23  pop     r14
0x18002cc25  pop     r13
0x18002cc27  pop     r12
0x18002cc29  pop     rdi
0x18002cc2a  pop     rsi
0x18002cc2b  pop     rbp
0x18002cc2c  jmp     cs:__imp_RtlLeaveCriticalSection
```
