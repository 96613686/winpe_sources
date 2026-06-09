# FSVMMediaBuffer::~FSVMMediaBuffer(void)

- ea: `0x1800e7770`
- end: `0x1800e78ba`
- name: `??1FSVMMediaBuffer@@MEAA@XZ`
- size: `330`
- prototype: `void __fastcall(FSVMMediaBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e1474`
- `0x1800e78c0`

## callees

- `0x180008cf0`
- `0x1800095c8`
- `0x1800e5e24`
- `0x1800e7770`
- `0x1800e8390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e782d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e782d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e77f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e77f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e78a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e78a2`

## pseudocode

```c
void __fastcall FSVMMediaBuffer::~FSVMMediaBuffer(FSVMMediaBuffer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  *(_QWORD *)this = &FSVMMediaBuffer::`vftable'{for `FSVMObject'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  *((_QWORD *)this + 4) = &FSVMServerMediaBuffer::`vftable'{for `IFSVMMediaBuffer'};
  *((_QWORD *)this + 5) = &FSVMMediaBuffer::`vftable'{for `IMFMediaBuffer'};
  *((_QWORD *)this + 6) = &FSVMServerMediaBuffer::`vftable'{for `IMFMediaBufferInternal'};
  *((_QWORD *)this + 7) = &FSVMMediaBuffer::`vftable'{for `IMF2DBuffer2'};
  *((_QWORD *)this + 8) = &FSVMServerMediaBuffer::`vftable'{for `IMF2DBuffer2Internal'};
  *((_QWORD *)this + 9) = &FSVMServerMediaBuffer::`vftable'{for `IMF2DBuffer3Internal'};
  *((_QWORD *)this + 10) = &FSVMMediaBuffer::`vftable'{for `IMFDXGIBuffer'};
  *((_QWORD *)this + 11) = &FSVMServerMediaBuffer::`vftable'{for `IMFDXGIBufferInternal'};
  *((_QWORD *)this + 12) = &FSVMMediaBuffer::`vftable'{for `IMFGetService'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  FSVMMediaBuffer::InternalClose(this);
  if ( (unsigned __int8)byte_18010EC53 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 57), 11, &WPP_bf0389658ee6330598387757c9c6501a_Traceguids, this);
  LeaveCriticalSection(v2);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 224);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 216);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 208);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 200);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 192);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 184);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 176);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 168);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 152);
  DeleteCriticalSection(v2);
  FSVMObject::~FSVMObject(this);
}

```

## disassembly

```asm
0x1800e7770  mov     [rsp+arg_0], rbx
0x1800e7775  push    rdi
0x1800e7776  sub     rsp, 20h
0x1800e777a  lea     rax, ??_7FSVMMediaBuffer@@6BFSVMObject@@@; const FSVMMediaBuffer::`vftable'{for `FSVMObject'}
0x1800e7781  mov     rbx, rcx
0x1800e7784  mov     [rcx], rax
0x1800e7787  lea     rdi, [rcx+68h]
0x1800e778b  lea     rax, ??_7FSVMServerMediaBuffer@@6BIFSVMMediaBuffer@@@; const FSVMServerMediaBuffer::`vftable'{for `IFSVMMediaBuffer'}
0x1800e7792  mov     [rcx+20h], rax
0x1800e7796  lea     rax, ??_7FSVMMediaBuffer@@6BIMFMediaBuffer@@@; const FSVMMediaBuffer::`vftable'{for `IMFMediaBuffer'}
0x1800e779d  mov     [rcx+28h], rax
0x1800e77a1  lea     rax, ??_7FSVMServerMediaBuffer@@6BIMFMediaBufferInternal@@@; const FSVMServerMediaBuffer::`vftable'{for `IMFMediaBufferInternal'}
0x1800e77a8  mov     [rcx+30h], rax
0x1800e77ac  lea     rax, ??_7FSVMMediaBuffer@@6BIMF2DBuffer2@@@; const FSVMMediaBuffer::`vftable'{for `IMF2DBuffer2'}
0x1800e77b3  mov     [rcx+38h], rax
0x1800e77b7  lea     rax, ??_7FSVMServerMediaBuffer@@6BIMF2DBuffer2Internal@@@; const FSVMServerMediaBuffer::`vftable'{for `IMF2DBuffer2Internal'}
0x1800e77be  mov     [rcx+40h], rax
0x1800e77c2  lea     rax, ??_7FSVMServerMediaBuffer@@6BIMF2DBuffer3Internal@@@; const FSVMServerMediaBuffer::`vftable'{for `IMF2DBuffer3Internal'}
0x1800e77c9  mov     [rcx+48h], rax
0x1800e77cd  lea     rax, ??_7FSVMMediaBuffer@@6BIMFDXGIBuffer@@@; const FSVMMediaBuffer::`vftable'{for `IMFDXGIBuffer'}
0x1800e77d4  mov     [rcx+50h], rax
0x1800e77d8  lea     rax, ??_7FSVMServerMediaBuffer@@6BIMFDXGIBufferInternal@@@; const FSVMServerMediaBuffer::`vftable'{for `IMFDXGIBufferInternal'}
0x1800e77df  mov     [rcx+58h], rax
0x1800e77e3  lea     rax, ??_7FSVMMediaBuffer@@6BIMFGetService@@@; const FSVMMediaBuffer::`vftable'{for `IMFGetService'}
0x1800e77ea  mov     [rcx+60h], rax
0x1800e77ee  mov     rcx, rdi; lpCriticalSection
0x1800e77f1  call    cs:__imp_EnterCriticalSection
0x1800e77f7  mov     rcx, rbx; this
0x1800e77fa  call    ?InternalClose@FSVMMediaBuffer@@MEAAXXZ; FSVMMediaBuffer::InternalClose(void)
0x1800e77ff  cmp     cs:byte_18010EC53, 8
0x1800e7806  jb      short loc_1800E782A
0x1800e7808  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e780f  lea     r8, WPP_bf0389658ee6330598387757c9c6501a_Traceguids
0x1800e7816  mov     edx, 0Bh
0x1800e781b  mov     r9, rbx
0x1800e781e  mov     rcx, [rcx+1C8h]
0x1800e7825  call    WPP_SF_q
0x1800e782a  mov     rcx, rdi; lpCriticalSection
0x1800e782d  call    cs:__imp_LeaveCriticalSection
0x1800e7833  lea     rcx, [rbx+0E0h]; void *
0x1800e783a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e783f  lea     rcx, [rbx+0D8h]; void *
0x1800e7846  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e784b  lea     rcx, [rbx+0D0h]; void *
0x1800e7852  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e7857  lea     rcx, [rbx+0C8h]; void *
0x1800e785e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e7863  lea     rcx, [rbx+0C0h]; void *
0x1800e786a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e786f  lea     rcx, [rbx+0B8h]; void *
0x1800e7876  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e787b  lea     rcx, [rbx+0B0h]; void *
0x1800e7882  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e7887  lea     rcx, [rbx+0A8h]; void *
0x1800e788e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e7893  lea     rcx, [rbx+98h]; void *
0x1800e789a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800e789f  mov     rcx, rdi; lpCriticalSection
0x1800e78a2  call    cs:__imp_DeleteCriticalSection
0x1800e78a8  mov     rcx, rbx; this
0x1800e78ab  mov     rbx, [rsp+28h+arg_0]
0x1800e78b0  add     rsp, 20h
0x1800e78b4  pop     rdi
0x1800e78b5  jmp     ??1FSVMObject@@MEAA@XZ; FSVMObject::~FSVMObject(void)
```
