# AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)

- ea: `0x180007e2c`
- end: `0x180007f43`
- name: `?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c980`

## callees

- `0x180006f74`
- `0x180007364`
- `0x180007e2c`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007f1a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007f1a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007f07`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007f07`

## pseudocode

```c
__int64 __fastcall AddTaskWNFTrigger(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rax
  int v4; // ebx
  SAFEARRAY *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // [rsp+40h] [rbp+20h] BYREF
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+30h] BYREF
  SAFEARRAY *psa; // [rsp+58h] [rbp+38h] BYREF

  v2 = *a1;
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v2 + 80))(a1, 12, &v9);
  if ( v4 < 0 )
    goto LABEL_2;
  v8 = 0;
  v4 = (**v9)(v9, &IID_IWnfStateChangeTrigger, &v8);
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 152LL))(v8, 0xFFFFFFFFLL), v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 184LL))(v8, *a2), v4 < 0) )
  {
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v8);
LABEL_2:
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v9);
    return (unsigned int)v4;
  }
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  v6 = psa;
  v7 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v8 + 200LL))(v8, psa);
  if ( v6 )
  {
    if ( SafeArrayUnlock(v6) >= 0 )
      SafeArrayDestroy(v6);
  }
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v8);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v9);
  return v7;
}

```

## disassembly

```asm
0x180007e2c  push    rbp
0x180007e2e  push    rbx
0x180007e2f  push    rdi
0x180007e30  mov     rbp, rsp
0x180007e33  sub     rsp, 20h
0x180007e37  mov     rax, [rcx]
0x180007e3a  lea     r8, [rbp+arg_10]
0x180007e3e  mov     rdi, rdx
0x180007e41  mov     [rbp+arg_10], 0
0x180007e49  mov     edx, 0Ch
0x180007e4e  mov     rax, [rax+50h]
0x180007e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e57  mov     ebx, eax
0x180007e59  test    eax, eax
0x180007e5b  jns     short loc_180007E6D
0x180007e5d  lea     rcx, [rbp+arg_10]
0x180007e61  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180007e66  mov     eax, ebx
0x180007e68  jmp     loc_180007F3A
0x180007e6d  mov     rcx, [rbp+arg_10]
0x180007e71  lea     r8, [rbp+arg_0]
0x180007e75  mov     [rbp+arg_0], 0
0x180007e7d  lea     rdx, IID_IWnfStateChangeTrigger
0x180007e84  mov     rax, [rcx]
0x180007e87  mov     rax, [rax]
0x180007e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e8f  mov     ebx, eax
0x180007e91  test    eax, eax
0x180007e93  jns     short loc_180007EA0
0x180007e95  lea     rcx, [rbp+arg_0]
0x180007e99  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180007e9e  jmp     short loc_180007E5D
0x180007ea0  mov     rcx, [rbp+arg_0]
0x180007ea4  or      edx, 0FFFFFFFFh
0x180007ea7  mov     rax, [rcx]
0x180007eaa  mov     rax, [rax+98h]
0x180007eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb6  mov     ebx, eax
0x180007eb8  test    eax, eax
0x180007eba  js      short loc_180007E95
0x180007ebc  mov     rcx, [rbp+arg_0]
0x180007ec0  mov     rdx, [rdi]
0x180007ec3  mov     rax, [rcx]
0x180007ec6  mov     rax, [rax+0B8h]
0x180007ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed2  mov     ebx, eax
0x180007ed4  test    eax, eax
0x180007ed6  js      short loc_180007E95
0x180007ed8  xor     edx, edx
0x180007eda  lea     rcx, [rbp+psa]
0x180007ede  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180007ee3  mov     rcx, [rbp+arg_0]
0x180007ee7  mov     rbx, [rbp+psa]
0x180007eeb  mov     rdx, rbx
0x180007eee  mov     rax, [rcx]
0x180007ef1  mov     rax, [rax+0C8h]
0x180007ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007efd  mov     edi, eax
0x180007eff  test    rbx, rbx
0x180007f02  jz      short loc_180007F26
0x180007f04  mov     rcx, rbx; psa
0x180007f07  call    cs:__imp_SafeArrayUnlock
0x180007f0e  nop     dword ptr [rax+rax+00h]
0x180007f13  test    eax, eax
0x180007f15  js      short loc_180007F26
0x180007f17  mov     rcx, rbx; psa
0x180007f1a  call    cs:__imp_SafeArrayDestroy
0x180007f21  nop     dword ptr [rax+rax+00h]
0x180007f26  lea     rcx, [rbp+arg_0]
0x180007f2a  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180007f2f  lea     rcx, [rbp+arg_10]
0x180007f33  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180007f38  mov     eax, edi
0x180007f3a  add     rsp, 20h
0x180007f3e  pop     rdi
0x180007f3f  pop     rbx
0x180007f40  pop     rbp
0x180007f41  retn
```
