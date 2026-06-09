# BiCreateBootEntry

- ea: `0x1400228bc`
- end: `0x140022cb2`
- name: `BiCreateBootEntry`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140022cb8`

## callees

- `0x1400133e4`
- `0x14001a5d8`
- `0x14001f1a4`
- `0x1400228bc`
- `0x140024b30`
- `0x1400265e2`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140022bae`
- `msvcrt!swprintf_s` at `0x140022bae`
- `ntdll!RtlAllocateHeap` at `0x140022a1e`
- `ntdll!RtlAllocateHeap` at `0x140022b0e`
- `ntdll!RtlAllocateHeap` at `0x140022a1e`
- `ntdll!RtlAllocateHeap` at `0x140022b0e`
- `ntdll!RtlFreeHeap` at `0x140022c08`
- `ntdll!RtlFreeHeap` at `0x140022c25`
- `ntdll!RtlFreeHeap` at `0x140022c42`
- `ntdll!RtlFreeHeap` at `0x140022c5f`
- `ntdll!RtlFreeHeap` at `0x140022c7c`
- `ntdll!RtlFreeHeap` at `0x140022c99`
- `ntdll!RtlFreeHeap` at `0x140022c08`
- `ntdll!RtlFreeHeap` at `0x140022c25`
- `ntdll!RtlFreeHeap` at `0x140022c42`
- `ntdll!RtlFreeHeap` at `0x140022c5f`
- `ntdll!RtlFreeHeap` at `0x140022c7c`
- `ntdll!RtlFreeHeap` at `0x140022c99`

## string_xrefs

- `0x140022923`: `BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x`
- `0x140022956`: `BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x`
- `0x14002298e`: `BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x`

## pseudocode

