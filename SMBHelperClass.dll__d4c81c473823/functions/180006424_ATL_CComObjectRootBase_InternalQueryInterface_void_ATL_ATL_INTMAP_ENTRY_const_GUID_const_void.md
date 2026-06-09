# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180006424`
- end: `0x180006528`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800072c0`
- `0x180007300`

## callees

- `0x180006424`
- `0x180012010`

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
0x180006424  push    rbx
0x180006426  push    rbp
0x180006427  push    rsi
0x180006428  push    rdi
0x180006429  push    r14
0x18000642b  sub     rsp, 30h
0x18000642f  mov     rsi, r9
0x180006432  mov     rdi, r8
0x180006435  mov     rbx, rdx
0x180006438  mov     r14, rcx
0x18000643b  test    rcx, rcx
0x18000643e  jz      loc_180006518
0x180006444  test    rdx, rdx
0x180006447  jz      loc_180006518
0x18000644d  test    r9, r9
0x180006450  jnz     short loc_18000645C
0x180006452  mov     eax, 80004003h
0x180006457  jmp     loc_18000651D
0x18000645c  mov     qword ptr [r9], 0
0x180006463  cmp     dword ptr [r8], 0
0x180006467  jnz     short loc_1800064A1
0x180006469  cmp     dword ptr [r8+4], 0
0x18000646e  jnz     short loc_1800064A1
0x180006470  cmp     dword ptr [r8+8], 0C0h
0x180006478  jnz     short loc_1800064A1
0x18000647a  cmp     dword ptr [r8+0Ch], 46000000h
0x180006482  jnz     short loc_1800064A1
0x180006484  mov     rbx, [rdx+8]
0x180006488  add     rbx, r14
0x18000648b  mov     rcx, rbx
0x18000648e  mov     rax, [rbx]
0x180006491  mov     rax, [rax+8]
0x180006495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649a  xor     eax, eax
0x18000649c  mov     [rsi], rbx
0x18000649f  jmp     short loc_18000651D
0x1800064a1  cmp     qword ptr [rdx+10h], 0
0x1800064a6  jz      short loc_180006508
0x1800064a8  mov     rcx, [rbx]
0x1800064ab  test    rcx, rcx
0x1800064ae  jnz     short loc_1800064B5
0x1800064b0  lea     ebp, [rcx+1]
0x1800064b3  jmp     short loc_1800064D5
0x1800064b5  mov     eax, [rdi]
0x1800064b7  cmp     [rcx], eax
0x1800064b9  jnz     short loc_1800064FD
0x1800064bb  mov     eax, [rdi+4]
0x1800064be  cmp     [rcx+4], eax
0x1800064c1  jnz     short loc_1800064FD
0x1800064c3  mov     eax, [rdi+8]
0x1800064c6  cmp     [rcx+8], eax
0x1800064c9  jnz     short loc_1800064FD
0x1800064cb  mov     eax, [rdi+0Ch]
0x1800064ce  cmp     [rcx+0Ch], eax
0x1800064d1  jnz     short loc_1800064FD
0x1800064d3  xor     ebp, ebp
0x1800064d5  mov     rax, [rbx+10h]
0x1800064d9  cmp     rax, 1
0x1800064dd  jz      short loc_18000650F
0x1800064df  mov     r9, [rbx+8]
0x1800064e3  mov     r8, rsi
0x1800064e6  mov     rdx, rdi
0x1800064e9  mov     rcx, r14
0x1800064ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f1  test    eax, eax
0x1800064f3  jz      short loc_18000651D
0x1800064f5  test    ebp, ebp
0x1800064f7  jnz     short loc_1800064FD
0x1800064f9  test    eax, eax
0x1800064fb  js      short loc_18000651D
0x1800064fd  add     rbx, 18h
0x180006501  cmp     qword ptr [rbx+10h], 0
0x180006506  jnz     short loc_1800064A8
0x180006508  mov     eax, 80004002h
0x18000650d  jmp     short loc_18000651D
0x18000650f  mov     rbx, [rbx+8]
0x180006513  jmp     loc_180006488
0x180006518  mov     eax, 80070057h
0x18000651d  add     rsp, 30h
0x180006521  pop     r14
0x180006523  pop     rdi
0x180006524  pop     rsi
0x180006525  pop     rbp
0x180006526  pop     rbx
0x180006527  retn
```
