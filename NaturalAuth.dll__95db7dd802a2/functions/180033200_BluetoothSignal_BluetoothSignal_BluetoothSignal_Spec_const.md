# BluetoothSignal::BluetoothSignal(BluetoothSignal::Spec const &)

- ea: `0x180033200`
- end: `0x18003333c`
- name: `??0BluetoothSignal@@QEAA@AEBUSpec@0@@Z`
- size: `316`
- prototype: `BluetoothSignal *__fastcall(BluetoothSignal *this, const struct BluetoothSignal::Spec *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180034624`

## callees

- `0x18000459c`
- `0x180012604`
- `0x1800131ec`
- `0x180032c2c`
- `0x180033344`
- `0x18003340c`
- `0x180033618`
- `0x1800349d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800332e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800332e7`

## pseudocode

```c
BluetoothSignal *__fastcall BluetoothSignal::BluetoothSignal(
        BluetoothSignal *this,
        const struct BluetoothSignal::Spec *a2)
{
  __int64 *v4; // rsi
  void *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  _BYTE v12[16]; // [rsp+20h] [rbp-58h] BYREF
  char v13[72]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+90h] [rbp+18h] BYREF

  *(_QWORD *)this = &BluetoothSignal::`vftable';
  v4 = (__int64 *)((char *)this + 8);
  v5 = operator new(0xC8u);
  v14 = (__int64)v5;
  v6 = BluetoothSignal::Spec::Spec((BluetoothSignal::Spec *)v13, a2);
  v7 = BluetoothSignal::Impl::Impl(v5, v6);
  *v4 = 0;
  v4[1] = 0;
  v14 = v7;
  v8 = operator new(0x18u);
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count<BluetoothSignal::Impl>::`vftable';
  *((_QWORD *)v8 + 2) = v7;
  *v4 = v7;
  v4[1] = (__int64)v8;
  v14 = 0;
  std::_Temporary_owner<BluetoothSignal::Impl>::~_Temporary_owner<BluetoothSignal::Impl>(&v14);
  *(_QWORD *)(*v4 + 120) = _InterlockedIncrement64(&qword_18005FD20);
  BluetoothSignal::GetDefaultRssi((signed __int8 *)(*v4 + 40), (signed __int8 *)(*v4 + 41));
  *(_QWORD *)(*v4 + 144) = CreateEventW(0, 1, 0, 0);
  v10 = std::async<void (&)(std::shared_ptr<BluetoothSignal::Impl>),std::shared_ptr<BluetoothSignal::Impl> &>(
          v12,
          v9,
          BluetoothSignal::Impl::InitializeDevicesAsync,
          v4);
  std::future<void>::operator=(*v4 + 152, v10);
  std::_State_manager<int>::~_State_manager<int>(v12);
  return this;
}

```

## disassembly

