# BiOpenStoreWithHash

- ea: `0x14001bb00`
- end: `0x14001bd3b`
- name: `BiOpenStoreWithHash`
- size: `571`
- prototype: `__int64 __fastcall(const void **, unsigned int, __int64, __int64 *)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x140003d30`
- `0x140004080`
- `0x140004f9c`
- `0x140005e18`
- `0x140007c10`
- `0x140009658`
- `0x140009bdc`
- `0x14001b1f4`

## callees

- `0x1400133e4`
- `0x14001ae94`
- `0x14001af00`
- `0x14001b354`
- `0x14001b92c`
- `0x14001bb00`
- `0x14001bd44`
- `0x14001c014`
- `0x14001ece0`
- `0x1400265e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001bc0c`
- `ntdll!RtlAllocateHeap` at `0x14001bc0c`
- `ntdll!RtlFreeHeap` at `0x14001bd1a`
- `ntdll!RtlFreeHeap` at `0x14001bd1a`

## string_xrefs

- `0x14001bbd0`: `Failed to open system store. Status: %x`
- `0x14001bc4c`: `Store path: "%s"`
- `0x14001bc6d`: `Store will be accessed with offline registry APIs.`
- `0x14001bca6`: `BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x`
- `0x14001bb4c`: `BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x`
- `0x14001bb78`: `Opening store. Flags: 0x%x`
- `0x14001bcc7`: `GuidCache`

## pseudocode

```c
__int64 __fastcall BiOpenStoreWithHash(const void **a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  char v5; // bp
  NTSTATUS v8; // eax
  unsigned int v9; // edi
  const wchar_t *v10; // r8
  int v12; // edi
  int v13; // r15d
  unsigned int v14; // esi
  __int64 v15; // rcx
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // r13d
  _DWORD *Heap; // rax
  void *v20; // r14
  _DWORD *v21; // r13
  __int64 v22; // r8
  int v23; // eax
  void *v24; // r8
  __int64 v25; // rsi
  int v26; // eax
  __int64 v27; // [rsp+90h] [rbp+18h] BYREF

  v27 = a3;
  v5 = a2 & 1;
  v8 = BiAcquireBcdSyncMutant(a2 & 1);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = 2;
    v27 = 0;
    v13 = a2 & 2;
    v14 = 0;
    BiLogMessage(2, L"Opening store. Flags: 0x%x", a2);
    if ( a1 )
    {
      if ( !v5 )
        BiCleanupLoadedStores(0);
      v18 = *(unsigned __int16 *)a1 + 14;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
      v20 = Heap;
      if ( Heap )
      {
        Heap[1] = v18;
        v21 = Heap + 3;
        *Heap = 1;
        Heap[2] = 3;
        memcpy_0(Heap + 3, a1[1], *(unsigned __int16 *)a1);
        *((_WORD *)v21 + ((unsigned __int64)*(unsigned __int16 *)a1 >> 1)) = 0;
        BiLogMessage(2, L"Store path: \"%s\"", v21);
        if ( v5 )
        {
          BiLogMessage(2, L"Store will be accessed with offline registry APIs.");
          v14 = 32;
        }
        v23 = BiAddStoreFromFile((__int64)v20, v14, v22, &v27);
        v16 = v23;
        if ( v23 >= 0 )
        {
          v25 = v27;
          BiDeleteRegistryValue(v27, L"GuidCache", v24);
          v26 = BiMarkTreatAsSystemStore(v25, 0);
          v16 = v26;
          if ( v26 >= 0 )
          {
            if ( !v13 )
              v25 |= 2uLL;
            *a4 = v25;
          }
          else
          {
            BiLogMessage(4, L"Failed to clear system store flag. Status: %x", (unsigned int)v26);
          }
        }
        else
        {
          if ( v23 != -1073741809 )
            v12 = 4;
          BiLogMessage(
            v12,
            L"BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x",
            v21,
            v14,
            v23);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      }
      else
      {
        v16 = -1073741801;
      }
    }
    else if ( v5 )
    {
      v16 = -1073741811;
    }
    else
    {
      if ( (a2 & 2) != 0 )
        BiLogMessage(2, L"Store will be synchronized with firmware.");
      else
        v14 = 2;
      v17 = BiOpenSystemStore(a4, v14);
      v16 = v17;
      if ( v17 < 0 )
        BiLogMessage(4, L"Failed to open system store. Status: %x", (unsigned int)v17);
    }
    LOBYTE(v15) = v5;
    BiReleaseBcdSyncMutant(v15);
    return v16;
  }
  else
  {
    if ( a1 )
      v10 = (const wchar_t *)a1[1];
    else
      v10 = L"NULL";
    BiLogMessage(4, L"BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x", v10, a2, v8);
    return v9;
  }
}

```

