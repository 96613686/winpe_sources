# RootHub_UcxEvtInterruptTransfer

- ea: `0x14001f340`
- end: `0x14001f81b`
- name: `RootHub_UcxEvtInterruptTransfer`
- size: `1243`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140019d6c`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001d154`
- `0x14001f340`
- `0x14001f830`
- `0x14001fb30`
- `0x14003b038`
- `0x14003b7d0`
- `0x140046070`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001f66d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001f66d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001f64c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001f64c`

## string_xrefs

- `0x14001f73b`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtInterruptTransfer(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  __int16 v5; // ax
  __int64 v6; // r15
  void *v7; // r13
  size_t v8; // rbx
  int v9; // edx
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  unsigned int i; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdi
  char v15; // cl
  unsigned int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // r8d
  unsigned __int64 v19; // rdx
  unsigned int Ulong; // eax
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  int v25; // r9d
  int v26; // edx
  int v27; // r8d
  int v28; // r9d
  int v29; // edx
  char v30; // [rsp+30h] [rbp-78h]
  __int128 v31; // [rsp+40h] [rbp-68h] BYREF
  __int128 v32; // [rsp+50h] [rbp-58h]
  __int64 v33; // [rsp+60h] [rbp-48h]

  v33 = 0;
  v31 = 0;
  v32 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  v4 = *(_QWORD *)(*(_QWORD *)(v3 + 8) + 88LL);
  v31 = 0;
  v33 = 0;
  v32 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v31) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_4;
    }
    v5 = -1;
  }
  else
  {
    v5 = 40;
  }
  LOWORD(v31) = v5;
LABEL_4:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v31);
  v6 = *((_QWORD *)&v31 + 1);
  v7 = *(void **)(*((_QWORD *)&v31 + 1) + 40LL);
  v8 = *(unsigned int *)(*((_QWORD *)&v31 + 1) + 36LL);
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 8) + 1041LL) && KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v26, v27, v28);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  if ( (unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(v3 + 8)) )
  {
    if ( *(_BYTE *)(v3 + 57) )
    {
      Controller_UpdateIdleTimeoutOnRootHubPDOD0Entry(*(_QWORD *)(v3 + 8));
      *(_BYTE *)(v3 + 57) = 0;
    }
    if ( (_DWORD)v8 )
    {
      memset(v7, 0, v8);
      if ( (unsigned int)v8 > 0x20 )
        v10 = 255;
      else
        v10 = 8 * v8 - 1;
      v11 = *(_DWORD *)(v3 + 16);
      if ( v10 <= v11 )
        v11 = v10;
      for ( i = 1; ; ++i )
      {
        while ( 1 )
        {
          if ( i > v11 )
            goto LABEL_28;
          v13 = i - 1;
          v14 = 120 * v13;
          v15 = *(_BYTE *)(120 * v13 + *(_QWORD *)(v3 + 48) + 13);
          if ( v15 == 2 )
            break;
          if ( v15 == 3 )
          {
            Ulong = XilRegister_ReadUlong(v4, *(_QWORD *)(v3 + 40) + 16 * v13);
            v17 = Ulong;
            if ( Ulong == -1 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v25 = 192;
                goto LABEL_34;
              }
LABEL_31:
              LOBYTE(v17) = 1;
              Controller_SetControllerGone(*(_QWORD *)(v3 + 8), v17);
              v23 = 3221225486LL;
              *(_DWORD *)(v6 + 4) = -1073713152;
              return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                       WdfDriverGlobals,
                       a2,
                       v23);
            }
            if ( (Ulong & 0xFA0000) != 0
              || ((v21 = *(_QWORD *)(v3 + 48), v22 = Ulong & 0x1E0, v22 == 320)
               || v22 == 192 && *(_DWORD *)(v14 + v21 + 108))
              && _InterlockedCompareExchange((volatile signed __int32 *)(v14 + v21 + 100), 0, 1) == 1 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v30 = v17;
                LOBYTE(v17) = 4;
                WPP_RECORDER_SF_dD(
                  *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                  v17,
                  11,
                  193,
                  (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                  i,
                  v30);
              }
              if ( (unsigned __int8)RootHub_HideInvalidDebugPortStatusAndChange(v3, i) )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v29) = 4;
                  WPP_RECORDER_SF_d(
                    *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                    v29,
                    11,
                    194,
                    (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                    i);
                }
              }
              else
              {
                *((_BYTE *)v7 + ((unsigned __int64)i >> 3)) |= 1 << (i & 7);
              }
            }
          }
LABEL_27:
          ++i;
        }
        v16 = XilRegister_ReadUlong(v4, *(_QWORD *)(v3 + 40) + 16 * v13);
        if ( v16 == -1 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v25 = 190;
LABEL_34:
            LOBYTE(v17) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
              v17,
              11,
              v25,
              (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
          }
          goto LABEL_31;
        }
        v18 = v16 & 0xFFBFFFFF;
        if ( (v16 & 0x1E0) != 0x1E0 )
          v18 = v16;
        if ( (v18 & 0x760000) == 0 )
          goto LABEL_27;
        v19 = (unsigned __int64)i >> 3;
        *((_BYTE *)v7 + v19) |= 1 << (i & 7);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_27;
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_dD(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v19,
          11,
          191,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
          i,
          v18);
      }
    }
LABEL_28:
    *(_DWORD *)(v6 + 4) = 0;
    v23 = 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v9,
        11,
        189,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    *(_DWORD *)(v6 + 4) = -1073713152;
    v23 = 3221225486LL;
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v23);
}

```

