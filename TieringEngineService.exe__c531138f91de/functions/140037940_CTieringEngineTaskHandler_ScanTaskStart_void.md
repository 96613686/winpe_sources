# CTieringEngineTaskHandler::ScanTaskStart(void)

- ea: `0x140037940`
- end: `0x140037bbb`
- name: `?ScanTaskStart@CTieringEngineTaskHandler@@AEAAXXZ`
- size: `635`
- prototype: `void __fastcall(CTieringEngineTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140037bd0`

## callees

- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140037940`
- `0x14003805c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x140037a6b`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x140037a6b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400379b0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400379b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140037ba0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140037ba0`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x140037b52`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x140037b52`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140037b73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140037b73`

## string_xrefs

- `0x140037962`: `CTieringEngineTaskHandler::ScanTaskStart`
- `0x1400379e3`: `Hr = CoInit.Initialize( COINIT_MULTITHREADED )`
- `0x140037a9f`: `Hr = AtlUnmarshalPtr( m_TaskCompletedWorkContext.TaskHandlerStatusMarshal, IID_ITaskHandlerStatus, &TaskHandlerStatusUnknown )`

## pseudocode

```c
void __fastcall CTieringEngineTaskHandler::ScanTaskStart(CTieringEngineTaskHandler *this)
{
  HRESULT v2; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  IStream *v6; // rsi
  void (__fastcall ***v7)(LPVOID, GUID *, __int64 *); // r9
  HRESULT v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  IStream *v11; // rbx
  _BYTE v12[8]; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v13; // [rsp+40h] [rbp-10h]
  __int64 v14; // [rsp+90h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::ScanTaskStart";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids);
  }
  v2 = CoInitializeEx(0, 0);
  v4 = v2;
  v13 = v2;
  if ( v2 >= 0 )
  {
    *((_DWORD *)this + 28) = 0;
    v6 = (IStream *)*((_QWORD *)this + 15);
    v7 = 0;
    ppv = 0;
    v8 = -2147024809;
    if ( v6 )
    {
      (*(void (__fastcall **)(IStream *, _QWORD, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, 0, 0);
      v8 = CoUnmarshalInterface(v6, &IID_ITaskHandlerStatus, &ppv);
      v7 = (void (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    }
    v13 = v8;
    if ( v8 >= 0 )
    {
      v10 = 0;
      v14 = 0;
      if ( v7 )
      {
        (**v7)(v7, &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, &v14);
        v10 = v14;
      }
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, *((unsigned int *)this + 28));
      v11 = (IStream *)*((_QWORD *)this + 15);
      if ( v11 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(
          *((_QWORD *)this + 15),
          0,
          0,
          0);
        CoReleaseMarshalData(v11);
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      *((_QWORD *)this + 15) = 0;
      SetEvent(*((HANDLE *)this + 10));
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            v3,
            (unsigned int)"Hr = AtlUnmarshalPtr( m_TaskCompletedWorkContext.TaskHandlerStatusMarshal, IID_ITaskHandlerSta"
                          "tus, &TaskHandlerStatusUnknown )",
            v8);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 2u )
          WPP_SF_d(v9[2], 34, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, (unsigned int)v8);
      }
    }
    (*(void (__fastcall **)(CTieringEngineTaskHandler *))(*(_QWORD *)this + 16LL))(this);
    CoUninitialize();
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          v3,
          (unsigned int)"Hr = CoInit.Initialize( COINIT_MULTITHREADED )",
          v2);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
        WPP_SF_d(v5[2], 32, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v4);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v12);
}

