# UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140033dfc`
- end: `0x14003401e`
- name: `?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140033798`

## callees

- `0x140002748`
- `0x14000ca20`
- `0x1400113b8`
- `0x140014ee4`
- `0x140014f14`
- `0x140033dfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140033ebb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140033f46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140033ebb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140033f46`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140033e90`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140033e90`

## pseudocode

```c
__int64 __fastcall UtilGetServiceInformationFromCommandLine(void *a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned int ProcessCommandLine; // ebx
  int v8; // edi
  __int64 v9; // r8
  LPWSTR *v10; // r14
  LPWSTR v11; // rdx
  __int64 v12; // r8
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  LPWSTR v16; // rdx
  __int64 v17; // r8
  LPCWSTR lpCmdLine[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v20[12]; // [rsp+30h] [rbp-18h] BYREF
  int pNumArgs; // [rsp+90h] [rbp+48h] BYREF

  lpCmdLine[0] = v20;
  lpCmdLine[1] = v20;
  v20[0] = 0;
  pNumArgs = 0;
  if ( !a1 )
  {
    ProcessCommandLine = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
      goto LABEL_32;
    }
    return ProcessCommandLine;
  }
  ProcessCommandLine = UtilGetProcessCommandLine(a1, (__int64)lpCmdLine);
  if ( (ProcessCommandLine & 0x80000000) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 92;
      v15 = ProcessCommandLine;
LABEL_31:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v15);
    }
    goto LABEL_32;
  }
  v8 = 1;
  v10 = CommandLineToArgvW(lpCmdLine[0], &pNumArgs);
  if ( pNumArgs <= 1 )
    goto LABEL_32;
  while ( !(unsigned int)_o__wcsicmp(L"-k", v10[v8], v9) )
  {
    if ( v8 + 1 < pNumArgs )
    {
      v11 = v10[v8 + 1];
      if ( *v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 v11) )
        {
          ProcessCommandLine = -2147024882;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 90;
LABEL_16:
            v15 = 2147942414LL;
            goto LABEL_31;
          }
          goto LABEL_32;
        }
      }
    }
LABEL_23:
    if ( ++v8 >= pNumArgs )
      goto LABEL_32;
  }
  if ( (unsigned int)_o__wcsicmp(L"-s", v10[v8], v9) )
    goto LABEL_23;
  *a3 = 1;
  if ( v8 + 1 >= pNumArgs )
    goto LABEL_23;
  v16 = v10[v8 + 1];
  if ( !*v16 )
    goto LABEL_23;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a4, v16) )
    goto LABEL_23;
  ProcessCommandLine = -2147024882;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 91;
    goto LABEL_16;
  }
LABEL_32:
  if ( lpCmdLine[0] != v20 )
    operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
  return ProcessCommandLine;
}

```

## disassembly

