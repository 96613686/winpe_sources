# PhoneController::_CreateDialQueueFromString(PhoneLine *,IDialQueueClient *,ushort const *,PhoneSettingsConfig *,int,int,DialQueue * *)

- ea: `0x180036e90`
- end: `0x18003704f`
- name: `?_CreateDialQueueFromString@PhoneController@@MEAAJPEAVPhoneLine@@PEAUIDialQueueClient@@PEBGPEAVPhoneSettingsConfig@@HHPEAPEAVDialQueue@@@Z`
- size: `447`
- prototype: `int(PhoneController *__hidden this, struct PhoneLine *, struct IDialQueueClient *, const unsigned __int16 *, struct PhoneSettingsConfig *, int, int, struct DialQueue **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005660`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180036e90`
- `0x180077750`
- `0x1800780cc`
- `0x1800781c0`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036eb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036eb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036ed4`

## string_xrefs

- `0x180036ec8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037029`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036f78`: `onecoreuap\net\phone\phoneservice\service\lib\dialexec.cpp`
- `0x180036fc3`: `onecoreuap\net\phone\phoneservice\service\lib\dialexec.cpp`
- `0x180036ff8`: `onecoreuap\net\phone\phoneservice\service\lib\dialexec.cpp`
- `0x18003700c`: `onecoreuap\net\phone\phoneservice\service\lib\dialexec.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_CreateDialQueueFromString(
        PhoneController *this,
        struct PhoneLine *a2,
        struct IDialQueueClient *a3,
        const unsigned __int16 *a4,
        struct PhoneSettingsConfig *a5,
        int a6,
        int a7,
        struct DialQueue **a8)
{
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  unsigned int v15; // edi
  int v16; // eax
  int v17; // eax
  BackTraceCollection *v18; // rcx
  BackTraceCollection *v19; // rcx

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v12, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5526);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v13 = operator new(0x68u);
  v14 = v13;
  v15 = -2147024882;
  if ( !v13 )
  {
    Log_HREvent_20(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\dialexec.cpp", 735);
    goto LABEL_13;
  }
  memset_0(v13, 0, 0x68u);
  *v14 = &DialQueue::`vftable';
  v14[6] = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)v14 + 14) = a6;
  v14[8] = a5;
  v14[10] = v14 + 10;
  v14[11] = v14 + 10;
  v14[12] = 0;
  v14[9] = 0;
  v16 = DialQueue::Initialize((DialQueue *)v14, a3);
  if ( v16 < 0 )
  {
    Log_HREvent_20((unsigned int)v16, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\dialexec.cpp", 742);
    (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
LABEL_13:
    Log_HREvent_20(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\dialexec.cpp", 780);
    goto LABEL_14;
  }
  v17 = DialQueue::AddDialString((DialQueue *)v14, a4, a7);
  v15 = v17;
  if ( v17 >= 0 )
  {
    *a8 = (struct DialQueue *)v14;
    return 0;
  }
  BackTraceCollection::Capture(v18, v17);
  Log_HREvent_20(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\dialexec.cpp", 782);
  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
LABEL_14:
  BackTraceCollection::Capture(v19, v15);
  Log_HREvent_7(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5528);
  return v15;
}

```

## disassembly

```asm
0x180036e90  mov     [rsp+arg_0], rbx
0x180036e95  push    rbp
0x180036e96  push    rsi
0x180036e97  push    rdi
0x180036e98  push    r14
0x180036e9a  push    r15
0x180036e9c  sub     rsp, 30h
0x180036ea0  mov     r14, [rsp+58h+arg_38]
0x180036ea8  mov     rbp, r9
0x180036eab  mov     r15, r8
0x180036eae  mov     rsi, rdx
0x180036eb1  mov     rbx, rcx
0x180036eb4  call    cs:__imp_GetCurrentThreadId
0x180036eba  cmp     [rbx+0F0h], eax
0x180036ec0  jz      short loc_180036EE7
0x180036ec2  mov     r8d, 1596h
0x180036ec8  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036ecf  call    Log_AssertionEvent_3
0x180036ed4  call    cs:__imp_GetCurrentThreadId
0x180036eda  cmp     [rbx+0F0h], eax
0x180036ee0  jz      short loc_180036EE7
0x180036ee2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180036ee7  mov     ecx, 68h ; 'h'; Size
0x180036eec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036ef1  xor     edx, edx; Val
0x180036ef3  mov     rbx, rax
0x180036ef6  mov     edi, 8007000Eh
0x180036efb  test    rax, rax
0x180036efe  jz      loc_180036FF2
0x180036f04  lea     r8d, [rdx+68h]; Size
0x180036f08  mov     rcx, rax; void *
0x180036f0b  call    memset_0
0x180036f10  lea     rax, ??_7DialQueue@@6B@; const DialQueue::`vftable'
0x180036f17  mov     [rbx], rax
0x180036f1a  mov     [rbx+30h], rsi
0x180036f1e  test    rsi, rsi
0x180036f21  jz      short loc_180036F32
0x180036f23  mov     rax, [rsi]
0x180036f26  mov     rcx, rsi
0x180036f29  mov     rax, [rax+8]
0x180036f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f32  mov     eax, [rsp+58h+arg_28]
0x180036f39  mov     rdx, r15; struct IDialQueueClient *
0x180036f3c  mov     [rbx+38h], eax
0x180036f3f  mov     rcx, rbx; this
0x180036f42  mov     rax, [rsp+58h+arg_20]
0x180036f4a  mov     [rbx+40h], rax
0x180036f4e  lea     rax, [rbx+50h]
0x180036f52  mov     [rax], rax
0x180036f55  mov     [rax+8], rax
0x180036f59  mov     qword ptr [rax+10h], 0
0x180036f61  mov     qword ptr [rbx+48h], 0
0x180036f69  call    ?Initialize@DialQueue@@QEAAJPEAUIDialQueueClient@@@Z; DialQueue::Initialize(IDialQueueClient *)
0x180036f6e  test    eax, eax
0x180036f70  jns     short loc_180036F9D
0x180036f72  mov     r9d, 2E6h
0x180036f78  lea     r8, aOnecoreuapNetP_4; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036f7f  xor     edx, edx
0x180036f81  mov     ecx, eax
0x180036f83  call    Log_HREvent_20
0x180036f88  mov     rax, [rbx]
0x180036f8b  mov     edx, 1
0x180036f90  mov     rcx, rbx
0x180036f93  mov     rax, [rax]
0x180036f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f9b  jmp     short loc_180037006
0x180036f9d  mov     r8d, [rsp+58h+arg_30]; int
0x180036fa5  mov     rdx, rbp; unsigned __int16 *
0x180036fa8  mov     rcx, rbx; this
0x180036fab  call    ?AddDialString@DialQueue@@QEAAJPEBGH@Z; DialQueue::AddDialString(ushort const *,int)
0x180036fb0  mov     edi, eax
0x180036fb2  test    eax, eax
0x180036fb4  jns     short loc_180036FEB
0x180036fb6  mov     edx, eax; int
0x180036fb8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180036fbd  mov     r9d, 30Eh
0x180036fc3  lea     r8, aOnecoreuapNetP_4; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036fca  mov     edx, 1
0x180036fcf  mov     ecx, edi
0x180036fd1  call    Log_HREvent_20
0x180036fd6  mov     rax, [rbx]
0x180036fd9  mov     edx, 1
0x180036fde  mov     rcx, rbx
0x180036fe1  mov     rax, [rax]
0x180036fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe9  jmp     short loc_18003701C
0x180036feb  mov     [r14], rbx
0x180036fee  xor     eax, eax
0x180036ff0  jmp     short loc_18003703E
0x180036ff2  mov     r9d, 2DFh
0x180036ff8  lea     r8, aOnecoreuapNetP_4; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036fff  mov     ecx, edi
0x180037001  call    Log_HREvent_20
0x180037006  mov     r9d, 30Ch
0x18003700c  lea     r8, aOnecoreuapNetP_4; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037013  xor     edx, edx
0x180037015  mov     ecx, edi
0x180037017  call    Log_HREvent_20
0x18003701c  mov     edx, edi; int
0x18003701e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037023  mov     r9d, 1598h
0x180037029  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037030  mov     edx, 1
0x180037035  mov     ecx, edi
0x180037037  call    Log_HREvent_7
0x18003703c  mov     eax, edi
0x18003703e  mov     rbx, [rsp+58h+arg_0]
0x180037043  add     rsp, 30h
0x180037047  pop     r15
0x180037049  pop     r14
0x18003704b  pop     rdi
0x18003704c  pop     rsi
0x18003704d  pop     rbp
0x18003704e  retn
```
