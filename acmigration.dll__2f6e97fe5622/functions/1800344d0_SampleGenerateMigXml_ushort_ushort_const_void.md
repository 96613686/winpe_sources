# SampleGenerateMigXml(ushort * *,ushort const *,void *)

- ea: `0x1800344d0`
- end: `0x180034598`
- name: `?SampleGenerateMigXml@@YAJPEAPEAGPEBGPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000a5e0`
- `0x1800344d0`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800344f8`
- `ntdll!RtlAllocateHeap` at `0x1800344f8`
- `ntdll!RtlFreeHeap` at `0x18003457b`
- `ntdll!RtlFreeHeap` at `0x18003457b`

## string_xrefs

- `0x18003452e`: `SampleMigXml`
- `0x18003450e`: `Failed to allocate migxml buffer [%x]`
- `0x18003451d`: `SampleGenerateMigXml`
- `0x180034559`: `SampleGenerateMigXml`
- `0x180034552`: `Failed to copy migxml to buffer [%x]`

## pseudocode

```c
__int64 __fastcall SampleGenerateMigXml(unsigned __int16 **a1, const unsigned __int16 *a2, void *a3)
{
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax

  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1Au);
  v5 = Heap;
  if ( Heap )
  {
    v7 = StringCchCopyW(Heap, 0xCu, L"SampleMigXml");
    v6 = v7;
    if ( v7 >= 0 )
    {
      *a1 = v5;
    }
    else
    {
      AslLogCallPrintf(1, "SampleGenerateMigXml", 88, "Failed to copy migxml to buffer [%x]", v7);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
  }
  else
  {
    v6 = -2147024882;
    *a1 = 0;
    AslLogCallPrintf(1, "SampleGenerateMigXml", 82, "Failed to allocate migxml buffer [%x]", -2147024882);
  }
  return v6;
}

```

## disassembly

```asm
0x1800344d0  mov     [rsp+arg_0], rbx
0x1800344d5  mov     [rsp+arg_8], rsi
0x1800344da  push    rdi
0x1800344db  sub     rsp, 30h
0x1800344df  mov     rsi, rcx
0x1800344e2  mov     edx, 8; Flags
0x1800344e7  mov     rcx, gs:60h
0x1800344f0  lea     r8d, [rdx+12h]; Size
0x1800344f4  mov     rcx, [rcx+30h]; HeapHandle
0x1800344f8  call    cs:__imp_RtlAllocateHeap
0x1800344fe  mov     rdi, rax
0x180034501  test    rax, rax
0x180034504  jnz     short loc_18003452E
0x180034506  mov     ebx, 8007000Eh
0x18003450b  mov     [rsi], rax
0x18003450e  lea     r9, aFailedToAlloca_14; "Failed to allocate migxml buffer [%x]"
0x180034515  mov     [rsp+38h+var_18], ebx
0x180034519  lea     r8d, [rax+52h]
0x18003451d  lea     rdx, aSamplegenerate; "SampleGenerateMigXml"
0x180034524  lea     ecx, [rax+1]
0x180034527  call    AslLogCallPrintf
0x18003452c  jmp     short loc_180034586
0x18003452e  lea     r8, aSamplemigxml; "SampleMigXml"
0x180034535  mov     edx, 0Ch; unsigned __int64
0x18003453a  mov     rcx, rdi; unsigned __int16 *
0x18003453d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034542  mov     ebx, eax
0x180034544  test    eax, eax
0x180034546  jns     short loc_180034583
0x180034548  mov     r8d, 58h ; 'X'
0x18003454e  mov     [rsp+38h+var_18], eax
0x180034552  lea     r9, aFailedToCopyMi; "Failed to copy migxml to buffer [%x]"
0x180034559  lea     rdx, aSamplegenerate; "SampleGenerateMigXml"
0x180034560  lea     ecx, [r8-57h]
0x180034564  call    AslLogCallPrintf
0x180034569  mov     rcx, gs:60h
0x180034572  mov     r8, rdi; P
0x180034575  xor     edx, edx; Flags
0x180034577  mov     rcx, [rcx+30h]; HeapHandle
0x18003457b  call    cs:__imp_RtlFreeHeap
0x180034581  jmp     short loc_180034586
0x180034583  mov     [rsi], rdi
0x180034586  mov     rsi, [rsp+38h+arg_8]
0x18003458b  mov     eax, ebx
0x18003458d  mov     rbx, [rsp+38h+arg_0]
0x180034592  add     rsp, 30h
0x180034596  pop     rdi
0x180034597  retn
```
