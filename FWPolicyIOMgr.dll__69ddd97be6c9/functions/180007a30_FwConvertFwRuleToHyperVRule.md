# FwConvertFwRuleToHyperVRule

- ea: `0x180007a30`
- end: `0x180007e79`
- name: `FwConvertFwRuleToHyperVRule`
- size: `1097`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800042c4`
- `0x180007a30`
- `0x1800087b0`
- `0x1800088a0`
- `0x18001e9ac`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x180007a51`
- `fwbase!FwAlloc` at `0x180007bf3`
- `fwbase!FwAlloc` at `0x180007cd9`
- `fwbase!FwAlloc` at `0x180007a51`
- `fwbase!FwAlloc` at `0x180007bf3`
- `fwbase!FwAlloc` at `0x180007cd9`
- `fwbase!FwArrayCopy` at `0x180007d91`
- `fwbase!FwArrayCopy` at `0x180007deb`
- `fwbase!FwArrayCopy` at `0x180007d91`
- `fwbase!FwArrayCopy` at `0x180007deb`
- `fwbase!FwStringCopy` at `0x180007adc`
- `fwbase!FwStringCopy` at `0x180007b1b`
- `fwbase!FwStringCopy` at `0x180007adc`
- `fwbase!FwStringCopy` at `0x180007b1b`

## pseudocode

