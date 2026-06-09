# UtilIsHostedApp(wchar_t const *,int *,_HOSTED_PROCESS_TYPE *)

- ea: `0x140031e20`
- end: `0x1400320c6`
- name: `?UtilIsHostedApp@@YAJPEB_WPEAHPEAW4_HOSTED_PROCESS_TYPE@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(const wchar_t *, int *, enum _HOSTED_PROCESS_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001bdbc`

## callees

- `0x140002470`
- `0x140002728`
- `0x14000c8a0`
- `0x14001444c`
- `0x140014474`
- `0x140031e20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031f5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031f7b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031f5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140031f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003203d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003203d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140031e85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140031e85`

## pseudocode

```c
__int64 __fastcall UtilIsHostedApp(const wchar_t *a1, int *a2, enum _HOSTED_PROCESS_TYPE *a3)
{
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  const wchar_t *v10; // rdi
  DWORD LastError; // ebx
  unsigned int v12; // ebx
  void *v14[2]; // [rsp+20h] [rbp-89h] BYREF
  _WORD v15[8]; // [rsp+30h] [rbp-79h] BYREF
  WCHAR Buffer[64]; // [rsp+40h] [rbp-69h] BYREF

  *a2 = 0;
  v14[0] = v15;
  v15[0] = 0;
  v14[1] = v15;
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
                              v14,
                              a1,
                              v10 - a1 - 1) )
      {
        if ( !(unsigned int)_o__wcsicmp(Buffer, v14[0]) )
        {
          v12 = 0;
          while ( (unsigned int)_o__wcsicmp((&off_14007A240)[2 * v12], v10) )
          {
            if ( ++v12 >= 2 )
              goto LABEL_21;
          }
          *a2 = 1;
          *(_DWORD *)a3 = *((_DWORD *)&off_14007A240 + 4 * v12 + 2);
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
  if ( v14[0] != v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  return LastError;
}

```

## disassembly

