# ValidateOpenExistingHeapFromAddress(TDebugOutputFunctor &,DeviceValidationInfo const &,void const *,unsigned __int64,D3D12_SHARED_HEAP::PortableHeapDesc *)

- ea: `0x180050174`
- end: `0x18005050e`
- name: `?ValidateOpenExistingHeapFromAddress@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBX_KPEAUPortableHeapDesc@D3D12_SHARED_HEAP@@@Z`
- size: `922`
- prototype: `int(struct TDebugOutputFunctor *, const struct DeviceValidationInfo *, const void *, unsigned __int64, struct D3D12_SHARED_HEAP::PortableHeapDesc *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004fee0`

## callees

- `0x18002a630`
- `0x18002ef50`
- `0x180050174`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800501d8`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800502b0`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180050311`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800501d8`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800502b0`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180050311`
- `api-ms-win-core-memory-l1-1-1!GetWriteWatch` at `0x18005046d`
- `api-ms-win-core-memory-l1-1-1!GetWriteWatch` at `0x18005046d`

## string_xrefs

- `0x180050378`: `OpenExistingHeap is only supported when all the pages in the heap have the same access protection. Protection for the page starting at 0x%p was %I32u, did not match the base page protection %I32u`
- `0x180050389`: `OpenExistingHeapFromAllocation1 cannot open a region that spans multiple VirtualAlloc allocations. The page at 0x%p comes from a different allocation than the input (0x%p) despite being in the requested size (0x%I64x).`
- `0x180050354`: `OpenExistingHeap is only supported when all the pages in the heap have the same state. State for the page starting at 0x%p was %I32u, did not match the base page state %I32u`
- `0x1800504a3`: `pAddress must point to a memory region that can be written without PAGE_NOCACHE. pAddress = 0x%p, region address = 0x%p, region size = %Iu, writeable = %u, PAGE_NOCACHE = %u.`
- `0x1800504c8`: `pAddress must point to a committed memory region. pAddress = 0x%p, region address = 0x%p, region size = %Iu, MEM_RESERVE = %u, MEM_FREE = %u.`
- `0x1800503b7`: `OpenExistingHeap is only supported when D3D12_FEATURE_DATA_EXISTING_HEAP::Supported is TRUE. `

## pseudocode

