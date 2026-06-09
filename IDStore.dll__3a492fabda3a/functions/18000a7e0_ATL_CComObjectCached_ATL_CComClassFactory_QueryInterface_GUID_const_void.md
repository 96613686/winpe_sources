# ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a7e0`
- end: `0x18000a905`
- name: `?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a7e0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(char *a1, _DWORD *a2, char **a3)
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
    for ( i = &`ATL::CComClassFactory::_GetEntries'::`2'::_entries; ; i += 3 )
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
0x18000a7e0  push    rbx
0x18000a7e2  push    rbp
0x18000a7e3  push    rsi
0x18000a7e4  push    rdi
0x18000a7e5  push    r14
0x18000a7e7  sub     rsp, 30h
0x18000a7eb  mov     rsi, r8
0x18000a7ee  mov     rdi, rdx
0x18000a7f1  mov     r14, rcx
0x18000a7f4  test    rcx, rcx
0x18000a7f7  jz      loc_18000A8FB
0x18000a7fd  test    r8, r8
0x18000a800  jz      loc_18000A8C0
0x18000a806  mov     qword ptr [r8], 0
0x18000a80d  cmp     dword ptr [rdx], 0
0x18000a810  jz      short loc_18000A884
0x18000a812  lea     rbx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; ATL::_ATL_INTMAP_ENTRY const near * const `ATL::CComClassFactory::_GetEntries(void)'::`2'::_entries
0x18000a819  mov     r10, [rbx+10h]
0x18000a81d  test    r10, r10
0x18000a820  jz      loc_18000A8F1
0x18000a826  mov     rcx, [rbx]
0x18000a829  test    rcx, rcx
0x18000a82c  jz      loc_18000A8C7
0x18000a832  mov     eax, [rdi]
0x18000a834  cmp     [rcx], eax
0x18000a836  jnz     short loc_18000A87E
0x18000a838  mov     eax, [rdi+4]
0x18000a83b  cmp     [rcx+4], eax
0x18000a83e  jnz     short loc_18000A87E
0x18000a840  mov     eax, [rdi+8]
0x18000a843  cmp     [rcx+8], eax
0x18000a846  jnz     short loc_18000A87E
0x18000a848  mov     eax, [rdi+0Ch]
0x18000a84b  cmp     [rcx+0Ch], eax
0x18000a84e  jnz     short loc_18000A87E
0x18000a850  xor     ebp, ebp
0x18000a852  cmp     r10, 1
0x18000a856  jnz     short loc_18000A8CE
0x18000a858  mov     rbx, [rbx+8]
0x18000a85c  add     rbx, r14
0x18000a85f  mov     rax, [rbx]
0x18000a862  mov     rcx, rbx
0x18000a865  mov     rax, [rax+8]
0x18000a869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a86e  mov     [rsi], rbx
0x18000a871  xor     eax, eax
0x18000a873  add     rsp, 30h
0x18000a877  pop     r14
0x18000a879  pop     rdi
0x18000a87a  pop     rsi
0x18000a87b  pop     rbp
0x18000a87c  pop     rbx
0x18000a87d  retn
0x18000a87e  add     rbx, 18h
0x18000a882  jmp     short loc_18000A819
0x18000a884  cmp     dword ptr [rdx+4], 0
0x18000a888  jnz     short loc_18000A812
0x18000a88a  cmp     dword ptr [rdx+8], 0C0h
0x18000a891  jnz     loc_18000A812
0x18000a897  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000a89e  jnz     loc_18000A812
0x18000a8a4  mov     rax, [rcx]
0x18000a8a7  mov     rax, [rax+8]
0x18000a8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b0  mov     [rsi], r14
0x18000a8b3  xor     eax, eax
0x18000a8b5  add     rsp, 30h
0x18000a8b9  pop     r14
0x18000a8bb  pop     rdi
0x18000a8bc  pop     rsi
0x18000a8bd  pop     rbp
0x18000a8be  pop     rbx
0x18000a8bf  retn
0x18000a8c0  mov     eax, 80004003h
0x18000a8c5  jmp     short loc_18000A873
0x18000a8c7  mov     ebp, 1
0x18000a8cc  jmp     short loc_18000A852
0x18000a8ce  mov     r9, [rbx+8]
0x18000a8d2  mov     r8, rsi
0x18000a8d5  mov     rdx, rdi
0x18000a8d8  mov     rcx, r14
0x18000a8db  mov     rax, r10
0x18000a8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e3  test    eax, eax
0x18000a8e5  jz      short loc_18000A873
0x18000a8e7  test    ebp, ebp
0x18000a8e9  jnz     short loc_18000A87E
0x18000a8eb  test    eax, eax
0x18000a8ed  js      short loc_18000A873
0x18000a8ef  jmp     short loc_18000A87E
0x18000a8f1  mov     eax, 80004002h
0x18000a8f6  jmp     loc_18000A873
0x18000a8fb  mov     eax, 80070057h
0x18000a900  jmp     loc_18000A873
```
