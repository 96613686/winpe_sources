# BipEnumerateEvents

- ea: `0x180009e10`
- end: `0x18000a1af`
- name: `BipEnumerateEvents`
- size: `927`
- prototype: `__int64 __usercall@<rax>(void *Source2@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009a44`
- `0x18000a1c0`
- `0x180086d18`

## callees

- `0x180008560`
- `0x180009e10`
- `0x180049844`
- `0x18004df58`
- `0x180078e24`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18000a12f`
- `ntdll!RtlReAllocateHeap` at `0x18000a12f`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180009ef4`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180009ef4`
- `ntdll!RtlInitEnumerationHashTable` at `0x180009e68`
- `ntdll!RtlInitEnumerationHashTable` at `0x180009e68`
- `ntdll!RtlCompareUnicodeStrings` at `0x180009f76`
- `ntdll!RtlCompareUnicodeStrings` at `0x180009f76`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009e57`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009e57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009eb4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a16e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009eb4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a16e`
- `ntdll!RtlFreeHeap` at `0x18000a15b`
- `ntdll!RtlFreeHeap` at `0x18000a15b`
- `ntdll!RtlAllocateHeap` at `0x180009e88`
- `ntdll!RtlAllocateHeap` at `0x180009e88`
- `ntdll!RtlEqualSid` at `0x180009f3d`
- `ntdll!RtlEqualSid` at `0x18000a050`
- `ntdll!RtlEqualSid` at `0x180009f3d`
- `ntdll!RtlEqualSid` at `0x18000a050`
- `ntdll!RtlEndEnumerationHashTable` at `0x180009ea6`
- `ntdll!RtlEndEnumerationHashTable` at `0x180009ea6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180009f12`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180009f12`

## pseudocode

