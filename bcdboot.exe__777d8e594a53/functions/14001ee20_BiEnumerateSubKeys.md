# BiEnumerateSubKeys

- ea: `0x14001ee20`
- end: `0x14001f19e`
- name: `BiEnumerateSubKeys`
- size: `894`
- prototype: `__int64 __fastcall(unsigned __int64, char **, ULONG *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140013c1c`
- `0x140019bb8`
- `0x14001b354`
- `0x14001bd44`
- `0x14001ec14`
- `0x140022258`

## callees

- `0x14001ee20`
- `0x1400265e2`
- `0x140026650`

## import_xrefs

- `ntdll!ZwQueryKey` at `0x14001eeb9`
- `ntdll!ZwQueryKey` at `0x14001eeb9`
- `ntdll!ZwEnumerateKey` at `0x14001f024`
- `ntdll!ZwEnumerateKey` at `0x14001f024`
- `ntdll!RtlAllocateHeap` at `0x14001ef9b`
- `ntdll!RtlAllocateHeap` at `0x14001efe5`
- `ntdll!RtlAllocateHeap` at `0x14001ef9b`
- `ntdll!RtlAllocateHeap` at `0x14001efe5`
- `ntdll!RtlFreeHeap` at `0x14001f0f8`
- `ntdll!RtlFreeHeap` at `0x14001f119`
- `ntdll!RtlFreeHeap` at `0x14001f0f8`
- `ntdll!RtlFreeHeap` at `0x14001f119`

## pseudocode

