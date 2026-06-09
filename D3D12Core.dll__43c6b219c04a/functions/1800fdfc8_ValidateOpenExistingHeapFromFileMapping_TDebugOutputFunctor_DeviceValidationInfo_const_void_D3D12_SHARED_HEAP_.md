# ValidateOpenExistingHeapFromFileMapping(TDebugOutputFunctor &,DeviceValidationInfo const &,void *,D3D12_SHARED_HEAP::PortableHeapDesc *)

- ea: `0x1800fdfc8`
- end: `0x1800fe190`
- name: `?ValidateOpenExistingHeapFromFileMapping@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEAXPEAUPortableHeapDesc@D3D12_SHARED_HEAP@@@Z`
- size: `456`
- prototype: `int(struct TDebugOutputFunctor *, const struct DeviceValidationInfo *, void *, struct D3D12_SHARED_HEAP::PortableHeapDesc *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f82f0`

## callees

- `0x18002ef50`
- `0x1800fdfc8`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800fe0d5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800fe0d5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800fe0c3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800fe0c3`

## string_xrefs

- `0x1800fe074`: `hFileMapping must be a committed memory region that is not uncached. hFileMapping = 0x%p, SEC_RESERVE = %u, SEC_NOCACHE = %u.`
- `0x1800fe16b`: `hFileMapping must have CPU write access. hFileMapping = 0x%p.`
- `0x1800fe116`: `OpenExistingHeap is only supported when D3D12_FEATURE_DATA_EXISTING_HEAP::Supported is TRUE. `

## pseudocode

```c
__int64 __fastcall ValidateOpenExistingHeapFromFileMapping(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        void *a3,
        struct D3D12_SHARED_HEAP::PortableHeapDesc *a4)
{
  __int64 v8; // rax
  const void *v9; // rax
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T v12; // [rsp+40h] [rbp-38h]
  __int64 v13; // [rsp+90h] [rbp+18h] BYREF

