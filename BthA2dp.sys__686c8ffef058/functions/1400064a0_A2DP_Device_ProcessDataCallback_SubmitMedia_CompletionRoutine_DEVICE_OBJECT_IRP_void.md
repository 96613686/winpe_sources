# A2DP_Device::ProcessDataCallback_SubmitMedia_CompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400064a0`
- end: `0x1400068d3`
- name: `?ProcessDataCallback_SubmitMedia_CompletionRoutine@A2DP_Device@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1075`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x140005e50`
- `0x1400064a0`
- `0x1400068dc`
- `0x14000700c`
- `0x14000f570`
- `0x14000f6e4`
- `0x140034c2c`
- `0x14005903c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400065b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006679`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006679`

## string_xrefs

- `0x14000679a`: `ProcessDataCallback_SubmitMedia_CompletionRoutine`

## pseudocode

```c
__int64 __fastcall A2DP_Device::ProcessDataCallback_SubmitMedia_CompletionRoutine(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        unsigned int *a3)
{
  unsigned int *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  CPcmPin *v6; // rdi
  bool v7; // al
  volatile signed __int32 *v8; // rbp
  signed __int32 v9; // esi
  int v10; // edi
  PDEVICE_OBJECT v11; // rcx
  unsigned int i; // edi
  volatile signed __int32 v13; // ecx
  bool v15; // r10
  bool v16; // al
  bool v17; // dl
  int v18; // [rsp+20h] [rbp-68h]
  int v19; // [rsp+28h] [rbp-60h]
  int v20; // [rsp+38h] [rbp-50h]

  v3 = a3;
  if ( a3 )
  {
    v4 = *(_QWORD *)a3;
    v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 24LL);
    if ( v5 )
    {
      v6 = *(CPcmPin **)(v5 + 16);
      if ( v6 )
      {
        v15 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            v15,
            (_DWORD)a3,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            14,
            154,
            (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
            v4,
            v3[3]);
        }
        CPcmPin::BytesCompletedCallback(v6, v3[3]);
      }
      else
      {
        v7 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v7,
            (_DWORD)a3,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            14,
            155,
            (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
            v4);
        }
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          (_DWORD)a3,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          14,
          156,
          (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
          v4);
      }
    }
    v8 = *(volatile signed __int32 **)v3;
    v9 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v3 + 2760LL));
    v10 = _InterlockedDecrement(v8 + 856);
    v11 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v4 || (_BYTE)a3 )
      WPP_RECORDER_AND_TRACE_SF_dsddq(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        (_DWORD)a3,
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        v19,
        47,
        v20,
        v9,
        (__int64)"ProcessDataCallback_SubmitMedia_CompletionRoutine",
        3,
        v10,
        (char)v8);
    if ( v10 < 0 )
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(v11, 3, 0, "Invalid A2DP_Device dereference");
    if ( !v9 )
    {
      for ( i = 0; i < 0xE; ++i )
      {
        v13 = v8[i + 853];
        if ( v13 )
        {
          LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_llq(
              WPP_GLOBAL_Control->AttachedDevice,
              v4,
              (_DWORD)a3,
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              5,
              48,
              (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
              i,
              v13,
              (char)v8);
          }
        }
      }
      if ( v8 )
      {
        A2DP_Device::~A2DP_Device((A2DP_Device *)v8);
        ExFreePoolWithTag((PVOID)v8, 0x646D4370u);
      }
    }
    ExFreePoolWithTag(v3, 0x50444141u);
  }
  else
  {
    v17 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v17,
        (_DWORD)a3,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        14,
        157,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400064a0  mov     rax, rsp
0x1400064a3  mov     [rax+20h], rbx
0x1400064a7  push    r12
0x1400064a9  push    r14
0x1400064ab  push    r15
0x1400064ad  sub     rsp, 70h
0x1400064b1  mov     rbx, r8
0x1400064b4  test    r8, r8
0x1400064b7  jz      loc_14000685A
0x1400064bd  mov     rdx, [r8]
0x1400064c0  lea     r12, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400064c7  mov     [rax+8], rbp
0x1400064cb  mov     [rax+10h], rsi
0x1400064cf  mov     [rax+18h], rdi
0x1400064d3  mov     rax, [rdx+8]
0x1400064d7  mov     rcx, [rax+18h]
0x1400064db  test    rcx, rcx
0x1400064de  jz      loc_14000669E
0x1400064e4  mov     rdi, [rcx+10h]
0x1400064e8  test    rdi, rdi
0x1400064eb  jnz     loc_14000661F
0x1400064f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064f8  lea     r14, WPP_GLOBAL_Control
0x1400064ff  cmp     rcx, r14
0x140006502  jnz     loc_140006744
0x140006508  xor     al, al
0x14000650a  lea     r15, WPP_RECORDER_INITIALIZED
0x140006511  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006518  setnz   r8b
0x14000651c  test    al, al
0x14000651e  jnz     loc_140006762
0x140006524  test    r8b, r8b
0x140006527  jnz     loc_140006762
0x14000652d  mov     rbp, [rbx]
0x140006530  mov     edi, 0FFFFFFFFh
0x140006535  mov     esi, edi
0x140006537  lock xadd [rbp+0AC8h], esi
0x14000653f  dec     esi
0x140006541  lock xadd [rbp+0D60h], edi
0x140006549  dec     edi
0x14000654b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006552  cmp     rcx, r14
0x140006555  jnz     loc_140006603
0x14000655b  xor     dl, dl
0x14000655d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006564  jnz     loc_1400065F0
0x14000656a  xor     r8b, r8b
0x14000656d  test    dl, dl
0x14000656f  jnz     loc_140006796
0x140006575  test    r8b, r8b
0x140006578  jnz     loc_140006796
0x14000657e  test    edi, edi
0x140006580  js      loc_1400067D0
0x140006586  test    esi, esi
0x140006588  jnz     short loc_1400065AE
0x14000658a  xor     edi, edi
0x14000658c  movsxd  rax, edi
0x14000658f  mov     ecx, [rbp+rax*4+0D54h]
0x140006596  test    ecx, ecx
0x140006598  jnz     loc_1400067E9
0x14000659e  inc     edi
0x1400065a0  cmp     edi, 0Eh
0x1400065a3  jb      short loc_14000658C
0x1400065a5  test    rbp, rbp
0x1400065a8  jnz     loc_140006669
0x1400065ae  mov     edx, 50444141h; Tag
0x1400065b3  mov     rcx, rbx; P
0x1400065b6  call    cs:__imp_ExFreePoolWithTag
0x1400065bd  nop     dword ptr [rax+rax+00h]
0x1400065c2  mov     rdi, [rsp+88h+arg_10]
0x1400065ca  mov     rsi, [rsp+88h+arg_8]
0x1400065d2  mov     rbp, [rsp+88h+arg_0]
0x1400065da  mov     rbx, [rsp+88h+arg_18]
0x1400065e2  xor     eax, eax
0x1400065e4  add     rsp, 70h
0x1400065e8  pop     r15
0x1400065ea  pop     r14
0x1400065ec  pop     r12
0x1400065ee  retn
0x1400065f0  cmp     word ptr [rcx+48h], 0
0x1400065f5  jz      loc_14000656A
0x1400065fb  mov     r8b, 1
0x1400065fe  jmp     loc_14000656D
0x140006603  mov     eax, [rcx+2Ch]
0x140006606  test    al, 10h
0x140006608  jz      loc_14000655B
0x14000660e  cmp     byte ptr [rcx+29h], 5
0x140006612  jb      loc_14000655B
0x140006618  mov     dl, 1
0x14000661a  jmp     loc_14000655D
0x14000661f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006626  lea     r14, WPP_GLOBAL_Control
0x14000662d  cmp     rcx, r14
0x140006630  jnz     short loc_14000668A
0x140006632  xor     r10b, r10b
0x140006635  lea     r15, WPP_RECORDER_INITIALIZED
0x14000663c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006643  setnz   r8b
0x140006647  test    r10b, r10b
0x14000664a  jnz     loc_140006709
0x140006650  test    r8b, r8b
0x140006653  jnz     loc_140006709
0x140006659  mov     edx, [rbx+0Ch]; unsigned int
0x14000665c  mov     rcx, rdi; this
0x14000665f  call    ?BytesCompletedCallback@CPcmPin@@QEAAJK@Z; CPcmPin::BytesCompletedCallback(ulong)
0x140006664  jmp     loc_14000652D
0x140006669  mov     rcx, rbp; this
0x14000666c  call    ??1A2DP_Device@@QEAA@XZ; A2DP_Device::~A2DP_Device(void)
0x140006671  mov     edx, 646D4370h; Tag
0x140006676  mov     rcx, rbp; P
0x140006679  call    cs:__imp_ExFreePoolWithTag
0x140006680  nop     dword ptr [rax+rax+00h]
0x140006685  jmp     loc_1400065AE
0x14000668a  test    dword ptr [rcx+2Ch], 2000h
0x140006691  jz      short loc_140006632
0x140006693  cmp     byte ptr [rcx+29h], 4
0x140006697  jb      short loc_140006632
0x140006699  mov     r10b, 1
0x14000669c  jmp     short loc_140006635
0x14000669e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066a5  lea     r14, WPP_GLOBAL_Control
0x1400066ac  cmp     rcx, r14
0x1400066af  jnz     loc_140006778
0x1400066b5  xor     al, al
0x1400066b7  lea     r15, WPP_RECORDER_INITIALIZED
0x1400066be  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400066c5  setnz   r8b
0x1400066c9  test    al, al
0x1400066cb  jnz     short loc_1400066D6
0x1400066cd  test    r8b, r8b
0x1400066d0  jz      loc_14000652D
0x1400066d6  mov     [rsp+88h+var_48], rdx
0x1400066db  mov     [rsp+88h+var_50], r12
0x1400066e0  mov     [rsp+88h+var_58], 9Ch
0x1400066e7  mov     r9, [rcx+40h]
0x1400066eb  movzx   edx, al
0x1400066ee  mov     rcx, [rcx+18h]
0x1400066f2  mov     [rsp+88h+var_60], 0Eh
0x1400066fa  mov     [rsp+88h+var_68], 4
0x1400066ff  call    WPP_RECORDER_AND_TRACE_SF_q
0x140006704  jmp     loc_14000652D
0x140006709  mov     eax, [rbx+0Ch]
0x14000670c  mov     r9, [rcx+40h]
0x140006710  mov     rcx, [rcx+18h]
0x140006714  mov     dword ptr [rsp+88h+var_40], eax
0x140006718  mov     [rsp+88h+var_48], rdx
0x14000671d  movzx   edx, r10b
0x140006721  mov     [rsp+88h+var_50], r12
0x140006726  mov     [rsp+88h+var_58], 9Ah
0x14000672d  mov     [rsp+88h+var_60], 0Eh
0x140006735  mov     [rsp+88h+var_68], 4
0x14000673a  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14000673f  jmp     loc_140006659
0x140006744  test    dword ptr [rcx+2Ch], 2000h
0x14000674b  jz      loc_140006508
0x140006751  cmp     byte ptr [rcx+29h], 4
0x140006755  jb      loc_140006508
0x14000675b  mov     al, 1
0x14000675d  jmp     loc_14000650A
0x140006762  mov     [rsp+88h+var_48], rdx
0x140006767  mov     [rsp+88h+var_50], r12
0x14000676c  mov     [rsp+88h+var_58], 9Bh
0x140006773  jmp     loc_1400066E7
0x140006778  test    dword ptr [rcx+2Ch], 2000h
0x14000677f  jz      loc_1400066B5
0x140006785  cmp     byte ptr [rcx+29h], 4
0x140006789  jb      loc_1400066B5
0x14000678f  mov     al, 1
0x140006791  jmp     loc_1400066B7
0x140006796  mov     r9, [rcx+40h]
0x14000679a  lea     rax, aProcessdatacal_0; "ProcessDataCallback_SubmitMedia_Complet"...
0x1400067a1  mov     rcx, [rcx+18h]
0x1400067a5  mov     [rsp+88h+var_28], rbp
0x1400067aa  mov     [rsp+88h+var_30], edi
0x1400067ae  mov     dword ptr [rsp+88h+var_38], 3
0x1400067b6  mov     [rsp+88h+var_40], rax
0x1400067bb  mov     dword ptr [rsp+88h+var_48], esi
0x1400067bf  mov     [rsp+88h+var_58], 2Fh ; '/'
0x1400067c6  call    WPP_RECORDER_AND_TRACE_SF_dsddq
0x1400067cb  jmp     loc_14000657E
0x1400067d0  lea     r9, aInvalidA2dpDev; "Invalid A2DP_Device dereference"
0x1400067d7  xor     r8d, r8d
0x1400067da  mov     edx, 3
0x1400067df  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1400067e4  jmp     loc_140006586
0x1400067e9  mov     r10, cs:WPP_GLOBAL_Control
0x1400067f0  cmp     r10, r14
0x1400067f3  jz      short loc_140006808
0x1400067f5  mov     eax, [r10+2Ch]
0x1400067f9  test    al, 10h
0x1400067fb  jz      short loc_140006808
0x1400067fd  cmp     byte ptr [r10+29h], 2
0x140006802  jb      short loc_140006808
0x140006804  mov     dl, 1
0x140006806  jmp     short loc_14000680A
0x140006808  xor     dl, dl
0x14000680a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006811  setnz   r8b
0x140006815  test    dl, dl
0x140006817  jnz     short loc_140006822
0x140006819  test    r8b, r8b
0x14000681c  jz      loc_14000659E
0x140006822  mov     r9, [r10+40h]
0x140006826  mov     [rsp+88h+var_38], rbp
0x14000682b  mov     dword ptr [rsp+88h+var_40], ecx
0x14000682f  mov     rcx, [r10+18h]
0x140006833  mov     dword ptr [rsp+88h+var_48], edi
0x140006837  mov     [rsp+88h+var_50], r12
0x14000683c  mov     [rsp+88h+var_58], 30h ; '0'
0x140006843  mov     [rsp+88h+var_60], 5
0x14000684b  mov     [rsp+88h+var_68], 2
0x140006850  call    WPP_RECORDER_AND_TRACE_SF_llq
0x140006855  jmp     loc_14000659E
0x14000685a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006861  lea     r14, WPP_GLOBAL_Control
0x140006868  cmp     rcx, r14
0x14000686b  jz      short loc_140006880
0x14000686d  test    dword ptr [rcx+2Ch], 2000h
0x140006874  jz      short loc_140006880
0x140006876  cmp     byte ptr [rcx+29h], 4
0x14000687a  jb      short loc_140006880
0x14000687c  mov     dl, 1
0x14000687e  jmp     short loc_140006882
0x140006880  xor     dl, dl
0x140006882  lea     r15, WPP_RECORDER_INITIALIZED
0x140006889  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006890  setnz   r8b
0x140006894  test    dl, dl
0x140006896  jnz     short loc_1400068A1
0x140006898  test    r8b, r8b
0x14000689b  jz      loc_1400065DA
0x1400068a1  mov     r9, [rcx+40h]
0x1400068a5  lea     r12, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400068ac  mov     rcx, [rcx+18h]
0x1400068b0  mov     [rsp+88h+var_50], r12
0x1400068b5  mov     [rsp+88h+var_58], 9Dh
0x1400068bc  mov     [rsp+88h+var_60], 0Eh
0x1400068c4  mov     [rsp+88h+var_68], 4
0x1400068c9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400068ce  jmp     loc_1400065DA
```
