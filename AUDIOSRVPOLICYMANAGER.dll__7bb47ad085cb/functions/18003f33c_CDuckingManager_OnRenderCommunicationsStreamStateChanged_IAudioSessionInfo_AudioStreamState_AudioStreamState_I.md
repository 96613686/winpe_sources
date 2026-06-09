# CDuckingManager::OnRenderCommunicationsStreamStateChanged(IAudioSessionInfo *,_AudioStreamState,_AudioStreamState,IAudioStreamInfo *)

- ea: `0x18003f33c`
- end: `0x18003f628`
- name: `?OnRenderCommunicationsStreamStateChanged@CDuckingManager@@QEAAJPEAUIAudioSessionInfo@@W4_AudioStreamState@@1PEAUIAudioStreamInfo@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022390`
- `0x180024bf0`

## callees

- `0x180001c74`
- `0x18000b9c0`
- `0x180019a80`
- `0x18001fc90`
- `0x180024370`
- `0x180029c28`
- `0x180031960`
- `0x18003e664`
- `0x18003f33c`
- `0x18003f630`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f3a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f4e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f3a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f4e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f524`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f524`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDuckingManager::OnRenderCommunicationsStreamStateChanged(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  struct CDuckingManager *v6; // rbx
  __int64 v8; // r14
  _DWORD *v9; // rax
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r14
  _DWORD *v15; // rax
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  char *v20; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+28h] [rbp-A0h] BYREF
  __int64 (__fastcall **v22)(); // [rsp+30h] [rbp-98h] BYREF
  __int64 v23; // [rsp+38h] [rbp-90h]
  struct CDuckingManager *v24; // [rsp+40h] [rbp-88h]
  __int64 v25; // [rsp+48h] [rbp-80h]
  __int64 (__fastcall ***v26)(); // [rsp+68h] [rbp-60h]
  __int64 v27; // [rsp+70h] [rbp-58h] BYREF
  struct CDuckingManager *v28; // [rsp+78h] [rbp-50h]
  _QWORD v29[2]; // [rsp+80h] [rbp-48h] BYREF

  v21 = a5;
  v6 = g_DuckingManager;
  if ( *((_BYTE *)g_DuckingManager + 456) )
    return 0;
  if ( a4 == 1 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 72LL))(a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
    v20 = (char *)v6 + 136;
    std::wstring::wstring(&v27, v8);
    v9 = (_DWORD *)std::unordered_map<std::wstring,CRenderEndpointDuckingManagerContext>::operator[](
                     (char *)v6 + 176,
                     &v27);
    ++*v9;
    std::wstring::~wstring(&v27);
    if ( v6 != (struct CDuckingManager *)-136LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
    if ( *((_DWORD *)v6 + 104) == 3 )
      return 0;
    v20 = 0;
    wil::try_com_query_to<IDuckingController,IAudioStreamInfo * &>(&v21, &v20);
    v10 = (__int64 *)wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(
                       &v21,
                       a2);
    v11 = *v10;
    *v10 = 0;
    v27 = v11;
    v28 = v6;
    wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(
      v29,
      v20);
    v22 = off_1800506F0;
    v12 = v27;
    v27 = 0;
    v23 = v12;
    v24 = v28;
    v13 = v29[0];
    v29[0] = 0;
    v25 = v13;
    v26 = &v22;
    CSerialWorkQueue::QueueWorkItem((char *)v6 + 240, &v22);
    lambda_642215a69899d380996b25cb8587b28c_::__lambda_642215a69899d380996b25cb8587b28c_(&v27);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
  }
  else
  {
    if ( a4 )
      return 0;
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 72LL))(a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
    v20 = (char *)v6 + 136;
    std::wstring::wstring(&v27, v14);
    v15 = (_DWORD *)std::unordered_map<std::wstring,CRenderEndpointDuckingManagerContext>::operator[](
                      (char *)v6 + 176,
                      &v27);
    --*v15;
    std::wstring::~wstring(&v27);
    if ( v6 != (struct CDuckingManager *)-136LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
    if ( *((_DWORD *)v6 + 104) == 3 )
      return 0;
    v20 = 0;
    wil::try_com_query_to<IDuckingController,IAudioStreamInfo * &>(&v21, &v20);
    v16 = (__int64 *)wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(
                       &v21,
                       a2);
    v17 = *v16;
    *v16 = 0;
    v27 = v17;
    v28 = v6;
    wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(
      v29,
      v20);
    v22 = off_1800506C0;
    v18 = v27;
    v27 = 0;
    v23 = v18;
    v24 = v28;
    v19 = v29[0];
    v29[0] = 0;
    v25 = v19;
    v26 = &v22;
    CSerialWorkQueue::QueueWorkItem((char *)v6 + 240, &v22);
    lambda_642215a69899d380996b25cb8587b28c_::__lambda_642215a69899d380996b25cb8587b28c_(&v27);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
  return 0;
}

```

## disassembly

```asm
0x18003f33c  push    rbx
0x18003f33e  push    rsi
0x18003f33f  push    rdi
0x18003f340  push    r14
0x18003f342  sub     rsp, 0A8h
0x18003f349  mov     rax, cs:__security_cookie
0x18003f350  xor     rax, rsp
0x18003f353  mov     [rsp+0C8h+var_38], rax
0x18003f35b  mov     rsi, rdx
0x18003f35e  mov     rax, [rsp+0C8h+arg_20]
0x18003f366  mov     [rsp+0C8h+var_A0], rax
0x18003f36b  mov     rbx, cs:?g_DuckingManager@@3PEAVCDuckingManager@@EA; CDuckingManager * g_DuckingManager
0x18003f372  cmp     byte ptr [rbx+1C8h], 0
0x18003f379  jz      short loc_18003F382
0x18003f37b  xor     eax, eax
0x18003f37d  jmp     loc_18003F60A
0x18003f382  cmp     r9d, 1
0x18003f386  jnz     loc_18003F4C0
0x18003f38c  mov     rax, [rdx]
0x18003f38f  mov     rcx, rsi
0x18003f392  mov     rax, [rax+48h]
0x18003f396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f39b  mov     r14, rax
0x18003f39e  lea     rdi, [rbx+88h]
0x18003f3a5  mov     rcx, rdi; lpCriticalSection
0x18003f3a8  call    cs:__imp_EnterCriticalSection
0x18003f3ae  mov     [rsp+0C8h+var_A8], rdi
0x18003f3b3  mov     rdx, r14
0x18003f3b6  lea     rcx, [rsp+0C8h+var_58]
0x18003f3bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003f3c0  nop
0x18003f3c1  lea     rcx, [rbx+0B0h]
0x18003f3c8  lea     rdx, [rsp+0C8h+var_58]
0x18003f3cd  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@@std@@@2@@std@@QEAAAEAUCRenderEndpointDuckingManagerContext@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,CRenderEndpointDuckingManagerContext>::operator[](std::wstring &&)
0x18003f3d2  inc     dword ptr [rax]
0x18003f3d4  lea     rcx, [rsp+0C8h+var_58]
0x18003f3d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003f3de  nop
0x18003f3df  test    rdi, rdi
0x18003f3e2  jz      short loc_18003F3ED
0x18003f3e4  mov     rcx, rdi; lpCriticalSection
0x18003f3e7  call    cs:__imp_LeaveCriticalSection
0x18003f3ed  cmp     dword ptr [rbx+1A0h], 3
0x18003f3f4  jz      loc_18003F602
0x18003f3fa  mov     [rsp+0C8h+var_A8], 0
0x18003f403  lea     rdx, [rsp+0C8h+var_A8]
0x18003f408  lea     rcx, [rsp+0C8h+var_A0]
0x18003f40d  call    ??$try_com_query_to@UIDuckingController@@AEAPEAUIAudioStreamInfo@@@wil@@YA_NAEAPEAUIAudioStreamInfo@@PEAPEAUIDuckingController@@@Z; wil::try_com_query_to<IDuckingController,IAudioStreamInfo * &>(IAudioStreamInfo * &,IDuckingController * *)
0x18003f412  mov     rdx, rsi
0x18003f415  lea     rcx, [rsp+0C8h+var_A0]
0x18003f41a  call    ??0?$com_ptr_t@UIDuckingController@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIDuckingController@@@Z; wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(IDuckingController *)
0x18003f41f  nop
0x18003f420  mov     rcx, [rax]
0x18003f423  mov     qword ptr [rax], 0
0x18003f42a  mov     [rsp+0C8h+var_58], rcx
0x18003f42f  mov     [rsp+0C8h+var_50], rbx
0x18003f434  mov     rdx, [rsp+0C8h+var_A8]
0x18003f439  lea     rcx, [rsp+0C8h+var_48]
0x18003f441  call    ??0?$com_ptr_t@UIDuckingController@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIDuckingController@@@Z; wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(IDuckingController *)
0x18003f446  nop
0x18003f447  lea     rax, off_1800506F0
0x18003f44e  mov     [rsp+0C8h+var_98], rax
0x18003f453  mov     rax, [rsp+0C8h+var_58]
0x18003f458  mov     [rsp+0C8h+var_58], 0
0x18003f461  mov     [rsp+0C8h+var_90], rax
0x18003f466  mov     rax, [rsp+0C8h+var_50]
0x18003f46b  mov     [rsp+0C8h+var_88], rax
0x18003f470  mov     rax, [rsp+0C8h+var_48]
0x18003f478  mov     [rsp+0C8h+var_48], 0
0x18003f484  mov     [rsp+0C8h+var_80], rax
0x18003f489  lea     rax, [rsp+0C8h+var_98]
0x18003f48e  mov     [rsp+0C8h+var_60], rax
0x18003f493  lea     rcx, [rbx+0F0h]
0x18003f49a  lea     rdx, [rsp+0C8h+var_98]
0x18003f49f  call    ?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z; CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)
0x18003f4a4  nop
0x18003f4a5  lea     rcx, [rsp+0C8h+var_58]
0x18003f4aa  call    _lambda_642215a69899d380996b25cb8587b28c_____lambda_642215a69899d380996b25cb8587b28c_
0x18003f4af  nop
0x18003f4b0  lea     rcx, [rsp+0C8h+var_A0]
0x18003f4b5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f4ba  nop
0x18003f4bb  jmp     loc_18003F5F8
0x18003f4c0  test    r9d, r9d
0x18003f4c3  jnz     loc_18003F602
0x18003f4c9  mov     rax, [rdx]
0x18003f4cc  mov     rcx, rsi
0x18003f4cf  mov     rax, [rax+48h]
0x18003f4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4d8  mov     r14, rax
0x18003f4db  lea     rdi, [rbx+88h]
0x18003f4e2  mov     rcx, rdi; lpCriticalSection
0x18003f4e5  call    cs:__imp_EnterCriticalSection
0x18003f4eb  mov     [rsp+0C8h+var_A8], rdi
0x18003f4f0  mov     rdx, r14
0x18003f4f3  lea     rcx, [rsp+0C8h+var_58]
0x18003f4f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003f4fd  nop
0x18003f4fe  lea     rcx, [rbx+0B0h]
0x18003f505  lea     rdx, [rsp+0C8h+var_58]
0x18003f50a  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@@std@@@2@@std@@QEAAAEAUCRenderEndpointDuckingManagerContext@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,CRenderEndpointDuckingManagerContext>::operator[](std::wstring &&)
0x18003f50f  dec     dword ptr [rax]
0x18003f511  lea     rcx, [rsp+0C8h+var_58]
0x18003f516  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003f51b  nop
0x18003f51c  test    rdi, rdi
0x18003f51f  jz      short loc_18003F52A
0x18003f521  mov     rcx, rdi; lpCriticalSection
0x18003f524  call    cs:__imp_LeaveCriticalSection
0x18003f52a  cmp     dword ptr [rbx+1A0h], 3
0x18003f531  jz      loc_18003F602
0x18003f537  mov     [rsp+0C8h+var_A8], 0
0x18003f540  lea     rdx, [rsp+0C8h+var_A8]
0x18003f545  lea     rcx, [rsp+0C8h+var_A0]
0x18003f54a  call    ??$try_com_query_to@UIDuckingController@@AEAPEAUIAudioStreamInfo@@@wil@@YA_NAEAPEAUIAudioStreamInfo@@PEAPEAUIDuckingController@@@Z; wil::try_com_query_to<IDuckingController,IAudioStreamInfo * &>(IAudioStreamInfo * &,IDuckingController * *)
0x18003f54f  mov     rdx, rsi
0x18003f552  lea     rcx, [rsp+0C8h+var_A0]
0x18003f557  call    ??0?$com_ptr_t@UIDuckingController@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIDuckingController@@@Z; wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(IDuckingController *)
0x18003f55c  nop
0x18003f55d  mov     rcx, [rax]
0x18003f560  mov     qword ptr [rax], 0
0x18003f567  mov     [rsp+0C8h+var_58], rcx
0x18003f56c  mov     [rsp+0C8h+var_50], rbx
0x18003f571  mov     rdx, [rsp+0C8h+var_A8]
0x18003f576  lea     rcx, [rsp+0C8h+var_48]
0x18003f57e  call    ??0?$com_ptr_t@UIDuckingController@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIDuckingController@@@Z; wil::com_ptr_t<IDuckingController,wil::err_returncode_policy>::com_ptr_t<IDuckingController,wil::err_returncode_policy>(IDuckingController *)
0x18003f583  nop
0x18003f584  lea     rax, off_1800506C0
0x18003f58b  mov     [rsp+0C8h+var_98], rax
0x18003f590  mov     rax, [rsp+0C8h+var_58]
0x18003f595  mov     [rsp+0C8h+var_58], 0
0x18003f59e  mov     [rsp+0C8h+var_90], rax
0x18003f5a3  mov     rax, [rsp+0C8h+var_50]
0x18003f5a8  mov     [rsp+0C8h+var_88], rax
0x18003f5ad  mov     rax, [rsp+0C8h+var_48]
0x18003f5b5  mov     [rsp+0C8h+var_48], 0
0x18003f5c1  mov     [rsp+0C8h+var_80], rax
0x18003f5c6  lea     rax, [rsp+0C8h+var_98]
0x18003f5cb  mov     [rsp+0C8h+var_60], rax
0x18003f5d0  lea     rcx, [rbx+0F0h]
0x18003f5d7  lea     rdx, [rsp+0C8h+var_98]
0x18003f5dc  call    ?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z; CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)
0x18003f5e1  nop
0x18003f5e2  lea     rcx, [rsp+0C8h+var_58]
0x18003f5e7  call    _lambda_642215a69899d380996b25cb8587b28c_____lambda_642215a69899d380996b25cb8587b28c_
0x18003f5ec  nop
0x18003f5ed  lea     rcx, [rsp+0C8h+var_A0]
0x18003f5f2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f5f7  nop
0x18003f5f8  lea     rcx, [rsp+0C8h+var_A8]
0x18003f5fd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003f602  xor     eax, eax
0x18003f604  jmp     short loc_18003F60A
0x18003f606  mov     eax, dword ptr [rsp+0C8h+var_A8]
0x18003f60a  mov     rcx, [rsp+0C8h+var_38]
0x18003f612  xor     rcx, rsp; StackCookie
0x18003f615  call    __security_check_cookie
0x18003f61a  add     rsp, 0A8h
0x18003f621  pop     r14
0x18003f623  pop     rdi
0x18003f624  pop     rsi
0x18003f625  pop     rbx
0x18003f626  retn
```
