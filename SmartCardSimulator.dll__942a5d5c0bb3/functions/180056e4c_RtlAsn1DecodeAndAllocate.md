# RtlAsn1DecodeAndAllocate

- ea: `0x180056e4c`
- end: `0x180057062`
- name: `RtlAsn1DecodeAndAllocate`
- size: `534`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e380`
- `0x18000e558`
- `0x18000e760`
- `0x18000e968`
- `0x18000eb20`
- `0x180027a90`
- `0x18003e8ec`
- `0x18003ea90`
- `0x18003ec74`
- `0x18003ee4c`

## callees

- `0x180056a94`
- `0x180056bc8`
- `0x180056dec`
- `0x180056e4c`
- `0x1800586d2`
- `0x18005e010`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180056e72`
- `ntdll!WinSqmIsOptedIn` at `0x180056e72`
- `ntdll!WinSqmIncrementDWORD` at `0x180056ea0`
- `ntdll!WinSqmIncrementDWORD` at `0x180056ea0`

## string_xrefs

- `0x180057043`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\object.c`

## pseudocode

```c
__int64 __fastcall RtlAsn1DecodeAndAllocate(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 *a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rdi
  unsigned __int64 v14; // rbp
  unsigned int v15; // ebx
  __int64 v16; // rcx
  int v17; // edx
  __int64 *v18; // r8
  __int64 ObjectEntry; // r14
  __int64 *v20; // r13
  int v21; // eax
  void *v22; // rax
  __int64 v24[11]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+8h] BYREF

  v25 = 0;
  v24[0] = 0;
  if ( (unsigned int)WinSqmIsOptedIn()
    && (!a1 || wcscmp_0(*(const wchar_t **)(a1 + 8), L"{DCD07F46-25B9-4844-BFA5-C7D582C66524}")) )
  {
    WinSqmIncrementDWORD(0, 11115, 1);
  }
  if ( a7 && (!*(_QWORD *)(a7 + 8) || !*(_QWORD *)(a7 + 16)) )
  {
    v12 = 867;
LABEL_29:
    v15 = -2146893785;
    v16 = 2148073511LL;
    goto LABEL_30;
  }
  if ( !a4 || (v13 = a8) == 0 )
  {
    v12 = 875;
    goto LABEL_29;
  }
  v14 = a5;
  if ( a5 > 0x7FFFFFF0 )
  {
    v15 = -2146881276;
    v12 = 882;
    v16 = 2148086020LL;
LABEL_30:
    DebugTraceError(v16, v11, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\object.c", v12);
    return v15;
  }
  *a8 = 0;
  ObjectEntry = ASN1_FindObjectEntry(a1, a2);
  if ( !ObjectEntry )
    return (unsigned int)-2146893783;
  v20 = &qword_180060328;
  if ( v18 )
    v20 = v18;
  v21 = ASN1_DecodeObject(ObjectEntry, v17, a4, v14, 0, 0, (__int64)&v25);
  v15 = v21;
  if ( v21 < 0 )
  {
    v11 = *(_QWORD *)(qword_180076928 + 16);
    if ( v11 )
      (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, unsigned __int64))(qword_180076928 + 16))(
        a1,
        a2,
        ObjectEntry,
        (unsigned int)v21,
        a4,
        v14);
    v12 = 928;
    goto LABEL_21;
  }
  v22 = (void *)((__int64 (__fastcall *)(__int64))v20[1])(v25);
  *v13 = v22;
  if ( !v22 )
  {
    v15 = -2146893810;
    v12 = 940;
    v16 = 2148073486LL;
    goto LABEL_30;
  }
  v15 = ASN1_DecodeObject(ObjectEntry, v11, a4, v14, (__int64)v24, v22, (__int64)&v25);
  if ( (v15 & 0x80000000) != 0 )
  {
    ((void (__fastcall *)(_QWORD))v20[2])(*v13);
    v12 = 961;
    *v13 = 0;
LABEL_21:
    v16 = v15;
    goto LABEL_30;
  }
  if ( a6 )
    *a6 = v24[0];
  return v15;
}

