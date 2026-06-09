# FSKsEvent::HandleOnEvent(IUnknown *,int *)

- ea: `0x1800b6150`
- end: `0x1800b64d7`
- name: `?HandleOnEvent@FSKsEvent@@UEAAJPEAUIUnknown@@PEAH@Z`
- size: `903`
- prototype: `int(FSKsEvent *__hidden this, struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008338`
- `0x180008cf0`
- `0x18000920c`
- `0x180009494`
- `0x180009608`
- `0x180018998`
- `0x18004d714`
- `0x18004d748`
- `0x18004f37c`
- `0x1800b6150`
- `0x1800b7528`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b6384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b6384`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b6180`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b6180`
- `MFPlat!MFCreateAsyncResult` at `0x1800b6437`
- `MFPlat!MFCreateAsyncResult` at `0x1800b6437`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800b645f`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800b645f`

## pseudocode

```c
__int64 __fastcall FSKsEvent::HandleOnEvent(FSKsEvent *this, struct IUnknown *a2, int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  char v5; // bl
  void *v8; // rdx
  __int64 v9; // r8
  FSString *v10; // rax
  const char *String; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  _QWORD *v14; // rsi
  wil::details *v15; // rcx
  __int64 v16; // rdx
  __int64 (__fastcall *v18)(FSKsEvent *, GUID *, IUnknown **); // rbx
  HRESULT v19; // eax
  __int64 v20; // rdx
  IMFAsyncResult *v21; // rcx
  __int64 v22; // [rsp+40h] [rbp-20h]
  _BYTE v23[24]; // [rsp+48h] [rbp-18h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+A0h] [rbp+40h] BYREF
  IUnknown *punkObject; // [rsp+B8h] [rbp+58h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  v5 = 0;
  LODWORD(ppAsyncResult) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v22 = *((_QWORD *)this + 10);
  ppAsyncResult = 0;
  punkObject = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_qidid(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      20,
      v9,
      this,
      *((_QWORD *)this + 19),
      *((unsigned __int8 *)this + 128),
      *((_QWORD *)this + 9),
      *((_DWORD *)this + 24));
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v10 = ClientContextInfoTrace::ClientContextInfoTrace(
              (ClientContextInfoTrace *)v23,
              *((struct IFSClientContextInfo **)this + 21));
      String = FSString::GetString(v10);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        21,
        (unsigned int)&WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
        (_DWORD)this,
        (__int64)String);
      v5 = 1;
    }
  }
  if ( (v5 & 1) != 0 )
    FSString::~FSString((FSString *)v23);
  if ( !*((_QWORD *)this + 10) )
  {
    v12 = -1072875845;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
        this,
        -1072875845);
    goto LABEL_46;
  }
  if ( !a2 )
  {
    v12 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_46:
      if ( !byte_18010EC4D )
        goto LABEL_27;
      v16 = 30;
      goto LABEL_26;
    }
    v13 = 23;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v12);
    goto LABEL_46;
  }
  if ( !a3 )
  {
    v12 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_46;
    v13 = 24;
    goto LABEL_13;
  }
  v14 = (_QWORD *)((char *)this + 152);
  *a3 = 0;
  v12 = 0;
  if ( *((_QWORD *)this + 19) && *((_BYTE *)this + 128) )
  {
    *v14 = 0;
    v15 = (wil::details *)*((_QWORD *)this + 17);
    if ( v15 && *((_QWORD *)this + 18) )
    {
      wil::details::SetEvent(v15, v8);
      if ( (*(_DWORD *)(v22 + 20) & 2) != 0 )
      {
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          (char *)this + 136,
          0);
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          (char *)this + 144,
          0);
        *((_BYTE *)this + 128) = 0;
        *((_QWORD *)this + 9) = -1;
        *a3 = 1;
LABEL_23:
        v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
        goto LABEL_24;
      }
      if ( *v14 )
      {
        v12 = -1072875814;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
            this,
            -1072875814);
        goto LABEL_45;
      }
      v18 = **(__int64 (__fastcall ***)(FSKsEvent *, GUID *, IUnknown **))this;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&punkObject);
      v19 = v18(this, &GUID_00000000_0000_0000_c000_000000000046, &punkObject);
      v12 = v19;
      if ( v19 >= 0 )
      {
        v21 = ppAsyncResult;
        ppAsyncResult = 0;
        if ( v21 )
          ((void (__fastcall *)(IMFAsyncResult *))v21->lpVtbl->Release)(v21);
        v19 = MFCreateAsyncResult(punkObject, (IMFAsyncCallback *)this + 1, a2, &ppAsyncResult);
        v12 = v19;
        if ( v19 >= 0 )
        {
          v19 = MFPutWaitingWorkItem(*((HANDLE *)this + 18), 0, ppAsyncResult, (MFWORKITEM_KEY *)this + 19);
          v12 = v19;
          if ( v19 >= 0 )
            goto LABEL_23;
          if ( g_wppLevels )
          {
            v20 = 29;
            goto LABEL_44;
          }
        }
        else if ( g_wppLevels )
        {
          v20 = 28;
          goto LABEL_44;
        }
      }
      else if ( g_wppLevels )
      {
        v20 = 27;
LABEL_44:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v19);
      }
    }
    else
    {
      v19 = -1072875845;
      *((_BYTE *)this + 128) = 0;
      v12 = -1072875845;
      if ( g_wppLevels )
      {
        v20 = 25;
        goto LABEL_44;
      }
    }
