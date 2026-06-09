# com::http::HTTP_RESPONSE_by_IHttpResponse(Microsoft::Applications::Events::SimpleHttpResponse const *)

- ea: `0x1400e9e50`
- end: `0x1400ea12f`
- name: `?HTTP_RESPONSE_by_IHttpResponse@http@com@@YA?AV?$unique_ptr@U__MIDL___MIDL_itf_com_http_server_if_0000_0000_0003@@Uresponse_deleter_t@http@com@@@std@@PEBVSimpleHttpResponse@Events@Applications@Microsoft@@@Z`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ea340`

## callees

- `0x1400e9e50`
- `0x1400eb834`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400e9ec8`
- `ole32!CoTaskMemAlloc` at `0x1400e9f0a`
- `ole32!CoTaskMemAlloc` at `0x1400e9fbb`
- `ole32!CoTaskMemAlloc` at `0x1400e9ec8`
- `ole32!CoTaskMemAlloc` at `0x1400e9f0a`
- `ole32!CoTaskMemAlloc` at `0x1400e9fbb`
- `ole32!CoTaskMemFree` at `0x1400ea051`
- `ole32!CoTaskMemFree` at `0x1400ea090`
- `ole32!CoTaskMemFree` at `0x1400ea0a9`
- `ole32!CoTaskMemFree` at `0x1400ea0b7`
- `ole32!CoTaskMemFree` at `0x1400ea0cf`
- `ole32!CoTaskMemFree` at `0x1400ea0d8`
- `ole32!CoTaskMemFree` at `0x1400ea107`
- `ole32!CoTaskMemFree` at `0x1400ea051`
- `ole32!CoTaskMemFree` at `0x1400ea090`
- `ole32!CoTaskMemFree` at `0x1400ea0a9`
- `ole32!CoTaskMemFree` at `0x1400ea0b7`
- `ole32!CoTaskMemFree` at `0x1400ea0cf`
- `ole32!CoTaskMemFree` at `0x1400ea0d8`
- `ole32!CoTaskMemFree` at `0x1400ea107`

## pseudocode

