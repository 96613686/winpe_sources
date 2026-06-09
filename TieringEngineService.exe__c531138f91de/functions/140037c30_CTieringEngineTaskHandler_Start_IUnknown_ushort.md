# CTieringEngineTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x140037c30`
- end: `0x140037ee0`
- name: `?Start@CTieringEngineTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `688`
- prototype: `__int64 __fastcall(LPSTREAM *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009f1c`
- `0x140037c30`
- `0x14003805c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140037dae`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140037dae`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140037d7e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140037d7e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140037e72`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140037e72`

## string_xrefs

- `0x140037c5a`: `CTieringEngineTaskHandler::Start`
- `0x140037e00`: `Hr = AtlMarshalPtrInProc( TaskHandlerStatus, IID_ITaskHandlerStatus, &m_TaskCompletedWorkContext.TaskHandlerStatusMarshal )`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::Start(LPSTREAM *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  int v6; // r8d
  _QWORD *v7; // rcx
  IUnknown *v8; // rbx
  HRESULT StreamOnHGlobal; // edi
  LPSTREAM *v10; // rsi
  _BYTE v12[8]; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+38h] [rbp-10h]
  IUnknown *v14; // [rsp+88h] [rbp+40h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::Start";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, this);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 0;
  v14 = 0;
  if ( a2 )
  {
    ((void (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
      a2,
      &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
      &v14);
    v8 = v14;
    v7 = WPP_GLOBAL_Control;
  }
  if ( !v8 )
  {
    StreamOnHGlobal = -2147467262;
    v13 = -2147467262;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    {
      WPP_SF_d(v7[2], 18, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, 2147500034LL);
      v8 = v14;
    }
    if ( v8 )
      ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
    goto LABEL_44;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
  {
    WPP_SF_S(v7[2], 19, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, a3);
    v8 = v14;
    v7 = WPP_GLOBAL_Control;
  }
  v10 = this + 15;
  if ( this == (LPSTREAM *)-120LL )
  {
    StreamOnHGlobal = -2147467261;
    v13 = -2147467261;
LABEL_26:
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      {
        WPP_SF_sd(
          v7[2],
          20,
          v6,
          (unsigned int)"Hr = AtlMarshalPtrInProc( TaskHandlerStatus, IID_ITaskHandlerStatus, &m_TaskCompletedWorkContext"
                        ".TaskHandlerStatusMarshal )",
          StreamOnHGlobal);
        v8 = v14;
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      {
        WPP_SF_d(v7[2], 21, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, (unsigned int)StreamOnHGlobal);
        v8 = v14;
      }
    }
    if ( v8 )
      ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
    goto LABEL_44;
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, this + 15);
  if ( StreamOnHGlobal >= 0 )
  {
    StreamOnHGlobal = CoMarshalInterface(*v10, &IID_ITaskHandlerStatus, v8, 3u, 0, 1u);
    if ( StreamOnHGlobal < 0 )
    {
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)*v10 + 16LL))(*v10);
      *v10 = 0;
    }
  }
  v13 = StreamOnHGlobal;
  if ( StreamOnHGlobal < 0 )
  {
    v8 = v14;
    v7 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  (*((void (__fastcall **)(LPSTREAM *))*this + 1))(this);
  SubmitThreadpoolWork(this[12]);
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, this);
  }
  if ( v14 )
    ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
  StreamOnHGlobal = 0;
LABEL_44:
  CHResultImp::~CHResultImp((CHResultImp *)v12);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x140037c30  push    rbp
