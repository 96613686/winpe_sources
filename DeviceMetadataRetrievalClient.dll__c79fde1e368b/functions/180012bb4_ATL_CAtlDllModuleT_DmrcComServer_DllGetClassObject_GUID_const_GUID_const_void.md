# ATL::CAtlDllModuleT<DmrcComServer>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180012bb4`
- end: `0x180012cba`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VDmrcComServer@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012dd0`

## callees

- `0x180012bb4`
- `0x180014010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012c51`
- `KERNEL32!EnterCriticalSection` at `0x180012c51`
- `KERNEL32!LeaveCriticalSection` at `0x180012c7c`
- `KERNEL32!LeaveCriticalSection` at `0x180012c7c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<DmrcComServer>::DllGetClassObject(
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
      for ( i = off_18001E320; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001E328; ++i )
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
                EnterCriticalSection(&CriticalSection);
                if ( !*v11 )
                  v7 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                         *((_QWORD *)v9 + 3),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         (__int64)v9 + 32);
                LeaveCriticalSection(&CriticalSection);
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
0x180012bb4  push    rbx
0x180012bb6  push    rbp
0x180012bb7  push    rsi
0x180012bb8  push    rdi
0x180012bb9  push    r14
0x180012bbb  sub     rsp, 20h
0x180012bbf  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180012bc6  mov     r14, r9
0x180012bc9  mov     r9, rdx
0x180012bcc  mov     rbp, r8
0x180012bcf  jnz     short loc_180012BDB
0x180012bd1  mov     ebx, 8000FFFFh
0x180012bd6  jmp     loc_180012CAD
0x180012bdb  test    r14, r14
0x180012bde  jnz     short loc_180012BEA
0x180012be0  mov     ebx, 80004003h
0x180012be5  jmp     loc_180012CAD
0x180012bea  mov     qword ptr [r14], 0
0x180012bf1  xor     ebx, ebx
0x180012bf3  mov     rcx, cs:off_18001E320
0x180012bfa  mov     r8, cs:off_18001E328
0x180012c01  jmp     short loc_180012C3A
0x180012c03  mov     rsi, [rcx]
0x180012c06  test    rsi, rsi
0x180012c09  jz      short loc_180012C36
0x180012c0b  cmp     [rsi+10h], rbx
0x180012c0f  jz      short loc_180012C36
0x180012c11  mov     rdx, [rsi]
0x180012c14  mov     eax, [rdx]
0x180012c16  cmp     [r9], eax
0x180012c19  jnz     short loc_180012C36
0x180012c1b  mov     eax, [rdx+4]
0x180012c1e  cmp     [r9+4], eax
0x180012c22  jnz     short loc_180012C36
0x180012c24  mov     eax, [rdx+8]
0x180012c27  cmp     [r9+8], eax
0x180012c2b  jnz     short loc_180012C36
0x180012c2d  mov     eax, [rdx+0Ch]
0x180012c30  cmp     [r9+0Ch], eax
0x180012c34  jz      short loc_180012C41
0x180012c36  add     rcx, 8
0x180012c3a  cmp     rcx, r8
0x180012c3d  jb      short loc_180012C03
0x180012c3f  jmp     short loc_180012C9D
0x180012c41  lea     rdi, [rsi+20h]
0x180012c45  cmp     [rdi], rbx
0x180012c48  jnz     short loc_180012C82
0x180012c4a  lea     rcx, CriticalSection; lpCriticalSection
0x180012c51  call    cs:__imp_EnterCriticalSection
0x180012c57  cmp     [rdi], rbx
0x180012c5a  jnz     short loc_180012C75
0x180012c5c  mov     rcx, [rsi+18h]
0x180012c60  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180012c67  mov     rax, [rsi+10h]
0x180012c6b  mov     r8, rdi
0x180012c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c73  mov     ebx, eax
0x180012c75  lea     rcx, CriticalSection; lpCriticalSection
0x180012c7c  call    cs:__imp_LeaveCriticalSection
0x180012c82  mov     rcx, [rdi]
0x180012c85  test    rcx, rcx
0x180012c88  jz      short loc_180012C9D
0x180012c8a  mov     rax, [rcx]
0x180012c8d  mov     r8, r14
0x180012c90  mov     rdx, rbp
0x180012c93  mov     rax, [rax]
0x180012c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9b  mov     ebx, eax
0x180012c9d  cmp     qword ptr [r14], 0
0x180012ca1  jnz     short loc_180012CAD
0x180012ca3  test    ebx, ebx
0x180012ca5  mov     eax, 80040111h
0x180012caa  cmovz   ebx, eax
0x180012cad  mov     eax, ebx
0x180012caf  add     rsp, 20h
0x180012cb3  pop     r14
0x180012cb5  pop     rdi
0x180012cb6  pop     rsi
0x180012cb7  pop     rbp
0x180012cb8  pop     rbx
0x180012cb9  retn
```
