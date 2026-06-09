# PnpDeviceInstance::NotifyDeviceChange(_GUID,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HCMNOTIFICATION__ * const,_CM_NOTIFY_ACTION,PnpManagerBase::ThreadPoolContext *)

- ea: `0x180074fb0`
- end: `0x18007508c`
- name: `?NotifyDeviceChange@PnpDeviceInstance@@EEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHCMNOTIFICATION__@@W4_CM_NOTIFY_ACTION@@PEAUThreadPoolContext@PnpManagerBase@@@Z`
- size: `220`
- prototype: `__int64 __usercall@<rax>(PnpDeviceInstance *this@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000fb14`
- `0x180074fb0`
- `0x180075158`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180074fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180074fed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074fe2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074fe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007506e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007506e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PnpDeviceInstance::NotifyDeviceChange(
        PnpDeviceInstance *this,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  DWORD CurrentThreadId; // eax
  wil *v11; // rcx
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+60h] [rbp+8h]

  if ( !*((_QWORD *)this + 9) )
    return std::wstring::_Tidy_deallocate(a3);
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    *(_DWORD *)(a6 + 88) = CurrentThreadId;
    v11 = (wil *)a5;
    if ( ((a5 - 2) & 0xFFFFFFFC) == 0 )
    {
      if ( a5 != 3 )
      {
        if ( a4 == *((_QWORD *)this + 9) )
          PnpDeviceInstance::OnDeviceRemoval(this, 0);
        goto LABEL_20;
      }
LABEL_8:
      if ( a4 == *((_QWORD *)this + 9) )
      {
        v11 = (wil *)*((_QWORD *)this + 22);
        if ( v11 )
        {
          v13 = *a2;
          (*(void (__fastcall **)(wil *, __int128 *))(*(_QWORD *)v11 + 16LL))(v11, &v13);
        }
      }
      goto LABEL_20;
    }
    if ( a5 == 3 )
      goto LABEL_8;
  }
  catch ( std::bad_alloc )
  {
    v9 = v14;
  }
  catch ( std::bad_weak_ptr )
  {
    v9 = v14;
  }
  catch ( std::exception )
  {
    v9 = v14;
  }
  catch ( ... )
  {
    wil::ResultFromCaughtException(v11);
    v9 = v14;
  }
LABEL_20:
  if ( v9 )
    LeaveCriticalSection(v9);
  return std::wstring::_Tidy_deallocate(a3);
}

```

## disassembly

```asm
0x180074fb0  mov     [rsp+arg_8], rbx
0x180074fb5  mov     [rsp+arg_10], r8
0x180074fba  push    rsi
0x180074fbb  push    rdi
0x180074fbc  push    r14
0x180074fbe  sub     rsp, 40h
0x180074fc2  mov     rsi, r9
0x180074fc5  mov     r14, rdx
0x180074fc8  mov     rdi, rcx
0x180074fcb  cmp     qword ptr [rcx+48h], 0
0x180074fd0  jz      loc_180075075
0x180074fd6  lea     rbx, [rcx+18h]
0x180074fda  mov     [rsp+58h+arg_0], rbx
0x180074fdf  mov     rcx, rbx; lpCriticalSection
0x180074fe2  call    cs:__imp_EnterCriticalSection
0x180074fe8  mov     [rsp+58h+var_38], rbx
0x180074fed  call    cs:__imp_GetCurrentThreadId
0x180074ff3  mov     rcx, [rsp+58h+arg_28]
0x180074ffb  mov     [rcx+58h], eax
0x180074ffe  mov     ecx, [rsp+58h+arg_20]
0x180075005  lea     eax, [rcx-2]
0x180075008  test    eax, 0FFFFFFFCh
0x18007500d  jnz     short loc_180075026
0x18007500f  cmp     ecx, 3
0x180075012  jz      short loc_18007502B
0x180075014  cmp     rsi, [rdi+48h]
0x180075018  jnz     short loc_180075059
0x18007501a  xor     edx, edx; bool
0x18007501c  mov     rcx, rdi; this
0x18007501f  call    ?OnDeviceRemoval@PnpDeviceInstance@@AEAAX_N@Z; PnpDeviceInstance::OnDeviceRemoval(bool)
0x180075024  jmp     short loc_180075059
0x180075026  cmp     ecx, 3
0x180075029  jnz     short loc_180075059
0x18007502b  cmp     rsi, [rdi+48h]
0x18007502f  jnz     short loc_180075059
0x180075031  mov     rcx, [rdi+0B0h]
0x180075038  test    rcx, rcx
0x18007503b  jz      short loc_180075059
0x18007503d  movups  xmm0, xmmword ptr [r14]
0x180075041  movdqu  [rsp+58h+var_28], xmm0
0x180075047  mov     rax, [rcx]
0x18007504a  lea     rdx, [rsp+58h+var_28]
0x18007504f  mov     rax, [rax+10h]
0x180075053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075058  nop
0x180075059  jmp     short loc_180075066
0x18007505b  jmp     short loc_180075061
0x18007505d  jmp     short loc_180075061
0x18007505f  jmp     short $+2
0x180075061  mov     rbx, [rsp+58h+arg_0]
0x180075066  test    rbx, rbx
0x180075069  jz      short loc_180075075
0x18007506b  mov     rcx, rbx; lpCriticalSection
0x18007506e  call    cs:__imp_LeaveCriticalSection
0x180075074  nop
0x180075075  mov     rcx, [rsp+58h+arg_10]
0x18007507a  mov     rbx, [rsp+58h+arg_8]
0x18007507f  add     rsp, 40h
0x180075083  pop     r14
0x180075085  pop     rdi
0x180075086  pop     rsi
0x180075087  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
