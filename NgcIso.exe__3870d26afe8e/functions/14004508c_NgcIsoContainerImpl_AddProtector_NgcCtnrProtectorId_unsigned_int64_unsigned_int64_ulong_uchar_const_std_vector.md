# NgcIsoContainerImpl::AddProtector(NgcCtnrProtectorId,unsigned __int64,unsigned __int64,ulong,uchar const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x14004508c`
- end: `0x140045361`
- name: `?AddProtector@NgcIsoContainerImpl@@QEAAJW4NgcCtnrProtectorId@@_K1KPEBEPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400222d0`

## callees

- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b3a0`
- `0x14000e034`
- `0x14004508c`
- `0x140045368`
- `0x1400455f0`
- `0x140053e40`
- `0x140071010`

## string_xrefs

- `0x1400450d6`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x140045100`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x14004523a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x1400452af`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x1400452f8`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x140045338`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcIsoContainerImpl::AddProtector(
        __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  int AuthorizingProtectorForTicket; // esi
  __int64 v12; // rdx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // [rsp+20h] [rbp-48h]
  int v30; // [rsp+20h] [rbp-48h]
  int v31; // [rsp+20h] [rbp-48h]
  int v32; // [rsp+20h] [rbp-48h]
  int v33; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v34[32]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  int v36; // [rsp+A0h] [rbp+38h] BYREF

  if ( *(_DWORD *)(a1 + 24) != 2 )
    goto LABEL_17;
  v36 = 0;
  AuthorizingProtectorForTicket = TicketManager::GetAuthorizingProtectorForTicket(
                                    *(TicketManager **)(a1 + 208),
                                    a3,
                                    (enum NgcCtnrProtectorId *)&v36);
  if ( AuthorizingProtectorForTicket < 0 )
  {
    v12 = 452;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
      (const char *)(unsigned int)AuthorizingProtectorForTicket,
      v29);
    return (unsigned int)AuthorizingProtectorForTicket;
  }
  if ( v36 != 5 )
  {
    v33 = 0;
    AuthorizingProtectorForTicket = TicketManager::GetAuthorizingProtectorForTicket(
                                      *(TicketManager **)(a1 + 208),
                                      a4,
                                      (enum NgcCtnrProtectorId *)&v33);
    if ( AuthorizingProtectorForTicket < 0 )
    {
      v12 = 458;
      goto LABEL_4;
    }
    if ( v33 == 5 )
    {
      v14 = 459;
      goto LABEL_7;
    }
    if ( a2 == 7 )
    {
      if ( v36 != 1 )
      {
        v14 = 464;
        goto LABEL_7;
      }
      if ( v33 != 1 )
      {
        v14 = 465;
        goto LABEL_7;
      }
    }
LABEL_17:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v34);
    if ( a2 )
    {
      v16 = a2 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( !v18 )
          {
            v26 = NgcIsoContainerImpl::AddRecoveryProtector((NgcIsoContainerImpl *)a1, a3, a4);
            v15 = v26;
            if ( v26 < 0 )
            {
              v23 = (unsigned int)v26;
              v24 = 499;
              goto LABEL_39;
            }
LABEL_36:
            std::vector<unsigned char>::operator=(a7, v34);
            std::vector<unsigned char>::_Tidy(v34);
            return 0;
          }
          v19 = v18 - 1;
          if ( !v19 )
            goto LABEL_37;
          v20 = v19 - 1;
          if ( v20 )
          {
            v21 = v20 - 1;
            if ( v21 )
            {
              if ( v21 == 1 )
              {
                v29 = a6;
                v22 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64, _QWORD))(*(_QWORD *)a1 + 40LL))(
                        a1,
                        a3,
                        a4,
                        (unsigned int)a5);
                v15 = v22;
                if ( v22 < 0 )
                {
                  v23 = (unsigned int)v22;
                  v24 = 493;
LABEL_39:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
                    (const char *)v23,
                    v29);
                  std::vector<unsigned char>::_Tidy(v34);
                  return v15;
                }
                goto LABEL_36;
              }
              goto LABEL_37;
            }
            v15 = -2147467263;
            v24 = 509;
          }
          else
          {
            v30 = a5;
            v25 = NgcIsoContainerImpl::AddTpmPasswordProtector(a1, 5, a3, a4);
            v15 = v25;
            if ( v25 >= 0 )
              goto LABEL_36;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2F2,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
              (const char *)(unsigned int)v25,
              v30);
            v24 = 506;
          }
        }
        else
        {
          v31 = a5;
          v27 = NgcIsoContainerImpl::AddTpmPasswordProtector(a1, 2, a3, a4);
          v15 = v27;
          if ( v27 >= 0 )
            goto LABEL_36;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
            (const char *)(unsigned int)v27,
            v31);
          v24 = 485;
        }
      }
      else
      {
        v32 = a5;
        v28 = NgcIsoContainerImpl::AddTpmPasswordProtector(a1, 1, a3, a4);
        v15 = v28;
        if ( v28 >= 0 )
          goto LABEL_36;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21C,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
          (const char *)(unsigned int)v28,
          v32);
        v24 = 478;
      }
LABEL_38:
      v23 = v15;
      goto LABEL_39;
    }
LABEL_37:
    v15 = -2147024809;
    v24 = 513;
    goto LABEL_38;
  }
  v14 = 453;
LABEL_7:
  v15 = -2146893808;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
    (const char *)0x80090010LL,
    v29);
  return v15;
}

```

