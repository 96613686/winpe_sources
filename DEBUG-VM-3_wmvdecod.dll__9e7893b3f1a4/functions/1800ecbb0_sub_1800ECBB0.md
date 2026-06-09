# sub_1800ECBB0

- ea: `0x1800ecbb0`
- end: `0x1800ecc61`
- name: `sub_1800ECBB0`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ede20`

## callees

- `0x180057fe4`
- `0x1800cd9c8`
- `0x1800ecbb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ecc0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ecc0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecbd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecbd5`

## pseudocode

```c
__int64 __fastcall sub_1800ECBB0(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  void *v3; // rsi
  int v7; // edi
  unsigned int v9; // ebp
  __int64 (__fastcall *v10)(__int64, void *, _QWORD); // rbx

  v3 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v9 = dword_180281168 + 40 + dword_18028115C;
    v3 = CoTaskMemAlloc(v9);
    if ( v3 )
    {
      v10 = (__int64 (__fastcall *)(__int64, void *, _QWORD))sub_1800CD9C8(&word_180263F76);
      v7 = v10(a1, v3, v9);
      sub_180057FE4(v10);
      if ( v7 >= 0 )
      {
        *a2 = v3;
        *a3 = v9;
        return (unsigned int)v7;
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147467261;
  }
  CoTaskMemFree(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ecbb0  push    rbx
0x1800ecbb2  push    rbp
0x1800ecbb3  push    rsi
0x1800ecbb4  push    rdi
0x1800ecbb5  push    r14
0x1800ecbb7  push    r15
0x1800ecbb9  sub     rsp, 28h
0x1800ecbbd  xor     esi, esi
0x1800ecbbf  mov     r14, r8
0x1800ecbc2  mov     r15, rdx
0x1800ecbc5  mov     rdi, rcx
0x1800ecbc8  test    rdx, rdx
0x1800ecbcb  jnz     short loc_1800ECBF1
0x1800ecbcd  mov     edi, 80004003h
0x1800ecbd2  mov     rcx, rsi; pv
0x1800ecbd5  call    cs:CoTaskMemFree
0x1800ecbdc  nop     dword ptr [rax+rax+00h]
0x1800ecbe1  mov     eax, edi
0x1800ecbe3  add     rsp, 28h
0x1800ecbe7  pop     r15
0x1800ecbe9  pop     r14
0x1800ecbeb  pop     rdi
0x1800ecbec  pop     rsi
0x1800ecbed  pop     rbp
0x1800ecbee  pop     rbx
0x1800ecbef  retn
0x1800ecbf1  test    r14, r14
0x1800ecbf4  jz      short loc_1800ECBCD
0x1800ecbf6  mov     [rdx], rsi
0x1800ecbf9  mov     [r8], esi
0x1800ecbfc  mov     eax, cs:dword_180281168
0x1800ecc02  mov     ebp, cs:dword_18028115C
0x1800ecc08  add     eax, 28h ; '('
0x1800ecc0b  add     ebp, eax
0x1800ecc0d  mov     ecx, ebp; cb
0x1800ecc0f  call    cs:CoTaskMemAlloc
0x1800ecc16  nop     dword ptr [rax+rax+00h]
0x1800ecc1b  mov     rsi, rax
0x1800ecc1e  test    rax, rax
0x1800ecc21  jnz     short loc_1800ECC2A
0x1800ecc23  mov     edi, 8007000Eh
0x1800ecc28  jmp     short loc_1800ECBD2
0x1800ecc2a  lea     rcx, word_180263F76
0x1800ecc31  call    sub_1800CD9C8
0x1800ecc36  mov     r8d, ebp
0x1800ecc39  mov     rdx, rsi
0x1800ecc3c  mov     rcx, rdi
0x1800ecc3f  mov     rbx, rax
0x1800ecc42  call    rax
0x1800ecc44  nop     dword ptr [rax]
0x1800ecc47  mov     rcx, rbx
0x1800ecc4a  mov     edi, eax
0x1800ecc4c  call    sub_180057FE4
0x1800ecc51  test    edi, edi
0x1800ecc53  js      loc_1800ECBD2
0x1800ecc59  mov     [r15], rsi
0x1800ecc5c  mov     [r14], ebp
0x1800ecc5f  jmp     short loc_1800ECBE1
```
