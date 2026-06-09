# TxfFreeTopsRange

- ea: `0x140100b64`
- end: `0x140100e82`
- name: `TxfFreeTopsRange`
- size: `798`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140039038`
- `0x14010ae4c`
- `0x14029b00c`

## callees

- `0x140100b64`
- `0x14020bbc0`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x140100d59`
- `ntoskrnl!RtlClearBits` at `0x140100dac`
- `ntoskrnl!RtlClearBits` at `0x140100d59`
- `ntoskrnl!RtlClearBits` at `0x140100dac`
- `ntoskrnl!CcPinRead` at `0x140100cc6`
- `ntoskrnl!CcPinRead` at `0x140100cc6`
- `ntoskrnl!CcPurgeCacheSection` at `0x140100c8d`
- `ntoskrnl!CcPurgeCacheSection` at `0x140100c8d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140100e5b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140100e5b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140100df6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140100df6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d40`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d93`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d40`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d93`
- `ntoskrnl!CcUnpinData` at `0x140100cfe`
- `ntoskrnl!CcUnpinData` at `0x140100cfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d23`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100dc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d23`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100dc9`
- `ntoskrnl!CcFlushCache` at `0x140100cee`
- `ntoskrnl!CcFlushCache` at `0x140100cee`

## pseudocode

```c
char __fastcall TxfFreeTopsRange(__int64 a1, __int64 a2, unsigned __int64 *a3, unsigned int a4, unsigned int a5)
{
  unsigned int v6; // r14d
  __int64 v8; // r13
  unsigned __int64 v10; // r15
  ULONG v11; // esi
  __int64 v12; // r8
  char result; // al
  unsigned __int64 v14; // r8
  const signed __int64 **v15; // r9
  unsigned __int64 v16; // rdx
  ULONG v17; // ebx
  int v18; // ebx
  __int64 i; // rcx
  _QWORD *v20; // rdx
  ULONG v21; // r8d
  PVOID Buffer; // [rsp+30h] [rbp-10h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+80h] [rbp+40h] BYREF
  PVOID Bcb; // [rsp+90h] [rbp+50h] BYREF

  v6 = a5;
  v8 = a4;
  v10 = *a3 >> 12;
  Bcb = 0;
  Buffer = 0;
  FileOffset.QuadPart = 0;
  v11 = (a4 + 4095) >> 12;
  if ( (a5 & 1) != 0 )
  {
    a5 &= 0x10u;
    if ( (v6 & 0x10) == 0 )
    {
      v12 = v6 >> 3;
      LOBYTE(v12) = (v6 & 8) != 0;
      result = NtfsAcquireScbPagingResourceExclusive(0, *(_QWORD *)(a1 + 280), v12);
      if ( !result )
        return result;
    }
    v14 = *a3;
    v15 = (const signed __int64 **)(a1 + 344);
    v16 = (*a3 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    if ( v16 == *a3 )
    {
      v16 = *a3;
    }
    else if ( !_bittest64(*v15, (unsigned int)(v10 - 1)) )
    {
      v16 = v14 & 0xFFFFFFFFFFFFF000uLL;
    }
    FileOffset.QuadPart = v16;
    if ( ((v14 + v8) & 0xFFFFFFFFFFFFF000uLL) == v14 + v8 )
    {
      v17 = v8 + *(_DWORD *)a3 - v16;
    }
    else
    {
      v18 = v8 + *(_DWORD *)a3;
      if ( !_bittest64(*v15, (unsigned int)v10 + v11) )
        v18 += 4095;
      v17 = (v18 & 0xFFFFF000) - FileOffset.LowPart;
    }
    if ( v17 )
    {
      CcPurgeCacheSection(
        (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 288LL) + 16LL),
        &FileOffset,
        v17,
        0);
      CcPinRead(*(PFILE_OBJECT *)(*(_QWORD *)(a1 + 280) + 280LL), &FileOffset, v17, 5u, &Bcb, &Buffer);
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 288LL) + 16LL), &FileOffset, v17, 0);
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    if ( !a5 )
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a1 + 280) + 16LL));
    if ( (v6 & 0x20) == 0 )
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
    RtlClearBits((PRTL_BITMAP)(a1 + 336), v10, v11);
    if ( (v6 & 0x20) == 0 )
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
  }
  if ( (v6 & 2) != 0 )
  {
    if ( (v6 & 0x20) == 0 )
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
    RtlClearBits((PRTL_BITMAP)(a1 + 304), v10, v11);
    *(_DWORD *)(a1 + 300) += v11;
    if ( (v6 & 0x20) == 0 )
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
  }
  if ( (v6 & 4) != 0 && *(_QWORD *)(a2 + 296) )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
    for ( i = *(_QWORD *)(a2 + 296); i; i = *(_QWORD *)(i + 24) )
    {
      v20 = *(_QWORD **)(a2 + 296);
      v21 = (unsigned __int64)v11 <= v20[1] ? v11 : *((_DWORD *)v20 + 2);
      if ( *v20 )
        *(_QWORD *)(*v20 + 16LL) -= (unsigned __int64)v21 << 12;
      *(_QWORD *)(*(_QWORD *)(a2 + 296) + 8LL) -= v21;
      v11 -= v21;
      if ( !v11 )
        break;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
  }
  return 1;
}

