# UniBMergeDriverDevmode

- ea: `0x180034b94`
- end: `0x180034d94`
- name: `UniBMergeDriverDevmode`
- size: `512`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const wchar_t *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180034518`

## callees

- `0x180004320`
- `0x180034208`
- `0x180034b94`
- `0x180034e10`
- `0x18003540c`
- `0x18004fdd0`

## string_xrefs

- `0x180034d14`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall UniBMergeDriverDevmode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const wchar_t *a6,
        __int64 a7,
        _WORD *a8)
{
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  int v16; // eax
  __int64 v17; // r8
  unsigned __int16 v18; // dx
  unsigned __int16 v19; // r8
  __int64 v20; // rdx
  __int64 v22; // [rsp+28h] [rbp-60h]

  VMergePublicDevmodeFields(a7, a1, a3);
  v11 = (_OWORD *)(a7 + *(unsigned __int16 *)(a7 + 68));
  if ( *(_DWORD *)v11 == 1431193924 )
  {
    v12 = 4;
    v13 = a1 + *(unsigned __int16 *)(a1 + 68);
    v14 = (_OWORD *)v13;
    do
    {
      *v14 = *v11;
      v14[1] = v11[1];
      v14[2] = v11[2];
      v14[3] = v11[3];
      v14[4] = v11[4];
      v14[5] = v11[5];
      v14[6] = v11[6];
      v15 = v11[7];
      v11 += 8;
      v14[7] = v15;
      v14 += 8;
      --v12;
    }
    while ( v12 );
    *v14 = *v11;
    v14[1] = v11[1];
    v14[2] = v11[2];
    v14[3] = v11[3];
    v14[4] = v11[4];
    *(_OWORD *)((char *)v14 + 76) = *(_OWORD *)((char *)v11 + 76);
    v16 = *(_DWORD *)(a4 + 12);
    if ( *(_DWORD *)(v13 + 12) != v16 )
    {
      *(_DWORD *)(v13 + 12) = v16;
      *(_DWORD *)(v13 + 44) = *(_DWORD *)(a4 + 20);
      GPDInitDefaultOptions(a4, v13 + 48, 0x100u, 0);
      if ( a8[33] >= 0x600u && a8[35] > 0x230u )
      {
        v17 = (unsigned __int16)a8[34];
        if ( *(_DWORD *)((char *)a8 + v17) == 1431193924 )
        {
          v18 = *(_WORD *)((char *)a8 + v17 + 8);
          if ( v18 > 0x230u )
          {
            v19 = *(_WORD *)((char *)a8 + v17 + 6);
            if ( v19 )
            {
              if ( v18 > v19 && a8[35] >= v18 )
                bJTKeywordsToDocOptionArray(a4, a3, a5, a6, v13 + 48, v22, (__int64)a8, v18, v19);
            }
          }
        }
      }
    }
    if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(a5 + 40), L"PrintConfig.dll")
      && (!*(_DWORD *)(a3 + 304) || !*(_DWORD *)(a3 + 308) || !(unsigned int)IsValidJobPasscodeString(a3, v13 + 572)) )
    {
      v20 = *(unsigned __int16 *)(a1 + 68);
      if ( v20 + a1 + 604 <= a1 + v20 + (unsigned __int64)*(unsigned __int16 *)(a1 + 70) )
      {
        *(_DWORD *)(v20 + a1 + 16) &= ~0x100u;
        *(_OWORD *)(v20 + a1 + 572) = 0;
        *(_OWORD *)(v20 + a1 + 588) = 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180034b94  push    rbx
0x180034b96  push    rbp
0x180034b97  push    rsi
0x180034b98  push    rdi
0x180034b99  push    r12
0x180034b9b  push    r14
0x180034b9d  push    r15
0x180034b9f  sub     rsp, 50h
0x180034ba3  mov     rbx, [rsp+88h+arg_30]
0x180034bab  mov     rdi, rcx
0x180034bae  mov     rdx, rcx
0x180034bb1  mov     rbp, r9
0x180034bb4  mov     rcx, rbx
0x180034bb7  mov     rsi, r8
0x180034bba  call    VMergePublicDevmodeFields
0x180034bbf  movzx   ecx, word ptr [rbx+44h]
0x180034bc3  add     rcx, rbx
0x180034bc6  cmp     dword ptr [rcx], 554E4944h
0x180034bcc  jnz     loc_180034D7F
0x180034bd2  movzx   ebx, word ptr [rdi+44h]
0x180034bd6  mov     edx, 4
0x180034bdb  add     rbx, rdi
0x180034bde  mov     rax, rbx
0x180034be1  lea     r8d, [rdx+7Ch]
0x180034be5  movups  xmm0, xmmword ptr [rcx]
0x180034be8  movups  xmmword ptr [rax], xmm0
0x180034beb  movups  xmm1, xmmword ptr [rcx+10h]
0x180034bef  movups  xmmword ptr [rax+10h], xmm1
0x180034bf3  movups  xmm0, xmmword ptr [rcx+20h]
0x180034bf7  movups  xmmword ptr [rax+20h], xmm0
0x180034bfb  movups  xmm1, xmmword ptr [rcx+30h]
0x180034bff  movups  xmmword ptr [rax+30h], xmm1
0x180034c03  movups  xmm0, xmmword ptr [rcx+40h]
0x180034c07  movups  xmmword ptr [rax+40h], xmm0
0x180034c0b  movups  xmm1, xmmword ptr [rcx+50h]
0x180034c0f  movups  xmmword ptr [rax+50h], xmm1
0x180034c13  movups  xmm0, xmmword ptr [rcx+60h]
0x180034c17  movups  xmmword ptr [rax+60h], xmm0
0x180034c1b  movups  xmm1, xmmword ptr [rcx+70h]
0x180034c1f  add     rcx, r8
0x180034c22  movups  xmmword ptr [rax+70h], xmm1
0x180034c26  add     rax, r8
0x180034c29  sub     rdx, 1
0x180034c2d  jnz     short loc_180034BE5
0x180034c2f  movups  xmm0, xmmword ptr [rcx]
0x180034c32  mov     r14, [rsp+88h+arg_20]
0x180034c3a  xor     r12d, r12d
0x180034c3d  movups  xmmword ptr [rax], xmm0
0x180034c40  movups  xmm1, xmmword ptr [rcx+10h]
0x180034c44  movups  xmmword ptr [rax+10h], xmm1
0x180034c48  movups  xmm0, xmmword ptr [rcx+20h]
0x180034c4c  movups  xmmword ptr [rax+20h], xmm0
0x180034c50  movups  xmm1, xmmword ptr [rcx+30h]
0x180034c54  movups  xmmword ptr [rax+30h], xmm1
0x180034c58  movups  xmm0, xmmword ptr [rcx+40h]
0x180034c5c  movups  xmmword ptr [rax+40h], xmm0
0x180034c60  movups  xmm1, xmmword ptr [rcx+4Ch]
0x180034c64  movups  xmmword ptr [rax+4Ch], xmm1
0x180034c68  mov     eax, [rbp+0Ch]
0x180034c6b  cmp     [rbx+0Ch], eax
0x180034c6e  jz      loc_180034D10
0x180034c74  mov     [rbx+0Ch], eax
0x180034c77  lea     r15, [rbx+30h]
0x180034c7b  mov     eax, [rbp+14h]
0x180034c7e  mov     rdx, r15
0x180034c81  xor     r9d, r9d
0x180034c84  mov     [rbx+2Ch], eax
0x180034c87  mov     r8d, 100h
0x180034c8d  mov     rcx, rbp
0x180034c90  call    GPDInitDefaultOptions
0x180034c95  mov     rax, [rsp+88h+arg_38]
0x180034c9d  mov     ecx, 600h
0x180034ca2  cmp     [rax+42h], cx
0x180034ca6  jb      short loc_180034D10
0x180034ca8  mov     ecx, 230h
0x180034cad  cmp     [rax+46h], cx
0x180034cb1  jbe     short loc_180034D10
0x180034cb3  movzx   r8d, word ptr [rax+44h]
0x180034cb8  cmp     dword ptr [r8+rax], 554E4944h
0x180034cc0  jnz     short loc_180034D10
0x180034cc2  movzx   edx, word ptr [r8+rax+8]
0x180034cc8  cmp     dx, cx
0x180034ccb  jbe     short loc_180034D10
0x180034ccd  movzx   r8d, word ptr [r8+rax+6]
0x180034cd3  test    r8w, r8w
0x180034cd7  jz      short loc_180034D10
0x180034cd9  cmp     dx, r8w
0x180034cdd  jbe     short loc_180034D10
0x180034cdf  cmp     [rax+46h], dx
0x180034ce3  jb      short loc_180034D10
0x180034ce5  mov     r9, [rsp+88h+arg_28]
0x180034ced  mov     rcx, rbp
0x180034cf0  mov     [rsp+88h+var_48], r8w
0x180034cf6  mov     r8, r14
0x180034cf9  mov     [rsp+88h+var_50], dx
0x180034cfe  mov     rdx, rsi
0x180034d01  mov     [rsp+88h+var_58], rax
0x180034d06  mov     [rsp+88h+var_68], r15
0x180034d0b  call    bJTKeywordsToDocOptionArray
0x180034d10  mov     rcx, [r14+28h]; unsigned __int16 *
0x180034d14  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180034d1b  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180034d20  test    al, al
0x180034d22  jz      short loc_180034D7F
0x180034d24  cmp     [rsi+130h], r12d
0x180034d2b  jz      short loc_180034D49
0x180034d2d  cmp     [rsi+134h], r12d
0x180034d34  jz      short loc_180034D49
0x180034d36  lea     rdx, [rbx+23Ch]
0x180034d3d  mov     rcx, rsi
0x180034d40  call    IsValidJobPasscodeString
0x180034d45  test    eax, eax
0x180034d47  jnz     short loc_180034D7F
0x180034d49  movzx   edx, word ptr [rdi+44h]
0x180034d4d  lea     rax, [rdi+25Ch]
0x180034d54  movzx   ecx, word ptr [rdi+46h]
0x180034d58  add     rax, rdx
0x180034d5b  add     rcx, rdx
0x180034d5e  add     rcx, rdi
0x180034d61  cmp     rax, rcx
0x180034d64  ja      short loc_180034D7F
0x180034d66  btr     dword ptr [rdx+rdi+10h], 8
0x180034d6c  xorps   xmm0, xmm0
0x180034d6f  movups  xmmword ptr [rdx+rdi+23Ch], xmm0
0x180034d77  movups  xmmword ptr [rdx+rdi+24Ch], xmm0
0x180034d7f  mov     eax, 1
0x180034d84  add     rsp, 50h
0x180034d88  pop     r15
0x180034d8a  pop     r14
0x180034d8c  pop     r12
0x180034d8e  pop     rdi
0x180034d8f  pop     rsi
0x180034d90  pop     rbp
0x180034d91  pop     rbx
0x180034d92  retn
```
