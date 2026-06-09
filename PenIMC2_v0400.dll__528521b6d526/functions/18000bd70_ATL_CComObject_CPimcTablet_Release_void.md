# ATL::CComObject<CPimcTablet>::Release(void)

- ea: `0x18000bd70`
- end: `0x18000bdda`
- name: `?Release@?$CComObject@VCPimcTablet@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bd70`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CPimcTablet>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 168LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bd70  mov     [rsp+arg_0], rbx
0x18000bd75  push    rdi
0x18000bd76  sub     rsp, 30h
0x18000bd7a  mov     rbx, rcx
0x18000bd7d  sub     dword ptr [rcx+8], 1
0x18000bd81  mov     edi, [rcx+8]
0x18000bd84  jnz     short loc_18000BDCD
0x18000bd86  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bd8d  mov     rax, [rcx]
0x18000bd90  mov     rax, [rax+8]
0x18000bd94  call    cs:__guard_dispatch_icall_fptr
0x18000bd9a  nop
0x18000bd9b  test    rbx, rbx
0x18000bd9e  jz      short loc_18000BDB9
0x18000bda0  mov     rax, [rbx]
0x18000bda3  mov     edx, 1
0x18000bda8  mov     rcx, rbx
0x18000bdab  mov     rax, [rax+0A8h]
0x18000bdb2  call    cs:__guard_dispatch_icall_fptr
0x18000bdb8  nop
0x18000bdb9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bdc0  mov     rdx, [rcx]
0x18000bdc3  mov     rax, [rdx+10h]
0x18000bdc7  call    cs:__guard_dispatch_icall_fptr
0x18000bdcd  mov     eax, edi
0x18000bdcf  mov     rbx, [rsp+38h+arg_0]
0x18000bdd4  add     rsp, 30h
0x18000bdd8  pop     rdi
0x18000bdd9  retn
```