```asm
0x140033dfc  push    rbp
0x140033dfe  push    rbx
0x140033dff  push    rsi
0x140033e00  push    rdi
0x140033e01  push    r12
0x140033e03  push    r13
0x140033e05  push    r14
0x140033e07  push    r15
0x140033e09  mov     rbp, rsp
0x140033e0c  sub     rsp, 48h
0x140033e10  xor     edi, edi
0x140033e12  lea     rax, [rbp+var_18]
0x140033e16  mov     [rbp+lpCmdLine], rax
0x140033e1a  lea     rax, [rbp+var_18]
0x140033e1e  mov     [rbp+var_20], rax
0x140033e22  mov     r12, r9
0x140033e25  mov     [rbp+var_18], di
0x140033e29  mov     r15, r8
0x140033e2c  mov     [rbp+pNumArgs], edi
0x140033e2f  mov     r13, rdx
0x140033e32  test    rcx, rcx
0x140033e35  jnz     short loc_140033E75
0x140033e37  mov     ebx, 80070057h
0x140033e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e43  lea     rax, WPP_GLOBAL_Control
0x140033e4a  cmp     rcx, rax
0x140033e4d  jz      loc_14003400A
0x140033e53  test    byte ptr [rcx+1Ch], 1
0x140033e57  jz      loc_14003400A
0x140033e5d  mov     rcx, [rcx+10h]
0x140033e61  lea     edx, [rdi+59h]
0x140033e64  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033e6b  call    WPP_SF_
0x140033e70  jmp     loc_140033FF1
0x140033e75  lea     rdx, [rbp+lpCmdLine]
0x140033e79  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140033e7e  mov     ebx, eax
0x140033e80  test    eax, eax
0x140033e82  js      loc_140033FC0
0x140033e88  mov     rcx, [rbp+lpCmdLine]; lpCmdLine
0x140033e8c  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x140033e90  call    cs:__imp_CommandLineToArgvW
0x140033e97  nop     dword ptr [rax+rax+00h]
0x140033e9c  mov     edi, 1
0x140033ea1  mov     r14, rax
0x140033ea4  cmp     [rbp+pNumArgs], edi
0x140033ea7  jle     loc_140033FF1
0x140033ead  movsxd  rsi, edi
0x140033eb0  lea     rcx, aK; "-k"
0x140033eb7  mov     rdx, [r14+rsi*8]
0x140033ebb  call    cs:__imp__o__wcsicmp
0x140033ec2  nop     dword ptr [rax+rax+00h]
0x140033ec7  xor     ecx, ecx
0x140033ec9  test    eax, eax
0x140033ecb  jnz     short loc_140033F3B
0x140033ecd  lea     eax, [rdi+1]
0x140033ed0  cmp     eax, [rbp+pNumArgs]
0x140033ed3  jge     loc_140033F8B
0x140033ed9  mov     rdx, [r14+rsi*8+8]
0x140033ede  cmp     cx, [rdx]
0x140033ee1  jz      loc_140033F8B
0x140033ee7  or      r8, 0FFFFFFFFFFFFFFFFh
0x140033eeb  inc     r8
0x140033eee  cmp     [rdx+r8*2], cx
0x140033ef3  jnz     short loc_140033EEB
0x140033ef5  mov     rcx, r13
0x140033ef8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140033efd  test    al, al
0x140033eff  jnz     loc_140033F8B
0x140033f05  mov     ebx, 8007000Eh
0x140033f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f11  lea     rax, WPP_GLOBAL_Control
0x140033f18  cmp     rcx, rax
0x140033f1b  jz      loc_140033FF1
0x140033f21  test    byte ptr [rcx+1Ch], 1
0x140033f25  jz      loc_140033FF1
0x140033f2b  mov     edx, 5Ah ; 'Z'
0x140033f30  mov     r9d, 8007000Eh
0x140033f36  jmp     loc_140033FE1
0x140033f3b  mov     rdx, [r14+rsi*8]
0x140033f3f  lea     rcx, aS_2; "-s"
0x140033f46  call    cs:__imp__o__wcsicmp
0x140033f4d  nop     dword ptr [rax+rax+00h]
0x140033f52  xor     ecx, ecx
0x140033f54  test    eax, eax
0x140033f56  jnz     short loc_140033F8B
0x140033f58  lea     eax, [rdi+1]
0x140033f5b  mov     dword ptr [r15], 1
0x140033f62  cmp     eax, [rbp+pNumArgs]
0x140033f65  jge     short loc_140033F8B
0x140033f67  mov     rdx, [r14+rsi*8+8]
0x140033f6c  cmp     cx, [rdx]
0x140033f6f  jz      short loc_140033F8B
0x140033f71  or      r8, 0FFFFFFFFFFFFFFFFh
0x140033f75  inc     r8
0x140033f78  cmp     [rdx+r8*2], cx
0x140033f7d  jnz     short loc_140033F75
0x140033f7f  mov     rcx, r12
0x140033f82  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140033f87  test    al, al
0x140033f89  jz      short loc_140033F98
0x140033f8b  inc     edi
0x140033f8d  cmp     edi, [rbp+pNumArgs]
0x140033f90  jl      loc_140033EAD
0x140033f96  jmp     short loc_140033FF1
0x140033f98  mov     ebx, 8007000Eh
0x140033f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033fa4  lea     rax, WPP_GLOBAL_Control
0x140033fab  cmp     rcx, rax
0x140033fae  jz      short loc_140033FF1
0x140033fb0  test    byte ptr [rcx+1Ch], 1
0x140033fb4  jz      short loc_140033FF1
0x140033fb6  mov     edx, 5Bh ; '['
0x140033fbb  jmp     loc_140033F30
0x140033fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140033fc7  lea     rax, WPP_GLOBAL_Control
0x140033fce  cmp     rcx, rax
0x140033fd1  jz      short loc_140033FF1
0x140033fd3  test    byte ptr [rcx+1Ch], 1
0x140033fd7  jz      short loc_140033FF1
0x140033fd9  mov     edx, 5Ch ; '\'
0x140033fde  mov     r9d, ebx
0x140033fe1  mov     rcx, [rcx+10h]
0x140033fe5  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033fec  call    WPP_SF_d
0x140033ff1  mov     rcx, [rbp+lpCmdLine]; void *
0x140033ff5  lea     rax, [rbp+var_18]
0x140033ff9  cmp     rcx, rax
0x140033ffc  jz      short loc_14003400A
0x140033ffe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140034005  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003400a  mov     eax, ebx
0x14003400c  add     rsp, 48h
0x140034010  pop     r15
0x140034012  pop     r14
0x140034014  pop     r13
0x140034016  pop     r12
0x140034018  pop     rdi
0x140034019  pop     rsi
0x14003401a  pop     rbx
0x14003401b  pop     rbp
0x14003401c  retn
```
