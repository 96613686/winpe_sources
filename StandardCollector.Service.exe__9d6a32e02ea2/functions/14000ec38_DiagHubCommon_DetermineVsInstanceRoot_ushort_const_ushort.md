# DiagHubCommon::DetermineVsInstanceRoot(ushort const *,ushort * *)

- ea: `0x14000ec38`
- end: `0x14000ed8b`
- name: `?DetermineVsInstanceRoot@DiagHubCommon@@YAJPEBGPEAPEAG@Z`
- size: `339`
- prototype: `__int64 __fastcall(DiagHubCommon *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005b70`
- `0x14000f9d4`

## callees

- `0x14000e7fc`
- `0x14000eaec`
- `0x14000ec38`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000ec99`
- `ole32!CoCreateInstance` at `0x14000ec99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::DetermineVsInstanceRoot(
        DiagHubCommon *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  int InstanceByPath; // eax
  __int64 v8; // [rsp+30h] [rbp-20h] BYREF
  __int64 v9; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF

  if ( !this || !a2 )
    return 2147500035LL;
  *(_QWORD *)a2 = 0;
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_177f0c4a_1cd3_4de7_a32c_71dbbb9fa36d,
         0,
         0x17u,
         &GUID_42843719_db4c_46c2_8e7c_64f1816efd5b,
         &ppv);
  if ( v5 >= 0 )
  {
    v9 = 0;
    v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_26aab78c_4a60_49d6_af3b_3c35bc93365d,
           &v9);
    if ( v5 < 0 )
    {
LABEL_13:
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      goto LABEL_15;
    }
    v8 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 48LL))(v9, &v8);
    if ( v5 >= 0 )
    {
      InstanceByPath = anonymous_namespace_::FindInstanceByPath(v8, this, a2);
      v5 = InstanceByPath;
      if ( InstanceByPath == -518979493 )
      {
        if ( (unsigned int)anonymous_namespace_::TryGetInstallRootFromTestAssets(a2) )
          goto LABEL_11;
      }
      else if ( InstanceByPath < 0 )
      {
        goto LABEL_11;
      }
      v5 = 0;
    }
LABEL_11:
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    goto LABEL_13;
  }
LABEL_15:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000ec38  mov     [rsp-18h+arg_10], rbx
0x14000ec3d  push    rbp
0x14000ec3e  push    rsi
0x14000ec3f  push    rdi
0x14000ec40  mov     rbp, rsp
0x14000ec43  sub     rsp, 50h
0x14000ec47  mov     rax, cs:__security_cookie
0x14000ec4e  xor     rax, rsp
0x14000ec51  mov     [rbp+var_8], rax
0x14000ec55  mov     rdi, rdx
0x14000ec58  mov     rsi, rcx
0x14000ec5b  test    rcx, rcx
0x14000ec5e  jz      loc_14000ED6A
0x14000ec64  test    rdx, rdx
0x14000ec67  jz      loc_14000ED6A
0x14000ec6d  mov     qword ptr [rdx], 0
0x14000ec74  mov     [rbp+var_10], 0
0x14000ec7c  lea     rax, [rbp+var_10]
0x14000ec80  mov     [rsp+50h+ppv], rax; ppv
0x14000ec85  lea     r9, _GUID_42843719_db4c_46c2_8e7c_64f1816efd5b; riid
0x14000ec8c  xor     edx, edx; pUnkOuter
0x14000ec8e  lea     r8d, [rdx+17h]; dwClsContext
0x14000ec92  lea     rcx, _GUID_177f0c4a_1cd3_4de7_a32c_71dbbb9fa36d; rclsid
0x14000ec99  call    cs:__imp_CoCreateInstance
0x14000ec9f  mov     ebx, eax
0x14000eca1  test    eax, eax
0x14000eca3  js      loc_14000ED4F
0x14000eca9  mov     [rbp+var_18], 0
0x14000ecb1  mov     rcx, [rbp+var_10]
0x14000ecb5  mov     rax, [rcx]
0x14000ecb8  lea     r8, [rbp+var_18]
0x14000ecbc  lea     rdx, _GUID_26aab78c_4a60_49d6_af3b_3c35bc93365d
0x14000ecc3  mov     rax, [rax]
0x14000ecc6  call    cs:__guard_dispatch_icall_fptr
0x14000eccc  mov     ebx, eax
0x14000ecce  test    eax, eax
0x14000ecd0  js      short loc_14000ED38
0x14000ecd2  mov     [rbp+var_20], 0
0x14000ecda  mov     rcx, [rbp+var_18]
0x14000ecde  mov     rax, [rcx]
0x14000ece1  lea     rdx, [rbp+var_20]
0x14000ece5  mov     rax, [rax+30h]
0x14000ece9  call    cs:__guard_dispatch_icall_fptr
0x14000ecef  mov     ebx, eax
0x14000ecf1  test    eax, eax
0x14000ecf3  js      short loc_14000ED21
0x14000ecf5  mov     r8, rdi
0x14000ecf8  mov     rdx, rsi
0x14000ecfb  mov     rcx, [rbp+var_20]
0x14000ecff  call    _anonymous_namespace___FindInstanceByPath
0x14000ed04  mov     ebx, eax
0x14000ed06  cmp     eax, 0E111005Bh
0x14000ed0b  jnz     short loc_14000ED1B
0x14000ed0d  mov     rcx, rdi
0x14000ed10  call    _anonymous_namespace___TryGetInstallRootFromTestAssets
0x14000ed15  test    eax, eax
0x14000ed17  jnz     short loc_14000ED21
0x14000ed19  jmp     short loc_14000ED1F
0x14000ed1b  test    eax, eax
0x14000ed1d  js      short loc_14000ED21
0x14000ed1f  xor     ebx, ebx
0x14000ed21  mov     rcx, [rbp+var_20]
0x14000ed25  test    rcx, rcx
0x14000ed28  jz      short loc_14000ED38
0x14000ed2a  mov     rax, [rcx]
0x14000ed2d  mov     rax, [rax+10h]
0x14000ed31  call    cs:__guard_dispatch_icall_fptr
0x14000ed37  nop
0x14000ed38  mov     rcx, [rbp+var_18]
0x14000ed3c  test    rcx, rcx
0x14000ed3f  jz      short loc_14000ED4F
0x14000ed41  mov     rax, [rcx]
0x14000ed44  mov     rax, [rax+10h]
0x14000ed48  call    cs:__guard_dispatch_icall_fptr
0x14000ed4e  nop
0x14000ed4f  mov     rcx, [rbp+var_10]
0x14000ed53  test    rcx, rcx
0x14000ed56  jz      short loc_14000ED66
0x14000ed58  mov     rdx, [rcx]
0x14000ed5b  mov     rax, [rdx+10h]
0x14000ed5f  call    cs:__guard_dispatch_icall_fptr
0x14000ed65  nop
0x14000ed66  mov     eax, ebx
0x14000ed68  jmp     short loc_14000ED6F
0x14000ed6a  mov     eax, 80004003h
0x14000ed6f  mov     rcx, [rbp+var_8]
0x14000ed73  xor     rcx, rsp; StackCookie
0x14000ed76  call    __security_check_cookie
0x14000ed7b  mov     rbx, [rsp+50h+arg_10]
0x14000ed83  add     rsp, 50h
0x14000ed87  pop     rdi
0x14000ed88  pop     rsi
0x14000ed89  pop     rbp
0x14000ed8a  retn
```
