# DllGetClassObject

- ea: `0x180009ce0`
- end: `0x180009de6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009ce0`
- `0x180012010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009da8`
- `KERNEL32!LeaveCriticalSection` at `0x180009da8`
- `KERNEL32!EnterCriticalSection` at `0x180009d7d`
- `KERNEL32!EnterCriticalSection` at `0x180009d7d`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rcx
  __int64 *v8; // r9
  __int64 v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18001B110;
  v8 = (__int64 *)off_18001B118;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18001B118 )
  {
    v9 = *(_QWORD *)v7;
    if ( *(_QWORD *)v7 )
    {
      if ( *(_QWORD *)(v9 + 16) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)(v9 + 32);
          if ( !*(_QWORD *)(v9 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                     *(_QWORD *)(v9 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
          break;
        }
      }
    }
    v7 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v7 + 8);
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180009ce0  push    rbx
0x180009ce2  push    rbp
0x180009ce3  push    rsi
0x180009ce4  push    rdi
0x180009ce5  push    r14
0x180009ce7  sub     rsp, 20h
0x180009ceb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180009cf2  mov     r14, r8
0x180009cf5  mov     r8, rcx
0x180009cf8  mov     rbp, rdx
0x180009cfb  jnz     short loc_180009D07
0x180009cfd  mov     ebx, 8000FFFFh
0x180009d02  jmp     loc_180009DD9
0x180009d07  test    r14, r14
0x180009d0a  jnz     short loc_180009D16
0x180009d0c  mov     ebx, 80004003h
0x180009d11  jmp     loc_180009DD9
0x180009d16  mov     qword ptr [r14], 0
0x180009d1d  xor     ebx, ebx
0x180009d1f  mov     rcx, cs:off_18001B110
0x180009d26  mov     r9, cs:off_18001B118
0x180009d2d  jmp     short loc_180009D66
0x180009d2f  mov     rsi, [rcx]
0x180009d32  test    rsi, rsi
0x180009d35  jz      short loc_180009D62
0x180009d37  cmp     [rsi+10h], rbx
0x180009d3b  jz      short loc_180009D62
0x180009d3d  mov     rdx, [rsi]
0x180009d40  mov     eax, [rdx]
0x180009d42  cmp     [r8], eax
0x180009d45  jnz     short loc_180009D62
0x180009d47  mov     eax, [rdx+4]
0x180009d4a  cmp     [r8+4], eax
0x180009d4e  jnz     short loc_180009D62
0x180009d50  mov     eax, [rdx+8]
0x180009d53  cmp     [r8+8], eax
0x180009d57  jnz     short loc_180009D62
0x180009d59  mov     eax, [rdx+0Ch]
0x180009d5c  cmp     [r8+0Ch], eax
0x180009d60  jz      short loc_180009D6D
0x180009d62  add     rcx, 8
0x180009d66  cmp     rcx, r9
0x180009d69  jb      short loc_180009D2F
0x180009d6b  jmp     short loc_180009DC9
0x180009d6d  lea     rdi, [rsi+20h]
0x180009d71  cmp     [rdi], rbx
0x180009d74  jnz     short loc_180009DAE
0x180009d76  lea     rcx, CriticalSection; lpCriticalSection
0x180009d7d  call    cs:__imp_EnterCriticalSection
0x180009d83  cmp     [rdi], rbx
0x180009d86  jnz     short loc_180009DA1
0x180009d88  mov     rcx, [rsi+18h]
0x180009d8c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009d93  mov     rax, [rsi+10h]
0x180009d97  mov     r8, rdi
0x180009d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d9f  mov     ebx, eax
0x180009da1  lea     rcx, CriticalSection; lpCriticalSection
0x180009da8  call    cs:__imp_LeaveCriticalSection
0x180009dae  mov     rcx, [rdi]
0x180009db1  test    rcx, rcx
0x180009db4  jz      short loc_180009DC9
0x180009db6  mov     rax, [rcx]
0x180009db9  mov     r8, r14
0x180009dbc  mov     rdx, rbp
0x180009dbf  mov     rax, [rax]
0x180009dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc7  mov     ebx, eax
0x180009dc9  cmp     qword ptr [r14], 0
0x180009dcd  jnz     short loc_180009DD9
0x180009dcf  test    ebx, ebx
0x180009dd1  mov     eax, 80040111h
0x180009dd6  cmovz   ebx, eax
0x180009dd9  mov     eax, ebx
0x180009ddb  add     rsp, 20h
0x180009ddf  pop     r14
0x180009de1  pop     rdi
0x180009de2  pop     rsi
0x180009de3  pop     rbp
0x180009de4  pop     rbx
0x180009de5  retn
```
