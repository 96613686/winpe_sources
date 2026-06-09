# UtilIsHostedApp(wchar_t const *,int *,_HOSTED_PROCESS_TYPE *)

- ea: `0x140034024`
- end: `0x1400342e6`
- name: `?UtilIsHostedApp@@YAJPEB_WPEAHPEAW4_HOSTED_PROCESS_TYPE@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(const wchar_t *, int *, enum _HOSTED_PROCESS_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001cf1c`

## callees

- `0x140002490`
- `0x140002748`
- `0x14000ca20`
- `0x140014ee4`
- `0x140014f14`
- `0x140034024`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140034164`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003418b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140034164`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003418b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034256`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140034089`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140034089`

## pseudocode

```c
__int64 __fastcall UtilIsHostedApp(const wchar_t *a1, int *a2, enum _HOSTED_PROCESS_TYPE *a3)
{
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  const wchar_t *v10; // rdi
  __int64 v11; // r8
  DWORD LastError; // ebx
  __int64 v13; // r8
  unsigned int v14; // ebx
  void *v16[2]; // [rsp+20h] [rbp-89h] BYREF
  _WORD v17[8]; // [rsp+30h] [rbp-79h] BYREF
  WCHAR Buffer[64]; // [rsp+40h] [rbp-69h] BYREF

  *a2 = 0;
  v16[0] = v17;
  v17[0] = 0;
  v16[1] = v17;
  Buffer[0] = 0;
  *(_DWORD *)a3 = 3;
  if ( GetSystemDirectoryW(Buffer, 0x40u) - 1 > 0x3F )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, LastError);
    }
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( !a1 )
      goto LABEL_29;
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = &a1[v6];
    while ( 1 )
    {
      v10 = v7;
      if ( v7 <= a1 )
        break;
      v8 = *--v7;
      LOWORD(v8) = v8 - 47;
      if ( (unsigned __int16)v8 <= 0x2Du )
      {
        v9 = 0x200000000801LL;
        if ( _bittest64(&v9, v8) )
          break;
      }
    }
    if ( v10 && v10 != a1 )
    {
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              v16,
                              a1) )
      {
        if ( !(unsigned int)_o__wcsicmp(Buffer, v16[0], v11) )
        {
          v14 = 0;
          while ( (unsigned int)_o__wcsicmp((&off_14007E238)[2 * v14], v10, v13) )
          {
            if ( ++v14 >= 2 )
              goto LABEL_21;
          }
          *a2 = 1;
          *(_DWORD *)a3 = *((_DWORD *)&off_14007E238 + 4 * v14 + 2);
        }
LABEL_21:
        if ( *a2 )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              *(unsigned int *)a3);
          }
        }
        else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
        }
        LastError = 0;
      }
      else
      {
        LastError = -2147024882;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
            2147942414LL);
        }
      }
    }
    else
    {
LABEL_29:
      LastError = -2147024809;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
      }
    }
  }
  if ( v16[0] != v17 )
    operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
  return LastError;
}

