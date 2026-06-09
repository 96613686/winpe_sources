# CancelPendingComTaskPoolTasks(ulong,bool)

- ea: `0x180004fbc`
- end: `0x18000509d`
- name: `?CancelPendingComTaskPoolTasks@@YAXK_N@Z`
- size: `225`
- prototype: `void __fastcall(unsigned int, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006360`

## callees

- `0x180004fbc`
- `0x1800145b0`
- `0x180041ec0`
- `0x180046b0c`
- `0x18006ea28`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000506a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000506a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180004fd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180004fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000507d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000507d`
- `SHCORE!SHTaskPoolQueueTask` at `0x180005040`
- `SHCORE!SHTaskPoolQueueTask` at `0x180005040`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CancelPendingComTaskPoolTasks(unsigned int a1)
{
  char *Event; // rdi
  __int64 v3; // rcx
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  int v6; // esi

  Event = (char *)CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event && (int)ResultFromKnownLastError() < 0 )
    goto LABEL_13;
  v4 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v4);
    v5[2] = Event;
    *v5 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a847f980382ff80e4546269ffbdc31c5_>::`vftable';
  }
  else
  {
    v5 = 0;
  }
  v6 = SHTaskPoolQueueTask(3, 258, a1, 0);
  if ( v5 )
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  if ( v6 >= 0 )
    WaitForSingleObjectEx(Event, 0xFFFFFFFF, 0);
  if ( (unsigned __int64)(Event - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Event);
  if ( v6 < 0 )
LABEL_13:
    Windows::Internal::ComTaskPool::QueueTask<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>(v3, 258, a1);
}

```

## disassembly

```asm
0x180004fbc  push    rbx
0x180004fbe  push    rbp
0x180004fbf  push    rsi
0x180004fc0  push    rdi
0x180004fc1  sub     rsp, 38h
0x180004fc5  mov     ebp, ecx
0x180004fc7  xor     edx, edx; lpName
0x180004fc9  xor     ecx, ecx; lpEventAttributes
0x180004fcb  mov     r9d, 1F0003h; dwDesiredAccess
0x180004fd1  lea     r8d, [rdx+1]; dwFlags
0x180004fd5  call    cs:__imp_CreateEventExW
0x180004fdb  mov     rdi, rax
0x180004fde  test    rax, rax
0x180004fe1  jnz     short loc_180004FF0
0x180004fe3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004fe8  test    eax, eax
0x180004fea  js      loc_180005087
0x180004ff0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004ff7  mov     ecx, 18h; unsigned __int64
0x180004ffc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005001  mov     rbx, rax
0x180005004  test    rax, rax
0x180005007  jz      short loc_180005021
0x180005009  mov     rcx, rax
0x18000500c  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180005011  mov     [rbx+10h], rdi
0x180005015  lea     rax, ??_7?$CTaskWrapper@V_lambda_a847f980382ff80e4546269ffbdc31c5_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a847f980382ff80e4546269ffbdc31c5_>::`vftable'
0x18000501c  mov     [rbx], rax
0x18000501f  jmp     short loc_180005023
0x180005021  xor     ebx, ebx
0x180005023  mov     [rsp+58h+var_30], 0
0x18000502c  mov     [rsp+58h+var_38], rbx
0x180005031  xor     r9d, r9d
0x180005034  mov     r8d, ebp
0x180005037  mov     edx, 102h
0x18000503c  lea     ecx, [r9+3]
0x180005040  call    cs:__imp_SHTaskPoolQueueTask
0x180005046  mov     esi, eax
0x180005048  test    rbx, rbx
0x18000504b  jz      short loc_18000505D
0x18000504d  mov     rcx, [rbx]
0x180005050  mov     rax, [rcx+10h]
0x180005054  mov     rcx, rbx
0x180005057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505c  nop
0x18000505d  test    esi, esi
0x18000505f  js      short loc_180005070
0x180005061  xor     r8d, r8d; bAlertable
0x180005064  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005067  mov     rcx, rdi; hHandle
0x18000506a  call    cs:__imp_WaitForSingleObjectEx
0x180005070  lea     rax, [rdi-1]
0x180005074  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005078  ja      short loc_180005083
0x18000507a  mov     rcx, rdi; hObject
0x18000507d  call    cs:__imp_CloseHandle
0x180005083  test    esi, esi
0x180005085  jns     short loc_180005094
0x180005087  mov     r8d, ebp
0x18000508a  mov     edx, 102h
0x18000508f  call    ??$QueueTask@V_lambda_dff7b450e7eee25fd5a246545de8ddb9_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_dff7b450e7eee25fd5a246545de8ddb9_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_dff7b450e7eee25fd5a246545de8ddb9_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_dff7b450e7eee25fd5a246545de8ddb9_ &&)
0x180005094  add     rsp, 38h
0x180005098  pop     rdi
0x180005099  pop     rsi
0x18000509a  pop     rbp
0x18000509b  pop     rbx
0x18000509c  retn
```
