# std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const *)

- ea: `0x140005ed8`
- end: `0x14000605e`
- name: `??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z`
- size: `390`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140007210`
- `0x140009dd8`
- `0x140009e94`
- `0x14000a75c`
- `0x14000d158`
- `0x14000d2c8`
- `0x14000d438`
- `0x14000f170`

## callees

- `0x140005ed8`
- `0x140007f94`
- `0x140013010`

## import_xrefs

- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x140005fa2`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x140005fa2`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140005f7f`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140005fc3`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140005f7f`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140005fc3`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x14000600a`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x14000600a`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140006019`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140006019`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140006003`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140006003`

## pseudocode

```c
__int64 *__fastcall std::operator<<<unsigned short,std::char_traits<unsigned short>>(__int64 *a1, __int64 a2)
{
  __int64 *v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // r15
  __int64 v6; // r14
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rax
  __int16 v10; // ax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-38h] BYREF
  char v15; // [rsp+28h] [rbp-30h]

  v3 = a1;
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  v6 = *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40);
  if ( v6 <= 0 || v6 <= v5 )
    v7 = 0;
  else
    v7 = v6 - v5;
  std::basic_ostream<unsigned short>::sentry::sentry(&v14, a1);
  if ( v15 )
  {
    v8 = *v3;
    v9 = *(int *)(*v3 + 4);
    if ( (*(_DWORD *)((_BYTE *)v3 + v9 + 24) & 0x1C0) != 0x40 )
    {
      while ( v7 > 0 )
      {
        try
        {
          v10 = std::basic_streambuf<unsigned short>::sputc(
                  *(__int64 *)((char *)v3 + *(int *)(*v3 + 4) + 72),
                  *(unsigned __int16 *)((char *)v3 + *(int *)(*v3 + 4) + 88));
        }
        catch ( ... )
        {
          LOBYTE(v11) = 1;
          std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), 4, v11);
          v3 = a1;
          v4 = 0;
          goto LABEL_21;
        }
        if ( v10 == -1 )
          goto LABEL_18;
        --v7;
      }
      v8 = *v3;
    }
    if ( std::basic_streambuf<unsigned short>::sputn(*(__int64 *)((char *)v3 + *(int *)(v8 + 4) + 72), a2, v5) == v5 )
    {
      while ( v7 > 0 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)v3 + *(int *)(*v3 + 4) + 72),
                                 *(unsigned __int16 *)((char *)v3 + *(int *)(*v3 + 4) + 88)) == 0xFFFF )
          goto LABEL_18;
        --v7;
      }
    }
    else
    {
LABEL_18:
      v4 = 4;
    }
    *(__int64 *)((char *)v3 + *(int *)(*v3 + 4) + 40) = 0;
  }
  else
  {
    v4 = 4;
  }
LABEL_21:
  std::basic_ios<unsigned short>::setstate((char *)v3 + *(int *)(*v3 + 4), v4, 0);
  if ( !std::uncaught_exception() )
    std::basic_ostream<unsigned short>::_Osfx(v14);
  v12 = *(_QWORD *)(*(int *)(*(_QWORD *)v14 + 4LL) + v14 + 72);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v3;
}

