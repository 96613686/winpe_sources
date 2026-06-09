# FindMatchingPortRule(_tag_FW_RULE *,ushort const *,NET_FW_IP_VERSION_,ushort,NET_FW_IP_PROTOCOL_,ushort,FW_INET_ADDR_STORAGE *,_tag_FW_RULE_ACTION * const,int * const)

- ea: `0x1800197d8`
- end: `0x180019cd5`
- name: `?FindMatchingPortRule@@YAHPEAU_tag_FW_RULE@@PEBGW4NET_FW_IP_VERSION_@@GW4NET_FW_IP_PROTOCOL_@@GPEATFW_INET_ADDR_STORAGE@@QEAW4_tag_FW_RULE_ACTION@@QEAH@Z`
- size: `1277`
- prototype: `int(struct _tag_FW_RULE *, const unsigned __int16 *, enum NET_FW_IP_VERSION_, unsigned __int16, enum NET_FW_IP_PROTOCOL_, unsigned __int16, union FW_INET_ADDR_STORAGE *, enum _tag_FW_RULE_ACTION *const, int *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ef0`

## callees

- `0x1800197d8`
- `0x18003104c`
- `0x1800372f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001988d`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001988d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019936`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019936`
- `fwbase!FwBaseFree` at `0x180019969`
- `fwbase!FwBaseFree` at `0x180019969`
- `fwbase!FwAllocArray` at `0x18001984a`
- `fwbase!FwAllocArray` at `0x18001984a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a36`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a36`

## pseudocode

```c
__int64 __fastcall FindMatchingPortRule(
        struct _tag_FW_RULE **a1,
        const unsigned __int16 *a2,
        enum NET_FW_IP_VERSION_ a3,
        unsigned __int16 a4,
        enum NET_FW_IP_PROTOCOL_ a5,
        unsigned __int16 a6,
        union FW_INET_ADDR_STORAGE *a7,
        enum _tag_FW_RULE_ACTION *const a8,
        int *const a9)
{
  unsigned __int16 v9; // si
  const WCHAR *lpString2; // rbp
  unsigned int v12; // r14d
  struct _tag_FW_RULE *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // r15
  enum _tag_FW_RULE_ACTION *v16; // r13
  unsigned int v17; // r12d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  const WCHAR *v22; // rax
  int v24; // edx
  unsigned int v25; // ecx
  unsigned int i; // eax
  __int64 v27; // r8
  unsigned int v28; // ecx
  __int64 v29; // r9
  int v30; // edx
  unsigned int j; // eax
  unsigned int v32; // ebp
  __int64 v33; // rsi
  int v34; // ebx
  int v35; // ecx
  int v36; // eax
  unsigned int v37; // ecx
  __int64 v38; // r9
  unsigned int v39; // eax
  bool v40; // zf
  unsigned int v41; // [rsp+30h] [rbp-58h]
  _QWORD *v42; // [rsp+38h] [rbp-50h]
  int v43; // [rsp+90h] [rbp+8h]

  v9 = a4;
  lpString2 = a2;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids);
  v12 = 0;
  v13 = (struct _tag_FW_RULE *)a1;
  if ( a1 )
  {
    do
    {
      v13 = *(struct _tag_FW_RULE **)v13;
      ++v12;
    }
    while ( v13 );
    v41 = v12;
    if ( v12 )
    {
      v14 = (_QWORD *)FwAllocArray(v12, 8);
      v42 = v14;
      v15 = v14;
      if ( v14 )
      {
        v16 = a8;
        v17 = 0;
        v18 = 0;
        do
        {
          v14[v18] = a1;
          v18 = (unsigned int)(v18 + 1);
          a1 = (struct _tag_FW_RULE **)*a1;
        }
        while ( a1 );
        qsort(v14, v12, 8u, CompareRulesByAction);
        *(_QWORD *)a8 = 0x400000004LL;
        *((_DWORD *)a8 + 2) = 4;
        v19 = 0;
        *(_QWORD *)a9 = 0;
        a9[2] = 0;
        v43 = 0;
        while ( 1 )
        {
          v20 = v15[v19];
          if ( (*(_BYTE *)(v20 + 292) & 1) == 0 || *(_DWORD *)(v20 + 44) != 1 )
            goto LABEL_16;
          v21 = *(unsigned __int16 *)(v20 + 48);
          if ( a6 < 0x100u )
            break;
          if ( v21 != a5 && (_WORD)v21 != 256 )
            goto LABEL_16;
          v22 = *(const WCHAR **)(v20 + 272);
          if ( lpString2 )
          {
            if ( v22 && CompareStringW(0x7Fu, 1u, v22, -1, lpString2, -1) != 2 )
              goto LABEL_16;
            v24 = 1;
          }
          else
          {
            v24 = 0;
            if ( v22 && *(_DWORD *)(v20 + 288) != 2 )
              goto LABEL_16;
          }
          v25 = *(_DWORD *)(v20 + 64);
          if ( v9 )
          {
            if ( v25 )
            {
              for ( i = 0; ; ++i )
              {
                if ( i >= v25 )
                  goto LABEL_16;
                v27 = *(_QWORD *)(v20 + 72);
                if ( *(_WORD *)(v27 + 4LL * i) <= v9 && *(_WORD *)(v27 + 4LL * i + 2) >= v9 )
                  break;
              }
              goto LABEL_37;
            }
            if ( v24 )
              goto LABEL_37;
            v40 = *(_QWORD *)(v20 + 272) == 0;
          }
          else
          {
            v40 = v25 == 0;
          }
          if ( v40 )
            goto LABEL_37;
LABEL_16:
          v19 = (unsigned int)(v43 + 1);
          v43 = v19;
          if ( (unsigned int)v19 >= v12 )
          {
            FwBaseFree(v15);
            return v17;
          }
        }
        if ( (_WORD)v21 == 1 )
        {
          v28 = *(_DWORD *)(v20 + 56);
          if ( !v28 )
            goto LABEL_16;
          v29 = *(_QWORD *)(v20 + 64);
          v30 = 0;
          for ( j = 0; j < v28; ++j )
          {
            if ( *(_BYTE *)(v29 + 4LL * j) == (_BYTE)a6 && *(_WORD *)(v29 + 4LL * j + 2) == 256 )
              v30 = 1;
          }
          v16 = a8;
        }
        else
        {
          if ( v21 != 58 )
            goto LABEL_16;
          v37 = *(_DWORD *)(v20 + 56);
          if ( !v37 )
            goto LABEL_16;
          v38 = *(_QWORD *)(v20 + 64);
          v39 = 0;
          v30 = 0;
          do
          {
            if ( *(_BYTE *)(v38 + 4LL * v39) == (_BYTE)a6 && *(_WORD *)(v38 + 4LL * v39 + 2) == 256 )
              v30 = 1;
            ++v39;
          }
          while ( v39 < v37 );
          v9 = a4;
        }
        if ( !v30 )
          goto LABEL_16;
LABEL_37:
        if ( a7 && !LocalAddressCoveredByRule((struct _tag_FW_RULE *)v20, a3, a7) )
          goto LABEL_16;
        v32 = 0;
        v33 = 0;
        while ( 1 )
        {
          v34 = *(_DWORD *)(v20 + 40);
          if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(v32) & v34) == 0 )
            goto LABEL_62;
          if ( *(_DWORD *)(v20 + 176)
            || *(_DWORD *)(v20 + 180)
            || *(_DWORD *)(v20 + 184)
            || *(_DWORD *)(v20 + 216)
            || *(_DWORD *)(v20 + 200)
            || *(_DWORD *)(v20 + 232)
            || *(_QWORD *)(v20 + 296)
            || *(_QWORD *)(v20 + 304)
            || (*(_BYTE *)(v20 + 292) & 6) != 0
            || (v35 = 0, *(_WORD *)(v20 + 48) != 1) && *(_WORD *)(v20 + 48) != 58 && *(_WORD *)(v20 + 56) )
          {
            v35 = 1;
          }
          if ( *(_QWORD *)(v20 + 280) || *(_DWORD *)(v20 + 264) || *(_DWORD *)(v20 + 248) )
            v35 = 1;
          v36 = *(_DWORD *)(v20 + 288);
          if ( v36 == 2 )
          {
            if ( v35 && *((_DWORD *)v16 + v33) == 3 )
            {
LABEL_75:
              *((_DWORD *)v16 + v33) = 3;
              a9[v33] = 1;
LABEL_61:
              v17 = 1;
              goto LABEL_62;
            }
          }
          else if ( v36 == 3 && *((_DWORD *)v16 + v33) == 2 && a9[v33] )
          {
            goto LABEL_75;
          }
          if ( v36 < *((_DWORD *)v16 + v33) )
          {
            if ( v36 != 1 || *((_DWORD *)v16 + v33) != 3 )
              a9[v33] = v35;
            *((_DWORD *)v16 + v33) = v36;
            goto LABEL_61;
          }
          if ( v36 == *((_DWORD *)v16 + v33) )
          {
            if ( !v35 )
              a9[v33] = 0;
            goto LABEL_61;
          }
LABEL_62:
          ++v32;
          ++v33;
          if ( v32 >= 3 )
          {
            v12 = v41;
            v15 = v42;
            v9 = a4;
            lpString2 = a2;
            goto LABEL_16;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800197d8  mov     [rsp+arg_18], r9w
0x1800197de  mov     [rsp+arg_10], r8d
0x1800197e3  mov     [rsp+arg_8], rdx
0x1800197e8  push    rbx
0x1800197e9  push    rbp
0x1800197ea  push    rsi
0x1800197eb  push    rdi
0x1800197ec  push    r12
0x1800197ee  push    r13
0x1800197f0  push    r14
0x1800197f2  push    r15
0x1800197f4  sub     rsp, 48h
0x1800197f8  movzx   esi, r9w
0x1800197fc  mov     rbp, rdx
0x1800197ff  mov     rbx, rcx
0x180019802  mov     rcx, cs:WPP_GLOBAL_Control
0x180019809  lea     rax, WPP_GLOBAL_Control
0x180019810  cmp     rcx, rax
0x180019813  jnz     loc_180019C34
0x180019819  xor     r14d, r14d
0x18001981c  mov     rax, rbx
0x18001981f  test    rbx, rbx
0x180019822  jz      loc_180019B4F
0x180019828  mov     rax, [rax]
0x18001982b  inc     r14d
0x18001982e  test    rax, rax
0x180019831  jnz     short loc_180019828
0x180019833  mov     [rsp+88h+var_58], r14d
0x180019838  test    r14d, r14d
0x18001983b  jz      loc_180019B4F
0x180019841  lea     edx, [rax+8]
0x180019844  mov     ecx, r14d
0x180019847  mov     edi, r14d
0x18001984a  call    cs:__imp_FwAllocArray
0x180019850  mov     [rsp+88h+var_50], rax
0x180019855  mov     r15, rax
0x180019858  test    rax, rax
0x18001985b  jz      loc_180019B4F
0x180019861  mov     r13, [rsp+88h+arg_38]
0x180019869  xor     r12d, r12d
0x18001986c  xor     ecx, ecx
0x18001986e  mov     [rax+rcx*8], rbx
0x180019872  inc     ecx
0x180019874  mov     rbx, [rbx]
0x180019877  test    rbx, rbx
0x18001987a  jnz     short loc_18001986E
0x18001987c  lea     r9, CompareRulesByAction; CompareFunction
0x180019883  mov     rdx, rdi; NumOfElements
0x180019886  lea     r8d, [rbx+8]; SizeOfElements
0x18001988a  mov     rcx, rax; Base
0x18001988d  call    cs:__imp_qsort
0x180019893  mov     rcx, [rsp+88h+arg_40]
0x18001989b  mov     rax, 400000004h
0x1800198a5  mov     [r13+0], rax
0x1800198a9  mov     [r13+8], eax
0x1800198ad  mov     eax, ebx
0x1800198af  mov     [rcx], rbx
0x1800198b2  mov     [rcx+8], ebx
0x1800198b5  mov     [rsp+88h+arg_0], eax
0x1800198bc  test    r14d, r14d
0x1800198bf  jz      loc_180019966
0x1800198c5  mov     ecx, 100h
0x1800198ca  lea     r11d, [rbx+1]
0x1800198ce  mov     rdi, [r15+rax*8]
0x1800198d2  test    [rdi+124h], r11b
0x1800198d9  jz      short loc_18001994C
0x1800198db  cmp     [rdi+2Ch], r11d
0x1800198df  jnz     short loc_18001994C
0x1800198e1  movzx   r10d, [rsp+88h+arg_28]
0x1800198ea  movzx   eax, word ptr [rdi+30h]
0x1800198ee  cmp     r10w, cx
0x1800198f2  jb      loc_1800199C5
0x1800198f8  cmp     eax, [rsp+88h+arg_20]
0x1800198ff  jnz     loc_1800199BA
0x180019905  mov     rax, [rdi+110h]
0x18001990c  test    rbp, rbp
0x18001990f  jz      loc_180019B56
0x180019915  test    rax, rax
0x180019918  jz      short loc_180019983
0x18001991a  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019922  or      r9d, 0FFFFFFFFh; cchCount1
0x180019926  mov     r8, rax; lpString1
0x180019929  mov     [rsp+88h+lpString2], rbp; lpString2
0x18001992e  mov     edx, r11d; dwCmpFlags
0x180019931  mov     ecx, 7Fh; Locale
0x180019936  call    cs:__imp_CompareStringW
0x18001993c  mov     r11d, 1
0x180019942  cmp     eax, 2
0x180019945  jz      short loc_180019983
0x180019947  mov     ecx, 100h
0x18001994c  mov     eax, [rsp+88h+arg_0]
0x180019953  add     eax, r11d
0x180019956  mov     [rsp+88h+arg_0], eax
0x18001995d  cmp     eax, r14d
0x180019960  jb      loc_1800198CE
0x180019966  mov     rcx, r15
0x180019969  call    cs:__imp_FwBaseFree
0x18001996f  mov     eax, r12d
0x180019972  add     rsp, 48h
0x180019976  pop     r15
0x180019978  pop     r14
0x18001997a  pop     r13
0x18001997c  pop     r12
0x18001997e  pop     rdi
0x18001997f  pop     rsi
0x180019980  pop     rbp
0x180019981  pop     rbx
0x180019982  retn
0x180019983  mov     edx, r11d
0x180019986  mov     ecx, [rdi+40h]
0x180019989  test    si, si
0x18001998c  jz      loc_180019C77
0x180019992  test    ecx, ecx
0x180019994  jz      loc_180019C66
0x18001999a  mov     eax, ebx
0x18001999c  cmp     eax, ecx
0x18001999e  jnb     short loc_180019947
0x1800199a0  mov     r8, [rdi+48h]
0x1800199a4  mov     edx, eax
0x1800199a6  cmp     [r8+rdx*4], si
0x1800199ab  ja      short loc_1800199B5
0x1800199ad  cmp     [r8+rdx*4+2], si
0x1800199b3  jnb     short loc_180019A12
0x1800199b5  add     eax, r11d
0x1800199b8  jmp     short loc_18001999C
0x1800199ba  cmp     ax, cx
0x1800199bd  jz      loc_180019905
0x1800199c3  jmp     short loc_18001994C
0x1800199c5  cmp     ax, r11w
0x1800199c9  jnz     loc_180019C58
0x1800199cf  mov     ecx, [rdi+38h]
0x1800199d2  test    ecx, ecx
0x1800199d4  jz      loc_180019947
0x1800199da  mov     r9, [rdi+40h]
0x1800199de  mov     edx, ebx
0x1800199e0  mov     eax, ebx
0x1800199e2  mov     r13d, 100h
0x1800199e8  mov     r8d, eax
0x1800199eb  cmp     [r9+r8*4], r10b
0x1800199ef  jnz     short loc_1800199FB
0x1800199f1  cmp     [r9+r8*4+2], r13w
0x1800199f7  cmovz   edx, r11d
0x1800199fb  add     eax, r11d
0x1800199fe  cmp     eax, ecx
0x180019a00  jb      short loc_1800199E8
0x180019a02  mov     r13, [rsp+88h+arg_38]
0x180019a0a  test    edx, edx
0x180019a0c  jz      loc_180019947
0x180019a12  cmp     [rsp+88h+arg_30], rbx
0x180019a1a  jnz     loc_180019C84
0x180019a20  mov     r15, [rsp+88h+arg_40]
0x180019a28  xor     r14d, r14d
0x180019a2b  mov     ebp, r14d
0x180019a2e  mov     esi, r14d
0x180019a31  mov     ebx, [rdi+28h]
0x180019a34  mov     ecx, ebp
0x180019a36  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019a3c  test    ebx, eax
0x180019a3e  jz      loc_180019B73
0x180019a44  cmp     [rdi+0B0h], r14d
0x180019a4b  jnz     loc_180019B8F
0x180019a51  cmp     [rdi+0B4h], r14d
0x180019a58  jnz     loc_180019B8F
0x180019a5e  cmp     [rdi+0B8h], r14d
0x180019a65  jnz     loc_180019B8F
0x180019a6b  cmp     [rdi+0D8h], r14d
0x180019a72  jnz     loc_180019B8F
0x180019a78  cmp     [rdi+0C8h], r14d
0x180019a7f  jnz     loc_180019B8F
0x180019a85  cmp     [rdi+0E8h], r14d
0x180019a8c  jnz     loc_180019B8F
0x180019a92  cmp     [rdi+128h], r14
0x180019a99  jnz     loc_180019B8F
0x180019a9f  cmp     [rdi+130h], r14
0x180019aa6  jnz     loc_180019B8F
0x180019aac  test    byte ptr [rdi+124h], 6
0x180019ab3  mov     r11d, 1
0x180019ab9  jnz     loc_180019B95
0x180019abf  mov     ecx, r14d
0x180019ac2  cmp     [rdi+30h], r11w
0x180019ac7  jz      short loc_180019ADB
0x180019ac9  cmp     word ptr [rdi+30h], 3Ah ; ':'
0x180019ace  jz      short loc_180019ADB
0x180019ad0  cmp     [rdi+38h], r14w
0x180019ad5  jnz     loc_180019B95
0x180019adb  cmp     [rdi+118h], r14
0x180019ae2  jz      loc_180019BC3
0x180019ae8  mov     ecx, r11d
0x180019aeb  mov     eax, [rdi+120h]
0x180019af1  cmp     eax, 2
0x180019af4  jz      loc_180019B9D
0x180019afa  cmp     eax, 3
0x180019afd  jnz     short loc_180019B0B
0x180019aff  cmp     dword ptr [r13+rsi*4+0], 2
0x180019b05  jz      loc_180019CAC
0x180019b0b  cmp     eax, [r13+rsi*4+0]
0x180019b10  jl      short loc_180019B7B
0x180019b12  jnz     short loc_180019B1F
0x180019b14  test    ecx, ecx
0x180019b16  jz      loc_180019CCC
0x180019b1c  mov     r12d, r11d
0x180019b1f  add     ebp, r11d
0x180019b22  add     rsi, r11
0x180019b25  cmp     ebp, 3
0x180019b28  jb      loc_180019A31
0x180019b2e  mov     r14d, [rsp+88h+var_58]
0x180019b33  xor     ebx, ebx
0x180019b35  mov     r15, [rsp+88h+var_50]
0x180019b3a  movzx   esi, [rsp+88h+arg_18]
0x180019b42  mov     rbp, [rsp+88h+arg_8]
0x180019b4a  jmp     loc_180019947
0x180019b4f  xor     eax, eax
0x180019b51  jmp     loc_180019972
0x180019b56  mov     edx, ebx
0x180019b58  test    rax, rax
0x180019b5b  jz      loc_180019986
0x180019b61  cmp     dword ptr [rdi+120h], 2
0x180019b68  jnz     loc_18001994C
0x180019b6e  jmp     loc_180019986
0x180019b73  mov     r11d, 1
0x180019b79  jmp     short loc_180019B1F
0x180019b7b  cmp     eax, r11d
0x180019b7e  jz      loc_180019CBB
0x180019b84  mov     [r15+rsi*4], ecx
0x180019b88  mov     [r13+rsi*4+0], eax
0x180019b8d  jmp     short loc_180019B1C
0x180019b8f  mov     r11d, 1
0x180019b95  mov     ecx, r11d
0x180019b98  jmp     loc_180019ADB
0x180019b9d  test    ecx, ecx
0x180019b9f  jz      loc_180019B0B
0x180019ba5  cmp     dword ptr [r13+rsi*4+0], 3
0x180019bab  jnz     loc_180019B0B
0x180019bb1  mov     dword ptr [r13+rsi*4+0], 3
0x180019bba  mov     [r15+rsi*4], r11d
0x180019bbe  jmp     loc_180019B1C
0x180019bc3  cmp     [rdi+108h], r14d
0x180019bca  jnz     loc_180019AE8
0x180019bd0  cmp     [rdi+0F8h], r14d
0x180019bd7  jz      loc_180019AEB
0x180019bdd  jmp     loc_180019AE8
0x180019be2  cmp     ax, r11w
0x180019be6  jz      loc_1800199CF
0x180019bec  cmp     eax, 3Ah ; ':'
0x180019bef  jnz     loc_18001994C
0x180019bf5  mov     ecx, [rdi+38h]
0x180019bf8  test    ecx, ecx
0x180019bfa  jz      loc_180019947
0x180019c00  mov     r9, [rdi+40h]
0x180019c04  mov     eax, ebx
0x180019c06  mov     edx, ebx
0x180019c08  mov     esi, 100h
0x180019c0d  mov     r8d, eax
0x180019c10  cmp     [r9+r8*4], r10b
0x180019c14  jnz     short loc_180019C20
0x180019c16  cmp     [r9+r8*4+2], si
0x180019c1c  cmovz   edx, r11d
0x180019c20  add     eax, r11d
0x180019c23  cmp     eax, ecx
0x180019c25  jb      short loc_180019C0D
0x180019c27  movzx   esi, [rsp+88h+arg_18]
0x180019c2f  jmp     loc_180019A0A
0x180019c34  test    byte ptr [rcx+1Ch], 8
0x180019c38  jz      loc_180019819
0x180019c3e  mov     rcx, [rcx+10h]
0x180019c42  lea     r8, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids
0x180019c49  mov     edx, 0Ch
0x180019c4e  call    WPP_SF_
0x180019c53  jmp     loc_180019819
0x180019c58  cmp     eax, 3Ah ; ':'
0x180019c5b  jnz     loc_18001994C
0x180019c61  jmp     loc_180019BE2
0x180019c66  test    edx, edx
0x180019c68  jnz     loc_180019A12
0x180019c6e  cmp     [rdi+110h], rbx
0x180019c75  jmp     short loc_180019C79
0x180019c77  test    ecx, ecx
0x180019c79  jnz     loc_180019947
0x180019c7f  jmp     loc_180019A12
0x180019c84  mov     r8, [rsp+88h+arg_30]; union FW_INET_ADDR_STORAGE *
0x180019c8c  mov     rcx, rdi; struct _tag_FW_RULE *
0x180019c8f  mov     edx, [rsp+88h+arg_10]; enum NET_FW_IP_VERSION_
0x180019c96  call    ?LocalAddressCoveredByRule@@YAHPEAU_tag_FW_RULE@@W4NET_FW_IP_VERSION_@@PEATFW_INET_ADDR_STORAGE@@@Z; LocalAddressCoveredByRule(_tag_FW_RULE *,NET_FW_IP_VERSION_,FW_INET_ADDR_STORAGE *)
0x180019c9b  test    eax, eax
0x180019c9d  jnz     loc_180019A20
0x180019ca3  lea     r11d, [rax+1]
0x180019ca7  jmp     loc_180019947
0x180019cac  cmp     [r15+rsi*4], r14d
0x180019cb0  jz      loc_180019B0B
0x180019cb6  jmp     loc_180019BB1
0x180019cbb  cmp     dword ptr [r13+rsi*4+0], 3
0x180019cc1  jz      loc_180019B88
0x180019cc7  jmp     loc_180019B84
0x180019ccc  mov     [r15+rsi*4], r14d
0x180019cd0  jmp     loc_180019B1C
```
