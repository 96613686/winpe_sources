# Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::~Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>(void)

- ea: `0x180023520`
- end: `0x18002359b`
- name: `??1?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@QEAA@XZ`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033a74`

## callees

- `0x180023520`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023575`

## pseudocode

```c
__int64 *__fastcall Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::~Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 *v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 *result; // rax

  v2 = a1 + 24;
  while ( 1 )
  {
    v3 = *(__int64 **)v2;
    if ( *(_QWORD *)v2 == v2 )
      break;
    if ( v3 )
    {
      v4 = (__int64 *)v3[1];
      v5 = *v3;
      *v4 = *v3;
      *(_QWORD *)(v5 + 8) = v4;
      *v3 = (__int64)v3;
      v3[1] = (__int64)v3;
      CoTaskMemFree(v3);
    }
  }
  while ( 1 )
  {
    v6 = *(_QWORD **)(a1 + 16);
    if ( !v6 )
      break;
    *(_QWORD *)(a1 + 16) = v6[2];
    CoTaskMemFree(v6);
  }
  CoTaskMemFree(*(LPVOID *)a1);
  v7 = *(_QWORD **)(v2 + 8);
  result = *(__int64 **)v2;
  *v7 = *(_QWORD *)v2;
  result[1] = (__int64)v7;
  *(_QWORD *)v2 = v2;
  *(_QWORD *)(v2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x180023520  mov     [rsp+arg_0], rbx
0x180023525  push    rdi
0x180023526  sub     rsp, 20h
0x18002352a  mov     rdi, rcx
0x18002352d  lea     rbx, [rcx+18h]
0x180023531  mov     rcx, [rbx]; pv
0x180023534  cmp     rcx, rbx
0x180023537  jz      short loc_180023569
0x180023539  test    rcx, rcx
0x18002353c  jz      short loc_180023531
0x18002353e  mov     rdx, [rcx+8]
0x180023542  mov     rax, [rcx]
0x180023545  mov     [rdx], rax
0x180023548  mov     [rax+8], rdx
0x18002354c  mov     [rcx], rcx
0x18002354f  mov     [rcx+8], rcx
0x180023553  call    cs:__imp_CoTaskMemFree
0x180023559  jmp     short loc_180023531
0x18002355b  mov     rax, [rcx+10h]
0x18002355f  mov     [rdi+10h], rax
0x180023563  call    cs:__imp_CoTaskMemFree
0x180023569  mov     rcx, [rdi+10h]; pv
0x18002356d  test    rcx, rcx
0x180023570  jnz     short loc_18002355B
0x180023572  mov     rcx, [rdi]; pv
0x180023575  call    cs:__imp_CoTaskMemFree
0x18002357b  mov     rcx, [rbx+8]
0x18002357f  mov     rax, [rbx]
0x180023582  mov     [rcx], rax
0x180023585  mov     [rax+8], rcx
0x180023589  mov     [rbx], rbx
0x18002358c  mov     [rbx+8], rbx
0x180023590  mov     rbx, [rsp+28h+arg_0]
0x180023595  add     rsp, 20h
0x180023599  pop     rdi
0x18002359a  retn
```
