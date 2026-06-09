# Broker::SebBroker::ValidateCreationParameters(_SebiSystemEventCreationParameter const &,bool)

- ea: `0x180004250`
- end: `0x180004607`
- name: `?ValidateCreationParameters@SebBroker@Broker@@AEAAXAEBU_SebiSystemEventCreationParameter@@_N@Z`
- size: `951`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this, const struct _SebiSystemEventCreationParameter *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010560`

## callees

- `0x180004250`
- `0x180005a50`
- `0x18001d9ac`

## pseudocode

```c
void __fastcall Broker::SebBroker::ValidateCreationParameters(
        Broker::SebBroker *this,
        const struct _SebiSystemEventCreationParameter *a2,
        char a3)
{
  _QWORD *v6; // rcx
  unsigned int v7; // r9d
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int128 v12; // [rsp+28h] [rbp-20h]
  int v13; // [rsp+38h] [rbp-10h]

  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 30) )
  {
    v7 = *((_DWORD *)a2 + 3);
    if ( v7 > 3 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 85, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    v8 = *((int *)a2 + 2);
    if ( (unsigned int)v8 > 0x4B )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 86, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( v7 == 1 && *((_DWORD *)a2 + 4) )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 87, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( *((_DWORD *)&Broker::EventPolicyTable + 12 * v8 + 7) != v7 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 88, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( (_DWORD)v8 == 21 && !*((_DWORD *)a2 + 4) )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 89, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( *((_DWORD *)&Broker::EventPolicyTable + 12 * v8 + 1) != *((_DWORD *)a2 + 5) )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 90, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( a3 )
    {
      if ( (unsigned int)v8 > 0x16 )
        goto LABEL_15;
      v9 = 4227584;
      if ( !_bittest(&v9, v8) )
        goto LABEL_15;
    }
    else if ( (unsigned int)v8 > 0x16 || (v10 = 4227584, !_bittest(&v10, v8)) )
    {
      if ( *(_QWORD *)a2 )
      {
        if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
          WPP_SF_(v6[2], 91, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
        v13 = 4;
        pExceptionObject = &Broker::InvalidParameter::`vftable';
        v12 = 0;
        throw (Broker::InvalidParameter *)&pExceptionObject;
      }
      goto LABEL_15;
    }
    if ( !*(_QWORD *)a2 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 92, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
      v13 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v12 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    goto LABEL_15;
  }
  if ( (*((_BYTE *)v6 + 28) & 1) == 0 )
    return;
  if ( *((_BYTE *)v6 + 25) >= 4u )
  {
    WPP_SF_(v6[2], 84, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 93, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
}

```

## disassembly

```asm
0x180004250  push    rbp
0x180004252  push    rbx
0x180004253  push    rsi
0x180004254  push    rdi
0x180004255  mov     rbp, rsp
0x180004258  sub     rsp, 48h
0x18000425c  movzx   esi, r8b
0x180004260  mov     rdi, rdx
0x180004263  mov     rbx, rcx
0x180004266  mov     rcx, cs:WPP_GLOBAL_Control
0x18000426d  test    byte ptr [rcx+1Ch], 1
0x180004271  jz      short loc_18000427D
0x180004273  cmp     byte ptr [rcx+19h], 4
0x180004277  jnb     loc_180004322
0x18000427d  cmp     dword ptr [rbx+78h], 0
0x180004281  jz      short loc_180004296
0x180004283  test    byte ptr [rcx+1Ch], 1
0x180004287  jnz     loc_1800043F3
0x18000428d  add     rsp, 48h
0x180004291  pop     rdi
0x180004292  pop     rsi
0x180004293  pop     rbx
0x180004294  pop     rbp
0x180004295  retn
0x180004296  mov     r9d, [rdi+0Ch]
0x18000429a  cmp     r9d, 3
0x18000429e  ja      loc_1800045BC
0x1800042a4  movsxd  rdx, dword ptr [rdi+8]
0x1800042a8  cmp     edx, 4Bh ; 'K'
0x1800042ab  ja      loc_180004571
0x1800042b1  cmp     r9d, 1
0x1800042b5  jz      loc_18000439E
0x1800042bb  lea     r8, [rdx+rdx*2]
0x1800042bf  add     r8, r8
0x1800042c2  lea     r10, ?EventPolicyTable@Broker@@3PAU_EventPolicy@1@A; Broker::_EventPolicy near * Broker::EventPolicyTable
0x1800042c9  cmp     [r10+r8*8+1Ch], r9d
0x1800042ce  jnz     loc_18000441E
0x1800042d4  cmp     edx, 15h
0x1800042d7  jz      loc_180004469
0x1800042dd  mov     eax, [rdi+14h]
0x1800042e0  cmp     [r10+r8*8+4], eax
0x1800042e5  jnz     loc_1800044BE
0x1800042eb  test    sil, sil
0x1800042ee  jz      loc_180004509
0x1800042f4  cmp     edx, 16h
0x1800042f7  jbe     short loc_180004343
0x1800042f9  test    byte ptr [rcx+1Ch], 1
0x1800042fd  jz      short loc_18000428D
0x1800042ff  cmp     byte ptr [rcx+19h], 4
0x180004303  jb      short loc_18000428D
0x180004305  mov     rcx, [rcx+10h]
0x180004309  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180004310  mov     edx, 5Dh ; ']'
0x180004315  add     rsp, 48h
0x180004319  pop     rdi
0x18000431a  pop     rsi
0x18000431b  pop     rbx
0x18000431c  pop     rbp
0x18000431d  jmp     WPP_SF_
0x180004322  mov     rcx, [rcx+10h]
0x180004326  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000432d  mov     edx, 53h ; 'S'
0x180004332  call    WPP_SF_
0x180004337  mov     rcx, cs:WPP_GLOBAL_Control
0x18000433e  jmp     loc_18000427D
0x180004343  mov     eax, 408200h
0x180004348  bt      eax, edx
0x18000434b  jnb     short loc_1800042F9
0x18000434d  cmp     qword ptr [rdi], 0
0x180004351  jnz     short loc_1800042F9
0x180004353  test    byte ptr [rcx+1Ch], 1
0x180004357  jz      short loc_180004374
0x180004359  cmp     byte ptr [rcx+19h], 2
0x18000435d  jb      short loc_180004374
0x18000435f  mov     rcx, [rcx+10h]
0x180004363  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000436a  mov     edx, 5Ch ; '\'
0x18000436f  call    WPP_SF_
0x180004374  xorps   xmm0, xmm0
0x180004377  mov     [rbp+var_10], 4
0x18000437e  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180004385  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000438c  mov     [rbp+pExceptionObject], rax
0x180004390  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004394  movups  [rbp+var_20], xmm0
0x180004398  call    _CxxThrowException_0
0x18000439e  cmp     dword ptr [rdi+10h], 0
0x1800043a2  jz      loc_1800042BB
0x1800043a8  test    byte ptr [rcx+1Ch], 1
0x1800043ac  jz      short loc_1800043C9
0x1800043ae  cmp     byte ptr [rcx+19h], 2
0x1800043b2  jb      short loc_1800043C9
0x1800043b4  mov     rcx, [rcx+10h]
0x1800043b8  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800043bf  mov     edx, 57h ; 'W'
0x1800043c4  call    WPP_SF_
0x1800043c9  xorps   xmm0, xmm0
0x1800043cc  mov     [rbp+var_10], 4
0x1800043d3  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800043da  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800043e1  mov     [rbp+pExceptionObject], rax
0x1800043e5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800043e9  movups  [rbp+var_20], xmm0
0x1800043ed  call    _CxxThrowException_0
0x1800043f3  cmp     byte ptr [rcx+19h], 4
0x1800043f7  jb      loc_1800042F9
0x1800043fd  mov     rcx, [rcx+10h]
0x180004401  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180004408  mov     edx, 54h ; 'T'
0x18000440d  call    WPP_SF_
0x180004412  mov     rcx, cs:WPP_GLOBAL_Control
0x180004419  jmp     loc_1800042F9
0x18000441e  test    byte ptr [rcx+1Ch], 1
0x180004422  jz      short loc_18000443F
0x180004424  cmp     byte ptr [rcx+19h], 2
0x180004428  jb      short loc_18000443F
0x18000442a  mov     rcx, [rcx+10h]
0x18000442e  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180004435  mov     edx, 58h ; 'X'
0x18000443a  call    WPP_SF_
0x18000443f  xorps   xmm0, xmm0
0x180004442  mov     [rbp+var_10], 4
0x180004449  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180004450  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180004457  mov     [rbp+pExceptionObject], rax
0x18000445b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000445f  movups  [rbp+var_20], xmm0
0x180004463  call    _CxxThrowException_0
0x180004469  cmp     dword ptr [rdi+10h], 0
0x18000446d  jnz     loc_1800042DD
0x180004473  test    byte ptr [rcx+1Ch], 1
0x180004477  jz      short loc_180004494
0x180004479  cmp     byte ptr [rcx+19h], 2
0x18000447d  jb      short loc_180004494
0x18000447f  mov     rcx, [rcx+10h]
0x180004483  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000448a  mov     edx, 59h ; 'Y'
0x18000448f  call    WPP_SF_
0x180004494  xorps   xmm0, xmm0
0x180004497  mov     [rbp+var_10], 4
0x18000449e  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800044a5  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800044ac  mov     [rbp+pExceptionObject], rax
0x1800044b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800044b4  movups  [rbp+var_20], xmm0
0x1800044b8  call    _CxxThrowException_0
0x1800044be  test    byte ptr [rcx+1Ch], 1
0x1800044c2  jz      short loc_1800044DF
0x1800044c4  cmp     byte ptr [rcx+19h], 2
0x1800044c8  jb      short loc_1800044DF
0x1800044ca  mov     rcx, [rcx+10h]
0x1800044ce  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800044d5  mov     edx, 5Ah ; 'Z'
0x1800044da  call    WPP_SF_
0x1800044df  xorps   xmm0, xmm0
0x1800044e2  mov     [rbp+var_10], 4
0x1800044e9  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800044f0  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800044f7  mov     [rbp+pExceptionObject], rax
0x1800044fb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800044ff  movups  [rbp+var_20], xmm0
0x180004503  call    _CxxThrowException_0
0x180004509  cmp     edx, 16h
0x18000450c  ja      short loc_18000451C
0x18000450e  mov     eax, 408200h
0x180004513  bt      eax, edx
0x180004516  jb      loc_18000434D
0x18000451c  cmp     qword ptr [rdi], 0
0x180004520  jz      loc_1800042F9
0x180004526  test    byte ptr [rcx+1Ch], 1
0x18000452a  jz      short loc_180004547
0x18000452c  cmp     byte ptr [rcx+19h], 2
0x180004530  jb      short loc_180004547
0x180004532  mov     rcx, [rcx+10h]
0x180004536  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000453d  mov     edx, 5Bh ; '['
0x180004542  call    WPP_SF_
0x180004547  xorps   xmm0, xmm0
0x18000454a  mov     [rbp+var_10], 4
0x180004551  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180004558  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000455f  mov     [rbp+pExceptionObject], rax
0x180004563  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004567  movups  [rbp+var_20], xmm0
0x18000456b  call    _CxxThrowException_0
0x180004571  test    byte ptr [rcx+1Ch], 1
0x180004575  jz      short loc_180004592
0x180004577  cmp     byte ptr [rcx+19h], 2
0x18000457b  jb      short loc_180004592
0x18000457d  mov     rcx, [rcx+10h]
0x180004581  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180004588  mov     edx, 56h ; 'V'
0x18000458d  call    WPP_SF_
0x180004592  xorps   xmm0, xmm0
0x180004595  mov     [rbp+var_10], 4
0x18000459c  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800045a3  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800045aa  mov     [rbp+pExceptionObject], rax
0x1800045ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800045b2  movups  [rbp+var_20], xmm0
0x1800045b6  call    _CxxThrowException_0
0x1800045bc  test    byte ptr [rcx+1Ch], 1
0x1800045c0  jz      short loc_1800045DD
0x1800045c2  cmp     byte ptr [rcx+19h], 2
0x1800045c6  jb      short loc_1800045DD
0x1800045c8  mov     rcx, [rcx+10h]
0x1800045cc  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800045d3  mov     edx, 55h ; 'U'
0x1800045d8  call    WPP_SF_
0x1800045dd  xorps   xmm0, xmm0
0x1800045e0  mov     [rbp+var_10], 4
0x1800045e7  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800045ee  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800045f5  mov     [rbp+pExceptionObject], rax
0x1800045f9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800045fd  movups  [rbp+var_20], xmm0
0x180004601  call    _CxxThrowException_0
```
