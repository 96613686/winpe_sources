# MpPostRead

- ea: `0x140001550`
- end: `0x1400018a1`
- name: `MpPostRead`
- size: `849`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140001550`
- `0x1400018a4`
- `0x140003af0`
- `0x14000a760`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x1400544a0`
- `0x14005a490`

## import_xrefs

- `ntoskrnl!KeIsExecutingDpc` at `0x1400015d0`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400015d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400015e4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400015e4`
- `ntoskrnl!PsInitialSystemProcess` at `0x140001811`
- `ntoskrnl!IoThreadToProcess` at `0x140001647`
- `ntoskrnl!IoThreadToProcess` at `0x14000166f`
- `ntoskrnl!IoThreadToProcess` at `0x14000182a`
- `ntoskrnl!IoThreadToProcess` at `0x140001647`
- `ntoskrnl!IoThreadToProcess` at `0x14000166f`
- `ntoskrnl!IoThreadToProcess` at `0x14000182a`
- `FLTMGR!FltReleaseContext` at `0x1400016b1`
- `FLTMGR!FltReleaseContext` at `0x1400016b1`
- `FLTMGR!FltGetRequestorProcess` at `0x14000173a`
- `FLTMGR!FltGetRequestorProcess` at `0x14000173a`
- `FLTMGR!FltGetStreamContext` at `0x140001618`
- `FLTMGR!FltGetStreamContext` at `0x140001618`

## pseudocode

```c
__int64 __fastcall MpPostRead(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  __int64 v5; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _FILE_OBJECT *v8; // rdx
  struct _KPROCESS *v9; // rdi
  struct _KPROCESS *v10; // rdi
  __int64 v11; // rcx
  int v13; // edi
  struct _KPROCESS *RequestorProcess; // rax
  struct _KPROCESS *v15; // rdi
  int ProcessContextByObject; // r14d
  int v17; // eax
  PEPROCESS v18; // rax
  PETHREAD Thread; // rdi
  struct _DEVICE_OBJECT *AttachedDevice; // rsi
  int RequestorProcessId; // eax
  _BYTE v22[8]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp-40h]
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-38h] BYREF

  Context = 0;
  v5 = 0;
  v22[0] = 0;
  v23 = 0;
  if ( (a4 & 1) == 0 && CallbackData->IoStatus.Status >= 0 )
  {
    if ( CallbackData->IoStatus.Information )
    {
      Iopb = CallbackData->Iopb;
      if ( (Iopb->MinorFunction & 6) != 6
        && (Iopb->IrpFlags & 3) == 0
        && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 8) == 0 )
      {
        if ( !(unsigned int)KeIsExecutingDpc() && KeGetCurrentIrql() <= 1u )
        {
          if ( CallbackData->Thread )
          {
            v8 = *(struct _FILE_OBJECT **)(a2 + 32);
            if ( v8 )
            {
              if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), v8, &Context) >= 0 )
              {
                v9 = *(struct _KPROCESS **)(MpData + 232);
                if ( IoThreadToProcess(KeGetCurrentThread()) != v9 )
                {
                  v10 = *(struct _KPROCESS **)(MpData + 256);
                  if ( IoThreadToProcess(KeGetCurrentThread()) != v10 )
                    _InterlockedOr((volatile signed __int32 *)Context + 12, 0x800u);
                }
                v11 = *((_QWORD *)Context + 1);
                if ( (*(_BYTE *)(v11 + 448) & 0x20) == 0 )
                {
                  v13 = *(_DWORD *)(MpData + 868);
                  MpSeqDetectCtxUpdate(
                    v11,
                    CallbackData->Thread,
                    *(_QWORD *)(a2 + 32),
                    &CallbackData->Iopb->Parameters.QuerySecurity.SecurityBuffer,
                    CallbackData->IoStatus.Information,
                    (__int64)v22);
                  if ( (v13 & 0x1000) != 0 )
                  {
                    if ( v22[0] )
                    {
                      RequestorProcess = FltGetRequestorProcess(CallbackData);
                      v15 = RequestorProcess;
                      if ( *(_DWORD *)(MpData + 4076) )
                      {
                        if ( RequestorProcess == PsInitialSystemProcess )
                        {
                          v18 = IoThreadToProcess(KeGetCurrentThread());
                          if ( v15 != v18 )
                            v15 = v18;
                        }
                      }
                      ProcessContextByObject = MpGetProcessContextByObject(v15);
                      if ( ProcessContextByObject < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                        {
                          _mm_lfence();
                          Thread = CallbackData->Thread;
                          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                          RequestorProcessId = MpGetRequestorProcessId(CallbackData);
                          WPP_SF_qDD(
                            AttachedDevice,
                            25,
                            WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids,
                            Thread,
                            RequestorProcessId,
                            ProcessContextByObject);
                        }
                        v5 = v23;
                      }
                      else
                      {
                        _mm_lfence();
                        v5 = v23;
                        v17 = MpSendFileAsyncMessage(
                                6,
                                (_DWORD)CallbackData,
                                a2,
                                *(_DWORD *)(*((_QWORD *)Context + 1) + 84LL),
                                -1,
                                0,
                                *(_QWORD *)(a2 + 40),
                                0,
                                v23,
                                0,
                                0);
                        if ( v17 < 0
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                        {
                          _mm_lfence();
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            26,
                            WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids,
                            (unsigned int)v17);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        if ( Context )
          FltReleaseContext(Context);
        if ( v5 )
          MpReleaseProcessContext(v5);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140001550  push    rbx
0x140001552  push    rbp
0x140001553  push    rsi
0x140001554  push    r15
0x140001556  sub     rsp, 88h
0x14000155d  mov     rax, cs:__security_cookie
0x140001564  xor     rax, rsp
0x140001567  mov     [rsp+0A8h+var_30], rax
0x14000156c  xor     r15d, r15d
0x14000156f  mov     rbp, rdx
0x140001572  mov     [rsp+0A8h+Context], r15
0x140001577  mov     esi, r15d
0x14000157a  mov     [rsp+0A8h+var_48], sil
0x14000157f  mov     rbx, rcx
0x140001582  mov     [rsp+0A8h+var_40], r15
0x140001587  test    r9b, 1
0x14000158b  jnz     loc_1400016CA
0x140001591  cmp     [rcx+18h], esi
0x140001594  jl      loc_1400016CA
0x14000159a  cmp     [rcx+20h], r15
0x14000159e  jz      loc_1400016CA
0x1400015a4  mov     rcx, [rcx+10h]
0x1400015a8  movzx   eax, byte ptr [rcx+5]
0x1400015ac  and     al, 6
0x1400015ae  cmp     al, 6
0x1400015b0  jz      loc_1400016CA
0x1400015b6  mov     eax, [rcx]
0x1400015b8  test    al, 3
0x1400015ba  jnz     loc_1400016CA
0x1400015c0  mov     rax, [rdx+20h]
0x1400015c4  mov     ecx, [rax+50h]
0x1400015c7  test    cl, 8
0x1400015ca  jnz     loc_1400016CA
0x1400015d0  call    cs:__imp_KeIsExecutingDpc
0x1400015d7  nop     dword ptr [rax+rax+00h]
0x1400015dc  test    eax, eax
0x1400015de  jnz     loc_1400016A7
0x1400015e4  call    cs:__imp_KeGetCurrentIrql
0x1400015eb  nop     dword ptr [rax+rax+00h]
0x1400015f0  cmp     al, 1
0x1400015f2  ja      loc_1400016A7
0x1400015f8  cmp     [rbx+8], r15
0x1400015fc  jz      loc_1400016A7
0x140001602  mov     rdx, [rbp+20h]; FileObject
0x140001606  test    rdx, rdx
0x140001609  jz      loc_1400016A7
0x14000160f  mov     rcx, [rbp+18h]; Instance
0x140001613  lea     r8, [rsp+0A8h+Context]; Context
0x140001618  call    cs:__imp_FltGetStreamContext
0x14000161f  nop     dword ptr [rax+rax+00h]
0x140001624  test    eax, eax
0x140001626  js      short loc_1400016A7
0x140001628  mov     rcx, gs:188h; Thread
0x140001631  mov     rax, cs:MpData
0x140001638  mov     [rsp+0A8h+arg_10], rdi
0x140001640  mov     rdi, [rax+0E8h]
0x140001647  call    cs:__imp_IoThreadToProcess
0x14000164e  nop     dword ptr [rax+rax+00h]
0x140001653  cmp     rax, rdi
0x140001656  jz      short loc_14000168D
0x140001658  mov     rcx, gs:188h; Thread
0x140001661  mov     rax, cs:MpData
0x140001668  mov     rdi, [rax+100h]
0x14000166f  call    cs:__imp_IoThreadToProcess
0x140001676  nop     dword ptr [rax+rax+00h]
0x14000167b  cmp     rax, rdi
0x14000167e  jz      short loc_14000168D
0x140001680  mov     rax, [rsp+0A8h+Context]
0x140001685  lock or dword ptr [rax+30h], 800h
0x14000168d  mov     rax, [rsp+0A8h+Context]
0x140001692  mov     rcx, [rax+8]
0x140001696  test    byte ptr [rcx+1C0h], 20h
0x14000169d  jz      short loc_1400016E7
0x14000169f  mov     rdi, [rsp+0A8h+arg_10]
0x1400016a7  mov     rcx, [rsp+0A8h+Context]; Context
0x1400016ac  test    rcx, rcx
0x1400016af  jz      short loc_1400016BD
0x1400016b1  call    cs:__imp_FltReleaseContext
0x1400016b8  nop     dword ptr [rax+rax+00h]
0x1400016bd  test    rsi, rsi
0x1400016c0  jz      short loc_1400016CA
0x1400016c2  mov     rcx, rsi
0x1400016c5  call    MpReleaseProcessContext
0x1400016ca  xor     eax, eax
0x1400016cc  mov     rcx, [rsp+0A8h+var_30]
0x1400016d1  xor     rcx, rsp; StackCookie
0x1400016d4  call    __security_check_cookie
0x1400016d9  add     rsp, 88h
0x1400016e0  pop     r15
0x1400016e2  pop     rsi
0x1400016e3  pop     rbp
0x1400016e4  pop     rbx
0x1400016e5  retn
0x1400016e7  mov     rax, cs:MpData
0x1400016ee  mov     edi, [rax+364h]
0x1400016f4  lea     rax, [rsp+0A8h+var_48]
0x1400016f9  mov     r9, [rbx+10h]
0x1400016fd  mov     r8, [rbp+20h]
0x140001701  add     r9, 28h ; '('
0x140001705  mov     rdx, [rbx+8]
0x140001709  mov     [rsp+0A8h+var_80], rax
0x14000170e  mov     eax, [rbx+20h]
0x140001711  mov     [rsp+0A8h+var_88], eax
0x140001715  call    MpSeqDetectCtxUpdate
0x14000171a  bt      edi, 0Ch
0x14000171e  jnb     loc_14000169F
0x140001724  cmp     [rsp+0A8h+var_48], sil
0x140001729  jz      loc_14000169F
0x14000172f  mov     rcx, rbx; CallbackData
0x140001732  mov     [rsp+0A8h+var_28], r14
0x14000173a  call    cs:__imp_FltGetRequestorProcess
0x140001741  nop     dword ptr [rax+rax+00h]
0x140001746  mov     rcx, cs:MpData
0x14000174d  mov     rdi, rax
0x140001750  cmp     [rcx+0FECh], esi
0x140001756  jnz     loc_140001811
0x14000175c  lea     rdx, [rsp+0A8h+var_40]
0x140001761  mov     rcx, rdi; Process
0x140001764  call    MpGetProcessContextByObject
0x140001769  mov     r14d, eax
0x14000176c  test    eax, eax
0x14000176e  js      loc_140001842
0x140001774  lfence
0x140001777  mov     rax, [rsp+0A8h+Context]
0x14000177c  mov     r8, rbp
0x14000177f  mov     rsi, [rsp+0A8h+var_40]
0x140001784  mov     rdx, rbx
0x140001787  mov     [rsp+0A8h+var_58], r15
0x14000178c  mov     ecx, 6
0x140001791  mov     [rsp+0A8h+var_60], r15
0x140001796  mov     r9, [rax+8]
0x14000179a  mov     rax, [rbp+28h]
0x14000179e  mov     [rsp+0A8h+var_68], rsi
0x1400017a3  mov     [rsp+0A8h+var_70], r15
0x1400017a8  mov     r9d, [r9+54h]
0x1400017ac  mov     [rsp+0A8h+var_78], rax
0x1400017b1  mov     dword ptr [rsp+0A8h+var_80], r15d
0x1400017b6  mov     [rsp+0A8h+var_88], 0FFFFFFFFh
0x1400017be  call    MpSendFileAsyncMessage
0x1400017c3  test    eax, eax
0x1400017c5  jns     short loc_140001804
0x1400017c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017ce  lea     rdx, WPP_GLOBAL_Control
0x1400017d5  cmp     rcx, rdx
0x1400017d8  jz      short loc_140001804
0x1400017da  mov     ecx, [rcx+2Ch]
0x1400017dd  test    cl, 2
0x1400017e0  jz      short loc_140001804
0x1400017e2  lfence
0x1400017e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017ec  lea     r8, WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids
0x1400017f3  mov     edx, 1Ah
0x1400017f8  mov     r9d, eax
0x1400017fb  mov     rcx, [rcx+18h]
0x1400017ff  call    WPP_SF_d
0x140001804  mov     r14, [rsp+0A8h+var_28]
0x14000180c  jmp     loc_14000169F
0x140001811  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140001818  cmp     rdi, [rcx]
0x14000181b  jnz     loc_14000175C
0x140001821  mov     rcx, gs:188h; Thread
0x14000182a  call    cs:__imp_IoThreadToProcess
0x140001831  nop     dword ptr [rax+rax+00h]
0x140001836  cmp     rdi, rax
0x140001839  cmovnz  rdi, rax
0x14000183d  jmp     loc_14000175C
0x140001842  mov     rax, cs:WPP_GLOBAL_Control
0x140001849  lea     rdx, WPP_GLOBAL_Control
0x140001850  cmp     rax, rdx
0x140001853  jz      short loc_140001897
0x140001855  mov     edx, [rax+2Ch]
0x140001858  test    dl, 2
0x14000185b  jz      short loc_140001897
0x14000185d  lfence
0x140001860  mov     rax, cs:WPP_GLOBAL_Control
0x140001867  mov     rcx, rbx
0x14000186a  mov     rdi, [rbx+8]
0x14000186e  mov     rsi, [rax+18h]
0x140001872  call    MpGetRequestorProcessId
0x140001877  mov     edx, 19h
0x14000187c  mov     dword ptr [rsp+0A8h+var_80], r14d
0x140001881  mov     r9, rdi
0x140001884  mov     [rsp+0A8h+var_88], eax
0x140001888  lea     r8, WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids
0x14000188f  mov     rcx, rsi
0x140001892  call    WPP_SF_qDD
0x140001897  mov     rsi, [rsp+0A8h+var_40]
0x14000189c  jmp     loc_140001804
```
