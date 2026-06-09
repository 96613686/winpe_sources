# I_CRYPT_XML_HANDLE_FREE_DOC(_HXML_HANDLE *)

- ea: `0x180010bd0`
- end: `0x180010cbd`
- name: `?I_CRYPT_XML_HANDLE_FREE_DOC@@YAJPEAU_HXML_HANDLE@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct _HXML_HANDLE *lpMem)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004f60`
- `0x1800070d0`
- `0x180010bd0`
- `0x180010cd0`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180010ca3`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180010ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010c80`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010c80`

## string_xrefs

- `0x180010bed`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_HANDLE_FREE_DOC(struct _HXML_HANDLE *lpMem)
{
  void *v1; // rdi
  const char *v3; // rax
  int v4; // r10d
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rcx
  void *v8; // r8

  v1 = (void *)*((_QWORD *)lpMem + 6);
  if ( (int)I_CryptXmlWsStateUninitialize((__int64)lpMem) < 0 )
  {
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v4, v3, 53);
  }
  v5 = *((_QWORD *)lpMem + 17);
  if ( *(_QWORD *)(v5 + 32) && *(_DWORD *)(v5 + 24) )
  {
    v6 = 0;
    do
    {
      v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 32) + 8 * v6) + 8LL);
      if ( v7 )
        I_CryptXmlRelease(v7);
      v5 = *((_QWORD *)lpMem + 17);
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *(_DWORD *)(v5 + 24) );
  }
  v8 = (void *)*((_QWORD *)lpMem + 23);
  if ( v8 )
    HeapFree(v1, 0, v8);
  if ( *((int *)lpMem + 15) >= 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 8));
  HeapFree(v1, 0, lpMem);
  HeapDestroy(v1);
  return 0;
}

```

## disassembly

```asm
0x180010bd0  mov     [rsp+arg_8], rbx
0x180010bd5  push    rdi
0x180010bd6  sub     rsp, 20h
0x180010bda  mov     rdi, [rcx+30h]
0x180010bde  mov     rbx, rcx
0x180010be1  call    I_CryptXmlWsStateUninitialize
0x180010be6  mov     r10d, eax
0x180010be9  test    eax, eax
0x180010beb  jns     short loc_180010C11
0x180010bed  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010bf4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010bf9  mov     r8, rax
0x180010bfc  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010c03  mov     edx, r10d
0x180010c06  mov     r9d, 35h ; '5'
0x180010c0c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180010c11  mov     rax, [rbx+88h]
0x180010c18  cmp     qword ptr [rax+20h], 0
0x180010c1d  jz      short loc_180010C59
0x180010c1f  cmp     dword ptr [rax+18h], 0
0x180010c23  jbe     short loc_180010C59
0x180010c25  mov     [rsp+28h+arg_0], rsi
0x180010c2a  xor     esi, esi
0x180010c2c  nop     dword ptr [rax+00h]
0x180010c30  mov     rax, [rax+20h]
0x180010c34  mov     rcx, [rax+rsi*8]
0x180010c38  mov     rcx, [rcx+8]
0x180010c3c  test    rcx, rcx
0x180010c3f  jz      short loc_180010C46
0x180010c41  call    I_CryptXmlRelease
0x180010c46  mov     rax, [rbx+88h]
0x180010c4d  inc     esi
0x180010c4f  cmp     esi, [rax+18h]
0x180010c52  jb      short loc_180010C30
0x180010c54  mov     rsi, [rsp+28h+arg_0]
0x180010c59  mov     r8, [rbx+0B8h]; lpMem
0x180010c60  test    r8, r8
0x180010c63  jz      short loc_180010C76
0x180010c65  xor     edx, edx; dwFlags
0x180010c67  mov     rcx, rdi; hHeap
0x180010c6a  call    cs:__imp_HeapFree
0x180010c71  nop     dword ptr [rax+rax+00h]
0x180010c76  cmp     dword ptr [rbx+3Ch], 0
0x180010c7a  jl      short loc_180010C8C
0x180010c7c  lea     rcx, [rbx+8]; lpCriticalSection
0x180010c80  call    cs:__imp_DeleteCriticalSection
0x180010c87  nop     dword ptr [rax+rax+00h]
0x180010c8c  mov     r8, rbx; lpMem
0x180010c8f  xor     edx, edx; dwFlags
0x180010c91  mov     rcx, rdi; hHeap
0x180010c94  call    cs:__imp_HeapFree
0x180010c9b  nop     dword ptr [rax+rax+00h]
0x180010ca0  mov     rcx, rdi; hHeap
0x180010ca3  call    cs:__imp_HeapDestroy
0x180010caa  nop     dword ptr [rax+rax+00h]
0x180010caf  mov     rbx, [rsp+28h+arg_8]
0x180010cb4  xor     eax, eax
0x180010cb6  add     rsp, 20h
0x180010cba  pop     rdi
0x180010cbb  retn
```
