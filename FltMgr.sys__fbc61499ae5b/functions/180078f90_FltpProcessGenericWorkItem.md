# FltpProcessGenericWorkItem

- ea: `0x180078f90`
- end: `0x1800790de`
- name: `FltpProcessGenericWorkItem`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009f20`
- `0x180010400`
- `0x1800147b0`
- `0x180024800`
- `0x1800248e0`
- `0x180078f90`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180078fc2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180078fc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800790b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800790b4`
- `ntoskrnl!IoClearActivityIdThread` at `0x180079069`
- `ntoskrnl!IoClearActivityIdThread` at `0x180079069`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180079028`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1800790a0`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180079028`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1800790a0`
- `ntoskrnl!IoSetActivityIdThread` at `0x180079044`
- `ntoskrnl!IoSetActivityIdThread` at `0x180079044`

## pseudocode

```c
void __fastcall FltpProcessGenericWorkItem(__int64 a1)
{
  int v2; // ecx
  void *v3; // rbp
  unsigned int v4; // edi
  __int64 v5; // rbx
  __int128 v6; // [rsp+50h] [rbp-68h] BYREF
  struct _IO_PRIORITY_INFO OutputPriorityInfo; // [rsp+60h] [rbp-58h] BYREF

  OutputPriorityInfo = 0;
  v6 = 0;
  KeEnterCriticalRegion();
  v3 = *(void **)(a1 + 96);
  if ( (byte_180040A44 & 1) != 0 )
    McTemplateU0spdpppd_EtwWriteTransfer(
      v2,
      (unsigned int)WorkSup_c464,
      (unsigned int)"FltpProcessGenericWorkItem",
      a1,
      *(_DWORD *)(a1 + 40),
      (char)v3,
      *(_QWORD *)(a1 + 48),
      *(_QWORD *)(a1 + 56),
      *(_DWORD *)(a1 + 76));
  v4 = IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)(a1 + 64), &OutputPriorityInfo, KeGetCurrentThread());
  v6 = *(_OWORD *)(a1 + 80);
  v5 = IoSetActivityIdThread(&v6);
  (*(void (__fastcall **)(__int64, void *, _QWORD))(a1 + 48))(a1, v3, *(_QWORD *)(a1 + 56));
  IoClearActivityIdThread(v5);
  if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\worksup.c", 511, 0) >= 0 )
    IoApplyPriorityInfoThread(&OutputPriorityInfo, 0, KeGetCurrentThread());
  FltObjectDereference(v3);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180078f90  push    rbx
0x180078f92  push    rbp
0x180078f93  push    rsi
0x180078f94  push    rdi
0x180078f95  push    r14
0x180078f97  push    r15
0x180078f99  sub     rsp, 88h
0x180078fa0  mov     rax, cs:__security_cookie
0x180078fa7  xor     rax, rsp
0x180078faa  mov     [rsp+0B8h+var_48], rax
0x180078faf  xorps   xmm0, xmm0
0x180078fb2  xorps   xmm1, xmm1
0x180078fb5  movups  xmmword ptr [rsp+0B8h+OutputPriorityInfo.Size], xmm0
0x180078fba  mov     rsi, rcx
0x180078fbd  movups  [rsp+0B8h+var_68], xmm1
0x180078fc2  call    cs:__imp_KeEnterCriticalRegion
0x180078fc9  nop     dword ptr [rax+rax+00h]
0x180078fce  test    cs:byte_180040A44, 1
0x180078fd5  mov     rbp, [rsi+60h]
0x180078fd9  jz      short loc_180079016
0x180078fdb  mov     eax, [rsi+4Ch]
0x180078fde  lea     r8, aFltpprocessgen; "FltpProcessGenericWorkItem"
0x180078fe5  mov     [rsp+0B8h+var_78], eax
0x180078fe9  lea     rdx, WorkSup_c464
0x180078ff0  mov     rax, [rsi+38h]
0x180078ff4  mov     r9, rsi
0x180078ff7  mov     [rsp+0B8h+var_80], rax
0x180078ffc  mov     rax, [rsi+30h]
0x180079000  mov     [rsp+0B8h+var_88], rax
0x180079005  mov     eax, [rsi+28h]
0x180079008  mov     [rsp+0B8h+var_90], rbp
0x18007900d  mov     [rsp+0B8h+var_98], eax
0x180079011  call    McTemplateU0spdpppd_EtwWriteTransfer
0x180079016  mov     r8, gs:188h; Thread
0x18007901f  lea     rcx, [rsi+40h]; InputPriorityInfo
0x180079023  lea     rdx, [rsp+0B8h+OutputPriorityInfo]; OutputPriorityInfo
0x180079028  call    cs:__imp_IoApplyPriorityInfoThread
0x18007902f  nop     dword ptr [rax+rax+00h]
0x180079034  movups  xmm0, xmmword ptr [rsi+50h]
0x180079038  lea     rcx, [rsp+0B8h+var_68]
0x18007903d  mov     edi, eax
0x18007903f  movups  [rsp+0B8h+var_68], xmm0
0x180079044  call    cs:__imp_IoSetActivityIdThread
0x18007904b  nop     dword ptr [rax+rax+00h]
0x180079050  mov     r8, [rsi+38h]
0x180079054  mov     rdx, rbp
0x180079057  mov     rbx, rax
0x18007905a  mov     rcx, rsi
0x18007905d  mov     rax, [rsi+30h]
0x180079061  call    _guard_dispatch_icall
0x180079066  mov     rcx, rbx
0x180079069  call    cs:__imp_IoClearActivityIdThread
0x180079070  nop     dword ptr [rax+rax+00h]
0x180079075  mov     r8d, 1FFh
0x18007907b  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x180079082  xor     r9d, r9d
0x180079085  mov     ecx, edi
0x180079087  call    FltpDbgStatus
0x18007908c  test    eax, eax
0x18007908e  js      short loc_1800790AC
0x180079090  mov     r8, gs:188h; Thread
0x180079099  lea     rcx, [rsp+0B8h+OutputPriorityInfo]; InputPriorityInfo
0x18007909e  xor     edx, edx; OutputPriorityInfo
0x1800790a0  call    cs:__imp_IoApplyPriorityInfoThread
0x1800790a7  nop     dword ptr [rax+rax+00h]
0x1800790ac  mov     rcx, rbp; FltObject
0x1800790af  call    FltObjectDereference
0x1800790b4  call    cs:__imp_KeLeaveCriticalRegion
0x1800790bb  nop     dword ptr [rax+rax+00h]
0x1800790c0  mov     rcx, [rsp+0B8h+var_48]
0x1800790c5  xor     rcx, rsp; StackCookie
0x1800790c8  call    __security_check_cookie
0x1800790cd  add     rsp, 88h
0x1800790d4  pop     r15
0x1800790d6  pop     r14
0x1800790d8  pop     rdi
0x1800790d9  pop     rsi
0x1800790da  pop     rbp
0x1800790db  pop     rbx
0x1800790dc  retn
```
