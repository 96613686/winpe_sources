# CBroker::SebPublishWnfEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180004610`
- end: `0x180004a75`
- name: `?SebPublishWnfEventCallback@CBroker@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1125`
- prototype: `int(CBroker *__hidden this, struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800030e0`
- `0x180003120`
- `0x180003950`
- `0x180004610`
- `0x180004a80`
- `0x180005230`
- `0x180005a80`
- `0x180008c00`
- `0x180019f24`
- `0x18001bcdc`
- `0x180020a10`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CBroker::SebPublishWnfEventCallback(
        CBroker *this,
        struct _WNF_STATE_NAME a2,
        __int64 a3,
        struct _WNF_TYPE_ID *a4,
        char *a5,
        const void *a6)
{
  struct _WNF_TYPE_ID *v6; // rdi
  ULONG v7; // r12d
  _QWORD *v9; // rcx
  unsigned int v10; // r15d
  char *v11; // r14
  struct _RTL_SRWLOCK *v12; // rsi
  unsigned int v14; // r8d
  int v15; // eax
  __int64 v16; // r9
  _DWORD *v17; // rdx
  char *v18; // r8
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  __int64 v21; // rdx
  int v22; // [rsp+74h] [rbp+Ch]

  v22 = HIDWORD(this);
  v6 = a4;
  v7 = a2.Data[0];
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v10 = (unsigned int)a6;
    v11 = a5;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD))WPP_SF_DDDqd)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)this,
      HIDWORD(this),
      a2.Data[0],
      a5,
      (_DWORD)a6);
    v9 = WPP_GLOBAL_Control;
  }
  else
  {
    v10 = (unsigned int)a6;
    v11 = a5;
  }
  v12 = (struct _RTL_SRWLOCK *)*((_QWORD *)v6 + 23);
  if ( !v12 )
    goto LABEL_5;
  if ( !v7 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_DD(v9[2], 11, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (unsigned int)this, v22);
    try
    {
      CBroker::SebBroker::DisableEvent(
        v12,
        (struct _WNF_TYPE_ID *)((char *)v6 + 8),
        (const struct _GUID *)((char *)v6 + 120));
    }
    catch ( ... )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids);
      v6 = a4;
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  if ( *((_DWORD *)v6 + 24) == 4148 )
    goto LABEL_22;
  if ( v10 < 8 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) == 0 )
      return 0;
    if ( *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_5;
    v21 = 13;
LABEL_61:
    WPP_SF__guid_(v9[2], v21, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)v6 + 120);
LABEL_33:
    v9 = WPP_GLOBAL_Control;
