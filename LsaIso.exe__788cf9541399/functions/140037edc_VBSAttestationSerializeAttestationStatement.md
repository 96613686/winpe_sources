# VBSAttestationSerializeAttestationStatement

- ea: `0x140037edc`
- end: `0x14003806e`
- name: `VBSAttestationSerializeAttestationStatement`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140013124`
- `0x140013700`

## callees

- `0x140037b10`
- `0x140037bec`
- `0x140037e90`
- `0x140037edc`
- `0x140038160`

## string_xrefs

- `0x14003804d`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationSerializeAttestationStatement(__int64 a1, unsigned __int8 *a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  int v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // eax
  unsigned int v11; // [rsp+40h] [rbp+20h] BYREF
  unsigned __int8 *v12; // [rsp+48h] [rbp+28h] BYREF

  v12 = a2;
  v11 = 0;
  v5 = -2146893819;
  if ( !a1 || !a3 )
  {
    v8 = 579;
    v7 = 2148073477LL;
    goto LABEL_28;
  }
  *a3 = 12;
  if ( a2 )
  {
    if ( (int)CopyULONGAdvanceDest((_DWORD **)&v12, (_DWORD *)a1) >= 0 )
    {
      if ( (int)CopyULONGAdvanceDest((_DWORD **)&v12, (_DWORD *)(a1 + 4)) >= 0 )
      {
        if ( (int)CopyULONGAdvanceDest((_DWORD **)&v12, (_DWORD *)(a1 + 8)) >= 0 )
        {
          if ( *(_DWORD *)(a1 + 8) == 5 )
          {
            v9 = VBSAttestationSerializeRootHeader((struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *)(a1 + 12), v12, &v11);
            v5 = v9;
            if ( v9 < 0 )
            {
              v8 = 683;
              goto LABEL_9;
            }
          }
          else
          {
            if ( *(_DWORD *)(a1 + 8) != 6 )
            {
              v7 = 3221225485LL;
              v8 = 690;
              v5 = -1073741811;
              goto LABEL_28;
            }
            v9 = VBSAttestationSerializeIdentityHeader((unsigned int *)(a1 + 12), (__int64)v12, &v11);
            v5 = v9;
            if ( v9 < 0 )
            {
              v8 = 666;
              goto LABEL_9;
            }
          }
          goto LABEL_26;
        }
        v8 = 648;
      }
      else
      {
        v8 = 643;
      }
    }
    else
    {
      v8 = 638;
    }
    v7 = 3221225701LL;
    goto LABEL_28;
  }
  v6 = *(_DWORD *)(a1 + 8) - 5;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      v7 = 3221225485LL;
      v8 = 629;
      v5 = -1073741811;
LABEL_28:
      VBS_ATTEST_TRACE_ERROR_IN(
        v7,
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
        v8);
      return v5;
    }
    v9 = VBSAttestationSerializeIdentityHeader((unsigned int *)(a1 + 12), 0, &v11);
    v5 = v9;
    if ( v9 < 0 )
    {
      v8 = 604;
LABEL_9:
      v7 = (unsigned int)v9;
      goto LABEL_28;
    }
  }
  else
  {
    v9 = VBSAttestationSerializeRootHeader((struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *)(a1 + 12), 0, &v11);
    v5 = v9;
    if ( v9 < 0 )
    {
      v8 = 621;
      goto LABEL_9;
    }
  }
LABEL_26:
  *a3 += v11;
  return v5;
}

```

## disassembly