```c
__int64 __fastcall BiCreateBootEntry(__int64 a1, _QWORD *a2)
{
  _DWORD *v2; // rdi
  void *v3; // rsi
  unsigned int *v4; // r14
  void *v5; // r13
  char *v6; // r15
  int Element; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  __int64 v12; // r12
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  char *Heap; // rax
  __int64 v20; // rbx
  size_t v21; // r8
  int KeyName; // eax
  int v23; // r8d
  unsigned int v24; // ecx
  PVOID ProcessHeap; // rcx
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  int v28; // ecx
  size_t v29; // r8
  PVOID v30; // rdx
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  size_t v36; // [rsp+30h] [rbp-38h] BYREF
  void *v37; // [rsp+38h] [rbp-30h] BYREF
  void *Src; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v39; // [rsp+48h] [rbp-20h] BYREF
  void *v40; // [rsp+50h] [rbp-18h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-10h] BYREF
  size_t v44; // [rsp+C0h] [rbp+58h] BYREF
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  LODWORD(v44) = 0;
  LODWORD(Size) = 0;
  LODWORD(v36) = 0;
  v2 = 0;
  P[0] = 0;
  v3 = 0;
  v39 = 0;
  v4 = 0;
  Src = 0;
  v5 = 0;
  v37 = 0;
  v6 = 0;
  v40 = 0;
  Element = BiGetElement(a1, 301989892, P, &v44);
  v9 = Element;
  if ( Element < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x",
      (unsigned int)Element);
    goto LABEL_25;
  }
  v10 = BiGetElement(a1, 285212673, &v39, &Size);
  v9 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x",
      (unsigned int)v10);
    v2 = v39;
    goto LABEL_25;
  }
  v11 = BiGetElement(a1, 301989890, &Src, &v36);
  v9 = v11;
  if ( v11 < 0 )
  {
    BiLogMessage(4, L"BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x", (unsigned int)v11);
    v2 = v39;
    v3 = Src;
    goto LABEL_25;
  }
  v2 = v39;
  v3 = Src;
  if ( *v39 != 2 )
  {
    v9 = -1073741637;
    goto LABEL_25;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)Src + v13) );
  v14 = 2 * v13 + 2;
  v15 = -1;
  LODWORD(v36) = v14;
  do
    ++v15;
  while ( *((_WORD *)v39 + v15 + 10) );
  v16 = 2 * v15 + 2;
  v17 = v16 + v14;
  LODWORD(Size) = v16;
  if ( v16 + v14 < v16 )
    goto LABEL_24;
  v18 = v17 + 12;
  if ( v17 + 12 < v17 )
    goto LABEL_24;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  v6 = Heap;
  if ( !Heap )
  {
LABEL_16:
    v9 = -1073741670;
    goto LABEL_25;
  }
  *((_DWORD *)Heap + 1) = v18;
  v20 = (unsigned int)Size;
  v21 = (unsigned int)Size;
  *(_DWORD *)Heap = 1;
  *((_DWORD *)Heap + 2) = 3;
  memcpy_0(Heap + 12, v2 + 5, v21);
  memcpy_0(&v6[v20 + 12], v3, (unsigned int)v36);
  v9 = BiTranslateFilePath(v6, 4, &v37);
  if ( v9 < 0 || (KeyName = BiGetKeyName(a1, &v40), v5 = v40, v9 = KeyName, KeyName < 0) )
  {
    v4 = (unsigned int *)v37;
    goto LABEL_25;
  }
  do
    ++v12;
  while ( *((_WORD *)v40 + v12) );
  v4 = (unsigned int *)v37;
  LODWORD(v39) = (2 * v12 + 45) & 0xFFFFFFFC;
  LODWORD(v36) = (_DWORD)v39 + 16;
  v23 = *((_DWORD *)v37 + 1);
  v24 = ((_DWORD)v39 + 47) & 0xFFFFFFFC;
  LODWORD(Src) = v24;
  if ( (unsigned int)v44 + v24 + v23 + 4 < (unsigned int)v44 )
  {
LABEL_24:
    v9 = -1073741675;
  }
  else
  {
    LODWORD(Size) = (v24 + v44 + 3) & 0xFFFFFFFC;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    LODWORD(v37) = v23 + Size;
    v26 = RtlAllocateHeap(ProcessHeap, 0, (unsigned int)(v23 + Size));
    v27 = v26;
    if ( !v26 )
      goto LABEL_16;
    v28 = Size;
    v29 = (unsigned int)v44;
    v30 = P[0];
    *v26 = 1;
    v31 = (int)v37;
    v27[5] = v28;
    v32 = v36;
    v27[1] = v31;
    v33 = (unsigned int)Src;
    v27[6] = v32;
    v27[2] = -1;
    v27[3] = 5;
    v27[4] = v33;
    memcpy_0((char *)v27 + v33, v30, v29);
    memcpy_0((char *)v27 + (unsigned int)Size, v4, v4[1]);
    *(_QWORD *)(v27 + 7) = 0x53574F444E4957LL;
    v27[10] = v36;
    v27[11] = (_DWORD)v39;
    v27[9] = 1;
    swprintf_s((wchar_t *const)v27 + 24, (unsigned int)v12 + 11LL, L"%s%s", L"BCDOBJECT=", v5);
    v34 = (unsigned int)v27[11];
    *(_DWORD *)((char *)v27 + v34 + 28) = 1;
    *(_DWORD *)((char *)v27 + v34 + 32) = 16;
    *(_DWORD *)((char *)v27 + v34 + 36) = 4;
    *(_DWORD *)((char *)v27 + v34 + 40) = 327551;
    *a2 = v27;
    v9 = 0;
  }
LABEL_25:
  if ( P[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400228bc  mov     [rsp-40h+arg_8], rdx
0x1400228c1  mov     [rsp-40h+arg_0], rcx
0x1400228c6  push    rbp
0x1400228c7  push    rbx
0x1400228c8  push    rsi
0x1400228c9  push    rdi
0x1400228ca  push    r12
0x1400228cc  push    r13
0x1400228ce  push    r14
0x1400228d0  push    r15
0x1400228d2  mov     rbp, rsp
0x1400228d5  sub     rsp, 68h
0x1400228d9  xor     eax, eax
0x1400228db  lea     r9, [rbp+arg_10]
0x1400228df  lea     r8, [rbp+P]
0x1400228e3  mov     dword ptr [rbp+arg_10], eax
0x1400228e6  mov     edx, 12000004h
0x1400228eb  mov     dword ptr [rbp+Size], eax
0x1400228ee  mov     dword ptr [rbp+var_38], eax
0x1400228f1  mov     edi, eax
0x1400228f3  mov     [rbp+P], rax
0x1400228f7  mov     esi, eax
0x1400228f9  mov     [rbp+var_20], rax
0x1400228fd  mov     r14d, eax
0x140022900  mov     [rbp+Src], rax
0x140022904  mov     r13d, eax
0x140022907  mov     [rbp+var_30], rax
0x14002290b  mov     r15d, eax
0x14002290e  mov     [rbp+var_18], rax
0x140022912  mov     r12, rcx
0x140022915  call    BiGetElement
0x14002291a  mov     ebx, eax
0x14002291c  test    eax, eax
0x14002291e  jns     short loc_140022938
0x140022920  mov     r8d, eax
0x140022923  lea     rdx, aBicreatebooten_0; "BiCreateBootEntry: Could not retrieve B"...
0x14002292a  lea     ecx, [r15+4]
0x14002292e  call    BiLogMessage
0x140022933  jmp     loc_140022BED
0x140022938  lea     r9, [rbp+Size]
0x14002293c  mov     edx, 11000001h
0x140022941  lea     r8, [rbp+var_20]
0x140022945  mov     rcx, r12
0x140022948  call    BiGetElement
0x14002294d  mov     ebx, eax
0x14002294f  test    eax, eax
0x140022951  jns     short loc_140022970
0x140022953  mov     r8d, eax
0x140022956  lea     rdx, aBicreatebooten_1; "BiCreateBootEntry: Could not retrieve B"...
0x14002295d  mov     ecx, 4
0x140022962  call    BiLogMessage
0x140022967  mov     rdi, [rbp+var_20]
0x14002296b  jmp     loc_140022BED
0x140022970  lea     r9, [rbp+var_38]
0x140022974  mov     edx, 12000002h
0x140022979  lea     r8, [rbp+Src]
0x14002297d  mov     rcx, r12
0x140022980  call    BiGetElement
0x140022985  mov     ebx, eax
0x140022987  test    eax, eax
0x140022989  jns     short loc_1400229AC
0x14002298b  mov     r8d, eax
0x14002298e  lea     rdx, aBicreatebooten; "BiCreateBootEntry: Could not retrieve B"...
0x140022995  mov     ecx, 4
0x14002299a  call    BiLogMessage
0x14002299f  mov     rdi, [rbp+var_20]
0x1400229a3  mov     rsi, [rbp+Src]
0x1400229a7  jmp     loc_140022BED
0x1400229ac  mov     rdi, [rbp+var_20]
0x1400229b0  mov     rsi, [rbp+Src]
0x1400229b4  cmp     dword ptr [rdi], 2
0x1400229b7  jz      short loc_1400229C3
0x1400229b9  mov     ebx, 0C00000BBh
0x1400229be  jmp     loc_140022BED
0x1400229c3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400229c7  mov     rax, r12
0x1400229ca  xor     ebx, ebx
0x1400229cc  inc     rax
0x1400229cf  cmp     [rsi+rax*2], bx
0x1400229d3  jnz     short loc_1400229CC
0x1400229d5  lea     edx, ds:2[rax*2]
0x1400229dc  mov     rax, r12
0x1400229df  mov     dword ptr [rbp+var_38], edx
0x1400229e2  inc     rax
0x1400229e5  cmp     [rdi+rax*2+14h], bx
0x1400229ea  jnz     short loc_1400229E2
0x1400229ec  lea     ecx, ds:2[rax*2]
0x1400229f3  lea     eax, [rcx+rdx]
0x1400229f6  mov     dword ptr [rbp+Size], ecx
0x1400229f9  cmp     eax, ecx
0x1400229fb  jb      loc_140022BE8
0x140022a01  lea     ebx, [rax+0Ch]
0x140022a04  cmp     ebx, eax
0x140022a06  jb      loc_140022BE8
0x140022a0c  mov     rcx, gs:60h
0x140022a15  xor     edx, edx; Flags
0x140022a17  mov     r8d, ebx; Size
0x140022a1a  mov     rcx, [rcx+30h]; HeapHandle
0x140022a1e  call    cs:__imp_RtlAllocateHeap
0x140022a24  mov     r15, rax
0x140022a27  test    rax, rax
0x140022a2a  jnz     short loc_140022A36
0x140022a2c  mov     ebx, 0C000009Ah
0x140022a31  jmp     loc_140022BED
0x140022a36  mov     [rax+4], ebx
0x140022a39  lea     rcx, [rax+0Ch]; void *
0x140022a3d  mov     ebx, dword ptr [rbp+Size]
0x140022a40  lea     rdx, [rdi+14h]; Src
0x140022a44  mov     r8d, ebx; Size
0x140022a47  mov     dword ptr [rax], 1
0x140022a4d  mov     dword ptr [rax+8], 3
0x140022a54  call    memcpy_0
0x140022a59  mov     r8d, dword ptr [rbp+var_38]; Size
0x140022a5d  lea     rcx, [rbx+0Ch]
0x140022a61  add     rcx, r15; void *
0x140022a64  mov     rdx, rsi; Src
0x140022a67  call    memcpy_0
0x140022a6c  lea     r8, [rbp+var_30]
0x140022a70  mov     edx, 4
0x140022a75  mov     rcx, r15
0x140022a78  call    BiTranslateFilePath
0x140022a7d  mov     ebx, eax
0x140022a7f  test    eax, eax
0x140022a81  js      loc_140022BE2
0x140022a87  mov     rcx, [rbp+arg_0]
0x140022a8b  lea     rdx, [rbp+var_18]
0x140022a8f  call    BiGetKeyName
0x140022a94  mov     r13, [rbp+var_18]
0x140022a98  mov     ebx, eax
0x140022a9a  test    eax, eax
0x140022a9c  js      loc_140022BE2
0x140022aa2  inc     r12
0x140022aa5  cmp     [r13+r12*2+0], r14w
0x140022aab  jnz     short loc_140022AA2
0x140022aad  mov     edx, dword ptr [rbp+arg_10]
0x140022ab0  lea     eax, ds:2Dh[r12*2]
0x140022ab8  mov     r14, [rbp+var_30]
0x140022abc  mov     r9d, 0FFFFFFFCh
0x140022ac2  and     eax, r9d
0x140022ac5  mov     dword ptr [rbp+var_20], eax
0x140022ac8  add     eax, 10h
0x140022acb  mov     dword ptr [rbp+var_38], eax
0x140022ace  mov     r8d, [r14+4]
0x140022ad2  lea     ecx, [rax+1Fh]
0x140022ad5  and     ecx, r9d
0x140022ad8  lea     eax, [r8+4]
0x140022adc  mov     dword ptr [rbp+Src], ecx
0x140022adf  add     eax, ecx
0x140022ae1  add     eax, edx
0x140022ae3  cmp     eax, edx
0x140022ae5  jb      loc_140022BE8
0x140022aeb  lea     eax, [rdx+3]
0x140022aee  xor     edx, edx; Flags
0x140022af0  add     eax, ecx
0x140022af2  mov     rcx, gs:60h
0x140022afb  and     eax, r9d
0x140022afe  mov     dword ptr [rbp+Size], eax
0x140022b01  add     eax, r8d
0x140022b04  mov     r8d, eax; Size
0x140022b07  mov     rcx, [rcx+30h]; HeapHandle
0x140022b0b  mov     dword ptr [rbp+var_30], eax
0x140022b0e  call    cs:__imp_RtlAllocateHeap
0x140022b14  mov     rbx, rax
0x140022b17  test    rax, rax
0x140022b1a  jz      loc_140022A2C
0x140022b20  mov     ecx, dword ptr [rbp+Size]
0x140022b23  mov     r8d, dword ptr [rbp+arg_10]; Size
0x140022b27  mov     rdx, [rbp+P]; Src
0x140022b2b  mov     dword ptr [rax], 1
0x140022b31  mov     eax, dword ptr [rbp+var_30]
0x140022b34  mov     [rbx+14h], ecx
0x140022b37  mov     ecx, dword ptr [rbp+var_38]
0x140022b3a  mov     [rbx+4], eax
0x140022b3d  mov     eax, dword ptr [rbp+Src]
0x140022b40  mov     [rbx+18h], ecx
0x140022b43  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x140022b4a  mov     dword ptr [rbx+0Ch], 5
0x140022b51  lea     rcx, [rbx+rax]; void *
0x140022b55  mov     [rbx+10h], eax
0x140022b58  call    memcpy_0
0x140022b5d  mov     ecx, dword ptr [rbp+Size]
0x140022b60  mov     rdx, r14; Src
0x140022b63  mov     r8d, [r14+4]; Size
0x140022b67  add     rcx, rbx; void *
0x140022b6a  call    memcpy_0
0x140022b6f  mov     rax, 53574F444E4957h
0x140022b79  mov     edx, r12d
0x140022b7c  mov     [rbx+1Ch], rax
0x140022b80  lea     rcx, [rbx+30h]; Buffer
0x140022b84  mov     eax, dword ptr [rbp+var_38]
0x140022b87  lea     r9, aBcdobject; "BCDOBJECT="
0x140022b8e  mov     [rbx+28h], eax
0x140022b91  lea     r8, aSS_0; "%s%s"
0x140022b98  mov     eax, dword ptr [rbp+var_20]
0x140022b9b  add     rdx, 0Bh; BufferCount
0x140022b9f  mov     [rbx+2Ch], eax
0x140022ba2  mov     dword ptr [rbx+24h], 1
0x140022ba9  mov     [rsp+68h+var_48], r13
0x140022bae  call    cs:__imp_swprintf_s
0x140022bb4  mov     eax, [rbx+2Ch]
0x140022bb7  mov     dword ptr [rax+rbx+1Ch], 1
0x140022bbf  mov     dword ptr [rax+rbx+20h], 10h
0x140022bc7  mov     dword ptr [rax+rbx+24h], 4
0x140022bcf  mov     dword ptr [rax+rbx+28h], 4FF7Fh
0x140022bd7  mov     rax, [rbp+arg_8]
0x140022bdb  mov     [rax], rbx
0x140022bde  xor     ebx, ebx
0x140022be0  jmp     short loc_140022BED
0x140022be2  mov     r14, [rbp+var_30]
0x140022be6  jmp     short loc_140022BED
0x140022be8  mov     ebx, 0C0000095h
0x140022bed  mov     rax, [rbp+P]
0x140022bf1  test    rax, rax
0x140022bf4  jz      short loc_140022C0E
0x140022bf6  mov     rcx, gs:60h
0x140022bff  mov     r8, rax; P
0x140022c02  xor     edx, edx; Flags
0x140022c04  mov     rcx, [rcx+30h]; HeapHandle
0x140022c08  call    cs:__imp_RtlFreeHeap
0x140022c0e  test    rdi, rdi
0x140022c11  jz      short loc_140022C2B
0x140022c13  mov     rcx, gs:60h
0x140022c1c  mov     r8, rdi; P
0x140022c1f  xor     edx, edx; Flags
0x140022c21  mov     rcx, [rcx+30h]; HeapHandle
0x140022c25  call    cs:__imp_RtlFreeHeap
0x140022c2b  test    rsi, rsi
0x140022c2e  jz      short loc_140022C48
0x140022c30  mov     rcx, gs:60h
0x140022c39  mov     r8, rsi; P
0x140022c3c  xor     edx, edx; Flags
0x140022c3e  mov     rcx, [rcx+30h]; HeapHandle
0x140022c42  call    cs:__imp_RtlFreeHeap
0x140022c48  test    r14, r14
0x140022c4b  jz      short loc_140022C65
0x140022c4d  mov     rcx, gs:60h
0x140022c56  mov     r8, r14; P
0x140022c59  xor     edx, edx; Flags
0x140022c5b  mov     rcx, [rcx+30h]; HeapHandle
0x140022c5f  call    cs:__imp_RtlFreeHeap
0x140022c65  test    r13, r13
0x140022c68  jz      short loc_140022C82
0x140022c6a  mov     rcx, gs:60h
0x140022c73  mov     r8, r13; P
0x140022c76  xor     edx, edx; Flags
0x140022c78  mov     rcx, [rcx+30h]; HeapHandle
0x140022c7c  call    cs:__imp_RtlFreeHeap
0x140022c82  test    r15, r15
0x140022c85  jz      short loc_140022C9F
0x140022c87  mov     rcx, gs:60h
0x140022c90  mov     r8, r15; P
0x140022c93  xor     edx, edx; Flags
0x140022c95  mov     rcx, [rcx+30h]; HeapHandle
0x140022c99  call    cs:__imp_RtlFreeHeap
0x140022c9f  mov     eax, ebx
0x140022ca1  add     rsp, 68h
0x140022ca5  pop     r15
0x140022ca7  pop     r14
0x140022ca9  pop     r13
0x140022cab  pop     r12
0x140022cad  pop     rdi
0x140022cae  pop     rsi
0x140022caf  pop     rbx
0x140022cb0  pop     rbp
0x140022cb1  retn
```
