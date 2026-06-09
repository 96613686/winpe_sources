# ATL::CAtlDllModuleT<CSlayeruiModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180004324`
- end: `0x18000442a`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCSlayeruiModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800086c0`

## callees

- `0x180004324`
- `0x180017010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800043c1`
- `KERNEL32!EnterCriticalSection` at `0x1800043c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800043ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800043ec`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<CSlayeruiModule>::DllGetClassObject(
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
      for ( i = off_1800202E0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800202E8; ++i )
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
                EnterCriticalSection(&stru_1800202F0);
                if ( !*v11 )
                  v7 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                         *((_QWORD *)v9 + 3),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         (__int64)v9 + 32);
                LeaveCriticalSection(&stru_1800202F0);
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
0x180004324  push    rbx
0x180004326  push    rbp
0x180004327  push    rsi
0x180004328  push    rdi
0x180004329  push    r14
0x18000432b  sub     rsp, 20h
0x18000432f  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180004336  mov     r14, r9
0x180004339  mov     r9, rdx
0x18000433c  mov     rbp, r8
0x18000433f  jnz     short loc_18000434B
0x180004341  mov     ebx, 8000FFFFh
0x180004346  jmp     loc_18000441D
0x18000434b  test    r14, r14
0x18000434e  jnz     short loc_18000435A
0x180004350  mov     ebx, 80004003h
0x180004355  jmp     loc_18000441D
0x18000435a  mov     qword ptr [r14], 0
0x180004361  xor     ebx, ebx
0x180004363  mov     rcx, cs:off_1800202E0
0x18000436a  mov     r8, cs:off_1800202E8
0x180004371  jmp     short loc_1800043AA
0x180004373  mov     rsi, [rcx]
0x180004376  test    rsi, rsi
0x180004379  jz      short loc_1800043A6
0x18000437b  cmp     [rsi+10h], rbx
0x18000437f  jz      short loc_1800043A6
0x180004381  mov     rdx, [rsi]
0x180004384  mov     eax, [rdx]
0x180004386  cmp     [r9], eax
0x180004389  jnz     short loc_1800043A6
0x18000438b  mov     eax, [rdx+4]
0x18000438e  cmp     [r9+4], eax
0x180004392  jnz     short loc_1800043A6
0x180004394  mov     eax, [rdx+8]
0x180004397  cmp     [r9+8], eax
0x18000439b  jnz     short loc_1800043A6
0x18000439d  mov     eax, [rdx+0Ch]
0x1800043a0  cmp     [r9+0Ch], eax
0x1800043a4  jz      short loc_1800043B1
0x1800043a6  add     rcx, 8
0x1800043aa  cmp     rcx, r8
0x1800043ad  jb      short loc_180004373
0x1800043af  jmp     short loc_18000440D
0x1800043b1  lea     rdi, [rsi+20h]
0x1800043b5  cmp     [rdi], rbx
0x1800043b8  jnz     short loc_1800043F2
0x1800043ba  lea     rcx, stru_1800202F0; lpCriticalSection
0x1800043c1  call    cs:__imp_EnterCriticalSection
0x1800043c7  cmp     [rdi], rbx
0x1800043ca  jnz     short loc_1800043E5
0x1800043cc  mov     rcx, [rsi+18h]
0x1800043d0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800043d7  mov     rax, [rsi+10h]
0x1800043db  mov     r8, rdi
0x1800043de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e3  mov     ebx, eax
0x1800043e5  lea     rcx, stru_1800202F0; lpCriticalSection
0x1800043ec  call    cs:__imp_LeaveCriticalSection
0x1800043f2  mov     rcx, [rdi]
0x1800043f5  test    rcx, rcx
0x1800043f8  jz      short loc_18000440D
0x1800043fa  mov     rax, [rcx]
0x1800043fd  mov     r8, r14
0x180004400  mov     rdx, rbp
0x180004403  mov     rax, [rax]
0x180004406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000440b  mov     ebx, eax
0x18000440d  cmp     qword ptr [r14], 0
0x180004411  jnz     short loc_18000441D
0x180004413  test    ebx, ebx
0x180004415  mov     eax, 80040111h
0x18000441a  cmovz   ebx, eax
0x18000441d  mov     eax, ebx
0x18000441f  add     rsp, 20h
0x180004423  pop     r14
0x180004425  pop     rdi
0x180004426  pop     rsi
0x180004427  pop     rbp
0x180004428  pop     rbx
0x180004429  retn
```
