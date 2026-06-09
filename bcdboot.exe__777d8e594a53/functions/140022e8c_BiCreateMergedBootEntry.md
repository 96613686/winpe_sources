# BiCreateMergedBootEntry

- ea: `0x140022e8c`
- end: `0x140023210`
- name: `BiCreateMergedBootEntry`
- size: `900`
- prototype: `__int64 __fastcall(_DWORD *, _WORD *, _DWORD *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140024cf0`
- `0x14002515c`

## callees

- `0x1400133e4`
- `0x140022e8c`
- `0x140023f80`
- `0x140024160`
- `0x140024b30`
- `0x1400265e2`
- `0x1400265fa`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140022fd7`
- `ntdll!RtlAllocateHeap` at `0x1400230c0`
- `ntdll!RtlAllocateHeap` at `0x140022fd7`
- `ntdll!RtlAllocateHeap` at `0x1400230c0`
- `ntdll!RtlFreeHeap` at `0x140023197`
- `ntdll!RtlFreeHeap` at `0x1400231b5`
- `ntdll!RtlFreeHeap` at `0x1400231d3`
- `ntdll!RtlFreeHeap` at `0x1400231f0`
- `ntdll!RtlFreeHeap` at `0x140023197`
- `ntdll!RtlFreeHeap` at `0x1400231b5`
- `ntdll!RtlFreeHeap` at `0x1400231d3`
- `ntdll!RtlFreeHeap` at `0x1400231f0`

## string_xrefs

- `0x14002316b`: `BiCreateMergedBootEntry failed %x`

## pseudocode

```c
__int64 __fastcall BiCreateMergedBootEntry(_DWORD *a1, _WORD *a2, _DWORD *a3, _WORD *a4, _QWORD *a5)
{
  __int64 v5; // r13
  _WORD *v6; // rax
  _WORD *v7; // rbx
  _DWORD *v9; // rdi
  _WORD *v10; // r14
  char *v11; // r15
  int DeviceFromEfiPath; // ebx
  char *v13; // r12
  int FilePathFromEfiPath; // eax
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  char *Heap; // rax
  __int64 v21; // rbx
  size_t v22; // r8
  int v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // r13d
  int v26; // r8d
  _DWORD *v27; // rax
  _DWORD *v28; // r12
  __int64 v29; // rcx
  int v30; // eax
  char v32; // [rsp+20h] [rbp-30h]
  size_t Size; // [rsp+24h] [rbp-2Ch] BYREF
  _DWORD *v34; // [rsp+30h] [rbp-20h] BYREF
  void *Src; // [rsp+38h] [rbp-18h] BYREF
  PVOID P; // [rsp+40h] [rbp-10h]
  char v38; // [rsp+A0h] [rbp+50h]

  v5 = -1;
  v6 = a4;
  Size = 0;
  v7 = a2;
  P = 0;
  v34 = 0;
  v9 = 0;
  v38 = 0;
  v10 = 0;
  Src = 0;
  v11 = 0;
  v32 = 0;
  if ( !a3 )
  {
    v9 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
    if ( !a4 )
      goto LABEL_23;
    v34 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
    DeviceFromEfiPath = BiGetDeviceFromEfiPath(v9 + 3);
    if ( DeviceFromEfiPath < 0 )
      goto LABEL_32;
    v6 = a4;
    v13 = (char *)P + 20;
    goto LABEL_12;
  }
  if ( *a3 != 5 )
  {
    if ( *a3 != 2 )
    {
      DeviceFromEfiPath = -1073741811;
      goto LABEL_32;
    }
    v13 = (char *)(a3 + 5);
    if ( !a4 )
    {
      v9 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
      v34 = v9;
      FilePathFromEfiPath = BiGetFilePathFromEfiPath(v9 + 3, &Src, &Size);
      v10 = Src;
      DeviceFromEfiPath = FilePathFromEfiPath;
      if ( FilePathFromEfiPath < 0 )
        goto LABEL_32;
      v32 = 1;
      goto LABEL_13;
    }
LABEL_12:
    v10 = v6;
LABEL_13:
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v13[2 * v15] );
    v16 = 2 * v15 + 2;
    v17 = -1;
    HIDWORD(Size) = v16;
    do
      ++v17;
    while ( v10[v17] );
    LODWORD(Size) = 2 * v17 + 2;
    v18 = v16 + Size;
    if ( v16 + (unsigned int)Size < v16 || (v19 = v18 + 12, v18 + 12 < v18) )
    {
      DeviceFromEfiPath = -1073741675;
      goto LABEL_32;
    }
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
    v11 = Heap;
    if ( !Heap )
    {
LABEL_20:
      DeviceFromEfiPath = -1073741670;
      goto LABEL_32;
    }
    *((_DWORD *)Heap + 1) = v19;
    v21 = HIDWORD(Size);
    v22 = HIDWORD(Size);
    *(_DWORD *)Heap = 1;
    *((_DWORD *)Heap + 2) = 3;
    memcpy_0(Heap + 12, v13, v22);
    memcpy_0(&v11[v21 + 12], v10, (unsigned int)Size);
    v23 = BiTranslateFilePath(v11, 4, &v34);
    v9 = v34;
    DeviceFromEfiPath = v23;
    if ( v23 < 0 )
      goto LABEL_32;
    v7 = a2;
    v38 = 1;
LABEL_23:
    if ( !v7 )
      v7 = (_WORD *)((char *)a1 + (unsigned int)a1[4]);
    do
      ++v5;
    while ( v7[v5] );
    v24 = a1[6];
    v25 = 2 * v5 + 2;
    if ( v24 + v25 < v24 || (v26 = v9[1], v24 + v25 + v26 + 36 < v24 + v25) )
    {
      DeviceFromEfiPath = -1073741675;
      goto LABEL_32;
    }
    LODWORD(v34) = (v24 + 31) & 0xFFFFFFFC;
    LODWORD(Size) = (v25 + (_DWORD)v34 + 3) & 0xFFFFFFFC;
    HIDWORD(Size) = v26 + Size;
    Src = (void *)(unsigned int)(v26 + Size);
    v27 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Src);
    v28 = v27;
    if ( v27 )
    {
      memset_0(v27, 0, (size_t)Src);
      v29 = (unsigned int)v34;
      v28[1] = HIDWORD(Size);
      *v28 = 1;
      v28[2] = a1[2];
      v28[3] = a1[3];
      v30 = Size;
      v28[4] = v29;
      v28[5] = v30;
      v28[6] = a1[6];
      memcpy_0((char *)v28 + v29, v7, v25);
      memcpy_0((char *)v28 + (unsigned int)Size, v9, (unsigned int)v9[1]);
      memcpy_0(v28 + 7, a1 + 7, (unsigned int)a1[6]);
      *a5 = v28;
      DeviceFromEfiPath = 0;
      goto LABEL_33;
    }
    goto LABEL_20;
  }
  DeviceFromEfiPath = -1073741810;
