# CAdapter::PrepareDeviceForSystemPowerTargetSxStateFromWdfPowerCallback(ulong,bool)

- ea: `0x140055990`
- end: `0x140055d0f`
- name: `?PrepareDeviceForSystemPowerTargetSxStateFromWdfPowerCallback@CAdapter@@QEAAJK_N@Z`
- size: `895`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400ce1f0`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x14001a1e0`
- `0x14001a20c`
- `0x14001dec0`
- `0x14002b148`
- `0x1400520a8`
- `0x140055990`
- `0x1400693f4`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CAdapter::PrepareDeviceForSystemPowerTargetSxStateFromWdfPowerCallback(
        CAdapter *this,
        int a2,
        bool a3)
{
  int v5; // edx
  CJobBase *v6; // rbx
  unsigned int NextActivityId; // eax
  unsigned int v8; // r9d
  int v9; // edx
  unsigned int started; // esi
  int v12; // edx
  _QWORD *v13; // rsi
  int v14; // eax
  int v15; // edx
  unsigned int v16; // r14d
  int v17; // edx
  int v18; // edx
  int v19; // esi
  _QWORD *v20[2]; // [rsp+30h] [rbp-10h] BYREF
  int v21; // [rsp+78h] [rbp+38h] BYREF
  struct IEventContext *v22; // [rsp+88h] [rbp+48h] BYREF

  v21 = a2;
  v6 = (CJobBase *)operator new(0x238u);
  if ( !v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        107,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    }
    return 3221225626LL;
  }
  NextActivityId = IActivityId::get_NextActivityId();
  CJobBase::CJobBase(v6, NextActivityId);
  *((_QWORD *)v6 + 67) = 0;
  *(_QWORD *)v6 = &CDevicePrepareForSystemPowerTargetToSxStateJob::`vftable'{for `IOperationCompletionCallback'};
  *((_QWORD *)v6 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
  *((_QWORD *)v6 + 68) = 0;
  *((_BYTE *)v6 + 552) = 0;
  *((_DWORD *)v6 + 139) = 0;
  *((_QWORD *)v6 + 70) = 0;
  *((_BYTE *)v6 + 42) = 1;
  started = CDevicePrepareForSystemPowerTargetToSxStateJob::InitializeFromWdfCallback(v6, this, a3, v8);
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        108,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    }
    goto LABEL_5;
  }
  *((_BYTE *)v6 + 507) = 0;
  v13 = operator new(0x18u);
  if ( !v13 )
  {
    v20[0] = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        109,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    }
    wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(v20, 0);
    (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    return 3221225626LL;
  }
  v13[1] = 0;
  *v13 = &CJobCompleteNotifier::`vftable';
  v13[2] = 0;
  v22 = 0;
  v20[0] = v13;
  v14 = IEventContext::CreateInstance(&v22);
  v16 = v14;
  if ( !v14 )
  {
    v21 = 0;
    v13[1] = v22;
    v13[2] = &v21;
    started = ActiveJobsList::StartAddNewJob(
                (CAdapter *)((char *)this + 928),
                v6,
                (struct IOperationCompletionCallback *)v13,
                0);
    if ( !started )
    {
      v20[0] = 0;
      (*(void (__fastcall **)(struct IEventContext *))(*(_QWORD *)v22 + 24LL))(v22);
      v19 = v21;
      if ( v21 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          1,
          113,
          (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
          v21);
      }
      started = v19 != 0 ? 0xC0000001 : 0;
      if ( v22 )
      {
        (**(void (__fastcall ***)(struct IEventContext *, __int64))v22)(v22, 1);
        v22 = 0;
      }
      wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(v20, 0);
      (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
      return started;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        112,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    }
    if ( v22 )
    {
      (**(void (__fastcall ***)(struct IEventContext *, __int64))v22)(v22, 1);
      v22 = 0;
    }
    wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(v20, 0);
LABEL_5:
    (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    return started;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      110,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
      v14,
      v20[0]);
  }
  if ( v22 )
  {
    (**(void (__fastcall ***)(struct IEventContext *, __int64))v22)(v22, 1);
    v22 = 0;
  }
  wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(v20, 0);
  (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
  return v16;
}

```

