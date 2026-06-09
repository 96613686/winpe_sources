# DllGetClassObject

- ea: `0x18000a2c0`
- end: `0x18000a3c6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a2c0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a388`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a35d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a35d`

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
  v7 = off_18001E140;
  v8 = off_18001E148;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001E148 )
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
0x18000a2c0  push    rbx
0x18000a2c2  push    rbp
0x18000a2c3  push    rsi
0x18000a2c4  push    rdi
0x18000a2c5  push    r14
0x18000a2c7  sub     rsp, 20h
0x18000a2cb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000a2d2  mov     r14, r8
0x18000a2d5  mov     r8, rcx
0x18000a2d8  mov     rbp, rdx
0x18000a2db  jnz     short loc_18000A2E7
0x18000a2dd  mov     ebx, 8000FFFFh
0x18000a2e2  jmp     loc_18000A3B9
0x18000a2e7  test    r14, r14
0x18000a2ea  jnz     short loc_18000A2F6
0x18000a2ec  mov     ebx, 80004003h
0x18000a2f1  jmp     loc_18000A3B9
0x18000a2f6  mov     qword ptr [r14], 0
0x18000a2fd  xor     ebx, ebx
0x18000a2ff  mov     rcx, cs:off_18001E140
0x18000a306  mov     r9, cs:off_18001E148
0x18000a30d  jmp     short loc_18000A346
0x18000a30f  mov     rsi, [rcx]
0x18000a312  test    rsi, rsi
0x18000a315  jz      short loc_18000A342
0x18000a317  cmp     [rsi+10h], rbx
0x18000a31b  jz      short loc_18000A342
0x18000a31d  mov     rdx, [rsi]
0x18000a320  mov     eax, [rdx]
0x18000a322  cmp     [r8], eax
0x18000a325  jnz     short loc_18000A342
0x18000a327  mov     eax, [rdx+4]
0x18000a32a  cmp     [r8+4], eax
0x18000a32e  jnz     short loc_18000A342
0x18000a330  mov     eax, [rdx+8]
0x18000a333  cmp     [r8+8], eax
0x18000a337  jnz     short loc_18000A342
0x18000a339  mov     eax, [rdx+0Ch]
0x18000a33c  cmp     [r8+0Ch], eax
0x18000a340  jz      short loc_18000A34D
0x18000a342  add     rcx, 8
0x18000a346  cmp     rcx, r9
0x18000a349  jb      short loc_18000A30F
0x18000a34b  jmp     short loc_18000A3A9
0x18000a34d  lea     rdi, [rsi+20h]
0x18000a351  cmp     [rdi], rbx
0x18000a354  jnz     short loc_18000A38E
0x18000a356  lea     rcx, CriticalSection; lpCriticalSection
0x18000a35d  call    cs:__imp_EnterCriticalSection
0x18000a363  cmp     [rdi], rbx
0x18000a366  jnz     short loc_18000A381
0x18000a368  mov     rcx, [rsi+18h]
0x18000a36c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a373  mov     rax, [rsi+10h]
0x18000a377  mov     r8, rdi
0x18000a37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a37f  mov     ebx, eax
0x18000a381  lea     rcx, CriticalSection; lpCriticalSection
0x18000a388  call    cs:__imp_LeaveCriticalSection
0x18000a38e  mov     rcx, [rdi]
0x18000a391  test    rcx, rcx
0x18000a394  jz      short loc_18000A3A9
0x18000a396  mov     rax, [rcx]
0x18000a399  mov     r8, r14
0x18000a39c  mov     rdx, rbp
0x18000a39f  mov     rax, [rax]
0x18000a3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a7  mov     ebx, eax
0x18000a3a9  cmp     qword ptr [r14], 0
0x18000a3ad  jnz     short loc_18000A3B9
0x18000a3af  test    ebx, ebx
0x18000a3b1  mov     eax, 80040111h
0x18000a3b6  cmovz   ebx, eax
0x18000a3b9  mov     eax, ebx
0x18000a3bb  add     rsp, 20h
0x18000a3bf  pop     r14
0x18000a3c1  pop     rdi
0x18000a3c2  pop     rsi
0x18000a3c3  pop     rbp
0x18000a3c4  pop     rbx
0x18000a3c5  retn
```
