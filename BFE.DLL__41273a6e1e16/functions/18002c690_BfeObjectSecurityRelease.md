# BfeObjectSecurityRelease

- ea: `0x18002c690`
- end: `0x18002c7b7`
- name: `BfeObjectSecurityRelease`
- size: `295`
- prototype: `__int64 __fastcall(LPCVOID lpMem)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010d60`
- `0x180013640`
- `0x18002c574`
- `0x18002c5dc`
- `0x18006be5c`

## callees

- `0x18002c690`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18002c6cd`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002c6cd`
- `ntdll!RtlExpandHashTable` at `0x18002c76a`
- `ntdll!RtlExpandHashTable` at `0x18002c76a`
- `ntdll!RtlContractHashTable` at `0x18002c749`
- `ntdll!RtlContractHashTable` at `0x18002c749`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002c79d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002c79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c716`

## pseudocode

```c
void __fastcall BfeObjectSecurityRelease(_DWORD *lpMem)
{
  bool v1; // zf
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // edi
  __int64 v6; // rcx
  _DWORD *v7; // [rsp+28h] [rbp-20h] BYREF

  if ( lpMem )
  {
    v1 = lpMem[6]-- == 1;
    v7 = lpMem;
    if ( v1 )
    {
      RtlRemoveEntryHashTable(&qword_1800F5AD0, lpMem, 0);
      v5 = dword_1800F5AE4;
      v6 = (unsigned int)(3 * dword_1800F5AD8);
      if ( dword_1800F5AE4 > (unsigned int)v6 )
      {
        do
        {
          if ( !(unsigned __int8)RtlExpandHashTable(&qword_1800F5AD0) )
            break;
          v6 = (unsigned int)(3 * dword_1800F5AD8);
        }
        while ( v5 > (unsigned int)v6 );
      }
      else if ( dword_1800F5AE4 < (unsigned int)dword_1800F5AD8 )
      {
        while ( (unsigned __int8)RtlContractHashTable(&qword_1800F5AD0) && v5 < dword_1800F5AD8 )
          ;
      }
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v6, v3, v4) )
      {
        WfpMemFree25B(&v7);
      }
      else
      {
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, lpMem));
        HeapFree(gWfpHeap, 0, lpMem);
      }
    }
  }
}

```

## disassembly

```asm
0x18002c690  test    rcx, rcx
0x18002c693  jz      locret_18002C734
0x18002c699  push    rbx
0x18002c69a  sub     rsp, 40h
0x18002c69e  mov     rax, cs:__security_cookie
0x18002c6a5  xor     rax, rsp
0x18002c6a8  mov     [rsp+48h+var_18], rax
0x18002c6ad  sub     dword ptr [rcx+18h], 1
0x18002c6b1  mov     rbx, rcx
0x18002c6b4  mov     [rsp+48h+var_20], rcx
0x18002c6b9  jnz     short loc_18002C722
0x18002c6bb  mov     rdx, rcx
0x18002c6be  mov     [rsp+48h+arg_8], rdi
0x18002c6c3  lea     rcx, qword_1800F5AD0
0x18002c6ca  xor     r8d, r8d
0x18002c6cd  call    cs:__imp_RtlRemoveEntryHashTable
0x18002c6d4  nop     dword ptr [rax+rax+00h]
0x18002c6d9  mov     eax, cs:dword_1800F5AD8
0x18002c6df  mov     edi, cs:dword_1800F5AE4
0x18002c6e5  lea     ecx, [rax+rax*2]
0x18002c6e8  cmp     edi, ecx
0x18002c6ea  ja      short loc_18002C763
0x18002c6ec  cmp     edi, eax
0x18002c6ee  jb      short loc_18002C742
0x18002c6f0  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18002c6f5  mov     rdi, [rsp+48h+arg_8]
0x18002c6fa  test    eax, eax
0x18002c6fc  jnz     short loc_18002C736
0x18002c6fe  cmp     cs:gWfpTrackHeapBytes, eax
0x18002c704  jnz     loc_18002C791
0x18002c70a  mov     rcx, cs:gWfpHeap; hHeap
0x18002c711  mov     r8, rbx; lpMem
0x18002c714  xor     edx, edx; dwFlags
0x18002c716  call    cs:__imp_HeapFree
0x18002c71d  nop     dword ptr [rax+rax+00h]
0x18002c722  mov     rcx, [rsp+48h+var_18]
0x18002c727  xor     rcx, rsp; StackCookie
0x18002c72a  call    __security_check_cookie
0x18002c72f  add     rsp, 40h
0x18002c733  pop     rbx
0x18002c734  retn
0x18002c736  lea     rcx, [rsp+48h+var_20]
0x18002c73b  call    WfpMemFree25B
0x18002c740  jmp     short loc_18002C722
0x18002c742  lea     rcx, qword_1800F5AD0
0x18002c749  call    cs:__imp_RtlContractHashTable
0x18002c750  nop     dword ptr [rax+rax+00h]
0x18002c755  test    al, al
0x18002c757  jz      short loc_18002C6F0
0x18002c759  cmp     edi, cs:dword_1800F5AD8
0x18002c75f  jb      short loc_18002C742
0x18002c761  jmp     short loc_18002C6F0
0x18002c763  lea     rcx, qword_1800F5AD0
0x18002c76a  call    cs:__imp_RtlExpandHashTable
0x18002c771  nop     dword ptr [rax+rax+00h]
0x18002c776  test    al, al
0x18002c778  jz      loc_18002C6F0
0x18002c77e  mov     eax, cs:dword_1800F5AD8
0x18002c784  lea     ecx, [rax+rax*2]
0x18002c787  cmp     edi, ecx
0x18002c789  jbe     loc_18002C6F0
0x18002c78f  jmp     short loc_18002C763
0x18002c791  mov     rcx, cs:gWfpHeap; hHeap
0x18002c798  mov     r8, rbx; lpMem
0x18002c79b  xor     edx, edx; dwFlags
0x18002c79d  call    cs:__imp_HeapSize
0x18002c7a4  nop     dword ptr [rax+rax+00h]
0x18002c7a9  neg     eax
0x18002c7ab  lock add cs:gWfpHeapBytesAllocated, eax
0x18002c7b2  jmp     loc_18002C70A
```
