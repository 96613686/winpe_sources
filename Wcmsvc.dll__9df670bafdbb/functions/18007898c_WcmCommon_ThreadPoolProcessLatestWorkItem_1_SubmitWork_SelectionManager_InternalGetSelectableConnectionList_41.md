# WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__SelectionManager::InternalGetSelectableConnectionList_::_41_::_lambda_1___

- ea: `0x18007898c`
- end: `0x180078a95`
- name: `WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__SelectionManager::InternalGetSelectableConnectionList_::_41_::_lambda_1___`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e970`

## callees

- `0x180008c2c`
- `0x180008c78`
- `0x180008db0`
- `0x180027630`
- `0x18007898c`
- `0x18008534c`
- `0x180085bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800789d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800789d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a77`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180078a86`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180078a86`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__SelectionManager::InternalGetSelectableConnectionList_::_41_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  bool v4; // si
  char *v5; // rax
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v7[40]; // [rsp+30h] [rbp-68h] BYREF
  char *v8; // [rsp+58h] [rbp-40h]
  __int64 (__fastcall **v9)(); // [rsp+60h] [rbp-38h]
  char *v10; // [rsp+68h] [rbp-30h]

  if ( !(unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady() )
  {
    lpCriticalSection[0] = 0;
    wil::EnterCriticalSection(lpCriticalSection, a1);
    if ( *(_BYTE *)(a1 + 216) )
    {
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 208) == 0;
      memset_0(v7, 0, 0x40u);
      v5 = (char *)operator new(0x40u);
      lpCriticalSection[1] = (LPCRITICAL_SECTION)v5;
      *((_QWORD *)v5 + 7) = 0;
      *(_QWORD *)v5 = off_1800F8FD0;
      *(_OWORD *)(v5 + 8) = *(_OWORD *)a2;
      *((_DWORD *)v5 + 6) = *(_DWORD *)(a2 + 16);
      *((_QWORD *)v5 + 7) = v5;
      v8 = v5;
      v9 = std::_Any_big_RTTI_obj<std::function<void (void)>>;
      v10 = (char *)&std::function<void (void)> `RTTI Type Descriptor' + 1;
      std::any::operator=((std::any *)(a1 + 152));
      std::any::reset((std::any *)v7);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      if ( v4 )
        SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 120));
    }
  }
}

```

## disassembly

```asm
0x18007898c  push    rbx
0x18007898e  push    rbp
0x18007898f  push    rsi
0x180078990  push    rdi
0x180078991  sub     rsp, 78h
0x180078995  mov     rbp, rdx
0x180078998  mov     rdi, rcx
0x18007899b  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x1800789a0  test    al, al
0x1800789a2  jnz     loc_180078A8C
0x1800789a8  mov     [rsp+98h+lpCriticalSection], 0
0x1800789b1  mov     rdx, rdi
0x1800789b4  lea     rcx, [rsp+98h+lpCriticalSection]
0x1800789b9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800789be  nop
0x1800789bf  cmp     byte ptr [rdi+0D8h], 0
0x1800789c6  jz      short loc_1800789E1
0x1800789c8  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x1800789cd  test    rcx, rcx
0x1800789d0  jz      loc_180078A8C
0x1800789d6  call    cs:__imp_LeaveCriticalSection
0x1800789dc  jmp     loc_180078A8C
0x1800789e1  lea     rbx, [rdi+98h]
0x1800789e8  cmp     qword ptr [rbx+38h], 0
0x1800789ed  setz    sil
0x1800789f1  xor     edx, edx; Val
0x1800789f3  lea     r8d, [rdx+40h]; Size
0x1800789f7  lea     rcx, [rsp+98h+var_68]; void *
0x1800789fc  call    memset_0
0x180078a01  mov     ecx, 40h ; '@'; Size
0x180078a06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078a0b  mov     [rsp+98h+var_70], rax
0x180078a10  mov     qword ptr [rax+38h], 0
0x180078a18  lea     rcx, off_1800F8FD0
0x180078a1f  mov     [rax], rcx
0x180078a22  movups  xmm0, xmmword ptr [rbp+0]
0x180078a26  movups  xmmword ptr [rax+8], xmm0
0x180078a2a  mov     edx, [rbp+10h]
0x180078a2d  mov     [rax+18h], edx
0x180078a30  mov     [rax+38h], rax
0x180078a34  mov     [rsp+98h+var_40], rax
0x180078a39  lea     rax, ??$_Any_big_RTTI_obj@V?$function@$$A6AXXZ@std@@@std@@3U_Any_big_RTTI@1@B; _Any_big_RTTI::_Any_big_RTTI const std::_Any_big_RTTI_obj<std::function<void (void)>>
0x180078a40  mov     [rsp+98h+var_38], rax
0x180078a45  lea     rax, ??_R0?AV?$function@$$A6AXXZ@std@@@8; std::function<void (void)> `RTTI Type Descriptor'
0x180078a4c  or      rax, 1
0x180078a50  mov     [rsp+98h+var_30], rax
0x180078a55  lea     rdx, [rsp+98h+var_68]
0x180078a5a  mov     rcx, rbx; this
0x180078a5d  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180078a62  lea     rcx, [rsp+98h+var_68]; this
0x180078a67  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180078a6c  nop
0x180078a6d  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180078a72  test    rcx, rcx
0x180078a75  jz      short loc_180078A7D
0x180078a77  call    cs:__imp_LeaveCriticalSection
0x180078a7d  test    sil, sil
0x180078a80  jz      short loc_180078A8C
0x180078a82  mov     rcx, [rdi+78h]; pwk
0x180078a86  call    cs:__imp_SubmitThreadpoolWork
0x180078a8c  add     rsp, 78h
0x180078a90  pop     rdi
0x180078a91  pop     rsi
0x180078a92  pop     rbp
0x180078a93  pop     rbx
0x180078a94  retn
```
