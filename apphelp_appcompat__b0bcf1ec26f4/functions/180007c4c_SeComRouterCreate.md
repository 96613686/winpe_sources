# SeComRouterCreate

- ea: `0x180007c4c`
- end: `0x180007df1`
- name: `SeComRouterCreate`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007518`

## callees

- `0x180007424`
- `0x180007c4c`
- `0x180009a14`
- `0x18000f114`
- `0x180035af4`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180007c86`
- `ntdll!RtlInitializeCriticalSection` at `0x180007c86`
- `ntdll!RtlAllocateHeap` at `0x180007c71`
- `ntdll!RtlAllocateHeap` at `0x180007c71`

## string_xrefs

- `0x180007dba`: `SeComRouterCreate`
- `0x180007dde`: `SeComRouterCreate`
- `0x180007dd1`: `Failed to create DLL inex list`

## pseudocode

```c
__int64 __fastcall SeComRouterCreate(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *ProcessHeap; // rcx
  PVOID v5; // rcx
  PVOID v6; // rcx
  int v7; // edi

  Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xC0u);
  v3 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SeComRouterCreate", 96, "Out of memory");
    return (unsigned int)-1073741801;
  }
  RtlInitializeCriticalSection(Heap);
  ProcessHeap = (struct _RTL_CRITICAL_SECTION_DEBUG *)NtCurrentPeb()->ProcessHeap;
  *(_OWORD *)&v3[1].DebugInfo = 0;
  *(_OWORD *)&v3[1].OwningThread = 0;
  *(_OWORD *)&v3[1].SpinCount = 0;
  if ( !ProcessHeap )
    ProcessHeap = (struct _RTL_CRITICAL_SECTION_DEBUG *)NtCurrentPeb()->ProcessHeap;
  v3[1].DebugInfo = ProcessHeap;
  v3[1].SpinCount = 4;
  *(_QWORD *)&v3[1].LockCount = 48;
  v5 = NtCurrentPeb()->ProcessHeap;
  *(_OWORD *)&v3[2].LockCount = 0;
  *(_OWORD *)&v3[2].LockSemaphore = 0;
  *(_OWORD *)&v3[3].DebugInfo = 0;
  if ( !v5 )
    v5 = NtCurrentPeb()->ProcessHeap;
  *(_QWORD *)&v3[2].LockCount = v5;
  v3[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)256;
  v3[2].OwningThread = (HANDLE)32;
  v6 = NtCurrentPeb()->ProcessHeap;
  *(_OWORD *)&v3[3].OwningThread = 0;
  *(_OWORD *)&v3[3].SpinCount = 0;
  *(_OWORD *)&v3[4].LockCount = 0;
  if ( !v6 )
    v6 = NtCurrentPeb()->ProcessHeap;
  v3[3].OwningThread = v6;
  *(_QWORD *)&v3[4].LockCount = 256;
  v3[3].LockSemaphore = (HANDLE)64;
  v7 = SeInExCreate(&v3[4].LockSemaphore);
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "SeComRouterCreate", 139, "Failed to create DLL inex list");
  }
  else
  {
    v7 = SeInExAppend(v3[4].LockSemaphore, L"*", 1);
    if ( v7 >= 0 )
    {
      g_ActiveComRouter = v3;
      v7 = 0;
      *a1 = v3;
      return (unsigned int)v7;
    }
  }
  SeComRouterDelete(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007c4c  push    rbx
0x180007c4e  push    rsi
0x180007c4f  push    rdi
0x180007c50  push    r14
0x180007c52  sub     rsp, 28h
0x180007c56  mov     r14, rcx
0x180007c59  mov     edx, 8; Flags
0x180007c5e  mov     rcx, gs:60h
0x180007c67  mov     r8d, 0C0h; Size
0x180007c6d  mov     rcx, [rcx+30h]; HeapHandle
0x180007c71  call    cs:__imp_RtlAllocateHeap
0x180007c77  mov     rbx, rax
0x180007c7a  test    rax, rax
0x180007c7d  jz      loc_180007DAD
0x180007c83  mov     rcx, rax; CriticalSection
0x180007c86  call    cs:__imp_RtlInitializeCriticalSection
0x180007c8c  mov     rax, gs:60h
0x180007c95  xorps   xmm0, xmm0
0x180007c98  mov     rcx, [rax+30h]
0x180007c9c  movups  xmmword ptr [rbx+28h], xmm0
0x180007ca0  movups  xmmword ptr [rbx+38h], xmm0
0x180007ca4  movups  xmmword ptr [rbx+48h], xmm0
0x180007ca8  test    rcx, rcx
0x180007cab  jnz     short loc_180007CBA
0x180007cad  mov     rax, gs:60h
0x180007cb6  mov     rcx, [rax+30h]
0x180007cba  mov     [rbx+28h], rcx
0x180007cbe  mov     qword ptr [rbx+48h], 4
0x180007cc6  mov     qword ptr [rbx+30h], 30h ; '0'
0x180007cce  mov     rax, gs:60h
0x180007cd7  mov     rcx, [rax+30h]
0x180007cdb  movups  xmmword ptr [rbx+58h], xmm0
0x180007cdf  movups  xmmword ptr [rbx+68h], xmm0
0x180007ce3  movups  xmmword ptr [rbx+78h], xmm0
0x180007ce7  test    rcx, rcx
0x180007cea  jnz     short loc_180007CF9
0x180007cec  mov     rax, gs:60h
0x180007cf5  mov     rcx, [rax+30h]
0x180007cf9  mov     [rbx+58h], rcx
0x180007cfd  mov     edx, 100h
0x180007d02  mov     [rbx+78h], rdx
0x180007d06  mov     qword ptr [rbx+60h], 20h ; ' '
0x180007d0e  mov     rax, gs:60h
0x180007d17  mov     rcx, [rax+30h]
0x180007d1b  movups  xmmword ptr [rbx+88h], xmm0
0x180007d22  movups  xmmword ptr [rbx+98h], xmm0
0x180007d29  movups  xmmword ptr [rbx+0A8h], xmm0
0x180007d30  test    rcx, rcx
0x180007d33  jnz     short loc_180007D42
0x180007d35  mov     rax, gs:60h
0x180007d3e  mov     rcx, [rax+30h]
0x180007d42  mov     [rbx+88h], rcx
0x180007d49  lea     rsi, [rbx+0B8h]
0x180007d50  mov     [rbx+0A8h], rdx
0x180007d57  mov     rcx, rsi
0x180007d5a  mov     qword ptr [rbx+90h], 40h ; '@'
0x180007d65  call    SeInExCreate
0x180007d6a  mov     edi, eax
0x180007d6c  test    eax, eax
0x180007d6e  js      short loc_180007DD1
0x180007d70  mov     rcx, [rsi]
0x180007d73  lea     rdx, asc_18005E958; "*"
0x180007d7a  mov     r8d, 1
0x180007d80  call    SeInExAppend
0x180007d85  mov     edi, eax
0x180007d87  test    eax, eax
0x180007d89  jns     short loc_180007D9F
0x180007d8b  mov     rcx, rbx; P
0x180007d8e  call    SeComRouterDelete
0x180007d93  mov     eax, edi
0x180007d95  add     rsp, 28h
0x180007d99  pop     r14
0x180007d9b  pop     rdi
0x180007d9c  pop     rsi
0x180007d9d  pop     rbx
0x180007d9e  retn
0x180007d9f  mov     cs:g_ActiveComRouter, rbx
0x180007da6  xor     edi, edi
0x180007da8  mov     [r14], rbx
0x180007dab  jmp     short loc_180007D93
0x180007dad  mov     r8d, 60h ; '`'
0x180007db3  lea     r9, aOutOfMemory; "Out of memory"
0x180007dba  lea     rdx, aSecomroutercre; "SeComRouterCreate"
0x180007dc1  lea     ecx, [r8-5Fh]
0x180007dc5  call    AslLogCallPrintf
0x180007dca  mov     edi, 0C0000017h
0x180007dcf  jmp     short loc_180007D93
0x180007dd1  lea     r9, aFailedToCreate; "Failed to create DLL inex list"
0x180007dd8  mov     r8d, 8Bh
0x180007dde  lea     rdx, aSecomroutercre; "SeComRouterCreate"
0x180007de5  mov     ecx, 1
0x180007dea  call    AslLogCallPrintf
0x180007def  jmp     short loc_180007D8B
```
