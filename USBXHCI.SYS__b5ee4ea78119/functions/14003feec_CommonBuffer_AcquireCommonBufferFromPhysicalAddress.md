# CommonBuffer_AcquireCommonBufferFromPhysicalAddress

- ea: `0x14003feec`
- end: `0x14004015b`
- name: `CommonBuffer_AcquireCommonBufferFromPhysicalAddress`
- size: `623`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003cfa8`
- `0x140040704`

## callees

- `0x14001ad0c`
- `0x14003feec`
- `0x1400403f0`
- `0x1400404ec`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140040007`
- `ntoskrnl!ExAllocatePool2` at `0x140040007`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ff7c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ff7c`
- `ntoskrnl!MmAllocateMdlForIoSpace` at `0x14003ff43`
- `ntoskrnl!MmAllocateMdlForIoSpace` at `0x14003ff43`
- `ntoskrnl!IoFreeMdl` at `0x140040124`
- `ntoskrnl!IoFreeMdl` at `0x140040124`
- `ntoskrnl!MmUnmapLockedPages` at `0x140040114`
- `ntoskrnl!MmUnmapLockedPages` at `0x140040114`

## pseudocode

```c
_QWORD *__fastcall CommonBuffer_AcquireCommonBufferFromPhysicalAddress(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5)
{
  char v5; // bl
  PVOID v7; // rsi
  _QWORD *v10; // rdi
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  struct _MDL *v14; // rcx
  int v15; // r15d
  _UNKNOWN **v16; // rdx
  int v17; // r9d
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // r9d
  _QWORD *Pool2; // rax
  PMDL MemoryDescriptorList; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-20h] BYREF

  v5 = a2;
  v7 = 0;
  v25[1] = a3;
  v24 = 0;
  MemoryDescriptorList = 0;
  v10 = 0;
  v25[0] = a2;
  v11 = MmAllocateMdlForIoSpace(v25, (unsigned __int64)a3 >> 12, &MemoryDescriptorList);
  v14 = MemoryDescriptorList;
  v15 = v11;
  if ( v11 < 0 || !MemoryDescriptorList )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_17:
      if ( v15 < 0 && v14 )
      {
        if ( v7 )
        {
          MmUnmapLockedPages(v7, v14);
          v14 = MemoryDescriptorList;
        }
        IoFreeMdl(v14);
      }
      return v10;
    }
    WPP_RECORDER_SF_iid(*(_QWORD *)(*(_QWORD *)a1 + 72LL), (unsigned int)&WPP_RECORDER_INITIALIZED, v12, v13);
LABEL_16:
    v14 = MemoryDescriptorList;
    goto LABEL_17;
  }
  v7 = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v7 )
  {
    v16 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = 18;
      LOBYTE(v16) = 2;
LABEL_11:
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)a1 + 72LL),
        (_DWORD)v16,
        8,
        v17,
        (__int64)WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids,
        a3);
      return v10;
    }
    return v10;
  }
  v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 96LL) + 24LL);
  v15 = (*(__int64 (__fastcall **)(__int64, PMDL, _QWORD, _QWORD))(*(_QWORD *)(v18 + 8) + 312LL))(
          v18,
          MemoryDescriptorList,
          0,
          0);
  if ( v15 < 0 || !v24 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_iiid(
        *(_QWORD *)(*(_QWORD *)a1 + 72LL),
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        v19,
        v20,
        (unsigned int)&v24,
        v15,
        v5,
        v24,
        a3);
    goto LABEL_16;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 104, 1229146200);
  v10 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x68u);
    v10[2] = v7;
    v10[3] = v24;
    *((_DWORD *)v10 + 16) = a5;
    *((_DWORD *)v10 + 10) = a3;
    *((_DWORD *)v10 + 11) = a3;
    v10[9] = a4;
    v10[11] = MemoryDescriptorList;
    *((_DWORD *)v10 + 20) = 4;
    v16 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = 20;
      LOBYTE(v16) = 4;
      goto LABEL_11;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14003feec  mov     [rsp-38h+arg_18], rbx
