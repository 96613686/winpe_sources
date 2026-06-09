# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800098f0`
- end: `0x1800099f4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009a30`
- `0x180009a50`
- `0x18000af50`
- `0x18000afe0`
- `0x18000c220`
- `0x18000c290`
- `0x18000d0c0`

## callees

- `0x1800098f0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x1800098f0  push    rbx
0x1800098f2  push    rbp
0x1800098f3  push    rsi
0x1800098f4  push    rdi
0x1800098f5  push    r14
0x1800098f7  sub     rsp, 30h
0x1800098fb  mov     rsi, r9
0x1800098fe  mov     rdi, r8
0x180009901  mov     rbx, rdx
0x180009904  mov     r14, rcx
0x180009907  test    rcx, rcx
0x18000990a  jz      loc_1800099E4
0x180009910  test    rdx, rdx
0x180009913  jz      loc_1800099E4
0x180009919  test    r9, r9
0x18000991c  jnz     short loc_180009928
0x18000991e  mov     eax, 80004003h
0x180009923  jmp     loc_1800099E9
0x180009928  mov     qword ptr [r9], 0
0x18000992f  cmp     dword ptr [r8], 0
0x180009933  jnz     short loc_18000996D
0x180009935  cmp     dword ptr [r8+4], 0
0x18000993a  jnz     short loc_18000996D
0x18000993c  cmp     dword ptr [r8+8], 0C0h
0x180009944  jnz     short loc_18000996D
0x180009946  cmp     dword ptr [r8+0Ch], 46000000h
0x18000994e  jnz     short loc_18000996D
0x180009950  mov     rbx, [rdx+8]
0x180009954  add     rbx, r14
0x180009957  mov     rcx, rbx
0x18000995a  mov     rax, [rbx]
0x18000995d  mov     rax, [rax+8]
0x180009961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009966  xor     eax, eax
0x180009968  mov     [rsi], rbx
0x18000996b  jmp     short loc_1800099E9
0x18000996d  cmp     qword ptr [rdx+10h], 0
0x180009972  jz      short loc_1800099D4
0x180009974  mov     rcx, [rbx]
0x180009977  test    rcx, rcx
0x18000997a  jnz     short loc_180009981
0x18000997c  lea     ebp, [rcx+1]
0x18000997f  jmp     short loc_1800099A1
0x180009981  mov     eax, [rdi]
0x180009983  cmp     [rcx], eax
0x180009985  jnz     short loc_1800099C9
0x180009987  mov     eax, [rdi+4]
0x18000998a  cmp     [rcx+4], eax
0x18000998d  jnz     short loc_1800099C9
0x18000998f  mov     eax, [rdi+8]
0x180009992  cmp     [rcx+8], eax
0x180009995  jnz     short loc_1800099C9
0x180009997  mov     eax, [rdi+0Ch]
0x18000999a  cmp     [rcx+0Ch], eax
0x18000999d  jnz     short loc_1800099C9
0x18000999f  xor     ebp, ebp
0x1800099a1  mov     rax, [rbx+10h]
0x1800099a5  cmp     rax, 1
0x1800099a9  jz      short loc_1800099DB
0x1800099ab  mov     r9, [rbx+8]
0x1800099af  mov     r8, rsi
0x1800099b2  mov     rdx, rdi
0x1800099b5  mov     rcx, r14
0x1800099b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099bd  test    eax, eax
0x1800099bf  jz      short loc_1800099E9
0x1800099c1  test    ebp, ebp
0x1800099c3  jnz     short loc_1800099C9
0x1800099c5  test    eax, eax
0x1800099c7  js      short loc_1800099E9
0x1800099c9  add     rbx, 18h
0x1800099cd  cmp     qword ptr [rbx+10h], 0
0x1800099d2  jnz     short loc_180009974
0x1800099d4  mov     eax, 80004002h
0x1800099d9  jmp     short loc_1800099E9
0x1800099db  mov     rbx, [rbx+8]
0x1800099df  jmp     loc_180009954
0x1800099e4  mov     eax, 80070057h
0x1800099e9  add     rsp, 30h
0x1800099ed  pop     r14
0x1800099ef  pop     rdi
0x1800099f0  pop     rsi
0x1800099f1  pop     rbp
0x1800099f2  pop     rbx
0x1800099f3  retn
```
