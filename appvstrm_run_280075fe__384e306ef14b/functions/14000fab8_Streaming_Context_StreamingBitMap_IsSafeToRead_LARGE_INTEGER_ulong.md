# Streaming::Context::StreamingBitMap::IsSafeToRead(_LARGE_INTEGER,ulong)

- ea: `0x14000fab8`
- end: `0x14000fb95`
- name: `?IsSafeToRead@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@K@Z`
- size: `221`
- prototype: `unsigned __int8 __fastcall(PRTL_BITMAP BitMapHeader, union _LARGE_INTEGER, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000984c`
- `0x140009d98`
- `0x14000af6c`

## callees

- `0x14000fab8`

## import_xrefs

- `ntoskrnl!RtlAreBitsSet` at `0x14000fb52`
- `ntoskrnl!RtlAreBitsSet` at `0x14000fb52`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fb7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fb7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fb6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fb6e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000fb34`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000fb34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fb1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fb1b`

## pseudocode

```c
BOOLEAN __fastcall Streaming::Context::StreamingBitMap::IsSafeToRead(
        PRTL_BITMAP BitMapHeader,
        union _LARGE_INTEGER a2,
        unsigned int a3)
{
  __int128 QuadPart; // rax
  ULONG SizeOfBitMap; // esi
  __int64 v6; // rbp
  __int128 v7; // rax
  unsigned int v8; // eax
  bool v9; // bl
  BOOLEAN v10; // si
  struct _ERESOURCE *v11; // rcx

  QuadPart = a2.QuadPart;
  SizeOfBitMap = BitMapHeader[2].SizeOfBitMap;
  v6 = (__int64)(WORD4(QuadPart) + (_QWORD)QuadPart) >> 16;
  v7 = (__int64)((unsigned __int16)(WORD4(QuadPart) + QuadPart) - (unsigned __int64)WORD4(QuadPart) + a3);
  v8 = ((unsigned __int16)(WORD4(v7) + v7) != (unsigned __int64)WORD4(v7))
     + (unsigned int)((__int64)(WORD4(v7) + (_QWORD)v7) >> 16);
  if ( v8 <= SizeOfBitMap )
    SizeOfBitMap = v8;
  v9 = 0;
  if ( *(_QWORD *)&BitMapHeader[3].SizeOfBitMap )
  {
    KeEnterCriticalRegion();
    v9 = ExAcquireResourceSharedLite(*(PERESOURCE *)&BitMapHeader[3].SizeOfBitMap, 1u) == 1;
  }
  v10 = RtlAreBitsSet(BitMapHeader, v6, SizeOfBitMap);
  if ( v9 )
  {
    v11 = *(struct _ERESOURCE **)&BitMapHeader[3].SizeOfBitMap;
    if ( v11 )
    {
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14000fab8  push    rbx
0x14000faba  push    rbp
0x14000fabb  push    rsi
0x14000fabc  push    rdi
0x14000fabd  push    r14
0x14000fabf  sub     rsp, 20h
0x14000fac3  mov     rax, rdx
0x14000fac6  mov     rdi, rcx
0x14000fac9  cqo
0x14000facb  mov     ecx, 0FFFFh
0x14000fad0  and     rdx, rcx
0x14000fad3  add     rax, rdx
0x14000fad6  mov     esi, [rdi+20h]
0x14000fad9  mov     rbp, rax
0x14000fadc  and     rax, rcx
0x14000fadf  sar     rbp, 10h
0x14000fae3  sub     rax, rdx
0x14000fae6  mov     rdx, rax
0x14000fae9  mov     eax, r8d
0x14000faec  add     rax, rdx
0x14000faef  cqo
0x14000faf1  and     rdx, rcx
0x14000faf4  add     rax, rdx
0x14000faf7  mov     r8, rax
0x14000fafa  and     rax, rcx
0x14000fafd  xor     ecx, ecx
0x14000faff  sar     r8, 10h
0x14000fb03  cmp     rax, rdx
0x14000fb06  setnz   cl
0x14000fb09  lea     eax, [rcx+r8]
0x14000fb0d  cmp     eax, esi
0x14000fb0f  cmovbe  esi, eax
0x14000fb12  xor     bl, bl
0x14000fb14  cmp     qword ptr [rdi+30h], 0
0x14000fb19  jz      short loc_14000FB4A
0x14000fb1b  call    cs:__imp_KeEnterCriticalRegion
0x14000fb22  nop     dword ptr [rax+rax+00h]
0x14000fb27  mov     rcx, [rdi+30h]; Resource
0x14000fb2b  mov     r14d, 1
0x14000fb31  mov     dl, r14b; Wait
0x14000fb34  call    cs:__imp_ExAcquireResourceSharedLite
0x14000fb3b  nop     dword ptr [rax+rax+00h]
0x14000fb40  cmp     al, r14b
0x14000fb43  movzx   ebx, bl
0x14000fb46  cmovz   ebx, r14d
0x14000fb4a  mov     r8d, esi; Length
0x14000fb4d  mov     edx, ebp; StartingIndex
0x14000fb4f  mov     rcx, rdi; BitMapHeader
0x14000fb52  call    cs:__imp_RtlAreBitsSet
0x14000fb59  nop     dword ptr [rax+rax+00h]
0x14000fb5e  mov     sil, al
0x14000fb61  test    bl, bl
0x14000fb63  jz      short loc_14000FB86
0x14000fb65  mov     rcx, [rdi+30h]; Resource
0x14000fb69  test    rcx, rcx
0x14000fb6c  jz      short loc_14000FB86
0x14000fb6e  call    cs:__imp_ExReleaseResourceLite
0x14000fb75  nop     dword ptr [rax+rax+00h]
0x14000fb7a  call    cs:__imp_KeLeaveCriticalRegion
0x14000fb81  nop     dword ptr [rax+rax+00h]
0x14000fb86  mov     al, sil
0x14000fb89  add     rsp, 20h
0x14000fb8d  pop     r14
0x14000fb8f  pop     rdi
0x14000fb90  pop     rsi
0x14000fb91  pop     rbp
0x14000fb92  pop     rbx
0x14000fb93  retn
```
