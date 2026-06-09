# SeHookManagerDelete

- ea: `0x180035cf0`
- end: `0x180035de5`
- name: `SeHookManagerDelete`
- size: `245`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180056ab8`

## callees

- `0x180024a80`
- `0x180035cf0`
- `0x180035dec`
- `0x1800569d4`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180035d89`
- `ntdll!RtlDeleteCriticalSection` at `0x180035d89`
- `ntdll!RtlFreeHeap` at `0x180035d65`
- `ntdll!RtlFreeHeap` at `0x180035da4`
- `ntdll!RtlFreeHeap` at `0x180035dd4`
- `ntdll!RtlFreeHeap` at `0x180035d65`
- `ntdll!RtlFreeHeap` at `0x180035da4`
- `ntdll!RtlFreeHeap` at `0x180035dd4`

## pseudocode

```c
void __fastcall SeHookManagerDelete(PVOID P)
{
  ULONGLONG v1; // rax
  ULONGLONG i; // rdi
  ULONGLONG v4; // rdx
  ULONGLONG v5; // rcx
  void *v6; // r8
  void *v7; // r8
  ULONGLONG pullResult; // [rsp+30h] [rbp+8h] BYREF

  if ( P )
  {
    v1 = *((_QWORD *)P + 2);
    if ( v1 )
    {
      for ( i = 0; i < v1; ++i )
      {
        v4 = 0;
        if ( i < v1 )
        {
          v5 = *((_QWORD *)P + 1);
          pullResult = 0;
          if ( ULongLongMult(v5, i, &pullResult) < 0 || (v4 = *((_QWORD *)P + 5) + pullResult, v4 < *((_QWORD *)P + 5)) )
            v4 = 0;
        }
        SepHooksetFree(v4);
        v1 = *((_QWORD *)P + 2);
      }
    }
    v6 = (void *)*((_QWORD *)P + 5);
    if ( v6 )
      RtlFreeHeap(*(HANDLE *)P, 0, v6);
    *(_OWORD *)P = 0;
    *((_OWORD *)P + 1) = 0;
    *((_OWORD *)P + 2) = 0;
    SeInExDelete(*((void **)P + 6));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)P + 53);
    v7 = (void *)*((_QWORD *)P + 275);
    if ( v7 )
      RtlFreeHeap(*((HANDLE *)P + 270), 0, v7);
    *((_OWORD *)P + 135) = 0;
    *((_OWORD *)P + 136) = 0;
    *((_OWORD *)P + 137) = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
}

```

## disassembly

```asm
0x180035cf0  test    rcx, rcx
0x180035cf3  jz      locret_180035DE4
0x180035cf9  mov     [rsp+arg_8], rbx
0x180035cfe  push    rdi
0x180035cff  sub     rsp, 20h
0x180035d03  mov     rax, [rcx+10h]
0x180035d07  mov     rbx, rcx
0x180035d0a  test    rax, rax
0x180035d0d  jz      short loc_180035D57
0x180035d0f  xor     edi, edi
0x180035d11  xor     edx, edx
0x180035d13  cmp     rdi, rax
0x180035d16  jnb     short loc_180035D43
0x180035d18  mov     rcx, [rbx+8]; ullMultiplicand
0x180035d1c  lea     r8, [rsp+28h+pullResult]; pullResult
0x180035d21  mov     [rsp+28h+pullResult], rdx
0x180035d26  mov     rdx, rdi; ullMultiplier
0x180035d29  call    ULongLongMult
0x180035d2e  test    eax, eax
0x180035d30  js      short loc_180035D41
0x180035d32  mov     rdx, [rsp+28h+pullResult]
0x180035d37  add     rdx, [rbx+28h]
0x180035d3b  cmp     rdx, [rbx+28h]
0x180035d3f  jnb     short loc_180035D43
0x180035d41  xor     edx, edx
0x180035d43  mov     rcx, rdx
0x180035d46  call    SepHooksetFree
0x180035d4b  mov     rax, [rbx+10h]
0x180035d4f  inc     rdi
0x180035d52  cmp     rdi, rax
0x180035d55  jb      short loc_180035D11
0x180035d57  mov     r8, [rbx+28h]; P
0x180035d5b  test    r8, r8
0x180035d5e  jz      short loc_180035D6B
0x180035d60  mov     rcx, [rbx]; HeapHandle
0x180035d63  xor     edx, edx; Flags
0x180035d65  call    cs:__imp_RtlFreeHeap
0x180035d6b  xorps   xmm0, xmm0
0x180035d6e  movups  xmmword ptr [rbx], xmm0
0x180035d71  movups  xmmword ptr [rbx+10h], xmm0
0x180035d75  movups  xmmword ptr [rbx+20h], xmm0
0x180035d79  mov     rcx, [rbx+30h]; void *
0x180035d7d  call    SeInExDelete
0x180035d82  lea     rcx, [rbx+848h]; CriticalSection
0x180035d89  call    cs:__imp_RtlDeleteCriticalSection
0x180035d8f  mov     r8, [rbx+898h]; P
0x180035d96  test    r8, r8
0x180035d99  jz      short loc_180035DAA
0x180035d9b  mov     rcx, [rbx+870h]; HeapHandle
0x180035da2  xor     edx, edx; Flags
0x180035da4  call    cs:__imp_RtlFreeHeap
0x180035daa  xorps   xmm0, xmm0
0x180035dad  mov     r8, rbx; P
0x180035db0  movups  xmmword ptr [rbx+870h], xmm0
0x180035db7  xor     edx, edx; Flags
0x180035db9  movups  xmmword ptr [rbx+880h], xmm0
0x180035dc0  movups  xmmword ptr [rbx+890h], xmm0
0x180035dc7  mov     rcx, gs:60h
0x180035dd0  mov     rcx, [rcx+30h]; HeapHandle
0x180035dd4  call    cs:__imp_RtlFreeHeap
0x180035dda  mov     rbx, [rsp+28h+arg_8]
0x180035ddf  add     rsp, 20h
0x180035de3  pop     rdi
0x180035de4  retn
```