```

## disassembly

```asm
0x140005ed8  mov     [rsp+arg_8], rbx
0x140005edd  mov     [rsp+arg_18], rsi
0x140005ee2  mov     [rsp+arg_0], rcx
0x140005ee7  push    rdi
0x140005ee8  push    r12
0x140005eea  push    r13
0x140005eec  push    r14
0x140005eee  push    r15
0x140005ef0  sub     rsp, 30h
0x140005ef4  mov     r13, rdx
0x140005ef7  mov     rdi, rcx
0x140005efa  xor     esi, esi
0x140005efc  mov     ebx, esi
0x140005efe  mov     [rsp+58h+arg_10], ebx
0x140005f02  or      r15, 0FFFFFFFFFFFFFFFFh
0x140005f06  inc     r15
0x140005f09  cmp     [rdx+r15*2], si
0x140005f0e  jnz     short loc_140005F06
0x140005f10  mov     rax, [rcx]
0x140005f13  movsxd  rcx, dword ptr [rax+4]
0x140005f17  mov     r14, [rcx+rdi+28h]
0x140005f1c  test    r14, r14
0x140005f1f  jle     short loc_140005F2B
0x140005f21  cmp     r14, r15
0x140005f24  jle     short loc_140005F2B
0x140005f26  sub     r14, r15
0x140005f29  jmp     short loc_140005F2E
0x140005f2b  mov     r14, rsi
0x140005f2e  mov     rdx, rdi
0x140005f31  lea     rcx, [rsp+58h+var_38]
0x140005f36  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x140005f3b  nop
0x140005f3c  cmp     [rsp+58h+var_30], sil
0x140005f41  jnz     short loc_140005F4D
0x140005f43  mov     ebx, 4
0x140005f48  jmp     loc_140005FF4
0x140005f4d  mov     rdx, [rdi]
0x140005f50  movsxd  rax, dword ptr [rdx+4]
0x140005f54  mov     ecx, [rax+rdi+18h]
0x140005f58  and     ecx, 1C0h
0x140005f5e  mov     r12d, 0FFFFh
0x140005f64  cmp     ecx, 40h ; '@'
0x140005f67  jz      short loc_140005F93
0x140005f69  test    r14, r14
0x140005f6c  jle     short loc_140005F90
0x140005f6e  mov     rax, [rdi]
0x140005f71  movsxd  rcx, dword ptr [rax+4]
0x140005f75  movzx   edx, word ptr [rcx+rdi+58h]
0x140005f7a  mov     rcx, [rcx+rdi+48h]
0x140005f7f  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x140005f85  cmp     r12w, ax
0x140005f89  jz      short loc_140005FCF
0x140005f8b  dec     r14
0x140005f8e  jmp     short loc_140005F69
0x140005f90  mov     rdx, [rdi]
0x140005f93  movsxd  rcx, dword ptr [rdx+4]
0x140005f97  mov     r8, r15
0x140005f9a  mov     rdx, r13
0x140005f9d  mov     rcx, [rcx+rdi+48h]
0x140005fa2  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x140005fa8  cmp     rax, r15
0x140005fab  jnz     short loc_140005FCF
0x140005fad  test    r14, r14
0x140005fb0  jle     short loc_140005FD8
0x140005fb2  mov     rax, [rdi]
0x140005fb5  movsxd  rcx, dword ptr [rax+4]
0x140005fb9  movzx   edx, word ptr [rcx+rdi+58h]
0x140005fbe  mov     rcx, [rcx+rdi+48h]
0x140005fc3  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x140005fc9  cmp     r12w, ax
0x140005fcd  jnz     short loc_140005FE6
0x140005fcf  mov     ebx, 4
0x140005fd4  mov     [rsp+58h+arg_10], ebx
0x140005fd8  mov     rax, [rdi]
0x140005fdb  movsxd  rcx, dword ptr [rax+4]
0x140005fdf  mov     [rcx+rdi+28h], rsi
0x140005fe4  jmp     short loc_140005FF4
0x140005fe6  dec     r14
0x140005fe9  jmp     short loc_140005FAD
0x140005feb  mov     rdi, [rsp+58h+arg_0]
0x140005ff0  mov     ebx, [rsp+58h+arg_10]
0x140005ff4  mov     rax, [rdi]
0x140005ff7  movsxd  rcx, dword ptr [rax+4]
0x140005ffb  add     rcx, rdi
0x140005ffe  xor     r8d, r8d
0x140006001  mov     edx, ebx
0x140006003  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140006009  nop
0x14000600a  call    cs:__imp_?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x140006010  test    al, al
0x140006012  jnz     short loc_140006020
0x140006014  mov     rcx, [rsp+58h+var_38]
0x140006019  call    cs:__imp_?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x14000601f  nop
0x140006020  mov     rdx, [rsp+58h+var_38]
0x140006025  mov     rax, [rdx]
0x140006028  movsxd  rcx, dword ptr [rax+4]
0x14000602c  mov     rcx, [rcx+rdx+48h]
0x140006031  test    rcx, rcx
0x140006034  jz      short loc_140006043
0x140006036  mov     rax, [rcx]
0x140006039  mov     rax, [rax+10h]
0x14000603d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006042  nop
0x140006043  mov     rax, rdi
0x140006046  mov     rbx, [rsp+58h+arg_8]
0x14000604b  mov     rsi, [rsp+58h+arg_18]
0x140006050  add     rsp, 30h
0x140006054  pop     r15
0x140006056  pop     r14
0x140006058  pop     r13
0x14000605a  pop     r12
0x14000605c  pop     rdi
0x14000605d  retn
```
