# FwppStreamInjectPrologue

- ea: `0x180003b60`
- end: `0x180003fab`
- name: `FwppStreamInjectPrologue`
- size: `1099`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f70`
- `0x18001e740`

## callees

- `0x180003b60`
- `0x180004904`
- `0x18000a224`
- `0x18000c9b4`
- `0x18000de60`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180003c17`
- `ntoskrnl!MmBadPointer` at `0x180003d76`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180003f37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180003f37`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180003cd3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180003d0c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180003cd3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180003d0c`
- `NETIO!WfpNblInfoGet` at `0x180003bff`
- `NETIO!WfpNblInfoGet` at `0x180003bff`
- `NETIO!NetioDereferenceNetBufferList` at `0x180003e2b`
- `NETIO!NetioDereferenceNetBufferList` at `0x180003e2b`
- `NETIO!NetioInitializeNetBufferListContextPrimitive` at `0x180003e10`
- `NETIO!NetioInitializeNetBufferListContextPrimitive` at `0x180003e10`
- `NETIO!NetioInitializeNetBufferListContext` at `0x180003d50`
- `NETIO!NetioInitializeNetBufferListContext` at `0x180003d50`

## string_xrefs

- `0x180003ec9`: `ExAllocateFromNPagedLookasideList`
- `0x180003efb`: `ExAllocateFromNPagedLookasideList`
- `0x180003ee1`: `WfpAllocFromNPagedLookasideList`
- `0x180003f13`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppStreamInjectPrologue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // edx
  int v8; // esi
  int v9; // r12d
  __int64 v10; // rdi
  __int64 v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rbx
  _QWORD *v14; // r13
  char v15; // r15
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rsi
  __int64 v19; // rbp
  char v21; // al
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // r8d
  int v30; // [rsp+30h] [rbp-58h]
  int v31; // [rsp+90h] [rbp+8h]

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v31 = 0;
  v30 = 0;
  v10 = a3;
  v11 = a1;
  if ( a1 )
  {
    v12 = a6;
    if ( !a6 )
    {
      v26 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppStreamInjectPrologue", -1071513572);
      goto LABEL_42;
    }
    v9 = 1;
    if ( _InterlockedAdd(&gFwpTcpIp, 1u) < 0 )
    {
      v26 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppStreamInjectPrologue", -1071513344);
      goto LABEL_42;
    }
    v13 = 0;
    while ( 1 )
    {
      if ( !v10 )
        return v13;
      ++v9;
      if ( _InterlockedAdd(&gFwpTcpIp, 1u) < 0 )
      {
        v29 = -1071513344;
LABEL_64:
        v26 = WfpReportSysErrorAsNtStatus(a1, (int)"FwppStreamInjectPrologue", v29);
        v10 = a3;
LABEL_42:
        v13 = v26;
        if ( v26 )
        {
LABEL_43:
          v7 = v31;
          goto LABEL_44;
        }
        return v13;
      }
      v31 = v7 + 1;
      if ( _InterlockedAdd((volatile signed __int32 *)(v11 + 40), 1u) < 0 )
      {
        v29 = -1071513343;
        goto LABEL_64;
      }
      v14 = 0;
      v15 = 0;
      v16 = (_QWORD *)WfpNblInfoGet(v10);
      if ( !v16 || (v17 = MmBadPointer, v16 == MmBadPointer) )
      {
        v18 = MmBadPointer;
        if ( v16 != MmBadPointer )
        {
          v18 = 0;
LABEL_14:
          v19 = WfpReportSysErrorAsNtStatus((__int64)v16, (int)"FwppPrepareNetBufferListForInjection", -1071513547);
          v13 = v19;
          if ( v19 )
            goto LABEL_57;
          v12 = a6;
          goto LABEL_16;
        }
        v17 = MmBadPointer;
      }
      else
      {
        v18 = (_QWORD *)v16[1];
      }
      if ( !v18 )
        goto LABEL_14;
      if ( v18 == v17 )
        goto LABEL_14;
      if ( v18[41] )
        goto LABEL_14;
      v21 = *((_BYTE *)v18 + 368);
      *((_BYTE *)v18 + 368) = 1;
      if ( v21 == 1 )
        goto LABEL_14;
      v14 = ExAllocateFromNPagedLookasideList(&stru_180048500);
      if ( !v14 )
      {
        v27 = WfpReportSysErrorAsNtStatus(v22, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
        v13 = v27;
        if ( v27 )
        {
          WfpReportError(v27, (int)"WfpAllocFromNPagedLookasideList");
          LODWORD(v19) = v13;
          goto LABEL_60;
        }
      }
      v14[3] = a2;
      v13 = 0;
      v14[2] = v11;
      *(_DWORD *)v14 = 1768978246;
      v24 = ExAllocateFromNPagedLookasideList(&stru_180048240);
      if ( !v24 )
      {
        v28 = WfpReportSysErrorAsNtStatus(v23, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
        v13 = v28;
        if ( v28 )
        {
          v15 = 1;
          WfpReportError(v28, (int)"WfpAllocFromNPagedLookasideList");
          LODWORD(v19) = v13;
LABEL_57:
          if ( v14 )
            ExFreeToNPagedLookasideList(&stru_180048500, v14);
          if ( v15 )
LABEL_60:
            *((_BYTE *)v18 + 368) = 0;
          WfpReportError(v19, (int)"FwppPrepareNetBufferListForInjection");
          v8 = v30;
          v10 = a3;
          goto LABEL_43;
        }
      }
      v24[2] = a7;
      *v24 = v11;
      v24[1] = v12;
      if ( *((_DWORD *)v18 + 1) == 1 )
      {
        NetioInitializeNetBufferListContextPrimitive(v10, *(_QWORD *)(v10 + 24), FwppInjectComplete, v24);
        a1 = *(_QWORD *)(v10 + 24);
        if ( a1 )
          NetioDereferenceNetBufferList(a1, 0);
      }
      else
      {
        NetioInitializeNetBufferListContext(v10, 0, FwppInjectComplete, v24);
      }
      *((_DWORD *)v18 + 44) = 1;
      v14[1] = v18;
      v18[41] = v14;
LABEL_16:
      if ( a4 || a5 || (v25 = *(_QWORD *)(v10 + 24)) != 0 && *(int *)(v25 + 136) < 0 )
        *(_DWORD *)(v10 + 136) |= 0x80000000;
      v10 = *(_QWORD *)v10;
      v8 = v30 + 1;
      v7 = v31;
      ++v30;
    }
  }
  v13 = -1071513572;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, a3, "FwppStreamInjectPrologue", -1071513572);
    v7 = 0;
  }
