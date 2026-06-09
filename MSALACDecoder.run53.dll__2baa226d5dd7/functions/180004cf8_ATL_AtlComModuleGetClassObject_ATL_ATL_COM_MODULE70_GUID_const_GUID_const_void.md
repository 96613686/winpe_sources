# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180004cf8`
- end: `0x180004dfe`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007320`

## callees

- `0x180004cf8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004dc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004dc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d95`

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
  for ( i = (__int64 *)off_18000F0A0; i < (__int64 *)off_18000F0A8; ++i )
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
0x180004cf8  push    rbx
0x180004cfa  push    rbp
0x180004cfb  push    rsi
0x180004cfc  push    rdi
0x180004cfd  push    r14
0x180004cff  sub     rsp, 20h
0x180004d03  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180004d0a  mov     r14, r9
0x180004d0d  mov     r9, rdx
0x180004d10  mov     rbp, r8
0x180004d13  jnz     short loc_180004D1F
0x180004d15  mov     eax, 8000FFFFh
0x180004d1a  jmp     loc_180004DF3
0x180004d1f  test    r14, r14
0x180004d22  jnz     short loc_180004D2E
0x180004d24  mov     eax, 80004003h
0x180004d29  jmp     loc_180004DF3
0x180004d2e  mov     qword ptr [r14], 0
0x180004d35  xor     ebx, ebx
0x180004d37  mov     rcx, cs:off_18000F0A0
0x180004d3e  mov     r8, cs:off_18000F0A8
0x180004d45  jmp     short loc_180004D7E
0x180004d47  mov     rsi, [rcx]
0x180004d4a  test    rsi, rsi
0x180004d4d  jz      short loc_180004D7A
0x180004d4f  cmp     [rsi+10h], rbx
0x180004d53  jz      short loc_180004D7A
0x180004d55  mov     rdx, [rsi]
0x180004d58  mov     eax, [rdx]
0x180004d5a  cmp     [r9], eax
0x180004d5d  jnz     short loc_180004D7A
0x180004d5f  mov     eax, [rdx+4]
0x180004d62  cmp     [r9+4], eax
0x180004d66  jnz     short loc_180004D7A
0x180004d68  mov     eax, [rdx+8]
0x180004d6b  cmp     [r9+8], eax
0x180004d6f  jnz     short loc_180004D7A
0x180004d71  mov     eax, [rdx+0Ch]
0x180004d74  cmp     [r9+0Ch], eax
0x180004d78  jz      short loc_180004D85
0x180004d7a  add     rcx, 8
0x180004d7e  cmp     rcx, r8
0x180004d81  jb      short loc_180004D47
0x180004d83  jmp     short loc_180004DE1
0x180004d85  lea     rdi, [rsi+20h]
0x180004d89  cmp     [rdi], rbx
0x180004d8c  jnz     short loc_180004DC6
0x180004d8e  lea     rcx, CriticalSection; lpCriticalSection
0x180004d95  call    cs:__imp_EnterCriticalSection
0x180004d9b  cmp     [rdi], rbx
0x180004d9e  jnz     short loc_180004DB9
0x180004da0  mov     rcx, [rsi+18h]
0x180004da4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004dab  mov     rax, [rsi+10h]
0x180004daf  mov     r8, rdi
0x180004db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db7  mov     ebx, eax
0x180004db9  lea     rcx, CriticalSection; lpCriticalSection
0x180004dc0  call    cs:__imp_LeaveCriticalSection
0x180004dc6  mov     rcx, [rdi]
0x180004dc9  test    rcx, rcx
0x180004dcc  jz      short loc_180004DE1
0x180004dce  mov     rax, [rcx]
0x180004dd1  mov     r8, r14
0x180004dd4  mov     rdx, rbp
0x180004dd7  mov     rax, [rax]
0x180004dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddf  mov     ebx, eax
0x180004de1  cmp     qword ptr [r14], 0
0x180004de5  jnz     short loc_180004DF1
0x180004de7  test    ebx, ebx
0x180004de9  mov     eax, 80040111h
0x180004dee  cmovz   ebx, eax
0x180004df1  mov     eax, ebx
0x180004df3  add     rsp, 20h
0x180004df7  pop     r14
0x180004df9  pop     rdi
0x180004dfa  pop     rsi
0x180004dfb  pop     rbp
0x180004dfc  pop     rbx
0x180004dfd  retn
```
