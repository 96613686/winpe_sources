# FSKsEvent::InternalEnableEvent(IKsControl *,IFSControl *)

- ea: `0x1800b6710`
- end: `0x1800b6aa8`
- name: `?InternalEnableEvent@FSKsEvent@@MEAAJPEAUIKsControl@@PEAUIFSControl@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(FSKsEvent *__hidden this, struct IKsControl *, struct IFSControl *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x1800b6710`
- `0x1800b74b8`
- `0x1800b7528`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCancelWorkItem` at `0x1800b6a0b`
- `MFPlat!MFCancelWorkItem` at `0x1800b6a0b`
- `MFPlat!MFCreateAsyncResult` at `0x1800b692c`
- `MFPlat!MFCreateAsyncResult` at `0x1800b692c`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800b6958`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800b6958`

## pseudocode

```c
__int64 __fastcall FSKsEvent::InternalEnableEvent(
        FSKsEvent *this,
        struct IKsControl *a2,
        __int64 (__fastcall ***a3)(struct IFSControl *, GUID *, IUnknown **))
{
  __int64 v3; // r13
  _DWORD *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  char v10; // r14
  __int64 (__fastcall **v11)(FSKsEvent *, GUID *, IUnknown **); // rax
  __int64 (__fastcall *v12)(FSKsEvent *, GUID *, IUnknown **); // rbx
  HRESULT v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(struct IFSControl *, GUID *, IUnknown **); // rbx
  IMFAsyncResult *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  MFWORKITEM_KEY v20; // rcx
  IUnknown *punkState; // [rsp+40h] [rbp-10h] BYREF
  IUnknown *punkObject; // [rsp+48h] [rbp-8h] BYREF
  int v24; // [rsp+90h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *((_QWORD *)this + 10);
  v24 = 0;
  v7 = (_DWORD *)((char *)this + 96);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qidid(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      47,
      *((unsigned __int8 *)this + 128),
      this,
      *((_QWORD *)this + 19),
      *((unsigned __int8 *)this + 128),
      *((_QWORD *)this + 9),
      *v7);
  if ( !*((_QWORD *)this + 10) )
  {
    v8 = -1072875850;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
        this,
        -1072875850);
    goto LABEL_41;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_41;
    v9 = 49;
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( g_wppLevels )
    {
      v9 = 50;
LABEL_10:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
        this,
        -2147024809);
    }
LABEL_41:
    if ( byte_18010EC4D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 57, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v8);
    return v8;
  }
  v10 = 0;
  if ( *v7 == 1 )
  {
    v11 = *(__int64 (__fastcall ***)(FSKsEvent *, GUID *, IUnknown **))this;
    ppAsyncResult = 0;
    punkObject = 0;
    punkState = 0;
    v12 = *v11;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&punkObject);
    v13 = v12(this, &GUID_00000000_0000_0000_c000_000000000046, &punkObject);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 51;
LABEL_33:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v13);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    v15 = **a3;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&punkState);
    v13 = v15((struct IFSControl *)a3, &GUID_00000000_0000_0000_c000_000000000046, &punkState);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 52;
        goto LABEL_33;
      }
