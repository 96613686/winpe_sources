# FwCopyCSRule

- ea: `0x180007200`
- end: `0x1800078cf`
- name: `FwCopyCSRule`
- size: `1743`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800042c4`
- `0x180007200`
- `0x1800088a0`
- `0x18001e770`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x18000721e`
- `fwbase!FwAlloc` at `0x18000721e`
- `fwbase!FwArrayCopy` at `0x1800072d6`
- `fwbase!FwArrayCopy` at `0x180007339`
- `fwbase!FwArrayCopy` at `0x1800073f7`
- `fwbase!FwArrayCopy` at `0x180007466`
- `fwbase!FwArrayCopy` at `0x1800072d6`
- `fwbase!FwArrayCopy` at `0x180007339`
- `fwbase!FwArrayCopy` at `0x1800073f7`
- `fwbase!FwArrayCopy` at `0x180007466`
- `fwbase!FwStringCopy` at `0x18000752a`
- `fwbase!FwStringCopy` at `0x18000756c`
- `fwbase!FwStringCopy` at `0x1800075b4`
- `fwbase!FwStringCopy` at `0x1800075fc`
- `fwbase!FwStringCopy` at `0x180007644`
- `fwbase!FwStringCopy` at `0x18000768c`
- `fwbase!FwStringCopy` at `0x1800076d4`
- `fwbase!FwStringCopy` at `0x180007734`
- `fwbase!FwStringCopy` at `0x18000777c`
- `fwbase!FwStringCopy` at `0x180007829`
- `fwbase!FwStringCopy` at `0x180007866`
- `fwbase!FwStringCopy` at `0x18000752a`
- `fwbase!FwStringCopy` at `0x18000756c`
- `fwbase!FwStringCopy` at `0x1800075b4`
- `fwbase!FwStringCopy` at `0x1800075fc`
- `fwbase!FwStringCopy` at `0x180007644`
- `fwbase!FwStringCopy` at `0x18000768c`
- `fwbase!FwStringCopy` at `0x1800076d4`
- `fwbase!FwStringCopy` at `0x180007734`
- `fwbase!FwStringCopy` at `0x18000777c`
- `fwbase!FwStringCopy` at `0x180007829`
- `fwbase!FwStringCopy` at `0x180007866`

## pseudocode

