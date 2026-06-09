# OOBEOneDriveOptin::AttemptPopulateKfmSource(void)

- ea: `0x180019a0c`
- end: `0x180019ac0`
- name: `?AttemptPopulateKfmSource@OOBEOneDriveOptin@@AEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a030`
- `0x18001b3c0`
- `0x18001cc30`

## callees

- `0x180007134`
- `0x18001136c`
- `0x180019a0c`
- `0x18001d150`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019a53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019a53`

## string_xrefs

- `0x180019a8f`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OOBEOneDriveOptin::AttemptPopulateKfmSource(OOBEOneDriveOptin *this)
{
  char *v1; // rsi
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, _QWORD, char *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v9; // [rsp+40h] [rbp+8h] BYREF

  v1 = (char *)this + 72;
  if ( *((_QWORD *)this + 9) )
    return 0;
  v9 = 0;
  if ( CoCreateInstance(
         &GUID_07ca83f0_df06_4e67_89dd_e80924a49512,
         0,
         4u,
         &GUID_b5e5ee2e_e012_4fc8_bce0_c956af66c4f3,
         &v9) < 0
    || (v3 = v9,
        v4 = *(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v9 + 24LL),
        wil::com_ptr_t<IKFMEventSource,wil::err_exception_policy>::reset(v1),
        v5 = v4(v3, 0, v1),
        v6 = v5,
        v5 >= 0) )
  {
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  }
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v9);
  return v6;
}

```

## disassembly

```asm
0x180019a0c  mov     [rsp+arg_8], rbx
0x180019a11  mov     [rsp+arg_10], rsi
0x180019a16  push    rdi
0x180019a17  sub     rsp, 30h
0x180019a1b  lea     rsi, [rcx+48h]
0x180019a1f  cmp     qword ptr [rsi], 0
0x180019a23  jz      short loc_180019A2C
0x180019a25  xor     eax, eax
0x180019a27  jmp     loc_180019AB0
0x180019a2c  mov     [rsp+38h+arg_0], 0
0x180019a35  lea     rax, [rsp+38h+arg_0]
0x180019a3a  mov     qword ptr [rsp+38h+ppv], rax; int
0x180019a3f  lea     r9, _GUID_b5e5ee2e_e012_4fc8_bce0_c956af66c4f3; riid
0x180019a46  xor     edx, edx; pUnkOuter
0x180019a48  lea     r8d, [rdx+4]; dwClsContext
0x180019a4c  lea     rcx, _GUID_07ca83f0_df06_4e67_89dd_e80924a49512; rclsid
0x180019a53  call    cs:__imp_CoCreateInstance
0x180019a59  test    eax, eax
0x180019a5b  js      short loc_180019AA2
0x180019a5d  mov     rdi, [rsp+38h+arg_0]
0x180019a62  mov     rax, [rdi]
0x180019a65  mov     rbx, [rax+18h]
0x180019a69  mov     rcx, rsi
0x180019a6c  call    ?reset@?$com_ptr_t@UIKFMEventSource@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IKFMEventSource,wil::err_exception_policy>::reset(void)
0x180019a71  mov     r8, rsi
0x180019a74  xor     edx, edx
0x180019a76  mov     rcx, rdi
0x180019a79  mov     rax, rbx
0x180019a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a81  mov     ebx, eax
0x180019a83  test    eax, eax
0x180019a85  jns     short loc_180019AA2
0x180019a87  mov     rcx, [rsp+38h]; this
0x180019a8c  mov     r9d, eax; char *
0x180019a8f  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019a96  mov     edx, 29Ch; void *
0x180019a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019aa0  jmp     short loc_180019AA4
0x180019aa2  xor     ebx, ebx
0x180019aa4  lea     rcx, [rsp+38h+arg_0]
0x180019aa9  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180019aae  mov     eax, ebx
0x180019ab0  mov     rbx, [rsp+38h+arg_8]
0x180019ab5  mov     rsi, [rsp+38h+arg_10]
0x180019aba  add     rsp, 30h
0x180019abe  pop     rdi
0x180019abf  retn
```
