# ??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x18000cb5c`
- end: `0x18000cbac`
- name: `??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011bef`
- `0x180011c4f`

## callees

- `0x18000cb5c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb9c`

## pseudocode

```c
void __fastcall __1__unique_struct_U__co_array_t_PEAUIMVKey____P6AXPEAU1___E_1_FreeMvKeyArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  _QWORD *v1; // rdi
  unsigned int v2; // esi
  __int64 i; // rbx
  __int64 v4; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
    {
      v4 = v1[i];
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        v1[i] = 0;
      }
    }
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x18000cb5c  push    rbx
0x18000cb5e  push    rbp
0x18000cb5f  push    rsi
0x18000cb60  push    rdi
0x18000cb61  sub     rsp, 28h
0x18000cb65  mov     rdi, [rcx]
0x18000cb68  test    rdi, rdi
0x18000cb6b  jz      short loc_18000CBA3
0x18000cb6d  mov     esi, [rcx+8]
0x18000cb70  xor     ebx, ebx
0x18000cb72  test    esi, esi
0x18000cb74  jz      short loc_18000CB99
0x18000cb76  mov     rcx, [rdi+rbx*8]
0x18000cb7a  test    rcx, rcx
0x18000cb7d  jz      short loc_18000CB93
0x18000cb7f  mov     rax, [rcx]
0x18000cb82  mov     rax, [rax+10h]
0x18000cb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb8b  mov     qword ptr [rdi+rbx*8], 0
0x18000cb93  inc     ebx
0x18000cb95  cmp     ebx, esi
0x18000cb97  jb      short loc_18000CB76
0x18000cb99  mov     rcx, rdi; pv
0x18000cb9c  call    cs:__imp_CoTaskMemFree
0x18000cba2  nop
0x18000cba3  add     rsp, 28h
0x18000cba7  pop     rdi
0x18000cba8  pop     rsi
0x18000cba9  pop     rbp
0x18000cbaa  pop     rbx
0x18000cbab  retn
```