```c
__int64 __fastcall FwCopyCSRule(__int64 a1, void **a2)
{
  void *v4; // rax
  int v5; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(520);
  *a2 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x208u);
    *((_WORD *)*a2 + 4) = *(_WORD *)(a1 + 8);
    *((_WORD *)*a2 + 170) = *(_WORD *)(a1 + 340);
    *((_DWORD *)*a2 + 84) = *(_DWORD *)(a1 + 336);
    *((_DWORD *)*a2 + 10) = *(_DWORD *)(a1 + 40);
    *((_WORD *)*a2 + 152) = *(_WORD *)(a1 + 304);
    v5 = FwArrayCopy(
           16,
           FwShallowCopySidAndAttributes,
           wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
           a1 + 192,
           (char *)*a2 + 192);
    if ( v5 >= 0 )
    {
      v5 = FwArrayCopy(
             4,
             FwCopyPlatform,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             a1 + 352,
             (char *)*a2 + 352);
      if ( v5 >= 0 )
      {
        *((_DWORD *)*a2 + 52) = *(_DWORD *)(a1 + 208);
        *((_DWORD *)*a2 + 53) = *(_DWORD *)(a1 + 212);
        *(_OWORD *)((char *)*a2 + 216) = *(_OWORD *)(a1 + 216);
        *((_DWORD *)*a2 + 58) = *(_DWORD *)(a1 + 232);
        *(_OWORD *)((char *)*a2 + 236) = *(_OWORD *)(a1 + 236);
        *((_WORD *)*a2 + 128) = *(_WORD *)(a1 + 256);
        v5 = FwArrayCopy(
               4,
               FwCopyPlatform,
               wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
               a1 + 264,
               (char *)*a2 + 264);
        if ( v5 >= 0 )
        {
          *((_WORD *)*a2 + 140) = *(_WORD *)(a1 + 280);
          v5 = FwArrayCopy(
                 4,
                 FwCopyPlatform,
                 wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                 a1 + 288,
                 (char *)*a2 + 288);
          if ( v5 >= 0 )
          {
            v5 = FwCopyWFAddressesContents(a1 + 48, (char *)*a2 + 48);
            if ( v5 >= 0 )
            {
              v5 = FwCopyWFAddressesContents(a1 + 120, (char *)*a2 + 120);
              if ( v5 >= 0 )
              {
                v5 = FwStringCopy(*(_QWORD *)(a1 + 24), (char *)*a2 + 24);
                if ( v5 >= 0 )
                {
                  v5 = FwStringCopy(*(_QWORD *)(a1 + 32), (char *)*a2 + 32);
                  if ( v5 >= 0 )
                  {
                    v5 = FwStringCopy(*(_QWORD *)(a1 + 344), (char *)*a2 + 344);
                    if ( v5 >= 0 )
                    {
                      v5 = FwStringCopy(*(_QWORD *)(a1 + 312), (char *)*a2 + 312);
                      if ( v5 >= 0 )
                      {
                        v5 = FwStringCopy(*(_QWORD *)(a1 + 320), (char *)*a2 + 320);
                        if ( v5 >= 0 )
                        {
                          v5 = FwStringCopy(*(_QWORD *)(a1 + 328), (char *)*a2 + 328);
                          if ( v5 >= 0 )
                          {
                            v5 = FwStringCopy(*(_QWORD *)(a1 + 376), (char *)*a2 + 376);
                            if ( v5 >= 0 )
                            {
                              *((_DWORD *)*a2 + 96) = *(_DWORD *)(a1 + 384);
                              *((_DWORD *)*a2 + 92) = *(_DWORD *)(a1 + 368);
                              v5 = FwStringCopy(*(_QWORD *)(a1 + 16), (char *)*a2 + 16);
                              if ( v5 >= 0 )
                              {
                                v5 = FwStringCopy(*(_QWORD *)(a1 + 416), (char *)*a2 + 416);
                                if ( v5 >= 0 )
                                {
                                  v5 = FwCopyWFAddressesContents(a1 + 424, (char *)*a2 + 424);
                                  if ( v5 >= 0 )
                                  {
                                    *((_DWORD *)*a2 + 124) = *(_DWORD *)(a1 + 496);
                                    *((_DWORD *)*a2 + 125) = *(_DWORD *)(a1 + 500);
                                    v5 = FwStringCopy(*(_QWORD *)(a1 + 504), (char *)*a2 + 504);
                                    if ( v5 >= 0 )
                                    {
                                      v5 = FwStringCopy(*(_QWORD *)(a1 + 512), (char *)*a2 + 512);
                                      if ( v5 >= 0 )
                                      {
                                        *(_QWORD *)*a2 = 0;
                                        return (unsigned int)v5;
                                      }
                                      v6 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                        && (WPP_GLOBAL_Control[14] & 1) != 0 )
                                      {
                                        v7 = 81;
                                        goto LABEL_77;
                                      }
                                    }
                                    else
                                    {
                                      v6 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                        && (WPP_GLOBAL_Control[14] & 1) != 0 )
                                      {
                                        v7 = 80;
                                        goto LABEL_77;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    v6 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                      && (WPP_GLOBAL_Control[14] & 1) != 0 )
                                    {
                                      v7 = 79;
                                      goto LABEL_77;
                                    }
                                  }
                                }
                                else
                                {
                                  v6 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                    && (WPP_GLOBAL_Control[14] & 1) != 0 )
                                  {
                                    v7 = 78;
                                    goto LABEL_77;
                                  }
                                }
                              }
                              else
                              {
                                v6 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                  && (WPP_GLOBAL_Control[14] & 1) != 0 )
                                {
                                  v7 = 77;
                                  goto LABEL_77;
                                }
                              }
                            }
                            else
                            {
                              v6 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                                && (WPP_GLOBAL_Control[14] & 1) != 0 )
                              {
                                v7 = 76;
                                goto LABEL_77;
                              }
                            }
                          }
                          else
                          {
                            v6 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
                              && (WPP_GLOBAL_Control[14] & 1) != 0 )
                            {
                              v7 = 75;
                              goto LABEL_77;
                            }
                          }
                        }
                        else
                        {
                          v6 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                          {
                            v7 = 74;
                            goto LABEL_77;
                          }
                        }
                      }
                      else
                      {
                        v6 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                        {
                          v7 = 73;
                          goto LABEL_77;
                        }
                      }
                    }
                    else
                    {
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                      {
                        v7 = 72;
                        goto LABEL_77;
                      }
                    }
                  }
                  else
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                    {
                      v7 = 71;
                      goto LABEL_77;
                    }
                  }
                }
                else
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v7 = 70;
                    goto LABEL_77;
                  }
                }
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v7 = 69;
                  goto LABEL_77;
                }
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v7 = 68;
                goto LABEL_77;
              }
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v7 = 67;
              goto LABEL_77;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v7 = 66;
            goto LABEL_77;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v7 = 65;
          goto LABEL_77;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v7 = 64;
        goto LABEL_77;
      }
    }
  }
  else
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 63;
LABEL_77:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
    }
  }
  if ( *a2 )
  {
    FwCSRuleFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007200  push    rbx
0x180007202  push    rsi
0x180007203  push    rdi
0x180007204  push    r14
0x180007206  sub     rsp, 38h
0x18000720a  mov     rsi, rcx
0x18000720d  mov     qword ptr [rdx], 0
0x180007214  mov     ebx, 208h
0x180007219  mov     rdi, rdx
0x18000721c  mov     ecx, ebx
0x18000721e  call    cs:__imp_FwAlloc
0x180007224  mov     [rdi], rax
0x180007227  test    rax, rax
0x18000722a  jnz     short loc_18000725C
0x18000722c  mov     ebx, 8007000Eh
0x180007231  mov     rcx, cs:WPP_GLOBAL_Control
0x180007238  lea     rax, WPP_GLOBAL_Control
0x18000723f  cmp     rcx, rax
0x180007242  jz      loc_1800078A3
0x180007248  test    byte ptr [rcx+1Ch], 1
0x18000724c  jz      loc_1800078A3
0x180007252  mov     edx, 3Fh ; '?'
0x180007257  jmp     loc_180007890
0x18000725c  mov     r8, rbx; Size
0x18000725f  xor     edx, edx; Val
0x180007261  mov     rcx, rax; void *
0x180007264  call    memset_0
0x180007269  movzx   eax, word ptr [rsi+8]
0x18000726d  lea     r9, [rsi+0C0h]
0x180007274  mov     rcx, [rdi]
0x180007277  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000727e  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x180007285  mov     [rcx+8], ax
0x180007289  movzx   eax, word ptr [rsi+154h]
0x180007290  mov     rcx, [rdi]
0x180007293  mov     [rcx+154h], ax
0x18000729a  mov     eax, [rsi+150h]
0x1800072a0  mov     rcx, [rdi]
0x1800072a3  mov     [rcx+150h], eax
0x1800072a9  mov     eax, [rsi+28h]
0x1800072ac  mov     rcx, [rdi]
0x1800072af  mov     [rcx+28h], eax
0x1800072b2  mov     rcx, [rdi]
0x1800072b5  movzx   eax, word ptr [rsi+130h]
0x1800072bc  mov     [rcx+130h], ax
0x1800072c3  mov     ecx, 10h
0x1800072c8  mov     rax, [rdi]
0x1800072cb  add     rax, 0C0h
0x1800072d1  mov     [rsp+58h+var_38], rax
0x1800072d6  call    cs:__imp_FwArrayCopy
0x1800072dc  mov     ebx, eax
0x1800072de  test    eax, eax
0x1800072e0  jns     short loc_18000730D
0x1800072e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072e9  lea     rax, WPP_GLOBAL_Control
0x1800072f0  cmp     rcx, rax
0x1800072f3  jz      loc_1800078A3
0x1800072f9  test    byte ptr [rcx+1Ch], 1
0x1800072fd  jz      loc_1800078A3
0x180007303  mov     edx, 40h ; '@'
0x180007308  jmp     loc_180007890
0x18000730d  mov     rax, [rdi]
0x180007310  lea     r9, [rsi+160h]
0x180007317  add     rax, 160h
0x18000731d  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007324  mov     r14d, 4
0x18000732a  mov     [rsp+58h+var_38], rax
0x18000732f  lea     rdx, FwCopyPlatform
0x180007336  mov     ecx, r14d
0x180007339  call    cs:__imp_FwArrayCopy
0x18000733f  mov     ebx, eax
0x180007341  test    eax, eax
0x180007343  jns     short loc_18000736F
0x180007345  mov     rcx, cs:WPP_GLOBAL_Control
0x18000734c  lea     rax, WPP_GLOBAL_Control
0x180007353  cmp     rcx, rax
0x180007356  jz      loc_1800078A3
0x18000735c  test    byte ptr [rcx+1Ch], 1
0x180007360  jz      loc_1800078A3
0x180007366  lea     edx, [r14+3Dh]
0x18000736a  jmp     loc_180007890
0x18000736f  mov     eax, [rsi+0D0h]
0x180007375  lea     r9, [rsi+108h]
0x18000737c  mov     rcx, [rdi]
0x18000737f  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007386  lea     rdx, FwCopyPlatform
0x18000738d  mov     [rcx+0D0h], eax
0x180007393  mov     rcx, [rdi]
0x180007396  mov     eax, [rsi+0D4h]
0x18000739c  mov     [rcx+0D4h], eax
0x1800073a2  mov     rax, [rdi]
0x1800073a5  movups  xmm0, xmmword ptr [rsi+0D8h]
0x1800073ac  movdqu  xmmword ptr [rax+0D8h], xmm0
0x1800073b4  mov     rcx, [rdi]
0x1800073b7  mov     eax, [rsi+0E8h]
0x1800073bd  mov     [rcx+0E8h], eax
0x1800073c3  mov     rax, [rdi]
0x1800073c6  movups  xmm0, xmmword ptr [rsi+0ECh]
0x1800073cd  movdqu  xmmword ptr [rax+0ECh], xmm0
0x1800073d5  mov     rcx, [rdi]
0x1800073d8  movzx   eax, word ptr [rsi+100h]
0x1800073df  mov     [rcx+100h], ax
0x1800073e6  mov     rcx, r14
0x1800073e9  mov     rax, [rdi]
0x1800073ec  add     rax, 108h
0x1800073f2  mov     [rsp+58h+var_38], rax
0x1800073f7  call    cs:__imp_FwArrayCopy
0x1800073fd  mov     ebx, eax
0x1800073ff  test    eax, eax
0x180007401  jns     short loc_18000742E
0x180007403  mov     rcx, cs:WPP_GLOBAL_Control
0x18000740a  lea     rax, WPP_GLOBAL_Control
0x180007411  cmp     rcx, rax
0x180007414  jz      loc_1800078A3
0x18000741a  test    byte ptr [rcx+1Ch], 1
0x18000741e  jz      loc_1800078A3
0x180007424  mov     edx, 42h ; 'B'
0x180007429  jmp     loc_180007890
0x18000742e  mov     r9, [rdi]
0x180007431  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007438  movzx   eax, word ptr [rsi+118h]
0x18000743f  lea     rdx, FwCopyPlatform
0x180007446  mov     rcx, r14
0x180007449  mov     [r9+118h], ax
0x180007451  lea     r9, [rsi+120h]
0x180007458  mov     rax, [rdi]
0x18000745b  add     rax, 120h
0x180007461  mov     [rsp+58h+var_38], rax
0x180007466  call    cs:__imp_FwArrayCopy
0x18000746c  mov     ebx, eax
0x18000746e  test    eax, eax
0x180007470  jns     short loc_18000749D
0x180007472  mov     rcx, cs:WPP_GLOBAL_Control
0x180007479  lea     rax, WPP_GLOBAL_Control
0x180007480  cmp     rcx, rax
0x180007483  jz      loc_1800078A3
0x180007489  test    byte ptr [rcx+1Ch], 1
0x18000748d  jz      loc_1800078A3
0x180007493  mov     edx, 43h ; 'C'
0x180007498  jmp     loc_180007890
0x18000749d  mov     rdx, [rdi]
0x1800074a0  lea     rcx, [rsi+30h]
0x1800074a4  add     rdx, 30h ; '0'
0x1800074a8  call    FwCopyWFAddressesContents
0x1800074ad  mov     ebx, eax
0x1800074af  test    eax, eax
0x1800074b1  jns     short loc_1800074DE
0x1800074b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074ba  lea     rax, WPP_GLOBAL_Control
0x1800074c1  cmp     rcx, rax
0x1800074c4  jz      loc_1800078A3
0x1800074ca  test    byte ptr [rcx+1Ch], 1
0x1800074ce  jz      loc_1800078A3
0x1800074d4  mov     edx, 44h ; 'D'
0x1800074d9  jmp     loc_180007890
0x1800074de  mov     rdx, [rdi]
0x1800074e1  lea     rcx, [rsi+78h]
0x1800074e5  add     rdx, 78h ; 'x'
0x1800074e9  call    FwCopyWFAddressesContents
0x1800074ee  mov     ebx, eax
0x1800074f0  test    eax, eax
0x1800074f2  jns     short loc_18000751F
0x1800074f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074fb  lea     rax, WPP_GLOBAL_Control
0x180007502  cmp     rcx, rax
0x180007505  jz      loc_1800078A3
0x18000750b  test    byte ptr [rcx+1Ch], 1
0x18000750f  jz      loc_1800078A3
0x180007515  mov     edx, 45h ; 'E'
0x18000751a  jmp     loc_180007890
0x18000751f  mov     rdx, [rdi]
0x180007522  mov     rcx, [rsi+18h]
0x180007526  add     rdx, 18h
0x18000752a  call    cs:__imp_FwStringCopy
0x180007530  mov     ebx, eax
0x180007532  test    eax, eax
0x180007534  jns     short loc_180007561
0x180007536  mov     rcx, cs:WPP_GLOBAL_Control
0x18000753d  lea     rax, WPP_GLOBAL_Control
0x180007544  cmp     rcx, rax
0x180007547  jz      loc_1800078A3
0x18000754d  test    byte ptr [rcx+1Ch], 1
0x180007551  jz      loc_1800078A3
0x180007557  mov     edx, 46h ; 'F'
0x18000755c  jmp     loc_180007890
0x180007561  mov     rdx, [rdi]
0x180007564  mov     rcx, [rsi+20h]
0x180007568  add     rdx, 20h ; ' '
0x18000756c  call    cs:__imp_FwStringCopy
0x180007572  mov     ebx, eax
0x180007574  test    eax, eax
0x180007576  jns     short loc_1800075A3
0x180007578  mov     rcx, cs:WPP_GLOBAL_Control
0x18000757f  lea     rax, WPP_GLOBAL_Control
0x180007586  cmp     rcx, rax
0x180007589  jz      loc_1800078A3
0x18000758f  test    byte ptr [rcx+1Ch], 1
0x180007593  jz      loc_1800078A3
0x180007599  mov     edx, 47h ; 'G'
0x18000759e  jmp     loc_180007890
0x1800075a3  mov     rdx, [rdi]
0x1800075a6  mov     rcx, [rsi+158h]
0x1800075ad  add     rdx, 158h
0x1800075b4  call    cs:__imp_FwStringCopy
0x1800075ba  mov     ebx, eax
0x1800075bc  test    eax, eax
0x1800075be  jns     short loc_1800075EB
0x1800075c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075c7  lea     rax, WPP_GLOBAL_Control
0x1800075ce  cmp     rcx, rax
0x1800075d1  jz      loc_1800078A3
0x1800075d7  test    byte ptr [rcx+1Ch], 1
0x1800075db  jz      loc_1800078A3
0x1800075e1  mov     edx, 48h ; 'H'
0x1800075e6  jmp     loc_180007890
0x1800075eb  mov     rdx, [rdi]
0x1800075ee  mov     rcx, [rsi+138h]
0x1800075f5  add     rdx, 138h
0x1800075fc  call    cs:__imp_FwStringCopy
0x180007602  mov     ebx, eax
0x180007604  test    eax, eax
0x180007606  jns     short loc_180007633
0x180007608  mov     rcx, cs:WPP_GLOBAL_Control
0x18000760f  lea     rax, WPP_GLOBAL_Control
0x180007616  cmp     rcx, rax
0x180007619  jz      loc_1800078A3
0x18000761f  test    byte ptr [rcx+1Ch], 1
0x180007623  jz      loc_1800078A3
0x180007629  mov     edx, 49h ; 'I'
0x18000762e  jmp     loc_180007890
0x180007633  mov     rdx, [rdi]
0x180007636  mov     rcx, [rsi+140h]
0x18000763d  add     rdx, 140h
0x180007644  call    cs:__imp_FwStringCopy
0x18000764a  mov     ebx, eax
0x18000764c  test    eax, eax
0x18000764e  jns     short loc_18000767B
0x180007650  mov     rcx, cs:WPP_GLOBAL_Control
0x180007657  lea     rax, WPP_GLOBAL_Control
0x18000765e  cmp     rcx, rax
0x180007661  jz      loc_1800078A3
0x180007667  test    byte ptr [rcx+1Ch], 1
0x18000766b  jz      loc_1800078A3
0x180007671  mov     edx, 4Ah ; 'J'
0x180007676  jmp     loc_180007890
0x18000767b  mov     rdx, [rdi]
0x18000767e  mov     rcx, [rsi+148h]
0x180007685  add     rdx, 148h
0x18000768c  call    cs:__imp_FwStringCopy
0x180007692  mov     ebx, eax
0x180007694  test    eax, eax
0x180007696  jns     short loc_1800076C3
0x180007698  mov     rcx, cs:WPP_GLOBAL_Control
0x18000769f  lea     rax, WPP_GLOBAL_Control
0x1800076a6  cmp     rcx, rax
0x1800076a9  jz      loc_1800078A3
0x1800076af  test    byte ptr [rcx+1Ch], 1
0x1800076b3  jz      loc_1800078A3
0x1800076b9  mov     edx, 4Bh ; 'K'
0x1800076be  jmp     loc_180007890
0x1800076c3  mov     rdx, [rdi]
0x1800076c6  mov     rcx, [rsi+178h]
0x1800076cd  add     rdx, 178h
0x1800076d4  call    cs:__imp_FwStringCopy
0x1800076da  mov     ebx, eax
0x1800076dc  test    eax, eax
0x1800076de  jns     short loc_18000770B
0x1800076e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076e7  lea     rax, WPP_GLOBAL_Control
0x1800076ee  cmp     rcx, rax
0x1800076f1  jz      loc_1800078A3
0x1800076f7  test    byte ptr [rcx+1Ch], 1
0x1800076fb  jz      loc_1800078A3
0x180007701  mov     edx, 4Ch ; 'L'
0x180007706  jmp     loc_180007890
0x18000770b  mov     rcx, [rdi]
0x18000770e  mov     eax, [rsi+180h]
0x180007714  mov     [rcx+180h], eax
0x18000771a  mov     rcx, [rdi]
0x18000771d  mov     eax, [rsi+170h]
0x180007723  mov     [rcx+170h], eax
0x180007729  mov     rdx, [rdi]
0x18000772c  mov     rcx, [rsi+10h]
0x180007730  add     rdx, 10h
0x180007734  call    cs:__imp_FwStringCopy
0x18000773a  mov     ebx, eax
0x18000773c  test    eax, eax
0x18000773e  jns     short loc_18000776B
0x180007740  mov     rcx, cs:WPP_GLOBAL_Control
0x180007747  lea     rax, WPP_GLOBAL_Control
0x18000774e  cmp     rcx, rax
0x180007751  jz      loc_1800078A3
0x180007757  test    byte ptr [rcx+1Ch], 1
0x18000775b  jz      loc_1800078A3
0x180007761  mov     edx, 4Dh ; 'M'
0x180007766  jmp     loc_180007890
0x18000776b  mov     rdx, [rdi]
0x18000776e  mov     rcx, [rsi+1A0h]
0x180007775  add     rdx, 1A0h
0x18000777c  call    cs:__imp_FwStringCopy
  ... truncated ...
```
