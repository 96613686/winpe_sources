# GetPackagePathForMoniker

- ea: `0x180018f50`
- end: `0x1800190b3`
- name: `GetPackagePathForMoniker`
- size: `355`
- prototype: `__int64 __fastcall(PCWSTR packageFullName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016e28`

## callees

- `0x180018f50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001905e`
- `ntdll!RtlFreeHeap` at `0x1800190a5`
- `ntdll!RtlFreeHeap` at `0x18001905e`
- `ntdll!RtlFreeHeap` at `0x1800190a5`
- `ntdll!RtlAllocateHeap` at `0x180018fa4`
- `ntdll!RtlAllocateHeap` at `0x180019016`
- `ntdll!RtlAllocateHeap` at `0x180018fa4`
- `ntdll!RtlAllocateHeap` at `0x180019016`
- `KERNELBASE!PackageIdFromFullName` at `0x180018f79`
- `KERNELBASE!PackageIdFromFullName` at `0x180018fcb`
- `KERNELBASE!PackageIdFromFullName` at `0x180018f79`
- `KERNELBASE!PackageIdFromFullName` at `0x180018fcb`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180018fec`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180019035`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180018fec`
- `KERNELBASE!GetStagedPackagePathByFullName` at `0x180019035`

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
0x180018f50  mov     rax, rsp
0x180018f53  mov     [rax+8], rbx
0x180018f57  mov     [rax+10h], rbp
0x180018f5b  push    rsi
0x180018f5c  push    rdi
0x180018f5d  push    r14
0x180018f5f  sub     rsp, 20h
0x180018f63  mov     r14, rdx
0x180018f66  mov     dword ptr [rax+18h], 0
0x180018f6d  xor     edx, edx; flags
0x180018f6f  lea     r8, [rax+18h]; bufferLength
0x180018f73  xor     r9d, r9d; buffer
0x180018f76  mov     rsi, rcx
0x180018f79  call    cs:__imp_PackageIdFromFullName
0x180018f80  nop     dword ptr [rax+rax+00h]
0x180018f85  mov     ebx, eax
0x180018f87  cmp     eax, 7Ah ; 'z'
0x180018f8a  jnz     loc_18001906F
0x180018f90  mov     rcx, gs:60h
0x180018f99  xor     edx, edx; Flags
0x180018f9b  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180018fa0  mov     rcx, [rcx+30h]; HeapHandle
0x180018fa4  call    cs:__imp_RtlAllocateHeap
0x180018fab  nop     dword ptr [rax+rax+00h]
0x180018fb0  mov     rbp, rax
0x180018fb3  test    rax, rax
0x180018fb6  jz      loc_180019085
0x180018fbc  mov     r9, rax; buffer
0x180018fbf  lea     r8, [rsp+38h+Size]; bufferLength
0x180018fc4  xor     edx, edx; flags
0x180018fc6  mov     rcx, rsi; packageFullName
0x180018fc9  xor     edi, edi
0x180018fcb  call    cs:__imp_PackageIdFromFullName
0x180018fd2  nop     dword ptr [rax+rax+00h]
0x180018fd7  mov     ebx, eax
0x180018fd9  test    eax, eax
0x180018fdb  jnz     short loc_18001904C
0x180018fdd  xor     r8d, r8d; path
0x180018fe0  mov     dword ptr [rsp+38h+Size], edi
0x180018fe4  lea     rdx, [rsp+38h+Size]; pathLength
0x180018fe9  mov     rcx, rsi; packageFullName
0x180018fec  call    cs:__imp_GetStagedPackagePathByFullName
0x180018ff3  nop     dword ptr [rax+rax+00h]
0x180018ff8  mov     ebx, eax
0x180018ffa  cmp     eax, 7Ah ; 'z'
0x180018ffd  jnz     short loc_18001904C
0x180018fff  mov     rcx, gs:60h
0x180019008  xor     edx, edx; Flags
0x18001900a  mov     r8d, dword ptr [rsp+38h+Size]
0x18001900f  add     r8, r8; Size
0x180019012  mov     rcx, [rcx+30h]; HeapHandle
0x180019016  call    cs:__imp_RtlAllocateHeap
0x18001901d  nop     dword ptr [rax+rax+00h]
0x180019022  mov     rdi, rax
0x180019025  test    rax, rax
0x180019028  jz      short loc_18001908C
0x18001902a  mov     r8, rax; path
0x18001902d  lea     rdx, [rsp+38h+Size]; pathLength
0x180019032  mov     rcx, rsi; packageFullName
0x180019035  call    cs:__imp_GetStagedPackagePathByFullName
0x18001903c  nop     dword ptr [rax+rax+00h]
0x180019041  mov     ebx, eax
0x180019043  test    eax, eax
0x180019045  jnz     short loc_18001904C
0x180019047  mov     [r14], rdi
0x18001904a  xor     edi, edi
0x18001904c  mov     rcx, gs:60h
0x180019055  mov     r8, rbp; P
0x180019058  xor     edx, edx; Flags
0x18001905a  mov     rcx, [rcx+30h]; HeapHandle
0x18001905e  call    cs:__imp_RtlFreeHeap
0x180019065  nop     dword ptr [rax+rax+00h]
0x18001906a  test    rdi, rdi
0x18001906d  jnz     short loc_180019093
0x18001906f  mov     rbp, [rsp+38h+arg_8]
0x180019074  mov     eax, ebx
0x180019076  mov     rbx, [rsp+38h+arg_0]
0x18001907b  add     rsp, 20h
0x18001907f  pop     r14
0x180019081  pop     rdi
0x180019082  pop     rsi
0x180019083  retn
0x180019085  mov     ebx, 8
0x18001908a  jmp     short loc_18001906F
0x18001908c  mov     ebx, 8
0x180019091  jmp     short loc_18001904C
0x180019093  mov     rcx, gs:60h
0x18001909c  mov     r8, rdi; P
0x18001909f  xor     edx, edx; Flags
0x1800190a1  mov     rcx, [rcx+30h]; HeapHandle
0x1800190a5  call    cs:__imp_RtlFreeHeap
0x1800190ac  nop     dword ptr [rax+rax+00h]
0x1800190b1  jmp     short loc_18001906F
```
