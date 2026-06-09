# CheckIsInternetAvailable(ulong,bool *)

- ea: `0x1800471f4`
- end: `0x18004752d`
- name: `?CheckIsInternetAvailable@@YAJKPEA_N@Z`
- size: `825`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180032b74`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001cde8`
- `0x180023c1c`
- `0x180034070`
- `0x180046d08`
- `0x180047104`
- `0x1800471f4`
- `0x18007200c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800473e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800473e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180047504`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180047504`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180047455`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180047455`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CheckIsInternetAvailable(__int64 a1, bool *a2)
{
  PVOID *v3; // rcx
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // edx
  FveEasNetworkStatus *v8; // rsi
  unsigned int CurrentStatus; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  char v13; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[7]; // [rsp+31h] [rbp-37h] BYREF
  FveEasNetworkStatus *v15; // [rsp+38h] [rbp-30h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+48h] [rbp-20h] BYREF

  v15 = 0;
  pHandles = 0;
  dwindex = 0;
  v13 = 0;
  v14[0] = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    v5 = CInitializeCom::Initialize((CInitializeCom *)v14);
    v4 = v5;
    if ( v5 )
    {
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v5);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 < 0 )
        goto LABEL_47;
    }
    v6 = FveEasNetworkStatus::Create(&v15);
    v4 = v6;
    v8 = v15;
    if ( !v6 )
      goto LABEL_18;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v6);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 >= 0 )
    {
LABEL_18:
      CurrentStatus = FveEasNetworkStatusImpl::GetCurrentStatus(*(_QWORD *)v8 + 8LL, &v13);
      v4 = CurrentStatus;
      if ( CurrentStatus )
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
            CurrentStatus);
          v3 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v4 < 0 )
          goto LABEL_44;
      }
      else
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
      {
        *a2 = 1;
        v3 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_44;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      }
      else
      {
        if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
          WPP_SF_(v3[2], 30, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
        pHandles = CreateEventW(0, 0, 0, 0);
        v15 = (FveEasNetworkStatus *)pHandles;
        v10 = FveEasNetworkStatus::RegisterForStatusChange__lambda_77f80eac8da8f876157974a3c3d088c5___(v8, &v15);
        v4 = v10;
        if ( v10 )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v10);
            v3 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v4 < 0 )
            goto LABEL_44;
        }
        v11 = CoWaitForMultipleHandles(0, 0xEA60u, 1u, &pHandles, &dwindex);
        v4 = v11;
        if ( v11 )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v11);
            v3 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v4 < 0 )
            goto LABEL_44;
        }
        *a2 = 1;
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_44:
    if ( !v8 )
      goto LABEL_47;
    FveEasNetworkStatus::`scalar deleting destructor'(v8, v7);
    goto LABEL_46;
  }
  v4 = -2147467261;
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 )
  {
    WPP_SF_d(v3[2], 25, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, 2147500035LL);
LABEL_46:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_d(v3[2], 33, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v4);
  if ( v14[0] )
    CoUninitialize();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800471f4  push    rbp
0x1800471f6  push    rbx
0x1800471f7  push    rsi
0x1800471f8  push    r12
0x1800471fa  push    r13
0x1800471fc  push    r14
0x1800471fe  mov     rbp, rsp
0x180047201  sub     rsp, 68h
0x180047205  mov     rax, cs:__security_cookie
0x18004720c  xor     rax, rsp
0x18004720f  mov     [rbp+var_18], rax
0x180047213  mov     r14, rdx
0x180047216  mov     [rbp+var_30], 0
0x18004721e  mov     [rbp+pHandles], 0
0x180047226  mov     [rbp+dwindex], 0
0x18004722d  mov     [rbp+var_38], 0
0x180047231  mov     [rbp+var_37], 0
0x180047235  lea     r12, WPP_GLOBAL_Control
0x18004723c  lea     r13, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047243  mov     rcx, cs:WPP_GLOBAL_Control
0x18004724a  cmp     rcx, r12
0x18004724d  jz      short loc_18004726D
0x18004724f  test    byte ptr [rcx+1Ch], 20h
0x180047253  jz      short loc_18004726D
0x180047255  mov     edx, 18h
0x18004725a  mov     r8, r13
0x18004725d  mov     rcx, [rcx+10h]
0x180047261  call    WPP_SF_
0x180047266  mov     rcx, cs:WPP_GLOBAL_Control
0x18004726d  test    r14, r14
0x180047270  jnz     short loc_1800472A2
0x180047272  mov     ebx, 80004003h
0x180047277  cmp     rcx, r12
0x18004727a  jz      loc_1800474B7
0x180047280  test    byte ptr [rcx+1Ch], 40h
0x180047284  jz      loc_1800474B7
0x18004728a  lea     edx, [r14+19h]
0x18004728e  mov     r9d, ebx
0x180047291  mov     r8, r13
0x180047294  mov     rcx, [rcx+10h]
0x180047298  call    WPP_SF_d
0x18004729d  jmp     loc_1800474B0
0x1800472a2  mov     byte ptr [r14], 0
0x1800472a6  lea     rcx, [rbp+var_37]; this
0x1800472aa  call    ?Initialize@CInitializeCom@@QEAAJXZ; CInitializeCom::Initialize(void)
0x1800472af  mov     ebx, eax
0x1800472b1  test    eax, eax
0x1800472b3  jz      short loc_1800472EA
0x1800472b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472bc  cmp     rcx, r12
0x1800472bf  jz      short loc_1800472E2
0x1800472c1  test    byte ptr [rcx+1Ch], 40h
0x1800472c5  jz      short loc_1800472E2
0x1800472c7  mov     edx, 1Ah
0x1800472cc  mov     r9d, eax
0x1800472cf  mov     r8, r13
0x1800472d2  mov     rcx, [rcx+10h]
0x1800472d6  call    WPP_SF_d
0x1800472db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472e2  test    ebx, ebx
0x1800472e4  js      loc_1800474B7
0x1800472ea  lea     rcx, [rbp+var_30]; struct FveEasNetworkStatus **
0x1800472ee  call    ?Create@FveEasNetworkStatus@@SAJPEAPEAV1@@Z; FveEasNetworkStatus::Create(FveEasNetworkStatus * *)
0x1800472f3  mov     ebx, eax
0x1800472f5  mov     rsi, [rbp+var_30]
0x1800472f9  test    eax, eax
0x1800472fb  jz      short loc_180047332
0x1800472fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180047304  cmp     rcx, r12
0x180047307  jz      short loc_18004732A
0x180047309  test    byte ptr [rcx+1Ch], 40h
0x18004730d  jz      short loc_18004732A
0x18004730f  mov     edx, 1Bh
0x180047314  mov     r9d, eax
0x180047317  mov     r8, r13
0x18004731a  mov     rcx, [rcx+10h]
0x18004731e  call    WPP_SF_d
0x180047323  mov     rcx, cs:WPP_GLOBAL_Control
0x18004732a  test    ebx, ebx
0x18004732c  js      loc_1800474A3
0x180047332  mov     rcx, [rsi]
0x180047335  add     rcx, 8
0x180047339  lea     rdx, [rbp+var_38]
0x18004733d  call    ?GetCurrentStatus@FveEasNetworkStatusImpl@@SAJAEBV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@AEAUFveEasNetworkStatusArgs@@@Z; FveEasNetworkStatusImpl::GetCurrentStatus(Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> const &,FveEasNetworkStatusArgs &)
0x180047342  mov     ebx, eax
0x180047344  test    eax, eax
0x180047346  jz      short loc_18004737F
0x180047348  mov     rcx, cs:WPP_GLOBAL_Control
0x18004734f  cmp     rcx, r12
0x180047352  jz      short loc_180047375
0x180047354  test    byte ptr [rcx+1Ch], 40h
0x180047358  jz      short loc_180047375
0x18004735a  mov     edx, 1Ch
0x18004735f  mov     r9d, eax
0x180047362  mov     r8, r13
0x180047365  mov     rcx, [rcx+10h]
0x180047369  call    WPP_SF_d
0x18004736e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047375  test    ebx, ebx
0x180047377  js      loc_1800474A3
0x18004737d  jmp     short loc_180047386
0x18004737f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047386  cmp     [rbp+var_38], 0
0x18004738a  jz      short loc_1800473C0
0x18004738c  mov     byte ptr [r14], 1
0x180047390  mov     rcx, cs:WPP_GLOBAL_Control
0x180047397  cmp     rcx, r12
0x18004739a  jz      loc_1800474A3
0x1800473a0  test    byte ptr [rcx+1Ch], 8
0x1800473a4  jz      loc_1800474A3
0x1800473aa  mov     edx, 1Dh
0x1800473af  mov     r8, r13
0x1800473b2  mov     rcx, [rcx+10h]
0x1800473b6  call    WPP_SF_
0x1800473bb  jmp     loc_18004749C
0x1800473c0  cmp     rcx, r12
0x1800473c3  jz      short loc_1800473DC
0x1800473c5  test    byte ptr [rcx+1Ch], 8
0x1800473c9  jz      short loc_1800473DC
0x1800473cb  mov     edx, 1Eh
0x1800473d0  mov     r8, r13
0x1800473d3  mov     rcx, [rcx+10h]
0x1800473d7  call    WPP_SF_
0x1800473dc  xor     r9d, r9d; lpName
0x1800473df  xor     r8d, r8d; bInitialState
0x1800473e2  xor     edx, edx; bManualReset
0x1800473e4  xor     ecx, ecx; lpEventAttributes
0x1800473e6  call    cs:__imp_CreateEventW
0x1800473ed  nop     dword ptr [rax+rax+00h]
0x1800473f2  mov     [rbp+pHandles], rax
0x1800473f6  mov     [rbp+var_30], rax
0x1800473fa  lea     rdx, [rbp+var_30]
0x1800473fe  mov     rcx, rsi
0x180047401  call    FveEasNetworkStatus__RegisterForStatusChange__lambda_77f80eac8da8f876157974a3c3d088c5___
0x180047406  mov     ebx, eax
0x180047408  test    eax, eax
0x18004740a  jz      short loc_18004743D
0x18004740c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047413  cmp     rcx, r12
0x180047416  jz      short loc_180047439
0x180047418  test    byte ptr [rcx+1Ch], 40h
0x18004741c  jz      short loc_180047439
0x18004741e  mov     edx, 1Fh
0x180047423  mov     r9d, eax
0x180047426  mov     r8, r13
0x180047429  mov     rcx, [rcx+10h]
0x18004742d  call    WPP_SF_d
0x180047432  mov     rcx, cs:WPP_GLOBAL_Control
0x180047439  test    ebx, ebx
0x18004743b  js      short loc_1800474A3
0x18004743d  lea     rax, [rbp+dwindex]
0x180047441  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180047446  lea     r9, [rbp+pHandles]; pHandles
0x18004744a  mov     edx, 0EA60h; dwTimeout
0x18004744f  xor     ecx, ecx; dwFlags
0x180047451  lea     r8d, [rcx+1]; cHandles
0x180047455  call    cs:__imp_CoWaitForMultipleHandles
0x18004745c  nop     dword ptr [rax+rax+00h]
0x180047461  mov     ebx, eax
0x180047463  test    eax, eax
0x180047465  jz      short loc_180047498
0x180047467  mov     rcx, cs:WPP_GLOBAL_Control
0x18004746e  cmp     rcx, r12
0x180047471  jz      short loc_180047494
0x180047473  test    byte ptr [rcx+1Ch], 40h
0x180047477  jz      short loc_180047494
0x180047479  mov     edx, 20h ; ' '
0x18004747e  mov     r9d, eax
0x180047481  mov     r8, r13
0x180047484  mov     rcx, [rcx+10h]
0x180047488  call    WPP_SF_d
0x18004748d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047494  test    ebx, ebx
0x180047496  js      short loc_1800474A3
0x180047498  mov     byte ptr [r14], 1
0x18004749c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474a3  test    rsi, rsi
0x1800474a6  jz      short loc_1800474B7
0x1800474a8  mov     rcx, rsi; this
0x1800474ab  call    ??_GFveEasNetworkStatus@@QEAAPEAXI@Z; FveEasNetworkStatus::`scalar deleting destructor'(uint)
0x1800474b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474b7  mov     rax, [rbp+pHandles]
0x1800474bb  test    rax, rax
0x1800474be  jz      short loc_1800474DE
0x1800474c0  mov     rcx, rax; hObject
0x1800474c3  call    cs:__imp_CloseHandle
0x1800474ca  nop     dword ptr [rax+rax+00h]
0x1800474cf  mov     [rbp+pHandles], 0
0x1800474d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474de  cmp     rcx, r12
0x1800474e1  jz      short loc_1800474FE
0x1800474e3  test    byte ptr [rcx+1Ch], 20h
0x1800474e7  jz      short loc_1800474FE
0x1800474e9  mov     edx, 21h ; '!'
0x1800474ee  mov     r9d, ebx
0x1800474f1  mov     r8, r13
0x1800474f4  mov     rcx, [rcx+10h]
0x1800474f8  call    WPP_SF_d
0x1800474fd  nop
0x1800474fe  cmp     [rbp+var_37], 0
0x180047502  jz      short loc_180047510
0x180047504  call    cs:__imp_CoUninitialize
0x18004750b  nop     dword ptr [rax+rax+00h]
0x180047510  mov     eax, ebx
0x180047512  mov     rcx, [rbp+var_18]
0x180047516  xor     rcx, rsp; StackCookie
0x180047519  call    __security_check_cookie
0x18004751e  add     rsp, 68h
0x180047522  pop     r14
0x180047524  pop     r13
0x180047526  pop     r12
0x180047528  pop     rsi
0x180047529  pop     rbx
0x18004752a  pop     rbp
0x18004752b  retn
```
