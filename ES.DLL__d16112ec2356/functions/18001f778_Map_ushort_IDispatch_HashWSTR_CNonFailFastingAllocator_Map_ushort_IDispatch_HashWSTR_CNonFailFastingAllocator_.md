# Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::~Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>(void)

- ea: `0x18001f778`
- end: `0x18001f7e2`
- name: `??1?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f494`

## callees

- `0x18001f778`
- `0x180026684`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7bc`

## pseudocode

```c
_QWORD *__fastcall Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::~Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>(
        __int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *result; // rax

  v2 = (_QWORD *)(a1 + 24);
  while ( 1 )
  {
    v3 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    if ( v3 )
      Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::`scalar deleting destructor'(v3, 1);
  }
  while ( 1 )
  {
    v4 = *(_QWORD **)(a1 + 16);
    if ( !v4 )
      break;
    *(_QWORD *)(a1 + 16) = v4[2];
    CoTaskMemFree(v4);
  }
  CoTaskMemFree(*(LPVOID *)a1);
  v5 = (_QWORD *)v2[1];
  result = (_QWORD *)*v2;
  *v5 = *v2;
  result[1] = v5;
  *v2 = v2;
  v2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x18001f778  mov     [rsp+arg_0], rbx
0x18001f77d  push    rdi
0x18001f77e  sub     rsp, 20h
0x18001f782  mov     rdi, rcx
0x18001f785  lea     rbx, [rcx+18h]
0x18001f789  mov     rcx, [rbx]
0x18001f78c  cmp     rcx, rbx
0x18001f78f  jz      short loc_18001F7B0
0x18001f791  test    rcx, rcx
0x18001f794  jz      short loc_18001F789
0x18001f796  mov     edx, 1
0x18001f79b  call    ??_GAssoc@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAAPEAXI@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::`scalar deleting destructor'(uint)
0x18001f7a0  jmp     short loc_18001F789
0x18001f7a2  mov     rax, [rcx+10h]
0x18001f7a6  mov     [rdi+10h], rax
0x18001f7aa  call    cs:__imp_CoTaskMemFree
0x18001f7b0  mov     rcx, [rdi+10h]; pv
0x18001f7b4  test    rcx, rcx
0x18001f7b7  jnz     short loc_18001F7A2
0x18001f7b9  mov     rcx, [rdi]; pv
0x18001f7bc  call    cs:__imp_CoTaskMemFree
0x18001f7c2  mov     rcx, [rbx+8]
0x18001f7c6  mov     rax, [rbx]
0x18001f7c9  mov     [rcx], rax
0x18001f7cc  mov     [rax+8], rcx
0x18001f7d0  mov     [rbx], rbx
0x18001f7d3  mov     [rbx+8], rbx
0x18001f7d7  mov     rbx, [rsp+28h+arg_0]
0x18001f7dc  add     rsp, 20h
0x18001f7e0  pop     rdi
0x18001f7e1  retn
```