0x14003fef1  push    rbp
0x14003fef2  push    rsi
0x14003fef3  push    rdi
0x14003fef4  push    r12
0x14003fef6  push    r13
0x14003fef8  push    r14
0x14003fefa  push    r15
0x14003fefc  mov     rbp, rsp
0x14003feff  sub     rsp, 80h
0x14003ff06  mov     rax, cs:__security_cookie
0x14003ff0d  xor     rax, rsp
0x14003ff10  mov     [rbp+var_10], rax
0x14003ff14  mov     rbx, rdx
0x14003ff17  mov     r14d, r8d
0x14003ff1a  mov     edx, r8d
0x14003ff1d  xor     esi, esi
0x14003ff1f  mov     [rbp+var_18], rdx
0x14003ff23  lea     r8, [rbp+MemoryDescriptorList]
0x14003ff27  mov     r12, rcx
0x14003ff2a  shr     rdx, 0Ch
0x14003ff2e  lea     rcx, [rbp+var_20]
0x14003ff32  mov     [rbp+var_28], rsi
0x14003ff36  mov     r13, r9
0x14003ff39  mov     [rbp+MemoryDescriptorList], rsi
0x14003ff3d  mov     edi, esi
0x14003ff3f  mov     [rbp+var_20], rbx
0x14003ff43  call    cs:__imp_MmAllocateMdlForIoSpace
0x14003ff4a  nop     dword ptr [rax+rax+00h]
0x14003ff4f  mov     rcx, [rbp+MemoryDescriptorList]; MemoryDescriptorList
0x14003ff53  movsxd  r15, eax
0x14003ff56  test    eax, eax
0x14003ff58  js      loc_1400400CF
0x14003ff5e  test    rcx, rcx
0x14003ff61  jz      loc_1400400CF
0x14003ff67  mov     [rsp+80h+Priority], 40000010h; Priority
0x14003ff6f  lea     r8d, [rsi+1]; CacheType
0x14003ff73  xor     r9d, r9d; RequestedAddress
0x14003ff76  mov     [rsp+80h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14003ff7a  xor     edx, edx; AccessMode
0x14003ff7c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003ff83  nop     dword ptr [rax+rax+00h]
0x14003ff88  mov     rsi, rax
0x14003ff8b  test    rax, rax
0x14003ff8e  jnz     short loc_14003FFAF
0x14003ff90  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ff97  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003ff9e  jz      loc_140040130
0x14003ffa4  lea     r9d, [rdi+12h]
0x14003ffa8  mov     dl, 2
0x14003ffaa  jmp     loc_140040073
0x14003ffaf  mov     rax, [r12]
0x14003ffb3  lea     rdx, [rbp+var_28]
0x14003ffb7  mov     qword ptr [rsp+80h+BugCheckOnFailure], rdx
0x14003ffbc  xor     r9d, r9d
0x14003ffbf  mov     rdx, [rbp+MemoryDescriptorList]
0x14003ffc3  xor     r8d, r8d
0x14003ffc6  mov     rcx, [rax+60h]
0x14003ffca  mov     rcx, [rcx+18h]
0x14003ffce  mov     rax, [rcx+8]
0x14003ffd2  mov     rax, [rax+138h]
0x14003ffd9  call    _guard_dispatch_icall
0x14003ffde  movsxd  r15, eax
0x14003ffe1  mov     rax, [rbp+var_28]
0x14003ffe5  test    r15d, r15d
0x14003ffe8  js      loc_14004009C
0x14003ffee  test    rax, rax
0x14003fff1  jz      loc_14004009C
0x14003fff7  mov     ebx, 68h ; 'h'
0x14003fffc  mov     r8d, 49434858h
0x140040002  mov     edx, ebx
0x140040004  lea     ecx, [rbx-28h]
0x140040007  call    cs:__imp_ExAllocatePool2
0x14004000e  nop     dword ptr [rax+rax+00h]
0x140040013  mov     rdi, rax
0x140040016  test    rax, rax
0x140040019  jz      loc_140040130
0x14004001f  mov     r8d, ebx; Size
0x140040022  xor     edx, edx; Val
0x140040024  mov     rcx, rax; void *
0x140040027  call    memset
0x14004002c  mov     [rdi+10h], rsi
0x140040030  mov     rcx, [rbp+var_28]
0x140040034  mov     [rdi+18h], rcx
0x140040038  mov     ecx, [rbp+arg_20]
0x14004003b  mov     [rdi+40h], ecx
0x14004003e  mov     [rdi+28h], r14d
0x140040042  mov     [rdi+2Ch], r14d
0x140040046  mov     [rdi+48h], r13
0x14004004a  mov     rax, [rbp+MemoryDescriptorList]
0x14004004e  mov     [rdi+58h], rax
0x140040052  mov     dword ptr [rdi+50h], 4
0x140040059  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040060  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140040067  jz      loc_140040130
0x14004006d  lea     r9d, [rbx-54h]
0x140040071  mov     dl, 4
0x140040073  mov     rcx, [r12]
0x140040077  lea     rax, WPP_6a5376b16cbf3dbdeb6b8133660a6549_Traceguids
0x14004007e  mov     [rsp+80h+Priority], r14d
0x140040083  mov     r8d, 8
0x140040089  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x14004008e  mov     rcx, [rcx+48h]
0x140040092  call    WPP_RECORDER_SF_d
0x140040097  jmp     loc_140040130
0x14004009c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400400a3  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400400aa  jz      short loc_1400400FB
0x1400400ac  mov     rcx, [r12]
0x1400400b0  mov     [rsp+80h+var_40], r14d
0x1400400b5  mov     [rsp+80h+var_48], rax
0x1400400ba  mov     [rsp+80h+var_50], rbx
0x1400400bf  mov     rcx, [rcx+48h]
0x1400400c3  mov     qword ptr [rsp+80h+Priority], r15
0x1400400c8  call    WPP_RECORDER_SF_iiid
0x1400400cd  jmp     short loc_1400400FB
0x1400400cf  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400400d6  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400400dd  jz      short loc_1400400FF
0x1400400df  mov     rcx, [r12]
0x1400400e3  mov     dword ptr [rsp+80h+var_48], r14d
0x1400400e8  mov     [rsp+80h+var_50], rbx
0x1400400ed  mov     qword ptr [rsp+80h+Priority], r15
0x1400400f2  mov     rcx, [rcx+48h]
0x1400400f6  call    WPP_RECORDER_SF_iid
0x1400400fb  mov     rcx, [rbp+MemoryDescriptorList]
0x1400400ff  test    r15d, r15d
0x140040102  jns     short loc_140040130
0x140040104  test    rcx, rcx
0x140040107  jz      short loc_140040130
0x140040109  test    rsi, rsi
0x14004010c  jz      short loc_140040124
0x14004010e  mov     rdx, rcx; MemoryDescriptorList
0x140040111  mov     rcx, rsi; BaseAddress
0x140040114  call    cs:__imp_MmUnmapLockedPages
0x14004011b  nop     dword ptr [rax+rax+00h]
0x140040120  mov     rcx, [rbp+MemoryDescriptorList]; Mdl
0x140040124  call    cs:__imp_IoFreeMdl
0x14004012b  nop     dword ptr [rax+rax+00h]
0x140040130  mov     rax, rdi
0x140040133  mov     rcx, [rbp+var_10]
0x140040137  xor     rcx, rsp; StackCookie
0x14004013a  call    __security_check_cookie
0x14004013f  mov     rbx, [rsp+80h+arg_18]
0x140040147  add     rsp, 80h
0x14004014e  pop     r15
0x140040150  pop     r14
0x140040152  pop     r13
0x140040154  pop     r12
0x140040156  pop     rdi
0x140040157  pop     rsi
0x140040158  pop     rbp
0x140040159  retn
```
