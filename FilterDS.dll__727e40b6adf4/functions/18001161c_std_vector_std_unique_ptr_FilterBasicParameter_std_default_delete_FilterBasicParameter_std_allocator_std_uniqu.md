# std::vector<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>,std::allocator<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>>>::push_back(std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>> &&)

- ea: `0x18001161c`
- end: `0x180011769`
- name: `?push_back@?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@2@@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001094c`

## callees

- `0x18000cd9c`
- `0x1800112f0`
- `0x18001161c`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<FilterBasicParameter>>::push_back(__int64 *a1, __int64 *a2)
{
  unsigned __int64 v4; // rcx
  bool v5; // al
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  __int64 result; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rcx

  v4 = a1[1];
  v5 = (unsigned __int64)a2 < v4 && *a1 <= (unsigned __int64)a2;
  v6 = a1[2];
  if ( v5 )
  {
    v7 = *a1;
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v8 = (__int64)(v4 - v7) >> 3;
      if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v9 = v8 + 1;
      v10 = 0;
      v11 = (v6 - v7) >> 3;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v10 = v11 + (v11 >> 1);
      if ( v10 < v9 )
        v10 = v9;
      std::vector<std::unique_ptr<FilterBasicParameter>>::_Reallocate((__int64)a1, v10);
    }
    v12 = (_QWORD *)a1[1];
    v13 = ((__int64)a2 - v7) >> 3;
    result = *(_QWORD *)(*a1 + 8 * v13);
    *(_QWORD *)(*a1 + 8 * v13) = 0;
    *v12 = result;
  }
  else
  {
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v15 = (__int64)(v4 - *a1) >> 3;
      if ( v15 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v16 = v15 + 1;
      v17 = (v6 - *a1) >> 3;
      v18 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v17 >> 1) >= v17 )
        v18 = v17 + (v17 >> 1);
      if ( v18 < v16 )
        v18 = v16;
      std::vector<std::unique_ptr<FilterBasicParameter>>::_Reallocate((__int64)a1, v18);
    }
    v19 = (_QWORD *)a1[1];
    result = *a2;
    *a2 = 0;
    *v19 = result;
  }
  a1[1] += 8;
  return result;
}

```

## disassembly

```asm
0x18001161c  mov     [rsp+arg_0], rbx
0x180011621  mov     [rsp+arg_8], rsi
0x180011626  push    rdi
0x180011627  sub     rsp, 20h
0x18001162b  mov     rbx, rcx
0x18001162e  mov     rdi, rdx
0x180011631  mov     rcx, [rcx+8]
0x180011635  cmp     rdx, rcx
0x180011638  jnb     short loc_180011643
0x18001163a  cmp     [rbx], rdx
0x18001163d  ja      short loc_180011643
0x18001163f  mov     al, 1
0x180011641  jmp     short loc_180011645
0x180011643  xor     al, al
0x180011645  mov     r8, [rbx+10h]
0x180011649  test    al, al
0x18001164b  jz      loc_1800116D7
0x180011651  mov     rsi, [rbx]
0x180011654  cmp     rcx, r8
0x180011657  jnz     short loc_1800116B8
0x180011659  mov     rax, r8
0x18001165c  sub     rax, rcx
0x18001165f  sar     rax, 3
0x180011663  cmp     rax, 1
0x180011667  jnb     short loc_1800116B8
0x180011669  sub     rcx, rsi
0x18001166c  mov     r9, 1FFFFFFFFFFFFFFFh
0x180011676  sar     rcx, 3
0x18001167a  mov     rax, r9
0x18001167d  sub     rax, rcx
0x180011680  cmp     rax, 1
0x180011684  jb      loc_180011763
0x18001168a  inc     rcx
0x18001168d  xor     edx, edx
0x18001168f  sub     r8, rsi
0x180011692  sar     r8, 3
0x180011696  mov     rax, r8
0x180011699  shr     rax, 1
0x18001169c  sub     r9, rax
0x18001169f  add     rax, r8
0x1800116a2  cmp     r9, r8
0x1800116a5  cmovnb  rdx, rax
0x1800116a9  cmp     rdx, rcx
0x1800116ac  cmovb   rdx, rcx
0x1800116b0  mov     rcx, rbx
0x1800116b3  call    ?_Reallocate@?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<FilterBasicParameter>>::_Reallocate(unsigned __int64)
0x1800116b8  mov     rcx, [rbx]
0x1800116bb  sub     rdi, rsi
0x1800116be  mov     rdx, [rbx+8]
0x1800116c2  sar     rdi, 3
0x1800116c6  mov     rax, [rcx+rdi*8]
0x1800116ca  mov     qword ptr [rcx+rdi*8], 0
0x1800116d2  mov     [rdx], rax
0x1800116d5  jmp     short loc_180011748
0x1800116d7  cmp     rcx, r8
0x1800116da  jnz     short loc_180011737
0x1800116dc  mov     rax, r8
0x1800116df  sub     rax, rcx
0x1800116e2  sar     rax, 3
0x1800116e6  cmp     rax, 1
0x1800116ea  jnb     short loc_180011737
0x1800116ec  sub     rcx, [rbx]
0x1800116ef  mov     r9, 1FFFFFFFFFFFFFFFh
0x1800116f9  sar     rcx, 3
0x1800116fd  mov     rax, r9
0x180011700  sub     rax, rcx
0x180011703  cmp     rax, 1
0x180011707  jb      short loc_18001175D
0x180011709  sub     r8, [rbx]
0x18001170c  inc     rcx
0x18001170f  sar     r8, 3
0x180011713  xor     edx, edx
0x180011715  mov     rax, r8
0x180011718  shr     rax, 1
0x18001171b  sub     r9, rax
0x18001171e  add     rax, r8
0x180011721  cmp     r9, r8
0x180011724  cmovnb  rdx, rax
0x180011728  cmp     rdx, rcx
0x18001172b  cmovb   rdx, rcx
0x18001172f  mov     rcx, rbx
0x180011732  call    ?_Reallocate@?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<FilterBasicParameter>>::_Reallocate(unsigned __int64)
0x180011737  mov     rcx, [rbx+8]
0x18001173b  mov     rax, [rdi]
0x18001173e  mov     qword ptr [rdi], 0
0x180011745  mov     [rcx], rax
0x180011748  add     qword ptr [rbx+8], 8
0x18001174d  mov     rbx, [rsp+28h+arg_0]
0x180011752  mov     rsi, [rsp+28h+arg_8]
0x180011757  add     rsp, 20h
0x18001175b  pop     rdi
0x18001175c  retn
0x18001175d  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
0x180011763  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