```asm
0x140037edc  mov     [rsp-18h+arg_10], rbx
0x140037ee1  mov     [rsp-18h+arg_18], rsi
0x140037ee6  mov     [rsp-18h+arg_8], rdx
0x140037eeb  push    rbp
0x140037eec  push    rdi
0x140037eed  push    r14
0x140037eef  mov     rbp, rsp
0x140037ef2  sub     rsp, 20h
0x140037ef6  mov     [rbp+arg_0], 0
0x140037efd  mov     rdi, r8
0x140037f00  mov     rsi, rcx
0x140037f03  mov     ebx, 80090005h
0x140037f08  test    rcx, rcx
0x140037f0b  jz      loc_140038045
0x140037f11  test    r8, r8
0x140037f14  jz      loc_140038045
0x140037f1a  mov     dword ptr [r8], 0Ch
0x140037f21  test    rdx, rdx
0x140037f24  jnz     short loc_140037F8C
0x140037f26  mov     ecx, [rcx+8]
0x140037f29  sub     ecx, 5
0x140037f2c  jz      short loc_140037F6B
0x140037f2e  cmp     ecx, 1
0x140037f31  jz      short loc_140037F45
0x140037f33  mov     ecx, 0C000000Dh
0x140037f38  mov     r8d, 275h
0x140037f3e  mov     ebx, ecx
0x140037f40  jmp     loc_14003804D
0x140037f45  lea     rcx, [rsi+0Ch]
0x140037f49  xor     edx, edx
0x140037f4b  lea     r8, [rbp+arg_0]
0x140037f4f  call    VBSAttestationSerializeIdentityHeader
0x140037f54  mov     ebx, eax
0x140037f56  test    eax, eax
0x140037f58  jns     loc_14003803E
0x140037f5e  mov     r8d, 25Ch
0x140037f64  mov     ecx, eax
0x140037f66  jmp     loc_14003804D
0x140037f6b  lea     rcx, [rsi+0Ch]; struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *
0x140037f6f  xor     edx, edx; unsigned __int8 *
0x140037f71  lea     r8, [rbp+arg_0]; unsigned int *
0x140037f75  call    ?VBSAttestationSerializeRootHeader@@YAJPEAU_NCRYPT_VBS_ROOT_ATTESTATION_HEADER@@PEAEPEAK@Z; VBSAttestationSerializeRootHeader(_NCRYPT_VBS_ROOT_ATTESTATION_HEADER *,uchar *,ulong *)
0x140037f7a  mov     ebx, eax
0x140037f7c  test    eax, eax
0x140037f7e  jns     loc_14003803E
0x140037f84  mov     r8d, 26Dh
0x140037f8a  jmp     short loc_140037F64
0x140037f8c  mov     rdx, rsi
0x140037f8f  lea     rcx, [rbp+arg_8]
0x140037f93  call    CopyULONGAdvanceDest
0x140037f98  test    eax, eax
0x140037f9a  jns     short loc_140037FAC
0x140037f9c  mov     r8d, 27Eh
0x140037fa2  mov     ecx, 0C00000E5h
0x140037fa7  jmp     loc_14003804D
0x140037fac  lea     rdx, [rsi+4]
0x140037fb0  lea     rcx, [rbp+arg_8]
0x140037fb4  call    CopyULONGAdvanceDest
0x140037fb9  test    eax, eax
0x140037fbb  jns     short loc_140037FC5
0x140037fbd  mov     r8d, 283h
0x140037fc3  jmp     short loc_140037FA2
0x140037fc5  lea     rdx, [rsi+8]
0x140037fc9  lea     rcx, [rbp+arg_8]
0x140037fcd  call    CopyULONGAdvanceDest
0x140037fd2  test    eax, eax
0x140037fd4  jns     short loc_140037FDE
0x140037fd6  mov     r8d, 288h
0x140037fdc  jmp     short loc_140037FA2
0x140037fde  mov     ecx, [rsi+8]
0x140037fe1  sub     ecx, 5
0x140037fe4  jz      short loc_14003801C
0x140037fe6  cmp     ecx, 1
0x140037fe9  jz      short loc_140037FFA
0x140037feb  mov     ecx, 0C000000Dh
0x140037ff0  mov     r8d, 2B2h
0x140037ff6  mov     ebx, ecx
0x140037ff8  jmp     short loc_14003804D
0x140037ffa  mov     rdx, [rbp+arg_8]
0x140037ffe  lea     rcx, [rsi+0Ch]
0x140038002  lea     r8, [rbp+arg_0]
0x140038006  call    VBSAttestationSerializeIdentityHeader
0x14003800b  mov     ebx, eax
0x14003800d  test    eax, eax
0x14003800f  jns     short loc_14003803E
0x140038011  mov     r8d, 29Ah
0x140038017  jmp     loc_140037F64
0x14003801c  mov     rdx, [rbp+arg_8]; unsigned __int8 *
0x140038020  lea     rcx, [rsi+0Ch]; struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *
0x140038024  lea     r8, [rbp+arg_0]; unsigned int *
0x140038028  call    ?VBSAttestationSerializeRootHeader@@YAJPEAU_NCRYPT_VBS_ROOT_ATTESTATION_HEADER@@PEAEPEAK@Z; VBSAttestationSerializeRootHeader(_NCRYPT_VBS_ROOT_ATTESTATION_HEADER *,uchar *,ulong *)
0x14003802d  mov     ebx, eax
0x14003802f  test    eax, eax
0x140038031  jns     short loc_14003803E
0x140038033  mov     r8d, 2ABh
0x140038039  jmp     loc_140037F64
0x14003803e  mov     eax, [rbp+arg_0]
0x140038041  add     [rdi], eax
0x140038043  jmp     short loc_140038059
0x140038045  mov     r8d, 243h
0x14003804b  mov     ecx, ebx
0x14003804d  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140038054  call    VBS_ATTEST_TRACE_ERROR_IN
0x140038059  mov     rsi, [rsp+20h+arg_18]
0x14003805e  mov     eax, ebx
0x140038060  mov     rbx, [rsp+20h+arg_10]
0x140038065  add     rsp, 20h
0x140038069  pop     r14
0x14003806b  pop     rdi
0x14003806c  pop     rbp
0x14003806d  retn
```
