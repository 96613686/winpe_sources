# SharedMessagePortRefPtr::Initialize(InputCapability)

- ea: `0x1800148f0`
- end: `0x180014ab5`
- name: `?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b860`
- `0x1800536fc`

## callees

- `0x1800132f0`
- `0x1800148f0`
- `0x180014b90`
- `0x180058010`

## import_xrefs

- `CoreUIComponents!CoreUIClientCreate` at `0x18001491b`
- `CoreUIComponents!CoreUIClientCreate` at `0x18001491b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014992`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014992`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a99`

## pseudocode

```c
__int64 __fastcall SharedMessagePortRefPtr::Initialize(_QWORD *a1, int a2)
{
  __int64 v2; // rdi
  PSECURITY_DESCRIPTOR v4; // r14
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // ebx
  int v9; // r9d
  const unsigned __int16 *const near *v10; // rcx
  __int64 (__fastcall *v11)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *); // r11
  const unsigned __int16 *const near *v12; // rdx
  int v13; // eax
  __int64 v14; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *const near *v18; // [rsp+40h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+78h] [rbp+28h]
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  v2 = a2;
  v21 = 0;
  v20 = 0;
  v4 = 0;
  v5 = CoreUIClientCreate(&v21);
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v9 = 116;
    goto LABEL_4;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, &v20);
  v8 = v5;
  if ( v5 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-419202837"
             "2-3968301570-1997628692-1435953622)",
            1u,
            &SecurityDescriptor,
            0) )
      FailFastWithHR(-2147467259, retaddr, 0xF3u);
    v10 = (&c_wszMessagePortNames)[v2];
    v4 = SecurityDescriptor;
    SecurityDescriptor = 0;
    v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *))(*(_QWORD *)v20 + 24LL);
    if ( v10 )
    {
      v12 = v10;
      v18 = v10;
      v13 = 0;
      while ( *(_WORD *)v10 )
      {
        v10 = (const unsigned __int16 *const near *)((char *)v10 + 2);
        ++v13;
      }
      v17 = v13 | 0x80000000;
    }
    else
    {
      v12 = 0;
      v18 = 0;
    }
    v5 = v11(v20, (unsigned __int64)&v17 & -(__int64)(v12 != 0), v4, a1 + 1);
    v8 = v5;
    if ( v5 >= 0 )
    {
      v14 = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      if ( *a1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = v14;
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v9 = 127;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v9 = 119;
LABEL_4:
    McTemplateU0sqq_EventWriteTransfer(v7, v6, (unsigned int)"SharedMessagePortRefPtr::Initialize", v9, v5);
  }
LABEL_24:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  LocalFree(v4);
  return v8;
}

```

## disassembly

