# I_CRYPT_XML_HANDLE_FREE_SIGNATURE(_HXML_HANDLE *)

- ea: `0x18000fcc0`
- end: `0x18000fe42`
- name: `?I_CRYPT_XML_HANDLE_FREE_SIGNATURE@@YAJPEAU_HXML_HANDLE@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct _HXML_HANDLE *lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004f60`
- `0x18000fcc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fe14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fe14`
- `bcrypt!BCryptDestroyKey` at `0x18000fcf6`
- `bcrypt!BCryptDestroyKey` at `0x18000fcf6`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_HANDLE_FREE_SIGNATURE(struct _HXML_HANDLE *lpMem)
{
  __int64 v1; // rax
  void *v3; // rdi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // r8
  __int64 v7; // r8
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rcx

  v1 = *((_QWORD *)lpMem + 18);
  v3 = (void *)*((_QWORD *)lpMem + 6);
  if ( v1 )
  {
    v4 = *(_QWORD *)(v1 + 152);
    if ( v4 )
    {
      v5 = *(void **)(v4 + 32);
      if ( v5 )
        BCryptDestroyKey(v5);
      HeapFree(v3, 0, *(LPVOID *)(*((_QWORD *)lpMem + 18) + 152LL));
    }
    v6 = *(void **)(*((_QWORD *)lpMem + 18) + 128LL);
    if ( v6 )
      HeapFree(v3, 0, v6);
    v7 = *((_QWORD *)lpMem + 18);
    if ( *(_QWORD *)(v7 + 112) )
    {
      if ( *(_DWORD *)(v7 + 104) )
      {
        v8 = 0;
        do
        {
          v9 = *(_QWORD *)(*(_QWORD *)(v7 + 112) + 8 * v8);
          if ( v9 )
          {
            v10 = *(_QWORD *)(v9 + 8);
            if ( v10 )
              I_CryptXmlRelease(v10);
          }
          v7 = *((_QWORD *)lpMem + 18);
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (unsigned int)v8 < *(_DWORD *)(v7 + 104) );
      }
      HeapFree(v3, 0, *(LPVOID *)(v7 + 112));
    }
    v11 = *((_QWORD *)lpMem + 18);
    if ( *(_QWORD *)(v11 + 168) )
    {
      if ( *(_DWORD *)(v11 + 160) )
      {
        v12 = 0;
        do
        {
          v13 = *(_QWORD *)(*(_QWORD *)(v11 + 168) + 8 * v12);
          if ( v13 )
          {
            v14 = *(_QWORD *)(v13 + 8);
            if ( v14 )
              I_CryptXmlRelease(v14);
          }
          v11 = *((_QWORD *)lpMem + 18);
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < *(_DWORD *)(v11 + 160) );
      }
      HeapFree(v3, 0, *(LPVOID *)(v11 + 168));
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
0x18000fcc0  mov     [rsp+arg_8], rbx
0x18000fcc5  push    rdi
0x18000fcc6  sub     rsp, 20h
0x18000fcca  mov     rax, [rcx+90h]
0x18000fcd1  mov     rbx, rcx
0x18000fcd4  mov     rdi, [rcx+30h]
0x18000fcd8  test    rax, rax
0x18000fcdb  jz      loc_18000FE0A
0x18000fce1  mov     rcx, [rax+98h]
0x18000fce8  test    rcx, rcx
0x18000fceb  jz      short loc_18000FD21
0x18000fced  mov     rcx, [rcx+20h]; hKey
0x18000fcf1  test    rcx, rcx
0x18000fcf4  jz      short loc_18000FD02
0x18000fcf6  call    cs:__imp_BCryptDestroyKey
0x18000fcfd  nop     dword ptr [rax+rax+00h]
0x18000fd02  mov     r8, [rbx+90h]
0x18000fd09  xor     edx, edx; dwFlags
0x18000fd0b  mov     rcx, rdi; hHeap
0x18000fd0e  mov     r8, [r8+98h]; lpMem
0x18000fd15  call    cs:__imp_HeapFree
0x18000fd1c  nop     dword ptr [rax+rax+00h]
0x18000fd21  mov     rax, [rbx+90h]
0x18000fd28  mov     r8, [rax+80h]; lpMem
0x18000fd2f  test    r8, r8
0x18000fd32  jz      short loc_18000FD45
0x18000fd34  xor     edx, edx; dwFlags
0x18000fd36  mov     rcx, rdi; hHeap
0x18000fd39  call    cs:__imp_HeapFree
0x18000fd40  nop     dword ptr [rax+rax+00h]
0x18000fd45  mov     r8, [rbx+90h]
0x18000fd4c  mov     [rsp+28h+arg_0], rsi
0x18000fd51  cmp     qword ptr [r8+70h], 0
0x18000fd56  jz      short loc_18000FDA0
0x18000fd58  cmp     dword ptr [r8+68h], 0
0x18000fd5d  jbe     short loc_18000FD8B
0x18000fd5f  xor     esi, esi
0x18000fd61  mov     rax, [r8+70h]
0x18000fd65  mov     rdx, [rax+rsi*8]
0x18000fd69  test    rdx, rdx
0x18000fd6c  jz      short loc_18000FD7C
0x18000fd6e  mov     rcx, [rdx+8]
0x18000fd72  test    rcx, rcx
0x18000fd75  jz      short loc_18000FD7C
0x18000fd77  call    I_CryptXmlRelease
0x18000fd7c  mov     r8, [rbx+90h]
0x18000fd83  inc     esi
0x18000fd85  cmp     esi, [r8+68h]
0x18000fd89  jb      short loc_18000FD61
0x18000fd8b  mov     r8, [r8+70h]; lpMem
0x18000fd8f  xor     edx, edx; dwFlags
0x18000fd91  mov     rcx, rdi; hHeap
0x18000fd94  call    cs:__imp_HeapFree
0x18000fd9b  nop     dword ptr [rax+rax+00h]
0x18000fda0  mov     r8, [rbx+90h]
0x18000fda7  cmp     qword ptr [r8+0A8h], 0
0x18000fdaf  jz      short loc_18000FE05
0x18000fdb1  cmp     dword ptr [r8+0A0h], 0
0x18000fdb9  jbe     short loc_18000FDED
0x18000fdbb  xor     esi, esi
0x18000fdbd  mov     rax, [r8+0A8h]
0x18000fdc4  mov     rdx, [rax+rsi*8]
0x18000fdc8  test    rdx, rdx
0x18000fdcb  jz      short loc_18000FDDB
0x18000fdcd  mov     rcx, [rdx+8]
0x18000fdd1  test    rcx, rcx
0x18000fdd4  jz      short loc_18000FDDB
0x18000fdd6  call    I_CryptXmlRelease
0x18000fddb  mov     r8, [rbx+90h]
0x18000fde2  inc     esi
0x18000fde4  cmp     esi, [r8+0A0h]
0x18000fdeb  jb      short loc_18000FDBD
0x18000fded  mov     r8, [r8+0A8h]; lpMem
0x18000fdf4  xor     edx, edx; dwFlags
0x18000fdf6  mov     rcx, rdi; hHeap
0x18000fdf9  call    cs:__imp_HeapFree
0x18000fe00  nop     dword ptr [rax+rax+00h]
0x18000fe05  mov     rsi, [rsp+28h+arg_0]
0x18000fe0a  cmp     dword ptr [rbx+3Ch], 0
0x18000fe0e  jl      short loc_18000FE20
0x18000fe10  lea     rcx, [rbx+8]; lpCriticalSection
0x18000fe14  call    cs:__imp_DeleteCriticalSection
0x18000fe1b  nop     dword ptr [rax+rax+00h]
0x18000fe20  mov     r8, rbx; lpMem
0x18000fe23  xor     edx, edx; dwFlags
0x18000fe25  mov     rcx, rdi; hHeap
0x18000fe28  call    cs:__imp_HeapFree
0x18000fe2f  nop     dword ptr [rax+rax+00h]
0x18000fe34  mov     rbx, [rsp+28h+arg_8]
0x18000fe39  xor     eax, eax
0x18000fe3b  add     rsp, 20h
0x18000fe3f  pop     rdi
0x18000fe40  retn
```
