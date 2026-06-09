# BfeObjectSecurityRelease

- ea: `0x18002aef0`
- end: `0x18002aff4`
- name: `BfeObjectSecurityRelease`
- size: `260`
- prototype: `__int64 __fastcall(LPCVOID lpMem)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010360`
- `0x180012be0`
- `0x18002add8`
- `0x18002ae3c`
- `0x180069888`

## callees

- `0x18002aef0`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18002af2d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002af2d`
- `ntdll!RtlExpandHashTable` at `0x18002afb7`
- `ntdll!RtlExpandHashTable` at `0x18002afb7`
- `ntdll!RtlContractHashTable` at `0x18002af98`
- `ntdll!RtlContractHashTable` at `0x18002af98`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002afe0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002afe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002af6c`

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
      RtlRemoveEntryHashTable(&qword_1800F2AB0, lpMem, 0);
      v5 = dword_1800F2AC4;
      v6 = (unsigned int)(3 * dword_1800F2AB8);
      if ( dword_1800F2AC4 > (unsigned int)v6 )
      {
        do
        {
          if ( !(unsigned __int8)RtlExpandHashTable(&qword_1800F2AB0) )
            break;
          v6 = (unsigned int)(3 * dword_1800F2AB8);
        }
        while ( v5 > (unsigned int)v6 );
      }
      else if ( dword_1800F2AC4 < (unsigned int)dword_1800F2AB8 )
      {
        while ( (unsigned __int8)RtlContractHashTable(&qword_1800F2AB0) && v5 < dword_1800F2AB8 )
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
0x18002aef0  test    rcx, rcx
0x18002aef3  jz      locret_18002AF84
0x18002aef9  push    rbx
0x18002aefa  sub     rsp, 40h
0x18002aefe  mov     rax, cs:__security_cookie
0x18002af05  xor     rax, rsp
0x18002af08  mov     [rsp+48h+var_18], rax
0x18002af0d  sub     dword ptr [rcx+18h], 1
0x18002af11  mov     rbx, rcx
0x18002af14  mov     [rsp+48h+var_20], rcx
0x18002af19  jnz     short loc_18002AF72
0x18002af1b  mov     rdx, rcx
0x18002af1e  mov     [rsp+48h+arg_8], rdi
0x18002af23  lea     rcx, qword_1800F2AB0
0x18002af2a  xor     r8d, r8d
0x18002af2d  call    cs:__imp_RtlRemoveEntryHashTable
0x18002af33  mov     eax, cs:dword_1800F2AB8
0x18002af39  mov     edi, cs:dword_1800F2AC4
0x18002af3f  lea     ecx, [rax+rax*2]
0x18002af42  cmp     edi, ecx
0x18002af44  ja      short loc_18002AFB0
0x18002af46  cmp     edi, eax
0x18002af48  jb      short loc_18002AF91
0x18002af4a  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18002af4f  mov     rdi, [rsp+48h+arg_8]
0x18002af54  test    eax, eax
0x18002af56  jnz     short loc_18002AF85
0x18002af58  cmp     cs:gWfpTrackHeapBytes, eax
0x18002af5e  jnz     short loc_18002AFD4
0x18002af60  mov     rcx, cs:gWfpHeap; hHeap
0x18002af67  mov     r8, rbx; lpMem
0x18002af6a  xor     edx, edx; dwFlags
0x18002af6c  call    cs:__imp_HeapFree
0x18002af72  mov     rcx, [rsp+48h+var_18]
0x18002af77  xor     rcx, rsp; StackCookie
0x18002af7a  call    __security_check_cookie
0x18002af7f  add     rsp, 40h
0x18002af83  pop     rbx
0x18002af84  retn
0x18002af85  lea     rcx, [rsp+48h+var_20]
0x18002af8a  call    WfpMemFree25B
0x18002af8f  jmp     short loc_18002AF72
0x18002af91  lea     rcx, qword_1800F2AB0
0x18002af98  call    cs:__imp_RtlContractHashTable
0x18002af9e  test    al, al
0x18002afa0  jz      short loc_18002AF4A
0x18002afa2  cmp     edi, cs:dword_1800F2AB8
0x18002afa8  jb      short loc_18002AF91
0x18002afaa  jmp     short loc_18002AF4A
0x18002afb0  lea     rcx, qword_1800F2AB0
0x18002afb7  call    cs:__imp_RtlExpandHashTable
0x18002afbd  test    al, al
0x18002afbf  jz      short loc_18002AF4A
0x18002afc1  mov     eax, cs:dword_1800F2AB8
0x18002afc7  lea     ecx, [rax+rax*2]
0x18002afca  cmp     edi, ecx
0x18002afcc  jbe     loc_18002AF4A
0x18002afd2  jmp     short loc_18002AFB0
0x18002afd4  mov     rcx, cs:gWfpHeap; hHeap
0x18002afdb  mov     r8, rbx; lpMem
0x18002afde  xor     edx, edx; dwFlags
0x18002afe0  call    cs:__imp_HeapSize
0x18002afe6  neg     eax
0x18002afe8  lock add cs:gWfpHeapBytesAllocated, eax
0x18002afef  jmp     loc_18002AF60
```
