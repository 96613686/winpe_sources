# ATL::CAtlDllModuleT<CDsmApiModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000dc10`
- end: `0x18000dd16`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCDsmApiModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e090`

## callees

- `0x18000dc10`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dcad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dcad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcd8`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<CDsmApiModule>::DllGetClassObject(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v7; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( ATL::_AtlComModule )
  {
    if ( a4 )
    {
      *a4 = 0;
      v7 = 0;
      for ( i = off_180017360; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180017368; ++i )
      {
        v9 = *i;
        if ( *i )
        {
          if ( *((_QWORD *)v9 + 2) )
          {
            v10 = *(_DWORD **)v9;
            if ( *a2 == **(_DWORD **)v9 && a2[1] == v10[1] && a2[2] == v10[2] && a2[3] == v10[3] )
            {
              v11 = (_QWORD *)((char *)v9 + 32);
              if ( !*((_QWORD *)v9 + 4) )
              {
                EnterCriticalSection(&stru_180017370);
                if ( !*v11 )
                  v7 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                         *((_QWORD *)v9 + 3),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         (__int64)v9 + 32);
                LeaveCriticalSection(&stru_180017370);
              }
              if ( *v11 )
                v7 = (**(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))*v11)(*v11, a3, a4);
              break;
            }
          }
        }
      }
      if ( !*a4 && !v7 )
        return (unsigned int)-2147221231;
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v7;
}

```

## disassembly

```asm
0x18000dc10  push    rbx
0x18000dc12  push    rbp
0x18000dc13  push    rsi
0x18000dc14  push    rdi
0x18000dc15  push    r14
0x18000dc17  sub     rsp, 20h
0x18000dc1b  mov     r14, r9
0x18000dc1e  mov     rbp, r8
0x18000dc21  mov     r9, rdx
0x18000dc24  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000dc2b  jnz     short loc_18000DC37
0x18000dc2d  mov     ebx, 8000FFFFh
0x18000dc32  jmp     loc_18000DD09
0x18000dc37  test    r14, r14
0x18000dc3a  jnz     short loc_18000DC46
0x18000dc3c  mov     ebx, 80004003h
0x18000dc41  jmp     loc_18000DD09
0x18000dc46  mov     qword ptr [r14], 0
0x18000dc4d  xor     ebx, ebx
0x18000dc4f  mov     rcx, cs:off_180017360
0x18000dc56  mov     r8, cs:off_180017368
0x18000dc5d  jmp     short loc_18000DC96
0x18000dc5f  mov     rsi, [rcx]
0x18000dc62  test    rsi, rsi
0x18000dc65  jz      short loc_18000DC92
0x18000dc67  cmp     [rsi+10h], rbx
0x18000dc6b  jz      short loc_18000DC92
0x18000dc6d  mov     rdx, [rsi]
0x18000dc70  mov     eax, [rdx]
0x18000dc72  cmp     [r9], eax
0x18000dc75  jnz     short loc_18000DC92
0x18000dc77  mov     eax, [rdx+4]
0x18000dc7a  cmp     [r9+4], eax
0x18000dc7e  jnz     short loc_18000DC92
0x18000dc80  mov     eax, [rdx+8]
0x18000dc83  cmp     [r9+8], eax
0x18000dc87  jnz     short loc_18000DC92
0x18000dc89  mov     eax, [rdx+0Ch]
0x18000dc8c  cmp     [r9+0Ch], eax
0x18000dc90  jz      short loc_18000DC9D
0x18000dc92  add     rcx, 8
0x18000dc96  cmp     rcx, r8
0x18000dc99  jb      short loc_18000DC5F
0x18000dc9b  jmp     short loc_18000DCF9
0x18000dc9d  lea     rdi, [rsi+20h]
0x18000dca1  cmp     [rdi], rbx
0x18000dca4  jnz     short loc_18000DCDE
0x18000dca6  lea     rcx, stru_180017370; lpCriticalSection
0x18000dcad  call    cs:__imp_EnterCriticalSection
0x18000dcb3  cmp     [rdi], rbx
0x18000dcb6  jnz     short loc_18000DCD1
0x18000dcb8  mov     r8, rdi
0x18000dcbb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000dcc2  mov     rcx, [rsi+18h]
0x18000dcc6  mov     rax, [rsi+10h]
0x18000dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccf  mov     ebx, eax
0x18000dcd1  lea     rcx, stru_180017370; lpCriticalSection
0x18000dcd8  call    cs:__imp_LeaveCriticalSection
0x18000dcde  mov     rcx, [rdi]
0x18000dce1  test    rcx, rcx
0x18000dce4  jz      short loc_18000DCF9
0x18000dce6  mov     rax, [rcx]
0x18000dce9  mov     r8, r14
0x18000dcec  mov     rdx, rbp
0x18000dcef  mov     rax, [rax]
0x18000dcf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf7  mov     ebx, eax
0x18000dcf9  cmp     qword ptr [r14], 0
0x18000dcfd  jnz     short loc_18000DD09
0x18000dcff  mov     eax, 80040111h
0x18000dd04  test    ebx, ebx
0x18000dd06  cmovz   ebx, eax
0x18000dd09  mov     eax, ebx
0x18000dd0b  add     rsp, 20h
0x18000dd0f  pop     r14
0x18000dd11  pop     rdi
0x18000dd12  pop     rsi
0x18000dd13  pop     rbp
0x18000dd14  pop     rbx
0x18000dd15  retn
```
