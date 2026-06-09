# FSStream::OnMediaStreamEvent(IMFAsyncResult *)

- ea: `0x1800addd8`
- end: `0x1800ae234`
- name: `?OnMediaStreamEvent@FSStream@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `1116`
- prototype: `void __fastcall(FSStream *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800acaa0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180017ccc`
- `0x1800809ec`
- `0x1800addd8`
- `0x1800ae4d0`
- `0x1800aeecc`
- `0x1800af094`
- `0x1800afd00`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae1a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae1a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae137`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae137`
- `MFPlat!MFCreateMediaEvent` at `0x1800ae1e6`
- `MFPlat!MFCreateMediaEvent` at `0x1800ae1e6`

## pseudocode

```c
void __fastcall FSStream::OnMediaStreamEvent(FSStream *this, struct IMFAsyncResult *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  HRESULT (__stdcall *GetState)(IMFAsyncResult *, IUnknown **); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, struct IMFAsyncResult *, IMFMediaEvent **); // rbx
  struct IMFMediaEvent *v13; // rdx
  char v14; // r14
  char v15; // al
  const char *v16; // r9
  int v17; // eax
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-8h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  int v21; // [rsp+90h] [rbp+40h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+98h] [rbp+48h] BYREF

  v21 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  ppEvent = 0;
  if ( !a2 )
  {
    v4 = -1072875845;
    if ( g_wppLevels )
    {
      v5 = 252;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v4);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  GetState = a2->lpVtbl->GetState;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v19);
  v7 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))GetState)(
         a2,
         &v19);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v8 = 253;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v7);
    goto LABEL_54;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  v10 = **v19;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v18);
  v7 = v10(v9, &GUID_d182108f_4ec6_443f_aa42_a71106ec825f, &v18);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v8 = 254;
    goto LABEL_9;
  }
  v11 = v18;
  v12 = *(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, IMFMediaEvent **))(*(_QWORD *)v18 + 40LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
  v7 = v12(v11, a2, &ppEvent);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v8 = 255;
    goto LABEL_9;
  }
  if ( !ppEvent )
  {
    v4 = -2147024809;
    if ( g_wppLevels )
    {
      v5 = 257;
      goto LABEL_4;
    }
LABEL_54:
    FSStream::SetAsyncStatus(this, v4);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
    MFCreateMediaEvent(1u, &GUID_00000000_0000_0000_0000_000000000000, v4, 0, &ppEvent);
LABEL_56:
    (*(void (__fastcall **)(FSStream *, _QWORD, IMFMediaEvent *, _QWORD))(*(_QWORD *)this + 208LL))(this, 0, ppEvent, 0);
    goto LABEL_57;
  }
  v7 = ((__int64 (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetType)(ppEvent, &v21);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v8 = 258;
    goto LABEL_9;
  }
  v7 = ((__int64 (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetStatus)(ppEvent, &v20);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v8 = 259;
    goto LABEL_9;
  }
  v14 = 0;
  switch ( v21 )
  {
    case 1:
      v14 = 1;
      FSStream::SetAsyncStatus(this, v20);
      break;
    case 202:
    case 204:
      if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
      {
        v16 = "started";
        if ( v21 != 202 )
          v16 = "seeked";
        WPP_SF_qsDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          260,
          (unsigned int)&WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
          (_DWORD)this,
          (__int64)v16,
          *((_DWORD *)this + 22),
          *((_DWORD *)this + 23),
          v20);
      }
      FSStream::OnStreamStarted(this, v13);
      break;
    case 208:
      v15 = byte_18010EC4D;
      if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
      {
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          261,
          &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
          this,
          *((_DWORD *)this + 22),
          *((_DWORD *)this + 23),
          v20);
        v15 = byte_18010EC4D;
      }
      if ( (unsigned __int8)v15 >= 8u )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          267,
          &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
          this,
          *((_DWORD *)this + 22),
          *((_DWORD *)this + 23),
          *((_DWORD *)this + 40));
      break;
    case 213:
      v7 = FSStream::OnSampleFromMediaStream(this, ppEvent);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_54;
        v8 = 262;
        goto LABEL_9;
      }
      break;
    case 216:
      v7 = FSStream::OnStreamFormatChanged(this, ppEvent);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_54;
        v8 = 263;
        goto LABEL_9;
      }
      break;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !*((_DWORD *)this + 53) && *((_QWORD *)this + 40) == v18 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v18 + 32LL))(v18, (char *)this + 16, v18);
    v4 = v17;
    if ( v17 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v17);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      goto LABEL_54;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v4 < 0 )
    goto LABEL_54;
  if ( v14 )
    goto LABEL_56;
LABEL_57:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppEvent);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v18);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v19);
}