0x140037c32  push    rbx
0x140037c33  push    rsi
0x140037c34  push    rdi
0x140037c35  push    r13
0x140037c37  push    r14
0x140037c39  mov     rbp, rsp
0x140037c3c  sub     rsp, 48h
0x140037c40  mov     rsi, r8
0x140037c43  mov     rdi, rdx
0x140037c46  mov     r14, rcx
0x140037c49  mov     ecx, 8
0x140037c4e  mov     rax, gs:58h
0x140037c57  mov     r9, [rax]
0x140037c5a  lea     rax, aCtieringengine; "CTieringEngineTaskHandler::Start"
0x140037c61  mov     [rcx+r9], rax
0x140037c65  lea     rcx, [rbp+var_18]; this
0x140037c69  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140037c6e  lea     r13, WPP_GLOBAL_Control
0x140037c75  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c7c  cmp     rcx, r13
0x140037c7f  jz      short loc_140037CAC
0x140037c81  test    byte ptr [rcx+1Ch], 1
0x140037c85  jz      short loc_140037CAC
0x140037c87  cmp     byte ptr [rcx+19h], 4
0x140037c8b  jb      short loc_140037CAC
0x140037c8d  mov     edx, 11h
0x140037c92  mov     r9, r14
0x140037c95  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037c9c  mov     rcx, [rcx+10h]
0x140037ca0  call    WPP_SF_q
0x140037ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x140037cac  xor     ebx, ebx
0x140037cae  mov     [rbp+arg_8], rbx
0x140037cb2  test    rdi, rdi
0x140037cb5  jz      short loc_140037CDB
0x140037cb7  mov     rax, [rdi]
0x140037cba  lea     r8, [rbp+arg_8]
0x140037cbe  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x140037cc5  mov     rcx, rdi
0x140037cc8  mov     rax, [rax]
0x140037ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037cd0  mov     rbx, [rbp+arg_8]
0x140037cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140037cdb  test    rbx, rbx
0x140037cde  jnz     short loc_140037D2D
0x140037ce0  mov     edi, 80004002h
0x140037ce5  mov     [rbp+var_10], edi
0x140037ce8  cmp     rcx, r13
0x140037ceb  jz      short loc_140037D13
0x140037ced  test    byte ptr [rcx+1Ch], 1
0x140037cf1  jz      short loc_140037D13
0x140037cf3  cmp     byte ptr [rcx+19h], 2
0x140037cf7  jb      short loc_140037D13
0x140037cf9  lea     edx, [rbx+12h]
0x140037cfc  mov     r9d, edi
0x140037cff  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037d06  mov     rcx, [rcx+10h]
0x140037d0a  call    WPP_SF_d
0x140037d0f  mov     rbx, [rbp+arg_8]
0x140037d13  test    rbx, rbx
0x140037d16  jz      short loc_140037D28
0x140037d18  mov     rax, [rbx]
0x140037d1b  mov     rcx, rbx
0x140037d1e  mov     rax, [rax+10h]
0x140037d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d27  nop
0x140037d28  jmp     loc_140037EC8
0x140037d2d  cmp     rcx, r13
0x140037d30  jz      short loc_140037D61
0x140037d32  test    byte ptr [rcx+1Ch], 1
0x140037d36  jz      short loc_140037D61
0x140037d38  cmp     byte ptr [rcx+19h], 4
0x140037d3c  jb      short loc_140037D61
0x140037d3e  mov     edx, 13h
0x140037d43  mov     r9, rsi
0x140037d46  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037d4d  mov     rcx, [rcx+10h]
0x140037d51  call    WPP_SF_S
0x140037d56  mov     rbx, [rbp+arg_8]
0x140037d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d61  lea     rsi, [r14+78h]
0x140037d65  test    rsi, rsi
0x140037d68  jnz     short loc_140037D74
0x140037d6a  mov     edi, 80004003h
0x140037d6f  mov     [rbp+var_10], edi
0x140037d72  jmp     short loc_140037DE6
0x140037d74  mov     r8, rsi; ppstm
0x140037d77  mov     edx, 1; fDeleteOnRelease
0x140037d7c  xor     ecx, ecx; hGlobal
0x140037d7e  call    cs:__imp_CreateStreamOnHGlobal
0x140037d84  mov     edi, eax
0x140037d86  test    eax, eax
0x140037d88  js      short loc_140037DD0
0x140037d8a  mov     [rsp+48h+mshlflags], 1; mshlflags
0x140037d92  mov     [rsp+48h+pvDestContext], 0; pvDestContext
0x140037d9b  mov     r9d, 3; dwDestContext
0x140037da1  mov     r8, rbx; pUnk
0x140037da4  lea     rdx, IID_ITaskHandlerStatus; riid
0x140037dab  mov     rcx, [rsi]; pStm
0x140037dae  call    cs:__imp_CoMarshalInterface
0x140037db4  mov     edi, eax
0x140037db6  test    eax, eax
0x140037db8  jns     short loc_140037DD0
0x140037dba  mov     rcx, [rsi]
0x140037dbd  mov     rax, [rcx]
0x140037dc0  mov     rax, [rax+10h]
0x140037dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037dc9  mov     qword ptr [rsi], 0
0x140037dd0  mov     [rbp+var_10], edi
0x140037dd3  test    edi, edi
0x140037dd5  jns     loc_140037E5F
0x140037ddb  mov     rbx, [rbp+arg_8]
0x140037ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140037de6  cmp     rcx, r13
0x140037de9  jz      short loc_140037E48
0x140037deb  test    byte ptr [rcx+1Ch], 1
0x140037def  jz      short loc_140037E1B
0x140037df1  cmp     byte ptr [rcx+19h], 2
0x140037df5  jb      short loc_140037E1B
0x140037df7  mov     edx, 14h
0x140037dfc  mov     dword ptr [rsp+48h+pvDestContext], edi
0x140037e00  lea     r9, aHrAtlmarshalpt; "Hr = AtlMarshalPtrInProc( TaskHandlerSt"...
0x140037e07  mov     rcx, [rcx+10h]
0x140037e0b  call    WPP_SF_sd
0x140037e10  mov     rbx, [rbp+arg_8]
0x140037e14  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e1b  cmp     rcx, r13
0x140037e1e  jz      short loc_140037E48
0x140037e20  test    byte ptr [rcx+1Ch], 1
0x140037e24  jz      short loc_140037E48
0x140037e26  cmp     byte ptr [rcx+19h], 2
0x140037e2a  jb      short loc_140037E48
0x140037e2c  mov     edx, 15h
0x140037e31  mov     r9d, edi
0x140037e34  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037e3b  mov     rcx, [rcx+10h]
0x140037e3f  call    WPP_SF_d
0x140037e44  mov     rbx, [rbp+arg_8]
0x140037e48  test    rbx, rbx
0x140037e4b  jz      short loc_140037E5D
0x140037e4d  mov     rax, [rbx]
0x140037e50  mov     rcx, rbx
0x140037e53  mov     rax, [rax+10h]
0x140037e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e5c  nop
0x140037e5d  jmp     short loc_140037EC8
0x140037e5f  mov     rax, [r14]
0x140037e62  mov     rcx, r14
0x140037e65  mov     rax, [rax+8]
0x140037e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e6e  mov     rcx, [r14+60h]; pwk
0x140037e72  call    cs:__imp_SubmitThreadpoolWork
0x140037e78  mov     [rbp+var_10], 0
0x140037e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e86  cmp     rcx, r13
0x140037e89  jz      short loc_140037EB0
0x140037e8b  test    byte ptr [rcx+1Ch], 1
0x140037e8f  jz      short loc_140037EB0
0x140037e91  cmp     byte ptr [rcx+19h], 4
0x140037e95  jb      short loc_140037EB0
0x140037e97  mov     edx, 16h
0x140037e9c  mov     r9, r14
0x140037e9f  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037ea6  mov     rcx, [rcx+10h]
0x140037eaa  call    WPP_SF_q
0x140037eaf  nop
0x140037eb0  mov     rcx, [rbp+arg_8]
0x140037eb4  test    rcx, rcx
0x140037eb7  jz      short loc_140037EC6
0x140037eb9  mov     rax, [rcx]
0x140037ebc  mov     rax, [rax+10h]
0x140037ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ec5  nop
0x140037ec6  xor     edi, edi
0x140037ec8  lea     rcx, [rbp+var_18]; this
0x140037ecc  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140037ed1  mov     eax, edi
0x140037ed3  add     rsp, 48h
0x140037ed7  pop     r14
0x140037ed9  pop     r13
0x140037edb  pop     rdi
0x140037edc  pop     rsi
0x140037edd  pop     rbx
0x140037ede  pop     rbp
0x140037edf  retn
```
