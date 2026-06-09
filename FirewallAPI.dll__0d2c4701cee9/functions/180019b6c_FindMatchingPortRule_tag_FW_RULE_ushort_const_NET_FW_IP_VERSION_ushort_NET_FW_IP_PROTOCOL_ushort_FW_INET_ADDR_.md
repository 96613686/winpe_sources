# FindMatchingPortRule(_tag_FW_RULE *,ushort const *,NET_FW_IP_VERSION_,ushort,NET_FW_IP_PROTOCOL_,ushort,FW_INET_ADDR_STORAGE *,_tag_FW_RULE_ACTION * const,int * const)

- ea: `0x180019b6c`
- end: `0x18001a088`
- name: `?FindMatchingPortRule@@YAHPEAU_tag_FW_RULE@@PEBGW4NET_FW_IP_VERSION_@@GW4NET_FW_IP_PROTOCOL_@@GPEATFW_INET_ADDR_STORAGE@@QEAW4_tag_FW_RULE_ACTION@@QEAH@Z`
- size: `1308`
- prototype: `int(struct _tag_FW_RULE *, const unsigned __int16 *, enum NET_FW_IP_VERSION_, unsigned __int16, enum NET_FW_IP_PROTOCOL_, unsigned __int16, union FW_INET_ADDR_STORAGE *, enum _tag_FW_RULE_ACTION *const, int *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191e0`

## callees

