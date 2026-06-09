# utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::push_back(utl::unique_ptr<_URB,utl::default_delete<_URB>> &&)

- ea: `0x140002a94`
- end: `0x140002b34`
- name: `?push_back@?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@2@@Z`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400025e4`
- `0x140019764`

## callees

- `0x140002944`
- `0x140002a94`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::push_back(
        __int64 *a1,
        __int64 *a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbp
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  char v10; // di
  _QWORD *v11; // r8
  __int64 v12; // rax

  v4 = (_QWORD *)a1[1];
  v5 = (_QWORD *)a1[2];
  if ( v4 != v5 )
  {
    v6 = *a2;
    *a2 = 0;
    *v4 = v6;
LABEL_10:
    a1[1] += 8;
    return 1;
  }
  v7 = *a1;
  v8 = ((__int64)v5 - *a1) >> 3;
  v9 = 7 * (v8 >> 2) + 8;
  if ( v9 > 0xFFFFFFFFFFFFFFFLL )
    v9 = 0xFFFFFFFFFFFFFFFLL;
  v10 = 0;
  if ( v8 < v9
    && utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::_SetCapacity(
         (__int64)a1,
         v9) )
  {
    v11 = (_QWORD *)a1[1];
    if ( (char *)a2 - v7 < (char *)v11 - *a1 )
      a2 = (__int64 *)((char *)a2 + *a1 - v7);
    v12 = *a2;
    *a2 = 0;
    *v11 = v12;
    goto LABEL_10;
  }
  return v10;
}

```

## disassembly

```asm
0x140002a94  push    rbx
0x140002a96  push    rbp
0x140002a97  push    rsi
0x140002a98  push    rdi
0x140002a99  sub     rsp, 28h
0x140002a9d  mov     rsi, rdx
0x140002aa0  mov     rbx, rcx
0x140002aa3  mov     rdx, [rcx+8]
0x140002aa7  mov     rcx, [rcx+10h]
0x140002aab  cmp     rdx, rcx
0x140002aae  jz      short loc_140002ABD
0x140002ab0  mov     rax, [rsi]
0x140002ab3  xor     edi, edi
0x140002ab5  mov     [rsi], rdi
0x140002ab8  mov     [rdx], rax
0x140002abb  jmp     short loc_140002B1F
0x140002abd  mov     rbp, [rbx]
0x140002ac0  sub     rcx, rbp
0x140002ac3  sar     rcx, 3
0x140002ac7  mov     rax, rcx
0x140002aca  shr     rax, 2
0x140002ace  imul    rdx, rax, 7
0x140002ad2  mov     rax, 0FFFFFFFFFFFFFFFh
0x140002adc  add     rdx, 8
0x140002ae0  cmp     rdx, rax
0x140002ae3  cmova   rdx, rax
0x140002ae7  xor     edi, edi
0x140002ae9  cmp     rcx, rdx
0x140002aec  jnb     short loc_140002B27
0x140002aee  mov     rcx, rbx
0x140002af1  call    ?_SetCapacity@?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::_SetCapacity(unsigned __int64)
0x140002af6  test    al, al
0x140002af8  jz      short loc_140002B27
0x140002afa  mov     r8, [rbx+8]
0x140002afe  mov     rcx, rsi
0x140002b01  mov     rdx, [rbx]
0x140002b04  mov     rax, r8
0x140002b07  sub     rax, rdx
0x140002b0a  sub     rcx, rbp
0x140002b0d  cmp     rcx, rax
0x140002b10  jnb     short loc_140002B16
0x140002b12  lea     rsi, [rcx+rdx]
0x140002b16  mov     rax, [rsi]
0x140002b19  mov     [rsi], rdi
0x140002b1c  mov     [r8], rax
0x140002b1f  add     qword ptr [rbx+8], 8
0x140002b24  mov     dil, 1
0x140002b27  mov     al, dil
0x140002b2a  add     rsp, 28h
0x140002b2e  pop     rdi
0x140002b2f  pop     rsi
0x140002b30  pop     rbp
0x140002b31  pop     rbx
0x140002b32  retn
```
