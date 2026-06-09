# ATL::CAtlDllModuleT<CUICOMModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800036fc`
- end: `0x180003802`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCUICOMModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004ea0`

## callees

- `0x1800036fc`
- `0x180007010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003799`
- `KERNEL32!EnterCriticalSection` at `0x180003799`
- `KERNEL32!LeaveCriticalSection` at `0x1800037c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800037c4`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<CUICOMModule>::DllGetClassObject(__int64 a1, _DWORD *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *i; // rcx
  __int64 v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( ATL::_AtlComModule )
  {
    if ( a4 )
    {
      *a4 = 0;
      v7 = 0;
      for ( i = off_18000B0B0;
            i < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18000B0B8;
            i = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)i + 8) )
      {
        v9 = *(_QWORD *)i;
        if ( *(_QWORD *)i )
        {
          if ( *(_QWORD *)(v9 + 16) )
          {
            v10 = *(_DWORD **)v9;
            if ( *a2 == **(_DWORD **)v9 && a2[1] == v10[1] && a2[2] == v10[2] && a2[3] == v10[3] )
            {
              v11 = (_QWORD *)(v9 + 32);
              if ( !*(_QWORD *)(v9 + 32) )
              {
                EnterCriticalSection(&CriticalSection);
                if ( !*v11 )
                  v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                         *(_QWORD *)(v9 + 24),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         v9 + 32);
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
0x1800036fc  push    rbx
0x1800036fe  push    rbp
0x1800036ff  push    rsi
0x180003700  push    rdi
0x180003701  push    r14
0x180003703  sub     rsp, 20h
0x180003707  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000370e  mov     r14, r9
0x180003711  mov     r9, rdx
0x180003714  mov     rbp, r8
0x180003717  jnz     short loc_180003723
0x180003719  mov     ebx, 8000FFFFh
0x18000371e  jmp     loc_1800037F5
0x180003723  test    r14, r14
0x180003726  jnz     short loc_180003732
0x180003728  mov     ebx, 80004003h
0x18000372d  jmp     loc_1800037F5
0x180003732  mov     qword ptr [r14], 0
0x180003739  xor     ebx, ebx
0x18000373b  mov     rcx, cs:off_18000B0B0
0x180003742  mov     r8, cs:off_18000B0B8
0x180003749  jmp     short loc_180003782
0x18000374b  mov     rsi, [rcx]
0x18000374e  test    rsi, rsi
0x180003751  jz      short loc_18000377E
0x180003753  cmp     [rsi+10h], rbx
0x180003757  jz      short loc_18000377E
0x180003759  mov     rdx, [rsi]
0x18000375c  mov     eax, [rdx]
0x18000375e  cmp     [r9], eax
0x180003761  jnz     short loc_18000377E
0x180003763  mov     eax, [rdx+4]
0x180003766  cmp     [r9+4], eax
0x18000376a  jnz     short loc_18000377E
0x18000376c  mov     eax, [rdx+8]
0x18000376f  cmp     [r9+8], eax
0x180003773  jnz     short loc_18000377E
0x180003775  mov     eax, [rdx+0Ch]
0x180003778  cmp     [r9+0Ch], eax
0x18000377c  jz      short loc_180003789
0x18000377e  add     rcx, 8
0x180003782  cmp     rcx, r8
0x180003785  jb      short loc_18000374B
0x180003787  jmp     short loc_1800037E5
0x180003789  lea     rdi, [rsi+20h]
0x18000378d  cmp     [rdi], rbx
0x180003790  jnz     short loc_1800037CA
0x180003792  lea     rcx, CriticalSection; lpCriticalSection
0x180003799  call    cs:__imp_EnterCriticalSection
0x18000379f  cmp     [rdi], rbx
0x1800037a2  jnz     short loc_1800037BD
0x1800037a4  mov     rcx, [rsi+18h]
0x1800037a8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800037af  mov     rax, [rsi+10h]
0x1800037b3  mov     r8, rdi
0x1800037b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bb  mov     ebx, eax
0x1800037bd  lea     rcx, CriticalSection; lpCriticalSection
0x1800037c4  call    cs:__imp_LeaveCriticalSection
0x1800037ca  mov     rcx, [rdi]
0x1800037cd  test    rcx, rcx
0x1800037d0  jz      short loc_1800037E5
0x1800037d2  mov     rax, [rcx]
0x1800037d5  mov     r8, r14
0x1800037d8  mov     rdx, rbp
0x1800037db  mov     rax, [rax]
0x1800037de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e3  mov     ebx, eax
0x1800037e5  cmp     qword ptr [r14], 0
0x1800037e9  jnz     short loc_1800037F5
0x1800037eb  test    ebx, ebx
0x1800037ed  mov     eax, 80040111h
0x1800037f2  cmovz   ebx, eax
0x1800037f5  mov     eax, ebx
0x1800037f7  add     rsp, 20h
0x1800037fb  pop     r14
0x1800037fd  pop     rdi
0x1800037fe  pop     rsi
0x1800037ff  pop     rbp
0x180003800  pop     rbx
0x180003801  retn
```
