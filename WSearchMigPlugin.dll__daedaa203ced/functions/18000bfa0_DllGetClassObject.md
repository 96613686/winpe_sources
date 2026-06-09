# DllGetClassObject

- ea: `0x18000bfa0`
- end: `0x18000c0a6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000bfa0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c03d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c03d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c068`

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
  v7 = off_180025520;
  v8 = off_180025528;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180025528 )
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
            EnterCriticalSection(&stru_180025530);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&stru_180025530);
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
0x18000bfa0  push    rbx
0x18000bfa2  push    rbp
0x18000bfa3  push    rsi
0x18000bfa4  push    rdi
0x18000bfa5  push    r14
0x18000bfa7  sub     rsp, 20h
0x18000bfab  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000bfb2  mov     r14, r8
0x18000bfb5  mov     r8, rcx
0x18000bfb8  mov     rbp, rdx
0x18000bfbb  jnz     short loc_18000BFC7
0x18000bfbd  mov     ebx, 8000FFFFh
0x18000bfc2  jmp     loc_18000C099
0x18000bfc7  test    r14, r14
0x18000bfca  jnz     short loc_18000BFD6
0x18000bfcc  mov     ebx, 80004003h
0x18000bfd1  jmp     loc_18000C099
0x18000bfd6  mov     qword ptr [r14], 0
0x18000bfdd  xor     ebx, ebx
0x18000bfdf  mov     rcx, cs:off_180025520
0x18000bfe6  mov     r9, cs:off_180025528
0x18000bfed  jmp     short loc_18000C026
0x18000bfef  mov     rsi, [rcx]
0x18000bff2  test    rsi, rsi
0x18000bff5  jz      short loc_18000C022
0x18000bff7  cmp     [rsi+10h], rbx
0x18000bffb  jz      short loc_18000C022
0x18000bffd  mov     rdx, [rsi]
0x18000c000  mov     eax, [rdx]
0x18000c002  cmp     [r8], eax
0x18000c005  jnz     short loc_18000C022
0x18000c007  mov     eax, [rdx+4]
0x18000c00a  cmp     [r8+4], eax
0x18000c00e  jnz     short loc_18000C022
0x18000c010  mov     eax, [rdx+8]
0x18000c013  cmp     [r8+8], eax
0x18000c017  jnz     short loc_18000C022
0x18000c019  mov     eax, [rdx+0Ch]
0x18000c01c  cmp     [r8+0Ch], eax
0x18000c020  jz      short loc_18000C02D
0x18000c022  add     rcx, 8
0x18000c026  cmp     rcx, r9
0x18000c029  jb      short loc_18000BFEF
0x18000c02b  jmp     short loc_18000C089
0x18000c02d  lea     rdi, [rsi+20h]
0x18000c031  cmp     [rdi], rbx
0x18000c034  jnz     short loc_18000C06E
0x18000c036  lea     rcx, stru_180025530; lpCriticalSection
0x18000c03d  call    cs:__imp_EnterCriticalSection
0x18000c043  cmp     [rdi], rbx
0x18000c046  jnz     short loc_18000C061
0x18000c048  mov     rcx, [rsi+18h]
0x18000c04c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c053  mov     rax, [rsi+10h]
0x18000c057  mov     r8, rdi
0x18000c05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c05f  mov     ebx, eax
0x18000c061  lea     rcx, stru_180025530; lpCriticalSection
0x18000c068  call    cs:__imp_LeaveCriticalSection
0x18000c06e  mov     rcx, [rdi]
0x18000c071  test    rcx, rcx
0x18000c074  jz      short loc_18000C089
0x18000c076  mov     rax, [rcx]
0x18000c079  mov     r8, r14
0x18000c07c  mov     rdx, rbp
0x18000c07f  mov     rax, [rax]
0x18000c082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c087  mov     ebx, eax
0x18000c089  cmp     qword ptr [r14], 0
0x18000c08d  jnz     short loc_18000C099
0x18000c08f  test    ebx, ebx
0x18000c091  mov     eax, 80040111h
0x18000c096  cmovz   ebx, eax
0x18000c099  mov     eax, ebx
0x18000c09b  add     rsp, 20h
0x18000c09f  pop     r14
0x18000c0a1  pop     rdi
0x18000c0a2  pop     rsi
0x18000c0a3  pop     rbp
0x18000c0a4  pop     rbx
0x18000c0a5  retn
```
