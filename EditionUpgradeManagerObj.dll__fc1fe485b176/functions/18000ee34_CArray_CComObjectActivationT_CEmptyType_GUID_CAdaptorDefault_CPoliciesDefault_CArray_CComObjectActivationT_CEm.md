# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)

- ea: `0x18000ee34`
- end: `0x18000eebe`
- name: `??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ`
- size: `138`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ef08`
- `0x180012af4`

## callees

- `0x180009480`
- `0x18000ee34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee92`

## pseudocode

```c
int __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(
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
0x18000ee34  mov     [rsp+arg_0], rbx
0x18000ee39  mov     [rsp+arg_8], rsi
0x18000ee3e  push    rdi
0x18000ee3f  sub     rsp, 20h
0x18000ee43  cmp     dword ptr [rcx], 0
0x18000ee46  mov     rbx, rcx
0x18000ee49  jz      short loc_18000EE82
0x18000ee4b  mov     rsi, [rcx+8]
0x18000ee4f  xor     edi, edi
0x18000ee51  cmp     [rcx+4], edi
0x18000ee54  cmovle  edi, [rcx+4]
0x18000ee58  test    rsi, rsi
0x18000ee5b  jz      short loc_18000EE71
0x18000ee5d  call    cs:__imp_GetProcessHeap
0x18000ee63  mov     r8, rsi; lpMem
0x18000ee66  xor     edx, edx; dwFlags
0x18000ee68  mov     rcx, rax; hHeap
0x18000ee6b  call    cs:__imp_HeapFree
0x18000ee71  mov     qword ptr [rbx+8], 0
0x18000ee79  mov     [rbx+4], edi
0x18000ee7c  mov     dword ptr [rbx], 0
0x18000ee82  xor     ecx, ecx
0x18000ee84  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ee89  mov     rdi, [rbx+8]
0x18000ee8d  test    rdi, rdi
0x18000ee90  jz      short loc_18000EEAE
0x18000ee92  call    cs:__imp_GetProcessHeap
0x18000ee98  mov     r8, rdi; lpMem
0x18000ee9b  xor     edx, edx; dwFlags
0x18000ee9d  mov     rcx, rax; hHeap
0x18000eea0  call    cs:__imp_HeapFree
0x18000eea6  mov     qword ptr [rbx+8], 0
0x18000eeae  mov     rbx, [rsp+28h+arg_0]
0x18000eeb3  mov     rsi, [rsp+28h+arg_8]
0x18000eeb8  add     rsp, 20h
0x18000eebc  pop     rdi
0x18000eebd  retn
```
