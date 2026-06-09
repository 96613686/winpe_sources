# wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)

- ea: `0x1800056fc`
- end: `0x1800057d0`
- name: `?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z`
- size: `212`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004b60`
- `0x1800095a8`
- `0x18000bff0`

## callees

- `0x1800056fc`
- `0x180005950`
- `0x180005988`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::SetBuffer(void **this, char *a2, unsigned __int64 a3, const char *a4)
{
  _WORD *v8; // rcx
  char v9; // al
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( (unsigned __int64)a4 < 0xA )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, a2, a3, a4);
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(this + 6, 0);
  this[3] = a2;
  this[4] = &a2[a3];
  *((_BYTE *)this + 57) = 0;
  this[5] = (void *)&a4[(_QWORD)a2];
  if ( a3 < 0xA )
    goto LABEL_13;
  v8 = a2 + 2;
  if ( *(_WORD *)a2 || (v9 = 0, *v8 > *(_WORD *)this) )
    v9 = 1;
  *((_BYTE *)this + 57) = v9;
  if ( *(_WORD *)a2
    || *v8 != *(_WORD *)this
    || *((_WORD *)a2 + 2) != *((_WORD *)this + 1)
    || a2[8] != *((_BYTE *)this + 4)
    || *((_WORD *)a2 + 3) != *((_WORD *)this + 3)
    || a2[9] != *((_BYTE *)this + 8) )
  {
LABEL_13:
    *(_WORD *)a2 = 0;
    *((_WORD *)a2 + 1) = *(_WORD *)this;
    *((_WORD *)a2 + 2) = *((_WORD *)this + 1);
    a2[8] = *((_BYTE *)this + 4);
    *((_WORD *)a2 + 3) = *((_WORD *)this + 3);
    a2[9] = *((_BYTE *)this + 8);
    this[4] = (char *)this[3] + 10;
  }
}

```

## disassembly

```asm
0x1800056fc  push    rbx
0x1800056fe  push    rbp
0x1800056ff  push    rsi
0x180005700  push    rdi
0x180005701  sub     rsp, 28h
0x180005705  mov     rsi, r9
0x180005708  mov     rbp, r8
0x18000570b  mov     rdi, rdx
0x18000570e  mov     rbx, rcx
0x180005711  cmp     r9, 0Ah
0x180005715  jnb     short loc_180005722
0x180005717  mov     rcx, [rsp+48h]; this
0x18000571c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005722  add     rcx, 30h ; '0'
0x180005726  xor     edx, edx
0x180005728  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x18000572d  lea     rax, [rdi+rbp]
0x180005731  mov     [rbx+18h], rdi
0x180005735  xor     edx, edx
0x180005737  mov     [rbx+20h], rax
0x18000573b  mov     [rbx+39h], dl
0x18000573e  lea     rax, [rdi+rsi]
0x180005742  mov     [rbx+28h], rax
0x180005746  cmp     rbp, 0Ah
0x18000574a  jb      short loc_180005795
0x18000574c  lea     rcx, [rdi+2]
0x180005750  cmp     [rdi], dx
0x180005753  ja      short loc_18000575F
0x180005755  movzx   eax, word ptr [rbx]
0x180005758  cmp     [rcx], ax
0x18000575b  mov     al, dl
0x18000575d  jbe     short loc_180005761
0x18000575f  mov     al, 1
0x180005761  mov     [rbx+39h], al
0x180005764  cmp     [rdi], dx
0x180005767  jnz     short loc_180005795
0x180005769  movzx   eax, word ptr [rbx]
0x18000576c  cmp     [rcx], ax
0x18000576f  jnz     short loc_180005795
0x180005771  movzx   eax, word ptr [rbx+2]
0x180005775  cmp     [rdi+4], ax
0x180005779  jnz     short loc_180005795
0x18000577b  mov     al, [rbx+4]
0x18000577e  cmp     [rdi+8], al
0x180005781  jnz     short loc_180005795
0x180005783  movzx   eax, word ptr [rbx+6]
0x180005787  cmp     [rdi+6], ax
0x18000578b  jnz     short loc_180005795
0x18000578d  mov     al, [rbx+8]
0x180005790  cmp     [rdi+9], al
0x180005793  jz      short loc_1800057C7
0x180005795  mov     [rdi], dx
0x180005798  movzx   eax, word ptr [rbx]
0x18000579b  mov     [rdi+2], ax
0x18000579f  movzx   eax, word ptr [rbx+2]
0x1800057a3  mov     [rdi+4], ax
0x1800057a7  mov     al, [rbx+4]
0x1800057aa  mov     [rdi+8], al
0x1800057ad  movzx   eax, word ptr [rbx+6]
0x1800057b1  mov     [rdi+6], ax
0x1800057b5  mov     al, [rbx+8]
0x1800057b8  mov     [rdi+9], al
0x1800057bb  mov     rax, [rbx+18h]
0x1800057bf  add     rax, 0Ah
0x1800057c3  mov     [rbx+20h], rax
0x1800057c7  add     rsp, 28h
0x1800057cb  pop     rdi
0x1800057cc  pop     rsi
0x1800057cd  pop     rbp
0x1800057ce  pop     rbx
0x1800057cf  retn
```
