# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180005588`
- end: `0x18000568c`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800056e0`
- `0x180005770`
- `0x180005790`
- `0x180005d10`
- `0x180005d80`

## callees

- `0x180005588`
- `0x180007010`

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
0x180005588  push    rbx
0x18000558a  push    rbp
0x18000558b  push    rsi
0x18000558c  push    rdi
0x18000558d  push    r14
0x18000558f  sub     rsp, 30h
0x180005593  mov     rsi, r9
0x180005596  mov     rdi, r8
0x180005599  mov     rbx, rdx
0x18000559c  mov     r14, rcx
0x18000559f  test    rcx, rcx
0x1800055a2  jz      loc_18000567C
0x1800055a8  test    rdx, rdx
0x1800055ab  jz      loc_18000567C
0x1800055b1  test    r9, r9
0x1800055b4  jnz     short loc_1800055C0
0x1800055b6  mov     eax, 80004003h
0x1800055bb  jmp     loc_180005681
0x1800055c0  mov     qword ptr [r9], 0
0x1800055c7  cmp     dword ptr [r8], 0
0x1800055cb  jnz     short loc_180005605
0x1800055cd  cmp     dword ptr [r8+4], 0
0x1800055d2  jnz     short loc_180005605
0x1800055d4  cmp     dword ptr [r8+8], 0C0h
0x1800055dc  jnz     short loc_180005605
0x1800055de  cmp     dword ptr [r8+0Ch], 46000000h
0x1800055e6  jnz     short loc_180005605
0x1800055e8  mov     rbx, [rdx+8]
0x1800055ec  add     rbx, r14
0x1800055ef  mov     rcx, rbx
0x1800055f2  mov     rax, [rbx]
0x1800055f5  mov     rax, [rax+8]
0x1800055f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fe  xor     eax, eax
0x180005600  mov     [rsi], rbx
0x180005603  jmp     short loc_180005681
0x180005605  cmp     qword ptr [rdx+10h], 0
0x18000560a  jz      short loc_18000566C
0x18000560c  mov     rcx, [rbx]
0x18000560f  test    rcx, rcx
0x180005612  jnz     short loc_180005619
0x180005614  lea     ebp, [rcx+1]
0x180005617  jmp     short loc_180005639
0x180005619  mov     eax, [rdi]
0x18000561b  cmp     [rcx], eax
0x18000561d  jnz     short loc_180005661
0x18000561f  mov     eax, [rdi+4]
0x180005622  cmp     [rcx+4], eax
0x180005625  jnz     short loc_180005661
0x180005627  mov     eax, [rdi+8]
0x18000562a  cmp     [rcx+8], eax
0x18000562d  jnz     short loc_180005661
0x18000562f  mov     eax, [rdi+0Ch]
0x180005632  cmp     [rcx+0Ch], eax
0x180005635  jnz     short loc_180005661
0x180005637  xor     ebp, ebp
0x180005639  mov     rax, [rbx+10h]
0x18000563d  cmp     rax, 1
0x180005641  jz      short loc_180005673
0x180005643  mov     r9, [rbx+8]
0x180005647  mov     r8, rsi
0x18000564a  mov     rdx, rdi
0x18000564d  mov     rcx, r14
0x180005650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005655  test    eax, eax
0x180005657  jz      short loc_180005681
0x180005659  test    ebp, ebp
0x18000565b  jnz     short loc_180005661
0x18000565d  test    eax, eax
0x18000565f  js      short loc_180005681
0x180005661  add     rbx, 18h
0x180005665  cmp     qword ptr [rbx+10h], 0
0x18000566a  jnz     short loc_18000560C
0x18000566c  mov     eax, 80004002h
0x180005671  jmp     short loc_180005681
0x180005673  mov     rbx, [rbx+8]
0x180005677  jmp     loc_1800055EC
0x18000567c  mov     eax, 80070057h
0x180005681  add     rsp, 30h
0x180005685  pop     r14
0x180005687  pop     rdi
0x180005688  pop     rsi
0x180005689  pop     rbp
0x18000568a  pop     rbx
0x18000568b  retn
```