```

## disassembly

```asm
0x1800addd8  push    rbp
0x1800addda  push    rbx
0x1800adddb  push    rsi
0x1800adddc  push    rdi
0x1800adddd  push    r14
0x1800adddf  mov     rbp, rsp
0x1800adde2  sub     rsp, 50h
0x1800adde6  mov     [rbp+arg_10], 0
0x1800added  mov     r14, rdx
0x1800addf0  mov     [rbp+arg_8], 0
0x1800addf7  mov     rsi, rcx
0x1800addfa  mov     [rbp+var_8], 0
0x1800ade02  mov     [rbp+var_10], 0
0x1800ade0a  mov     [rbp+arg_18], 0
0x1800ade12  test    rdx, rdx
0x1800ade15  jnz     short loc_1800ADE51
0x1800ade17  mov     ebx, 0C00D36BBh
0x1800ade1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ade23  jb      loc_1800AE1B0
0x1800ade29  mov     edx, 0FCh
0x1800ade2e  mov     dword ptr [rsp+50h+ppEvent], ebx
0x1800ade32  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade39  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800ade40  mov     r9, rsi
0x1800ade43  mov     rcx, [rcx+10h]
0x1800ade47  call    WPP_SF_qD
0x1800ade4c  jmp     loc_1800AE1B0
0x1800ade51  mov     rax, [rdx]
0x1800ade54  lea     rcx, [rbp+var_8]
0x1800ade58  mov     rbx, [rax+18h]
0x1800ade5c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ade61  lea     rdx, [rbp+var_8]
0x1800ade65  mov     rcx, r14
0x1800ade68  mov     rax, rbx
0x1800ade6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade70  mov     ebx, eax
0x1800ade72  test    eax, eax
0x1800ade74  jns     short loc_1800ADE8E
0x1800ade76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ade7d  jb      loc_1800AE1B0
0x1800ade83  mov     edx, 0FDh
0x1800ade88  mov     dword ptr [rsp+50h+ppEvent], eax
0x1800ade8c  jmp     short loc_1800ADE32
0x1800ade8e  mov     rdi, [rbp+var_8]
0x1800ade92  lea     rcx, [rbp+var_10]
0x1800ade96  mov     rax, [rdi]
0x1800ade99  mov     rbx, [rax]
0x1800ade9c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800adea1  lea     r8, [rbp+var_10]
0x1800adea5  mov     rcx, rdi
0x1800adea8  lea     rdx, _GUID_d182108f_4ec6_443f_aa42_a71106ec825f
0x1800adeaf  mov     rax, rbx
0x1800adeb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adeb7  mov     ebx, eax
0x1800adeb9  test    eax, eax
0x1800adebb  jns     short loc_1800ADED1
0x1800adebd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adec4  jb      loc_1800AE1B0
0x1800adeca  mov     edx, 0FEh
0x1800adecf  jmp     short loc_1800ADE88
0x1800aded1  mov     rdi, [rbp+var_10]
0x1800aded5  lea     rcx, [rbp+arg_18]
0x1800aded9  mov     rax, [rdi]
0x1800adedc  mov     rbx, [rax+28h]
0x1800adee0  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800adee5  lea     r8, [rbp+arg_18]
0x1800adee9  mov     rdx, r14
0x1800adeec  mov     rcx, rdi
0x1800adeef  mov     rax, rbx
0x1800adef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adef7  mov     ebx, eax
0x1800adef9  test    eax, eax
0x1800adefb  jns     short loc_1800ADF14
0x1800adefd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adf04  jb      loc_1800AE1B0
0x1800adf0a  mov     edx, 0FFh
0x1800adf0f  jmp     loc_1800ADE88
0x1800adf14  mov     rcx, [rbp+arg_18]
0x1800adf18  test    rcx, rcx
0x1800adf1b  jnz     short loc_1800ADF39
0x1800adf1d  mov     ebx, 80070057h
0x1800adf22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adf29  jb      loc_1800AE1B0
0x1800adf2f  mov     edx, 101h
0x1800adf34  jmp     loc_1800ADE2E
0x1800adf39  mov     rax, [rcx]
0x1800adf3c  lea     rdx, [rbp+arg_10]
0x1800adf40  mov     rax, [rax+108h]
0x1800adf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf4c  mov     ebx, eax
0x1800adf4e  test    eax, eax
0x1800adf50  jns     short loc_1800ADF69
0x1800adf52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adf59  jb      loc_1800AE1B0
0x1800adf5f  mov     edx, 102h
0x1800adf64  jmp     loc_1800ADE88
0x1800adf69  mov     rcx, [rbp+arg_18]
0x1800adf6d  lea     rdx, [rbp+arg_8]
0x1800adf71  mov     rax, [rcx]
0x1800adf74  mov     rax, [rax+118h]
0x1800adf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf80  mov     ebx, eax
0x1800adf82  test    eax, eax
0x1800adf84  jns     short loc_1800ADF9D
0x1800adf86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adf8d  jb      loc_1800AE1B0
0x1800adf93  mov     edx, 103h
0x1800adf98  jmp     loc_1800ADE88
0x1800adf9d  mov     eax, [rbp+arg_10]
0x1800adfa0  xor     r14b, r14b
0x1800adfa3  sub     eax, 1
0x1800adfa6  jz      loc_1800AE122
0x1800adfac  sub     eax, 0C9h
0x1800adfb1  jz      loc_1800AE0B8
0x1800adfb7  sub     eax, 2
0x1800adfba  jz      loc_1800AE0B8
0x1800adfc0  sub     eax, 4
0x1800adfc3  jz      short loc_1800AE02D
0x1800adfc5  sub     eax, 5
0x1800adfc8  jz      short loc_1800AE000
0x1800adfca  cmp     eax, 3
0x1800adfcd  jnz     loc_1800AE130
0x1800adfd3  mov     rdx, [rbp+arg_18]; struct IMFMediaEvent *
0x1800adfd7  mov     rcx, rsi; this
0x1800adfda  call    ?OnStreamFormatChanged@FSStream@@IEAAJPEAUIMFMediaEvent@@@Z; FSStream::OnStreamFormatChanged(IMFMediaEvent *)
0x1800adfdf  mov     ebx, eax
0x1800adfe1  test    eax, eax
0x1800adfe3  jns     loc_1800AE130
0x1800adfe9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adff0  jb      loc_1800AE1B0
0x1800adff6  mov     edx, 107h
0x1800adffb  jmp     loc_1800ADE88
0x1800ae000  mov     rdx, [rbp+arg_18]; struct IMFMediaEvent *
0x1800ae004  mov     rcx, rsi; this
0x1800ae007  call    ?OnSampleFromMediaStream@FSStream@@IEAAJPEAUIMFMediaEvent@@@Z; FSStream::OnSampleFromMediaStream(IMFMediaEvent *)
0x1800ae00c  mov     ebx, eax
0x1800ae00e  test    eax, eax
0x1800ae010  jns     loc_1800AE130
0x1800ae016  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae01d  jb      loc_1800AE1B0
0x1800ae023  mov     edx, 106h
0x1800ae028  jmp     loc_1800ADE88
0x1800ae02d  mov     al, cs:byte_18010EC4D
0x1800ae033  cmp     al, 10h
0x1800ae035  jb      short loc_1800AE074
0x1800ae037  mov     eax, [rbp+arg_8]
0x1800ae03a  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800ae041  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae048  mov     edx, 105h
0x1800ae04d  mov     [rsp+50h+var_20], eax
0x1800ae051  mov     r9, rsi
0x1800ae054  mov     eax, [rsi+5Ch]
0x1800ae057  mov     [rsp+50h+var_28], eax
0x1800ae05b  mov     eax, [rsi+58h]
0x1800ae05e  mov     rcx, [rcx+0D8h]
0x1800ae065  mov     dword ptr [rsp+50h+ppEvent], eax
0x1800ae069  call    WPP_SF_qddd
0x1800ae06e  mov     al, cs:byte_18010EC4D
0x1800ae074  cmp     al, 8
0x1800ae076  jb      loc_1800AE130
0x1800ae07c  mov     eax, [rsi+0A0h]
0x1800ae082  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800ae089  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae090  mov     edx, 10Bh
0x1800ae095  mov     [rsp+50h+var_20], eax
0x1800ae099  mov     r9, rsi
0x1800ae09c  mov     eax, [rsi+5Ch]
0x1800ae09f  mov     [rsp+50h+var_28], eax
0x1800ae0a3  mov     eax, [rsi+58h]
0x1800ae0a6  mov     rcx, [rcx+0D8h]
0x1800ae0ad  mov     dword ptr [rsp+50h+ppEvent], eax
0x1800ae0b1  call    WPP_SF_qddd
0x1800ae0b6  jmp     short loc_1800AE130
0x1800ae0b8  cmp     cs:byte_18010EC4D, 10h
0x1800ae0bf  jb      short loc_1800AE118
0x1800ae0c1  mov     ecx, [rsi+5Ch]
0x1800ae0c4  lea     rax, aSeeked; "seeked"
0x1800ae0cb  mov     r8d, [rsi+58h]
0x1800ae0cf  lea     r9, aStarted; "started"
0x1800ae0d6  cmp     [rbp+arg_10], 0CAh
0x1800ae0dd  mov     edx, 104h
0x1800ae0e2  cmovnz  r9, rax
0x1800ae0e6  mov     eax, [rbp+arg_8]
0x1800ae0e9  mov     [rsp+50h+var_18], eax
0x1800ae0ed  mov     [rsp+50h+var_20], ecx
0x1800ae0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae0f8  mov     [rsp+50h+var_28], r8d
0x1800ae0fd  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800ae104  mov     [rsp+50h+ppEvent], r9
0x1800ae109  mov     r9, rsi
0x1800ae10c  mov     rcx, [rcx+0D8h]
0x1800ae113  call    WPP_SF_qsDDD
0x1800ae118  mov     rcx, rsi; this
0x1800ae11b  call    ?OnStreamStarted@FSStream@@IEAAXPEAUIMFMediaEvent@@@Z; FSStream::OnStreamStarted(IMFMediaEvent *)
0x1800ae120  jmp     short loc_1800AE130
0x1800ae122  mov     edx, [rbp+arg_8]; int
0x1800ae125  mov     rcx, rsi; this
0x1800ae128  mov     r14b, 1
0x1800ae12b  call    ?SetAsyncStatus@FSStream@@QEAAXJ@Z; FSStream::SetAsyncStatus(long)
0x1800ae130  lea     rdi, [rsi+18h]
0x1800ae134  mov     rcx, rdi; lpCriticalSection
0x1800ae137  call    cs:__imp_EnterCriticalSection
0x1800ae13d  cmp     dword ptr [rsi+0D4h], 0
0x1800ae144  jnz     short loc_1800AE1A3
0x1800ae146  mov     rcx, [rbp+var_10]
0x1800ae14a  cmp     [rsi+140h], rcx
0x1800ae151  jnz     short loc_1800AE1A3
0x1800ae153  mov     rax, [rcx]
0x1800ae156  lea     rdx, [rsi+10h]
0x1800ae15a  mov     r8, rcx
0x1800ae15d  mov     rax, [rax+20h]
0x1800ae161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae166  mov     ebx, eax
0x1800ae168  test    eax, eax
0x1800ae16a  jns     short loc_1800AE1A3
0x1800ae16c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae173  jb      short loc_1800AE198
0x1800ae175  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae17c  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800ae183  mov     edx, 108h
0x1800ae188  mov     dword ptr [rsp+50h+ppEvent], eax
0x1800ae18c  mov     r9, rsi
0x1800ae18f  mov     rcx, [rcx+10h]
0x1800ae193  call    WPP_SF_qD
0x1800ae198  mov     rcx, rdi; lpCriticalSection
0x1800ae19b  call    cs:__imp_LeaveCriticalSection
0x1800ae1a1  jmp     short loc_1800AE1B0
0x1800ae1a3  mov     rcx, rdi; lpCriticalSection
0x1800ae1a6  call    cs:__imp_LeaveCriticalSection
0x1800ae1ac  test    ebx, ebx
0x1800ae1ae  jns     short loc_1800AE1EE
0x1800ae1b0  mov     edx, ebx; int
0x1800ae1b2  mov     rcx, rsi; this
0x1800ae1b5  call    ?SetAsyncStatus@FSStream@@QEAAXJ@Z; FSStream::SetAsyncStatus(long)
0x1800ae1ba  lea     rcx, [rbp+arg_18]
0x1800ae1be  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ae1c3  lea     rcx, [rbp+arg_18]
0x1800ae1c7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ae1cc  xor     r9d, r9d; pvValue
0x1800ae1cf  lea     rax, [rbp+arg_18]
0x1800ae1d3  mov     r8d, ebx; hrStatus
0x1800ae1d6  mov     [rsp+50h+ppEvent], rax; ppEvent
0x1800ae1db  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x1800ae1e2  lea     ecx, [r9+1]; met
0x1800ae1e6  call    cs:__imp_MFCreateMediaEvent
0x1800ae1ec  jmp     short loc_1800AE1F3
0x1800ae1ee  test    r14b, r14b
0x1800ae1f1  jz      short loc_1800AE20E
0x1800ae1f3  mov     rax, [rsi]
0x1800ae1f6  xor     r9d, r9d
0x1800ae1f9  mov     r8, [rbp+arg_18]
0x1800ae1fd  xor     edx, edx
0x1800ae1ff  mov     rcx, rsi
0x1800ae202  mov     rax, [rax+0D0h]
0x1800ae209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae20e  lea     rcx, [rbp+arg_18]; void *
0x1800ae212  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ae217  lea     rcx, [rbp+var_10]; void *
0x1800ae21b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ae220  lea     rcx, [rbp+var_8]; void *
0x1800ae224  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ae229  add     rsp, 50h
0x1800ae22d  pop     r14
0x1800ae22f  pop     rdi
0x1800ae230  pop     rsi
0x1800ae231  pop     rbx
0x1800ae232  pop     rbp
0x1800ae233  retn
```
