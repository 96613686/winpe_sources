# AuthHostWebInstance::ProcessUrlActionInternal(ushort const *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x140010900`
- end: `0x140011171`
- name: `?ProcessUrlActionInternal@AuthHostWebInstance@@AEAAJPEBGKPEAEK1K@Z`
- size: `2161`
- prototype: `int(AuthHostWebInstance *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140010820`

## callees

- `0x14000429c`
- `0x14000c3dc`
- `0x1400104f0`
- `0x140010900`
- `0x1400113a0`
- `0x140011438`
- `0x1400114c8`
- `0x140011550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010a5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010a5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010a6a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400109ef`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400109ef`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::ProcessUrlActionInternal(
        AuthHostWebInstance *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        IID *rclsid,
        unsigned int a7)
{
  unsigned int v8; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  bool v13; // zf
  unsigned int v14; // eax
  unsigned __int8 *v15; // rbx
  int v16; // r14d
  int v17; // r8d
  int v18; // esi
  unsigned int v19; // ebp
  PVOID v20; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // r8
  __int64 *v24; // rdx
  bool v25; // zf
  bool v26; // zf
  unsigned int v27; // eax
  int v28; // edx
  _QWORD *v29; // rcx
  __int64 *v30; // rdx
  __int64 v31; // rdx
  bool v32; // zf
  LPOLESTR lpsz; // [rsp+78h] [rbp+20h] BYREF

  v8 = a3;
  if ( !a4 || a5 < 4 )
    return 2147942487LL;
  if ( a3 <= 0x180E )
  {
    if ( a3 == 6158 )
      goto LABEL_191;
    if ( a3 <= 0x1602 )
    {
      if ( a3 == 5634 )
        goto LABEL_32;
      if ( a3 <= 0x120A )
      {
        if ( a3 == 4618 )
          goto LABEL_74;
        if ( a3 <= 0x1204 )
        {
          if ( a3 == 4612 || a3 == 4097 || a3 == 4100 )
            goto LABEL_74;
          v11 = a3 - 4608;
          if ( a3 != 4608 )
          {
LABEL_14:
            v12 = v11 - 1;
            if ( !v12 )
              goto LABEL_74;
            goto LABEL_15;
          }
          v15 = (unsigned __int8 *)rclsid;
          lpsz = 0;
          if ( rclsid && a7 == 16 )
          {
            v16 = 0;
            v18 = 3;
            v19 = 1;
            if ( StringFromCLSID(rclsid, &lpsz) >= 0 )
              v16 = (int)lpsz;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
            {
              WPP_SF_S_guid_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, v17, v16, (__int64)v15, (__int64)a2);
            }
            if ( (Microsoft_Windows_WebAuthEnableBits & 4) != 0 )
              McTemplateU0jz_EventWriteTransfer(v20, UrlActionActiveXDisallowedEvent, v15, a2);
            CoTaskMemFree(lpsz);
            goto LABEL_41;
          }
          CoTaskMemFree(0);
          return 2147942487LL;
        }
        if ( a3 != 4613 )
        {
          if ( a3 == 4614 )
            goto LABEL_74;
          v12 = a3 - 4615;
          if ( a3 != 4615 )
            goto LABEL_15;
        }
        goto LABEL_32;
      }
      if ( a3 <= 0x1407 )
      {
        if ( a3 == 5127 || a3 == 4619 )
          goto LABEL_74;
        if ( a3 != 5120 )
        {
          if ( a3 == 5121 || a3 == 5122 )
            goto LABEL_74;
          v14 = a3 - 5125;
          v13 = a3 == 5125;
          goto LABEL_188;
        }
        goto LABEL_32;
      }
      switch ( a3 )
      {
        case 0x1408u:
          goto LABEL_74;
        case 0x1409u:
        case 0x140Au:
          goto LABEL_32;
        case 0x140Bu:
          goto LABEL_74;
      }
      v25 = a3 == 5633;
      goto LABEL_182;
    }
    if ( a3 <= 0x1800 )
    {
      if ( a3 == 6144 )
        goto LABEL_74;
      if ( a3 > 0x1609 )
      {
        if ( a3 == 5642 )
          goto LABEL_74;
        v11 = a3 - 5643;
        if ( a3 != 5643 )
          goto LABEL_14;
        goto LABEL_32;
      }
      switch ( a3 )
      {
        case 0x1609u:
          goto LABEL_74;
        case 0x1603u:
        case 0x1604u:
          goto LABEL_32;
        case 0x1605u:
        case 0x1606u:
          goto LABEL_74;
      }
      v27 = a3 - 5639;
      v26 = a3 == 5639;
LABEL_180:
      if ( v26 )
        goto LABEL_74;
LABEL_181:
      v25 = v27 == 1;
      goto LABEL_182;
    }
    if ( a3 <= 0x1808 )
    {
      if ( a3 == 6152 || a3 == 6146 || a3 == 6147 || a3 == 6148 )
        goto LABEL_74;
      v12 = a3 - 6149;
      if ( a3 == 6149 )
        goto LABEL_191;
LABEL_15:
      v14 = v12 - 1;
      v13 = v14 == 0;
LABEL_188:
      if ( !v13 )
      {
LABEL_189:
        v32 = v14 == 1;
LABEL_190:
        if ( !v32 )
          goto LABEL_191;
      }
LABEL_74:
      v18 = 3;
      v19 = 1;
      if ( a3 == 5121 || a3 == 5642 || a3 == 9984 || a3 == 5644 )
        goto LABEL_41;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 5u )
      {
        goto LABEL_167;
      }
      v28 = 24;
      goto LABEL_166;
    }
    if ( a3 == 6153 )
      goto LABEL_74;
LABEL_191:
    v18 = 0;
    v19 = -2146697199;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, a3, a3, (__int64)a2);
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 4) == 0 )
      goto LABEL_41;
    v23 = v8;
    v24 = UrlActionDefaultEvent;
    goto LABEL_40;
  }
  if ( a3 > 0x2101 )
  {
    if ( a3 <= 0x2401 )
    {
      if ( a3 == 9217 )
        goto LABEL_74;
      if ( a3 > 0x2200 )
      {
        if ( a3 != 8705 )
        {
          if ( a3 == 8960 )
            goto LABEL_191;
          if ( a3 != 8961 && a3 != 8962 )
          {
            v32 = a3 == 9216;
            goto LABEL_190;
          }
        }
        goto LABEL_74;
      }
      if ( a3 == 8704 || a3 == 8450 || a3 == 8451 )
        goto LABEL_74;
      if ( a3 != 8452 )
      {
        if ( a3 == 8453 )
          goto LABEL_191;
        v14 = a3 - 8454;
        if ( a3 == 8454 )
        {
          v18 = 3;
          v19 = 0;
          v22 = WPP_GLOBAL_Control;
          v8 = 8454;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 65) < 5u )
          {
            goto LABEL_167;
          }
          v28 = 25;
LABEL_166:
          WPP_SF_DS(v22[7], v28, a3, v8, (__int64)a2);
LABEL_167:
          if ( (Microsoft_Windows_WebAuthEnableBits & 8) == 0 )
            goto LABEL_41;
          v23 = v8;
          goto LABEL_133;
        }
        goto LABEL_189;
      }
      goto LABEL_32;
    }
    if ( a3 > 0x2703 )
    {
      if ( a3 != 9988 )
      {
        if ( a3 == 9989 || a3 == 9990 )
          goto LABEL_74;
        v14 = a3 - 9992;
        v13 = a3 == 9992;
        goto LABEL_188;
      }
      goto LABEL_32;
    }
    switch ( a3 )
    {
      case 0x2703u:
      case 0x2402u:
        goto LABEL_74;
      case 0x2500u:
LABEL_32:
        v18 = 0;
        v19 = 0;
        if ( a3 == 5120 )
          goto LABEL_41;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, a3, a3, (__int64)a2);
        }
        if ( (Microsoft_Windows_WebAuthEnableBits & 8) == 0 )
          goto LABEL_41;
        v23 = v8;
        goto LABEL_39;
      case 0x2600u:
        goto LABEL_74;
    }
    v27 = a3 - 9984;
    v26 = a3 == 9984;
    goto LABEL_180;
  }
  if ( a3 == 8449 )
    goto LABEL_74;
  if ( a3 > 0x1D01 )
  {
    if ( a3 > 0x2000 )
    {
      if ( a3 == 8193 || a3 == 8196 || a3 == 8197 || a3 == 8199 )
        goto LABEL_74;
      v25 = a3 == 8448;
LABEL_182:
      if ( !v25 )
        goto LABEL_191;
      goto LABEL_32;
    }
    if ( a3 == 0x2000 )
      goto LABEL_74;
    goto LABEL_191;
  }
  if ( a3 == 7425 )
    goto LABEL_191;
  if ( a3 > 0x1A04 )
  {
    if ( a3 == 6661 )
      goto LABEL_74;
    if ( a3 == 6662 || a3 == 6672 )
      goto LABEL_32;
    if ( a3 != 7168 )
      goto LABEL_191;
    v18 = 0;
    v19 = 0;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids, a2);
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 8) == 0 )
      goto LABEL_41;
    v30 = UrlActionJavaPermissionsProhibitedEvent;
LABEL_144:
    McTemplateU0z_EventWriteTransfer(v29, v30, a2);
    goto LABEL_41;
  }
  if ( a3 != 6660 )
  {
    if ( a3 == 6159 )
      goto LABEL_191;
    if ( a3 == 6160 )
      goto LABEL_74;
    if ( a3 != 6656 )
    {
      if ( a3 == 6657 )
        goto LABEL_191;
      v27 = a3 - 6658;
      if ( a3 == 6658 )
        goto LABEL_32;
      goto LABEL_181;
    }
    v19 = 0;
    if ( (*((_DWORD *)this + 32) & 0x100000) != 0 )
    {
      if ( AuthHostWebInstance::IsSilentLogonZoneForUrl(this, a2) )
      {
        v18 = 0;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids, a2);
        }
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) == 0 )
          goto LABEL_41;
        v30 = UrlActionCredentialsSilentLogonOkEvent;
        goto LABEL_144;
      }
      if ( (*((_DWORD *)this + 32) & 0x20000) == 0 )
      {
        v18 = 0x10000;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids, a2);
        }
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) == 0 )
          goto LABEL_41;
        v30 = UrlActionCredentialsMustPromptUserEvent;
        goto LABEL_144;
      }
      v29 = WPP_GLOBAL_Control;
      v18 = 196608;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 5u )
      {
        goto LABEL_114;
      }
      v31 = 29;
    }
    else
    {
      v18 = 196608;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 5u )
      {
        goto LABEL_114;
      }
      v31 = 30;
    }
    WPP_SF_S(v29[7], v31, &WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids, a2);
LABEL_114:
    if ( (Microsoft_Windows_WebAuthEnableBits & 1) == 0 )
      goto LABEL_41;
    v30 = UrlActionCredentialsAnonymousOnlyEvent;
    goto LABEL_144;
  }
  if ( (*((_DWORD *)this + 32) & 0x100000) == 0 )
  {
    v18 = 3;
    v19 = 1;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, a3, 6660, (__int64)a2);
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 8) == 0 )
      goto LABEL_41;
    v23 = 6660;
LABEL_133:
    v24 = UrlActionDisallowedEvent;
    goto LABEL_40;
  }
  v18 = 0;
  v19 = 0;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, a3, 6660, (__int64)a2);
  }
  if ( (Microsoft_Windows_WebAuthEnableBits & 8) == 0 )
    goto LABEL_41;
  v23 = 6660;
LABEL_39:
  v24 = UrlActionAllowedEvent;
LABEL_40:
  McTemplateU0dz_EventWriteTransfer(v22, v24, v23, a2);
LABEL_41:
  *(_DWORD *)a4 = v18;
  return v19;
}

```

