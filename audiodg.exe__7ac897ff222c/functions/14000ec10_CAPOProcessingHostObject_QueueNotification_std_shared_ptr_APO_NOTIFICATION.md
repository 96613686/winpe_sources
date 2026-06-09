# CAPOProcessingHostObject::QueueNotification(std::shared_ptr<APO_NOTIFICATION> &)

- ea: `0x14000ec10`
- end: `0x14000ef02`
- name: `?QueueNotification@CAPOProcessingHostObject@@QEAAXAEAV?$shared_ptr@UAPO_NOTIFICATION@@@std@@@Z`
- size: `754`
- prototype: ``
- caller_count: `12`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x14000ea00`
- `0x140022a60`
- `0x140023458`
- `0x1400235dc`
- `0x14002cf6c`
- `0x140039f54`
- `0x140056f10`
- `0x14005808c`
- `0x140059804`
- `0x14005ab10`
- `0x14005b320`
- `0x14005b670`

## callees

- `0x14000ec10`
- `0x14000f1a4`
- `0x14000f294`
- `0x14000f36c`
- `0x14000f3b8`
- `0x14000f3f8`
- `0x14005d104`
- `0x14005d148`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ece1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ece1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ec35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ec35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eea4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000eebf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000eebf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000ee96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000ee96`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CAPOProcessingHostObject::QueueNotification(struct _RTL_CRITICAL_SECTION *a1, __int64 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 (__fastcall ***SpinCount)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall **v6)(_QWORD, GUID *, _QWORD **); // rax
  int v7; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r15
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  unsigned int v14; // edx
  _QWORD *v15; // rsi
  _DWORD *v16; // rdi
  std::_Ref_count_base *v17; // rcx
  signed int v18; // ebx
  _BYTE *v19; // rdx
  struct _TP_WORK *ThreadpoolWork; // rbx
  signed int LastError; // eax
  bool v22; // sf
  _QWORD *v23; // rdx
  int v24; // [rsp+20h] [rbp-79h]
  _QWORD v25[7]; // [rsp+30h] [rbp-69h] BYREF
  _QWORD *v26; // [rsp+68h] [rbp-31h]
  _DWORD *v27; // [rsp+70h] [rbp-29h]
  _BYTE v28[56]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE *v29; // [rsp+B0h] [rbp+17h]
  __int128 v30; // [rsp+B8h] [rbp+1Fh]
  __int64 v31; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  _QWORD *v33; // [rsp+100h] [rbp+67h] BYREF
  __int64 v34; // [rsp+110h] [rbp+77h] BYREF
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+118h] [rbp+7Fh]

  v4 = a1 + 1;
  EnterCriticalSection(a1 + 1);
  v35 = v4;
  if ( a1[2].DebugInfo )
  {
    SpinCount = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))a1->SpinCount;
    v34 = 0;
    v6 = *SpinCount;
    v33 = 0;
    v7 = (*v6)(SpinCount, &GUID_00000038_0000_0000_c000_000000000046, &v33);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v33 + 24LL))(v33, &v34);
    if ( v33 )
      (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
    if ( v7 >= 0 )
    {
      DebugInfo = a1[2].DebugInfo;
      v9 = a2[1];
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      v10 = *a2;
      v11 = a2[1];
      v12 = v34;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      v25[0] = off_1400B8E90;
      v25[1] = v10;
      v25[2] = v11;
      v30 = 0;
      v31 = 0;
      v25[3] = v12;
      v26 = v25;
      v33 = v25;
      if ( !LOBYTE(DebugInfo[1].EntryCount) && (int)CSerialWorkQueue::Initialize((PTP_POOL *)DebugInfo) >= 0 )
      {
        v13 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v15 = v13;
        if ( v13 )
        {
          *v13 = 0;
          v13[1] = 0;
          v13[2] = 0;
        }
        else
        {
          v15 = 0;
        }
        if ( v15 )
        {
          v29 = 0;
          if ( v26 )
            v29 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v26)(v26, v28);
          v15[2] = DebugInfo;
          v16 = operator new(0x50u);
          v27 = v16;
          *(_OWORD *)v16 = 0;
          v16[2] = 1;
          v16[3] = 1;
          *(_QWORD *)v16 = &std::_Ref_count_obj2<std::function<void (void)>>::`vftable';
          std::function<void (void)>::function<void (void)>(v16 + 4, v28);
          *v15 = v16 + 4;
          v17 = (std::_Ref_count_base *)v15[1];
          v15[1] = v16;
          if ( v17 )
            std::_Ref_count_base::_Decref(v17);
          v18 = *v15 == 0 ? 0x8007000E : 0;
          if ( v29 )
          {
            v19 = v28;
            LOBYTE(v19) = v29 != v28;
            (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v29 + 32LL))(v29, v19);
          }
          if ( v18 >= 0 )
          {
            ThreadpoolWork = CreateThreadpoolWork(
                               CSerialWorkQueue::WorkCallback,
                               v15,
                               (PTP_CALLBACK_ENVIRON)&DebugInfo->CriticalSection);
            if ( ThreadpoolWork )
              goto LABEL_33;
            LastError = GetLastError();
            v22 = LastError < 0;
            if ( LastError > 0 )
              v22 = 1;
            if ( !v22 )
            {
LABEL_33:
              v15 = 0;
              SubmitThreadpoolWork(ThreadpoolWork);
            }
          }
        }
        if ( v15 )
          _WorkTask::`scalar deleting destructor'((_WorkTask *)v15, v14);
      }
      if ( v26 )
      {
        v23 = v25;
        LOBYTE(v23) = v26 != v25;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v26 + 32LL))(v26, v23);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghostobject.cpp",
        (const char *)(unsigned int)v7,
        v24);
    }
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x14000ec10  mov     [rsp-8+arg_8], rbx
0x14000ec15  push    rbp
0x14000ec16  push    rsi
0x14000ec17  push    rdi
0x14000ec18  push    r14
0x14000ec1a  push    r15
0x14000ec1c  lea     rbp, [rsp-37h]
0x14000ec21  sub     rsp, 0D0h
0x14000ec28  mov     rsi, rdx
0x14000ec2b  mov     rbx, rcx
0x14000ec2e  lea     r14, [rcx+28h]
0x14000ec32  mov     rcx, r14; lpCriticalSection
0x14000ec35  call    cs:__imp_EnterCriticalSection
0x14000ec3b  mov     [rbp+57h+arg_18], r14
0x14000ec3f  cmp     qword ptr [rbx+50h], 0
0x14000ec44  jz      loc_14000ECD9
0x14000ec4a  mov     rcx, [rbx+20h]
0x14000ec4e  mov     [rbp+57h+arg_10], 0
0x14000ec56  mov     rax, [rcx]
0x14000ec59  mov     [rbp+57h+arg_0], 0
0x14000ec61  lea     r8, [rbp+57h+arg_0]
0x14000ec65  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x14000ec6c  mov     rax, [rax]
0x14000ec6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec74  mov     edi, eax
0x14000ec76  test    eax, eax
0x14000ec78  js      short loc_14000EC90
0x14000ec7a  mov     rcx, [rbp+57h+arg_0]
0x14000ec7e  mov     rax, [rcx]
0x14000ec81  lea     rdx, [rbp+57h+arg_10]
0x14000ec85  mov     rax, [rax+18h]
0x14000ec89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec8e  mov     edi, eax
0x14000ec90  mov     rcx, [rbp+57h+arg_0]
0x14000ec94  test    rcx, rcx
0x14000ec97  jz      short loc_14000ECA6
0x14000ec99  mov     rax, [rcx]
0x14000ec9c  mov     rax, [rax+10h]
0x14000eca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eca5  nop
0x14000eca6  mov     rcx, [rbp+5Fh]; this
0x14000ecaa  test    edi, edi
0x14000ecac  jns     short loc_14000ECFE
0x14000ecae  mov     r9d, edi; char *
0x14000ecb1  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14000ecb8  mov     edx, 171h; void *
0x14000ecbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000ecc2  nop
0x14000ecc3  mov     rcx, [rbp+57h+arg_10]
0x14000ecc7  test    rcx, rcx
0x14000ecca  jz      short loc_14000ECD9
0x14000eccc  mov     rax, [rcx]
0x14000eccf  mov     rax, [rax+10h]
0x14000ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ecd8  nop
0x14000ecd9  test    r14, r14
0x14000ecdc  jz      short loc_14000ECE7
0x14000ecde  mov     rcx, r14; lpCriticalSection
0x14000ece1  call    cs:__imp_LeaveCriticalSection
0x14000ece7  mov     rbx, [rsp+0F0h+arg_8]
0x14000ecef  add     rsp, 0D0h
0x14000ecf6  pop     r15
0x14000ecf8  pop     r14
0x14000ecfa  pop     rdi
0x14000ecfb  pop     rsi
0x14000ecfc  pop     rbp
0x14000ecfd  retn
0x14000ecfe  mov     r15, [rbx+50h]
0x14000ed02  mov     rax, [rsi+8]
0x14000ed06  test    rax, rax
0x14000ed09  jz      short loc_14000ED0F
0x14000ed0b  lock inc dword ptr [rax+8]
0x14000ed0f  mov     rdi, [rsi]
0x14000ed12  mov     rsi, [rsi+8]
0x14000ed16  mov     rbx, [rbp+57h+arg_10]
0x14000ed1a  test    rbx, rbx
0x14000ed1d  jz      short loc_14000ED2F
0x14000ed1f  mov     rax, [rbx]
0x14000ed22  mov     rcx, rbx
0x14000ed25  mov     rax, [rax+8]
0x14000ed29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed2e  nop
0x14000ed2f  lea     rax, off_1400B8E90
0x14000ed36  mov     [rbp+57h+var_C0], rax
0x14000ed3a  mov     [rbp+57h+var_B8], rdi
0x14000ed3e  mov     [rbp+57h+var_B0], rsi
0x14000ed42  xorps   xmm0, xmm0
0x14000ed45  movdqu  [rbp+57h+var_38], xmm0
0x14000ed4a  mov     [rbp+57h+var_28], 0
0x14000ed52  mov     [rbp+57h+var_A8], rbx
0x14000ed56  lea     rax, [rbp+57h+var_C0]
0x14000ed5a  mov     [rbp+57h+var_88], rax
0x14000ed5e  lea     rax, [rbp+57h+var_C0]
0x14000ed62  mov     [rbp+57h+arg_0], rax
0x14000ed66  mov     al, [r15+50h]
0x14000ed6a  nop
0x14000ed6b  test    al, al
0x14000ed6d  jnz     loc_14000EECB
0x14000ed73  mov     rcx, r15; this
0x14000ed76  call    ?Initialize@CSerialWorkQueue@@AEAAJXZ; CSerialWorkQueue::Initialize(void)
0x14000ed7b  test    eax, eax
0x14000ed7d  js      loc_14000EECB
0x14000ed83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000ed8a  mov     ecx, 18h; unsigned __int64
0x14000ed8f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000ed94  mov     rsi, rax
0x14000ed97  mov     [rbp+57h+var_D0], rax
0x14000ed9b  test    rax, rax
0x14000ed9e  jz      loc_14000EEF0
0x14000eda4  mov     qword ptr [rax], 0
0x14000edab  mov     qword ptr [rax+8], 0
0x14000edb3  mov     qword ptr [rax+10h], 0
0x14000edbb  mov     [rbp+57h+var_D0], rsi
0x14000edbf  test    rsi, rsi
0x14000edc2  jz      loc_14000EEC6
0x14000edc8  lea     rax, [rbp+57h+var_78]
0x14000edcc  mov     [rbp+57h+var_C8], rax
0x14000edd0  mov     [rbp+57h+var_40], 0
0x14000edd8  mov     rcx, [rbp+57h+var_88]
0x14000eddc  test    rcx, rcx
0x14000eddf  jz      short loc_14000EDF4
0x14000ede1  mov     rax, [rcx]
0x14000ede4  lea     rdx, [rbp+57h+var_78]
0x14000ede8  mov     rax, [rax]
0x14000edeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edf0  mov     [rbp+57h+var_40], rax
0x14000edf4  lea     rax, [rbp+57h+var_78]
0x14000edf8  mov     [rbp+57h+var_C8], rax
0x14000edfc  mov     [rsi+10h], r15
0x14000ee00  mov     ecx, 50h ; 'P'; Size
0x14000ee05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ee0a  mov     rdi, rax
0x14000ee0d  mov     [rbp+57h+var_80], rax
0x14000ee11  xorps   xmm0, xmm0
0x14000ee14  movups  xmmword ptr [rax], xmm0
0x14000ee17  mov     dword ptr [rax+8], 1
0x14000ee1e  mov     dword ptr [rax+0Ch], 1
0x14000ee25  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AXXZ@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<void (void)>>::`vftable'
0x14000ee2c  mov     [rdi], rax
0x14000ee2f  lea     rbx, [rdi+10h]
0x14000ee33  lea     rdx, [rbp+57h+var_78]
0x14000ee37  mov     rcx, rbx
0x14000ee3a  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x14000ee3f  nop
0x14000ee40  mov     [rsi], rbx
0x14000ee43  mov     rcx, [rsi+8]; this
0x14000ee47  mov     [rsi+8], rdi
0x14000ee4b  test    rcx, rcx
0x14000ee4e  jz      short loc_14000EE55
0x14000ee50  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000ee55  mov     rax, [rsi]
0x14000ee58  neg     rax
0x14000ee5b  sbb     ebx, ebx
0x14000ee5d  not     ebx
0x14000ee5f  and     ebx, 8007000Eh
0x14000ee65  mov     rcx, [rbp+57h+var_40]
0x14000ee69  test    rcx, rcx
0x14000ee6c  jz      short loc_14000EE84
0x14000ee6e  mov     rax, [rcx]
0x14000ee71  lea     rdx, [rbp+57h+var_78]
0x14000ee75  cmp     rcx, rdx
0x14000ee78  setnz   dl
0x14000ee7b  mov     rax, [rax+20h]
0x14000ee7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee84  test    ebx, ebx
0x14000ee86  js      short loc_14000EEC6
0x14000ee88  lea     r8, [r15+8]; pcbe
0x14000ee8c  mov     rdx, rsi; pv
0x14000ee8f  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14000ee96  call    cs:__imp_CreateThreadpoolWork
0x14000ee9c  mov     rbx, rax
0x14000ee9f  test    rax, rax
0x14000eea2  jnz     short loc_14000EEBA
0x14000eea4  call    cs:__imp_GetLastError
0x14000eeaa  test    eax, eax
0x14000eeac  jle     short loc_14000EEB8
0x14000eeae  movzx   eax, ax
0x14000eeb1  or      eax, 80070000h
0x14000eeb6  test    eax, eax
0x14000eeb8  js      short loc_14000EEC6
0x14000eeba  xor     esi, esi
0x14000eebc  mov     rcx, rbx; pwk
0x14000eebf  call    cs:__imp_SubmitThreadpoolWork
0x14000eec5  nop
0x14000eec6  test    rsi, rsi
0x14000eec9  jnz     short loc_14000EEF7
0x14000eecb  mov     rcx, [rbp+57h+var_88]
0x14000eecf  test    rcx, rcx
0x14000eed2  jz      short loc_14000EEEB
0x14000eed4  mov     rax, [rcx]
0x14000eed7  lea     rdx, [rbp+57h+var_C0]
0x14000eedb  cmp     rcx, rdx
0x14000eede  setnz   dl
0x14000eee1  mov     rax, [rax+20h]
0x14000eee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eeea  nop
0x14000eeeb  jmp     loc_14000ECC3
0x14000eef0  xor     esi, esi
0x14000eef2  jmp     loc_14000EDBB
0x14000eef7  mov     rcx, rsi; this
0x14000eefa  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x14000eeff  jmp     short loc_14000EECB
```
