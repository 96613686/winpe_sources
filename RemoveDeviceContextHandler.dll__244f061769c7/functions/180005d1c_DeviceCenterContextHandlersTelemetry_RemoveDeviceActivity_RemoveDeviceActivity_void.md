# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(void)

- ea: `0x180005d1c`
- end: `0x180005e34`
- name: `??1RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAA@XZ`
- size: `280`
- prototype: `void __fastcall(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180007a10`
- `0x1800085b0`
- `0x18000b5dc`

## callees

- `0x180001be0`
- `0x1800054f0`
- `0x180005adc`
- `0x180005b50`
- `0x180005d1c`
- `0x180008814`
- `0x18000c966`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dab`

## pseudocode

```c
void __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *this)
{
  bool v1; // zf
  volatile signed __int32 *v3; // rcx
  char v4; // si
  void *v5; // rdi
  _DWORD *v6; // rcx
  int v7; // eax
  int v8; // edx
  const struct wil::FailureInfo *v9; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v11[160]; // [rsp+30h] [rbp-A8h] BYREF

  v1 = *((_QWORD *)this + 35) == 0;
  *(_QWORD *)this = &DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable';
  if ( v1 )
    goto LABEL_13;
  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v3 && *v3 == 1 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
      {
        v5 = (void *)*((_QWORD *)this + 35);
        if ( v5 )
        {
          wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)v5 + 8);
          operator delete(v5);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v4 )
  {
LABEL_13:
    v6 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v6 == 1 )
    {
      v7 = -2147024322;
      v8 = v6[62];
      if ( (int)v6[22] < 0 )
        v7 = v6[22];
      if ( v8 < 1 )
      {
        memset_0(v11, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v11, v9);
      }
      if ( (int)v6[18] >= 0 )
        v6[18] = v7;
      v6[62] = v8 - 1;
      (*(void (__fastcall **)(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180005d1c  mov     [rsp+arg_8], rbx
0x180005d21  mov     [rsp+arg_10], rsi
0x180005d26  push    rdi
0x180005d27  sub     rsp, 0D0h
0x180005d2e  cmp     qword ptr [rcx+118h], 0
0x180005d36  lea     rax, ??_7RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@6B@; const DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable'
0x180005d3d  mov     [rcx], rax
0x180005d40  mov     rbx, rcx
0x180005d43  jz      short loc_180005DB6
0x180005d45  lea     rdx, [rsp+0D8h+SRWLock]
0x180005d4a  call    ?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180005d4f  mov     rcx, [rbx+118h]
0x180005d56  test    rcx, rcx
0x180005d59  jz      short loc_180005D65
0x180005d5b  cmp     dword ptr [rcx], 1
0x180005d5e  jnz     short loc_180005D65
0x180005d60  mov     sil, 1
0x180005d63  jmp     short loc_180005DA1
0x180005d65  xor     sil, sil
0x180005d68  test    rcx, rcx
0x180005d6b  jz      short loc_180005DA1
0x180005d6d  or      eax, 0FFFFFFFFh
0x180005d70  lock xadd [rcx], eax
0x180005d74  cmp     eax, 1
0x180005d77  jnz     short loc_180005D96
0x180005d79  mov     rdi, [rbx+118h]
0x180005d80  test    rdi, rdi
0x180005d83  jz      short loc_180005D96
0x180005d85  lea     rcx, [rdi+8]
0x180005d89  call    ??1?$ActivityData@VDeviceCenterContextHandlersLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005d8e  mov     rcx, rdi; Block
0x180005d91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d96  mov     qword ptr [rbx+118h], 0
0x180005da1  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x180005da6  test    rcx, rcx
0x180005da9  jz      short loc_180005DB1
0x180005dab  call    cs:__imp_ReleaseSRWLockExclusive
0x180005db1  test    sil, sil
0x180005db4  jz      short loc_180005DFB
0x180005db6  mov     rcx, [rbx+110h]
0x180005dbd  cmp     dword ptr [rcx], 1
0x180005dc0  jnz     short loc_180005DFB
0x180005dc2  cmp     dword ptr [rcx+58h], 0
0x180005dc6  mov     eax, 8007023Eh
0x180005dcb  mov     edx, [rcx+0F8h]
0x180005dd1  cmovl   eax, [rcx+58h]
0x180005dd5  cmp     edx, 1
0x180005dd8  jl      short loc_180005E17
0x180005dda  cmp     dword ptr [rcx+48h], 0
0x180005dde  jl      short loc_180005DE3
0x180005de0  mov     [rcx+48h], eax
0x180005de3  lea     eax, [rdx-1]
0x180005de6  mov     [rcx+0F8h], eax
0x180005dec  mov     rcx, rbx
0x180005def  mov     rax, [rbx]
0x180005df2  mov     rax, [rax+8]
0x180005df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfb  mov     rcx, rbx
0x180005dfe  lea     r11, [rsp+0D8h+var_8]
0x180005e06  mov     rbx, [r11+18h]
0x180005e0a  mov     rsi, [r11+20h]
0x180005e0e  mov     rsp, r11
0x180005e11  pop     rdi
0x180005e12  jmp     ??1?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005e17  xor     edx, edx; Val
0x180005e19  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180005e1e  mov     r8d, 98h; Size
0x180005e24  call    memset_0
0x180005e29  lea     rcx, [rsp+0D8h+var_A8]; this
0x180005e2e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
