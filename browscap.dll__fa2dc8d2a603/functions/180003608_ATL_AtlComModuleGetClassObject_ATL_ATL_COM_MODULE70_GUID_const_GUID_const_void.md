# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003608`
- end: `0x18000370e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007110`

## callees

- `0x180003608`
- `0x18000d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800036d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800036d0`
- `KERNEL32!EnterCriticalSection` at `0x1800036a5`
- `KERNEL32!EnterCriticalSection` at `0x1800036a5`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = (__int64 *)off_180012140[0]; i < (__int64 *)off_180012148; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180003608  push    rbx
0x18000360a  push    rbp
0x18000360b  push    rsi
0x18000360c  push    rdi
0x18000360d  push    r14
0x18000360f  sub     rsp, 20h
0x180003613  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000361a  mov     r14, r9
0x18000361d  mov     r9, rdx
0x180003620  mov     rbp, r8
0x180003623  jnz     short loc_18000362F
0x180003625  mov     eax, 8000FFFFh
0x18000362a  jmp     loc_180003703
0x18000362f  test    r14, r14
0x180003632  jnz     short loc_18000363E
0x180003634  mov     eax, 80004003h
0x180003639  jmp     loc_180003703
0x18000363e  mov     qword ptr [r14], 0
0x180003645  xor     ebx, ebx
0x180003647  mov     rcx, cs:off_180012140
0x18000364e  mov     r8, cs:off_180012148
0x180003655  jmp     short loc_18000368E
0x180003657  mov     rsi, [rcx]
0x18000365a  test    rsi, rsi
0x18000365d  jz      short loc_18000368A
0x18000365f  cmp     [rsi+10h], rbx
0x180003663  jz      short loc_18000368A
0x180003665  mov     rdx, [rsi]
0x180003668  mov     eax, [rdx]
0x18000366a  cmp     [r9], eax
0x18000366d  jnz     short loc_18000368A
0x18000366f  mov     eax, [rdx+4]
0x180003672  cmp     [r9+4], eax
0x180003676  jnz     short loc_18000368A
0x180003678  mov     eax, [rdx+8]
0x18000367b  cmp     [r9+8], eax
0x18000367f  jnz     short loc_18000368A
0x180003681  mov     eax, [rdx+0Ch]
0x180003684  cmp     [r9+0Ch], eax
0x180003688  jz      short loc_180003695
0x18000368a  add     rcx, 8
0x18000368e  cmp     rcx, r8
0x180003691  jb      short loc_180003657
0x180003693  jmp     short loc_1800036F1
0x180003695  lea     rdi, [rsi+20h]
0x180003699  cmp     [rdi], rbx
0x18000369c  jnz     short loc_1800036D6
0x18000369e  lea     rcx, CriticalSection; lpCriticalSection
0x1800036a5  call    cs:__imp_EnterCriticalSection
0x1800036ab  cmp     [rdi], rbx
0x1800036ae  jnz     short loc_1800036C9
0x1800036b0  mov     rcx, [rsi+18h]
0x1800036b4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800036bb  mov     rax, [rsi+10h]
0x1800036bf  mov     r8, rdi
0x1800036c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c7  mov     ebx, eax
0x1800036c9  lea     rcx, CriticalSection; lpCriticalSection
0x1800036d0  call    cs:__imp_LeaveCriticalSection
0x1800036d6  mov     rcx, [rdi]
0x1800036d9  test    rcx, rcx
0x1800036dc  jz      short loc_1800036F1
0x1800036de  mov     rax, [rcx]
0x1800036e1  mov     r8, r14
0x1800036e4  mov     rdx, rbp
0x1800036e7  mov     rax, [rax]
0x1800036ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ef  mov     ebx, eax
0x1800036f1  cmp     qword ptr [r14], 0
0x1800036f5  jnz     short loc_180003701
0x1800036f7  test    ebx, ebx
0x1800036f9  mov     eax, 80040111h
0x1800036fe  cmovz   ebx, eax
0x180003701  mov     eax, ebx
0x180003703  add     rsp, 20h
0x180003707  pop     r14
0x180003709  pop     rdi
0x18000370a  pop     rsi
0x18000370b  pop     rbp
0x18000370c  pop     rbx
0x18000370d  retn
```
