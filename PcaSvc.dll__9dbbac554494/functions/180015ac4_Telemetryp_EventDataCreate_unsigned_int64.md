# Telemetryp_EventDataCreate(unsigned __int64)

- ea: `0x180015ac4`
- end: `0x180015e4e`
- name: `?Telemetryp_EventDataCreate@@YAK_K@Z`
- size: `906`
- prototype: `unsigned int __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180016290`

## callees

- `0x180012920`
- `0x1800133c0`
- `0x180013fac`
- `0x180015ac4`
- `0x18007a9cf`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180015c63`
- `ntdll!RtlLeaveCriticalSection` at `0x180015c63`
- `ntdll!RtlEnterCriticalSection` at `0x180015c0f`
- `ntdll!RtlEnterCriticalSection` at `0x180015c0f`
- `ntdll!RtlDeleteCriticalSection` at `0x180015e2b`
- `ntdll!RtlDeleteCriticalSection` at `0x180015e2b`
- `ntdll!RtlInitializeCriticalSection` at `0x180015b1d`
- `ntdll!RtlInitializeCriticalSection` at `0x180015b1d`
- `ntdll!RtlFreeHeap` at `0x180015e43`
- `ntdll!RtlFreeHeap` at `0x180015e43`
- `ntdll!RtlReAllocateHeap` at `0x180015d55`
- `ntdll!RtlReAllocateHeap` at `0x180015d55`
- `ntdll!RtlAllocateHeap` at `0x180015b08`
- `ntdll!RtlAllocateHeap` at `0x180015d1f`
- `ntdll!RtlAllocateHeap` at `0x180015b08`
- `ntdll!RtlAllocateHeap` at `0x180015d1f`

## string_xrefs

- `0x180015bf4`: `Telemetryp_EventDataCreate`
- `0x180015c9c`: `Telemetryp_EventDataCreate`
- `0x180015dad`: `Telemetryp_EventDataCreate`
- `0x180015dc6`: `Failed to copy User Sid [%d]`
- `0x180015dba`: `Failed to copy executable path [%d]`

## pseudocode

```c
__int64 __fastcall Telemetryp_EventDataCreate(unsigned __int64 a1)
{
  int v2; // esi
  struct _PCA_CHAIN *v3; // rbx
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  ULONG_PTR SpinCount; // rcx
  size_t *v7; // r8
  size_t *v8; // r8
  unsigned int v9; // r11d
  unsigned __int64 v10; // r15
  struct _RTL_CRITICAL_SECTION **v11; // rbx
  struct _RTL_CRITICAL_SECTION **v12; // rax
  unsigned int v13; // ebx
  unsigned __int64 v15; // r14
  unsigned __int128 v16; // rax
  SIZE_T v17; // r12
  struct _RTL_CRITICAL_SECTION **v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  const char *v21; // r9
  size_t v22; // [rsp+20h] [rbp-38h]
  size_t v23; // [rsp+20h] [rbp-38h]

  v2 = *((_DWORD *)PcapChainFromHandle(a1) + 4);
  v3 = PcapChainFromHandle(a1);
  Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1648u);
  v5 = Heap;
  if ( !Heap )
  {
    v13 = 14;
    AslLogCallPrintf(1, (unsigned int)"Telemetryp_EventDataCreate", 580, (unsigned int)"Out of memory");
    return v13;
  }
  RtlInitializeCriticalSection(Heap);
  LODWORD(v5[1].OwningThread) = *((_DWORD *)v3 + 1193) != 0;
  SpinCount = v5[99].SpinCount;
  v7 = (size_t *)(SpinCount | 0x2000000);
  v5[99].SpinCount = SpinCount | 0x2000000;
  if ( *((_WORD *)v3 + 2352) == 332 )
  {
    v19 = 0x1002000000LL;
    goto LABEL_30;
  }
  if ( *((_WORD *)v3 + 2352) == 452 )
  {
    v19 = 0x4002000000LL;
LABEL_30:
    v5[99].SpinCount = v19 | SpinCount;
    goto LABEL_6;
  }
  if ( *((unsigned __int16 *)v3 + 2352) == 34404 )
  {
    v7 = (size_t *)(SpinCount | 0x2002000000LL);
    v5[99].SpinCount = SpinCount | 0x2002000000LL;
  }
