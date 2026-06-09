# std::_Med3<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)

- ea: `0x180024a5c`
- end: `0x180024b70`
- name: `??$_Med3@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@00UCompareElement@@@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024dec`

## callees

- `0x180024a5c`
- `0x18002f010`

## pseudocode

```c
unsigned __int64 __fastcall std::_Med3<IMtfSuggestionListElement * *,CompareElement>(
        unsigned __int64 *a1,
        unsigned __int64 *a2,
        __int64 **a3,
        char a4)
{
  __int64 *v4; // rbx
  _QWORD *v6; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 *v11; // rcx
  __int64 *v12; // rbx
  __int64 v13; // rax
  unsigned __int64 result; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 *v17; // rbx
  __int64 v18; // rax
  _QWORD *v19; // rcx
  unsigned int v20; // [rsp+40h] [rbp+20h] BYREF
  unsigned int v21; // [rsp+58h] [rbp+38h] BYREF

  LOBYTE(v21) = a4;
  v4 = (__int64 *)*a1;
  v6 = (_QWORD *)*a2;
  v20 = 0;
  (*(void (__fastcall **)(_QWORD *, unsigned int *))(*v6 + 24LL))(v6, &v20);
  v9 = *v4;
  v21 = 0;
  (*(void (__fastcall **)(__int64 *, unsigned int *))(v9 + 24))(v4, &v21);
  if ( v20 > v21 )
  {
    v10 = (_QWORD *)*a2;
    *a2 = *a1;
    *a1 = (unsigned __int64)v10;
  }
  v11 = *a3;
  v12 = (__int64 *)*a2;
  v20 = 0;
  (*(void (__fastcall **)(__int64 *, unsigned int *))(*v11 + 24))(v11, &v20);
  v13 = *v12;
  v21 = 0;
  (*(void (__fastcall **)(__int64 *, unsigned int *))(v13 + 24))(v12, &v21);
  result = v21;
  if ( v20 > v21 )
  {
    v15 = *a3;
    *a3 = (__int64 *)*a2;
    *a2 = (unsigned __int64)v15;
    v16 = *v15;
    v17 = (__int64 *)*a1;
    v20 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v16 + 24))(v15, &v20);
    v18 = *v17;
    v21 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v18 + 24))(v17, &v21);
    result = v21;
    if ( v20 > v21 )
    {
      result = *a1;
      v19 = (_QWORD *)*a2;
      *a2 = *a1;
      *a1 = (unsigned __int64)v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024a5c  mov     [rsp-18h+arg_8], rbx
0x180024a61  mov     [rsp-18h+arg_10], rsi
0x180024a66  mov     byte ptr [rsp-18h+arg_18], r9b
0x180024a6b  push    rbp
0x180024a6c  push    rdi
0x180024a6d  push    r14
0x180024a6f  mov     rbp, rsp
0x180024a72  sub     rsp, 20h
0x180024a76  mov     rbx, [rcx]
0x180024a79  mov     rsi, rcx
0x180024a7c  mov     rcx, [rdx]
0x180024a7f  mov     rdi, rdx
0x180024a82  lea     rdx, [rbp+arg_0]
0x180024a86  mov     [rbp+arg_0], 0
0x180024a8d  mov     r14, r8
0x180024a90  mov     rax, [rcx]
0x180024a93  mov     rax, [rax+18h]
0x180024a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a9c  mov     rax, [rbx]
0x180024a9f  lea     rdx, [rbp+arg_18]
0x180024aa3  mov     rcx, rbx
0x180024aa6  mov     [rbp+arg_18], 0
0x180024aad  mov     rax, [rax+18h]
0x180024ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab6  mov     eax, [rbp+arg_18]
0x180024ab9  cmp     [rbp+arg_0], eax
0x180024abc  jbe     short loc_180024ACA
0x180024abe  mov     rax, [rsi]
0x180024ac1  mov     rcx, [rdi]
0x180024ac4  mov     [rdi], rax
0x180024ac7  mov     [rsi], rcx
0x180024aca  mov     rcx, [r14]
0x180024acd  lea     rdx, [rbp+arg_0]
0x180024ad1  mov     rbx, [rdi]
0x180024ad4  mov     [rbp+arg_0], 0
0x180024adb  mov     rax, [rcx]
0x180024ade  mov     rax, [rax+18h]
0x180024ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ae7  mov     rax, [rbx]
0x180024aea  lea     rdx, [rbp+arg_18]
0x180024aee  mov     rcx, rbx
0x180024af1  mov     [rbp+arg_18], 0
0x180024af8  mov     rax, [rax+18h]
0x180024afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b01  mov     eax, [rbp+arg_18]
0x180024b04  cmp     [rbp+arg_0], eax
0x180024b07  jbe     short loc_180024B5D
0x180024b09  mov     rcx, [r14]
0x180024b0c  lea     rdx, [rbp+arg_0]
0x180024b10  mov     rax, [rdi]
0x180024b13  mov     [r14], rax
0x180024b16  mov     [rdi], rcx
0x180024b19  mov     rax, [rcx]
0x180024b1c  mov     rbx, [rsi]
0x180024b1f  mov     [rbp+arg_0], 0
0x180024b26  mov     rax, [rax+18h]
0x180024b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b2f  mov     rax, [rbx]
0x180024b32  lea     rdx, [rbp+arg_18]
0x180024b36  mov     rcx, rbx
0x180024b39  mov     [rbp+arg_18], 0
0x180024b40  mov     rax, [rax+18h]
0x180024b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b49  mov     eax, [rbp+arg_18]
0x180024b4c  cmp     [rbp+arg_0], eax
0x180024b4f  jbe     short loc_180024B5D
0x180024b51  mov     rax, [rsi]
0x180024b54  mov     rcx, [rdi]
0x180024b57  mov     [rdi], rax
0x180024b5a  mov     [rsi], rcx
0x180024b5d  mov     rbx, [rsp+20h+arg_8]
0x180024b62  mov     rsi, [rsp+20h+arg_10]
0x180024b67  add     rsp, 20h
0x180024b6b  pop     r14
0x180024b6d  pop     rdi
0x180024b6e  pop     rbp
0x180024b6f  retn
```
