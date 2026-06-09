# UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140031c08`
- end: `0x140031e17`
- name: `?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z`
- size: `527`
- prototype: `__int64 __fastcall(void *, __int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140031544`

## callees

- `0x140002728`
- `0x14000c8a0`
- `0x140010cdc`
- `0x14001444c`
- `0x140014474`
- `0x140031c08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031cc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031d46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031cc1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031d46`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140031c9c`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140031c9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetServiceInformationFromCommandLine(void *a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned int ProcessCommandLine; // ebx
  int v8; // edi
  LPWSTR *v9; // r14
  LPWSTR v10; // rdx
  __int64 v11; // r8
  CUserModeHangReport *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  LPWSTR v15; // rdx
  __int64 v16; // r8
  LPCWSTR lpCmdLine[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v19[12]; // [rsp+30h] [rbp-18h] BYREF
  int pNumArgs; // [rsp+90h] [rbp+48h] BYREF

  lpCmdLine[0] = v19;
  lpCmdLine[1] = v19;
  v19[0] = 0;
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
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 92;
      v14 = ProcessCommandLine;
LABEL_31:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v14);
    }
    goto LABEL_32;
  }
  v8 = 1;
  v9 = CommandLineToArgvW(lpCmdLine[0], &pNumArgs);
  if ( pNumArgs <= 1 )
    goto LABEL_32;
  while ( !(unsigned int)_o__wcsicmp(L"-k", v9[v8]) )
  {
    if ( v8 + 1 < pNumArgs )
    {
      v10 = v9[v8 + 1];
      if ( *v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a2,
                                 v10) )
        {
          ProcessCommandLine = -2147024882;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 90;
LABEL_16:
            v14 = 2147942414LL;
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
  if ( (unsigned int)_o__wcsicmp(L"-s", v9[v8]) )
    goto LABEL_23;
  *a3 = 1;
  if ( v8 + 1 >= pNumArgs )
    goto LABEL_23;
  v15 = v9[v8 + 1];
  if ( !*v15 )
    goto LABEL_23;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a4, v15) )
    goto LABEL_23;
  ProcessCommandLine = -2147024882;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 91;
    goto LABEL_16;
  }
LABEL_32:
  if ( lpCmdLine[0] != v19 )
    operator delete((void *)lpCmdLine[0], (const struct std::nothrow_t *)&std::nothrow);
  return ProcessCommandLine;
}

```

## disassembly

