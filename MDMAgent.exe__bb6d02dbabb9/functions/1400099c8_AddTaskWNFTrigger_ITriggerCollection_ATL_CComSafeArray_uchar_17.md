# AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)

- ea: `0x1400099c8`
- end: `0x140009adf`
- name: `?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d780`

## callees

- `0x140008f4c`
- `0x140009268`
- `0x1400099c8`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140009ab6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140009ab6`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140009aa3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140009aa3`

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
0x1400099c8  push    rbp
0x1400099ca  push    rbx
0x1400099cb  push    rdi
0x1400099cc  mov     rbp, rsp
0x1400099cf  sub     rsp, 20h
0x1400099d3  mov     rax, [rcx]
0x1400099d6  lea     r8, [rbp+arg_10]
0x1400099da  mov     rdi, rdx
0x1400099dd  mov     [rbp+arg_10], 0
0x1400099e5  mov     edx, 0Ch
0x1400099ea  mov     rax, [rax+50h]
0x1400099ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099f3  mov     ebx, eax
0x1400099f5  test    eax, eax
0x1400099f7  jns     short loc_140009A09
0x1400099f9  lea     rcx, [rbp+arg_10]
0x1400099fd  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x140009a02  mov     eax, ebx
0x140009a04  jmp     loc_140009AD6
0x140009a09  mov     rcx, [rbp+arg_10]
0x140009a0d  lea     r8, [rbp+arg_0]
0x140009a11  mov     [rbp+arg_0], 0
0x140009a19  lea     rdx, IID_IWnfStateChangeTrigger
0x140009a20  mov     rax, [rcx]
0x140009a23  mov     rax, [rax]
0x140009a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a2b  mov     ebx, eax
0x140009a2d  test    eax, eax
0x140009a2f  jns     short loc_140009A3C
0x140009a31  lea     rcx, [rbp+arg_0]
0x140009a35  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x140009a3a  jmp     short loc_1400099F9
0x140009a3c  mov     rcx, [rbp+arg_0]
0x140009a40  or      edx, 0FFFFFFFFh
0x140009a43  mov     rax, [rcx]
0x140009a46  mov     rax, [rax+98h]
0x140009a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a52  mov     ebx, eax
0x140009a54  test    eax, eax
0x140009a56  js      short loc_140009A31
0x140009a58  mov     rcx, [rbp+arg_0]
0x140009a5c  mov     rdx, [rdi]
0x140009a5f  mov     rax, [rcx]
0x140009a62  mov     rax, [rax+0B8h]
0x140009a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a6e  mov     ebx, eax
0x140009a70  test    eax, eax
0x140009a72  js      short loc_140009A31
0x140009a74  xor     edx, edx
0x140009a76  lea     rcx, [rbp+psa]
0x140009a7a  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x140009a7f  mov     rcx, [rbp+arg_0]
0x140009a83  mov     rbx, [rbp+psa]
0x140009a87  mov     rdx, rbx
0x140009a8a  mov     rax, [rcx]
0x140009a8d  mov     rax, [rax+0C8h]
0x140009a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a99  mov     edi, eax
0x140009a9b  test    rbx, rbx
0x140009a9e  jz      short loc_140009AC2
0x140009aa0  mov     rcx, rbx; psa
0x140009aa3  call    cs:__imp_SafeArrayUnlock
0x140009aaa  nop     dword ptr [rax+rax+00h]
0x140009aaf  test    eax, eax
0x140009ab1  js      short loc_140009AC2
0x140009ab3  mov     rcx, rbx; psa
0x140009ab6  call    cs:__imp_SafeArrayDestroy
0x140009abd  nop     dword ptr [rax+rax+00h]
0x140009ac2  lea     rcx, [rbp+arg_0]
0x140009ac6  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x140009acb  lea     rcx, [rbp+arg_10]
0x140009acf  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x140009ad4  mov     eax, edi
0x140009ad6  add     rsp, 20h
0x140009ada  pop     rdi
0x140009adb  pop     rbx
0x140009adc  pop     rbp
0x140009add  retn
```
