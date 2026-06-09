# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003da8`
- end: `0x180003eae`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a40`

## callees

- `0x180003da8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e45`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_1800270D0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800270D8; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *((_QWORD *)v10 + 2) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)((char *)v10 + 32);
          if ( !*((_QWORD *)v10 + 4) )
          {
            EnterCriticalSection(&stru_1800270E0);
            if ( !*v12 )
              v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                     *((_QWORD *)v10 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v10 + 32);
            LeaveCriticalSection(&stru_1800270E0);
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
0x180003da8  push    rbx
0x180003daa  push    rbp
0x180003dab  push    rsi
0x180003dac  push    rdi
0x180003dad  push    r14
0x180003daf  sub     rsp, 20h
0x180003db3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180003dba  mov     r14, r9
0x180003dbd  mov     r9, rdx
0x180003dc0  mov     rbp, r8
0x180003dc3  jnz     short loc_180003DCF
0x180003dc5  mov     eax, 8000FFFFh
0x180003dca  jmp     loc_180003EA3
0x180003dcf  test    r14, r14
0x180003dd2  jnz     short loc_180003DDE
0x180003dd4  mov     eax, 80004003h
0x180003dd9  jmp     loc_180003EA3
0x180003dde  mov     qword ptr [r14], 0
0x180003de5  xor     ebx, ebx
0x180003de7  mov     rcx, cs:off_1800270D0
0x180003dee  mov     r8, cs:off_1800270D8
0x180003df5  jmp     short loc_180003E2E
0x180003df7  mov     rsi, [rcx]
0x180003dfa  test    rsi, rsi
0x180003dfd  jz      short loc_180003E2A
0x180003dff  cmp     [rsi+10h], rbx
0x180003e03  jz      short loc_180003E2A
0x180003e05  mov     rdx, [rsi]
0x180003e08  mov     eax, [rdx]
0x180003e0a  cmp     [r9], eax
0x180003e0d  jnz     short loc_180003E2A
0x180003e0f  mov     eax, [rdx+4]
0x180003e12  cmp     [r9+4], eax
0x180003e16  jnz     short loc_180003E2A
0x180003e18  mov     eax, [rdx+8]
0x180003e1b  cmp     [r9+8], eax
0x180003e1f  jnz     short loc_180003E2A
0x180003e21  mov     eax, [rdx+0Ch]
0x180003e24  cmp     [r9+0Ch], eax
0x180003e28  jz      short loc_180003E35
0x180003e2a  add     rcx, 8
0x180003e2e  cmp     rcx, r8
0x180003e31  jb      short loc_180003DF7
0x180003e33  jmp     short loc_180003E91
0x180003e35  lea     rdi, [rsi+20h]
0x180003e39  cmp     [rdi], rbx
0x180003e3c  jnz     short loc_180003E76
0x180003e3e  lea     rcx, stru_1800270E0; lpCriticalSection
0x180003e45  call    cs:__imp_EnterCriticalSection
0x180003e4b  cmp     [rdi], rbx
0x180003e4e  jnz     short loc_180003E69
0x180003e50  mov     rcx, [rsi+18h]
0x180003e54  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003e5b  mov     rax, [rsi+10h]
0x180003e5f  mov     r8, rdi
0x180003e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e67  mov     ebx, eax
0x180003e69  lea     rcx, stru_1800270E0; lpCriticalSection
0x180003e70  call    cs:__imp_LeaveCriticalSection
0x180003e76  mov     rcx, [rdi]
0x180003e79  test    rcx, rcx
0x180003e7c  jz      short loc_180003E91
0x180003e7e  mov     rax, [rcx]
0x180003e81  mov     r8, r14
0x180003e84  mov     rdx, rbp
0x180003e87  mov     rax, [rax]
0x180003e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8f  mov     ebx, eax
0x180003e91  cmp     qword ptr [r14], 0
0x180003e95  jnz     short loc_180003EA1
0x180003e97  test    ebx, ebx
0x180003e99  mov     eax, 80040111h
0x180003e9e  cmovz   ebx, eax
0x180003ea1  mov     eax, ebx
0x180003ea3  add     rsp, 20h
0x180003ea7  pop     r14
0x180003ea9  pop     rdi
0x180003eaa  pop     rsi
0x180003eab  pop     rbp
0x180003eac  pop     rbx
0x180003ead  retn
```
