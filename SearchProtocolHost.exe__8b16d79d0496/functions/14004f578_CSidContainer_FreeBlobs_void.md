# CSidContainer::FreeBlobs(void)

- ea: `0x14004f578`
- end: `0x14004f5e1`
- name: `?FreeBlobs@CSidContainer@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CSidContainer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140022d38`

## callees

- `0x14004f578`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004f5a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004f5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004f5a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004f5c4`

## pseudocode

```c
void __fastcall CSidContainer::FreeBlobs(CSidContainer *this)
{
  unsigned int v2; // edi
  __int64 v3; // rbp
  __int64 v4; // rsi
  void *v5; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    v2 = 0;
    do
    {
      v3 = *(_QWORD *)this;
      v4 = 2LL * v2;
      v5 = *(void **)(*(_QWORD *)this + 16LL * v2 + 8);
      if ( v5 )
        CoTaskMemFree(v5);
      ++v2;
      *(_QWORD *)(v3 + 8 * v4 + 8) = 0;
      *(_DWORD *)(v3 + 8 * v4) = 0;
    }
    while ( v2 < *((_DWORD *)this + 2) );
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x14004f578  push    rbx
0x14004f57a  push    rbp
0x14004f57b  push    rsi
0x14004f57c  push    rdi
0x14004f57d  sub     rsp, 28h
0x14004f581  mov     eax, [rcx+8]
0x14004f584  mov     rbx, rcx
0x14004f587  test    eax, eax
0x14004f589  jz      short loc_14004F5D8
0x14004f58b  xor     edi, edi
0x14004f58d  test    eax, eax
0x14004f58f  jz      short loc_14004F5C1
0x14004f591  mov     rbp, [rbx]
0x14004f594  mov     esi, edi
0x14004f596  add     rsi, rsi
0x14004f599  mov     rcx, [rbp+rsi*8+8]; pv
0x14004f59e  test    rcx, rcx
0x14004f5a1  jz      short loc_14004F5A9
0x14004f5a3  call    cs:__imp_CoTaskMemFree
0x14004f5a9  inc     edi
0x14004f5ab  mov     qword ptr [rbp+rsi*8+8], 0
0x14004f5b4  mov     dword ptr [rbp+rsi*8+0], 0
0x14004f5bc  cmp     edi, [rbx+8]
0x14004f5bf  jb      short loc_14004F591
0x14004f5c1  mov     rcx, [rbx]; pv
0x14004f5c4  call    cs:__imp_CoTaskMemFree
0x14004f5ca  mov     qword ptr [rbx], 0
0x14004f5d1  mov     dword ptr [rbx+8], 0
0x14004f5d8  add     rsp, 28h
0x14004f5dc  pop     rdi
0x14004f5dd  pop     rsi
0x14004f5de  pop     rbp
0x14004f5df  pop     rbx
0x14004f5e0  retn
```
