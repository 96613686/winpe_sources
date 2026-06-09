# StringEnumerationMatcher::findMatches(Enumerator<ushort *> &,EditDistance &)

- ea: `0x18000ab58`
- end: `0x18000ae78`
- name: `?findMatches@StringEnumerationMatcher@@QEAAXAEAV?$Enumerator@PEAG@@AEAVEditDistance@@@Z`
- size: `800`
- prototype: `void __fastcall(_QWORD ***, unsigned int (__fastcall ***)(_QWORD, unsigned __int16 **), _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x1800015b8`
- `0x18000a960`
- `0x18000ab58`
- `0x18000e594`
- `0x180012010`

## import_xrefs

- `msvcrt!towlower` at `0x18000acac`
- `msvcrt!towlower` at `0x18000acb8`
- `msvcrt!towlower` at `0x18000acac`
- `msvcrt!towlower` at `0x18000acb8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000adc1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000adc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ada0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ada0`

## pseudocode

```c
void __fastcall StringEnumerationMatcher::findMatches(
        _QWORD ***a1,
        unsigned int (__fastcall ***a2)(_QWORD, unsigned __int16 **),
        _QWORD *a3)
{
  unsigned int (__fastcall ***v4)(_QWORD, unsigned __int16 **); // r8
  _QWORD *v5; // rsi
  __int64 v6; // rdx
  _QWORD **v7; // r8
  _QWORD *i; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // r14
  unsigned int v11; // eax
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // r14
  unsigned __int64 j; // rsi
  wint_t v18; // bx
  wint_t v19; // di
  wint_t v20; // r8
  __int64 v21; // r11
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r11
  int v24; // edx
  unsigned int v25; // r8d
  unsigned __int64 v26; // rcx
  bool v27; // cc
  __int64 v28; // rdi
  _QWORD *v29; // rbx
  _QWORD **v30; // rax
  void *v31; // rcx
  _QWORD *v32; // rcx
  _QWORD *v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rax
  unsigned __int64 v38; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v39; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v40; // [rsp+30h] [rbp-48h]
  unsigned __int16 *v43; // [rsp+98h] [rbp+20h] BYREF

  v4 = a2;
  v5 = a1;
  v43 = 0;
  if ( a1[1] )
  {
    v6 = 0;
    v7 = *a1;
    for ( i = **a1; i != v7; i = (_QWORD *)*i )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(i[2] + 2 * v9) );
      v6 += v9 + 2;
    }
    v38 = v6 - 2;
    v4 = a2;
  }
  else
  {
    v38 = 0;
  }
  if ( v5[3] )
  {
    while ( 1 )
    {
      if ( !(**v4)(v4, &v43) )
        return;
      v10 = -1;
      do
        ++v10;
      while ( v43[v10] );
      v40 = v10;
      if ( v5[6] > v5[5] )
        return;
      if ( !*a3 || v10 > a3[3] + 4LL )
        break;
      if ( v10 )
      {
        if ( !a3[2] )
          break;
        v39 = v43;
        v12 = v10 + 1;
        v13 = 0;
        if ( v10 != -1 )
        {
          do
          {
            *(_DWORD *)(*a3 + 4 * a3[3] * v13) = v13;
            ++v13;
          }
          while ( v13 < v12 );
        }
        v14 = 1;
        v15 = a3[3];
        if ( v15 > 1 )
        {
          v16 = v39;
          do
          {
            for ( j = 1; j < v12; ++j )
            {
              v18 = v16[j - 1];
              v19 = towlower(*(_WORD *)(a3[1] + 2 * v14 - 2));
              v20 = towlower(v18);
              v21 = a3[3];
              v22 = v14 + v21 * (j - 1);
              v23 = v14 + j * v21;
              v24 = *(_DWORD *)(*a3 + 4 * v23 - 4);
              v25 = (v19 != v20) + *(_DWORD *)(*a3 + 4 * v22 - 4);
              if ( v24 + 1 >= (unsigned int)(*(_DWORD *)(*a3 + 4 * v22) + 1) )
                v24 = *(_DWORD *)(*a3 + 4 * v22);
              if ( v25 >= v24 + 1 )
                v25 = v24 + 1;
              *(_DWORD *)(*a3 + 4 * v23) = v25;
            }
            ++v14;
            v15 = a3[3];
          }
          while ( v14 < v15 );
          v5 = a1;
          v10 = v40;
        }
        v11 = *(_DWORD *)(*a3 + 4 * v15 * (v10 + 1) - 4);
      }
      else
      {
        v11 = *((_DWORD *)a3 + 6);
      }
LABEL_33:
      if ( !v11 )
      {
        *((_DWORD *)v5 + 14) = 1;
        return;
      }
      v26 = a3[2];
      if ( v26 < 6 )
        v27 = v11 <= *((_DWORD *)qword_180016B90 + v26);
      else
        v27 = v11 <= 2;
      if ( v27 )
      {
        v28 = v11;
        if ( (unsigned __int64)v11 >= v5[8] )
        {
          if ( v11 != v5[8] )
            goto LABEL_54;
        }
        else
        {
          v29 = (_QWORD *)*v5;
          while ( 1 )
          {
            v29 = (_QWORD *)*v29;
            v30 = (_QWORD **)*v5;
            if ( v29 == (_QWORD *)*v5 )
              break;
            v31 = (void *)v29[2];
            if ( v31 )
              CoTaskMemFree(v31);
          }
          v32 = *v30;
          *v30 = v30;
          *(_QWORD *)(*v5 + 8LL) = *v5;
          v5[1] = 0;
          if ( v32 != (_QWORD *)*v5 )
          {
            do
            {
              v33 = (_QWORD *)*v32;
              operator delete(v32);
              v32 = v33;
            }
            while ( v33 != (_QWORD *)*v5 );
          }
          v5[8] = v28;
        }
        if ( v5[1] < v5[3] )
        {
          v39 = 0;
          v38 += v10 + 2;
          if ( v38 >= v5[4] )
            return;
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            AllocateAndLoadString(&v39, v43);
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &enum TestException `RTTI Type Descriptor', 0) )
            {
              __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_18000AE65);
              return;
            }
            if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
            {
              __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_18000AE65);
              return;
            }
          }
          if ( __eh34_try(-1, 2) )
          {
            __eh34_scope_strut(2);
            v35 = *v5;
            v36 = std::_List_buy<Repair *>::_Buynode<Repair * const &>(v34, *v5, *(_QWORD *)(*v5 + 8LL), &v39);
            v37 = v5[1];
            if ( v37 == 0xAAAAAAAAAAAAAA9LL )
              std::_Xlength_error("list<T> too long");
            v5[1] = v37 + 1;
            *(_QWORD *)(v35 + 8) = v36;
            **(_QWORD **)(v36 + 8) = v36;
          }
          if ( __eh34_catch(2) )
          {
            if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              CoTaskMemFree(v39);
              __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000AE65);
              return;
            }
          }
        }
      }
