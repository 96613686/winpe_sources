# Variant_ValidateBuffer(ulong *,uchar *,int)

- ea: `0x18001d734`
- end: `0x18001deb6`
- name: `?Variant_ValidateBuffer@@YAXPEAKPEAEH@Z`
- size: `1922`
- prototype: `void __fastcall(unsigned int *pFlags, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c7f0`
- `0x18001cfb0`

## callees

- `0x18000c190`
- `0x18001c674`
- `0x18001c6b0`
- `0x18001d734`
- `0x180030a8c`
- `0x180049d54`
- `0x18004e530`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001dc95`
- `RPCRT4!RpcRaiseException` at `0x18001dc95`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001d77e`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x18001d77e`

## string_xrefs

- `0x18001de94`: `Unexpected end of buffer during BUFFER.Read()`
- `0x18001d975`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001d9c4`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001d9f4`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001dc9f`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001dcb7`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001dcc4`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001dcfc`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001dd60`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001ddc1`: `Unexpected end of buffer during BUFFER.Increment(%lu)`
- `0x18001de2f`: `Unexpected end of buffer during BUFFER.Increment(%lu)`

## pseudocode

```c
void __fastcall Variant_ValidateBuffer(unsigned int *pFlags, unsigned __int8 *a2, int a3)
{
  RPC_STATUS UserMarshalInfo; // eax
  unsigned __int8 *v7; // r10
  __int64 v8; // rcx
  int v9; // r11d
  unsigned __int8 *v10; // rcx
  unsigned __int8 *v11; // rcx
  unsigned int *v12; // r9
  int v13; // r8d
  unsigned __int16 v14; // cx
  unsigned int v15; // edi
  int v16; // ebx
  unsigned int v17; // edx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  unsigned int v24; // edx
  unsigned int v25; // r9d
  bool v26; // zf
  unsigned int v27; // edx
  unsigned int v28; // eax
  _DWORD *v29; // r9
  int v30; // edx
  unsigned int v31; // r8d
  unsigned int *v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rax
  char *v35; // rdx
  unsigned __int64 v36; // rax
  _QWORD *v37; // rdx
  unsigned __int16 *v38; // rdx
  int v39; // ebx
  char *v40; // rcx
  int v41; // eax
  int v42; // ecx
  int v43; // eax
  unsigned int v44; // r8d
  unsigned __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  _QWORD v59[2]; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int8 *v60; // [rsp+30h] [rbp-39h]
  unsigned int BufferSize; // [rsp+38h] [rbp-31h]
  NDR_USER_MARSHAL_INFO pMarshalInfo; // [rsp+40h] [rbp-29h] BYREF

  if ( (unsigned int)SBGetConfigValue(0) )
    return;
  v59[0] = a2;
  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  UserMarshalInfo = NdrGetUserMarshalInfo(pFlags, 1u, &pMarshalInfo);
  if ( UserMarshalInfo )
    RpcRaiseException(UserMarshalInfo);
  v59[1] = pMarshalInfo.Level1.Buffer;
  BufferSize = pMarshalInfo.Level1.BufferSize;
  v7 = (unsigned __int8 *)pMarshalInfo.Level1.Buffer + pMarshalInfo.Level1.BufferSize;
  v60 = v7;
  if ( a2 < pMarshalInfo.Level1.Buffer || a2 > v7 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Buffer pointer out of bounds");
  v8 = -(int)a2 & 7;
  v9 = (int)v7;
  if ( (int)v7 - (int)a2 < (unsigned int)v8 )
    SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Increment(%lu)", v8);
  v10 = &a2[v8];
  v59[0] = v10;
  if ( (unsigned __int64)(v7 - v10) < 4 )
    goto LABEL_145;
  v11 = v10 + 4;
  v59[0] = v11;
  if ( (unsigned __int64)(v7 - v11) < 4 )
    goto LABEL_145;
  v59[0] = v11 + 4;
  if ( (unsigned __int64)(v7 - (v11 + 4)) < 2 )
    goto LABEL_145;
  v59[0] = v11 + 6;
  if ( (unsigned __int64)(v7 - (v11 + 6)) < 2 )
    goto LABEL_145;
  v59[0] = v11 + 8;
  if ( (unsigned __int64)(v7 - (v11 + 8)) < 2 )
    goto LABEL_145;
  v59[0] = v11 + 10;
  if ( (unsigned __int64)(v7 - (v11 + 10)) < 2 )
    goto LABEL_145;
  if ( (unsigned int)((_DWORD)v7 - ((_DWORD)v11 + 12)) < 4 )
    goto LABEL_43;
  v12 = (unsigned int *)(v11 + 16);
  v59[0] = v11 + 16;
  if ( a3 )
  {
    v27 = -(int)v12 & 7;
    if ( (int)v7 - (int)v12 < v27 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Increment(%lu)", v27);
    v12 = (unsigned int *)((char *)v12 + v27);
    v59[0] = v12;
  }
  v13 = *((unsigned __int16 *)v11 + 2);
  v14 = v13 & 0xBFFF;
  v15 = 0;
  v16 = v13 & 0x4000;
  if ( (v13 & 0x4000) == 0 )
  {
LABEL_15:
    if ( (v13 & 0x2000) == 0 )
      goto LABEL_16;
    if ( (a3 != 0 ? 8 : 4) != v15 && (v13 & 0x4000) != 0 )
      goto LABEL_31;
    if ( a3 )
    {
      SafeBuffer::Increment((SafeBuffer *)v59, -LODWORD(v59[0]) & 7);
      if ( !SafeBuffer::Read<unsigned __int64>((SafeBuffer *)v59) )
        return;
      v7 = v60;
      v29 = (_DWORD *)v59[0];
      v9 = (int)v60;
    }
    else
    {
      if ( (unsigned __int64)(v7 - (unsigned __int8 *)v12) < 4 )
        goto LABEL_145;
      v28 = *v12;
      v29 = v12 + 1;
      if ( !v28 )
        return;
    }
    v30 = a3 != 0 ? 7 : 3;
    v31 = v30 & (v30 - (v30 & (unsigned int)v29) + 1);
    if ( v9 - (int)v29 < v31 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Increment(%lu)", v31);
    v32 = (_DWORD *)((char *)v29 + v31);
    v33 = v7 - (unsigned __int8 *)v32;
    if ( a3 )
    {
      if ( v33 < 8 )
        goto LABEL_145;
      v34 = *(_QWORD *)v32;
      v35 = (char *)(v32 + 2);
    }
    else
    {
      if ( v33 < 4 )
        goto LABEL_145;
      v34 = *v32;
      v35 = (char *)(v32 + 1);
    }
    if ( !v34 )
      return;
    v36 = v7 - (unsigned __int8 *)v35;
    if ( a3 )
    {
      if ( v36 < 8 )
        goto LABEL_145;
      v47 = *(_QWORD *)v35;
      v37 = v35 + 8;
      if ( (unsigned int)v47 != v47 )
        goto LABEL_89;
    }
    else
    {
      if ( v36 < 4 )
        goto LABEL_145;
      v37 = v35 + 4;
    }
    if ( (unsigned __int64)(v7 - (unsigned __int8 *)v37) >= 2 )
    {
      v38 = (unsigned __int16 *)v37 + 1;
      v59[0] = v38;
      if ( (unsigned __int64)(v7 - (unsigned __int8 *)v38) >= 2 )
      {
        v39 = *v38;
        v59[0] = v38 + 1;
        if ( (unsigned __int64)(v7 - (unsigned __int8 *)(v38 + 1)) >= 4 )
        {
          v59[0] = v38 + 3;
          if ( (unsigned __int64)(v7 - (unsigned __int8 *)(v38 + 3)) >= 4 )
          {
            v40 = (char *)(v38 + 5);
            v59[0] = v38 + 5;
            if ( a3 )
            {
              SafeBuffer::Increment((SafeBuffer *)v59, -LODWORD(v59[0]) & 7);
              v7 = v60;
              v40 = (char *)v59[0];
              v9 = (int)v60;
            }
            if ( (unsigned __int64)(v7 - (unsigned __int8 *)v40) >= 4 )
            {
              v41 = *(_DWORD *)v40;
              v42 = (_DWORD)v40 + 4;
              if ( (unsigned __int16)v41 == v41 )
              {
                if ( (_WORD)v41 == 0x800D )
                {
                  if ( (unsigned int)(v9 - v42) < 0x10 )
                    SafeBuffer::RaiseShieldException(
                      (SafeBuffer *)v59,
                      "Unexpected end of buffer during BUFFER.Increment(%lu)",
                      16);
                  v43 = v39 & 0xF60;
                  if ( v43 != 576 && v43 != 1088 )
                    SafeBuffer::RaiseShieldException(
                      (SafeBuffer *)v59,
                      "Buffer inconsistency in SafeArray embedded in Variant: sfDiscr == SF_HAVEIID but fFeatures (%lxh) "
                      "is neither FADF_UNKNOWN|FADF_HAVEIID nor FADF_DISPATCH|FADF_HAVEIID",
                      v39);
                }
                return;
              }
LABEL_89:
              SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected cast truncation");
            }
          }
        }
      }
    }
LABEL_145:
    SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Read()");
  }
  if ( v14 != 36 )
  {
    v45 = v7 - (unsigned __int8 *)v12;
    if ( a3 )
    {
      if ( v45 < 8 )
        goto LABEL_145;
      v46 = *(_QWORD *)v12;
      v12 += 2;
      v15 = v46;
      v59[0] = v12;
      if ( (unsigned int)v46 != v46 )
        goto LABEL_89;
    }
    else
    {
      if ( v45 < 4 )
        goto LABEL_145;
      v15 = *v12++;
      v59[0] = v12;
    }
    if ( v15 > 0x18 )
      goto LABEL_31;
    goto LABEL_15;
  }
LABEL_16:
  v17 = a3 != 0 ? 8 : 4;
  if ( v14 > 0xDu )
  {
    if ( v14 > 0x15u )
    {
      v56 = v14 - 22;
      if ( v56 )
      {
        v57 = v56 - 1;
        if ( v57 )
        {
          v58 = v57 - 13;
          if ( !v58 )
            goto LABEL_127;
          if ( (unsigned int)(v58 - 1) < 2 )
          {
            if ( v17 == v15 || (v13 & 0x4000) == 0 )
            {
              v17 = 4;
              goto LABEL_127;
            }
            goto LABEL_31;
          }
          goto LABEL_139;
        }
      }
      goto LABEL_41;
    }
    if ( v14 == 21 )
      goto LABEL_79;
    v51 = v14 - 14;
    if ( v51 )
    {
      v52 = v51 - 2;
      if ( !v52 || (v53 = v52 - 1) == 0 )
      {
        if ( v17 == v15 || (v13 & 0x4000) == 0 )
        {
          v17 = 1;
          goto LABEL_127;
        }
LABEL_31:
        SafeBuffer::RaiseShieldException((SafeBuffer *)v59, qword_1800AD360);
      }
      v54 = v53 - 1;
      if ( !v54 )
        goto LABEL_29;
      v55 = v54 - 1;
      if ( !v55 )
        goto LABEL_41;
      if ( v55 != 1 )
        goto LABEL_139;
LABEL_79:
      v44 = -(int)v12 & 7;
      if ( (int)v7 - (int)v12 < v44 )
        SafeBuffer::RaiseShieldException(
          (SafeBuffer *)v59,
          "Unexpected end of buffer during BUFFER.Increment(%lu)",
          v44);
      v25 = v44 + (_DWORD)v12;
      v26 = v17 == v15;
LABEL_36:
      if ( v26 || !v16 )
      {
        if ( (unsigned int)v7 - v25 < 8 )
          SafeBuffer::RaiseShieldException(
            (SafeBuffer *)v59,
            "Unexpected end of buffer during BUFFER.Increment(%lu)",
            8);
        return;
      }
      goto LABEL_31;
    }
    SafeBuffer::Increment((SafeBuffer *)v59, -LODWORD(v59[0]) & 7);
    if ( v15 == 16 )
    {
      if ( v16 )
      {
LABEL_133:
        v17 = 14;
        goto LABEL_127;
      }
    }
    else if ( v16 )
    {
      goto LABEL_31;
    }
    if ( (unsigned __int16)SafeBuffer::Read<unsigned short>((SafeBuffer *)v59) != 14 )
      goto LABEL_31;
    goto LABEL_133;
  }
  if ( v14 == 13 )
    goto LABEL_44;
  if ( v14 > 6u )
  {
    v19 = v14 - 7;
    if ( !v19 )
    {
LABEL_107:
      SafeBuffer::Increment((SafeBuffer *)v59, -LODWORD(v59[0]) & 7);
      if ( v15 == 8 || !v16 )
      {
        v17 = 8;
LABEL_127:
        SafeBuffer::Increment((SafeBuffer *)v59, v17);
        return;
      }
      goto LABEL_31;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            if ( v23 == 1 )
            {
              if ( (v13 & 0x4000) != 0 && ((v15 - 16) & 0xFFFFFFF7) == 0 )
                goto LABEL_127;
              goto LABEL_31;
            }
            goto LABEL_139;
          }
          goto LABEL_29;
        }
LABEL_41:
        if ( v17 != v15 && (v13 & 0x4000) != 0 )
          goto LABEL_31;
        if ( (unsigned int)((_DWORD)v7 - (_DWORD)v12) >= 4 )
          return;
LABEL_43:
        SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Increment(%lu)", 4);
      }
    }
LABEL_44:
    if ( v17 == v15 || (v13 & 0x4000) == 0 )
    {
      if ( (int)v7 - (int)v12 < v17 )
        SafeBuffer::RaiseShieldException(
          (SafeBuffer *)v59,
          "Unexpected end of buffer during BUFFER.Increment(%lu)",
          v17);
      return;
    }
    goto LABEL_31;
  }
  if ( v14 == 6 )
  {
    v24 = -(int)v12 & 7;
    if ( (int)v7 - (int)v12 < v24 )
      SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Unexpected end of buffer during BUFFER.Increment(%lu)", v24);
    v25 = v24 + (_DWORD)v12;
    v26 = v15 == 8;
    goto LABEL_36;
  }
  if ( v14 )
  {
    v18 = v14 - 1;
    if ( v18 )
    {
      v48 = v18 - 1;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          v50 = v49 - 1;
          if ( v50 )
          {
            if ( v50 == 1 )
              goto LABEL_107;
LABEL_139:
            SafeBuffer::RaiseShieldException((SafeBuffer *)v59, "Illegal vartype: %lxh", v13);
          }
        }
        goto LABEL_41;
      }
LABEL_29:
      if ( v17 == v15 || (v13 & 0x4000) == 0 )
      {
        if ( (unsigned int)((_DWORD)v7 - (_DWORD)v12) < 2 )
          SafeBuffer::RaiseShieldException(
            (SafeBuffer *)v59,
            "Unexpected end of buffer during BUFFER.Increment(%lu)",
            2);
        return;
      }
      goto LABEL_31;
    }
  }
  if ( (v13 & 0x4000) != 0 )
    goto LABEL_31;
}