  if ( !a3 )
  {
    TDebugOutputFunctor::operator()(a1, 1089, "hFileMapping is NULL.");
    return 2147942487LL;
  }
  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( (int)((__int64 (__fastcall *)(void *, _QWORD, __int128 *, __int64, __int64 *))pfnNtQuerySection)(
              a3,
              0,
              &v11,
              24,
              &v13) < 0 )
  {
    TDebugOutputFunctor::operator()(a1, 1089, "QuerySection on hFileMapping failed. hFileMapping = 0x%p.", a3);
    return 2147942487LL;
  }
  if ( (DWORD2(v11) & 0x14000000) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1089,
      "hFileMapping must be a committed memory region that is not uncached. hFileMapping = 0x%p, SEC_RESERVE = %u, SEC_NOCACHE = %u.",
      a3,
      (DWORD2(v11) >> 26) & 1,
      (DWORD2(v11) >> 28) & 1);
    return 2147942487LL;
  }
  v8 = (DWORD2(v11) & 0x80000) != 0 ? 0x10000LL : 4096LL;
  if ( (__int64)v12 < v8 )
    LODWORD(v8) = v12;
  v9 = MapViewOfFile(a3, 0xF001Fu, 0, 0, (unsigned int)v8);
  if ( !v9 )
  {
    TDebugOutputFunctor::operator()(a1, 1089, "hFileMapping must have CPU write access. hFileMapping = 0x%p.", a3);
    return 2147942487LL;
  }
  UnmapViewOfFile(v9);
  if ( v12 >= 0x100000000LL )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1089,
      "hFileMapping must be 4GiB or less. hFileMapping = 0x%p, allocation size = %Iu.",
      a3,
      v12);
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
  if ( a4 )
  {
    *(_QWORD *)a4 = v12;
    *((_DWORD *)a4 + 2) = 4;
    *((_DWORD *)a4 + 3) = (((DWORD2(v11) >> 30) & 1) == 0) | 2;
    *((_DWORD *)a4 + 4) = 1;
    *((_DWORD *)a4 + 5) = 1;
    *((_DWORD *)a4 + 6) = 1;
    *((_QWORD *)a4 + 4) = 0x10000;
    *((_DWORD *)a4 + 10) = 1057;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fdfc8  push    rbx
0x1800fdfca  push    rbp
0x1800fdfcb  push    rsi
0x1800fdfcc  push    rdi
0x1800fdfcd  sub     rsp, 58h
0x1800fdfd1  mov     rbx, r9
0x1800fdfd4  mov     rsi, r8
0x1800fdfd7  mov     rbp, rdx
0x1800fdfda  mov     rdi, rcx
0x1800fdfdd  test    r8, r8
0x1800fdfe0  jnz     short loc_1800FDFF8
0x1800fdfe2  lea     r8, aHfilemappingIs; "hFileMapping is NULL."
0x1800fdfe9  mov     edx, 441h
0x1800fdfee  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fdff3  jmp     loc_1800FE182
0x1800fdff8  mov     [rsp+78h+arg_10], 0
0x1800fe004  xorps   xmm0, xmm0
0x1800fe007  xor     eax, eax
0x1800fe009  movups  [rsp+78h+var_48], xmm0
0x1800fe00e  mov     [rsp+78h+var_38], rax
0x1800fe013  lea     rax, [rsp+78h+arg_10]
0x1800fe01b  mov     [rsp+78h+dwNumberOfBytesToMap], rax
0x1800fe020  mov     r9d, 18h
0x1800fe026  lea     r8, [rsp+78h+var_48]
0x1800fe02b  xor     edx, edx
0x1800fe02d  mov     rcx, rsi
0x1800fe030  mov     rax, cs:?pfnNtQuerySection@@3P6AJPEAXW4_SECTION_INFORMATION_CLASS@@0_KPEA_K@ZEA; long (*pfnNtQuerySection)(void *,_SECTION_INFORMATION_CLASS,void *,unsigned __int64,unsigned __int64 *)
0x1800fe037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe03c  test    eax, eax
0x1800fe03e  jns     short loc_1800FE04C
0x1800fe040  lea     r8, aQuerysectionOn; "QuerySection on hFileMapping failed. hF"...
0x1800fe047  jmp     loc_1800FE172
0x1800fe04c  mov     edx, dword ptr [rsp+78h+var_48+8]
0x1800fe050  test    edx, 14000000h
0x1800fe056  jz      short loc_1800FE08D
0x1800fe058  mov     eax, edx
0x1800fe05a  shr     eax, 1Ch
0x1800fe05d  mov     ecx, 1
0x1800fe062  and     eax, ecx
0x1800fe064  shr     edx, 1Ah
0x1800fe067  and     edx, ecx
0x1800fe069  mov     [rsp+78h+var_50], eax
0x1800fe06d  mov     dword ptr [rsp+78h+dwNumberOfBytesToMap], edx
0x1800fe071  mov     r9, rsi
0x1800fe074  lea     r8, aHfilemappingMu_0; "hFileMapping must be a committed memory"...
0x1800fe07b  mov     edx, 441h
0x1800fe080  mov     rcx, rdi
0x1800fe083  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe088  jmp     loc_1800FE182
0x1800fe08d  and     edx, 80000h
0x1800fe093  neg     edx
0x1800fe095  sbb     rax, rax
0x1800fe098  and     eax, 0F000h
0x1800fe09d  add     rax, 1000h
0x1800fe0a3  cmp     [rsp+78h+var_38], rax
0x1800fe0a8  cmovl   rax, [rsp+78h+var_38]
0x1800fe0ae  mov     eax, eax
0x1800fe0b0  mov     [rsp+78h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x1800fe0b5  xor     r9d, r9d; dwFileOffsetLow
0x1800fe0b8  xor     r8d, r8d; dwFileOffsetHigh
0x1800fe0bb  mov     edx, 0F001Fh; dwDesiredAccess
0x1800fe0c0  mov     rcx, rsi; hFileMappingObject
0x1800fe0c3  call    cs:__imp_MapViewOfFile
0x1800fe0c9  test    rax, rax
0x1800fe0cc  jz      loc_1800FE16B
0x1800fe0d2  mov     rcx, rax; lpBaseAddress
0x1800fe0d5  call    cs:__imp_UnmapViewOfFile
0x1800fe0db  mov     rcx, 100000000h
0x1800fe0e5  mov     rax, [rsp+78h+var_38]
0x1800fe0ea  cmp     rax, rcx
0x1800fe0ed  jb      short loc_1800FE10D
0x1800fe0ef  mov     [rsp+78h+dwNumberOfBytesToMap], rax
0x1800fe0f4  mov     r9, rsi
0x1800fe0f7  lea     r8, aHfilemappingMu_1; "hFileMapping must be 4GiB or less. hFil"...
0x1800fe0fe  mov     edx, 441h
0x1800fe103  mov     rcx, rdi
0x1800fe106  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe10b  jmp     short loc_1800FE182
0x1800fe10d  cmp     dword ptr [rbp+310h], 0
0x1800fe114  jnz     short loc_1800FE12A
0x1800fe116  lea     r8, aOpenexistinghe_2; "OpenExistingHeap is only supported when"...
0x1800fe11d  mov     edx, 458h
0x1800fe122  mov     rcx, rdi
0x1800fe125  jmp     loc_1800FDFEE
0x1800fe12a  test    rbx, rbx
0x1800fe12d  jz      short loc_1800FE167
0x1800fe12f  mov     [rbx], rax
0x1800fe132  mov     dword ptr [rbx+8], 4
0x1800fe139  mov     eax, dword ptr [rsp+78h+var_48+8]
0x1800fe13d  shr     eax, 1Eh
0x1800fe140  not     eax
0x1800fe142  mov     ecx, 1
0x1800fe147  and     eax, ecx
0x1800fe149  or      eax, 2
0x1800fe14c  mov     [rbx+0Ch], eax
0x1800fe14f  mov     [rbx+10h], ecx
0x1800fe152  mov     [rbx+14h], ecx
0x1800fe155  mov     [rbx+18h], ecx
0x1800fe158  mov     qword ptr [rbx+20h], 10000h
0x1800fe160  mov     dword ptr [rbx+28h], 421h
0x1800fe167  xor     eax, eax
0x1800fe169  jmp     short loc_1800FE187
0x1800fe16b  lea     r8, aHfilemappingMu; "hFileMapping must have CPU write access"...
0x1800fe172  mov     r9, rsi
0x1800fe175  mov     edx, 441h
0x1800fe17a  mov     rcx, rdi
0x1800fe17d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe182  mov     eax, 80070057h
0x1800fe187  add     rsp, 58h
0x1800fe18b  pop     rdi
0x1800fe18c  pop     rsi
0x1800fe18d  pop     rbp
0x1800fe18e  pop     rbx
0x1800fe18f  retn
```