```

## disassembly

```asm
0x140037940  push    rbp
0x140037942  push    rbx
0x140037943  push    rsi
0x140037944  push    rdi
0x140037945  push    r15
0x140037947  mov     rbp, rsp
0x14003794a  sub     rsp, 50h
0x14003794e  mov     rdi, rcx
0x140037951  mov     ecx, 8
0x140037956  mov     rax, gs:58h
0x14003795f  mov     rdx, [rax]
0x140037962  lea     rax, aCtieringengine_5; "CTieringEngineTaskHandler::ScanTaskStar"...
0x140037969  mov     [rcx+rdx], rax
0x14003796d  lea     rcx, [rbp+var_18]; this
0x140037971  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140037976  nop
0x140037977  lea     r15, WPP_GLOBAL_Control
0x14003797e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037985  cmp     rcx, r15
0x140037988  jz      short loc_1400379AC
0x14003798a  test    byte ptr [rcx+1Ch], 1
0x14003798e  jz      short loc_1400379AC
0x140037990  cmp     byte ptr [rcx+19h], 4
0x140037994  jb      short loc_1400379AC
0x140037996  mov     edx, 1Eh
0x14003799b  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x1400379a2  mov     rcx, [rcx+10h]
0x1400379a6  call    WPP_SF_
0x1400379ab  nop
0x1400379ac  xor     edx, edx; dwCoInit
0x1400379ae  xor     ecx, ecx; pvReserved
0x1400379b0  call    cs:__imp_CoInitializeEx
0x1400379b6  mov     ebx, eax
0x1400379b8  mov     [rbp+arg_8], eax
0x1400379bb  mov     [rbp+var_10], eax
0x1400379be  test    eax, eax
0x1400379c0  jns     short loc_140037A29
0x1400379c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400379c9  cmp     rcx, r15
0x1400379cc  jz      short loc_140037A24
0x1400379ce  test    byte ptr [rcx+1Ch], 1
0x1400379d2  jz      short loc_1400379FA
0x1400379d4  cmp     byte ptr [rcx+19h], 2
0x1400379d8  jb      short loc_1400379FA
0x1400379da  mov     edx, 1Fh
0x1400379df  mov     [rsp+50h+var_30], eax
0x1400379e3  lea     r9, aHrCoinitInitia; "Hr = CoInit.Initialize( COINIT_MULTITHR"...
0x1400379ea  mov     rcx, [rcx+10h]
0x1400379ee  call    WPP_SF_sd
0x1400379f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400379fa  cmp     rcx, r15
0x1400379fd  jz      short loc_140037A24
0x1400379ff  test    byte ptr [rcx+1Ch], 1
0x140037a03  jz      short loc_140037A24
0x140037a05  cmp     byte ptr [rcx+19h], 2
0x140037a09  jb      short loc_140037A24
0x140037a0b  mov     edx, 20h ; ' '
0x140037a10  mov     r9d, ebx
0x140037a13  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037a1a  mov     rcx, [rcx+10h]
0x140037a1e  call    WPP_SF_d
0x140037a23  nop
0x140037a24  jmp     loc_140037BA7
0x140037a29  mov     dword ptr [rdi+70h], 0
0x140037a30  mov     [rbp+var_20], rdi
0x140037a34  mov     rsi, [rdi+78h]
0x140037a38  xor     r9d, r9d
0x140037a3b  mov     [rbp+ppv], r9
0x140037a3f  mov     ebx, 80070057h
0x140037a44  test    rsi, rsi
0x140037a47  jz      short loc_140037A77
0x140037a49  xor     edx, edx
0x140037a4b  mov     rax, [rsi]
0x140037a4e  xor     r8d, r8d
0x140037a51  mov     rcx, rsi
0x140037a54  mov     rax, [rax+28h]
0x140037a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037a5d  lea     r8, [rbp+ppv]; ppv
0x140037a61  lea     rdx, IID_ITaskHandlerStatus; riid
0x140037a68  mov     rcx, rsi; pStm
0x140037a6b  call    cs:__imp_CoUnmarshalInterface
0x140037a71  mov     ebx, eax
0x140037a73  mov     r9, [rbp+ppv]
0x140037a77  mov     [rbp+var_10], ebx
0x140037a7a  test    ebx, ebx
0x140037a7c  jns     short loc_140037AF5
0x140037a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a85  cmp     rcx, r15
0x140037a88  jz      short loc_140037AE0
0x140037a8a  test    byte ptr [rcx+1Ch], 1
0x140037a8e  jz      short loc_140037AB6
0x140037a90  cmp     byte ptr [rcx+19h], 2
0x140037a94  jb      short loc_140037AB6
0x140037a96  mov     edx, 21h ; '!'
0x140037a9b  mov     [rsp+50h+var_30], ebx
0x140037a9f  lea     r9, aHrAtlunmarshal; "Hr = AtlUnmarshalPtr( m_TaskCompletedWo"...
0x140037aa6  mov     rcx, [rcx+10h]
0x140037aaa  call    WPP_SF_sd
0x140037aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ab6  cmp     rcx, r15
0x140037ab9  jz      short loc_140037AE0
0x140037abb  test    byte ptr [rcx+1Ch], 1
0x140037abf  jz      short loc_140037AE0
0x140037ac1  cmp     byte ptr [rcx+19h], 2
0x140037ac5  jb      short loc_140037AE0
0x140037ac7  mov     edx, 22h ; '"'
0x140037acc  mov     r9d, ebx
0x140037acf  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037ad6  mov     rcx, [rcx+10h]
0x140037ada  call    WPP_SF_d
0x140037adf  nop
0x140037ae0  mov     rax, [rdi]
0x140037ae3  mov     rcx, rdi
0x140037ae6  mov     rax, [rax+10h]
0x140037aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037aef  nop
0x140037af0  jmp     loc_140037BA0
0x140037af5  xor     ecx, ecx
0x140037af7  mov     [rbp+arg_10], rcx
0x140037afb  test    r9, r9
0x140037afe  jz      short loc_140037B1D
0x140037b00  mov     rax, [r9]
0x140037b03  lea     r8, [rbp+arg_10]
0x140037b07  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x140037b0e  mov     rcx, r9
0x140037b11  mov     rax, [rax]
0x140037b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b19  mov     rcx, [rbp+arg_10]
0x140037b1d  mov     rax, [rcx]
0x140037b20  mov     edx, [rdi+70h]
0x140037b23  mov     rax, [rax+20h]
0x140037b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b2c  mov     [rbp+var_10], eax
0x140037b2f  mov     rbx, [rdi+78h]
0x140037b33  test    rbx, rbx
0x140037b36  jz      short loc_140037B67
0x140037b38  xor     edx, edx
0x140037b3a  mov     rax, [rbx]
0x140037b3d  xor     r9d, r9d
0x140037b40  xor     r8d, r8d
0x140037b43  mov     rcx, rbx
0x140037b46  mov     rax, [rax+28h]
0x140037b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b4f  mov     rcx, rbx; pStm
0x140037b52  call    cs:__imp_CoReleaseMarshalData
0x140037b58  mov     rax, [rbx]
0x140037b5b  mov     rcx, rbx
0x140037b5e  mov     rax, [rax+10h]
0x140037b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b67  mov     qword ptr [rdi+78h], 0
0x140037b6f  mov     rcx, [rdi+50h]; hEvent
0x140037b73  call    cs:__imp_SetEvent
0x140037b79  nop
0x140037b7a  mov     rcx, [rbp+arg_10]
0x140037b7e  test    rcx, rcx
0x140037b81  jz      short loc_140037B90
0x140037b83  mov     rax, [rcx]
0x140037b86  mov     rax, [rax+10h]
0x140037b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b8f  nop
0x140037b90  mov     rax, [rdi]
0x140037b93  mov     rcx, rdi
0x140037b96  mov     rax, [rax+10h]
0x140037b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b9f  nop
0x140037ba0  call    cs:__imp_CoUninitialize
0x140037ba6  nop
0x140037ba7  lea     rcx, [rbp+var_18]; this
0x140037bab  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140037bb0  add     rsp, 50h
0x140037bb4  pop     r15
0x140037bb6  pop     rdi
0x140037bb7  pop     rsi
0x140037bb8  pop     rbx
0x140037bb9  pop     rbp
0x140037bba  retn
```
