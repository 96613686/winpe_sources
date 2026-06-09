# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800015c0`
- end: `0x180001714`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `340`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006540`
- `0x180008d20`
- `0x18000b010`

## callees

- `0x1800015c0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::AtlInternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 v8; // r10
  _DWORD *v9; // rcx
  int v10; // ebp
  __int64 result; // rax
  char *v12; // rbx
  char *v13; // rbx

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v13 = &a1[*((_QWORD *)a2 + 1)];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
    result = 0;
    *a4 = v13;
    return result;
  }
  while ( 1 )
  {
    v8 = *((_QWORD *)v6 + 2);
    if ( !v8 )
      return 2147500034LL;
    v9 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v9 != a3->Data1
        || v9[1] != *(_DWORD *)&a3->Data2
        || v9[2] != *(_DWORD *)a3->Data4
        || v9[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_8;
      }
      v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    if ( v8 == 1 )
      break;
    result = (*((__int64 (__fastcall **)(char *, const struct _GUID *, char **, _QWORD))v6 + 2))(
               a1,
               a3,
               a4,
               *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v10 && (int)result < 0 )
      return result;
LABEL_8:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
  }
  v12 = &a1[*((_QWORD *)v6 + 1)];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
  result = 0;
  *a4 = v12;
  return result;
}

```

## disassembly

```asm
0x1800015c0  push    rbx
0x1800015c2  push    rsi
0x1800015c3  push    rdi
0x1800015c4  push    r14
0x1800015c6  sub     rsp, 38h
0x1800015ca  mov     rsi, r9
0x1800015cd  mov     rdi, r8
0x1800015d0  mov     rbx, rdx
0x1800015d3  mov     r14, rcx
0x1800015d6  test    rcx, rcx
0x1800015d9  jz      loc_18000170A
0x1800015df  test    rdx, rdx
0x1800015e2  jz      loc_18000170A
0x1800015e8  test    r9, r9
0x1800015eb  jz      loc_180001689
0x1800015f1  mov     qword ptr [r9], 0
0x1800015f8  cmp     dword ptr [r8], 0
0x1800015fc  jz      loc_180001698
0x180001602  mov     [rsp+58h+arg_0], rbp
0x180001607  mov     r10, [rbx+10h]
0x18000160b  test    r10, r10
0x18000160e  jz      short loc_180001640
0x180001610  mov     rcx, [rbx]
0x180001613  test    rcx, rcx
0x180001616  jz      short loc_180001654
0x180001618  mov     eax, [rdi]
0x18000161a  cmp     [rcx], eax
0x18000161c  jz      short loc_180001624
0x18000161e  add     rbx, 18h
0x180001622  jmp     short loc_180001607
0x180001624  mov     eax, [rdi+4]
0x180001627  cmp     [rcx+4], eax
0x18000162a  jnz     short loc_18000161E
0x18000162c  mov     eax, [rdi+8]
0x18000162f  cmp     [rcx+8], eax
0x180001632  jnz     short loc_18000161E
0x180001634  mov     eax, [rdi+0Ch]
0x180001637  cmp     [rcx+0Ch], eax
0x18000163a  jnz     short loc_18000161E
0x18000163c  xor     ebp, ebp
0x18000163e  jmp     short loc_180001659
0x180001640  mov     rbp, [rsp+58h+arg_0]
0x180001645  mov     eax, 80004002h
0x18000164a  add     rsp, 38h
0x18000164e  pop     r14
0x180001650  pop     rdi
0x180001651  pop     rsi
0x180001652  pop     rbx
0x180001653  retn
0x180001654  mov     ebp, 1
0x180001659  cmp     r10, 1
0x18000165d  jnz     short loc_1800016DC
0x18000165f  mov     rbx, [rbx+8]
0x180001663  add     rbx, r14
0x180001666  mov     rcx, rbx
0x180001669  mov     rax, [rbx]
0x18000166c  mov     rax, [rax+8]
0x180001670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001675  xor     eax, eax
0x180001677  mov     [rsi], rbx
0x18000167a  mov     rbp, [rsp+58h+arg_0]
0x18000167f  add     rsp, 38h
0x180001683  pop     r14
0x180001685  pop     rdi
0x180001686  pop     rsi
0x180001687  pop     rbx
0x180001688  retn
0x180001689  mov     eax, 80004003h
0x18000168e  add     rsp, 38h
0x180001692  pop     r14
0x180001694  pop     rdi
0x180001695  pop     rsi
0x180001696  pop     rbx
0x180001697  retn
0x180001698  cmp     dword ptr [r8+4], 0
0x18000169d  jnz     loc_180001602
0x1800016a3  cmp     dword ptr [r8+8], 0C0h
0x1800016ab  jnz     loc_180001602
0x1800016b1  cmp     dword ptr [r8+0Ch], 46000000h
0x1800016b9  jnz     loc_180001602
0x1800016bf  mov     rbx, [rdx+8]
0x1800016c3  add     rbx, r14
0x1800016c6  mov     rcx, rbx
0x1800016c9  mov     rax, [rbx]
0x1800016cc  mov     rax, [rax+8]
0x1800016d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d5  xor     eax, eax
0x1800016d7  mov     [rsi], rbx
0x1800016da  jmp     short loc_18000167F
0x1800016dc  mov     r9, [rbx+8]
0x1800016e0  mov     r8, rsi
0x1800016e3  mov     rdx, rdi
0x1800016e6  mov     rcx, r14
0x1800016e9  mov     rax, r10
0x1800016ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016f1  test    eax, eax
0x1800016f3  jz      short loc_18000167A
0x1800016f5  test    ebp, ebp
0x1800016f7  jnz     loc_18000161E
0x1800016fd  test    eax, eax
0x1800016ff  js      loc_18000167A
0x180001705  jmp     loc_18000161E
0x18000170a  mov     eax, 80070057h
0x18000170f  jmp     loc_18000167F
```
