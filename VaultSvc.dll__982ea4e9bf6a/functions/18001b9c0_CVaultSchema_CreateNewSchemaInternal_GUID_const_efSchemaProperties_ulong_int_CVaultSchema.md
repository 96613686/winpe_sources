# CVaultSchema::CreateNewSchemaInternal(_GUID const *,efSchemaProperties,ulong,int,CVaultSchema * *)

- ea: `0x18001b9c0`
- end: `0x18001bbfb`
- name: `?CreateNewSchemaInternal@CVaultSchema@@SAKPEBU_GUID@@W4efSchemaProperties@@KHPEAPEAV1@@Z`
- size: `571`
- prototype: `__int64 __fastcall(_OWORD *, int, unsigned int, int, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b798`
- `0x18001b970`

## callees

- `0x1800121d0`
- `0x180012210`
- `0x18001a640`
- `0x18001b9c0`
- `0x180038e44`
- `0x18003b7b0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba0f`

## pseudocode

```c
__int64 __fastcall CVaultSchema::CreateNewSchemaInternal(_OWORD *a1, int a2, unsigned int a3, int a4, _QWORD *a5)
{
  unsigned __int64 v9; // rax
  char *v10; // rax
  _DWORD *v11; // rbx
  char *v12; // rsi
  char *v13; // rax
  unsigned int v14; // ecx
  unsigned int VaultSecurable; // edi
  _QWORD *v17; // rcx
  __int64 v18; // rdx

  if ( a3 < 2 )
    return 87;
  v9 = 32LL * a3;
  if ( v9 > 0xFFFFFFFF )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 534;
    v18 = 14;
    goto LABEL_25;
  }
  if ( (int)v9 + 152 < (unsigned int)v9 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 534;
    v18 = 15;
LABEL_25:
    WPP_SF_(v17[2], v18, WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids);
    return 534;
  }
  v10 = (char *)LocalAlloc(0x40u, (unsigned int)(v9 + 152));
  v11 = v10;
  if ( !v10 )
    return 14;
  v12 = v10 + 152;
  *(_QWORD *)v10 = &CVaultSchema::`vftable';
  *((_DWORD *)v10 + 2) = 1;
  *(_OWORD *)(v10 + 12) = *a1;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *((_DWORD *)v10 + 16) = 0;
  *((_QWORD *)v10 + 10) = 0;
  *((_QWORD *)v10 + 11) = 0;
  std::_Tree<std::_Tmap_traits<enum VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<enum VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Alloc_sentinel_and_proxy(v10 + 80);
  v11[24] = a2;
  v11[26] = 0;
  *((_QWORD *)v11 + 14) = 0;
  *((_QWORD *)v11 + 15) = qword_18005F710;
  v11[32] = 0;
  *((_QWORD *)v11 + 17) = 1;
  *((_QWORD *)v11 + 9) = 0;
  *(_QWORD *)v12 = &CVaultSchemaElement::`vftable';
  *((_DWORD *)v12 + 2) = 2;
  v12[24] = 0;
  *((_QWORD *)v11 + 6) = v12;
  *((_QWORD *)v12 + 4) = &CVaultSchemaElement::`vftable';
  *((_DWORD *)v12 + 10) = 3;
  v12[56] = 0;
  *((_QWORD *)v11 + 7) = v12 + 32;
  v13 = v12 + 64;
  v14 = a3 - 2;
  if ( a3 == 2 )
    goto LABEL_6;
  if ( (v11[24] & 1) == 0 )
  {
    *(_QWORD *)v13 = &CVaultSchemaElement::`vftable';
    *((_DWORD *)v12 + 18) = 1;
    v12[88] = 0;
    *((_QWORD *)v11 + 5) = v13;
    v13 = v12 + 96;
    v14 = a3 - 3;
  }
  if ( !v14 )
  {
LABEL_6:
    *((_WORD *)v11 + 34) = 0;
  }
  else
  {
    *((_QWORD *)v11 + 9) = v13;
    *((_WORD *)v11 + 34) = v14;
    do
    {
      *(_QWORD *)v13 = &CVaultSchemaElement::`vftable';
      *((_DWORD *)v13 + 2) = 0;
      v13[24] = 0;
      v13 += 32;
      --v14;
    }
    while ( v14 );
  }
  if ( !a4
    && ((VaultSecurable = VaultCreateVaultSecurable(2, v11 + 3, 0, v11 + 36)) != 0
     || (VaultSecurable = CVaultGenericPropertyCollection<enum ESchemaPropertyId,0>::InitializeCollection(v11 + 26)) != 0) )
  {
    (*(void (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)v11 + 16LL))(v11, 0);
    VaultFreeInternal(v11);
    return VaultSecurable;
  }
  else
  {
    *a5 = v11;
    return 0;
  }
}