```asm
0x1800148f0  mov     [rsp-28h+arg_0], rbx
0x1800148f5  push    rbp
0x1800148f6  push    rsi
0x1800148f7  push    rdi
0x1800148f8  push    r14
0x1800148fa  push    r15
0x1800148fc  mov     rbp, rsp
0x1800148ff  sub     rsp, 50h
0x180014903  xor     r15d, r15d
0x180014906  movsxd  rdi, edx
0x180014909  mov     rsi, rcx
0x18001490c  mov     [rbp+arg_18], r15
0x180014910  lea     rcx, [rbp+arg_18]
0x180014914  mov     [rbp+arg_10], r15
0x180014918  mov     r14d, r15d
0x18001491b  call    cs:__imp_CoreUIClientCreate
0x180014921  mov     ebx, eax
0x180014923  test    eax, eax
0x180014925  jns     short loc_18001494D
0x180014927  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001492e  jz      loc_180014A64
0x180014934  lea     r9d, [r15+74h]
0x180014938  lea     r8, aSharedmessagep; "SharedMessagePortRefPtr::Initialize"
0x18001493f  mov     [rsp+50h+var_30], eax
0x180014943  call    McTemplateU0sqq_EventWriteTransfer
0x180014948  jmp     loc_180014A64
0x18001494d  mov     rcx, [rbp+arg_18]
0x180014951  lea     rdx, [rbp+arg_10]
0x180014955  mov     rax, [rcx]
0x180014958  mov     rax, [rax+30h]
0x18001495c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014961  mov     ebx, eax
0x180014963  test    eax, eax
0x180014965  jns     short loc_18001497C
0x180014967  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001496e  jz      loc_180014A64
0x180014974  mov     r9d, 77h ; 'w'
0x18001497a  jmp     short loc_180014938
0x18001497c  xor     r9d, r9d; SecurityDescriptorSize
0x18001497f  mov     [rbp+SecurityDescriptor], r15
0x180014983  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180014987  lea     rcx, StringSecurityDescriptor; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x18001498e  lea     edx, [r9+1]; StringSDRevision
0x180014992  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014998  test    eax, eax
0x18001499a  jnz     short loc_1800149B0
0x18001499c  mov     rdx, [rbp+28h]; unsigned __int64
0x1800149a0  mov     ecx, 80004005h; int
0x1800149a5  mov     r8d, 0F3h; unsigned __int64
0x1800149ab  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1800149b0  mov     r10, [rbp+arg_10]
0x1800149b4  lea     rcx, ?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x1800149bb  mov     rcx, [rcx+rdi*8]
0x1800149bf  mov     r14, [rbp+SecurityDescriptor]
0x1800149c3  mov     [rbp+SecurityDescriptor], r15
0x1800149c7  mov     rax, [r10]
0x1800149ca  mov     r11, [rax+18h]
0x1800149ce  test    rcx, rcx
0x1800149d1  jz      short loc_1800149F5
0x1800149d3  mov     rdx, rcx
0x1800149d6  mov     [rbp+var_10], rcx
0x1800149da  mov     rax, r15
0x1800149dd  jmp     short loc_1800149E6
0x1800149df  lea     rcx, [rcx+2]
0x1800149e3  inc     rax
0x1800149e6  cmp     [rcx], r15w
0x1800149ea  jnz     short loc_1800149DF
0x1800149ec  bts     eax, 1Fh
0x1800149f0  mov     [rbp+var_18], eax
0x1800149f3  jmp     short loc_1800149FC
0x1800149f5  mov     rdx, r15
0x1800149f8  mov     [rbp+var_10], rdx
0x1800149fc  neg     rdx
0x1800149ff  lea     rax, [rbp+var_18]
0x180014a03  lea     r9, [rsi+8]
0x180014a07  mov     r8, r14
0x180014a0a  sbb     rdx, rdx
0x180014a0d  mov     rcx, r10
0x180014a10  and     rdx, rax
0x180014a13  mov     rax, r11
0x180014a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a1b  mov     ebx, eax
0x180014a1d  test    eax, eax
0x180014a1f  jns     short loc_180014A35
0x180014a21  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180014a28  jz      short loc_180014A64
0x180014a2a  mov     r9d, 7Fh
0x180014a30  jmp     loc_180014938
0x180014a35  mov     rdi, [rbp+arg_10]
0x180014a39  test    rdi, rdi
0x180014a3c  jz      short loc_180014A4D
0x180014a3e  mov     rax, [rdi]
0x180014a41  mov     rcx, rdi
0x180014a44  mov     rax, [rax+8]
0x180014a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a4d  mov     rcx, [rsi]
0x180014a50  test    rcx, rcx
0x180014a53  jz      short loc_180014A61
0x180014a55  mov     rax, [rcx]
0x180014a58  mov     rax, [rax+10h]
0x180014a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a61  mov     [rsi], rdi
0x180014a64  mov     rcx, [rbp+arg_18]
0x180014a68  test    rcx, rcx
0x180014a6b  jz      short loc_180014A7D
0x180014a6d  mov     rax, [rcx]
0x180014a70  mov     rax, [rax+10h]
0x180014a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a79  mov     [rbp+arg_18], r15
0x180014a7d  mov     rcx, [rbp+arg_10]
0x180014a81  test    rcx, rcx
0x180014a84  jz      short loc_180014A96
0x180014a86  mov     rax, [rcx]
0x180014a89  mov     rax, [rax+10h]
0x180014a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a92  mov     [rbp+arg_10], r15
0x180014a96  mov     rcx, r14; hMem
0x180014a99  call    cs:__imp_LocalFree
0x180014a9f  mov     eax, ebx
0x180014aa1  mov     rbx, [rsp+50h+arg_0]
0x180014aa9  add     rsp, 50h
0x180014aad  pop     r15
0x180014aaf  pop     r14
0x180014ab1  pop     rdi
0x180014ab2  pop     rsi
0x180014ab3  pop     rbp
0x180014ab4  retn
```
