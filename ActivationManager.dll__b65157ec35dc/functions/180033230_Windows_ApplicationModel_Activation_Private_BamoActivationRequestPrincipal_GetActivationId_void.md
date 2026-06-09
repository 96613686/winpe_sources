# Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal::GetActivationId(void)

- ea: `0x180033230`
- end: `0x18003333e`
- name: `?GetActivationId@BamoActivationRequestPrincipal@Private@Activation@ApplicationModel@Windows@@UEAA_KXZ`
- size: `270`
- prototype: `unsigned __int64 __fastcall(Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180033230`
- `0x18004498c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003327e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003329a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003327e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003329a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal::GetActivationId(
        Windows::ApplicationModel::Activation::Private::BamoActivationRequestPrincipal *this)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  const char *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rdi
  const char *v8; // r9
  signed __int32 v9; // edx
  bool v10; // sf
  signed __int32 v11; // edx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  v3 = *(_QWORD *)(v2 + 32);
  if ( *(_DWORD *)(v3 + 184) == GetCurrentThreadId() )
  {
    v2 = 0;
    v5 = 0;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 16) + 24LL))(*(_QWORD *)(v3 + 16));
    *(_DWORD *)(v3 + 184) = GetCurrentThreadId();
    v5 = v2;
  }
  v6 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    v7 = *(_QWORD *)(v5 + 32);
    if ( *(_DWORD *)(v7 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v8);
    *(_DWORD *)(v7 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 32LL))(*(_QWORD *)(v7 + 16));
  }
  if ( v2 )
  {
    v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF);
    v10 = v9 - 1 < 0;
    v11 = v9 - 1;
    if ( v10 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v4);
    if ( !v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x180033230  mov     [rsp+arg_8], rbx
0x180033235  mov     [rsp+arg_10], rsi
0x18003323a  push    rdi
0x18003323b  sub     rsp, 20h
0x18003323f  mov     rdi, rcx
0x180033242  mov     rbx, [rcx+18h]
0x180033246  mov     [rsp+28h+arg_0], 0
0x18003324f  mov     rsi, [rbx+20h]
0x180033253  call    cs:__imp_GetCurrentThreadId
0x180033259  cmp     [rsi+0B8h], eax
0x18003325f  jz      loc_180033334
0x180033265  mov     [rsp+28h+arg_0], rbx
0x18003326a  lock inc dword ptr [rbx+8]
0x18003326e  mov     rcx, [rsi+10h]
0x180033272  mov     rax, [rcx]
0x180033275  mov     rax, [rax+18h]
0x180033279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003327e  call    cs:__imp_GetCurrentThreadId
0x180033284  mov     [rsi+0B8h], eax
0x18003328a  mov     rax, rbx
0x18003328d  mov     rsi, [rdi+38h]
0x180033291  test    rbx, rbx
0x180033294  jz      short loc_1800332CD
0x180033296  mov     rdi, [rax+20h]
0x18003329a  call    cs:__imp_GetCurrentThreadId
0x1800332a0  cmp     [rdi+0B8h], eax
0x1800332a6  setnz   al
0x1800332a9  mov     rcx, [rsp+28h]; this
0x1800332ae  test    al, al
0x1800332b0  jnz     short loc_180033310
0x1800332b2  mov     dword ptr [rdi+0B8h], 0
0x1800332bc  mov     rcx, [rdi+10h]
0x1800332c0  mov     rax, [rcx]
0x1800332c3  mov     rax, [rax+20h]
0x1800332c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332cc  nop
0x1800332cd  test    rbx, rbx
0x1800332d0  jz      short loc_1800332FD
0x1800332d2  or      edx, 0FFFFFFFFh
0x1800332d5  lock xadd [rbx+8], edx
0x1800332da  add     edx, 0FFFFFFFFh
0x1800332dd  sets    al
0x1800332e0  mov     rcx, [rsp+28h]; this
0x1800332e5  test    al, al
0x1800332e7  jnz     short loc_180033322
0x1800332e9  test    edx, edx
0x1800332eb  jnz     short loc_1800332FD
0x1800332ed  mov     rdx, [rbx]
0x1800332f0  mov     rcx, rbx
0x1800332f3  mov     rax, [rdx+18h]
0x1800332f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332fc  nop
0x1800332fd  mov     rax, rsi
0x180033300  mov     rbx, [rsp+28h+arg_8]
0x180033305  mov     rsi, [rsp+28h+arg_10]
0x18003330a  add     rsp, 20h
0x18003330e  pop     rdi
0x18003330f  retn
0x180033310  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x180033317  mov     edx, 9A3h; void *
0x18003331c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180033322  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x180033329  mov     edx, 33h ; '3'; void *
0x18003332e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180033334  xor     ebx, ebx
0x180033336  xor     eax, eax
0x180033338  jmp     loc_18003328D
```
