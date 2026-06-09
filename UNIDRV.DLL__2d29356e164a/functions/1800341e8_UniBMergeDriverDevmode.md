# UniBMergeDriverDevmode

- ea: `0x1800341e8`
- end: `0x1800343e7`
- name: `UniBMergeDriverDevmode`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180033b84`

## callees

- `0x180004454`
- `0x18003388c`
- `0x1800341e8`
- `0x180034464`
- `0x180034a60`
- `0x18004e704`

## string_xrefs

- `0x180034368`: `PrintConfig.dll`

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

  VMergePublicDevmodeFields(a7, a1);
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
      GPDInitDefaultOptions(a4, v13 + 48, 256, 0);
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
0x1800341e8  push    rbx
0x1800341ea  push    rbp
0x1800341eb  push    rsi
0x1800341ec  push    rdi
0x1800341ed  push    r12
0x1800341ef  push    r14
0x1800341f1  push    r15
0x1800341f3  sub     rsp, 50h
0x1800341f7  mov     rbx, [rsp+88h+arg_30]
0x1800341ff  mov     rdi, rcx
0x180034202  mov     rdx, rcx
0x180034205  mov     rbp, r9
0x180034208  mov     rcx, rbx
0x18003420b  mov     rsi, r8
0x18003420e  call    VMergePublicDevmodeFields
0x180034213  movzx   ecx, word ptr [rbx+44h]
0x180034217  add     rcx, rbx
0x18003421a  cmp     dword ptr [rcx], 554E4944h
0x180034220  jnz     loc_1800343D3
0x180034226  movzx   ebx, word ptr [rdi+44h]
0x18003422a  mov     edx, 4
0x18003422f  add     rbx, rdi
0x180034232  mov     rax, rbx
0x180034235  lea     r8d, [rdx+7Ch]
0x180034239  movups  xmm0, xmmword ptr [rcx]
0x18003423c  movups  xmmword ptr [rax], xmm0
0x18003423f  movups  xmm1, xmmword ptr [rcx+10h]
0x180034243  movups  xmmword ptr [rax+10h], xmm1
0x180034247  movups  xmm0, xmmword ptr [rcx+20h]
0x18003424b  movups  xmmword ptr [rax+20h], xmm0
0x18003424f  movups  xmm1, xmmword ptr [rcx+30h]
0x180034253  movups  xmmword ptr [rax+30h], xmm1
0x180034257  movups  xmm0, xmmword ptr [rcx+40h]
0x18003425b  movups  xmmword ptr [rax+40h], xmm0
0x18003425f  movups  xmm1, xmmword ptr [rcx+50h]
0x180034263  movups  xmmword ptr [rax+50h], xmm1
0x180034267  movups  xmm0, xmmword ptr [rcx+60h]
0x18003426b  movups  xmmword ptr [rax+60h], xmm0
0x18003426f  movups  xmm1, xmmword ptr [rcx+70h]
0x180034273  add     rcx, r8
0x180034276  movups  xmmword ptr [rax+70h], xmm1
0x18003427a  add     rax, r8
0x18003427d  sub     rdx, 1
0x180034281  jnz     short loc_180034239
0x180034283  movups  xmm0, xmmword ptr [rcx]
0x180034286  mov     r14, [rsp+88h+arg_20]
0x18003428e  xor     r12d, r12d
0x180034291  movups  xmmword ptr [rax], xmm0
0x180034294  movups  xmm1, xmmword ptr [rcx+10h]
0x180034298  movups  xmmword ptr [rax+10h], xmm1
0x18003429c  movups  xmm0, xmmword ptr [rcx+20h]
0x1800342a0  movups  xmmword ptr [rax+20h], xmm0
0x1800342a4  movups  xmm1, xmmword ptr [rcx+30h]
0x1800342a8  movups  xmmword ptr [rax+30h], xmm1
0x1800342ac  movups  xmm0, xmmword ptr [rcx+40h]
0x1800342b0  movups  xmmword ptr [rax+40h], xmm0
0x1800342b4  movups  xmm1, xmmword ptr [rcx+4Ch]
0x1800342b8  movups  xmmword ptr [rax+4Ch], xmm1
0x1800342bc  mov     eax, [rbp+0Ch]
0x1800342bf  cmp     [rbx+0Ch], eax
0x1800342c2  jz      loc_180034364
0x1800342c8  mov     [rbx+0Ch], eax
0x1800342cb  lea     r15, [rbx+30h]
0x1800342cf  mov     eax, [rbp+14h]
0x1800342d2  mov     rdx, r15
0x1800342d5  xor     r9d, r9d
0x1800342d8  mov     [rbx+2Ch], eax
0x1800342db  mov     r8d, 100h
0x1800342e1  mov     rcx, rbp
0x1800342e4  call    GPDInitDefaultOptions
0x1800342e9  mov     rax, [rsp+88h+arg_38]
0x1800342f1  mov     ecx, 600h
0x1800342f6  cmp     [rax+42h], cx
0x1800342fa  jb      short loc_180034364
0x1800342fc  mov     ecx, 230h
0x180034301  cmp     [rax+46h], cx
0x180034305  jbe     short loc_180034364
0x180034307  movzx   r8d, word ptr [rax+44h]
0x18003430c  cmp     dword ptr [r8+rax], 554E4944h
0x180034314  jnz     short loc_180034364
0x180034316  movzx   edx, word ptr [r8+rax+8]
0x18003431c  cmp     dx, cx
0x18003431f  jbe     short loc_180034364
0x180034321  movzx   r8d, word ptr [r8+rax+6]
0x180034327  test    r8w, r8w
0x18003432b  jz      short loc_180034364
0x18003432d  cmp     dx, r8w
0x180034331  jbe     short loc_180034364
0x180034333  cmp     [rax+46h], dx
0x180034337  jb      short loc_180034364
0x180034339  mov     r9, [rsp+88h+arg_28]
0x180034341  mov     rcx, rbp
0x180034344  mov     [rsp+88h+var_48], r8w
0x18003434a  mov     r8, r14
0x18003434d  mov     [rsp+88h+var_50], dx
0x180034352  mov     rdx, rsi
0x180034355  mov     [rsp+88h+var_58], rax
0x18003435a  mov     [rsp+88h+var_68], r15
0x18003435f  call    bJTKeywordsToDocOptionArray
0x180034364  mov     rcx, [r14+28h]; unsigned __int16 *
0x180034368  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x18003436f  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180034374  test    al, al
0x180034376  jz      short loc_1800343D3
0x180034378  cmp     [rsi+130h], r12d
0x18003437f  jz      short loc_18003439D
0x180034381  cmp     [rsi+134h], r12d
0x180034388  jz      short loc_18003439D
0x18003438a  lea     rdx, [rbx+23Ch]
0x180034391  mov     rcx, rsi
0x180034394  call    IsValidJobPasscodeString
0x180034399  test    eax, eax
0x18003439b  jnz     short loc_1800343D3
0x18003439d  movzx   edx, word ptr [rdi+44h]
0x1800343a1  lea     rax, [rdi+25Ch]
0x1800343a8  movzx   ecx, word ptr [rdi+46h]
0x1800343ac  add     rax, rdx
0x1800343af  add     rcx, rdx
0x1800343b2  add     rcx, rdi
0x1800343b5  cmp     rax, rcx
0x1800343b8  ja      short loc_1800343D3
0x1800343ba  btr     dword ptr [rdx+rdi+10h], 8
0x1800343c0  xorps   xmm0, xmm0
0x1800343c3  movups  xmmword ptr [rdx+rdi+23Ch], xmm0
0x1800343cb  movups  xmmword ptr [rdx+rdi+24Ch], xmm0
0x1800343d3  mov     eax, 1
0x1800343d8  add     rsp, 50h
0x1800343dc  pop     r15
0x1800343de  pop     r14
0x1800343e0  pop     r12
0x1800343e2  pop     rdi
0x1800343e3  pop     rsi
0x1800343e4  pop     rbp
0x1800343e5  pop     rbx
0x1800343e6  retn
```
