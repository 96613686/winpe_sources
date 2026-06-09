# VARIANT_UserUnmarshal

- ea: `0x18001cfb0`
- end: `0x18001d72b`
- name: `VARIANT_UserUnmarshal`
- size: `1915`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, VARIANT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001cfb0`
- `0x18001e030`

## callees

- `0x18000bcb0`
- `0x18001ac58`
- `0x18001c6e0`
- `0x18001cfb0`
- `0x18001d734`
- `0x18001dec0`
- `0x18001e030`
- `0x180020860`
- `0x180021dc0`
- `0x18004dd00`
- `0x18004e530`
- `0x18009b1d0`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserUnmarshal` at `0x18001d35b`
- `combase!WdtpInterfacePointer_UserUnmarshal` at `0x18001d35b`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x18001d04d`
- `combase!__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding` at `0x18001d04d`
- `RPCRT4!RpcRaiseException` at `0x18001d043`
- `RPCRT4!RpcRaiseException` at `0x18001d1a2`
- `RPCRT4!RpcRaiseException` at `0x18001d23e`
- `RPCRT4!RpcRaiseException` at `0x18001d5d4`
- `RPCRT4!RpcRaiseException` at `0x18001d5e0`
- `RPCRT4!RpcRaiseException` at `0x18001d609`
- `RPCRT4!RpcRaiseException` at `0x18001d641`
- `RPCRT4!RpcRaiseException` at `0x18001d043`
- `RPCRT4!RpcRaiseException` at `0x18001d1a2`
- `RPCRT4!RpcRaiseException` at `0x18001d23e`
- `RPCRT4!RpcRaiseException` at `0x18001d5d4`
- `RPCRT4!RpcRaiseException` at `0x18001d5e0`
- `RPCRT4!RpcRaiseException` at `0x18001d609`
- `RPCRT4!RpcRaiseException` at `0x18001d641`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001cff3`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001cff3`

## pseudocode

```c
unsigned __int8 *__stdcall VARIANT_UserUnmarshal(unsigned int *a1, unsigned __int8 *a2, VARIANT *a3)
{
  RPC_STATUS UserMarshalInfo; // eax
  unsigned __int64 BufferSize; // rbp
  unsigned __int64 Buffer; // rdi
  VARTYPE *v9; // rbx
  unsigned __int64 v10; // r12
  VARTYPE vt; // r15
  VARTYPE v13; // si
  __int16 v14; // dx
  VARTYPE *v15; // rbx
  WORD v16; // ax
  struct tagSAFEARRAY **p_parray; // rsi
  __int16 v18; // ax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int SafeArrayDiscr; // eax
  unsigned int v22; // eax
  GUID *v23; // r9
  unsigned __int8 *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // r12d
  struct tagSAFEARRAY **v28; // rax
  unsigned __int64 v29; // rdx
  struct tagSAFEARRAY *v30; // rax
  unsigned __int64 v31; // rbx
  struct tagSAFEARRAY *v32; // rax
  char v33; // al
  unsigned __int64 v34; // rbx
  __int128 v35; // xmm0
  unsigned int v36; // eax
  NDR_USER_MARSHAL_INFO pMarshalInfo; // [rsp+30h] [rbp-A8h] BYREF
  __int16 v38; // [rsp+F0h] [rbp+18h]

  if ( !a3 )
    return a2;
  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  UserMarshalInfo = NdrGetUserMarshalInfo(a1, 1u, &pMarshalInfo);
  if ( UserMarshalInfo )
    RpcRaiseException(UserMarshalInfo);
  BufferSize = pMarshalInfo.Level1.BufferSize;
  Buffer = (unsigned __int64)pMarshalInfo.Level1.Buffer;
  Variant_ValidateBuffer(a1, a2, 0);
  if ( BufferSize < 2 )
    goto LABEL_6;
  v9 = (VARTYPE *)(((unsigned __int64)(a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8);
  if ( (unsigned __int64)v9 < Buffer )
    goto LABEL_6;
  v10 = BufferSize - 2;
  if ( BufferSize - 2 < (unsigned __int64)v9 - Buffer )
    goto LABEL_6;
  vt = a3->vt;
  v13 = *v9;
  if ( (a3->vt & 0x4000) != 0 )
  {
    if ( vt != v13 )
      RpcRaiseException(-2147024809);
    v14 = 0x4000;
  }
  else
  {
    VariantClear(a3);
    *(_OWORD *)&a3->vt = 0;
    a3->pRecInfo = 0;
    v14 = 0;
    a3->vt = v13;
    vt = v13;
  }
  v38 = v14;
  if ( BufferSize < 6 )
    goto LABEL_6;
  v15 = v9 + 1;
  if ( (unsigned __int64)v15 < Buffer || BufferSize - 6 < (unsigned __int64)v15 - Buffer )
    goto LABEL_6;
  a3->wReserved1 = *v15;
  a3->wReserved2 = v15[1];
  v16 = v15[2];
  a2 = (unsigned __int8 *)(v15 + 5);
  a3->wReserved3 = v16;
  if ( (vt & 0x2000) != 0 )
    vt &= 0x6000u;
  if ( (vt & 0x4000) == 0 )
  {
    if ( vt == 14 )
    {
      p_parray = (struct tagSAFEARRAY **)a3;
    }
    else
    {
      if ( vt == 12 )
        goto LABEL_6;
      p_parray = &a3->parray;
    }
    *p_parray = 0;
    goto LABEL_22;
  }
  p_parray = 0;
  vt &= ~0x4000u;
  if ( vt == 36 )
    goto LABEL_22;
  if ( v14 != 0x4000 )
  {
    if ( (unsigned __int64)a2 < Buffer || BufferSize - 4 < (unsigned __int64)&a2[-Buffer] )
      goto LABEL_6;
    if ( vt != 8 && vt != 9 )
    {
      if ( vt == 12 )
      {
        v26 = 24;
LABEL_82:
        v27 = v26;
        v28 = (struct tagSAFEARRAY **)operator new[](v26);
        p_parray = v28;
        if ( !v28 )
          RpcRaiseException(-2147024882);
        a2 += 4;
        memset_0(v28, 0, v27);
        a3->llVal = (LONGLONG)p_parray;
        v10 = BufferSize - 2;
        goto LABEL_22;
      }
      if ( vt != 13 && vt != 20 && vt != 21 && vt != 37 && vt != 38 && vt != 0x2000 )
      {
        v26 = *(_DWORD *)a2;
        if ( !*(_DWORD *)a2 )
          goto LABEL_6;
        goto LABEL_82;
      }
    }
    v26 = 8;
    goto LABEL_82;
  }
  p_parray = a3->pparray;
  if ( !p_parray )
    goto LABEL_46;
  a2 += 4;
LABEL_22:
  if ( vt == 0x2000 )
  {
    if ( (a3->vt & 0x9FFF) == 0x48 )
      a3->vt &= 0xFFB7u;
    if ( (unsigned __int64)a2 < Buffer || BufferSize - 4 < (unsigned __int64)&a2[-Buffer] )
      goto LABEL_6;
    v20 = *(_DWORD *)a2;
    a2 += 4;
    if ( v20 )
    {
      a2 = (unsigned __int8 *)LPSAFEARRAY_Unmarshal(a1, a2);
      if ( *p_parray )
      {
        SafeArrayDiscr = GetSafeArrayDiscr(*p_parray, a1);
        if ( (a3->vt & 0xFFF) == 0xC && SafeArrayDiscr != 12 )
          a3->vt = SafeArrayDiscr | a3->vt & 0xFFF3;
      }
      goto LABEL_30;
    }
    _SafeArrayDestroy(*p_parray, 1);
    goto LABEL_69;
  }
  if ( vt > 0x2000u )
    goto LABEL_121;
  if ( vt > 0xDu )
  {
    if ( vt <= 0x15u )
    {
      if ( vt != 21 )
      {
        switch ( vt )
        {
          case 0xEu:
            if ( BufferSize < 0x10 )
              goto LABEL_6;
            v34 = (unsigned __int64)(a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            if ( v34 < Buffer || BufferSize - 16 < v34 - Buffer )
              goto LABEL_6;
            v35 = *(_OWORD *)v34;
            a2 = (unsigned __int8 *)(v34 + 16);
            *(_OWORD *)p_parray = v35;
            goto LABEL_30;
          case 0x10u:
          case 0x11u:
            if ( (unsigned __int64)a2 < Buffer || BufferSize - 1 < (unsigned __int64)&a2[-Buffer] )
              goto LABEL_6;
            v33 = *a2++;
            *(_BYTE *)p_parray = v33;
            goto LABEL_30;
          case 0x12u:
            goto LABEL_40;
          case 0x13u:
            goto LABEL_47;
        }
        if ( vt != 20 )
          goto LABEL_121;
      }
      if ( BufferSize < 8 )
        goto LABEL_6;
      v29 = (unsigned __int64)(a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( v29 < Buffer || BufferSize - 8 < v29 - Buffer )
        goto LABEL_6;
      v30 = *(struct tagSAFEARRAY **)v29;
      a2 = (unsigned __int8 *)(v29 + 8);
LABEL_91:
      *p_parray = v30;
      goto LABEL_30;
    }
    if ( vt == 22 || vt == 23 )
      goto LABEL_47;
    if ( vt != 36 )
    {
      if ( (unsigned int)vt - 37 > 1 )
        goto LABEL_121;
      if ( (unsigned __int64)a2 < Buffer || BufferSize - 4 < (unsigned __int64)&a2[-Buffer] )
        goto LABEL_6;
      v30 = (struct tagSAFEARRAY *)*(int *)a2;
      a2 += 4;
      goto LABEL_91;
    }
    if ( v38 != 0x4000 || a3->pRecInfo && a3->llVal )
    {
      if ( (unsigned __int64)a2 < Buffer || BufferSize - 4 < (unsigned __int64)&a2[-Buffer] )
        goto LABEL_6;
      v36 = *(_DWORD *)a2;
      a2 += 4;
      if ( !v36 )
        goto LABEL_30;
      v24 = (unsigned __int8 *)BRECORD_UserUnmarshal(a1, a2, 1u, (__int64)&a3->llVal);
LABEL_65:
      a2 = v24;
      goto LABEL_30;
    }
LABEL_46:
    RpcRaiseException(1780);
  }
  if ( vt == 13 )
    goto LABEL_59;
  if ( vt <= 6u )
  {
    if ( vt == 6 )
      goto LABEL_92;
    if ( !vt || vt == 1 )
      goto LABEL_30;
    if ( vt != 2 )
    {
      if ( vt != 3 && vt != 4 )
      {
        if ( vt != 5 )
          goto LABEL_121;
LABEL_92:
        if ( BufferSize >= 8 )
        {
          v31 = (unsigned __int64)(a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v31 >= Buffer && BufferSize - 8 >= v31 - Buffer )
          {
            v32 = *(struct tagSAFEARRAY **)v31;
            a2 = (unsigned __int8 *)(v31 + 8);
            *p_parray = v32;
            goto LABEL_30;
          }
        }
LABEL_6:
        RpcRaiseException(1783);
      }
LABEL_47:
      if ( (unsigned __int64)a2 >= Buffer && BufferSize - 4 >= (unsigned __int64)&a2[-Buffer] )
      {
        v19 = *(_DWORD *)a2;
        a2 += 4;
        *(_DWORD *)p_parray = v19;
        goto LABEL_30;
      }
      goto LABEL_6;
    }
LABEL_40:
    if ( (unsigned __int64)a2 >= Buffer && v10 >= (unsigned __int64)&a2[-Buffer] )
    {
      v18 = *(_WORD *)a2;
      a2 += 2;
      *(_WORD *)p_parray = v18;
      goto LABEL_30;
    }
    goto LABEL_6;
  }
  if ( vt == 7 )
    goto LABEL_92;
  if ( vt == 8 )
  {
    v25 = *(_DWORD *)a2;
    a2 += 4;
    if ( v25 )
    {
      v24 = BSTR_UserUnmarshal(a1, a2, (BSTR *)p_parray);
      goto LABEL_65;
    }
    SysFreeString(&(*p_parray)->cDims);
LABEL_69:
    *p_parray = 0;
    goto LABEL_30;
  }
  if ( vt != 9 )
  {
    switch ( vt )
    {
      case 0xAu:
        goto LABEL_47;
      case 0xBu:
        goto LABEL_40;
      case 0xCu:
        v24 = VARIANT_UserUnmarshal(a1, a2 + 4, (VARIANT *)p_parray);
        goto LABEL_65;
    }
LABEL_121:
    RpcRaiseException(-2147352568);
  }
LABEL_59:
  if ( (unsigned __int64)a2 < Buffer || BufferSize - 4 < (unsigned __int64)&a2[-Buffer] )
    goto LABEL_6;
  v22 = *(_DWORD *)a2;
  a2 += 4;
  if ( v22 )
  {
    v23 = &IID_IUnknown;
    if ( vt != 13 )
      v23 = &IID_IDispatch;
    v24 = (unsigned __int8 *)WdtpInterfacePointer_UserUnmarshal(a1, a2, p_parray, v23);
    goto LABEL_65;
  }
  if ( *p_parray )
  {
    (*(void (__fastcall **)(struct tagSAFEARRAY *, __int64, __int64))(*(_QWORD *)&(*p_parray)->cDims + 16LL))(
      *p_parray,
      13,
      0x4000);
    goto LABEL_69;
  }
LABEL_30:
  if ( (unsigned __int64)a2 < Buffer || BufferSize < (unsigned __int64)&a2[-Buffer] )
  {
    VARIANT_UserFree(a1, a3);
    RpcRaiseException(1783);
  }
  if ( (unsigned int)CoDoesOtherSideVariantMarshalingNeedTrailingPadding(a1) )
    return (unsigned __int8 *)((unsigned __int64)(a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  return a2;
}

```

## disassembly

```asm
0x18001cfb0  push    rbx
0x18001cfb2  push    rbp
0x18001cfb3  push    rsi
0x18001cfb4  push    rdi
0x18001cfb5  push    r12
0x18001cfb7  push    r13
0x18001cfb9  push    r14
0x18001cfbb  push    r15
0x18001cfbd  sub     rsp, 98h
0x18001cfc4  mov     r14, r8
0x18001cfc7  mov     rbx, rdx
0x18001cfca  mov     r13, rcx
0x18001cfcd  test    r8, r8
0x18001cfd0  jz      loc_18001D05B
0x18001cfd6  xor     edx, edx; Val
0x18001cfd8  lea     rcx, [rsp+0D8h+pMarshalInfo]; void *
0x18001cfdd  lea     r8d, [rdx+58h]; Size
0x18001cfe1  call    memset_0
0x18001cfe6  lea     r8, [rsp+0D8h+pMarshalInfo]; pMarshalInfo
0x18001cfeb  mov     edx, 1; InformationLevel
0x18001cff0  mov     rcx, r13; pFlags
0x18001cff3  call    cs:__imp_NdrGetUserMarshalInfo
0x18001cff9  test    eax, eax
0x18001cffb  jnz     loc_18001D5D2
0x18001d001  mov     ebp, dword ptr [rsp+0D8h+pMarshalInfo.8+8]
0x18001d005  xor     r8d, r8d; int
0x18001d008  mov     rdi, qword ptr [rsp+0D8h+pMarshalInfo.8]
0x18001d00d  mov     rdx, rbx; unsigned __int8 *
0x18001d010  mov     rcx, r13; pFlags
0x18001d013  call    ?Variant_ValidateBuffer@@YAXPEAKPEAEH@Z; Variant_ValidateBuffer(ulong *,uchar *,int)
0x18001d018  cmp     rbp, 2
0x18001d01c  jb      short loc_18001D03E
0x18001d01e  add     rbx, 7
0x18001d022  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001d026  add     rbx, 8
0x18001d02a  cmp     rbx, rdi
0x18001d02d  jb      short loc_18001D03E
0x18001d02f  mov     rax, rbx
0x18001d032  lea     r12, [rbp-2]
0x18001d036  sub     rax, rdi
0x18001d039  cmp     r12, rax
0x18001d03c  jnb     short loc_18001D072
0x18001d03e  mov     ecx, 6F7h; exception
0x18001d043  call    cs:__imp_RpcRaiseException
0x18001d049  int     3; Trap to Debugger
0x18001d04a  mov     rcx, r13
0x18001d04d  call    cs:__imp_CoDoesOtherSideVariantMarshalingNeedTrailingPadding
0x18001d053  test    eax, eax
0x18001d055  jnz     loc_18001D71E
0x18001d05b  mov     rax, rbx
0x18001d05e  add     rsp, 98h
0x18001d065  pop     r15
0x18001d067  pop     r14
0x18001d069  pop     r13
0x18001d06b  pop     r12
0x18001d06d  pop     rdi
0x18001d06e  pop     rsi
0x18001d06f  pop     rbp
0x18001d070  pop     rbx
0x18001d071  retn
0x18001d072  movzx   r15d, word ptr [r14]
0x18001d076  mov     r8d, 4000h
0x18001d07c  movzx   esi, word ptr [rbx]
0x18001d07f  test    r8w, r15w
0x18001d083  jnz     loc_18001D1A9
0x18001d089  mov     rcx, r14; pvarg
0x18001d08c  call    VariantClear
0x18001d091  xor     eax, eax
0x18001d093  xorps   xmm0, xmm0
0x18001d096  movups  xmmword ptr [r14], xmm0
0x18001d09a  mov     [r14+10h], rax
0x18001d09e  xor     edx, edx
0x18001d0a0  mov     [r14], si
0x18001d0a4  movzx   r15d, si
0x18001d0a8  mov     r8d, 4000h
0x18001d0ae  mov     [rsp+0D8h+arg_10], edx
0x18001d0b5  cmp     rbp, 6
0x18001d0b9  jb      short loc_18001D03E
0x18001d0bb  add     rbx, 2
0x18001d0bf  cmp     rbx, rdi
0x18001d0c2  jb      loc_18001D03E
0x18001d0c8  mov     rcx, rbx
0x18001d0cb  lea     rax, [rbp-6]
0x18001d0cf  sub     rcx, rdi
0x18001d0d2  cmp     rax, rcx
0x18001d0d5  jb      loc_18001D03E
0x18001d0db  movzx   eax, word ptr [rbx]
0x18001d0de  mov     r9d, 2000h
0x18001d0e4  mov     [r14+2], ax
0x18001d0e9  movzx   eax, word ptr [rbx+2]
0x18001d0ed  mov     [r14+4], ax
0x18001d0f2  movzx   eax, word ptr [rbx+4]
0x18001d0f6  add     rbx, 0Ah
0x18001d0fa  mov     [r14+6], ax
0x18001d0ff  test    r9w, r15w
0x18001d103  jz      short loc_18001D10E
0x18001d105  mov     eax, 6000h
0x18001d10a  and     r15w, ax
0x18001d10e  mov     eax, 0Ch
0x18001d113  lea     r10d, [rax+2]
0x18001d117  test    r8w, r15w
0x18001d11b  jnz     loc_18001D20C
0x18001d121  cmp     r15w, r10w
0x18001d125  jz      loc_18001D610
0x18001d12b  cmp     r15w, ax
0x18001d12f  jz      loc_18001D03E
0x18001d135  lea     rsi, [r14+8]
0x18001d139  mov     qword ptr [rsi], 0
0x18001d140  movzx   ecx, r15w
0x18001d144  cmp     ecx, r9d
0x18001d147  jz      loc_18001D26E
0x18001d14d  ja      loc_18001D63C
0x18001d153  mov     edx, 0Dh
0x18001d158  cmp     ecx, edx
0x18001d15a  ja      loc_18001D471
0x18001d160  jz      loc_18001D312
0x18001d166  cmp     ecx, 6
0x18001d169  ja      short loc_18001D1BC
0x18001d16b  jz      loc_18001D4BD
0x18001d171  test    ecx, ecx
0x18001d173  jz      short loc_18001D17E
0x18001d175  sub     ecx, 1
0x18001d178  jnz     loc_18001D618
0x18001d17e  cmp     rbx, rdi
0x18001d181  jb      short loc_18001D192
0x18001d183  mov     rax, rbx
0x18001d186  sub     rax, rdi
0x18001d189  cmp     rbp, rax
0x18001d18c  jnb     loc_18001D04A
0x18001d192  mov     rdx, r14; VARIANT *
0x18001d195  mov     rcx, r13; unsigned int *
0x18001d198  call    VARIANT_UserFree
0x18001d19d  mov     ecx, 6F7h; exception
0x18001d1a2  call    cs:__imp_RpcRaiseException
0x18001d1a8  int     3; Trap to Debugger
0x18001d1a9  cmp     r15w, si
0x18001d1ad  jnz     loc_18001D5DB
0x18001d1b3  movzx   edx, r8w
0x18001d1b7  jmp     loc_18001D0AE
0x18001d1bc  sub     ecx, 7
0x18001d1bf  jz      loc_18001D4BD
0x18001d1c5  sub     ecx, 1
0x18001d1c8  jz      loc_18001D369
0x18001d1ce  sub     ecx, 1
0x18001d1d1  jz      loc_18001D312
0x18001d1d7  sub     ecx, 1
0x18001d1da  jz      short loc_18001D245
0x18001d1dc  sub     ecx, 1
0x18001d1df  jnz     loc_18001D648
0x18001d1e5  cmp     rbx, rdi
0x18001d1e8  jb      loc_18001D03E
0x18001d1ee  mov     rax, rbx
0x18001d1f1  sub     rax, rdi
0x18001d1f4  cmp     r12, rax
0x18001d1f7  jb      loc_18001D03E
0x18001d1fd  movzx   eax, word ptr [rbx]
0x18001d200  add     rbx, 2
0x18001d204  mov     [rsi], ax
0x18001d207  jmp     loc_18001D17E
0x18001d20c  mov     eax, 0BFFFh
0x18001d211  xor     esi, esi
0x18001d213  and     r15w, ax
0x18001d217  cmp     r15w, 24h ; '$'
0x18001d21c  jz      loc_18001D140
0x18001d222  cmp     dx, r8w
0x18001d226  jnz     loc_18001D3A0
0x18001d22c  mov     rsi, [r14+8]
0x18001d230  test    rsi, rsi
0x18001d233  jnz     loc_18001D5E7
0x18001d239  mov     ecx, 6F4h; exception
0x18001d23e  call    cs:__imp_RpcRaiseException
0x18001d244  int     3; Trap to Debugger
0x18001d245  cmp     rbx, rdi
0x18001d248  jb      loc_18001D03E
0x18001d24e  mov     rcx, rbx
0x18001d251  lea     rax, [rbp-4]
0x18001d255  sub     rcx, rdi
0x18001d258  cmp     rax, rcx
0x18001d25b  jb      loc_18001D03E
0x18001d261  mov     eax, [rbx]
0x18001d263  add     rbx, 4
0x18001d267  mov     [rsi], eax
0x18001d269  jmp     loc_18001D17E
0x18001d26e  movzx   ecx, word ptr [r14]
0x18001d272  mov     eax, ecx
0x18001d274  and     eax, 0FFFF9FFFh
0x18001d279  cmp     eax, 48h ; 'H'
0x18001d27c  jz      loc_18001D70D
0x18001d282  cmp     rbx, rdi
0x18001d285  jb      loc_18001D03E
0x18001d28b  mov     rcx, rbx
0x18001d28e  lea     rax, [rbp-4]
0x18001d292  sub     rcx, rdi
0x18001d295  cmp     rax, rcx
0x18001d298  jb      loc_18001D03E
0x18001d29e  mov     eax, [rbx]
0x18001d2a0  add     rbx, 4
0x18001d2a4  test    eax, eax
0x18001d2a6  jz      loc_18001D387
0x18001d2ac  xor     r9d, r9d
0x18001d2af  mov     r8, rsi
0x18001d2b2  mov     rdx, rbx; unsigned __int8 *
0x18001d2b5  mov     rcx, r13; pFlags
0x18001d2b8  call    LPSAFEARRAY_Unmarshal
0x18001d2bd  mov     rcx, [rsi]; struct tagSAFEARRAY *
0x18001d2c0  mov     rbx, rax
0x18001d2c3  test    rcx, rcx
0x18001d2c6  jz      loc_18001D17E
0x18001d2cc  mov     rdx, r13; unsigned int *
0x18001d2cf  call    ?GetSafeArrayDiscr@@YA?AW4tagSF_TYPE@@PEAUtagSAFEARRAY@@PEAK@Z; GetSafeArrayDiscr(tagSAFEARRAY *,ulong *)
0x18001d2d4  movzx   edx, word ptr [r14]
0x18001d2d8  mov     r8d, 0FFFh
0x18001d2de  movzx   ecx, dx
0x18001d2e1  and     cx, r8w
0x18001d2e5  mov     r8d, 0Ch
0x18001d2eb  cmp     cx, r8w
0x18001d2ef  jnz     loc_18001D17E
0x18001d2f5  cmp     eax, r8d
0x18001d2f8  jz      loc_18001D17E
0x18001d2fe  mov     ecx, 0FFF3h
0x18001d303  and     dx, cx
0x18001d306  or      dx, ax
0x18001d309  mov     [r14], dx
0x18001d30d  jmp     loc_18001D17E
0x18001d312  cmp     rbx, rdi
0x18001d315  jb      loc_18001D03E
0x18001d31b  mov     rcx, rbx
0x18001d31e  lea     rax, [rbp-4]
0x18001d322  sub     rcx, rdi
0x18001d325  cmp     rax, rcx
0x18001d328  jb      loc_18001D03E
0x18001d32e  mov     eax, [rbx]
0x18001d330  add     rbx, 4
0x18001d334  test    eax, eax
0x18001d336  jz      loc_18001D661
0x18001d33c  cmp     r15w, dx
0x18001d340  lea     rax, IID_IDispatch
0x18001d347  lea     r9, IID_IUnknown
0x18001d34e  mov     r8, rsi
0x18001d351  cmovnz  r9, rax
0x18001d355  mov     rdx, rbx
0x18001d358  mov     rcx, r13
0x18001d35b  call    cs:__imp_WdtpInterfacePointer_UserUnmarshal
0x18001d361  mov     rbx, rax
0x18001d364  jmp     loc_18001D17E
0x18001d369  mov     eax, [rbx]
0x18001d36b  add     rbx, 4
0x18001d36f  test    eax, eax
0x18001d371  jz      loc_18001D464
0x18001d377  mov     r8, rsi; BSTR *
0x18001d37a  mov     rdx, rbx; unsigned __int8 *
0x18001d37d  mov     rcx, r13; unsigned int *
0x18001d380  call    BSTR_UserUnmarshal
0x18001d385  jmp     short loc_18001D361
0x18001d387  mov     rcx, [rsi]; struct tagSAFEARRAY *
0x18001d38a  mov     edx, 1; int
0x18001d38f  call    ?_SafeArrayDestroy@@YAJPEAUtagSAFEARRAY@@H@Z; _SafeArrayDestroy(tagSAFEARRAY *,int)
0x18001d394  mov     qword ptr [rsi], 0
0x18001d39b  jmp     loc_18001D17E
0x18001d3a0  cmp     rbx, rdi
0x18001d3a3  jb      loc_18001D03E
0x18001d3a9  mov     rcx, rbx
0x18001d3ac  lea     rax, [rbp-4]
0x18001d3b0  sub     rcx, rdi
0x18001d3b3  cmp     rax, rcx
0x18001d3b6  jb      loc_18001D03E
0x18001d3bc  movzx   ecx, r15w
0x18001d3c0  sub     ecx, 8
0x18001d3c3  jz      loc_18001D5FA
0x18001d3c9  sub     ecx, 1
0x18001d3cc  jz      loc_18001D5FA
0x18001d3d2  sub     ecx, 3
0x18001d3d5  jz      loc_18001D5F0
0x18001d3db  sub     ecx, 1
0x18001d3de  jz      loc_18001D5FA
0x18001d3e4  sub     ecx, 7
0x18001d3e7  jz      loc_18001D5FA
0x18001d3ed  sub     ecx, 1
0x18001d3f0  jz      loc_18001D5FA
0x18001d3f6  sub     ecx, 10h
0x18001d3f9  jz      loc_18001D5FA
0x18001d3ff  sub     ecx, 1
0x18001d402  jz      loc_18001D5FA
0x18001d408  cmp     ecx, 1FDAh
0x18001d40e  jz      loc_18001D5FA
0x18001d414  mov     eax, [rbx]
0x18001d416  test    eax, eax
0x18001d418  jz      loc_18001D03E
0x18001d41e  mov     ecx, eax; unsigned __int64
0x18001d420  mov     r12d, eax
0x18001d423  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d428  mov     rsi, rax
0x18001d42b  test    rax, rax
0x18001d42e  jz      loc_18001D604
0x18001d434  add     rbx, 4
0x18001d438  mov     r8d, r12d; Size
0x18001d43b  xor     edx, edx; Val
0x18001d43d  mov     rcx, rax; void *
0x18001d440  call    memset_0
0x18001d445  mov     r8d, 4000h
  ... truncated ...
```