LABEL_45:
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
    goto LABEL_46;
  }
LABEL_24:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v16 = 31;
LABEL_26:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v12);
  }
LABEL_27:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&punkObject);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppAsyncResult);
  LeaveCriticalSection(v3);
  return v12;
}

```

## disassembly

```asm
0x1800b6150  mov     [rsp-38h+arg_8], rbx
0x1800b6155  push    rbp
0x1800b6156  push    rsi
0x1800b6157  push    rdi
0x1800b6158  push    r12
0x1800b615a  push    r13
0x1800b615c  push    r14
0x1800b615e  push    r15
0x1800b6160  mov     rbp, rsp
0x1800b6163  sub     rsp, 60h
0x1800b6167  xor     r15d, r15d
0x1800b616a  lea     r12, [rcx+18h]
0x1800b616e  mov     rdi, rcx
0x1800b6171  mov     ebx, r15d
0x1800b6174  mov     rcx, r12; lpCriticalSection
0x1800b6177  mov     dword ptr [rbp+ppAsyncResult], ebx
0x1800b617a  mov     r14, r8
0x1800b617d  mov     r13, rdx
0x1800b6180  call    cs:__imp_EnterCriticalSection
0x1800b6186  mov     rax, [rdi+50h]
0x1800b618a  mov     [rbp+var_20], rax
0x1800b618e  mov     [rbp+ppAsyncResult], r15
0x1800b6192  mov     [rbp+punkObject], r15
0x1800b6196  cmp     cs:byte_18010EC4D, 8
0x1800b619d  jb      loc_1800B622F
0x1800b61a3  mov     eax, [rdi+60h]
0x1800b61a6  lea     edx, [r15+14h]
0x1800b61aa  movzx   ecx, byte ptr [rdi+80h]
0x1800b61b1  mov     r9, rdi
0x1800b61b4  mov     [rsp+60h+var_28], eax
0x1800b61b8  mov     rax, [rdi+48h]
0x1800b61bc  mov     [rsp+60h+var_30], rax
0x1800b61c1  mov     rax, [rdi+98h]
0x1800b61c8  mov     [rsp+60h+var_38], ecx
0x1800b61cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b61d3  mov     [rsp+60h+var_40], rax
0x1800b61d8  mov     rcx, [rcx+0D8h]
0x1800b61df  call    WPP_SF_qidid
0x1800b61e4  cmp     cs:byte_18010EC4D, 8
0x1800b61eb  jb      short loc_1800B622F
0x1800b61ed  mov     rdx, [rdi+0A8h]; struct IFSClientContextInfo *
0x1800b61f4  lea     rcx, [rbp+var_18]; this
0x1800b61f8  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x1800b61fd  mov     rcx, rax; this
0x1800b6200  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800b6205  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b620c  lea     edx, [r15+15h]
0x1800b6210  mov     r9, rdi
0x1800b6213  mov     [rsp+60h+var_40], rax
0x1800b6218  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b621f  mov     rcx, [rcx+0D8h]
0x1800b6226  call    WPP_SF_qs
0x1800b622b  lea     ebx, [r15+1]
0x1800b622f  test    bl, 1
0x1800b6232  jz      short loc_1800B623D
0x1800b6234  lea     rcx, [rbp+var_18]; this
0x1800b6238  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800b623d  cmp     [rdi+50h], r15
0x1800b6241  jnz     short loc_1800B627F
0x1800b6243  mov     eax, 0C00D36BBh
0x1800b6248  mov     ebx, eax
0x1800b624a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6251  jb      loc_1800B64C0
0x1800b6257  mov     edx, 16h
0x1800b625c  mov     dword ptr [rsp+60h+var_40], eax
0x1800b6260  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6267  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b626e  mov     r9, rdi
0x1800b6271  mov     rcx, [rcx+10h]
0x1800b6275  call    WPP_SF_qD
0x1800b627a  jmp     loc_1800B64C0
0x1800b627f  test    r13, r13
0x1800b6282  jnz     short loc_1800B62A0
0x1800b6284  mov     ebx, 80070057h
0x1800b6289  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6290  jb      loc_1800B64C0
0x1800b6296  lea     edx, [r13+17h]
0x1800b629a  mov     dword ptr [rsp+60h+var_40], ebx
0x1800b629e  jmp     short loc_1800B6260
0x1800b62a0  test    r14, r14
0x1800b62a3  jnz     short loc_1800B62BD
0x1800b62a5  mov     ebx, 80004003h
0x1800b62aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b62b1  jb      loc_1800B64C0
0x1800b62b7  lea     edx, [r14+18h]
0x1800b62bb  jmp     short loc_1800B629A
0x1800b62bd  lea     rsi, [rdi+98h]
0x1800b62c4  mov     [r14], r15d
0x1800b62c7  mov     ebx, r15d
0x1800b62ca  cmp     [rsi], r15
0x1800b62cd  jz      short loc_1800B6340
0x1800b62cf  cmp     [rdi+80h], r15b
0x1800b62d6  jz      short loc_1800B6340
0x1800b62d8  lea     r12, [rdi+88h]
0x1800b62df  mov     [rsi], r15
0x1800b62e2  mov     rcx, [r12]; this
0x1800b62e6  test    rcx, rcx
0x1800b62e9  jz      loc_1800B6482
0x1800b62ef  lea     r15, [rdi+90h]
0x1800b62f6  cmp     [r15], rbx
0x1800b62f9  jz      loc_1800B647F
0x1800b62ff  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800b6304  mov     rcx, [rbp+var_20]
0x1800b6308  mov     eax, [rcx+14h]
0x1800b630b  test    al, 2
0x1800b630d  jz      loc_1800B63A4
0x1800b6313  xor     edx, edx
0x1800b6315  mov     rcx, r12
0x1800b6318  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800b631d  xor     edx, edx
0x1800b631f  mov     rcx, r15
0x1800b6322  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800b6327  mov     [rdi+80h], bl
0x1800b632d  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x1800b6335  mov     dword ptr [r14], 1
0x1800b633c  lea     r12, [rdi+18h]
0x1800b6340  cmp     cs:byte_18010EC4D, 8
0x1800b6347  jb      short loc_1800B636F
0x1800b6349  mov     edx, 1Fh
0x1800b634e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6355  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b635c  mov     r9, rdi
0x1800b635f  mov     dword ptr [rsp+60h+var_40], ebx
0x1800b6363  mov     rcx, [rcx+0D8h]
0x1800b636a  call    WPP_SF_qD
0x1800b636f  lea     rcx, [rbp+punkObject]; void *
0x1800b6373  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b6378  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800b637c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b6381  mov     rcx, r12; lpCriticalSection
0x1800b6384  call    cs:__imp_LeaveCriticalSection
0x1800b638a  mov     eax, ebx
0x1800b638c  mov     rbx, [rsp+60h+arg_8]
0x1800b6394  add     rsp, 60h
0x1800b6398  pop     r15
0x1800b639a  pop     r14
0x1800b639c  pop     r13
0x1800b639e  pop     r12
0x1800b63a0  pop     rdi
0x1800b63a1  pop     rsi
0x1800b63a2  pop     rbp
0x1800b63a3  retn
0x1800b63a4  cmp     [rsi], rbx
0x1800b63a7  jz      short loc_1800B63C9
0x1800b63a9  mov     ebx, 0C00D36DAh
0x1800b63ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b63b5  jb      loc_1800B64BC
0x1800b63bb  mov     edx, 1Ah
0x1800b63c0  mov     dword ptr [rsp+60h+var_40], ebx
0x1800b63c4  jmp     loc_1800B64A2
0x1800b63c9  mov     rax, [rdi]
0x1800b63cc  lea     rcx, [rbp+punkObject]
0x1800b63d0  mov     rbx, [rax]
0x1800b63d3  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b63d8  lea     r8, [rbp+punkObject]
0x1800b63dc  mov     rcx, rdi
0x1800b63df  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800b63e6  mov     rax, rbx
0x1800b63e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b63ee  mov     ebx, eax
0x1800b63f0  test    eax, eax
0x1800b63f2  jns     short loc_1800B640B
0x1800b63f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b63fb  jb      loc_1800B64BC
0x1800b6401  mov     edx, 1Bh
0x1800b6406  jmp     loc_1800B649E
0x1800b640b  mov     rcx, [rbp+ppAsyncResult]
0x1800b640f  mov     [rbp+ppAsyncResult], 0
0x1800b6417  test    rcx, rcx
0x1800b641a  jz      short loc_1800B6428
0x1800b641c  mov     rax, [rcx]
0x1800b641f  mov     rax, [rax+10h]
0x1800b6423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6428  mov     rcx, [rbp+punkObject]; punkObject
0x1800b642c  lea     rdx, [rdi+8]; pCallback
0x1800b6430  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800b6434  mov     r8, r13; punkState
0x1800b6437  call    cs:__imp_MFCreateAsyncResult
0x1800b643d  mov     ebx, eax
0x1800b643f  test    eax, eax
0x1800b6441  jns     short loc_1800B6453
0x1800b6443  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b644a  jb      short loc_1800B64BC
0x1800b644c  mov     edx, 1Ch
0x1800b6451  jmp     short loc_1800B649E
0x1800b6453  mov     r8, [rbp+ppAsyncResult]; pResult
0x1800b6457  mov     r9, rsi; pKey
0x1800b645a  mov     rcx, [r15]; hEvent
0x1800b645d  xor     edx, edx; Priority
0x1800b645f  call    cs:__imp_MFPutWaitingWorkItem
0x1800b6465  mov     ebx, eax
0x1800b6467  test    eax, eax
0x1800b6469  jns     loc_1800B633C
0x1800b646f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6476  jb      short loc_1800B64BC
0x1800b6478  mov     edx, 1Dh
0x1800b647d  jmp     short loc_1800B649E
0x1800b647f  xor     r15d, r15d
0x1800b6482  mov     eax, 0C00D36BBh
0x1800b6487  mov     [rdi+80h], r15b
0x1800b648e  mov     ebx, eax
0x1800b6490  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6497  jb      short loc_1800B64BC
0x1800b6499  mov     edx, 19h
0x1800b649e  mov     dword ptr [rsp+60h+var_40], eax
0x1800b64a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b64a9  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b64b0  mov     r9, rdi
0x1800b64b3  mov     rcx, [rcx+10h]
0x1800b64b7  call    WPP_SF_qD
0x1800b64bc  lea     r12, [rdi+18h]
0x1800b64c0  cmp     cs:byte_18010EC4D, 1
0x1800b64c7  jb      loc_1800B636F
0x1800b64cd  mov     edx, 1Eh
0x1800b64d2  jmp     loc_1800B634E
```
