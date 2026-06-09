# DllGetClassObject

- ea: `0x180009bb0`
- end: `0x180009cb6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009bb0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c78`

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
0x180009bb0  push    rbx
0x180009bb2  push    rbp
0x180009bb3  push    rsi
0x180009bb4  push    rdi
0x180009bb5  push    r14
0x180009bb7  sub     rsp, 20h
0x180009bbb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180009bc2  mov     r14, r8
0x180009bc5  mov     r8, rcx
0x180009bc8  mov     rbp, rdx
0x180009bcb  jnz     short loc_180009BD7
0x180009bcd  mov     ebx, 8000FFFFh
0x180009bd2  jmp     loc_180009CA9
0x180009bd7  test    r14, r14
0x180009bda  jnz     short loc_180009BE6
0x180009bdc  mov     ebx, 80004003h
0x180009be1  jmp     loc_180009CA9
0x180009be6  mov     qword ptr [r14], 0
0x180009bed  xor     ebx, ebx
0x180009bef  mov     rcx, cs:off_180015100
0x180009bf6  mov     r9, cs:off_180015108
0x180009bfd  jmp     short loc_180009C36
0x180009bff  mov     rsi, [rcx]
0x180009c02  test    rsi, rsi
0x180009c05  jz      short loc_180009C32
0x180009c07  cmp     [rsi+10h], rbx
0x180009c0b  jz      short loc_180009C32
0x180009c0d  mov     rdx, [rsi]
0x180009c10  mov     eax, [rdx]
0x180009c12  cmp     [r8], eax
0x180009c15  jnz     short loc_180009C32
0x180009c17  mov     eax, [rdx+4]
0x180009c1a  cmp     [r8+4], eax
0x180009c1e  jnz     short loc_180009C32
0x180009c20  mov     eax, [rdx+8]
0x180009c23  cmp     [r8+8], eax
0x180009c27  jnz     short loc_180009C32
0x180009c29  mov     eax, [rdx+0Ch]
0x180009c2c  cmp     [r8+0Ch], eax
0x180009c30  jz      short loc_180009C3D
0x180009c32  add     rcx, 8
0x180009c36  cmp     rcx, r9
0x180009c39  jb      short loc_180009BFF
0x180009c3b  jmp     short loc_180009C99
0x180009c3d  lea     rdi, [rsi+20h]
0x180009c41  cmp     [rdi], rbx
0x180009c44  jnz     short loc_180009C7E
0x180009c46  lea     rcx, CriticalSection; lpCriticalSection
0x180009c4d  call    cs:__imp_EnterCriticalSection
0x180009c53  cmp     [rdi], rbx
0x180009c56  jnz     short loc_180009C71
0x180009c58  mov     rcx, [rsi+18h]
0x180009c5c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009c63  mov     rax, [rsi+10h]
0x180009c67  mov     r8, rdi
0x180009c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6f  mov     ebx, eax
0x180009c71  lea     rcx, CriticalSection; lpCriticalSection
0x180009c78  call    cs:__imp_LeaveCriticalSection
0x180009c7e  mov     rcx, [rdi]
0x180009c81  test    rcx, rcx
0x180009c84  jz      short loc_180009C99
0x180009c86  mov     rax, [rcx]
0x180009c89  mov     r8, r14
0x180009c8c  mov     rdx, rbp
0x180009c8f  mov     rax, [rax]
0x180009c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c97  mov     ebx, eax
0x180009c99  cmp     qword ptr [r14], 0
0x180009c9d  jnz     short loc_180009CA9
0x180009c9f  test    ebx, ebx
0x180009ca1  mov     eax, 80040111h
0x180009ca6  cmovz   ebx, eax
0x180009ca9  mov     eax, ebx
0x180009cab  add     rsp, 20h
0x180009caf  pop     r14
0x180009cb1  pop     rdi
0x180009cb2  pop     rsi
0x180009cb3  pop     rbp
0x180009cb4  pop     rbx
0x180009cb5  retn
```