- `0x180019b6c`
- `0x18003336c`
- `0x180039bb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180019c27`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180019c27`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019cd6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019cd6`
- `fwbase!FwBaseFree` at `0x180019d0f`
- `fwbase!FwBaseFree` at `0x180019d0f`
- `fwbase!FwAllocArray` at `0x180019bde`
- `fwbase!FwAllocArray` at `0x180019bde`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019de3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019de3`

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
0x180019b6c  mov     [rsp+arg_18], r9w
0x180019b72  mov     [rsp+arg_10], r8d
0x180019b77  mov     [rsp+arg_8], rdx
0x180019b7c  push    rbx
0x180019b7d  push    rbp
0x180019b7e  push    rsi
0x180019b7f  push    rdi
0x180019b80  push    r12
0x180019b82  push    r13
0x180019b84  push    r14
0x180019b86  push    r15
0x180019b88  sub     rsp, 48h
0x180019b8c  movzx   esi, r9w
0x180019b90  mov     rbp, rdx
0x180019b93  mov     rbx, rcx
0x180019b96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b9d  lea     rax, WPP_GLOBAL_Control
0x180019ba4  cmp     rcx, rax
0x180019ba7  jnz     loc_180019FE7
0x180019bad  xor     r14d, r14d
0x180019bb0  mov     rax, rbx
0x180019bb3  test    rbx, rbx
0x180019bb6  jz      loc_180019F02
0x180019bbc  mov     rax, [rax]
0x180019bbf  inc     r14d
0x180019bc2  test    rax, rax
0x180019bc5  jnz     short loc_180019BBC
0x180019bc7  mov     [rsp+88h+var_58], r14d
0x180019bcc  test    r14d, r14d
0x180019bcf  jz      loc_180019F02
0x180019bd5  lea     edx, [rax+8]
0x180019bd8  mov     ecx, r14d
0x180019bdb  mov     edi, r14d
0x180019bde  call    cs:__imp_FwAllocArray
0x180019be5  nop     dword ptr [rax+rax+00h]
0x180019bea  mov     [rsp+88h+var_50], rax
0x180019bef  mov     r15, rax
0x180019bf2  test    rax, rax
0x180019bf5  jz      loc_180019F02
0x180019bfb  mov     r13, [rsp+88h+arg_38]
0x180019c03  xor     r12d, r12d
0x180019c06  xor     ecx, ecx
0x180019c08  mov     [rax+rcx*8], rbx
0x180019c0c  inc     ecx
0x180019c0e  mov     rbx, [rbx]
0x180019c11  test    rbx, rbx
0x180019c14  jnz     short loc_180019C08
0x180019c16  lea     r9, CompareRulesByAction; CompareFunction
0x180019c1d  mov     rdx, rdi; NumOfElements
0x180019c20  lea     r8d, [rbx+8]; SizeOfElements
0x180019c24  mov     rcx, rax; Base
0x180019c27  call    cs:__imp_qsort
0x180019c2e  nop     dword ptr [rax+rax+00h]
0x180019c33  mov     rcx, [rsp+88h+arg_40]
0x180019c3b  mov     rax, 400000004h
0x180019c45  mov     [r13+0], rax
0x180019c49  mov     [r13+8], eax
0x180019c4d  mov     eax, ebx
0x180019c4f  mov     [rcx], rbx
0x180019c52  mov     [rcx+8], ebx
0x180019c55  mov     [rsp+88h+arg_0], eax
0x180019c5c  test    r14d, r14d
0x180019c5f  jz      loc_180019D0C
0x180019c65  mov     ecx, 100h
0x180019c6a  lea     r11d, [rbx+1]
0x180019c6e  mov     rdi, [r15+rax*8]
0x180019c72  test    [rdi+124h], r11b
0x180019c79  jz      short loc_180019CF2
0x180019c7b  cmp     [rdi+2Ch], r11d
0x180019c7f  jnz     short loc_180019CF2
0x180019c81  movzx   r10d, [rsp+88h+arg_28]
0x180019c8a  movzx   eax, word ptr [rdi+30h]
0x180019c8e  cmp     r10w, cx
0x180019c92  jb      loc_180019D72
0x180019c98  cmp     eax, [rsp+88h+arg_20]
0x180019c9f  jnz     loc_180019D67
0x180019ca5  mov     rax, [rdi+110h]
0x180019cac  test    rbp, rbp
0x180019caf  jz      loc_180019F09
0x180019cb5  test    rax, rax
0x180019cb8  jz      short loc_180019D30
0x180019cba  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019cc2  or      r9d, 0FFFFFFFFh; cchCount1
0x180019cc6  mov     r8, rax; lpString1
0x180019cc9  mov     [rsp+88h+lpString2], rbp; lpString2
0x180019cce  mov     edx, r11d; dwCmpFlags
0x180019cd1  mov     ecx, 7Fh; Locale
0x180019cd6  call    cs:__imp_CompareStringW
0x180019cdd  nop     dword ptr [rax+rax+00h]
0x180019ce2  mov     r11d, 1
0x180019ce8  cmp     eax, 2
0x180019ceb  jz      short loc_180019D30
0x180019ced  mov     ecx, 100h
0x180019cf2  mov     eax, [rsp+88h+arg_0]
0x180019cf9  add     eax, r11d
0x180019cfc  mov     [rsp+88h+arg_0], eax
0x180019d03  cmp     eax, r14d
0x180019d06  jb      loc_180019C6E
0x180019d0c  mov     rcx, r15
0x180019d0f  call    cs:__imp_FwBaseFree
0x180019d16  nop     dword ptr [rax+rax+00h]
0x180019d1b  mov     eax, r12d
0x180019d1e  add     rsp, 48h
0x180019d22  pop     r15
0x180019d24  pop     r14
0x180019d26  pop     r13
0x180019d28  pop     r12
0x180019d2a  pop     rdi
0x180019d2b  pop     rsi
0x180019d2c  pop     rbp
0x180019d2d  pop     rbx
0x180019d2e  retn
0x180019d30  mov     edx, r11d
0x180019d33  mov     ecx, [rdi+40h]
0x180019d36  test    si, si
0x180019d39  jz      loc_18001A02A
0x180019d3f  test    ecx, ecx
0x180019d41  jz      loc_18001A019
0x180019d47  mov     eax, ebx
0x180019d49  cmp     eax, ecx
0x180019d4b  jnb     short loc_180019CED
0x180019d4d  mov     r8, [rdi+48h]
0x180019d51  mov     edx, eax
0x180019d53  cmp     [r8+rdx*4], si
0x180019d58  ja      short loc_180019D62
0x180019d5a  cmp     [r8+rdx*4+2], si
0x180019d60  jnb     short loc_180019DBF
0x180019d62  add     eax, r11d
0x180019d65  jmp     short loc_180019D49
0x180019d67  cmp     ax, cx
0x180019d6a  jz      loc_180019CA5
0x180019d70  jmp     short loc_180019CF2
0x180019d72  cmp     ax, r11w
0x180019d76  jnz     loc_18001A00B
0x180019d7c  mov     ecx, [rdi+38h]
0x180019d7f  test    ecx, ecx
0x180019d81  jz      loc_180019CED
0x180019d87  mov     r9, [rdi+40h]
0x180019d8b  mov     edx, ebx
0x180019d8d  mov     eax, ebx
0x180019d8f  mov     r13d, 100h
0x180019d95  mov     r8d, eax
0x180019d98  cmp     [r9+r8*4], r10b
0x180019d9c  jnz     short loc_180019DA8
0x180019d9e  cmp     [r9+r8*4+2], r13w
0x180019da4  cmovz   edx, r11d
0x180019da8  add     eax, r11d
0x180019dab  cmp     eax, ecx
0x180019dad  jb      short loc_180019D95
0x180019daf  mov     r13, [rsp+88h+arg_38]
0x180019db7  test    edx, edx
0x180019db9  jz      loc_180019CED
0x180019dbf  cmp     [rsp+88h+arg_30], rbx
0x180019dc7  jnz     loc_18001A037
0x180019dcd  mov     r15, [rsp+88h+arg_40]
0x180019dd5  xor     r14d, r14d
0x180019dd8  mov     ebp, r14d
0x180019ddb  mov     esi, r14d
0x180019dde  mov     ebx, [rdi+28h]
0x180019de1  mov     ecx, ebp
0x180019de3  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019dea  nop     dword ptr [rax+rax+00h]
0x180019def  test    ebx, eax
0x180019df1  jz      loc_180019F26
0x180019df7  cmp     [rdi+0B0h], r14d
0x180019dfe  jnz     loc_180019F42
0x180019e04  cmp     [rdi+0B4h], r14d
0x180019e0b  jnz     loc_180019F42
0x180019e11  cmp     [rdi+0B8h], r14d
0x180019e18  jnz     loc_180019F42
0x180019e1e  cmp     [rdi+0D8h], r14d
0x180019e25  jnz     loc_180019F42
0x180019e2b  cmp     [rdi+0C8h], r14d
0x180019e32  jnz     loc_180019F42
0x180019e38  cmp     [rdi+0E8h], r14d
0x180019e3f  jnz     loc_180019F42
0x180019e45  cmp     [rdi+128h], r14
0x180019e4c  jnz     loc_180019F42
0x180019e52  cmp     [rdi+130h], r14
0x180019e59  jnz     loc_180019F42
0x180019e5f  test    byte ptr [rdi+124h], 6
0x180019e66  mov     r11d, 1
0x180019e6c  jnz     loc_180019F48
0x180019e72  mov     ecx, r14d
0x180019e75  cmp     [rdi+30h], r11w
0x180019e7a  jz      short loc_180019E8E
0x180019e7c  cmp     word ptr [rdi+30h], 3Ah ; ':'
0x180019e81  jz      short loc_180019E8E
0x180019e83  cmp     [rdi+38h], r14w
0x180019e88  jnz     loc_180019F48
0x180019e8e  cmp     [rdi+118h], r14
0x180019e95  jz      loc_180019F76
0x180019e9b  mov     ecx, r11d
0x180019e9e  mov     eax, [rdi+120h]
0x180019ea4  cmp     eax, 2
0x180019ea7  jz      loc_180019F50
0x180019ead  cmp     eax, 3
0x180019eb0  jnz     short loc_180019EBE
0x180019eb2  cmp     dword ptr [r13+rsi*4+0], 2
0x180019eb8  jz      loc_18001A05F
0x180019ebe  cmp     eax, [r13+rsi*4+0]
0x180019ec3  jl      short loc_180019F2E
0x180019ec5  jnz     short loc_180019ED2
0x180019ec7  test    ecx, ecx
0x180019ec9  jz      loc_18001A07F
0x180019ecf  mov     r12d, r11d
0x180019ed2  add     ebp, r11d
0x180019ed5  add     rsi, r11
0x180019ed8  cmp     ebp, 3
0x180019edb  jb      loc_180019DDE
0x180019ee1  mov     r14d, [rsp+88h+var_58]
0x180019ee6  xor     ebx, ebx
0x180019ee8  mov     r15, [rsp+88h+var_50]
0x180019eed  movzx   esi, [rsp+88h+arg_18]
0x180019ef5  mov     rbp, [rsp+88h+arg_8]
0x180019efd  jmp     loc_180019CED
0x180019f02  xor     eax, eax
0x180019f04  jmp     loc_180019D1E
0x180019f09  mov     edx, ebx
0x180019f0b  test    rax, rax
0x180019f0e  jz      loc_180019D33
0x180019f14  cmp     dword ptr [rdi+120h], 2
0x180019f1b  jnz     loc_180019CF2
0x180019f21  jmp     loc_180019D33
0x180019f26  mov     r11d, 1
0x180019f2c  jmp     short loc_180019ED2
0x180019f2e  cmp     eax, r11d
0x180019f31  jz      loc_18001A06E
0x180019f37  mov     [r15+rsi*4], ecx
0x180019f3b  mov     [r13+rsi*4+0], eax
0x180019f40  jmp     short loc_180019ECF
0x180019f42  mov     r11d, 1
0x180019f48  mov     ecx, r11d
0x180019f4b  jmp     loc_180019E8E
0x180019f50  test    ecx, ecx
0x180019f52  jz      loc_180019EBE
0x180019f58  cmp     dword ptr [r13+rsi*4+0], 3
0x180019f5e  jnz     loc_180019EBE
0x180019f64  mov     dword ptr [r13+rsi*4+0], 3
0x180019f6d  mov     [r15+rsi*4], r11d
0x180019f71  jmp     loc_180019ECF
0x180019f76  cmp     [rdi+108h], r14d
0x180019f7d  jnz     loc_180019E9B
0x180019f83  cmp     [rdi+0F8h], r14d
0x180019f8a  jz      loc_180019E9E
0x180019f90  jmp     loc_180019E9B
0x180019f95  cmp     ax, r11w
0x180019f99  jz      loc_180019D7C
0x180019f9f  cmp     eax, 3Ah ; ':'
0x180019fa2  jnz     loc_180019CF2
0x180019fa8  mov     ecx, [rdi+38h]
0x180019fab  test    ecx, ecx
0x180019fad  jz      loc_180019CED
0x180019fb3  mov     r9, [rdi+40h]
0x180019fb7  mov     eax, ebx
0x180019fb9  mov     edx, ebx
0x180019fbb  mov     esi, 100h
0x180019fc0  mov     r8d, eax
0x180019fc3  cmp     [r9+r8*4], r10b
0x180019fc7  jnz     short loc_180019FD3
0x180019fc9  cmp     [r9+r8*4+2], si
0x180019fcf  cmovz   edx, r11d
0x180019fd3  add     eax, r11d
0x180019fd6  cmp     eax, ecx
0x180019fd8  jb      short loc_180019FC0
0x180019fda  movzx   esi, [rsp+88h+arg_18]
0x180019fe2  jmp     loc_180019DB7
0x180019fe7  test    byte ptr [rcx+1Ch], 8
0x180019feb  jz      loc_180019BAD
0x180019ff1  mov     rcx, [rcx+10h]
0x180019ff5  lea     r8, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids
0x180019ffc  mov     edx, 0Ch
0x18001a001  call    WPP_SF_
0x18001a006  jmp     loc_180019BAD
0x18001a00b  cmp     eax, 3Ah ; ':'
0x18001a00e  jnz     loc_180019CF2
0x18001a014  jmp     loc_180019F95
0x18001a019  test    edx, edx
0x18001a01b  jnz     loc_180019DBF
0x18001a021  cmp     [rdi+110h], rbx
0x18001a028  jmp     short loc_18001A02C
0x18001a02a  test    ecx, ecx
0x18001a02c  jnz     loc_180019CED
0x18001a032  jmp     loc_180019DBF
0x18001a037  mov     r8, [rsp+88h+arg_30]; union FW_INET_ADDR_STORAGE *
0x18001a03f  mov     rcx, rdi; struct _tag_FW_RULE *
0x18001a042  mov     edx, [rsp+88h+arg_10]; enum NET_FW_IP_VERSION_
0x18001a049  call    ?LocalAddressCoveredByRule@@YAHPEAU_tag_FW_RULE@@W4NET_FW_IP_VERSION_@@PEATFW_INET_ADDR_STORAGE@@@Z; LocalAddressCoveredByRule(_tag_FW_RULE *,NET_FW_IP_VERSION_,FW_INET_ADDR_STORAGE *)
0x18001a04e  test    eax, eax
0x18001a050  jnz     loc_180019DCD
0x18001a056  lea     r11d, [rax+1]
0x18001a05a  jmp     loc_180019CED
0x18001a05f  cmp     [r15+rsi*4], r14d
0x18001a063  jz      loc_180019EBE
0x18001a069  jmp     loc_180019F64
0x18001a06e  cmp     dword ptr [r13+rsi*4+0], 3
0x18001a074  jz      loc_180019F3B
0x18001a07a  jmp     loc_180019F37
0x18001a07f  mov     [r15+rsi*4], r14d
0x18001a083  jmp     loc_180019ECF
  ... truncated ...
```
