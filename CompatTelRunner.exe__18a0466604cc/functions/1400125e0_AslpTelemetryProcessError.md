# AslpTelemetryProcessError

- ea: `0x1400125e0`
- end: `0x14001274f`
- name: `AslpTelemetryProcessError`
- size: `367`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000be78`

## callees

- `0x1400113b4`
- `0x1400125e0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x140012748`
- `ntdll!RtlInitAnsiString` at `0x140012702`
- `ntdll!RtlInitAnsiString` at `0x140012702`
- `ntdll!RtlEnterCriticalSection` at `0x14001261a`
- `ntdll!RtlEnterCriticalSection` at `0x14001261a`
- `ntdll!RtlAllocateHeap` at `0x1400126b7`
- `ntdll!RtlAllocateHeap` at `0x1400126b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012607`

## pseudocode

```c
NTSTATUS __fastcall AslpTelemetryProcessError(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  DWORD v6; // ebp
  unsigned __int64 v7; // r9
  unsigned int i; // r14d
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  SIZE_T v15; // rbp
  char *Heap; // rax
  const char *v17; // rdi
  int v18; // eax
  __int64 v20; // [rsp+20h] [rbp-48h]
  DWORD CurrentThreadId; // [rsp+88h] [rbp+20h]

  v4 = a2;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CurrentThreadId;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
  v7 = *(_QWORD *)(a1 + 192);
  if ( v7 )
  {
    for ( i = 0; i < v7; ++i )
    {
      v9 = 0;
      if ( i < v7 )
      {
        v10 = *(_QWORD *)(a1 + 184) * i;
        if ( !is_mul_ok(*(_QWORD *)(a1 + 184), i) || (v11 = *(_QWORD *)(a1 + 216), v9 = v11 + v10, v11 + v10 < v11) )
          v9 = 0;
      }
      if ( *(_DWORD *)v9 == v6 )
      {
        if ( !*(_QWORD *)(v9 + 32) )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_BYTE *)(v4 + v12) );
          if ( a3 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *(_BYTE *)(a3 + v13) );
            v14 = (unsigned __int16)v13;
          }
          else
          {
            v14 = 16;
          }
          v15 = v14 + (unsigned __int16)v12 + 2LL;
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
          v17 = Heap;
          if ( !Heap )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          if ( a3 )
          {
            v18 = RtlStringCchPrintfA(Heap, v15, "%s#%s", a2, a3);
          }
          else
          {
            LODWORD(v20) = 0;
            v18 = RtlStringCchPrintfA(Heap, v15, "%s#%d", a2, v20);
          }
          if ( v18 < 0 )
            return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
          RtlInitAnsiString((PANSI_STRING)(v9 + 24), v17);
          v4 = a2;
          v6 = CurrentThreadId;
        }
        ++*(_DWORD *)(v9 + 40);
      }
      v7 = *(_QWORD *)(a1 + 192);
    }
  }
  return RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
}

```

## disassembly

```asm
0x1400125e0  mov     [rsp+arg_10], rbx
0x1400125e5  mov     [rsp+arg_18], r9d
0x1400125ea  mov     [rsp+arg_8], rdx
0x1400125ef  push    rbp
0x1400125f0  push    rsi
0x1400125f1  push    rdi
0x1400125f2  push    r12
0x1400125f4  push    r13
0x1400125f6  push    r14
0x1400125f8  push    r15
0x1400125fa  sub     rsp, 30h
0x1400125fe  mov     r12, r8
0x140012601  mov     rdi, rdx
0x140012604  mov     rsi, rcx
0x140012607  call    cs:__imp_GetCurrentThreadId
0x14001260d  lea     rcx, [rsi+58h]; CriticalSection
0x140012611  mov     [rsp+68h+arg_18], eax
0x140012618  mov     ebp, eax
0x14001261a  call    cs:__imp_RtlEnterCriticalSection
0x140012620  mov     r9, [rsi+0C0h]
0x140012627  test    r9, r9
0x14001262a  jz      loc_14001272D
0x140012630  xor     r14d, r14d
0x140012633  xor     ebx, ebx
0x140012635  mov     eax, r14d
0x140012638  cmp     rax, r9
0x14001263b  jnb     short loc_14001265B
0x14001263d  mul     qword ptr [rsi+0B8h]
0x140012644  test    rdx, rdx
0x140012647  jnz     short loc_140012659
0x140012649  mov     rcx, [rsi+0D8h]
0x140012650  lea     rbx, [rcx+rax]
0x140012654  cmp     rbx, rcx
0x140012657  jnb     short loc_14001265B
0x140012659  xor     ebx, ebx
0x14001265b  cmp     [rbx], ebp
0x14001265d  jnz     loc_140012717
0x140012663  cmp     qword ptr [rbx+20h], 0
0x140012668  jnz     loc_140012714
0x14001266e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140012672  inc     rcx
0x140012675  cmp     byte ptr [rdi+rcx], 0
0x140012679  jnz     short loc_140012672
0x14001267b  test    r12, r12
0x14001267e  jz      short loc_140012693
0x140012680  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012684  inc     rax
0x140012687  cmp     byte ptr [r12+rax], 0
0x14001268c  jnz     short loc_140012684
0x14001268e  movzx   edx, ax
0x140012691  jmp     short loc_140012698
0x140012693  mov     edx, 10h
0x140012698  movzx   ebp, cx
0x14001269b  mov     rcx, gs:60h
0x1400126a4  add     rbp, 2
0x1400126a8  add     rbp, rdx
0x1400126ab  mov     edx, 8; Flags
0x1400126b0  mov     r8, rbp; Size
0x1400126b3  mov     rcx, [rcx+30h]; HeapHandle
0x1400126b7  call    cs:__imp_RtlAllocateHeap
0x1400126bd  mov     rdi, rax
0x1400126c0  test    rax, rax
0x1400126c3  jz      short loc_14001272D
0x1400126c5  mov     r9, [rsp+68h+arg_8]
0x1400126ca  mov     rdx, rbp; unsigned __int64
0x1400126cd  mov     rcx, rax; char *
0x1400126d0  test    r12, r12
0x1400126d3  jz      short loc_1400126E3
0x1400126d5  mov     [rsp+68h+var_48], r12
0x1400126da  lea     r8, aSS_0; "%s#%s"
0x1400126e1  jmp     short loc_1400126F2
0x1400126e3  mov     dword ptr [rsp+68h+var_48], 0
0x1400126eb  lea     r8, aSD_0; "%s#%d"
0x1400126f2  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400126f7  test    eax, eax
0x1400126f9  js      short loc_14001272D
0x1400126fb  mov     rdx, rdi; SourceString
0x1400126fe  lea     rcx, [rbx+18h]; DestinationString
0x140012702  call    cs:__imp_RtlInitAnsiString
0x140012708  mov     rdi, [rsp+68h+arg_8]
0x14001270d  mov     ebp, [rsp+68h+arg_18]
0x140012714  inc     dword ptr [rbx+28h]
0x140012717  mov     r9, [rsi+0C0h]
0x14001271e  inc     r14d
0x140012721  mov     eax, r14d
0x140012724  cmp     rax, r9
0x140012727  jb      loc_140012633
0x14001272d  lea     rcx, [rsi+58h]
0x140012731  mov     rbx, [rsp+68h+arg_10]
0x140012739  add     rsp, 30h
0x14001273d  pop     r15
0x14001273f  pop     r14
0x140012741  pop     r13
0x140012743  pop     r12
0x140012745  pop     rdi
0x140012746  pop     rsi
0x140012747  pop     rbp
0x140012748  jmp     cs:__imp_RtlLeaveCriticalSection
```