```c
__int64 __fastcall BiEnumerateSubKeys(unsigned __int64 a1, char **a2, ULONG *a3)
{
  unsigned int v4; // esi
  unsigned int *v5; // r13
  char *Heap; // r15
  NTSTATUS v7; // ebx
  __int64 v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // esi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // eax
  ULONG v16; // ebx
  ULONG v17; // r15d
  NTSTATUS v18; // eax
  char *v19; // rbx
  char *v20; // rcx
  unsigned int i; // [rsp+34h] [rbp-B4h]
  char *v23; // [rsp+38h] [rbp-B0h]
  ULONG ResultLength; // [rsp+40h] [rbp-A8h] BYREF
  int v25; // [rsp+44h] [rbp-A4h]
  HANDLE KeyHandle; // [rsp+48h] [rbp-A0h]
  char **v27; // [rsp+50h] [rbp-98h]
  ULONG *v28; // [rsp+58h] [rbp-90h]
  void *v29; // [rsp+60h] [rbp-88h]
  char **v30; // [rsp+68h] [rbp-80h]
  ULONG *v31; // [rsp+70h] [rbp-78h]
  __int128 KeyInformation; // [rsp+78h] [rbp-70h] BYREF
  __int128 v33; // [rsp+88h] [rbp-60h]
  __int128 v34; // [rsp+98h] [rbp-50h]

  v28 = a3;
  v27 = a2;
  v30 = a2;
  v31 = a3;
  KeyInformation = 0;
  v33 = 0;
  v34 = 0;
  ResultLength = 0;
  v4 = 0;
  for ( i = 0; ; i = v4 )
  {
    *a2 = 0;
    *a3 = 0;
    v5 = 0;
    Heap = 0;
    KeyHandle = (HANDLE)(a1 & 0xFFFFFFFFFFFFFFFDuLL);
    v7 = ZwQueryKey((HANDLE)(a1 & 0xFFFFFFFFFFFFFFFDuLL), KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
    if ( ((v7 + 0x80000000) & 0x80000000) != 0 || v7 == -2147483643 )
    {
      v8 = DWORD1(v33);
      if ( !DWORD1(v33) )
      {
        v7 = 0;
        goto LABEL_35;
      }
      v9 = DWORD2(v33) + 2;
      v10 = -1;
      if ( (unsigned int)(DWORD2(v33) + 2) >= DWORD2(v33) )
        v10 = DWORD2(v33) + 2;
      v7 = v9 < DWORD2(v33) ? 0xC0000095 : 0;
      if ( v9 >= DWORD2(v33) )
      {
        v11 = v10 * (unsigned __int64)DWORD1(v33);
        v10 *= DWORD1(v33);
        if ( v11 > 0xFFFFFFFF )
          v10 = -1;
        v7 = v11 > 0xFFFFFFFF ? 0xC0000095 : 0;
      }
      if ( v7 < 0 )
        goto LABEL_34;
      v12 = 8LL * DWORD1(v33);
      v13 = 8 * DWORD1(v33);
      if ( v12 > 0xFFFFFFFF )
        v13 = -1;
      v7 = v12 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( v12 > 0xFFFFFFFF )
        goto LABEL_34;
      v14 = v13 + v10;
      v15 = -1;
      if ( v13 + v10 >= v13 )
        v15 = v13 + v10;
      v7 = v14 < v13 ? 0xC0000095 : 0;
      if ( v14 < v13 )
        goto LABEL_34;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      v23 = Heap;
      if ( Heap )
      {
        v16 = DWORD2(v33) + 26;
        v25 = DWORD2(v33) + 26;
        if ( DWORD2(v33) >= 0xFFFFFFE6 )
        {
          v7 = -1073741675;
          goto LABEL_34;
        }
        v5 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
        if ( v5 )
        {
          v29 = &Heap[8 * v8];
          v17 = 0;
          if ( !(_DWORD)v8 )
            goto LABEL_31;
          while ( 1 )
          {
            v18 = ZwEnumerateKey(KeyHandle, v17, KeyBasicInformation, v5, v16, &ResultLength);
            v7 = v18;
            if ( v18 == -2147483622 )
              break;
            if ( v18 < 0 )
              goto LABEL_33;
            if ( (unsigned __int64)v5[3] + 2 > v10 )
            {
              v7 = -1073741789;
              goto LABEL_33;
            }
            v19 = (char *)v29;
            *(_QWORD *)&v23[8 * v17] = v29;
            memcpy_0(v19, v5 + 4, v5[3]);
            v20 = &v19[v5[3]];
            *(_WORD *)v20 = 0;
            v29 = v20 + 2;
            v10 += -2 - v5[3];
            ++v17;
            v16 = v25;
            if ( v17 >= (unsigned int)v8 )
              goto LABEL_31;
          }
          if ( v17 )
          {
LABEL_31:
            *v27 = v23;
            *v28 = v17;
            v7 = 0;
          }
LABEL_33:
          Heap = v23;
          goto LABEL_34;
        }
      }
      v7 = -1073741670;
LABEL_34:
      v4 = i;
    }
LABEL_35:
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    if ( v7 < 0 && Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v7 != -1073741443 )
      break;
    __debugbreak();
    a1 = (unsigned __int64)KeyHandle;
    a2 = v27;
    a3 = v28;
    if ( v4 >= 5 )
      break;
    ++v4;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001ee20  mov     r11, rsp
0x14001ee23  push    rbx
0x14001ee24  push    rsi
0x14001ee25  push    rdi
0x14001ee26  push    r12
0x14001ee28  push    r13
0x14001ee2a  push    r14
0x14001ee2c  push    r15
0x14001ee2e  sub     rsp, 0B0h
0x14001ee35  mov     rax, cs:__security_cookie
0x14001ee3c  xor     rax, rsp
0x14001ee3f  mov     [rsp+0E8h+var_40], rax
0x14001ee47  mov     [rsp+0E8h+var_90], r8
0x14001ee4c  mov     [rsp+0E8h+var_98], rdx
0x14001ee51  mov     rax, rcx
0x14001ee54  mov     [rsp+0E8h+var_80], rdx
0x14001ee59  mov     [rsp+0E8h+var_78], r8
0x14001ee5e  xorps   xmm0, xmm0
0x14001ee61  movups  [rsp+0E8h+KeyInformation], xmm0
0x14001ee66  movups  xmmword ptr [r11-60h], xmm0
0x14001ee6b  movups  xmmword ptr [r11-50h], xmm0
0x14001ee70  xor     edi, edi
0x14001ee72  mov     [rsp+0E8h+var_A8], edi
0x14001ee76  mov     esi, edi
0x14001ee78  mov     [rsp+0E8h+var_B4], edi
0x14001ee7c  mov     r12d, 80000000h
0x14001ee82  mov     r14d, 0FFFFFFFFh
0x14001ee88  mov     [rdx], rdi
0x14001ee8b  mov     [r8], edi
0x14001ee8e  mov     r13, rdi
0x14001ee91  mov     r15, rdi
0x14001ee94  and     rax, 0FFFFFFFFFFFFFFFDh
0x14001ee98  mov     [rsp+0E8h+KeyHandle], rax
0x14001ee9d  lea     rcx, [rsp+0E8h+var_A8]
0x14001eea2  mov     [rsp+0E8h+ResultLength], rcx; ResultLength
0x14001eea7  mov     r9d, 30h ; '0'; Length
0x14001eead  lea     r8, [rsp+0E8h+KeyInformation]; KeyInformation
0x14001eeb2  lea     edx, [r9-2Eh]; KeyInformationClass
0x14001eeb6  mov     rcx, rax; KeyHandle
0x14001eeb9  call    cs:__imp_ZwQueryKey
0x14001eebf  mov     ebx, eax
0x14001eec1  mov     [rsp+0E8h+var_B8], eax
0x14001eec5  add     eax, r12d
0x14001eec8  test    r12d, eax
0x14001eecb  jnz     short loc_14001EED9
0x14001eecd  cmp     ebx, 80000005h
0x14001eed3  jnz     loc_14001F0E1
0x14001eed9  mov     r12d, [rsp+0E8h+var_5C]
0x14001eee1  test    r12d, r12d
0x14001eee4  jnz     short loc_14001EEF1
0x14001eee6  mov     ebx, edi
0x14001eee8  mov     [rsp+0E8h+var_B8], ebx
0x14001eeec  jmp     loc_14001F0DB
0x14001eef1  mov     ecx, [rsp+0E8h+var_58]
0x14001eef8  lea     eax, [rcx+2]
0x14001eefb  mov     esi, r14d
0x14001eefe  cmp     eax, ecx
0x14001ef00  cmovnb  esi, eax
0x14001ef03  sbb     ebx, ebx
0x14001ef05  mov     r9d, 0C0000095h
0x14001ef0b  and     ebx, r9d
0x14001ef0e  mov     [rsp+0E8h+var_B8], ebx
0x14001ef12  cmp     eax, ecx
0x14001ef14  jb      short loc_14001EF35
0x14001ef16  mov     rcx, r12
0x14001ef19  mov     eax, esi
0x14001ef1b  imul    rcx, rax
0x14001ef1f  cmp     rcx, r14
0x14001ef22  mov     esi, ecx
0x14001ef24  jbe     short loc_14001EF29
0x14001ef26  mov     esi, r14d
0x14001ef29  cmp     r14, rcx
0x14001ef2c  sbb     ebx, ebx
0x14001ef2e  and     ebx, r9d
0x14001ef31  mov     [rsp+0E8h+var_B8], ebx
0x14001ef35  mov     r8d, edi
0x14001ef38  test    ebx, ebx
0x14001ef3a  js      loc_14001F0D7
0x14001ef40  mov     rax, r12
0x14001ef43  shl     rax, 3
0x14001ef47  cmp     rax, r14
0x14001ef4a  mov     r8d, eax
0x14001ef4d  jbe     short loc_14001EF52
0x14001ef4f  mov     r8d, r14d
0x14001ef52  cmp     r14, rax
0x14001ef55  sbb     ebx, ebx
0x14001ef57  and     ebx, r9d
0x14001ef5a  mov     [rsp+0E8h+var_B8], ebx
0x14001ef5e  test    ebx, ebx
0x14001ef60  js      loc_14001F0D7
0x14001ef66  mov     edx, r8d
0x14001ef69  lea     ecx, [r8+rsi]
0x14001ef6d  mov     eax, r14d
0x14001ef70  cmp     ecx, r8d
0x14001ef73  cmovnb  eax, ecx
0x14001ef76  mov     r8d, eax; Size
0x14001ef79  cmp     ecx, edx
0x14001ef7b  sbb     ebx, ebx
0x14001ef7d  and     ebx, r9d
0x14001ef80  mov     [rsp+0E8h+var_B8], ebx
0x14001ef84  test    ebx, ebx
0x14001ef86  js      loc_14001F0D7
0x14001ef8c  mov     rcx, gs:60h
0x14001ef95  xor     edx, edx; Flags
0x14001ef97  mov     rcx, [rcx+30h]; HeapHandle
0x14001ef9b  call    cs:__imp_RtlAllocateHeap
0x14001efa1  mov     r15, rax
0x14001efa4  mov     [rsp+0E8h+var_B0], rax
0x14001efa9  test    rax, rax
0x14001efac  jnz     short loc_14001EFBC
0x14001efae  mov     ebx, 0C000009Ah
0x14001efb3  mov     [rsp+0E8h+var_B8], ebx
0x14001efb7  jmp     loc_14001F0D7
0x14001efbc  mov     ebx, [rsp+0E8h+var_58]
0x14001efc3  add     ebx, 1Ah
0x14001efc6  mov     [rsp+0E8h+var_A4], ebx
0x14001efca  cmp     ebx, 1Ah
0x14001efcd  jb      loc_14001F0C8
0x14001efd3  mov     r8d, ebx; Size
0x14001efd6  mov     rcx, gs:60h
0x14001efdf  xor     edx, edx; Flags
0x14001efe1  mov     rcx, [rcx+30h]; HeapHandle
0x14001efe5  call    cs:__imp_RtlAllocateHeap
0x14001efeb  mov     r13, rax
0x14001efee  test    rax, rax
0x14001eff1  jz      short loc_14001EFAE
0x14001eff3  lea     rcx, [r15+r12*8]
0x14001eff7  mov     [rsp+0E8h+var_88], rcx
0x14001effc  mov     r15d, edi
0x14001efff  test    r12d, r12d
0x14001f002  jz      loc_14001F0AF
0x14001f008  lea     rax, [rsp+0E8h+var_A8]
0x14001f00d  mov     [rsp+0E8h+var_C0], rax; ResultLength
0x14001f012  mov     dword ptr [rsp+0E8h+ResultLength], ebx; Length
0x14001f016  mov     r9, r13; KeyInformation
0x14001f019  xor     r8d, r8d; KeyInformationClass
0x14001f01c  mov     edx, r15d; Index
0x14001f01f  mov     rcx, [rsp+0E8h+KeyHandle]; KeyHandle
0x14001f024  call    cs:__imp_ZwEnumerateKey
0x14001f02a  mov     ebx, eax
0x14001f02c  mov     [rsp+0E8h+var_B8], eax
0x14001f030  cmp     eax, 8000001Ah
0x14001f035  jz      short loc_14001F0AA
0x14001f037  test    eax, eax
0x14001f039  js      loc_14001F0D2
0x14001f03f  mov     ecx, [r13+0Ch]
0x14001f043  add     rcx, 2
0x14001f047  mov     eax, esi
0x14001f049  cmp     rcx, rax
0x14001f04c  ja      short loc_14001F09F
0x14001f04e  mov     eax, r15d
0x14001f051  mov     rcx, [rsp+0E8h+var_B0]
0x14001f056  mov     rbx, [rsp+0E8h+var_88]
0x14001f05b  mov     [rcx+rax*8], rbx
0x14001f05f  mov     r8d, [r13+0Ch]; Size
0x14001f063  lea     rdx, [r13+10h]; Src
0x14001f067  mov     rcx, rbx; void *
0x14001f06a  call    memcpy_0
0x14001f06f  mov     ecx, [r13+0Ch]
0x14001f073  add     rcx, rbx
0x14001f076  mov     [rcx], di
0x14001f079  add     rcx, 2
0x14001f07d  mov     [rsp+0E8h+var_88], rcx
0x14001f082  mov     eax, 0FFFFFFFEh
0x14001f087  sub     eax, [r13+0Ch]
0x14001f08b  add     esi, eax
0x14001f08d  inc     r15d
0x14001f090  cmp     r15d, r12d
0x14001f093  mov     ebx, [rsp+0E8h+var_A4]
0x14001f097  jb      loc_14001F008
0x14001f09d  jmp     short loc_14001F0AF
0x14001f09f  mov     ebx, 0C0000023h
0x14001f0a4  mov     [rsp+0E8h+var_B8], ebx
0x14001f0a8  jmp     short loc_14001F0D2
0x14001f0aa  test    r15d, r15d
0x14001f0ad  jz      short loc_14001F0D2
0x14001f0af  mov     rax, [rsp+0E8h+var_B0]
0x14001f0b4  mov     rcx, [rsp+0E8h+var_98]
0x14001f0b9  mov     [rcx], rax
0x14001f0bc  mov     rax, [rsp+0E8h+var_90]
0x14001f0c1  mov     [rax], r15d
0x14001f0c4  mov     ebx, edi
0x14001f0c6  jmp     short loc_14001F0A4
0x14001f0c8  mov     ebx, 0C0000095h
0x14001f0cd  jmp     loc_14001EFB3
0x14001f0d2  mov     r15, [rsp+0E8h+var_B0]
0x14001f0d7  mov     esi, [rsp+0E8h+var_B4]
0x14001f0db  mov     r12d, 80000000h
0x14001f0e1  test    r13, r13
0x14001f0e4  jz      short loc_14001F0FE
0x14001f0e6  mov     rcx, gs:60h
0x14001f0ef  mov     r8, r13; P
0x14001f0f2  xor     edx, edx; Flags
0x14001f0f4  mov     rcx, [rcx+30h]; HeapHandle
0x14001f0f8  call    cs:__imp_RtlFreeHeap
0x14001f0fe  test    ebx, ebx
0x14001f100  jns     short loc_14001F11F
0x14001f102  test    r15, r15
0x14001f105  jz      short loc_14001F11F
0x14001f107  mov     rcx, gs:60h
0x14001f110  mov     r8, r15; P
0x14001f113  xor     edx, edx; Flags
0x14001f115  mov     rcx, [rcx+30h]; HeapHandle
0x14001f119  call    cs:__imp_RtlFreeHeap
0x14001f11f  cmp     ebx, 0C000017Dh
0x14001f125  jnz     short loc_14001F179
0x14001f127  int     3; Trap to Debugger
0x14001f128  mov     rax, [rsp+0E8h+KeyHandle]
0x14001f12d  mov     rdx, [rsp+0E8h+var_98]
0x14001f132  mov     r8, [rsp+0E8h+var_90]
0x14001f137  jmp     short loc_14001F169
0x14001f139  mov     esi, 5
0x14001f13e  xor     edi, edi
0x14001f140  mov     r12d, 80000000h
0x14001f146  mov     r14d, 0FFFFFFFFh
0x14001f14c  mov     ebx, [rsp+0E8h+var_B8]
0x14001f150  mov     rax, [rsp+0E8h+KeyHandle]
0x14001f155  mov     rdx, [rsp+0E8h+var_80]
0x14001f15a  mov     [rsp+0E8h+var_98], rdx
0x14001f15f  mov     r8, [rsp+0E8h+var_78]
0x14001f164  mov     [rsp+0E8h+var_90], r8
0x14001f169  cmp     esi, 5
0x14001f16c  jnb     short loc_14001F179
0x14001f16e  inc     esi
0x14001f170  mov     [rsp+0E8h+var_B4], esi
0x14001f174  jmp     loc_14001EE88
0x14001f179  mov     eax, ebx
0x14001f17b  mov     rcx, [rsp+0E8h+var_40]
0x14001f183  xor     rcx, rsp; StackCookie
0x14001f186  call    __security_check_cookie
0x14001f18b  add     rsp, 0B0h
0x14001f192  pop     r15
0x14001f194  pop     r14
0x14001f196  pop     r13
0x14001f198  pop     r12
0x14001f19a  pop     rdi
0x14001f19b  pop     rsi
0x14001f19c  pop     rbx
0x14001f19d  retn
```
