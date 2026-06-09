# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180007440`
- end: `0x180007544`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e10`
- `0x180007ea0`
- `0x180007ec0`

## callees

- `0x180007440`
- `0x180013010`

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
0x180007440  push    rbx
0x180007442  push    rbp
0x180007443  push    rsi
0x180007444  push    rdi
0x180007445  push    r14
0x180007447  sub     rsp, 30h
0x18000744b  mov     rsi, r9
0x18000744e  mov     rdi, r8
0x180007451  mov     rbx, rdx
0x180007454  mov     r14, rcx
0x180007457  test    rcx, rcx
0x18000745a  jz      loc_180007534
0x180007460  test    rdx, rdx
0x180007463  jz      loc_180007534
0x180007469  test    r9, r9
0x18000746c  jnz     short loc_180007478
0x18000746e  mov     eax, 80004003h
0x180007473  jmp     loc_180007539
0x180007478  mov     qword ptr [r9], 0
0x18000747f  cmp     dword ptr [r8], 0
0x180007483  jnz     short loc_1800074BD
0x180007485  cmp     dword ptr [r8+4], 0
0x18000748a  jnz     short loc_1800074BD
0x18000748c  cmp     dword ptr [r8+8], 0C0h
0x180007494  jnz     short loc_1800074BD
0x180007496  cmp     dword ptr [r8+0Ch], 46000000h
0x18000749e  jnz     short loc_1800074BD
0x1800074a0  mov     rbx, [rdx+8]
0x1800074a4  add     rbx, r14
0x1800074a7  mov     rcx, rbx
0x1800074aa  mov     rax, [rbx]
0x1800074ad  mov     rax, [rax+8]
0x1800074b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b6  xor     eax, eax
0x1800074b8  mov     [rsi], rbx
0x1800074bb  jmp     short loc_180007539
0x1800074bd  cmp     qword ptr [rdx+10h], 0
0x1800074c2  jz      short loc_180007524
0x1800074c4  mov     rcx, [rbx]
0x1800074c7  test    rcx, rcx
0x1800074ca  jnz     short loc_1800074D1
0x1800074cc  lea     ebp, [rcx+1]
0x1800074cf  jmp     short loc_1800074F1
0x1800074d1  mov     eax, [rdi]
0x1800074d3  cmp     [rcx], eax
0x1800074d5  jnz     short loc_180007519
0x1800074d7  mov     eax, [rdi+4]
0x1800074da  cmp     [rcx+4], eax
0x1800074dd  jnz     short loc_180007519
0x1800074df  mov     eax, [rdi+8]
0x1800074e2  cmp     [rcx+8], eax
0x1800074e5  jnz     short loc_180007519
0x1800074e7  mov     eax, [rdi+0Ch]
0x1800074ea  cmp     [rcx+0Ch], eax
0x1800074ed  jnz     short loc_180007519
0x1800074ef  xor     ebp, ebp
0x1800074f1  mov     rax, [rbx+10h]
0x1800074f5  cmp     rax, 1
0x1800074f9  jz      short loc_18000752B
0x1800074fb  mov     r9, [rbx+8]
0x1800074ff  mov     r8, rsi
0x180007502  mov     rdx, rdi
0x180007505  mov     rcx, r14
0x180007508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750d  test    eax, eax
0x18000750f  jz      short loc_180007539
0x180007511  test    ebp, ebp
0x180007513  jnz     short loc_180007519
0x180007515  test    eax, eax
0x180007517  js      short loc_180007539
0x180007519  add     rbx, 18h
0x18000751d  cmp     qword ptr [rbx+10h], 0
0x180007522  jnz     short loc_1800074C4
0x180007524  mov     eax, 80004002h
0x180007529  jmp     short loc_180007539
0x18000752b  mov     rbx, [rbx+8]
0x18000752f  jmp     loc_1800074A4
0x180007534  mov     eax, 80070057h
0x180007539  add     rsp, 30h
0x18000753d  pop     r14
0x18000753f  pop     rdi
0x180007540  pop     rsi
0x180007541  pop     rbp
0x180007542  pop     rbx
0x180007543  retn
```
