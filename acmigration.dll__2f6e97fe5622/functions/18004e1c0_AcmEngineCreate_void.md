# AcmEngineCreate(void * *)

- ea: `0x18004e1c0`
- end: `0x18004e268`
- name: `?AcmEngineCreate@@YAJPEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa70`

## callees

- `0x18004e1c0`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004e20d`
- `ntdll!RtlAllocateHeap` at `0x18004e20d`

## string_xrefs

- `0x18004e1e2`: `AcmEngineCreate`
- `0x18004e228`: `AcmEngineCreate`

## pseudocode

```c
__int64 __fastcall AcmEngineCreate(void **a1)
{
  unsigned int v1; // edi
  _QWORD *Heap; // rax

  v1 = 0;
  if ( a1 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x220u);
    if ( Heap )
    {
      Heap[66] = 21;
      Heap[65] = &g_MigrationShims;
      *((_DWORD *)Heap + 134) = 0;
      *a1 = Heap;
    }
    else
    {
      v1 = -2147024882;
      AslLogCallPrintf(1, "AcmEngineCreate", 114, "Failed to allocate engine");
    }
    return v1;
  }
  else
  {
    AslLogCallPrintf(1, "AcmEngineCreate", 103, "Invalid input");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004e1c0  mov     [rsp+arg_0], rbx
0x18004e1c5  push    rdi
0x18004e1c6  sub     rsp, 20h
0x18004e1ca  xor     edi, edi
0x18004e1cc  mov     rbx, rcx
0x18004e1cf  test    rcx, rcx
0x18004e1d2  jnz     short loc_18004E1F5
0x18004e1d4  lea     r8d, [rcx+67h]
0x18004e1d8  lea     ecx, [rbx+1]
0x18004e1db  lea     r9, aInvalidInput; "Invalid input"
0x18004e1e2  lea     rdx, aAcmenginecreat_0; "AcmEngineCreate"
0x18004e1e9  call    AslLogCallPrintf
0x18004e1ee  mov     eax, 80070057h
0x18004e1f3  jmp     short loc_18004E25D
0x18004e1f5  mov     rcx, gs:60h
0x18004e1fe  mov     edx, 8; Flags
0x18004e203  mov     r8d, 220h; Size
0x18004e209  mov     rcx, [rcx+30h]; HeapHandle
0x18004e20d  call    cs:__imp_RtlAllocateHeap
0x18004e213  test    rax, rax
0x18004e216  jnz     short loc_18004E239
0x18004e218  lea     r9, aFailedToAlloca_11; "Failed to allocate engine"
0x18004e21f  mov     edi, 8007000Eh
0x18004e224  lea     r8d, [rax+72h]
0x18004e228  lea     rdx, aAcmenginecreat_0; "AcmEngineCreate"
0x18004e22f  lea     ecx, [rax+1]
0x18004e232  call    AslLogCallPrintf
0x18004e237  jmp     short loc_18004E25B
0x18004e239  mov     qword ptr [rax+210h], 15h
0x18004e244  lea     rcx, ?g_MigrationShims@@3PAPEAU_ACM_SHIM@@A; _ACM_SHIM * near * g_MigrationShims
0x18004e24b  mov     [rax+208h], rcx
0x18004e252  mov     [rax+218h], edi
0x18004e258  mov     [rbx], rax
0x18004e25b  mov     eax, edi
0x18004e25d  mov     rbx, [rsp+28h+arg_0]
0x18004e262  add     rsp, 20h
0x18004e266  pop     rdi
0x18004e267  retn
```
