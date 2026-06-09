# SerializeProcessingModeCharacteristics(std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>,std::allocator<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>>> &,ulong *,uchar * *)

- ea: `0x180022470`
- end: `0x180022745`
- name: `?SerializeProcessingModeCharacteristics@@YAJAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@PEAKPEAPEAE@Z`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800170ac`

## callees

- `0x180010da8`
- `0x180022470`
- `0x18003f78c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800224cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800224cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SerializeProcessingModeCharacteristics(_QWORD *a1, unsigned int *a2, _QWORD *a3)
{
  int v3; // r15d
  _OWORD **v4; // r10
  _OWORD **v6; // r9
  unsigned int i; // esi
  __int64 *v8; // r8
  __int64 *j; // rax
  __int64 v10; // rcx
  _BYTE *v11; // rax
  _DWORD *v12; // rbx
  _BYTE *k; // rcx
  _DWORD *v15; // rdi
  unsigned int v16; // ebp
  _OWORD **v17; // r13
  _OWORD **v18; // r15
  unsigned int v19; // ebp
  unsigned __int16 ***v20; // r14
  unsigned __int16 ***v21; // r12
  unsigned int v22; // ebp
  unsigned int v23; // ebp
  unsigned int v24; // ebp
  unsigned int v25; // ebp
  unsigned int v26; // ebp
  unsigned __int16 *v27; // rdx
  size_t v28; // r8
  __int64 v29; // rax
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-38h]
  int v32; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (_OWORD **)a1[1];
  v6 = (_OWORD **)*a1;
  for ( i = 8; v6 != v4; ++v6 )
  {
    i += 20;
    v8 = (__int64 *)*((_QWORD *)*v6 + 3);
    for ( j = (__int64 *)*((_QWORD *)*v6 + 2); j != v8; i += *(unsigned __int16 *)(*(_QWORD *)v10 + 16LL) + 38 )
      v10 = *j++;
  }
  v11 = CoTaskMemAlloc(i);
  v12 = v11;
  if ( v11 )
  {
    for ( k = &v11[i]; v11 != k; ++v11 )
      *v11 = 0;
    if ( i >= 4 )
    {
      *v12 = 10;
      if ( i - 4 >= 4 )
      {
        v15 = v12 + 2;
        v16 = i - 8;
        v12[1] = (__int64)(a1[1] - *a1) >> 3;
        v17 = (_OWORD **)a1[1];
        v32 = v3;
        v18 = (_OWORD **)*a1;
LABEL_14:
        if ( v18 == v17 )
        {
          *a2 = i;
          *a3 = v12;
          return 0;
        }
        else
        {
          if ( v16 < 0x10 )
          {
            v30 = 126;
          }
          else
          {
            v19 = v16 - 16;
            *(_OWORD *)v15 = **v18;
            if ( v19 < 4 )
            {
              v30 = 130;
            }
            else
            {
              v16 = v19 - 4;
              v15[4] = (__int64)(*((_QWORD *)*v18 + 3) - *((_QWORD *)*v18 + 2)) >> 3;
              v15 += 5;
              v20 = (unsigned __int16 ***)*((_QWORD *)*v18 + 2);
              v21 = (unsigned __int16 ***)*((_QWORD *)*v18 + 3);
              while ( 1 )
              {
                if ( v20 == v21 )
                {
                  ++v18;
                  goto LABEL_14;
                }
                if ( v16 < 4 )
                  break;
                v22 = v16 - 4;
                *v15 = *((_DWORD *)*v20 + 2);
                if ( v22 < 4 )
                {
                  v30 = 139;
                  goto LABEL_29;
                }
                v23 = v22 - 4;
                v15[1] = *((_DWORD *)*v20 + 3);
                if ( v23 < 4 )
                {
                  v30 = 142;
                  goto LABEL_29;
                }
                v24 = v23 - 4;
                v15[2] = *((_DWORD *)*v20 + 4);
                if ( v24 < 4 )
                {
                  v30 = 145;
                  goto LABEL_29;
                }
                v25 = v24 - 4;
                v15[3] = *((_DWORD *)*v20 + 5);
                if ( v25 < 4 )
                {
                  v30 = 148;
                  goto LABEL_29;
                }
                v26 = v25 - 4;
                v15[4] = *((_DWORD *)*v20 + 6);
                v27 = **v20;
                v28 = v27[8] + 18LL;
                if ( v26 < v28 )
                {
                  v30 = 150;
                  goto LABEL_29;
                }
                memcpy_0(v15 + 5, v27, v28);
                v29 = (**v20)[8];
                v15 = (_DWORD *)((char *)v15 + v29 + 38);
                v16 = v26 - v29 - 18;
                ++v20;
              }
              v30 = 136;
            }
          }
LABEL_29:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)0x8007007ALL,
            v32);
          CoTaskMemFree(v12);
          return 2147942522LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)0x8007007ALL,
          v31);
        CoTaskMemFree(v12);
        return 2147942522LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)0x8007007ALL,
        v31);
      CoTaskMemFree(v12);
      return 2147942522LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      v31);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180022470  mov     [rsp+arg_10], r8