```c
_QWORD *__fastcall com::http::HTTP_RESPONSE_by_IHttpResponse(_QWORD *a1, __int64 a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // r12
  __int64 v4; // r15
  _QWORD *v6; // r14
  size_t v7; // rsi
  void *v8; // rax
  void *v9; // rdi
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  const char *v12; // rdx
  char *v13; // rcx
  LPVOID *v14; // rbp
  unsigned __int64 v15; // rax
  _QWORD *v16; // rsi
  _QWORD *v17; // rdi
  char *v18; // r13
  com *v19; // rcx
  LPVOID *v20; // r14
  _DWORD *v21; // r12
  __int64 v22; // rax
  const char *v23; // rdx
  _QWORD *v24; // rbx
  com *v25; // rcx
  __int64 v26; // rax
  __int64 **v27; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v30; // rbp
  char *v31; // rdi
  __int64 k; // rsi
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rsi
  int v37; // [rsp+20h] [rbp-68h]
  char *v38; // [rsp+20h] [rbp-68h]
  int v39; // [rsp+28h] [rbp-60h]
  unsigned __int64 v40; // [rsp+28h] [rbp-60h]
  char *v41; // [rsp+30h] [rbp-58h]
  size_t Size; // [rsp+38h] [rbp-50h]

  v2 = (_QWORD *)(a2 + 8);
  v3 = 0x1000000;
  v4 = *(_QWORD *)(a2 + 56);
  if ( *(_QWORD *)(a2 + 104) - *(_QWORD *)(a2 + 96) < 0x1000000u )
    v3 = *(_QWORD *)(a2 + 104) - *(_QWORD *)(a2 + 96);
  v6 = a1;
  v39 = *(_DWORD *)(a2 + 44);
  v37 = *(_DWORD *)(a2 + 40);
  Size = v3;
  if ( *(_QWORD *)(a2 + 32) > 0xFu )
    v2 = (_QWORD *)*v2;
  if ( !v2 )
    goto LABEL_53;
  v7 = -1;
  do
    ++v7;
  while ( *((_BYTE *)v2 + v7) );
  v8 = CoTaskMemAlloc(v7 + 1);
  v9 = v8;
  if ( v8 )
    memset(v8, 0, v7 + 1);
  else
    v9 = 0;
  memmove(v9, v2, v7);
  if ( !v9 )
    goto LABEL_53;
  v10 = CoTaskMemAlloc(v3 + 1568);
  v11 = v10;
  if ( !v10 )
  {
    CoTaskMemFree(v9);
LABEL_53:
    *v6 = 0;
    return v6;
  }
  memset(v10, 0, v3 + 1568);
  v13 = (char *)(v11 + 6);
  v11[4] = v4;
  v14 = (LPVOID *)v11;
  *(_QWORD *)v11 = v9;
  v11[2] = v37;
  v11[3] = v39;
  v11[390] = v3;
  v11[2] = *(_DWORD *)(a2 + 40);
  v11[3] = *(_DWORD *)(a2 + 44);
  v15 = 0;
  v16 = *(_QWORD **)(a2 + 48);
  v41 = (char *)(v11 + 6);
  v17 = (_QWORD *)*v16;
  while ( 1 )
  {
    if ( v17 == v16 || v15 >= 0x40 )
    {
      memmove(v11 + 391, *(const void **)(a2 + 96), Size);
      goto LABEL_51;
    }
    v18 = v13;
    v40 = v15 + 1;
    v38 = v13 + 24;
    v19 = (com *)(v17 + 4);
    if ( v17[7] > 0xFu )
      v19 = (com *)v17[4];
    v20 = v14;
    v21 = v11;
    v22 = com::string_copy_and_release(v19, v12);
    *(_QWORD *)v18 = v22;
    if ( !v22 )
      break;
    v24 = CoTaskMemAlloc(8u);
    if ( !v24 )
      goto LABEL_34;
    v25 = (com *)(v17 + 8);
    *v24 = 0;
    if ( v17[11] > 0xFu )
      v25 = *(com **)v25;
    v26 = com::string_copy_and_release(v25, v23);
    *v24 = v26;
    if ( !v26 )
    {
      CoTaskMemFree(v24);
LABEL_34:
      v11 = 0;
      goto LABEL_36;
    }
    *((_QWORD *)v18 + 2) = v24;
    v11 = v21;
    *((_DWORD *)v18 + 2) = 1;
    v27 = (__int64 **)v17[2];
    if ( *((_BYTE *)v27 + 25) )
    {
      for ( i = v17[1]; !*(_BYTE *)(i + 25) && v17 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v17 = (_QWORD *)i;
      v17 = (_QWORD *)i;
    }
    else
    {
      v17 = (_QWORD *)v17[2];
      for ( j = *v27; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v17 = j;
    }
    v15 = v40;
    v13 = v38;
  }
  v20 = (LPVOID *)v11;
  v11 = 0;
  if ( !v20 )
    goto LABEL_51;
LABEL_36:
  if ( *((_DWORD *)v20 + 4) )
  {
    v30 = *((unsigned int *)v20 + 4);
    v31 = v41 + 8;
    do
    {
      for ( k = 0; (unsigned int)k < *(_DWORD *)v31; k = (unsigned int)(k + 1) )
      {
        v33 = *(void **)(*((_QWORD *)v31 + 1) + 8 * k);
        if ( v33 )
          CoTaskMemFree(v33);
      }
      v34 = (void *)*((_QWORD *)v31 - 1);
      v35 = (void *)*((_QWORD *)v31 + 1);
      if ( v34 )
        CoTaskMemFree(v34);
      if ( v35 )
        CoTaskMemFree(v35);
      v31 += 24;
      --v30;
    }
    while ( v30 );
  }
  if ( *v20 )
    CoTaskMemFree(*v20);
  CoTaskMemFree(v20);
LABEL_51:
  v6 = a1;
  *a1 = v11;
  return v6;
}

```

