# SidebandAudioWdmDevice::AddFileObject(_FILE_OBJECT * const)

- ea: `0x14005a048`
- end: `0x14005a16f`
- name: `?AddFileObject@SidebandAudioWdmDevice@@IEAAJQEAU_FILE_OBJECT@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(SidebandAudioWdmDevice *__hidden this, struct _FILE_OBJECT *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14007d500`

## callees

- `0x140005030`
- `0x14000e690`
- `0x14000f950`
- `0x14001f830`
- `0x1400205f4`
- `0x14005a048`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005a109`
- `ntoskrnl!ExAllocatePool2` at `0x14005a109`

## pseudocode

```c
__int64 __fastcall SidebandAudioWdmDevice::AddFileObject(SidebandAudioWdmDevice *this, struct _FILE_OBJECT *const a2)
{
  int v4; // r8d
  bool v5; // al
  unsigned int v6; // ebx
  __int64 *v7; // rdx
  _QWORD *Pool2; // rax
  _QWORD *v9; // rcx
  _BYTE v11[24]; // [rsp+50h] [rbp-18h] BYREF
  _QWORD *v12; // [rsp+70h] [rbp+8h] BYREF

  wil::acquire_kspin_lock(v11, (char *)this + 16);
  if ( SidebandAudioWdmDevice::IsKnownFileObject(this, a2) )
  {
    v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v6 = -1073740008;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids;
      LOBYTE(v7) = v5;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v7,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        26,
        (__int64)WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids,
        24);
    }
  }
  else
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1684882288);
    v12 = Pool2;
    if ( Pool2 )
    {
      Pool2[2] = a2;
      v9 = (_QWORD *)*((_QWORD *)this + 15);
      Pool2[1] = v9;
      *Pool2 = (char *)this + 112;
      v12 = 0;
      *v9 = Pool2;
      *((_QWORD *)this + 15) = Pool2;
      ++*((_QWORD *)this + 16);
    }
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v12);
    v6 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v11);
  return v6;
}

```

## disassembly

```asm
0x14005a048  mov     [rsp+arg_8], rbx
0x14005a04d  push    rdi
0x14005a04e  sub     rsp, 60h
0x14005a052  mov     rdi, rdx
0x14005a055  mov     rbx, rcx
0x14005a058  lea     rdx, [rcx+10h]
0x14005a05c  lea     rcx, [rsp+68h+var_18]
0x14005a061  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14005a066  mov     rdx, rdi; struct _FILE_OBJECT *
0x14005a069  mov     rcx, rbx; this
0x14005a06c  call    ?IsKnownFileObject@SidebandAudioWdmDevice@@AEAA_NQEAU_FILE_OBJECT@@@Z; SidebandAudioWdmDevice::IsKnownFileObject(_FILE_OBJECT * const)
0x14005a071  test    al, al
0x14005a073  jz      loc_14005A0FB
0x14005a079  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a080  lea     rax, WPP_GLOBAL_Control
0x14005a087  cmp     rcx, rax
0x14005a08a  jz      short loc_14005A0A0
0x14005a08c  mov     eax, [rcx+2Ch]
0x14005a08f  test    al, 2
0x14005a091  jz      short loc_14005A0A0
0x14005a093  cmp     byte ptr [rcx+29h], 2
0x14005a097  jb      short loc_14005A0A0
0x14005a099  mov     eax, 1
0x14005a09e  jmp     short loc_14005A0A2
0x14005a0a0  xor     al, al
0x14005a0a2  lea     rdx, WPP_RECORDER_INITIALIZED
0x14005a0a9  mov     ebx, 0C0000718h
0x14005a0ae  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14005a0b5  setnz   r8b
0x14005a0b9  test    al, al
0x14005a0bb  jnz     short loc_14005A0C6
0x14005a0bd  test    r8b, r8b
0x14005a0c0  jz      loc_14005A157
0x14005a0c6  mov     r9, [rcx+40h]
0x14005a0ca  lea     rdx, WPP_6f6ca3ff72523c797fc054add42d8828_Traceguids
0x14005a0d1  mov     rcx, [rcx+18h]
0x14005a0d5  mov     [rsp+68h+var_28], ebx
0x14005a0d9  mov     [rsp+68h+var_30], rdx
0x14005a0de  mov     dl, al
0x14005a0e0  mov     [rsp+68h+var_38], 1Ah
0x14005a0e7  mov     [rsp+68h+var_40], 2
0x14005a0ef  mov     [rsp+68h+var_48], 2
0x14005a0f4  call    WPP_RECORDER_AND_TRACE_SF_d
0x14005a0f9  jmp     short loc_14005A157
0x14005a0fb  mov     edx, 18h
0x14005a100  mov     r8d, 646D4370h
0x14005a106  lea     ecx, [rdx+28h]
0x14005a109  call    cs:__imp_ExAllocatePool2
0x14005a110  nop     dword ptr [rax+rax+00h]
0x14005a115  mov     [rsp+68h+arg_0], rax
0x14005a11a  test    rax, rax
0x14005a11d  jz      short loc_14005A14B
0x14005a11f  mov     [rax+10h], rdi
0x14005a123  lea     rdx, [rbx+70h]
0x14005a127  mov     rcx, [rdx+8]
0x14005a12b  mov     [rax+8], rcx
0x14005a12f  mov     [rax], rdx
0x14005a132  mov     [rsp+68h+arg_0], 0
0x14005a13b  mov     [rcx], rax
0x14005a13e  mov     [rdx+8], rax
0x14005a142  mov     eax, 1
0x14005a147  add     [rdx+10h], rax
0x14005a14b  lea     rcx, [rsp+68h+arg_0]
0x14005a150  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x14005a155  xor     ebx, ebx
0x14005a157  lea     rcx, [rsp+68h+var_18]
0x14005a15c  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14005a161  mov     eax, ebx
0x14005a163  mov     rbx, [rsp+68h+arg_8]
0x14005a168  add     rsp, 60h
0x14005a16c  pop     rdi
0x14005a16d  retn
```
