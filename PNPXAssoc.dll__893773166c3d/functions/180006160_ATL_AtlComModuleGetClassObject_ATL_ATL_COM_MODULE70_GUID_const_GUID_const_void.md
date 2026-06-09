# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006160`
- end: `0x180006266`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008fc0`

## callees

- `0x180006160`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180006228`
- `KERNEL32!LeaveCriticalSection` at `0x180006228`
- `KERNEL32!EnterCriticalSection` at `0x1800061fd`
- `KERNEL32!EnterCriticalSection` at `0x1800061fd`

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
  for ( i = off_18001A200[0]; i < off_18001A208; ++i )
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
            EnterCriticalSection(&stru_18001A210);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_18001A210);
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
0x180006160  push    rbx
0x180006162  push    rbp
0x180006163  push    rsi
0x180006164  push    rdi
0x180006165  push    r14
0x180006167  sub     rsp, 20h
0x18000616b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180006172  mov     r14, r9
0x180006175  mov     r9, rdx
0x180006178  mov     rbp, r8
0x18000617b  jnz     short loc_180006187
0x18000617d  mov     eax, 8000FFFFh
0x180006182  jmp     loc_18000625B
0x180006187  test    r14, r14
0x18000618a  jnz     short loc_180006196
0x18000618c  mov     eax, 80004003h
0x180006191  jmp     loc_18000625B
0x180006196  mov     qword ptr [r14], 0
0x18000619d  xor     ebx, ebx
0x18000619f  mov     rcx, cs:off_18001A200
0x1800061a6  mov     r8, cs:off_18001A208
0x1800061ad  jmp     short loc_1800061E6
0x1800061af  mov     rsi, [rcx]
0x1800061b2  test    rsi, rsi
0x1800061b5  jz      short loc_1800061E2
0x1800061b7  cmp     [rsi+10h], rbx
0x1800061bb  jz      short loc_1800061E2
0x1800061bd  mov     rdx, [rsi]
0x1800061c0  mov     eax, [rdx]
0x1800061c2  cmp     [r9], eax
0x1800061c5  jnz     short loc_1800061E2
0x1800061c7  mov     eax, [rdx+4]
0x1800061ca  cmp     [r9+4], eax
0x1800061ce  jnz     short loc_1800061E2
0x1800061d0  mov     eax, [rdx+8]
0x1800061d3  cmp     [r9+8], eax
0x1800061d7  jnz     short loc_1800061E2
0x1800061d9  mov     eax, [rdx+0Ch]
0x1800061dc  cmp     [r9+0Ch], eax
0x1800061e0  jz      short loc_1800061ED
0x1800061e2  add     rcx, 8
0x1800061e6  cmp     rcx, r8
0x1800061e9  jb      short loc_1800061AF
0x1800061eb  jmp     short loc_180006249
0x1800061ed  lea     rdi, [rsi+20h]
0x1800061f1  cmp     [rdi], rbx
0x1800061f4  jnz     short loc_18000622E
0x1800061f6  lea     rcx, stru_18001A210; lpCriticalSection
0x1800061fd  call    cs:__imp_EnterCriticalSection
0x180006203  cmp     [rdi], rbx
0x180006206  jnz     short loc_180006221
0x180006208  mov     rcx, [rsi+18h]
0x18000620c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006213  mov     rax, [rsi+10h]
0x180006217  mov     r8, rdi
0x18000621a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000621f  mov     ebx, eax
0x180006221  lea     rcx, stru_18001A210; lpCriticalSection
0x180006228  call    cs:__imp_LeaveCriticalSection
0x18000622e  mov     rcx, [rdi]
0x180006231  test    rcx, rcx
0x180006234  jz      short loc_180006249
0x180006236  mov     rax, [rcx]
0x180006239  mov     r8, r14
0x18000623c  mov     rdx, rbp
0x18000623f  mov     rax, [rax]
0x180006242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006247  mov     ebx, eax
0x180006249  cmp     qword ptr [r14], 0
0x18000624d  jnz     short loc_180006259
0x18000624f  test    ebx, ebx
0x180006251  mov     eax, 80040111h
0x180006256  cmovz   ebx, eax
0x180006259  mov     eax, ebx
0x18000625b  add     rsp, 20h
0x18000625f  pop     r14
0x180006261  pop     rdi
0x180006262  pop     rsi
0x180006263  pop     rbp
0x180006264  pop     rbx
0x180006265  retn
```
