# CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(void)

- ea: `0x180025f00`
- end: `0x180025f8a`
- name: `??1?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ`
- size: `138`
- prototype: `int __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180026824`
- `0x180029140`
- `0x18002a3c4`
- `0x18002aed4`
- `0x18002bae0`
- `0x18002c9fc`

## callees

- `0x180025f00`
- `0x1800293a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f6c`

## pseudocode

```c
int __fastcall CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(
        __int64 a1)
{
  void *v2; // rsi
  int v3; // edi
  HANDLE ProcessHeap; // rax
  int result; // eax
  void *v6; // rdi
  HANDLE v7; // rax

  if ( *(_DWORD *)a1 )
  {
    v2 = *(void **)(a1 + 8);
    v3 = 0;
    if ( *(int *)(a1 + 4) <= 0 )
      v3 = *(_DWORD *)(a1 + 4);
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = v3;
    *(_DWORD *)a1 = 0;
  }
  result = CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = *(void **)(a1 + 8);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    result = HeapFree(v7, 0, v6);
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025f00  mov     [rsp+arg_0], rbx
0x180025f05  mov     [rsp+arg_8], rsi
0x180025f0a  push    rdi
0x180025f0b  sub     rsp, 20h
0x180025f0f  cmp     dword ptr [rcx], 0
0x180025f12  mov     rbx, rcx
0x180025f15  jz      short loc_180025F4E
0x180025f17  mov     rsi, [rcx+8]
0x180025f1b  xor     edi, edi
0x180025f1d  cmp     [rcx+4], edi
0x180025f20  cmovle  edi, [rcx+4]
0x180025f24  test    rsi, rsi
0x180025f27  jz      short loc_180025F3D
0x180025f29  call    cs:__imp_GetProcessHeap
0x180025f2f  mov     r8, rsi; lpMem
0x180025f32  xor     edx, edx; dwFlags
0x180025f34  mov     rcx, rax; hHeap
0x180025f37  call    cs:__imp_HeapFree
0x180025f3d  mov     qword ptr [rbx+8], 0
0x180025f45  mov     [rbx+4], edi
0x180025f48  mov     dword ptr [rbx], 0
0x180025f4e  xor     ecx, ecx
0x180025f50  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180025f55  mov     rdi, [rbx+8]
0x180025f59  test    rdi, rdi
0x180025f5c  jz      short loc_180025F7A
0x180025f5e  call    cs:__imp_GetProcessHeap
0x180025f64  mov     r8, rdi; lpMem
0x180025f67  xor     edx, edx; dwFlags
0x180025f69  mov     rcx, rax; hHeap
0x180025f6c  call    cs:__imp_HeapFree
0x180025f72  mov     qword ptr [rbx+8], 0
0x180025f7a  mov     rbx, [rsp+28h+arg_0]
0x180025f7f  mov     rsi, [rsp+28h+arg_8]
0x180025f84  add     rsp, 20h
0x180025f88  pop     rdi
0x180025f89  retn
```
