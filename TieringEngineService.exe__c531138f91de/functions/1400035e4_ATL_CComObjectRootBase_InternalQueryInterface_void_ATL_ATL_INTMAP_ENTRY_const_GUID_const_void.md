# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1400035e4`
- end: `0x1400036e8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003a90`
- `0x140003b00`
- `0x140003b90`
- `0x140003bb0`
- `0x140003bd0`

## callees

- `0x1400035e4`
- `0x140041010`

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
0x1400035e4  push    rbx
0x1400035e6  push    rbp
0x1400035e7  push    rsi
0x1400035e8  push    rdi
0x1400035e9  push    r14
0x1400035eb  sub     rsp, 30h
0x1400035ef  mov     rsi, r9
0x1400035f2  mov     rdi, r8
0x1400035f5  mov     rbx, rdx
0x1400035f8  mov     r14, rcx
0x1400035fb  test    rcx, rcx
0x1400035fe  jz      loc_1400036D8
0x140003604  test    rdx, rdx
0x140003607  jz      loc_1400036D8
0x14000360d  test    r9, r9
0x140003610  jnz     short loc_14000361C
0x140003612  mov     eax, 80004003h
0x140003617  jmp     loc_1400036DD
0x14000361c  mov     qword ptr [r9], 0
0x140003623  cmp     dword ptr [r8], 0
0x140003627  jnz     short loc_140003661
0x140003629  cmp     dword ptr [r8+4], 0
0x14000362e  jnz     short loc_140003661
0x140003630  cmp     dword ptr [r8+8], 0C0h
0x140003638  jnz     short loc_140003661
0x14000363a  cmp     dword ptr [r8+0Ch], 46000000h
0x140003642  jnz     short loc_140003661
0x140003644  mov     rbx, [rdx+8]
0x140003648  add     rbx, r14
0x14000364b  mov     rcx, rbx
0x14000364e  mov     rax, [rbx]
0x140003651  mov     rax, [rax+8]
0x140003655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000365a  xor     eax, eax
0x14000365c  mov     [rsi], rbx
0x14000365f  jmp     short loc_1400036DD
0x140003661  cmp     qword ptr [rdx+10h], 0
0x140003666  jz      short loc_1400036C8
0x140003668  mov     rcx, [rbx]
0x14000366b  test    rcx, rcx
0x14000366e  jnz     short loc_140003675
0x140003670  lea     ebp, [rcx+1]
0x140003673  jmp     short loc_140003695
0x140003675  mov     eax, [rdi]
0x140003677  cmp     [rcx], eax
0x140003679  jnz     short loc_1400036BD
0x14000367b  mov     eax, [rdi+4]
0x14000367e  cmp     [rcx+4], eax
0x140003681  jnz     short loc_1400036BD
0x140003683  mov     eax, [rdi+8]
0x140003686  cmp     [rcx+8], eax
0x140003689  jnz     short loc_1400036BD
0x14000368b  mov     eax, [rdi+0Ch]
0x14000368e  cmp     [rcx+0Ch], eax
0x140003691  jnz     short loc_1400036BD
0x140003693  xor     ebp, ebp
0x140003695  mov     rax, [rbx+10h]
0x140003699  cmp     rax, 1
0x14000369d  jz      short loc_1400036CF
0x14000369f  mov     r9, [rbx+8]
0x1400036a3  mov     r8, rsi
0x1400036a6  mov     rdx, rdi
0x1400036a9  mov     rcx, r14
0x1400036ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036b1  test    eax, eax
0x1400036b3  jz      short loc_1400036DD
0x1400036b5  test    ebp, ebp
0x1400036b7  jnz     short loc_1400036BD
0x1400036b9  test    eax, eax
0x1400036bb  js      short loc_1400036DD
0x1400036bd  add     rbx, 18h
0x1400036c1  cmp     qword ptr [rbx+10h], 0
0x1400036c6  jnz     short loc_140003668
0x1400036c8  mov     eax, 80004002h
0x1400036cd  jmp     short loc_1400036DD
0x1400036cf  mov     rbx, [rbx+8]
0x1400036d3  jmp     loc_140003648
0x1400036d8  mov     eax, 80070057h
0x1400036dd  add     rsp, 30h
0x1400036e1  pop     r14
0x1400036e3  pop     rdi
0x1400036e4  pop     rsi
0x1400036e5  pop     rbp
0x1400036e6  pop     rbx
0x1400036e7  retn
```