LABEL_6:
  LODWORD(v5[1].DebugInfo) = 26;
  LODWORD(v5[100].DebugInfo) = v2;
  LODWORD(v5[55].OwningThread) = 0;
  HIDWORD(v5[99].DebugInfo) = 0;
  LODWORD(v5[99].LockSemaphore) = 0;
  *(_QWORD *)&v5[129].LockCount = 0;
  HIDWORD(v5[129].OwningThread) = 0;
  if ( StringCopyWorkerW((STRSAFE_LPWSTR)&v5[103], 0x104u, v7, (STRSAFE_PCNZWCH)v3 + 1568, v22) < 0 )
  {
    v13 = 122;
    v20 = 640;
    v21 = "Failed to copy executable path [%d]";
LABEL_35:
    LODWORD(v23) = v13;
    AslLogCallPrintf(1, (unsigned int)"Telemetryp_EventDataCreate", v20, (_DWORD)v21, v23);
    RtlDeleteCriticalSection(v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    return v13;
  }
  *(_QWORD *)&v5[1].LockCount = *((_QWORD *)v3 + 590);
  if ( StringCopyWorkerW((STRSAFE_LPWSTR)&v5[116], v9, v8, (STRSAFE_PCNZWCH)v3 + 18, v23) < 0 )
  {
    LODWORD(v23) = 122;
    AslLogCallPrintf(
      1,
      (unsigned int)"Telemetryp_EventDataCreate",
      656,
      (unsigned int)"Failed to copy User Sid [%d]",
      v23);
    LOWORD(v5[116].DebugInfo) = 0;
  }
  RtlEnterCriticalSection(&g_TelemetryQueueLock);
  v10 = xmmword_180159908;
  if ( (unsigned __int64)xmmword_180159908 >= *((_QWORD *)&xmmword_180159908 + 1) )
  {
    if ( (unsigned __int64)(xmmword_180159908 + 1) <= *((_QWORD *)&xmmword_180159908 + 1) )
    {
      v13 = -1073741811;
      goto LABEL_14;
    }
    if ( (_QWORD)xmmword_180159918 + (_QWORD)xmmword_180159908 < (unsigned __int64)(xmmword_180159908 + 1) )
      goto LABEL_13;
    if ( !is_mul_ok(*((unsigned __int64 *)&xmmword_180159908 + 1), (unsigned __int64)*(&g_TelemetryQueue + 1)) )
      goto LABEL_13;
    v15 = (xmmword_180159918 + xmmword_180159908) & ~(xmmword_180159918 - 1);
    v16 = v15 * (unsigned __int128)(unsigned __int64)*(&g_TelemetryQueue + 1);
    v17 = v15 * (_QWORD)*(&g_TelemetryQueue + 1);
    if ( !is_mul_ok(v15, (unsigned __int64)*(&g_TelemetryQueue + 1)) )
      goto LABEL_13;
    if ( *((_QWORD *)&xmmword_180159918 + 1) )
    {
      v11 = (struct _RTL_CRITICAL_SECTION **)RtlReAllocateHeap(
                                               g_TelemetryQueue,
                                               DWORD2(v16),
                                               *((PVOID *)&xmmword_180159918 + 1),
                                               v17);
    }
    else
    {
      v18 = (struct _RTL_CRITICAL_SECTION **)RtlAllocateHeap(g_TelemetryQueue, DWORD2(v16), v16);
      v11 = v18;
      if ( v18 )
        memset_0(v18, 0, v17);
    }
    if ( !v11 )
    {
      v13 = -1073741801;
      goto LABEL_14;
    }
    *((_QWORD *)&xmmword_180159918 + 1) = v11;
    *((_QWORD *)&xmmword_180159908 + 1) = v15;
  }
  else
  {
    v11 = (struct _RTL_CRITICAL_SECTION **)*((_QWORD *)&xmmword_180159918 + 1);
  }
  if ( !is_mul_ok((unsigned __int64)*(&g_TelemetryQueue + 1), v10)
    || (v12 = (struct _RTL_CRITICAL_SECTION **)((char *)v11 + (_QWORD)*(&g_TelemetryQueue + 1) * v10), v12 < v11) )
  {
LABEL_13:
    v13 = -1073741675;
    goto LABEL_14;
  }
  *v12 = v5;
  *(_QWORD *)&xmmword_180159908 = xmmword_180159908 + 1;
  v13 = 0;
LABEL_14:
  RtlLeaveCriticalSection(&g_TelemetryQueueLock);
  if ( v13 )
  {
    v20 = 669;
    v21 = "Failed to queue telemetry event [%d]";
    goto LABEL_35;
  }
  return v13;
}