LABEL_24:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&punkState);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&punkObject);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppAsyncResult);
      goto LABEL_41;
    }
    if ( *((_QWORD *)this + 19) )
    {
      v8 = -1072875814;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids,
          this,
          -1072875814);
      goto LABEL_24;
    }
    v16 = ppAsyncResult;
    ppAsyncResult = 0;
    if ( v16 )
      ((void (__fastcall *)(IMFAsyncResult *))v16->lpVtbl->Release)(v16);
    v13 = MFCreateAsyncResult(punkObject, (IMFAsyncCallback *)this + 1, punkState, &ppAsyncResult);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 54;
        goto LABEL_33;
      }
      goto LABEL_24;
    }
    v13 = MFPutWaitingWorkItem(*((HANDLE *)this + 18), 0, ppAsyncResult, (MFWORKITEM_KEY *)this + 19);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 55;
        goto LABEL_33;
      }
      goto LABEL_24;
    }
    v10 = 1;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&punkState);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&punkObject);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppAsyncResult);
  }
  v17 = ((__int64 (__fastcall *)(struct IKsControl *, __int64, _QWORD, _DWORD *, int, int *))a2->lpVtbl->KsEvent)(
          a2,
          v3,
          *((unsigned int *)this + 22),
          v7,
          32,
          &v24);
  v8 = v17;
  if ( v17 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids, this, v17);
    if ( v10 )
    {
      v20 = *((_QWORD *)this + 19);
      if ( v20 )
      {
        MFCancelWorkItem(v20);
        *((_QWORD *)this + 19) = 0;
      }
    }
    goto LABEL_41;
  }
  *((_BYTE *)this + 128) = 1;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qDid(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v18,
      v19,
      this,
      v17,
      *((_QWORD *)this + 19),
      *((unsigned __int8 *)this + 128));
  return v8;
}