```c
__int64 __fastcall FwConvertFwRuleToHyperVRule(__int64 a1, _QWORD *a2)
{
  _WORD *v4; // rax
  _WORD *v5; // rbx
  __int64 v6; // r9
  int v7; // edi
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r8

  *a2 = 0;
  v4 = (_WORD *)FwAlloc(296);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x128u);
    v5[4] = 545;
    *((_OWORD *)v5 + 17) = 0;
    *((_DWORD *)v5 + 66) = 1;
    v7 = FwStringCopy(*(_QWORD *)(a1 + 16), v5 + 8);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v9 = 224;
      goto LABEL_10;
    }
    v7 = FwStringCopy(*(_QWORD *)(a1 + 24), v5 + 12);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v9 = 225;
      goto LABEL_10;
    }
    *((_DWORD *)v5 + 9) = *(_DWORD *)(a1 + 44);
    v5[28] = *(_WORD *)(a1 + 48);
    *((_DWORD *)v5 + 64) = *(_DWORD *)(a1 + 288);
    *((_DWORD *)v5 + 72) = *(_DWORD *)(a1 + 40);
    if ( (*(_BYTE *)(a1 + 292) & 1) != 0 )
      v5[130] = 1;
    switch ( *(_DWORD *)(a1 + 340) )
    {
      case 1:
        *((_DWORD *)v5 + 67) = 8;
        break;
      case 2:
        *((_DWORD *)v5 + 67) = 9;
        break;
      case 3:
        *((_DWORD *)v5 + 67) = 10;
        break;
      case 6:
        *((_DWORD *)v5 + 67) = 11;
        break;
      default:
        MicrosoftTelemetryAssertTriggeredNoArgs();
        *((_DWORD *)v5 + 67) = 0;
        break;
    }
    if ( *(_WORD *)(a1 + 48) == 1 )
    {
      if ( *(_DWORD *)(a1 + 56) )
      {
        v10 = FwAlloc(4LL * *(unsigned int *)(a1 + 56));
        *((_QWORD *)v5 + 19) = v10;
        if ( !v10 )
        {
          v6 = 2147942414LL;
          v7 = -2147024882;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v9 = 226;
            goto LABEL_5;
          }
          goto LABEL_60;
        }
        v11 = 0;
        for ( *((_DWORD *)v5 + 36) = *(_DWORD *)(a1 + 56);
              (unsigned int)v11 < *(_DWORD *)(a1 + 56);
              v11 = (unsigned int)(v11 + 1) )
        {
          *(_WORD *)(*((_QWORD *)v5 + 19) + 4 * v11) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 64) + 4 * v11);
          *(_WORD *)(*((_QWORD *)v5 + 19) + 4 * v11 + 2) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 64) + 4 * v11);
        }
      }
    }
    else if ( *(_WORD *)(a1 + 48) == 58 )
    {
      if ( *(_DWORD *)(a1 + 56) )
      {
        v12 = FwAlloc(4LL * *(unsigned int *)(a1 + 56));
        *((_QWORD *)v5 + 19) = v12;
        if ( !v12 )
        {
          v6 = 2147942414LL;
          v7 = -2147024882;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v9 = 227;
            goto LABEL_5;
          }
          goto LABEL_60;
        }
        v13 = 0;
        for ( *((_DWORD *)v5 + 36) = *(_DWORD *)(a1 + 56);
              (unsigned int)v13 < *(_DWORD *)(a1 + 56);
              v13 = (unsigned int)(v13 + 1) )
        {
          *(_WORD *)(*((_QWORD *)v5 + 19) + 4 * v13) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 64) + 4 * v13);
          *(_WORD *)(*((_QWORD *)v5 + 19) + 4 * v13 + 2) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 64) + 4 * v13);
        }
      }
    }
    else
    {
      v7 = FwArrayCopy(
             4,
             FwCopyPlatform,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             a1 + 64,
             v5 + 72);
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_60;
        v9 = 228;
        goto LABEL_10;
      }
      v7 = FwArrayCopy(
             4,
             FwCopyPlatform,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             a1 + 88,
             v5 + 120);
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_60;
        v9 = 229;
        goto LABEL_10;
      }
    }
    v7 = FwCopyWFAddressesContents(a1 + 104, v5 + 32);
    if ( v7 >= 0 )
    {
      v7 = FwCopyWFAddressesContents(a1 + 176, v5 + 80);
      if ( v7 >= 0 )
      {
        *a2 = v5;
        v5 = 0;
        goto LABEL_60;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v9 = 231;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v9 = 230;
    }
LABEL_10:
    v6 = (unsigned int)v7;
    goto LABEL_5;
  }
  v6 = 2147942414LL;
  v7 = -2147024882;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v9 = 223;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v6);
  }
LABEL_60:
  FwFreeHyperVRulesBySchemaVersion(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007a30  push    rbx
0x180007a32  push    rbp
0x180007a33  push    rsi
0x180007a34  push    rdi
0x180007a35  push    r13
0x180007a37  push    r14
0x180007a39  sub     rsp, 38h
0x180007a3d  mov     rsi, rcx
0x180007a40  mov     qword ptr [rdx], 0
0x180007a47  mov     edi, 128h
0x180007a4c  mov     r14, rdx
0x180007a4f  mov     ecx, edi
0x180007a51  call    cs:__imp_FwAlloc
0x180007a57  mov     rbx, rax
0x180007a5a  mov     r13d, 221h
0x180007a60  test    rax, rax
0x180007a63  jnz     short loc_180007AAC
0x180007a65  mov     r9d, 8007000Eh
0x180007a6b  mov     edi, r9d
0x180007a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a75  lea     rax, WPP_GLOBAL_Control
0x180007a7c  cmp     rcx, rax
0x180007a7f  jz      loc_180007E5F
0x180007a85  lea     ebp, [rbx+1]
0x180007a88  test    [rcx+1Ch], bpl
0x180007a8c  jz      loc_180007E5F
0x180007a92  mov     edx, 0DFh
0x180007a97  mov     rcx, [rcx+10h]
0x180007a9b  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180007aa2  call    WPP_SF_d
0x180007aa7  jmp     loc_180007E5F
0x180007aac  mov     r8, rdi; Size
0x180007aaf  xor     edx, edx; Val
0x180007ab1  mov     rcx, rbx; void *
0x180007ab4  call    memset_0
0x180007ab9  xorps   xmm0, xmm0
0x180007abc  mov     [rbx+8], r13w
0x180007ac1  movdqu  xmmword ptr [rbx+110h], xmm0
0x180007ac9  mov     ebp, 1
0x180007ace  lea     rdx, [rbx+10h]
0x180007ad2  mov     [rbx+108h], ebp
0x180007ad8  mov     rcx, [rsi+10h]
0x180007adc  call    cs:__imp_FwStringCopy
0x180007ae2  mov     edi, eax
0x180007ae4  test    eax, eax
0x180007ae6  jns     short loc_180007B13
0x180007ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007aef  lea     rax, WPP_GLOBAL_Control
0x180007af6  cmp     rcx, rax
0x180007af9  jz      loc_180007E5F
0x180007aff  test    [rcx+1Ch], bpl
0x180007b03  jz      loc_180007E5F
0x180007b09  mov     edx, 0E0h
0x180007b0e  mov     r9d, edi
0x180007b11  jmp     short loc_180007A97
0x180007b13  mov     rcx, [rsi+18h]
0x180007b17  lea     rdx, [rbx+18h]
0x180007b1b  call    cs:__imp_FwStringCopy
0x180007b21  mov     edi, eax
0x180007b23  test    eax, eax
0x180007b25  jns     short loc_180007B4F
0x180007b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b2e  lea     rax, WPP_GLOBAL_Control
0x180007b35  cmp     rcx, rax
0x180007b38  jz      loc_180007E5F
0x180007b3e  test    [rcx+1Ch], bpl
0x180007b42  jz      loc_180007E5F
0x180007b48  mov     edx, 0E1h
0x180007b4d  jmp     short loc_180007B0E
0x180007b4f  mov     eax, [rsi+2Ch]
0x180007b52  mov     [rbx+24h], eax
0x180007b55  movzx   eax, word ptr [rsi+30h]
0x180007b59  mov     [rbx+38h], ax
0x180007b5d  mov     eax, [rsi+120h]
0x180007b63  mov     [rbx+100h], eax
0x180007b69  mov     eax, [rsi+28h]
0x180007b6c  mov     [rbx+120h], eax
0x180007b72  test    [rsi+124h], bpl
0x180007b79  jz      short loc_180007B82
0x180007b7b  mov     [rbx+104h], bp
0x180007b82  mov     ecx, [rsi+154h]
0x180007b88  sub     ecx, ebp
0x180007b8a  jz      short loc_180007BCE
0x180007b8c  sub     ecx, ebp
0x180007b8e  jz      short loc_180007BC2
0x180007b90  sub     ecx, ebp
0x180007b92  jz      short loc_180007BB6
0x180007b94  cmp     ecx, 3
0x180007b97  jz      short loc_180007BAA
0x180007b99  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007b9e  mov     dword ptr [rbx+10Ch], 0
0x180007ba8  jmp     short loc_180007BD8
0x180007baa  mov     dword ptr [rbx+10Ch], 0Bh
0x180007bb4  jmp     short loc_180007BD8
0x180007bb6  mov     dword ptr [rbx+10Ch], 0Ah
0x180007bc0  jmp     short loc_180007BD8
0x180007bc2  mov     dword ptr [rbx+10Ch], 9
0x180007bcc  jmp     short loc_180007BD8
0x180007bce  mov     dword ptr [rbx+10Ch], 8
0x180007bd8  cmp     [rsi+30h], bp
0x180007bdc  jnz     loc_180007CC1
0x180007be2  cmp     dword ptr [rsi+38h], 0
0x180007be6  jbe     loc_180007C7F
0x180007bec  mov     ecx, [rsi+38h]
0x180007bef  shl     rcx, 2
0x180007bf3  call    cs:__imp_FwAlloc
0x180007bf9  mov     [rbx+98h], rax
0x180007c00  test    rax, rax
0x180007c03  jnz     short loc_180007C39
0x180007c05  mov     r9d, 8007000Eh
0x180007c0b  mov     edi, r9d
0x180007c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c15  lea     rax, WPP_GLOBAL_Control
0x180007c1c  cmp     rcx, rax
0x180007c1f  jz      loc_180007E5F
0x180007c25  test    [rcx+1Ch], bpl
0x180007c29  jz      loc_180007E5F
0x180007c2f  mov     edx, 0E2h
0x180007c34  jmp     loc_180007A97
0x180007c39  mov     eax, [rsi+38h]
0x180007c3c  xor     r8d, r8d
0x180007c3f  mov     [rbx+90h], eax
0x180007c45  cmp     [rsi+38h], r8d
0x180007c49  jbe     short loc_180007C7F
0x180007c4b  mov     rax, [rsi+40h]
0x180007c4f  movzx   ecx, byte ptr [rax+r8*4]
0x180007c54  mov     rax, [rbx+98h]
0x180007c5b  mov     [rax+r8*4], cx
0x180007c60  mov     rax, [rsi+40h]
0x180007c64  movzx   ecx, byte ptr [rax+r8*4]
0x180007c69  mov     rax, [rbx+98h]
0x180007c70  mov     [rax+r8*4+2], cx
0x180007c76  add     r8d, ebp
0x180007c79  cmp     r8d, [rsi+38h]
0x180007c7d  jb      short loc_180007C4B
0x180007c7f  lea     rdx, [rbx+40h]
0x180007c83  lea     rcx, [rsi+68h]
0x180007c87  call    FwCopyWFAddressesContents
0x180007c8c  mov     edi, eax
0x180007c8e  test    eax, eax
0x180007c90  jns     loc_180007E1E
0x180007c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c9d  lea     rax, WPP_GLOBAL_Control
0x180007ca4  cmp     rcx, rax
0x180007ca7  jz      loc_180007E5F
0x180007cad  test    [rcx+1Ch], bpl
0x180007cb1  jz      loc_180007E5F
0x180007cb7  mov     edx, 0E6h
0x180007cbc  jmp     loc_180007B0E
0x180007cc1  cmp     word ptr [rsi+30h], 3Ah ; ':'
0x180007cc6  jnz     loc_180007D6E
0x180007ccc  cmp     dword ptr [rsi+38h], 0
0x180007cd0  jbe     short loc_180007C7F
0x180007cd2  mov     ecx, [rsi+38h]
0x180007cd5  shl     rcx, 2
0x180007cd9  call    cs:__imp_FwAlloc
0x180007cdf  mov     [rbx+98h], rax
0x180007ce6  test    rax, rax
0x180007ce9  jnz     short loc_180007D1F
0x180007ceb  mov     r9d, 8007000Eh
0x180007cf1  mov     edi, r9d
0x180007cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cfb  lea     rax, WPP_GLOBAL_Control
0x180007d02  cmp     rcx, rax
0x180007d05  jz      loc_180007E5F
0x180007d0b  test    [rcx+1Ch], bpl
0x180007d0f  jz      loc_180007E5F
0x180007d15  mov     edx, 0E3h
0x180007d1a  jmp     loc_180007A97
0x180007d1f  mov     eax, [rsi+38h]
0x180007d22  xor     r8d, r8d
0x180007d25  mov     [rbx+90h], eax
0x180007d2b  cmp     [rsi+38h], r8d
0x180007d2f  jbe     loc_180007C7F
0x180007d35  mov     rax, [rsi+40h]
0x180007d39  movzx   ecx, byte ptr [rax+r8*4]
0x180007d3e  mov     rax, [rbx+98h]
0x180007d45  mov     [rax+r8*4], cx
0x180007d4a  mov     rax, [rsi+40h]
0x180007d4e  movzx   ecx, byte ptr [rax+r8*4]
0x180007d53  mov     rax, [rbx+98h]
0x180007d5a  mov     [rax+r8*4+2], cx
0x180007d60  add     r8d, ebp
0x180007d63  cmp     r8d, [rsi+38h]
0x180007d67  jb      short loc_180007D35
0x180007d69  jmp     loc_180007C7F
0x180007d6e  lea     rax, [rbx+90h]
0x180007d75  mov     ecx, 4
0x180007d7a  lea     r9, [rsi+40h]
0x180007d7e  mov     [rsp+68h+var_48], rax
0x180007d83  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007d8a  lea     rdx, FwCopyPlatform
0x180007d91  call    cs:__imp_FwArrayCopy
0x180007d97  mov     edi, eax
0x180007d99  test    eax, eax
0x180007d9b  jns     short loc_180007DC8
0x180007d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007da4  lea     rax, WPP_GLOBAL_Control
0x180007dab  cmp     rcx, rax
0x180007dae  jz      loc_180007E5F
0x180007db4  test    [rcx+1Ch], bpl
0x180007db8  jz      loc_180007E5F
0x180007dbe  mov     edx, 0E4h
0x180007dc3  jmp     loc_180007B0E
0x180007dc8  lea     rax, [rbx+0F0h]
0x180007dcf  mov     ecx, 4
0x180007dd4  lea     r9, [rsi+58h]
0x180007dd8  mov     [rsp+68h+var_48], rax
0x180007ddd  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007de4  lea     rdx, FwCopyPlatform
0x180007deb  call    cs:__imp_FwArrayCopy
0x180007df1  mov     edi, eax
0x180007df3  test    eax, eax
0x180007df5  jns     loc_180007C7F
0x180007dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e02  lea     rax, WPP_GLOBAL_Control
0x180007e09  cmp     rcx, rax
0x180007e0c  jz      short loc_180007E5F
0x180007e0e  test    [rcx+1Ch], bpl
0x180007e12  jz      short loc_180007E5F
0x180007e14  mov     edx, 0E5h
0x180007e19  jmp     loc_180007B0E
0x180007e1e  lea     rdx, [rbx+0A0h]
0x180007e25  lea     rcx, [rsi+0B0h]
0x180007e2c  call    FwCopyWFAddressesContents
0x180007e31  mov     edi, eax
0x180007e33  test    eax, eax
0x180007e35  jns     short loc_180007E5A
0x180007e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e3e  lea     rax, WPP_GLOBAL_Control
0x180007e45  cmp     rcx, rax
0x180007e48  jz      short loc_180007E5F
0x180007e4a  test    [rcx+1Ch], bpl
0x180007e4e  jz      short loc_180007E5F
0x180007e50  mov     edx, 0E7h
0x180007e55  jmp     loc_180007B0E
0x180007e5a  mov     [r14], rbx
0x180007e5d  xor     ebx, ebx
0x180007e5f  mov     edx, r13d
0x180007e62  mov     rcx, rbx; void *
0x180007e65  call    FwFreeHyperVRulesBySchemaVersion
0x180007e6a  mov     eax, edi
0x180007e6c  add     rsp, 38h
0x180007e70  pop     r14
0x180007e72  pop     r13
0x180007e74  pop     rdi
0x180007e75  pop     rsi
0x180007e76  pop     rbp
0x180007e77  pop     rbx
0x180007e78  retn
```
