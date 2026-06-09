# std::vector<std::shared_ptr<DeviceConfiguration::Device>,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>::_Emplace_reallocate<std::shared_ptr<DeviceConfiguration::Device> const &>(std::shared_ptr<DeviceConfiguration::Device> * const,std::shared_ptr<DeviceConfiguration::Device> const &)

- ea: `0x18000e294`
- end: `0x18000e3e9`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@1@QEAV21@AEBV21@@Z`
- size: `341`
- prototype: `char *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000fbe0`

## callees

- `0x18000b838`
- `0x18000e108`
- `0x18000e220`
- `0x18000e254`
- `0x18000e294`
- `0x18000e554`
- `0x18000eb28`
- `0x1800114d4`
- `0x1800115f8`

## pseudocode

```c
char *__fastcall std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Emplace_reallocate<std::shared_ptr<DeviceConfiguration::Device> const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r14
  __int64 v4; // rbp
  __int64 v7; // rdi
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rsi
  char *v13; // r14
  __int64 v14; // rdx
  _QWORD *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD v19[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-60h]
  char *v21; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v4 = 0xFFFFFFFFFFFFFFFLL;
  v7 = (a1[1] - *a1) >> 4;
  if ( v7 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<unsigned short>::_Xlength();
  v8 = v7 + 1;
  v9 = (a1[2] - v3) >> 4;
  if ( v9 <= 0xFFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v10 = (v9 >> 1) + v9;
    v11 = v8;
    if ( v10 >= v8 )
      v11 = v10;
    if ( v11 > 0xFFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v4 = v11;
  }
  v19[0] = a1;
  v19[2] = v4;
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(16 * v4);
  v13 = (char *)v12 + ((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL);
  v21 = v13 + 16;
  std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v13, a3);
  v14 = a1[1];
  v15 = v12;
  v16 = *a1;
  v20 = v13;
  if ( a2 != v14 )
  {
    std::_Uninitialized_move<std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(
      v16,
      a2,
      v12);
    v14 = a1[1];
    v15 = v13 + 16;
    v16 = a2;
    v20 = v12;
  }
  std::_Uninitialized_move<std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(
    v16,
    v14,
    v15);
  v17 = *a1;
  v19[1] = 0;
  if ( v17 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(v17, a1[1]);
    std::_Deallocate<16>((_QWORD *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  *a1 = (__int64)v12;
  a1[1] = (__int64)&v12[2 * v8];
  a1[2] = (__int64)&v12[2 * v4];
  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Reallocation_guard::~_Reallocation_guard(v19);
  return v13;
}

```

## disassembly

```asm
0x18000e294  mov     [rsp+arg_10], r8
0x18000e299  push    rbx
0x18000e29a  push    rbp
0x18000e29b  push    rsi
0x18000e29c  push    rdi
0x18000e29d  push    r12
0x18000e29f  push    r13
0x18000e2a1  push    r14
0x18000e2a3  push    r15
0x18000e2a5  sub     rsp, 58h
0x18000e2a9  mov     r14, [rcx]
0x18000e2ac  mov     rbp, 0FFFFFFFFFFFFFFFh
0x18000e2b6  mov     rdi, [rcx+8]
0x18000e2ba  mov     r15, rdx
0x18000e2bd  sub     rdi, r14
0x18000e2c0  mov     rbx, rcx
0x18000e2c3  sar     rdi, 4
0x18000e2c7  cmp     rdi, rbp
0x18000e2ca  jz      loc_18000E3E3
0x18000e2d0  mov     rcx, [rcx+10h]
0x18000e2d4  mov     rax, rbp
0x18000e2d7  sub     rcx, r14
0x18000e2da  inc     rdi
0x18000e2dd  sar     rcx, 4
0x18000e2e1  mov     rdx, rcx
0x18000e2e4  shr     rdx, 1
0x18000e2e7  sub     rax, rdx
0x18000e2ea  cmp     rcx, rax
0x18000e2ed  ja      short loc_18000E309
0x18000e2ef  lea     rax, [rdx+rcx]
0x18000e2f3  mov     rcx, rdi
0x18000e2f6  cmp     rax, rdi
0x18000e2f9  cmovnb  rcx, rax
0x18000e2fd  cmp     rcx, rbp
0x18000e300  ja      loc_18000E3DD
0x18000e306  mov     rbp, rcx
0x18000e309  mov     r12, rbp
0x18000e30c  shl     r12, 4
0x18000e310  mov     rcx, r12
0x18000e313  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e318  mov     rdx, [rsp+98h+arg_10]
0x18000e320  mov     rcx, r15
0x18000e323  sub     rcx, r14
0x18000e326  mov     [rsp+98h+var_78], rbx
0x18000e32b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000e32f  mov     [rsp+98h+var_68], rbp
0x18000e334  mov     rsi, rax
0x18000e337  lea     r14, [rcx+rax]
0x18000e33b  lea     r13, [r14+10h]
0x18000e33f  mov     rcx, r14
0x18000e342  mov     [rsp+98h+var_58], r13
0x18000e347  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000e34c  mov     rdx, [rbx+8]
0x18000e350  mov     r8, rsi
0x18000e353  mov     rcx, [rbx]
0x18000e356  mov     [rsp+98h+var_60], r14
0x18000e35b  cmp     r15, rdx
0x18000e35e  jz      short loc_18000E377
0x18000e360  mov     rdx, r15
0x18000e363  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@YAPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(std::shared_ptr<DeviceConfiguration::Device> * const,std::shared_ptr<DeviceConfiguration::Device> * const,std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>> &)
0x18000e368  mov     rdx, [rbx+8]
0x18000e36c  mov     r8, r13
0x18000e36f  mov     rcx, r15
0x18000e372  mov     [rsp+98h+var_60], rsi
0x18000e377  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@YAPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(std::shared_ptr<DeviceConfiguration::Device> * const,std::shared_ptr<DeviceConfiguration::Device> * const,std::shared_ptr<DeviceConfiguration::Device> *,std::allocator<std::shared_ptr<DeviceConfiguration::Device>> &)
0x18000e37c  mov     rcx, [rbx]
0x18000e37f  mov     [rsp+98h+var_70], 0
0x18000e388  test    rcx, rcx
0x18000e38b  jz      short loc_18000E3A9
0x18000e38d  mov     rdx, [rbx+8]
0x18000e391  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(std::shared_ptr<DeviceConfiguration::Device> *,std::shared_ptr<DeviceConfiguration::Device> * const,std::allocator<std::shared_ptr<DeviceConfiguration::Device>> &)
0x18000e396  mov     rdx, [rbx+10h]
0x18000e39a  sub     rdx, [rbx]
0x18000e39d  mov     rcx, [rbx]
0x18000e3a0  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000e3a4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e3a9  mov     [rbx], rsi
0x18000e3ac  lea     rcx, [r12+rsi]
0x18000e3b0  shl     rdi, 4
0x18000e3b4  add     rdi, rsi
0x18000e3b7  mov     [rbx+8], rdi
0x18000e3bb  mov     [rbx+10h], rcx
0x18000e3bf  lea     rcx, [rsp+98h+var_78]
0x18000e3c4  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000e3c9  mov     rax, r14
0x18000e3cc  add     rsp, 58h
0x18000e3d0  pop     r15
0x18000e3d2  pop     r14
0x18000e3d4  pop     r13
0x18000e3d6  pop     r12
0x18000e3d8  pop     rdi
0x18000e3d9  pop     rsi
0x18000e3da  pop     rbp
0x18000e3db  pop     rbx
0x18000e3dc  retn
0x18000e3dd  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000e3e3  call    ?_Xlength@?$vector@GV?$allocator@G@std@@@std@@CAXXZ; std::vector<ushort>::_Xlength(void)
```
