# SensorDevice::TraceObject(IFSTraceString * *)

- ea: `0x180049f10`
- end: `0x18004a06c`
- name: `?TraceObject@SensorDevice@@UEAAJPEAPEAUIFSTraceString@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, struct IFSTraceString **)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180008f9c`
- `0x18001b3d8`
- `0x18003f334`
- `0x18003f56c`
- `0x180049f10`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a043`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a043`

## pseudocode

```c
__int64 __fastcall SensorDevice::TraceObject(SensorDevice *this, struct IFSTraceString **a2)
{
  int v4; // ebx
  const char *v5; // r14
  FSTraceString *v6; // r15
  int v7; // ebx
  const char *v8; // rsi
  int v9; // edi
  unsigned int v10; // eax
  LPVOID v12; // [rsp+40h] [rbp-10h] BYREF
  struct FSTraceString *v13; // [rsp+48h] [rbp-8h] BYREF
  int v14; // [rsp+98h] [rbp+48h] BYREF
  int v15; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+58h] BYREF

  v13 = 0;
  pv = 0;
  v14 = 0;
  v12 = 0;
  v15 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = FSTraceString::CreateFSTraceString(&v13);
    if ( v4 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, const IID *, LPVOID *, int *))(**((_QWORD **)this + 12) + 104LL))(
        *((_QWORD *)this + 12),
        &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
        &pv,
        &v14);
      (*(void (__fastcall **)(_QWORD, const IID *, LPVOID *, int *))(**((_QWORD **)this + 12) + 104LL))(
        *((_QWORD *)this + 12),
        &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
        &v12,
        &v15);
      v5 = L"<null>";
      v6 = v13;
      v7 = *((_DWORD *)this + 44);
      v8 = L"<null>";
      v9 = *((_DWORD *)this + 45);
      if ( v12 )
        v8 = (const char *)v12;
      if ( pv )
        v5 = (const char *)pv;
      v10 = MFGetAttributeUINT32(*((_QWORD *)this + 12), MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE, 0);
      FSTraceString::SetFormatString(
        v6,
        "strmcount=%u,type=%d,faceauth=%d,secure=%d,fname=%ws,devname=%ws",
        *((unsigned int *)this + 30),
        v10,
        v9,
        v7,
        v5,
        v8);
      v4 = (**(__int64 (__fastcall ***)(FSTraceString *, GUID *, struct IFSTraceString **))v6)(
             v6,
             &GUID_3858aded_fdea_4e35_bd7a_f90c8e8727bf,
             a2);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v12 )
      CoTaskMemFree(v12);
  }
  else
  {
    v4 = -2147467261;
  }
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180049f10  mov     [rsp-38h+arg_0], rbx
0x180049f15  push    rbp
0x180049f16  push    rsi
0x180049f17  push    rdi
0x180049f18  push    r12
0x180049f1a  push    r13
0x180049f1c  push    r14
0x180049f1e  push    r15
0x180049f20  mov     rbp, rsp
0x180049f23  sub     rsp, 50h
0x180049f27  xor     edi, edi
0x180049f29  mov     r12, rdx
0x180049f2c  mov     [rbp+var_8], rdi
0x180049f30  mov     r13, rcx
0x180049f33  mov     [rbp+pv], rdi
0x180049f37  mov     [rbp+arg_8], edi
0x180049f3a  mov     [rbp+var_10], rdi
0x180049f3e  mov     [rbp+arg_10], edi
0x180049f41  test    rdx, rdx
0x180049f44  jnz     short loc_180049F50
0x180049f46  mov     ebx, 80004003h
0x180049f4b  jmp     loc_18004A049
0x180049f50  lea     rcx, [rbp+var_8]; struct FSTraceString **
0x180049f54  mov     [rdx], rdi
0x180049f57  call    ?CreateFSTraceString@FSTraceString@@SAJPEAPEAV1@@Z; FSTraceString::CreateFSTraceString(FSTraceString * *)
0x180049f5c  mov     ebx, eax
0x180049f5e  test    eax, eax
0x180049f60  js      loc_18004A02B
0x180049f66  mov     rcx, [r13+60h]
0x180049f6a  lea     r9, [rbp+arg_8]
0x180049f6e  lea     r8, [rbp+pv]
0x180049f72  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x180049f79  mov     rax, [rcx]
0x180049f7c  mov     rax, [rax+68h]
0x180049f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f85  mov     rcx, [r13+60h]
0x180049f89  lea     r9, [rbp+arg_10]
0x180049f8d  lea     r8, [rbp+var_10]
0x180049f91  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180049f98  mov     rax, [rcx]
0x180049f9b  mov     rax, [rax+68h]
0x180049f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fa4  mov     rax, [rbp+var_10]
0x180049fa8  lea     r14, aNull_0; "<null>"
0x180049faf  mov     rcx, [r13+60h]
0x180049fb3  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE
0x180049fba  mov     r15, [rbp+var_8]
0x180049fbe  test    rax, rax
0x180049fc1  mov     ebx, [r13+0B0h]
0x180049fc8  mov     rsi, r14
0x180049fcb  mov     edi, [r13+0B4h]
0x180049fd2  cmovnz  rsi, rax
0x180049fd6  mov     rax, [rbp+pv]
0x180049fda  test    rax, rax
0x180049fdd  cmovnz  r14, rax
0x180049fe1  xor     r8d, r8d
0x180049fe4  call    MFGetAttributeUINT32
0x180049fe9  mov     r8d, [r13+78h]
0x180049fed  lea     rdx, aStrmcountUType; "strmcount=%u,type=%d,faceauth=%d,secure"...
0x180049ff4  mov     [rsp+50h+var_18], rsi
0x180049ff9  mov     r9d, eax
0x180049ffc  mov     [rsp+50h+var_20], r14
0x18004a001  mov     rcx, r15; this
0x18004a004  mov     [rsp+50h+var_28], ebx
0x18004a008  mov     [rsp+50h+var_30], edi
0x18004a00c  call    ?SetFormatString@FSTraceString@@QEAAXPEBDZZ; FSTraceString::SetFormatString(char const *,...)
0x18004a011  mov     rax, [r15]
0x18004a014  lea     rdx, _GUID_3858aded_fdea_4e35_bd7a_f90c8e8727bf
0x18004a01b  mov     r8, r12
0x18004a01e  mov     rcx, r15
0x18004a021  mov     rax, [rax]
0x18004a024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a029  mov     ebx, eax
0x18004a02b  mov     rcx, [rbp+pv]; pv
0x18004a02f  test    rcx, rcx
0x18004a032  jz      short loc_18004A03A
0x18004a034  call    cs:__imp_CoTaskMemFree
0x18004a03a  mov     rcx, [rbp+var_10]; pv
0x18004a03e  test    rcx, rcx
0x18004a041  jz      short loc_18004A049
0x18004a043  call    cs:__imp_CoTaskMemFree
0x18004a049  lea     rcx, [rbp+var_8]
0x18004a04d  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004a052  mov     eax, ebx
0x18004a054  mov     rbx, [rsp+50h+arg_0]
0x18004a05c  add     rsp, 50h
0x18004a060  pop     r15
0x18004a062  pop     r14
0x18004a064  pop     r13
0x18004a066  pop     r12
0x18004a068  pop     rdi
0x18004a069  pop     rsi
0x18004a06a  pop     rbp
0x18004a06b  retn
```
