# FSActivityObject::OnPrivacyShutterChanged(IMFAsyncResult *)

- ea: `0x180023a5c`
- end: `0x180023d48`
- name: `?OnPrivacyShutterChanged@FSActivityObject@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `748`
- prototype: `void __fastcall(FSActivityObject *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023a40`

## callees

- `0x180008cf0`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x18001abc8`
- `0x180022fbc`
- `0x180023238`
- `0x180023a5c`
- `0x180023e08`
- `0x180024238`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023c58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023c58`
- `MFPlat!MFCreateAsyncResult` at `0x180023bdd`
- `MFPlat!MFCreateAsyncResult` at `0x180023bdd`
- `MFPlat!MFPutWaitingWorkItem` at `0x180023c14`
- `MFPlat!MFPutWaitingWorkItem` at `0x180023c14`

## pseudocode

```c
void __fastcall FSActivityObject::OnPrivacyShutterChanged(FSActivityObject *this, struct IMFAsyncResult *a2)
{
  __int64 v2; // r14
  int v4; // esi
  HRESULT PrivacyShutterValue; // eax
  __int64 v6; // rdx
  IMFAsyncResult *v7; // rcx
  int v8; // edx
  int v9; // r8d
  const wchar_t *v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-20h]
  IMFAsyncResult *ppAsyncResult; // [rsp+80h] [rbp+40h] BYREF
  struct IMFAsyncResult *v13; // [rsp+88h] [rbp+48h] BYREF
  __int64 v14; // [rsp+90h] [rbp+50h] BYREF

  v13 = a2;
  v2 = 0;
  v14 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 47, &WPP_7bc5bb764cec377de403c44151704250_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_BYTE *)this + 64) )
  {
    v4 = -1072873851;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_7bc5bb764cec377de403c44151704250_Traceguids,
        this,
        -1072873851);
    goto LABEL_6;
  }
  v4 = 0;
  if ( *((_BYTE *)this + 200) )
  {
    ppAsyncResult = 0;
    LODWORD(v13) = 0;
    PrivacyShutterValue = FSActivityObject::GetPrivacyShutterValue(this, (unsigned int *)&v13);
    v4 = PrivacyShutterValue;
    if ( PrivacyShutterValue < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_12:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppAsyncResult);
LABEL_6:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        goto LABEL_34;
      }
      v6 = 49;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        &WPP_7bc5bb764cec377de403c44151704250_Traceguids,
        this,
        PrivacyShutterValue);
      goto LABEL_12;
    }
    if ( (_DWORD)v13 )
      FSActivityObject::SetOcclusionState(this);
    else
      FSActivityObject::ClearOcclusionState(this);
    v2 = *((_QWORD *)this + 9);
    v14 = v2;
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    ++*((_DWORD *)this + 51);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 50, &WPP_7bc5bb764cec377de403c44151704250_Traceguids, this);
    v7 = ppAsyncResult;
    ppAsyncResult = 0;
    if ( v7 )
      ((void (__fastcall *)(IMFAsyncResult *))v7->lpVtbl->Release)(v7);
    PrivacyShutterValue = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 1, 0, &ppAsyncResult);
    v4 = PrivacyShutterValue;
    if ( PrivacyShutterValue < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v6 = 51;
      goto LABEL_11;
    }
    PrivacyShutterValue = MFPutWaitingWorkItem(*((HANDLE *)this + 23), 0, ppAsyncResult, (MFWORKITEM_KEY *)this + 24);
    v4 = PrivacyShutterValue;
    if ( PrivacyShutterValue < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v6 = 52;
      goto LABEL_11;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppAsyncResult);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 176));
    v4 = FSActivityManager::InternalPostOcclusionStates((FSActivityManager *)v2);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 176));
    if ( v4 >= 0 )
      goto LABEL_36;
    if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_7bc5bb764cec377de403c44151704250_Traceguids, this, v4);
      goto LABEL_34;
    }
  }
  if ( v4 < 0 )
  {
LABEL_34:
    if ( byte_18010EC4D )
    {
      LODWORD(v11) = v4;
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        54,
        &WPP_7bc5bb764cec377de403c44151704250_Traceguids,
        this,
        v11,
        *((_DWORD *)this + 42));
    }
    goto LABEL_40;
  }
LABEL_36:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = L"yes";
    if ( !*((_BYTE *)this + 200) )
      v10 = L"no";
    WPP_SF_qDdSD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v8,
      v9,
      (_DWORD)this,
      v4,
      *((_DWORD *)this + 42),
      (__int64)v10,
      *((_DWORD *)this + 51));
  }
LABEL_40:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v14);
}

