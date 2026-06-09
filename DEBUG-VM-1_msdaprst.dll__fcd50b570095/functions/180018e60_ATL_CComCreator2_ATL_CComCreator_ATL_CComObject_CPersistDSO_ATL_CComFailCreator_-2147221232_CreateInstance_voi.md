# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPersistDSO>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180018e60`
- end: `0x180018f02`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPersistDSO@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001d94`
- `0x18000c848`
- `0x18000c870`
- `0x180018458`
- `0x180018714`
- `0x180018e60`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPersistDSO>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  unsigned __int8 *v6; // rax
  __int64 v7; // rsi
  int *v8; // rcx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = MMMAlloc(0x1380u, a2);
  if ( v6 )
    v7 = ATL::CComObject<CPersistDSO>::CComObject<CPersistDSO>(v6);
  else
    v7 = 0;
  if ( v7 )
  {
    ATL::SafeIncrementReferenceMultiThread((int *)(v7 + 48));
    ATL::SafeDecrementReferenceMultiThread(v8);
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      ATL::CComObject<CPersistDSO>::`scalar deleting destructor'((unsigned __int8 *)v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180018e60  push    rbx
0x180018e62  push    rbp
0x180018e63  push    rsi
0x180018e64  push    rdi
0x180018e65  sub     rsp, 28h
0x180018e69  mov     rdi, r8
0x180018e6c  mov     rbp, rdx
0x180018e6f  test    rcx, rcx
0x180018e72  jnz     short loc_180018EE6
0x180018e74  test    r8, r8
0x180018e77  jnz     short loc_180018E80
0x180018e79  mov     ebx, 80004003h
0x180018e7e  jmp     short loc_180018EF7
0x180018e80  mov     qword ptr [r8], 0
0x180018e87  mov     ebx, 8007000Eh
0x180018e8c  mov     ecx, 1380h; unsigned int
0x180018e91  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180018e96  mov     [rsp+48h+arg_0], rax
0x180018e9b  test    rax, rax
0x180018e9e  jz      short loc_180018EAD
0x180018ea0  mov     rcx, rax
0x180018ea3  call    ??0?$CComObject@VCPersistDSO@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPersistDSO>::CComObject<CPersistDSO>(void *)
0x180018ea8  mov     rsi, rax
0x180018eab  jmp     short loc_180018EAF
0x180018ead  xor     esi, esi
0x180018eaf  test    rsi, rsi
0x180018eb2  jz      short loc_180018EF7
0x180018eb4  lea     rcx, [rsi+30h]; int *
0x180018eb8  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeIncrementReferenceMultiThread(long *)
0x180018ebd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x180018ec2  mov     rcx, [rsi]
0x180018ec5  mov     rax, [rcx]
0x180018ec8  mov     r8, rdi
0x180018ecb  mov     rdx, rbp
0x180018ece  mov     rcx, rsi
0x180018ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed6  mov     ebx, eax
0x180018ed8  test    eax, eax
0x180018eda  jz      short loc_180018EF7
0x180018edc  mov     rcx, rsi; unsigned __int8 *
0x180018edf  call    ??_G?$CComObject@VCPersistDSO@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(uint)
0x180018ee4  jmp     short loc_180018EF7
0x180018ee6  test    rdi, rdi
0x180018ee9  jz      short loc_180018E79
0x180018eeb  mov     qword ptr [r8], 0
0x180018ef2  mov     ebx, 80040110h
0x180018ef7  mov     eax, ebx
0x180018ef9  add     rsp, 28h
0x180018efd  pop     rdi
0x180018efe  pop     rsi
0x180018eff  pop     rbp
0x180018f00  pop     rbx
0x180018f01  retn
```