```c
__int64 __fastcall ValidateOpenExistingHeapFromAddress(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        __int64 a3,
        __int64 a4,
        struct D3D12_SHARED_HEAP::PortableHeapDesc *a5)
{
  char *BaseAddress; // r11
  PVOID AllocationBase; // r10
  SIZE_T RegionSize; // r9
  DWORD Protect; // ecx
  DWORD State; // edx
  SIZE_T v14; // rax
  SIZE_T v15; // rax
  char *v16; // r14
  PVOID v17; // r9
  const char *v18; // r8
  const char *v19; // r8
  struct D3D12_SHARED_HEAP::PortableHeapDesc *v20; // rdi
  __int64 v21; // rcx
  DWORD v22; // eax
  int v24; // r8d
  DWORD lpdwCount; // [rsp+20h] [rbp-61h]
  DWORD lpdwGranularity; // [rsp+28h] [rbp-59h]
  ULONG_PTR dwCount; // [rsp+40h] [rbp-41h] BYREF
  PVOID Addresses; // [rsp+48h] [rbp-39h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+50h] [rbp-31h] BYREF
  struct _MEMORY_BASIC_INFORMATION v30; // [rsp+80h] [rbp-1h] BYREF
  DWORD dwGranularity; // [rsp+F0h] [rbp+6Fh] BYREF

  if ( !a3 )
  {
    TDebugOutputFunctor::operator()(a1, 1088, "pAddress is NULL.");
    return 2147942487LL;
  }
  memset(&Buffer, 0, sizeof(Buffer));
  if ( !VirtualQuery((LPCVOID)a3, &Buffer, 0x30u) )
  {
    TDebugOutputFunctor::operator()(a1, 1088, "VirtualQuery on pAddress failed. pAddress = 0x%p.", (const void *)a3);
    return 2147942487LL;
  }
  BaseAddress = (char *)Buffer.BaseAddress;
  AllocationBase = Buffer.AllocationBase;
  if ( a4 )
  {
    if ( Buffer.BaseAddress != (PVOID)a3 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1088,
        "pAddress must be aligned to the page size. pAddress = 0x%p, but the base address for the page containing that address = 0x%p",
        a3,
        Buffer.BaseAddress);
      return 2147942487LL;
    }
    a4 = Align<unsigned __int64>(a4, 4096);
  }
  else if ( Buffer.AllocationBase != (PVOID)a3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1088,
      "pAddress must be equal to the base address of an allocated memory region. pAddress = 0x%p, base address containing"
      " pAddress = 0x%p.",
      a3,
      Buffer.AllocationBase);
    return 2147942487LL;
  }
  v30 = Buffer;
  RegionSize = Buffer.RegionSize;
  Protect = Buffer.Protect;
  State = Buffer.State;
  while ( 1 )
  {
    if ( (State & 0x13000) != 0x1000 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1088,
        "pAddress must point to a committed memory region. pAddress = 0x%p, region address = 0x%p, region size = %Iu, MEM"
        "_RESERVE = %u, MEM_FREE = %u.",
        a3,
        v30.BaseAddress,
        RegionSize,
        (State >> 13) & 1,
        HIWORD(State) & 1);
      return 2147942487LL;
    }
    if ( !Protect || (Protect & 0x223) != 0 )
    {
      v24 = 1;
      if ( !Protect || (Protect & 0x23) != 0 )
        v24 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1088,
        "pAddress must point to a memory region that can be written without PAGE_NOCACHE. pAddress = 0x%p, region address"
        " = 0x%p, region size = %Iu, writeable = %u, PAGE_NOCACHE = %u.",
        a3,
        v30.BaseAddress,
        RegionSize,
        v24,
        (Protect >> 9) & 1);
      return 2147942487LL;
    }
    if ( a4 )
      break;
    v14 = VirtualQuery((char *)v30.BaseAddress + RegionSize, &v30, 0x30u);
    AllocationBase = Buffer.AllocationBase;
    if ( !v14 || v30.AllocationBase != Buffer.AllocationBase )
    {
LABEL_20:
      v15 = a4;
      if ( !a4 )
        v15 = Buffer.RegionSize;
      if ( v15 >= 0x100000000LL )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1088,
          "pAddress must point to a memory region that is 4GiB or less. pAddress = 0x%p, allocation size = %Iu.",
          a3,
          Buffer.RegionSize);
        return 2147942487LL;
      }
      if ( !*((_DWORD *)a2 + 196) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1112,
          "OpenExistingHeap is only supported when D3D12_FEATURE_DATA_EXISTING_HEAP::Supported is TRUE. ");
        return 2147942487LL;
      }
      v20 = a5;
      if ( a5 )
      {
        *(_QWORD *)a5 = v15;
        v21 = 0x400000;
        v22 = ~(Buffer.Protect >> 10);
        *((_DWORD *)v20 + 2) = 4;
        *((_DWORD *)v20 + 4) = 1;
        *((_DWORD *)v20 + 5) = 1;
        *((_DWORD *)v20 + 3) = v22 & 1 | 2;
        *((_DWORD *)v20 + 6) = 1;
        *((_QWORD *)v20 + 4) = 4096;
        if ( !(a3 % 0x400000) || (v21 = 0x10000, !(a3 % 0x10000)) )
          *((_QWORD *)v20 + 4) = v21;
        *((_DWORD *)v20 + 10) = 1057;
        if ( !a4 )
        {
          dwCount = 1;
          Addresses = 0;
          dwGranularity = 0;
          if ( !GetWriteWatch(0, AllocationBase, 0x1000u, &Addresses, &dwCount, &dwGranularity) )
            *((_DWORD *)v20 + 10) |= 0x200u;
        }
      }
      return 0;
    }
LABEL_27:
    Protect = v30.Protect;
    if ( v30.Protect != Buffer.Protect )
    {
      v18 = "OpenExistingHeap is only supported when all the pages in the heap have the same access protection. Protectio"
            "n for the page starting at 0x%p was %I32u, did not match the base page protection %I32u";
      lpdwGranularity = Buffer.Protect;
      lpdwCount = v30.Protect;
      goto LABEL_31;
    }
    State = v30.State;
    if ( v30.State != Buffer.State )
    {
      lpdwGranularity = Buffer.State;
      v18 = "OpenExistingHeap is only supported when all the pages in the heap have the same state. State for the page st"
            "arting at 0x%p was %I32u, did not match the base page state %I32u";
      lpdwCount = v30.State;
LABEL_31:
      TDebugOutputFunctor::operator()(a1, 1112, v18, v30.BaseAddress, lpdwCount, lpdwGranularity);
      return 2147942487LL;
    }
    RegionSize = v30.RegionSize;
    Buffer.RegionSize += v30.RegionSize;
    BaseAddress = (char *)Buffer.BaseAddress;
  }
  v16 = (char *)v30.BaseAddress + RegionSize;
  if ( (char *)v30.BaseAddress + RegionSize >= &BaseAddress[a4] )
    goto LABEL_20;
  if ( VirtualQuery((char *)v30.BaseAddress + RegionSize, &v30, 0x30u) )
  {
    v17 = v30.AllocationBase;
    AllocationBase = Buffer.AllocationBase;
    if ( v30.AllocationBase != Buffer.AllocationBase )
    {
      v19 = "OpenExistingHeapFromAllocation1 cannot open a region that spans multiple VirtualAlloc allocations. The page "
            "at 0x%p comes from a different allocation than the input (0x%p) despite being in the requested size (0x%I64x).";
      goto LABEL_35;
    }
    goto LABEL_27;
  }
  v17 = v16;
  v19 = "Failed to query page information for address 0x%p in region specified by base address = 0x%p and size = 0x%I64x."
        " This could indicate that the region is not fully allocated.";
LABEL_35:
  TDebugOutputFunctor::operator()(a1, 1088, v19, v17, a3, a4);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180050174  mov     [rsp-8+arg_0], rbx
0x180050179  mov     [rsp-8+arg_8], rsi
0x18005017e  push    rbp
0x18005017f  push    rdi
0x180050180  push    r13
0x180050182  push    r14
0x180050184  push    r15
0x180050186  lea     rbp, [rsp-2Fh]
0x18005018b  sub     rsp, 0B0h
0x180050192  mov     rsi, r9
0x180050195  mov     rbx, r8
0x180050198  mov     r15, rdx
0x18005019b  mov     rdi, rcx
0x18005019e  test    r8, r8
0x1800501a1  jnz     short loc_1800501B9
0x1800501a3  lea     r8, aPaddressIsNull; "pAddress is NULL."
0x1800501aa  mov     edx, 440h
0x1800501af  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800501b4  jmp     loc_1800504ED
0x1800501b9  xorps   xmm0, xmm0
0x1800501bc  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x1800501c0  mov     r13d, 30h ; '0'
0x1800501c6  mov     rcx, rbx; lpAddress
0x1800501c9  mov     r8d, r13d; dwLength
0x1800501cc  movups  xmmword ptr [rbp+4Fh+Buffer.BaseAddress], xmm0
0x1800501d0  movups  xmmword ptr [rbp+4Fh+Buffer.AllocationProtect], xmm0
0x1800501d4  movups  xmmword ptr [rbp+4Fh+Buffer.State], xmm0
0x1800501d8  call    cs:__imp_VirtualQuery
0x1800501de  test    rax, rax
0x1800501e1  jnz     short loc_1800501FF
0x1800501e3  mov     r9, rbx
0x1800501e6  lea     r8, aVirtualqueryOn; "VirtualQuery on pAddress failed. pAddre"...
0x1800501ed  mov     edx, 440h
0x1800501f2  mov     rcx, rdi
0x1800501f5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800501fa  jmp     loc_1800504ED
0x1800501ff  mov     r11, [rbp+4Fh+Buffer.BaseAddress]
0x180050203  mov     r10, [rbp+4Fh+Buffer.AllocationBase]
0x180050207  test    rsi, rsi
0x18005020a  jnz     short loc_180050232
0x18005020c  cmp     r10, rbx
0x18005020f  jz      short loc_180050255
0x180050211  mov     [rsp+0D0h+lpdwCount], r10
0x180050216  lea     r8, aPaddressMustBe; "pAddress must be equal to the base addr"...
0x18005021d  mov     r9, rbx
0x180050220  mov     edx, 440h
0x180050225  mov     rcx, rdi
0x180050228  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18005022d  jmp     loc_1800504ED
0x180050232  cmp     r11, rbx
0x180050235  jz      short loc_180050245
0x180050237  mov     [rsp+0D0h+lpdwCount], r11
0x18005023c  lea     r8, aPaddressMustBe_0; "pAddress must be aligned to the page si"...
0x180050243  jmp     short loc_18005021D
0x180050245  mov     edx, 1000h
0x18005024a  mov     rcx, rsi
0x18005024d  call    ??$Align@_K@@YA_K_K0@Z; Align<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180050252  mov     rsi, rax
0x180050255  movups  xmm0, xmmword ptr [rbp+4Fh+Buffer.BaseAddress]
0x180050259  movups  xmm1, xmmword ptr [rbp+4Fh+Buffer.AllocationProtect]
0x18005025d  movups  xmmword ptr [rbp+4Fh+var_50.BaseAddress], xmm0
0x180050261  movups  xmm0, xmmword ptr [rbp+4Fh+Buffer.State]
0x180050265  movups  xmmword ptr [rbp+4Fh+var_50.AllocationProtect], xmm1
0x180050269  mov     r9, [rbp+4Fh+var_50.RegionSize]
0x18005026d  movups  xmmword ptr [rbp+4Fh+var_50.State], xmm0
0x180050271  mov     ecx, [rbp+4Fh+var_50.Protect]
0x180050274  mov     edx, [rbp+4Fh+var_50.State]
0x180050277  mov     eax, edx
0x180050279  and     eax, 13000h
0x18005027e  cmp     eax, 1000h
0x180050283  jnz     loc_1800504AC
0x180050289  test    ecx, ecx
0x18005028b  jz      loc_180050480
0x180050291  test    ecx, 223h
0x180050297  jnz     loc_180050480
0x18005029d  test    rsi, rsi
0x1800502a0  jnz     short loc_1800502F7
0x1800502a2  mov     rcx, [rbp+4Fh+var_50.BaseAddress]
0x1800502a6  lea     rdx, [rbp+4Fh+var_50]; lpBuffer
0x1800502aa  add     rcx, r9; lpAddress
0x1800502ad  mov     r8, r13; dwLength
0x1800502b0  call    cs:__imp_VirtualQuery
0x1800502b6  mov     r10, [rbp+4Fh+Buffer.AllocationBase]
0x1800502ba  test    rax, rax
0x1800502bd  jz      short loc_1800502C5
0x1800502bf  cmp     [rbp+4Fh+var_50.AllocationBase], r10
0x1800502c3  jz      short loc_18005032D
0x1800502c5  mov     rcx, [rbp+4Fh+Buffer.RegionSize]
0x1800502c9  test    rsi, rsi
0x1800502cc  mov     rax, rsi
0x1800502cf  mov     rdx, 100000000h
0x1800502d9  cmovz   rax, rcx
0x1800502dd  cmp     rax, rdx
0x1800502e0  jb      loc_1800503AD
0x1800502e6  mov     [rsp+0D0h+lpdwCount], rcx
0x1800502eb  lea     r8, aPaddressMustPo_1; "pAddress must point to a memory region "...
0x1800502f2  jmp     loc_18005021D
0x1800502f7  mov     r14, [rbp+4Fh+var_50.BaseAddress]
0x1800502fb  lea     rax, [r11+rsi]
0x1800502ff  add     r14, r9
0x180050302  cmp     r14, rax
0x180050305  jnb     short loc_1800502C5
0x180050307  mov     r8, r13; dwLength
0x18005030a  lea     rdx, [rbp+4Fh+var_50]; lpBuffer
0x18005030e  mov     rcx, r14; lpAddress
0x180050311  call    cs:__imp_VirtualQuery
0x180050317  test    rax, rax
0x18005031a  jz      loc_1800503A1
0x180050320  mov     r9, [rbp+4Fh+var_50.AllocationBase]
0x180050324  mov     r10, [rbp+4Fh+Buffer.AllocationBase]
0x180050328  cmp     r9, r10
0x18005032b  jnz     short loc_180050389
0x18005032d  mov     ecx, [rbp+4Fh+var_50.Protect]
0x180050330  cmp     ecx, [rbp+4Fh+Buffer.Protect]
0x180050333  jnz     short loc_180050375
0x180050335  mov     edx, [rbp+4Fh+var_50.State]
0x180050338  mov     eax, [rbp+4Fh+Buffer.State]
0x18005033b  cmp     edx, eax
0x18005033d  jnz     short loc_180050350
0x18005033f  mov     r9, [rbp+4Fh+var_50.RegionSize]
0x180050343  add     [rbp+4Fh+Buffer.RegionSize], r9
0x180050347  mov     r11, [rbp+4Fh+Buffer.BaseAddress]
0x18005034b  jmp     loc_180050277
0x180050350  mov     dword ptr [rsp+0D0h+lpdwGranularity], eax
0x180050354  lea     r8, aOpenexistinghe_1; "OpenExistingHeap is only supported when"...
0x18005035b  mov     dword ptr [rsp+0D0h+lpdwCount], edx
0x18005035f  mov     r9, [rbp+4Fh+var_50.BaseAddress]
0x180050363  mov     edx, 458h
0x180050368  mov     rcx, rdi
0x18005036b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180050370  jmp     loc_1800504ED
0x180050375  mov     eax, [rbp+4Fh+Buffer.Protect]
0x180050378  lea     r8, aOpenexistinghe; "OpenExistingHeap is only supported when"...
0x18005037f  mov     dword ptr [rsp+0D0h+lpdwGranularity], eax
0x180050383  mov     dword ptr [rsp+0D0h+lpdwCount], ecx
0x180050387  jmp     short loc_18005035F
0x180050389  lea     r8, aOpenexistinghe_0; "OpenExistingHeapFromAllocation1 cannot "...
0x180050390  mov     [rsp+0D0h+lpdwGranularity], rsi
0x180050395  mov     edx, 440h
0x18005039a  mov     [rsp+0D0h+lpdwCount], rbx
0x18005039f  jmp     short loc_180050368
0x1800503a1  mov     r9, r14
0x1800503a4  lea     r8, aFailedToQueryP; "Failed to query page information for ad"...
0x1800503ab  jmp     short loc_180050390
0x1800503ad  cmp     dword ptr [r15+310h], 0
0x1800503b5  jnz     short loc_1800503CB
0x1800503b7  lea     r8, aOpenexistinghe_2; "OpenExistingHeap is only supported when"...
0x1800503be  mov     edx, 458h
0x1800503c3  mov     rcx, rdi
0x1800503c6  jmp     loc_1800501AF
0x1800503cb  mov     rdi, [rbp+4Fh+arg_20]
0x1800503cf  test    rdi, rdi
0x1800503d2  jz      loc_18005047C
0x1800503d8  mov     [rdi], rax
0x1800503db  mov     r8d, 1
0x1800503e1  mov     eax, [rbp+4Fh+Buffer.Protect]
0x1800503e4  mov     ecx, 400000h
0x1800503e9  shr     eax, 0Ah
0x1800503ec  not     eax
0x1800503ee  mov     dword ptr [rdi+8], 4
0x1800503f5  and     eax, r8d
0x1800503f8  mov     [rdi+10h], r8d
0x1800503fc  or      eax, 2
0x1800503ff  mov     [rdi+14h], r8d
0x180050403  mov     [rdi+0Ch], eax
0x180050406  mov     rax, rbx
0x180050409  cqo
0x18005040b  mov     [rdi+18h], r8d
0x18005040f  idiv    rcx
0x180050412  mov     qword ptr [rdi+20h], 1000h
0x18005041a  test    rdx, rdx
0x18005041d  jz      short loc_180050431
0x18005041f  mov     rax, rbx
0x180050422  mov     ecx, 10000h
0x180050427  cqo
0x180050429  idiv    rcx
0x18005042c  test    rdx, rdx
0x18005042f  jnz     short loc_180050435
0x180050431  mov     [rdi+20h], rcx
0x180050435  mov     dword ptr [rdi+28h], 421h
0x18005043c  test    rsi, rsi
0x18005043f  jnz     short loc_18005047C
0x180050441  lea     rax, [rbp+4Fh+dwGranularity]
0x180050445  mov     [rbp+4Fh+dwCount], r8
0x180050449  mov     [rsp+0D0h+lpdwGranularity], rax; lpdwGranularity
0x18005044e  lea     r9, [rbp+4Fh+Addresses]; lpAddresses
0x180050452  lea     rax, [rbp+4Fh+dwCount]
0x180050456  mov     [rbp+4Fh+Addresses], rsi
0x18005045a  mov     r8d, 1000h; dwRegionSize
0x180050460  mov     [rsp+0D0h+lpdwCount], rax; lpdwCount
0x180050465  mov     rdx, r10; lpBaseAddress
0x180050468  mov     [rbp+4Fh+dwGranularity], esi
0x18005046b  xor     ecx, ecx; dwFlags
0x18005046d  call    cs:__imp_GetWriteWatch
0x180050473  test    eax, eax
0x180050475  jnz     short loc_18005047C
0x180050477  bts     dword ptr [rdi+28h], 9
0x18005047c  xor     eax, eax
0x18005047e  jmp     short loc_1800504F2
0x180050480  mov     eax, ecx
0x180050482  mov     r8d, 1
0x180050488  shr     eax, 9
0x18005048b  and     eax, r8d
0x18005048e  test    ecx, ecx
0x180050490  jz      short loc_180050497
0x180050492  test    cl, 23h
0x180050495  jz      short loc_18005049A
0x180050497  xor     r8d, r8d
0x18005049a  mov     [rsp+0D0h+var_98], eax
0x18005049e  mov     [rsp+0D0h+var_A0], r8d
0x1800504a3  lea     r8, aPaddressMustPo; "pAddress must point to a memory region "...
0x1800504aa  jmp     short loc_1800504CF
0x1800504ac  mov     eax, edx
0x1800504ae  mov     r8d, 1
0x1800504b4  shr     eax, 10h
0x1800504b7  and     eax, r8d
0x1800504ba  shr     edx, 0Dh
0x1800504bd  and     edx, r8d
0x1800504c0  mov     [rsp+0D0h+var_98], eax
0x1800504c4  mov     [rsp+0D0h+var_A0], edx
0x1800504c8  lea     r8, aPaddressMustPo_0; "pAddress must point to a committed memo"...
0x1800504cf  mov     rax, [rbp+4Fh+var_50.BaseAddress]
0x1800504d3  mov     edx, 440h
0x1800504d8  mov     [rsp+0D0h+lpdwGranularity], r9
0x1800504dd  mov     rcx, rdi
0x1800504e0  mov     r9, rbx
0x1800504e3  mov     [rsp+0D0h+lpdwCount], rax
0x1800504e8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800504ed  mov     eax, 80070057h
0x1800504f2  lea     r11, [rsp+0D0h+var_20]
0x1800504fa  mov     rbx, [r11+30h]
0x1800504fe  mov     rsi, [r11+38h]
0x180050502  mov     rsp, r11
0x180050505  pop     r15
0x180050507  pop     r14
0x180050509  pop     r13
0x18005050b  pop     rdi
0x18005050c  pop     rbp
0x18005050d  retn
```