## disassembly

```asm
0x14001f340  push    rbx
0x14001f342  push    rsi
0x14001f343  push    rdi
0x14001f344  push    r12
0x14001f346  push    r13
0x14001f348  push    r14
0x14001f34a  push    r15
0x14001f34c  sub     rsp, 70h
0x14001f350  mov     rax, cs:__security_cookie
0x14001f357  xor     rax, rsp
0x14001f35a  mov     [rsp+0A8h+var_40], rax
0x14001f35f  mov     r8, cs:off_14006C130
0x14001f366  xor     eax, eax
0x14001f368  mov     [rsp+0A8h+var_48], rax
0x14001f36d  xorps   xmm0, xmm0
0x14001f370  mov     rax, cs:WdfFunctions_01033
0x14001f377  mov     r12, rdx
0x14001f37a  movups  [rsp+0A8h+var_68], xmm0
0x14001f37f  mov     rdx, rcx
0x14001f382  mov     rcx, cs:WdfDriverGlobals
0x14001f389  movups  [rsp+0A8h+var_58], xmm0
0x14001f38e  mov     rax, [rax+650h]
0x14001f395  call    _guard_dispatch_icall
0x14001f39a  xorps   xmm0, xmm0
0x14001f39d  mov     rsi, rax
0x14001f3a0  mov     rcx, [rax+8]
0x14001f3a4  xor     eax, eax
0x14001f3a6  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14001f3ac  mov     r14, [rcx+58h]
0x14001f3b0  movups  [rsp+0A8h+var_68], xmm0
0x14001f3b5  mov     [rsp+0A8h+var_48], rax
0x14001f3ba  movups  [rsp+0A8h+var_58], xmm0
0x14001f3bf  jnz     loc_14001F709
0x14001f3c5  mov     eax, 28h ; '('
0x14001f3ca  mov     word ptr [rsp+0A8h+var_68], ax
0x14001f3cf  mov     rax, cs:WdfFunctions_01033
0x14001f3d6  lea     r8, [rsp+0A8h+var_68]
0x14001f3db  mov     rcx, cs:WdfDriverGlobals
0x14001f3e2  mov     rdx, r12
0x14001f3e5  mov     rax, [rax+850h]
0x14001f3ec  call    _guard_dispatch_icall
0x14001f3f1  mov     r15, qword ptr [rsp+0A8h+var_68+8]
0x14001f3f6  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001f3fd  mov     rax, [rsi+8]
0x14001f401  mov     r13, [r15+28h]
0x14001f405  cmp     byte ptr [rax+411h], 0
0x14001f40c  mov     ebx, [r15+24h]
0x14001f410  jnz     loc_14001F64C
0x14001f416  mov     rcx, [rsi+8]
0x14001f41a  call    Controller_IsControllerAccessible
0x14001f41f  test    al, al
0x14001f421  jz      loc_14001F687
0x14001f427  cmp     byte ptr [rsi+39h], 0
0x14001f42b  jnz     loc_14001F601
0x14001f431  mov     [rsp+0A8h+arg_10], rbp
0x14001f439  test    ebx, ebx
0x14001f43b  jz      loc_14001F584
0x14001f441  mov     r8, rbx; Size
0x14001f444  xor     edx, edx; Val
0x14001f446  mov     rcx, r13; void *
0x14001f449  call    memset
0x14001f44e  cmp     ebx, 20h ; ' '
0x14001f451  ja      loc_14001F795
0x14001f457  lea     ebx, ds:0FFFFFFFFFFFFFFFFh[rbx*8]
0x14001f45e  mov     ebp, [rsi+10h]
0x14001f461  cmp     ebx, ebp
0x14001f463  cmovbe  ebp, ebx
0x14001f466  mov     ebx, 1
0x14001f46b  nop     dword ptr [rax+rax+00h]
0x14001f470  cmp     ebx, ebp
0x14001f472  ja      loc_14001F584
0x14001f478  mov     rax, [rsi+30h]
0x14001f47c  lea     edx, [rbx-1]
0x14001f47f  imul    rdi, rdx, 78h ; 'x'
0x14001f483  movzx   ecx, byte ptr [rdi+rax+0Dh]
0x14001f488  cmp     cl, 2
0x14001f48b  jnz     loc_14001F533
0x14001f491  shl     rdx, 4
0x14001f495  mov     rcx, r14
0x14001f498  add     rdx, [rsi+28h]
0x14001f49c  call    XilRegister_ReadUlong
0x14001f4a1  cmp     eax, 0FFFFFFFFh
0x14001f4a4  jz      loc_14001F5D2
0x14001f4aa  mov     ecx, eax
0x14001f4ac  mov     r8d, eax
0x14001f4af  btr     r8d, 16h
0x14001f4b4  and     ecx, 1E0h
0x14001f4ba  cmp     ecx, 1E0h
0x14001f4c0  cmovnz  r8d, eax
0x14001f4c4  test    r8d, 760000h
0x14001f4cb  jz      loc_14001F57D
0x14001f4d1  mov     edx, ebx
0x14001f4d3  mov     eax, ebx
0x14001f4d5  shr     rdx, 3
0x14001f4d9  and     eax, 7
0x14001f4dc  movzx   ecx, byte ptr [rdx+r13]
0x14001f4e1  bts     ecx, eax
0x14001f4e4  mov     [rdx+r13], cl
0x14001f4e8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001f4ef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f4f6  jz      loc_14001F57D
0x14001f4fc  mov     rcx, [rsi+8]
0x14001f500  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001f507  mov     dword ptr [rsp+0A8h+var_78], r8d
0x14001f50c  mov     r9d, 0BFh
0x14001f512  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14001f516  mov     r8d, 0Bh
0x14001f51c  mov     dl, 4
0x14001f51e  mov     [rsp+0A8h+var_88], rax
0x14001f523  mov     rcx, [rcx+48h]
0x14001f527  call    WPP_RECORDER_SF_dD
0x14001f52c  inc     ebx
0x14001f52e  jmp     loc_14001F470
0x14001f533  cmp     cl, 3
0x14001f536  jnz     short loc_14001F57D
0x14001f538  shl     rdx, 4
0x14001f53c  mov     rcx, r14
0x14001f53f  add     rdx, [rsi+28h]
0x14001f543  call    XilRegister_ReadUlong
0x14001f548  mov     edx, eax
0x14001f54a  cmp     eax, 0FFFFFFFFh
0x14001f54d  jz      loc_14001F613
0x14001f553  test    eax, 0FA0000h
0x14001f558  jnz     loc_14001F6C7
0x14001f55e  mov     r8, [rsi+30h]
0x14001f562  and     eax, 1E0h
0x14001f567  cmp     eax, 140h
0x14001f56c  jz      loc_14001F6B3
0x14001f572  cmp     eax, 0C0h
0x14001f577  jz      loc_14001F6A7
0x14001f57d  inc     ebx
0x14001f57f  jmp     loc_14001F470
0x14001f584  mov     dword ptr [r15+4], 0
0x14001f58c  xor     r8d, r8d
0x14001f58f  mov     rbp, [rsp+0A8h+arg_10]
0x14001f597  mov     rax, cs:WdfFunctions_01033
0x14001f59e  mov     rdx, r12
0x14001f5a1  mov     rcx, cs:WdfDriverGlobals
0x14001f5a8  mov     rax, [rax+838h]
0x14001f5af  call    _guard_dispatch_icall
0x14001f5b4  mov     rcx, [rsp+0A8h+var_40]
0x14001f5b9  xor     rcx, rsp; StackCookie
0x14001f5bc  call    __security_check_cookie
0x14001f5c1  add     rsp, 70h
0x14001f5c5  pop     r15
0x14001f5c7  pop     r14
0x14001f5c9  pop     r13
0x14001f5cb  pop     r12
0x14001f5cd  pop     rdi
0x14001f5ce  pop     rsi
0x14001f5cf  pop     rbx
0x14001f5d0  retn
0x14001f5d2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001f5d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f5e0  jnz     loc_14001F810
0x14001f5e6  mov     rcx, [rsi+8]
0x14001f5ea  mov     dl, 1
0x14001f5ec  call    Controller_SetControllerGone
0x14001f5f1  mov     r8d, 0C000000Eh
0x14001f5f7  mov     dword ptr [r15+4], 0C0007000h
0x14001f5ff  jmp     short loc_14001F58F
0x14001f601  mov     rcx, [rsi+8]
0x14001f605  call    Controller_UpdateIdleTimeoutOnRootHubPDOD0Entry
0x14001f60a  mov     byte ptr [rsi+39h], 0
0x14001f60e  jmp     loc_14001F431
0x14001f613  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001f61a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f621  jz      short loc_14001F5E6
0x14001f623  mov     r9d, 0C0h
0x14001f629  mov     rcx, [rsi+8]
0x14001f62d  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001f634  mov     r8d, 0Bh
0x14001f63a  mov     [rsp+0A8h+var_88], rax
0x14001f63f  mov     dl, 2
0x14001f641  mov     rcx, [rcx+48h]
0x14001f645  call    WPP_RECORDER_SF_
0x14001f64a  jmp     short loc_14001F5E6
0x14001f64c  call    cs:__imp_KeGetCurrentIrql
0x14001f653  nop     dword ptr [rax+rax+00h]
0x14001f658  test    al, al
0x14001f65a  jz      loc_14001F416
0x14001f660  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001f667  jnz     loc_14001F734
0x14001f66d  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14001f674  nop     dword ptr [rax+rax+00h]
0x14001f679  test    al, al
0x14001f67b  jnz     loc_14001F416
0x14001f681  int     3; Trap to Debugger
0x14001f682  jmp     loc_14001F416
0x14001f687  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001f68e  jnz     loc_14001F769
0x14001f694  mov     dword ptr [r15+4], 0C0007000h
0x14001f69c  mov     r8d, 0C000000Eh
0x14001f6a2  jmp     loc_14001F597
0x14001f6a7  cmp     dword ptr [rdi+r8+6Ch], 0
0x14001f6ad  jz      loc_14001F57D
0x14001f6b3  xor     ecx, ecx
0x14001f6b5  mov     eax, 1
0x14001f6ba  lock cmpxchg [rdi+r8+64h], ecx
0x14001f6c1  jnz     loc_14001F57D
0x14001f6c7  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001f6ce  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001f6d5  jnz     loc_14001F79F
0x14001f6db  mov     edx, ebx
0x14001f6dd  mov     rcx, rsi
0x14001f6e0  call    RootHub_HideInvalidDebugPortStatusAndChange
0x14001f6e5  test    al, al
0x14001f6e7  jnz     loc_14001F7D3
0x14001f6ed  mov     edx, ebx
0x14001f6ef  mov     eax, ebx
0x14001f6f1  shr     rdx, 3
0x14001f6f5  and     eax, 7
0x14001f6f8  movzx   ecx, byte ptr [rdx+r13]
0x14001f6fd  bts     ecx, eax
0x14001f700  mov     [rdx+r13], cl
0x14001f704  jmp     loc_14001F57D
0x14001f709  cmp     cs:WdfStructureCount, 33h ; '3'
0x14001f710  jbe     short loc_14001F72A
0x14001f712  mov     rax, cs:WdfStructures
0x14001f719  movzx   ecx, word ptr [rax+198h]
0x14001f720  mov     word ptr [rsp+0A8h+var_68], cx
0x14001f725  jmp     loc_14001F3CF
0x14001f72a  mov     eax, 0FFFFh
0x14001f72f  jmp     loc_14001F3CA
0x14001f734  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f73b  lea     rax, aCodePathRequir; "Code Path Requires Passive Level"
0x14001f742  mov     [rsp+0A8h+var_70], rax
0x14001f747  lea     rax, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14001f74e  mov     dword ptr [rsp+0A8h+var_78], 0D91h
0x14001f756  mov     [rsp+0A8h+var_80], rax
0x14001f75b  mov     rcx, [rcx+40h]
0x14001f75f  call    WPP_RECORDER_SF_sds
0x14001f764  jmp     loc_14001F66D
0x14001f769  mov     rcx, [rsi+8]
0x14001f76d  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001f774  mov     r9d, 0BDh
0x14001f77a  mov     [rsp+0A8h+var_88], rax
0x14001f77f  mov     r8d, 0Bh
0x14001f785  mov     dl, 2
0x14001f787  mov     rcx, [rcx+48h]
0x14001f78b  call    WPP_RECORDER_SF_
0x14001f790  jmp     loc_14001F694
0x14001f795  mov     ebx, 0FFh
0x14001f79a  jmp     loc_14001F45E
0x14001f79f  mov     rcx, [rsi+8]
0x14001f7a3  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001f7aa  mov     dword ptr [rsp+0A8h+var_78], edx
0x14001f7ae  mov     r9d, 0C1h
0x14001f7b4  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14001f7b8  mov     r8d, 0Bh
0x14001f7be  mov     dl, 4
0x14001f7c0  mov     [rsp+0A8h+var_88], rax
0x14001f7c5  mov     rcx, [rcx+48h]
0x14001f7c9  call    WPP_RECORDER_SF_dD
0x14001f7ce  jmp     loc_14001F6DB
0x14001f7d3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14001f7da  jz      loc_14001F57D
0x14001f7e0  mov     rcx, [rsi+8]
0x14001f7e4  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14001f7eb  mov     r9d, 0C2h
0x14001f7f1  mov     dword ptr [rsp+0A8h+var_80], ebx
0x14001f7f5  mov     r8d, 0Bh
0x14001f7fb  mov     [rsp+0A8h+var_88], rax
0x14001f800  mov     dl, 4
0x14001f802  mov     rcx, [rcx+48h]
0x14001f806  call    WPP_RECORDER_SF_d
0x14001f80b  jmp     loc_14001F57D
0x14001f810  mov     r9d, 0BEh
0x14001f816  jmp     loc_14001F629
```
