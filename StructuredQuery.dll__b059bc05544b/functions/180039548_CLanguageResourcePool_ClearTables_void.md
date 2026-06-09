# CLanguageResourcePool::_ClearTables(void)

- ea: `0x180039548`
- end: `0x1800395cf`
- name: `?_ClearTables@CLanguageResourcePool@@AEAAXXZ`
- size: `135`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038318`
- `0x1800390d0`

## callees

- `0x180039548`
- `0x18003980c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003955f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003955f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395c2`

## pseudocode

```c
void __fastcall CLanguageResourcePool::_ClearTables(LPVOID *this)
{
  _QWORD *v1; // rsi
  struct WORDBREAKER_CLASS_NODE *v3; // rbx
  _QWORD *v4; // rbx
  struct WORDBREAKER_CLASS_NODE *v5; // rbp

  v1 = this + 5;
  CoTaskMemFree(this[5]);
  v3 = (struct WORDBREAKER_CLASS_NODE *)this[6];
  if ( v3 )
  {
    v5 = (struct WORDBREAKER_CLASS_NODE *)((char *)v3 + 104 * *((unsigned int *)this + 8));
    if ( v3 >= v5 )
    {
      v4 = this + 6;
    }
    else
    {
      do
      {
        CLanguageResourcePool::_DeleteWordBreakerClassNodeWithSiblings(v3);
        v3 = (struct WORDBREAKER_CLASS_NODE *)((char *)v3 + 104);
      }
      while ( v3 < v5 );
      v1 = this + 5;
      v4 = this + 6;
    }
    CoTaskMemFree(this[6]);
  }
  else
  {
    v4 = this + 6;
  }
  this[4] = 0;
  *v1 = 0;
  *v4 = 0;
}

```

## disassembly

```asm
0x180039548  push    rbx
0x18003954a  push    rbp
0x18003954b  push    rsi
0x18003954c  push    rdi
0x18003954d  push    r14
0x18003954f  push    r15
0x180039551  sub     rsp, 28h
0x180039555  lea     rsi, [rcx+28h]
0x180039559  mov     rdi, rcx
0x18003955c  mov     rcx, [rsi]; pv
0x18003955f  call    cs:__imp_CoTaskMemFree
0x180039565  lea     r15, [rdi+30h]
0x180039569  mov     rbx, [r15]
0x18003956c  test    rbx, rbx
0x18003956f  jnz     short loc_180039597
0x180039571  mov     rbx, r15
0x180039574  mov     qword ptr [rdi+20h], 0
0x18003957c  mov     qword ptr [rsi], 0
0x180039583  mov     qword ptr [rbx], 0
0x18003958a  add     rsp, 28h
0x18003958e  pop     r15
0x180039590  pop     r14
0x180039592  pop     rdi
0x180039593  pop     rsi
0x180039594  pop     rbp
0x180039595  pop     rbx
0x180039596  retn
0x180039597  mov     eax, [rdi+20h]
0x18003959a  imul    rbp, rax, 68h ; 'h'
0x18003959e  add     rbp, rbx
0x1800395a1  cmp     rbx, rbp
0x1800395a4  jnb     short loc_1800395CA
0x1800395a6  mov     rcx, rbx; struct WORDBREAKER_CLASS_NODE *
0x1800395a9  call    ?_DeleteWordBreakerClassNodeWithSiblings@CLanguageResourcePool@@CAXPEAUWORDBREAKER_CLASS_NODE@@@Z; CLanguageResourcePool::_DeleteWordBreakerClassNodeWithSiblings(WORDBREAKER_CLASS_NODE *)
0x1800395ae  add     rbx, 68h ; 'h'
0x1800395b2  cmp     rbx, rbp
0x1800395b5  jb      short loc_1800395A6
0x1800395b7  lea     rsi, [rdi+28h]
0x1800395bb  lea     rbx, [rdi+30h]
0x1800395bf  mov     rcx, [r15]; pv
0x1800395c2  call    cs:__imp_CoTaskMemFree
0x1800395c8  jmp     short loc_180039574
0x1800395ca  mov     rbx, r15
0x1800395cd  jmp     short loc_1800395BF
```