LABEL_5:
    if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF__guid_(v9[2], 25, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)v6 + 120);
    return 0;
  }
  v14 = *(_DWORD *)v11;
  if ( (*(_DWORD *)v11 & 0x1000000) != 0 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) == 0 )
      return 0;
    if ( *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_5;
    v21 = 14;
    goto LABEL_61;
  }
  if ( v10 < (unsigned __int64)((v14 >> 2) & 0xFFF) + 8 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) == 0 )
      return 0;
    if ( *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_5;
    v21 = 15;
    goto LABEL_61;
  }
  if ( ((v14 >> 2) & 0xFFF) - 1 <= 0x12 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) == 0 )
      return 0;
    if ( *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_5;
    v21 = 16;
    goto LABEL_61;
  }
  if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
  {
    WPP_SF_ddddd(v9[2]);
    v9 = WPP_GLOBAL_Control;
  }
  v15 = *((_DWORD *)v6 + 25);
  if ( v15 )
  {
    if ( v15 >= 1 && (*v11 & 1) == 0 )
    {
      if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 2u )
        WPP_SF__guid_dd(v9[2], 19, 0, (char *)v6 + 120, v15, 0);
      return 0;
    }
    goto LABEL_18;
  }
  if ( (*(_DWORD *)v11 & 1) == 0 )
  {
LABEL_18:
    v16 = *((unsigned int *)v11 + 1);
    if ( (_DWORD)v16 != -1 && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    {
      WPP_SF_d(v9[2], 20, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, v16);
      v9 = WPP_GLOBAL_Control;
    }
    v17 = (_DWORD *)((char *)v6 + 100);
    if ( (*((_BYTE *)v9 + 28) & 1) == 0 || (v17 = (_DWORD *)((char *)v6 + 100), *((_BYTE *)v9 + 25) < 4u) )
    {
LABEL_23:
      v18 = 0;
      if ( *((_DWORD *)v6 + 24) == 4148 )
      {
        LOBYTE(v20) = 0;
LABEL_30:
        if ( *((_QWORD *)v6 + 17) )
          CBroker::SebEvent::OnSignaledBrokerLib(v6, (unsigned __int8)v20, v11, v10);
        else
          CBroker::SebEvent::OnSignaled(v6, (unsigned __int8)v20, v11, v10);
        if ( *((_DWORD *)v6 + 38) == 3 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF__guid_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
              (char *)v6 + 120);
          CBroker::SebBroker::DisableEvent(
            v12,
            (struct _WNF_TYPE_ID *)((char *)v6 + 8),
            (const struct _GUID *)((char *)v6 + 120));
        }
        goto LABEL_33;
      }
      v19 = *(_DWORD *)v11;
      v10 = (*(_DWORD *)v11 >> 2) & 0xFFF;
      if ( v10 )
        v18 = v11 + 8;
      if ( *v17 == 4 )
      {
        if ( (v19 & 0x3FC000) != 0 )
        {
          v20 = v19 >> 14;
          goto LABEL_29;
        }
      }
      else if ( !*v17 )
      {
        LOBYTE(v20) = 1;
        goto LABEL_29;
      }
      v20 = (v19 >> 1) & 1;
LABEL_29:
      v11 = v18;
      goto LABEL_30;
    }
    WPP_SF__guid_D(v9[2], 21, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)v6 + 120, *((_DWORD *)v11 + 1));
LABEL_22:
    v17 = (_DWORD *)((char *)v6 + 100);
    goto LABEL_23;
  }
  if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    WPP_SF__guid_dd(v9[2], 18, 0, (char *)v6 + 120, 0, *(_DWORD *)v11 & 1);
  return 0;
}

