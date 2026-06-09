# FwSafearrayToLuids(tagVARIANT,_tag_FW_INTERFACE_LUIDS *)

- ea: `0x1800324fc`
- end: `0x180032837`
- name: `?FwSafearrayToLuids@@YAJUtagVARIANT@@PEAU_tag_FW_INTERFACE_LUIDS@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct _tag_FW_INTERFACE_LUIDS *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800287f0`
- `0x180041d30`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x180031a00`
- `0x180031b3c`
- `0x1800324fc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003262e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003262e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800325e2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800325e2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003267f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003267f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003279f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003279f`
- `fwbase!FwBaseFree` at `0x1800327e4`
- `fwbase!FwBaseFree` at `0x1800327ff`
- `fwbase!FwBaseFree` at `0x1800327e4`
- `fwbase!FwBaseFree` at `0x1800327ff`
- `fwbase!FwArrayAppend` at `0x180032742`
- `fwbase!FwArrayAppend` at `0x180032742`
- `FWPolicyIOMgr!FwCopyLUID` at `0x18003272f`

## pseudocode

```c
__int64 __fastcall FwSafearrayToLuids(struct tagVARIANT *a1, struct _tag_FW_INTERFACE_LUIDS *a2)
{
  int Adapters; // ebx
  __int64 v4; // r9
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  SAFEARRAY *parray; // r14
  HRESULT LBound; // eax
  FwPolicy2 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  LONG i; // r15d
  int v13; // eax
  HRESULT v14; // eax
  struct _IP_ADAPTER_ADDRESSES_LH *v16; // [rsp+20h] [rbp-30h] BYREF
  void *ppvData; // [rsp+28h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+30h] [rbp-20h] BYREF
  LONG plUbound; // [rsp+34h] [rbp-1Ch] BYREF
  struct _GUID v20; // [rsp+38h] [rbp-18h] BYREF

  v16 = 0;
  v20 = GUID_NULL;
  plLbound = 0;
  plUbound = 0;
  ppvData = 0;
  *(_OWORD *)a2 = 0;
  if ( !a1->vt )
    return 0;
  if ( a1->vt != 8204 )
  {
    v4 = 2147942487LL;
    Adapters = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 37;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v4);
LABEL_50:
    if ( *((_QWORD *)a2 + 1) )
      FwBaseFree(a2);
    *(_OWORD *)a2 = 0;
    return (unsigned int)Adapters;
  }
  parray = a1->parray;
  if ( !parray )
  {
    v4 = 2147942487LL;
    Adapters = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 38;
    goto LABEL_7;
  }
  LBound = SafeArrayGetLBound(a1->parray, 1u, &plLbound);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 39;
    goto LABEL_16;
  }
  LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 40;
    goto LABEL_16;
  }
  if ( plUbound - plLbound + 1 <= 0 )
    return 0;
  LBound = SafeArrayAccessData(parray, &ppvData);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 41;
LABEL_16:
    v4 = (unsigned int)LBound;
    goto LABEL_7;
  }
  Adapters = FwGetAdapters(&v16);
  if ( Adapters >= 0 )
  {
    for ( i = plLbound; ; ++i )
    {
      if ( i > plUbound )
        goto LABEL_43;
      v13 = FwInterfaceNameToLuid(v16, *((unsigned __int16 *const *)ppvData + 3 * i + 1), &v20);
      Adapters = v13;
      if ( v13 < 0 )
        break;
      v13 = FwArrayAppend(16, FwCopyLUID, a2, &v20);
      Adapters = v13;
      if ( v13 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 44;
LABEL_41:
          v11 = (unsigned int)v13;
          goto LABEL_42;
        }
        goto LABEL_43;
      }
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 43;
      goto LABEL_41;
    }
  }
  else
  {
    Adapters = -2147418113;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 42;
      v11 = 2147549183LL;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v11);
    }
  }
LABEL_43:
  v14 = SafeArrayUnaccessData(parray);
  if ( v14 < 0
    && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids,
      (unsigned int)v14);
  }
  if ( v16 )
    FwBaseFree(v16);
  if ( Adapters < 0 )
    goto LABEL_50;
  return (unsigned int)Adapters;
}

