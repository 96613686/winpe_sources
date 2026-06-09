# sub_14000DEDC

- ea: `0x14000dedc`
- end: `0x14000e19b`
- name: `sub_14000DEDC`
- size: `703`
- prototype: `char __fastcall(PNET_BUFFER_LIST SrcNetBufferList, __int64, void *, __int64, char, void (__fastcall *)(_QWORD, PVOID, _QWORD, __int64, __int64), __int64, __int64, NDIS_HANDLE *, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ab08`
- `0x14000afe8`
- `0x14000c104`
- `0x14000c3fc`
- `0x14000c8a4`
- `0x14000cb90`

## callees

- `0x140001010`
- `0x140008abc`
- `0x14000daa8`
- `0x14000dedc`
- `0x140015890`
- `0x1400158d0`
- `0x140015c80`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14000dfb8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14000dfb8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000e126`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000e15c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000e126`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14000e15c`
- `NDIS!NdisReleaseReadWriteLock` at `0x14000dfe3`
- `NDIS!NdisReleaseReadWriteLock` at `0x14000dfe3`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000e09e`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000e09e`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000e08a`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000e08a`
- `NDIS!NdisGetDataBuffer` at `0x14000e0c2`
- `NDIS!NdisGetDataBuffer` at `0x14000e0c2`
- `NDIS!NdisAcquireReadWriteLock` at `0x14000df66`
- `NDIS!NdisAcquireReadWriteLock` at `0x14000df66`

## string_xrefs

- `0x14000e142`: `Could not allocate NBL in BrdgCompSendToMultipleAdapters`

## pseudocode

```c
char __fastcall sub_14000DEDC(
        PNET_BUFFER_LIST SrcNetBufferList,
        __int64 a2,
        void *a3,
        __int64 a4,
        char a5,
        void (__fastcall *a6)(_QWORD, PVOID, _QWORD, __int64, __int64),
        __int64 a7,
        __int64 a8,
        NDIS_HANDLE *a9,
        int a10)
{
  NDIS_HANDLE *v11; // r15
  __int64 v14; // rsi
  unsigned __int64 i; // rbx
  PNET_BUFFER_LIST v16; // rdi
  PVOID DataBuffer; // rax
  PVOID v18; // r15
  struct _LOCK_STATE LockState; // [rsp+30h] [rbp-D0h] BYREF
  PNET_BUFFER_LIST DestNetBufferList; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  _QWORD v25[62]; // [rsp+60h] [rbp-A0h] BYREF

  v11 = a9;
  v23 = a7;
  v22 = a8;
  v24 = (__int64)a9;
  v14 = 0;
  sub_140015C80(v25, 0, 496);
  LockState = 0;
  NdisAcquireReadWriteLock(&Lock, 0, &LockState);
  for ( i = (unsigned __int64)WorkItemContext; i; i = *(_QWORD *)i )
  {
    if ( (void *)i != a3
      && *(_DWORD *)(i + 1140) == 1
      && *(_DWORD *)(i + 1080) == 4
      && !*(_BYTE *)(i + 36)
      && (a5 || *(_BYTE *)(i + 1136))
      && (unsigned int)v14 < 0x3E
      && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(i + 24), 1u) )
    {
      v25[v14] = i;
      v14 = (unsigned int)(v14 + 1);
    }
  }
  NdisReleaseReadWriteLock(&Lock, &LockState);
  while ( (unsigned int)i < (unsigned int)v14 )
  {
    DestNetBufferList = 0;
    if ( (unsigned int)sub_140008ABC(v11, a2, (__int64 *)&DestNetBufferList, 1) )
    {
      if ( (byte_14001E7B4 & 1) != 0 )
        sub_140001010("Could not allocate NBL in BrdgCompSendToMultipleAdapters");
      do
      {
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v25[i] + 24LL), 1u);
        i = (unsigned int)(i + 1);
      }
      while ( (unsigned int)i < (unsigned int)v14 );
      return 0;
    }
    v16 = DestNetBufferList;
    if ( DestNetBufferList )
    {
      if ( a10 )
      {
        if ( a10 == 1 )
        {
          NdisCopySendNetBufferListInfo(DestNetBufferList, SrcNetBufferList);
        }
        else if ( a10 == 2 )
        {
          DestNetBufferList->NetBufferListInfo[4] = SrcNetBufferList->NetBufferListInfo[4];
          v16->NetBufferListInfo[8] = SrcNetBufferList->NetBufferListInfo[8];
          v16->NetBufferListInfo[9] = SrcNetBufferList->NetBufferListInfo[9];
          v16->NetBufferListInfo[14] = SrcNetBufferList->NetBufferListInfo[14];
          SrcNetBufferList->Context->ContextData[SrcNetBufferList->Context->Offset + 24] |= 0x10u;
        }
      }
      else
      {
        NdisCopyReceiveNetBufferListInfo(DestNetBufferList, SrcNetBufferList);
      }
      DataBuffer = NdisGetDataBuffer(v16->FirstNetBuffer, *(_DWORD *)(v16->Link.Region + 24), 0, 1u, 0);
      v18 = DataBuffer;
      if ( a6 )
        a6(*(unsigned int *)(v16->Link.Region + 24), DataBuffer, v25[i], v23, v22);
      sub_14000DAA8(v16, *(unsigned int *)(v16->Link.Region + 24), v18, v25[i]);
      v11 = (NDIS_HANDLE *)v24;
    }
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v25[i] + 24LL), 1u);
    i = (unsigned int)(i + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14000dedc  mov     [rsp-8+arg_10], rbx
0x14000dee1  push    rbp
0x14000dee2  push    rsi
0x14000dee3  push    rdi
0x14000dee4  push    r12
0x14000dee6  push    r13
0x14000dee8  push    r14
0x14000deea  push    r15
0x14000deec  lea     rbp, [rsp-160h]
0x14000def4  sub     rsp, 260h
0x14000defb  mov     rax, cs:__security_cookie
0x14000df02  xor     rax, rsp
0x14000df05  mov     [rbp+190h+var_40], rax
0x14000df0c  mov     rax, [rbp+190h+arg_30]
0x14000df13  mov     rdi, r8
0x14000df16  mov     r15, [rbp+190h+arg_40]
0x14000df1d  mov     r13, rdx
0x14000df20  mov     r12, [rbp+190h+arg_28]
0x14000df27  mov     r14, rcx
0x14000df2a  mov     [rsp+290h+var_248], rax
0x14000df2f  lea     rcx, [rsp+290h+var_230]
0x14000df34  mov     rax, [rbp+190h+arg_38]
0x14000df3b  xor     edx, edx
0x14000df3d  mov     r8d, 1F0h
0x14000df43  mov     [rsp+290h+var_250], rax
0x14000df48  mov     [rsp+290h+var_240], r15
0x14000df4d  xor     esi, esi
0x14000df4f  call    sub_140015C80
0x14000df54  lea     r8, [rsp+290h+LockState]; LockState
0x14000df59  mov     dword ptr [rsp+290h+LockState.LockState], esi
0x14000df5d  xor     edx, edx; fWrite
0x14000df5f  lea     rcx, Lock; Lock
0x14000df66  call    cs:NdisAcquireReadWriteLock
0x14000df6d  nop     dword ptr [rax+rax+00h]
0x14000df72  mov     rbx, cs:WorkItemContext
0x14000df79  jmp     short loc_14000DFD2
0x14000df7b  cmp     rbx, rdi
0x14000df7e  jz      short loc_14000DFCF
0x14000df80  cmp     dword ptr [rbx+474h], 1
0x14000df87  jnz     short loc_14000DFCF
0x14000df89  cmp     dword ptr [rbx+438h], 4
0x14000df90  jnz     short loc_14000DFCF
0x14000df92  cmp     byte ptr [rbx+24h], 0
0x14000df96  jnz     short loc_14000DFCF
0x14000df98  cmp     [rbp+190h+arg_20], 0
0x14000df9f  jnz     short loc_14000DFAA
0x14000dfa1  cmp     byte ptr [rbx+470h], 0
0x14000dfa8  jz      short loc_14000DFCF
0x14000dfaa  cmp     esi, 3Eh ; '>'
0x14000dfad  jnb     short loc_14000DFCF
0x14000dfaf  mov     rcx, [rbx+18h]; RunRefCacheAware
0x14000dfb3  mov     edx, 1; Count
0x14000dfb8  call    cs:ExAcquireRundownProtectionCacheAwareEx
0x14000dfbf  nop     dword ptr [rax+rax+00h]
0x14000dfc4  test    al, al
0x14000dfc6  jz      short loc_14000DFCF
0x14000dfc8  mov     [rsp+rsi*8+290h+var_230], rbx
0x14000dfcd  inc     esi
0x14000dfcf  mov     rbx, [rbx]
0x14000dfd2  test    rbx, rbx
0x14000dfd5  jnz     short loc_14000DF7B
0x14000dfd7  lea     rdx, [rsp+290h+LockState]; LockState
0x14000dfdc  lea     rcx, Lock; Lock
0x14000dfe3  call    cs:NdisReleaseReadWriteLock
0x14000dfea  nop     dword ptr [rax+rax+00h]
0x14000dfef  cmp     ebx, esi
0x14000dff1  jnb     loc_14000E16E
0x14000dff7  mov     r9b, 1
0x14000dffa  mov     [rsp+290h+DestNetBufferList], 0
0x14000e003  lea     r8, [rsp+290h+DestNetBufferList]
0x14000e008  mov     rdx, r13
0x14000e00b  mov     rcx, r15
0x14000e00e  call    sub_140008ABC
0x14000e013  test    eax, eax
0x14000e015  jnz     loc_14000E139
0x14000e01b  mov     rdi, [rsp+290h+DestNetBufferList]
0x14000e020  test    rdi, rdi
0x14000e023  jz      loc_14000E118
0x14000e029  mov     ecx, [rbp+190h+arg_48]
0x14000e02f  test    ecx, ecx
0x14000e031  jz      short loc_14000E098
0x14000e033  sub     ecx, 1
0x14000e036  jz      short loc_14000E084
0x14000e038  cmp     ecx, 1
0x14000e03b  jnz     short loc_14000E0AA
0x14000e03d  mov     rax, [r14+0B0h]
0x14000e044  mov     [rdi+0B0h], rax
0x14000e04b  mov     rax, [r14+0D0h]
0x14000e052  mov     [rdi+0D0h], rax
0x14000e059  mov     rax, [r14+0D8h]
0x14000e060  mov     [rdi+0D8h], rax
0x14000e067  mov     rax, [r14+100h]
0x14000e06e  mov     [rdi+100h], rax
0x14000e075  mov     rcx, [r14+10h]
0x14000e079  movzx   eax, word ptr [rcx+0Ah]
0x14000e07d  or      byte ptr [rax+rcx+28h], 10h
0x14000e082  jmp     short loc_14000E0AA
0x14000e084  mov     rdx, r14; SrcNetBufferList
0x14000e087  mov     rcx, rdi; DestNetBufferList
0x14000e08a  call    cs:NdisCopySendNetBufferListInfo
0x14000e091  nop     dword ptr [rax+rax+00h]
0x14000e096  jmp     short loc_14000E0AA
0x14000e098  mov     rdx, r14; SrcNetBufferList
0x14000e09b  mov     rcx, rdi; DestNetBufferList
0x14000e09e  call    cs:NdisCopyReceiveNetBufferListInfo
0x14000e0a5  nop     dword ptr [rax+rax+00h]
0x14000e0aa  mov     rcx, [rdi+8]; NetBuffer
0x14000e0ae  mov     r9d, 1; AlignMultiple
0x14000e0b4  xor     r8d, r8d; Storage
0x14000e0b7  mov     [rsp+290h+AlignOffset], 0; AlignOffset
0x14000e0bf  mov     edx, [rcx+18h]; BytesNeeded
0x14000e0c2  call    cs:NdisGetDataBuffer
0x14000e0c9  nop     dword ptr [rax+rax+00h]
0x14000e0ce  mov     r15, rax
0x14000e0d1  test    r12, r12
0x14000e0d4  jz      short loc_14000E0FC
0x14000e0d6  mov     rcx, [rdi+8]
0x14000e0da  mov     rdx, r15
0x14000e0dd  mov     rax, [rsp+290h+var_250]
0x14000e0e2  mov     r9, [rsp+290h+var_248]
0x14000e0e7  mov     r8, [rsp+rbx*8+290h+var_230]
0x14000e0ec  mov     ecx, [rcx+18h]
0x14000e0ef  mov     qword ptr [rsp+290h+AlignOffset], rax
0x14000e0f4  mov     rax, r12
0x14000e0f7  call    _guard_dispatch_icall
0x14000e0fc  mov     rdx, [rdi+8]
0x14000e100  mov     r8, r15
0x14000e103  mov     r9, [rsp+rbx*8+290h+var_230]
0x14000e108  mov     rcx, rdi
0x14000e10b  mov     edx, [rdx+18h]
0x14000e10e  call    sub_14000DAA8
0x14000e113  mov     r15, [rsp+290h+var_240]
0x14000e118  mov     rcx, [rsp+rbx*8+290h+var_230]
0x14000e11d  mov     edx, 1; Count
0x14000e122  mov     rcx, [rcx+18h]; RunRef
0x14000e126  call    cs:ExReleaseRundownProtectionCacheAwareEx
0x14000e12d  nop     dword ptr [rax+rax+00h]
0x14000e132  inc     ebx
0x14000e134  jmp     loc_14000DFEF
0x14000e139  test    cs:byte_14001E7B4, 1
0x14000e140  jz      short loc_14000E14E
0x14000e142  lea     rcx, aCouldNotAlloca_0; "Could not allocate NBL in BrdgCompSendT"...
0x14000e149  call    sub_140001010
0x14000e14e  mov     rcx, [rsp+rbx*8+290h+var_230]
0x14000e153  mov     edx, 1; Count
0x14000e158  mov     rcx, [rcx+18h]; RunRef
0x14000e15c  call    cs:ExReleaseRundownProtectionCacheAwareEx
0x14000e163  nop     dword ptr [rax+rax+00h]
0x14000e168  inc     ebx
0x14000e16a  cmp     ebx, esi
0x14000e16c  jb      short loc_14000E14E
0x14000e16e  xor     al, al
0x14000e170  mov     rcx, [rbp+190h+var_40]
0x14000e177  xor     rcx, rsp; StackCookie
0x14000e17a  call    __security_check_cookie
0x14000e17f  mov     rbx, [rsp+290h+arg_10]
0x14000e187  add     rsp, 260h
0x14000e18e  pop     r15
0x14000e190  pop     r14
0x14000e192  pop     r13
0x14000e194  pop     r12
0x14000e196  pop     rdi
0x14000e197  pop     rsi
0x14000e198  pop     rbp
0x14000e199  retn
```
