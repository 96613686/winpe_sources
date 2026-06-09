# CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)

- ea: `0x18002ba58`
- end: `0x18002bb78`
- name: `?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CSerialWorkQueue *this)`
- caller_count: `10`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b600`
- `0x18002b740`
- `0x18002bcc0`
- `0x18005e300`
- `0x18006acac`
- `0x180073288`
- `0x18007b014`
- `0x1800d21d0`
- `0x1800d356c`
- `0x1800d37c0`

## callees

- `0x18000cae4`
- `0x18002ac74`
- `0x18002acb4`
- `0x18002af08`
- `0x18002ba58`
- `0x1800469b4`
- `0x180087ed0`
- `0x1800d58b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002bb36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002bb36`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002bb6a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002bb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSerialWorkQueue::QueueWorkItem(CSerialWorkQueue *this, __int64 a2)
{
  int v4; // edi
  _QWORD *v5; // rax
  unsigned int v6; // edx
  void *v7; // rbx
  _WorkTask *v8; // rcx
  __int64 v10; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  _BYTE v13[88]; // [rsp+20h] [rbp-58h] BYREF

  v4 = 0;
  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 80) )
    goto LABEL_12;
  v4 = CSerialWorkQueue::Initialize((PTP_POOL *)this);
  if ( v4 < 0 )
    goto LABEL_12;
  v5 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v10 = std::function<void (void)>::function<void (void)>(v13, a2);
    v4 = _WorkTask::Initialize(v7, v10, this);
    if ( v4 >= 0 )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         CSerialWorkQueue::WorkCallback,
                         v7,
                         (PTP_CALLBACK_ENVIRON)((char *)this + 8));
      if ( ThreadpoolWork )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_8;
      }
      v7 = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
      v8 = 0;
      goto LABEL_9;
    }
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  v8 = (_WorkTask *)v7;
LABEL_9:
  if ( v7 && v8 )
    _WorkTask::`scalar deleting destructor'(v8, v6);
LABEL_12:
  std::_Func_class<void,>::_Tidy(a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ba58  mov     [rsp+arg_18], rbx
0x18002ba5d  mov     [rsp+arg_8], rdx
0x18002ba62  push    rbp
0x18002ba63  push    rsi
0x18002ba64  push    rdi
0x18002ba65  sub     rsp, 60h
0x18002ba69  mov     rbp, rdx
0x18002ba6c  mov     rsi, rcx
0x18002ba6f  xor     edi, edi
0x18002ba71  add     rcx, 50h ; 'P'
0x18002ba75  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18002ba7a  test    al, al
0x18002ba7c  jnz     short loc_18002BAED
0x18002ba7e  mov     rcx, rsi; this
0x18002ba81  call    ?Initialize@CSerialWorkQueue@@AEAAJXZ; CSerialWorkQueue::Initialize(void)
0x18002ba86  mov     edi, eax
0x18002ba88  test    eax, eax
0x18002ba8a  js      short loc_18002BAED
0x18002ba8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ba93  mov     ecx, 18h; unsigned __int64
0x18002ba98  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ba9d  mov     rbx, rax
0x18002baa0  mov     [rsp+78h+arg_0], rax
0x18002baa8  test    rax, rax
0x18002baab  jz      short loc_18002BAC6
0x18002baad  mov     qword ptr [rax], 0
0x18002bab4  mov     qword ptr [rax+8], 0
0x18002babc  mov     qword ptr [rax+10h], 0
0x18002bac4  jmp     short loc_18002BAC8
0x18002bac6  xor     ebx, ebx
0x18002bac8  mov     [rsp+78h+arg_0], rbx
0x18002bad0  test    rbx, rbx
0x18002bad3  jnz     short loc_18002BB07
0x18002bad5  mov     edi, 8007000Eh
0x18002bada  mov     rcx, rbx; this
0x18002badd  test    rbx, rbx
0x18002bae0  jz      short loc_18002BAED
0x18002bae2  test    rcx, rcx
0x18002bae5  jz      short loc_18002BAED
0x18002bae7  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x18002baec  nop
0x18002baed  mov     rcx, rbp
0x18002baf0  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18002baf5  mov     eax, edi
0x18002baf7  mov     rbx, [rsp+78h+arg_18]
0x18002baff  add     rsp, 60h
0x18002bb03  pop     rdi
0x18002bb04  pop     rsi
0x18002bb05  pop     rbp
0x18002bb06  retn
0x18002bb07  mov     rdx, rbp
0x18002bb0a  lea     rcx, [rsp+78h+var_58]
0x18002bb0f  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18002bb14  mov     r8, rsi
0x18002bb17  mov     rdx, rax
0x18002bb1a  mov     rcx, rbx
0x18002bb1d  call    ?Initialize@_WorkTask@@QEAAJV?$function@$$A6AXXZ@std@@PEAVCSerialWorkQueue@@@Z; _WorkTask::Initialize(std::function<void (void)>,CSerialWorkQueue *)
0x18002bb22  mov     edi, eax
0x18002bb24  test    eax, eax
0x18002bb26  js      short loc_18002BADA
0x18002bb28  lea     r8, [rsi+8]; pcbe
0x18002bb2c  mov     rdx, rbx; pv
0x18002bb2f  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002bb36  call    cs:__imp_CreateThreadpoolWork
0x18002bb3c  mov     rsi, rax
0x18002bb3f  test    rax, rax
0x18002bb42  jnz     short loc_18002BB63
0x18002bb44  call    cs:__imp_GetLastError
0x18002bb4a  mov     edi, eax
0x18002bb4c  test    eax, eax
0x18002bb4e  jle     short loc_18002BB59
0x18002bb50  movzx   edi, ax
0x18002bb53  or      edi, 80070000h
0x18002bb59  test    edi, edi
0x18002bb5b  js      loc_18002BADA
0x18002bb61  jmp     short loc_18002BB65
0x18002bb63  xor     edi, edi
0x18002bb65  xor     ebx, ebx
0x18002bb67  mov     rcx, rsi; pwk
0x18002bb6a  call    cs:__imp_SubmitThreadpoolWork
0x18002bb70  xor     ecx, ecx
0x18002bb72  jmp     loc_18002BADD
```
