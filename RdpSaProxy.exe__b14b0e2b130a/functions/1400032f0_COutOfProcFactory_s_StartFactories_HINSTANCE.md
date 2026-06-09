# COutOfProcFactory::s_StartFactories(HINSTANCE__ *)

- ea: `0x1400032f0`
- end: `0x1400034c1`
- name: `?s_StartFactories@COutOfProcFactory@@SAJPEAUHINSTANCE__@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002944`

## callees

- `0x140001540`
- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x1400032f0`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400033d8`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400033d8`

## pseudocode

```c
__int64 __fastcall COutOfProcFactory::s_StartFactories(HINSTANCE a1)
{
  struct COutOfProcFactoryData near **v1; // rbx
  _DWORD *v2; // rax
  __int64 v3; // rcx
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  IUnknown *v6; // rdi
  HRESULT v7; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  DWORD dwRegister; // [rsp+60h] [rbp+8h] BYREF

  dwRegister = 0;
  v1 = &g_rgFactoryData;
  COutOfProcFactory::s_hInstance = a1;
  while ( 1 )
  {
    v1[7] = 0;
    *((_DWORD *)v1 + 16) = 0;
    v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v3 = (__int64)v2;
    if ( v2 )
    {
      v2[6] = -607474739;
      *((_QWORD *)v2 + 2) = "COutOfProcFactory";
      v2[7] = 1;
      *(_QWORD *)v2 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v2 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
      *(_QWORD *)v2 = &COutOfProcFactory::`vftable'{for `INonDelegatingUnknown'};
      *((_QWORD *)v2 + 1) = &COutOfProcFactory::`vftable'{for `CTSObject'};
      *((_QWORD *)v2 + 6) = &COutOfProcFactory::`vftable';
      v2[10] = 0;
      *((_QWORD *)v2 + 4) = v2;
      *((_QWORD *)v2 + 7) = v1;
    }
    else
    {
      v3 = 0;
    }
    v4 = v3 + 48;
    v5 = -v3;
    v6 = (IUnknown *)(v4 & -(__int64)(v5 != 0));
    if ( !v6 )
      break;
    ((void (__fastcall *)(unsigned __int64))v6->lpVtbl->AddRef)(v4 & -(__int64)(v5 != 0));
    v7 = CoRegisterClassObject((const IID *const)*v1, v6, 4u, 1u, &dwRegister);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CoRegisterClassObject failed!",
          v7);
      }
      ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
      return (unsigned int)v7;
    }
    *((_DWORD *)v1 + 16) = dwRegister;
    v1[7] = (struct COutOfProcFactoryData near *)v6;
    v1 += 9;
    if ( v1 > &g_rgFactoryData )
      return (unsigned int)v7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids, v9, -2147024882);
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1400032f0  push    rbx
0x1400032f2  push    rsi
0x1400032f3  push    rdi
0x1400032f4  push    r14
0x1400032f6  sub     rsp, 38h
0x1400032fa  lea     r14, ?g_rgFactoryData@@3PAVCOutOfProcFactoryData@@A; COutOfProcFactoryData near * g_rgFactoryData
0x140003301  mov     [rsp+58h+dwRegister], 0
0x140003309  mov     rbx, r14
0x14000330c  mov     cs:?s_hInstance@COutOfProcFactory@@2PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * COutOfProcFactory::s_hInstance
0x140003313  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000331a  mov     qword ptr [rbx+38h], 0
0x140003322  mov     ecx, 40h ; '@'; unsigned __int64
0x140003327  mov     dword ptr [rbx+40h], 0
0x14000332e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140003333  mov     rcx, rax
0x140003336  test    rax, rax
0x140003339  jz      short loc_14000339A
0x14000333b  mov     dword ptr [rax+18h], 0DBCAABCDh
0x140003342  lea     rax, aCoutofprocfact; "COutOfProcFactory"
0x140003349  mov     [rcx+10h], rax
0x14000334d  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x140003354  mov     dword ptr [rcx+1Ch], 1
0x14000335b  mov     [rcx], rax
0x14000335e  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x140003365  mov     [rcx+8], rax
0x140003369  lea     rax, ??_7COutOfProcFactory@@6BINonDelegatingUnknown@@@; const COutOfProcFactory::`vftable'{for `INonDelegatingUnknown'}
0x140003370  mov     [rcx], rax
0x140003373  lea     rax, ??_7COutOfProcFactory@@6BCTSObject@@@; const COutOfProcFactory::`vftable'{for `CTSObject'}
0x14000337a  mov     [rcx+8], rax
0x14000337e  lea     rax, ??_7COutOfProcFactory@@6B@; const COutOfProcFactory::`vftable'
0x140003385  mov     [rcx+30h], rax
0x140003389  mov     dword ptr [rcx+28h], 0
0x140003390  mov     [rcx+20h], rcx
0x140003394  mov     [rcx+38h], rbx
0x140003398  jmp     short loc_14000339C
0x14000339a  xor     ecx, ecx
0x14000339c  lea     rax, [rcx+30h]
0x1400033a0  neg     rcx
0x1400033a3  sbb     rdi, rdi
0x1400033a6  and     rdi, rax
0x1400033a9  jz      loc_140003465
0x1400033af  mov     rax, [rdi]
0x1400033b2  mov     rcx, rdi
0x1400033b5  mov     rax, [rax+8]
0x1400033b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033be  mov     rcx, [rbx]; rclsid
0x1400033c1  lea     rax, [rsp+58h+dwRegister]
0x1400033c6  mov     r9d, 1; flags
0x1400033cc  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x1400033d1  mov     rdx, rdi; pUnk
0x1400033d4  lea     r8d, [r9+3]; dwClsContext
0x1400033d8  call    cs:__imp_CoRegisterClassObject
0x1400033de  mov     esi, eax
0x1400033e0  test    eax, eax
0x1400033e2  js      short loc_140003401
0x1400033e4  mov     ecx, [rsp+58h+dwRegister]
0x1400033e8  mov     [rbx+40h], ecx
0x1400033eb  mov     [rbx+38h], rdi
0x1400033ef  add     rbx, 48h ; 'H'
0x1400033f3  cmp     rbx, r14
0x1400033f6  jbe     loc_140003313
0x1400033fc  jmp     loc_1400034B5
0x140003401  mov     rax, cs:WPP_GLOBAL_Control
0x140003408  lea     rcx, WPP_GLOBAL_Control
0x14000340f  cmp     rax, rcx
0x140003412  jz      short loc_140003454
0x140003414  test    byte ptr [rax+1Ch], 8
0x140003418  jz      short loc_140003454
0x14000341a  cmp     byte ptr [rax+19h], 2
0x14000341e  jb      short loc_140003454
0x140003420  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003425  lea     rcx, aCoregisterclas; "CoRegisterClassObject failed!"
0x14000342c  mov     [rsp+58h+var_30], esi
0x140003430  mov     [rsp+58h+lpdwRegister], rcx
0x140003435  lea     r8, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids
0x14000343c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003443  mov     edx, 0Eh
0x140003448  mov     r9d, eax
0x14000344b  mov     rcx, [rcx+10h]
0x14000344f  call    WPP_SF_DsD
0x140003454  mov     rax, [rdi]
0x140003457  mov     rcx, rdi
0x14000345a  mov     rax, [rax+10h]
0x14000345e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003463  jmp     short loc_1400034B5
0x140003465  mov     rax, cs:WPP_GLOBAL_Control
0x14000346c  lea     rcx, WPP_GLOBAL_Control
0x140003473  cmp     rax, rcx
0x140003476  jz      short loc_1400034B0
0x140003478  test    byte ptr [rax+1Ch], 8
0x14000347c  jz      short loc_1400034B0
0x14000347e  cmp     byte ptr [rax+19h], 2
0x140003482  jb      short loc_1400034B0
0x140003484  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003489  mov     rcx, cs:WPP_GLOBAL_Control
0x140003490  lea     r8, WPP_e8c4a0e291a43e32a201fcd03ffdd7b3_Traceguids
0x140003497  mov     edx, 0Dh
0x14000349c  mov     dword ptr [rsp+58h+lpdwRegister], 8007000Eh
0x1400034a4  mov     r9d, eax
0x1400034a7  mov     rcx, [rcx+10h]
0x1400034ab  call    WPP_SF_Dd
0x1400034b0  mov     esi, 8007000Eh
0x1400034b5  mov     eax, esi
0x1400034b7  add     rsp, 38h
0x1400034bb  pop     r14
0x1400034bd  pop     rdi
0x1400034be  pop     rsi
0x1400034bf  pop     rbx
0x1400034c0  retn
```
