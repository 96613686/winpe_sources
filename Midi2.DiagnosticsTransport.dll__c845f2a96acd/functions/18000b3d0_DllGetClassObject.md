# DllGetClassObject

- ea: `0x18000b3d0`
- end: `0x18000b4d6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b3d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b498`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b498`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b46d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b46d`

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
  v7 = off_18001A100;
  v8 = off_18001A108;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001A108 )
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
            EnterCriticalSection(&stru_18001A110);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&stru_18001A110);
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
0x18000b3d0  push    rbx
0x18000b3d2  push    rbp
0x18000b3d3  push    rsi
0x18000b3d4  push    rdi
0x18000b3d5  push    r14
0x18000b3d7  sub     rsp, 20h
0x18000b3db  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000b3e2  mov     r14, r8
0x18000b3e5  mov     r8, rcx
0x18000b3e8  mov     rbp, rdx
0x18000b3eb  jnz     short loc_18000B3F7
0x18000b3ed  mov     ebx, 8000FFFFh
0x18000b3f2  jmp     loc_18000B4C9
0x18000b3f7  test    r14, r14
0x18000b3fa  jnz     short loc_18000B406
0x18000b3fc  mov     ebx, 80004003h
0x18000b401  jmp     loc_18000B4C9
0x18000b406  mov     qword ptr [r14], 0
0x18000b40d  xor     ebx, ebx
0x18000b40f  mov     rcx, cs:off_18001A100
0x18000b416  mov     r9, cs:off_18001A108
0x18000b41d  jmp     short loc_18000B456
0x18000b41f  mov     rsi, [rcx]
0x18000b422  test    rsi, rsi
0x18000b425  jz      short loc_18000B452
0x18000b427  cmp     [rsi+10h], rbx
0x18000b42b  jz      short loc_18000B452
0x18000b42d  mov     rdx, [rsi]
0x18000b430  mov     eax, [rdx]
0x18000b432  cmp     [r8], eax
0x18000b435  jnz     short loc_18000B452
0x18000b437  mov     eax, [rdx+4]
0x18000b43a  cmp     [r8+4], eax
0x18000b43e  jnz     short loc_18000B452
0x18000b440  mov     eax, [rdx+8]
0x18000b443  cmp     [r8+8], eax
0x18000b447  jnz     short loc_18000B452
0x18000b449  mov     eax, [rdx+0Ch]
0x18000b44c  cmp     [r8+0Ch], eax
0x18000b450  jz      short loc_18000B45D
0x18000b452  add     rcx, 8
0x18000b456  cmp     rcx, r9
0x18000b459  jb      short loc_18000B41F
0x18000b45b  jmp     short loc_18000B4B9
0x18000b45d  lea     rdi, [rsi+20h]
0x18000b461  cmp     [rdi], rbx
0x18000b464  jnz     short loc_18000B49E
0x18000b466  lea     rcx, stru_18001A110; lpCriticalSection
0x18000b46d  call    cs:__imp_EnterCriticalSection
0x18000b473  cmp     [rdi], rbx
0x18000b476  jnz     short loc_18000B491
0x18000b478  mov     rcx, [rsi+18h]
0x18000b47c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000b483  mov     rax, [rsi+10h]
0x18000b487  mov     r8, rdi
0x18000b48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b48f  mov     ebx, eax
0x18000b491  lea     rcx, stru_18001A110; lpCriticalSection
0x18000b498  call    cs:__imp_LeaveCriticalSection
0x18000b49e  mov     rcx, [rdi]
0x18000b4a1  test    rcx, rcx
0x18000b4a4  jz      short loc_18000B4B9
0x18000b4a6  mov     rax, [rcx]
0x18000b4a9  mov     r8, r14
0x18000b4ac  mov     rdx, rbp
0x18000b4af  mov     rax, [rax]
0x18000b4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b7  mov     ebx, eax
0x18000b4b9  cmp     qword ptr [r14], 0
0x18000b4bd  jnz     short loc_18000B4C9
0x18000b4bf  test    ebx, ebx
0x18000b4c1  mov     eax, 80040111h
0x18000b4c6  cmovz   ebx, eax
0x18000b4c9  mov     eax, ebx
0x18000b4cb  add     rsp, 20h
0x18000b4cf  pop     r14
0x18000b4d1  pop     rdi
0x18000b4d2  pop     rsi
0x18000b4d3  pop     rbp
0x18000b4d4  pop     rbx
0x18000b4d5  retn
```
