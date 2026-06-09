# ATL::CComObject<CEnhancedStorageEnumerator>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800023b0`
- end: `0x1800024e5`
- name: `?QueryInterface@?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800023b0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageEnumerator>::QueryInterface(char *a1, _DWORD *a2, char **a3)
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
  for ( i = &`CEnhancedStorageEnumerator::_GetEntries'::`2'::_entries; ; i += 3 )
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
0x1800023b0  push    rbx
0x1800023b2  push    rbp
0x1800023b3  push    rsi
0x1800023b4  push    rdi
0x1800023b5  push    r14
0x1800023b7  sub     rsp, 30h
0x1800023bb  mov     rsi, r8
0x1800023be  mov     rdi, rdx
0x1800023c1  mov     r14, rcx
0x1800023c4  test    rcx, rcx
0x1800023c7  jz      loc_1800024DB
0x1800023cd  test    r8, r8
0x1800023d0  jz      loc_18000246A
0x1800023d6  mov     qword ptr [r8], 0
0x1800023dd  cmp     dword ptr [rdx], 0
0x1800023e0  jz      loc_18000247A
0x1800023e6  lea     rbx, ?_entries@?1??_GetEntries@CEnhancedStorageEnumerator@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CEnhancedStorageEnumerator::_GetEntries(void)'::`2'::_entries
0x1800023ed  nop     dword ptr [rax]
0x1800023f0  mov     r10, [rbx+10h]
0x1800023f4  test    r10, r10
0x1800023f7  jz      short loc_180002429
0x1800023f9  mov     rcx, [rbx]
0x1800023fc  test    rcx, rcx
0x1800023ff  jz      short loc_180002439
0x180002401  mov     eax, [rdi]
0x180002403  cmp     [rcx], eax
0x180002405  jz      short loc_18000240D
0x180002407  add     rbx, 18h
0x18000240b  jmp     short loc_1800023F0
0x18000240d  mov     eax, [rdi+4]
0x180002410  cmp     [rcx+4], eax
0x180002413  jnz     short loc_180002407
0x180002415  mov     eax, [rdi+8]
0x180002418  cmp     [rcx+8], eax
0x18000241b  jnz     short loc_180002407
0x18000241d  mov     eax, [rdi+0Ch]
0x180002420  cmp     [rcx+0Ch], eax
0x180002423  jnz     short loc_180002407
0x180002425  xor     ebp, ebp
0x180002427  jmp     short loc_18000243E
0x180002429  mov     eax, 80004002h
0x18000242e  add     rsp, 30h
0x180002432  pop     r14
0x180002434  pop     rdi
0x180002435  pop     rsi
0x180002436  pop     rbp
0x180002437  pop     rbx
0x180002438  retn
0x180002439  mov     ebp, 1
0x18000243e  cmp     r10, 1
0x180002442  jnz     short loc_1800024B1
0x180002444  mov     rbx, [rbx+8]
0x180002448  add     rbx, r14
0x18000244b  mov     rax, [rbx]
0x18000244e  mov     rcx, rbx
0x180002451  mov     rax, [rax+8]
0x180002455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245a  mov     [rsi], rbx
0x18000245d  xor     eax, eax
0x18000245f  add     rsp, 30h
0x180002463  pop     r14
0x180002465  pop     rdi
0x180002466  pop     rsi
0x180002467  pop     rbp
0x180002468  pop     rbx
0x180002469  retn
0x18000246a  mov     eax, 80004003h
0x18000246f  add     rsp, 30h
0x180002473  pop     r14
0x180002475  pop     rdi
0x180002476  pop     rsi
0x180002477  pop     rbp
0x180002478  pop     rbx
0x180002479  retn
0x18000247a  cmp     dword ptr [rdx+4], 0
0x18000247e  jnz     loc_1800023E6
0x180002484  cmp     dword ptr [rdx+8], 0C0h
0x18000248b  jnz     loc_1800023E6
0x180002491  cmp     dword ptr [rdx+0Ch], 46000000h
0x180002498  jnz     loc_1800023E6
0x18000249e  mov     rax, [rcx]
0x1800024a1  mov     rax, [rax+8]
0x1800024a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024aa  mov     [rsi], r14
0x1800024ad  xor     eax, eax
0x1800024af  jmp     short loc_18000245F
0x1800024b1  mov     r9, [rbx+8]
0x1800024b5  mov     r8, rsi
0x1800024b8  mov     rdx, rdi
0x1800024bb  mov     rcx, r14
0x1800024be  mov     rax, r10
0x1800024c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c6  test    eax, eax
0x1800024c8  jz      short loc_18000245F
0x1800024ca  test    ebp, ebp
0x1800024cc  jnz     loc_180002407
0x1800024d2  test    eax, eax
0x1800024d4  js      short loc_18000245F
0x1800024d6  jmp     loc_180002407
0x1800024db  mov     eax, 80070057h
0x1800024e0  jmp     loc_18000245F
```
