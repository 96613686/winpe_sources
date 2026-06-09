# DllGetClassObject

- ea: `0x180009b20`
- end: `0x180009c26`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009b20`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009bbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009bbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009be8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009be8`

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
  v7 = off_180012100;
  v8 = off_180012108;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180012108 )
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
0x180009b20  push    rbx
0x180009b22  push    rbp
0x180009b23  push    rsi
0x180009b24  push    rdi
0x180009b25  push    r14
0x180009b27  sub     rsp, 20h
0x180009b2b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180009b32  mov     r14, r8
0x180009b35  mov     r8, rcx
0x180009b38  mov     rbp, rdx
0x180009b3b  jnz     short loc_180009B47
0x180009b3d  mov     ebx, 8000FFFFh
0x180009b42  jmp     loc_180009C19
0x180009b47  test    r14, r14
0x180009b4a  jnz     short loc_180009B56
0x180009b4c  mov     ebx, 80004003h
0x180009b51  jmp     loc_180009C19
0x180009b56  mov     qword ptr [r14], 0
0x180009b5d  xor     ebx, ebx
0x180009b5f  mov     rcx, cs:off_180012100
0x180009b66  mov     r9, cs:off_180012108
0x180009b6d  jmp     short loc_180009BA6
0x180009b6f  mov     rsi, [rcx]
0x180009b72  test    rsi, rsi
0x180009b75  jz      short loc_180009BA2
0x180009b77  cmp     [rsi+10h], rbx
0x180009b7b  jz      short loc_180009BA2
0x180009b7d  mov     rdx, [rsi]
0x180009b80  mov     eax, [rdx]
0x180009b82  cmp     [r8], eax
0x180009b85  jnz     short loc_180009BA2
0x180009b87  mov     eax, [rdx+4]
0x180009b8a  cmp     [r8+4], eax
0x180009b8e  jnz     short loc_180009BA2
0x180009b90  mov     eax, [rdx+8]
0x180009b93  cmp     [r8+8], eax
0x180009b97  jnz     short loc_180009BA2
0x180009b99  mov     eax, [rdx+0Ch]
0x180009b9c  cmp     [r8+0Ch], eax
0x180009ba0  jz      short loc_180009BAD
0x180009ba2  add     rcx, 8
0x180009ba6  cmp     rcx, r9
0x180009ba9  jb      short loc_180009B6F
0x180009bab  jmp     short loc_180009C09
0x180009bad  lea     rdi, [rsi+20h]
0x180009bb1  cmp     [rdi], rbx
0x180009bb4  jnz     short loc_180009BEE
0x180009bb6  lea     rcx, CriticalSection; lpCriticalSection
0x180009bbd  call    cs:__imp_EnterCriticalSection
0x180009bc3  cmp     [rdi], rbx
0x180009bc6  jnz     short loc_180009BE1
0x180009bc8  mov     rcx, [rsi+18h]
0x180009bcc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009bd3  mov     rax, [rsi+10h]
0x180009bd7  mov     r8, rdi
0x180009bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bdf  mov     ebx, eax
0x180009be1  lea     rcx, CriticalSection; lpCriticalSection
0x180009be8  call    cs:__imp_LeaveCriticalSection
0x180009bee  mov     rcx, [rdi]
0x180009bf1  test    rcx, rcx
0x180009bf4  jz      short loc_180009C09
0x180009bf6  mov     rax, [rcx]
0x180009bf9  mov     r8, r14
0x180009bfc  mov     rdx, rbp
0x180009bff  mov     rax, [rax]
0x180009c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c07  mov     ebx, eax
0x180009c09  cmp     qword ptr [r14], 0
0x180009c0d  jnz     short loc_180009C19
0x180009c0f  test    ebx, ebx
0x180009c11  mov     eax, 80040111h
0x180009c16  cmovz   ebx, eax
0x180009c19  mov     eax, ebx
0x180009c1b  add     rsp, 20h
0x180009c1f  pop     r14
0x180009c21  pop     rdi
0x180009c22  pop     rsi
0x180009c23  pop     rbp
0x180009c24  pop     rbx
0x180009c25  retn
```
