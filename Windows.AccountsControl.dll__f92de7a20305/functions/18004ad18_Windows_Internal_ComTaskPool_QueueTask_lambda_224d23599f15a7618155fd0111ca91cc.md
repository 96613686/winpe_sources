# Windows::Internal::ComTaskPool::QueueTask__lambda_224d23599f15a7618155fd0111ca91cc___

- ea: `0x18004ad18`
- end: `0x18004ad9d`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_224d23599f15a7618155fd0111ca91cc___`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004bc70`

## callees

- `0x180015850`
- `0x18004a804`
- `0x18004ad18`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad54`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004ad73`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004ad73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Windows::Internal::ComTaskPool::QueueTask__lambda_224d23599f15a7618155fd0111ca91cc___()
{
  __int64 *v0; // rax
  __int64 v1; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v3; // edi
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF
  __int64 v6; // [rsp+58h] [rbp+20h]

  v0 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_224d23599f15a7618155fd0111ca91cc_____lambda_224d23599f15a7618155fd0111ca91cc___(&v5);
  v1 = *v0;
  v6 = *v0;
  *v0 = 0;
  if ( v5 )
  {
    v5 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v3 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x18004ad18  mov     [rsp+arg_0], rbx
0x18004ad1d  push    rdi
0x18004ad1e  sub     rsp, 30h
0x18004ad22  lea     rcx, [rsp+38h+arg_10]
0x18004ad27  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_224d23599f15a7618155fd0111ca91cc_____lambda_224d23599f15a7618155fd0111ca91cc___
0x18004ad2c  mov     rbx, [rax]
0x18004ad2f  mov     [rsp+38h+arg_18], rbx
0x18004ad34  mov     qword ptr [rax], 0
0x18004ad3b  mov     rcx, [rsp+38h+arg_10]
0x18004ad40  test    rcx, rcx
0x18004ad43  jz      short loc_18004AD54
0x18004ad45  mov     [rsp+38h+arg_10], 0
0x18004ad4e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>>::Release(void)
0x18004ad53  nop
0x18004ad54  call    cs:__imp_GetCurrentThreadId
0x18004ad5a  mov     [rsp+38h+var_10], 0
0x18004ad63  mov     [rsp+38h+var_18], rbx
0x18004ad68  xor     r9d, r9d
0x18004ad6b  mov     r8d, eax
0x18004ad6e  xor     edx, edx
0x18004ad70  lea     ecx, [rdx+3]
0x18004ad73  call    cs:__imp_SHTaskPoolQueueTask
0x18004ad79  mov     edi, eax
0x18004ad7b  test    rbx, rbx
0x18004ad7e  jz      short loc_18004AD90
0x18004ad80  mov     rdx, [rbx]
0x18004ad83  mov     rcx, rbx
0x18004ad86  mov     rax, [rdx+10h]
0x18004ad8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad8f  nop
0x18004ad90  mov     eax, edi
0x18004ad92  mov     rbx, [rsp+38h+arg_0]
0x18004ad97  add     rsp, 30h
0x18004ad9b  pop     rdi
0x18004ad9c  retn
```
