# MbxRequest::_CreateInner(WDFDEVICE__ *,MbxRequest::RequestType,MbxRequest::MessageType,void *,void *,unsigned __int64,_GUID const *,MBBREQUEST__ * *)

- ea: `0x14000f0c0`
- end: `0x14000f294`
- name: `?_CreateInner@MbxRequest@@CAJPEAUWDFDEVICE__@@W4RequestType@1@W4MessageType@1@PEAX3_KPEBU_GUID@@PEAPEAUMBBREQUEST__@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64, __int64, __int128 *, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140011680`
- `0x140017aa0`
- `0x140017c80`
- `0x14001e14c`
- `0x14001fcf4`

## callees

- `0x140001db8`
- `0x14000f0c0`
- `0x140025800`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall MbxRequest::_CreateInner(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int128 *a7,
        _QWORD *a8)
{
  _QWORD *v8; // rdi
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int128 v20; // [rsp+30h] [rbp-40h] BYREF
  __int128 v21; // [rsp+40h] [rbp-30h]
  __int128 v22; // [rsp+50h] [rbp-20h]
  __int64 *v23; // [rsp+60h] [rbp-10h]

  v8 = a8;
  v23 = 0;
  *a8 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v20) = -1;
    else
      LODWORD(v20) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v20) = 56;
  }
  a8 = 0;
  *((_QWORD *)&v21 + 1) = 0x100000001LL;
  v23 = off_14005DFE8;
  *(_QWORD *)&v21 = CFxObject<MBBREQUEST__ *,MbxRequest,&MbxRequest * GetMbxRequestFromHandle(MBBREQUEST__ *),0>::_OnDestroy;
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _QWORD **))(WdfFunctions_01031 + 1656))(
          WdfDriverGlobals,
          &v20,
          &a8);
  if ( v13 >= 0 )
  {
    v17 = a8;
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *, __int64 *))(WdfFunctions_01031 + 1616))(
            WdfDriverGlobals,
            a8,
            off_14005DFE8);
    if ( v18 )
    {
      *(_QWORD *)(v18 + 8) = v17;
      *(_BYTE *)(v18 + 16) = 1;
      *(_QWORD *)v18 = &MbxRequest::`vftable';
      *(_QWORD *)(v18 + 48) = a5;
      *(_QWORD *)(v18 + 24) = a1;
      *(_QWORD *)(v18 + 32) = a4;
      *(_DWORD *)(v18 + 40) = a3;
      *(_DWORD *)(v18 + 44) = a2;
      *(_QWORD *)(v18 + 56) = a6;
      v19 = *a7;
      *(_QWORD *)(v18 + 80) = 0;
      *(_OWORD *)(v18 + 64) = v19;
    }
    *v8 = v17;
    return 0;
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
            WdfDriverGlobals,
            a1,
            off_14005DF70);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        11,
        10,
        (__int64)WPP_2abdd358d8153330bd03ce58746f3e7e_Traceguids,
        v13);
    }
    Verifier_ReportViolation(*(_QWORD *)(v15 + 1584), v14, 7);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x14000f0c0  push    rbp
0x14000f0c2  push    rbx
0x14000f0c3  push    rsi
0x14000f0c4  push    rdi
0x14000f0c5  push    r12
0x14000f0c7  push    r14
0x14000f0c9  push    r15
0x14000f0cb  mov     rbp, rsp
0x14000f0ce  sub     rsp, 70h
0x14000f0d2  mov     rdi, [rbp+arg_38]
0x14000f0d6  xorps   xmm0, xmm0
0x14000f0d9  xor     eax, eax
0x14000f0db  mov     r14, r9
0x14000f0de  mov     r15d, r8d
0x14000f0e1  mov     [rbp+var_10], rax
0x14000f0e5  mov     r12d, edx
0x14000f0e8  mov     rsi, rcx
0x14000f0eb  mov     qword ptr [rdi], 0
0x14000f0f2  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14000f0f8  movups  [rbp+var_40], xmm0
0x14000f0fc  movups  [rbp+var_30], xmm0
0x14000f100  movups  [rbp+var_20], xmm0
0x14000f104  jz      short loc_14000F12A
0x14000f106  cmp     cs:WdfStructureCount, 26h ; '&'
0x14000f10d  jbe     short loc_14000F121
0x14000f10f  mov     rax, cs:WdfStructures
0x14000f116  mov     ecx, [rax+130h]
0x14000f11c  mov     dword ptr [rbp+var_40], ecx
0x14000f11f  jmp     short loc_14000F131
0x14000f121  mov     dword ptr [rbp+var_40], 0FFFFFFFFh
0x14000f128  jmp     short loc_14000F131
0x14000f12a  mov     dword ptr [rbp+var_40], 38h ; '8'
0x14000f131  mov     rcx, cs:WdfDriverGlobals
0x14000f138  lea     r8, [rbp+arg_38]
0x14000f13c  mov     eax, 1
0x14000f141  mov     [rbp+arg_38], 0
0x14000f149  mov     dword ptr [rbp+var_30+8], eax
0x14000f14c  lea     rdx, [rbp+var_40]
0x14000f150  mov     dword ptr [rbp+var_30+0Ch], eax
0x14000f153  mov     rax, cs:off_14005DFE8
0x14000f15a  mov     [rbp+var_10], rax
0x14000f15e  lea     rax, ?_OnDestroy@?$CFxObject@PEAUMBBREQUEST__@@VMbxRequest@@$1?GetMbxRequestFromHandle@@YAPEAV2@PEAU1@@Z$0A@@@KAXPEAX@Z; CFxObject<MBBREQUEST__ *,MbxRequest,&GetMbxRequestFromHandle(MBBREQUEST__ *),0>::_OnDestroy(void *)
0x14000f165  mov     qword ptr [rbp+var_30], rax
0x14000f169  mov     rax, cs:WdfFunctions_01031
0x14000f170  mov     rax, [rax+678h]
0x14000f177  call    _guard_dispatch_icall
0x14000f17c  mov     ebx, eax
0x14000f17e  test    eax, eax
0x14000f180  jns     loc_14000F209
0x14000f186  mov     rcx, cs:WdfFunctions_01031
0x14000f18d  mov     rdx, rsi
0x14000f190  mov     r8, cs:off_14005DF70
0x14000f197  mov     rax, [rcx+650h]
0x14000f19e  mov     rcx, cs:WdfDriverGlobals
0x14000f1a5  call    _guard_dispatch_icall
0x14000f1aa  mov     rdi, rax
0x14000f1ad  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f1b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f1bb  jz      short loc_14000F1E9
0x14000f1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1c4  lea     rax, WPP_2abdd358d8153330bd03ce58746f3e7e_Traceguids
0x14000f1cb  mov     r9d, 0Ah
0x14000f1d1  mov     [rsp+70h+var_48], ebx
0x14000f1d5  mov     dl, 2
0x14000f1d7  mov     [rsp+70h+var_50], rax
0x14000f1dc  mov     rcx, [rcx+40h]
0x14000f1e0  lea     r8d, [r9+1]
0x14000f1e4  call    WPP_RECORDER_SF_d
0x14000f1e9  mov     rcx, [rdi+630h]
0x14000f1f0  xor     r9d, r9d
0x14000f1f3  mov     [rsp+70h+var_50], 0
0x14000f1fc  lea     r8d, [r9+7]
0x14000f200  call    ?Verifier_ReportViolation@@YAXPEAU_MBX_PRIVATE_GLOBALS@@W4_VerifierAction@@W4_FailureCode@@_K3@Z; Verifier_ReportViolation(_MBX_PRIVATE_GLOBALS *,_VerifierAction,_FailureCode,unsigned __int64,unsigned __int64)
0x14000f205  mov     eax, ebx
0x14000f207  jmp     short loc_14000F284
0x14000f209  mov     rax, cs:WdfFunctions_01031
0x14000f210  mov     rbx, [rbp+arg_38]
0x14000f214  mov     r8, cs:off_14005DFE8
0x14000f21b  mov     rdx, rbx
0x14000f21e  mov     rcx, cs:WdfDriverGlobals
0x14000f225  mov     rax, [rax+650h]
0x14000f22c  call    _guard_dispatch_icall
0x14000f231  mov     rdx, rax
0x14000f234  test    rax, rax
0x14000f237  jz      short loc_14000F27F
0x14000f239  mov     rcx, [rbp+arg_20]
0x14000f23d  mov     [rax+8], rbx
0x14000f241  mov     byte ptr [rax+10h], 1
0x14000f245  lea     rax, ??_7MbxRequest@@6B@; const MbxRequest::`vftable'
0x14000f24c  mov     [rdx], rax
0x14000f24f  mov     rax, [rbp+arg_30]
0x14000f253  mov     [rdx+30h], rcx
0x14000f257  mov     rcx, [rbp+arg_28]
0x14000f25b  mov     [rdx+18h], rsi
0x14000f25f  mov     [rdx+20h], r14
0x14000f263  mov     [rdx+28h], r15d
0x14000f267  mov     [rdx+2Ch], r12d
0x14000f26b  mov     [rdx+38h], rcx
0x14000f26f  movups  xmm0, xmmword ptr [rax]
0x14000f272  mov     qword ptr [rdx+50h], 0
0x14000f27a  movdqu  xmmword ptr [rdx+40h], xmm0
0x14000f27f  mov     [rdi], rbx
0x14000f282  xor     eax, eax
0x14000f284  add     rsp, 70h
0x14000f288  pop     r15
0x14000f28a  pop     r14
0x14000f28c  pop     r12
0x14000f28e  pop     rdi
0x14000f28f  pop     rsi
0x14000f290  pop     rbx
0x14000f291  pop     rbp
0x14000f292  retn
```
