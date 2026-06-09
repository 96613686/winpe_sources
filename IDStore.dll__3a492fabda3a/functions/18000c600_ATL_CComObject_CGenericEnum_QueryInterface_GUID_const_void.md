# ATL::CComObject<CGenericEnum>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c600`
- end: `0x18000c725`
- name: `?QueryInterface@?$CComObject@VCGenericEnum@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c600`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGenericEnum>::QueryInterface(char *a1, _DWORD *a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  char *v10; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = 0;
    if ( !*a2 && !a2[1] && a2[2] == 192 && a2[3] == 1174405120 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
      *a3 = a1;
      return 0;
    }
    for ( i = &`CGenericEnum::_GetEntries'::`2'::_entries; ; i += 3 )
    {
      v7 = i[2];
      if ( !v7 )
        return 2147500034LL;
      v8 = *i;
      if ( *i )
      {
        if ( v8->Data1 != *a2
          || *(_DWORD *)&v8->Data2 != a2[1]
          || *(_DWORD *)v8->Data4 != a2[2]
          || *(_DWORD *)&v8->Data4[4] != a2[3] )
        {
          continue;
        }
        v9 = 0;
      }
      else
      {
        v9 = 1;
      }
      if ( v7 == (GUID *)1 )
      {
        v10 = (char *)i[1] + (_QWORD)a1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
        *a3 = v10;
        return 0;
      }
      result = ((__int64 (__fastcall *)(char *, _DWORD *, char **, GUID *))i[2])(a1, a2, a3, i[1]);
      if ( !(_DWORD)result || !v9 && (int)result < 0 )
        return result;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000c600  push    rbx
0x18000c602  push    rbp
0x18000c603  push    rsi
0x18000c604  push    rdi
0x18000c605  push    r14
0x18000c607  sub     rsp, 30h
0x18000c60b  mov     rsi, r8
0x18000c60e  mov     rdi, rdx
0x18000c611  mov     r14, rcx
0x18000c614  test    rcx, rcx
0x18000c617  jz      loc_18000C71B
0x18000c61d  test    r8, r8
0x18000c620  jz      loc_18000C6E0
0x18000c626  mov     qword ptr [r8], 0
0x18000c62d  cmp     dword ptr [rdx], 0
0x18000c630  jz      short loc_18000C6A4
0x18000c632  lea     rbx, ?_entries@?1??_GetEntries@CGenericEnum@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CGenericEnum::_GetEntries(void)'::`2'::_entries
0x18000c639  mov     r10, [rbx+10h]
0x18000c63d  test    r10, r10
0x18000c640  jz      loc_18000C711
0x18000c646  mov     rcx, [rbx]
0x18000c649  test    rcx, rcx
0x18000c64c  jz      loc_18000C6E7
0x18000c652  mov     eax, [rdi]
0x18000c654  cmp     [rcx], eax
0x18000c656  jnz     short loc_18000C69E
0x18000c658  mov     eax, [rdi+4]
0x18000c65b  cmp     [rcx+4], eax
0x18000c65e  jnz     short loc_18000C69E
0x18000c660  mov     eax, [rdi+8]
0x18000c663  cmp     [rcx+8], eax
0x18000c666  jnz     short loc_18000C69E
0x18000c668  mov     eax, [rdi+0Ch]
0x18000c66b  cmp     [rcx+0Ch], eax
0x18000c66e  jnz     short loc_18000C69E
0x18000c670  xor     ebp, ebp
0x18000c672  cmp     r10, 1
0x18000c676  jnz     short loc_18000C6EE
0x18000c678  mov     rbx, [rbx+8]
0x18000c67c  add     rbx, r14
0x18000c67f  mov     rax, [rbx]
0x18000c682  mov     rcx, rbx
0x18000c685  mov     rax, [rax+8]
0x18000c689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68e  mov     [rsi], rbx
0x18000c691  xor     eax, eax
0x18000c693  add     rsp, 30h
0x18000c697  pop     r14
0x18000c699  pop     rdi
0x18000c69a  pop     rsi
0x18000c69b  pop     rbp
0x18000c69c  pop     rbx
0x18000c69d  retn
0x18000c69e  add     rbx, 18h
0x18000c6a2  jmp     short loc_18000C639
0x18000c6a4  cmp     dword ptr [rdx+4], 0
0x18000c6a8  jnz     short loc_18000C632
0x18000c6aa  cmp     dword ptr [rdx+8], 0C0h
0x18000c6b1  jnz     loc_18000C632
0x18000c6b7  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000c6be  jnz     loc_18000C632
0x18000c6c4  mov     rax, [rcx]
0x18000c6c7  mov     rax, [rax+8]
0x18000c6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d0  mov     [rsi], r14
0x18000c6d3  xor     eax, eax
0x18000c6d5  add     rsp, 30h
0x18000c6d9  pop     r14
0x18000c6db  pop     rdi
0x18000c6dc  pop     rsi
0x18000c6dd  pop     rbp
0x18000c6de  pop     rbx
0x18000c6df  retn
0x18000c6e0  mov     eax, 80004003h
0x18000c6e5  jmp     short loc_18000C693
0x18000c6e7  mov     ebp, 1
0x18000c6ec  jmp     short loc_18000C672
0x18000c6ee  mov     r9, [rbx+8]
0x18000c6f2  mov     r8, rsi
0x18000c6f5  mov     rdx, rdi
0x18000c6f8  mov     rcx, r14
0x18000c6fb  mov     rax, r10
0x18000c6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c703  test    eax, eax
0x18000c705  jz      short loc_18000C693
0x18000c707  test    ebp, ebp
0x18000c709  jnz     short loc_18000C69E
0x18000c70b  test    eax, eax
0x18000c70d  js      short loc_18000C693
0x18000c70f  jmp     short loc_18000C69E
0x18000c711  mov     eax, 80004002h
0x18000c716  jmp     loc_18000C693
0x18000c71b  mov     eax, 80070057h
0x18000c720  jmp     loc_18000C693
```
