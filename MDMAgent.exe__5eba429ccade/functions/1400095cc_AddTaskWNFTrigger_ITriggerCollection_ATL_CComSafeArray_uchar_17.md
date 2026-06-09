# AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)

- ea: `0x1400095cc`
- end: `0x1400096d6`
- name: `?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d0fc`

## callees

- `0x140008b48`
- `0x140008e48`
- `0x1400095cc`
- `0x140019010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400096b4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400096b4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1400096a7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1400096a7`

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
0x1400095cc  push    rbp
0x1400095ce  push    rbx
0x1400095cf  push    rdi
0x1400095d0  mov     rbp, rsp
0x1400095d3  sub     rsp, 20h
0x1400095d7  mov     rax, [rcx]
0x1400095da  lea     r8, [rbp+arg_10]
0x1400095de  mov     rdi, rdx
0x1400095e1  mov     [rbp+arg_10], 0
0x1400095e9  mov     edx, 0Ch
0x1400095ee  mov     rax, [rax+50h]
0x1400095f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095f7  mov     ebx, eax
0x1400095f9  test    eax, eax
0x1400095fb  jns     short loc_14000960D
0x1400095fd  lea     rcx, [rbp+arg_10]
0x140009601  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x140009606  mov     eax, ebx
0x140009608  jmp     loc_1400096CE
0x14000960d  mov     rcx, [rbp+arg_10]
0x140009611  lea     r8, [rbp+arg_0]
0x140009615  mov     [rbp+arg_0], 0
0x14000961d  lea     rdx, IID_IWnfStateChangeTrigger
0x140009624  mov     rax, [rcx]
0x140009627  mov     rax, [rax]
0x14000962a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000962f  mov     ebx, eax
0x140009631  test    eax, eax
0x140009633  jns     short loc_140009640
0x140009635  lea     rcx, [rbp+arg_0]
0x140009639  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000963e  jmp     short loc_1400095FD
0x140009640  mov     rcx, [rbp+arg_0]
0x140009644  or      edx, 0FFFFFFFFh
0x140009647  mov     rax, [rcx]
0x14000964a  mov     rax, [rax+98h]
0x140009651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009656  mov     ebx, eax
0x140009658  test    eax, eax
0x14000965a  js      short loc_140009635
0x14000965c  mov     rcx, [rbp+arg_0]
0x140009660  mov     rdx, [rdi]
0x140009663  mov     rax, [rcx]
0x140009666  mov     rax, [rax+0B8h]
0x14000966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009672  mov     ebx, eax
0x140009674  test    eax, eax
0x140009676  js      short loc_140009635
0x140009678  xor     edx, edx
0x14000967a  lea     rcx, [rbp+psa]
0x14000967e  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x140009683  mov     rcx, [rbp+arg_0]
0x140009687  mov     rbx, [rbp+psa]
0x14000968b  mov     rdx, rbx
0x14000968e  mov     rax, [rcx]
0x140009691  mov     rax, [rax+0C8h]
0x140009698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000969d  mov     edi, eax
0x14000969f  test    rbx, rbx
0x1400096a2  jz      short loc_1400096BA
0x1400096a4  mov     rcx, rbx; psa
0x1400096a7  call    cs:__imp_SafeArrayUnlock
0x1400096ad  test    eax, eax
0x1400096af  js      short loc_1400096BA
0x1400096b1  mov     rcx, rbx; psa
0x1400096b4  call    cs:__imp_SafeArrayDestroy
0x1400096ba  lea     rcx, [rbp+arg_0]
0x1400096be  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1400096c3  lea     rcx, [rbp+arg_10]
0x1400096c7  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x1400096cc  mov     eax, edi
0x1400096ce  add     rsp, 20h
0x1400096d2  pop     rdi
0x1400096d3  pop     rbx
0x1400096d4  pop     rbp
0x1400096d5  retn
```
