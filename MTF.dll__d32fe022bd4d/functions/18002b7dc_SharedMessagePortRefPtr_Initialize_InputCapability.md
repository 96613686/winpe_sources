# SharedMessagePortRefPtr::Initialize(InputCapability)

- ea: `0x18002b7dc`
- end: `0x18002b995`
- name: `?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800236cc`

## callees

- `0x18000a440`
- `0x18001048c`
- `0x18002b7dc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b979`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b87b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b87b`
- `CoreUIComponents!CoreUIClientCreate` at `0x18002b804`
- `CoreUIComponents!CoreUIClientCreate` at `0x18002b804`

## pseudocode

```c
__int64 __fastcall SharedMessagePortRefPtr::Initialize(_QWORD *a1)
{
  PSECURITY_DESCRIPTOR v2; // r14
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // ecx
  __int64 (__fastcall *v9)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *); // r11
  const unsigned __int16 *const near *v10; // rax
  const unsigned __int16 *const near *v11; // rdx
  int v12; // ecx
  __int64 v13; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *const near *v17; // [rsp+40h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+78h] [rbp+28h]
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF
  __int64 v20; // [rsp+98h] [rbp+48h] BYREF

  v20 = 0;
  v19 = 0;
  v2 = 0;
  v3 = CoreUIClientCreate(&v20);
  v6 = v3;
  if ( v3 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v7 = 116;
    goto LABEL_4;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, &v19);
  v6 = v3;
  if ( v3 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-419202837"
             "2-3968301570-1997628692-1435953622)",
            1u,
            &SecurityDescriptor,
            0) )
      FailFastWithHR(v8, retaddr, 0xF3u);
    v2 = SecurityDescriptor;
    SecurityDescriptor = 0;
    v9 = *(__int64 (__fastcall **)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *))(*(_QWORD *)v19 + 24LL);
    v10 = c_wszMessagePortNames;
    if ( c_wszMessagePortNames )
    {
      v11 = c_wszMessagePortNames;
      v17 = c_wszMessagePortNames;
      v12 = 0;
      while ( *(_WORD *)v10 )
      {
        v10 = (const unsigned __int16 *const near *)((char *)v10 + 2);
        ++v12;
      }
      v16 = v12 | 0x80000000;
    }
    else
    {
      v11 = 0;
      v17 = 0;
    }
    v3 = v9(v19, (unsigned __int64)&v16 & -(__int64)(v11 != 0), v2, a1 + 1);
    v6 = v3;
    if ( v3 >= 0 )
    {
      v13 = v19;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      if ( *a1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = v13;
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v7 = 127;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v7 = 119;
LABEL_4:
    McTemplateU0sqq_EventWriteTransfer(v5, v4, (unsigned int)"SharedMessagePortRefPtr::Initialize", v7, v3);
  }
LABEL_24:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  LocalFree(v2);
  return v6;
}

