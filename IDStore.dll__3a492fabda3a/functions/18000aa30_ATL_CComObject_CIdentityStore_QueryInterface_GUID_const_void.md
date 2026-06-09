# ATL::CComObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000aa30`
- end: `0x18000ab55`
- name: `?QueryInterface@?$CComObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011920`
- `0x180011a20`
- `0x180011a30`

## callees

- `0x18000aa30`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::QueryInterface(char *a1, _DWORD *a2, char **a3)
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
    for ( i = &`CIdentityStore::_GetEntries'::`2'::_entries; ; i += 3 )
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
0x18000aa30  push    rbx
0x18000aa32  push    rbp
0x18000aa33  push    rsi
0x18000aa34  push    rdi
0x18000aa35  push    r14
0x18000aa37  sub     rsp, 30h
0x18000aa3b  mov     rsi, r8
0x18000aa3e  mov     rdi, rdx
0x18000aa41  mov     r14, rcx
0x18000aa44  test    rcx, rcx
0x18000aa47  jz      loc_18000AB4B
0x18000aa4d  test    r8, r8
0x18000aa50  jz      loc_18000AB10
0x18000aa56  mov     qword ptr [r8], 0
0x18000aa5d  cmp     dword ptr [rdx], 0
0x18000aa60  jz      short loc_18000AAD4
0x18000aa62  lea     rbx, ?_entries@?1??_GetEntries@CIdentityStore@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIdentityStore::_GetEntries(void)'::`2'::_entries
0x18000aa69  mov     r10, [rbx+10h]
0x18000aa6d  test    r10, r10
0x18000aa70  jz      loc_18000AB41
0x18000aa76  mov     rcx, [rbx]
0x18000aa79  test    rcx, rcx
0x18000aa7c  jz      loc_18000AB17
0x18000aa82  mov     eax, [rdi]
0x18000aa84  cmp     [rcx], eax
0x18000aa86  jnz     short loc_18000AACE
0x18000aa88  mov     eax, [rdi+4]
0x18000aa8b  cmp     [rcx+4], eax
0x18000aa8e  jnz     short loc_18000AACE
0x18000aa90  mov     eax, [rdi+8]
0x18000aa93  cmp     [rcx+8], eax
0x18000aa96  jnz     short loc_18000AACE
0x18000aa98  mov     eax, [rdi+0Ch]
0x18000aa9b  cmp     [rcx+0Ch], eax
0x18000aa9e  jnz     short loc_18000AACE
0x18000aaa0  xor     ebp, ebp
0x18000aaa2  cmp     r10, 1
0x18000aaa6  jnz     short loc_18000AB1E
0x18000aaa8  mov     rbx, [rbx+8]
0x18000aaac  add     rbx, r14
0x18000aaaf  mov     rax, [rbx]
0x18000aab2  mov     rcx, rbx
0x18000aab5  mov     rax, [rax+8]
0x18000aab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aabe  mov     [rsi], rbx
0x18000aac1  xor     eax, eax
0x18000aac3  add     rsp, 30h
0x18000aac7  pop     r14
0x18000aac9  pop     rdi
0x18000aaca  pop     rsi
0x18000aacb  pop     rbp
0x18000aacc  pop     rbx
0x18000aacd  retn
0x18000aace  add     rbx, 18h
0x18000aad2  jmp     short loc_18000AA69
0x18000aad4  cmp     dword ptr [rdx+4], 0
0x18000aad8  jnz     short loc_18000AA62
0x18000aada  cmp     dword ptr [rdx+8], 0C0h
0x18000aae1  jnz     loc_18000AA62
0x18000aae7  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000aaee  jnz     loc_18000AA62
0x18000aaf4  mov     rax, [rcx]
0x18000aaf7  mov     rax, [rax+8]
0x18000aafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab00  mov     [rsi], r14
0x18000ab03  xor     eax, eax
0x18000ab05  add     rsp, 30h
0x18000ab09  pop     r14
0x18000ab0b  pop     rdi
0x18000ab0c  pop     rsi
0x18000ab0d  pop     rbp
0x18000ab0e  pop     rbx
0x18000ab0f  retn
0x18000ab10  mov     eax, 80004003h
0x18000ab15  jmp     short loc_18000AAC3
0x18000ab17  mov     ebp, 1
0x18000ab1c  jmp     short loc_18000AAA2
0x18000ab1e  mov     r9, [rbx+8]
0x18000ab22  mov     r8, rsi
0x18000ab25  mov     rdx, rdi
0x18000ab28  mov     rcx, r14
0x18000ab2b  mov     rax, r10
0x18000ab2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab33  test    eax, eax
0x18000ab35  jz      short loc_18000AAC3
0x18000ab37  test    ebp, ebp
0x18000ab39  jnz     short loc_18000AACE
0x18000ab3b  test    eax, eax
0x18000ab3d  js      short loc_18000AAC3
0x18000ab3f  jmp     short loc_18000AACE
0x18000ab41  mov     eax, 80004002h
0x18000ab46  jmp     loc_18000AAC3
0x18000ab4b  mov     eax, 80070057h
0x18000ab50  jmp     loc_18000AAC3
```