```

## disassembly

```asm
0x180056e4c  mov     rax, rsp
0x180056e4f  push    rbx
0x180056e50  push    rbp
0x180056e51  push    rsi
0x180056e52  push    rdi
0x180056e53  push    r12
0x180056e55  push    r13
0x180056e57  push    r14
0x180056e59  push    r15
0x180056e5b  sub     rsp, 58h
0x180056e5f  xor     ebx, ebx
0x180056e61  mov     r15, r9
0x180056e64  mov     [rax+8], rbx
0x180056e68  mov     r12d, edx
0x180056e6b  mov     [rax-58h], rbx
0x180056e6f  mov     rsi, rcx
0x180056e72  call    cs:__imp_WinSqmIsOptedIn
0x180056e78  test    eax, eax
0x180056e7a  jz      short loc_180056EA6
0x180056e7c  test    rsi, rsi
0x180056e7f  jz      short loc_180056E95
0x180056e81  mov     rcx, [rsi+8]; String1
0x180056e85  lea     rdx, aDcd07f4625b948; "{DCD07F46-25B9-4844-BFA5-C7D582C66524}"
0x180056e8c  call    wcscmp_0
0x180056e91  test    eax, eax
0x180056e93  jz      short loc_180056EA6
0x180056e95  xor     ecx, ecx
0x180056e97  mov     edx, 2B6Bh
0x180056e9c  lea     r8d, [rcx+1]
0x180056ea0  call    cs:__imp_WinSqmIncrementDWORD
0x180056ea6  mov     r8, [rsp+98h+arg_30]
0x180056eae  test    r8, r8
0x180056eb1  jz      short loc_180056ECA
0x180056eb3  cmp     [r8+8], rbx
0x180056eb7  jz      short loc_180056EBF
0x180056eb9  cmp     [r8+10h], rbx
0x180056ebd  jnz     short loc_180056ECA
0x180056ebf  mov     r9d, 363h
0x180056ec5  jmp     loc_180057039
0x180056eca  test    r15, r15
0x180056ecd  jz      loc_180057033
0x180056ed3  mov     rdi, [rsp+98h+arg_38]
0x180056edb  test    rdi, rdi
0x180056ede  jz      loc_180057033
0x180056ee4  mov     rbp, [rsp+98h+arg_20]
0x180056eec  cmp     rbp, 7FFFFFF0h
0x180056ef3  jbe     short loc_180056F0A
0x180056ef5  mov     ebx, 80093104h
0x180056efa  mov     r9d, 372h
0x180056f00  mov     ecx, 80093104h
0x180056f05  jmp     loc_180057043
0x180056f0a  mov     edx, r12d
0x180056f0d  mov     [rdi], rbx
0x180056f10  mov     rcx, rsi
0x180056f13  call    ASN1_FindObjectEntry
0x180056f18  mov     r14, rax
0x180056f1b  test    rax, rax
0x180056f1e  jnz     short loc_180056F2A
0x180056f20  mov     ebx, 80090029h
0x180056f25  jmp     loc_18005704F
0x180056f2a  test    r8, r8
0x180056f2d  lea     rax, [rsp+98h+arg_0]
0x180056f35  mov     [rsp+98h+var_68], rax; __int64
0x180056f3a  lea     r13, qword_180060328
0x180056f41  cmovnz  r13, r8
0x180056f45  mov     [rsp+98h+var_70], rbx; void *
0x180056f4a  mov     r8, r15; int
0x180056f4d  mov     [rsp+98h+var_78], rbx; __int64
0x180056f52  mov     r9, rbp; int
0x180056f55  mov     rcx, r14; int
0x180056f58  call    ASN1_DecodeObject
0x180056f5d  mov     ebx, eax
0x180056f5f  test    eax, eax
0x180056f61  jns     short loc_180056FA6
0x180056f63  mov     rcx, cs:qword_180076928
0x180056f6a  mov     rdx, [rcx+10h]
0x180056f6e  test    rdx, rdx
0x180056f71  jz      short loc_180056F99
0x180056f73  mov     rcx, cs:qword_180076928
0x180056f7a  mov     r9d, ebx
0x180056f7d  mov     [rsp+98h+var_70], rbp
0x180056f82  mov     r8, r14
0x180056f85  mov     edx, r12d
0x180056f88  mov     [rsp+98h+var_78], r15
0x180056f8d  mov     rax, [rcx+10h]
0x180056f91  mov     rcx, rsi
0x180056f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f99  mov     r9d, 3A0h
0x180056f9f  mov     ecx, ebx
0x180056fa1  jmp     loc_180057043
0x180056fa6  mov     rcx, [rsp+98h+arg_0]
0x180056fae  mov     rax, [r13+8]
0x180056fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056fb7  mov     [rdi], rax
0x180056fba  test    rax, rax
0x180056fbd  jnz     short loc_180056FD1
0x180056fbf  mov     ebx, 8009000Eh
0x180056fc4  mov     r9d, 3ACh
0x180056fca  mov     ecx, 8009000Eh
0x180056fcf  jmp     short loc_180057043
0x180056fd1  lea     rcx, [rsp+98h+arg_0]
0x180056fd9  mov     r9, rbp; int
0x180056fdc  mov     [rsp+98h+var_68], rcx; __int64
0x180056fe1  mov     r8, r15; int
0x180056fe4  mov     [rsp+98h+var_70], rax; void *
0x180056fe9  mov     rcx, r14; int
0x180056fec  lea     rax, [rsp+98h+var_58]
0x180056ff1  mov     [rsp+98h+var_78], rax; __int64
0x180056ff6  call    ASN1_DecodeObject
0x180056ffb  mov     ebx, eax
0x180056ffd  test    eax, eax
0x180056fff  jns     short loc_18005701C
0x180057001  mov     rcx, [rdi]
0x180057004  mov     rax, [r13+10h]
0x180057008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005700d  mov     r9d, 3C1h
0x180057013  mov     qword ptr [rdi], 0
0x18005701a  jmp     short loc_180056F9F
0x18005701c  mov     rcx, [rsp+98h+arg_28]
0x180057024  test    rcx, rcx
0x180057027  jz      short loc_18005704F
0x180057029  mov     rax, [rsp+98h+var_58]
0x18005702e  mov     [rcx], rax
0x180057031  jmp     short loc_18005704F
0x180057033  mov     r9d, 36Bh
0x180057039  mov     ebx, 80090027h
0x18005703e  mov     ecx, 80090027h
0x180057043  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x18005704a  call    DebugTraceError
0x18005704f  mov     eax, ebx
0x180057051  add     rsp, 58h
0x180057055  pop     r15
0x180057057  pop     r14
0x180057059  pop     r13
0x18005705b  pop     r12
0x18005705d  pop     rdi
0x18005705e  pop     rsi
0x18005705f  pop     rbp
0x180057060  pop     rbx
0x180057061  retn
```
