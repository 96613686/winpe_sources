# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800054d4`
- end: `0x1800055d8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ac0`
- `0x180005b60`
- `0x180005b80`

## callees

- `0x1800054d4`
- `0x18000b010`

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
0x1800054d4  push    rbx
0x1800054d6  push    rbp
0x1800054d7  push    rsi
0x1800054d8  push    rdi
0x1800054d9  push    r14
0x1800054db  sub     rsp, 30h
0x1800054df  mov     rsi, r9
0x1800054e2  mov     rdi, r8
0x1800054e5  mov     rbx, rdx
0x1800054e8  mov     r14, rcx
0x1800054eb  test    rcx, rcx
0x1800054ee  jz      loc_1800055C8
0x1800054f4  test    rdx, rdx
0x1800054f7  jz      loc_1800055C8
0x1800054fd  test    r9, r9
0x180005500  jnz     short loc_18000550C
0x180005502  mov     eax, 80004003h
0x180005507  jmp     loc_1800055CD
0x18000550c  mov     qword ptr [r9], 0
0x180005513  cmp     dword ptr [r8], 0
0x180005517  jnz     short loc_180005551
0x180005519  cmp     dword ptr [r8+4], 0
0x18000551e  jnz     short loc_180005551
0x180005520  cmp     dword ptr [r8+8], 0C0h
0x180005528  jnz     short loc_180005551
0x18000552a  cmp     dword ptr [r8+0Ch], 46000000h
0x180005532  jnz     short loc_180005551
0x180005534  mov     rbx, [rdx+8]
0x180005538  add     rbx, r14
0x18000553b  mov     rcx, rbx
0x18000553e  mov     rax, [rbx]
0x180005541  mov     rax, [rax+8]
0x180005545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554a  xor     eax, eax
0x18000554c  mov     [rsi], rbx
0x18000554f  jmp     short loc_1800055CD
0x180005551  cmp     qword ptr [rdx+10h], 0
0x180005556  jz      short loc_1800055B8
0x180005558  mov     rcx, [rbx]
0x18000555b  test    rcx, rcx
0x18000555e  jnz     short loc_180005565
0x180005560  lea     ebp, [rcx+1]
0x180005563  jmp     short loc_180005585
0x180005565  mov     eax, [rdi]
0x180005567  cmp     [rcx], eax
0x180005569  jnz     short loc_1800055AD
0x18000556b  mov     eax, [rdi+4]
0x18000556e  cmp     [rcx+4], eax
0x180005571  jnz     short loc_1800055AD
0x180005573  mov     eax, [rdi+8]
0x180005576  cmp     [rcx+8], eax
0x180005579  jnz     short loc_1800055AD
0x18000557b  mov     eax, [rdi+0Ch]
0x18000557e  cmp     [rcx+0Ch], eax
0x180005581  jnz     short loc_1800055AD
0x180005583  xor     ebp, ebp
0x180005585  mov     rax, [rbx+10h]
0x180005589  cmp     rax, 1
0x18000558d  jz      short loc_1800055BF
0x18000558f  mov     r9, [rbx+8]
0x180005593  mov     r8, rsi
0x180005596  mov     rdx, rdi
0x180005599  mov     rcx, r14
0x18000559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a1  test    eax, eax
0x1800055a3  jz      short loc_1800055CD
0x1800055a5  test    ebp, ebp
0x1800055a7  jnz     short loc_1800055AD
0x1800055a9  test    eax, eax
0x1800055ab  js      short loc_1800055CD
0x1800055ad  add     rbx, 18h
0x1800055b1  cmp     qword ptr [rbx+10h], 0
0x1800055b6  jnz     short loc_180005558
0x1800055b8  mov     eax, 80004002h
0x1800055bd  jmp     short loc_1800055CD
0x1800055bf  mov     rbx, [rbx+8]
0x1800055c3  jmp     loc_180005538
0x1800055c8  mov     eax, 80070057h
0x1800055cd  add     rsp, 30h
0x1800055d1  pop     r14
0x1800055d3  pop     rdi
0x1800055d4  pop     rsi
0x1800055d5  pop     rbp
0x1800055d6  pop     rbx
0x1800055d7  retn
```