## disassembly

```asm
0x140055990  mov     [rsp-28h+arg_0], rbx
0x140055995  mov     [rsp-28h+arg_10], rsi
0x14005599a  mov     [rsp-28h+arg_8], edx
0x14005599e  push    rbp
0x14005599f  push    rdi
0x1400559a0  push    r12
0x1400559a2  push    r14
0x1400559a4  push    r15
0x1400559a6  mov     rbp, rsp
0x1400559a9  sub     rsp, 40h
0x1400559ad  mov     r15, rcx
0x1400559b0  mov     sil, r8b
0x1400559b3  mov     ecx, 238h; unsigned __int64
0x1400559b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400559bd  xor     r12d, r12d
0x1400559c0  mov     rbx, rax
0x1400559c3  test    rax, rax
0x1400559c6  jz      loc_140055CB8
0x1400559cc  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x1400559d1  mov     edx, eax; unsigned int
0x1400559d3  mov     rcx, rbx; this
0x1400559d6  call    ??0CJobBase@@IEAA@K@Z; CJobBase::CJobBase(ulong)
0x1400559db  lea     rcx, ??_7CDevicePrepareForSystemPowerTargetToSxStateJob@@6BIOperationCompletionCallback@@@; const CDevicePrepareForSystemPowerTargetToSxStateJob::`vftable'{for `IOperationCompletionCallback'}
0x1400559e2  mov     [rbx+218h], r12
0x1400559e9  mov     [rbx], rcx
0x1400559ec  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400559f3  lea     edi, [r12+1]
0x1400559f8  mov     [rbx+8], rax
0x1400559fc  mov     rcx, rbx; this
0x1400559ff  mov     [rbx+220h], r12
0x140055a06  mov     r8b, sil; bool
0x140055a09  mov     [rbx+228h], r12b
0x140055a10  mov     rdx, r15; struct CAdapter *
0x140055a13  mov     [rbx+22Ch], r12d
0x140055a1a  mov     [rbx+230h], r12
0x140055a21  mov     [rbx+2Ah], dil
0x140055a25  call    ?InitializeFromWdfCallback@CDevicePrepareForSystemPowerTargetToSxStateJob@@QEAAHPEAVCAdapter@@_NK@Z; CDevicePrepareForSystemPowerTargetToSxStateJob::InitializeFromWdfCallback(CAdapter *,bool,ulong)
0x140055a2a  mov     esi, eax
0x140055a2c  test    eax, eax
0x140055a2e  jz      short loc_140055A7E
0x140055a30  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055a37  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055a3e  jz      short loc_140055A66
0x140055a40  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055a47  mov     r8d, edi
0x140055a4a  mov     [rsp+40h+var_20], rcx
0x140055a4f  lea     r9d, [r12+6Ch]
0x140055a54  mov     rcx, cs:WPP_GLOBAL_Control
0x140055a5b  mov     dl, 2
0x140055a5d  mov     rcx, [rcx+40h]
0x140055a61  call    WPP_RECORDER_SF_
0x140055a66  mov     rax, [rbx]
0x140055a69  mov     rax, [rax+28h]
0x140055a6d  mov     edx, edi
0x140055a6f  mov     rcx, rbx
0x140055a72  call    _guard_dispatch_icall
0x140055a77  mov     eax, esi
0x140055a79  jmp     loc_140055CF5
0x140055a7e  mov     ecx, 18h; unsigned __int64
0x140055a83  mov     [rbx+1FBh], r12b
0x140055a8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140055a8f  mov     rsi, rax
0x140055a92  test    rax, rax
0x140055a95  jz      loc_140055C5F
0x140055a9b  lea     rax, ??_7CJobCompleteNotifier@@6B@; const CJobCompleteNotifier::`vftable'
0x140055aa2  mov     [rsi+8], r12
0x140055aa6  mov     [rsi], rax
0x140055aa9  lea     rcx, [rbp+arg_18]; struct IEventContext **
0x140055aad  mov     [rsi+10h], r12
0x140055ab1  mov     [rbp+arg_18], r12
0x140055ab5  mov     [rbp+var_10], rsi
0x140055ab9  call    ?CreateInstance@IEventContext@@SAHPEAPEAV1@@Z; IEventContext::CreateInstance(IEventContext * *)
0x140055abe  mov     r14d, eax
0x140055ac1  test    eax, eax
0x140055ac3  jz      short loc_140055B3E
0x140055ac5  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055acc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055ad3  jz      short loc_140055B00
0x140055ad5  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055adc  mov     [rsp+40h+var_18], eax
0x140055ae0  mov     [rsp+40h+var_20], rcx
0x140055ae5  mov     r9d, 6Eh ; 'n'
0x140055aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140055af2  mov     r8d, edi
0x140055af5  mov     dl, 2
0x140055af7  mov     rcx, [rcx+40h]
0x140055afb  call    WPP_RECORDER_SF_d
0x140055b00  mov     rcx, [rbp+arg_18]
0x140055b04  test    rcx, rcx
0x140055b07  jz      short loc_140055B1A
0x140055b09  mov     rax, [rcx]
0x140055b0c  mov     edx, edi
0x140055b0e  mov     rax, [rax]
0x140055b11  call    _guard_dispatch_icall
0x140055b16  mov     [rbp+arg_18], r12
0x140055b1a  xor     edx, edx
0x140055b1c  lea     rcx, [rbp+var_10]
0x140055b20  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x140055b25  mov     rax, [rbx]
0x140055b28  mov     edx, edi
0x140055b2a  mov     rcx, rbx
0x140055b2d  mov     rax, [rax+28h]
0x140055b31  call    _guard_dispatch_icall
0x140055b36  mov     eax, r14d
0x140055b39  jmp     loc_140055CF5
0x140055b3e  mov     rax, [rbp+arg_18]
0x140055b42  lea     rcx, [r15+3A0h]; this
0x140055b49  mov     [rbp+arg_8], r12d
0x140055b4d  xor     r9d, r9d; void *
0x140055b50  mov     [rsi+8], rax
0x140055b54  mov     r8, rsi; struct IOperationCompletionCallback *
0x140055b57  lea     rax, [rbp+arg_8]
0x140055b5b  mov     rdx, rbx; struct CJobBase *
0x140055b5e  mov     [rsi+10h], rax
0x140055b62  call    ?StartAddNewJob@ActiveJobsList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@PEAX@Z; ActiveJobsList::StartAddNewJob(CJobBase *,IOperationCompletionCallback *,void *)
0x140055b67  mov     esi, eax
0x140055b69  test    eax, eax
0x140055b6b  jz      short loc_140055BCE
0x140055b6d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055b74  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055b7b  jz      short loc_140055BA4
0x140055b7d  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055b84  mov     r9d, 70h ; 'p'
0x140055b8a  mov     [rsp+40h+var_20], rcx
0x140055b8f  mov     r8d, edi
0x140055b92  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b99  mov     dl, 2
0x140055b9b  mov     rcx, [rcx+40h]
0x140055b9f  call    WPP_RECORDER_SF_
0x140055ba4  mov     rcx, [rbp+arg_18]
0x140055ba8  test    rcx, rcx
0x140055bab  jz      short loc_140055BBE
0x140055bad  mov     rax, [rcx]
0x140055bb0  mov     edx, edi
0x140055bb2  mov     rax, [rax]
0x140055bb5  call    _guard_dispatch_icall
0x140055bba  mov     [rbp+arg_18], r12
0x140055bbe  xor     edx, edx
0x140055bc0  lea     rcx, [rbp+var_10]
0x140055bc4  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x140055bc9  jmp     loc_140055A66
0x140055bce  mov     rcx, [rbp+arg_18]
0x140055bd2  mov     [rbp+var_10], r12
0x140055bd6  mov     rax, [rcx]
0x140055bd9  mov     rax, [rax+18h]
0x140055bdd  call    _guard_dispatch_icall
0x140055be2  mov     esi, [rbp+arg_8]
0x140055be5  test    esi, esi
0x140055be7  jz      short loc_140055C24
0x140055be9  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055bf0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055bf7  jz      short loc_140055C24
0x140055bf9  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055c00  mov     [rsp+40h+var_18], esi
0x140055c04  mov     [rsp+40h+var_20], rcx
0x140055c09  mov     r9d, 71h ; 'q'
0x140055c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c16  mov     r8d, edi
0x140055c19  mov     dl, 2
0x140055c1b  mov     rcx, [rcx+40h]
0x140055c1f  call    WPP_RECORDER_SF_d
0x140055c24  mov     rcx, [rbp+arg_18]
0x140055c28  neg     esi
0x140055c2a  sbb     esi, esi
0x140055c2c  and     esi, 0C0000001h
0x140055c32  test    rcx, rcx
0x140055c35  jz      short loc_140055C48
0x140055c37  mov     rax, [rcx]
0x140055c3a  mov     edx, edi
0x140055c3c  mov     rax, [rax]
0x140055c3f  call    _guard_dispatch_icall
0x140055c44  mov     [rbp+arg_18], r12
0x140055c48  xor     edx, edx
0x140055c4a  lea     rcx, [rbp+var_10]
0x140055c4e  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x140055c53  mov     rcx, [rbx]
0x140055c56  mov     rax, [rcx+28h]
0x140055c5a  jmp     loc_140055A6D
0x140055c5f  mov     [rbp+var_10], r12
0x140055c63  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055c6a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055c71  jz      short loc_140055C9A
0x140055c73  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055c7a  mov     r9d, 6Dh ; 'm'
0x140055c80  mov     [rsp+40h+var_20], rcx
0x140055c85  mov     r8d, edi
0x140055c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c8f  mov     dl, 2
0x140055c91  mov     rcx, [rcx+40h]
0x140055c95  call    WPP_RECORDER_SF_
0x140055c9a  xor     edx, edx
0x140055c9c  lea     rcx, [rbp+var_10]
0x140055ca0  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x140055ca5  mov     rax, [rbx]
0x140055ca8  mov     edx, edi
0x140055caa  mov     rcx, rbx
0x140055cad  mov     rax, [rax+28h]
0x140055cb1  call    _guard_dispatch_icall
0x140055cb6  jmp     short loc_140055CF0
0x140055cb8  lea     rcx, WPP_RECORDER_INITIALIZED
0x140055cbf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140055cc6  jz      short loc_140055CF0
0x140055cc8  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140055ccf  mov     r9d, 6Bh ; 'k'
0x140055cd5  mov     [rsp+40h+var_20], rcx
0x140055cda  mov     dl, 2
0x140055cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ce3  lea     r8d, [r9-6Ah]
0x140055ce7  mov     rcx, [rcx+40h]
0x140055ceb  call    WPP_RECORDER_SF_
0x140055cf0  mov     eax, 0C000009Ah
0x140055cf5  lea     r11, [rsp+40h+var_s0]
0x140055cfa  mov     rbx, [r11+30h]
0x140055cfe  mov     rsi, [r11+40h]
0x140055d02  mov     rsp, r11
0x140055d05  pop     r15
0x140055d07  pop     r14
0x140055d09  pop     r12
0x140055d0b  pop     rdi
0x140055d0c  pop     rbp
0x140055d0d  retn
```