LABEL_44:
  if ( v10 )
  {
    do
    {
      if ( !v8 )
        break;
      FwppUndoNetBufferListInjectionChanges(v10);
      v10 = *(_QWORD *)v10;
      --v8;
    }
    while ( v10 );
    v7 = v31;
  }
  if ( v7 > 0 )
    _InterlockedAdd((volatile signed __int32 *)(v11 + 40), -v7);
  if ( v9 > 0 )
    _InterlockedAdd(&gFwpTcpIp, -v9);
  if ( v13 )
    WfpReportError(v13, (int)"FwppStreamInjectPrologue");
  return v13;
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_18], r9b
0x180003b65  mov     [rsp+arg_10], r8
0x180003b6a  mov     [rsp+arg_8], rdx
0x180003b6f  push    rbx
0x180003b70  push    rbp
0x180003b71  push    rsi
0x180003b72  push    rdi
0x180003b73  push    r12
0x180003b75  push    r13
0x180003b77  push    r14
0x180003b79  push    r15
0x180003b7b  sub     rsp, 48h
0x180003b7f  xor     edx, edx
0x180003b81  xor     esi, esi
0x180003b83  xor     r12d, r12d
0x180003b86  mov     [rsp+88h+arg_0], edx
0x180003b8d  mov     [rsp+88h+var_58], esi
0x180003b91  mov     rdi, r8
0x180003b94  mov     r14, rcx
0x180003b97  test    rcx, rcx
0x180003b9a  jz      loc_180003DBE
0x180003ba0  mov     rbp, [rsp+88h+arg_28]
0x180003ba8  test    rbp, rbp
0x180003bab  jz      loc_180003E43
0x180003bb1  mov     r12d, 1
0x180003bb7  lock add cs:gFwpTcpIp, r12d
0x180003bbf  js      loc_180003EAF
0x180003bc5  xor     ebx, ebx
0x180003bc7  test    rdi, rdi
0x180003bca  jz      loc_180003CA4
0x180003bd0  inc     r12d
0x180003bd3  lock add cs:gFwpTcpIp, 1
0x180003bdb  js      loc_180003F78
0x180003be1  inc     edx
0x180003be3  mov     [rsp+88h+arg_0], edx
0x180003bea  lock add dword ptr [r14+28h], 1
0x180003bf0  js      loc_180003F70
0x180003bf6  mov     rcx, rdi
0x180003bf9  xor     r13d, r13d
0x180003bfc  xor     r15b, r15b
0x180003bff  call    cs:__imp_WfpNblInfoGet
0x180003c06  nop     dword ptr [rax+rax+00h]
0x180003c0b  mov     rcx, rax
0x180003c0e  test    rax, rax
0x180003c11  jz      loc_180003D76
0x180003c17  mov     rax, cs:MmBadPointer
0x180003c1e  mov     rdx, [rax]
0x180003c21  cmp     rcx, rdx
0x180003c24  jz      loc_180003D76
0x180003c2a  mov     rsi, [rcx+8]
0x180003c2e  test    rsi, rsi
0x180003c31  jz      short loc_180003C41
0x180003c33  cmp     rsi, rdx
0x180003c36  jz      short loc_180003C41
0x180003c38  cmp     [rsi+148h], r13
0x180003c3f  jz      short loc_180003CB9
0x180003c41  mov     r8d, 0C0220035h
0x180003c47  lea     rdx, aFwpppreparenet; "FwppPrepareNetBufferListForInjection"
0x180003c4e  call    WfpReportSysErrorAsNtStatus
0x180003c53  mov     rbp, rax
0x180003c56  mov     rbx, rax
0x180003c59  test    rax, rax
0x180003c5c  jnz     loc_180003F28
0x180003c62  mov     rbp, [rsp+88h+arg_28]
0x180003c6a  cmp     [rsp+88h+arg_18], 0
0x180003c72  jz      loc_180003D91
0x180003c78  or      dword ptr [rdi+88h], 80000000h
0x180003c82  mov     esi, [rsp+88h+var_58]
0x180003c86  mov     rdi, [rdi]
0x180003c89  inc     esi
0x180003c8b  mov     edx, [rsp+88h+arg_0]
0x180003c92  mov     [rsp+88h+var_58], esi
0x180003c96  jmp     loc_180003BC7
0x180003c9b  test    rbx, rbx
0x180003c9e  jnz     loc_180003F97
0x180003ca4  mov     rax, rbx
0x180003ca7  add     rsp, 48h
0x180003cab  pop     r15
0x180003cad  pop     r14
0x180003caf  pop     r13
0x180003cb1  pop     r12
0x180003cb3  pop     rdi
0x180003cb4  pop     rsi
0x180003cb5  pop     rbp
0x180003cb6  pop     rbx
0x180003cb7  retn
0x180003cb9  mov     eax, 1
0x180003cbe  xchg    al, [rsi+170h]
0x180003cc4  cmp     al, 1
0x180003cc6  jz      loc_180003C41
0x180003ccc  lea     rcx, stru_180048500; Lookaside
0x180003cd3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180003cda  nop     dword ptr [rax+rax+00h]
0x180003cdf  mov     r13, rax
0x180003ce2  test    rax, rax
0x180003ce5  jz      loc_180003EC3
0x180003ceb  mov     rax, [rsp+88h+arg_8]
0x180003cf3  lea     rcx, stru_180048240; Lookaside
0x180003cfa  mov     [r13+18h], rax
0x180003cfe  xor     ebx, ebx
0x180003d00  mov     [r13+10h], r14
0x180003d04  mov     dword ptr [r13+0], 69707746h
0x180003d0c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180003d13  nop     dword ptr [rax+rax+00h]
0x180003d18  mov     r15, rax
0x180003d1b  test    rax, rax
0x180003d1e  jz      loc_180003EF5
0x180003d24  mov     rax, [rsp+88h+arg_30]
0x180003d2c  lea     r8, FwppInjectComplete
0x180003d33  mov     [r15+10h], rax
0x180003d37  mov     r9, r15
0x180003d3a  mov     [r15], r14
0x180003d3d  mov     rcx, rdi
0x180003d40  mov     [r15+8], rbp
0x180003d44  cmp     dword ptr [rsi+4], 1
0x180003d48  jz      loc_180003E0C
0x180003d4e  xor     edx, edx
0x180003d50  call    cs:__imp_NetioInitializeNetBufferListContext
0x180003d57  nop     dword ptr [rax+rax+00h]
0x180003d5c  mov     dword ptr [rsi+0B0h], 1
0x180003d66  mov     [r13+8], rsi
0x180003d6a  mov     [rsi+148h], r13
0x180003d71  jmp     loc_180003C6A
0x180003d76  mov     rax, cs:MmBadPointer
0x180003d7d  mov     rsi, [rax]
0x180003d80  cmp     rcx, rsi
0x180003d83  jnz     loc_180003E3C
0x180003d89  mov     rdx, rsi
0x180003d8c  jmp     loc_180003C2E
0x180003d91  cmp     [rsp+88h+arg_20], 0
0x180003d99  jnz     loc_180003C78
0x180003d9f  mov     rax, [rdi+18h]
0x180003da3  test    rax, rax
0x180003da6  jz      loc_180003C82
0x180003dac  cmp     dword ptr [rax+88h], 0
0x180003db3  jge     loc_180003C82
0x180003db9  jmp     loc_180003C78
0x180003dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dc5  lea     rax, WPP_GLOBAL_Control
0x180003dcc  mov     rbx, 0FFFFFFFFC022001Ch
0x180003dd3  cmp     rcx, rax
0x180003dd6  jz      loc_180003E69
0x180003ddc  cmp     byte ptr [rcx+29h], 2
0x180003de0  jb      loc_180003E69
0x180003de6  test    dword ptr [rcx+2Ch], 1000h
0x180003ded  jz      short loc_180003E69
0x180003def  mov     rcx, [rcx+18h]
0x180003df3  lea     r9, aFwppstreaminje_1; "FwppStreamInjectPrologue"
0x180003dfa  mov     edx, 0Ah
0x180003dff  mov     [rsp+88h+var_68], ebx
0x180003e03  call    WPP_SF_sd
0x180003e08  mov     edx, esi
0x180003e0a  jmp     short loc_180003E69
0x180003e0c  mov     rdx, [rdi+18h]
0x180003e10  call    cs:__imp_NetioInitializeNetBufferListContextPrimitive
0x180003e17  nop     dword ptr [rax+rax+00h]
0x180003e1c  mov     rcx, [rdi+18h]
0x180003e20  test    rcx, rcx
0x180003e23  jz      loc_180003D5C
0x180003e29  xor     edx, edx
0x180003e2b  call    cs:__imp_NetioDereferenceNetBufferList
0x180003e32  nop     dword ptr [rax+rax+00h]
0x180003e37  jmp     loc_180003D5C
0x180003e3c  xor     esi, esi
0x180003e3e  jmp     loc_180003C41
0x180003e43  mov     r8, 0FFFFFFFFC022001Ch
0x180003e4a  lea     rdx, aFwppstreaminje_1; "FwppStreamInjectPrologue"
0x180003e51  call    WfpReportSysErrorAsNtStatus
0x180003e56  mov     rbx, rax
0x180003e59  test    rax, rax
0x180003e5c  jz      loc_180003CA4
0x180003e62  mov     edx, [rsp+88h+arg_0]
0x180003e69  test    rdi, rdi
0x180003e6c  jz      short loc_180003E8B
0x180003e6e  test    esi, esi
0x180003e70  jz      short loc_180003E84
0x180003e72  mov     rcx, rdi
0x180003e75  call    FwppUndoNetBufferListInjectionChanges
0x180003e7a  mov     rdi, [rdi]
0x180003e7d  dec     esi
0x180003e7f  test    rdi, rdi
0x180003e82  jnz     short loc_180003E6E
0x180003e84  mov     edx, [rsp+88h+arg_0]
0x180003e8b  test    edx, edx
0x180003e8d  jle     short loc_180003E96
0x180003e8f  neg     edx
0x180003e91  lock add [r14+28h], edx
0x180003e96  test    r12d, r12d
0x180003e99  jle     loc_180003C9B
0x180003e9f  neg     r12d
0x180003ea2  lock add cs:gFwpTcpIp, r12d
0x180003eaa  jmp     loc_180003C9B
0x180003eaf  mov     r8d, 0C0220100h
0x180003eb5  lea     rdx, aFwppstreaminje_1; "FwppStreamInjectPrologue"
0x180003ebc  call    WfpReportSysErrorAsNtStatus
0x180003ec1  jmp     short loc_180003E56
0x180003ec3  mov     r8d, 0C0000017h
0x180003ec9  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180003ed0  call    WfpReportSysErrorAsNtStatus
0x180003ed5  mov     rbx, rax
0x180003ed8  test    rax, rax
0x180003edb  jz      loc_180003CEB
0x180003ee1  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180003ee8  mov     rcx, rax
0x180003eeb  call    WfpReportError
0x180003ef0  mov     rbp, rbx
0x180003ef3  jmp     short loc_180003F48
0x180003ef5  mov     r8d, 0C0000017h
0x180003efb  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180003f02  call    WfpReportSysErrorAsNtStatus
0x180003f07  mov     rbx, rax
0x180003f0a  test    rax, rax
0x180003f0d  jz      loc_180003D24
0x180003f13  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180003f1a  mov     rcx, rax
0x180003f1d  mov     r15b, 1
0x180003f20  call    WfpReportError
0x180003f25  mov     rbp, rbx
0x180003f28  test    r13, r13
0x180003f2b  jz      short loc_180003F43
0x180003f2d  mov     rdx, r13; Entry
0x180003f30  lea     rcx, stru_180048500; Lookaside
0x180003f37  call    cs:__imp_ExFreeToNPagedLookasideList
0x180003f3e  nop     dword ptr [rax+rax+00h]
0x180003f43  test    r15b, r15b
0x180003f46  jz      short loc_180003F50
0x180003f48  xor     eax, eax
0x180003f4a  xchg    al, [rsi+170h]
0x180003f50  lea     rdx, aFwpppreparenet; "FwppPrepareNetBufferListForInjection"
0x180003f57  mov     rcx, rbp
0x180003f5a  call    WfpReportError
0x180003f5f  mov     esi, [rsp+88h+var_58]
0x180003f63  mov     rdi, [rsp+88h+arg_10]
0x180003f6b  jmp     loc_180003E62
0x180003f70  mov     r8d, 0C0220101h
0x180003f76  jmp     short loc_180003F7E
0x180003f78  mov     r8d, 0C0220100h
0x180003f7e  lea     rdx, aFwppstreaminje_1; "FwppStreamInjectPrologue"
0x180003f85  call    WfpReportSysErrorAsNtStatus
0x180003f8a  mov     rdi, [rsp+88h+arg_10]
0x180003f92  jmp     loc_180003E56
0x180003f97  lea     rdx, aFwppstreaminje_1; "FwppStreamInjectPrologue"
0x180003f9e  mov     rcx, rbx
0x180003fa1  call    WfpReportError
0x180003fa6  jmp     loc_180003CA4
```
