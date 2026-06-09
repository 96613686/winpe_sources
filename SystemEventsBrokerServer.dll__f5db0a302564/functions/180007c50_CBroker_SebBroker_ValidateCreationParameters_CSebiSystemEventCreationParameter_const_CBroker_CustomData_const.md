# CBroker::SebBroker::ValidateCreationParameters(_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *)

- ea: `0x180007c50`
- end: `0x18000821f`
- name: `?ValidateCreationParameters@SebBroker@CBroker@@AEAAXAEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@@Z`
- size: `1487`
- prototype: `void __fastcall(CBroker::SebBroker *__hidden this, const struct _CSebiSystemEventCreationParameter *, const struct CBroker::_CustomData *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006e00`
- `0x18000f680`

## callees

- `0x180003950`
- `0x180005a50`
- `0x180007c50`
- `0x18001d9ac`

## pseudocode

```c
void __fastcall CBroker::SebBroker::ValidateCreationParameters(
        CBroker::SebBroker *this,
        const struct _CSebiSystemEventCreationParameter *a2,
        const struct CBroker::_CustomData *a3)
{
  _QWORD *v6; // rcx
  unsigned int v7; // edx
  __int64 v8; // r9
  int v9; // r8d
  int v10; // eax
  unsigned int v11; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  __int128 v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+48h] [rbp-10h]

  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 86) )
  {
    v7 = *((_DWORD *)a2 + 3);
    if ( v7 > 4 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 60, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v14 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v13 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    v8 = *((int *)a2 + 2);
    if ( (unsigned int)(v8 - 4096) > 0x42 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 61, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v14 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v13 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( v7 == 4 )
    {
      if ( !*((_DWORD *)a2 + 4) )
      {
        if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
          WPP_SF_(v6[2], 62, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
        v14 = 4;
        pExceptionObject = &Broker::InvalidParameter::`vftable';
        v13 = 0;
        throw (Broker::InvalidParameter *)&pExceptionObject;
      }
    }
    else if ( v7 != 1 )
    {
      goto LABEL_11;
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 63, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v14 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v13 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
LABEL_11:
    v9 = *(_DWORD *)&byte_180035F60[40 * v8 - 163840];
    if ( v9 != v7 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_DD(v6[2], 64, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, v8, v9);
      v14 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v13 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( !a3 )
      goto LABEL_13;
    if ( (_DWORD)v8 != 4148 )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_(v6[2], 65, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v14 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v13 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    v10 = *((_DWORD *)a3 + 2);
    if ( *(_QWORD *)a3 )
    {
      if ( v10 )
      {
LABEL_54:
        if ( *((_DWORD *)a3 + 3) )
        {
          if ( !v10 )
          {
            if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
              WPP_SF_(v6[2], 67, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
            v14 = 4;
            pExceptionObject = &Broker::InvalidParameter::`vftable';
            v13 = 0;
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
        }
        else if ( !v10 )
        {
          goto LABEL_13;
        }
        if ( !*((_DWORD *)a2 + 4) )
        {
          if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
            WPP_SF_(v6[2], 68, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v14 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v13 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
LABEL_13:
        if ( *((_DWORD *)a2 + 7)
          || *((_DWORD *)a2 + 8)
          || *((_DWORD *)a2 + 9)
          || *((_DWORD *)a2 + 10)
          || *((_DWORD *)a2 + 11)
          || *((_DWORD *)a2 + 12)
          || *((_DWORD *)a2 + 13) )
        {
          if ( (_DWORD)v8 != 4148 )
          {
            if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
              WPP_SF_(v6[2], 69, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
            v14 = 4;
            pExceptionObject = &Broker::InvalidParameter::`vftable';
            v13 = 0;
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
        }
        else if ( (_DWORD)v8 != 4148 )
        {
          goto LABEL_33;
        }
        if ( !a3 && *((_DWORD *)a2 + 4) )
        {
          if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
            WPP_SF_(v6[2], 70, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v14 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v13 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        v11 = *((_DWORD *)a2 + 11);
        if ( *((_DWORD *)a2 + 9) )
        {
          if ( v11 < *((_DWORD *)a2 + 10) )
          {
            if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
              WPP_SF_(v6[2], 72, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
            v14 = 4;
            pExceptionObject = &Broker::InvalidParameter::`vftable';
            v13 = 0;
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
        }
        else if ( v11 || *((_DWORD *)a2 + 10) )
        {
          if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
            WPP_SF_(v6[2], 71, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v14 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v13 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        goto LABEL_33;
      }
    }
    else if ( !v10 )
    {
      goto LABEL_54;
    }
    if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(v6[2], 66, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v14 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v13 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  if ( (*((_BYTE *)v6 + 28) & 1) == 0 )
    return;
  if ( *((_BYTE *)v6 + 25) >= 4u )
  {
    WPP_SF_(v6[2], 59, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 73, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
}

```

## disassembly

```asm
0x180007c50  push    rbp
0x180007c52  push    rbx
0x180007c53  push    rsi
0x180007c54  push    rdi
0x180007c55  mov     rbp, rsp
0x180007c58  sub     rsp, 58h
0x180007c5c  mov     rsi, r8
0x180007c5f  mov     rdi, rdx
0x180007c62  mov     rbx, rcx
0x180007c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c6c  test    byte ptr [rcx+1Ch], 1
0x180007c70  jz      short loc_180007C7C
0x180007c72  cmp     byte ptr [rcx+19h], 4
0x180007c76  jnb     loc_180007E35
0x180007c7c  cmp     dword ptr [rbx+158h], 0
0x180007c83  jz      short loc_180007C98
0x180007c85  test    byte ptr [rcx+1Ch], 1
0x180007c89  jnz     loc_180007E56
0x180007c8f  add     rsp, 58h
0x180007c93  pop     rdi
0x180007c94  pop     rsi
0x180007c95  pop     rbx
0x180007c96  pop     rbp
0x180007c97  retn
0x180007c98  mov     edx, [rdi+0Ch]
0x180007c9b  cmp     edx, 4
0x180007c9e  ja      loc_1800081D4
0x180007ca4  movsxd  r9, dword ptr [rdi+8]
0x180007ca8  lea     eax, [r9-1000h]
0x180007caf  cmp     eax, 42h ; 'B'
0x180007cb2  ja      loc_180008189
0x180007cb8  cmp     edx, 4
0x180007cbb  jz      loc_180007E7A
0x180007cc1  cmp     edx, 1
0x180007cc4  jz      loc_180007D66
0x180007cca  lea     rax, [r9-1000h]
0x180007cd1  lea     rax, [rax+rax*4]
0x180007cd5  lea     r8, byte_180035F60
0x180007cdc  mov     r8d, [r8+rax*8]
0x180007ce0  cmp     r8d, edx
0x180007ce3  jnz     loc_180007ECF
0x180007ce9  test    rsi, rsi
0x180007cec  jnz     loc_180007F1F
0x180007cf2  cmp     dword ptr [rdi+1Ch], 0
0x180007cf6  jz      loc_180007DBB
0x180007cfc  cmp     r9d, 1034h
0x180007d03  jnz     loc_180008089
0x180007d09  test    rsi, rsi
0x180007d0c  jnz     loc_1800080D4
0x180007d12  cmp     [rdi+10h], esi
0x180007d15  jz      loc_1800080D4
0x180007d1b  test    byte ptr [rcx+1Ch], 1
0x180007d1f  jz      short loc_180007D3C
0x180007d21  cmp     byte ptr [rcx+19h], 4
0x180007d25  jb      short loc_180007D3C
0x180007d27  mov     rcx, [rcx+10h]
0x180007d2b  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007d32  mov     edx, 46h ; 'F'
0x180007d37  call    WPP_SF_
0x180007d3c  xorps   xmm0, xmm0
0x180007d3f  mov     [rbp+var_10], 4
0x180007d46  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007d4d  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007d54  mov     [rbp+pExceptionObject], rax
0x180007d58  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007d5c  movups  [rbp+var_20], xmm0
0x180007d60  call    _CxxThrowException_0
0x180007d66  cmp     dword ptr [rdi+18h], 0
0x180007d6a  jz      loc_180007CCA
0x180007d70  test    byte ptr [rcx+1Ch], 1
0x180007d74  jz      short loc_180007D91
0x180007d76  cmp     byte ptr [rcx+19h], 2
0x180007d7a  jb      short loc_180007D91
0x180007d7c  mov     rcx, [rcx+10h]
0x180007d80  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007d87  mov     edx, 3Fh ; '?'
0x180007d8c  call    WPP_SF_
0x180007d91  xorps   xmm0, xmm0
0x180007d94  mov     [rbp+var_10], 4
0x180007d9b  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007da2  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007da9  mov     [rbp+pExceptionObject], rax
0x180007dad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007db1  movups  [rbp+var_20], xmm0
0x180007db5  call    _CxxThrowException_0
0x180007dbb  cmp     dword ptr [rdi+20h], 0
0x180007dbf  jnz     loc_180007CFC
0x180007dc5  cmp     dword ptr [rdi+24h], 0
0x180007dc9  jnz     loc_180007CFC
0x180007dcf  cmp     dword ptr [rdi+28h], 0
0x180007dd3  jnz     loc_180007CFC
0x180007dd9  cmp     dword ptr [rdi+2Ch], 0
0x180007ddd  jnz     loc_180007CFC
0x180007de3  cmp     dword ptr [rdi+30h], 0
0x180007de7  jnz     loc_180007CFC
0x180007ded  cmp     dword ptr [rdi+34h], 0
0x180007df1  jnz     loc_180007CFC
0x180007df7  cmp     r9d, 1034h
0x180007dfe  jz      loc_180007D09
0x180007e04  test    byte ptr [rcx+1Ch], 1
0x180007e08  jz      loc_180007C8F
0x180007e0e  cmp     byte ptr [rcx+19h], 4
0x180007e12  jb      loc_180007C8F
0x180007e18  mov     rcx, [rcx+10h]
0x180007e1c  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007e23  mov     edx, 49h ; 'I'
0x180007e28  add     rsp, 58h
0x180007e2c  pop     rdi
0x180007e2d  pop     rsi
0x180007e2e  pop     rbx
0x180007e2f  pop     rbp
0x180007e30  jmp     WPP_SF_
0x180007e35  mov     rcx, [rcx+10h]
0x180007e39  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007e40  mov     edx, 3Ah ; ':'
0x180007e45  call    WPP_SF_
0x180007e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e51  jmp     loc_180007C7C
0x180007e56  cmp     byte ptr [rcx+19h], 4
0x180007e5a  jb      short loc_180007E04
0x180007e5c  mov     rcx, [rcx+10h]
0x180007e60  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007e67  mov     edx, 3Bh ; ';'
0x180007e6c  call    WPP_SF_
0x180007e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e78  jmp     short loc_180007E04
0x180007e7a  cmp     dword ptr [rdi+10h], 0
0x180007e7e  jnz     loc_180007D66
0x180007e84  test    byte ptr [rcx+1Ch], 1
0x180007e88  jz      short loc_180007EA5
0x180007e8a  cmp     byte ptr [rcx+19h], 2
0x180007e8e  jb      short loc_180007EA5
0x180007e90  mov     rcx, [rcx+10h]
0x180007e94  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007e9b  mov     edx, 3Eh ; '>'
0x180007ea0  call    WPP_SF_
0x180007ea5  xorps   xmm0, xmm0
0x180007ea8  mov     [rbp+var_10], 4
0x180007eaf  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007eb6  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007ebd  mov     [rbp+pExceptionObject], rax
0x180007ec1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007ec5  movups  [rbp+var_20], xmm0
0x180007ec9  call    _CxxThrowException_0
0x180007ecf  test    byte ptr [rcx+1Ch], 1
0x180007ed3  jz      short loc_180007EF5
0x180007ed5  cmp     byte ptr [rcx+19h], 2
0x180007ed9  jb      short loc_180007EF5
0x180007edb  mov     rcx, [rcx+10h]
0x180007edf  mov     edx, 40h ; '@'
0x180007ee4  mov     [rsp+58h+var_38], r8d
0x180007ee9  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007ef0  call    WPP_SF_DD
0x180007ef5  xorps   xmm0, xmm0
0x180007ef8  mov     [rbp+var_10], 4
0x180007eff  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007f06  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007f0d  mov     [rbp+pExceptionObject], rax
0x180007f11  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007f15  movups  [rbp+var_20], xmm0
0x180007f19  call    _CxxThrowException_0
0x180007f1f  cmp     r9d, 1034h
0x180007f26  jz      short loc_180007F73
0x180007f28  test    byte ptr [rcx+1Ch], 1
0x180007f2c  jz      short loc_180007F49
0x180007f2e  cmp     byte ptr [rcx+19h], 2
0x180007f32  jb      short loc_180007F49
0x180007f34  mov     rcx, [rcx+10h]
0x180007f38  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007f3f  mov     edx, 41h ; 'A'
0x180007f44  call    WPP_SF_
0x180007f49  xorps   xmm0, xmm0
0x180007f4c  mov     [rbp+var_10], 4
0x180007f53  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007f5a  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007f61  mov     [rbp+pExceptionObject], rax
0x180007f65  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007f69  movups  [rbp+var_20], xmm0
0x180007f6d  call    _CxxThrowException_0
0x180007f73  cmp     qword ptr [rsi], 0
0x180007f77  mov     eax, [rsi+8]
0x180007f7a  jz      short loc_180007FDD
0x180007f7c  test    eax, eax
0x180007f7e  jz      short loc_180007FE1
0x180007f80  cmp     dword ptr [rsi+0Ch], 0
0x180007f84  jz      loc_18000802C
0x180007f8a  test    eax, eax
0x180007f8c  jnz     loc_180008034
0x180007f92  test    byte ptr [rcx+1Ch], 1
0x180007f96  jz      short loc_180007FB3
0x180007f98  cmp     byte ptr [rcx+19h], 2
0x180007f9c  jb      short loc_180007FB3
0x180007f9e  mov     rcx, [rcx+10h]
0x180007fa2  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007fa9  mov     edx, 43h ; 'C'
0x180007fae  call    WPP_SF_
0x180007fb3  xorps   xmm0, xmm0
0x180007fb6  mov     [rbp+var_10], 4
0x180007fbd  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180007fc4  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180007fcb  mov     [rbp+pExceptionObject], rax
0x180007fcf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007fd3  movups  [rbp+var_20], xmm0
0x180007fd7  call    _CxxThrowException_0
0x180007fdd  test    eax, eax
0x180007fdf  jz      short loc_180007F80
0x180007fe1  test    byte ptr [rcx+1Ch], 1
0x180007fe5  jz      short loc_180008002
0x180007fe7  cmp     byte ptr [rcx+19h], 2
0x180007feb  jb      short loc_180008002
0x180007fed  mov     rcx, [rcx+10h]
0x180007ff1  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180007ff8  mov     edx, 42h ; 'B'
0x180007ffd  call    WPP_SF_
0x180008002  xorps   xmm0, xmm0
0x180008005  mov     [rbp+var_10], 4
0x18000800c  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180008013  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000801a  mov     [rbp+pExceptionObject], rax
0x18000801e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008022  movups  [rbp+var_20], xmm0
0x180008026  call    _CxxThrowException_0
0x18000802c  test    eax, eax
0x18000802e  jz      loc_180007CF2
0x180008034  cmp     dword ptr [rdi+10h], 0
0x180008038  jnz     loc_180007CF2
0x18000803e  test    byte ptr [rcx+1Ch], 1
0x180008042  jz      short loc_18000805F
0x180008044  cmp     byte ptr [rcx+19h], 2
0x180008048  jb      short loc_18000805F
0x18000804a  mov     rcx, [rcx+10h]
0x18000804e  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180008055  mov     edx, 44h ; 'D'
0x18000805a  call    WPP_SF_
0x18000805f  xorps   xmm0, xmm0
0x180008062  mov     [rbp+var_10], 4
0x180008069  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180008070  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180008077  mov     [rbp+pExceptionObject], rax
0x18000807b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000807f  movups  [rbp+var_20], xmm0
0x180008083  call    _CxxThrowException_0
0x180008089  test    byte ptr [rcx+1Ch], 1
0x18000808d  jz      short loc_1800080AA
0x18000808f  cmp     byte ptr [rcx+19h], 2
0x180008093  jb      short loc_1800080AA
0x180008095  mov     rcx, [rcx+10h]
0x180008099  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x1800080a0  mov     edx, 45h ; 'E'
0x1800080a5  call    WPP_SF_
0x1800080aa  xorps   xmm0, xmm0
0x1800080ad  mov     [rbp+var_10], 4
0x1800080b4  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800080bb  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800080c2  mov     [rbp+pExceptionObject], rax
0x1800080c6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800080ca  movups  [rbp+var_20], xmm0
0x1800080ce  call    _CxxThrowException_0
0x1800080d4  cmp     dword ptr [rdi+24h], 0
0x1800080d8  mov     eax, [rdi+2Ch]
0x1800080db  jnz     short loc_180008135
0x1800080dd  test    eax, eax
0x1800080df  jnz     short loc_1800080EA
0x1800080e1  cmp     [rdi+28h], eax
0x1800080e4  jz      loc_180007E04
0x1800080ea  test    byte ptr [rcx+1Ch], 1
0x1800080ee  jz      short loc_18000810B
0x1800080f0  cmp     byte ptr [rcx+19h], 2
0x1800080f4  jb      short loc_18000810B
0x1800080f6  mov     rcx, [rcx+10h]
0x1800080fa  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180008101  mov     edx, 47h ; 'G'
0x180008106  call    WPP_SF_
0x18000810b  xorps   xmm0, xmm0
0x18000810e  mov     [rbp+var_10], 4
0x180008115  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000811c  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180008123  mov     [rbp+pExceptionObject], rax
0x180008127  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000812b  movups  [rbp+var_20], xmm0
0x18000812f  call    _CxxThrowException_0
0x180008135  cmp     eax, [rdi+28h]
0x180008138  jnb     loc_180007E04
0x18000813e  test    byte ptr [rcx+1Ch], 1
0x180008142  jz      short loc_18000815F
0x180008144  cmp     byte ptr [rcx+19h], 2
0x180008148  jb      short loc_18000815F
0x18000814a  mov     rcx, [rcx+10h]
0x18000814e  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180008155  mov     edx, 48h ; 'H'
0x18000815a  call    WPP_SF_
0x18000815f  xorps   xmm0, xmm0
0x180008162  mov     [rbp+var_10], 4
0x180008169  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180008170  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180008177  mov     [rbp+pExceptionObject], rax
0x18000817b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000817f  movups  [rbp+var_20], xmm0
0x180008183  call    _CxxThrowException_0
0x180008189  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
