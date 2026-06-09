# FwOpenAppCDbPolicyStore

- ea: `0x180016790`
- end: `0x180016923`
- name: `FwOpenAppCDbPolicyStore`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180016790`
- `0x180016930`

## import_xrefs

- `fwbase!FwFree` at `0x1800168fe`
- `fwbase!FwFree` at `0x1800168fe`
- `fwbase!FwAlloc` at `0x1800167e9`
- `fwbase!FwAlloc` at `0x1800167e9`
- `fwbase!FwStringCopy` at `0x18001689e`
- `fwbase!FwStringCopy` at `0x18001689e`

## pseudocode

```c
__int64 __fastcall FwOpenAppCDbPolicyStore(int a1, int a2, __int64 *a3)
{
  __int64 v4; // rbp
  __int64 v6; // rax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r8
  _OWORD *v13; // rdx
  struct _tag_WF_POLICY_STORE near **v14; // rax
  __int128 v15; // xmm1
  int v16; // eax

  v4 = a1;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 376, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  *a3 = 0;
  if ( (unsigned int)(a2 - 1) <= 1 )
  {
    v6 = FwAlloc(264);
    v7 = v6;
    if ( v6 )
    {
      v12 = 2;
      v13 = (_OWORD *)v6;
      v14 = &AppCPolicyStore + 33 * v4;
      do
      {
        *v13 = *(_OWORD *)v14;
        v13[1] = *((_OWORD *)v14 + 1);
        v13[2] = *((_OWORD *)v14 + 2);
        v13[3] = *((_OWORD *)v14 + 3);
        v13[4] = *((_OWORD *)v14 + 4);
        v13[5] = *((_OWORD *)v14 + 5);
        v13[6] = *((_OWORD *)v14 + 6);
        v15 = *((_OWORD *)v14 + 7);
        v14 += 16;
        v13[7] = v15;
        v13 += 8;
        --v12;
      }
      while ( v12 );
      *(_QWORD *)v13 = *v14;
      *(_DWORD *)(v7 + 12) = a2;
      v16 = FwStringCopy(*(&AppCPolicyStore + 33 * v4 + 2), v7 + 16);
      v8 = v16;
      if ( v16 >= 0 )
      {
        v16 = FwPolicyStoreFillOfInternalKeys((struct _tag_WF_POLICY_STORE *)v7);
        v8 = v16;
        if ( v16 >= 0 )
        {
          *a3 = v7;
          *(_DWORD *)v7 = 532;
          return v8;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_21:
          FwFree(v7);
          return v8;
        }
        v10 = 379;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_21;
        v10 = 378;
      }
      v11 = (unsigned int)v16;
    }
    else
    {
      v8 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_21;
      v10 = 377;
      v11 = 2147942414LL;
    }
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v11);
    goto LABEL_21;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180016790  push    rbx
0x180016792  push    rbp
0x180016793  push    rsi
0x180016794  push    rdi
0x180016795  push    r14
0x180016797  sub     rsp, 20h
0x18001679b  mov     rsi, r8
0x18001679e  movsxd  rbp, ecx
0x1800167a1  mov     ebx, edx
0x1800167a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167aa  lea     r14, WPP_GLOBAL_Control
0x1800167b1  cmp     rcx, r14
0x1800167b4  jz      short loc_1800167D1
0x1800167b6  test    byte ptr [rcx+1Ch], 8
0x1800167ba  jz      short loc_1800167D1
0x1800167bc  mov     rcx, [rcx+10h]
0x1800167c0  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800167c7  mov     edx, 178h
0x1800167cc  call    WPP_SF_
0x1800167d1  lea     eax, [rbx-1]
0x1800167d4  mov     qword ptr [rsi], 0
0x1800167db  cmp     eax, 1
0x1800167de  ja      loc_180016913
0x1800167e4  mov     ecx, 108h
0x1800167e9  call    cs:__imp_FwAlloc
0x1800167ef  mov     rdi, rax
0x1800167f2  test    rax, rax
0x1800167f5  jnz     short loc_180016823
0x1800167f7  mov     ebx, 8007000Eh
0x1800167fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180016803  cmp     rcx, r14
0x180016806  jz      loc_1800168FB
0x18001680c  test    byte ptr [rcx+1Ch], 1
0x180016810  jz      loc_1800168FB
0x180016816  mov     edx, 179h
0x18001681b  mov     r9d, ebx
0x18001681e  jmp     loc_1800168EB
0x180016823  imul    rcx, rbp, 108h
0x18001682a  mov     r8d, 2
0x180016830  lea     r9, ?AppCPolicyStore@@3PAU_tag_WF_POLICY_STORE@@A; _tag_WF_POLICY_STORE near * AppCPolicyStore
0x180016837  mov     rdx, rdi
0x18001683a  lea     rax, [rcx+r9]
0x18001683e  lea     r10d, [r8+7Eh]
0x180016842  movups  xmm0, xmmword ptr [rax]
0x180016845  movups  xmmword ptr [rdx], xmm0
0x180016848  movups  xmm1, xmmword ptr [rax+10h]
0x18001684c  movups  xmmword ptr [rdx+10h], xmm1
0x180016850  movups  xmm0, xmmword ptr [rax+20h]
0x180016854  movups  xmmword ptr [rdx+20h], xmm0
0x180016858  movups  xmm1, xmmword ptr [rax+30h]
0x18001685c  movups  xmmword ptr [rdx+30h], xmm1
0x180016860  movups  xmm0, xmmword ptr [rax+40h]
0x180016864  movups  xmmword ptr [rdx+40h], xmm0
0x180016868  movups  xmm1, xmmword ptr [rax+50h]
0x18001686c  movups  xmmword ptr [rdx+50h], xmm1
0x180016870  movups  xmm0, xmmword ptr [rax+60h]
0x180016874  movups  xmmword ptr [rdx+60h], xmm0
0x180016878  movups  xmm1, xmmword ptr [rax+70h]
0x18001687c  add     rax, r10
0x18001687f  movups  xmmword ptr [rdx+70h], xmm1
0x180016883  add     rdx, r10
0x180016886  sub     r8, 1
0x18001688a  jnz     short loc_180016842
0x18001688c  mov     rax, [rax]
0x18001688f  mov     [rdx], rax
0x180016892  lea     rdx, [rdi+10h]
0x180016896  mov     [rdi+0Ch], ebx
0x180016899  mov     rcx, [rcx+r9+10h]
0x18001689e  call    cs:__imp_FwStringCopy
0x1800168a4  mov     ebx, eax
0x1800168a6  test    eax, eax
0x1800168a8  jns     short loc_1800168C3
0x1800168aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168b1  cmp     rcx, r14
0x1800168b4  jz      short loc_1800168FB
0x1800168b6  test    byte ptr [rcx+1Ch], 1
0x1800168ba  jz      short loc_1800168FB
0x1800168bc  mov     edx, 17Ah
0x1800168c1  jmp     short loc_1800168E8
0x1800168c3  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x1800168c6  call    ?FwPolicyStoreFillOfInternalKeys@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; FwPolicyStoreFillOfInternalKeys(_tag_WF_POLICY_STORE *)
0x1800168cb  mov     ebx, eax
0x1800168cd  test    eax, eax
0x1800168cf  jns     short loc_180016906
0x1800168d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168d8  cmp     rcx, r14
0x1800168db  jz      short loc_1800168FB
0x1800168dd  test    byte ptr [rcx+1Ch], 1
0x1800168e1  jz      short loc_1800168FB
0x1800168e3  mov     edx, 17Bh
0x1800168e8  mov     r9d, eax
0x1800168eb  mov     rcx, [rcx+10h]
0x1800168ef  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800168f6  call    WPP_SF_d
0x1800168fb  mov     rcx, rdi
0x1800168fe  call    cs:__imp_FwFree
0x180016904  jmp     short loc_18001690F
0x180016906  mov     [rsi], rdi
0x180016909  mov     dword ptr [rdi], 214h
0x18001690f  mov     eax, ebx
0x180016911  jmp     short loc_180016918
0x180016913  mov     eax, 80070057h
0x180016918  add     rsp, 20h
0x18001691c  pop     r14
0x18001691e  pop     rdi
0x18001691f  pop     rsi
0x180016920  pop     rbp
0x180016921  pop     rbx
0x180016922  retn
```