```

## disassembly

```asm
0x180015ac4  mov     [rsp+arg_0], rbx
0x180015ac9  mov     [rsp+arg_10], rbp
0x180015ace  push    rsi
0x180015acf  push    rdi
0x180015ad0  push    r12
0x180015ad2  push    r14
0x180015ad4  push    r15
0x180015ad6  sub     rsp, 30h
0x180015ada  mov     rbx, rcx
0x180015add  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180015ae2  mov     rcx, rbx; unsigned __int64
0x180015ae5  mov     esi, [rax+10h]
0x180015ae8  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180015aed  mov     rcx, gs:60h
0x180015af6  mov     edx, 8; Flags
0x180015afb  mov     r8d, 1648h; Size
0x180015b01  mov     rbx, rax
0x180015b04  mov     rcx, [rcx+30h]; HeapHandle
0x180015b08  call    cs:__imp_RtlAllocateHeap
0x180015b0e  mov     rdi, rax
0x180015b11  test    rax, rax
0x180015b14  jz      loc_180015C8A
0x180015b1a  mov     rcx, rax; CriticalSection
0x180015b1d  call    cs:__imp_RtlInitializeCriticalSection
0x180015b23  xor     eax, eax
0x180015b25  cmp     [rbx+12A4h], eax
0x180015b2b  setnz   al
0x180015b2e  mov     [rdi+38h], eax
0x180015b31  mov     rcx, [rdi+0F98h]
0x180015b38  mov     r8, rcx
0x180015b3b  bts     r8, 19h; pcchNewDestLength
0x180015b40  mov     [rdi+0F98h], r8
0x180015b47  movzx   edx, word ptr [rbx+1260h]
0x180015b4e  sub     edx, 14Ch
0x180015b54  jz      loc_180015D8F
0x180015b5a  sub     edx, 78h ; 'x'
0x180015b5d  jz      loc_180015D83
0x180015b63  cmp     edx, 84A0h
0x180015b69  jz      loc_180015D6A
0x180015b6f  mov     dword ptr [rdi+28h], 1Ah
0x180015b76  lea     r9, [rbx+0C40h]; pszSrc
0x180015b7d  mov     [rdi+0FA0h], esi
0x180015b83  lea     rcx, [rdi+1018h]; pszDest
0x180015b8a  mov     dword ptr [rdi+8A8h], 0
0x180015b94  mov     r11d, 104h
0x180015b9a  mov     dword ptr [rdi+0F7Ch], 0
0x180015ba4  mov     edx, r11d; cchDest
0x180015ba7  mov     dword ptr [rdi+0F90h], 0
0x180015bb1  mov     qword ptr [rdi+1430h], 0
0x180015bbc  mov     dword ptr [rdi+143Ch], 0
0x180015bc6  call    StringCopyWorkerW
0x180015bcb  test    eax, eax
0x180015bcd  js      loc_180015DA8
0x180015bd3  mov     rax, [rbx+1270h]
0x180015bda  lea     r14, [rdi+1220h]
0x180015be1  mov     rcx, r14; pszDest
0x180015be4  mov     [rdi+30h], rax
0x180015be8  lea     r9, [rbx+24h]; pszSrc
0x180015bec  mov     edx, r11d; cchDest
0x180015bef  call    StringCopyWorkerW
0x180015bf4  lea     rbp, aTelemetrypEven_3; "Telemetryp_EventDataCreate"
0x180015bfb  mov     esi, 1
0x180015c00  test    eax, eax
0x180015c02  js      loc_180015DC6
0x180015c08  lea     rcx, ?g_TelemetryQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180015c0f  call    cs:__imp_RtlEnterCriticalSection
0x180015c15  mov     rdx, qword ptr cs:xmmword_180159908+8; Flags
0x180015c1c  mov     r15, qword ptr cs:xmmword_180159908
0x180015c23  cmp     r15, rdx
0x180015c26  jnb     loc_180015CAD
0x180015c2c  mov     rbx, qword ptr cs:xmmword_180159918+8
0x180015c33  mov     rax, r15
0x180015c36  mov     [rsp+58h+arg_8], 0
0x180015c3f  mul     qword ptr cs:?g_TelemetryQueue@@3V?$RtlArray@PEAU_PCA_TELEMETRY_EVENT_DATA@@@@A+8; RtlArray<_PCA_TELEMETRY_EVENT_DATA *> g_TelemetryQueue
0x180015c46  test    rdx, rdx
0x180015c49  jnz     short loc_180015C57
0x180015c4b  add     rax, rbx
0x180015c4e  cmp     rax, rbx
0x180015c51  jnb     loc_180015DFA
0x180015c57  mov     ebx, 0C0000095h
0x180015c5c  lea     rcx, ?g_TelemetryQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180015c63  call    cs:__imp_RtlLeaveCriticalSection
0x180015c69  test    ebx, ebx
0x180015c6b  jnz     loc_180015E0B
0x180015c71  mov     rbp, [rsp+58h+arg_10]
0x180015c76  mov     eax, ebx
0x180015c78  mov     rbx, [rsp+58h+arg_0]
0x180015c7d  add     rsp, 30h
0x180015c81  pop     r15
0x180015c83  pop     r14
0x180015c85  pop     r12
0x180015c87  pop     rdi
0x180015c88  pop     rsi
0x180015c89  retn
0x180015c8a  mov     ebx, 0Eh
0x180015c8f  lea     r9, aOutOfMemory; "Out of memory"
0x180015c96  mov     r8d, 244h
0x180015c9c  lea     rdx, aTelemetrypEven_3; "Telemetryp_EventDataCreate"
0x180015ca3  lea     ecx, [rbx-0Dh]
0x180015ca6  call    AslLogCallPrintf
0x180015cab  jmp     short loc_180015C71
0x180015cad  lea     rcx, [r15+1]
0x180015cb1  cmp     rcx, rdx
0x180015cb4  jbe     loc_180015DF0
0x180015cba  mov     r14, qword ptr cs:xmmword_180159918
0x180015cc1  dec     r14
0x180015cc4  lea     r8, [r14+rcx]
0x180015cc8  cmp     r8, rcx
0x180015ccb  jb      short loc_180015C57
0x180015ccd  mov     rcx, qword ptr cs:?g_TelemetryQueue@@3V?$RtlArray@PEAU_PCA_TELEMETRY_EVENT_DATA@@@@A+8; RtlArray<_PCA_TELEMETRY_EVENT_DATA *> g_TelemetryQueue
0x180015cd4  mov     rax, rcx
0x180015cd7  mov     [rsp+58h+arg_8], 0
0x180015ce0  mul     rdx
0x180015ce3  test    rdx, rdx
0x180015ce6  jnz     loc_180015C57
0x180015cec  not     r14
0x180015cef  mov     [rsp+58h+arg_8], rdx
0x180015cf4  and     r14, r8
0x180015cf7  mov     rax, rcx
0x180015cfa  mul     r14
0x180015cfd  mov     r12, rax
0x180015d00  test    rdx, rdx
0x180015d03  jnz     loc_180015C57
0x180015d09  mov     r8, qword ptr cs:xmmword_180159918+8; Ptr
0x180015d10  mov     rcx, qword ptr cs:?g_TelemetryQueue@@3V?$RtlArray@PEAU_PCA_TELEMETRY_EVENT_DATA@@@@A; Heap
0x180015d17  test    r8, r8
0x180015d1a  jnz     short loc_180015D52
0x180015d1c  mov     r8, rax; Size
0x180015d1f  call    cs:__imp_RtlAllocateHeap
0x180015d25  mov     rbx, rax
0x180015d28  test    rax, rax
0x180015d2b  jz      short loc_180015D3A
0x180015d2d  mov     r8, r12; Size
0x180015d30  xor     edx, edx; Val
0x180015d32  mov     rcx, rax; void *
0x180015d35  call    memset_0
0x180015d3a  test    rbx, rbx
0x180015d3d  jz      short loc_180015D60
0x180015d3f  mov     qword ptr cs:xmmword_180159918+8, rbx
0x180015d46  mov     qword ptr cs:xmmword_180159908+8, r14
0x180015d4d  jmp     loc_180015C33
0x180015d52  mov     r9, r12; Size
0x180015d55  call    cs:__imp_RtlReAllocateHeap
0x180015d5b  mov     rbx, rax
0x180015d5e  jmp     short loc_180015D3A
0x180015d60  mov     ebx, 0C0000017h
0x180015d65  jmp     loc_180015C5C
0x180015d6a  mov     rax, 2000000000h
0x180015d74  or      r8, rax
0x180015d77  mov     [rdi+0F98h], r8
0x180015d7e  jmp     loc_180015B6F
0x180015d83  mov     rax, 4002000000h
0x180015d8d  jmp     short loc_180015D99
0x180015d8f  mov     rax, 1002000000h
0x180015d99  or      rcx, rax
0x180015d9c  mov     [rdi+0F98h], rcx
0x180015da3  jmp     loc_180015B6F
0x180015da8  mov     ebx, 7Ah ; 'z'
0x180015dad  lea     rbp, aTelemetrypEven_3; "Telemetryp_EventDataCreate"
0x180015db4  mov     r8d, 280h
0x180015dba  lea     r9, aFailedToCopyEx_0; "Failed to copy executable path [%d]"
0x180015dc1  lea     esi, [rbx-79h]
0x180015dc4  jmp     short loc_180015E18
0x180015dc6  lea     r9, aFailedToCopyUs_1; "Failed to copy User Sid [%d]"
0x180015dcd  mov     dword ptr [rsp+58h+var_38], 7Ah ; 'z'
0x180015dd5  mov     r8d, 290h
0x180015ddb  mov     rdx, rbp
0x180015dde  mov     ecx, esi
0x180015de0  call    AslLogCallPrintf
0x180015de5  xor     eax, eax
0x180015de7  mov     [r14], ax
0x180015deb  jmp     loc_180015C08
0x180015df0  mov     ebx, 0C000000Dh
0x180015df5  jmp     loc_180015C5C
0x180015dfa  mov     [rax], rdi
0x180015dfd  add     qword ptr cs:xmmword_180159908, rsi
0x180015e04  xor     ebx, ebx
0x180015e06  jmp     loc_180015C5C
0x180015e0b  mov     r8d, 29Dh
0x180015e11  lea     r9, aFailedToQueueT; "Failed to queue telemetry event [%d]"
0x180015e18  mov     eax, ebx
0x180015e1a  mov     dword ptr [rsp+58h+var_38], ebx
0x180015e1e  mov     rdx, rbp
0x180015e21  mov     ecx, esi
0x180015e23  call    AslLogCallPrintf
0x180015e28  mov     rcx, rdi; CriticalSection
0x180015e2b  call    cs:__imp_RtlDeleteCriticalSection
0x180015e31  mov     rcx, gs:60h
0x180015e3a  mov     r8, rdi; P
0x180015e3d  xor     edx, edx; Flags
0x180015e3f  mov     rcx, [rcx+30h]; HeapHandle
0x180015e43  call    cs:__imp_RtlFreeHeap
0x180015e49  jmp     loc_180015C71
```
