# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18001fb68`
- end: `0x18001fc6e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800226f0`

## callees

- `0x18001fb68`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc30`

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
  for ( i = (__int64 *)off_1800350E0; i < (__int64 *)off_1800350E8; ++i )
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
0x18001fb68  push    rbx
0x18001fb6a  push    rbp
0x18001fb6b  push    rsi
0x18001fb6c  push    rdi
0x18001fb6d  push    r14
0x18001fb6f  sub     rsp, 20h
0x18001fb73  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18001fb7a  mov     r14, r9
0x18001fb7d  mov     r9, rdx
0x18001fb80  mov     rbp, r8
0x18001fb83  jnz     short loc_18001FB8F
0x18001fb85  mov     eax, 8000FFFFh
0x18001fb8a  jmp     loc_18001FC63
0x18001fb8f  test    r14, r14
0x18001fb92  jnz     short loc_18001FB9E
0x18001fb94  mov     eax, 80004003h
0x18001fb99  jmp     loc_18001FC63
0x18001fb9e  mov     qword ptr [r14], 0
0x18001fba5  xor     ebx, ebx
0x18001fba7  mov     rcx, cs:off_1800350E0
0x18001fbae  mov     r8, cs:off_1800350E8
0x18001fbb5  jmp     short loc_18001FBEE
0x18001fbb7  mov     rsi, [rcx]
0x18001fbba  test    rsi, rsi
0x18001fbbd  jz      short loc_18001FBEA
0x18001fbbf  cmp     [rsi+10h], rbx
0x18001fbc3  jz      short loc_18001FBEA
0x18001fbc5  mov     rdx, [rsi]
0x18001fbc8  mov     eax, [rdx]
0x18001fbca  cmp     [r9], eax
0x18001fbcd  jnz     short loc_18001FBEA
0x18001fbcf  mov     eax, [rdx+4]
0x18001fbd2  cmp     [r9+4], eax
0x18001fbd6  jnz     short loc_18001FBEA
0x18001fbd8  mov     eax, [rdx+8]
0x18001fbdb  cmp     [r9+8], eax
0x18001fbdf  jnz     short loc_18001FBEA
0x18001fbe1  mov     eax, [rdx+0Ch]
0x18001fbe4  cmp     [r9+0Ch], eax
0x18001fbe8  jz      short loc_18001FBF5
0x18001fbea  add     rcx, 8
0x18001fbee  cmp     rcx, r8
0x18001fbf1  jb      short loc_18001FBB7
0x18001fbf3  jmp     short loc_18001FC51
0x18001fbf5  lea     rdi, [rsi+20h]
0x18001fbf9  cmp     [rdi], rbx
0x18001fbfc  jnz     short loc_18001FC36
0x18001fbfe  lea     rcx, CriticalSection; lpCriticalSection
0x18001fc05  call    cs:__imp_EnterCriticalSection
0x18001fc0b  cmp     [rdi], rbx
0x18001fc0e  jnz     short loc_18001FC29
0x18001fc10  mov     rcx, [rsi+18h]
0x18001fc14  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001fc1b  mov     rax, [rsi+10h]
0x18001fc1f  mov     r8, rdi
0x18001fc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc27  mov     ebx, eax
0x18001fc29  lea     rcx, CriticalSection; lpCriticalSection
0x18001fc30  call    cs:__imp_LeaveCriticalSection
0x18001fc36  mov     rcx, [rdi]
0x18001fc39  test    rcx, rcx
0x18001fc3c  jz      short loc_18001FC51
0x18001fc3e  mov     rax, [rcx]
0x18001fc41  mov     r8, r14
0x18001fc44  mov     rdx, rbp
0x18001fc47  mov     rax, [rax]
0x18001fc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc4f  mov     ebx, eax
0x18001fc51  cmp     qword ptr [r14], 0
0x18001fc55  jnz     short loc_18001FC61
0x18001fc57  test    ebx, ebx
0x18001fc59  mov     eax, 80040111h
0x18001fc5e  cmovz   ebx, eax
0x18001fc61  mov     eax, ebx
0x18001fc63  add     rsp, 20h
0x18001fc67  pop     r14
0x18001fc69  pop     rdi
0x18001fc6a  pop     rsi
0x18001fc6b  pop     rbp
0x18001fc6c  pop     rbx
0x18001fc6d  retn
```
