# ATL::CComObject<CPimcTablet>::CreateInstance(ATL::CComObject<CPimcTablet> * *)

- ea: `0x18000c35c`
- end: `0x18000c472`
- name: `?CreateInstance@?$CComObject@VCPimcTablet@@@ATL@@SAJPEAPEAV12@@Z`
- size: `278`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bbb0`

## callees

- `0x18000c35c`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ATL::CComObject<CPimcTablet>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v3; // r14d
  char *v4; // rax
  char *v5; // rdi
  __int64 *v6; // rdx
  char *v7; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+70h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  try
  {
    v4 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 2) = 0;
      v6 = (__int64 *)(v4 + 16);
      *((_QWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 3) = 0;
      *((_DWORD *)v4 + 8) = 0;
      v4[48] = 0;
      *((_QWORD *)v4 + 9) = 0;
      v4[92] = 0;
      *((_DWORD *)v4 + 13) = 0;
      *((_QWORD *)v4 + 7) = 0;
      *((_QWORD *)v4 + 8) = 0;
      if ( *((_QWORD *)v4 + 2) )
      {
        v9 = *v6;
        *v6 = 0;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      *(_QWORD *)v5 = &ATL::CComObject<CPimcTablet>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v7 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = *((_DWORD *)v5 + 2);
    v3 = 0;
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000c35c  mov     [rsp+arg_0], rcx
0x18000c361  push    rbx
0x18000c362  push    rsi
0x18000c363  push    rdi
0x18000c364  push    r14
0x18000c366  sub     rsp, 38h
0x18000c36a  mov     rsi, rcx
0x18000c36d  xor     ebx, ebx
0x18000c36f  test    rcx, rcx
0x18000c372  jnz     short loc_18000C37E
0x18000c374  mov     eax, 80004003h
0x18000c379  jmp     loc_18000C468
0x18000c37e  mov     [rcx], rbx
0x18000c381  mov     r14d, 8007000Eh
0x18000c387  mov     [rsp+58h+arg_8], r14d
0x18000c38c  mov     [rsp+58h+var_38], rbx
0x18000c391  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c398  mov     ecx, 60h ; '`'; unsigned __int64
0x18000c39d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c3a2  mov     rdi, rax
0x18000c3a5  mov     [rsp+58h+arg_18], rax
0x18000c3aa  test    rax, rax
0x18000c3ad  jz      loc_18000C439
0x18000c3b3  mov     [rax+8], ebx
0x18000c3b6  lea     rdx, [rax+10h]
0x18000c3ba  mov     [rsp+58h+arg_10], rdx
0x18000c3bf  mov     [rdx], rbx
0x18000c3c2  add     rax, 18h
0x18000c3c6  mov     [rsp+58h+arg_10], rax
0x18000c3cb  mov     [rax], rbx
0x18000c3ce  mov     [rdi+20h], ebx
0x18000c3d1  mov     [rdi+30h], bl
0x18000c3d4  mov     [rdi+48h], rbx
0x18000c3d8  mov     [rdi+5Ch], bl
0x18000c3db  mov     [rdi+34h], ebx
0x18000c3de  mov     [rdi+38h], rbx
0x18000c3e2  mov     [rdi+40h], rbx
0x18000c3e6  cmp     [rdx], rbx
0x18000c3e9  jz      short loc_18000C418
0x18000c3eb  mov     [rsp+58h+arg_10], rbx
0x18000c3f0  mov     rcx, [rsp+58h+arg_10]
0x18000c3f5  mov     rax, [rdx]
0x18000c3f8  mov     [rsp+58h+arg_10], rax
0x18000c3fd  mov     [rdx], rcx
0x18000c400  mov     rcx, [rsp+58h+arg_10]
0x18000c405  test    rcx, rcx
0x18000c408  jz      short loc_18000C418
0x18000c40a  mov     rax, [rcx]
0x18000c40d  mov     rax, [rax+10h]
0x18000c411  call    cs:__guard_dispatch_icall_fptr
0x18000c417  nop
0x18000c418  lea     rax, ??_7?$CComObject@VCPimcTablet@@@ATL@@6B@; const ATL::CComObject<CPimcTablet>::`vftable'
0x18000c41f  mov     [rdi], rax
0x18000c422  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c429  mov     rax, [rcx]
0x18000c42c  mov     rax, [rax+8]
0x18000c430  call    cs:__guard_dispatch_icall_fptr
0x18000c436  nop
0x18000c437  jmp     short loc_18000C43C
0x18000c439  mov     rdi, rbx
0x18000c43c  mov     [rsp+58h+var_38], rdi
0x18000c441  jmp     short loc_18000C454
0x18000c443  xor     ebx, ebx
0x18000c445  mov     rsi, [rsp+58h+arg_0]
0x18000c44a  mov     r14d, [rsp+58h+arg_8]
0x18000c44f  mov     rdi, [rsp+58h+var_38]
0x18000c454  test    rdi, rdi
0x18000c457  jz      short loc_18000C462
0x18000c459  mov     eax, [rdi+8]
0x18000c45c  mov     [rdi+8], eax
0x18000c45f  mov     r14d, ebx
0x18000c462  mov     [rsi], rdi
0x18000c465  mov     eax, r14d
0x18000c468  add     rsp, 38h
0x18000c46c  pop     r14
0x18000c46e  pop     rdi
0x18000c46f  pop     rsi
0x18000c470  pop     rbx
0x18000c471  retn
```
