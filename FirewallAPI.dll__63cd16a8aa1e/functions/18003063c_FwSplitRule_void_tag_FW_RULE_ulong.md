# FwSplitRule(void *,_tag_FW_RULE *,ulong)

- ea: `0x18003063c`
- end: `0x1800308f0`
- name: `?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z`
- size: `692`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_RULE *, unsigned int)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800021f0`
- `0x18000270c`
- `0x180015eb0`
- `0x180030d08`
- `0x180030da4`
- `0x1800392c0`
- `0x180044108`
- `0x180044480`
- `0x180044eb0`

## callees

- `0x180005954`
- `0x1800140b0`
- `0x180014690`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003063c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800307e8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800307e8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800307a0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800307a0`
- `fwbase!FwBaseFree` at `0x180030881`
- `fwbase!FwBaseFree` at `0x180030881`
- `fwbase!FwStringCopy` at `0x180030896`
- `fwbase!FwStringCopy` at `0x180030896`

## pseudocode

```c
__int64 __fastcall FwSplitRule(unsigned __int16 *a1, struct _tag_FW_RULE *a2, int a3)
{
  int v6; // edi
  __int128 *p_Src; // rcx
  __int64 v8; // rdx
  struct _tag_FW_RULE *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // rax
  int v24; // eax
  int v25; // ebx
  FwPolicy2 *v26; // rcx
  __int64 v27; // rdx
  int v28; // edi
  int v29; // eax
  OLECHAR *v30; // rcx
  __int128 Src; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR *v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+48h] [rbp-B8h]
  GUID pguid; // [rsp+220h] [rbp+120h] BYREF
  OLECHAR sz[256]; // [rsp+230h] [rbp+130h] BYREF

  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  v6 = *((_DWORD *)a2 + 10);
  p_Src = &Src;
  v8 = 3;
  v9 = a2;
  do
  {
    v10 = *((_OWORD *)v9 + 1);
    *p_Src = *(_OWORD *)v9;
    v11 = *((_OWORD *)v9 + 2);
    p_Src[1] = v10;
    v12 = *((_OWORD *)v9 + 3);
    p_Src[2] = v11;
    v13 = *((_OWORD *)v9 + 4);
    p_Src[3] = v12;
    v14 = *((_OWORD *)v9 + 5);
    p_Src[4] = v13;
    v15 = *((_OWORD *)v9 + 6);
    p_Src[5] = v14;
    v16 = *((_OWORD *)v9 + 7);
    v9 = (struct _tag_FW_RULE *)((char *)v9 + 128);
    p_Src[6] = v15;
    p_Src[7] = v16;
    p_Src += 8;
    --v8;
  }
  while ( v8 );
  v17 = *((_OWORD *)v9 + 1);
  *p_Src = *(_OWORD *)v9;
  v18 = *((_OWORD *)v9 + 2);
  p_Src[1] = v17;
  v19 = *((_OWORD *)v9 + 3);
  p_Src[2] = v18;
  v20 = *((_OWORD *)v9 + 4);
  p_Src[3] = v19;
  v21 = *((_OWORD *)v9 + 5);
  p_Src[4] = v20;
  v22 = *((_OWORD *)v9 + 6);
  v23 = *((_QWORD *)v9 + 14);
  p_Src[5] = v21;
  p_Src[6] = v22;
  *((_QWORD *)p_Src + 14) = v23;
  v34 = (unsigned __int8)v6 & (unsigned __int8)~(_BYTE)a3 & 7;
  v24 = FWSetFirewallRule(a1, &Src);
  v25 = v24;
  if ( !v24 )
    goto LABEL_11;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v27 = 78;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v25);
    }
  }
  else
  {
LABEL_11:
    v25 = CoCreateGuid(&pguid);
    if ( v25 >= 0 )
    {
      if ( StringFromGUID2(&pguid, sz, 256) )
      {
        v28 = a3 & v6;
        v33 = sz;
        v34 = v28;
        v29 = FWAddFirewallRule((__int64)a1, &Src);
        v25 = v29;
        if ( !v29 )
          goto LABEL_26;
        if ( v29 > 0 )
          v25 = (unsigned __int16)v29 | 0x80070000;
        if ( v25 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v27 = 81;
            goto LABEL_10;
          }
        }
        else
        {
LABEL_26:
          FwBaseFree(*((_QWORD *)a2 + 2));
          v30 = v33;
          *((_QWORD *)a2 + 2) = 0;
          v25 = FwStringCopy(v30, (char *)a2 + 16);
          if ( v25 >= 0 )
          {
            *((_DWORD *)a2 + 10) = v28;
            return (unsigned int)v25;
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v27 = 82;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v25 = -2147024774;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = 80;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 79;
        goto LABEL_10;
      }
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18003063c  mov     [rsp-8+arg_18], rbx
0x180030641  push    rbp
0x180030642  push    rsi
0x180030643  push    rdi
0x180030644  push    r14
0x180030646  push    r15
0x180030648  lea     rbp, [rsp-340h]
0x180030650  sub     rsp, 440h
0x180030657  mov     rax, cs:__security_cookie
0x18003065e  xor     rax, rsp
0x180030661  mov     [rbp+360h+var_30], rax
0x180030668  mov     r15d, r8d
0x18003066b  mov     rsi, rdx
0x18003066e  mov     r14, rcx
0x180030671  xorps   xmm0, xmm0
0x180030674  xor     edx, edx; Val
0x180030676  lea     rcx, [rbp+360h+sz]; void *
0x18003067d  mov     r8d, 200h; Size
0x180030683  movups  xmmword ptr [rbp+360h+pguid.Data1], xmm0
0x18003068a  call    memset_0
0x18003068f  mov     edi, [rsi+28h]
0x180030692  lea     rcx, [rsp+460h+Src]
0x180030697  mov     edx, 3
0x18003069c  mov     rax, rsi
0x18003069f  lea     r8d, [rdx+7Dh]
0x1800306a3  movups  xmm0, xmmword ptr [rax]
0x1800306a6  movups  xmm1, xmmword ptr [rax+10h]
0x1800306aa  movups  xmmword ptr [rcx], xmm0
0x1800306ad  movups  xmm0, xmmword ptr [rax+20h]
0x1800306b1  movups  xmmword ptr [rcx+10h], xmm1
0x1800306b5  movups  xmm1, xmmword ptr [rax+30h]
0x1800306b9  movups  xmmword ptr [rcx+20h], xmm0
0x1800306bd  movups  xmm0, xmmword ptr [rax+40h]
0x1800306c1  movups  xmmword ptr [rcx+30h], xmm1
0x1800306c5  movups  xmm1, xmmword ptr [rax+50h]
0x1800306c9  movups  xmmword ptr [rcx+40h], xmm0
0x1800306cd  movups  xmm0, xmmword ptr [rax+60h]
0x1800306d1  movups  xmmword ptr [rcx+50h], xmm1
0x1800306d5  movups  xmm1, xmmword ptr [rax+70h]
0x1800306d9  add     rax, r8
0x1800306dc  movups  xmmword ptr [rcx+60h], xmm0
0x1800306e0  movups  xmmword ptr [rcx+70h], xmm1
0x1800306e4  add     rcx, r8
0x1800306e7  sub     rdx, 1
0x1800306eb  jnz     short loc_1800306A3
0x1800306ed  movups  xmm0, xmmword ptr [rax]
0x1800306f0  lea     rdx, [rsp+460h+Src]; Src
0x1800306f5  movups  xmm1, xmmword ptr [rax+10h]
0x1800306f9  movups  xmmword ptr [rcx], xmm0
0x1800306fc  movups  xmm0, xmmword ptr [rax+20h]
0x180030700  movups  xmmword ptr [rcx+10h], xmm1
0x180030704  movups  xmm1, xmmword ptr [rax+30h]
0x180030708  movups  xmmword ptr [rcx+20h], xmm0
0x18003070c  movups  xmm0, xmmword ptr [rax+40h]
0x180030710  movups  xmmword ptr [rcx+30h], xmm1
0x180030714  movups  xmm1, xmmword ptr [rax+50h]
0x180030718  movups  xmmword ptr [rcx+40h], xmm0
0x18003071c  movups  xmm0, xmmword ptr [rax+60h]
0x180030720  mov     rax, [rax+70h]
0x180030724  movups  xmmword ptr [rcx+50h], xmm1
0x180030728  movups  xmmword ptr [rcx+60h], xmm0
0x18003072c  mov     [rcx+70h], rax
0x180030730  mov     eax, r15d
0x180030733  not     eax
0x180030735  mov     rcx, r14; __int64
0x180030738  and     eax, edi
0x18003073a  and     eax, 7
0x18003073d  mov     [rsp+460h+var_418], eax
0x180030741  call    FWSetFirewallRule
0x180030746  mov     ebx, eax
0x180030748  test    eax, eax
0x18003074a  jz      short loc_180030799
0x18003074c  jle     short loc_180030757
0x18003074e  movzx   ebx, ax
0x180030751  or      ebx, 80070000h
0x180030757  test    ebx, ebx
0x180030759  jns     short loc_180030799
0x18003075b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030762  lea     rax, WPP_GLOBAL_Control
0x180030769  cmp     rcx, rax
0x18003076c  jz      loc_1800308C8
0x180030772  test    byte ptr [rcx+1Ch], 1
0x180030776  jz      loc_1800308C8
0x18003077c  mov     edx, 4Eh ; 'N'
0x180030781  mov     rcx, [rcx+10h]
0x180030785  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003078c  mov     r9d, ebx
0x18003078f  call    WPP_SF_d
0x180030794  jmp     loc_1800308C8
0x180030799  lea     rcx, [rbp+360h+pguid]; pguid
0x1800307a0  call    cs:__imp_CoCreateGuid
0x1800307a6  mov     ebx, eax
0x1800307a8  test    eax, eax
0x1800307aa  jns     short loc_1800307D4
0x1800307ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307b3  lea     rax, WPP_GLOBAL_Control
0x1800307ba  cmp     rcx, rax
0x1800307bd  jz      loc_1800308C8
0x1800307c3  test    byte ptr [rcx+1Ch], 1
0x1800307c7  jz      loc_1800308C8
0x1800307cd  mov     edx, 4Fh ; 'O'
0x1800307d2  jmp     short loc_180030781
0x1800307d4  mov     r8d, 100h; cchMax
0x1800307da  lea     rdx, [rbp+360h+sz]; lpsz
0x1800307e1  lea     rcx, [rbp+360h+pguid]; rguid
0x1800307e8  call    cs:__imp_StringFromGUID2
0x1800307ee  test    eax, eax
0x1800307f0  jnz     short loc_180030822
0x1800307f2  mov     ebx, 8007007Ah
0x1800307f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307fe  lea     rax, WPP_GLOBAL_Control
0x180030805  cmp     rcx, rax
0x180030808  jz      loc_1800308C8
0x18003080e  test    byte ptr [rcx+1Ch], 1
0x180030812  jz      loc_1800308C8
0x180030818  mov     edx, 50h ; 'P'
0x18003081d  jmp     loc_180030781
0x180030822  lea     rax, [rbp+360h+sz]
0x180030829  and     edi, r15d
0x18003082c  lea     rdx, [rsp+460h+Src]; Src
0x180030831  mov     [rsp+460h+var_430], rax
0x180030836  mov     rcx, r14; __int64
0x180030839  mov     [rsp+460h+var_418], edi
0x18003083d  call    FWAddFirewallRule
0x180030842  mov     ebx, eax
0x180030844  test    eax, eax
0x180030846  jz      short loc_18003087A
0x180030848  jle     short loc_180030853
0x18003084a  movzx   ebx, ax
0x18003084d  or      ebx, 80070000h
0x180030853  test    ebx, ebx
0x180030855  jns     short loc_18003087A
0x180030857  mov     rcx, cs:WPP_GLOBAL_Control
0x18003085e  lea     rax, WPP_GLOBAL_Control
0x180030865  cmp     rcx, rax
0x180030868  jz      short loc_1800308C8
0x18003086a  test    byte ptr [rcx+1Ch], 1
0x18003086e  jz      short loc_1800308C8
0x180030870  mov     edx, 51h ; 'Q'
0x180030875  jmp     loc_180030781
0x18003087a  lea     rbx, [rsi+10h]
0x18003087e  mov     rcx, [rbx]
0x180030881  call    cs:__imp_FwBaseFree
0x180030887  mov     rcx, [rsp+460h+var_430]
0x18003088c  mov     rdx, rbx
0x18003088f  mov     qword ptr [rbx], 0
0x180030896  call    cs:__imp_FwStringCopy
0x18003089c  mov     ebx, eax
0x18003089e  test    eax, eax
0x1800308a0  jns     short loc_1800308C5
0x1800308a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308a9  lea     rax, WPP_GLOBAL_Control
0x1800308b0  cmp     rcx, rax
0x1800308b3  jz      short loc_1800308C8
0x1800308b5  test    byte ptr [rcx+1Ch], 1
0x1800308b9  jz      short loc_1800308C8
0x1800308bb  mov     edx, 52h ; 'R'
0x1800308c0  jmp     loc_180030781
0x1800308c5  mov     [rsi+28h], edi
0x1800308c8  mov     eax, ebx
0x1800308ca  mov     rcx, [rbp+360h+var_30]
0x1800308d1  xor     rcx, rsp; StackCookie
0x1800308d4  call    __security_check_cookie
0x1800308d9  mov     rbx, [rsp+460h+arg_18]
0x1800308e1  add     rsp, 440h
0x1800308e8  pop     r15
0x1800308ea  pop     r14
0x1800308ec  pop     rdi
0x1800308ed  pop     rsi
0x1800308ee  pop     rbp
0x1800308ef  retn
```