## disassembly

```asm
0x14001bb00  mov     [rsp+arg_10], r8
0x14001bb05  push    rbx
0x14001bb06  push    rbp
0x14001bb07  push    rsi
0x14001bb08  push    rdi
0x14001bb09  push    r12
0x14001bb0b  push    r13
0x14001bb0d  push    r14
0x14001bb0f  push    r15
0x14001bb11  sub     rsp, 38h
0x14001bb15  mov     bpl, dl
0x14001bb18  mov     rbx, rcx
0x14001bb1b  and     bpl, 1
0x14001bb1f  mov     r12, r9
0x14001bb22  mov     cl, bpl
0x14001bb25  mov     r14d, edx
0x14001bb28  call    BiAcquireBcdSyncMutant
0x14001bb2d  mov     edi, eax
0x14001bb2f  test    eax, eax
0x14001bb31  jns     short loc_14001BB64
0x14001bb33  test    rbx, rbx
0x14001bb36  jz      short loc_14001BB3E
0x14001bb38  mov     r8, [rbx+8]
0x14001bb3c  jmp     short loc_14001BB45
0x14001bb3e  lea     r8, aNull; "NULL"
0x14001bb45  mov     r9d, r14d
0x14001bb48  mov     [rsp+78h+var_58], edi
0x14001bb4c  lea     rdx, aBcdopenstoreFa; "BcdOpenStore: Failed to acquire BCD syn"...
0x14001bb53  mov     ecx, 4
0x14001bb58  call    BiLogMessage
0x14001bb5d  mov     eax, edi
0x14001bb5f  jmp     loc_14001BD2A
0x14001bb64  mov     edi, 2
0x14001bb69  mov     [rsp+78h+arg_10], 0
0x14001bb75  mov     r15d, r14d
0x14001bb78  lea     rdx, aOpeningStoreFl; "Opening store. Flags: 0x%x"
0x14001bb7f  mov     ecx, edi
0x14001bb81  mov     r8d, r14d
0x14001bb84  and     r15d, edi
0x14001bb87  xor     esi, esi
0x14001bb89  call    BiLogMessage
0x14001bb8e  test    rbx, rbx
0x14001bb91  jnz     short loc_14001BBE6
0x14001bb93  test    bpl, bpl
0x14001bb96  jz      short loc_14001BBA2
0x14001bb98  mov     ebx, 0C000000Dh
0x14001bb9d  jmp     loc_14001BD20
0x14001bba2  test    r15d, r15d
0x14001bba5  jnz     short loc_14001BBAB
0x14001bba7  mov     esi, edi
0x14001bba9  jmp     short loc_14001BBB9
0x14001bbab  lea     rdx, aStoreWillBeSyn; "Store will be synchronized with firmwar"...
0x14001bbb2  mov     ecx, edi
0x14001bbb4  call    BiLogMessage
0x14001bbb9  mov     edx, esi
0x14001bbbb  mov     rcx, r12
0x14001bbbe  call    BiOpenSystemStore
0x14001bbc3  mov     ebx, eax
0x14001bbc5  test    eax, eax
0x14001bbc7  jns     loc_14001BD20
0x14001bbcd  mov     r8d, eax
0x14001bbd0  lea     rdx, aFailedToOpenSy; "Failed to open system store. Status: %x"
0x14001bbd7  mov     ecx, 4
0x14001bbdc  call    BiLogMessage
0x14001bbe1  jmp     loc_14001BD20
0x14001bbe6  test    bpl, bpl
0x14001bbe9  jnz     short loc_14001BBF2
0x14001bbeb  xor     ecx, ecx
0x14001bbed  call    BiCleanupLoadedStores
0x14001bbf2  mov     rcx, gs:60h
0x14001bbfb  xor     edx, edx; Flags
0x14001bbfd  movzx   r13d, word ptr [rbx]
0x14001bc01  add     r13d, 0Eh
0x14001bc05  mov     r8d, r13d; Size
0x14001bc08  mov     rcx, [rcx+30h]; HeapHandle
0x14001bc0c  call    cs:__imp_RtlAllocateHeap
0x14001bc12  mov     r14, rax
0x14001bc15  test    rax, rax
0x14001bc18  jnz     short loc_14001BC24
0x14001bc1a  mov     ebx, 0C0000017h
0x14001bc1f  jmp     loc_14001BD20
0x14001bc24  mov     [rax+4], r13d
0x14001bc28  lea     r13, [rax+0Ch]
0x14001bc2c  mov     dword ptr [rax], 1
0x14001bc32  mov     rcx, r13; void *
0x14001bc35  mov     dword ptr [rax+8], 3
0x14001bc3c  movzx   r8d, word ptr [rbx]; Size
0x14001bc40  mov     rdx, [rbx+8]; Src
0x14001bc44  call    memcpy_0
0x14001bc49  movzx   ecx, word ptr [rbx]
0x14001bc4c  lea     rdx, aStorePathS; "Store path: \"%s\""
0x14001bc53  shr     rcx, 1
0x14001bc56  xor     eax, eax
0x14001bc58  mov     r8, r13
0x14001bc5b  mov     [r13+rcx*2+0], ax
0x14001bc61  mov     ecx, edi
0x14001bc63  call    BiLogMessage
0x14001bc68  test    bpl, bpl
0x14001bc6b  jz      short loc_14001BC80
0x14001bc6d  lea     rdx, aStoreWillBeAcc; "Store will be accessed with offline reg"...
0x14001bc74  mov     ecx, edi
0x14001bc76  call    BiLogMessage
0x14001bc7b  mov     esi, 20h ; ' '
0x14001bc80  lea     r9, [rsp+78h+arg_10]
0x14001bc88  mov     edx, esi
0x14001bc8a  mov     rcx, r14
0x14001bc8d  call    BiAddStoreFromFile
0x14001bc92  mov     ebx, eax
0x14001bc94  test    eax, eax
0x14001bc96  jns     short loc_14001BCBF
0x14001bc98  mov     ecx, 4
0x14001bc9d  mov     [rsp+78h+var_58], eax
0x14001bca1  cmp     eax, 0C000000Fh
0x14001bca6  lea     rdx, aBcdopenstoreFa_1; "BcdOpenStore: Failed to add store from "...
0x14001bcad  mov     r9d, esi
0x14001bcb0  mov     r8, r13
0x14001bcb3  cmovnz  edi, ecx
0x14001bcb6  mov     ecx, edi
0x14001bcb8  call    BiLogMessage
0x14001bcbd  jmp     short loc_14001BD08
0x14001bcbf  mov     rsi, [rsp+78h+arg_10]
0x14001bcc7  lea     rdx, aGuidcache; "GuidCache"
0x14001bcce  mov     rcx, rsi
0x14001bcd1  call    BiDeleteRegistryValue
0x14001bcd6  xor     edx, edx
0x14001bcd8  mov     rcx, rsi
0x14001bcdb  call    BiMarkTreatAsSystemStore
0x14001bce0  mov     ebx, eax
0x14001bce2  test    eax, eax
0x14001bce4  jns     short loc_14001BCFC
0x14001bce6  mov     r8d, eax
0x14001bce9  lea     rdx, aFailedToClearS; "Failed to clear system store flag. Stat"...
0x14001bcf0  mov     ecx, 4
0x14001bcf5  call    BiLogMessage
0x14001bcfa  jmp     short loc_14001BD08
0x14001bcfc  test    r15d, r15d
0x14001bcff  jnz     short loc_14001BD04
0x14001bd01  or      rsi, rdi
0x14001bd04  mov     [r12], rsi
0x14001bd08  mov     rcx, gs:60h
0x14001bd11  mov     r8, r14; P
0x14001bd14  xor     edx, edx; Flags
0x14001bd16  mov     rcx, [rcx+30h]; HeapHandle
0x14001bd1a  call    cs:__imp_RtlFreeHeap
0x14001bd20  mov     cl, bpl
0x14001bd23  call    BiReleaseBcdSyncMutant
0x14001bd28  mov     eax, ebx
0x14001bd2a  add     rsp, 38h
0x14001bd2e  pop     r15
0x14001bd30  pop     r14
0x14001bd32  pop     r13
0x14001bd34  pop     r12
0x14001bd36  pop     rdi
0x14001bd37  pop     rsi
0x14001bd38  pop     rbp
0x14001bd39  pop     rbx
0x14001bd3a  retn
```
