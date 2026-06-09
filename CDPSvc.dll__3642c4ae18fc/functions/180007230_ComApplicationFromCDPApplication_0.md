# ComApplicationFromCDPApplication_0

- ea: `0x180007230`
- end: `0x1800073fe`
- name: `ComApplicationFromCDPApplication_0`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f848`

## callees

- `0x180007230`
- `0x1800130ec`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000730b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007371`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800073d0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000730b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007371`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800073d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800073b7`

## string_xrefs

- `0x18000725a`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180007285`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
__int64 __fastcall ComApplicationFromCDPApplication_0(__int64 a1, char **a2)
{
  char *v5; // r13
  __int64 v6; // rax
  const char *v7; // rbp
  char *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rcx
  rsize_t v11; // r12
  char *v12; // rax
  char *v13; // r15
  __int64 v14; // rax
  const char *v15; // rbp
  __int64 v16; // rcx
  rsize_t v17; // r12
  char *v18; // rax
  char *v19; // r15
  const char *v20; // rbp
  char *v21; // rax
  rsize_t v22; // r14
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
        while ( *(_BYTE *)(v10 + v6) );
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
        while ( *(_BYTE *)(v16 + v14) );
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
0x180007230  mov     [rsp+arg_0], rbx
0x180007235  push    rbp
0x180007236  push    rsi
0x180007237  push    rdi
0x180007238  push    r12
0x18000723a  push    r13
0x18000723c  push    r14
0x18000723e  push    r15
0x180007240  sub     rsp, 40h
0x180007244  mov     rsi, rdx
0x180007247  mov     r14, rcx
0x18000724a  test    rdx, rdx
0x18000724d  jnz     short loc_180007275
0x18000724f  mov     rcx, [rsp+78h]; this
0x180007254  mov     r9d, 80004003h; char *
0x18000725a  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180007261  mov     edx, 137h; void *
0x180007266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000726b  mov     eax, 80004003h
0x180007270  jmp     loc_1800073E6
0x180007275  test    r14, r14
0x180007278  jnz     short loc_1800072A0
0x18000727a  mov     rcx, [rsp+78h]; this
0x18000727f  mov     r9d, 80070057h; char *
0x180007285  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000728c  mov     edx, 138h; void *
0x180007291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007296  mov     eax, 80070057h
0x18000729b  jmp     loc_1800073E6
0x1800072a0  xor     r13d, r13d
0x1800072a3  mov     [rsp+78h+arg_8], r13
0x1800072ab  mov     [rsp+78h+arg_18], r13
0x1800072b3  mov     [rsp+78h+arg_10], r13
0x1800072bb  mov     rax, [rcx]
0x1800072be  mov     rax, [rax+18h]
0x1800072c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c7  mov     rbp, rax
0x1800072ca  mov     ebx, r13d
0x1800072cd  mov     [rsp+78h+arg_10], rbx
0x1800072d5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800072dc  test    rax, rax
0x1800072df  jz      short loc_18000731C
0x1800072e1  mov     rcx, rdi
0x1800072e4  lea     rcx, [rcx+1]
0x1800072e8  cmp     [rcx+rax], bl
0x1800072eb  jnz     short loc_1800072E4
0x1800072ed  lea     r12, [rcx+1]
0x1800072f1  mov     rcx, r12; cb
0x1800072f4  call    cs:__imp_CoTaskMemAlloc
0x1800072fa  mov     r15, rax
0x1800072fd  test    rax, rax
0x180007300  jz      short loc_18000731C
0x180007302  mov     r8, rbp; Source
0x180007305  mov     rdx, r12; SizeInBytes
0x180007308  mov     rcx, rax; Destination
0x18000730b  call    cs:__imp_strcpy_s
0x180007311  mov     rbx, r15
0x180007314  mov     [rsp+78h+arg_10], rbx
0x18000731c  mov     [rsp+78h+arg_8], r13
0x180007324  mov     rax, [r14]
0x180007327  mov     rcx, r14
0x18000732a  mov     rax, [rax+20h]
0x18000732e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007333  mov     rbp, rax
0x180007336  mov     [rsp+78h+arg_8], r13
0x18000733e  test    rax, rax
0x180007341  jz      short loc_180007382
0x180007343  mov     rcx, rdi
0x180007346  lea     rcx, [rcx+1]
0x18000734a  cmp     byte ptr [rcx+rax], 0
0x18000734e  jnz     short loc_180007346
0x180007350  lea     r12, [rcx+1]
0x180007354  mov     rcx, r12; cb
0x180007357  call    cs:__imp_CoTaskMemAlloc
0x18000735d  mov     r15, rax
0x180007360  xor     r13d, r13d
0x180007363  test    rax, rax
0x180007366  jz      short loc_180007382
0x180007368  mov     r8, rbp; Source
0x18000736b  mov     rdx, r12; SizeInBytes
0x18000736e  mov     rcx, rax; Destination
0x180007371  call    cs:__imp_strcpy_s
0x180007377  mov     [rsp+78h+arg_8], r15
0x18000737f  mov     r13, r15
0x180007382  mov     [rsp+78h+arg_18], 0
0x18000738e  mov     rax, [r14]
0x180007391  mov     rcx, r14
0x180007394  mov     rax, [rax+28h]
0x180007398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000739d  mov     rbp, rax
0x1800073a0  xor     eax, eax
0x1800073a2  test    rbp, rbp
0x1800073a5  jz      short loc_1800073D9
0x1800073a7  lea     rdi, [rdi+1]
0x1800073ab  cmp     [rdi+rbp], al
0x1800073ae  jnz     short loc_1800073A7
0x1800073b0  lea     r14, [rdi+1]
0x1800073b4  mov     rcx, r14; cb
0x1800073b7  call    cs:__imp_CoTaskMemAlloc
0x1800073bd  mov     rdi, rax
0x1800073c0  xor     eax, eax
0x1800073c2  test    rdi, rdi
0x1800073c5  jz      short loc_1800073D9
0x1800073c7  mov     r8, rbp; Source
0x1800073ca  mov     rdx, r14; SizeInBytes
0x1800073cd  mov     rcx, rdi; Destination
0x1800073d0  call    cs:__imp_strcpy_s
0x1800073d6  mov     rax, rdi
0x1800073d9  mov     [rsi], rbx
0x1800073dc  mov     [rsi+8], r13
0x1800073e0  mov     [rsi+10h], rax
0x1800073e4  xor     eax, eax
0x1800073e6  mov     rbx, [rsp+78h+arg_0]
0x1800073ee  add     rsp, 40h
0x1800073f2  pop     r15
0x1800073f4  pop     r14
0x1800073f6  pop     r13
0x1800073f8  pop     r12
0x1800073fa  pop     rdi
0x1800073fb  pop     rsi
0x1800073fc  pop     rbp
0x1800073fd  retn
```
