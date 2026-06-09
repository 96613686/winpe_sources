# MbbAdapterSetOptionalServiceSupport(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x140004c70`
- end: `0x14000501f`
- name: `?MbbAdapterSetOptionalServiceSupport@@YAXPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `943`
- prototype: `void __fastcall(struct _MINIPORT_ADAPTER_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x14000bb48`

## callees

- `0x140004c70`
- `0x14001eca4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004e40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005008`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004f89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005008`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ca2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ec3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004faf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ca2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004ec3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004faf`

## pseudocode

```c
void __fastcall MbbAdapterSetOptionalServiceSupport(struct _MINIPORT_ADAPTER_CONTEXT *a1)
{
  KIRQL *v2; // rsi
  struct _MBB_DS *DeviceService; // rdi
  KIRQL v4; // al
  KIRQL v5; // r9
  __int64 v6; // r8
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  int v19; // ecx
  unsigned int v20; // eax
  struct _MBB_DS *v21; // rdi
  KIRQL v22; // al
  __int64 v23; // r8
  struct _MBB_DS *v24; // rdi
  KIRQL v25; // al
  __int64 v26; // r9
  KIRQL v27; // al
  KIRQL v28; // al
  struct _MBB_DS *v29; // rdi
  KIRQL v30; // al
  __int64 v31; // r9

  v2 = (KIRQL *)a1 + 8;
  DeviceService = MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_BASIC_CONNECT_EXTENSIONS);
  if ( DeviceService )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    *v2 = v4;
    v5 = v4;
    if ( *((_DWORD *)DeviceService + 6) )
    {
      v6 = 0;
      while ( 1 )
      {
        v7 = *(_DWORD *)(*((_QWORD *)DeviceService + 4) + 4 * v6);
        if ( v7 <= 0xB )
        {
          if ( v7 == 11 )
          {
            *((_DWORD *)a1 + 272) |= 0x20000u;
          }
          else
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 3;
                  if ( v11 )
                  {
                    v12 = v11 - 1;
                    if ( v12 )
                    {
                      v13 = v12 - 2;
                      if ( v13 )
                      {
                        if ( v13 == 1 )
                          *((_DWORD *)a1 + 272) |= 0x10000u;
                      }
                      else
                      {
                        *((_DWORD *)a1 + 272) |= 0x8000u;
                      }
                    }
                    else
                    {
                      *((_DWORD *)a1 + 272) |= 0x1000u;
                    }
                  }
                  else
                  {
                    *((_DWORD *)a1 + 272) |= 0x4000u;
                  }
                }
                else
                {
                  *((_DWORD *)a1 + 272) |= 0x800u;
                }
              }
              else
              {
                *((_DWORD *)a1 + 272) |= 0x200u;
              }
            }
            else
            {
              *((_DWORD *)a1 + 272) |= 0x100u;
            }
          }
          goto LABEL_34;
        }
        v14 = v7 - 13;
        if ( !v14 )
        {
          *((_DWORD *)a1 + 272) |= 0x40000u;
          goto LABEL_34;
        }
        v15 = v14 - 3;
        if ( !v15 )
        {
          v19 = *((_WORD *)a1 + 41) >= 0x300u ? 0x2000000 : 0;
          v20 = *((_DWORD *)a1 + 272) & 0xFDFFFFFF;
          goto LABEL_31;
        }
        v16 = v15 - 1;
        if ( !v16 )
        {
          v19 = *((_WORD *)a1 + 41) >= 0x300u ? 0x4000000 : 0;
          v20 = *((_DWORD *)a1 + 272) & 0xFBFFFFFF;
          goto LABEL_31;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v19 = *((_WORD *)a1 + 41) >= 0x300u ? 0x400000 : 0;
          v20 = *((_DWORD *)a1 + 272) & 0xFFBFFFFF;
          goto LABEL_31;
        }
        v18 = v17 - 1;
        if ( !v18 )
          break;
        if ( v18 == 1 )
        {
          v19 = *((_WORD *)a1 + 41) >= 0x400u ? 0x1000000 : 0;
          v20 = *((_DWORD *)a1 + 272) & 0xFEFFFFFF;
LABEL_31:
          *((_DWORD *)a1 + 272) = v20 | v19;
        }