```asm
0x180033200  mov     [rsp+arg_8], rbx
0x180033205  mov     [rsp+arg_0], rcx
0x18003320a  push    rsi
0x18003320b  push    rdi
0x18003320c  push    r14
0x18003320e  sub     rsp, 60h
0x180033212  mov     rdi, rdx
0x180033215  mov     r14, rcx
0x180033218  lea     rax, ??_7BluetoothSignal@@6B@; const BluetoothSignal::`vftable'
0x18003321f  mov     [rcx], rax
0x180033222  lea     rsi, [rcx+8]
0x180033226  mov     ecx, 0C8h; Size
0x18003322b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033230  mov     rbx, rax
0x180033233  mov     [rsp+78h+arg_10], rax
0x18003323b  mov     rdx, rdi; struct BluetoothSignal::Spec *
0x18003323e  lea     rcx, [rsp+78h+var_48]; this
0x180033243  call    ??0Spec@BluetoothSignal@@QEAA@AEBU01@@Z; BluetoothSignal::Spec::Spec(BluetoothSignal::Spec const &)
0x180033248  mov     rdx, rax
0x18003324b  mov     rcx, rbx
0x18003324e  call    ??0Impl@BluetoothSignal@@QEAA@USpec@1@@Z; BluetoothSignal::Impl::Impl(BluetoothSignal::Spec)
0x180033253  mov     rbx, rax
0x180033256  xor     edi, edi
0x180033258  mov     [rsi], rdi
0x18003325b  mov     [rsi+8], rdi
0x18003325f  mov     [rsp+78h+arg_10], rax
0x180033267  lea     ecx, [rdi+18h]; Size
0x18003326a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003326f  mov     [rsp+78h+arg_10], rax
0x180033277  xorps   xmm0, xmm0
0x18003327a  movups  xmmword ptr [rax], xmm0
0x18003327d  mov     dword ptr [rax+8], 1
0x180033284  mov     dword ptr [rax+0Ch], 1
0x18003328b  lea     rcx, ??_7?$_Ref_count@VImpl@BluetoothSignal@@@std@@6B@; const std::_Ref_count<BluetoothSignal::Impl>::`vftable'
0x180033292  mov     [rax], rcx
0x180033295  mov     [rax+10h], rbx
0x180033299  mov     [rsi], rbx
0x18003329c  mov     [rsi+8], rax
0x1800332a0  mov     [rsp+78h+arg_10], rdi
0x1800332a8  lea     rcx, [rsp+78h+arg_10]
0x1800332b0  call    ??1?$_Temporary_owner@VImpl@BluetoothSignal@@@std@@QEAA@XZ; std::_Temporary_owner<BluetoothSignal::Impl>::~_Temporary_owner<BluetoothSignal::Impl>(void)
0x1800332b5  nop
0x1800332b6  lea     ecx, [rdi+1]
0x1800332b9  lock xadd cs:qword_18005FD20, rcx
0x1800332c2  inc     rcx
0x1800332c5  mov     rax, [rsi]
0x1800332c8  mov     [rax+78h], rcx
0x1800332cc  mov     rcx, [rsi]
0x1800332cf  lea     rdx, [rcx+29h]; signed __int8 *
0x1800332d3  add     rcx, 28h ; '('; signed __int8 *
0x1800332d7  call    ?GetDefaultRssi@BluetoothSignal@@SAXPEAC0@Z; BluetoothSignal::GetDefaultRssi(signed char *,signed char *)
0x1800332dc  xor     r9d, r9d; lpName
0x1800332df  xor     r8d, r8d; bInitialState
0x1800332e2  lea     edx, [rdi+1]; bManualReset
0x1800332e5  xor     ecx, ecx; lpEventAttributes
0x1800332e7  call    cs:__imp_CreateEventW
0x1800332ed  mov     rcx, [rsi]
0x1800332f0  mov     [rcx+90h], rax
0x1800332f7  mov     r9, rsi
0x1800332fa  lea     r8, ?InitializeDevicesAsync@Impl@BluetoothSignal@@SAXV?$shared_ptr@VImpl@BluetoothSignal@@@std@@@Z; BluetoothSignal::Impl::InitializeDevicesAsync(std::shared_ptr<BluetoothSignal::Impl>)
0x180033301  lea     rcx, [rsp+78h+var_58]
0x180033306  call    ??$async@A6AXV?$shared_ptr@VImpl@BluetoothSignal@@@std@@@ZAEAV12@@std@@YA?AV?$future@X@0@W4launch@0@A6AXV?$shared_ptr@VImpl@BluetoothSignal@@@0@@ZAEAV30@@Z; std::async<void (&)(std::shared_ptr<BluetoothSignal::Impl>),std::shared_ptr<BluetoothSignal::Impl> &>(std::launch,void (&)(std::shared_ptr<BluetoothSignal::Impl>),std::shared_ptr<BluetoothSignal::Impl> &)
0x18003330b  mov     rcx, [rsi]
0x18003330e  add     rcx, 98h
0x180033315  mov     rdx, rax
0x180033318  call    ??4?$future@X@std@@QEAAAEAV01@$$QEAV01@@Z; std::future<void>::operator=(std::future<void> &&)
0x18003331d  lea     rcx, [rsp+78h+var_58]
0x180033322  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x180033327  nop
0x180033328  mov     rax, r14
0x18003332b  mov     rbx, [rsp+78h+arg_8]
0x180033333  add     rsp, 60h
0x180033337  pop     r14
0x180033339  pop     rdi
0x18003333a  pop     rsi
0x18003333b  retn
```