```

## disassembly

```asm
0x1800b6710  mov     r11, rsp
0x1800b6713  mov     [r11+10h], rbx
0x1800b6717  push    rbp
0x1800b6718  push    rsi
0x1800b6719  push    rdi
0x1800b671a  push    r12
0x1800b671c  push    r13
0x1800b671e  push    r14
0x1800b6720  push    r15
0x1800b6722  mov     rbp, rsp
0x1800b6725  sub     rsp, 50h
0x1800b6729  mov     r13, [rcx+50h]
0x1800b672d  xor     ebx, ebx
0x1800b672f  mov     [rbp+arg_0], ebx
0x1800b6732  mov     r15, r8
0x1800b6735  mov     r12, rdx
0x1800b6738  mov     rdi, rcx
0x1800b673b  cmp     cs:byte_18010EC4D, 8
0x1800b6742  lea     rsi, [rcx+60h]
0x1800b6746  jb      short loc_1800B6786
0x1800b6748  movzx   r8d, byte ptr [rcx+80h]
0x1800b6750  lea     edx, [rbx+2Fh]
0x1800b6753  mov     eax, [rsi]
0x1800b6755  mov     r9, rcx
0x1800b6758  mov     [rsp+50h+var_18], eax
0x1800b675c  mov     rax, [rcx+48h]
0x1800b6760  mov     [r11-58h], rax
0x1800b6764  mov     rax, [rcx+98h]
0x1800b676b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6772  mov     [r11-60h], r8d
0x1800b6776  mov     [r11-68h], rax
0x1800b677a  mov     rcx, [rcx+0D8h]
0x1800b6781  call    WPP_SF_qidid
0x1800b6786  cmp     [rdi+50h], rbx
0x1800b678a  jnz     short loc_1800B67C6
0x1800b678c  mov     ebx, 0C00D36B6h
0x1800b6791  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6798  jb      loc_1800B6A1C
0x1800b679e  mov     edx, 30h ; '0'
0x1800b67a3  mov     [rsp+50h+var_30], ebx
0x1800b67a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b67ae  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b67b5  mov     r9, rdi
0x1800b67b8  mov     rcx, [rcx+10h]
0x1800b67bc  call    WPP_SF_qD
0x1800b67c1  jmp     loc_1800B6A1C
0x1800b67c6  test    r15, r15
0x1800b67c9  jnz     short loc_1800B67E9
0x1800b67cb  mov     eax, 80070057h
0x1800b67d0  mov     ebx, eax
0x1800b67d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b67d9  jb      loc_1800B6A1C
0x1800b67df  lea     edx, [r15+31h]
0x1800b67e3  mov     [rsp+50h+var_30], eax
0x1800b67e7  jmp     short loc_1800B67A7
0x1800b67e9  test    r12, r12
0x1800b67ec  jnz     short loc_1800B6809
0x1800b67ee  mov     eax, 80070057h
0x1800b67f3  mov     ebx, eax
0x1800b67f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b67fc  jb      loc_1800B6A1C
0x1800b6802  lea     edx, [r12+32h]
0x1800b6807  jmp     short loc_1800B67E3
0x1800b6809  cmp     dword ptr [rsi], 1
0x1800b680c  mov     r14b, bl
0x1800b680f  jnz     loc_1800B699D
0x1800b6815  mov     rax, [rdi]
0x1800b6818  lea     rcx, [rbp+punkObject]
0x1800b681c  mov     [rbp+ppAsyncResult], rbx
0x1800b6820  mov     [rbp+punkObject], rbx
0x1800b6824  mov     [rbp+punkState], rbx
0x1800b6828  mov     rbx, [rax]
0x1800b682b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b6830  lea     r8, [rbp+punkObject]
0x1800b6834  mov     rcx, rdi
0x1800b6837  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800b683e  mov     rax, rbx
0x1800b6841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6846  mov     ebx, eax
0x1800b6848  test    eax, eax
0x1800b684a  jns     short loc_1800B6863
0x1800b684c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6853  jb      loc_1800B68DF
0x1800b6859  mov     edx, 33h ; '3'
0x1800b685e  jmp     loc_1800B6976
0x1800b6863  mov     rax, [r15]
0x1800b6866  lea     rcx, [rbp+punkState]
0x1800b686a  mov     rbx, [rax]
0x1800b686d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b6872  lea     r8, [rbp+punkState]
0x1800b6876  mov     rcx, r15
0x1800b6879  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800b6880  mov     rax, rbx
0x1800b6883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6888  mov     ebx, eax
0x1800b688a  test    eax, eax
0x1800b688c  jns     short loc_1800B68A1
0x1800b688e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6895  jb      short loc_1800B68DF
0x1800b6897  mov     edx, 34h ; '4'
0x1800b689c  jmp     loc_1800B6976
0x1800b68a1  lea     r14, [rdi+98h]
0x1800b68a8  cmp     qword ptr [r14], 0
0x1800b68ac  jz      short loc_1800B68FF
0x1800b68ae  mov     ebx, 0C00D36DAh
0x1800b68b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b68ba  jb      short loc_1800B68DF
0x1800b68bc  mov     edx, 35h ; '5'
0x1800b68c1  mov     [rsp+50h+var_30], ebx
0x1800b68c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b68cc  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b68d3  mov     r9, rdi
0x1800b68d6  mov     rcx, [rcx+10h]
0x1800b68da  call    WPP_SF_qD
0x1800b68df  lea     rcx, [rbp+punkState]; void *
0x1800b68e3  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b68e8  lea     rcx, [rbp+punkObject]; void *
0x1800b68ec  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b68f1  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800b68f5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b68fa  jmp     loc_1800B6A1C
0x1800b68ff  mov     rcx, [rbp+ppAsyncResult]
0x1800b6903  mov     [rbp+ppAsyncResult], 0
0x1800b690b  test    rcx, rcx
0x1800b690e  jz      short loc_1800B691C
0x1800b6910  mov     rax, [rcx]
0x1800b6913  mov     rax, [rax+10h]
0x1800b6917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b691c  mov     r8, [rbp+punkState]; punkState
0x1800b6920  lea     rdx, [rdi+8]; pCallback
0x1800b6924  mov     rcx, [rbp+punkObject]; punkObject
0x1800b6928  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800b692c  call    cs:__imp_MFCreateAsyncResult
0x1800b6932  mov     ebx, eax
0x1800b6934  test    eax, eax
0x1800b6936  jns     short loc_1800B6948
0x1800b6938  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b693f  jb      short loc_1800B68DF
0x1800b6941  mov     edx, 36h ; '6'
0x1800b6946  jmp     short loc_1800B6976
0x1800b6948  mov     r8, [rbp+ppAsyncResult]; pResult
0x1800b694c  mov     r9, r14; pKey
0x1800b694f  mov     rcx, [rdi+90h]; hEvent
0x1800b6956  xor     edx, edx; Priority
0x1800b6958  call    cs:__imp_MFPutWaitingWorkItem
0x1800b695e  mov     ebx, eax
0x1800b6960  test    eax, eax
0x1800b6962  jns     short loc_1800B697F
0x1800b6964  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b696b  jb      loc_1800B68DF
0x1800b6971  mov     edx, 37h ; '7'
0x1800b6976  mov     [rsp+50h+var_30], eax
0x1800b697a  jmp     loc_1800B68C5
0x1800b697f  lea     rcx, [rbp+punkState]; void *
0x1800b6983  mov     r14b, 1
0x1800b6986  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b698b  lea     rcx, [rbp+punkObject]; void *
0x1800b698f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b6994  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800b6998  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b699d  mov     rax, [r12]
0x1800b69a1  lea     rcx, [rbp+arg_0]
0x1800b69a5  mov     r8d, [rdi+58h]
0x1800b69a9  mov     r9, rsi
0x1800b69ac  mov     [rsp+50h+var_28], rcx
0x1800b69b1  mov     rdx, r13
0x1800b69b4  mov     rcx, r12
0x1800b69b7  mov     [rsp+50h+var_30], 20h ; ' '
0x1800b69bf  mov     rax, [rax+28h]
0x1800b69c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69c8  mov     ebx, eax
0x1800b69ca  test    eax, eax
0x1800b69cc  jns     short loc_1800B6A4D
0x1800b69ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b69d5  jb      short loc_1800B69FA
0x1800b69d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b69de  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b69e5  mov     edx, 38h ; '8'
0x1800b69ea  mov     [rsp+50h+var_30], eax
0x1800b69ee  mov     r9, rdi
0x1800b69f1  mov     rcx, [rcx+10h]
0x1800b69f5  call    WPP_SF_qD
0x1800b69fa  test    r14b, r14b
0x1800b69fd  jz      short loc_1800B6A1C
0x1800b69ff  mov     rcx, [rdi+98h]; Key
0x1800b6a06  test    rcx, rcx
0x1800b6a09  jz      short loc_1800B6A1C
0x1800b6a0b  call    cs:__imp_MFCancelWorkItem
0x1800b6a11  mov     qword ptr [rdi+98h], 0
0x1800b6a1c  cmp     cs:byte_18010EC4D, 1
0x1800b6a23  jb      short loc_1800B6A8E
0x1800b6a25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a2c  lea     r8, WPP_4b0984c5b16033c65e69eaac7c786463_Traceguids
0x1800b6a33  mov     edx, 39h ; '9'
0x1800b6a38  mov     [rsp+50h+var_30], ebx
0x1800b6a3c  mov     r9, rdi
0x1800b6a3f  mov     rcx, [rcx+0D8h]
0x1800b6a46  call    WPP_SF_qD
0x1800b6a4b  jmp     short loc_1800B6A8E
0x1800b6a4d  mov     byte ptr [rdi+80h], 1
0x1800b6a54  cmp     cs:byte_18010EC4D, 8
0x1800b6a5b  jb      short loc_1800B6A8E
0x1800b6a5d  movzx   eax, byte ptr [rdi+80h]
0x1800b6a64  mov     r9, rdi
0x1800b6a67  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a6e  mov     [rsp+50h+var_20], eax
0x1800b6a72  mov     rax, [rdi+98h]
0x1800b6a79  mov     [rsp+50h+var_28], rax
0x1800b6a7e  mov     rcx, [rcx+0D8h]
0x1800b6a85  mov     [rsp+50h+var_30], ebx
0x1800b6a89  call    WPP_SF_qDid
0x1800b6a8e  mov     eax, ebx
0x1800b6a90  mov     rbx, [rsp+50h+arg_8]
0x1800b6a98  add     rsp, 50h
0x1800b6a9c  pop     r15
0x1800b6a9e  pop     r14
0x1800b6aa0  pop     r13
0x1800b6aa2  pop     r12
0x1800b6aa4  pop     rdi
0x1800b6aa5  pop     rsi
0x1800b6aa6  pop     rbp
0x1800b6aa7  retn
```