0x180022475  mov     [rsp+arg_8], rdx
0x18002247a  push    rbx
0x18002247b  push    rsi
0x18002247c  push    rdi
0x18002247d  push    r14
0x18002247f  sub     rsp, 38h
0x180022483  mov     r10, [rcx+8]
0x180022487  mov     r14, rcx
0x18002248a  mov     r9, [rcx]
0x18002248d  mov     esi, 8
0x180022492  cmp     r9, r10
0x180022495  jz      short loc_1800224CB
0x180022497  mov     rax, [r9]
0x18002249a  add     esi, 14h
0x18002249d  mov     r8, [rax+18h]
0x1800224a1  mov     rax, [rax+10h]
0x1800224a5  cmp     rax, r8
0x1800224a8  jz      short loc_1800224C2
0x1800224aa  mov     rcx, [rax]
0x1800224ad  add     esi, 26h ; '&'
0x1800224b0  add     rax, 8
0x1800224b4  mov     rdx, [rcx]
0x1800224b7  movzx   ecx, word ptr [rdx+10h]
0x1800224bb  add     esi, ecx
0x1800224bd  cmp     rax, r8
0x1800224c0  jnz     short loc_1800224AA
0x1800224c2  add     r9, 8
0x1800224c6  cmp     r9, r10
0x1800224c9  jnz     short loc_180022497
0x1800224cb  mov     ecx, esi; cb
0x1800224cd  mov     edi, esi
0x1800224cf  call    cs:__imp_CoTaskMemAlloc
0x1800224d5  mov     rbx, rax
0x1800224d8  test    rax, rax
0x1800224db  jnz     short loc_180022508
0x1800224dd  mov     rcx, [rsp+58h]; this
0x1800224e2  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800224e9  mov     r9d, 8007000Eh; char *
0x1800224ef  mov     edx, 6Dh ; 'm'; void *
0x1800224f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800224f9  mov     eax, 8007000Eh
0x1800224fe  add     rsp, 38h
0x180022502  pop     r14
0x180022504  pop     rdi
0x180022505  pop     rsi
0x180022506  pop     rbx
0x180022507  retn
0x180022508  lea     rcx, [rdi+rax]
0x18002250c  cmp     rbx, rcx
0x18002250f  jz      short loc_18002251D
0x180022511  xor     edx, edx
0x180022513  mov     [rax], dl
0x180022515  inc     rax
0x180022518  cmp     rax, rcx
0x18002251b  jnz     short loc_180022511
0x18002251d  cmp     esi, 4
0x180022520  jnb     short loc_18002254E
0x180022522  mov     rcx, [rsp+58h]; this
0x180022527  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002252e  mov     r9d, 8007007Ah; char *
0x180022534  mov     edx, 75h ; 'u'; void *
0x180022539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002253e  mov     rcx, rbx; pv
0x180022541  call    cs:__imp_CoTaskMemFree
0x180022547  mov     eax, 8007007Ah
0x18002254c  jmp     short loc_1800224FE
0x18002254e  mov     [rsp+58h+arg_0], rbp
0x180022553  lea     ebp, [rsi-4]
0x180022556  mov     dword ptr [rbx], 0Ah
0x18002255c  cmp     ebp, 4
0x18002255f  jnb     short loc_180022590
0x180022561  mov     rcx, [rsp+58h]; this
0x180022566  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002256d  mov     r9d, 8007007Ah; char *
0x180022573  mov     edx, 79h ; 'y'; void *
0x180022578  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002257d  mov     rcx, rbx; pv
0x180022580  call    cs:__imp_CoTaskMemFree
0x180022586  mov     eax, 8007007Ah
0x18002258b  jmp     loc_18002273B
0x180022590  mov     rax, [r14+8]
0x180022594  lea     rdi, [rbx+8]
0x180022598  sub     rax, [r14]
0x18002259b  sar     rax, 3
0x18002259f  mov     [rsp+58h+var_28], r12
0x1800225a4  add     ebp, 0FFFFFFFCh
0x1800225a7  mov     [rsp+58h+var_30], r13
0x1800225ac  mov     [rbx+4], eax
0x1800225af  mov     r13, [r14+8]
0x1800225b3  mov     qword ptr [rsp+58h+var_38], r15; int
0x1800225b8  mov     r15, [r14]
0x1800225bb  cmp     r15, r13
0x1800225be  jz      loc_18002271B
0x1800225c4  cmp     ebp, 10h
0x1800225c7  jb      loc_1800226C5
0x1800225cd  mov     rax, [r15]
0x1800225d0  add     ebp, 0FFFFFFF0h
0x1800225d3  movups  xmm0, xmmword ptr [rax]
0x1800225d6  movups  xmmword ptr [rdi], xmm0
0x1800225d9  cmp     ebp, 4
0x1800225dc  jb      loc_180022714
0x1800225e2  mov     rax, [r15]
0x1800225e5  add     ebp, 0FFFFFFFCh
0x1800225e8  mov     rcx, [rax+18h]
0x1800225ec  sub     rcx, [rax+10h]
0x1800225f0  sar     rcx, 3
0x1800225f4  mov     [rdi+10h], ecx
0x1800225f7  add     rdi, 14h
0x1800225fb  mov     rax, [r15]
0x1800225fe  mov     r14, [rax+10h]
0x180022602  mov     r12, [rax+18h]
0x180022606  cmp     r14, r12
0x180022609  jz      loc_1800226B5
0x18002260f  cmp     ebp, 4
0x180022612  jb      loc_18002270D
0x180022618  mov     rax, [r14]
0x18002261b  add     ebp, 0FFFFFFFCh
0x18002261e  mov     ecx, [rax+8]
0x180022621  mov     [rdi], ecx
0x180022623  cmp     ebp, 4
0x180022626  jb      loc_180022706
0x18002262c  mov     rax, [r14]
0x18002262f  add     ebp, 0FFFFFFFCh
0x180022632  mov     ecx, [rax+0Ch]
0x180022635  mov     [rdi+4], ecx
0x180022638  cmp     ebp, 4
0x18002263b  jb      loc_1800226FF
0x180022641  mov     rax, [r14]
0x180022644  add     ebp, 0FFFFFFFCh
0x180022647  mov     ecx, [rax+10h]
0x18002264a  mov     [rdi+8], ecx
0x18002264d  cmp     ebp, 4
0x180022650  jb      loc_1800226F8
0x180022656  mov     rax, [r14]
0x180022659  add     ebp, 0FFFFFFFCh
0x18002265c  mov     ecx, [rax+14h]
0x18002265f  mov     [rdi+0Ch], ecx
0x180022662  cmp     ebp, 4
0x180022665  jb      loc_1800226F1
0x18002266b  mov     rax, [r14]
0x18002266e  add     ebp, 0FFFFFFFCh
0x180022671  mov     ecx, [rax+18h]
0x180022674  mov     [rdi+10h], ecx
0x180022677  mov     rax, [r14]
0x18002267a  mov     rdx, [rax]; Src
0x18002267d  mov     eax, ebp
0x18002267f  movzx   r8d, word ptr [rdx+10h]
0x180022684  add     r8, 12h; Size
0x180022688  cmp     rax, r8
0x18002268b  jb      short loc_1800226BE
0x18002268d  lea     rcx, [rdi+14h]; void *
0x180022691  call    memcpy_0
0x180022696  mov     rax, [r14]
0x180022699  add     rdi, 26h ; '&'
0x18002269d  mov     rcx, [rax]
0x1800226a0  movzx   eax, word ptr [rcx+10h]
0x1800226a4  sub     ebp, eax
0x1800226a6  add     rdi, rax
0x1800226a9  sub     ebp, 12h
0x1800226ac  add     r14, 8
0x1800226b0  jmp     loc_180022606
0x1800226b5  add     r15, 8
0x1800226b9  jmp     loc_1800225BB
0x1800226be  mov     edx, 96h
0x1800226c3  jmp     short loc_1800226CA
0x1800226c5  mov     edx, 7Eh ; '~'; void *
0x1800226ca  mov     rcx, [rsp+58h]; this
0x1800226cf  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800226d6  mov     r9d, 8007007Ah; char *
0x1800226dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226e1  mov     rcx, rbx; pv
0x1800226e4  call    cs:__imp_CoTaskMemFree
0x1800226ea  mov     eax, 8007007Ah
0x1800226ef  jmp     short loc_18002272C
0x1800226f1  mov     edx, 94h
0x1800226f6  jmp     short loc_1800226CA
0x1800226f8  mov     edx, 91h
0x1800226fd  jmp     short loc_1800226CA
0x1800226ff  mov     edx, 8Eh
0x180022704  jmp     short loc_1800226CA
0x180022706  mov     edx, 8Bh
0x18002270b  jmp     short loc_1800226CA
0x18002270d  mov     edx, 88h
0x180022712  jmp     short loc_1800226CA
0x180022714  mov     edx, 82h
0x180022719  jmp     short loc_1800226CA
0x18002271b  mov     rax, [rsp+58h+arg_8]
0x180022720  mov     [rax], esi
0x180022722  mov     rax, [rsp+58h+arg_10]
0x180022727  mov     [rax], rbx
0x18002272a  xor     eax, eax
0x18002272c  mov     r13, [rsp+58h+var_30]
0x180022731  mov     r12, [rsp+58h+var_28]
0x180022736  mov     r15, qword ptr [rsp+58h+var_38]
0x18002273b  mov     rbp, [rsp+58h+arg_0]
0x180022740  jmp     loc_1800224FE
```