LABEL_34:
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= *((_DWORD *)DeviceService + 6) )
          goto LABEL_35;
      }
      v19 = *((_WORD *)a1 + 41) >= 0x300u ? 0x800000 : 0;
      v20 = *((_DWORD *)a1 + 272) & 0xFF7FFFFF;
      goto LABEL_31;
    }
LABEL_35:
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v5);
  }
  v21 = MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_SARCONTROL);
  if ( v21 )
  {
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    v23 = 0;
    for ( *v2 = v22; (unsigned int)v23 < *((_DWORD *)v21 + 6); v23 = (unsigned int)(v23 + 1) )
    {
      if ( *(_DWORD *)(*((_QWORD *)v21 + 4) + 4 * v23) == 1 )
        *((_DWORD *)a1 + 272) |= 0x400u;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v22);
  }
  v24 = MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_UICC_LOW_LEVEL);
  if ( v24 )
  {
    v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    v26 = 0;
    for ( *v2 = v25; (unsigned int)v26 < *((_DWORD *)v24 + 6); v26 = (unsigned int)(v26 + 1) )
    {
      if ( *(_DWORD *)(*((_QWORD *)v24 + 4) + 4 * v26) == 1 )
      {
        *((_DWORD *)a1 + 272) |= 0x2000u;
      }
      else if ( *(_DWORD *)(*((_QWORD *)v24 + 4) + 4 * v26) != 7 )
      {
        continue;
      }
      *((_DWORD *)a1 + 272) |= 0x100000u;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v25);
  }
  if ( MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_DSS) )
  {
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    *((_DWORD *)a1 + 272) |= 0x200000u;
    *v2 = v27;
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v27);
  }
  if ( MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_USSD) )
  {
    v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    *((_DWORD *)a1 + 272) |= 2u;
    *v2 = v28;
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v28);
  }
  v29 = MbbUtilFindDeviceService(a1, (struct _GUID *)&MBB_UUID_AUTH);
  if ( v29 )
  {
    v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1);
    v31 = 0;
    for ( *((_BYTE *)a1 + 8) = v30; (unsigned int)v31 < *((_DWORD *)v29 + 6); v31 = (unsigned int)(v31 + 1) )
    {
      switch ( *(_DWORD *)(*((_QWORD *)v29 + 4) + 4 * v31) )
      {
        case 1:
          *((_DWORD *)a1 + 272) |= 8u;
          break;
        case 2:
          *((_DWORD *)a1 + 272) |= 0x10u;
          break;
        case 3:
          *((_DWORD *)a1 + 272) |= 4u;
          break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1, v30);
  }
}