```

## disassembly

```asm
0x18001b9c0  push    rbx
0x18001b9c2  push    rsi
0x18001b9c3  push    rdi
0x18001b9c4  push    r12
0x18001b9c6  push    r13
0x18001b9c8  push    r14
0x18001b9ca  push    r15
0x18001b9cc  sub     rsp, 30h
0x18001b9d0  mov     r12d, r9d
0x18001b9d3  mov     edi, r8d
0x18001b9d6  mov     r13d, edx
0x18001b9d9  mov     r14, rcx
0x18001b9dc  cmp     r8d, 2
0x18001b9e0  jb      loc_18001BB49
0x18001b9e6  mov     eax, edi
0x18001b9e8  shl     rax, 5
0x18001b9ec  mov     ecx, 0FFFFFFFFh
0x18001b9f1  cmp     rax, rcx
0x18001b9f4  ja      loc_18001BBC3
0x18001b9fa  lea     ecx, [rax+98h]
0x18001ba00  cmp     ecx, eax
0x18001ba02  jb      loc_18001BB50
0x18001ba08  mov     edx, ecx; uBytes
0x18001ba0a  mov     ecx, 40h ; '@'; uFlags
0x18001ba0f  call    cs:__imp_LocalAlloc
0x18001ba15  mov     rbx, rax
0x18001ba18  mov     [rsp+68h+var_48], rax
0x18001ba1d  xor     edx, edx
0x18001ba1f  test    rax, rax
0x18001ba22  jz      loc_18001BAFA
0x18001ba28  lea     rsi, [rax+98h]
0x18001ba2f  lea     rax, ??_7CVaultSchema@@6B@; const CVaultSchema::`vftable'
0x18001ba36  mov     [rbx], rax
0x18001ba39  mov     dword ptr [rbx+8], 1
0x18001ba40  movups  xmm0, xmmword ptr [r14]
0x18001ba44  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x18001ba49  mov     [rbx+20h], rdx
0x18001ba4d  mov     [rbx+28h], rdx
0x18001ba51  mov     [rbx+40h], edx
0x18001ba54  lea     rcx, [rbx+50h]
0x18001ba58  mov     [rcx], rdx
0x18001ba5b  mov     [rcx+8], rdx
0x18001ba5f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@U?$less@W4VAULT_SCHEMA_ELEMENT_ID@@@std@@V?$allocator@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001ba64  mov     [rbx+60h], r13d
0x18001ba68  xor     r13d, r13d
0x18001ba6b  mov     [rbx+68h], r13d
0x18001ba6f  mov     [rbx+70h], r13
0x18001ba73  mov     rax, cs:qword_18005F710
0x18001ba7a  mov     [rbx+78h], rax
0x18001ba7e  mov     [rbx+80h], r13d
0x18001ba85  lea     edx, [r13+1]
0x18001ba89  mov     [rbx+88h], rdx
0x18001ba90  mov     [rbx+48h], r13
0x18001ba94  lea     r8, ??_7CVaultSchemaElement@@6B@; const CVaultSchemaElement::`vftable'
0x18001ba9b  mov     [rsi], r8
0x18001ba9e  lea     r10d, [r13+2]
0x18001baa2  mov     [rsi+8], r10d
0x18001baa6  mov     [rsi+18h], r13b
0x18001baaa  mov     [rbx+30h], rsi
0x18001baae  lea     rax, [rsi+20h]
0x18001bab2  mov     [rax], r8
0x18001bab5  mov     dword ptr [rax+8], 3
0x18001babc  mov     [rax+18h], r13b
0x18001bac0  mov     [rbx+38h], rax
0x18001bac4  add     rax, 20h ; ' '
0x18001bac8  lea     ecx, [rdi-2]
0x18001bacb  test    ecx, ecx
0x18001bacd  jnz     loc_18001BB78
0x18001bad3  mov     [rbx+44h], r13w
0x18001bad8  test    r12d, r12d
0x18001badb  jz      short loc_18001BB01
0x18001badd  mov     rax, [rsp+68h+arg_20]
0x18001bae5  mov     [rax], rbx
0x18001bae8  xor     eax, eax
0x18001baea  add     rsp, 30h
0x18001baee  pop     r15
0x18001baf0  pop     r14
0x18001baf2  pop     r13
0x18001baf4  pop     r12
0x18001baf6  pop     rdi
0x18001baf7  pop     rsi
0x18001baf8  pop     rbx
0x18001baf9  retn
0x18001bafa  mov     eax, 0Eh
0x18001baff  jmp     short loc_18001BAEA
0x18001bb01  lea     r9, [rbx+90h]
0x18001bb08  xor     r8d, r8d
0x18001bb0b  lea     rdx, [rbx+0Ch]
0x18001bb0f  mov     ecx, r10d
0x18001bb12  call    ?VaultCreateVaultSecurable@@YAKW4EVaultSecurableType@@AEBU_GUID@@PEAVCVaultSid@@PEAPEAVIVaultSecurable@@@Z; VaultCreateVaultSecurable(EVaultSecurableType,_GUID const &,CVaultSid *,IVaultSecurable * *)
0x18001bb17  mov     edi, eax
0x18001bb19  test    eax, eax
0x18001bb1b  jnz     short loc_18001BB2C
0x18001bb1d  lea     rcx, [rbx+68h]
0x18001bb21  call    ?InitializeCollection@?$CVaultGenericPropertyCollection@W4ESchemaPropertyId@@$0A@@@QEAAKXZ; CVaultGenericPropertyCollection<ESchemaPropertyId,0>::InitializeCollection(void)
0x18001bb26  mov     edi, eax
0x18001bb28  test    eax, eax
0x18001bb2a  jz      short loc_18001BADD
0x18001bb2c  mov     rcx, [rbx]
0x18001bb2f  mov     rax, [rcx+10h]
0x18001bb33  xor     edx, edx
0x18001bb35  mov     rcx, rbx
0x18001bb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb3d  mov     rcx, rbx; hMem
0x18001bb40  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18001bb45  mov     eax, edi
0x18001bb47  jmp     short loc_18001BAEA
0x18001bb49  mov     eax, 57h ; 'W'
0x18001bb4e  jmp     short loc_18001BAEA
0x18001bb50  lea     rax, WPP_GLOBAL_Control
0x18001bb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb5e  cmp     rcx, rax
0x18001bb61  jz      loc_18001BBF1
0x18001bb67  test    byte ptr [rcx+1Ch], 4
0x18001bb6b  jz      loc_18001BBF1
0x18001bb71  mov     edx, 0Fh
0x18001bb76  jmp     short loc_18001BBE1
0x18001bb78  test    [rbx+60h], dl
0x18001bb7b  jnz     short loc_18001BB91
0x18001bb7d  mov     [rax], r8
0x18001bb80  mov     [rax+8], edx
0x18001bb83  mov     [rax+18h], r13b
0x18001bb87  mov     [rbx+28h], rax
0x18001bb8b  add     rax, 20h ; ' '
0x18001bb8f  dec     ecx
0x18001bb91  test    ecx, ecx
0x18001bb93  jz      loc_18001BAD3
0x18001bb99  mov     [rbx+48h], rax
0x18001bb9d  mov     [rbx+44h], cx
0x18001bba1  mov     edx, 0FFFFFFFFh
0x18001bba6  mov     [rax], r8
0x18001bba9  mov     [rax+8], r13d
0x18001bbad  mov     [rax+18h], r13b
0x18001bbb1  lea     rax, [rax+20h]
0x18001bbb5  add     ecx, edx
0x18001bbb7  jnz     short loc_18001BBA6
0x18001bbb9  jmp     loc_18001BAD8
0x18001bbbe  jmp     loc_18001BAFA
0x18001bbc3  lea     rax, WPP_GLOBAL_Control
0x18001bbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbd1  cmp     rcx, rax
0x18001bbd4  jz      short loc_18001BBF1
0x18001bbd6  test    byte ptr [rcx+1Ch], 4
0x18001bbda  jz      short loc_18001BBF1
0x18001bbdc  mov     edx, 0Eh
0x18001bbe1  lea     r8, WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids
0x18001bbe8  mov     rcx, [rcx+10h]
0x18001bbec  call    WPP_SF_
0x18001bbf1  mov     eax, 216h
0x18001bbf6  jmp     loc_18001BAEA
```
