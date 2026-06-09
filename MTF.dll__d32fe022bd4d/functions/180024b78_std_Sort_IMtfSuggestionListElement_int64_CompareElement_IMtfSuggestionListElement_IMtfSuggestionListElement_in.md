# std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,__int64,CompareElement)

- ea: `0x180024b78`
- end: `0x180024de4`
- name: `??$_Sort@PEAPEAUIMtfSuggestionListElement@@_JUCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@0_JUCompareElement@@@Z`
- size: `620`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024b78`
- `0x18002a220`

## callees

- `0x180002972`
- `0x180024930`
- `0x180024b78`
- `0x180024dec`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(
        char *a1,
        char *a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl
  __int64 result; // rax
  char *v7; // rsi
  char *v8; // r14
  char *v9; // r12
  char *v10; // r15
  __int64 v11; // r9
  __int64 v12; // rdi
  __int64 k; // r15
  char *i; // rdi
  __int64 *v15; // r13
  __int64 *v16; // rbx
  __int64 v17; // rax
  char *v18; // r12
  char *j; // r15
  __int64 v20; // rax
  __int64 *v21; // rbx
  __int64 v22; // rax
  int v23; // [rsp+20h] [rbp-30h]
  unsigned int v24; // [rsp+30h] [rbp-20h] BYREF
  char *v25; // [rsp+38h] [rbp-18h] BYREF
  char *v26; // [rsp+40h] [rbp-10h]
  __int64 v27; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v28; // [rsp+98h] [rbp+48h] BYREF

  v4 = a4;
  result = (a2 - a1) >> 3;
  v7 = a2;
  v8 = a1;
  if ( result <= 32 )
    goto LABEL_14;
  do
  {
    if ( a3 <= 0 )
      break;
    LOBYTE(a4) = v4;
    std::_Unguarded_partition<IMtfSuggestionListElement * *,CompareElement>(&v25, v8, v7, a4);
    v9 = v25;
    v10 = v26;
    LOBYTE(v11) = v4;
    a3 = a3 / 2 / 2 + a3 / 2;
    if ( (__int64)((v25 - v8) & 0xFFFFFFFFFFFFFFF8uLL) >= (__int64)((v7 - v26) & 0xFFFFFFFFFFFFFFF8uLL) )
    {
      std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(v26, v7, a3, v11);
      v7 = v9;
    }
    else
    {
      std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(v8, v25, a3, v11);
      v8 = v10;
    }
    result = (v7 - v8) >> 3;
  }
  while ( result > 32 );
  if ( result <= 32 )
  {
LABEL_14:
    if ( result > 1 && v8 != v7 )
    {
      for ( i = v8 + 8; i != v7; i += 8 )
      {
        v15 = *(__int64 **)i;
        v16 = *(__int64 **)v8;
        v28 = 0;
        (*(void (__fastcall **)(__int64 *, unsigned int *))(*v15 + 24))(v15, &v28);
        v17 = *v16;
        LODWORD(v27) = 0;
        (*(void (__fastcall **)(__int64 *, __int64 *))(v17 + 24))(v16, &v27);
        if ( v28 <= (unsigned int)v27 )
        {
          v18 = i;
          for ( j = i; ; v18 = j )
          {
            v20 = *v15;
            j -= 8;
            v28 = 0;
            v21 = *(__int64 **)j;
            (*(void (__fastcall **)(__int64 *, unsigned int *))(v20 + 24))(v15, &v28);
            v22 = *v21;
            v24 = 0;
            (*(void (__fastcall **)(__int64 *, unsigned int *))(v22 + 24))(v21, &v24);
            result = v24;
            if ( v28 <= v24 )
              break;
            *(_QWORD *)v18 = *(_QWORD *)j;
          }
          *(_QWORD *)v18 = v15;
        }
        else
        {
          result = (__int64)memmove_0(&i[-((i - v8) & 0xFFFFFFFFFFFFFFF8uLL) + 8], v8, (i - v8) & 0xFFFFFFFFFFFFFFF8uLL);
          *(_QWORD *)v8 = v15;
        }
      }
    }
  }
  else
  {
    v12 = (v7 - v8) >> 3;
    if ( v12 > 1 )
    {
      for ( k = v12 / 2;
            k > 0;
            std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(
              (_DWORD)v8,
              k,
              (v7 - v8) >> 3,
              (unsigned int)&v27,
              v23) )
      {
        --k;
        LOBYTE(v23) = v4;
        v27 = *(_QWORD *)&v8[8 * k];
      }
      do
      {
        LOBYTE(v23) = v4;
        v27 = *((_QWORD *)v7 - 1);
        *((_QWORD *)v7 - 1) = *(_QWORD *)v8;
        std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(
          (_DWORD)v8,
          0,
          (v7 - v8 - 8) >> 3,
          (unsigned int)&v27,
          v23);
        v7 -= 8;
        result = (v7 - v8) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      while ( result > 8 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024b78  mov     [rsp-38h+arg_10], rbx
0x180024b7d  push    rbp
0x180024b7e  push    rsi
0x180024b7f  push    rdi
0x180024b80  push    r12
0x180024b82  push    r13
0x180024b84  push    r14
0x180024b86  push    r15
0x180024b88  mov     rbp, rsp
0x180024b8b  sub     rsp, 50h
0x180024b8f  mov     rax, rdx
0x180024b92  mov     bl, r9b
0x180024b95  sub     rax, rcx
0x180024b98  mov     rdi, r8
0x180024b9b  sar     rax, 3
0x180024b9f  mov     rsi, rdx
0x180024ba2  mov     r14, rcx
0x180024ba5  cmp     rax, 20h ; ' '
0x180024ba9  jle     loc_180024CE5
0x180024baf  test    rdi, rdi
0x180024bb2  jle     loc_180024C3C
0x180024bb8  mov     r9b, bl
0x180024bbb  lea     rcx, [rbp+var_18]
0x180024bbf  mov     r8, rsi
0x180024bc2  mov     rdx, r14
0x180024bc5  call    ??$_Unguarded_partition@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YA?AU?$pair@PEAPEAUIMtfSuggestionListElement@@PEAPEAU1@@0@PEAPEAUIMtfSuggestionListElement@@0UCompareElement@@@Z; std::_Unguarded_partition<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)
0x180024bca  mov     r12, [rbp+var_18]
0x180024bce  mov     rax, rdi
0x180024bd1  mov     r15, [rbp+var_10]
0x180024bd5  cqo
0x180024bd7  sub     rax, rdx
0x180024bda  mov     rcx, rsi
0x180024bdd  sar     rax, 1
0x180024be0  sub     rcx, r15
0x180024be3  mov     rdi, rax
0x180024be6  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180024bea  cqo
0x180024bec  mov     r9b, bl
0x180024bef  sub     rax, rdx
0x180024bf2  sar     rax, 1
0x180024bf5  add     rdi, rax
0x180024bf8  mov     rax, r12
0x180024bfb  sub     rax, r14
0x180024bfe  mov     r8, rdi
0x180024c01  and     rax, 0FFFFFFFFFFFFFFF8h
0x180024c05  cmp     rax, rcx
0x180024c08  jge     short loc_180024C1A
0x180024c0a  mov     rdx, r12
0x180024c0d  mov     rcx, r14
0x180024c10  call    ??$_Sort@PEAPEAUIMtfSuggestionListElement@@_JUCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@0_JUCompareElement@@@Z; std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,__int64,CompareElement)
0x180024c15  mov     r14, r15
0x180024c18  jmp     short loc_180024C28
0x180024c1a  mov     rdx, rsi
0x180024c1d  mov     rcx, r15
0x180024c20  call    ??$_Sort@PEAPEAUIMtfSuggestionListElement@@_JUCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@0_JUCompareElement@@@Z; std::_Sort<IMtfSuggestionListElement * *,__int64,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,__int64,CompareElement)
0x180024c25  mov     rsi, r12
0x180024c28  mov     rax, rsi
0x180024c2b  sub     rax, r14
0x180024c2e  sar     rax, 3
0x180024c32  cmp     rax, 20h ; ' '
0x180024c36  jg      loc_180024BAF
0x180024c3c  cmp     rax, 20h ; ' '
0x180024c40  jle     loc_180024CE5
0x180024c46  mov     rdi, rsi
0x180024c49  sub     rdi, r14
0x180024c4c  sar     rdi, 3
0x180024c50  cmp     rdi, 1
0x180024c54  jle     loc_180024DCC
0x180024c5a  mov     rax, rdi
0x180024c5d  cqo
0x180024c5f  sub     rax, rdx
0x180024c62  sar     rax, 1
0x180024c65  mov     r15, rax
0x180024c68  test    rax, rax
0x180024c6b  jle     short loc_180024C95
0x180024c6d  dec     r15
0x180024c70  mov     byte ptr [rsp+50h+var_30], bl
0x180024c74  lea     r9, [rbp+arg_0]
0x180024c78  mov     r8, rdi
0x180024c7b  mov     rdx, r15
0x180024c7e  mov     rcx, [r14+r15*8]
0x180024c82  mov     [rbp+arg_0], rcx
0x180024c86  mov     rcx, r14
0x180024c89  call    ??$_Adjust_heap@PEAPEAUIMtfSuggestionListElement@@_JPEAU1@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@_J1$$QEAPEAU1@UCompareElement@@@Z; std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(IMtfSuggestionListElement * *,__int64,__int64,IMtfSuggestionListElement * &&,CompareElement)
0x180024c8e  test    r15, r15
0x180024c91  jg      short loc_180024C6D
0x180024c93  jmp     short loc_180024C9F
0x180024c95  cmp     rdi, 1
0x180024c99  jle     loc_180024DCC
0x180024c9f  lea     rdi, [rsi-8]
0x180024ca3  mov     byte ptr [rsp+50h+var_30], bl
0x180024ca7  mov     rax, [rdi]
0x180024caa  lea     r9, [rbp+arg_0]
0x180024cae  mov     [rbp+arg_0], rax
0x180024cb2  sub     rsi, r14
0x180024cb5  mov     rax, [r14]
0x180024cb8  xor     edx, edx
0x180024cba  mov     rcx, r14
0x180024cbd  mov     [rdi], rax
0x180024cc0  lea     r8, [rsi-8]
0x180024cc4  sar     r8, 3
0x180024cc8  call    ??$_Adjust_heap@PEAPEAUIMtfSuggestionListElement@@_JPEAU1@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@_J1$$QEAPEAU1@UCompareElement@@@Z; std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(IMtfSuggestionListElement * *,__int64,__int64,IMtfSuggestionListElement * &&,CompareElement)
0x180024ccd  mov     rax, rdi
0x180024cd0  mov     rsi, rdi
0x180024cd3  sub     rax, r14
0x180024cd6  and     rax, 0FFFFFFFFFFFFFFF8h
0x180024cda  cmp     rax, 8
0x180024cde  jg      short loc_180024C9F
0x180024ce0  jmp     loc_180024DCC
0x180024ce5  cmp     rax, 1
0x180024ce9  jle     loc_180024DCC
0x180024cef  cmp     r14, rsi
0x180024cf2  jz      loc_180024DCC
0x180024cf8  lea     rdi, [r14+8]
0x180024cfc  jmp     loc_180024DC3
0x180024d01  mov     r13, [rdi]
0x180024d04  lea     rdx, [rbp+arg_8]
0x180024d08  mov     rbx, [r14]
0x180024d0b  mov     rcx, r13
0x180024d0e  mov     [rbp+arg_8], 0
0x180024d15  mov     rax, [r13+0]
0x180024d19  mov     rax, [rax+18h]
0x180024d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d22  mov     rax, [rbx]
0x180024d25  lea     rdx, [rbp+arg_0]
0x180024d29  mov     rcx, rbx
0x180024d2c  mov     dword ptr [rbp+arg_0], 0
0x180024d33  mov     rax, [rax+18h]
0x180024d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d3c  mov     eax, dword ptr [rbp+arg_0]
0x180024d3f  cmp     [rbp+arg_8], eax
0x180024d42  jbe     short loc_180024D65
0x180024d44  mov     r8, rdi
0x180024d47  mov     rcx, rdi
0x180024d4a  sub     r8, r14
0x180024d4d  mov     rdx, r14; Src
0x180024d50  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180024d54  sub     rcx, r8
0x180024d57  add     rcx, 8; void *
0x180024d5b  call    memmove_0
0x180024d60  mov     [r14], r13
0x180024d63  jmp     short loc_180024DBF
0x180024d65  mov     r12, rdi
0x180024d68  mov     r15, rdi
0x180024d6b  mov     rax, [r13+0]
0x180024d6f  lea     rdx, [rbp+arg_8]
0x180024d73  sub     r15, 8
0x180024d77  mov     [rbp+arg_8], 0
0x180024d7e  mov     rcx, r13
0x180024d81  mov     rax, [rax+18h]
0x180024d85  mov     rbx, [r15]
0x180024d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d8d  mov     rax, [rbx]
0x180024d90  lea     rdx, [rbp+var_20]
0x180024d94  mov     rcx, rbx
0x180024d97  mov     [rbp+var_20], 0
0x180024d9e  mov     rax, [rax+18h]
0x180024da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024da7  mov     eax, [rbp+var_20]
0x180024daa  cmp     [rbp+arg_8], eax
0x180024dad  jbe     short loc_180024DBB
0x180024daf  mov     rax, [r15]
0x180024db2  mov     [r12], rax
0x180024db6  mov     r12, r15
0x180024db9  jmp     short loc_180024D6B
0x180024dbb  mov     [r12], r13
0x180024dbf  add     rdi, 8
0x180024dc3  cmp     rdi, rsi
0x180024dc6  jnz     loc_180024D01
0x180024dcc  mov     rbx, [rsp+50h+arg_10]
0x180024dd4  add     rsp, 50h
0x180024dd8  pop     r15
0x180024dda  pop     r14
0x180024ddc  pop     r13
0x180024dde  pop     r12
0x180024de0  pop     rdi
0x180024de1  pop     rsi
0x180024de2  pop     rbp
0x180024de3  retn
```
