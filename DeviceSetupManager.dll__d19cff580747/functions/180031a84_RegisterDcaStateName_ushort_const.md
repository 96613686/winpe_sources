# RegisterDcaStateName(ushort const *)

- ea: `0x180031a84`
- end: `0x180031ff7`
- name: `?RegisterDcaStateName@@YAJPEBG@Z`
- size: `1395`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e190`

## callees

- `0x18000e8e4`
- `0x18001af70`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x180022070`
- `0x180025074`
- `0x180027ba8`
- `0x180031a84`
- `0x180032000`
- `0x1800324dc`
- `0x1800327a4`
- `0x180032aa0`
- `0x180032cb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031e5d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180031be0`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180031be0`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180031e4e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180031e4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegisterDcaStateName(unsigned __int16 *a1)
{
  unsigned __int128 v2; // rax
  signed int ObjectProperties; // r14d
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // rbx
  char v6; // di
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // r13
  __int64 v14; // rdi
  __int64 v15; // rsi
  int v16; // eax
  __int64 v17; // rax
  const unsigned __int16 *v18; // r12
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rsi
  LPVOID v21; // rsi
  unsigned __int16 *v22; // r13
  unsigned __int16 *v23; // rdi
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int16 **v30; // [rsp+20h] [rbp-49h]
  unsigned __int64 *v31; // [rsp+28h] [rbp-41h]
  unsigned int *v32; // [rsp+30h] [rbp-39h]
  char v33; // [rsp+40h] [rbp-29h]
  unsigned __int64 v34; // [rsp+44h] [rbp-25h] BYREF
  unsigned int v35[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v36; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v37; // [rsp+60h] [rbp-9h]
  LPVOID pv; // [rsp+70h] [rbp+7h] BYREF

  v37 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d57ca44452473f5574b7c550b191f620_Traceguids, a1);
  if ( dword_18005A598 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18005A598);
    if ( dword_18005A598 == -1 )
    {
      *(_OWORD *)&xmmword_18005A1F0 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
      dword_18005A200 = 108;
      dword_18005A204 = 0;
      qword_18005A208 = 0;
      xmmword_18005A210 = DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers;
      dword_18005A220 = 109;
      dword_18005A224 = 0;
      qword_18005A228 = 0;
      xmmword_18005A230 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
      dword_18005A240 = 100;
      dword_18005A244 = 0;
      qword_18005A248 = 0;
      Init_thread_footer(&dword_18005A598);
    }
  }
  LODWORD(v34) = 0;
  *(_QWORD *)v35 = 0;
  v32 = v35;
  v31 = &v34;
  v30 = &xmmword_18005A1F0;
  ObjectProperties = DevGetObjectProperties(2, a1, 0);
  if ( ObjectProperties < 0 )
    goto LABEL_44;
  pv = 0;
  v4 = 0;
  v5 = 0;
  v36 = 0;
  if ( (_DWORD)v34 != 3 )
    goto LABEL_42;
  v34 = 3;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v8 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_WnfStateName + 1);
  v9 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
  v10 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers + 1);
  v11 = DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers;
  v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
  v13 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
  while ( ObjectProperties >= 0 )
  {
    v14 = 6 * v7;
    v15 = *(_QWORD *)v35;
    v16 = *(_DWORD *)(*(_QWORD *)v35 + 48 * v7 + 16);
    switch ( v16 )
    {
      case 'd':
        v17 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14) - v13;
        if ( !v17 )
          v17 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14 + 8) - v12;
        if ( v17 )
          break;
        v18 = *(const unsigned __int16 **)(*(_QWORD *)v35 + 8 * v14 + 40);
        if ( !v18 || *(_DWORD *)(*(_QWORD *)v35 + 8 * v14 + 32) != 8210 )
          break;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v5 = 0;
        v36 = 0;
        v20 = v19 + 1;
        if ( v19 + 1 < v19 || (v36 = 0, v2 = v20 * (unsigned __int128)2uLL, !is_mul_ok(v20, 2u)) )
        {
          ObjectProperties = -2147024362;
          break;
        }
        v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v20);
        v36 = v5;
        ObjectProperties = v5 == 0 ? 0x8007000E : 0;
        if ( v5 )
          StringCchCopyNExW(v5, v19 + 1, v18, v19, v30, v31, (unsigned int)v32);
        goto LABEL_23;
      case 'm':
        v28 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14) - v11;
        if ( !v28 )
          v28 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14 + 8) - v10;
        if ( v28 || !*(_QWORD *)(*(_QWORD *)v35 + 8 * v14 + 40) || *(_DWORD *)(*(_QWORD *)v35 + 8 * v14 + 32) != 8210 )
          break;
        *(_QWORD *)&v2 = CoTaskMemAlloc(*(unsigned int *)(*(_QWORD *)v35 + 8 * v14 + 36));
        v4 = (unsigned __int16 *)v2;
        if ( (_QWORD)v2 )
          ObjectProperties = memcpy_s(
                               (void *const)v2,
                               *(unsigned int *)(v15 + 8 * v14 + 36),
                               *(const void *const *)(v15 + 8 * v14 + 40),
                               *(unsigned int *)(v15 + 8 * v14 + 36)) != 0
                           ? 0x80004005
                           : 0;
        else
          ObjectProperties = -2147024882;
LABEL_23:
        v8 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_WnfStateName + 1);
        v9 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
        v10 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers + 1);
        v11 = DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers;
        v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
        v13 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
        break;
      case 'l':
        v29 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14) - v9;
        if ( !v29 )
          v29 = *(_QWORD *)(*(_QWORD *)v35 + 8 * v14 + 8) - v8;
        if ( !v29 && *(_QWORD *)(*(_QWORD *)v35 + 8 * v14 + 40) && *(_DWORD *)(*(_QWORD *)v35 + 8 * v14 + 32) == 4099 )
        {
          v6 = 1;
          v33 = 1;
          ObjectProperties = memcpy_s(
                               &pv,
                               8u,
                               *(const void *const *)(*(_QWORD *)v35 + 40LL),
                               *(unsigned int *)(*(_QWORD *)v35 + 36LL)) != 0
                           ? 0x80004005
                           : 0;
          v8 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_WnfStateName + 1);
          v9 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
          v10 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers + 1);
          v11 = DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers;
          v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
          v13 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
          goto LABEL_25;
        }
        break;
    }
    v6 = v33;
LABEL_25:
    v7 = (unsigned int)(HIDWORD(v34) + 1);
    HIDWORD(v34) = v7;
    if ( (unsigned int)v7 >= (unsigned int)v34 )
      break;
  }
  v21 = pv;
  v22 = v37;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SSLL(*((_QWORD *)WPP_GLOBAL_Control + 2), DWORD2(v2), v9, (_DWORD)v5, (__int64)v4, (char)pv, SBYTE4(pv));
  if ( ObjectProperties >= 0 && v5 && v4 && v6 )
  {
    pv = 0;
    ObjectProperties = _InstalledFullNameFromFamilyName(v5, (unsigned __int16 **)&pv);
    v23 = (unsigned __int16 *)pv;
    if ( ObjectProperties >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_d57ca44452473f5574b7c550b191f620_Traceguids,
          (_DWORD)pv,
          (__int64)v5);
      v24 = _RegisterEvents((struct _WNF_STATE_NAME)v21, v23, v4, v22);
      ObjectProperties = v24;
      if ( v24 < 0 && (Microsoft_Windows_DeviceSetupManagerEnableBits & 0x10) != 0 )
        McTemplateU0zzq_EventWriteTransfer(v26, v25, (_DWORD)v22, (_DWORD)v23, v24);
    }
    if ( v23 )
      CoTaskMemFree(v23);
  }
LABEL_42:
  CoTaskMemFree(v4);
  DevFreeObjectProperties((unsigned int)v34, *(_QWORD *)v35);
  if ( v5 )
    CoTaskMemFree(v5);
LABEL_44:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_d57ca44452473f5574b7c550b191f620_Traceguids,
      (unsigned int)ObjectProperties);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180031a84  push    rbp
0x180031a86  push    rbx
0x180031a87  push    rsi
0x180031a88  push    rdi
0x180031a89  push    r12
0x180031a8b  push    r13
0x180031a8d  push    r14
0x180031a8f  push    r15
0x180031a91  lea     rbp, [rsp-1Fh]
0x180031a96  sub     rsp, 88h
0x180031a9d  mov     rax, cs:__security_cookie
0x180031aa4  xor     rax, rsp
0x180031aa7  mov     [rbp+57h+var_48], rax
0x180031aab  mov     r13, rcx
0x180031aae  mov     [rbp+57h+var_60], rcx
0x180031ab2  lea     rdi, WPP_GLOBAL_Control
0x180031ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ac0  cmp     rcx, rdi
0x180031ac3  jz      short loc_180031AE3
0x180031ac5  test    byte ptr [rcx+1Ch], 1
0x180031ac9  jz      short loc_180031AE3
0x180031acb  mov     edx, 0Eh
0x180031ad0  mov     r9, r13
0x180031ad3  lea     r8, WPP_d57ca44452473f5574b7c550b191f620_Traceguids
0x180031ada  mov     rcx, [rcx+10h]
0x180031ade  call    WPP_SF_S
0x180031ae3  mov     ecx, cs:_tls_index
0x180031ae9  mov     rax, gs:58h
0x180031af2  mov     edx, 4
0x180031af7  mov     rax, [rax+rcx*8]
0x180031afb  xor     r12d, r12d
0x180031afe  mov     eax, [rdx+rax]
0x180031b01  cmp     cs:dword_18005A598, eax
0x180031b07  jle     loc_180031BAA
0x180031b0d  lea     rcx, dword_18005A598
0x180031b14  call    _Init_thread_header
0x180031b19  cmp     cs:dword_18005A598, 0FFFFFFFFh
0x180031b20  jnz     loc_180031BAA
0x180031b26  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x180031b2d  movaps  cs:xmmword_18005A1F0, xmm0
0x180031b34  mov     eax, cs:dword_18004B910
0x180031b3a  mov     cs:dword_18005A200, eax
0x180031b40  mov     cs:dword_18005A204, r12d
0x180031b47  mov     cs:qword_18005A208, r12
0x180031b4e  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers
0x180031b55  movaps  cs:xmmword_18005A210, xmm0
0x180031b5c  mov     eax, cs:dword_18004B8F8
0x180031b62  mov     cs:dword_18005A220, eax
0x180031b68  mov     cs:dword_18005A224, r12d
0x180031b6f  mov     cs:qword_18005A228, r12
0x180031b76  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180031b7d  movaps  cs:xmmword_18005A230, xmm0
0x180031b84  mov     eax, cs:dword_180048E18
0x180031b8a  mov     cs:dword_18005A240, eax
0x180031b90  mov     cs:dword_18005A244, r12d
0x180031b97  mov     cs:qword_18005A248, r12
0x180031b9e  lea     rcx, dword_18005A598
0x180031ba5  call    _Init_thread_footer
0x180031baa  mov     dword ptr [rbp+57h+var_7C], r12d
0x180031bae  mov     qword ptr [rbp+57h+var_70], r12
0x180031bb2  lea     rax, [rbp+57h+var_70]
0x180031bb6  mov     qword ptr [rsp+0C0h+var_90], rax; unsigned int
0x180031bbb  lea     rax, [rbp+57h+var_7C]
0x180031bbf  mov     [rsp+0C0h+var_98], rax; unsigned __int64 *
0x180031bc4  lea     rax, xmmword_18005A1F0
0x180031bcb  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x180031bd0  mov     r9d, 3
0x180031bd6  xor     r8d, r8d
0x180031bd9  mov     rdx, r13
0x180031bdc  lea     ecx, [r9-1]
0x180031be0  call    cs:__imp_DevGetObjectProperties
0x180031be6  mov     r14d, eax
0x180031be9  test    eax, eax
0x180031beb  js      loc_180031E63
0x180031bf1  mov     [rbp+57h+pv], r12
0x180031bf5  mov     r15, r12
0x180031bf8  mov     rbx, r12
0x180031bfb  mov     [rbp+57h+var_68], rbx
0x180031bff  cmp     dword ptr [rbp+57h+var_7C], 3
0x180031c03  jnz     loc_180031E3E
0x180031c09  mov     dil, r12b
0x180031c0c  mov     [rbp+57h+var_80], r12b
0x180031c10  mov     eax, r12d
0x180031c13  mov     dword ptr [rbp+57h+var_7C+4], eax
0x180031c16  mov     rcx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName+8
0x180031c1d  mov     r8, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x180031c24  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers+8
0x180031c2b  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers
0x180031c32  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x180031c39  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180031c40  test    r14d, r14d
0x180031c43  js      loc_180031D46
0x180031c49  lea     rdi, [rax+rax*2]
0x180031c4d  add     rdi, rdi
0x180031c50  mov     rsi, qword ptr [rbp+57h+var_70]
0x180031c54  mov     eax, [rsi+rdi*8+10h]
0x180031c58  cmp     eax, 64h ; 'd'
0x180031c5b  jnz     loc_180031EBB
0x180031c61  mov     rax, [rsi+rdi*8]
0x180031c65  sub     rax, r13
0x180031c68  jnz     short loc_180031C72
0x180031c6a  mov     rax, [rsi+rdi*8+8]
0x180031c6f  sub     rax, r11
0x180031c72  test    rax, rax
0x180031c75  jnz     loc_180031D31
0x180031c7b  mov     r12, [rsi+rdi*8+28h]
0x180031c80  test    r12, r12
0x180031c83  jz      loc_180031D2E
0x180031c89  cmp     dword ptr [rsi+rdi*8+20h], 2012h
0x180031c91  jnz     loc_180031D2E
0x180031c97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031c9b  inc     rdi
0x180031c9e  cmp     [r12+rdi*2], ax
0x180031ca3  jnz     short loc_180031C9B
0x180031ca5  mov     rbx, rax
0x180031ca8  mov     [rbp+57h+var_68], rax
0x180031cac  lea     rsi, [rdi+1]
0x180031cb0  cmp     rsi, rdi
0x180031cb3  jb      loc_180031EB0
0x180031cb9  mov     [rbp+57h+var_68], rax
0x180031cbd  mov     eax, 2
0x180031cc2  mul     rsi
0x180031cc5  test    rdx, rdx
0x180031cc8  jnz     loc_180031EB0
0x180031cce  mov     rcx, rax; cb
0x180031cd1  call    cs:__imp_CoTaskMemAlloc
0x180031cd7  mov     rbx, rax
0x180031cda  mov     [rbp+57h+var_68], rax
0x180031cde  neg     rax
0x180031ce1  sbb     r14d, r14d
0x180031ce4  not     r14d
0x180031ce7  and     r14d, 8007000Eh
0x180031cee  test    rbx, rbx
0x180031cf1  jz      short loc_180031D04
0x180031cf3  mov     r9, rdi; unsigned __int64
0x180031cf6  mov     r8, r12; unsigned __int16 *
0x180031cf9  mov     rdx, rsi; unsigned __int64
0x180031cfc  mov     rcx, rbx; unsigned __int16 *
0x180031cff  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180031d04  mov     rcx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName+8
0x180031d0b  mov     r8, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x180031d12  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers+8
0x180031d19  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers
0x180031d20  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x180031d27  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180031d2e  xor     r12d, r12d
0x180031d31  mov     dil, [rbp+57h+var_80]
0x180031d35  mov     eax, dword ptr [rbp+57h+var_7C+4]
0x180031d38  inc     eax
0x180031d3a  mov     dword ptr [rbp+57h+var_7C+4], eax
0x180031d3d  cmp     eax, dword ptr [rbp+57h+var_7C]
0x180031d40  jb      loc_180031C40
0x180031d46  mov     rsi, [rbp+57h+pv]
0x180031d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d51  lea     rax, WPP_GLOBAL_Control
0x180031d58  cmp     rcx, rax
0x180031d5b  mov     r13, [rbp+57h+var_60]
0x180031d5f  jz      short loc_180031D83
0x180031d61  test    byte ptr [rcx+1Ch], 1
0x180031d65  jz      short loc_180031D83
0x180031d67  mov     eax, dword ptr [rbp+57h+pv+4]
0x180031d6a  mov     [rsp+0C0h+var_90], eax
0x180031d6e  mov     dword ptr [rsp+0C0h+var_98], esi
0x180031d72  mov     [rsp+0C0h+var_A0], r15
0x180031d77  mov     r9, rbx
0x180031d7a  mov     rcx, [rcx+10h]
0x180031d7e  call    WPP_SF_SSLL
0x180031d83  test    r14d, r14d
0x180031d86  js      loc_180031E37
0x180031d8c  test    rbx, rbx
0x180031d8f  jz      loc_180031E37
0x180031d95  test    r15, r15
0x180031d98  jz      loc_180031E37
0x180031d9e  test    dil, dil
0x180031da1  jz      loc_180031E37
0x180031da7  mov     [rbp+57h+pv], r12
0x180031dab  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180031daf  mov     rcx, rbx; unsigned __int16 *
0x180031db2  call    ?_InstalledFullNameFromFamilyName@@YAJPEBGPEAPEAG@Z; _InstalledFullNameFromFamilyName(ushort const *,ushort * *)
0x180031db7  mov     r14d, eax
0x180031dba  mov     rdi, [rbp+57h+pv]
0x180031dbe  test    eax, eax
0x180031dc0  js      short loc_180031E29
0x180031dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dc9  lea     rax, WPP_GLOBAL_Control
0x180031dd0  cmp     rcx, rax
0x180031dd3  jz      short loc_180031DF8
0x180031dd5  test    byte ptr [rcx+1Ch], 1
0x180031dd9  jz      short loc_180031DF8
0x180031ddb  mov     edx, 10h
0x180031de0  mov     [rsp+0C0h+var_A0], rbx
0x180031de5  mov     r9, rdi
0x180031de8  lea     r8, WPP_d57ca44452473f5574b7c550b191f620_Traceguids
0x180031def  mov     rcx, [rcx+10h]
0x180031df3  call    WPP_SF_SS
0x180031df8  mov     r9, r13; unsigned __int16 *
0x180031dfb  mov     r8, r15; unsigned __int16 *
0x180031dfe  mov     rdx, rdi; unsigned __int16 *
0x180031e01  mov     rcx, rsi; struct _WNF_STATE_NAME
0x180031e04  call    ?_RegisterEvents@@YAJU_WNF_STATE_NAME@@PEAG1PEBG@Z; _RegisterEvents(_WNF_STATE_NAME,ushort *,ushort *,ushort const *)
0x180031e09  mov     r14d, eax
0x180031e0c  test    eax, eax
0x180031e0e  jns     short loc_180031E29
0x180031e10  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 10h
0x180031e17  jz      short loc_180031E29
0x180031e19  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180031e1d  mov     r9, rdi
0x180031e20  mov     r8, r13
0x180031e23  call    McTemplateU0zzq_EventWriteTransfer
0x180031e28  nop
0x180031e29  test    rdi, rdi
0x180031e2c  jz      short loc_180031E37
0x180031e2e  mov     rcx, rdi; pv
0x180031e31  call    cs:__imp_CoTaskMemFree
0x180031e37  lea     rdi, WPP_GLOBAL_Control
0x180031e3e  mov     rcx, r15; pv
0x180031e41  call    cs:__imp_CoTaskMemFree
0x180031e47  mov     rdx, qword ptr [rbp+57h+var_70]
0x180031e4b  mov     ecx, dword ptr [rbp+57h+var_7C]
0x180031e4e  call    cs:__imp_DevFreeObjectProperties
0x180031e54  nop
0x180031e55  test    rbx, rbx
0x180031e58  jz      short loc_180031E63
0x180031e5a  mov     rcx, rbx; pv
0x180031e5d  call    cs:__imp_CoTaskMemFree
0x180031e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e6a  cmp     rcx, rdi
0x180031e6d  jz      short loc_180031E8D
0x180031e6f  test    byte ptr [rcx+1Ch], 1
0x180031e73  jz      short loc_180031E8D
0x180031e75  mov     edx, 11h
0x180031e7a  mov     r9d, r14d
0x180031e7d  lea     r8, WPP_d57ca44452473f5574b7c550b191f620_Traceguids
0x180031e84  mov     rcx, [rcx+10h]
0x180031e88  call    WPP_SF_d
0x180031e8d  mov     eax, r14d
0x180031e90  mov     rcx, [rbp+57h+var_48]
0x180031e94  xor     rcx, rsp; StackCookie
0x180031e97  call    __security_check_cookie
0x180031e9c  add     rsp, 88h
0x180031ea3  pop     r15
0x180031ea5  pop     r14
0x180031ea7  pop     r13
0x180031ea9  pop     r12
0x180031eab  pop     rdi
0x180031eac  pop     rsi
0x180031ead  pop     rbx
0x180031eae  pop     rbp
0x180031eaf  retn
0x180031eb0  mov     r14d, 80070216h
0x180031eb6  jmp     loc_180031D2E
0x180031ebb  cmp     eax, 6Dh ; 'm'
0x180031ebe  jnz     loc_180031F60
0x180031ec4  mov     rax, [rsi+rdi*8]
0x180031ec8  sub     rax, r10
0x180031ecb  jnz     short loc_180031ED5
0x180031ecd  mov     rax, [rsi+rdi*8+8]
0x180031ed2  sub     rax, r9
0x180031ed5  test    rax, rax
0x180031ed8  jnz     loc_180031D31
0x180031ede  cmp     [rsi+rdi*8+28h], r12
0x180031ee3  jz      loc_180031D31
0x180031ee9  cmp     dword ptr [rsi+rdi*8+20h], 2012h
0x180031ef1  jnz     loc_180031D31
0x180031ef7  mov     ecx, [rsi+rdi*8+24h]; cb
0x180031efb  call    cs:__imp_CoTaskMemAlloc
0x180031f01  mov     r15, rax
0x180031f04  test    rax, rax
0x180031f07  jz      short loc_180031F2B
0x180031f09  mov     edx, [rsi+rdi*8+24h]; DestinationSize
0x180031f0d  mov     r9d, edx; SourceSize
0x180031f10  mov     r8, [rsi+rdi*8+28h]; Source
0x180031f15  mov     rcx, rax; Destination
0x180031f18  call    memcpy_s
0x180031f1d  neg     eax
0x180031f1f  sbb     r14d, r14d
0x180031f22  and     r14d, 80004005h
0x180031f29  jmp     short loc_180031F31
0x180031f2b  mov     r14d, 8007000Eh
0x180031f31  mov     rcx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName+8
0x180031f38  mov     r8, qword ptr cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x180031f3f  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers+8
0x180031f46  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_DCA_DeviceNotificationHandlers
0x180031f4d  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x180031f54  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180031f5b  jmp     loc_180031D31
0x180031f60  cmp     eax, 6Ch ; 'l'
0x180031f63  jnz     loc_180031D31
0x180031f69  mov     rax, [rsi+rdi*8]
0x180031f6d  sub     rax, r8
0x180031f70  jnz     short loc_180031F7A
0x180031f72  mov     rax, [rsi+rdi*8+8]
0x180031f77  sub     rax, rcx
0x180031f7a  test    rax, rax
0x180031f7d  jnz     loc_180031D31
0x180031f83  cmp     [rsi+rdi*8+28h], r12
0x180031f88  jz      loc_180031D31
0x180031f8e  cmp     dword ptr [rsi+rdi*8+20h], 1003h
0x180031f96  jnz     loc_180031D31
0x180031f9c  mov     dil, 1
  ... truncated ...
```
