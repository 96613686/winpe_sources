# NetSetupPropertyBag::GetUncached(_NETSETUPPROPKEY const &)

- ea: `0x180006070`
- end: `0x1800069c7`
- name: `?GetUncached@NetSetupPropertyBag@@AEBA?AV?$shared_ptr@VProperty@NetSetup2@@@std@@AEBU_NETSETUPPROPKEY@@@Z`
- size: `2391`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180008280`

## callees

- `0x180004d90`
- `0x180004e3c`
- `0x180005c94`
- `0x180005dd0`
- `0x180006070`
- `0x1800069d0`
- `0x180006eb0`
- `0x180007010`
- `0x180007250`
- `0x180008280`
- `0x18000f670`
- `0x180012830`
- `0x180020f40`
- `0x1800217b8`
- `0x180029900`
- `0x18002e34c`
- `0x180034cc8`
- `0x18005097c`
- `0x180052698`
- `0x18005b034`
- `0x1800646b8`
- `0x180064704`
- `0x180065035`
- `0x180081096`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006311`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006311`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800066a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800066a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
NetSetup2::Property **__fastcall NetSetupPropertyBag::GetUncached(
        __int64 a1,
        NetSetup2::Property **a2,
        unsigned int *a3)
{
  unsigned int v5; // eax
  __int64 *v6; // r15
  unsigned __int64 v7; // rsi
  __int64 *v8; // rdi
  __int64 v9; // rax
  bool v10; // cf
  bool v11; // r13
  HKEY v12; // rdi
  __int64 DefaultValue; // rax
  _DWORD *v14; // rbx
  NetSetup2::Property *v15; // rsi
  volatile signed __int32 *v16; // r15
  NetSetup2::Property **v17; // r14
  unsigned __int16 v19; // ax
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // di
  _DWORD *v22; // rax
  void **v23; // rdi
  void *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  std::_Ref_count_base *v28; // rcx
  __int64 v29; // rax
  NetSetup2::Property *v30; // rcx
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rax
  unsigned int v33; // ebx
  __int64 v34; // rax
  DWORD Uint32; // r15d
  __int64 *v36; // r13
  __int64 v37; // rdx
  volatile signed __int32 *v38; // r14
  __int64 v39; // rdx
  __int64 v40; // rax
  DWORD v41; // edi
  _QWORD *v42; // rax
  _QWORD *v43; // rbx
  NetSetup2::Property *v44; // [rsp+78h] [rbp-88h]
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  RTL_SRWLOCK *v46; // [rsp+90h] [rbp-70h]
  NetSetup2::Property *v47; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v48; // [rsp+A0h] [rbp-60h]
  NetSetup2::Property **v49; // [rsp+A8h] [rbp-58h]
  _QWORD v50[5]; // [rsp+B0h] [rbp-50h] BYREF
  char v51; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+E8h] [rbp-18h] BYREF
  DWORD cValues; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v54[4]; // [rsp+1BCh] [rbp+BCh] BYREF
  HKEY hKey; // [rsp+1C0h] [rbp+C0h] BYREF
  std::_Ref_count_base *v56; // [rsp+1C8h] [rbp+C8h]
  NetSetup2::Property *v57; // [rsp+1D0h] [rbp+D0h] BYREF
  volatile signed __int32 *v58; // [rsp+1D8h] [rbp+D8h]
  WCHAR v59[56]; // [rsp+1E0h] [rbp+E0h] BYREF

  v50[3] = -2;
  v49 = a2;
  v46 = (RTL_SRWLOCK *)a1;
  v50[4] = a2;
  v5 = a3[4];
  switch ( v5 )
  {
    case 2u:
      v25 = *(_QWORD *)a3 - NETSETUPPKEY_Object_Id;
      if ( *(_QWORD *)a3 == NETSETUPPKEY_Object_Id )
        v25 = *((_QWORD *)a3 + 1) - *(&NETSETUPPKEY_Object_Id + 1);
      if ( !v25 )
      {
        std::make_shared<NetSetup2::Property,_NETSETUPPROPKEY const &,_GUID const &>(a2, a3, a1 + 20);
        return a2;
      }
      goto LABEL_5;
    case 4u:
      v26 = *(_QWORD *)a3 - NETSETUPPKEY_Object_ApiObjectType;
      if ( *(_QWORD *)a3 == (_QWORD)NETSETUPPKEY_Object_ApiObjectType )
        v26 = *((_QWORD *)a3 + 1) - *((_QWORD *)&NETSETUPPKEY_Object_ApiObjectType + 1);
      if ( !v26 )
      {
        cValues = *(_DWORD *)(a1 + 16);
        std::make_shared<NetSetup2::Property,_NETSETUPPROPKEY const &,unsigned long>(a2, a3, &cValues);
        return a2;
      }
      goto LABEL_5;
    case 8u:
      v27 = *(_QWORD *)a3 - NETSETUPPKEY_Interface_NetLuidIndex;
      if ( *(_QWORD *)a3 == (_QWORD)NETSETUPPKEY_Interface_NetLuidIndex )
        v27 = *((_QWORD *)a3 + 1) - *((_QWORD *)&NETSETUPPKEY_Interface_NetLuidIndex + 1);
      if ( v27 )
        goto LABEL_5;
      NetSetupPropertyBag::Get((RTL_SRWLOCK *)a1, (__int64 *)&hKey, &NETSETUPPKEY_Interface_NetLuid);
      if ( hKey && *((_DWORD *)hKey + 5) )
      {
        v41 = (NetSetup2::Property::GetUint64((NetSetup2::Property *)hKey) >> 24) & 0xFFFFFF;
        v42 = operator new(0x40u);
        v43 = v42;
        v49 = (NetSetup2::Property **)v42;
        if ( v42 )
        {
          *((_DWORD *)v42 + 2) = 1;
          *((_DWORD *)v42 + 3) = 1;
          *v42 = &std::_Ref_count_obj<NetSetup2::Property>::`vftable';
          *((_OWORD *)v42 + 1) = NETSETUPPKEY_Interface_NetLuidIndex;
          *((_DWORD *)v42 + 8) = 8;
          v42[5] = 0;
          v42[7] = 0;
          cValues = v41;
          *((_DWORD *)v42 + 9) = 7;
          v42[6] = 0;
          std::vector<unsigned char>::_Insert<unsigned char *>(v42 + 5, 0, &cValues, v54);
        }
        else
        {
          v43 = 0;
        }
        a2[1] = (NetSetup2::Property *)v43;
        *a2 = (NetSetup2::Property *)(v43 + 2);
        if ( v56 )
          std::_Ref_count_base::_Decref(v56);
        return a2;
      }
      v28 = v56;
      break;
    case 0x14u:
      v29 = *(_QWORD *)a3 - NETSETUPPKEY_Driver_HideInUi;
      if ( *(_QWORD *)a3 == (_QWORD)NETSETUPPKEY_Driver_HideInUi )
        v29 = *((_QWORD *)a3 + 1) - *((_QWORD *)&NETSETUPPKEY_Driver_HideInUi + 1);
      if ( v29 )
        goto LABEL_5;
      NetSetupPropertyBag::ReadHiddenFlagFromNetCfg(a1, &v47);
      v30 = v47;
      if ( v47 )
      {
        *a2 = 0;
        a2[1] = 0;
        if ( a2 == &v47 )
        {
          v31 = (volatile signed __int32 *)v48;
        }
        else
        {
          a2[1] = v48;
          v31 = 0;
          v48 = 0;
          *a2 = v30;
          v47 = 0;
        }
        if ( v31 )
        {
          if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        return a2;
      }
      v28 = v48;
      break;
    default:
      goto LABEL_5;
  }
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
LABEL_5:
  v6 = qword_18008C0A0;
  v7 = 281;
  do
  {
    v8 = &v6[7 * (v7 >> 1)];
    v9 = *v8 - *(_QWORD *)a3;
    if ( *v8 == *(_QWORD *)a3 )
      v9 = v8[1] - *((_QWORD *)a3 + 1);
    if ( v9 )
    {
      v10 = *(_DWORD *)v8 < *a3;
      if ( *(_DWORD *)v8 == *a3
        && (v19 = *((_WORD *)a3 + 2), v10 = *((_WORD *)v8 + 2) < v19, *((_WORD *)v8 + 2) == v19)
        && (v20 = *((_WORD *)a3 + 3), v10 = *((_WORD *)v8 + 3) < v20, *((_WORD *)v8 + 3) == v20) )
      {
        if ( memcmp_0(v8 + 1, a3 + 2, 8u) >= 0 )
        {
LABEL_11:
          v7 >>= 1;
          continue;
        }
      }
      else if ( !v10 )
      {
        goto LABEL_11;
      }
    }
    else if ( *((_DWORD *)v8 + 4) >= a3[4] )
    {
      goto LABEL_11;
    }
    v6 = v8 + 7;
    v7 += -1LL - (v7 >> 1);
  }
  while ( (__int64)v7 > 0 );
  if ( *((_DWORD *)v6 + 4) != a3[4] )
    goto LABEL_14;
  v32 = *v6 - *(_QWORD *)a3;
  if ( *v6 == *(_QWORD *)a3 )
    v32 = v6[1] - *((_QWORD *)a3 + 1);
  if ( v32 )
  {
LABEL_14:
    v6 = 0;
  }
  else if ( *((_DWORD *)v6 + 8) )
  {
    GetDefaultValue(a2, v6);
    return a2;
  }
  v11 = 0;
  swprintf_s<44>(
    v59,
    L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\\%04x",
    *a3,
    *((unsigned __int16 *)a3 + 2),
    *((unsigned __int16 *)a3 + 3),
    *((unsigned __int8 *)a3 + 8),
    *((unsigned __int8 *)a3 + 9),
    *((unsigned __int8 *)a3 + 10),
    *((unsigned __int8 *)a3 + 11),
    *((unsigned __int8 *)a3 + 12),
    *((unsigned __int8 *)a3 + 13),
    *((unsigned __int8 *)a3 + 14),
    *((unsigned __int8 *)a3 + 15),
    a3[4],
    0);
  RegistryKey::TryOpenSubKey((HKEY *)&v46[1], (HKEY)&hKey, v59, 1u, 0);
  v12 = hKey;
  if ( hKey )
  {
    cValues = 0;
    v33 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v33 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids, v33);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v33);
      throw (Win32Exception *)pExceptionObject;
    }
    v11 = cValues == 0;
  }
  v45 = 0;
  if ( !v12 || v11 )
  {
    DefaultValue = GetDefaultValue(&v57, v6);
    if ( &v51 == (char *)DefaultValue )
    {
      v15 = 0;
      v14 = 0;
    }
    else
    {
      v14 = *(_DWORD **)(DefaultValue + 8);
      *(_QWORD *)(DefaultValue + 8) = 0;
      v15 = *(NetSetup2::Property **)DefaultValue;
      *(_QWORD *)DefaultValue = 0;
    }
    v44 = v15;
    *((_QWORD *)&v45 + 1) = v14;
    *(_QWORD *)&v45 = v15;
    v16 = v58;
    if ( v58 )
    {
      if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  else
  {
    cValues = 0;
    RegistryKey::GetValueBlob(&hKey, v50, 0, &cValues);
    v21 = cValues;
    if ( (cValues & 0xFFFF0000) != 0xFFFF0000 )
    {
      HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
      throw (HResultException *)pExceptionObject;
    }
    v22 = operator new(0x40u);
    v14 = v22;
    if ( v22 )
    {
      v22[2] = 1;
      v22[3] = 1;
      *(_QWORD *)v22 = &std::_Ref_count_obj<NetSetup2::Property>::`vftable';
      *((_OWORD *)v22 + 1) = *(_OWORD *)a3;
      *((_QWORD *)v22 + 4) = a3[4];
      *((_QWORD *)v22 + 5) = 0;
      *((_QWORD *)v22 + 6) = 0;
      *((_QWORD *)v22 + 7) = 0;
    }
    else
    {
      v14 = 0;
    }
    v15 = (NetSetup2::Property *)(v14 + 4);
    v44 = (NetSetup2::Property *)(v14 + 4);
    *((_QWORD *)&v45 + 1) = v14;
    *(_QWORD *)&v45 = v14 + 4;
    v14[9] = v21;
    v23 = (void **)(v14 + 10);
    if ( v14 + 10 == (_DWORD *)v50 )
    {
      v24 = (void *)v50[0];
    }
    else
    {
      if ( *v23 )
      {
        operator delete(*v23);
        *((_QWORD *)v14 + 6) = 0;
      }
      *v23 = (void *)v50[0];
      *((_QWORD *)v14 + 6) = v50[1];
      *((_QWORD *)v14 + 7) = v50[2];
      v24 = 0;
    }
    if ( v24 )
      operator delete(v24);
    v12 = hKey;
  }
  if ( a3[4] == 6 )
  {
    v34 = *(_QWORD *)a3 - NETSETUPPKEY_INF_Characteristics;
    if ( *(_QWORD *)a3 == NETSETUPPKEY_INF_Characteristics )
      v34 = *((_QWORD *)a3 + 1) - 0x17957FBBAD0689ALL;
    if ( !v34 )
    {
      if ( v15 && *((_DWORD *)v15 + 5) )
        Uint32 = NetSetup2::Property::GetUint32(v15);
      else
        Uint32 = 0;
      v36 = qword_1800999F0;
      do
      {
        NetSetupPropertyBag::Get(v46, (__int64 *)&v57, (__int128 *)v36);
        if ( *((_DWORD *)v57 + 5) && NetSetup2::Property::GetBoolean(v57) )
          Uint32 |= *((_DWORD *)v36 + 5);
        else
          Uint32 &= ~*((_DWORD *)v36 + 5);
        cValues = Uint32;
        v38 = v58;
        if ( v58 )
        {
          if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        v36 += 3;
      }
      while ( v36 != (__int64 *)&NETSETUPPKEY_Bind_DefaultDisabled );
      if ( LODWORD(v46[2].Ptr) == 3 )
      {
        Uint32 |= 0x40000u;
        cValues = Uint32;
      }
      v15 = v44;
      v12 = hKey;
      if ( v44 )
      {
        cValues = Uint32;
        *((_DWORD *)v44 + 5) = 7;
        v39 = *((_QWORD *)v44 + 3);
        *((_QWORD *)v44 + 4) = v39;
        std::vector<unsigned char>::_Insert<unsigned char *>((char *)v44 + 24, v39, &cValues, v54);
      }
      else if ( Uint32 )
      {
        v40 = std::make_shared<NetSetup2::Property,_NETSETUPPROPKEY const &,unsigned long &>(&v57, v37, &cValues);
        std::shared_ptr<NetSetup2::Property>::operator=(&v45, v40);
        std::_Ptr_base<NetSetup2::Property>::_Decref(&v57);
        v14 = (_DWORD *)*((_QWORD *)&v45 + 1);
        v15 = (NetSetup2::Property *)v45;
      }
    }
  }
  v17 = v49;
  *v49 = 0;
  v17[1] = 0;
  if ( v17 != (NetSetup2::Property **)&v45 )
  {
    v17[1] = (NetSetup2::Property *)v14;
    v14 = 0;
    *v17 = v15;
  }
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(_DWORD *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  if ( v12 )
    RegCloseKey(v12);
  return v17;
}

```

## disassembly

```asm
0x180006070  push    rbp
0x180006072  push    rsi
0x180006073  push    rdi
0x180006074  push    r12
0x180006076  push    r13
0x180006078  push    r14
0x18000607a  push    r15
0x18000607c  lea     rbp, [rsp-160h]
0x180006084  sub     rsp, 260h
0x18000608b  mov     [rbp+190h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x180006093  mov     [rsp+290h+arg_18], rbx
0x18000609b  mov     rax, cs:__security_cookie
0x1800060a2  xor     rax, rsp
0x1800060a5  mov     [rbp+190h+var_40], rax
0x1800060ac  mov     r14, r8
0x1800060af  mov     r13, rdx
0x1800060b2  mov     [rbp+190h+var_1E8], rdx
0x1800060b6  mov     [rbp+190h+var_200], rcx
0x1800060ba  mov     [rbp+190h+var_1C0], rdx
0x1800060be  xor     esi, esi
0x1800060c0  mov     [rsp+290h+var_220], esi
0x1800060c4  mov     eax, [r8+10h]
0x1800060c8  cmp     eax, 2
0x1800060cb  jz      loc_1800064C3
0x1800060d1  cmp     eax, 4
0x1800060d4  jz      loc_1800064FB
0x1800060da  cmp     eax, 8
0x1800060dd  jz      loc_18000653F
0x1800060e3  cmp     eax, 14h
0x1800060e6  jz      loc_18000658F
0x1800060ec  lea     r15, qword_18008C0A0
0x1800060f3  mov     esi, 119h
0x1800060f8  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800060ff  nop
0x180006100  mov     rbx, rsi
0x180006103  shr     rbx, 1
0x180006106  imul    rdi, rbx, 38h ; '8'
0x18000610a  add     rdi, r15
0x18000610d  mov     rax, [rdi]
0x180006110  sub     rax, [r14]
0x180006113  jnz     short loc_18000611D
0x180006115  mov     rax, [rdi+8]
0x180006119  sub     rax, [r14+8]
0x18000611d  test    rax, rax
0x180006120  jz      loc_18000631C
0x180006126  mov     eax, [r14]
0x180006129  cmp     [rdi], eax
0x18000612b  jz      loc_18000633B
0x180006131  setb    al
0x180006134  test    al, al
0x180006136  jnz     loc_180006329
0x18000613c  mov     rsi, rbx
0x18000613f  test    rsi, rsi
0x180006142  jg      short loc_180006100
0x180006144  mov     r12d, [r14+10h]
0x180006148  cmp     [r15+10h], r12d
0x18000614c  jz      loc_180006644
0x180006152  xor     r15d, r15d
0x180006155  xor     r13b, r13b
0x180006158  movzx   eax, byte ptr [r14+0Fh]
0x18000615d  movzx   ecx, byte ptr [r14+0Eh]
0x180006162  movzx   edx, byte ptr [r14+0Dh]
0x180006167  movzx   r8d, byte ptr [r14+0Ch]
0x18000616c  movzx   r10d, byte ptr [r14+0Bh]
0x180006171  movzx   r11d, byte ptr [r14+0Ah]
0x180006176  movzx   ebx, byte ptr [r14+9]
0x18000617b  movzx   edi, byte ptr [r14+8]
0x180006180  movzx   esi, word ptr [r14+6]
0x180006185  movzx   r9d, word ptr [r14+4]
0x18000618a  mov     [rsp+290h+var_228], r12d
0x18000618f  mov     [rsp+290h+var_230], eax
0x180006193  mov     dword ptr [rsp+290h+lpftLastWriteTime], ecx
0x180006197  mov     dword ptr [rsp+290h+lpcbSecurityDescriptor], edx
0x18000619b  mov     dword ptr [rsp+290h+lpcbMaxValueLen], r8d
0x1800061a0  mov     dword ptr [rsp+290h+lpcbMaxValueNameLen], r10d
0x1800061a5  mov     dword ptr [rsp+290h+lpcValues], r11d
0x1800061aa  mov     dword ptr [rsp+290h+lpcbMaxClassLen], ebx
0x1800061ae  mov     dword ptr [rsp+290h+lpcbMaxSubKeyLen], edi
0x1800061b2  mov     dword ptr [rsp+290h+lpcSubKeys], esi
0x1800061b6  mov     r8d, [r14]
0x1800061b9  lea     rdx, a08x04x04x02x02_0; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x1800061c0  lea     rcx, [rbp+190h+var_B0]
0x1800061c7  call    ??$swprintf_s@$0CM@@@YAHAEAY0CM@_WPEB_WZZ; swprintf_s<44>(wchar_t (&)[44],wchar_t const *,...)
0x1800061cc  mov     rcx, [rbp+190h+var_200]
0x1800061d0  add     rcx, 8
0x1800061d4  xor     r12d, r12d
0x1800061d7  mov     [rsp+290h+lpcSubKeys], r12
0x1800061dc  mov     r9d, 1
0x1800061e2  lea     r8, [rbp+190h+var_B0]
0x1800061e9  lea     rdx, [rbp+190h+hKey]
0x1800061f0  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x1800061f5  nop
0x1800061f6  mov     rdi, [rbp+190h+hKey]
0x1800061fd  test    rdi, rdi
0x180006200  jnz     loc_180006662
0x180006206  xorps   xmm0, xmm0
0x180006209  movdqu  [rbp+190h+var_210], xmm0
0x18000620e  test    rdi, rdi
0x180006211  jnz     loc_1800063B9
0x180006217  mov     rdx, r15
0x18000621a  lea     rcx, [rbp+190h+var_C0]
0x180006221  call    GetDefaultValue
0x180006226  lea     rcx, [rbp+190h+var_1B8]
0x18000622a  cmp     rcx, rax
0x18000622d  jz      loc_1800069BB
0x180006233  mov     rbx, [rax+8]
0x180006237  mov     [rax+8], r12
0x18000623b  mov     rsi, [rax]
0x18000623e  mov     [rax], r12
0x180006241  mov     [rsp+290h+var_218], rsi
0x180006246  mov     qword ptr [rbp+190h+var_210+8], rbx
0x18000624a  mov     qword ptr [rbp+190h+var_210], rsi
0x18000624e  mov     r15, [rbp+190h+var_B8]
0x180006255  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000625c  test    r15, r15
0x18000625f  jz      short loc_18000629B
0x180006261  mov     eax, r12d
0x180006264  lock xadd [r15+8], eax
0x18000626a  cmp     eax, 1
0x18000626d  jnz     short loc_18000629B
0x18000626f  mov     rax, [r15]
0x180006272  mov     rcx, r15
0x180006275  mov     rax, [rax]
0x180006278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000627d  mov     eax, r12d
0x180006280  lock xadd [r15+0Ch], eax
0x180006286  cmp     eax, 1
0x180006289  jnz     short loc_18000629B
0x18000628b  mov     rax, [r15]
0x18000628e  mov     rcx, r15
0x180006291  mov     rax, [rax+8]
0x180006295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000629a  nop
0x18000629b  cmp     dword ptr [r14+10h], 6
0x1800062a0  jz      loc_1800066C7
0x1800062a6  mov     r14, [rbp+190h+var_1E8]
0x1800062aa  xor     ecx, ecx
0x1800062ac  mov     [r14], rcx
0x1800062af  mov     [r14+8], rcx
0x1800062b3  lea     rax, [rbp+190h+var_210]
0x1800062b7  cmp     r14, rax
0x1800062ba  jz      short loc_1800062C5
0x1800062bc  mov     [r14+8], rbx
0x1800062c0  mov     ebx, ecx
0x1800062c2  mov     [r14], rsi
0x1800062c5  mov     [rsp+290h+var_220], 1
0x1800062cd  test    rbx, rbx
0x1800062d0  jz      short loc_180006309
0x1800062d2  mov     eax, r12d
0x1800062d5  lock xadd [rbx+8], eax
0x1800062da  cmp     eax, 1
0x1800062dd  jnz     short loc_180006309
0x1800062df  mov     rax, [rbx]
0x1800062e2  mov     rcx, rbx
0x1800062e5  mov     rax, [rax]
0x1800062e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ed  lock xadd [rbx+0Ch], r12d
0x1800062f3  cmp     r12d, 1
0x1800062f7  jnz     short loc_180006309
0x1800062f9  mov     rax, [rbx]
0x1800062fc  mov     rcx, rbx
0x1800062ff  mov     rax, [rax+8]
0x180006303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006308  nop
0x180006309  test    rdi, rdi
0x18000630c  jz      short loc_180006317
0x18000630e  mov     rcx, rdi; hKey
0x180006311  call    cs:__imp_RegCloseKey
0x180006317  mov     rax, r14
0x18000631a  jmp     short loc_18000638F
0x18000631c  mov     eax, [r14+10h]
0x180006320  cmp     [rdi+10h], eax
0x180006323  jnb     loc_18000613C
0x180006329  lea     r15, [rdi+38h]
0x18000632d  mov     rax, r12
0x180006330  sub     rax, rbx
0x180006333  add     rsi, rax
0x180006336  jmp     loc_18000613F
0x18000633b  movzx   eax, word ptr [r14+4]
0x180006340  cmp     [rdi+4], ax
0x180006344  jnz     loc_180006131
0x18000634a  movzx   eax, word ptr [r14+6]
0x18000634f  cmp     [rdi+6], ax
0x180006353  jnz     loc_180006131
0x180006359  lea     rdx, [r14+8]; Buf2
0x18000635d  lea     rcx, [rdi+8]; Buf1
0x180006361  mov     r8d, 8; Size
0x180006367  call    memcmp_0
0x18000636c  test    eax, eax
0x18000636e  jns     loc_18000613C
0x180006374  jmp     short loc_180006329
0x180006376  cmp     dword ptr [r15+20h], 0
0x18000637b  jz      loc_180006155
0x180006381  mov     rdx, r15
0x180006384  mov     rcx, r13
0x180006387  call    GetDefaultValue
0x18000638c  mov     rax, r13
0x18000638f  mov     rcx, [rbp+190h+var_40]
0x180006396  xor     rcx, rsp; StackCookie
0x180006399  call    __security_check_cookie
0x18000639e  mov     rbx, [rsp+290h+arg_18]
0x1800063a6  add     rsp, 260h
0x1800063ad  pop     r15
0x1800063af  pop     r14
0x1800063b1  pop     r13
0x1800063b3  pop     r12
0x1800063b5  pop     rdi
0x1800063b6  pop     rsi
0x1800063b7  pop     rbp
0x1800063b8  retn
0x1800063b9  test    r13b, r13b
0x1800063bc  jnz     loc_180006217
0x1800063c2  mov     [rbp+190h+cValues], r12d
0x1800063c9  lea     r9, [rbp+190h+cValues]
0x1800063d0  xor     r8d, r8d
0x1800063d3  lea     rdx, [rbp+190h+var_1E0]
0x1800063d7  lea     rcx, [rbp+190h+hKey]
0x1800063de  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x1800063e3  nop
0x1800063e4  mov     edi, [rbp+190h+cValues]
0x1800063ea  mov     eax, edi
0x1800063ec  and     eax, 0FFFF0000h
0x1800063f1  cmp     eax, 0FFFF0000h
0x1800063f6  jnz     loc_18000698B
0x1800063fc  mov     ecx, 40h ; '@'; Size
0x180006401  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006406  mov     rbx, rax
0x180006409  mov     [rsp+290h+var_218], rax
0x18000640e  test    rax, rax
0x180006411  jz      loc_1800069AA
0x180006417  mov     dword ptr [rax+8], 1
0x18000641e  mov     dword ptr [rax+0Ch], 1
0x180006425  lea     rcx, ??_7?$_Ref_count_obj@VProperty@NetSetup2@@@std@@6B@; const std::_Ref_count_obj<NetSetup2::Property>::`vftable'
0x18000642c  mov     [rax], rcx
0x18000642f  movups  xmm0, xmmword ptr [r14]
0x180006433  movups  xmmword ptr [rax+10h], xmm0
0x180006437  mov     eax, [r14+10h]
0x18000643b  mov     [rbx+20h], eax
0x18000643e  mov     [rbx+24h], r12d
0x180006442  mov     [rbx+28h], r12
0x180006446  mov     [rbx+30h], r12
0x18000644a  mov     [rbx+38h], r12
0x18000644e  lea     rsi, [rbx+10h]
0x180006452  mov     [rsp+290h+var_218], rsi
0x180006457  mov     qword ptr [rbp+190h+var_210+8], rbx
0x18000645b  mov     qword ptr [rbp+190h+var_210], rsi
0x18000645f  mov     [rsp+290h+var_220], r12d
0x180006464  movzx   eax, di
0x180006467  mov     [rsi+14h], eax
0x18000646a  lea     rdi, [rsi+18h]
0x18000646e  lea     rax, [rbp+190h+var_1E0]
0x180006472  cmp     rdi, rax
0x180006475  jz      loc_1800069B2
0x18000647b  mov     rcx, [rdi]; Block
0x18000647e  test    rcx, rcx
0x180006481  jz      short loc_18000648C
0x180006483  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006488  mov     [rdi+8], r12
0x18000648c  mov     rax, [rbp+190h+var_1E0]
0x180006490  mov     [rdi], rax
0x180006493  mov     rax, [rbp+190h+var_1D8]
0x180006497  mov     [rdi+8], rax
0x18000649b  mov     rax, [rbp+190h+var_1D0]
0x18000649f  mov     [rdi+10h], rax
0x1800064a3  mov     rcx, r12; Block
0x1800064a6  test    rcx, rcx
0x1800064a9  jz      short loc_1800064B0
0x1800064ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800064b0  mov     rdi, [rbp+190h+hKey]
0x1800064b7  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800064be  jmp     loc_18000629B
0x1800064c3  mov     rax, [r8]
0x1800064c6  sub     rax, qword ptr cs:NETSETUPPKEY_Object_Id
0x1800064cd  jnz     short loc_1800064DA
0x1800064cf  mov     rax, [r8+8]
0x1800064d3  sub     rax, qword ptr cs:NETSETUPPKEY_Object_Id+8
0x1800064da  test    rax, rax
0x1800064dd  jnz     loc_1800060EC
0x1800064e3  lea     r8, [rcx+14h]
0x1800064e7  mov     rdx, r14
0x1800064ea  mov     rcx, r13
0x1800064ed  call    ??$make_shared@VProperty@NetSetup2@@AEBU_NETSETUPPROPKEY@@AEBU_GUID@@@std@@YA?AV?$shared_ptr@VProperty@NetSetup2@@@0@AEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; std::make_shared<NetSetup2::Property,_NETSETUPPROPKEY const &,_GUID const &>(_NETSETUPPROPKEY const &,_GUID const &)
0x1800064f2  nop
0x1800064f3  mov     rax, r13
0x1800064f6  jmp     loc_18000638F
0x1800064fb  mov     rax, [r8]
0x1800064fe  sub     rax, qword ptr cs:NETSETUPPKEY_Object_ApiObjectType
0x180006505  jnz     short loc_180006512
0x180006507  mov     rax, [r8+8]
0x18000650b  sub     rax, qword ptr cs:NETSETUPPKEY_Object_ApiObjectType+8
0x180006512  test    rax, rax
0x180006515  jnz     loc_1800060EC
0x18000651b  mov     eax, [rcx+10h]
0x18000651e  mov     [rbp+190h+cValues], eax
0x180006524  lea     r8, [rbp+190h+cValues]
0x18000652b  mov     rdx, r14
0x18000652e  mov     rcx, r13
0x180006531  call    ??$make_shared@VProperty@NetSetup2@@AEBU_NETSETUPPROPKEY@@K@std@@YA?AV?$shared_ptr@VProperty@NetSetup2@@@0@AEBU_NETSETUPPROPKEY@@$$QEAK@Z; std::make_shared<NetSetup2::Property,_NETSETUPPROPKEY const &,ulong>(_NETSETUPPROPKEY const &,ulong &&)
0x180006536  nop
0x180006537  mov     rax, r13
  ... truncated ...
```
