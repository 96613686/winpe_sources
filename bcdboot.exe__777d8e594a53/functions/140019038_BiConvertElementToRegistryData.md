# BiConvertElementToRegistryData

- ea: `0x140019038`
- end: `0x14001941d`
- name: `BiConvertElementToRegistryData`
- size: `997`
- prototype: `__int64 __fastcall(unsigned int, const GUID *, unsigned int, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140018b54`

## callees

- `0x140015cd8`
- `0x140019038`
- `0x140019424`
- `0x140020720`
- `0x1400265e2`
- `0x140026650`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400190ef`
- `ntdll!RtlAllocateHeap` at `0x14001914d`
- `ntdll!RtlAllocateHeap` at `0x140019189`
- `ntdll!RtlAllocateHeap` at `0x1400191e4`
- `ntdll!RtlAllocateHeap` at `0x1400192d4`
- `ntdll!RtlAllocateHeap` at `0x140019370`
- `ntdll!RtlAllocateHeap` at `0x1400190ef`
- `ntdll!RtlAllocateHeap` at `0x14001914d`
- `ntdll!RtlAllocateHeap` at `0x140019189`
- `ntdll!RtlAllocateHeap` at `0x1400191e4`
- `ntdll!RtlAllocateHeap` at `0x1400192d4`
- `ntdll!RtlAllocateHeap` at `0x140019370`
- `ntdll!RtlFreeHeap` at `0x1400193b7`
- `ntdll!RtlFreeHeap` at `0x1400193ee`
- `ntdll!RtlFreeHeap` at `0x1400193b7`
- `ntdll!RtlFreeHeap` at `0x1400193ee`
- `ntdll!RtlStringFromGUID` at `0x14001926a`
- `ntdll!RtlStringFromGUID` at `0x14001926a`

## pseudocode

```c
__int64 __fastcall BiConvertElementToRegistryData(
        unsigned int a1,
        const GUID *a2,
        unsigned int a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  size_t v7; // rsi
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  _QWORD *v14; // rax
  _QWORD *Buffer; // rdi
  NTSTATUS v16; // ebx
  SIZE_T v17; // r14
  unsigned int v18; // esi
  int v19; // edx
  unsigned int i; // ecx
  _QWORD *v21; // rax
  _WORD *v22; // r13
  unsigned int j; // r14d
  size_t v24; // rbx
  char v25; // r15
  const GUID *v26; // rcx
  unsigned int v27; // eax
  _QWORD *v28; // rax
  int v29; // eax
  unsigned int *v30; // rbx
  _OWORD *Heap; // rax
  PVOID P; // [rsp+20h] [rbp-99h] BYREF
  unsigned int v34; // [rsp+28h] [rbp-91h]
  __int64 v35; // [rsp+30h] [rbp-89h] BYREF
  void *Src; // [rsp+38h] [rbp-81h]
  SIZE_T v37; // [rsp+40h] [rbp-79h]
  _QWORD *v38; // [rsp+48h] [rbp-71h]
  _DWORD *v39; // [rsp+50h] [rbp-69h]
  struct _UNICODE_STRING GuidString; // [rsp+58h] [rbp-61h] BYREF
  char v41; // [rsp+70h] [rbp-49h] BYREF

  v38 = a5;
  v39 = a6;
  v7 = a3;
  Src = &v41;
  v35 = 5111808;
  P = 0;
  GuidString = 0;
  v8 = (HIBYTE(a1) & 0xF) - 1;
  if ( !v8 )
  {
    if ( a2->Data1 == 6 )
      v29 = BiConvertQualifiedPartitionToBootEnvironment(a2, a3, &P);
    else
      v29 = BiConvertNtDeviceToBootEnvironment(a2, a3, a4, &P);
    v16 = v29;
    if ( v29 < 0 )
      goto LABEL_51;
    v30 = (unsigned int *)P;
    LODWORD(v17) = *((_DWORD *)P + 2) + 16;
    if ( *((_DWORD *)P + 2) >= 0xFFFFFFF0 )
    {
      v16 = -1073741811;
      goto LABEL_51;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v17);
    Buffer = Heap;
    if ( Heap )
    {
      *Heap = *(_OWORD *)&a2->Data2;
      memcpy_0(Heap + 1, v30, v30[2]);
      if ( P )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
      }
      goto LABEL_50;
    }
    goto LABEL_9;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v25 = 1;
    if ( (a3 & 1) != 0 )
      return (unsigned int)-1073741788;
    v26 = a2;
    v27 = a3 >> 1;
    if ( a3 >> 1 )
    {
      while ( LOWORD(v26->Data1) )
      {
        v26 = (const GUID *)((char *)v26 + 2);
        if ( !--v27 )
          goto LABEL_35;
      }
      LODWORD(v17) = a3;
    }
    else
    {
LABEL_35:
      LODWORD(v17) = a3 + 2;
      v25 = 0;
      if ( a3 + 2 < a3 )
        return (unsigned int)-1073741675;
    }
    v28 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v17);
    Buffer = v28;
    if ( v28 )
    {
      memcpy_0(v28, a2, v7);
      if ( !v25 )
        *(_WORD *)((char *)Buffer + (unsigned int)v17 - 2) = 0;
      goto LABEL_50;
    }
    goto LABEL_9;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( a3 == 16 )
    {
      v16 = RtlStringFromGUID(a2, &GuidString);
      if ( v16 < 0 )
        goto LABEL_51;
      Buffer = GuidString.Buffer;
      LODWORD(v17) = GuidString.Length + 2;
      goto LABEL_50;
    }
    return (unsigned int)-1073741788;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( (a3 & 0xF) != 0 )
      return (unsigned int)-1073741788;
    v18 = a3 >> 4;
    v19 = 0;
    for ( i = 0; i < v18; ++i )
      v19 += 78;
    v17 = (unsigned int)(v19 + 2);
    v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    Buffer = v21;
    if ( v21 )
    {
      v37 = v17;
      v22 = v21;
      v34 = 0;
      if ( v18 )
      {
        for ( j = v34; j < v18; ++j )
        {
          BiStringFromGUID(&a2[j], &v35);
          v24 = (unsigned int)(unsigned __int16)v35 + 2;
          memcpy_0(v22, Src, v24);
          v22 = (_WORD *)((char *)v22 + v24);
        }
        LODWORD(v17) = v37;
      }
      *v22 = 0;
      goto LABEL_50;
    }
    goto LABEL_9;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    LODWORD(v17) = 8;
    if ( a3 != 8 )
      return (unsigned int)-1073741788;
    Buffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
    if ( Buffer )
    {
      *Buffer = *(_QWORD *)&a2->Data1;
      goto LABEL_50;
    }