```c
__int64 __fastcall BipEnumerateEvents(void *Source2, void *a2, __int64 a3, int a4, unsigned int *a5, _QWORD *a6)
{
  const void *v6; // r13
  unsigned int v7; // r12d
  char *Heap; // rsi
  int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // r15
  PVOID v13; // rcx
  void *v14; // rdx
  unsigned int v15; // r13d
  __int64 v16; // rax
  void *v17; // rdx
  char *v18; // rax
  int v19; // [rsp+20h] [rbp-58h]
  unsigned int v20; // [rsp+30h] [rbp-48h]
  _OWORD v21[4]; // [rsp+38h] [rbp-40h] BYREF

  v6 = Source2;
  *((_QWORD *)&v21[0] + 1) = 0;
  memset(&v21[1], 0, 32);
  RtlAcquireSRWLockExclusive(&qword_1800C4370);
  if ( !(unsigned __int8)RtlInitEnumerationHashTable(qword_1800C4368, (char *)v21 + 8) )
  {
    RtlReleaseSRWLockExclusive(&qword_1800C4370);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_25bd4f2bfb31341b209eae5dd6f40fb0_Traceguids, 3221225473LL);
    return (unsigned int)-1073741823;
  }
  v7 = 0;
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, 0x400u);
  if ( Heap )
  {
    v20 = 64;
    v9 = 0;
    while ( 1 )
    {
      do
      {
        v11 = RtlEnumerateEntryHashTable(qword_1800C4368, (char *)v21 + 8);
        v12 = v11;
        if ( !v11 )
          goto LABEL_4;
      }
      while ( RtlCompareMemory((const void *)(v11 + 128), v6, 0x10u) != 16 );
      if ( !a2 || (v14 = *(void **)(v12 + 168)) != 0 && RtlEqualSid(a2, v14) )
      {
        v9 = 0;
        if ( a3
          && (v12 == -192 || (LOBYTE(v19) = 1, (unsigned int)RtlCompareUnicodeStrings(a3 + 256, 65, v12 + 448, 65, v19)))
          && (v9 = -1073741823, v13 = WPP_GLOBAL_Control, (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0)
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
        }
        else if ( v9 >= 0 )
        {
          goto LABEL_17;
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
        v9 = -1073741823;
      }
      if ( !*(_QWORD *)(v12 + 184) )
        goto LABEL_23;
      if ( (unsigned __int8)BipIsDeviceHoloLens(v13) )
      {
        if ( !a2 || (v17 = *(void **)(v12 + 184)) != 0 && RtlEqualSid(a2, v17) )
        {
          v9 = 0;
          if ( a3 && (v12 == -192 || !(unsigned __int8)BipPackageIdIsEquivalent(a3, v12 + 192)) )
          {
            v9 = -1073741823;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
          }
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
          v9 = -1073741823;
        }
      }
      if ( v9 < 0 )
      {
LABEL_23:
        v9 = 0;
        goto LABEL_24;
      }
LABEL_17:
      if ( a4 != -1 )
      {
        v6 = Source2;
        if ( a4 != *(_DWORD *)(v12 + 144) )
          continue;
      }
      v15 = v20;
      if ( v7 >= v20 )
      {
        v20 *= 2;
        v18 = (char *)RtlReAllocateHeap(BipHeap, 0, Heap, 32LL * v15);
        if ( !v18 )
          break;
        Heap = v18;
      }
      v16 = 2LL * v7++;
      *(_OWORD *)&Heap[8 * v16] = *(_OWORD *)(v12 + 32);
LABEL_24:
      v6 = Source2;
    }
  }
  v9 = -1073741801;
LABEL_4:
  RtlEndEnumerationHashTable(qword_1800C4368, (char *)v21 + 8);
  RtlReleaseSRWLockExclusive(&qword_1800C4370);
  if ( v9 < 0 )
  {
    if ( Heap )
      RtlFreeHeap(BipHeap, 0, Heap);
  }
  else
  {
    *a5 = v7;
    *a6 = Heap;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009e10  mov     rax, rsp
0x180009e13  mov     [rax+20h], r9d
0x180009e17  mov     [rax+18h], r8
0x180009e1b  mov     [rax+10h], rdx
0x180009e1f  mov     [rax+8], rcx
0x180009e23  push    rbp
0x180009e24  push    rbx
0x180009e25  push    rsi
0x180009e26  push    r12
0x180009e28  push    r13
0x180009e2a  push    r15
0x180009e2c  mov     rbp, rsp
0x180009e2f  sub     rsp, 78h
0x180009e33  xorps   xmm0, xmm0
0x180009e36  lea     rax, qword_1800C4368
0x180009e3d  mov     r13, rcx
0x180009e40  lea     rcx, qword_1800C4370
0x180009e47  movups  [rbp+var_40], xmm0
0x180009e4b  mov     qword ptr [rbp+var_40], rax
0x180009e4f  movups  [rbp+var_30], xmm0
0x180009e53  movups  [rbp+var_20], xmm0
0x180009e57  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009e5d  mov     rcx, qword ptr [rbp+var_40]
0x180009e61  lea     rdx, [rbp+var_40+8]
0x180009e65  mov     rcx, [rcx]
0x180009e68  call    cs:__imp_RtlInitEnumerationHashTable
0x180009e6e  test    al, al
0x180009e70  jz      loc_18000A166
0x180009e76  mov     rcx, cs:BipHeap; HeapHandle
0x180009e7d  xor     edx, edx; Flags
0x180009e7f  mov     r8d, 400h; Size
0x180009e85  xor     r12d, r12d
0x180009e88  call    cs:__imp_RtlAllocateHeap
0x180009e8e  mov     rsi, rax
0x180009e91  test    rax, rax
0x180009e94  jnz     short loc_180009EE0
0x180009e96  mov     ebx, 0C0000017h
0x180009e9b  mov     rcx, qword ptr [rbp+var_40]
0x180009e9f  lea     rdx, [rbp+var_40+8]
0x180009ea3  mov     rcx, [rcx]
0x180009ea6  call    cs:__imp_RtlEndEnumerationHashTable
0x180009eac  mov     rcx, qword ptr [rbp+var_40]
0x180009eb0  add     rcx, 8
0x180009eb4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009eba  test    ebx, ebx
0x180009ebc  js      loc_18000A146
0x180009ec2  mov     rax, [rbp+arg_20]
0x180009ec6  mov     [rax], r12d
0x180009ec9  mov     rax, [rbp+arg_28]
0x180009ecd  mov     [rax], rsi
0x180009ed0  mov     eax, ebx
0x180009ed2  add     rsp, 78h
0x180009ed6  pop     r15
0x180009ed8  pop     r13
0x180009eda  pop     r12
0x180009edc  pop     rsi
0x180009edd  pop     rbx
0x180009ede  pop     rbp
0x180009edf  retn
0x180009ee0  mov     [rbp+var_48], 40h ; '@'
0x180009ee7  xor     ebx, ebx
0x180009ee9  mov     rcx, qword ptr [rbp+var_40]
0x180009eed  lea     rdx, [rbp+var_40+8]
0x180009ef1  mov     rcx, [rcx]
0x180009ef4  call    cs:__imp_RtlEnumerateEntryHashTable
0x180009efa  mov     r15, rax
0x180009efd  test    rax, rax
0x180009f00  jz      short loc_180009E9B
0x180009f02  lea     rcx, [rax+80h]; Source1
0x180009f09  mov     r8d, 10h; Length
0x180009f0f  mov     rdx, r13; Source2
0x180009f12  call    cs:__imp_RtlCompareMemory
0x180009f18  cmp     rax, 10h
0x180009f1c  jnz     short loc_180009EE9
0x180009f1e  mov     rax, [rbp+Sid1]
0x180009f22  lea     r13, [r15+0C0h]
0x180009f29  test    rax, rax
0x180009f2c  jz      short loc_180009F47
0x180009f2e  mov     rdx, [r15+0A8h]; Sid2
0x180009f35  test    rdx, rdx
0x180009f38  jz      short loc_180009FB8
0x180009f3a  mov     rcx, rax; Sid1
0x180009f3d  call    cs:__imp_RtlEqualSid
0x180009f43  test    al, al
0x180009f45  jz      short loc_180009FB8
0x180009f47  mov     rax, [rbp+arg_10]
0x180009f4b  xor     ebx, ebx
0x180009f4d  test    rax, rax
0x180009f50  jz      short loc_180009F84
0x180009f52  test    r13, r13
0x180009f55  jz      loc_18000A0B3
0x180009f5b  lea     rcx, [rax+100h]
0x180009f62  mov     byte ptr [rsp+78h+var_58], 1
0x180009f67  lea     eax, [rbx+41h]
0x180009f6a  mov     r9d, eax
0x180009f6d  lea     r8, [r13+100h]
0x180009f74  mov     edx, eax
0x180009f76  call    cs:__imp_RtlCompareUnicodeStrings
0x180009f7c  test    eax, eax
0x180009f7e  jnz     loc_18000A0B3
0x180009f84  test    ebx, ebx
0x180009f86  js      short loc_180009FCA
0x180009f88  mov     r13d, [rbp+arg_18]
0x180009f8c  cmp     r13d, 0FFFFFFFFh
0x180009f90  jnz     loc_18000A0FF
0x180009f96  mov     r13d, [rbp+var_48]
0x180009f9a  cmp     r12d, r13d
0x180009f9d  jnb     loc_18000A115
0x180009fa3  movups  xmm0, xmmword ptr [r15+20h]
0x180009fa8  mov     eax, r12d
0x180009fab  add     rax, rax
0x180009fae  inc     r12d
0x180009fb1  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x180009fb6  jmp     short loc_180009FDA
0x180009fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fbf  test    byte ptr [rcx+1Ch], 40h
0x180009fc3  jnz     short loc_180009FE3
0x180009fc5  mov     ebx, 0C0000001h
0x180009fca  cmp     qword ptr [r15+0B8h], 0
0x180009fd2  jnz     loc_18000A0ED
0x180009fd8  xor     ebx, ebx
0x180009fda  mov     r13, [rbp+arg_0]
0x180009fde  jmp     loc_180009EE9
0x180009fe3  cmp     byte ptr [rcx+19h], 2
0x180009fe7  jb      short loc_180009FC5
0x180009fe9  mov     rcx, [rcx+10h]
0x180009fed  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x180009ff4  mov     edx, 0Ah
0x180009ff9  call    WPP_SF_
0x180009ffe  jmp     short loc_180009FC5
0x18000a000  mov     ebx, 0C0000001h
0x18000a005  test    ebx, ebx
0x18000a007  js      short loc_180009FD8
0x18000a009  jmp     loc_180009F88
0x18000a00e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a015  test    byte ptr [rcx+1Ch], 40h
0x18000a019  jz      short loc_18000A000
0x18000a01b  cmp     byte ptr [rcx+19h], 2
0x18000a01f  jb      short loc_18000A000
0x18000a021  mov     rcx, [rcx+10h]
0x18000a025  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18000a02c  mov     edx, 0Ah
0x18000a031  call    WPP_SF_
0x18000a036  jmp     short loc_18000A000
0x18000a038  mov     rax, [rbp+Sid1]
0x18000a03c  test    rax, rax
0x18000a03f  jz      short loc_18000A05A
0x18000a041  mov     rdx, [r15+0B8h]; Sid2
0x18000a048  test    rdx, rdx
0x18000a04b  jz      short loc_18000A00E
0x18000a04d  mov     rcx, rax; Sid1
0x18000a050  call    cs:__imp_RtlEqualSid
0x18000a056  test    al, al
0x18000a058  jz      short loc_18000A00E
0x18000a05a  mov     rax, [rbp+arg_10]
0x18000a05e  xor     ebx, ebx
0x18000a060  test    rax, rax
0x18000a063  jz      short loc_18000A005
0x18000a065  test    r13, r13
0x18000a068  jz      short loc_18000A079
0x18000a06a  mov     rdx, r13
0x18000a06d  mov     rcx, rax
0x18000a070  call    BipPackageIdIsEquivalent
0x18000a075  test    al, al
0x18000a077  jnz     short loc_18000A005
0x18000a079  mov     ebx, 0C0000001h
0x18000a07e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a085  test    byte ptr [rcx+1Ch], 40h
0x18000a089  jz      loc_18000A005
0x18000a08f  cmp     byte ptr [rcx+19h], 2
0x18000a093  jb      loc_18000A005
0x18000a099  mov     rcx, [rcx+10h]
0x18000a09d  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18000a0a4  mov     edx, 0Bh
0x18000a0a9  call    WPP_SF_
0x18000a0ae  jmp     loc_18000A005
0x18000a0b3  mov     ebx, 0C0000001h
0x18000a0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0bf  test    byte ptr [rcx+1Ch], 40h
0x18000a0c3  jz      loc_180009F84
0x18000a0c9  cmp     byte ptr [rcx+19h], 2
0x18000a0cd  jb      loc_180009F84
0x18000a0d3  mov     rcx, [rcx+10h]
0x18000a0d7  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18000a0de  mov     edx, 0Bh
0x18000a0e3  call    WPP_SF_
0x18000a0e8  jmp     loc_180009FCA
0x18000a0ed  call    BipIsDeviceHoloLens
0x18000a0f2  test    al, al
0x18000a0f4  jz      loc_18000A005
0x18000a0fa  jmp     loc_18000A038
0x18000a0ff  cmp     r13d, [r15+90h]
0x18000a106  mov     r13, [rbp+arg_0]
0x18000a10a  jnz     loc_180009EE9
0x18000a110  jmp     loc_180009F96
0x18000a115  mov     rcx, cs:BipHeap; Heap
0x18000a11c  add     r13d, r13d
0x18000a11f  mov     r9d, r13d
0x18000a122  mov     r8, rsi; Ptr
0x18000a125  shl     r9, 4; Size
0x18000a129  xor     edx, edx; Flags
0x18000a12b  mov     [rbp+var_48], r13d
0x18000a12f  call    cs:__imp_RtlReAllocateHeap
0x18000a135  test    rax, rax
0x18000a138  jz      loc_180009E96
0x18000a13e  mov     rsi, rax
0x18000a141  jmp     loc_180009FA3
0x18000a146  test    rsi, rsi
0x18000a149  jz      loc_180009ED0
0x18000a14f  mov     rcx, cs:BipHeap; HeapHandle
0x18000a156  mov     r8, rsi; P
0x18000a159  xor     edx, edx; Flags
0x18000a15b  call    cs:__imp_RtlFreeHeap
0x18000a161  jmp     loc_180009ED0
0x18000a166  mov     rcx, qword ptr [rbp+var_40]
0x18000a16a  add     rcx, 8
0x18000a16e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a17b  test    dword ptr [rcx+1Ch], 4000h
0x18000a182  jz      short loc_18000A1A5
0x18000a184  cmp     byte ptr [rcx+19h], 2
0x18000a188  jb      short loc_18000A1A5
0x18000a18a  mov     rcx, [rcx+10h]
0x18000a18e  lea     r8, WPP_25bd4f2bfb31341b209eae5dd6f40fb0_Traceguids
0x18000a195  mov     edx, 0Ah
0x18000a19a  mov     r9d, 0C0000001h
0x18000a1a0  call    WPP_SF_d
0x18000a1a5  mov     ebx, 0C0000001h
0x18000a1aa  jmp     loc_180009ED0
```