## disassembly

```asm
0x1400e9e50  mov     [rsp+arg_10], rbx
0x1400e9e55  push    rbp
0x1400e9e56  push    rsi
0x1400e9e57  push    rdi
0x1400e9e58  push    r12
0x1400e9e5a  push    r13
0x1400e9e5c  push    r14
0x1400e9e5e  push    r15
0x1400e9e60  sub     rsp, 50h
0x1400e9e64  mov     rax, [rdx+68h]
0x1400e9e68  lea     rbx, [rdx+8]
0x1400e9e6c  sub     rax, [rdx+60h]
0x1400e9e70  mov     r12d, 1000000h
0x1400e9e76  mov     r15, [rdx+38h]
0x1400e9e7a  cmp     rax, r12
0x1400e9e7d  mov     r13, rdx
0x1400e9e80  mov     [rsp+88h+var_48], rdx
0x1400e9e85  cmovb   r12, rax
0x1400e9e89  mov     [rsp+88h+var_40], rcx
0x1400e9e8e  cmp     qword ptr [rbx+18h], 0Fh
0x1400e9e93  mov     r14, rcx
0x1400e9e96  mov     eax, [rdx+2Ch]
0x1400e9e99  mov     dword ptr [rsp+88h+var_60], eax
0x1400e9e9d  mov     eax, [rdx+28h]
0x1400e9ea0  mov     dword ptr [rsp+88h+var_68], eax
0x1400e9ea4  mov     [rsp+88h+Size], r12
0x1400e9ea9  jbe     short loc_1400E9EAE
0x1400e9eab  mov     rbx, [rbx]
0x1400e9eae  test    rbx, rbx
0x1400e9eb1  jz      loc_1400EA10D
0x1400e9eb7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400e9ebb  inc     rsi
0x1400e9ebe  cmp     byte ptr [rbx+rsi], 0
0x1400e9ec2  jnz     short loc_1400E9EBB
0x1400e9ec4  lea     rcx, [rsi+1]; cb
0x1400e9ec8  call    cs:__imp_CoTaskMemAlloc
0x1400e9ece  mov     rdi, rax
0x1400e9ed1  test    rax, rax
0x1400e9ed4  jz      short loc_1400E9EE6
0x1400e9ed6  lea     r8, [rsi+1]; Size
0x1400e9eda  xor     edx, edx; Val
0x1400e9edc  mov     rcx, rax; void *
0x1400e9edf  call    memset
0x1400e9ee4  jmp     short loc_1400E9EE8
0x1400e9ee6  xor     edi, edi
0x1400e9ee8  mov     r8, rsi; Size
0x1400e9eeb  mov     rdx, rbx; Src
0x1400e9eee  mov     rcx, rdi; void *
0x1400e9ef1  call    memmove
0x1400e9ef6  test    rdi, rdi
0x1400e9ef9  jz      loc_1400EA10D
0x1400e9eff  lea     rsi, [r12+620h]
0x1400e9f07  mov     rcx, rsi; cb
0x1400e9f0a  call    cs:__imp_CoTaskMemAlloc
0x1400e9f10  mov     rbx, rax
0x1400e9f13  test    rax, rax
0x1400e9f16  jz      loc_1400EA104
0x1400e9f1c  mov     r8, rsi; Size
0x1400e9f1f  xor     edx, edx; Val
0x1400e9f21  mov     rcx, rax; void *
0x1400e9f24  call    memset
0x1400e9f29  mov     eax, dword ptr [rsp+88h+var_68]
0x1400e9f2d  lea     rcx, [rbx+18h]
0x1400e9f31  mov     [rbx+10h], r15d
0x1400e9f35  mov     rbp, rbx
0x1400e9f38  mov     [rbx], rdi
0x1400e9f3b  mov     [rbx+8], eax
0x1400e9f3e  mov     eax, dword ptr [rsp+88h+var_60]
0x1400e9f42  mov     [rbx+0Ch], eax
0x1400e9f45  mov     [rbx+618h], r12d
0x1400e9f4c  mov     eax, [r13+28h]
0x1400e9f50  mov     [rbx+8], eax
0x1400e9f53  mov     eax, [r13+2Ch]
0x1400e9f57  mov     [rbx+0Ch], eax
0x1400e9f5a  xor     eax, eax
0x1400e9f5c  mov     rsi, [r13+30h]
0x1400e9f60  mov     [rsp+88h+var_58], rcx
0x1400e9f65  mov     rdi, [rsi]
0x1400e9f68  cmp     rdi, rsi
0x1400e9f6b  jz      loc_1400EA0E0
0x1400e9f71  cmp     rax, 40h ; '@'
0x1400e9f75  jnb     loc_1400EA0E0
0x1400e9f7b  mov     r13, rcx
0x1400e9f7e  inc     rax
0x1400e9f81  add     rcx, 18h
0x1400e9f85  mov     [rsp+88h+var_60], rax
0x1400e9f8a  cmp     qword ptr [rdi+38h], 0Fh
0x1400e9f8f  mov     [rsp+88h+var_68], rcx
0x1400e9f94  lea     rcx, [rdi+20h]
0x1400e9f98  jbe     short loc_1400E9F9E
0x1400e9f9a  mov     rcx, [rdi+20h]; this
0x1400e9f9e  mov     r14, rbp
0x1400e9fa1  mov     r12, rbx
0x1400e9fa4  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400e9fa9  mov     [r13+0], rax
0x1400e9fad  test    rax, rax
0x1400e9fb0  jz      loc_1400EA05B
0x1400e9fb6  mov     ecx, 8; cb
0x1400e9fbb  call    cs:__imp_CoTaskMemAlloc
0x1400e9fc1  mov     rbx, rax
0x1400e9fc4  test    rax, rax
0x1400e9fc7  jz      loc_1400EA057
0x1400e9fcd  xor     eax, eax
0x1400e9fcf  lea     rcx, [rdi+40h]
0x1400e9fd3  mov     [rbx], rax
0x1400e9fd6  cmp     qword ptr [rdi+58h], 0Fh
0x1400e9fdb  jbe     short loc_1400E9FE0
0x1400e9fdd  mov     rcx, [rcx]; this
0x1400e9fe0  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400e9fe5  mov     [rbx], rax
0x1400e9fe8  test    rax, rax
0x1400e9feb  jz      short loc_1400EA04E
0x1400e9fed  mov     [r13+10h], rbx
0x1400e9ff1  mov     rbx, r12
0x1400e9ff4  mov     dword ptr [r13+8], 1
0x1400e9ffc  mov     rcx, [rdi+10h]
0x1400ea000  cmp     byte ptr [rcx+19h], 0
0x1400ea004  jz      short loc_1400EA031
0x1400ea006  mov     rax, [rdi+8]
0x1400ea00a  jmp     short loc_1400EA019
0x1400ea00c  cmp     rdi, [rax+10h]
0x1400ea010  jnz     short loc_1400EA01F
0x1400ea012  mov     rdi, rax
0x1400ea015  mov     rax, [rax+8]
0x1400ea019  cmp     byte ptr [rax+19h], 0
0x1400ea01d  jz      short loc_1400EA00C
0x1400ea01f  mov     rdi, rax
0x1400ea022  mov     rax, [rsp+88h+var_60]
0x1400ea027  mov     rcx, [rsp+88h+var_68]
0x1400ea02c  jmp     loc_1400E9F68
0x1400ea031  mov     rdi, rcx
0x1400ea034  mov     rcx, [rcx]
0x1400ea037  cmp     byte ptr [rcx+19h], 0
0x1400ea03b  jnz     short loc_1400EA022
0x1400ea03d  mov     rax, [rcx]
0x1400ea040  mov     rdi, rcx
0x1400ea043  mov     rcx, rax
0x1400ea046  cmp     byte ptr [rax+19h], 0
0x1400ea04a  jz      short loc_1400EA03D
0x1400ea04c  jmp     short loc_1400EA022
0x1400ea04e  mov     rcx, rbx; pv
0x1400ea051  call    cs:__imp_CoTaskMemFree
0x1400ea057  xor     ebx, ebx
0x1400ea059  jmp     short loc_1400EA069
0x1400ea05b  mov     r14, rbx
0x1400ea05e  xor     ebx, ebx
0x1400ea060  test    r14, r14
0x1400ea063  jz      loc_1400EA0FA
0x1400ea069  cmp     dword ptr [r14+10h], 0
0x1400ea06e  jbe     short loc_1400EA0C7
0x1400ea070  mov     rdi, [rsp+88h+var_58]
0x1400ea075  mov     ebp, [r14+10h]
0x1400ea079  add     rdi, 8
0x1400ea07d  xor     esi, esi
0x1400ea07f  cmp     [rdi], esi
0x1400ea081  jbe     short loc_1400EA09C
0x1400ea083  mov     rax, [rdi+8]
0x1400ea087  mov     rcx, [rax+rsi*8]; pv
0x1400ea08b  test    rcx, rcx
0x1400ea08e  jz      short loc_1400EA096
0x1400ea090  call    cs:__imp_CoTaskMemFree
0x1400ea096  inc     esi
0x1400ea098  cmp     esi, [rdi]
0x1400ea09a  jb      short loc_1400EA083
0x1400ea09c  mov     rcx, [rdi-8]; pv
0x1400ea0a0  mov     rsi, [rdi+8]
0x1400ea0a4  test    rcx, rcx
0x1400ea0a7  jz      short loc_1400EA0AF
0x1400ea0a9  call    cs:__imp_CoTaskMemFree
0x1400ea0af  test    rsi, rsi
0x1400ea0b2  jz      short loc_1400EA0BD
0x1400ea0b4  mov     rcx, rsi; pv
0x1400ea0b7  call    cs:__imp_CoTaskMemFree
0x1400ea0bd  add     rdi, 18h
0x1400ea0c1  sub     rbp, 1
0x1400ea0c5  jnz     short loc_1400EA07D
0x1400ea0c7  mov     rcx, [r14]; pv
0x1400ea0ca  test    rcx, rcx
0x1400ea0cd  jz      short loc_1400EA0D5
0x1400ea0cf  call    cs:__imp_CoTaskMemFree
0x1400ea0d5  mov     rcx, r14; pv
0x1400ea0d8  call    cs:__imp_CoTaskMemFree
0x1400ea0de  jmp     short loc_1400EA0FA
0x1400ea0e0  mov     rdx, [rsp+88h+var_48]
0x1400ea0e5  lea     rcx, [rbx+61Ch]; void *
0x1400ea0ec  mov     r8, [rsp+88h+Size]; Size
0x1400ea0f1  mov     rdx, [rdx+60h]; Src
0x1400ea0f5  call    memmove
0x1400ea0fa  mov     r14, [rsp+88h+var_40]
0x1400ea0ff  mov     [r14], rbx
0x1400ea102  jmp     short loc_1400EA114
0x1400ea104  mov     rcx, rdi; pv
0x1400ea107  call    cs:__imp_CoTaskMemFree
0x1400ea10d  mov     qword ptr [r14], 0
0x1400ea114  mov     rbx, [rsp+88h+arg_10]
0x1400ea11c  mov     rax, r14
0x1400ea11f  add     rsp, 50h
0x1400ea123  pop     r15
0x1400ea125  pop     r14
0x1400ea127  pop     r13
0x1400ea129  pop     r12
0x1400ea12b  pop     rdi
0x1400ea12c  pop     rsi
0x1400ea12d  pop     rbp
0x1400ea12e  retn
```