```asm
0x140031c08  push    rbp
0x140031c0a  push    rbx
0x140031c0b  push    rsi
0x140031c0c  push    rdi
0x140031c0d  push    r12
0x140031c0f  push    r13
0x140031c11  push    r14
0x140031c13  push    r15
0x140031c15  mov     rbp, rsp
0x140031c18  sub     rsp, 48h
0x140031c1c  xor     edi, edi
0x140031c1e  lea     rax, [rbp+var_18]
0x140031c22  mov     [rbp+lpCmdLine], rax
0x140031c26  lea     rax, [rbp+var_18]
0x140031c2a  mov     [rbp+var_20], rax
0x140031c2e  mov     r12, r9
0x140031c31  mov     [rbp+var_18], di
0x140031c35  mov     r15, r8
0x140031c38  mov     [rbp+pNumArgs], edi
0x140031c3b  mov     r13, rdx
0x140031c3e  test    rcx, rcx
0x140031c41  jnz     short loc_140031C81
0x140031c43  mov     ebx, 80070057h
0x140031c48  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c4f  lea     rax, WPP_GLOBAL_Control
0x140031c56  cmp     rcx, rax
0x140031c59  jz      loc_140031E04
0x140031c5f  test    byte ptr [rcx+1Ch], 1
0x140031c63  jz      loc_140031E04
0x140031c69  mov     rcx, [rcx+10h]
0x140031c6d  lea     edx, [rdi+59h]
0x140031c70  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031c77  call    WPP_SF_
0x140031c7c  jmp     loc_140031DEB
0x140031c81  lea     rdx, [rbp+lpCmdLine]
0x140031c85  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140031c8a  mov     ebx, eax
0x140031c8c  test    eax, eax
0x140031c8e  js      loc_140031DBA
0x140031c94  mov     rcx, [rbp+lpCmdLine]; lpCmdLine
0x140031c98  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x140031c9c  call    cs:__imp_CommandLineToArgvW
0x140031ca2  mov     edi, 1
0x140031ca7  mov     r14, rax
0x140031caa  cmp     [rbp+pNumArgs], edi
0x140031cad  jle     loc_140031DEB
0x140031cb3  movsxd  rsi, edi
0x140031cb6  lea     rcx, aK; "-k"
0x140031cbd  mov     rdx, [r14+rsi*8]
0x140031cc1  call    cs:__imp__o__wcsicmp
0x140031cc7  xor     ecx, ecx
0x140031cc9  test    eax, eax
0x140031ccb  jnz     short loc_140031D3B
0x140031ccd  lea     eax, [rdi+1]
0x140031cd0  cmp     eax, [rbp+pNumArgs]
0x140031cd3  jge     loc_140031D85
0x140031cd9  mov     rdx, [r14+rsi*8+8]
0x140031cde  cmp     cx, [rdx]
0x140031ce1  jz      loc_140031D85
0x140031ce7  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031ceb  inc     r8
0x140031cee  cmp     [rdx+r8*2], cx
0x140031cf3  jnz     short loc_140031CEB
0x140031cf5  mov     rcx, r13
0x140031cf8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031cfd  test    al, al
0x140031cff  jnz     loc_140031D85
0x140031d05  mov     ebx, 8007000Eh
0x140031d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d11  lea     rax, WPP_GLOBAL_Control
0x140031d18  cmp     rcx, rax
0x140031d1b  jz      loc_140031DEB
0x140031d21  test    byte ptr [rcx+1Ch], 1
0x140031d25  jz      loc_140031DEB
0x140031d2b  mov     edx, 5Ah ; 'Z'
0x140031d30  mov     r9d, 8007000Eh
0x140031d36  jmp     loc_140031DDB
0x140031d3b  mov     rdx, [r14+rsi*8]
0x140031d3f  lea     rcx, aS_2; "-s"
0x140031d46  call    cs:__imp__o__wcsicmp
0x140031d4c  xor     ecx, ecx
0x140031d4e  test    eax, eax
0x140031d50  jnz     short loc_140031D85
0x140031d52  lea     eax, [rdi+1]
0x140031d55  mov     dword ptr [r15], 1
0x140031d5c  cmp     eax, [rbp+pNumArgs]
0x140031d5f  jge     short loc_140031D85
0x140031d61  mov     rdx, [r14+rsi*8+8]
0x140031d66  cmp     cx, [rdx]
0x140031d69  jz      short loc_140031D85
0x140031d6b  or      r8, 0FFFFFFFFFFFFFFFFh
0x140031d6f  inc     r8
0x140031d72  cmp     [rdx+r8*2], cx
0x140031d77  jnz     short loc_140031D6F
0x140031d79  mov     rcx, r12
0x140031d7c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031d81  test    al, al
0x140031d83  jz      short loc_140031D92
0x140031d85  inc     edi
0x140031d87  cmp     edi, [rbp+pNumArgs]
0x140031d8a  jl      loc_140031CB3
0x140031d90  jmp     short loc_140031DEB
0x140031d92  mov     ebx, 8007000Eh
0x140031d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d9e  lea     rax, WPP_GLOBAL_Control
0x140031da5  cmp     rcx, rax
0x140031da8  jz      short loc_140031DEB
0x140031daa  test    byte ptr [rcx+1Ch], 1
0x140031dae  jz      short loc_140031DEB
0x140031db0  mov     edx, 5Bh ; '['
0x140031db5  jmp     loc_140031D30
0x140031dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140031dc1  lea     rax, WPP_GLOBAL_Control
0x140031dc8  cmp     rcx, rax
0x140031dcb  jz      short loc_140031DEB
0x140031dcd  test    byte ptr [rcx+1Ch], 1
0x140031dd1  jz      short loc_140031DEB
0x140031dd3  mov     edx, 5Ch ; '\'
0x140031dd8  mov     r9d, ebx
0x140031ddb  mov     rcx, [rcx+10h]
0x140031ddf  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031de6  call    WPP_SF_d
0x140031deb  mov     rcx, [rbp+lpCmdLine]; void *
0x140031def  lea     rax, [rbp+var_18]
0x140031df3  cmp     rcx, rax
0x140031df6  jz      short loc_140031E04
0x140031df8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140031dff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140031e04  mov     eax, ebx
0x140031e06  add     rsp, 48h
0x140031e0a  pop     r15
0x140031e0c  pop     r14
0x140031e0e  pop     r13
0x140031e10  pop     r12
0x140031e12  pop     rdi
0x140031e13  pop     rsi
0x140031e14  pop     rbx
0x140031e15  pop     rbp
0x140031e16  retn
```