```

## disassembly

```asm
0x1800324fc  mov     [rsp-28h+arg_10], rbx
0x180032501  push    rbp
0x180032502  push    rsi
0x180032503  push    r12
0x180032505  push    r14
0x180032507  push    r15
0x180032509  mov     rbp, rsp
0x18003250c  sub     rsp, 50h
0x180032510  mov     rax, cs:__security_cookie
0x180032517  xor     rax, rsp
0x18003251a  mov     [rbp+var_8], rax
0x18003251e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032525  xor     esi, esi
0x180032527  mov     r12, rdx
0x18003252a  xorps   xmm1, xmm1
0x18003252d  mov     [rbp+var_30], rsi
0x180032531  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180032536  mov     [rbp+plLbound], esi
0x180032539  mov     [rbp+plUbound], esi
0x18003253c  mov     [rbp+ppvData], rsi
0x180032540  movups  xmmword ptr [rdx], xmm1
0x180032543  cmp     [rcx], si
0x180032546  jnz     short loc_18003254F
0x180032548  mov     ebx, esi
0x18003254a  jmp     loc_180032813
0x18003254f  mov     eax, 200Ch
0x180032554  cmp     [rcx], ax
0x180032557  jz      short loc_18003259D
0x180032559  mov     r9d, 80070057h
0x18003255f  mov     ebx, r9d
0x180032562  mov     rcx, cs:WPP_GLOBAL_Control
0x180032569  lea     rsi, WPP_GLOBAL_Control
0x180032570  cmp     rcx, rsi
0x180032573  jz      loc_1800327F4
0x180032579  test    byte ptr [rcx+1Ch], 1
0x18003257d  jz      loc_1800327F4
0x180032583  mov     edx, 25h ; '%'
0x180032588  mov     rcx, [rcx+10h]
0x18003258c  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180032593  call    WPP_SF_d
0x180032598  jmp     loc_1800327F4
0x18003259d  mov     r14, [rcx+8]
0x1800325a1  test    r14, r14
0x1800325a4  jnz     short loc_1800325D6
0x1800325a6  mov     r9d, 80070057h
0x1800325ac  mov     ebx, r9d
0x1800325af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325b6  lea     rsi, WPP_GLOBAL_Control
0x1800325bd  cmp     rcx, rsi
0x1800325c0  jz      loc_1800327F4
0x1800325c6  test    byte ptr [rcx+1Ch], 1
0x1800325ca  jz      loc_1800327F4
0x1800325d0  lea     edx, [r14+26h]
0x1800325d4  jmp     short loc_180032588
0x1800325d6  lea     r8, [rbp+plLbound]; plLbound
0x1800325da  mov     edx, 1; nDim
0x1800325df  mov     rcx, r14; psa
0x1800325e2  call    cs:__imp_SafeArrayGetLBound
0x1800325e9  nop     dword ptr [rax+rax+00h]
0x1800325ee  mov     ebx, eax
0x1800325f0  test    eax, eax
0x1800325f2  jns     short loc_180032622
0x1800325f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325fb  lea     rsi, WPP_GLOBAL_Control
0x180032602  cmp     rcx, rsi
0x180032605  jz      loc_1800327F4
0x18003260b  test    byte ptr [rcx+1Ch], 1
0x18003260f  jz      loc_1800327F4
0x180032615  mov     edx, 27h ; '''
0x18003261a  mov     r9d, eax
0x18003261d  jmp     loc_180032588
0x180032622  lea     r8, [rbp+plUbound]; plUbound
0x180032626  mov     edx, 1; nDim
0x18003262b  mov     rcx, r14; psa
0x18003262e  call    cs:__imp_SafeArrayGetUBound
0x180032635  nop     dword ptr [rax+rax+00h]
0x18003263a  mov     ebx, eax
0x18003263c  test    eax, eax
0x18003263e  jns     short loc_180032668
0x180032640  mov     rcx, cs:WPP_GLOBAL_Control
0x180032647  lea     rsi, WPP_GLOBAL_Control
0x18003264e  cmp     rcx, rsi
0x180032651  jz      loc_1800327F4
0x180032657  test    byte ptr [rcx+1Ch], 1
0x18003265b  jz      loc_1800327F4
0x180032661  mov     edx, 28h ; '('
0x180032666  jmp     short loc_18003261A
0x180032668  mov     eax, [rbp+plUbound]
0x18003266b  sub     eax, [rbp+plLbound]
0x18003266e  inc     eax
0x180032670  test    eax, eax
0x180032672  jle     loc_180032548
0x180032678  lea     rdx, [rbp+ppvData]; ppvData
0x18003267c  mov     rcx, r14; psa
0x18003267f  call    cs:__imp_SafeArrayAccessData
0x180032686  nop     dword ptr [rax+rax+00h]
0x18003268b  mov     ebx, eax
0x18003268d  test    eax, eax
0x18003268f  jns     short loc_1800326BC
0x180032691  mov     rcx, cs:WPP_GLOBAL_Control
0x180032698  lea     rsi, WPP_GLOBAL_Control
0x18003269f  cmp     rcx, rsi
0x1800326a2  jz      loc_1800327F4
0x1800326a8  test    byte ptr [rcx+1Ch], 1
0x1800326ac  jz      loc_1800327F4
0x1800326b2  mov     edx, 29h ; ')'
0x1800326b7  jmp     loc_18003261A
0x1800326bc  lea     rcx, [rbp+var_30]; struct _IP_ADAPTER_ADDRESSES_LH **
0x1800326c0  call    ?FwGetAdapters@@YAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; FwGetAdapters(_IP_ADAPTER_ADDRESSES_LH * *)
0x1800326c5  lea     rsi, WPP_GLOBAL_Control
0x1800326cc  mov     ebx, eax
0x1800326ce  test    eax, eax
0x1800326d0  jns     short loc_1800326FE
0x1800326d2  mov     ebx, 8000FFFFh
0x1800326d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326de  cmp     rcx, rsi
0x1800326e1  jz      loc_18003279C
0x1800326e7  test    byte ptr [rcx+1Ch], 1
0x1800326eb  jz      loc_18003279C
0x1800326f1  mov     edx, 2Ah ; '*'
0x1800326f6  mov     r9d, ebx
0x1800326f9  jmp     loc_18003278C
0x1800326fe  mov     r15d, [rbp+plLbound]
0x180032702  cmp     r15d, [rbp+plUbound]
0x180032706  jg      loc_18003279C
0x18003270c  mov     rdx, [rbp+ppvData]
0x180032710  lea     r8, [rbp+var_18]; struct _GUID *
0x180032714  movsxd  rax, r15d
0x180032717  lea     rcx, [rax+rax*2]
0x18003271b  mov     rdx, [rdx+rcx*8+8]; unsigned __int16 *
0x180032720  mov     rcx, [rbp+var_30]; struct _IP_ADAPTER_ADDRESSES_LH *
0x180032724  call    ?FwInterfaceNameToLuid@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@QEAGPEAU_GUID@@@Z; FwInterfaceNameToLuid(_IP_ADAPTER_ADDRESSES_LH *,ushort * const,_GUID *)
0x180032729  mov     ebx, eax
0x18003272b  test    eax, eax
0x18003272d  js      short loc_180032772
0x18003272f  mov     rdx, cs:__imp_FwCopyLUID
0x180032736  lea     r9, [rbp+var_18]
0x18003273a  mov     r8, r12
0x18003273d  mov     ecx, 10h
0x180032742  call    cs:__imp_FwArrayAppend
0x180032749  nop     dword ptr [rax+rax+00h]
0x18003274e  mov     ebx, eax
0x180032750  test    eax, eax
0x180032752  js      short loc_180032759
0x180032754  inc     r15d
0x180032757  jmp     short loc_180032702
0x180032759  mov     rcx, cs:WPP_GLOBAL_Control
0x180032760  cmp     rcx, rsi
0x180032763  jz      short loc_18003279C
0x180032765  test    byte ptr [rcx+1Ch], 1
0x180032769  jz      short loc_18003279C
0x18003276b  mov     edx, 2Ch ; ','
0x180032770  jmp     short loc_180032789
0x180032772  mov     rcx, cs:WPP_GLOBAL_Control
0x180032779  cmp     rcx, rsi
0x18003277c  jz      short loc_18003279C
0x18003277e  test    byte ptr [rcx+1Ch], 1
0x180032782  jz      short loc_18003279C
0x180032784  mov     edx, 2Bh ; '+'
0x180032789  mov     r9d, eax
0x18003278c  mov     rcx, [rcx+10h]
0x180032790  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180032797  call    WPP_SF_d
0x18003279c  mov     rcx, r14; psa
0x18003279f  call    cs:__imp_SafeArrayUnaccessData
0x1800327a6  nop     dword ptr [rax+rax+00h]
0x1800327ab  test    eax, eax
0x1800327ad  jns     short loc_1800327D9
0x1800327af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327b6  cmp     rcx, rsi
0x1800327b9  jz      short loc_1800327D9
0x1800327bb  test    byte ptr [rcx+1Ch], 1
0x1800327bf  jz      short loc_1800327D9
0x1800327c1  mov     rcx, [rcx+10h]
0x1800327c5  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800327cc  mov     edx, 2Dh ; '-'
0x1800327d1  mov     r9d, eax
0x1800327d4  call    WPP_SF_d
0x1800327d9  cmp     [rbp+var_30], 0
0x1800327de  jz      short loc_1800327F0
0x1800327e0  mov     rcx, [rbp+var_30]
0x1800327e4  call    cs:__imp_FwBaseFree
0x1800327eb  nop     dword ptr [rax+rax+00h]
0x1800327f0  test    ebx, ebx
0x1800327f2  jns     short loc_180032813
0x1800327f4  cmp     qword ptr [r12+8], 0
0x1800327fa  jz      short loc_18003280B
0x1800327fc  mov     rcx, r12
0x1800327ff  call    cs:__imp_FwBaseFree
0x180032806  nop     dword ptr [rax+rax+00h]
0x18003280b  xorps   xmm0, xmm0
0x18003280e  movups  xmmword ptr [r12], xmm0
0x180032813  mov     eax, ebx
0x180032815  mov     rcx, [rbp+var_8]
0x180032819  xor     rcx, rsp; StackCookie
0x18003281c  call    __security_check_cookie
0x180032821  mov     rbx, [rsp+50h+arg_10]
0x180032829  add     rsp, 50h
0x18003282d  pop     r15
0x18003282f  pop     r14
0x180032831  pop     r12
0x180032833  pop     rsi
0x180032834  pop     rbp
0x180032835  retn
```
