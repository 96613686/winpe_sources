# CNetworkHandler::Start(void)

- ea: `0x18000c218`
- end: `0x18000c55c`
- name: `?Start@CNetworkHandler@@QEAAJXZ`
- size: `836`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x180001e6c`
- `0x1800030b0`
- `0x18000a644`
- `0x18000a778`
- `0x18000c218`
- `0x18000cfa4`
- `0x18001380e`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c304`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c304`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c4be`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c4be`
- `WS2_32!__imp_WSAStartup` at `0x18000c2c0`
- `WS2_32!__imp_WSAStartup` at `0x18000c2c0`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::Start(CNetworkHandler *this)
{
  CDeviceHandler *v2; // rax
  HRESULT Events; // ebx
  char *v4; // rsi
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v6)(CNetworkHandler *, GUID *, __int64 *); // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v10; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v11; // [rsp+38h] [rbp-1D0h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1C8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  memset_0(&WSAData, 0, sizeof(WSAData));
  v2 = (CDeviceHandler *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v2 = CDeviceHandler::CDeviceHandler(v2, 1);
  *((_QWORD *)this + 6) = v2;
  if ( v2 )
  {
    if ( !WSAStartup(0x202u, &WSAData) )
    {
      *((_DWORD *)this + 3) = 1;
      Events = CNetworkHandler::_CreateEvents(this);
      if ( Events < 0 )
        goto LABEL_44;
      v4 = (char *)this + 24;
      Events = CoCreateInstance(
                 &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
                 0,
                 1u,
                 &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
                 (LPVOID *)this + 3);
      if ( Events < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
        goto LABEL_44;
      }
      v5 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v4;
      v11 = 0;
      Events = (**v5)(v5, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &v11);
      if ( Events < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_33;
        v8 = 41;
      }
      else
      {
        v4 = (char *)this + 32;
        Events = (*(__int64 (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v11 + 32LL))(
                   v11,
                   &GUID_dcb00004_570f_4a9b_8d69_199fdba5723b,
                   (char *)this + 32);
        if ( Events >= 0 )
        {
          v6 = *(__int64 (__fastcall ***)(CNetworkHandler *, GUID *, __int64 *))this;
          v10 = 0;
          Events = (*v6)(this, &GUID_00000000_0000_0000_c000_000000000046, &v10);
          if ( Events >= 0 )
          {
            Events = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**(_QWORD **)v4 + 40LL))(
                       *(_QWORD *)v4,
                       v10,
                       (char *)this + 16);
            if ( Events < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
              }
              *((_DWORD *)this + 4) = 0;
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
            }
          }
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          goto LABEL_34;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_33:
          *(_QWORD *)v4 = 0;
LABEL_34:
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          goto LABEL_44;
        }
        v8 = 40;
      }
      WPP_SF_d(v7[2], v8, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
      goto LABEL_33;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WSAGetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    }
    Events = -2147467259;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    Events = -2147024882;
  }
LABEL_44:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return (unsigned int)Events;
}

```

## disassembly

