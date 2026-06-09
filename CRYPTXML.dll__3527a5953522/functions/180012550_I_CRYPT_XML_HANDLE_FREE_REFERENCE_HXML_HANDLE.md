# I_CRYPT_XML_HANDLE_FREE_REFERENCE(_HXML_HANDLE *)

- ea: `0x180012550`
- end: `0x180012599`
- name: `?I_CRYPT_XML_HANDLE_FREE_REFERENCE@@YAJPEAU_HXML_HANDLE@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(struct _HXML_HANDLE *lpMem)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180012550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001257f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001257f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001256b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001256b`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_HANDLE_FREE_REFERENCE(struct _HXML_HANDLE *lpMem)
{
  void *v2; // rdi

  v2 = (void *)*((_QWORD *)lpMem + 6);
  if ( *((int *)lpMem + 15) >= 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 8));
  HeapFree(v2, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x180012550  mov     [rsp+arg_0], rbx
0x180012555  push    rdi
0x180012556  sub     rsp, 20h
0x18001255a  cmp     dword ptr [rcx+3Ch], 0
0x18001255e  mov     rbx, rcx
0x180012561  mov     rdi, [rcx+30h]
0x180012565  jl      short loc_180012577
0x180012567  add     rcx, 8; lpCriticalSection
0x18001256b  call    cs:__imp_DeleteCriticalSection
0x180012572  nop     dword ptr [rax+rax+00h]
0x180012577  mov     r8, rbx; lpMem
0x18001257a  xor     edx, edx; dwFlags
0x18001257c  mov     rcx, rdi; hHeap
0x18001257f  call    cs:__imp_HeapFree
0x180012586  nop     dword ptr [rax+rax+00h]
0x18001258b  mov     rbx, [rsp+28h+arg_0]
0x180012590  xor     eax, eax
0x180012592  add     rsp, 20h
0x180012596  pop     rdi
0x180012597  retn
```