LABEL_32:
  BiLogMessage(4, L"BiCreateMergedBootEntry failed %x", (unsigned int)DeviceFromEfiPath);
LABEL_33:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v38 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v32 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return (unsigned int)DeviceFromEfiPath;
}

```

## disassembly

```asm
0x140022e8c  mov     [rsp-38h+arg_0], rbx
0x140022e91  mov     [rsp-38h+arg_18], r9
0x140022e96  mov     [rsp-38h+arg_8], rdx
0x140022e9b  push    rbp
0x140022e9c  push    rsi
0x140022e9d  push    rdi
0x140022e9e  push    r12
0x140022ea0  push    r13
0x140022ea2  push    r14
0x140022ea4  push    r15
0x140022ea6  mov     rbp, rsp
0x140022ea9  sub     rsp, 50h
0x140022ead  xor     r12d, r12d
0x140022eb0  or      r13, 0FFFFFFFFFFFFFFFFh
0x140022eb4  mov     dword ptr [rbp+Size+4], r12d
0x140022eb8  mov     rax, r9
0x140022ebb  mov     dword ptr [rbp+Size], r12d
0x140022ebf  mov     rbx, rdx
0x140022ec2  mov     [rbp+P], r12
0x140022ec6  mov     rsi, rcx
0x140022ec9  mov     [rbp+var_20], r12
0x140022ecd  mov     edi, r12d
0x140022ed0  mov     [rbp+arg_10], r12b
0x140022ed4  mov     r14d, r12d
0x140022ed7  mov     [rbp+Src], r12
0x140022edb  mov     r15d, r12d
0x140022ede  mov     [rbp+var_30], r12b
0x140022ee2  test    r8, r8
0x140022ee5  jz      short loc_140022F43
0x140022ee7  cmp     dword ptr [r8], 5
0x140022eeb  jnz     short loc_140022EF7
0x140022eed  mov     ebx, 0C000000Eh
0x140022ef2  jmp     loc_140023168
0x140022ef7  cmp     dword ptr [r8], 2
0x140022efb  jz      short loc_140022F07
0x140022efd  mov     ebx, 0C000000Dh
0x140022f02  jmp     loc_140023168
0x140022f07  xor     edx, edx
0x140022f09  lea     r12, [r8+14h]
0x140022f0d  test    rax, rax
0x140022f10  jnz     short loc_140022F7F
0x140022f12  mov     edi, [rcx+14h]
0x140022f15  lea     r8, [rbp+Size]
0x140022f19  add     rdi, rsi
0x140022f1c  lea     rdx, [rbp+Src]
0x140022f20  mov     [rbp+var_20], rdi
0x140022f24  lea     rcx, [rdi+0Ch]
0x140022f28  call    BiGetFilePathFromEfiPath
0x140022f2d  mov     r14, [rbp+Src]
0x140022f31  xor     edx, edx
0x140022f33  mov     ebx, eax
0x140022f35  test    eax, eax
0x140022f37  js      loc_140023165
0x140022f3d  mov     [rbp+var_30], 1
0x140022f41  jmp     short loc_140022F82
0x140022f43  mov     edi, [rcx+14h]
0x140022f46  add     rdi, rsi
0x140022f49  test    rax, rax
0x140022f4c  jz      loc_14002304E
0x140022f52  lea     rcx, [rdi+0Ch]; Src
0x140022f56  mov     [rbp+var_20], rdi
0x140022f5a  lea     r8, [rbp+Size+4]
0x140022f5e  lea     rdx, [rbp+P]
0x140022f62  call    BiGetDeviceFromEfiPath
0x140022f67  mov     ebx, eax
0x140022f69  test    eax, eax
0x140022f6b  js      loc_140023168
0x140022f71  mov     r12, [rbp+P]
0x140022f75  mov     rax, [rbp+arg_18]
0x140022f79  add     r12, 14h
0x140022f7d  xor     edx, edx
0x140022f7f  mov     r14, rax
0x140022f82  mov     rax, r13
0x140022f85  inc     rax
0x140022f88  cmp     [r12+rax*2], dx
0x140022f8d  jnz     short loc_140022F85
0x140022f8f  lea     ecx, ds:2[rax*2]
0x140022f96  mov     rax, r13
0x140022f99  mov     dword ptr [rbp+Size+4], ecx
0x140022f9c  inc     rax
0x140022f9f  cmp     [r14+rax*2], dx
0x140022fa4  jnz     short loc_140022F9C
0x140022fa6  lea     eax, ds:2[rax*2]
0x140022fad  mov     dword ptr [rbp+Size], eax
0x140022fb0  add     eax, ecx
0x140022fb2  cmp     eax, ecx
0x140022fb4  jb      loc_140023160
0x140022fba  lea     ebx, [rax+0Ch]
0x140022fbd  cmp     ebx, eax
0x140022fbf  jb      loc_140023160
0x140022fc5  mov     rcx, gs:60h
0x140022fce  xor     edx, edx; Flags
0x140022fd0  mov     r8d, ebx; Size
0x140022fd3  mov     rcx, [rcx+30h]; HeapHandle
0x140022fd7  call    cs:__imp_RtlAllocateHeap
0x140022fdd  mov     r15, rax
0x140022fe0  test    rax, rax
0x140022fe3  jnz     short loc_140022FEF
0x140022fe5  mov     ebx, 0C000009Ah
0x140022fea  jmp     loc_140023165
0x140022fef  mov     [rax+4], ebx
0x140022ff2  lea     rcx, [rax+0Ch]; void *
0x140022ff6  mov     ebx, dword ptr [rbp+Size+4]
0x140022ff9  mov     rdx, r12; Src
0x140022ffc  mov     r8d, ebx; Size
0x140022fff  mov     dword ptr [rax], 1
0x140023005  mov     dword ptr [rax+8], 3
0x14002300c  call    memcpy_0
0x140023011  mov     r8d, dword ptr [rbp+Size]; Size
0x140023015  lea     rcx, [rbx+0Ch]
0x140023019  add     rcx, r15; void *
0x14002301c  mov     rdx, r14; Src
0x14002301f  call    memcpy_0
0x140023024  lea     r8, [rbp+var_20]
0x140023028  mov     edx, 4
0x14002302d  mov     rcx, r15
0x140023030  call    BiTranslateFilePath
0x140023035  mov     rdi, [rbp+var_20]
0x140023039  xor     r12d, r12d
0x14002303c  mov     ebx, eax
0x14002303e  test    eax, eax
0x140023040  js      loc_140023168
0x140023046  mov     rbx, [rbp+arg_8]
0x14002304a  mov     [rbp+arg_10], 1
0x14002304e  test    rbx, rbx
0x140023051  jnz     short loc_140023059
0x140023053  mov     ebx, [rsi+10h]
0x140023056  add     rbx, rsi
0x140023059  inc     r13
0x14002305c  cmp     [rbx+r13*2], r12w
0x140023061  jnz     short loc_140023059
0x140023063  mov     edx, [rsi+18h]
0x140023066  lea     r13d, ds:2[r13*2]
0x14002306e  lea     ecx, [rdx+r13]
0x140023072  cmp     ecx, edx
0x140023074  jb      loc_140023159
0x14002307a  mov     r8d, [rdi+4]
0x14002307e  lea     eax, [r8+24h]
0x140023082  add     eax, ecx
0x140023084  cmp     eax, ecx
0x140023086  jb      loc_140023159
0x14002308c  lea     eax, [rdx+1Fh]
0x14002308f  mov     ecx, 0FFFFFFFCh
0x140023094  and     eax, ecx
0x140023096  xor     edx, edx; Flags
0x140023098  mov     dword ptr [rbp+var_20], eax
0x14002309b  add     eax, 3
0x14002309e  add     eax, r13d
0x1400230a1  and     eax, ecx
0x1400230a3  mov     rcx, gs:60h
0x1400230ac  mov     dword ptr [rbp+Size], eax
0x1400230af  add     eax, r8d
0x1400230b2  mov     r8d, eax; Size
0x1400230b5  mov     dword ptr [rbp+Size+4], eax
0x1400230b8  mov     [rbp+Src], rax
0x1400230bc  mov     rcx, [rcx+30h]; HeapHandle
0x1400230c0  call    cs:__imp_RtlAllocateHeap
0x1400230c6  mov     r12, rax
0x1400230c9  test    rax, rax
0x1400230cc  jz      loc_140022FE5
0x1400230d2  mov     r8, [rbp+Src]; Size
0x1400230d6  xor     edx, edx; Val
0x1400230d8  mov     rcx, rax; void *
0x1400230db  call    memset_0
0x1400230e0  mov     eax, dword ptr [rbp+Size+4]
0x1400230e3  mov     rdx, rbx; Src
0x1400230e6  mov     ecx, dword ptr [rbp+var_20]
0x1400230e9  mov     [r12+4], eax
0x1400230ee  mov     dword ptr [r12], 1
0x1400230f6  mov     eax, [rsi+8]
0x1400230f9  mov     [r12+8], eax
0x1400230fe  mov     eax, [rsi+0Ch]
0x140023101  mov     [r12+0Ch], eax
0x140023106  mov     eax, dword ptr [rbp+Size]
0x140023109  mov     [r12+10h], ecx
0x14002310e  add     rcx, r12; void *
0x140023111  mov     [r12+14h], eax
0x140023116  mov     eax, [rsi+18h]
0x140023119  mov     r8d, r13d; Size
0x14002311c  mov     [r12+18h], eax
0x140023121  call    memcpy_0
0x140023126  mov     ecx, dword ptr [rbp+Size]
0x140023129  mov     rdx, rdi; Src
0x14002312c  mov     r8d, [rdi+4]; Size
0x140023130  add     rcx, r12; void *
0x140023133  call    memcpy_0
0x140023138  mov     r8d, [rsi+18h]; Size
0x14002313c  lea     rdx, [rsi+1Ch]; Src
0x140023140  lea     rcx, [r12+1Ch]; void *
0x140023145  call    memcpy_0
0x14002314a  mov     rax, [rbp+arg_20]
0x14002314e  mov     [rax], r12
0x140023151  xor     r12d, r12d
0x140023154  mov     ebx, r12d
0x140023157  jmp     short loc_14002317C
0x140023159  mov     ebx, 0C0000095h
0x14002315e  jmp     short loc_140023168
0x140023160  mov     ebx, 0C0000095h
0x140023165  xor     r12d, r12d
0x140023168  mov     r8d, ebx
0x14002316b  lea     rdx, aBicreatemerged; "BiCreateMergedBootEntry failed %x"
0x140023172  mov     ecx, 4
0x140023177  call    BiLogMessage
0x14002317c  mov     rax, [rbp+P]
0x140023180  test    rax, rax
0x140023183  jz      short loc_14002319D
0x140023185  mov     rcx, gs:60h
0x14002318e  mov     r8, rax; P
0x140023191  xor     edx, edx; Flags
0x140023193  mov     rcx, [rcx+30h]; HeapHandle
0x140023197  call    cs:__imp_RtlFreeHeap
0x14002319d  cmp     [rbp+arg_10], r12b
0x1400231a1  jz      short loc_1400231BB
0x1400231a3  mov     rcx, gs:60h
0x1400231ac  mov     r8, rdi; P
0x1400231af  xor     edx, edx; Flags
0x1400231b1  mov     rcx, [rcx+30h]; HeapHandle
0x1400231b5  call    cs:__imp_RtlFreeHeap
0x1400231bb  cmp     [rbp+var_30], r12b
0x1400231bf  jz      short loc_1400231D9
0x1400231c1  mov     rcx, gs:60h
0x1400231ca  mov     r8, r14; P
0x1400231cd  xor     edx, edx; Flags
0x1400231cf  mov     rcx, [rcx+30h]; HeapHandle
0x1400231d3  call    cs:__imp_RtlFreeHeap
0x1400231d9  test    r15, r15
0x1400231dc  jz      short loc_1400231F6
0x1400231de  mov     rcx, gs:60h
0x1400231e7  mov     r8, r15; P
0x1400231ea  xor     edx, edx; Flags
0x1400231ec  mov     rcx, [rcx+30h]; HeapHandle
0x1400231f0  call    cs:__imp_RtlFreeHeap
0x1400231f6  mov     eax, ebx
0x1400231f8  mov     rbx, [rsp+50h+arg_0]
0x140023200  add     rsp, 50h
0x140023204  pop     r15
0x140023206  pop     r14
0x140023208  pop     r13
0x14002320a  pop     r12
0x14002320c  pop     rdi
0x14002320d  pop     rsi
0x14002320e  pop     rbp
0x14002320f  retn
```
