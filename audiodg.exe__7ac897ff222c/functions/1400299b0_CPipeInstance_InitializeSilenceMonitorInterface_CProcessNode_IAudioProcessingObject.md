# CPipeInstance::InitializeSilenceMonitorInterface(CProcessNode *,IAudioProcessingObject *)

- ea: `0x1400299b0`
- end: `0x140029b1b`
- name: `?InitializeSilenceMonitorInterface@CPipeInstance@@AEAAJPEAVCProcessNode@@PEAUIAudioProcessingObject@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(CPipeInstance *__hidden this, struct CProcessNode *, struct IAudioProcessingObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001e5b4`

## callees

- `0x14000e11c`
- `0x1400299b0`
- `0x140055de0`
- `0x14005d0e0`
- `0x140069128`
- `0x1400b5010`

## import_xrefs

- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x140029a82`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromMMDeviceId` at `0x140029a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029a20`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPipeInstance::InitializeSilenceMonitorInterface(
        CPipeInstance *this,
        struct CProcessNode *a2,
        struct IAudioProcessingObject *a3)
{
  int v5; // ebx
  LPVOID pv; // [rsp+20h] [rbp-50h] BYREF
  __int64 v8; // [rsp+28h] [rbp-48h] BYREF
  int v9; // [rsp+30h] [rbp-40h] BYREF
  GUID v10; // [rsp+34h] [rbp-3Ch]
  _BYTE v11[36]; // [rsp+44h] [rbp-2Ch] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  memset(v11, 0, sizeof(v11));
  pv = 0;
  if ( ((__int64 (__fastcall *)(struct IAudioProcessingObject *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
         a3,
         &GUID_22150b0d_ab8e_4f85_bd9a_8580e3b290f1,
         &v8) >= 0 )
  {
    v9 = 56;
    v10 = GUID_693badea_1eb1_4013_b799_285f624a55bd;
    mmdDevGetInstanceIdFromMMDeviceId(*((_QWORD *)this + 24), &pv);
    *(_QWORD *)&v11[4] = pv;
    *(_OWORD *)&v11[12] = *(_OWORD *)((char *)this + 296);
    *(_QWORD *)&v11[28] = AudioDgTelemetryProvider::Provider();
    v5 = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, __int64, int *))a3->lpVtbl->Initialize)(a3, 56, &v9);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids,
          (unsigned int)v5);
      }
      AudDGTraceLoggingErrorHelper("CPipeInstance::InitializeSilenceMonitorInterface", 0xF78u, v5);
    }
  }
  else
  {
    v5 = 0;
  }
  CoTaskMemFree(pv);
  pv = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400299b0  mov     [rsp-8+arg_8], rbx
0x1400299b5  mov     [rsp-8+arg_18], rdi
0x1400299ba  push    rbp
0x1400299bb  mov     rbp, rsp
0x1400299be  sub     rsp, 70h
0x1400299c2  mov     rax, cs:__security_cookie
0x1400299c9  xor     rax, rsp
0x1400299cc  mov     [rbp+var_8], rax
0x1400299d0  mov     rbx, r8
0x1400299d3  mov     rdi, rcx
0x1400299d6  mov     [rbp+var_48], 0
0x1400299de  mov     [rbp+var_40], 0
0x1400299e5  xor     eax, eax
0x1400299e7  xorps   xmm0, xmm0
0x1400299ea  movups  [rbp+var_3C], xmm0
0x1400299ee  movups  [rbp+var_2C], xmm0
0x1400299f2  movups  [rbp+var_1C], xmm0
0x1400299f6  mov     [rbp+var_C], eax
0x1400299f9  mov     [rbp+pv], rax
0x1400299fd  mov     rax, [r8]
0x140029a00  lea     r8, [rbp+var_48]
0x140029a04  lea     rdx, _GUID_22150b0d_ab8e_4f85_bd9a_8580e3b290f1
0x140029a0b  mov     rcx, rbx
0x140029a0e  mov     rax, [rax]
0x140029a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a16  test    eax, eax
0x140029a18  jns     short loc_140029A64
0x140029a1a  xor     ebx, ebx
0x140029a1c  mov     rcx, [rbp+pv]; pv
0x140029a20  call    cs:__imp_CoTaskMemFree
0x140029a26  mov     [rbp+pv], 0
0x140029a2e  mov     rcx, [rbp+var_48]
0x140029a32  test    rcx, rcx
0x140029a35  jz      short loc_140029A44
0x140029a37  mov     rax, [rcx]
0x140029a3a  mov     rax, [rax+10h]
0x140029a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a43  nop
0x140029a44  mov     eax, ebx
0x140029a46  mov     rcx, [rbp+var_8]
0x140029a4a  xor     rcx, rsp; StackCookie
0x140029a4d  call    __security_check_cookie
0x140029a52  lea     r11, [rsp+70h+var_s0]
0x140029a57  mov     rbx, [r11+18h]
0x140029a5b  mov     rdi, [r11+28h]
0x140029a5f  mov     rsp, r11
0x140029a62  pop     rbp
0x140029a63  retn
0x140029a64  mov     [rbp+var_40], 38h ; '8'
0x140029a6b  movups  xmm0, xmmword ptr cs:_GUID_693badea_1eb1_4013_b799_285f624a55bd.Data1
0x140029a72  movdqu  [rbp+var_3C], xmm0
0x140029a77  lea     rdx, [rbp+pv]
0x140029a7b  mov     rcx, [rdi+0C0h]
0x140029a82  call    cs:__imp_mmdDevGetInstanceIdFromMMDeviceId
0x140029a88  mov     rax, [rbp+pv]
0x140029a8c  mov     qword ptr [rbp+var_2C+4], rax
0x140029a90  movups  xmm0, xmmword ptr [rdi+128h]
0x140029a97  movdqu  [rbp+var_2C+0Ch], xmm0
0x140029a9c  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140029aa1  mov     qword ptr [rbp+var_1C+0Ch], rax
0x140029aa5  mov     rax, [rbx]
0x140029aa8  lea     r8, [rbp+var_40]
0x140029aac  mov     edx, 38h ; '8'
0x140029ab1  mov     rcx, rbx
0x140029ab4  mov     rax, [rax+30h]
0x140029ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029abd  mov     ebx, eax
0x140029abf  test    eax, eax
0x140029ac1  jns     loc_140029A1C
0x140029ac7  lea     rax, WPP_GLOBAL_Control
0x140029ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ad5  cmp     rcx, rax
0x140029ad8  jz      short loc_140029B01
0x140029ada  test    dword ptr [rcx+1Ch], 20000h
0x140029ae1  jz      short loc_140029B01
0x140029ae3  cmp     byte ptr [rcx+19h], 2
0x140029ae7  jb      short loc_140029B01
0x140029ae9  mov     edx, 31h ; '1'
0x140029aee  mov     r9d, ebx
0x140029af1  lea     r8, WPP_6325c7141cbf3fd739349202f957ecc0_Traceguids
0x140029af8  mov     rcx, [rcx+10h]
0x140029afc  call    WPP_SF_d
0x140029b01  mov     r8d, ebx; int
0x140029b04  mov     edx, 0F78h; unsigned int
0x140029b09  lea     rcx, aCpipeinstanceI_0; "CPipeInstance::InitializeSilenceMonitor"...
0x140029b10  call    ?AudDGTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudDGTraceLoggingErrorHelper(char const *,uint,long)
0x140029b15  jmp     loc_140029A1C
```