```

## disassembly

```asm
0x180023a5c  mov     [rsp-38h+arg_8], rdx
0x180023a61  push    rbp
0x180023a62  push    rbx
0x180023a63  push    rsi
0x180023a64  push    rdi
0x180023a65  push    r13
0x180023a67  push    r14
0x180023a69  push    r15
0x180023a6b  mov     rbp, rsp
0x180023a6e  sub     rsp, 40h
0x180023a72  xor     r14d, r14d
0x180023a75  mov     rdi, rcx
0x180023a78  mov     [rbp+arg_10], r14
0x180023a7c  cmp     cs:byte_18010EC4D, 8
0x180023a83  lea     r13, WPP_7bc5bb764cec377de403c44151704250_Traceguids
0x180023a8a  jb      short loc_180023AA9
0x180023a8c  mov     r9, rcx
0x180023a8f  lea     edx, [r14+2Fh]
0x180023a93  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a9a  mov     r8, r13
0x180023a9d  mov     rcx, [rcx+0D8h]
0x180023aa4  call    WPP_SF_q
0x180023aa9  lea     rbx, [rdi+18h]
0x180023aad  mov     rcx, rbx; lpCriticalSection
0x180023ab0  call    cs:__imp_EnterCriticalSection
0x180023ab6  cmp     [rdi+40h], r14b
0x180023aba  jz      short loc_180023AF7
0x180023abc  mov     esi, 0C00D3E85h
0x180023ac1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023ac8  jb      short loc_180023AE9
0x180023aca  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ad1  mov     edx, 30h ; '0'
0x180023ad6  mov     r9, rdi
0x180023ad9  mov     dword ptr [rsp+40h+var_20], esi
0x180023add  mov     r8, r13
0x180023ae0  mov     rcx, [rcx+10h]
0x180023ae4  call    WPP_SF_qD
0x180023ae9  mov     rcx, rbx; lpCriticalSection
0x180023aec  call    cs:__imp_LeaveCriticalSection
0x180023af2  jmp     loc_180023CA3
0x180023af7  xor     esi, esi
0x180023af9  lea     r15, [rdi+0C8h]
0x180023b00  cmp     [r15], sil
0x180023b03  jz      loc_180023C40
0x180023b09  lea     rdx, [rbp+arg_8]; unsigned int *
0x180023b0d  mov     [rbp+ppAsyncResult], rsi
0x180023b11  mov     rcx, rdi; this
0x180023b14  mov     dword ptr [rbp+arg_8], esi
0x180023b17  call    ?GetPrivacyShutterValue@FSActivityObject@@IEAAJPEAK@Z; FSActivityObject::GetPrivacyShutterValue(ulong *)
0x180023b1c  mov     esi, eax
0x180023b1e  test    eax, eax
0x180023b20  jns     short loc_180023B55
0x180023b22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023b29  jb      short loc_180023B4A
0x180023b2b  mov     edx, 31h ; '1'
0x180023b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b37  mov     r9, rdi
0x180023b3a  mov     r8, r13
0x180023b3d  mov     dword ptr [rsp+40h+var_20], eax
0x180023b41  mov     rcx, [rcx+10h]
0x180023b45  call    WPP_SF_qD
0x180023b4a  lea     rcx, [rbp+ppAsyncResult]; void *
0x180023b4e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180023b53  jmp     short loc_180023AE9
0x180023b55  mov     rcx, rdi
0x180023b58  cmp     dword ptr [rbp+arg_8], r14d
0x180023b5c  jnz     short loc_180023B65
0x180023b5e  call    ?ClearOcclusionState@FSActivityObject@@QEAAXW4MFCameraOcclusionState@@@Z; FSActivityObject::ClearOcclusionState(MFCameraOcclusionState)
0x180023b63  jmp     short loc_180023B6A
0x180023b65  call    ?SetOcclusionState@FSActivityObject@@QEAAXW4MFCameraOcclusionState@@@Z; FSActivityObject::SetOcclusionState(MFCameraOcclusionState)
0x180023b6a  mov     r14, [rdi+48h]
0x180023b6e  mov     [rbp+arg_10], r14
0x180023b72  test    r14, r14
0x180023b75  jz      short loc_180023B86
0x180023b77  mov     rax, [r14]
0x180023b7a  mov     rcx, r14
0x180023b7d  mov     rax, [rax+8]
0x180023b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b86  inc     dword ptr [rdi+0CCh]
0x180023b8c  cmp     cs:byte_18010EC4D, 8
0x180023b93  jb      short loc_180023BB3
0x180023b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b9c  mov     edx, 32h ; '2'
0x180023ba1  mov     r9, rdi
0x180023ba4  mov     r8, r13
0x180023ba7  mov     rcx, [rcx+0D8h]
0x180023bae  call    WPP_SF_q
0x180023bb3  mov     rcx, [rbp+ppAsyncResult]
0x180023bb7  mov     [rbp+ppAsyncResult], 0
0x180023bbf  test    rcx, rcx
0x180023bc2  jz      short loc_180023BD0
0x180023bc4  mov     rax, [rcx]
0x180023bc7  mov     rax, [rax+10h]
0x180023bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bd0  lea     rdx, [rdi+8]; pCallback
0x180023bd4  xor     r8d, r8d; punkState
0x180023bd7  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x180023bdb  xor     ecx, ecx; punkObject
0x180023bdd  call    cs:__imp_MFCreateAsyncResult
0x180023be3  mov     esi, eax
0x180023be5  test    eax, eax
0x180023be7  jns     short loc_180023C00
0x180023be9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023bf0  jb      loc_180023B4A
0x180023bf6  mov     edx, 33h ; '3'
0x180023bfb  jmp     loc_180023B30
0x180023c00  mov     r8, [rbp+ppAsyncResult]; pResult
0x180023c04  lea     r9, [rdi+0C0h]; pKey
0x180023c0b  mov     rcx, [rdi+0B8h]; hEvent
0x180023c12  xor     edx, edx; Priority
0x180023c14  call    cs:__imp_MFPutWaitingWorkItem
0x180023c1a  mov     esi, eax
0x180023c1c  test    eax, eax
0x180023c1e  jns     short loc_180023C37
0x180023c20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023c27  jb      loc_180023B4A
0x180023c2d  mov     edx, 34h ; '4'
0x180023c32  jmp     loc_180023B30
0x180023c37  lea     rcx, [rbp+ppAsyncResult]; void *
0x180023c3b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180023c40  mov     rcx, rbx; lpCriticalSection
0x180023c43  call    cs:__imp_LeaveCriticalSection
0x180023c49  test    r14, r14
0x180023c4c  jz      short loc_180023C9F
0x180023c4e  lea     rbx, [r14+0B0h]
0x180023c55  mov     rcx, rbx; lpCriticalSection
0x180023c58  call    cs:__imp_EnterCriticalSection
0x180023c5e  mov     rcx, r14; this
0x180023c61  call    ?InternalPostOcclusionStates@FSActivityManager@@IEAAJXZ; FSActivityManager::InternalPostOcclusionStates(void)
0x180023c66  mov     rcx, rbx; lpCriticalSection
0x180023c69  mov     esi, eax
0x180023c6b  call    cs:__imp_LeaveCriticalSection
0x180023c71  test    esi, esi
0x180023c73  jns     short loc_180023CDE
0x180023c75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023c7c  jb      short loc_180023C9F
0x180023c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c85  mov     edx, 35h ; '5'
0x180023c8a  mov     r9, rdi
0x180023c8d  mov     dword ptr [rsp+40h+var_20], esi
0x180023c91  mov     r8, r13
0x180023c94  mov     rcx, [rcx+10h]
0x180023c98  call    WPP_SF_qD
0x180023c9d  jmp     short loc_180023CA3
0x180023c9f  test    esi, esi
0x180023ca1  jns     short loc_180023CDE
0x180023ca3  cmp     cs:byte_18010EC4D, 1
0x180023caa  jb      loc_180023D30
0x180023cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cb7  mov     edx, 36h ; '6'
0x180023cbc  mov     eax, [rdi+0A8h]
0x180023cc2  mov     r9, rdi
0x180023cc5  mov     [rsp+40h+var_18], eax
0x180023cc9  mov     r8, r13
0x180023ccc  mov     dword ptr [rsp+40h+var_20], esi
0x180023cd0  mov     rcx, [rcx+0D8h]
0x180023cd7  call    WPP_SF_qDD
0x180023cdc  jmp     short loc_180023D30
0x180023cde  cmp     cs:byte_18010EC4D, 8
0x180023ce5  jb      short loc_180023D30
0x180023ce7  cmp     byte ptr [r15], 0
0x180023ceb  lea     rax, aNo; "no"
0x180023cf2  lea     rcx, aYes; "yes"
0x180023cf9  mov     r9, rdi
0x180023cfc  cmovz   rcx, rax
0x180023d00  mov     eax, [rdi+0CCh]
0x180023d06  mov     [rsp+40h+var_8], eax
0x180023d0a  mov     eax, [rdi+0A8h]
0x180023d10  mov     [rsp+40h+var_10], rcx
0x180023d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d1c  mov     [rsp+40h+var_18], eax
0x180023d20  mov     dword ptr [rsp+40h+var_20], esi
0x180023d24  mov     rcx, [rcx+0D8h]
0x180023d2b  call    WPP_SF_qDdSD
0x180023d30  lea     rcx, [rbp+arg_10]; void *
0x180023d34  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180023d39  add     rsp, 40h
0x180023d3d  pop     r15
0x180023d3f  pop     r14
0x180023d41  pop     r13
0x180023d43  pop     rdi
0x180023d44  pop     rsi
0x180023d45  pop     rbx
0x180023d46  pop     rbp
0x180023d47  retn
```
