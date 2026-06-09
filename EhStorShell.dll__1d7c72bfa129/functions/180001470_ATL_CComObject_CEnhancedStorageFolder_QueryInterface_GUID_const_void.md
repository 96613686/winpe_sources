# ATL::CComObject<CEnhancedStorageFolder>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001470`
- end: `0x1800015af`
- name: `?QueryInterface@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64, _DWORD *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d50`
- `0x180008d60`

## callees

- `0x180001470`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::QueryInterface(__int64 a1, _DWORD *a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // r14d
  __int64 result; // rax
  char *v11; // rbx
  char *v12; // rbx

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !*a2 && !a2[1] && a2[2] == 192 && a2[3] == 1174405120 )
  {
    v12 = (char *)(a1 + 16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 8LL))(a1 + 16);
    *a3 = v12;
    return 0;
  }
  for ( i = &`CEnhancedStorageFolder::_GetEntries'::`2'::_entries; ; i += 3 )
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
    result = ((__int64 (__fastcall *)(__int64, _DWORD *, char **, GUID *))i[2])(a1, a2, a3, i[1]);
    if ( !(_DWORD)result || !v9 && (int)result < 0 )
      return result;
  }
  v11 = (char *)i[1] + a1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  *a3 = v11;
  return 0;
}

```

## disassembly

```asm
0x180001470  push    rbx
0x180001472  push    rbp
0x180001473  push    rsi
0x180001474  push    rdi
0x180001475  push    r14
0x180001477  sub     rsp, 30h
0x18000147b  mov     rsi, r8
0x18000147e  mov     rdi, rdx
0x180001481  mov     rbp, rcx
0x180001484  test    rcx, rcx
0x180001487  jz      loc_1800015A5
0x18000148d  test    r8, r8
0x180001490  jz      loc_18000152C
0x180001496  mov     qword ptr [r8], 0
0x18000149d  cmp     dword ptr [rdx], 0
0x1800014a0  jz      loc_18000153C
0x1800014a6  lea     rbx, ?_entries@?1??_GetEntries@CEnhancedStorageFolder@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CEnhancedStorageFolder::_GetEntries(void)'::`2'::_entries
0x1800014ad  nop     dword ptr [rax]
0x1800014b0  mov     r10, [rbx+10h]
0x1800014b4  test    r10, r10
0x1800014b7  jz      short loc_1800014EA
0x1800014b9  mov     rcx, [rbx]
0x1800014bc  test    rcx, rcx
0x1800014bf  jz      short loc_1800014FA
0x1800014c1  mov     eax, [rdi]
0x1800014c3  cmp     [rcx], eax
0x1800014c5  jz      short loc_1800014CD
0x1800014c7  add     rbx, 18h
0x1800014cb  jmp     short loc_1800014B0
0x1800014cd  mov     eax, [rdi+4]
0x1800014d0  cmp     [rcx+4], eax
0x1800014d3  jnz     short loc_1800014C7
0x1800014d5  mov     eax, [rdi+8]
0x1800014d8  cmp     [rcx+8], eax
0x1800014db  jnz     short loc_1800014C7
0x1800014dd  mov     eax, [rdi+0Ch]
0x1800014e0  cmp     [rcx+0Ch], eax
0x1800014e3  jnz     short loc_1800014C7
0x1800014e5  xor     r14d, r14d
0x1800014e8  jmp     short loc_180001500
0x1800014ea  mov     eax, 80004002h
0x1800014ef  add     rsp, 30h
0x1800014f3  pop     r14
0x1800014f5  pop     rdi
0x1800014f6  pop     rsi
0x1800014f7  pop     rbp
0x1800014f8  pop     rbx
0x1800014f9  retn
0x1800014fa  mov     r14d, 1
0x180001500  cmp     r10, 1
0x180001504  jnz     short loc_18000157A
0x180001506  mov     rbx, [rbx+8]
0x18000150a  add     rbx, rbp
0x18000150d  mov     rax, [rbx]
0x180001510  mov     rcx, rbx
0x180001513  mov     rax, [rax+8]
0x180001517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151c  mov     [rsi], rbx
0x18000151f  xor     eax, eax
0x180001521  add     rsp, 30h
0x180001525  pop     r14
0x180001527  pop     rdi
0x180001528  pop     rsi
0x180001529  pop     rbp
0x18000152a  pop     rbx
0x18000152b  retn
0x18000152c  mov     eax, 80004003h
0x180001531  add     rsp, 30h
0x180001535  pop     r14
0x180001537  pop     rdi
0x180001538  pop     rsi
0x180001539  pop     rbp
0x18000153a  pop     rbx
0x18000153b  retn
0x18000153c  cmp     dword ptr [rdx+4], 0
0x180001540  jnz     loc_1800014A6
0x180001546  cmp     dword ptr [rdx+8], 0C0h
0x18000154d  jnz     loc_1800014A6
0x180001553  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000155a  jnz     loc_1800014A6
0x180001560  lea     rbx, [rcx+10h]
0x180001564  mov     rax, [rbx]
0x180001567  mov     rcx, rbx
0x18000156a  mov     rax, [rax+8]
0x18000156e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001573  mov     [rsi], rbx
0x180001576  xor     eax, eax
0x180001578  jmp     short loc_180001521
0x18000157a  mov     r9, [rbx+8]
0x18000157e  mov     r8, rsi
0x180001581  mov     rdx, rdi
0x180001584  mov     rcx, rbp
0x180001587  mov     rax, r10
0x18000158a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158f  test    eax, eax
0x180001591  jz      short loc_180001521
0x180001593  test    r14d, r14d
0x180001596  jnz     loc_1800014C7
0x18000159c  test    eax, eax
0x18000159e  js      short loc_180001521
0x1800015a0  jmp     loc_1800014C7
0x1800015a5  mov     eax, 80070057h
0x1800015aa  jmp     loc_180001521
```
