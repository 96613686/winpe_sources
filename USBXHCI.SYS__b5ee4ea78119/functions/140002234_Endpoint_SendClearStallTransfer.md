# Endpoint_SendClearStallTransfer

- ea: `0x140002234`
- end: `0x14000255f`
- name: `Endpoint_SendClearStallTransfer`
- size: `811`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400020c0`

## callees

- `0x140002234`
- `0x140002758`
- `0x1400599b0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!IoReuseIrp` at `0x140002262`
- `ntoskrnl!IoReuseIrp` at `0x140002262`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000235d`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000235d`

## pseudocode

```c
_UNKNOWN **__fastcall Endpoint_SendClearStallTransfer(_QWORD *Context)
{
  PIRP *v2; // rax
  PIRP v3; // rbp
  PIRP *v4; // rdi
  char v5; // al
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _IO_STACK_LOCATION *v7; // rax
  struct _DEVICE_OBJECT *v8; // rax
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdx
  int v14; // edx
  _UNKNOWN **result; // rax
  _IO_STACK_LOCATION *v16; // rax
  __int128 v17; // [rsp+40h] [rbp-48h] BYREF
  PIRP v18; // [rsp+50h] [rbp-38h]

  v18 = 0;
  v2 = (PIRP *)Context[36];
  v17 = 0;
  v3 = *v2;
  v4 = v2 + 1;
  IoReuseIrp(*v2, 0);
  v5 = (_BYTE)v4[16] & 0x1C;
  *((_BYTE *)v4 + 129) = 1;
  *((_BYTE *)v4 + 128) = v5 | 2;
  *((_WORD *)v4 + 65) = 0;
  *((_WORD *)v4 + 66) = *((unsigned __int8 *)Context + 98);
  *((_WORD *)v4 + 67) = 0;
  v4[5] = 0;
  v4[6] = 0;
  *(_DWORD *)v4 = 3276936;
  v4[4] = (PIRP)24;
  *((_DWORD *)v4 + 14) = 5000;
  CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
  memset(&CurrentStackLocation[-1], 0, sizeof(_IO_STACK_LOCATION));
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)v4;
  --v3->Tail.Overlay.CurrentStackLocation;
  --v3->CurrentLocation;
  v7 = v3->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v7[-1].MajorFunction = *(_OWORD *)&v7->MajorFunction;
  *(_OWORD *)&v7[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v7->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)&v7[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&v7->Parameters.ReadWriteConfig.Length;
  v7[-1].FileObject = v7->FileObject;
  v7[-1].Control = 0;
  v8 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 248))(
                                  WdfDriverGlobals,
                                  *(_QWORD *)*Context);
  if ( IoSetCompletionRoutineEx(v8, v3, Endpoint_ClearStallTransferCompletion, Context, 1u, 1u, 1u) < 0 )
  {
    v16 = v3->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))Endpoint_ClearStallTransferCompletion;
    v16[-1].Context = Context;
    v16[-1].Control = -32;
  }
  --v3->CurrentLocation;
  --v3->Tail.Overlay.CurrentStackLocation;
  v10 = Context[2];
  v11 = *(_QWORD *)(v10 + 184);
  if ( v11 )
  {
    v12 = *(_QWORD *)(*(_QWORD *)(v11 + 88) + 72LL);
    v17 = 0;
    v18 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x34 )
        LODWORD(v17) = -1;
      else
        LODWORD(v17) = *(_DWORD *)(WdfStructures + 416);
    }
    else
    {
      LODWORD(v17) = 24;
    }
    v13 = Context[36];
    *(_QWORD *)((char *)&v17 + 4) = 3;
    v18 = v3;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *))(WdfFunctions_01033 + 1992))(
      WdfDriverGlobals,
      *(_QWORD *)(v13 + 144),
      &v17);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = *(unsigned __int8 *)(Context[2] + 143LL);
      LOBYTE(v14) = 4;
      WPP_RECORDER_SF_ddq(
        Context[10],
        v14,
        13,
        72,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(Context[2] + 143LL),
        *((_DWORD *)Context + 38),
        *(_QWORD *)(Context[36] + 144LL));
    }
    result = (_UNKNOWN **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2248))(
                            WdfDriverGlobals,
                            *(_QWORD *)(Context[36] + 144LL),
                            v12);
    if ( (int)result < 0 )
      return (_UNKNOWN **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2104))(
                            WdfDriverGlobals,
                            *(_QWORD *)(Context[36] + 144LL),
                            (unsigned int)result);
  }
  else
  {
    result = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      return (_UNKNOWN **)WPP_RECORDER_SF_ddq(
                            Context[10],
                            v9,
                            13,
                            71,
                            (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
                            *(_BYTE *)(v10 + 143),
                            *((_DWORD *)Context + 38),
                            *(_QWORD *)(Context[36] + 144LL));
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002234  push    rbx
0x140002236  push    rbp
0x140002237  push    rsi
0x140002238  push    rdi
0x140002239  sub     rsp, 68h
0x14000223d  xor     eax, eax
0x14000223f  xorps   xmm0, xmm0
0x140002242  mov     [rsp+88h+var_38], rax
0x140002247  mov     rsi, rcx
0x14000224a  mov     rax, [rcx+120h]
0x140002251  xor     edx, edx; Iostatus
0x140002253  movups  [rsp+88h+var_48], xmm0
0x140002258  mov     rbp, [rax]
0x14000225b  lea     rdi, [rax+8]
0x14000225f  mov     rcx, rbp; Irp
0x140002262  call    cs:__imp_IoReuseIrp
0x140002269  nop     dword ptr [rax+rax+00h]
0x14000226e  mov     al, [rdi+80h]
0x140002274  xor     edx, edx; Val
0x140002276  and     al, 1Ch
0x140002278  mov     byte ptr [rdi+81h], 1
0x14000227f  or      al, 2
0x140002281  mov     [rdi+80h], al
0x140002287  xor     eax, eax
0x140002289  mov     [rdi+82h], ax
0x140002290  movzx   eax, byte ptr [rsi+62h]
0x140002294  mov     [rdi+84h], ax
0x14000229b  xor     eax, eax
0x14000229d  mov     [rdi+86h], ax
0x1400022a4  mov     [rdi+28h], rax
0x1400022a8  mov     [rdi+30h], rax
0x1400022ac  mov     dword ptr [rdi], 320088h
0x1400022b2  lea     r8d, [rax+48h]; Size
0x1400022b6  mov     qword ptr [rdi+20h], 18h
0x1400022be  mov     dword ptr [rdi+38h], 1388h
0x1400022c5  mov     rbx, [rbp+0B8h]
0x1400022cc  lea     rcx, [rbx-48h]; void *
0x1400022d0  call    memset
0x1400022d5  mov     byte ptr [rbx-48h], 0Fh
0x1400022d9  mov     dword ptr [rbx-30h], 220003h
0x1400022e0  mov     [rbx-40h], rdi
0x1400022e4  add     qword ptr [rbp+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400022ec  dec     byte ptr [rbp+43h]
0x1400022ef  mov     rax, [rbp+0B8h]
0x1400022f6  movups  xmm0, xmmword ptr [rax]
0x1400022f9  movups  xmmword ptr [rax-48h], xmm0
0x1400022fd  movups  xmm1, xmmword ptr [rax+10h]
0x140002301  movups  xmmword ptr [rax-38h], xmm1
0x140002305  movups  xmm0, xmmword ptr [rax+20h]
0x140002309  movups  xmmword ptr [rax-28h], xmm0
0x14000230d  movsd   xmm1, qword ptr [rax+30h]
0x140002312  movsd   qword ptr [rax-18h], xmm1
0x140002317  mov     byte ptr [rax-45h], 0
0x14000231b  mov     rdx, [rsi]
0x14000231e  mov     rax, cs:WdfFunctions_01033
0x140002325  mov     rcx, cs:WdfDriverGlobals
0x14000232c  mov     rdx, [rdx]
0x14000232f  mov     rax, [rax+0F8h]
0x140002336  call    _guard_dispatch_icall
0x14000233b  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x140002340  lea     rbx, Endpoint_ClearStallTransferCompletion
0x140002347  mov     r8, rbx; CompletionRoutine
0x14000234a  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000234f  mov     r9, rsi; Context
0x140002352  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140002357  mov     rdx, rbp; Irp
0x14000235a  mov     rcx, rax; DeviceObject
0x14000235d  call    cs:__imp_IoSetCompletionRoutineEx
0x140002364  nop     dword ptr [rax+rax+00h]
0x140002369  test    eax, eax
0x14000236b  js      loc_140002493
0x140002371  dec     byte ptr [rbp+43h]
0x140002374  add     qword ptr [rbp+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000237c  mov     rcx, [rsi+10h]
0x140002380  mov     rax, [rcx+0B8h]
0x140002387  test    rax, rax
0x14000238a  jz      loc_1400024AB
0x140002390  mov     rax, [rax+58h]
0x140002394  xorps   xmm0, xmm0
0x140002397  mov     rbx, [rax+48h]
0x14000239b  xor     eax, eax
0x14000239d  cmp     cs:WdfClientVersionHigherThanFramework, al
0x1400023a3  movups  [rsp+88h+var_48], xmm0
0x1400023a8  mov     [rsp+88h+var_38], rax
0x1400023ad  jnz     loc_140002506
0x1400023b3  mov     dword ptr [rsp+88h+var_48], 18h
0x1400023bb  mov     rdx, [rsi+120h]
0x1400023c2  lea     r8, [rsp+88h+var_48]
0x1400023c7  mov     rax, cs:WdfFunctions_01033
0x1400023ce  mov     rcx, cs:WdfDriverGlobals
0x1400023d5  mov     qword ptr [rsp+88h+var_48+4], 3
0x1400023de  mov     [rsp+88h+var_38], rbp
0x1400023e3  mov     rax, [rax+7C8h]
0x1400023ea  mov     rdx, [rdx+90h]
0x1400023f1  call    _guard_dispatch_icall
0x1400023f6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400023fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002404  jz      short loc_140002453
0x140002406  mov     rax, [rsi+10h]
0x14000240a  mov     r9d, 48h ; 'H'
0x140002410  mov     rcx, [rsi+120h]
0x140002417  movzx   edx, byte ptr [rax+8Fh]
0x14000241e  lea     r8d, [r9-3Bh]
0x140002422  mov     rax, [rcx+90h]
0x140002429  mov     rcx, [rsi+50h]
0x14000242d  mov     [rsp+88h+var_50], rax
0x140002432  mov     eax, [rsi+98h]
0x140002438  mov     dword ptr [rsp+88h+InvokeOnCancel], eax
0x14000243c  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140002443  mov     dword ptr [rsp+88h+InvokeOnError], edx
0x140002447  mov     dl, 4
0x140002449  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x14000244e  call    WPP_RECORDER_SF_ddq
0x140002453  mov     rdx, [rsi+120h]
0x14000245a  mov     r8, rbx
0x14000245d  mov     rax, cs:WdfFunctions_01033
0x140002464  mov     rcx, cs:WdfDriverGlobals
0x14000246b  mov     rdx, [rdx+90h]
0x140002472  mov     rax, [rax+8C8h]
0x140002479  call    _guard_dispatch_icall
0x14000247e  mov     r8d, eax
0x140002481  test    eax, eax
0x140002483  js      loc_140002532
0x140002489  add     rsp, 68h
0x14000248d  pop     rdi
0x14000248e  pop     rsi
0x14000248f  pop     rbp
0x140002490  pop     rbx
0x140002491  retn
0x140002493  mov     rax, [rbp+0B8h]
0x14000249a  mov     [rax-10h], rbx
0x14000249e  mov     [rax-8], rsi
0x1400024a2  mov     byte ptr [rax-45h], 0E0h
0x1400024a6  jmp     loc_140002371
0x1400024ab  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400024b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400024b9  jz      short loc_140002489
0x1400024bb  movzx   ecx, byte ptr [rcx+8Fh]
0x1400024c2  mov     r9d, 47h ; 'G'
0x1400024c8  mov     rax, [rsi+120h]
0x1400024cf  mov     dl, 2
0x1400024d1  lea     r8d, [r9-3Ah]
0x1400024d5  mov     rax, [rax+90h]
0x1400024dc  mov     [rsp+88h+var_50], rax
0x1400024e1  mov     eax, [rsi+98h]
0x1400024e7  mov     dword ptr [rsp+88h+InvokeOnCancel], eax
0x1400024eb  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x1400024f2  mov     dword ptr [rsp+88h+InvokeOnError], ecx
0x1400024f6  mov     rcx, [rsi+50h]
0x1400024fa  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x1400024ff  call    WPP_RECORDER_SF_ddq
0x140002504  jmp     short loc_140002489
0x140002506  cmp     cs:WdfStructureCount, 34h ; '4'
0x14000250d  jbe     short loc_140002525
0x14000250f  mov     rax, cs:WdfStructures
0x140002516  mov     ecx, [rax+1A0h]
0x14000251c  mov     dword ptr [rsp+88h+var_48], ecx
0x140002520  jmp     loc_1400023BB
0x140002525  mov     dword ptr [rsp+88h+var_48], 0FFFFFFFFh
0x14000252d  jmp     loc_1400023BB
0x140002532  mov     rcx, cs:WdfFunctions_01033
0x140002539  mov     rdx, [rsi+120h]
0x140002540  mov     rax, [rcx+838h]
0x140002547  mov     rcx, cs:WdfDriverGlobals
0x14000254e  mov     rdx, [rdx+90h]
0x140002555  call    _guard_dispatch_icall
0x14000255a  jmp     loc_140002489
```
