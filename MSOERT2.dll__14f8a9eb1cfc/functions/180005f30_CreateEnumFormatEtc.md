# CreateEnumFormatEtc

- ea: `0x180005f30`
- end: `0x180006008`
- name: `CreateEnumFormatEtc`
- size: `216`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, struct tagDATAOBJINFO *, struct tagFORMATETC *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004ce0`

## callees

- `0x180001f7c`
- `0x180005b58`
- `0x180005bf4`
- `0x180005cc4`
- `0x180005f30`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CreateEnumFormatEtc(
        struct IUnknown *a1,
        unsigned int a2,
        struct tagDATAOBJINFO *a3,
        struct tagFORMATETC *a4,
        _QWORD *a5)
{
  CEnumFormatEtc *v9; // rax
  CEnumFormatEtc *v10; // rax
  CEnumFormatEtc *v11; // rdi
  unsigned int v12; // edx
  int v13; // ebx

  if ( !a1 || !a5 || !a2 || a3 && a4 )
    return (unsigned int)-2147024809;
  *a5 = 0;
  v9 = (CEnumFormatEtc *)operator new(0x28u);
  if ( a3 )
  {
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_13;
    }
    v10 = CEnumFormatEtc::CEnumFormatEtc(v9, a1, a3, a2);
  }
  else
  {
    if ( !v9 )
      return (unsigned int)-2147024882;
    v10 = CEnumFormatEtc::CEnumFormatEtc(v9, a1, a2, a4);
  }
  v11 = v10;
LABEL_13:
  if ( !v11 )
    return (unsigned int)-2147024882;
  v13 = (**(__int64 (__fastcall ***)(CEnumFormatEtc *, GUID *, _QWORD *))v11)(v11, &IID_IEnumFORMATETC, a5);
  if ( v13 < 0 )
    CEnumFormatEtc::`scalar deleting destructor'(v11, v12);
  else
    return 0;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180005f30  push    rbx
0x180005f32  push    rbp
0x180005f33  push    rsi
0x180005f34  push    rdi
0x180005f35  push    r14
0x180005f37  sub     rsp, 20h
0x180005f3b  mov     rbp, r9
0x180005f3e  mov     rbx, r8
0x180005f41  mov     edi, edx
0x180005f43  mov     r14, rcx
0x180005f46  test    rcx, rcx
0x180005f49  jz      loc_180005FF6
0x180005f4f  mov     rsi, [rsp+48h+arg_20]
0x180005f54  test    rsi, rsi
0x180005f57  jz      loc_180005FF6
0x180005f5d  test    edx, edx
0x180005f5f  jz      loc_180005FF6
0x180005f65  test    rbx, rbx
0x180005f68  jz      short loc_180005F73
0x180005f6a  test    r9, r9
0x180005f6d  jnz     loc_180005FF6
0x180005f73  mov     ecx, 28h ; '('; Size
0x180005f78  mov     qword ptr [rsi], 0
0x180005f7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f84  test    rbx, rbx
0x180005f87  jz      short loc_180005FA5
0x180005f89  test    rax, rax
0x180005f8c  jz      short loc_180005FA1
0x180005f8e  mov     r9d, edi; unsigned int
0x180005f91  mov     r8, rbx; struct tagDATAOBJINFO *
0x180005f94  mov     rdx, r14; struct IUnknown *
0x180005f97  mov     rcx, rax; this
0x180005f9a  call    ??0CEnumFormatEtc@@QEAA@PEAUIUnknown@@PEAUtagDATAOBJINFO@@K@Z; CEnumFormatEtc::CEnumFormatEtc(IUnknown *,tagDATAOBJINFO *,ulong)
0x180005f9f  jmp     short loc_180005FBB
0x180005fa1  xor     edi, edi
0x180005fa3  jmp     short loc_180005FBE
0x180005fa5  test    rax, rax
0x180005fa8  jz      short loc_180005FEF
0x180005faa  mov     r9, rbp; struct tagFORMATETC *
0x180005fad  mov     r8d, edi; unsigned int
0x180005fb0  mov     rdx, r14; struct IUnknown *
0x180005fb3  mov     rcx, rax; this
0x180005fb6  call    ??0CEnumFormatEtc@@QEAA@PEAUIUnknown@@KPEBUtagFORMATETC@@@Z; CEnumFormatEtc::CEnumFormatEtc(IUnknown *,ulong,tagFORMATETC const *)
0x180005fbb  mov     rdi, rax
0x180005fbe  test    rdi, rdi
0x180005fc1  jz      short loc_180005FEF
0x180005fc3  mov     rax, [rdi]
0x180005fc6  lea     rdx, IID_IEnumFORMATETC
0x180005fcd  mov     r8, rsi
0x180005fd0  mov     rcx, rdi
0x180005fd3  mov     rax, [rax]
0x180005fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdb  mov     ebx, eax
0x180005fdd  test    eax, eax
0x180005fdf  js      short loc_180005FE5
0x180005fe1  xor     ebx, ebx
0x180005fe3  jmp     short loc_180005FFB
0x180005fe5  mov     rcx, rdi; this
0x180005fe8  call    ??_GCEnumFormatEtc@@QEAAPEAXI@Z; CEnumFormatEtc::`scalar deleting destructor'(uint)
0x180005fed  jmp     short loc_180005FFB
0x180005fef  mov     ebx, 8007000Eh
0x180005ff4  jmp     short loc_180005FFB
0x180005ff6  mov     ebx, 80070057h
0x180005ffb  mov     eax, ebx
0x180005ffd  add     rsp, 20h
0x180006001  pop     r14
0x180006003  pop     rdi
0x180006004  pop     rsi
0x180006005  pop     rbp
0x180006006  pop     rbx
0x180006007  retn
```
