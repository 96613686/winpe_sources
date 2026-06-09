# DllGetClassObject

- ea: `0x1800048c0`
- end: `0x1800049c6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800048c0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000495d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000495d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004988`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004988`

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
  v7 = off_1800110B0;
  v8 = off_1800110B8;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800110B8 )
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
0x1800048c0  push    rbx
0x1800048c2  push    rbp
0x1800048c3  push    rsi
0x1800048c4  push    rdi
0x1800048c5  push    r14
0x1800048c7  sub     rsp, 20h
0x1800048cb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800048d2  mov     r14, r8
0x1800048d5  mov     r8, rcx
0x1800048d8  mov     rbp, rdx
0x1800048db  jnz     short loc_1800048E7
0x1800048dd  mov     ebx, 8000FFFFh
0x1800048e2  jmp     loc_1800049B9
0x1800048e7  test    r14, r14
0x1800048ea  jnz     short loc_1800048F6
0x1800048ec  mov     ebx, 80004003h
0x1800048f1  jmp     loc_1800049B9
0x1800048f6  mov     qword ptr [r14], 0
0x1800048fd  xor     ebx, ebx
0x1800048ff  mov     rcx, cs:off_1800110B0
0x180004906  mov     r9, cs:off_1800110B8
0x18000490d  jmp     short loc_180004946
0x18000490f  mov     rsi, [rcx]
0x180004912  test    rsi, rsi
0x180004915  jz      short loc_180004942
0x180004917  cmp     [rsi+10h], rbx
0x18000491b  jz      short loc_180004942
0x18000491d  mov     rdx, [rsi]
0x180004920  mov     eax, [rdx]
0x180004922  cmp     [r8], eax
0x180004925  jnz     short loc_180004942
0x180004927  mov     eax, [rdx+4]
0x18000492a  cmp     [r8+4], eax
0x18000492e  jnz     short loc_180004942
0x180004930  mov     eax, [rdx+8]
0x180004933  cmp     [r8+8], eax
0x180004937  jnz     short loc_180004942
0x180004939  mov     eax, [rdx+0Ch]
0x18000493c  cmp     [r8+0Ch], eax
0x180004940  jz      short loc_18000494D
0x180004942  add     rcx, 8
0x180004946  cmp     rcx, r9
0x180004949  jb      short loc_18000490F
0x18000494b  jmp     short loc_1800049A9
0x18000494d  lea     rdi, [rsi+20h]
0x180004951  cmp     [rdi], rbx
0x180004954  jnz     short loc_18000498E
0x180004956  lea     rcx, CriticalSection; lpCriticalSection
0x18000495d  call    cs:__imp_EnterCriticalSection
0x180004963  cmp     [rdi], rbx
0x180004966  jnz     short loc_180004981
0x180004968  mov     rcx, [rsi+18h]
0x18000496c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004973  mov     rax, [rsi+10h]
0x180004977  mov     r8, rdi
0x18000497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497f  mov     ebx, eax
0x180004981  lea     rcx, CriticalSection; lpCriticalSection
0x180004988  call    cs:__imp_LeaveCriticalSection
0x18000498e  mov     rcx, [rdi]
0x180004991  test    rcx, rcx
0x180004994  jz      short loc_1800049A9
0x180004996  mov     rax, [rcx]
0x180004999  mov     r8, r14
0x18000499c  mov     rdx, rbp
0x18000499f  mov     rax, [rax]
0x1800049a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a7  mov     ebx, eax
0x1800049a9  cmp     qword ptr [r14], 0
0x1800049ad  jnz     short loc_1800049B9
0x1800049af  test    ebx, ebx
0x1800049b1  mov     eax, 80040111h
0x1800049b6  cmovz   ebx, eax
0x1800049b9  mov     eax, ebx
0x1800049bb  add     rsp, 20h
0x1800049bf  pop     r14
0x1800049c1  pop     rdi
0x1800049c2  pop     rsi
0x1800049c3  pop     rbp
0x1800049c4  pop     rbx
0x1800049c5  retn
```
