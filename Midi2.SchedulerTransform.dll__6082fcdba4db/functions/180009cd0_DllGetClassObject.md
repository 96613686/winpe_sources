# DllGetClassObject

- ea: `0x180009cd0`
- end: `0x180009dd6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d98`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rcx
  __int64 *v8; // r9
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_180015100;
  v8 = off_180015108;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180015108 )
  {
    v9 = *v7;
    if ( *v7 )
    {
      if ( *((_QWORD *)v9 + 2) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)((char *)v9 + 32);
          if ( !*((_QWORD *)v9 + 4) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
          break;
        }
      }
    }
    ++v7;
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180009cd0  push    rbx
0x180009cd2  push    rbp
0x180009cd3  push    rsi
0x180009cd4  push    rdi
0x180009cd5  push    r14
0x180009cd7  sub     rsp, 20h
0x180009cdb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180009ce2  mov     r14, r8
0x180009ce5  mov     r8, rcx
0x180009ce8  mov     rbp, rdx
0x180009ceb  jnz     short loc_180009CF7
0x180009ced  mov     ebx, 8000FFFFh
0x180009cf2  jmp     loc_180009DC9
0x180009cf7  test    r14, r14
0x180009cfa  jnz     short loc_180009D06
0x180009cfc  mov     ebx, 80004003h
0x180009d01  jmp     loc_180009DC9
0x180009d06  mov     qword ptr [r14], 0
0x180009d0d  xor     ebx, ebx
0x180009d0f  mov     rcx, cs:off_180015100
0x180009d16  mov     r9, cs:off_180015108
0x180009d1d  jmp     short loc_180009D56
0x180009d1f  mov     rsi, [rcx]
0x180009d22  test    rsi, rsi
0x180009d25  jz      short loc_180009D52
0x180009d27  cmp     [rsi+10h], rbx
0x180009d2b  jz      short loc_180009D52
0x180009d2d  mov     rdx, [rsi]
0x180009d30  mov     eax, [rdx]
0x180009d32  cmp     [r8], eax
0x180009d35  jnz     short loc_180009D52
0x180009d37  mov     eax, [rdx+4]
0x180009d3a  cmp     [r8+4], eax
0x180009d3e  jnz     short loc_180009D52
0x180009d40  mov     eax, [rdx+8]
0x180009d43  cmp     [r8+8], eax
0x180009d47  jnz     short loc_180009D52
0x180009d49  mov     eax, [rdx+0Ch]
0x180009d4c  cmp     [r8+0Ch], eax
0x180009d50  jz      short loc_180009D5D
0x180009d52  add     rcx, 8
0x180009d56  cmp     rcx, r9
0x180009d59  jb      short loc_180009D1F
0x180009d5b  jmp     short loc_180009DB9
0x180009d5d  lea     rdi, [rsi+20h]
0x180009d61  cmp     [rdi], rbx
0x180009d64  jnz     short loc_180009D9E
0x180009d66  lea     rcx, CriticalSection; lpCriticalSection
0x180009d6d  call    cs:__imp_EnterCriticalSection
0x180009d73  cmp     [rdi], rbx
0x180009d76  jnz     short loc_180009D91
0x180009d78  mov     rcx, [rsi+18h]
0x180009d7c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009d83  mov     rax, [rsi+10h]
0x180009d87  mov     r8, rdi
0x180009d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8f  mov     ebx, eax
0x180009d91  lea     rcx, CriticalSection; lpCriticalSection
0x180009d98  call    cs:__imp_LeaveCriticalSection
0x180009d9e  mov     rcx, [rdi]
0x180009da1  test    rcx, rcx
0x180009da4  jz      short loc_180009DB9
0x180009da6  mov     rax, [rcx]
0x180009da9  mov     r8, r14
0x180009dac  mov     rdx, rbp
0x180009daf  mov     rax, [rax]
0x180009db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009db7  mov     ebx, eax
0x180009db9  cmp     qword ptr [r14], 0
0x180009dbd  jnz     short loc_180009DC9
0x180009dbf  test    ebx, ebx
0x180009dc1  mov     eax, 80040111h
0x180009dc6  cmovz   ebx, eax
0x180009dc9  mov     eax, ebx
0x180009dcb  add     rsp, 20h
0x180009dcf  pop     r14
0x180009dd1  pop     rdi
0x180009dd2  pop     rsi
0x180009dd3  pop     rbp
0x180009dd4  pop     rbx
0x180009dd5  retn
```
