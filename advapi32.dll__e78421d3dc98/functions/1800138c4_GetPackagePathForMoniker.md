# GetPackagePathForMoniker

- ea: `0x1800138c4`
- end: `0x1800139f6`
- name: `GetPackagePathForMoniker`
- size: `306`
- prototype: `__int64 __fastcall(PCWSTR packageFullName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800118c0`

## callees

- `0x1800138c4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800139ae`
- `ntdll!RtlFreeHeap` at `0x1800139ee`
- `ntdll!RtlFreeHeap` at `0x1800139ae`
- `ntdll!RtlFreeHeap` at `0x1800139ee`
- `ntdll!RtlAllocateHeap` at `0x180013912`
- `ntdll!RtlAllocateHeap` at `0x180013972`
- `ntdll!RtlAllocateHeap` at `0x180013912`
- `ntdll!RtlAllocateHeap` at `0x180013972`
- `KERNELBASE!PackageIdFromFullName` at `0x1800138ed`
- `KERNELBASE!PackageIdFromFullName` at `0x180013933`
- `KERNELBASE!PackageIdFromFullName` at `0x1800138ed`
- `KERNELBASE!PackageIdFromFullName` at `0x180013933`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x18001394e`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x18001398b`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x18001394e`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x18001398b`

## pseudocode

```c
__int64 __fastcall GetPackagePathForMoniker(PCWSTR packageFullName, WCHAR **a2)
{
  unsigned int StagedPackagePathByFullName; // ebx
  BYTE *Heap; // rax
  BYTE *v6; // rbp
  WCHAR *v7; // rdi
  WCHAR *v8; // rax
  SIZE_T Size; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  StagedPackagePathByFullName = PackageIdFromFullName(packageFullName, 0, (UINT32 *)&Size, 0);
  if ( StagedPackagePathByFullName == 122 )
  {
    Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    v6 = Heap;
    if ( Heap )
    {
      v7 = 0;
      StagedPackagePathByFullName = PackageIdFromFullName(packageFullName, 0, (UINT32 *)&Size, Heap);
      if ( !StagedPackagePathByFullName )
      {
        LODWORD(Size) = 0;
        StagedPackagePathByFullName = GetStagedPackagePathByFullName(packageFullName, (UINT32 *)&Size, 0);
        if ( StagedPackagePathByFullName == 122 )
        {
          v8 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (unsigned int)Size);
          v7 = v8;
          if ( v8 )
          {
            StagedPackagePathByFullName = GetStagedPackagePathByFullName(packageFullName, (UINT32 *)&Size, v8);
            if ( !StagedPackagePathByFullName )
            {
              *a2 = v7;
              v7 = 0;
            }
          }
          else
          {
            StagedPackagePathByFullName = 8;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      if ( v7 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    }
    else
    {
      return 8;
    }
  }
  return StagedPackagePathByFullName;
}

```

## disassembly

```asm
0x1800138c4  mov     rax, rsp
0x1800138c7  mov     [rax+8], rbx
0x1800138cb  mov     [rax+10h], rbp
0x1800138cf  push    rsi
0x1800138d0  push    rdi
0x1800138d1  push    r14
0x1800138d3  sub     rsp, 20h
0x1800138d7  mov     r14, rdx
0x1800138da  mov     dword ptr [rax+18h], 0
0x1800138e1  xor     edx, edx; flags
0x1800138e3  lea     r8, [rax+18h]; bufferLength
0x1800138e7  xor     r9d, r9d; buffer
0x1800138ea  mov     rsi, rcx
0x1800138ed  call    cs:__imp_PackageIdFromFullName
0x1800138f3  mov     ebx, eax
0x1800138f5  cmp     eax, 7Ah ; 'z'
0x1800138f8  jnz     loc_1800139B9
0x1800138fe  mov     rcx, gs:60h
0x180013907  xor     edx, edx; Flags
0x180013909  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x18001390e  mov     rcx, [rcx+30h]; HeapHandle
0x180013912  call    cs:__imp_RtlAllocateHeap
0x180013918  mov     rbp, rax
0x18001391b  test    rax, rax
0x18001391e  jz      loc_1800139CE
0x180013924  mov     r9, rax; buffer
0x180013927  lea     r8, [rsp+38h+Size]; bufferLength
0x18001392c  xor     edx, edx; flags
0x18001392e  mov     rcx, rsi; packageFullName
0x180013931  xor     edi, edi
0x180013933  call    cs:__imp_PackageIdFromFullName
0x180013939  mov     ebx, eax
0x18001393b  test    eax, eax
0x18001393d  jnz     short loc_18001399C
0x18001393f  xor     r8d, r8d; path
0x180013942  mov     dword ptr [rsp+38h+Size], edi
0x180013946  lea     rdx, [rsp+38h+Size]; pathLength
0x18001394b  mov     rcx, rsi; packageFullName
0x18001394e  call    cs:__imp_GetStagedPackagePathByFullName
0x180013954  mov     ebx, eax
0x180013956  cmp     eax, 7Ah ; 'z'
0x180013959  jnz     short loc_18001399C
0x18001395b  mov     rcx, gs:60h
0x180013964  xor     edx, edx; Flags
0x180013966  mov     r8d, dword ptr [rsp+38h+Size]
0x18001396b  add     r8, r8; Size
0x18001396e  mov     rcx, [rcx+30h]; HeapHandle
0x180013972  call    cs:__imp_RtlAllocateHeap
0x180013978  mov     rdi, rax
0x18001397b  test    rax, rax
0x18001397e  jz      short loc_1800139D5
0x180013980  mov     r8, rax; path
0x180013983  lea     rdx, [rsp+38h+Size]; pathLength
0x180013988  mov     rcx, rsi; packageFullName
0x18001398b  call    cs:__imp_GetStagedPackagePathByFullName
0x180013991  mov     ebx, eax
0x180013993  test    eax, eax
0x180013995  jnz     short loc_18001399C
0x180013997  mov     [r14], rdi
0x18001399a  xor     edi, edi
0x18001399c  mov     rcx, gs:60h
0x1800139a5  mov     r8, rbp; P
0x1800139a8  xor     edx, edx; Flags
0x1800139aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800139ae  call    cs:__imp_RtlFreeHeap
0x1800139b4  test    rdi, rdi
0x1800139b7  jnz     short loc_1800139DC
0x1800139b9  mov     rbp, [rsp+38h+arg_8]
0x1800139be  mov     eax, ebx
0x1800139c0  mov     rbx, [rsp+38h+arg_0]
0x1800139c5  add     rsp, 20h
0x1800139c9  pop     r14
0x1800139cb  pop     rdi
0x1800139cc  pop     rsi
0x1800139cd  retn
0x1800139ce  mov     ebx, 8
0x1800139d3  jmp     short loc_1800139B9
0x1800139d5  mov     ebx, 8
0x1800139da  jmp     short loc_18001399C
0x1800139dc  mov     rcx, gs:60h
0x1800139e5  mov     r8, rdi; P
0x1800139e8  xor     edx, edx; Flags
0x1800139ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800139ee  call    cs:__imp_RtlFreeHeap
0x1800139f4  jmp     short loc_1800139B9
```
