# Windows::Payment::Mediator::Service::RpcCallManager::IsRunningInForeground(void)

- ea: `0x180081294`
- end: `0x180081349`
- name: `?IsRunningInForeground@RpcCallManager@Service@Mediator@Payment@Windows@@QEBA_NXZ`
- size: `181`
- prototype: `bool(Windows::Payment::Mediator::Service::RpcCallManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18007ec90`
- `0x180084ca4`

## callees

- `0x180007aac`
- `0x18002daa4`
- `0x180081294`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800812c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800812c5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800812b4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800812b4`
- `RMCLIENT!RmAccessCheck` at `0x1800812dc`
- `RMCLIENT!RmAccessCheck` at `0x1800812dc`

## string_xrefs

- `0x180081313`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180081334`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`

## pseudocode

```c
bool __fastcall Windows::Payment::Mediator::Service::RpcCallManager::IsRunningInForeground(
        Windows::Payment::Mediator::Service::RpcCallManager *this)
{
  void *v2; // rcx
  RPC_STATUS v3; // eax
  DWORD CurrentProcessId; // eax
  unsigned int v5; // eax
  char v6; // al
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int Pid; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 9) )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    Pid = 0;
    v3 = I_RpcBindingInqLocalClientPID(v2, &Pid);
    if ( v3 )
    {
      if ( v3 != 1725 )
      {
        v8 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
          (const char *)v8,
          v10);
      }
      CurrentProcessId = GetCurrentProcessId();
      Pid = CurrentProcessId;
    }
    else
    {
      CurrentProcessId = Pid;
    }
    v5 = RmAccessCheck(27, CurrentProcessId);
    if ( v5 == -2147024891 )
    {
      v6 = 0;
    }
    else
    {
      if ( v5 > 1 )
      {
        v9 = wil::verify_hresult<long>(v5);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
          (const char *)v9,
          v10);
      }
      v6 = 1;
    }
    *((_BYTE *)this + 8) = v6;
    *((_BYTE *)this + 9) = 1;
  }
  return *((_BYTE *)this + 8);
}

```

## disassembly

```asm
0x180081294  push    rbx; int
0x180081296  sub     rsp, 20h
0x18008129a  cmp     byte ptr [rcx+9], 0
0x18008129e  mov     rbx, rcx
0x1800812a1  jnz     short loc_1800812FB
0x1800812a3  mov     rcx, [rcx+10h]; Binding
0x1800812a7  lea     rdx, [rsp+28h+Pid]; Pid
0x1800812ac  mov     [rsp+28h+Pid], 0
0x1800812b4  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800812ba  test    eax, eax
0x1800812bc  jz      short loc_1800812D1
0x1800812be  cmp     eax, 6BDh
0x1800812c3  jnz     short loc_180081304
0x1800812c5  call    cs:__imp_GetCurrentProcessId
0x1800812cb  mov     [rsp+28h+Pid], eax
0x1800812cf  jmp     short loc_1800812D5
0x1800812d1  mov     eax, [rsp+28h+Pid]
0x1800812d5  mov     edx, eax
0x1800812d7  mov     ecx, 1Bh
0x1800812dc  call    cs:__imp_RmAccessCheck
0x1800812e2  cmp     eax, 80070005h
0x1800812e7  jz      short loc_1800812F2
0x1800812e9  cmp     eax, 1
0x1800812ec  ja      short loc_180081328
0x1800812ee  mov     al, 1
0x1800812f0  jmp     short loc_1800812F4
0x1800812f2  xor     al, al
0x1800812f4  mov     [rbx+8], al
0x1800812f7  mov     byte ptr [rbx+9], 1
0x1800812fb  mov     al, [rbx+8]
0x1800812fe  add     rsp, 20h
0x180081302  pop     rbx
0x180081303  retn
0x180081304  mov     ecx, 8000FFFFh
0x180081309  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18008130e  mov     rcx, [rsp+28h]; this
0x180081313  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18008131a  mov     r9d, eax; char *
0x18008131d  mov     edx, 76h ; 'v'; void *
0x180081322  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081328  mov     ecx, eax
0x18008132a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18008132f  mov     rcx, [rsp+28h]; this
0x180081334  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18008133b  mov     r9d, eax; char *
0x18008133e  mov     edx, 88h; void *
0x180081343  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