```asm
0x140031e20  mov     [rsp-8+arg_18], rbx
0x140031e25  push    rbp
0x140031e26  push    rsi
0x140031e27  push    rdi
0x140031e28  push    r12
0x140031e2a  push    r13
0x140031e2c  push    r14
0x140031e2e  push    r15
0x140031e30  lea     rbp, [rsp-27h]
0x140031e35  sub     rsp, 0D0h
0x140031e3c  mov     rax, cs:__security_cookie
0x140031e43  xor     rax, rsp
0x140031e46  mov     [rbp+57h+var_40], rax
0x140031e4a  xor     r12d, r12d
0x140031e4d  lea     rax, [rbp+57h+var_D0]
0x140031e51  mov     [rdx], r12d
0x140031e54  mov     r14, rdx
0x140031e57  mov     [rsp+100h+var_E0], rax
0x140031e5c  mov     rbx, rcx
0x140031e5f  lea     rax, [rbp+57h+var_D0]
0x140031e63  mov     [rbp+57h+var_D0], r12w
0x140031e68  lea     edx, [r12+40h]; uSize
0x140031e6d  mov     [rsp+100h+var_D8], rax
0x140031e72  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x140031e76  mov     [rbp+57h+Buffer], r12w
0x140031e7b  mov     r15, r8
0x140031e7e  mov     dword ptr [r8], 3
0x140031e85  call    cs:__imp_GetSystemDirectoryW
0x140031e8b  dec     eax
0x140031e8d  cmp     eax, 3Fh ; '?'
0x140031e90  ja      loc_14003203D
0x140031e96  test    rbx, rbx
0x140031e99  jz      loc_140032008
0x140031e9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140031ea3  inc     rax
0x140031ea6  cmp     [rbx+rax*2], r12w
0x140031eab  jnz     short loc_140031EA3
0x140031ead  lea     rcx, [rbx+rax*2]
0x140031eb1  jmp     short loc_140031ED4
0x140031eb3  sub     rcx, 2
0x140031eb7  movzx   eax, word ptr [rcx]
0x140031eba  sub     ax, 2Fh ; '/'
0x140031ebe  cmp     ax, 2Dh ; '-'
0x140031ec2  ja      short loc_140031ED4
0x140031ec4  mov     rdx, 200000000801h
0x140031ece  bt      rdx, rax
0x140031ed2  jb      short loc_140031EDC
0x140031ed4  mov     rdi, rcx
0x140031ed7  cmp     rcx, rbx
0x140031eda  ja      short loc_140031EB3
0x140031edc  test    rdi, rdi
0x140031edf  jz      loc_140032008
0x140031ee5  cmp     rdi, rbx
0x140031ee8  jz      loc_140032008
0x140031eee  mov     r8, rdi
0x140031ef1  lea     rcx, [rsp+100h+var_E0]
0x140031ef6  sub     r8, rbx
0x140031ef9  mov     rdx, rbx
0x140031efc  sar     r8, 1
0x140031eff  dec     r8
0x140031f02  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031f07  test    al, al
0x140031f09  jnz     short loc_140031F51
0x140031f0b  mov     ebx, 8007000Eh
0x140031f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140031f17  lea     rax, WPP_GLOBAL_Control
0x140031f1e  cmp     rcx, rax
0x140031f21  jz      loc_140032083
0x140031f27  test    byte ptr [rcx+1Ch], 1
0x140031f2b  jz      loc_140032083
0x140031f31  mov     rcx, [rcx+10h]
0x140031f35  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031f3c  mov     edx, 3Ch ; '<'
0x140031f41  mov     r9d, 8007000Eh
0x140031f47  call    WPP_SF_d
0x140031f4c  jmp     loc_140032083
0x140031f51  mov     rdx, [rsp+100h+var_E0]
0x140031f56  lea     rcx, [rbp+57h+Buffer]
0x140031f5a  call    cs:__imp__o__wcsicmp
0x140031f60  test    eax, eax
0x140031f62  jnz     short loc_140031F9D
0x140031f64  mov     ebx, r12d
0x140031f67  lea     r13, off_14007A240; "svchost.exe"
0x140031f6e  mov     esi, ebx
0x140031f70  mov     rdx, rdi
0x140031f73  add     rsi, rsi
0x140031f76  mov     rcx, [r13+rsi*8+0]
0x140031f7b  call    cs:__imp__o__wcsicmp
0x140031f81  test    eax, eax
0x140031f83  jz      short loc_140031F8E
0x140031f85  inc     ebx
0x140031f87  cmp     ebx, 2
0x140031f8a  jb      short loc_140031F6E
0x140031f8c  jmp     short loc_140031F9D
0x140031f8e  mov     dword ptr [r14], 1
0x140031f95  mov     eax, [r13+rsi*8+8]
0x140031f9a  mov     [r15], eax
0x140031f9d  cmp     [r14], r12d
0x140031fa0  jz      short loc_140031FD5
0x140031fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140031fa9  lea     rax, WPP_GLOBAL_Control
0x140031fb0  cmp     rcx, rax
0x140031fb3  jz      short loc_140032003
0x140031fb5  test    byte ptr [rcx+1Ch], 4
0x140031fb9  jz      short loc_140032003
0x140031fbb  mov     r9d, [r15]
0x140031fbe  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031fc5  mov     rcx, [rcx+10h]
0x140031fc9  mov     edx, 3Dh ; '='
0x140031fce  call    WPP_SF_d
0x140031fd3  jmp     short loc_140032003
0x140031fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140031fdc  lea     rax, WPP_GLOBAL_Control
0x140031fe3  cmp     rcx, rax
0x140031fe6  jz      short loc_140032003
0x140031fe8  test    byte ptr [rcx+1Ch], 4
0x140031fec  jz      short loc_140032003
0x140031fee  mov     rcx, [rcx+10h]
0x140031ff2  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031ff9  mov     edx, 3Eh ; '>'
0x140031ffe  call    WPP_SF_
0x140032003  mov     ebx, r12d
0x140032006  jmp     short loc_140032083
0x140032008  mov     ebx, 80070057h
0x14003200d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032014  lea     rax, WPP_GLOBAL_Control
0x14003201b  cmp     rcx, rax
0x14003201e  jz      short loc_140032083
0x140032020  test    byte ptr [rcx+1Ch], 1
0x140032024  jz      short loc_140032083
0x140032026  mov     rcx, [rcx+10h]
0x14003202a  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140032031  mov     edx, 3Bh ; ';'
0x140032036  call    WPP_SF_
0x14003203b  jmp     short loc_140032083
0x14003203d  call    cs:__imp_GetLastError
0x140032043  mov     ebx, eax
0x140032045  mov     rcx, cs:WPP_GLOBAL_Control
0x14003204c  lea     rax, WPP_GLOBAL_Control
0x140032053  cmp     rcx, rax
0x140032056  jz      short loc_140032076
0x140032058  test    byte ptr [rcx+1Ch], 1
0x14003205c  jz      short loc_140032076
0x14003205e  mov     rcx, [rcx+10h]
0x140032062  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140032069  mov     edx, 3Ah ; ':'
0x14003206e  mov     r9d, ebx
0x140032071  call    WPP_SF_d
0x140032076  test    ebx, ebx
0x140032078  jle     short loc_140032083
0x14003207a  movzx   ebx, bx
0x14003207d  or      ebx, 80070000h
0x140032083  mov     rcx, [rsp+100h+var_E0]; void *
0x140032088  lea     rax, [rbp+57h+var_D0]
0x14003208c  cmp     rcx, rax
0x14003208f  jz      short loc_14003209D
0x140032091  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140032098  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003209d  mov     eax, ebx
0x14003209f  mov     rcx, [rbp+57h+var_40]
0x1400320a3  xor     rcx, rsp; StackCookie
0x1400320a6  call    __security_check_cookie
0x1400320ab  mov     rbx, [rsp+100h+arg_18]
0x1400320b3  add     rsp, 0D0h
0x1400320ba  pop     r15
0x1400320bc  pop     r14
0x1400320be  pop     r13
0x1400320c0  pop     r12
0x1400320c2  pop     rdi
0x1400320c3  pop     rsi
0x1400320c4  pop     rbp
0x1400320c5  retn
```
