# WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__LocationManager::InternalTraceBadWifi_::_3_::_lambda_1___

- ea: `0x180077b84`
- end: `0x180077c88`
- name: `WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__LocationManager::InternalTraceBadWifi_::_3_::_lambda_1___`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c48a4`

## callees

- `0x180008c2c`
- `0x180008c78`
- `0x180008db0`
- `0x180027630`
- `0x180077b84`
- `0x18008534c`
- `0x180085bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077bce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077c6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077bce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077c6a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180077c79`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180077c79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__LocationManager::InternalTraceBadWifi_::_3_::_lambda_1___(
        __int64 a1,
        _OWORD *a2)
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
      *(_QWORD *)v5 = off_1800F8FA0;
      *(_OWORD *)(v5 + 8) = *a2;
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
0x180077b84  push    rbx
0x180077b86  push    rbp
0x180077b87  push    rsi
0x180077b88  push    rdi
0x180077b89  sub     rsp, 78h
0x180077b8d  mov     rbp, rdx
0x180077b90  mov     rdi, rcx
0x180077b93  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x180077b98  test    al, al
0x180077b9a  jnz     loc_180077C7F
0x180077ba0  mov     [rsp+98h+lpCriticalSection], 0
0x180077ba9  mov     rdx, rdi
0x180077bac  lea     rcx, [rsp+98h+lpCriticalSection]
0x180077bb1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180077bb6  nop
0x180077bb7  cmp     byte ptr [rdi+0D8h], 0
0x180077bbe  jz      short loc_180077BD9
0x180077bc0  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180077bc5  test    rcx, rcx
0x180077bc8  jz      loc_180077C7F
0x180077bce  call    cs:__imp_LeaveCriticalSection
0x180077bd4  jmp     loc_180077C7F
0x180077bd9  lea     rbx, [rdi+98h]
0x180077be0  cmp     qword ptr [rbx+38h], 0
0x180077be5  setz    sil
0x180077be9  xor     edx, edx; Val
0x180077beb  lea     r8d, [rdx+40h]; Size
0x180077bef  lea     rcx, [rsp+98h+var_68]; void *
0x180077bf4  call    memset_0
0x180077bf9  mov     ecx, 40h ; '@'; Size
0x180077bfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077c03  mov     [rsp+98h+var_70], rax
0x180077c08  mov     qword ptr [rax+38h], 0
0x180077c10  lea     rcx, off_1800F8FA0
0x180077c17  mov     [rax], rcx
0x180077c1a  movups  xmm0, xmmword ptr [rbp+0]
0x180077c1e  movdqu  xmmword ptr [rax+8], xmm0
0x180077c23  mov     [rax+38h], rax
0x180077c27  mov     [rsp+98h+var_40], rax
0x180077c2c  lea     rax, ??$_Any_big_RTTI_obj@V?$function@$$A6AXXZ@std@@@std@@3U_Any_big_RTTI@1@B; _Any_big_RTTI::_Any_big_RTTI const std::_Any_big_RTTI_obj<std::function<void (void)>>
0x180077c33  mov     [rsp+98h+var_38], rax
0x180077c38  lea     rax, ??_R0?AV?$function@$$A6AXXZ@std@@@8; std::function<void (void)> `RTTI Type Descriptor'
0x180077c3f  or      rax, 1
0x180077c43  mov     [rsp+98h+var_30], rax
0x180077c48  lea     rdx, [rsp+98h+var_68]
0x180077c4d  mov     rcx, rbx; this
0x180077c50  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180077c55  lea     rcx, [rsp+98h+var_68]; this
0x180077c5a  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180077c5f  nop
0x180077c60  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180077c65  test    rcx, rcx
0x180077c68  jz      short loc_180077C70
0x180077c6a  call    cs:__imp_LeaveCriticalSection
0x180077c70  test    sil, sil
0x180077c73  jz      short loc_180077C7F
0x180077c75  mov     rcx, [rdi+78h]; pwk
0x180077c79  call    cs:__imp_SubmitThreadpoolWork
0x180077c7f  add     rsp, 78h
0x180077c83  pop     rdi
0x180077c84  pop     rsi
0x180077c85  pop     rbp
0x180077c86  pop     rbx
0x180077c87  retn
```
