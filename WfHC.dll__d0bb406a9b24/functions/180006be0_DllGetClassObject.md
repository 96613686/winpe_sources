# DllGetClassObject

- ea: `0x180006be0`
- end: `0x180006d1c`
- name: `DllGetClassObject`
- size: `316`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006be0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ccd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ca0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ca0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rcx
  HRESULT v8; // edi
  _QWORD *v9; // rbx
  _DWORD *v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, const IID *const, LPVOID *); // rcx

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v7 = off_1800156B0;
  v8 = 0;
  if ( off_1800156B0 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_1800156B8 )
  {
    while ( 1 )
    {
      v9 = *(_QWORD **)v7;
      if ( *(_QWORD *)v7 )
      {
        if ( v9[2] )
        {
          v10 = (_DWORD *)*v9;
          if ( rclsid->Data1 == *(_DWORD *)*v9
            && *(_DWORD *)&rclsid->Data2 == v10[1]
            && *(_DWORD *)rclsid->Data4 == v10[2]
            && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
          {
            break;
          }
        }
      }
      v7 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v7 + 8);
      if ( v7 >= (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_1800156B8 )
        goto LABEL_20;
    }
    if ( !v9[4] )
    {
      EnterCriticalSection(&CriticalSection);
      if ( !v9[4] )
        v8 = ((__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))v9[2])(
               v9[3],
               &GUID_00000000_0000_0000_c000_000000000046,
               v9 + 4);
      LeaveCriticalSection(&CriticalSection);
    }
    v11 = (__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))v9[4];
    if ( v11 )
      v8 = (**v11)(v11, riid, ppv);
  }
LABEL_20:
  if ( !*ppv && !v8 )
    return -2147221231;
  return v8;
}

```

## disassembly

```asm
0x180006be0  mov     [rsp+arg_18], rbp
0x180006be5  push    r14
0x180006be7  sub     rsp, 20h
0x180006beb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180006bf2  mov     r14, r8
0x180006bf5  mov     rbp, rdx
0x180006bf8  mov     r9, rcx
0x180006bfb  jnz     short loc_180006C0E
0x180006bfd  mov     eax, 8000FFFFh
0x180006c02  mov     rbp, [rsp+28h+arg_18]
0x180006c07  add     rsp, 20h
0x180006c0b  pop     r14
0x180006c0d  retn
0x180006c0e  test    r14, r14
0x180006c11  jnz     short loc_180006C24
0x180006c13  mov     eax, 80004003h
0x180006c18  mov     rbp, [rsp+28h+arg_18]
0x180006c1d  add     rsp, 20h
0x180006c21  pop     r14
0x180006c23  retn
0x180006c24  mov     qword ptr [r8], 0
0x180006c2b  mov     rcx, cs:off_1800156B0
0x180006c32  mov     r8, cs:off_1800156B8
0x180006c39  mov     [rsp+28h+arg_10], rdi
0x180006c3e  xor     edi, edi
0x180006c40  cmp     rcx, r8
0x180006c43  jnb     loc_180006CF9
0x180006c49  mov     [rsp+28h+arg_0], rbx
0x180006c4e  xchg    ax, ax
0x180006c50  mov     rbx, [rcx]
0x180006c53  test    rbx, rbx
0x180006c56  jz      short loc_180006C83
0x180006c58  cmp     [rbx+10h], rdi
0x180006c5c  jz      short loc_180006C83
0x180006c5e  mov     rdx, [rbx]
0x180006c61  mov     eax, [rdx]
0x180006c63  cmp     [r9], eax
0x180006c66  jnz     short loc_180006C83
0x180006c68  mov     eax, [rdx+4]
0x180006c6b  cmp     [r9+4], eax
0x180006c6f  jnz     short loc_180006C83
0x180006c71  mov     eax, [rdx+8]
0x180006c74  cmp     [r9+8], eax
0x180006c78  jnz     short loc_180006C83
0x180006c7a  mov     eax, [rdx+0Ch]
0x180006c7d  cmp     [r9+0Ch], eax
0x180006c81  jz      short loc_180006C8E
0x180006c83  add     rcx, 8
0x180006c87  cmp     rcx, r8
0x180006c8a  jb      short loc_180006C50
0x180006c8c  jmp     short loc_180006CF4
0x180006c8e  mov     [rsp+28h+arg_8], rsi
0x180006c93  cmp     [rbx+20h], rdi
0x180006c97  jnz     short loc_180006CD3
0x180006c99  lea     rcx, CriticalSection; lpCriticalSection
0x180006ca0  call    cs:__imp_EnterCriticalSection
0x180006ca6  cmp     [rbx+20h], rdi
0x180006caa  jnz     short loc_180006CC6
0x180006cac  mov     rcx, [rbx+18h]
0x180006cb0  lea     r8, [rbx+20h]
0x180006cb4  mov     rax, [rbx+10h]
0x180006cb8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc4  mov     edi, eax
0x180006cc6  lea     rcx, CriticalSection; lpCriticalSection
0x180006ccd  call    cs:__imp_LeaveCriticalSection
0x180006cd3  mov     rcx, [rbx+20h]
0x180006cd7  mov     rsi, [rsp+28h+arg_8]
0x180006cdc  test    rcx, rcx
0x180006cdf  jz      short loc_180006CF4
0x180006ce1  mov     rax, [rcx]
0x180006ce4  mov     r8, r14
0x180006ce7  mov     rdx, rbp
0x180006cea  mov     rax, [rax]
0x180006ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf2  mov     edi, eax
0x180006cf4  mov     rbx, [rsp+28h+arg_0]
0x180006cf9  cmp     qword ptr [r14], 0
0x180006cfd  jnz     short loc_180006D09
0x180006cff  test    edi, edi
0x180006d01  mov     eax, 80040111h
0x180006d06  cmovz   edi, eax
0x180006d09  mov     rbp, [rsp+28h+arg_18]
0x180006d0e  mov     eax, edi
0x180006d10  mov     rdi, [rsp+28h+arg_10]
0x180006d15  add     rsp, 20h
0x180006d19  pop     r14
0x180006d1b  retn
```
