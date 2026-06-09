# DllGetClassObject

- ea: `0x18000c310`
- end: `0x18000c416`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c310`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3d8`

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
  v7 = off_180014160;
  v8 = off_180014168;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180014168 )
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
0x18000c310  push    rbx
0x18000c312  push    rbp
0x18000c313  push    rsi
0x18000c314  push    rdi
0x18000c315  push    r14
0x18000c317  sub     rsp, 20h
0x18000c31b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000c322  mov     r14, r8
0x18000c325  mov     r8, rcx
0x18000c328  mov     rbp, rdx
0x18000c32b  jnz     short loc_18000C337
0x18000c32d  mov     ebx, 8000FFFFh
0x18000c332  jmp     loc_18000C409
0x18000c337  test    r14, r14
0x18000c33a  jnz     short loc_18000C346
0x18000c33c  mov     ebx, 80004003h
0x18000c341  jmp     loc_18000C409
0x18000c346  mov     qword ptr [r14], 0
0x18000c34d  xor     ebx, ebx
0x18000c34f  mov     rcx, cs:off_180014160
0x18000c356  mov     r9, cs:off_180014168
0x18000c35d  jmp     short loc_18000C396
0x18000c35f  mov     rsi, [rcx]
0x18000c362  test    rsi, rsi
0x18000c365  jz      short loc_18000C392
0x18000c367  cmp     [rsi+10h], rbx
0x18000c36b  jz      short loc_18000C392
0x18000c36d  mov     rdx, [rsi]
0x18000c370  mov     eax, [rdx]
0x18000c372  cmp     [r8], eax
0x18000c375  jnz     short loc_18000C392
0x18000c377  mov     eax, [rdx+4]
0x18000c37a  cmp     [r8+4], eax
0x18000c37e  jnz     short loc_18000C392
0x18000c380  mov     eax, [rdx+8]
0x18000c383  cmp     [r8+8], eax
0x18000c387  jnz     short loc_18000C392
0x18000c389  mov     eax, [rdx+0Ch]
0x18000c38c  cmp     [r8+0Ch], eax
0x18000c390  jz      short loc_18000C39D
0x18000c392  add     rcx, 8
0x18000c396  cmp     rcx, r9
0x18000c399  jb      short loc_18000C35F
0x18000c39b  jmp     short loc_18000C3F9
0x18000c39d  lea     rdi, [rsi+20h]
0x18000c3a1  cmp     [rdi], rbx
0x18000c3a4  jnz     short loc_18000C3DE
0x18000c3a6  lea     rcx, CriticalSection; lpCriticalSection
0x18000c3ad  call    cs:__imp_EnterCriticalSection
0x18000c3b3  cmp     [rdi], rbx
0x18000c3b6  jnz     short loc_18000C3D1
0x18000c3b8  mov     rcx, [rsi+18h]
0x18000c3bc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c3c3  mov     rax, [rsi+10h]
0x18000c3c7  mov     r8, rdi
0x18000c3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3cf  mov     ebx, eax
0x18000c3d1  lea     rcx, CriticalSection; lpCriticalSection
0x18000c3d8  call    cs:__imp_LeaveCriticalSection
0x18000c3de  mov     rcx, [rdi]
0x18000c3e1  test    rcx, rcx
0x18000c3e4  jz      short loc_18000C3F9
0x18000c3e6  mov     rax, [rcx]
0x18000c3e9  mov     r8, r14
0x18000c3ec  mov     rdx, rbp
0x18000c3ef  mov     rax, [rax]
0x18000c3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f7  mov     ebx, eax
0x18000c3f9  cmp     qword ptr [r14], 0
0x18000c3fd  jnz     short loc_18000C409
0x18000c3ff  test    ebx, ebx
0x18000c401  mov     eax, 80040111h
0x18000c406  cmovz   ebx, eax
0x18000c409  mov     eax, ebx
0x18000c40b  add     rsp, 20h
0x18000c40f  pop     r14
0x18000c411  pop     rdi
0x18000c412  pop     rsi
0x18000c413  pop     rbp
0x18000c414  pop     rbx
0x18000c415  retn
```