```

## disassembly

```asm
0x180004610  mov     [rsp+arg_8], rbx
0x180004615  mov     [rsp+arg_18], r9
0x18000461a  mov     [rsp+arg_0], rcx
0x18000461f  push    rsi
0x180004620  push    rdi
0x180004621  push    r12
0x180004623  push    r14
0x180004625  push    r15
0x180004627  sub     rsp, 40h
0x18000462b  mov     rdi, r9
0x18000462e  mov     r12d, edx
0x180004631  mov     rbx, rcx
0x180004634  mov     rcx, cs:WPP_GLOBAL_Control
0x18000463b  test    byte ptr [rcx+1Ch], 1
0x18000463f  jz      short loc_18000464B
0x180004641  cmp     byte ptr [rcx+19h], 4
0x180004645  jnb     loc_180004802
0x18000464b  mov     r15d, dword ptr [rsp+68h+arg_28]
0x180004653  mov     r14, [rsp+68h+arg_20]
0x18000465b  mov     rsi, [rdi+0B8h]
0x180004662  test    rsi, rsi
0x180004665  jnz     short loc_180004685
0x180004667  test    byte ptr [rcx+1Ch], 1
0x18000466b  jnz     loc_1800047CE
0x180004671  xor     eax, eax
0x180004673  mov     rbx, [rsp+68h+arg_8]
0x180004678  add     rsp, 40h
0x18000467c  pop     r15
0x18000467e  pop     r14
0x180004680  pop     r12
0x180004682  pop     rdi
0x180004683  pop     rsi
0x180004684  retn
0x180004685  test    r12d, r12d
0x180004688  jz      loc_18000497D
0x18000468e  cmp     dword ptr [rdi+60h], 1034h
0x180004695  jz      loc_180004752
0x18000469b  cmp     r15d, 8
0x18000469f  jb      loc_180004947
0x1800046a5  mov     r8d, [r14]
0x1800046a8  bt      r8d, 18h
0x1800046ad  jb      loc_180004962
0x1800046b3  mov     edx, r8d
0x1800046b6  shr     rdx, 2
0x1800046ba  and     edx, 0FFFh
0x1800046c0  add     rdx, 8
0x1800046c4  mov     eax, r15d
0x1800046c7  cmp     rax, rdx
0x1800046ca  jb      loc_1800049E2
0x1800046d0  mov     r9d, r8d
0x1800046d3  shr     r9d, 2
0x1800046d7  and     r9d, 0FFFh
0x1800046de  lea     eax, [r9-1]
0x1800046e2  cmp     eax, 12h
0x1800046e5  jbe     loc_1800049FD
0x1800046eb  test    byte ptr [rcx+1Ch], 1
0x1800046ef  jz      short loc_1800046FB
0x1800046f1  cmp     byte ptr [rcx+19h], 4
0x1800046f5  jnb     loc_18000488D
0x1800046fb  mov     eax, [rdi+64h]
0x1800046fe  test    eax, eax
0x180004700  jz      loc_180004904
0x180004706  cmp     eax, 1
0x180004709  jge     loc_1800048C3
0x18000470f  mov     r9d, [r14+4]
0x180004713  cmp     r9d, 0FFFFFFFFh
0x180004717  jnz     loc_180004858
0x18000471d  lea     rdx, [rdi+64h]
0x180004721  test    byte ptr [rcx+1Ch], 1
0x180004725  jz      short loc_180004756
0x180004727  lea     rdx, [rdi+64h]
0x18000472b  cmp     byte ptr [rcx+19h], 4
0x18000472f  jb      short loc_180004756
0x180004731  lea     r9, [rdi+78h]
0x180004735  mov     edx, 15h
0x18000473a  mov     eax, [r14+4]
0x18000473e  mov     [rsp+68h+var_48], eax
0x180004742  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004749  mov     rcx, [rcx+10h]
0x18000474d  call    WPP_SF__guid_D
0x180004752  lea     rdx, [rdi+64h]
0x180004756  xor     r8d, r8d
0x180004759  cmp     dword ptr [rdi+60h], 1034h
0x180004760  jz      loc_1800047F6
0x180004766  mov     ecx, [r14]
0x180004769  mov     r15d, ecx
0x18000476c  shr     r15d, 2
0x180004770  lea     rax, [r14+8]
0x180004774  and     r15d, 0FFFh
0x18000477b  cmovnz  r8, rax
0x18000477f  mov     eax, [rdx]
0x180004781  cmp     eax, 4
0x180004784  jz      loc_180004844
0x18000478a  test    eax, eax
0x18000478c  jz      loc_180004A13
0x180004792  shr     ecx, 1
0x180004794  and     ecx, 1
0x180004797  mov     r14, r8
0x18000479a  movzx   edx, cl; unsigned int
0x18000479d  mov     r9d, r15d; unsigned int
0x1800047a0  mov     r8, r14; void *
0x1800047a3  mov     rcx, rdi; this
0x1800047a6  cmp     qword ptr [rdi+88h], 0
0x1800047ae  jnz     short loc_1800047FB
0x1800047b0  call    ?OnSignaled@SebEvent@CBroker@@QEAAXKPEBXI@Z; CBroker::SebEvent::OnSignaled(ulong,void const *,uint)
0x1800047b5  cmp     dword ptr [rdi+98h], 3
0x1800047bc  jz      loc_180004A1D
0x1800047c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047c9  jmp     loc_180004667
0x1800047ce  cmp     byte ptr [rcx+19h], 4
0x1800047d2  jb      loc_180004671
0x1800047d8  lea     r9, [rdi+78h]
0x1800047dc  mov     edx, 19h
0x1800047e1  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800047e8  mov     rcx, [rcx+10h]
0x1800047ec  call    WPP_SF__guid_
0x1800047f1  jmp     loc_180004671
0x1800047f6  mov     ecx, r8d
0x1800047f9  jmp     short loc_18000479A
0x1800047fb  call    ?OnSignaledBrokerLib@SebEvent@CBroker@@QEAAXKPEBXI@Z; CBroker::SebEvent::OnSignaledBrokerLib(ulong,void const *,uint)
0x180004800  jmp     short loc_1800047B5
0x180004802  mov     rax, rbx
0x180004805  shr     rax, 20h
0x180004809  mov     r15d, dword ptr [rsp+68h+arg_28]
0x180004811  mov     [rsp+68h+var_30], r15d
0x180004816  mov     r14, [rsp+68h+arg_20]
0x18000481e  mov     [rsp+68h+var_38], r14
0x180004823  mov     [rsp+68h+var_40], r12d
0x180004828  mov     [rsp+68h+var_48], eax
0x18000482c  mov     r9d, ebx
0x18000482f  mov     rcx, [rcx+10h]
0x180004833  call    WPP_SF_DDDqd
0x180004838  mov     rcx, cs:WPP_GLOBAL_Control
0x18000483f  jmp     loc_18000465B
0x180004844  test    ecx, 3FC000h
0x18000484a  jz      loc_180004792
0x180004850  shr     ecx, 0Eh
0x180004853  jmp     loc_180004797
0x180004858  test    byte ptr [rcx+1Ch], 1
0x18000485c  jz      loc_18000471D
0x180004862  cmp     byte ptr [rcx+19h], 4
0x180004866  jb      loc_18000471D
0x18000486c  mov     edx, 14h
0x180004871  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004878  mov     rcx, [rcx+10h]
0x18000487c  call    WPP_SF_d
0x180004881  mov     rcx, cs:WPP_GLOBAL_Control
0x180004888  jmp     loc_18000471D
0x18000488d  mov     edx, r8d
0x180004890  shr     edx, 1
0x180004892  and     edx, 1
0x180004895  and     r8d, 1
0x180004899  mov     eax, [r14+4]
0x18000489d  mov     [rsp+68h+var_30], eax
0x1800048a1  mov     dword ptr [rsp+68h+var_38], edx
0x1800048a5  mov     [rsp+68h+var_40], edx
0x1800048a9  mov     [rsp+68h+var_48], r8d
0x1800048ae  mov     rcx, [rcx+10h]
0x1800048b2  call    WPP_SF_ddddd
0x1800048b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048be  jmp     loc_1800046FB
0x1800048c3  test    byte ptr [r14], 1
0x1800048c7  jnz     loc_18000470F
0x1800048cd  test    byte ptr [rcx+1Ch], 1
0x1800048d1  jz      loc_180004671
0x1800048d7  cmp     byte ptr [rcx+19h], 2
0x1800048db  jb      loc_180004671
0x1800048e1  lea     r9, [rdi+78h]
0x1800048e5  mov     edx, 13h
0x1800048ea  xor     r8d, r8d
0x1800048ed  mov     [rsp+68h+var_40], r8d
0x1800048f2  mov     [rsp+68h+var_48], eax
0x1800048f6  mov     rcx, [rcx+10h]
0x1800048fa  call    WPP_SF__guid_dd
0x1800048ff  jmp     loc_180004671
0x180004904  mov     eax, [r14]
0x180004907  and     eax, 1
0x18000490a  jz      loc_18000470F
0x180004910  test    byte ptr [rcx+1Ch], 1
0x180004914  jz      loc_180004671
0x18000491a  cmp     byte ptr [rcx+19h], 2
0x18000491e  jb      loc_180004671
0x180004924  lea     r9, [rdi+78h]
0x180004928  mov     edx, 12h
0x18000492d  mov     [rsp+68h+var_40], eax
0x180004931  xor     r8d, r8d
0x180004934  mov     [rsp+68h+var_48], r8d
0x180004939  mov     rcx, [rcx+10h]
0x18000493d  call    WPP_SF__guid_dd
0x180004942  jmp     loc_180004671
0x180004947  test    byte ptr [rcx+1Ch], 1
0x18000494b  jz      loc_180004671
0x180004951  cmp     byte ptr [rcx+19h], 2
0x180004955  jb      loc_180004667
0x18000495b  mov     edx, 0Dh
0x180004960  jmp     short loc_1800049C9
0x180004962  test    byte ptr [rcx+1Ch], 1
0x180004966  jz      loc_180004671
0x18000496c  cmp     byte ptr [rcx+19h], 2
0x180004970  jb      loc_180004667
0x180004976  mov     edx, 0Eh
0x18000497b  jmp     short loc_1800049C9
0x18000497d  test    byte ptr [rcx+1Ch], 1
0x180004981  jz      short loc_1800049AA
0x180004983  cmp     byte ptr [rcx+19h], 4
0x180004987  jb      short loc_1800049AA
0x180004989  mov     edx, 0Bh
0x18000498e  mov     eax, dword ptr [rsp+68h+arg_0+4]
0x180004992  mov     [rsp+68h+var_48], eax
0x180004996  mov     r9d, ebx
0x180004999  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800049a0  mov     rcx, [rcx+10h]
0x1800049a4  call    WPP_SF_DD
0x1800049a9  nop
0x1800049aa  lea     r8, [rdi+78h]; struct _GUID *
0x1800049ae  lea     rdx, [rdi+8]; struct Broker::ApplicationIdentity *
0x1800049b2  mov     rcx, rsi; this
0x1800049b5  call    ?DisableEvent@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@@Z; CBroker::SebBroker::DisableEvent(Broker::ApplicationIdentity const &,_GUID const &)
0x1800049ba  jmp     loc_1800047C2
0x1800049bf  jmp     loc_180004A68
0x1800049c4  mov     edx, 10h
0x1800049c9  lea     r9, [rdi+78h]
0x1800049cd  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800049d4  mov     rcx, [rcx+10h]
0x1800049d8  call    WPP_SF__guid_
0x1800049dd  jmp     loc_1800047C2
0x1800049e2  test    byte ptr [rcx+1Ch], 1
0x1800049e6  jz      loc_180004671
0x1800049ec  cmp     byte ptr [rcx+19h], 2
0x1800049f0  jb      loc_180004667
0x1800049f6  mov     edx, 0Fh
0x1800049fb  jmp     short loc_1800049C9
0x1800049fd  test    byte ptr [rcx+1Ch], 1
0x180004a01  jz      loc_180004671
0x180004a07  cmp     byte ptr [rcx+19h], 2
0x180004a0b  jb      loc_180004667
0x180004a11  jmp     short loc_1800049C4
0x180004a13  mov     ecx, 1
0x180004a18  jmp     loc_180004797
0x180004a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a24  test    byte ptr [rcx+1Ch], 1
0x180004a28  jz      short loc_180004A49
0x180004a2a  cmp     byte ptr [rcx+19h], 4
0x180004a2e  jb      short loc_180004A49
0x180004a30  lea     r9, [rdi+78h]
0x180004a34  mov     edx, 16h
0x180004a39  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180004a40  mov     rcx, [rcx+10h]
0x180004a44  call    WPP_SF__guid_
0x180004a49  lea     r8, [rdi+78h]; struct _GUID *
0x180004a4d  lea     rdx, [rdi+8]; struct Broker::ApplicationIdentity *
0x180004a51  mov     rcx, rsi; this
0x180004a54  call    ?DisableEvent@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@@Z; CBroker::SebBroker::DisableEvent(Broker::ApplicationIdentity const &,_GUID const &)
0x180004a59  jmp     loc_1800047C2
0x180004a5e  mov     eax, 0C0000017h
0x180004a63  jmp     loc_180004673
0x180004a68  mov     rdi, [rsp+68h+arg_18]
0x180004a70  jmp     loc_1800047C2
```
