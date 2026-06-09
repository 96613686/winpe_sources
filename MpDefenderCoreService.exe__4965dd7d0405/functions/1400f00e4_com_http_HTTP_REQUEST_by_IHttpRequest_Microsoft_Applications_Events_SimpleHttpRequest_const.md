# com::http::HTTP_REQUEST_by_IHttpRequest(Microsoft::Applications::Events::SimpleHttpRequest const *)

- ea: `0x1400f00e4`
- end: `0x1400f02a1`
- name: `?HTTP_REQUEST_by_IHttpRequest@http@com@@YA?AV?$unique_ptr@U__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002@@Urequest_deleter_t@http@com@@@std@@PEBVSimpleHttpRequest@Events@Applications@Microsoft@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ef920`

## callees

- `0x1400e9b7c`
- `0x1400eb834`
- `0x1400f00e4`
- `0x1400f2108`
- `0x1401662d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400f01ba`
- `ole32!CoTaskMemAlloc` at `0x1400f01ba`
- `ole32!CoTaskMemFree` at `0x1400f024c`
- `ole32!CoTaskMemFree` at `0x1400f024c`

## pseudocode

```c
__int64 *__fastcall com::http::HTTP_REQUEST_by_IHttpRequest(__int64 *a1, __int64 a2)
{
  _BYTE *v2; // r9
  SIZE_T v3; // rax
  bool v5; // cc
  __int64 v7; // rcx
  _BYTE *v8; // r8
  __int64 **v9; // rdx
  const char *v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // r13
  _QWORD *v13; // rsi
  _QWORD *v14; // rbx
  com *v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  bool v20; // r9
  const char *v21; // rdx
  _QWORD *v22; // r14
  com *v23; // rcx
  __int64 v24; // rax
  __int64 **v25; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v28; // rdx
  __int64 v30[9]; // [rsp+30h] [rbp-48h] BYREF

  v2 = (_BYTE *)(a2 + 72);
  v3 = *(_QWORD *)(a2 + 160) - *(_QWORD *)(a2 + 152);
  v5 = *(_QWORD *)(a2 + 96) <= 0xFu;
  v7 = *(_QWORD *)(a2 + 112);
  v30[0] = 0;
  if ( !v5 )
    v2 = *(_BYTE **)v2;
  v8 = (_BYTE *)(a2 + 40);
  if ( *(_QWORD *)(a2 + 64) > 0xFu )
    v8 = *(_BYTE **)v8;
  v9 = (__int64 **)(a2 + 8);
  if ( (unsigned __int64)v9[3] > 0xF )
    v9 = (__int64 **)*v9;
  com::http::request_alloc(v30, v9, v8, v2, v7, v3);
  v11 = v30[0];
  if ( v30[0] )
  {
    v12 = 0;
    *(_DWORD *)(v30[0] + 24) = *(_DWORD *)(a2 + 180);
    *(_DWORD *)(v11 + 28) = *(_DWORD *)(a2 + 176);
    v13 = *(_QWORD **)(a2 + 104);
    v14 = (_QWORD *)*v13;
    while ( v14 != v13 )
    {
      v15 = (com *)(v14 + 4);
      v16 = v12 + *(_QWORD *)(v11 + 40);
      v12 += 24;
      if ( v14[7] > 0xFu )
        v15 = *(com **)v15;
      v17 = com::string_copy_and_release(v15, v10);
      *(_QWORD *)v16 = v17;
      if ( !v17 )
        goto LABEL_27;
      v22 = CoTaskMemAlloc(8u);
      if ( !v22 )
        goto LABEL_27;
      v23 = (com *)(v14 + 8);
      *v22 = 0;
      if ( v14[11] > 0xFu )
        v23 = *(com **)v23;
      v24 = com::string_copy_and_release(v23, v21);
      *v22 = v24;
      if ( !v24 )
      {
        CoTaskMemFree(v22);
LABEL_27:
        v28 = v11;
        v11 = 0;
        if ( !v28 )
          goto LABEL_31;
        com::http::request_deleter_t::operator()(v18, v28, v19, v20);
        break;
      }
      *(_DWORD *)(v16 + 8) = 1;
      *(_QWORD *)(v16 + 16) = v22;
      v25 = (__int64 **)v14[2];
      if ( *((_BYTE *)v25 + 25) )
      {
        for ( i = v14[1]; !*(_BYTE *)(i + 25) && v14 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v14 = (_QWORD *)i;
        v14 = (_QWORD *)i;
      }
      else
      {
        v14 = (_QWORD *)v14[2];
        for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v14 = j;
      }
    }
    if ( v11 )
      memmove(*(void **)(v11 + 56), *(const void **)(a2 + 152), *(unsigned int *)(v11 + 48));
LABEL_31:
    *a1 = v11;
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1400f00e4  mov     [rsp+arg_10], rbx
0x1400f00e9  push    rbp
0x1400f00ea  push    rsi
0x1400f00eb  push    rdi
0x1400f00ec  push    r12
0x1400f00ee  push    r13
0x1400f00f0  push    r14
0x1400f00f2  push    r15
0x1400f00f4  sub     rsp, 40h
0x1400f00f8  mov     rax, [rdx+0A0h]
0x1400f00ff  lea     r9, [rdx+48h]
0x1400f0103  sub     rax, [rdx+98h]
0x1400f010a  mov     r15, rcx
0x1400f010d  cmp     qword ptr [r9+18h], 0Fh
0x1400f0112  mov     rbp, rdx
0x1400f0115  mov     rcx, [rdx+70h]
0x1400f0119  mov     [rsp+78h+var_48], 0
0x1400f0122  jbe     short loc_1400F0127
0x1400f0124  mov     r9, [r9]
0x1400f0127  lea     r8, [rdx+28h]
0x1400f012b  cmp     qword ptr [r8+18h], 0Fh
0x1400f0130  jbe     short loc_1400F0135
0x1400f0132  mov     r8, [r8]
0x1400f0135  add     rdx, 8
0x1400f0139  cmp     qword ptr [rdx+18h], 0Fh
0x1400f013e  jbe     short loc_1400F0143
0x1400f0140  mov     rdx, [rdx]
0x1400f0143  mov     [rsp+78h+var_50], rax
0x1400f0148  mov     [rsp+78h+var_58], rcx
0x1400f014d  lea     rcx, [rsp+78h+var_48]
0x1400f0152  call    ?request_alloc@http@com@@YA?AV?$unique_ptr@U__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002@@Urequest_deleter_t@http@com@@@std@@PEBD00_K1@Z; com::http::request_alloc(char const *,char const *,char const *,unsigned __int64,unsigned __int64)
0x1400f0157  mov     rdi, [rsp+78h+var_48]
0x1400f015c  test    rdi, rdi
0x1400f015f  jz      loc_1400F027F
0x1400f0165  mov     eax, [rbp+0B4h]
0x1400f016b  xor     r13d, r13d
0x1400f016e  mov     [rdi+18h], eax
0x1400f0171  mov     eax, [rbp+0B0h]
0x1400f0177  mov     [rdi+1Ch], eax
0x1400f017a  mov     rsi, [rbp+68h]
0x1400f017e  mov     rbx, [rsi]
0x1400f0181  cmp     rbx, rsi
0x1400f0184  jz      loc_1400F0261
0x1400f018a  mov     r12, [rdi+28h]
0x1400f018e  lea     rcx, [rbx+20h]
0x1400f0192  add     r12, r13
0x1400f0195  add     r13, 18h
0x1400f0199  cmp     qword ptr [rbx+38h], 0Fh
0x1400f019e  jbe     short loc_1400F01A3
0x1400f01a0  mov     rcx, [rcx]; this
0x1400f01a3  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400f01a8  mov     [r12], rax
0x1400f01ac  test    rax, rax
0x1400f01af  jz      loc_1400F0252
0x1400f01b5  mov     ecx, 8; cb
0x1400f01ba  call    cs:__imp_CoTaskMemAlloc
0x1400f01c0  mov     r14, rax
0x1400f01c3  test    rax, rax
0x1400f01c6  jz      loc_1400F0252
0x1400f01cc  xor     eax, eax
0x1400f01ce  lea     rcx, [rbx+40h]
0x1400f01d2  mov     [r14], rax
0x1400f01d5  cmp     qword ptr [rbx+58h], 0Fh
0x1400f01da  jbe     short loc_1400F01DF
0x1400f01dc  mov     rcx, [rcx]; this
0x1400f01df  call    ?string_copy_and_release@com@@YA@PEBD@Z; com::string_copy_and_release(char const *)
0x1400f01e4  mov     [r14], rax
0x1400f01e7  test    rax, rax
0x1400f01ea  jz      short loc_1400F0249
0x1400f01ec  mov     dword ptr [r12+8], 1
0x1400f01f5  mov     [r12+10h], r14
0x1400f01fa  mov     rcx, [rbx+10h]
0x1400f01fe  cmp     byte ptr [rcx+19h], 0
0x1400f0202  jz      short loc_1400F0225
0x1400f0204  mov     rax, [rbx+8]
0x1400f0208  jmp     short loc_1400F0217
0x1400f020a  cmp     rbx, [rax+10h]
0x1400f020e  jnz     short loc_1400F021D
0x1400f0210  mov     rbx, rax
0x1400f0213  mov     rax, [rax+8]
0x1400f0217  cmp     byte ptr [rax+19h], 0
0x1400f021b  jz      short loc_1400F020A
0x1400f021d  mov     rbx, rax
0x1400f0220  jmp     loc_1400F0181
0x1400f0225  mov     rbx, rcx
0x1400f0228  mov     rcx, [rcx]
0x1400f022b  cmp     byte ptr [rcx+19h], 0
0x1400f022f  jnz     loc_1400F0181
0x1400f0235  mov     rax, [rcx]
0x1400f0238  mov     rbx, rcx
0x1400f023b  mov     rcx, rax
0x1400f023e  cmp     byte ptr [rax+19h], 0
0x1400f0242  jz      short loc_1400F0235
0x1400f0244  jmp     loc_1400F0181
0x1400f0249  mov     rcx, r14; pv
0x1400f024c  call    cs:__imp_CoTaskMemFree
0x1400f0252  mov     rdx, rdi
0x1400f0255  xor     edi, edi
0x1400f0257  test    rdx, rdx
0x1400f025a  jz      short loc_1400F027A
0x1400f025c  call    ??Rrequest_deleter_t@http@com@@QEAAXPEAU__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002@@@Z; com::http::request_deleter_t::operator()(__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002 *)
0x1400f0261  test    rdi, rdi
0x1400f0264  jz      short loc_1400F027A
0x1400f0266  mov     r8d, [rdi+30h]; Size
0x1400f026a  mov     rdx, [rbp+98h]; Src
0x1400f0271  mov     rcx, [rdi+38h]; void *
0x1400f0275  call    memmove
0x1400f027a  mov     [r15], rdi
0x1400f027d  jmp     short loc_1400F0286
0x1400f027f  mov     qword ptr [r15], 0
0x1400f0286  mov     rbx, [rsp+78h+arg_10]
0x1400f028e  mov     rax, r15
0x1400f0291  add     rsp, 40h
0x1400f0295  pop     r15
0x1400f0297  pop     r14
0x1400f0299  pop     r13
0x1400f029b  pop     r12
0x1400f029d  pop     rdi
0x1400f029e  pop     rsi
0x1400f029f  pop     rbp
0x1400f02a0  retn
```
