# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000398c`
- end: `0x180003a92`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800068f0`

## callees

- `0x18000398c`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003a29`
- `KERNEL32!EnterCriticalSection` at `0x180003a29`
- `KERNEL32!LeaveCriticalSection` at `0x180003a54`
- `KERNEL32!LeaveCriticalSection` at `0x180003a54`

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
  for ( i = (__int64 *)off_180013110[0]; i < (__int64 *)off_180013118; ++i )
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
0x18000398c  push    rbx
0x18000398e  push    rbp
0x18000398f  push    rsi
0x180003990  push    rdi
0x180003991  push    r14
0x180003993  sub     rsp, 20h
0x180003997  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000399e  mov     r14, r9
0x1800039a1  mov     r9, rdx
0x1800039a4  mov     rbp, r8
0x1800039a7  jnz     short loc_1800039B3
0x1800039a9  mov     eax, 8000FFFFh
0x1800039ae  jmp     loc_180003A87
0x1800039b3  test    r14, r14
0x1800039b6  jnz     short loc_1800039C2
0x1800039b8  mov     eax, 80004003h
0x1800039bd  jmp     loc_180003A87
0x1800039c2  mov     qword ptr [r14], 0
0x1800039c9  xor     ebx, ebx
0x1800039cb  mov     rcx, cs:off_180013110
0x1800039d2  mov     r8, cs:off_180013118
0x1800039d9  jmp     short loc_180003A12
0x1800039db  mov     rsi, [rcx]
0x1800039de  test    rsi, rsi
0x1800039e1  jz      short loc_180003A0E
0x1800039e3  cmp     [rsi+10h], rbx
0x1800039e7  jz      short loc_180003A0E
0x1800039e9  mov     rdx, [rsi]
0x1800039ec  mov     eax, [rdx]
0x1800039ee  cmp     [r9], eax
0x1800039f1  jnz     short loc_180003A0E
0x1800039f3  mov     eax, [rdx+4]
0x1800039f6  cmp     [r9+4], eax
0x1800039fa  jnz     short loc_180003A0E
0x1800039fc  mov     eax, [rdx+8]
0x1800039ff  cmp     [r9+8], eax
0x180003a03  jnz     short loc_180003A0E
0x180003a05  mov     eax, [rdx+0Ch]
0x180003a08  cmp     [r9+0Ch], eax
0x180003a0c  jz      short loc_180003A19
0x180003a0e  add     rcx, 8
0x180003a12  cmp     rcx, r8
0x180003a15  jb      short loc_1800039DB
0x180003a17  jmp     short loc_180003A75
0x180003a19  lea     rdi, [rsi+20h]
0x180003a1d  cmp     [rdi], rbx
0x180003a20  jnz     short loc_180003A5A
0x180003a22  lea     rcx, CriticalSection; lpCriticalSection
0x180003a29  call    cs:__imp_EnterCriticalSection
0x180003a2f  cmp     [rdi], rbx
0x180003a32  jnz     short loc_180003A4D
0x180003a34  mov     rcx, [rsi+18h]
0x180003a38  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003a3f  mov     rax, [rsi+10h]
0x180003a43  mov     r8, rdi
0x180003a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4b  mov     ebx, eax
0x180003a4d  lea     rcx, CriticalSection; lpCriticalSection
0x180003a54  call    cs:__imp_LeaveCriticalSection
0x180003a5a  mov     rcx, [rdi]
0x180003a5d  test    rcx, rcx
0x180003a60  jz      short loc_180003A75
0x180003a62  mov     rax, [rcx]
0x180003a65  mov     r8, r14
0x180003a68  mov     rdx, rbp
0x180003a6b  mov     rax, [rax]
0x180003a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a73  mov     ebx, eax
0x180003a75  cmp     qword ptr [r14], 0
0x180003a79  jnz     short loc_180003A85
0x180003a7b  test    ebx, ebx
0x180003a7d  mov     eax, 80040111h
0x180003a82  cmovz   ebx, eax
0x180003a85  mov     eax, ebx
0x180003a87  add     rsp, 20h
0x180003a8b  pop     r14
0x180003a8d  pop     rdi
0x180003a8e  pop     rsi
0x180003a8f  pop     rbp
0x180003a90  pop     rbx
0x180003a91  retn
```
