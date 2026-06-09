# BampDereferenceThrottledProcessInformation

- ea: `0x1400107f0`
- end: `0x140010870`
- name: `BampDereferenceThrottledProcessInformation`
- size: `128`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f460`
- `0x140010308`
- `0x14001044c`
- `0x1400105b0`
- `0x14001202c`
- `0x140012450`
- `0x140012eec`
- `0x140013c7c`
- `0x140014648`
- `0x14001474c`
- `0x140014d20`
- `0x140014f90`

## callees

- `0x1400107f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010862`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010862`
- `ntoskrnl!ZwClose` at `0x14001084e`
- `ntoskrnl!ZwClose` at `0x14001084e`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140010839`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140010839`

## pseudocode

```c
void __fastcall BampDereferenceThrottledProcessInformation(volatile signed __int64 *P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void *v5; // rcx

  v2 = _InterlockedExchangeAdd64(P + 33, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    if ( *((_QWORD *)P + 14) )
      ExUnsubscribeWnfStateChange();
    v5 = (void *)*((_QWORD *)P + 13);
    if ( v5 )
      ZwClose(v5);
    ExFreePoolWithTag((PVOID)P, 0x4B6D6142u);
  }
}

```

## disassembly

```asm
0x1400107f0  push    rbx
0x1400107f2  sub     rsp, 20h
0x1400107f6  mov     rbx, rcx
0x1400107f9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140010800  lock xadd [rcx+108h], rax
0x140010809  sub     rax, 1
0x14001080d  jle     short loc_140010816
0x14001080f  add     rsp, 20h
0x140010813  pop     rbx
0x140010814  retn
0x140010816  test    rax, rax
0x140010819  jz      short loc_140010830
0x14001081b  mov     ecx, 0Eh
0x140010820  int     29h; Win8: RtlFailFast(ecx)
0x140010822  add     rsp, 20h
0x140010826  pop     rbx
0x140010827  retn
0x140010830  mov     rcx, [rcx+70h]
0x140010834  test    rcx, rcx
0x140010837  jz      short loc_140010845
0x140010839  call    cs:__imp_ExUnsubscribeWnfStateChange
0x140010840  nop     dword ptr [rax+rax+00h]
0x140010845  mov     rcx, [rbx+68h]; Handle
0x140010849  test    rcx, rcx
0x14001084c  jz      short loc_14001085A
0x14001084e  call    cs:__imp_ZwClose
0x140010855  nop     dword ptr [rax+rax+00h]
0x14001085a  mov     edx, 4B6D6142h; Tag
0x14001085f  mov     rcx, rbx; P
0x140010862  call    cs:__imp_ExFreePoolWithTag
0x140010869  nop     dword ptr [rax+rax+00h]
0x14001086e  jmp     short loc_14001080F
```
