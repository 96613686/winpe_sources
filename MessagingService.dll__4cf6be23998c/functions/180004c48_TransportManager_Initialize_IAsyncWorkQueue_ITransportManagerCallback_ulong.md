# TransportManager::_Initialize(IAsyncWorkQueue *,ITransportManagerCallback *,ulong)

- ea: `0x180004c48`
- end: `0x180004e93`
- name: `?_Initialize@TransportManager@@AEAAJPEAUIAsyncWorkQueue@@PEAUITransportManagerCallback@@K@Z`
- size: `587`
- prototype: `__int64 __fastcall(TransportManager *this, struct IAsyncWorkQueue *, struct ITransportManagerCallback *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003090`

## callees

- `0x18000108c`
- `0x180001730`
- `0x1800044dc`
- `0x180004c48`
- `0x180006be8`
- `0x180006df0`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180004d5e`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`
- `0x180004e5a`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::_Initialize(
        TransportManager *this,
        struct IAsyncWorkQueue *a2,
        struct ITransportManagerCallback *a3,
        int a4)
{
  struct ITransportTaskCallback *v8; // rbp
  char *v9; // rax
  __int64 v10; // r8
  TextMessageTransport *v11; // rbx
  unsigned int v12; // ebp
  __int64 v13; // rax
  int v14; // edi
  __int64 v16; // rcx
  __int64 v17; // r8
  TextMessageTransport *v18; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+38h] [rbp-60h] BYREF
  TextMessageTransport **v20; // [rsp+58h] [rbp-40h]
  __int64 v21; // [rsp+60h] [rbp-38h]

  v8 = (struct ITransportTaskCallback *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v18 = 0;
  v9 = (char *)operator new(0x30u);
  v11 = (TextMessageTransport *)v9;
  if ( !v9 )
  {
    v12 = -2147024882;
    goto LABEL_25;
  }
  *(_QWORD *)(v9 + 12) = 0;
  *((_DWORD *)v9 + 5) = 0;
  *((_DWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *(_QWORD *)v9 = &ATL::CComObject<TextMessageTransport>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  (*(void (__fastcall **)(TextMessageTransport *))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = TextMessageTransport::_Initialize(v11, this, v8);
  v13 = *(_QWORD *)v11;
  if ( (v12 & 0x80000000) != 0 )
  {
    (*(void (__fastcall **)(TextMessageTransport *))(v13 + 16))(v11);
LABEL_25:
    Log_HREvent_2(v12, 1, v10, 19);
    Log_HREvent_2(v12, 1, v17, 10);
    Log_HREvent_0(v12, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    return v12;
  }
  (*(void (__fastcall **)(TextMessageTransport *))(v13 + 8))(v11);
  v18 = v11;
  (*(void (__fastcall **)(TextMessageTransport *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( this == (TransportManager *)-48LL )
  {
    v14 = -2147467261;
  }
  else
  {
    *((_QWORD *)this + 6) = v11;
    if ( v11 )
      (*(void (__fastcall **)(TextMessageTransport *))(*(_QWORD *)v11 + 8LL))(v11);
    v14 = 0;
  }
  if ( v14 >= 0 )
  {
    if ( *((struct IAsyncWorkQueue **)this + 5) != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)a2 + 8LL))(a2);
      v16 = *((_QWORD *)this + 5);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *((_QWORD *)this + 5) = a2;
    }
    *((_QWORD *)this + 12) = a3;
    *((_DWORD *)this + 22) = a4;
    if ( (unsigned int)dword_180013018 > 4 )
    {
      LODWORD(v18) = *((_DWORD *)this + 22);
      v20 = &v18;
      v21 = 4;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_180010296, 0, 0, 3u, &v19);
    }
    if ( v11 )
      (*(void (__fastcall **)(TextMessageTransport *))(*(_QWORD *)v11 + 16LL))(v11);
    return 0;
  }
  else
  {
    Log_HREvent_0((unsigned int)v14, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    if ( v11 )
      (*(void (__fastcall **)(TextMessageTransport *))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x180004c48  mov     [rsp+arg_10], rbx
0x180004c4d  mov     [rsp+arg_18], rbp
0x180004c52  push    rsi
0x180004c53  push    rdi
0x180004c54  push    r12
0x180004c56  push    r14
0x180004c58  push    r15
0x180004c5a  sub     rsp, 70h
0x180004c5e  mov     rax, cs:__security_cookie
0x180004c65  xor     rax, rsp
0x180004c68  mov     [rsp+98h+var_30], rax
0x180004c6d  mov     r15d, r9d
0x180004c70  mov     r12, r8
0x180004c73  mov     r14, rdx
0x180004c76  mov     rsi, rcx
0x180004c79  mov     rax, rcx
0x180004c7c  lea     r10, [rcx+8]
0x180004c80  neg     rax
0x180004c83  sbb     rbp, rbp
0x180004c86  and     rbp, r10
0x180004c89  xor     edi, edi
0x180004c8b  mov     [rsp+98h+var_68], rdi
0x180004c90  lea     ecx, [rdi+30h]; Size
0x180004c93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c98  mov     rbx, rax
0x180004c9b  test    rax, rax
0x180004c9e  jz      loc_180004E32
0x180004ca4  mov     [rax+0Ch], rdi
0x180004ca8  mov     [rax+14h], edi
0x180004cab  mov     [rax+8], edi
0x180004cae  mov     [rax+18h], rdi
0x180004cb2  mov     [rax+20h], rdi
0x180004cb6  mov     [rax+28h], rdi
0x180004cba  lea     rax, ??_7?$CComObject@VTextMessageTransport@@@ATL@@6B@; const ATL::CComObject<TextMessageTransport>::`vftable'
0x180004cc1  mov     [rbx], rax
0x180004cc4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004ccb  mov     rax, [rcx]
0x180004cce  mov     rax, [rax+8]
0x180004cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd7  mov     rax, [rbx]
0x180004cda  mov     rcx, rbx
0x180004cdd  mov     rax, [rax+8]
0x180004ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce6  mov     r8, rbp; struct ITransportTaskCallback *
0x180004ce9  mov     rdx, rsi; struct ITransportTaskScheduler *
0x180004cec  mov     rcx, rbx; this
0x180004cef  call    ?_Initialize@TextMessageTransport@@AEAAJPEAUITransportTaskScheduler@@PEAUITransportTaskCallback@@@Z; TextMessageTransport::_Initialize(ITransportTaskScheduler *,ITransportTaskCallback *)
0x180004cf4  mov     ebp, eax
0x180004cf6  mov     rcx, rbx
0x180004cf9  test    eax, eax
0x180004cfb  mov     rax, [rbx]
0x180004cfe  jns     short loc_180004D0E
0x180004d00  mov     rax, [rax+10h]
0x180004d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d09  jmp     loc_180004E37
0x180004d0e  mov     rax, [rax+8]
0x180004d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d17  mov     [rsp+98h+var_68], rbx
0x180004d1c  mov     rax, [rbx]
0x180004d1f  mov     rcx, rbx
0x180004d22  mov     rax, [rax+10h]
0x180004d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2b  lea     rax, [rsi+30h]
0x180004d2f  test    rax, rax
0x180004d32  jnz     short loc_180004D3B
0x180004d34  mov     edi, 80004003h
0x180004d39  jmp     short loc_180004D54
0x180004d3b  mov     [rax], rbx
0x180004d3e  test    rbx, rbx
0x180004d41  jz      short loc_180004D52
0x180004d43  mov     rax, [rbx]
0x180004d46  mov     rcx, rbx
0x180004d49  mov     rax, [rax+8]
0x180004d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d52  xor     edi, edi
0x180004d54  test    edi, edi
0x180004d56  jns     short loc_180004D8D
0x180004d58  mov     r9d, 1Fh
0x180004d5e  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004d65  lea     edx, [r9-1Eh]
0x180004d69  mov     ecx, edi
0x180004d6b  call    Log_HREvent_0
0x180004d70  nop
0x180004d71  test    rbx, rbx
0x180004d74  jz      short loc_180004D86
0x180004d76  mov     rcx, [rbx]
0x180004d79  mov     rax, [rcx+10h]
0x180004d7d  mov     rcx, rbx
0x180004d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d85  nop
0x180004d86  mov     eax, edi
0x180004d88  jmp     loc_180004E6D
0x180004d8d  cmp     [rsi+28h], r14
0x180004d91  jz      short loc_180004DC0
0x180004d93  test    r14, r14
0x180004d96  jz      short loc_180004DA7
0x180004d98  mov     rax, [r14]
0x180004d9b  mov     rcx, r14
0x180004d9e  mov     rax, [rax+8]
0x180004da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da7  mov     rcx, [rsi+28h]
0x180004dab  test    rcx, rcx
0x180004dae  jz      short loc_180004DBC
0x180004db0  mov     rax, [rcx]
0x180004db3  mov     rax, [rax+10h]
0x180004db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dbc  mov     [rsi+28h], r14
0x180004dc0  mov     [rsi+60h], r12
0x180004dc4  mov     [rsi+58h], r15d
0x180004dc8  mov     eax, cs:dword_180013018
0x180004dce  cmp     eax, 4
0x180004dd1  jbe     short loc_180004E19
0x180004dd3  mov     eax, [rsi+58h]
0x180004dd6  mov     dword ptr [rsp+98h+var_68], eax
0x180004dda  lea     rax, [rsp+98h+var_68]
0x180004ddf  mov     [rsp+98h+var_40], rax
0x180004de4  mov     [rsp+98h+var_38], 4
0x180004ded  lea     rax, [rsp+98h+var_60]
0x180004df2  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180004df7  mov     [rsp+98h+var_78], 3; ULONG
0x180004dff  xor     r9d, r9d; int
0x180004e02  xor     r8d, r8d; int
0x180004e05  lea     rdx, word_180010296; int
0x180004e0c  lea     rcx, dword_180013018; int
0x180004e13  call    _tlgWriteTransfer_EventWriteTransfer
0x180004e18  nop
0x180004e19  test    rbx, rbx
0x180004e1c  jz      short loc_180004E2E
0x180004e1e  mov     rax, [rbx]
0x180004e21  mov     rcx, rbx
0x180004e24  mov     rax, [rax+10h]
0x180004e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2d  nop
0x180004e2e  xor     eax, eax
0x180004e30  jmp     short loc_180004E6D
0x180004e32  mov     ebp, 8007000Eh
0x180004e37  mov     esi, 1
0x180004e3c  lea     r9d, [rsi+12h]
0x180004e40  mov     edx, esi
0x180004e42  mov     ecx, ebp
0x180004e44  call    Log_HREvent_2
0x180004e49  lea     r9d, [rsi+9]
0x180004e4d  mov     edx, esi
0x180004e4f  mov     ecx, ebp
0x180004e51  call    Log_HREvent_2
0x180004e56  lea     r9d, [rsi+1Ch]
0x180004e5a  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004e61  mov     edx, esi
0x180004e63  mov     ecx, ebp
0x180004e65  call    Log_HREvent_0
0x180004e6a  nop
0x180004e6b  mov     eax, ebp
0x180004e6d  mov     rcx, [rsp+98h+var_30]
0x180004e72  xor     rcx, rsp; StackCookie
0x180004e75  call    __security_check_cookie
0x180004e7a  lea     r11, [rsp+98h+var_28]
0x180004e7f  mov     rbx, [r11+40h]
0x180004e83  mov     rbp, [r11+48h]
0x180004e87  mov     rsp, r11
0x180004e8a  pop     r15
0x180004e8c  pop     r14
0x180004e8e  pop     r12
0x180004e90  pop     rdi
0x180004e91  pop     rsi
0x180004e92  retn
```
