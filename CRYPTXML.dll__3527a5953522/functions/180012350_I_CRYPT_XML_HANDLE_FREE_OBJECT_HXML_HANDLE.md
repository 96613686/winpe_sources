# I_CRYPT_XML_HANDLE_FREE_OBJECT(_HXML_HANDLE *)

- ea: `0x180012350`
- end: `0x180012419`
- name: `?I_CRYPT_XML_HANDLE_FREE_OBJECT@@YAJPEAU_HXML_HANDLE@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct _HXML_HANDLE *lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004f60`
- `0x180012350`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800123ff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800123eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800123eb`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_HANDLE_FREE_OBJECT(struct _HXML_HANDLE *lpMem)
{
  __int64 v1; // r8
  void *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rcx
  void *v6; // r8

  v1 = *((_QWORD *)lpMem + 17);
  v3 = (void *)*((_QWORD *)lpMem + 6);
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 40) )
    {
      v4 = 0;
      do
      {
        v5 = *(_QWORD *)(*(_QWORD *)(v1 + 48) + 8 * v4);
        if ( v5 )
          I_CryptXmlRelease(*(_QWORD *)(v5 + 8));
        v1 = *((_QWORD *)lpMem + 17);
        v4 = (unsigned int)(v4 + 1);
      }
      while ( (unsigned int)v4 < *(_DWORD *)(v1 + 40) );
      HeapFree(v3, 0, *(LPVOID *)(v1 + 48));
    }
    if ( (*((_DWORD *)lpMem + 40) & 1) != 0 )
    {
      v6 = (void *)*((_QWORD *)lpMem + 19);
      if ( v6 )
        HeapFree(v3, 0, v6);
    }
  }
  if ( *((int *)lpMem + 15) >= 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 8));
  HeapFree(v3, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x180012350  mov     [rsp+arg_8], rbx
0x180012355  push    rdi
0x180012356  sub     rsp, 20h
0x18001235a  mov     r8, [rcx+88h]
0x180012361  mov     rbx, rcx
0x180012364  mov     rdi, [rcx+30h]
0x180012368  test    r8, r8
0x18001236b  jz      short loc_1800123E1
0x18001236d  cmp     dword ptr [r8+28h], 0
0x180012372  jbe     short loc_1800123BA
0x180012374  mov     [rsp+28h+arg_0], rsi
0x180012379  xor     esi, esi
0x18001237b  mov     rax, [r8+30h]
0x18001237f  mov     rcx, [rax+rsi*8]
0x180012383  test    rcx, rcx
0x180012386  jz      short loc_180012391
0x180012388  mov     rcx, [rcx+8]
0x18001238c  call    I_CryptXmlRelease
0x180012391  mov     r8, [rbx+88h]
0x180012398  inc     esi
0x18001239a  cmp     esi, [r8+28h]
0x18001239e  jb      short loc_18001237B
0x1800123a0  mov     r8, [r8+30h]; lpMem
0x1800123a4  xor     edx, edx; dwFlags
0x1800123a6  mov     rsi, [rsp+28h+arg_0]
0x1800123ab  mov     rcx, rdi; hHeap
0x1800123ae  call    cs:__imp_HeapFree
0x1800123b5  nop     dword ptr [rax+rax+00h]
0x1800123ba  mov     eax, [rbx+0A0h]
0x1800123c0  test    al, 1
0x1800123c2  jz      short loc_1800123E1
0x1800123c4  mov     r8, [rbx+98h]; lpMem
0x1800123cb  test    r8, r8
0x1800123ce  jz      short loc_1800123E1
0x1800123d0  xor     edx, edx; dwFlags
0x1800123d2  mov     rcx, rdi; hHeap
0x1800123d5  call    cs:__imp_HeapFree
0x1800123dc  nop     dword ptr [rax+rax+00h]
0x1800123e1  cmp     dword ptr [rbx+3Ch], 0
0x1800123e5  jl      short loc_1800123F7
0x1800123e7  lea     rcx, [rbx+8]; lpCriticalSection
0x1800123eb  call    cs:__imp_DeleteCriticalSection
0x1800123f2  nop     dword ptr [rax+rax+00h]
0x1800123f7  mov     r8, rbx; lpMem
0x1800123fa  xor     edx, edx; dwFlags
0x1800123fc  mov     rcx, rdi; hHeap
0x1800123ff  call    cs:__imp_HeapFree
0x180012406  nop     dword ptr [rax+rax+00h]
0x18001240b  mov     rbx, [rsp+28h+arg_8]
0x180012410  xor     eax, eax
0x180012412  add     rsp, 20h
0x180012416  pop     rdi
0x180012417  retn
```