```

## disassembly

```asm
0x18002b7dc  mov     [rsp-28h+arg_0], rbx
0x18002b7e1  push    rbp
0x18002b7e2  push    rsi
0x18002b7e3  push    rdi
0x18002b7e4  push    r14
0x18002b7e6  push    r15
0x18002b7e8  mov     rbp, rsp
0x18002b7eb  sub     rsp, 50h
0x18002b7ef  xor     r15d, r15d
0x18002b7f2  mov     rsi, rcx
0x18002b7f5  lea     rcx, [rbp+arg_18]
0x18002b7f9  mov     [rbp+arg_18], r15
0x18002b7fd  mov     [rbp+arg_10], r15
0x18002b801  mov     r14d, r15d
0x18002b804  call    cs:__imp_CoreUIClientCreate
0x18002b80a  mov     ebx, eax
0x18002b80c  test    eax, eax
0x18002b80e  jns     short loc_18002B836
0x18002b810  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18002b817  jz      loc_18002B944
0x18002b81d  lea     r9d, [r15+74h]
0x18002b821  lea     r8, aSharedmessagep; "SharedMessagePortRefPtr::Initialize"
0x18002b828  mov     [rsp+50h+var_30], eax
0x18002b82c  call    McTemplateU0sqq_EventWriteTransfer
0x18002b831  jmp     loc_18002B944
0x18002b836  mov     rcx, [rbp+arg_18]
0x18002b83a  lea     rdx, [rbp+arg_10]
0x18002b83e  mov     rax, [rcx]
0x18002b841  mov     rax, [rax+30h]
0x18002b845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b84a  mov     ebx, eax
0x18002b84c  test    eax, eax
0x18002b84e  jns     short loc_18002B865
0x18002b850  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18002b857  jz      loc_18002B944
0x18002b85d  mov     r9d, 77h ; 'w'
0x18002b863  jmp     short loc_18002B821
0x18002b865  xor     r9d, r9d; SecurityDescriptorSize
0x18002b868  mov     [rbp+SecurityDescriptor], r15
0x18002b86c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002b870  lea     rcx, StringSecurityDescriptor; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x18002b877  lea     edx, [r9+1]; StringSDRevision
0x18002b87b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002b881  test    eax, eax
0x18002b883  jnz     short loc_18002B894
0x18002b885  mov     rdx, [rbp+28h]; unsigned __int64
0x18002b889  mov     r8d, 0F3h; unsigned __int64
0x18002b88f  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18002b894  mov     r10, [rbp+arg_10]
0x18002b898  mov     r14, [rbp+SecurityDescriptor]
0x18002b89c  mov     [rbp+SecurityDescriptor], r15
0x18002b8a0  mov     rax, [r10]
0x18002b8a3  mov     r11, [rax+18h]
0x18002b8a7  mov     rax, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x18002b8ae  test    rax, rax
0x18002b8b1  jz      short loc_18002B8D5
0x18002b8b3  mov     rdx, rax
0x18002b8b6  mov     [rbp+var_10], rax
0x18002b8ba  mov     rcx, r15
0x18002b8bd  jmp     short loc_18002B8C6
0x18002b8bf  lea     rax, [rax+2]
0x18002b8c3  inc     rcx
0x18002b8c6  cmp     [rax], r15w
0x18002b8ca  jnz     short loc_18002B8BF
0x18002b8cc  bts     ecx, 1Fh
0x18002b8d0  mov     [rbp+var_18], ecx
0x18002b8d3  jmp     short loc_18002B8DC
0x18002b8d5  mov     rdx, r15
0x18002b8d8  mov     [rbp+var_10], rdx
0x18002b8dc  neg     rdx
0x18002b8df  lea     rax, [rbp+var_18]
0x18002b8e3  lea     r9, [rsi+8]
0x18002b8e7  mov     r8, r14
0x18002b8ea  sbb     rdx, rdx
0x18002b8ed  mov     rcx, r10
0x18002b8f0  and     rdx, rax
0x18002b8f3  mov     rax, r11
0x18002b8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8fb  mov     ebx, eax
0x18002b8fd  test    eax, eax
0x18002b8ff  jns     short loc_18002B915
0x18002b901  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18002b908  jz      short loc_18002B944
0x18002b90a  mov     r9d, 7Fh
0x18002b910  jmp     loc_18002B821
0x18002b915  mov     rdi, [rbp+arg_10]
0x18002b919  test    rdi, rdi
0x18002b91c  jz      short loc_18002B92D
0x18002b91e  mov     rax, [rdi]
0x18002b921  mov     rcx, rdi
0x18002b924  mov     rax, [rax+8]
0x18002b928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b92d  mov     rcx, [rsi]
0x18002b930  test    rcx, rcx
0x18002b933  jz      short loc_18002B941
0x18002b935  mov     rax, [rcx]
0x18002b938  mov     rax, [rax+10h]
0x18002b93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b941  mov     [rsi], rdi
0x18002b944  mov     rcx, [rbp+arg_18]
0x18002b948  test    rcx, rcx
0x18002b94b  jz      short loc_18002B95D
0x18002b94d  mov     rax, [rcx]
0x18002b950  mov     rax, [rax+10h]
0x18002b954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b959  mov     [rbp+arg_18], r15
0x18002b95d  mov     rcx, [rbp+arg_10]
0x18002b961  test    rcx, rcx
0x18002b964  jz      short loc_18002B976
0x18002b966  mov     rax, [rcx]
0x18002b969  mov     rax, [rax+10h]
0x18002b96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b972  mov     [rbp+arg_10], r15
0x18002b976  mov     rcx, r14; hMem
0x18002b979  call    cs:__imp_LocalFree
0x18002b97f  mov     eax, ebx
0x18002b981  mov     rbx, [rsp+50h+arg_0]
0x18002b989  add     rsp, 50h
0x18002b98d  pop     r15
0x18002b98f  pop     r14
0x18002b991  pop     rdi
0x18002b992  pop     rsi
0x18002b993  pop     rbp
0x18002b994  retn
```