LABEL_9:
    v16 = -1073741801;
    goto LABEL_51;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 == 1 && (a3 & 7) != 0 )
      return (unsigned int)-1073741788;
    v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a3);
    Buffer = v14;
    if ( !v14 )
      goto LABEL_9;
    LODWORD(v17) = v7;
    memcpy_0(v14, a2, v7);
    goto LABEL_50;
  }
  if ( a3 - 1 > 1 )
    return (unsigned int)-1073741788;
  Buffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 1u);
  if ( !Buffer )
    goto LABEL_9;
  LODWORD(v17) = 1;
  *(_BYTE *)Buffer = LOBYTE(a2->Data1) != 0;
LABEL_50:
  v16 = 0;
  *v38 = Buffer;
  *v39 = v17;
LABEL_51:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140019038  mov     [rsp-8+arg_0], rbx
0x14001903d  push    rbp
0x14001903e  push    rsi
0x14001903f  push    rdi
0x140019040  push    r12
0x140019042  push    r13
0x140019044  push    r14
0x140019046  push    r15
0x140019048  lea     rbp, [rsp-17h]
0x14001904d  sub     rsp, 0D0h
0x140019054  mov     rax, cs:__security_cookie
0x14001905b  xor     rax, rsp
0x14001905e  mov     [rbp+47h+var_40], rax
0x140019062  mov     rax, [rbp+47h+arg_20]
0x140019066  xor     r13d, r13d
0x140019069  mov     [rbp+47h+var_B8], rax
0x14001906d  xorps   xmm0, xmm0
0x140019070  mov     rax, [rbp+47h+arg_28]
0x140019074  mov     r10d, r9d
0x140019077  shr     ecx, 18h
0x14001907a  mov     r12, rdx
0x14001907d  mov     [rbp+47h+var_B0], rax
0x140019081  and     ecx, 0Fh
0x140019084  mov     esi, r8d
0x140019087  lea     rax, [rbp+47h+var_90]
0x14001908b  mov     [rsp+100h+Src], rax
0x140019090  lea     r8d, [r13+4Eh]
0x140019094  mov     [rsp+100h+var_D0], 4E0000h
0x14001909d  mov     [rsp+100h+P], r13
0x1400190a2  movups  xmmword ptr [rbp+47h+GuidString.Length], xmm0
0x1400190a6  sub     ecx, 1
0x1400190a9  jz      loc_140019317
0x1400190af  sub     ecx, 1
0x1400190b2  jz      loc_14001928C
0x1400190b8  sub     ecx, 1
0x1400190bb  jz      loc_14001925A
0x1400190c1  sub     ecx, 1
0x1400190c4  jz      loc_1400191A7
0x1400190ca  sub     ecx, 1
0x1400190cd  jz      loc_14001916C
0x1400190d3  sub     ecx, 1
0x1400190d6  jz      short loc_14001912D
0x1400190d8  cmp     ecx, 1
0x1400190db  jz      short loc_14001911D
0x1400190dd  mov     rcx, gs:60h
0x1400190e6  mov     r8, rsi; Size
0x1400190e9  xor     edx, edx; Flags
0x1400190eb  mov     rcx, [rcx+30h]; HeapHandle
0x1400190ef  call    cs:__imp_RtlAllocateHeap
0x1400190f5  mov     rdi, rax
0x1400190f8  test    rax, rax
0x1400190fb  jnz     short loc_140019107
0x1400190fd  mov     ebx, 0C0000017h
0x140019102  jmp     loc_1400193D3
0x140019107  mov     r8, rsi; Size
0x14001910a  mov     rdx, r12; Src
0x14001910d  mov     rcx, rax; void *
0x140019110  mov     r14d, esi
0x140019113  call    memcpy_0
0x140019118  jmp     loc_1400193C2
0x14001911d  test    sil, 7
0x140019121  jz      short loc_1400190DD
0x140019123  mov     ebx, 0C0000024h
0x140019128  jmp     loc_1400193F4
0x14001912d  lea     eax, [rsi-1]
0x140019130  mov     r15d, 1
0x140019136  cmp     eax, r15d
0x140019139  ja      short loc_140019123
0x14001913b  mov     rcx, gs:60h
0x140019144  mov     r8d, r15d; Size
0x140019147  xor     edx, edx; Flags
0x140019149  mov     rcx, [rcx+30h]; HeapHandle
0x14001914d  call    cs:__imp_RtlAllocateHeap
0x140019153  mov     rdi, rax
0x140019156  test    rax, rax
0x140019159  jz      short loc_1400190FD
0x14001915b  cmp     [r12], r13b
0x14001915f  mov     r14d, r15d
0x140019162  setnz   al
0x140019165  mov     [rdi], al
0x140019167  jmp     loc_1400193C2
0x14001916c  mov     r14d, 8
0x140019172  cmp     esi, r14d
0x140019175  jnz     short loc_140019123
0x140019177  mov     rcx, gs:60h
0x140019180  mov     r8d, r14d; Size
0x140019183  xor     edx, edx; Flags
0x140019185  mov     rcx, [rcx+30h]; HeapHandle
0x140019189  call    cs:__imp_RtlAllocateHeap
0x14001918f  mov     rdi, rax
0x140019192  test    rax, rax
0x140019195  jz      loc_1400190FD
0x14001919b  mov     rax, [r12]
0x14001919f  mov     [rdi], rax
0x1400191a2  jmp     loc_1400193C2
0x1400191a7  test    sil, 0Fh
0x1400191ab  jnz     loc_140019123
0x1400191b1  shr     esi, 4
0x1400191b4  mov     edx, r13d
0x1400191b7  mov     ecx, r13d
0x1400191ba  mov     r15d, 1
0x1400191c0  test    esi, esi
0x1400191c2  jz      short loc_1400191CE
0x1400191c4  add     edx, r8d
0x1400191c7  add     ecx, r15d
0x1400191ca  cmp     ecx, esi
0x1400191cc  jb      short loc_1400191C4
0x1400191ce  mov     rcx, gs:60h
0x1400191d7  lea     r14d, [rdx+2]
0x1400191db  mov     r8d, r14d; Size
0x1400191de  xor     edx, edx; Flags
0x1400191e0  mov     rcx, [rcx+30h]; HeapHandle
0x1400191e4  call    cs:__imp_RtlAllocateHeap
0x1400191ea  mov     rdi, rax
0x1400191ed  test    rax, rax
0x1400191f0  jz      loc_1400190FD
0x1400191f6  mov     [rbp+47h+var_C0], r14
0x1400191fa  mov     r13, rax
0x1400191fd  mov     [rsp+100h+var_D8], 0
0x140019205  test    esi, esi
0x140019207  jz      short loc_14001924B
0x140019209  mov     r14d, [rsp+100h+var_D8]
0x14001920e  mov     ecx, r14d
0x140019211  lea     rdx, [rsp+100h+var_D0]
0x140019216  shl     rcx, 4
0x14001921a  add     rcx, r12
0x14001921d  call    BiStringFromGUID
0x140019222  movzx   eax, word ptr [rsp+100h+var_D0]
0x140019227  mov     rcx, r13; void *
0x14001922a  mov     rdx, [rsp+100h+Src]; Src
0x14001922f  add     eax, 2
0x140019232  mov     r8d, eax; Size
0x140019235  mov     ebx, eax
0x140019237  call    memcpy_0
0x14001923c  add     r13, rbx
0x14001923f  add     r14d, r15d
0x140019242  cmp     r14d, esi
0x140019245  jb      short loc_14001920E
0x140019247  mov     r14, [rbp+47h+var_C0]
0x14001924b  xor     eax, eax
0x14001924d  mov     [r13+0], ax
0x140019252  xor     r13d, r13d
0x140019255  jmp     loc_1400193C2
0x14001925a  cmp     esi, 10h
0x14001925d  jnz     loc_140019123
0x140019263  lea     rdx, [rbp+47h+GuidString]; GuidString
0x140019267  mov     rcx, r12; Guid
0x14001926a  call    cs:__imp_RtlStringFromGUID
0x140019270  mov     ebx, eax
0x140019272  test    eax, eax
0x140019274  js      loc_1400193D3
0x14001927a  movzx   r14d, [rbp+47h+GuidString.Length]
0x14001927f  mov     rdi, [rbp+47h+GuidString.Buffer]
0x140019283  add     r14d, 2
0x140019287  jmp     loc_1400193C2
0x14001928c  mov     r15d, 1
0x140019292  test    r15b, sil
0x140019295  jnz     loc_140019123
0x14001929b  mov     eax, esi
0x14001929d  mov     rcx, r12
0x1400192a0  shr     eax, 1
0x1400192a2  jz      short loc_1400192B3
0x1400192a4  cmp     [rcx], r13w
0x1400192a8  jz      short loc_140019308
0x1400192aa  add     rcx, 2
0x1400192ae  add     eax, 0FFFFFFFFh
0x1400192b1  jnz     short loc_1400192A4
0x1400192b3  lea     r14d, [rsi+2]
0x1400192b7  mov     r15b, r13b
0x1400192ba  cmp     r14d, esi
0x1400192bd  jb      short loc_14001930D
0x1400192bf  mov     rcx, gs:60h
0x1400192c8  xor     edx, edx; Flags
0x1400192ca  mov     r8d, r14d; Size
0x1400192cd  mov     ebx, r14d
0x1400192d0  mov     rcx, [rcx+30h]; HeapHandle
0x1400192d4  call    cs:__imp_RtlAllocateHeap
0x1400192da  mov     rdi, rax
0x1400192dd  test    rax, rax
0x1400192e0  jz      loc_1400190FD
0x1400192e6  mov     r8, rsi; Size
0x1400192e9  mov     rdx, r12; Src
0x1400192ec  mov     rcx, rax; void *
0x1400192ef  call    memcpy_0
0x1400192f4  test    r15b, r15b
0x1400192f7  jnz     loc_1400193C2
0x1400192fd  mov     [rbx+rdi-2], r13w
0x140019303  jmp     loc_1400193C2
0x140019308  mov     r14d, esi
0x14001930b  jmp     short loc_1400192BF
0x14001930d  mov     ebx, 0C0000095h
0x140019312  jmp     loc_1400193F4
0x140019317  cmp     dword ptr [rdx], 6
0x14001931a  mov     rcx, r12
0x14001931d  mov     edx, esi
0x14001931f  jnz     short loc_14001932D
0x140019321  lea     r8, [rsp+100h+P]
0x140019326  call    BiConvertQualifiedPartitionToBootEnvironment
0x14001932b  jmp     short loc_14001933A
0x14001932d  lea     r9, [rsp+100h+P]
0x140019332  mov     r8d, r10d
0x140019335  call    BiConvertNtDeviceToBootEnvironment
0x14001933a  mov     ebx, eax
0x14001933c  test    eax, eax
0x14001933e  js      loc_1400193D3
0x140019344  mov     rbx, [rsp+100h+P]
0x140019349  mov     r14d, [rbx+8]
0x14001934d  add     r14d, 10h
0x140019351  cmp     r14d, 10h
0x140019355  jnb     short loc_14001935E
0x140019357  mov     ebx, 0C000000Dh
0x14001935c  jmp     short loc_1400193D3
0x14001935e  mov     rcx, gs:60h
0x140019367  xor     edx, edx; Flags
0x140019369  mov     r8d, r14d; Size
0x14001936c  mov     rcx, [rcx+30h]; HeapHandle
0x140019370  call    cs:__imp_RtlAllocateHeap
0x140019376  mov     rdi, rax
0x140019379  test    rax, rax
0x14001937c  jz      loc_1400190FD
0x140019382  movups  xmm0, xmmword ptr [r12+4]
0x140019388  lea     rcx, [rax+10h]; void *
0x14001938c  mov     rdx, rbx; Src
0x14001938f  movdqu  xmmword ptr [rax], xmm0
0x140019393  mov     r8d, [rbx+8]; Size
0x140019397  call    memcpy_0
0x14001939c  cmp     [rsp+100h+P], r13
0x1400193a1  jz      short loc_1400193C2
0x1400193a3  mov     rcx, gs:60h
0x1400193ac  xor     edx, edx; Flags
0x1400193ae  mov     r8, [rsp+100h+P]; P
0x1400193b3  mov     rcx, [rcx+30h]; HeapHandle
0x1400193b7  call    cs:__imp_RtlFreeHeap
0x1400193bd  mov     [rsp+100h+P], r13
0x1400193c2  mov     rax, [rbp+47h+var_B8]
0x1400193c6  mov     ebx, r13d
0x1400193c9  mov     [rax], rdi
0x1400193cc  mov     rax, [rbp+47h+var_B0]
0x1400193d0  mov     [rax], r14d
0x1400193d3  cmp     [rsp+100h+P], r13
0x1400193d8  jz      short loc_1400193F4
0x1400193da  mov     rcx, gs:60h
0x1400193e3  xor     edx, edx; Flags
0x1400193e5  mov     r8, [rsp+100h+P]; P
0x1400193ea  mov     rcx, [rcx+30h]; HeapHandle
0x1400193ee  call    cs:__imp_RtlFreeHeap
0x1400193f4  mov     eax, ebx
0x1400193f6  mov     rcx, [rbp+47h+var_40]
0x1400193fa  xor     rcx, rsp; StackCookie
0x1400193fd  call    __security_check_cookie
0x140019402  mov     rbx, [rsp+100h+arg_0]
0x14001940a  add     rsp, 0D0h
0x140019411  pop     r15
0x140019413  pop     r14
0x140019415  pop     r13
0x140019417  pop     r12
0x140019419  pop     rdi
0x14001941a  pop     rsi
0x14001941b  pop     rbp
0x14001941c  retn
```
