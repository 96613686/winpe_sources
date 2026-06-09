# TryAutoUnlockVolumes(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> *,bool *)

- ea: `0x18000b570`
- end: `0x18000ba2d`
- name: `?TryAutoUnlockVolumes@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@PEA_N@Z`
- size: `1213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007d90`
- `0x18000a390`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000b570`
- `0x18002ae7c`
- `0x18002afa4`
- `0x180034070`
- `0x18004694c`
- `0x180047130`
- `0x180047b90`
- `0x180048198`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b678`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b678`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b88e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b88e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b7f1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b7f1`

## pseudocode

```c
__int64 __fastcall TryAutoUnlockVolumes(_QWORD **a1, _BYTE *a2, __int64 a3)
{
  _BYTE *v3; // r12
  _QWORD **v4; // rsi
  PVOID *v5; // rcx
  HRESULT v6; // r15d
  unsigned int v7; // r14d
  __int64 v8; // rdx
  __int64 v9; // r9
  int v11; // r14d
  _QWORD *v12; // rbx
  _QWORD *v13; // r9
  __int64 v14; // rcx
  _QWORD *v15; // r9
  __int64 v16; // rcx
  __int64 i; // rax
  bool v18; // zf
  HRESULT v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rbx
  _QWORD *v26; // r9
  _QWORD *v27; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-50h] BYREF
  _BYTE *v29; // [rsp+40h] [rbp-48h]
  _com_error *v30; // [rsp+48h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-38h] BYREF

  v3 = a2;
  v4 = a1;
  v29 = a2;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = -2147467259;
  ppv = 0;
  if ( !v4 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    {
      WPP_SF_(v5[2], 104, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147024809;
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 0x40) == 0 )
      goto LABEL_14;
    v8 = 105;
    goto LABEL_11;
  }
  v11 = 0;
  *v3 = 0;
  v12 = (_QWORD *)**v4;
  while ( v12 != *v4 )
  {
    if ( (v12[8] & 0x800) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v13 = v12 + 13;
        if ( v12[16] > 7u )
          v13 = (_QWORD *)*v13;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v13);
      }
      v27 = v12 + 13;
      v14 = (__int64)(v12 + 13);
      if ( v12[16] > 7u )
        v14 = v12[13];
      if ( (unsigned int)TryAutoUnlockVolumeWithSid(v14, 2) )
      {
        v11 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v15 = v27;
          if ( v12[16] > 7u )
            v15 = (_QWORD *)*v27;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v15);
        }
        UpdateVolumeEntryFlags((struct VolumeEntry *)(v12 + 8));
      }
    }
    v16 = v12[2];
    if ( *(_BYTE *)(v16 + 25) )
    {
      for ( i = v12[1]; !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v12 != *(_QWORD **)(i + 16) )
          break;
        v12 = (_QWORD *)i;
      }
      v12 = (_QWORD *)i;
    }
    else
    {
      v12 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min(
                        v16,
                        a2,
                        a3);
    }
  }
  v18 = v11 == 0;
  v7 = 0;
  if ( v18 )
    goto LABEL_13;
  v6 = CoInitializeEx(0, 0);
  LODWORD(v27) = v6;
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417850 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (unsigned int)v6);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = v6;
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 0x40) == 0 )
      goto LABEL_14;
    v8 = 109;
    v9 = (unsigned int)v6;
    goto LABEL_12;
  }
  v19 = CoCreateInstance(&rclsid, 0, 4u, &GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb, &ppv);
  v7 = v19;
  if ( v19 >= 0 )
  {
    if ( !ppv )
    {
      v7 = -2147467259;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_16;
      v8 = 112;
LABEL_11:
      v9 = v7;
LABEL_12:
      WPP_SF_d(v5[2], v8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v9);
LABEL_13:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    try
    {
      v22 = _bstr_t::_bstr_t((_bstr_t *)&v28, &dword_180086574);
      v7 = BdeUISrvLib::IBDEUILauncher::BdeUIContextTrigger(ppv, v23, v22);
    }
    catch ( _com_error *v30 )
    {
      v28 = *((_DWORD *)v30 + 2);
      v4 = a1;
      v7 = v28;
      v6 = (int)v27;
      v3 = v29;
    }
    if ( (v7 & 0x80000000) == 0 )
    {
      v24 = (_QWORD *)**v4;
      v27 = v24;
      while ( v24 != *v4 )
      {
        v25 = v24 + 8;
        if ( (v24[8] & 0x800) != 0 )
        {
          UpdateVolumeEntryFlags((struct VolumeEntry *)(v24 + 8));
          if ( (*(_DWORD *)v25 & 0x800) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v26 = v25 + 5;
              if ( v25[8] > 7u )
                v26 = (_QWORD *)*v26;
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v26);
            }
            *v3 = 1;
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++((__int64 *)&v27);
        v24 = v27;
      }
      goto LABEL_13;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v20 = 113;
      v21 = v7;
      goto LABEL_64;
    }
  }
  else
  {
    if ( v19 == -2147467238 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v7 = 0;
      *v3 = 1;
      goto LABEL_13;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v20 = 111;
      v21 = (unsigned int)v19;
LABEL_64:
      WPP_SF_d(v5[2], v20, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v21);
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_16:
  if ( v6 >= 0 )
  {
    CoUninitialize();
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_(v5[2], 115, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x18000b570  mov     [rsp+arg_10], rbx
0x18000b575  mov     [rsp+arg_18], rsi
0x18000b57a  mov     [rsp+arg_0], rcx
0x18000b57f  push    rdi
0x18000b580  push    r12
0x18000b582  push    r13
0x18000b584  push    r14
0x18000b586  push    r15
0x18000b588  sub     rsp, 60h
0x18000b58c  mov     rax, cs:__security_cookie
0x18000b593  xor     rax, rsp
0x18000b596  mov     [rsp+88h+var_30], rax
0x18000b59b  mov     r12, rdx
0x18000b59e  mov     rsi, rcx
0x18000b5a1  mov     [rsp+88h+var_48], rdx
0x18000b5a6  lea     rdi, WPP_GLOBAL_Control
0x18000b5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5b4  cmp     rcx, rdi
0x18000b5b7  jz      short loc_18000B5DB
0x18000b5b9  test    byte ptr [rcx+1Ch], 20h
0x18000b5bd  jz      short loc_18000B5DB
0x18000b5bf  mov     edx, 67h ; 'g'
0x18000b5c4  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b5cb  mov     rcx, [rcx+10h]
0x18000b5cf  call    WPP_SF_
0x18000b5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5db  mov     r15d, 80004005h
0x18000b5e1  mov     [rsp+88h+var_38], 0
0x18000b5ea  test    rsi, rsi
0x18000b5ed  jnz     loc_18000B6D6
0x18000b5f3  cmp     rcx, rdi
0x18000b5f6  jz      short loc_18000B61A
0x18000b5f8  test    byte ptr [rcx+1Ch], 2
0x18000b5fc  jz      short loc_18000B61A
0x18000b5fe  mov     edx, 68h ; 'h'
0x18000b603  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b60a  mov     rcx, [rcx+10h]
0x18000b60e  call    WPP_SF_
0x18000b613  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b61a  mov     r14d, 80070057h
0x18000b620  cmp     rcx, rdi
0x18000b623  jz      short loc_18000B64A
0x18000b625  test    byte ptr [rcx+1Ch], 40h
0x18000b629  jz      short loc_18000B64A
0x18000b62b  mov     edx, 69h ; 'i'
0x18000b630  mov     r9d, r14d
0x18000b633  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b63a  mov     rcx, [rcx+10h]
0x18000b63e  call    WPP_SF_d
0x18000b643  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b64a  mov     rdx, [rsp+88h+var_38]
0x18000b64f  test    rdx, rdx
0x18000b652  jz      short loc_18000B673
0x18000b654  mov     rax, [rdx]
0x18000b657  mov     rcx, rdx
0x18000b65a  mov     rax, [rax+10h]
0x18000b65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b663  mov     [rsp+88h+var_38], 0
0x18000b66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b673  test    r15d, r15d
0x18000b676  js      short loc_18000B68B
0x18000b678  call    cs:__imp_CoUninitialize
0x18000b67f  nop     dword ptr [rax+rax+00h]
0x18000b684  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68b  cmp     rcx, rdi
0x18000b68e  jz      short loc_18000B6AB
0x18000b690  test    byte ptr [rcx+1Ch], 20h
0x18000b694  jz      short loc_18000B6AB
0x18000b696  mov     edx, 73h ; 's'
0x18000b69b  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b6a2  mov     rcx, [rcx+10h]
0x18000b6a6  call    WPP_SF_
0x18000b6ab  mov     eax, r14d
0x18000b6ae  mov     rcx, [rsp+88h+var_30]
0x18000b6b3  xor     rcx, rsp; StackCookie
0x18000b6b6  call    __security_check_cookie
0x18000b6bb  lea     r11, [rsp+88h+var_28]
0x18000b6c0  mov     rbx, [r11+40h]
0x18000b6c4  mov     rsi, [r11+48h]
0x18000b6c8  mov     rsp, r11
0x18000b6cb  pop     r15
0x18000b6cd  pop     r14
0x18000b6cf  pop     r13
0x18000b6d1  pop     r12
0x18000b6d3  pop     rdi
0x18000b6d4  retn
0x18000b6d6  xor     r14d, r14d
0x18000b6d9  mov     [r12], r14b
0x18000b6dd  mov     rbx, [rsi]
0x18000b6e0  mov     rbx, [rbx]
0x18000b6e3  cmp     rbx, [rsi]
0x18000b6e6  jz      loc_18000B7DE
0x18000b6ec  test    dword ptr [rbx+40h], 800h
0x18000b6f3  jz      loc_18000B7A2
0x18000b6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b700  cmp     rcx, rdi
0x18000b703  jz      short loc_18000B731
0x18000b705  test    byte ptr [rcx+1Ch], 8
0x18000b709  jz      short loc_18000B731
0x18000b70b  lea     r9, [rbx+68h]
0x18000b70f  cmp     qword ptr [rbx+80h], 7
0x18000b717  jbe     short loc_18000B71C
0x18000b719  mov     r9, [r9]
0x18000b71c  mov     edx, 6Ah ; 'j'
0x18000b721  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b728  mov     rcx, [rcx+10h]
0x18000b72c  call    WPP_SF_S
0x18000b731  lea     rax, [rbx+68h]
0x18000b735  mov     [rsp+88h+var_58], rax
0x18000b73a  mov     rcx, rax
0x18000b73d  cmp     qword ptr [rbx+80h], 7
0x18000b745  jbe     short loc_18000B74A
0x18000b747  mov     rcx, [rax]
0x18000b74a  mov     edx, 2
0x18000b74f  call    ?TryAutoUnlockVolumeWithSid@@YAJPEBGW4FveSidUnlockContext@@@Z; TryAutoUnlockVolumeWithSid(ushort const *,FveSidUnlockContext)
0x18000b754  test    eax, eax
0x18000b756  jnz     short loc_18000B79C
0x18000b758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b75f  cmp     rcx, rdi
0x18000b762  jz      short loc_18000B791
0x18000b764  test    byte ptr [rcx+1Ch], 8
0x18000b768  jz      short loc_18000B791
0x18000b76a  mov     r9, [rsp+88h+var_58]
0x18000b76f  cmp     qword ptr [rbx+80h], 7
0x18000b777  jbe     short loc_18000B77C
0x18000b779  mov     r9, [r9]
0x18000b77c  mov     edx, 6Bh ; 'k'
0x18000b781  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b788  mov     rcx, [rcx+10h]
0x18000b78c  call    WPP_SF_S
0x18000b791  lea     rcx, [rbx+40h]; struct VolumeEntry *
0x18000b795  call    ?UpdateVolumeEntryFlags@@YAXPEAUVolumeEntry@@@Z; UpdateVolumeEntryFlags(VolumeEntry *)
0x18000b79a  jmp     short loc_18000B7A2
0x18000b79c  mov     r14d, 1
0x18000b7a2  mov     rcx, [rbx+10h]
0x18000b7a6  cmp     byte ptr [rcx+19h], 0
0x18000b7aa  jz      short loc_18000B7D1
0x18000b7ac  mov     rax, [rbx+8]
0x18000b7b0  cmp     byte ptr [rax+19h], 0
0x18000b7b4  jnz     short loc_18000B7C9
0x18000b7b6  cmp     rbx, [rax+10h]
0x18000b7ba  jnz     short loc_18000B7C9
0x18000b7bc  mov     rbx, rax
0x18000b7bf  mov     rax, [rax+8]
0x18000b7c3  cmp     byte ptr [rax+19h], 0
0x18000b7c7  jz      short loc_18000B7B6
0x18000b7c9  mov     rbx, rax
0x18000b7cc  jmp     loc_18000B6E3
0x18000b7d1  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<CSessionState>>,void *> *)
0x18000b7d6  mov     rbx, rax
0x18000b7d9  jmp     loc_18000B6E3
0x18000b7de  test    r14d, r14d
0x18000b7e1  mov     r14d, 0
0x18000b7e7  jz      loc_18000B643
0x18000b7ed  xor     edx, edx; dwCoInit
0x18000b7ef  xor     ecx, ecx; pvReserved
0x18000b7f1  call    cs:__imp_CoInitializeEx
0x18000b7f8  nop     dword ptr [rax+rax+00h]
0x18000b7fd  mov     r15d, eax
0x18000b800  mov     dword ptr [rsp+88h+var_58], eax
0x18000b804  mov     eax, 80000000h
0x18000b809  lea     ecx, [r15+rax]
0x18000b80d  test    eax, ecx
0x18000b80f  jnz     short loc_18000B86E
0x18000b811  cmp     r15d, 80010106h
0x18000b818  jz      short loc_18000B86E
0x18000b81a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b821  cmp     rcx, rdi
0x18000b824  jz      short loc_18000B84B
0x18000b826  test    byte ptr [rcx+1Ch], 2
0x18000b82a  jz      short loc_18000B84B
0x18000b82c  mov     edx, 6Ch ; 'l'
0x18000b831  mov     r9d, r15d
0x18000b834  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b83b  mov     rcx, [rcx+10h]
0x18000b83f  call    WPP_SF_d
0x18000b844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b84b  mov     r14d, r15d
0x18000b84e  cmp     rcx, rdi
0x18000b851  jz      loc_18000B64A
0x18000b857  test    byte ptr [rcx+1Ch], 40h
0x18000b85b  jz      loc_18000B64A
0x18000b861  mov     edx, 6Dh ; 'm'
0x18000b866  mov     r9d, r15d
0x18000b869  jmp     loc_18000B633
0x18000b86e  lea     rax, [rsp+88h+var_38]
0x18000b873  mov     [rsp+88h+ppv], rax; ppv
0x18000b878  lea     r9, _GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb; riid
0x18000b87f  xor     edx, edx; pUnkOuter
0x18000b881  mov     r8d, 4; dwClsContext
0x18000b887  lea     rcx, rclsid; rclsid
0x18000b88e  call    cs:__imp_CoCreateInstance
0x18000b895  nop     dword ptr [rax+rax+00h]
0x18000b89a  mov     r14d, eax
0x18000b89d  test    eax, eax
0x18000b89f  jns     short loc_18000B913
0x18000b8a1  cmp     eax, 8000401Ah
0x18000b8a6  jnz     short loc_18000B8DC
0x18000b8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8af  cmp     rcx, rdi
0x18000b8b2  jz      short loc_18000B8CF
0x18000b8b4  test    byte ptr [rcx+1Ch], 8
0x18000b8b8  jz      short loc_18000B8CF
0x18000b8ba  mov     edx, 6Eh ; 'n'
0x18000b8bf  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b8c6  mov     rcx, [rcx+10h]
0x18000b8ca  call    WPP_SF_
0x18000b8cf  xor     r14d, r14d
0x18000b8d2  mov     byte ptr [r12], 1
0x18000b8d7  jmp     loc_18000B643
0x18000b8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8e3  cmp     rcx, rdi
0x18000b8e6  jz      loc_18000B64A
0x18000b8ec  test    byte ptr [rcx+1Ch], 2
0x18000b8f0  jz      loc_18000B64A
0x18000b8f6  mov     edx, 6Fh ; 'o'
0x18000b8fb  mov     r9d, eax
0x18000b8fe  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000b905  mov     rcx, [rcx+10h]
0x18000b909  call    WPP_SF_d
0x18000b90e  jmp     loc_18000B643
0x18000b913  cmp     [rsp+88h+var_38], 0
0x18000b919  jnz     short loc_18000B945
0x18000b91b  mov     r14d, 80004005h
0x18000b921  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b928  cmp     rcx, rdi
0x18000b92b  jz      loc_18000B673
0x18000b931  test    byte ptr [rcx+1Ch], 40h
0x18000b935  jz      loc_18000B673
0x18000b93b  mov     edx, 70h ; 'p'
0x18000b940  jmp     loc_18000B630
0x18000b945  lea     rdx, dword_180086574; unsigned __int16 *
0x18000b94c  lea     rcx, [rsp+88h+var_50]; this
0x18000b951  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b956  mov     r8, rax
0x18000b959  mov     rcx, [rsp+88h+var_38]
0x18000b95e  call    ?BdeUIContextTrigger@IBDEUILauncher@BdeUISrvLib@@QEAAJJV_bstr_t@@F@Z; BdeUISrvLib::IBDEUILauncher::BdeUIContextTrigger(long,_bstr_t,short)
0x18000b963  mov     r14d, eax
0x18000b966  jmp     short loc_18000B986
0x18000b968  lea     rdi, WPP_GLOBAL_Control
0x18000b96f  mov     rsi, [rsp+88h+arg_0]
0x18000b977  mov     r14d, [rsp+88h+var_50]
0x18000b97c  mov     r15d, dword ptr [rsp+88h+var_58]
0x18000b981  mov     r12, [rsp+88h+var_48]
0x18000b986  test    r14d, r14d
0x18000b989  jns     short loc_18000B9B2
0x18000b98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b992  cmp     rcx, rdi
0x18000b995  jz      loc_18000B64A
0x18000b99b  test    byte ptr [rcx+1Ch], 2
0x18000b99f  jz      loc_18000B64A
0x18000b9a5  mov     edx, 71h ; 'q'
0x18000b9aa  mov     r9d, r14d
0x18000b9ad  jmp     loc_18000B8FE
0x18000b9b2  mov     rax, [rsi]
0x18000b9b5  mov     rax, [rax]
0x18000b9b8  mov     [rsp+88h+var_58], rax
0x18000b9bd  cmp     rax, [rsi]
0x18000b9c0  jz      loc_18000B643
0x18000b9c6  lea     rbx, [rax+40h]
0x18000b9ca  test    dword ptr [rbx], 800h
0x18000b9d0  jz      short loc_18000BA1C
0x18000b9d2  mov     rcx, rbx; struct VolumeEntry *
0x18000b9d5  call    ?UpdateVolumeEntryFlags@@YAXPEAUVolumeEntry@@@Z; UpdateVolumeEntryFlags(VolumeEntry *)
0x18000b9da  test    dword ptr [rbx], 800h
0x18000b9e0  jz      short loc_18000BA1C
0x18000b9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9e9  cmp     rcx, rdi
0x18000b9ec  jz      short loc_18000BA17
0x18000b9ee  test    byte ptr [rcx+1Ch], 8
0x18000b9f2  jz      short loc_18000BA17
0x18000b9f4  lea     r9, [rbx+28h]
0x18000b9f8  cmp     qword ptr [rbx+40h], 7
0x18000b9fd  jbe     short loc_18000BA02
0x18000b9ff  mov     r9, [r9]
0x18000ba02  mov     edx, 72h ; 'r'
0x18000ba07  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18000ba0e  mov     rcx, [rcx+10h]
0x18000ba12  call    WPP_SF_S
0x18000ba17  mov     byte ptr [r12], 1
0x18000ba1c  lea     rcx, [rsp+88h+var_58]
0x18000ba21  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++(void)
0x18000ba26  mov     rax, [rsp+88h+var_58]
0x18000ba2b  jmp     short loc_18000B9BD
```
