# ComApplicationFromCDPApplication

- ea: `0x180007050`
- end: `0x18000721e`
- name: `ComApplicationFromCDPApplication`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000db68`
- `0x18000e9e8`

## callees

- `0x180007050`
- `0x1800130ec`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000712b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007191`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800071f0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000712b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007191`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800071f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071d7`

## string_xrefs

- `0x18000707a`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800070a5`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComApplicationFromCDPApplication(__int64 a1, char **a2)
{
  char *v5; // r13
  __int64 v6; // rax
  const char *v7; // rsi
  char *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rcx
  rsize_t v11; // r12
  char *v12; // rax
  char *v13; // rbp
  __int64 v14; // rax
  const char *v15; // rsi
  __int64 v16; // rcx
  rsize_t v17; // r12
  char *v18; // rax
  char *v19; // rbp
  const char *v20; // rsi
  char *v21; // rax
  rsize_t v22; // rbp
  char *v23; // rdi
  int v24; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
  {
    if ( a1 )
    {
      v5 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v7 = (const char *)v6;
      v8 = 0;
      v9 = -1;
      if ( v6 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_BYTE *)(v6 + v10) );
        v11 = v10 + 1;
        v12 = (char *)CoTaskMemAlloc(v10 + 1);
        v13 = v12;
        if ( v12 )
        {
          strcpy_s(v12, v11, v7);
          v8 = v13;
        }
      }
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v15 = (const char *)v14;
      if ( v14 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_BYTE *)(v14 + v16) );
        v17 = v16 + 1;
        v18 = (char *)CoTaskMemAlloc(v16 + 1);
        v19 = v18;
        v5 = 0;
        if ( v18 )
        {
          strcpy_s(v18, v17, v15);
          v5 = v19;
        }
      }
      v20 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v21 = 0;
      if ( v20 )
      {
        do
          ++v9;
        while ( v20[v9] );
        v22 = v9 + 1;
        v23 = (char *)CoTaskMemAlloc(v9 + 1);
        v21 = 0;
        if ( v23 )
        {
          strcpy_s(v23, v22, v20);
          v21 = v23;
        }
      }
      *a2 = v8;
      a2[1] = v5;
      a2[2] = v21;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)0x80070057LL,
        v24);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      v24);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180007050  mov     [rsp+arg_0], rbx
0x180007055  push    rbp
0x180007056  push    rsi
0x180007057  push    rdi
0x180007058  push    r12
0x18000705a  push    r13
0x18000705c  push    r14
0x18000705e  push    r15
0x180007060  sub     rsp, 40h
0x180007064  mov     r15, rdx
0x180007067  mov     r14, rcx
0x18000706a  test    rdx, rdx
0x18000706d  jnz     short loc_180007095
0x18000706f  mov     rcx, [rsp+78h]; this
0x180007074  mov     r9d, 80004003h; char *
0x18000707a  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007081  mov     edx, 137h; void *
0x180007086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000708b  mov     eax, 80004003h
0x180007090  jmp     loc_180007206
0x180007095  test    r14, r14
0x180007098  jnz     short loc_1800070C0
0x18000709a  mov     rcx, [rsp+78h]; this
0x18000709f  mov     r9d, 80070057h; char *
0x1800070a5  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800070ac  mov     edx, 138h; void *
0x1800070b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070b6  mov     eax, 80070057h
0x1800070bb  jmp     loc_180007206
0x1800070c0  xor     r13d, r13d
0x1800070c3  mov     [rsp+78h+arg_8], r13
0x1800070cb  mov     [rsp+78h+arg_18], r13
0x1800070d3  mov     [rsp+78h+arg_10], r13
0x1800070db  mov     rax, [rcx]
0x1800070de  mov     rax, [rax+18h]
0x1800070e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e7  mov     rsi, rax
0x1800070ea  mov     ebx, r13d
0x1800070ed  mov     [rsp+78h+arg_10], rbx
0x1800070f5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800070fc  test    rax, rax
0x1800070ff  jz      short loc_18000713C
0x180007101  mov     rcx, rdi
0x180007104  lea     rcx, [rcx+1]
0x180007108  cmp     [rax+rcx], bl
0x18000710b  jnz     short loc_180007104
0x18000710d  lea     r12, [rcx+1]
0x180007111  mov     rcx, r12; cb
0x180007114  call    cs:__imp_CoTaskMemAlloc
0x18000711a  mov     rbp, rax
0x18000711d  test    rax, rax
0x180007120  jz      short loc_18000713C
0x180007122  mov     r8, rsi; Source
0x180007125  mov     rdx, r12; SizeInBytes
0x180007128  mov     rcx, rax; Destination
0x18000712b  call    cs:__imp_strcpy_s
0x180007131  mov     rbx, rbp
0x180007134  mov     [rsp+78h+arg_10], rbx
0x18000713c  mov     [rsp+78h+arg_8], r13
0x180007144  mov     rax, [r14]
0x180007147  mov     rcx, r14
0x18000714a  mov     rax, [rax+20h]
0x18000714e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007153  mov     rsi, rax
0x180007156  mov     [rsp+78h+arg_8], r13
0x18000715e  test    rax, rax
0x180007161  jz      short loc_1800071A2
0x180007163  mov     rcx, rdi
0x180007166  lea     rcx, [rcx+1]
0x18000716a  cmp     byte ptr [rax+rcx], 0
0x18000716e  jnz     short loc_180007166
0x180007170  lea     r12, [rcx+1]
0x180007174  mov     rcx, r12; cb
0x180007177  call    cs:__imp_CoTaskMemAlloc
0x18000717d  mov     rbp, rax
0x180007180  xor     r13d, r13d
0x180007183  test    rax, rax
0x180007186  jz      short loc_1800071A2
0x180007188  mov     r8, rsi; Source
0x18000718b  mov     rdx, r12; SizeInBytes
0x18000718e  mov     rcx, rax; Destination
0x180007191  call    cs:__imp_strcpy_s
0x180007197  mov     [rsp+78h+arg_8], rbp
0x18000719f  mov     r13, rbp
0x1800071a2  mov     [rsp+78h+arg_18], 0
0x1800071ae  mov     rax, [r14]
0x1800071b1  mov     rcx, r14
0x1800071b4  mov     rax, [rax+28h]
0x1800071b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071bd  mov     rsi, rax
0x1800071c0  xor     eax, eax
0x1800071c2  test    rsi, rsi
0x1800071c5  jz      short loc_1800071F9
0x1800071c7  lea     rdi, [rdi+1]
0x1800071cb  cmp     [rsi+rdi], al
0x1800071ce  jnz     short loc_1800071C7
0x1800071d0  lea     rbp, [rdi+1]
0x1800071d4  mov     rcx, rbp; cb
0x1800071d7  call    cs:__imp_CoTaskMemAlloc
0x1800071dd  mov     rdi, rax
0x1800071e0  xor     eax, eax
0x1800071e2  test    rdi, rdi
0x1800071e5  jz      short loc_1800071F9
0x1800071e7  mov     r8, rsi; Source
0x1800071ea  mov     rdx, rbp; SizeInBytes
0x1800071ed  mov     rcx, rdi; Destination
0x1800071f0  call    cs:__imp_strcpy_s
0x1800071f6  mov     rax, rdi
0x1800071f9  mov     [r15], rbx
0x1800071fc  mov     [r15+8], r13
0x180007200  mov     [r15+10h], rax
0x180007204  xor     eax, eax
0x180007206  mov     rbx, [rsp+78h+arg_0]
0x18000720e  add     rsp, 40h
0x180007212  pop     r15
0x180007214  pop     r14
0x180007216  pop     r13
0x180007218  pop     r12
0x18000721a  pop     rdi
0x18000721b  pop     rsi
0x18000721c  pop     rbp
0x18000721d  retn
```