```asm
0x18000c218  mov     [rsp+arg_8], rbx
0x18000c21d  mov     [rsp+arg_10], rsi
0x18000c222  push    rdi
0x18000c223  push    r14
0x18000c225  push    r15
0x18000c227  sub     rsp, 1F0h
0x18000c22e  mov     rax, cs:__security_cookie
0x18000c235  xor     rax, rsp
0x18000c238  mov     [rsp+208h+var_28], rax
0x18000c240  mov     rdi, rcx
0x18000c243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c24a  lea     r14, WPP_GLOBAL_Control
0x18000c251  lea     r15, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000c258  cmp     rcx, r14
0x18000c25b  jz      short loc_18000C274
0x18000c25d  test    byte ptr [rcx+1Ch], 20h
0x18000c261  jz      short loc_18000C274
0x18000c263  mov     rcx, [rcx+10h]
0x18000c267  mov     edx, 24h ; '$'
0x18000c26c  mov     r8, r15
0x18000c26f  call    WPP_SF_
0x18000c274  xor     edx, edx; Val
0x18000c276  lea     rcx, [rsp+208h+WSAData]; void *
0x18000c27b  mov     r8d, 198h; Size
0x18000c281  call    memset_0
0x18000c286  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c28d  mov     ecx, 38h ; '8'; unsigned __int64
0x18000c292  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c297  test    rax, rax
0x18000c29a  jz      short loc_18000C2A9
0x18000c29c  mov     edx, 1; int
0x18000c2a1  mov     rcx, rax; this
0x18000c2a4  call    ??0CDeviceHandler@@QEAA@H@Z; CDeviceHandler::CDeviceHandler(int)
0x18000c2a9  mov     [rdi+30h], rax
0x18000c2ad  test    rax, rax
0x18000c2b0  jz      loc_18000C4E6
0x18000c2b6  mov     ecx, 202h; wVersionRequested
0x18000c2bb  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x18000c2c0  call    cs:__imp_WSAStartup
0x18000c2c6  test    eax, eax
0x18000c2c8  jnz     loc_18000C4AC
0x18000c2ce  mov     rcx, rdi; this
0x18000c2d1  mov     dword ptr [rdi+0Ch], 1
0x18000c2d8  call    ?_CreateEvents@CNetworkHandler@@AEAAJXZ; CNetworkHandler::_CreateEvents(void)
0x18000c2dd  mov     ebx, eax
0x18000c2df  test    eax, eax
0x18000c2e1  js      loc_18000C50E
0x18000c2e7  xor     edx, edx; pUnkOuter
0x18000c2e9  lea     rsi, [rdi+18h]
0x18000c2ed  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18000c2f4  mov     [rsp+208h+ppv], rsi; ppv
0x18000c2f9  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x18000c300  lea     r8d, [rdx+1]; dwClsContext
0x18000c304  call    cs:__imp_CoCreateInstance
0x18000c30a  mov     ebx, eax
0x18000c30c  test    eax, eax
0x18000c30e  jns     short loc_18000C343
0x18000c310  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c317  cmp     rcx, r14
0x18000c31a  jz      loc_18000C50E
0x18000c320  test    byte ptr [rcx+1Ch], 2
0x18000c324  jz      loc_18000C50E
0x18000c32a  mov     rcx, [rcx+10h]
0x18000c32e  mov     edx, 25h ; '%'
0x18000c333  mov     r9d, eax
0x18000c336  mov     r8, r15
0x18000c339  call    WPP_SF_d
0x18000c33e  jmp     loc_18000C50E
0x18000c343  mov     rcx, [rsi]
0x18000c346  lea     r8, [rsp+208h+var_1D0]
0x18000c34b  mov     [rsp+208h+var_1D0], 0
0x18000c354  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18000c35b  mov     rax, [rcx]
0x18000c35e  mov     rax, [rax]
0x18000c361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c366  mov     ebx, eax
0x18000c368  test    eax, eax
0x18000c36a  js      loc_18000C467
0x18000c370  mov     rcx, [rsp+208h+var_1D0]
0x18000c375  lea     rsi, [rdi+20h]
0x18000c379  mov     r8, rsi
0x18000c37c  lea     rdx, _GUID_dcb00004_570f_4a9b_8d69_199fdba5723b
0x18000c383  mov     rax, [rcx]
0x18000c386  mov     rax, [rax+20h]
0x18000c38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c38f  mov     ebx, eax
0x18000c391  test    eax, eax
0x18000c393  js      loc_18000C44E
0x18000c399  mov     rax, [rdi]
0x18000c39c  lea     r8, [rsp+208h+var_1D8]
0x18000c3a1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c3a8  mov     [rsp+208h+var_1D8], 0
0x18000c3b1  mov     rcx, rdi
0x18000c3b4  mov     rax, [rax]
0x18000c3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3bc  mov     ebx, eax
0x18000c3be  test    eax, eax
0x18000c3c0  js      short loc_18000C436
0x18000c3c2  mov     rcx, [rsi]
0x18000c3c5  lea     r8, [rdi+10h]
0x18000c3c9  mov     rdx, [rsp+208h+var_1D8]
0x18000c3ce  mov     rax, [rcx]
0x18000c3d1  mov     rax, [rax+28h]
0x18000c3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3da  mov     ebx, eax
0x18000c3dc  test    eax, eax
0x18000c3de  js      short loc_18000C409
0x18000c3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3e7  cmp     rcx, r14
0x18000c3ea  jz      short loc_18000C436
0x18000c3ec  test    byte ptr [rcx+1Ch], 8
0x18000c3f0  jz      short loc_18000C436
0x18000c3f2  mov     r9d, [rdi+10h]
0x18000c3f6  mov     edx, 26h ; '&'
0x18000c3fb  mov     rcx, [rcx+10h]
0x18000c3ff  mov     r8, r15
0x18000c402  call    WPP_SF_d
0x18000c407  jmp     short loc_18000C436
0x18000c409  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c410  cmp     rcx, r14
0x18000c413  jz      short loc_18000C42F
0x18000c415  test    byte ptr [rcx+1Ch], 2
0x18000c419  jz      short loc_18000C42F
0x18000c41b  mov     rcx, [rcx+10h]
0x18000c41f  mov     edx, 27h ; '''
0x18000c424  mov     r9d, eax
0x18000c427  mov     r8, r15
0x18000c42a  call    WPP_SF_d
0x18000c42f  mov     dword ptr [rdi+10h], 0
0x18000c436  mov     rcx, [rsp+208h+var_1D8]
0x18000c43b  test    rcx, rcx
0x18000c43e  jz      short loc_18000C494
0x18000c440  mov     rax, [rcx]
0x18000c443  mov     rax, [rax+10h]
0x18000c447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44c  jmp     short loc_18000C494
0x18000c44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c455  cmp     rcx, r14
0x18000c458  jz      short loc_18000C48D
0x18000c45a  test    byte ptr [rcx+1Ch], 2
0x18000c45e  jz      short loc_18000C48D
0x18000c460  mov     edx, 28h ; '('
0x18000c465  jmp     short loc_18000C47E
0x18000c467  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c46e  cmp     rcx, r14
0x18000c471  jz      short loc_18000C48D
0x18000c473  test    byte ptr [rcx+1Ch], 2
0x18000c477  jz      short loc_18000C48D
0x18000c479  mov     edx, 29h ; ')'
0x18000c47e  mov     rcx, [rcx+10h]
0x18000c482  mov     r9d, eax
0x18000c485  mov     r8, r15
0x18000c488  call    WPP_SF_d
0x18000c48d  mov     qword ptr [rsi], 0
0x18000c494  mov     rcx, [rsp+208h+var_1D0]
0x18000c499  test    rcx, rcx
0x18000c49c  jz      short loc_18000C50E
0x18000c49e  mov     rax, [rcx]
0x18000c4a1  mov     rax, [rax+10h]
0x18000c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4aa  jmp     short loc_18000C50E
0x18000c4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b3  cmp     rcx, r14
0x18000c4b6  jz      short loc_18000C4DF
0x18000c4b8  test    byte ptr [rcx+1Ch], 2
0x18000c4bc  jz      short loc_18000C4DF
0x18000c4be  call    cs:__imp_WSAGetLastError
0x18000c4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4cb  mov     edx, 2Ah ; '*'
0x18000c4d0  mov     r9d, eax
0x18000c4d3  mov     r8, r15
0x18000c4d6  mov     rcx, [rcx+10h]
0x18000c4da  call    WPP_SF_d
0x18000c4df  mov     ebx, 80004005h
0x18000c4e4  jmp     short loc_18000C50E
0x18000c4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4ed  cmp     rcx, r14
0x18000c4f0  jz      short loc_18000C509
0x18000c4f2  test    byte ptr [rcx+1Ch], 2
0x18000c4f6  jz      short loc_18000C509
0x18000c4f8  mov     rcx, [rcx+10h]
0x18000c4fc  mov     edx, 2Bh ; '+'
0x18000c501  mov     r8, r15
0x18000c504  call    WPP_SF_
0x18000c509  mov     ebx, 8007000Eh
0x18000c50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c515  cmp     rcx, r14
0x18000c518  jz      short loc_18000C531
0x18000c51a  test    byte ptr [rcx+1Ch], 20h
0x18000c51e  jz      short loc_18000C531
0x18000c520  mov     rcx, [rcx+10h]
0x18000c524  mov     edx, 2Ch ; ','
0x18000c529  mov     r8, r15
0x18000c52c  call    WPP_SF_
0x18000c531  mov     eax, ebx
0x18000c533  mov     rcx, [rsp+208h+var_28]
0x18000c53b  xor     rcx, rsp; StackCookie
0x18000c53e  call    __security_check_cookie
0x18000c543  lea     r11, [rsp+208h+var_18]
0x18000c54b  mov     rbx, [r11+28h]
0x18000c54f  mov     rsi, [r11+30h]
0x18000c553  mov     rsp, r11
0x18000c556  pop     r15
0x18000c558  pop     r14
0x18000c55a  pop     rdi
0x18000c55b  retn
```