LABEL_54:
      ++v5[6];
      v4 = a2;
    }
    v11 = v10;
    goto LABEL_33;
  }
}

```

## disassembly

```asm
0x18000ab58  mov     rax, rsp
0x18000ab5b  mov     [rax+10h], rdx
0x18000ab5f  mov     [rax+8], rcx
0x18000ab63  push    rbx
0x18000ab64  push    rsi
0x18000ab65  push    rdi
0x18000ab66  push    r12
0x18000ab68  push    r13
0x18000ab6a  push    r14
0x18000ab6c  push    r15
0x18000ab6e  sub     rsp, 40h
0x18000ab72  mov     r15, r8
0x18000ab75  mov     r8, rdx
0x18000ab78  mov     rsi, rcx
0x18000ab7b  xor     r12d, r12d
0x18000ab7e  mov     [rax+20h], r12
0x18000ab82  cmp     [rcx+8], r12
0x18000ab86  jnz     short loc_18000AB8F
0x18000ab88  mov     [rsp+78h+var_58], r12
0x18000ab8d  jmp     short loc_18000ABCC
0x18000ab8f  mov     rdx, r12
0x18000ab92  mov     r8, [rcx]
0x18000ab95  mov     rax, [r8]
0x18000ab98  cmp     rax, r8
0x18000ab9b  jz      short loc_18000ABBB
0x18000ab9d  mov     r9, [rax+10h]
0x18000aba1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000aba5  inc     rcx
0x18000aba8  cmp     [r9+rcx*2], r12w
0x18000abad  jnz     short loc_18000ABA5
0x18000abaf  add     rdx, 2
0x18000abb3  add     rdx, rcx
0x18000abb6  mov     rax, [rax]
0x18000abb9  jmp     short loc_18000AB98
0x18000abbb  add     rdx, 0FFFFFFFFFFFFFFFEh
0x18000abbf  mov     [rsp+78h+var_58], rdx
0x18000abc4  mov     r8, [rsp+78h+arg_8]
0x18000abcc  cmp     [rsi+18h], r12
0x18000abd0  jz      loc_18000AD52
0x18000abd6  mov     rax, [r8]
0x18000abd9  lea     rdx, [rsp+78h+arg_18]
0x18000abe1  mov     rcx, r8
0x18000abe4  mov     rax, [rax]
0x18000abe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abec  test    eax, eax
0x18000abee  jz      loc_18000AD52
0x18000abf4  mov     rax, [rsp+78h+arg_18]
0x18000abfc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ac00  inc     r14
0x18000ac03  cmp     [rax+r14*2], r12w
0x18000ac08  jnz     short loc_18000AC00
0x18000ac0a  mov     [rsp+78h+var_48], r14
0x18000ac0f  mov     rax, [rsi+28h]
0x18000ac13  cmp     [rsi+30h], rax
0x18000ac17  ja      loc_18000AD52
0x18000ac1d  cmp     [r15], r12
0x18000ac20  jnz     short loc_18000AC2A
0x18000ac22  mov     eax, r14d
0x18000ac25  jmp     loc_18000AD47
0x18000ac2a  mov     rax, [r15+18h]
0x18000ac2e  add     rax, 4
0x18000ac32  cmp     r14, rax
0x18000ac35  ja      short loc_18000AC22
0x18000ac37  test    r14, r14
0x18000ac3a  jnz     short loc_18000AC45
0x18000ac3c  mov     eax, [r15+18h]
0x18000ac40  jmp     loc_18000AD47
0x18000ac45  cmp     [r15+10h], r12
0x18000ac49  jz      short loc_18000AC22
0x18000ac4b  mov     rax, [rsp+78h+arg_18]
0x18000ac53  mov     [rsp+78h+var_50], rax
0x18000ac58  lea     r13, [r14+1]
0x18000ac5c  mov     rdx, r12
0x18000ac5f  test    r13, r13
0x18000ac62  jz      short loc_18000AC7A
0x18000ac64  mov     rcx, rdx
0x18000ac67  imul    rcx, [r15+18h]
0x18000ac6c  mov     rax, [r15]
0x18000ac6f  mov     [rax+rcx*4], edx
0x18000ac72  inc     rdx
0x18000ac75  cmp     rdx, r13
0x18000ac78  jb      short loc_18000AC64
0x18000ac7a  mov     r12d, 1
0x18000ac80  mov     rax, [r15+18h]
0x18000ac84  cmp     rax, r12
0x18000ac87  jbe     loc_18000AD35
0x18000ac8d  mov     r14, [rsp+78h+var_50]
0x18000ac92  mov     esi, 1
0x18000ac97  cmp     r13, rsi
0x18000ac9a  jbe     short loc_18000AD18
0x18000ac9c  movzx   ebx, word ptr [r14+rsi*2-2]
0x18000aca2  mov     rcx, [r15+8]
0x18000aca6  movzx   ecx, word ptr [rcx+r12*2-2]; C
0x18000acac  call    cs:__imp_towlower
0x18000acb2  movzx   edi, ax
0x18000acb5  movzx   ecx, bx; C
0x18000acb8  call    cs:__imp_towlower
0x18000acbe  movzx   r8d, ax
0x18000acc2  mov     r11, [r15+18h]
0x18000acc6  mov     r10, [r15]
0x18000acc9  lea     rax, [rsi-1]
0x18000accd  imul    rax, r11
0x18000acd1  add     rax, r12
0x18000acd4  mov     r9d, [r10+rax*4]
0x18000acd8  imul    r11, rsi
0x18000acdc  add     r11, r12
0x18000acdf  mov     edx, [r10+r11*4-4]
0x18000ace4  xor     ecx, ecx
0x18000ace6  cmp     di, r8w
0x18000acea  setnz   cl
0x18000aced  mov     r8d, [r10+rax*4-4]
0x18000acf2  add     r8d, ecx
0x18000acf5  lea     ecx, [rdx+1]
0x18000acf8  lea     eax, [r9+1]
0x18000acfc  cmp     ecx, eax
0x18000acfe  cmovnb  edx, r9d
0x18000ad02  lea     eax, [rdx+1]
0x18000ad05  cmp     r8d, eax
0x18000ad08  cmovnb  r8d, eax
0x18000ad0c  mov     [r10+r11*4], r8d
0x18000ad10  inc     rsi
0x18000ad13  cmp     rsi, r13
0x18000ad16  jb      short loc_18000AC9C
0x18000ad18  inc     r12
0x18000ad1b  mov     rax, [r15+18h]
0x18000ad1f  cmp     r12, rax
0x18000ad22  jb      loc_18000AC92
0x18000ad28  mov     rsi, [rsp+78h+arg_0]
0x18000ad30  mov     r14, [rsp+78h+var_48]
0x18000ad35  lea     rcx, [r14+1]
0x18000ad39  imul    rcx, rax
0x18000ad3d  mov     rax, [r15]
0x18000ad40  mov     eax, [rax+rcx*4-4]
0x18000ad44  xor     r12d, r12d
0x18000ad47  test    eax, eax
0x18000ad49  jnz     short loc_18000AD62
0x18000ad4b  mov     dword ptr [rsi+38h], 1
0x18000ad52  add     rsp, 40h
0x18000ad56  pop     r15
0x18000ad58  pop     r14
0x18000ad5a  pop     r13
0x18000ad5c  pop     r12
0x18000ad5e  pop     rdi
0x18000ad5f  pop     rsi
0x18000ad60  pop     rbx
0x18000ad61  retn
0x18000ad62  mov     rcx, [r15+10h]
0x18000ad66  cmp     rcx, 6
0x18000ad6a  jb      short loc_18000AD71
0x18000ad6c  cmp     eax, 2
0x18000ad6f  jmp     short loc_18000AD7B
0x18000ad71  lea     rdx, qword_180016B90
0x18000ad78  cmp     eax, [rdx+rcx*4]
0x18000ad7b  ja      loc_18000AE54
0x18000ad81  mov     edi, eax
0x18000ad83  cmp     rdi, [rsi+40h]
0x18000ad87  jnb     short loc_18000ADD5
0x18000ad89  mov     rbx, [rsi]
0x18000ad8c  mov     rbx, [rbx]
0x18000ad8f  mov     rax, [rsi]
0x18000ad92  cmp     rbx, rax
0x18000ad95  jz      short loc_18000ADA8
0x18000ad97  mov     rcx, [rbx+10h]; pv
0x18000ad9b  test    rcx, rcx
0x18000ad9e  jz      short loc_18000AD8C
0x18000ada0  call    cs:__imp_CoTaskMemFree
0x18000ada6  jmp     short loc_18000AD8C
0x18000ada8  mov     rcx, [rax]
0x18000adab  mov     [rax], rax
0x18000adae  mov     rax, [rsi]
0x18000adb1  mov     [rax+8], rax
0x18000adb5  mov     [rsi+8], r12
0x18000adb9  cmp     rcx, [rsi]
0x18000adbc  jz      short loc_18000ADCF
0x18000adbe  mov     rbx, [rcx]
0x18000adc1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000adc7  mov     rcx, rbx
0x18000adca  cmp     rbx, [rsi]
0x18000adcd  jnz     short loc_18000ADBE
0x18000adcf  mov     [rsi+40h], rdi
0x18000add3  jmp     short loc_18000ADD7
0x18000add5  jnz     short loc_18000AE54
0x18000add7  mov     rax, [rsi+18h]
0x18000addb  cmp     [rsi+8], rax
0x18000addf  jnb     short loc_18000AE54
0x18000ade1  mov     [rsp+78h+var_50], r12
0x18000ade6  mov     rdi, [rsp+78h+var_58]
0x18000adeb  add     rdi, 2
0x18000adef  add     rdi, r14
0x18000adf2  mov     [rsp+78h+var_58], rdi
0x18000adf7  cmp     rdi, [rsi+20h]
0x18000adfb  jnb     loc_18000AD52
0x18000ae01  mov     rdx, [rsp+78h+arg_18]; unsigned __int16 *
0x18000ae09  lea     rcx, [rsp+78h+var_50]; unsigned __int16 **
0x18000ae0e  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000ae13  nop
0x18000ae14  mov     rbx, [rsi]
0x18000ae17  lea     r9, [rsp+78h+var_50]
0x18000ae1c  mov     r8, [rbx+8]
0x18000ae20  mov     rdx, rbx
0x18000ae23  call    ??$_Buynode@AEBQEAVRepair@@@?$_List_buy@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@1@PEAU21@0AEBQEAVRepair@@@Z; std::_List_buy<Repair *>::_Buynode<Repair * const &>(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *,Repair * const &)
0x18000ae28  mov     rdx, rax
0x18000ae2b  mov     rax, [rsi+8]
0x18000ae2f  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000ae39  sub     rcx, rax
0x18000ae3c  cmp     rcx, 1
0x18000ae40  jb      short loc_18000AE6A
0x18000ae42  inc     rax
0x18000ae45  mov     [rsi+8], rax
0x18000ae49  mov     [rbx+8], rdx
0x18000ae4d  mov     rax, [rdx+8]
0x18000ae51  mov     [rax], rdx
0x18000ae54  inc     qword ptr [rsi+30h]
0x18000ae58  mov     r8, [rsp+78h+arg_8]
0x18000ae60  jmp     loc_18000ABD6
0x18000ae65  jmp     loc_18000AD52
0x18000ae6a  lea     rcx, aListTTooLong; "list<T> too long"
0x18000ae71  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