```

## disassembly

```asm
0x140100b64  mov     [rsp-38h+arg_8], rbx
0x140100b69  push    rbp
0x140100b6a  push    rsi
0x140100b6b  push    rdi
0x140100b6c  push    r12
0x140100b6e  push    r13
0x140100b70  push    r14
0x140100b72  push    r15
0x140100b74  mov     rbp, rsp
0x140100b77  sub     rsp, 40h
0x140100b7b  mov     r15, [r8]
0x140100b7e  mov     rbx, r8
0x140100b81  mov     r14d, [rbp+arg_20]
0x140100b85  mov     r12, rdx
0x140100b88  mov     r13d, r9d
0x140100b8b  mov     rdi, rcx
0x140100b8e  shr     r15, 0Ch
0x140100b92  mov     [rbp+arg_10], 0
0x140100b9a  mov     [rbp+var_10], 0
0x140100ba2  lea     esi, [r13+0FFFh]
0x140100ba9  mov     qword ptr [rbp+FileOffset], 0
0x140100bb1  shr     esi, 0Ch
0x140100bb4  test    r14b, 1
0x140100bb8  jz      loc_140100D7C
0x140100bbe  mov     eax, r14d
0x140100bc1  and     eax, 10h
0x140100bc4  mov     [rbp+arg_20], eax
0x140100bc7  jnz     short loc_140100BEA
0x140100bc9  mov     rdx, [rcx+118h]
0x140100bd0  mov     r8d, r14d
0x140100bd3  shr     r8d, 3
0x140100bd7  xor     ecx, ecx
0x140100bd9  and     r8b, 1
0x140100bdd  call    NtfsAcquireScbPagingResourceExclusive
0x140100be2  test    al, al
0x140100be4  jz      loc_140100E69
0x140100bea  mov     r8, [rbx]
0x140100bed  lea     r9, [rdi+158h]
0x140100bf4  mov     r10, 0FFFFFFFFFFFFF000h
0x140100bfb  lea     rdx, [r8+0FFFh]
0x140100c02  and     rdx, r10
0x140100c05  cmp     rdx, r8
0x140100c08  jnz     short loc_140100C0F
0x140100c0a  mov     rdx, r8
0x140100c0d  jmp     short loc_140100C27
0x140100c0f  mov     rax, [r9]
0x140100c12  lea     ecx, [r15-1]
0x140100c16  bt      [rax], rcx
0x140100c1a  setb    al
0x140100c1d  test    al, al
0x140100c1f  jnz     short loc_140100C27
0x140100c21  mov     rdx, r8
0x140100c24  and     rdx, r10
0x140100c27  lea     rcx, [r8+r13]
0x140100c2b  mov     qword ptr [rbp+FileOffset], rdx
0x140100c2f  mov     rax, rcx
0x140100c32  and     rax, r10
0x140100c35  cmp     rax, rcx
0x140100c38  jnz     short loc_140100C43
0x140100c3a  mov     ebx, [rbx]
0x140100c3c  sub     ebx, edx
0x140100c3e  add     ebx, r13d
0x140100c41  jmp     short loc_140100C69
0x140100c43  mov     rax, [r9]
0x140100c46  lea     ecx, [r15+rsi]
0x140100c4a  bt      [rax], rcx
0x140100c4e  mov     ebx, [rbx]
0x140100c50  setb    cl
0x140100c53  add     ebx, r13d
0x140100c56  test    cl, cl
0x140100c58  jnz     short loc_140100C60
0x140100c5a  add     ebx, 0FFFh
0x140100c60  and     ebx, 0FFFFF000h
0x140100c66  sub     ebx, dword ptr [rbp+FileOffset]
0x140100c69  test    ebx, ebx
0x140100c6b  jz      loc_140100D12
0x140100c71  mov     rax, [rdi+118h]
0x140100c78  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100c7c  xor     r9d, r9d; Flags
0x140100c7f  mov     r8d, ebx; Length
0x140100c82  mov     rcx, [rax+120h]
0x140100c89  add     rcx, 10h; SectionObjectPointer
0x140100c8d  call    cs:__imp_CcPurgeCacheSection
0x140100c94  nop     dword ptr [rax+rax+00h]
0x140100c99  mov     rcx, [rdi+118h]
0x140100ca0  lea     rax, [rbp+var_10]
0x140100ca4  mov     [rsp+40h+Buffer], rax; Buffer
0x140100ca9  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100cad  lea     rax, [rbp+arg_10]
0x140100cb1  mov     r9d, 5; Flags
0x140100cb7  mov     r8d, ebx; Length
0x140100cba  mov     [rsp+40h+Bcb], rax; Bcb
0x140100cbf  mov     rcx, [rcx+118h]; FileObject
0x140100cc6  call    cs:__imp_CcPinRead
0x140100ccd  nop     dword ptr [rax+rax+00h]
0x140100cd2  mov     rax, [rdi+118h]
0x140100cd9  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100cdd  xor     r9d, r9d; IoStatus
0x140100ce0  mov     r8d, ebx; Length
0x140100ce3  mov     rcx, [rax+120h]
0x140100cea  add     rcx, 10h; SectionObjectPointer
0x140100cee  call    cs:__imp_CcFlushCache
0x140100cf5  nop     dword ptr [rax+rax+00h]
0x140100cfa  mov     rcx, [rbp+arg_10]; Bcb
0x140100cfe  call    cs:__imp_CcUnpinData
0x140100d05  nop     dword ptr [rax+rax+00h]
0x140100d0a  mov     [rbp+arg_10], 0
0x140100d12  cmp     [rbp+arg_20], 0
0x140100d16  jnz     short loc_140100D2F
0x140100d18  mov     rcx, [rdi+118h]
0x140100d1f  mov     rcx, [rcx+10h]; Resource
0x140100d23  call    cs:__imp_ExReleaseResourceLite
0x140100d2a  nop     dword ptr [rax+rax+00h]
0x140100d2f  mov     ebx, r14d
0x140100d32  and     ebx, 20h
0x140100d35  jnz     short loc_140100D4C
0x140100d37  mov     rcx, [rdi+170h]; Resource
0x140100d3e  mov     dl, 1; Wait
0x140100d40  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140100d47  nop     dword ptr [rax+rax+00h]
0x140100d4c  mov     r8d, esi; NumberToClear
0x140100d4f  lea     rcx, [rdi+150h]; BitMapHeader
0x140100d56  mov     edx, r15d; StartingIndex
0x140100d59  call    cs:__imp_RtlClearBits
0x140100d60  nop     dword ptr [rax+rax+00h]
0x140100d65  test    ebx, ebx
0x140100d67  jnz     short loc_140100D7C
0x140100d69  mov     rcx, [rdi+170h]; Resource
0x140100d70  call    cs:__imp_ExReleaseResourceLite
0x140100d77  nop     dword ptr [rax+rax+00h]
0x140100d7c  test    r14b, 2
0x140100d80  jz      short loc_140100DD5
0x140100d82  mov     ebx, r14d
0x140100d85  and     ebx, 20h
0x140100d88  jnz     short loc_140100D9F
0x140100d8a  mov     rcx, [rdi+170h]; Resource
0x140100d91  mov     dl, 1; Wait
0x140100d93  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140100d9a  nop     dword ptr [rax+rax+00h]
0x140100d9f  lea     rcx, [rdi+130h]; BitMapHeader
0x140100da6  mov     r8d, esi; NumberToClear
0x140100da9  mov     edx, r15d; StartingIndex
0x140100dac  call    cs:__imp_RtlClearBits
0x140100db3  nop     dword ptr [rax+rax+00h]
0x140100db8  add     [rdi+12Ch], esi
0x140100dbe  test    ebx, ebx
0x140100dc0  jnz     short loc_140100DD5
0x140100dc2  mov     rcx, [rdi+170h]; Resource
0x140100dc9  call    cs:__imp_ExReleaseResourceLite
0x140100dd0  nop     dword ptr [rax+rax+00h]
0x140100dd5  test    r14b, 4
0x140100dd9  jz      loc_140100E67
0x140100ddf  cmp     qword ptr [r12+128h], 0
0x140100de8  jz      short loc_140100E67
0x140100dea  mov     rcx, [rdi+10h]
0x140100dee  mov     ebx, 18A8h
0x140100df3  add     rcx, rbx; FastMutex
0x140100df6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140100dfd  nop     dword ptr [rax+rax+00h]
0x140100e02  mov     rcx, [r12+128h]
0x140100e0a  jmp     short loc_140100E4F
0x140100e0c  mov     rdx, [r12+128h]
0x140100e14  mov     eax, esi
0x140100e16  cmp     rax, [rdx+8]
0x140100e1a  jbe     short loc_140100E22
0x140100e1c  mov     r8d, [rdx+8]
0x140100e20  jmp     short loc_140100E25
0x140100e22  mov     r8d, esi
0x140100e25  mov     r9, [rdx]
0x140100e28  mov     edx, r8d
0x140100e2b  test    r9, r9
0x140100e2e  jz      short loc_140100E3A
0x140100e30  mov     eax, edx
0x140100e32  shl     rax, 0Ch
0x140100e36  sub     [r9+10h], rax
0x140100e3a  mov     rax, [r12+128h]
0x140100e42  sub     [rax+8], rdx
0x140100e46  sub     esi, r8d
0x140100e49  jz      short loc_140100E54
0x140100e4b  mov     rcx, [rcx+18h]
0x140100e4f  test    rcx, rcx
0x140100e52  jnz     short loc_140100E0C
0x140100e54  mov     rcx, [rdi+10h]
0x140100e58  add     rcx, rbx; FastMutex
0x140100e5b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140100e62  nop     dword ptr [rax+rax+00h]
0x140100e67  mov     al, 1
0x140100e69  mov     rbx, [rsp+40h+arg_8]
0x140100e71  add     rsp, 40h
0x140100e75  pop     r15
0x140100e77  pop     r14
0x140100e79  pop     r13
0x140100e7b  pop     r12
0x140100e7d  pop     rdi
0x140100e7e  pop     rsi
0x140100e7f  pop     rbp
0x140100e80  retn
```