## disassembly

```asm
0x140010900  mov     [rsp+arg_0], rbx
0x140010905  mov     [rsp+arg_8], rbp
0x14001090a  push    rsi
0x14001090b  push    rdi
0x14001090c  push    r12
0x14001090e  push    r14
0x140010910  push    r15
0x140010912  sub     rsp, 30h
0x140010916  mov     r15, r9
0x140010919  mov     ebx, r8d
0x14001091c  mov     rdi, rdx
0x14001091f  mov     rsi, rcx
0x140010922  test    r9, r9
0x140010925  jz      loc_140010A70
0x14001092b  cmp     [rsp+58h+arg_20], 4
0x140010933  jb      loc_140010A70
0x140010939  mov     eax, 180Eh
0x14001093e  mov     edx, 160Ah
0x140010943  mov     r12d, 3
0x140010949  cmp     ebx, eax
0x14001094b  ja      loc_140010C74
0x140010951  jz      loc_14001111B
0x140010957  lea     eax, [rdx-8]
0x14001095a  cmp     ebx, eax
0x14001095c  ja      loc_140010B7E
0x140010962  jz      loc_140010AA7
0x140010968  mov     eax, 120Ah
0x14001096d  cmp     ebx, eax
0x14001096f  ja      loc_140010B0B
0x140010975  jz      loc_140010C0D
0x14001097b  mov     eax, 1204h
0x140010980  cmp     ebx, eax
0x140010982  ja      loc_140010A8C
0x140010988  jz      loc_140010C0D
0x14001098e  mov     eax, ebx
0x140010990  sub     eax, 1001h
0x140010995  jz      loc_140010C0D
0x14001099b  sub     eax, r12d
0x14001099e  jz      loc_140010C0D
0x1400109a4  sub     eax, 1FCh
0x1400109a9  jz      short loc_1400109BC
0x1400109ab  sub     eax, 1
0x1400109ae  jz      loc_140010C0D
0x1400109b4  sub     eax, 1
0x1400109b7  jmp     loc_14001110C
0x1400109bc  mov     rbx, [rsp+58h+rclsid]
0x1400109c4  mov     [rsp+58h+lpsz], 0
0x1400109cd  test    rbx, rbx
0x1400109d0  jz      loc_140010A68
0x1400109d6  cmp     [rsp+58h+arg_30], 10h
0x1400109de  jnz     loc_140010A68
0x1400109e4  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x1400109e9  mov     rcx, rbx; rclsid
0x1400109ec  xor     r14d, r14d
0x1400109ef  call    cs:__imp_StringFromCLSID
0x1400109f5  mov     esi, r12d
0x1400109f8  mov     ebp, 1
0x1400109fd  test    eax, eax
0x1400109ff  cmovns  r14, [rsp+58h+lpsz]
0x140010a05  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a0c  lea     rax, WPP_GLOBAL_Control
0x140010a13  cmp     rcx, rax
0x140010a16  jz      short loc_140010A3D
0x140010a18  test    byte ptr [rcx+44h], 20h
0x140010a1c  jz      short loc_140010A3D
0x140010a1e  cmp     [rcx+41h], r12b
0x140010a22  jb      short loc_140010A3D
0x140010a24  mov     rcx, [rcx+38h]
0x140010a28  lea     edx, [rbp+1Fh]
0x140010a2b  mov     [rsp+58h+var_30], rdi
0x140010a30  mov     r9, r14
0x140010a33  mov     [rsp+58h+var_38], rbx
0x140010a38  call    WPP_SF_S_guid_S
0x140010a3d  test    cs:Microsoft_Windows_WebAuthEnableBits, 4
0x140010a44  jz      short loc_140010A58
0x140010a46  mov     r9, rdi
0x140010a49  lea     rdx, UrlActionActiveXDisallowedEvent
0x140010a50  mov     r8, rbx
0x140010a53  call    McTemplateU0jz_EventWriteTransfer
0x140010a58  mov     rcx, [rsp+58h+lpsz]; pv
0x140010a5d  call    cs:__imp_CoTaskMemFree
0x140010a63  jmp     loc_140010B01
0x140010a68  xor     ecx, ecx; pv
0x140010a6a  call    cs:__imp_CoTaskMemFree
0x140010a70  mov     eax, 80070057h
0x140010a75  mov     rbx, [rsp+58h+arg_0]
0x140010a7a  mov     rbp, [rsp+58h+arg_8]
0x140010a7f  add     rsp, 30h
0x140010a83  pop     r15
0x140010a85  pop     r14
0x140010a87  pop     r12
0x140010a89  pop     rdi
0x140010a8a  pop     rsi
0x140010a8b  retn
0x140010a8c  mov     eax, ebx
0x140010a8e  sub     eax, 1205h
0x140010a93  jz      short loc_140010AA7
0x140010a95  sub     eax, 1
0x140010a98  jz      loc_140010C0D
0x140010a9e  sub     eax, 1
0x140010aa1  jnz     loc_1400109B4
0x140010aa7  xor     esi, esi
0x140010aa9  xor     ebp, ebp
0x140010aab  cmp     ebx, 1400h
0x140010ab1  jz      short loc_140010B01
0x140010ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x140010aba  lea     rax, WPP_GLOBAL_Control
0x140010ac1  cmp     rcx, rax
0x140010ac4  jz      short loc_140010AE6
0x140010ac6  test    byte ptr [rcx+44h], 20h
0x140010aca  jz      short loc_140010AE6
0x140010acc  cmp     byte ptr [rcx+41h], 5
0x140010ad0  jb      short loc_140010AE6
0x140010ad2  mov     rcx, [rcx+38h]
0x140010ad6  lea     edx, [rsi+15h]
0x140010ad9  mov     r9d, ebx
0x140010adc  mov     [rsp+58h+var_38], rdi
0x140010ae1  call    WPP_SF_DS
0x140010ae6  test    cs:Microsoft_Windows_WebAuthEnableBits, 8
0x140010aed  jz      short loc_140010B01
0x140010aef  mov     r8d, ebx
0x140010af2  lea     rdx, UrlActionAllowedEvent
0x140010af9  mov     r9, rdi
0x140010afc  call    McTemplateU0dz_EventWriteTransfer
0x140010b01  mov     [r15], esi
0x140010b04  mov     eax, ebp
0x140010b06  jmp     loc_140010A75
0x140010b0b  mov     eax, 1407h
0x140010b10  cmp     ebx, eax
0x140010b12  ja      short loc_140010B4C
0x140010b14  jz      loc_140010C0D
0x140010b1a  mov     eax, ebx
0x140010b1c  sub     eax, 120Bh
0x140010b21  jz      loc_140010C0D
0x140010b27  sub     eax, 1F5h
0x140010b2c  jz      loc_140010AA7
0x140010b32  sub     eax, 1
0x140010b35  jz      loc_140010C0D
0x140010b3b  sub     eax, 1
0x140010b3e  jz      loc_140010C0D
0x140010b44  sub     eax, r12d
0x140010b47  jmp     loc_14001110C
0x140010b4c  mov     eax, ebx
0x140010b4e  sub     eax, 1408h
0x140010b53  jz      loc_140010C0D
0x140010b59  sub     eax, 1
0x140010b5c  jz      loc_140010AA7
0x140010b62  sub     eax, 1
0x140010b65  jz      loc_140010AA7
0x140010b6b  sub     eax, 1
0x140010b6e  jz      loc_140010C0D
0x140010b74  cmp     eax, 1F6h
0x140010b79  jmp     loc_1400110E2
0x140010b7e  mov     eax, 1800h
0x140010b83  cmp     ebx, eax
0x140010b85  ja      short loc_140010BD4
0x140010b87  jz      loc_140010C0D
0x140010b8d  mov     eax, 1609h
0x140010b92  cmp     ebx, eax
0x140010b94  ja      short loc_140010BC0
0x140010b96  jz      short loc_140010C0D
0x140010b98  mov     eax, ebx
0x140010b9a  sub     eax, 1603h
0x140010b9f  jz      loc_140010AA7
0x140010ba5  sub     eax, 1
0x140010ba8  jz      loc_140010AA7
0x140010bae  sub     eax, 1
0x140010bb1  jz      short loc_140010C0D
0x140010bb3  sub     eax, 1
0x140010bb6  jz      short loc_140010C0D
0x140010bb8  sub     eax, 1
0x140010bbb  jmp     loc_1400110D9
0x140010bc0  mov     eax, ebx
0x140010bc2  sub     eax, edx
0x140010bc4  jz      short loc_140010C0D
0x140010bc6  sub     eax, 1
0x140010bc9  jz      loc_140010AA7
0x140010bcf  jmp     loc_1400109AB
0x140010bd4  mov     eax, 1808h
0x140010bd9  cmp     ebx, eax
0x140010bdb  ja      short loc_140010C00
0x140010bdd  jz      short loc_140010C0D
0x140010bdf  mov     eax, ebx
0x140010be1  sub     eax, 1802h
0x140010be6  jz      short loc_140010C0D
0x140010be8  sub     eax, 1
0x140010beb  jz      short loc_140010C0D
0x140010bed  sub     eax, 1
0x140010bf0  jz      short loc_140010C0D
0x140010bf2  sub     eax, 1
0x140010bf5  jz      loc_14001111B
0x140010bfb  jmp     loc_1400109B4
0x140010c00  mov     eax, ebx
0x140010c02  sub     eax, 1809h
0x140010c07  jnz     loc_140010F86
0x140010c0d  mov     esi, r12d
0x140010c10  mov     ebp, 1
0x140010c15  cmp     ebx, 1401h
0x140010c1b  jz      loc_140010B01
0x140010c21  cmp     ebx, edx
0x140010c23  jz      loc_140010B01
0x140010c29  cmp     ebx, 2700h
0x140010c2f  jz      loc_140010B01
0x140010c35  cmp     ebx, 160Ch
0x140010c3b  jz      loc_140010B01
0x140010c41  mov     rcx, cs:WPP_GLOBAL_Control; this
0x140010c48  lea     rax, WPP_GLOBAL_Control
0x140010c4f  cmp     rcx, rax
0x140010c52  jz      loc_14001105D
0x140010c58  test    byte ptr [rcx+44h], 20h
0x140010c5c  jz      loc_14001105D
0x140010c62  cmp     byte ptr [rcx+41h], 5
0x140010c66  jb      loc_14001105D
0x140010c6c  lea     edx, [rbp+17h]
0x140010c6f  jmp     loc_14001104C
0x140010c74  mov     eax, 2101h
0x140010c79  cmp     ebx, eax
0x140010c7b  ja      loc_140010FC9
0x140010c81  jz      short loc_140010C0D
0x140010c83  mov     eax, 1D01h
0x140010c88  cmp     ebx, eax
0x140010c8a  ja      loc_140010F61
0x140010c90  jz      loc_14001111B
0x140010c96  mov     r14d, 1A04h
0x140010c9c  cmp     ebx, r14d
0x140010c9f  ja      loc_140010EDD
0x140010ca5  jz      loc_140010E2E
0x140010cab  mov     eax, ebx
0x140010cad  sub     eax, 180Fh
0x140010cb2  jz      loc_14001111B
0x140010cb8  sub     eax, 1
0x140010cbb  jz      loc_140010C0D
0x140010cc1  sub     eax, 1F0h
0x140010cc6  jz      short loc_140010CDF
0x140010cc8  sub     eax, 1
0x140010ccb  jz      loc_14001111B
0x140010cd1  sub     eax, 1
0x140010cd4  jz      loc_140010AA7
0x140010cda  jmp     loc_1400110DF
0x140010cdf  xor     ebp, ebp
0x140010ce1  test    dword ptr [rcx+80h], 100000h
0x140010ceb  jz      loc_140010E03
0x140010cf1  mov     rdx, rdi; unsigned __int16 *
0x140010cf4  call    ?IsSilentLogonZoneForUrl@AuthHostWebInstance@@AEAAHPEBG@Z; AuthHostWebInstance::IsSilentLogonZoneForUrl(ushort const *)
0x140010cf9  test    eax, eax
0x140010cfb  jz      short loc_140010D4D
0x140010cfd  xor     esi, esi
0x140010cff  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d06  lea     rax, WPP_GLOBAL_Control
0x140010d0d  cmp     rcx, rax
0x140010d10  jz      short loc_140010D34
0x140010d12  test    byte ptr [rcx+44h], 20h
0x140010d16  jz      short loc_140010D34
0x140010d18  cmp     byte ptr [rcx+41h], 5
0x140010d1c  jb      short loc_140010D34
0x140010d1e  mov     rcx, [rcx+38h]
0x140010d22  lea     edx, [rbp+1Bh]
0x140010d25  mov     r9, rdi
0x140010d28  lea     r8, WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids
0x140010d2f  call    WPP_SF_S
0x140010d34  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x140010d3b  jz      loc_140010B01
0x140010d41  lea     rdx, UrlActionCredentialsSilentLogonOkEvent
0x140010d48  jmp     loc_140010F54
0x140010d4d  test    dword ptr [rsi+80h], 20000h
0x140010d57  jnz     short loc_140010DAE
0x140010d59  mov     esi, 10000h
0x140010d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d65  lea     rax, WPP_GLOBAL_Control
0x140010d6c  cmp     rcx, rax
0x140010d6f  jz      short loc_140010D95
0x140010d71  test    byte ptr [rcx+44h], 20h
0x140010d75  jz      short loc_140010D95
0x140010d77  cmp     byte ptr [rcx+41h], 5
0x140010d7b  jb      short loc_140010D95
0x140010d7d  mov     rcx, [rcx+38h]
0x140010d81  lea     r8, WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids
0x140010d88  mov     edx, 1Ch
0x140010d8d  mov     r9, rdi
0x140010d90  call    WPP_SF_S
0x140010d95  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x140010d9c  jz      loc_140010B01
0x140010da2  lea     rdx, UrlActionCredentialsMustPromptUserEvent
0x140010da9  jmp     loc_140010F54
0x140010dae  mov     rcx, cs:WPP_GLOBAL_Control
0x140010db5  lea     rax, WPP_GLOBAL_Control
0x140010dbc  mov     esi, 30000h
0x140010dc1  cmp     rcx, rax
0x140010dc4  jz      short loc_140010DEA
0x140010dc6  test    byte ptr [rcx+44h], 20h
0x140010dca  jz      short loc_140010DEA
0x140010dcc  cmp     byte ptr [rcx+41h], 5
0x140010dd0  jb      short loc_140010DEA
0x140010dd2  mov     edx, 1Dh
0x140010dd7  mov     rcx, [rcx+38h]
0x140010ddb  lea     r8, WPP_2f62e1cc15cd35a2451044e3f3cd4e75_Traceguids
0x140010de2  mov     r9, rdi
0x140010de5  call    WPP_SF_S
0x140010dea  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x140010df1  jz      loc_140010B01
  ... truncated ...
```