```

## disassembly

```asm
0x18001d734  push    rbp
0x18001d736  push    rbx
0x18001d737  push    rsi
0x18001d738  push    rdi
0x18001d739  push    r14
0x18001d73b  lea     rbp, [rsp-37h]
0x18001d740  sub     rsp, 0A0h
0x18001d747  mov     rdi, rcx
0x18001d74a  mov     esi, r8d
0x18001d74d  xor     ecx, ecx
0x18001d74f  mov     rbx, rdx
0x18001d752  call    ?SBGetConfigValue@@YAHW4SBConfigValue@@@Z; SBGetConfigValue(SBConfigValue)
0x18001d757  test    eax, eax
0x18001d759  jnz     loc_18001D934
0x18001d75f  xor     edx, edx; Val
0x18001d761  mov     [rbp+57h+var_A0], rbx
0x18001d765  lea     r8d, [rax+58h]; Size
0x18001d769  lea     rcx, [rbp+57h+pMarshalInfo]; void *
0x18001d76d  call    memset_0
0x18001d772  lea     r8, [rbp+57h+pMarshalInfo]; pMarshalInfo
0x18001d776  mov     edx, 1; InformationLevel
0x18001d77b  mov     rcx, rdi; pFlags
0x18001d77e  call    cs:__imp_NdrGetUserMarshalInfo
0x18001d784  test    eax, eax
0x18001d786  jnz     loc_18001DC93
0x18001d78c  mov     rcx, qword ptr [rbp+57h+pMarshalInfo.8]
0x18001d790  mov     eax, dword ptr [rbp+57h+pMarshalInfo.8+8]
0x18001d793  mov     [rbp+57h+var_98], rcx
0x18001d797  mov     [rbp+57h+var_88], eax
0x18001d79a  lea     r10, [rcx+rax]
0x18001d79e  mov     [rbp+57h+var_90], r10
0x18001d7a2  cmp     rbx, rcx
0x18001d7a5  jb      loc_18001DEA5
0x18001d7ab  cmp     rbx, r10
0x18001d7ae  ja      loc_18001DEA5
0x18001d7b4  mov     ecx, ebx
0x18001d7b6  mov     eax, r10d
0x18001d7b9  neg     ecx
0x18001d7bb  sub     eax, ebx
0x18001d7bd  and     ecx, 7
0x18001d7c0  mov     r11d, r10d
0x18001d7c3  cmp     eax, ecx
0x18001d7c5  jb      loc_18001DC9C
0x18001d7cb  add     rcx, rbx
0x18001d7ce  mov     rax, r10
0x18001d7d1  sub     rax, rcx
0x18001d7d4  mov     [rbp+57h+var_A0], rcx
0x18001d7d8  mov     r14d, 4
0x18001d7de  cmp     rax, r14
0x18001d7e1  jb      loc_18001DE94
0x18001d7e7  add     rcx, r14
0x18001d7ea  mov     rax, r10
0x18001d7ed  sub     rax, rcx
0x18001d7f0  mov     [rbp+57h+var_A0], rcx
0x18001d7f4  cmp     rax, r14
0x18001d7f7  jb      loc_18001DE94
0x18001d7fd  lea     r8, [rcx+4]
0x18001d801  mov     rax, r10
0x18001d804  sub     rax, r8
0x18001d807  mov     [rbp+57h+var_A0], r8
0x18001d80b  cmp     rax, 2
0x18001d80f  jb      loc_18001DE94
0x18001d815  lea     rcx, [r8+2]
0x18001d819  mov     rax, r10
0x18001d81c  sub     rax, rcx
0x18001d81f  mov     [rbp+57h+var_A0], rcx
0x18001d823  cmp     rax, 2
0x18001d827  jb      loc_18001DE94
0x18001d82d  add     rcx, 2
0x18001d831  mov     rax, r10
0x18001d834  sub     rax, rcx
0x18001d837  mov     [rbp+57h+var_A0], rcx
0x18001d83b  cmp     rax, 2
0x18001d83f  jb      loc_18001DE94
0x18001d845  add     rcx, 2
0x18001d849  mov     rax, r10
0x18001d84c  sub     rax, rcx
0x18001d84f  mov     [rbp+57h+var_A0], rcx
0x18001d853  cmp     rax, 2
0x18001d857  jb      loc_18001DE94
0x18001d85d  lea     r9, [rcx+2]
0x18001d861  mov     ecx, r10d
0x18001d864  sub     ecx, r9d
0x18001d867  cmp     ecx, r14d
0x18001d86a  jb      loc_18001D9C1
0x18001d870  add     r9, r14
0x18001d873  mov     [rbp+57h+var_A0], r9
0x18001d877  test    esi, esi
0x18001d879  jnz     loc_18001D986
0x18001d87f  movzx   r8d, word ptr [r8]
0x18001d883  mov     eax, 0BFFFh
0x18001d888  movzx   ecx, r8w
0x18001d88c  mov     ebx, r8d
0x18001d88f  and     cx, ax
0x18001d892  xor     edi, edi
0x18001d894  and     ebx, 4000h
0x18001d89a  jnz     loc_18001DBE0
0x18001d8a0  bt      cx, 0Dh
0x18001d8a5  jb      loc_18001DA01
0x18001d8ab  neg     esi
0x18001d8ad  movzx   ecx, cx
0x18001d8b0  sbb     edx, edx
0x18001d8b2  and     edx, r14d
0x18001d8b5  add     edx, r14d
0x18001d8b8  cmp     ecx, 0Dh
0x18001d8bb  ja      loc_18001DBAB
0x18001d8c1  jz      loc_18001D9D5
0x18001d8c7  cmp     ecx, 6
0x18001d8ca  ja      short loc_18001D8E1
0x18001d8cc  jz      short loc_18001D942
0x18001d8ce  test    ecx, ecx
0x18001d8d0  jz      short loc_18001D8DB
0x18001d8d2  sub     ecx, 1
0x18001d8d5  jnz     loc_18001DD0D
0x18001d8db  test    ebx, ebx
0x18001d8dd  jz      short loc_18001D934
0x18001d8df  jmp     short loc_18001D916
0x18001d8e1  sub     ecx, 7
0x18001d8e4  jz      loc_18001DD31
0x18001d8ea  sub     ecx, 1
0x18001d8ed  jz      loc_18001D9D5
0x18001d8f3  sub     ecx, 1
0x18001d8f6  jz      loc_18001D9D5
0x18001d8fc  sub     ecx, 1
0x18001d8ff  jz      loc_18001D9AD
0x18001d905  sub     ecx, 1
0x18001d908  jnz     loc_18001DD7A
0x18001d90e  cmp     edx, edi
0x18001d910  jz      short loc_18001D927
0x18001d912  test    ebx, ebx
0x18001d914  jz      short loc_18001D927
0x18001d916  lea     rdx, qword_1800AD360; char *
0x18001d91d  lea     rcx, [rbp+57h+var_A0]; this
0x18001d921  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001d927  sub     r11d, r9d
0x18001d92a  cmp     r11d, 2
0x18001d92e  jb      loc_18001DDBB
0x18001d934  add     rsp, 0A0h
0x18001d93b  pop     r14
0x18001d93d  pop     rdi
0x18001d93e  pop     rsi
0x18001d93f  pop     rbx
0x18001d940  pop     rbp
0x18001d941  retn
0x18001d942  mov     edx, r9d
0x18001d945  mov     eax, r11d
0x18001d948  neg     edx
0x18001d94a  sub     eax, r9d
0x18001d94d  and     edx, 7
0x18001d950  cmp     eax, edx
0x18001d952  jb      loc_18001DD59
0x18001d958  mov     eax, edx
0x18001d95a  add     r9, rax
0x18001d95d  cmp     edi, 8
0x18001d960  jnz     loc_18001DD6D
0x18001d966  sub     r11d, r9d
0x18001d969  cmp     r11d, 8
0x18001d96d  jnb     short loc_18001D934
0x18001d96f  mov     r8d, 8
0x18001d975  lea     rdx, aUnexpectedEndO_0; "Unexpected end of buffer during BUFFER."...
0x18001d97c  lea     rcx, [rbp+57h+var_A0]; this
0x18001d980  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001d986  mov     edx, r9d
0x18001d989  mov     eax, r11d
0x18001d98c  neg     edx
0x18001d98e  sub     eax, r9d
0x18001d991  and     edx, 7
0x18001d994  cmp     eax, edx
0x18001d996  jb      loc_18001DCB0
0x18001d99c  mov     eax, edx
0x18001d99e  add     rax, r9
0x18001d9a1  mov     r9, rax
0x18001d9a4  mov     [rbp+57h+var_A0], rax
0x18001d9a8  jmp     loc_18001D87F
0x18001d9ad  cmp     edx, edi
0x18001d9af  jnz     loc_18001DE87
0x18001d9b5  sub     r11d, r9d
0x18001d9b8  cmp     r11d, r14d
0x18001d9bb  jnb     loc_18001D934
0x18001d9c1  mov     r8d, r14d
0x18001d9c4  lea     rdx, aUnexpectedEndO_0; "Unexpected end of buffer during BUFFER."...
0x18001d9cb  lea     rcx, [rbp+57h+var_A0]; this
0x18001d9cf  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001d9d5  cmp     edx, edi
0x18001d9d7  jz      short loc_18001D9E1
0x18001d9d9  test    ebx, ebx
0x18001d9db  jnz     loc_18001D916
0x18001d9e1  sub     r11d, r9d
0x18001d9e4  cmp     r11d, edx
0x18001d9e7  jnb     loc_18001D934
0x18001d9ed  mov     r8d, edx
0x18001d9f0  lea     rcx, [rbp+57h+var_A0]; this
0x18001d9f4  lea     rdx, aUnexpectedEndO_0; "Unexpected end of buffer during BUFFER."...
0x18001d9fb  call    ?RaiseShieldException@SafeBuffer@@QEAAXPEBDZZ; SafeBuffer::RaiseShieldException(char const *,...)
0x18001da01  mov     eax, esi
0x18001da03  neg     eax
0x18001da05  sbb     ecx, ecx
0x18001da07  and     ecx, r14d
0x18001da0a  add     ecx, r14d
0x18001da0d  cmp     ecx, edi
0x18001da0f  jz      short loc_18001DA19
0x18001da11  test    ebx, ebx
0x18001da13  jnz     loc_18001D916
0x18001da19  test    esi, esi
0x18001da1b  jnz     short loc_18001DA3C
0x18001da1d  mov     rax, r10
0x18001da20  sub     rax, r9
0x18001da23  cmp     rax, r14
0x18001da26  jb      loc_18001DE94
0x18001da2c  mov     eax, [r9]
0x18001da2f  add     r9, r14
0x18001da32  test    eax, eax
0x18001da34  jz      loc_18001D934
0x18001da3a  jmp     short loc_18001DA6A
0x18001da3c  mov     edx, dword ptr [rbp+57h+var_A0]
0x18001da3f  lea     rcx, [rbp+57h+var_A0]; this
0x18001da43  neg     edx
0x18001da45  and     edx, 7; unsigned int
0x18001da48  call    ?Increment@SafeBuffer@@QEAAXI@Z; SafeBuffer::Increment(uint)
0x18001da4d  lea     rcx, [rbp+57h+var_A0]; this
0x18001da51  call    ??$Read@_K@SafeBuffer@@QEAA_KXZ; SafeBuffer::Read<unsigned __int64>(void)
0x18001da56  test    rax, rax
0x18001da59  jz      loc_18001D934
0x18001da5f  mov     r10, [rbp+57h+var_90]
0x18001da63  mov     r9, [rbp+57h+var_A0]
0x18001da67  mov     r11d, r10d
0x18001da6a  mov     eax, esi
0x18001da6c  neg     eax
0x18001da6e  mov     eax, r9d
0x18001da71  sbb     edx, edx
0x18001da73  and     edx, r14d
0x18001da76  add     edx, 3
0x18001da79  and     eax, edx
0x18001da7b  mov     r8d, edx
0x18001da7e  sub     r8d, eax
0x18001da81  mov     eax, r11d
0x18001da84  inc     r8d
0x18001da87  sub     eax, r9d
0x18001da8a  and     r8d, edx
0x18001da8d  cmp     eax, r8d
0x18001da90  jb      loc_18001DCC4
0x18001da96  mov     ecx, r8d
0x18001da99  mov     rax, r10
0x18001da9c  add     rcx, r9
0x18001da9f  sub     rax, rcx
0x18001daa2  test    esi, esi
0x18001daa4  jnz     loc_18001DC62
0x18001daaa  cmp     rax, r14
0x18001daad  jb      loc_18001DE94
0x18001dab3  mov     eax, [rcx]
0x18001dab5  lea     rdx, [rcx+4]
0x18001dab9  test    rax, rax
0x18001dabc  jz      loc_18001D934
0x18001dac2  mov     rax, r10
0x18001dac5  sub     rax, rdx
0x18001dac8  test    esi, esi
0x18001daca  jnz     loc_18001DC44
0x18001dad0  cmp     rax, r14
0x18001dad3  jb      loc_18001DE94
0x18001dad9  add     rdx, r14
0x18001dadc  mov     rax, r10
0x18001dadf  sub     rax, rdx
0x18001dae2  cmp     rax, 2
0x18001dae6  jb      loc_18001DE94
0x18001daec  add     rdx, 2
0x18001daf0  mov     rax, r10
0x18001daf3  sub     rax, rdx
0x18001daf6  mov     [rbp+57h+var_A0], rdx
0x18001dafa  cmp     rax, 2
0x18001dafe  jb      loc_18001DE94
0x18001db04  movzx   ebx, word ptr [rdx]
0x18001db07  lea     rcx, [rdx+2]
0x18001db0b  mov     rax, r10
0x18001db0e  mov     [rbp+57h+var_A0], rcx
0x18001db12  sub     rax, rcx
0x18001db15  cmp     rax, r14
0x18001db18  jb      loc_18001DE94
0x18001db1e  add     rcx, r14
0x18001db21  mov     rax, r10
0x18001db24  sub     rax, rcx
0x18001db27  mov     [rbp+57h+var_A0], rcx
0x18001db2b  cmp     rax, r14
0x18001db2e  jb      loc_18001DE94
0x18001db34  add     rcx, r14
0x18001db37  mov     [rbp+57h+var_A0], rcx
0x18001db3b  test    esi, esi
0x18001db3d  jnz     loc_18001DCD5
0x18001db43  sub     r10, rcx
0x18001db46  cmp     r10, r14
0x18001db49  jb      loc_18001DE94
0x18001db4f  mov     eax, [rcx]
0x18001db51  add     rcx, r14
0x18001db54  movzx   edx, ax
0x18001db57  cmp     edx, eax
0x18001db59  jnz     loc_18001DC33
0x18001db5f  mov     eax, 800Dh
0x18001db64  cmp     dx, ax
0x18001db67  jnz     loc_18001D934
0x18001db6d  sub     r11d, ecx
0x18001db70  cmp     r11d, 10h
  ... truncated ...
```
