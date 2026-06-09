# CopyStream(IStream *,IStream * *)

- ea: `0x18004149c`
- end: `0x180041601`
- name: `?CopyStream@@YAJPEAUIStream@@PEAPEAU1@@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct IStream *pstm, struct IStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041290`

## callees

- `0x180006538`
- `0x180013244`
- `0x18003d858`
- `0x18004149c`
- `0x180041608`
- `0x180041638`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180041555`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180041555`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180041578`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180041578`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800415d7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800415e1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800415d7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800415e1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800414f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800414f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800415b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800415b0`

## string_xrefs

- `0x180041539`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004158d`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800415c6`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyStream(struct IStream *pstm, struct IStream **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  wil::details::in1diag3 *v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  HRESULT v14; // eax
  wil::details::in1diag3 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  IStream *pstma; // [rsp+48h] [rbp+28h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+30h] BYREF
  void *pv; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  pstma = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&pstma);
  v6 = SHCreateMemoryStream(v5, v4, &pstma);
  v7 = v6;
  v8 = retaddr;
  if ( v6 < 0 )
  {
    v9 = (unsigned int)v6;
    v10 = 159;
    goto LABEL_17;
  }
  pui.QuadPart = 0;
  v11 = IStream_Size(pstm, &pui);
  v7 = v11;
  v12 = retaddr;
  if ( v11 >= 0 )
  {
    pv = 0;
    v11 = CTCoAllocPolicy::Alloc(retaddr, 1u, pui.LowPart, &pv);
    v7 = v11;
    v12 = retaddr;
    if ( v11 < 0 )
    {
      v13 = 169;
      goto LABEL_7;
    }
    v14 = IStream_Read(pstm, pv, pui.LowPart);
    v7 = v14;
    v15 = retaddr;
    if ( v14 >= 0 )
    {
      v14 = IStream_Write(pstma, pv, pui.LowPart);
      v7 = v14;
      v15 = retaddr;
      if ( v14 >= 0 )
      {
        v7 = Microsoft::WRL::ComPtr<IStream>::CopyTo(&pstma, v17, a2);
        goto LABEL_14;
      }
      v16 = 175;
    }
    else
    {
      v16 = 172;
    }
    wil::details::in1diag3::_Log_Hr(
      v15,
      (void *)v16,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v14,
      savedregs);
LABEL_14:
    CoTaskMemFree(pv);
    goto LABEL_15;
  }
  v13 = 163;
LABEL_7:
  wil::details::in1diag3::_Log_Hr(
    v12,
    (void *)v13,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)(unsigned int)v11,
    savedregs);
LABEL_15:
  v8 = retaddr;
  if ( v7 >= 0 )
  {
    IStream_Reset(pstm);
    IStream_Reset(pstma);
    goto LABEL_19;
  }
  v9 = (unsigned int)v7;
  v10 = 184;
LABEL_17:
  wil::details::in1diag3::_Log_Hr(
    v8,
    (void *)v10,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)v9,
    savedregs);
LABEL_19:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&pstma);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004149c  mov     [rsp-18h+arg_0], rbx
0x1800414a1  push    rbp
0x1800414a2  push    rdi
0x1800414a3  push    r14; int
0x1800414a5  mov     rbp, rsp
0x1800414a8  sub     rsp, 20h
0x1800414ac  mov     r14, rdx
0x1800414af  mov     rdi, rcx
0x1800414b2  mov     qword ptr [rdx], 0
0x1800414b9  mov     [rbp+pstm], 0
0x1800414c1  lea     rcx, [rbp+pstm]
0x1800414c5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800414ca  lea     r8, [rbp+pstm]
0x1800414ce  call    SHCreateMemoryStream
0x1800414d3  mov     ebx, eax
0x1800414d5  mov     rcx, [rbp+18h]
0x1800414d9  test    eax, eax
0x1800414db  jns     short loc_1800414EA
0x1800414dd  mov     r9d, eax
0x1800414e0  mov     edx, 9Fh
0x1800414e5  jmp     loc_1800415C6
0x1800414ea  mov     qword ptr [rbp+pui], 0
0x1800414f2  lea     rdx, [rbp+pui]; pui
0x1800414f6  mov     rcx, rdi; pstm
0x1800414f9  call    cs:__imp_IStream_Size
0x1800414ff  mov     ebx, eax
0x180041501  mov     rcx, [rbp+18h]; void *
0x180041505  test    eax, eax
0x180041507  jns     short loc_180041510
0x180041509  mov     edx, 0A3h
0x18004150e  jmp     short loc_180041539
0x180041510  mov     [rbp+pv], 0
0x180041518  mov     r8d, dword ptr [rbp+pui]; unsigned __int64
0x18004151c  lea     r9, [rbp+pv]; void **
0x180041520  mov     edx, 1; unsigned int
0x180041525  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004152a  mov     ebx, eax
0x18004152c  mov     rcx, [rbp+18h]; this
0x180041530  test    eax, eax
0x180041532  jns     short loc_18004154A
0x180041534  mov     edx, 0A9h; void *
0x180041539  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180041540  mov     r9d, eax; char *
0x180041543  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041548  jmp     short loc_1800415B6
0x18004154a  mov     r8d, dword ptr [rbp+pui]; cb
0x18004154e  mov     rdx, [rbp+pv]; pv
0x180041552  mov     rcx, rdi; pstm
0x180041555  call    cs:__imp_IStream_Read
0x18004155b  mov     ebx, eax
0x18004155d  mov     rcx, [rbp+18h]
0x180041561  test    eax, eax
0x180041563  jns     short loc_18004156C
0x180041565  mov     edx, 0ACh
0x18004156a  jmp     short loc_18004158D
0x18004156c  mov     r8d, dword ptr [rbp+pui]; cb
0x180041570  mov     rdx, [rbp+pv]; pv
0x180041574  mov     rcx, [rbp+pstm]; pstm
0x180041578  call    cs:__imp_IStream_Write
0x18004157e  mov     ebx, eax
0x180041580  mov     rcx, [rbp+18h]; this
0x180041584  test    eax, eax
0x180041586  jns     short loc_18004159E
0x180041588  mov     edx, 0AFh; void *
0x18004158d  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180041594  mov     r9d, eax; char *
0x180041597  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004159c  jmp     short loc_1800415AC
0x18004159e  mov     r8, r14
0x1800415a1  lea     rcx, [rbp+pstm]
0x1800415a5  call    ?CopyTo@?$ComPtr@UIStream@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IStream>::CopyTo(_GUID const &,void * *)
0x1800415aa  mov     ebx, eax
0x1800415ac  mov     rcx, [rbp+pv]; pv
0x1800415b0  call    cs:__imp_CoTaskMemFree
0x1800415b6  mov     rcx, [rbp+18h]; this
0x1800415ba  test    ebx, ebx
0x1800415bc  jns     short loc_1800415D4
0x1800415be  mov     r9d, ebx; char *
0x1800415c1  mov     edx, 0B8h; void *
0x1800415c6  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800415cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800415d2  jmp     short loc_1800415E8
0x1800415d4  mov     rcx, rdi; pstm
0x1800415d7  call    cs:__imp_IStream_Reset
0x1800415dd  mov     rcx, [rbp+pstm]; pstm
0x1800415e1  call    cs:__imp_IStream_Reset
0x1800415e7  nop
0x1800415e8  lea     rcx, [rbp+pstm]
0x1800415ec  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800415f1  mov     eax, ebx
0x1800415f3  mov     rbx, [rsp+20h+arg_0]
0x1800415f8  add     rsp, 20h
0x1800415fc  pop     r14
0x1800415fe  pop     rdi
0x1800415ff  pop     rbp
0x180041600  retn
```
