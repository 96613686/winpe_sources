# ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001750`
- end: `0x180001885`
- name: `?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001750`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(char *a1, _DWORD *a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  __int64 result; // rax
  char *v11; // rbx

  if ( !a1 )
    return 2147942487LL;
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
      break;
    result = ((__int64 (__fastcall *)(char *, _DWORD *, char **, GUID *))i[2])(a1, a2, a3, i[1]);
    if ( !(_DWORD)result || !v9 && (int)result < 0 )
      return result;
  }
  v11 = (char *)i[1] + (_QWORD)a1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  *a3 = v11;
  return 0;
}

```

## disassembly

```asm
0x180001750  push    rbx
0x180001752  push    rbp
0x180001753  push    rsi
0x180001754  push    rdi
0x180001755  push    r14
0x180001757  sub     rsp, 30h
0x18000175b  mov     rsi, r8
0x18000175e  mov     rdi, rdx
0x180001761  mov     r14, rcx
0x180001764  test    rcx, rcx
0x180001767  jz      loc_18000187B
0x18000176d  test    r8, r8
0x180001770  jz      loc_18000180A
0x180001776  mov     qword ptr [r8], 0
0x18000177d  cmp     dword ptr [rdx], 0
0x180001780  jz      loc_18000181A
0x180001786  lea     rbx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; ATL::_ATL_INTMAP_ENTRY const near * const `ATL::CComClassFactory::_GetEntries(void)'::`2'::_entries
0x18000178d  nop     dword ptr [rax]
0x180001790  mov     r10, [rbx+10h]
0x180001794  test    r10, r10
0x180001797  jz      short loc_1800017C9
0x180001799  mov     rcx, [rbx]
0x18000179c  test    rcx, rcx
0x18000179f  jz      short loc_1800017D9
0x1800017a1  mov     eax, [rdi]
0x1800017a3  cmp     [rcx], eax
0x1800017a5  jz      short loc_1800017AD
0x1800017a7  add     rbx, 18h
0x1800017ab  jmp     short loc_180001790
0x1800017ad  mov     eax, [rdi+4]
0x1800017b0  cmp     [rcx+4], eax
0x1800017b3  jnz     short loc_1800017A7
0x1800017b5  mov     eax, [rdi+8]
0x1800017b8  cmp     [rcx+8], eax
0x1800017bb  jnz     short loc_1800017A7
0x1800017bd  mov     eax, [rdi+0Ch]
0x1800017c0  cmp     [rcx+0Ch], eax
0x1800017c3  jnz     short loc_1800017A7
0x1800017c5  xor     ebp, ebp
0x1800017c7  jmp     short loc_1800017DE
0x1800017c9  mov     eax, 80004002h
0x1800017ce  add     rsp, 30h
0x1800017d2  pop     r14
0x1800017d4  pop     rdi
0x1800017d5  pop     rsi
0x1800017d6  pop     rbp
0x1800017d7  pop     rbx
0x1800017d8  retn
0x1800017d9  mov     ebp, 1
0x1800017de  cmp     r10, 1
0x1800017e2  jnz     short loc_180001851
0x1800017e4  mov     rbx, [rbx+8]
0x1800017e8  add     rbx, r14
0x1800017eb  mov     rax, [rbx]
0x1800017ee  mov     rcx, rbx
0x1800017f1  mov     rax, [rax+8]
0x1800017f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017fa  mov     [rsi], rbx
0x1800017fd  xor     eax, eax
0x1800017ff  add     rsp, 30h
0x180001803  pop     r14
0x180001805  pop     rdi
0x180001806  pop     rsi
0x180001807  pop     rbp
0x180001808  pop     rbx
0x180001809  retn
0x18000180a  mov     eax, 80004003h
0x18000180f  add     rsp, 30h
0x180001813  pop     r14
0x180001815  pop     rdi
0x180001816  pop     rsi
0x180001817  pop     rbp
0x180001818  pop     rbx
0x180001819  retn
0x18000181a  cmp     dword ptr [rdx+4], 0
0x18000181e  jnz     loc_180001786
0x180001824  cmp     dword ptr [rdx+8], 0C0h
0x18000182b  jnz     loc_180001786
0x180001831  cmp     dword ptr [rdx+0Ch], 46000000h
0x180001838  jnz     loc_180001786
0x18000183e  mov     rax, [rcx]
0x180001841  mov     rax, [rax+8]
0x180001845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000184a  mov     [rsi], r14
0x18000184d  xor     eax, eax
0x18000184f  jmp     short loc_1800017FF
0x180001851  mov     r9, [rbx+8]
0x180001855  mov     r8, rsi
0x180001858  mov     rdx, rdi
0x18000185b  mov     rcx, r14
0x18000185e  mov     rax, r10
0x180001861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001866  test    eax, eax
0x180001868  jz      short loc_1800017FF
0x18000186a  test    ebp, ebp
0x18000186c  jnz     loc_1800017A7
0x180001872  test    eax, eax
0x180001874  js      short loc_1800017FF
0x180001876  jmp     loc_1800017A7
0x18000187b  mov     eax, 80070057h
0x180001880  jmp     loc_1800017FF
```