```

## disassembly

```asm
0x140004c70  push    rbx
0x140004c72  push    rsi
0x140004c73  push    rdi
0x140004c74  push    r14
0x140004c76  sub     rsp, 28h
0x140004c7a  lea     rdx, MBB_UUID_BASIC_CONNECT_EXTENSIONS; struct _GUID *
0x140004c81  mov     rbx, rcx
0x140004c84  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004c89  lea     rsi, [rbx+8]
0x140004c8d  mov     rdi, rax
0x140004c90  mov     r14d, 400h
0x140004c96  test    rax, rax
0x140004c99  jz      loc_140004E4C
0x140004c9f  mov     rcx, rbx; SpinLock
0x140004ca2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004ca9  nop     dword ptr [rax+rax+00h]
0x140004cae  mov     [rsi], al
0x140004cb0  mov     r9b, al
0x140004cb3  cmp     dword ptr [rdi+18h], 0
0x140004cb7  jbe     loc_140004E3A
0x140004cbd  xor     r8d, r8d
0x140004cc0  mov     r10d, 300h
0x140004cc6  mov     rax, [rdi+20h]
0x140004cca  mov     edx, [rax+r8*4]
0x140004cce  cmp     edx, 0Bh
0x140004cd1  ja      loc_140004D6C
0x140004cd7  jz      loc_140004D5F
0x140004cdd  sub     edx, 1
0x140004ce0  jz      short loc_140004D52
0x140004ce2  sub     edx, 1
0x140004ce5  jz      short loc_140004D45
0x140004ce7  sub     edx, 1
0x140004cea  jz      short loc_140004D38
0x140004cec  sub     edx, 3
0x140004cef  jz      short loc_140004D2B
0x140004cf1  sub     edx, 1
0x140004cf4  jz      short loc_140004D1E
0x140004cf6  sub     edx, 2
0x140004cf9  jz      short loc_140004D11
0x140004cfb  cmp     edx, 1
0x140004cfe  jnz     loc_140004E2D
0x140004d04  bts     dword ptr [rbx+440h], 10h
0x140004d0c  jmp     loc_140004E2D
0x140004d11  bts     dword ptr [rbx+440h], 0Fh
0x140004d19  jmp     loc_140004E2D
0x140004d1e  bts     dword ptr [rbx+440h], 0Ch
0x140004d26  jmp     loc_140004E2D
0x140004d2b  bts     dword ptr [rbx+440h], 0Eh
0x140004d33  jmp     loc_140004E2D
0x140004d38  bts     dword ptr [rbx+440h], 0Bh
0x140004d40  jmp     loc_140004E2D
0x140004d45  bts     dword ptr [rbx+440h], 9
0x140004d4d  jmp     loc_140004E2D
0x140004d52  bts     dword ptr [rbx+440h], 8
0x140004d5a  jmp     loc_140004E2D
0x140004d5f  bts     dword ptr [rbx+440h], 11h
0x140004d67  jmp     loc_140004E2D
0x140004d6c  sub     edx, 0Dh
0x140004d6f  jz      loc_140004E25
0x140004d75  sub     edx, 3
0x140004d78  jz      loc_140004E0A
0x140004d7e  sub     edx, 1
0x140004d81  jz      short loc_140004DE7
0x140004d83  sub     edx, 1
0x140004d86  jz      short loc_140004DCC
0x140004d88  sub     edx, 1
0x140004d8b  jz      short loc_140004DB1
0x140004d8d  cmp     edx, 1
0x140004d90  jnz     loc_140004E2D
0x140004d96  cmp     [rbx+52h], r14w
0x140004d9b  mov     eax, [rbx+440h]
0x140004da1  sbb     ecx, ecx
0x140004da3  not     ecx
0x140004da5  and     ecx, 1000000h
0x140004dab  btr     eax, 18h
0x140004daf  jmp     short loc_140004E00
0x140004db1  cmp     [rbx+52h], r10w
0x140004db6  mov     eax, [rbx+440h]
0x140004dbc  sbb     ecx, ecx
0x140004dbe  not     ecx
0x140004dc0  and     ecx, 800000h
0x140004dc6  btr     eax, 17h
0x140004dca  jmp     short loc_140004E00
0x140004dcc  cmp     [rbx+52h], r10w
0x140004dd1  mov     eax, [rbx+440h]
0x140004dd7  sbb     ecx, ecx
0x140004dd9  not     ecx
0x140004ddb  and     ecx, 400000h
0x140004de1  btr     eax, 16h
0x140004de5  jmp     short loc_140004E00
0x140004de7  cmp     [rbx+52h], r10w
0x140004dec  mov     eax, [rbx+440h]
0x140004df2  sbb     ecx, ecx
0x140004df4  not     ecx
0x140004df6  and     ecx, 4000000h
0x140004dfc  btr     eax, 1Ah
0x140004e00  or      ecx, eax
0x140004e02  mov     [rbx+440h], ecx
0x140004e08  jmp     short loc_140004E2D
0x140004e0a  cmp     [rbx+52h], r10w
0x140004e0f  mov     eax, [rbx+440h]
0x140004e15  sbb     ecx, ecx
0x140004e17  not     ecx
0x140004e19  and     ecx, 2000000h
0x140004e1f  btr     eax, 19h
0x140004e23  jmp     short loc_140004E00
0x140004e25  bts     dword ptr [rbx+440h], 12h
0x140004e2d  inc     r8d
0x140004e30  cmp     r8d, [rdi+18h]
0x140004e34  jb      loc_140004CC6
0x140004e3a  mov     dl, r9b; NewIrql
0x140004e3d  mov     rcx, rbx; SpinLock
0x140004e40  call    cs:__imp_KeReleaseSpinLock
0x140004e47  nop     dword ptr [rax+rax+00h]
0x140004e4c  lea     rdx, MBB_UUID_SARCONTROL; struct _GUID *
0x140004e53  mov     rcx, rbx; struct _MINIPORT_ADAPTER_CONTEXT *
0x140004e56  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004e5b  mov     rdi, rax
0x140004e5e  test    rax, rax
0x140004e61  jz      short loc_140004EA9
0x140004e63  mov     rcx, rbx; SpinLock
0x140004e66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004e6d  nop     dword ptr [rax+rax+00h]
0x140004e72  xor     r8d, r8d
0x140004e75  mov     [rsi], al
0x140004e77  cmp     [rdi+18h], r8d
0x140004e7b  jbe     short loc_140004E98
0x140004e7d  mov     rcx, [rdi+20h]
0x140004e81  cmp     dword ptr [rcx+r8*4], 1
0x140004e86  jnz     short loc_140004E8F
0x140004e88  or      [rbx+440h], r14d
0x140004e8f  inc     r8d
0x140004e92  cmp     r8d, [rdi+18h]
0x140004e96  jb      short loc_140004E7D
0x140004e98  mov     dl, al; NewIrql
0x140004e9a  mov     rcx, rbx; SpinLock
0x140004e9d  call    cs:__imp_KeReleaseSpinLock
0x140004ea4  nop     dword ptr [rax+rax+00h]
0x140004ea9  lea     rdx, MBB_UUID_UICC_LOW_LEVEL; struct _GUID *
0x140004eb0  mov     rcx, rbx; struct _MINIPORT_ADAPTER_CONTEXT *
0x140004eb3  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004eb8  mov     rdi, rax
0x140004ebb  test    rax, rax
0x140004ebe  jz      short loc_140004F1A
0x140004ec0  mov     rcx, rbx; SpinLock
0x140004ec3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004eca  nop     dword ptr [rax+rax+00h]
0x140004ecf  xor     r9d, r9d
0x140004ed2  mov     [rsi], al
0x140004ed4  cmp     [rdi+18h], r9d
0x140004ed8  jbe     short loc_140004F09
0x140004eda  mov     rcx, [rdi+20h]
0x140004ede  mov     r8d, [rcx+r9*4]
0x140004ee2  sub     r8d, 1
0x140004ee6  jz      short loc_140004EF0
0x140004ee8  cmp     r8d, 6
0x140004eec  jz      short loc_140004EF8
0x140004eee  jmp     short loc_140004F00
0x140004ef0  bts     dword ptr [rbx+440h], 0Dh
0x140004ef8  bts     dword ptr [rbx+440h], 14h
0x140004f00  inc     r9d
0x140004f03  cmp     r9d, [rdi+18h]
0x140004f07  jb      short loc_140004EDA
0x140004f09  mov     dl, al; NewIrql
0x140004f0b  mov     rcx, rbx; SpinLock
0x140004f0e  call    cs:__imp_KeReleaseSpinLock
0x140004f15  nop     dword ptr [rax+rax+00h]
0x140004f1a  lea     rdx, MBB_UUID_DSS; struct _GUID *
0x140004f21  mov     rcx, rbx; struct _MINIPORT_ADAPTER_CONTEXT *
0x140004f24  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004f29  test    rax, rax
0x140004f2c  jz      short loc_140004F58
0x140004f2e  mov     rcx, rbx; SpinLock
0x140004f31  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004f38  nop     dword ptr [rax+rax+00h]
0x140004f3d  bts     dword ptr [rbx+440h], 15h
0x140004f45  mov     rcx, rbx; SpinLock
0x140004f48  mov     dl, al; NewIrql
0x140004f4a  mov     [rsi], al
0x140004f4c  call    cs:__imp_KeReleaseSpinLock
0x140004f53  nop     dword ptr [rax+rax+00h]
0x140004f58  lea     rdx, MBB_UUID_USSD; struct _GUID *
0x140004f5f  mov     rcx, rbx; struct _MINIPORT_ADAPTER_CONTEXT *
0x140004f62  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004f67  test    rax, rax
0x140004f6a  jz      short loc_140004F95
0x140004f6c  mov     rcx, rbx; SpinLock
0x140004f6f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004f76  nop     dword ptr [rax+rax+00h]
0x140004f7b  or      dword ptr [rbx+440h], 2
0x140004f82  mov     rcx, rbx; SpinLock
0x140004f85  mov     dl, al; NewIrql
0x140004f87  mov     [rsi], al
0x140004f89  call    cs:__imp_KeReleaseSpinLock
0x140004f90  nop     dword ptr [rax+rax+00h]
0x140004f95  lea     rdx, MBB_UUID_AUTH; struct _GUID *
0x140004f9c  mov     rcx, rbx; struct _MINIPORT_ADAPTER_CONTEXT *
0x140004f9f  call    ?MbbUtilFindDeviceService@@YAPEAU_MBB_DS@@PEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_GUID@@@Z; MbbUtilFindDeviceService(_MINIPORT_ADAPTER_CONTEXT *,_GUID *)
0x140004fa4  mov     rdi, rax
0x140004fa7  test    rax, rax
0x140004faa  jz      short loc_140005014
0x140004fac  mov     rcx, rbx; SpinLock
0x140004faf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004fb6  nop     dword ptr [rax+rax+00h]
0x140004fbb  xor     r9d, r9d
0x140004fbe  mov     [rbx+8], al
0x140004fc1  cmp     [rdi+18h], r9d
0x140004fc5  jbe     short loc_140005003
0x140004fc7  mov     rcx, [rdi+20h]
0x140004fcb  mov     r8d, [rcx+r9*4]
0x140004fcf  sub     r8d, 1
0x140004fd3  jz      short loc_140004FF3
0x140004fd5  sub     r8d, 1
0x140004fd9  jz      short loc_140004FEA
0x140004fdb  cmp     r8d, 1
0x140004fdf  jnz     short loc_140004FFA
0x140004fe1  or      dword ptr [rbx+440h], 4
0x140004fe8  jmp     short loc_140004FFA
0x140004fea  or      dword ptr [rbx+440h], 10h
0x140004ff1  jmp     short loc_140004FFA
0x140004ff3  or      dword ptr [rbx+440h], 8
0x140004ffa  inc     r9d
0x140004ffd  cmp     r9d, [rdi+18h]
0x140005001  jb      short loc_140004FC7
0x140005003  mov     dl, al; NewIrql
0x140005005  mov     rcx, rbx; SpinLock
0x140005008  call    cs:__imp_KeReleaseSpinLock
0x14000500f  nop     dword ptr [rax+rax+00h]
0x140005014  add     rsp, 28h
0x140005018  pop     r14
0x14000501a  pop     rdi
0x14000501b  pop     rsi
0x14000501c  pop     rbx
0x14000501d  retn
```