```

## disassembly

```asm
0x140034024  mov     [rsp-8+arg_18], rbx
0x140034029  push    rbp
0x14003402a  push    rsi
0x14003402b  push    rdi
0x14003402c  push    r12
0x14003402e  push    r13
0x140034030  push    r14
0x140034032  push    r15
0x140034034  lea     rbp, [rsp-27h]
0x140034039  sub     rsp, 0D0h
0x140034040  mov     rax, cs:__security_cookie
0x140034047  xor     rax, rsp
0x14003404a  mov     [rbp+57h+var_40], rax
0x14003404e  xor     r12d, r12d
0x140034051  lea     rax, [rbp+57h+var_D0]
0x140034055  mov     [rdx], r12d
0x140034058  mov     r14, rdx
0x14003405b  mov     [rsp+100h+var_E0], rax
0x140034060  mov     rbx, rcx
0x140034063  lea     rax, [rbp+57h+var_D0]
0x140034067  mov     [rbp+57h+var_D0], r12w
0x14003406c  lea     edx, [r12+40h]; uSize
0x140034071  mov     [rsp+100h+var_D8], rax
0x140034076  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x14003407a  mov     [rbp+57h+Buffer], r12w
0x14003407f  mov     r15, r8
0x140034082  mov     dword ptr [r8], 3
0x140034089  call    cs:__imp_GetSystemDirectoryW
0x140034090  nop     dword ptr [rax+rax+00h]
0x140034095  dec     eax
0x140034097  cmp     eax, 3Fh ; '?'
0x14003409a  ja      loc_140034256
0x1400340a0  test    rbx, rbx
0x1400340a3  jz      loc_140034221
0x1400340a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400340ad  inc     rax
0x1400340b0  cmp     [rbx+rax*2], r12w
0x1400340b5  jnz     short loc_1400340AD
0x1400340b7  lea     rcx, [rbx+rax*2]
0x1400340bb  jmp     short loc_1400340DE
0x1400340bd  sub     rcx, 2
0x1400340c1  movzx   eax, word ptr [rcx]
0x1400340c4  sub     ax, 2Fh ; '/'
0x1400340c8  cmp     ax, 2Dh ; '-'
0x1400340cc  ja      short loc_1400340DE
0x1400340ce  mov     rdx, 200000000801h
0x1400340d8  bt      rdx, rax
0x1400340dc  jb      short loc_1400340E6
0x1400340de  mov     rdi, rcx
0x1400340e1  cmp     rcx, rbx
0x1400340e4  ja      short loc_1400340BD
0x1400340e6  test    rdi, rdi
0x1400340e9  jz      loc_140034221
0x1400340ef  cmp     rdi, rbx
0x1400340f2  jz      loc_140034221
0x1400340f8  mov     r8, rdi
0x1400340fb  lea     rcx, [rsp+100h+var_E0]
0x140034100  sub     r8, rbx
0x140034103  mov     rdx, rbx
0x140034106  sar     r8, 1
0x140034109  dec     r8
0x14003410c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140034111  test    al, al
0x140034113  jnz     short loc_14003415B
0x140034115  mov     ebx, 8007000Eh
0x14003411a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034121  lea     rax, WPP_GLOBAL_Control
0x140034128  cmp     rcx, rax
0x14003412b  jz      loc_1400342A2
0x140034131  test    byte ptr [rcx+1Ch], 1
0x140034135  jz      loc_1400342A2
0x14003413b  mov     rcx, [rcx+10h]
0x14003413f  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140034146  mov     edx, 3Ch ; '<'
0x14003414b  mov     r9d, 8007000Eh
0x140034151  call    WPP_SF_d
0x140034156  jmp     loc_1400342A2
0x14003415b  mov     rdx, [rsp+100h+var_E0]
0x140034160  lea     rcx, [rbp+57h+Buffer]
0x140034164  call    cs:__imp__o__wcsicmp
0x14003416b  nop     dword ptr [rax+rax+00h]
0x140034170  test    eax, eax
0x140034172  jnz     short loc_1400341B3
0x140034174  mov     ebx, r12d
0x140034177  lea     r13, off_14007E238; "svchost.exe"
0x14003417e  mov     esi, ebx
0x140034180  mov     rdx, rdi
0x140034183  add     rsi, rsi
0x140034186  mov     rcx, [r13+rsi*8+0]
0x14003418b  call    cs:__imp__o__wcsicmp
0x140034192  nop     dword ptr [rax+rax+00h]
0x140034197  test    eax, eax
0x140034199  jz      short loc_1400341A4
0x14003419b  inc     ebx
0x14003419d  cmp     ebx, 2
0x1400341a0  jb      short loc_14003417E
0x1400341a2  jmp     short loc_1400341B3
0x1400341a4  mov     dword ptr [r14], 1
0x1400341ab  mov     eax, [r13+rsi*8+8]
0x1400341b0  mov     [r15], eax
0x1400341b3  cmp     [r14], r12d
0x1400341b6  jz      short loc_1400341EB
0x1400341b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400341bf  lea     rax, WPP_GLOBAL_Control
0x1400341c6  cmp     rcx, rax
0x1400341c9  jz      short loc_140034219
0x1400341cb  test    byte ptr [rcx+1Ch], 4
0x1400341cf  jz      short loc_140034219
0x1400341d1  mov     r9d, [r15]
0x1400341d4  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1400341db  mov     rcx, [rcx+10h]
0x1400341df  mov     edx, 3Dh ; '='
0x1400341e4  call    WPP_SF_d
0x1400341e9  jmp     short loc_140034219
0x1400341eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400341f2  lea     rax, WPP_GLOBAL_Control
0x1400341f9  cmp     rcx, rax
0x1400341fc  jz      short loc_140034219
0x1400341fe  test    byte ptr [rcx+1Ch], 4
0x140034202  jz      short loc_140034219
0x140034204  mov     rcx, [rcx+10h]
0x140034208  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14003420f  mov     edx, 3Eh ; '>'
0x140034214  call    WPP_SF_
0x140034219  mov     ebx, r12d
0x14003421c  jmp     loc_1400342A2
0x140034221  mov     ebx, 80070057h
0x140034226  mov     rcx, cs:WPP_GLOBAL_Control
0x14003422d  lea     rax, WPP_GLOBAL_Control
0x140034234  cmp     rcx, rax
0x140034237  jz      short loc_1400342A2
0x140034239  test    byte ptr [rcx+1Ch], 1
0x14003423d  jz      short loc_1400342A2
0x14003423f  mov     rcx, [rcx+10h]
0x140034243  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14003424a  mov     edx, 3Bh ; ';'
0x14003424f  call    WPP_SF_
0x140034254  jmp     short loc_1400342A2
0x140034256  call    cs:__imp_GetLastError
0x14003425d  nop     dword ptr [rax+rax+00h]
0x140034262  mov     ebx, eax
0x140034264  mov     rcx, cs:WPP_GLOBAL_Control
0x14003426b  lea     rax, WPP_GLOBAL_Control
0x140034272  cmp     rcx, rax
0x140034275  jz      short loc_140034295
0x140034277  test    byte ptr [rcx+1Ch], 1
0x14003427b  jz      short loc_140034295
0x14003427d  mov     rcx, [rcx+10h]
0x140034281  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140034288  mov     edx, 3Ah ; ':'
0x14003428d  mov     r9d, ebx
0x140034290  call    WPP_SF_d
0x140034295  test    ebx, ebx
0x140034297  jle     short loc_1400342A2
0x140034299  movzx   ebx, bx
0x14003429c  or      ebx, 80070000h
0x1400342a2  mov     rcx, [rsp+100h+var_E0]; void *
0x1400342a7  lea     rax, [rbp+57h+var_D0]
0x1400342ab  cmp     rcx, rax
0x1400342ae  jz      short loc_1400342BC
0x1400342b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400342b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400342bc  mov     eax, ebx
0x1400342be  mov     rcx, [rbp+57h+var_40]
0x1400342c2  xor     rcx, rsp; StackCookie
0x1400342c5  call    __security_check_cookie
0x1400342ca  mov     rbx, [rsp+100h+arg_18]
0x1400342d2  add     rsp, 0D0h
0x1400342d9  pop     r15
0x1400342db  pop     r14
0x1400342dd  pop     r13
0x1400342df  pop     r12
0x1400342e1  pop     rdi
0x1400342e2  pop     rsi
0x1400342e3  pop     rbp
0x1400342e4  retn
```
