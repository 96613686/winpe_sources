# imp_ApxVolumeCreate

- ea: `0x18001b830`
- end: `0x18001bbd4`
- name: `imp_ApxVolumeCreate`
- size: `932`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_VOLUME_CONFIG *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x18000be74`
- `0x18000d210`
- `0x18001b340`
- `0x18001b830`

## string_xrefs

- `0x18001b8d9`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxVolumeCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_VOLUME_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  struct Apx::ApfVolume *v8; // rsi
  Apx::ApfVerify *v9; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  _QWORD *v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  struct Apx::ApfVolume *v20; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids);
  }
  v8 = 0;
  v20 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsApxInitialized(v9);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v11);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v12);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v13);
  if ( IsNull < 0 )
    goto LABEL_59;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Volume", v14);
  if ( IsNull < 0 )
    goto LABEL_59;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 48 )
  {
    v16 = *((_DWORD *)a3 + 4);
    if ( v16 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids, v16, 0);
      goto LABEL_59;
    }
    v17 = *((_QWORD *)a3 + 5);
    if ( !v17 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      v18 = 13;
LABEL_27:
      WPP_SF_d(v15[2], v18, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids);
LABEL_59:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    if ( *(_DWORD *)v17 != 24 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids,
        24,
        *(_DWORD *)v17);
      goto LABEL_59;
    }
    if ( *(_QWORD *)(v17 + 16) && *(_QWORD *)(v17 + 8) )
    {
      if ( *((_DWORD *)a3 + 1) != -1 )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        v18 = 16;
        goto LABEL_27;
      }
      if ( !*((_DWORD *)a3 + 5) )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        v18 = 17;
        goto LABEL_27;
      }
      if ( *((_DWORD *)a3 + 5) > 0xFFFFu )
      {
        IsNull = -2147024809;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)IsNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_60;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids);
        goto LABEL_59;
      }
      IsNull = Apx::ApfVolume::_CreateAndInitialize(a3, &v20);
      if ( IsNull >= 0 )
      {
        IsNull = 0;
        *(_QWORD *)a4 = ~(unsigned __int64)v20;
        goto LABEL_59;
      }
      v8 = v20;
    }
    else
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids);
    }
    if ( v8 )
      imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v8);
    goto LABEL_59;
  }
  IsNull = -2147024809;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids,
      48,
      *(_DWORD *)a3);
    goto LABEL_59;
  }
LABEL_60:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(v15[2], 19, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x18001b830  push    rbx
0x18001b832  push    rbp
0x18001b833  push    rsi
0x18001b834  push    rdi
0x18001b835  push    r13
0x18001b837  push    r14
0x18001b839  push    r15
0x18001b83b  sub     rsp, 40h
0x18001b83f  mov     r14, r9
0x18001b842  mov     rdi, r8
0x18001b845  mov     r15, rdx
0x18001b848  mov     rbp, rcx
0x18001b84b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b852  lea     r13, WPP_GLOBAL_Control
0x18001b859  cmp     rcx, r13
0x18001b85c  jz      short loc_18001B87F
0x18001b85e  test    byte ptr [rcx+1Ch], 1
0x18001b862  jz      short loc_18001B87F
0x18001b864  cmp     byte ptr [rcx+19h], 5
0x18001b868  jb      short loc_18001B87F
0x18001b86a  mov     rcx, [rcx+10h]
0x18001b86e  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001b875  mov     edx, 0Ah
0x18001b87a  call    WPP_SF_
0x18001b87f  xor     esi, esi
0x18001b881  lea     rdx, aGlobals; "Globals"
0x18001b888  mov     rcx, rbp; this
0x18001b88b  mov     [rsp+78h+var_48], rsi
0x18001b890  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001b895  mov     ebx, eax
0x18001b897  test    eax, eax
0x18001b899  js      loc_18001BB96
0x18001b89f  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x18001b8a4  mov     ebx, eax
0x18001b8a6  test    eax, eax
0x18001b8a8  js      loc_18001BB96
0x18001b8ae  mov     rcx, rbp; this
0x18001b8b1  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18001b8b6  mov     ebx, eax
0x18001b8b8  test    eax, eax
0x18001b8ba  js      loc_18001BB96
0x18001b8c0  lea     rdx, aAttributes; "Attributes"
0x18001b8c7  mov     rcx, r15; this
0x18001b8ca  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001b8cf  mov     ebx, eax
0x18001b8d1  test    eax, eax
0x18001b8d3  js      loc_18001BB96
0x18001b8d9  lea     rdx, aConfig_0; "Config"
0x18001b8e0  mov     rcx, rdi; this
0x18001b8e3  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001b8e8  mov     ebx, eax
0x18001b8ea  test    eax, eax
0x18001b8ec  js      loc_18001BB96
0x18001b8f2  lea     rdx, aVolume; "Volume"
0x18001b8f9  mov     rcx, r14; this
0x18001b8fc  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001b901  mov     ebx, eax
0x18001b903  test    eax, eax
0x18001b905  js      loc_18001BB96
0x18001b90b  mov     [r14], rsi
0x18001b90e  mov     eax, [rdi]
0x18001b910  cmp     eax, 30h ; '0'
0x18001b913  jz      short loc_18001B95E
0x18001b915  mov     ebx, 80070057h
0x18001b91a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b921  cmp     rcx, r13
0x18001b924  jz      loc_18001BBC3
0x18001b92a  test    byte ptr [rcx+1Ch], 40h
0x18001b92e  jz      loc_18001BB9D
0x18001b934  cmp     byte ptr [rcx+19h], 2
0x18001b938  jb      loc_18001BB9D
0x18001b93e  lea     edx, [rsi+0Bh]
0x18001b941  mov     [rsp+78h+var_58], eax
0x18001b945  lea     r9d, [rsi+30h]
0x18001b949  mov     rcx, [rcx+10h]
0x18001b94d  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001b954  call    WPP_SF_DDd
0x18001b959  jmp     loc_18001BB96
0x18001b95e  mov     eax, [rdi+10h]
0x18001b961  test    eax, eax
0x18001b963  jz      short loc_18001B9AF
0x18001b965  mov     ebx, 80070057h
0x18001b96a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b971  cmp     rcx, r13
0x18001b974  jz      loc_18001BBC3
0x18001b97a  test    byte ptr [rcx+1Ch], 40h
0x18001b97e  jz      loc_18001BB9D
0x18001b984  cmp     byte ptr [rcx+19h], 2
0x18001b988  jb      loc_18001BB9D
0x18001b98e  mov     rcx, [rcx+10h]
0x18001b992  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001b999  mov     edx, 0Ch
0x18001b99e  mov     [rsp+78h+var_58], esi
0x18001b9a2  mov     r9d, eax
0x18001b9a5  call    WPP_SF_DDd
0x18001b9aa  jmp     loc_18001BB96
0x18001b9af  mov     rax, [rdi+28h]
0x18001b9b3  test    rax, rax
0x18001b9b6  jnz     short loc_18001B9FD
0x18001b9b8  mov     r9d, 80070057h
0x18001b9be  mov     ebx, r9d
0x18001b9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9c8  cmp     rcx, r13
0x18001b9cb  jz      loc_18001BBC3
0x18001b9d1  test    byte ptr [rcx+1Ch], 40h
0x18001b9d5  jz      loc_18001BB9D
0x18001b9db  cmp     byte ptr [rcx+19h], 2
0x18001b9df  jb      loc_18001BB9D
0x18001b9e5  lea     edx, [rax+0Dh]
0x18001b9e8  mov     rcx, [rcx+10h]
0x18001b9ec  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001b9f3  call    WPP_SF_d
0x18001b9f8  jmp     loc_18001BB96
0x18001b9fd  mov     r8d, [rax]
0x18001ba00  cmp     r8d, 18h
0x18001ba04  jz      short loc_18001BA42
0x18001ba06  mov     ebx, 80070057h
0x18001ba0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba12  cmp     rcx, r13
0x18001ba15  jz      loc_18001BBC3
0x18001ba1b  test    byte ptr [rcx+1Ch], 40h
0x18001ba1f  jz      loc_18001BB9D
0x18001ba25  cmp     byte ptr [rcx+19h], 2
0x18001ba29  jb      loc_18001BB9D
0x18001ba2f  mov     edx, 0Eh
0x18001ba34  mov     [rsp+78h+var_58], r8d
0x18001ba39  lea     r9d, [rdx+0Ah]
0x18001ba3d  jmp     loc_18001B949
0x18001ba42  cmp     [rax+10h], rsi
0x18001ba46  jz      loc_18001BB4E
0x18001ba4c  cmp     [rax+8], rsi
0x18001ba50  jz      loc_18001BB4E
0x18001ba56  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x18001ba5a  jz      short loc_18001BA93
0x18001ba5c  mov     r9d, 80070057h
0x18001ba62  mov     ebx, r9d
0x18001ba65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba6c  cmp     rcx, r13
0x18001ba6f  jz      loc_18001BBC3
0x18001ba75  test    byte ptr [rcx+1Ch], 40h
0x18001ba79  jz      loc_18001BB9D
0x18001ba7f  cmp     byte ptr [rcx+19h], 2
0x18001ba83  jb      loc_18001BB9D
0x18001ba89  mov     edx, 10h
0x18001ba8e  jmp     loc_18001B9E8
0x18001ba93  cmp     [rdi+14h], esi
0x18001ba96  jnz     short loc_18001BACF
0x18001ba98  mov     r9d, 80070057h
0x18001ba9e  mov     ebx, r9d
0x18001baa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baa8  cmp     rcx, r13
0x18001baab  jz      loc_18001BBC3
0x18001bab1  test    byte ptr [rcx+1Ch], 40h
0x18001bab5  jz      loc_18001BB9D
0x18001babb  cmp     byte ptr [rcx+19h], 2
0x18001babf  jb      loc_18001BB9D
0x18001bac5  mov     edx, 11h
0x18001baca  jmp     loc_18001B9E8
0x18001bacf  mov     eax, 0FFFFh
0x18001bad4  cmp     [rdi+14h], eax
0x18001bad7  jbe     short loc_18001BB25
0x18001bad9  mov     r9d, 80070057h
0x18001badf  mov     ebx, r9d
0x18001bae2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bae9  cmp     rcx, r13
0x18001baec  jz      loc_18001BBC3
0x18001baf2  test    byte ptr [rcx+1Ch], 40h
0x18001baf6  jz      loc_18001BB9D
0x18001bafc  cmp     byte ptr [rcx+19h], 2
0x18001bb00  jb      loc_18001BB9D
0x18001bb06  mov     rcx, [rcx+10h]
0x18001bb0a  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001bb11  mov     [rsp+78h+var_58], r9d
0x18001bb16  mov     edx, 12h
0x18001bb1b  mov     r9d, eax
0x18001bb1e  call    WPP_SF_dd
0x18001bb23  jmp     short loc_18001BB96
0x18001bb25  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfVolume **
0x18001bb2a  mov     rcx, rdi; struct _APX_VOLUME_CONFIG *
0x18001bb2d  call    ?_CreateAndInitialize@ApfVolume@Apx@@SAJPEAU_APX_VOLUME_CONFIG@@PEAPEAV12@@Z; Apx::ApfVolume::_CreateAndInitialize(_APX_VOLUME_CONFIG *,Apx::ApfVolume * *)
0x18001bb32  mov     ebx, eax
0x18001bb34  test    eax, eax
0x18001bb36  js      short loc_18001BB47
0x18001bb38  mov     rax, [rsp+78h+var_48]
0x18001bb3d  xor     ebx, ebx
0x18001bb3f  not     rax
0x18001bb42  mov     [r14], rax
0x18001bb45  jmp     short loc_18001BB96
0x18001bb47  mov     rsi, [rsp+78h+var_48]
0x18001bb4c  jmp     short loc_18001BB84
0x18001bb4e  mov     r9d, 80070057h
0x18001bb54  mov     ebx, r9d
0x18001bb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb5e  cmp     rcx, r13
0x18001bb61  jz      short loc_18001BBC3
0x18001bb63  test    byte ptr [rcx+1Ch], 40h
0x18001bb67  jz      short loc_18001BB9D
0x18001bb69  cmp     byte ptr [rcx+19h], 2
0x18001bb6d  jb      short loc_18001BB9D
0x18001bb6f  mov     rcx, [rcx+10h]
0x18001bb73  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001bb7a  mov     edx, 0Fh
0x18001bb7f  call    WPP_SF_d
0x18001bb84  test    rsi, rsi
0x18001bb87  jz      short loc_18001BB96
0x18001bb89  not     rsi
0x18001bb8c  xor     ecx, ecx; this
0x18001bb8e  mov     rdx, rsi; Apx::ApfVerify *
0x18001bb91  call    imp_ApxObjectDelete
0x18001bb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb9d  cmp     rcx, r13
0x18001bba0  jz      short loc_18001BBC3
0x18001bba2  test    byte ptr [rcx+1Ch], 1
0x18001bba6  jz      short loc_18001BBC3
0x18001bba8  cmp     byte ptr [rcx+19h], 5
0x18001bbac  jb      short loc_18001BBC3
0x18001bbae  mov     rcx, [rcx+10h]
0x18001bbb2  lea     r8, WPP_21c43db2bc80321e71d6f92086c2d3ef_Traceguids
0x18001bbb9  mov     edx, 13h
0x18001bbbe  call    WPP_SF_
0x18001bbc3  mov     eax, ebx
0x18001bbc5  add     rsp, 40h
0x18001bbc9  pop     r15
0x18001bbcb  pop     r14
0x18001bbcd  pop     r13
0x18001bbcf  pop     rdi
0x18001bbd0  pop     rsi
0x18001bbd1  pop     rbp
0x18001bbd2  pop     rbx
0x18001bbd3  retn
```
