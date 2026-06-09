# IMSAdminBaseW_SetData_Proxy

- ea: `0x180002e90`
- end: `0x180003089`
- name: `IMSAdminBaseW_SetData_Proxy`
- size: `505`
- prototype: `HRESULT __stdcall(IMSAdminBaseW *This, METADATA_HANDLE hMDHandle, LPCWSTR pszMDPath, PMETADATA_RECORD pmdrMDData)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180001124`
- `0x180002e90`
- `0x1800031f4`
- `0x180003538`
- `0x180003f60`
- `0x180009010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002f6b`
- `KERNEL32!EnterCriticalSection` at `0x180002f6b`
- `KERNEL32!LeaveCriticalSection` at `0x180002f8f`
- `KERNEL32!LeaveCriticalSection` at `0x180002f9a`
- `KERNEL32!LeaveCriticalSection` at `0x180002f8f`
- `KERNEL32!LeaveCriticalSection` at `0x180002f9a`
- `RPCRT4!NdrClientCall2` at `0x18000303d`
- `RPCRT4!NdrClientCall2` at `0x18000303d`
- `ole32!CoTaskMemFree` at `0x180003053`
- `ole32!CoTaskMemFree` at `0x180003053`

## pseudocode

```c
HRESULT __stdcall IMSAdminBaseW_SetData_Proxy(
        IMSAdminBaseW *This,
        METADATA_HANDLE hMDHandle,
        LPCWSTR pszMDPath,
        PMETADATA_RECORD pmdrMDData)
{
  struct ADM_SECURE_DATA *v5; // rdi
  HRESULT Pointer; // ebx
  struct ADM_SECURE_DATA *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, LPVOID *, unsigned __int8 *, _QWORD, _DWORD); // r15
  void *v10; // rcx
  HRESULT v12; // [rsp+30h] [rbp-68h]
  LPVOID pv; // [rsp+38h] [rbp-60h] BYREF
  struct _METADATA_RECORD v14[2]; // [rsp+40h] [rbp-58h] BYREF

  memset(v14, 0, 40);
  v5 = 0;
  pv = 0;
  if ( !pmdrMDData )
  {
    Pointer = -2147024809;
    goto LABEL_17;
  }
  v14[0] = *pmdrMDData;
  if ( (v14[0].dwMDAttributes & 4) == 0 || !v14[0].pbMDData )
    goto LABEL_16;
  v7 = ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData((struct IUnknown *)This);
  v5 = v7;
  if ( !v7 )
  {
    Pointer = -2146646010;
    goto LABEL_17;
  }
  if ( *((_QWORD *)v7 + 4) )
    goto LABEL_12;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 64));
  if ( *((_QWORD *)v5 + 4)
    || (Pointer = ADM_SECURE_DATA::DoClientSideKeyExchange(v5, (struct IUnknown *)This), Pointer >= 0) )
  {
    LeaveCriticalSection(v8);
LABEL_12:
    v9 = (__int64 (__fastcall ***)(_QWORD, LPVOID *, unsigned __int8 *, _QWORD, _DWORD))*((_QWORD *)v5 + 6);
    Pointer = 0;
    goto LABEL_13;
  }
  v9 = 0;
  LeaveCriticalSection(v8);
LABEL_13:
  if ( Pointer >= 0 )
  {
    Pointer = (**v9)(v9, &pv, v14[0].pbMDData, v14[0].dwMDDataLen, 0);
    v12 = Pointer;
    if ( Pointer >= 0 )
    {
      v14[0].pbMDData = (unsigned __int8 *)pv;
      v14[0].dwMDDataLen = *((_DWORD *)pv + 1) + 8;
LABEL_16:
      Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_18000B384, This, hMDHandle, pszMDPath, v14, v12).Pointer;
    }
  }
LABEL_17:
  v10 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v10);
  }
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 6, 0xFFFFFFFF) == 1 )
  {
    ADM_SECURE_DATA::~ADM_SECURE_DATA(v5);
    operator delete(v5);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180002e90  mov     r11, rsp
0x180002e93  mov     [r11+18h], r8
0x180002e97  mov     [rsp+arg_8], edx
0x180002e9b  mov     [r11+8], rcx
0x180002e9f  push    rbx
0x180002ea0  push    rsi
0x180002ea1  push    rdi
0x180002ea2  push    r14
0x180002ea4  push    r15
0x180002ea6  sub     rsp, 70h
0x180002eaa  mov     rsi, rcx
0x180002ead  xorps   xmm0, xmm0
0x180002eb0  xor     eax, eax
0x180002eb2  movups  [rsp+98h+var_58], xmm0
0x180002eb7  movups  [rsp+98h+var_48], xmm0
0x180002ebc  mov     [r11-38h], rax
0x180002ec0  xor     edi, edi
0x180002ec2  mov     [rsp+98h+arg_18], rdi
0x180002eca  mov     [r11-60h], rax
0x180002ece  xor     ebx, ebx
0x180002ed0  test    r9, r9
0x180002ed3  jnz     short loc_180002EDF
0x180002ed5  mov     ebx, 80070057h
0x180002eda  jmp     loc_180003046
0x180002edf  movups  xmm0, xmmword ptr [r9]
0x180002ee3  movups  [rsp+98h+var_58], xmm0
0x180002ee8  movups  xmm1, xmmword ptr [r9+10h]
0x180002eed  movups  [rsp+98h+var_48], xmm1
0x180002ef2  movsd   xmm0, qword ptr [r9+20h]
0x180002ef8  movsd   [rsp+98h+var_38], xmm0
0x180002efe  jmp     short loc_180002F16
0x180002f00  mov     ebx, eax
0x180002f02  bts     ebx, 1Ch
0x180002f06  mov     rsi, [rsp+98h+arg_0]
0x180002f0e  mov     rdi, [rsp+98h+arg_18]
0x180002f16  test    ebx, ebx
0x180002f18  js      loc_180003046
0x180002f1e  mov     rax, qword ptr [rsp+98h+var_58]
0x180002f23  shr     rax, 20h
0x180002f27  test    al, 4
0x180002f29  jz      loc_18000300D
0x180002f2f  cmp     qword ptr [rsp+98h+var_48+8], 0
0x180002f35  jz      loc_18000300D
0x180002f3b  mov     rcx, rsi; struct IUnknown *
0x180002f3e  call    ?FindOrAddAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@@Z; ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(IUnknown *)
0x180002f43  mov     rdi, rax
0x180002f46  mov     [rsp+98h+arg_18], rax
0x180002f4e  test    rax, rax
0x180002f51  jnz     short loc_180002F5D
0x180002f53  mov     ebx, 800CC806h
0x180002f58  jmp     loc_180003046
0x180002f5d  cmp     qword ptr [rax+20h], 0
0x180002f62  jnz     short loc_180002FA0
0x180002f64  lea     r14, [rax+40h]
0x180002f68  mov     rcx, r14; lpCriticalSection
0x180002f6b  call    cs:__imp_EnterCriticalSection
0x180002f71  cmp     qword ptr [rdi+20h], 0
0x180002f76  jnz     short loc_180002F97
0x180002f78  mov     rdx, rsi; struct IUnknown *
0x180002f7b  mov     rcx, rdi; this
0x180002f7e  call    ?DoClientSideKeyExchange@ADM_SECURE_DATA@@AEAAJPEAUIUnknown@@@Z; ADM_SECURE_DATA::DoClientSideKeyExchange(IUnknown *)
0x180002f83  mov     ebx, eax
0x180002f85  test    eax, eax
0x180002f87  jns     short loc_180002F97
0x180002f89  xor     r15d, r15d
0x180002f8c  mov     rcx, r14; lpCriticalSection
0x180002f8f  call    cs:__imp_LeaveCriticalSection
0x180002f95  jmp     short loc_180002FA6
0x180002f97  mov     rcx, r14; lpCriticalSection
0x180002f9a  call    cs:__imp_LeaveCriticalSection
0x180002fa0  mov     r15, [rdi+30h]
0x180002fa4  xor     ebx, ebx
0x180002fa6  test    ebx, ebx
0x180002fa8  js      loc_180003046
0x180002fae  mov     rax, [r15]
0x180002fb1  mov     dword ptr [rsp+98h+var_78], 0
0x180002fb9  mov     r9d, dword ptr [rsp+98h+var_48]
0x180002fbe  mov     r8, qword ptr [rsp+98h+var_48+8]
0x180002fc3  lea     rdx, [rsp+98h+pv]
0x180002fc8  mov     rcx, r15
0x180002fcb  mov     rax, [rax]
0x180002fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd3  mov     ebx, eax
0x180002fd5  mov     [rsp+98h+var_68], eax
0x180002fd9  jmp     short loc_180002FF5
0x180002fdb  mov     ebx, eax
0x180002fdd  bts     ebx, 1Ch
0x180002fe1  mov     [rsp+98h+var_68], ebx
0x180002fe5  mov     rsi, [rsp+98h+arg_0]
0x180002fed  mov     rdi, [rsp+98h+arg_18]
0x180002ff5  test    ebx, ebx
0x180002ff7  js      short loc_180003046
0x180002ff9  mov     rax, [rsp+98h+pv]
0x180002ffe  mov     qword ptr [rsp+98h+var_48+8], rax
0x180003003  mov     ecx, [rax+4]
0x180003006  add     ecx, 8
0x180003009  mov     dword ptr [rsp+98h+var_48], ecx
0x18000300d  lea     rax, [rsp+98h+var_58]
0x180003012  mov     [rsp+98h+var_70], rax
0x180003017  mov     rax, [rsp+98h+arg_10]
0x18000301f  mov     [rsp+98h+var_78], rax
0x180003024  mov     r9d, [rsp+98h+arg_8]
0x18000302c  mov     r8, rsi
0x18000302f  lea     rdx, byte_18000B384; pFormat
0x180003036  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000303d  call    cs:__imp_NdrClientCall2
0x180003043  mov     rbx, rax
0x180003046  mov     rcx, [rsp+98h+pv]; pv
0x18000304b  test    rcx, rcx
0x18000304e  jz      short loc_180003059
0x180003050  mov     byte ptr [rcx], 58h ; 'X'
0x180003053  call    cs:__imp_CoTaskMemFree
0x180003059  test    rdi, rdi
0x18000305c  jz      short loc_18000307B
0x18000305e  or      eax, 0FFFFFFFFh
0x180003061  lock xadd [rdi+18h], eax
0x180003066  cmp     eax, 1
0x180003069  jnz     short loc_18000307B
0x18000306b  mov     rcx, rdi; this
0x18000306e  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180003073  mov     rcx, rdi; Block
0x180003076  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000307b  mov     eax, ebx
0x18000307d  add     rsp, 70h
0x180003081  pop     r15
0x180003083  pop     r14
0x180003085  pop     rdi
0x180003086  pop     rsi
0x180003087  pop     rbx
0x180003088  retn
```
