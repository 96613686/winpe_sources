# BfsDeleteEntry

- ea: `0x140010ffc`
- end: `0x140011266`
- name: `BfsDeleteEntry`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140009b9c`
- `0x14000c658`

## callees

- `0x14001079c`
- `0x140010ffc`
- `0x14001126c`
- `0x1400116a0`
- `0x140011894`
- `0x14001198c`
- `0x140011a38`
- `0x140012ab0`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001112f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001112f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400111d2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011219`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400111d2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011219`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011086`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140011086`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400110a6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400110a6`
- `ntoskrnl!RtlClearBits` at `0x140011197`
- `ntoskrnl!RtlClearBits` at `0x140011197`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001117f`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001117f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011075`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001111e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011075`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001111e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400110b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400111de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011225`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400110b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400111de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011225`

## pseudocode

```c
__int64 __fastcall BfsDeleteEntry(__int64 a1, int a2, const UNICODE_STRING *a3, __int128 *a4)
{
  __int128 v4; // xmm1
  __int64 result; // rax
  PVOID *v8; // rdi
  _DWORD *Entry; // rsi
  int v10; // eax
  volatile signed __int32 *v11; // rcx
  NTSTATUS EntryBlock; // ebx
  ULONG *v13; // r14
  ULONG EntryIndex; // ebx
  ULONG *v15; // [rsp+20h] [rbp-50h] BYREF
  _RTL_BITMAP BitMapHeader; // [rsp+28h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-38h] BYREF
  UNICODE_STRING v18; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v19[24]; // [rsp+58h] [rbp-18h] BYREF
  PVOID *v20; // [rsp+A0h] [rbp+30h] BYREF
  PVOID *v21; // [rsp+B8h] [rbp+48h] BYREF

  v4 = *a4;
  v20 = 0;
  v17 = v4;
  v18 = 0;
  result = BfsCreateDirectory(a1 + 48, a3, 1, &v20);
  if ( (int)result >= 0 )
  {
    v8 = v20;
    v21 = v20;
    while ( 1 )
    {
      v17 = *(_OWORD *)BfsGetPathComponent(v19, &v17, &v18);
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(v8, 0);
      Entry = (_DWORD *)BfsFindEntry(v8, &v18);
      ExReleasePushLockSharedEx(v8, 0);
      KeLeaveCriticalRegion();
      if ( !Entry )
        break;
      if ( (unsigned __int16)v17 < 2u )
      {
        LODWORD(v20) = 0;
        LODWORD(BitMapHeader.Buffer) = 0;
        *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
        v15 = 0;
        if ( *Entry != a2 )
        {
          EntryBlock = -1073741788;
LABEL_20:
          v11 = (volatile signed __int32 *)(v8 - 1);
LABEL_16:
          BfsDereferenceTableEntry(v11);
          return (unsigned int)EntryBlock;
        }
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v8, 0);
        EntryBlock = BfsGetEntryBlock(v8, Entry, &v15, &v20);
        if ( EntryBlock < 0 )
        {
          ExReleasePushLockExclusiveEx(v8, 0);
          KeLeaveCriticalRegion();
          goto LABEL_20;
        }
        v13 = v15;
        if ( *Entry == 1 )
        {
          EntryIndex = BfsGetEntryIndex(v15, Entry);
          RtlInitializeBitMap(&BitMapHeader, v13 + 3992, 0x1Eu);
          RtlClearBits(&BitMapHeader, EntryIndex, 1u);
          memset(Entry, 0, 0x214u);
        }
        else
        {
          *(_QWORD *)(Entry + 1) = 0;
        }
        EntryBlock = BfsWriteBlock(a1, (int)v20, v13);
        ExReleasePushLockExclusiveEx(v8, 0);
        KeLeaveCriticalRegion();
        BfsDereferenceTableEntry((volatile signed __int32 *)v8 - 2);
        if ( EntryBlock < 0 )
          return (unsigned int)EntryBlock;
      }
      else
      {
        v10 = BfsCreateDirectory((__int64)v8, &v18, 1, &v21);
        v11 = (volatile signed __int32 *)(v8 - 1);
        EntryBlock = v10;
        if ( v10 < 0 )
          goto LABEL_16;
        BfsDereferenceTableEntry(v11);
        v8 = v21;
      }
      if ( (unsigned __int16)v17 < 2u || v18.Length < 2u )
        return (unsigned int)EntryBlock;
    }
    BfsDereferenceTableEntry((volatile signed __int32 *)v8 - 2);
    return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x140010ffc  mov     [rsp-28h+arg_8], rbx
0x140011001  mov     [rsp-28h+arg_10], rsi
0x140011006  push    rbp
0x140011007  push    rdi
0x140011008  push    r12
0x14001100a  push    r14
0x14001100c  push    r15
0x14001100e  mov     rbp, rsp
0x140011011  sub     rsp, 70h
0x140011015  movups  xmm1, xmmword ptr [r9]
0x140011019  mov     rax, r8
0x14001101c  mov     [rbp+arg_0], 0
0x140011024  mov     r12d, edx
0x140011027  lea     r9, [rbp+arg_0]
0x14001102b  mov     r15, rcx
0x14001102e  xorps   xmm0, xmm0
0x140011031  add     rcx, 30h ; '0'
0x140011035  mov     r8d, 1
0x14001103b  mov     rdx, rax
0x14001103e  movdqu  [rbp+var_38], xmm1
0x140011043  movups  [rbp+var_28], xmm0
0x140011047  call    BfsCreateDirectory
0x14001104c  test    eax, eax
0x14001104e  js      loc_14001124C
0x140011054  mov     rdi, [rbp+arg_0]
0x140011058  mov     [rbp+arg_18], rdi
0x14001105c  lea     r8, [rbp+var_28]
0x140011060  lea     rdx, [rbp+var_38]
0x140011064  lea     rcx, [rbp+var_18]
0x140011068  call    BfsGetPathComponent
0x14001106d  movups  xmm1, xmmword ptr [rax]
0x140011070  movdqu  [rbp+var_38], xmm1
0x140011075  call    cs:__imp_KeEnterCriticalRegion
0x14001107c  nop     dword ptr [rax+rax+00h]
0x140011081  xor     edx, edx
0x140011083  mov     rcx, rdi
0x140011086  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001108d  nop     dword ptr [rax+rax+00h]
0x140011092  lea     rdx, [rbp+var_28]
0x140011096  mov     rcx, rdi
0x140011099  call    BfsFindEntry
0x14001109e  xor     edx, edx
0x1400110a0  mov     rcx, rdi
0x1400110a3  mov     rsi, rax
0x1400110a6  call    cs:__imp_ExReleasePushLockSharedEx
0x1400110ad  nop     dword ptr [rax+rax+00h]
0x1400110b2  call    cs:__imp_KeLeaveCriticalRegion
0x1400110b9  nop     dword ptr [rax+rax+00h]
0x1400110be  test    rsi, rsi
0x1400110c1  jz      loc_14001123E
0x1400110c7  cmp     word ptr [rbp+var_38], 2
0x1400110cc  jb      short loc_140011100
0x1400110ce  lea     r9, [rbp+arg_18]
0x1400110d2  mov     r8d, 1
0x1400110d8  lea     rdx, [rbp+var_28]
0x1400110dc  mov     rcx, rdi
0x1400110df  call    BfsCreateDirectory
0x1400110e4  lea     rcx, [rdi-8]; Buffer
0x1400110e8  mov     ebx, eax
0x1400110ea  test    eax, eax
0x1400110ec  js      loc_14001120B
0x1400110f2  call    BfsDereferenceTableEntry
0x1400110f7  mov     rdi, [rbp+arg_18]
0x1400110fb  jmp     loc_1400111F7
0x140011100  xor     eax, eax
0x140011102  mov     dword ptr [rbp+arg_0], 0
0x140011109  mov     qword ptr [rbp+BitMapHeader+4], rax
0x14001110d  mov     qword ptr [rbp+BitMapHeader.SizeOfBitMap], rax
0x140011111  mov     [rbp+var_50], rax
0x140011115  cmp     [rsi], r12d
0x140011118  jnz     loc_140011233
0x14001111e  call    cs:__imp_KeEnterCriticalRegion
0x140011125  nop     dword ptr [rax+rax+00h]
0x14001112a  xor     edx, edx
0x14001112c  mov     rcx, rdi
0x14001112f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011136  nop     dword ptr [rax+rax+00h]
0x14001113b  lea     r9, [rbp+arg_0]
0x14001113f  mov     rdx, rsi
0x140011142  lea     r8, [rbp+var_50]
0x140011146  mov     rcx, rdi
0x140011149  call    BfsGetEntryBlock
0x14001114e  mov     ebx, eax
0x140011150  test    eax, eax
0x140011152  js      loc_140011214
0x140011158  cmp     dword ptr [rsi], 1
0x14001115b  mov     r14, [rbp+var_50]
0x14001115f  jnz     short loc_1400111B5
0x140011161  mov     rdx, rsi
0x140011164  mov     rcx, r14
0x140011167  call    BfsGetEntryIndex
0x14001116c  lea     rdx, [r14+3E60h]; BitMapBuffer
0x140011173  mov     r8d, 1Eh; SizeOfBitMap
0x140011179  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001117d  mov     ebx, eax
0x14001117f  call    cs:__imp_RtlInitializeBitMap
0x140011186  nop     dword ptr [rax+rax+00h]
0x14001118b  mov     r8d, 1; NumberToClear
0x140011191  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x140011195  mov     edx, ebx; StartingIndex
0x140011197  call    cs:__imp_RtlClearBits
0x14001119e  nop     dword ptr [rax+rax+00h]
0x1400111a3  xor     edx, edx; Val
0x1400111a5  mov     r8d, 214h; Size
0x1400111ab  mov     rcx, rsi; void *
0x1400111ae  call    memset
0x1400111b3  jmp     short loc_1400111BD
0x1400111b5  mov     qword ptr [rsi+4], 0
0x1400111bd  mov     edx, dword ptr [rbp+arg_0]
0x1400111c0  mov     r8, r14
0x1400111c3  mov     rcx, r15
0x1400111c6  call    BfsWriteBlock
0x1400111cb  xor     edx, edx
0x1400111cd  mov     rcx, rdi
0x1400111d0  mov     ebx, eax
0x1400111d2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400111d9  nop     dword ptr [rax+rax+00h]
0x1400111de  call    cs:__imp_KeLeaveCriticalRegion
0x1400111e5  nop     dword ptr [rax+rax+00h]
0x1400111ea  lea     rcx, [rdi-8]; Buffer
0x1400111ee  call    BfsDereferenceTableEntry
0x1400111f3  test    ebx, ebx
0x1400111f5  js      short loc_140011210
0x1400111f7  cmp     word ptr [rbp+var_38], 2
0x1400111fc  jb      short loc_140011210
0x1400111fe  cmp     word ptr [rbp+var_28], 2
0x140011203  jnb     loc_14001105C
0x140011209  jmp     short loc_140011210
0x14001120b  call    BfsDereferenceTableEntry
0x140011210  mov     eax, ebx
0x140011212  jmp     short loc_14001124C
0x140011214  xor     edx, edx
0x140011216  mov     rcx, rdi
0x140011219  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011220  nop     dword ptr [rax+rax+00h]
0x140011225  call    cs:__imp_KeLeaveCriticalRegion
0x14001122c  nop     dword ptr [rax+rax+00h]
0x140011231  jmp     short loc_140011238
0x140011233  mov     ebx, 0C0000024h
0x140011238  lea     rcx, [rdi-8]
0x14001123c  jmp     short loc_14001120B
0x14001123e  lea     rcx, [rdi-8]; Buffer
0x140011242  call    BfsDereferenceTableEntry
0x140011247  mov     eax, 0C0000225h
0x14001124c  lea     r11, [rsp+70h+var_s0]
0x140011251  mov     rbx, [r11+38h]
0x140011255  mov     rsi, [r11+40h]
0x140011259  mov     rsp, r11
0x14001125c  pop     r15
0x14001125e  pop     r14
0x140011260  pop     r12
0x140011262  pop     rdi
0x140011263  pop     rbp
0x140011264  retn
```