## disassembly

```asm
0x14004508c  push    rbp
0x14004508e  push    rbx
0x14004508f  push    rsi
0x140045090  push    rdi
0x140045091  push    r14
0x140045093  push    r15
0x140045095  mov     rbp, rsp
0x140045098  sub     rsp, 68h
0x14004509c  mov     r15, r9
0x14004509f  mov     r14, r8
0x1400450a2  mov     ebx, edx
0x1400450a4  mov     rdi, rcx
0x1400450a7  cmp     dword ptr [rcx+18h], 2
0x1400450ab  jnz     loc_14004516B
0x1400450b1  mov     [rbp+arg_0], 0
0x1400450b8  lea     r8, [rbp+arg_0]; enum NgcCtnrProtectorId *
0x1400450bc  mov     rdx, r14; unsigned __int64
0x1400450bf  mov     rcx, [rcx+0D0h]; this
0x1400450c6  call    ?GetAuthorizingProtectorForTicket@TicketManager@@QEAAJ_KPEAW4NgcCtnrProtectorId@@@Z; TicketManager::GetAuthorizingProtectorForTicket(unsigned __int64,NgcCtnrProtectorId *)
0x1400450cb  mov     esi, eax
0x1400450cd  test    eax, eax
0x1400450cf  jns     short loc_1400450F0
0x1400450d1  mov     edx, 1C4h; void *
0x1400450d6  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400450dd  mov     r9d, esi; char *
0x1400450e0  mov     rcx, [rbp+30h]; this
0x1400450e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400450e9  mov     eax, esi
0x1400450eb  jmp     loc_140045354
0x1400450f0  cmp     [rbp+arg_0], 5
0x1400450f4  jnz     short loc_140045118
0x1400450f6  mov     edx, 1C5h; void *
0x1400450fb  mov     ebx, 80090010h
0x140045100  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140045107  mov     r9d, ebx; char *
0x14004510a  mov     rcx, [rbp+30h]; this
0x14004510e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045113  jmp     loc_140045352
0x140045118  mov     [rbp+var_28], 0
0x14004511f  lea     r8, [rbp+var_28]; enum NgcCtnrProtectorId *
0x140045123  mov     rdx, r15; unsigned __int64
0x140045126  mov     rcx, [rdi+0D0h]; this
0x14004512d  call    ?GetAuthorizingProtectorForTicket@TicketManager@@QEAAJ_KPEAW4NgcCtnrProtectorId@@@Z; TicketManager::GetAuthorizingProtectorForTicket(unsigned __int64,NgcCtnrProtectorId *)
0x140045132  mov     esi, eax
0x140045134  test    eax, eax
0x140045136  jns     short loc_14004513F
0x140045138  mov     edx, 1CAh
0x14004513d  jmp     short loc_1400450D6
0x14004513f  cmp     [rbp+var_28], 5
0x140045143  jnz     short loc_14004514C
0x140045145  mov     edx, 1CBh
0x14004514a  jmp     short loc_1400450FB
0x14004514c  cmp     ebx, 7
0x14004514f  jnz     short loc_14004516B
0x140045151  cmp     [rbp+arg_0], 1
0x140045155  jz      short loc_14004515E
0x140045157  mov     edx, 1D0h
0x14004515c  jmp     short loc_1400450FB
0x14004515e  cmp     [rbp+var_28], 1
0x140045162  jz      short loc_14004516B
0x140045164  mov     edx, 1D1h
0x140045169  jmp     short loc_1400450FB
0x14004516b  lea     rcx, [rbp+var_20]
0x14004516f  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140045174  nop
0x140045175  test    ebx, ebx
0x140045177  jz      loc_14004532B
0x14004517d  sub     ebx, 1
0x140045180  jz      loc_1400452C7
0x140045186  sub     ebx, 1
0x140045189  jz      loc_14004527E
0x14004518f  sub     ebx, 1
0x140045192  jz      loc_140045255
0x140045198  sub     ebx, 1
0x14004519b  jz      loc_14004532B
0x1400451a1  sub     ebx, 1
0x1400451a4  jz      short loc_140045205
0x1400451a6  sub     ebx, 1
0x1400451a9  jz      short loc_1400451F6
0x1400451ab  cmp     ebx, 1
0x1400451ae  jnz     loc_14004532B
0x1400451b4  mov     rax, [rdi]
0x1400451b7  mov     r9d, [rbp+arg_20]
0x1400451bb  lea     rcx, [rbp+var_20]
0x1400451bf  mov     [rsp+68h+var_40], rcx
0x1400451c4  mov     rcx, [rbp+arg_28]
0x1400451c8  mov     qword ptr [rsp+68h+var_48], rcx
0x1400451cd  mov     r8, r15
0x1400451d0  mov     rdx, r14
0x1400451d3  mov     rcx, rdi
0x1400451d6  mov     rax, [rax+28h]
0x1400451da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400451df  mov     ebx, eax
0x1400451e1  test    eax, eax
0x1400451e3  jns     loc_140045310
0x1400451e9  mov     r9d, eax
0x1400451ec  mov     edx, 1EDh
0x1400451f1  jmp     loc_140045338
0x1400451f6  mov     ebx, 80004001h
0x1400451fb  mov     edx, 1FDh
0x140045200  jmp     loc_140045335
0x140045205  mov     ecx, [rbp+arg_20]
0x140045208  mov     rax, [rbp+arg_28]
0x14004520c  mov     [rsp+68h+var_40], rax
0x140045211  mov     qword ptr [rsp+68h+var_48], rcx; int
0x140045216  mov     r9, r15
0x140045219  mov     r8, r14
0x14004521c  mov     edx, 5
0x140045221  mov     rcx, rdi
0x140045224  call    ?AddTpmPasswordProtector@NgcIsoContainerImpl@@IEAAJW4NgcCtnrProtectorId@@_K11PEBE@Z; NgcIsoContainerImpl::AddTpmPasswordProtector(NgcCtnrProtectorId,unsigned __int64,unsigned __int64,unsigned __int64,uchar const *)
0x140045229  mov     ebx, eax
0x14004522b  test    eax, eax
0x14004522d  jns     loc_140045310
0x140045233  mov     rcx, [rbp+30h]; this
0x140045237  mov     r9d, eax; char *
0x14004523a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140045241  mov     edx, 2F2h; void *
0x140045246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004524b  mov     edx, 1FAh
0x140045250  jmp     loc_140045335
0x140045255  lea     r9, [rbp+var_20]
0x140045259  mov     r8, r15
0x14004525c  mov     rdx, r14
0x14004525f  mov     rcx, rdi
0x140045262  call    ?AddRecoveryProtector@NgcIsoContainerImpl@@IEAAJ_K0PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoContainerImpl::AddRecoveryProtector(unsigned __int64,unsigned __int64,std::vector<uchar> *)
0x140045267  mov     ebx, eax
0x140045269  test    eax, eax
0x14004526b  jns     loc_140045310
0x140045271  mov     r9d, eax
0x140045274  mov     edx, 1F3h
0x140045279  jmp     loc_140045338
0x14004527e  mov     ecx, [rbp+arg_20]
0x140045281  mov     rax, [rbp+arg_28]
0x140045285  mov     [rsp+68h+var_40], rax
0x14004528a  mov     qword ptr [rsp+68h+var_48], rcx; int
0x14004528f  mov     r9, r15
0x140045292  mov     r8, r14
0x140045295  mov     edx, 2
0x14004529a  mov     rcx, rdi
0x14004529d  call    ?AddTpmPasswordProtector@NgcIsoContainerImpl@@IEAAJW4NgcCtnrProtectorId@@_K11PEBE@Z; NgcIsoContainerImpl::AddTpmPasswordProtector(NgcCtnrProtectorId,unsigned __int64,unsigned __int64,unsigned __int64,uchar const *)
0x1400452a2  mov     ebx, eax
0x1400452a4  test    eax, eax
0x1400452a6  jns     short loc_140045310
0x1400452a8  mov     rcx, [rbp+30h]; this
0x1400452ac  mov     r9d, eax; char *
0x1400452af  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400452b6  mov     edx, 240h; void *
0x1400452bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400452c0  mov     edx, 1E5h
0x1400452c5  jmp     short loc_140045335
0x1400452c7  mov     ecx, [rbp+arg_20]
0x1400452ca  mov     rax, [rbp+arg_28]
0x1400452ce  mov     [rsp+68h+var_40], rax
0x1400452d3  mov     qword ptr [rsp+68h+var_48], rcx; int
0x1400452d8  mov     r9, r15
0x1400452db  mov     r8, r14
0x1400452de  mov     edx, 1
0x1400452e3  mov     rcx, rdi
0x1400452e6  call    ?AddTpmPasswordProtector@NgcIsoContainerImpl@@IEAAJW4NgcCtnrProtectorId@@_K11PEBE@Z; NgcIsoContainerImpl::AddTpmPasswordProtector(NgcCtnrProtectorId,unsigned __int64,unsigned __int64,unsigned __int64,uchar const *)
0x1400452eb  mov     ebx, eax
0x1400452ed  test    eax, eax
0x1400452ef  jns     short loc_140045310
0x1400452f1  mov     rcx, [rbp+30h]; this
0x1400452f5  mov     r9d, eax; char *
0x1400452f8  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400452ff  mov     edx, 21Ch; void *
0x140045304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045309  mov     edx, 1DEh
0x14004530e  jmp     short loc_140045335
0x140045310  lea     rdx, [rbp+var_20]
0x140045314  mov     rcx, [rbp+arg_30]
0x140045318  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14004531d  nop
0x14004531e  lea     rcx, [rbp+var_20]
0x140045322  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140045327  xor     eax, eax
0x140045329  jmp     short loc_140045354
0x14004532b  mov     ebx, 80070057h
0x140045330  mov     edx, 201h; void *
0x140045335  mov     r9d, ebx; char *
0x140045338  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14004533f  mov     rcx, [rbp+30h]; this
0x140045343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045348  nop
0x140045349  lea     rcx, [rbp+var_20]
0x14004534d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140045352  mov     eax, ebx
0x140045354  add     rsp, 68h
0x140045358  pop     r15
0x14004535a  pop     r14
0x14004535c  pop     rdi
0x14004535d  pop     rsi
0x14004535e  pop     rbx
0x14004535f  pop     rbp
0x140045360  retn
```
