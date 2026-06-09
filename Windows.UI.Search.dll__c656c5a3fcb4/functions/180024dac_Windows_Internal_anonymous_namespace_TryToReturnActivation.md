# Windows::Internal::_anonymous_namespace_::TryToReturnActivation

- ea: `0x180024dac`
- end: `0x180024e3e`
- name: `Windows::Internal::_anonymous_namespace_::TryToReturnActivation`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800221c4`

## callees

- `0x180010a10`
- `0x18001eba0`
- `0x180024dac`
- `0x18007b010`

## import_xrefs

- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180024dc3`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180024dc3`
- `SHCORE!SHTaskPoolQueueTask` at `0x180024e17`
- `SHCORE!SHTaskPoolQueueTask` at `0x180024e17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::_anonymous_namespace_::TryToReturnActivation(__int64 a1)
{
  unsigned int UniqueContext; // edi
  __int64 *v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+38h] [rbp-10h]
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v6 = a1;
  v7 = 0;
  UniqueContext = SHTaskPoolGetUniqueContext();
  v2 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_34fbb4113c111a3d08810bf6cd94fc14_____lambda_34fbb4113c111a3d08810bf6cd94fc14___(
                    &v8,
                    &v6);
  v3 = *v2;
  *v2 = 0;
  v4 = v8;
  if ( v8 )
  {
    v8 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(v4);
  }
  result = SHTaskPoolQueueTask(3, 64, UniqueContext);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return result;
}

```

## disassembly

```asm
0x180024dac  mov     [rsp+arg_8], rbx
0x180024db1  push    rdi
0x180024db2  sub     rsp, 40h
0x180024db6  mov     [rsp+48h+var_18], rcx
0x180024dbb  mov     [rsp+48h+var_10], 0
0x180024dc3  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180024dc9  mov     edi, eax
0x180024dcb  lea     rdx, [rsp+48h+var_18]
0x180024dd0  lea     rcx, [rsp+48h+arg_0]
0x180024dd5  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_34fbb4113c111a3d08810bf6cd94fc14_____lambda_34fbb4113c111a3d08810bf6cd94fc14___
0x180024dda  mov     rbx, [rax]
0x180024ddd  mov     qword ptr [rax], 0
0x180024de4  mov     rcx, [rsp+48h+arg_0]
0x180024de9  test    rcx, rcx
0x180024dec  jz      short loc_180024DFC
0x180024dee  mov     [rsp+48h+arg_0], 0
0x180024df7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRoutedEventHandler@Xaml@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(void)
0x180024dfc  mov     [rsp+48h+var_20], 0
0x180024e05  mov     [rsp+48h+var_28], rbx
0x180024e0a  xor     r9d, r9d
0x180024e0d  mov     r8d, edi
0x180024e10  lea     edx, [r9+40h]
0x180024e14  lea     ecx, [rdx-3Dh]
0x180024e17  call    cs:__imp_SHTaskPoolQueueTask
0x180024e1d  nop
0x180024e1e  test    rbx, rbx
0x180024e21  jz      short loc_180024E33
0x180024e23  mov     rax, [rbx]
0x180024e26  mov     rcx, rbx
0x180024e29  mov     rax, [rax+10h]
0x180024e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e32  nop
0x180024e33  mov     rbx, [rsp+48h+arg_8]
0x180024e38  add     rsp, 40h
0x180024e3c  pop     rdi
0x180024e3d  retn
```
