# FSMCameraDeviceProperties::DeserializeFromBlob(uchar const *,ulong)

- ea: `0x180046490`
- end: `0x1800466c6`
- name: `?DeserializeFromBlob@FSMCameraDeviceProperties@@UEAAJPEBEK@Z`
- size: `566`
- prototype: `__int64 __fastcall(FSMCameraDeviceProperties *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005f98`
- `0x1800060f8`
- `0x180006a98`
- `0x180046490`
- `0x18004928c`
- `0x18004bf50`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800464b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800464b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800466a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800466a6`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceProperties::DeserializeFromBlob(
        FSMCameraDeviceProperties *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  unsigned __int64 v4; // r12
  const unsigned __int8 *v5; // r13
  int v6; // esi
  __int64 v7; // rbx
  unsigned int v8; // r15d
  const unsigned __int8 *v9; // r13
  struct FSMCameraDeviceProperty *v10; // rbx
  __int64 v11; // rdx
  struct FSMCameraDeviceProperty *v13; // [rsp+70h] [rbp+40h] BYREF
  const unsigned __int8 *v14; // [rsp+78h] [rbp+48h]
  void *v15; // [rsp+88h] [rbp+58h] BYREF

  v14 = a2;
  v4 = a3;
  v5 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 && (_DWORD)v4 )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v13 = 0;
      v15 = 0;
      if ( v4 < v7 + 48 )
        break;
      v8 = v7 + 48;
      if ( (int)v7 + 48 < (unsigned int)v7 )
      {
        v6 = -2147024362;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 47;
        goto LABEL_25;
      }
      v9 = &v5[(unsigned int)v7];
      v6 = 0;
      if ( (unsigned int)v4 < v8 + *((_DWORD *)v9 + 9) )
        break;
      (*(void (__fastcall **)(FSMCameraDeviceProperties *, const unsigned __int8 *))(*(_QWORD *)this + 136LL))(this, v9);
      v6 = FSMCameraDeviceProperty::CreateFSMDeviceProperty((const struct _DEVPROPKEY *)v9, *((_DWORD *)v9 + 8), &v13);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 48;
        goto LABEL_25;
      }
      v10 = v13;
      v6 = (*(__int64 (__fastcall **)(struct FSMCameraDeviceProperty *, __int64, _QWORD, void **, _QWORD))(*(_QWORD *)v13 + 48LL))(
             v13,
             2,
             *((unsigned int *)v9 + 9),
             &v15,
             0);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 49;
        goto LABEL_25;
      }
      memcpy_0(v15, &v14[v8], *((unsigned int *)v9 + 9));
      v6 = (*(__int64 (__fastcall **)(struct FSMCameraDeviceProperty *, _QWORD))(*(_QWORD *)v10 + 56LL))(
             v10,
             *((unsigned int *)v9 + 9));
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 50;
        goto LABEL_25;
      }
      v6 = (*(__int64 (__fastcall **)(FSMCameraDeviceProperties *, struct FSMCameraDeviceProperty *))(*(_QWORD *)this + 120LL))(
             this,
             v10);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 51;
        goto LABEL_25;
      }
      v7 = v8 + *((_DWORD *)v9 + 9);
      if ( (unsigned int)v7 < v8 )
      {
        v6 = -2147024362;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          break;
        v11 = 52;
LABEL_25:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, this, v6);
        break;
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v13);
      v5 = v14;
      v6 = 0;
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v13);
  }
  else
  {
    v6 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids,
        this,
        -2147024809);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046490  mov     [rsp-38h+arg_10], rbx
0x180046495  mov     [rsp-38h+arg_8], rdx
0x18004649a  push    rbp
0x18004649b  push    rsi
0x18004649c  push    rdi
0x18004649d  push    r12
0x18004649f  push    r13
0x1800464a1  push    r14
0x1800464a3  push    r15
0x1800464a5  mov     rbp, rsp
0x1800464a8  sub     rsp, 30h
0x1800464ac  mov     r14, rcx
0x1800464af  mov     r12d, r8d
0x1800464b2  add     rcx, 10h; lpCriticalSection
0x1800464b6  mov     r13, rdx
0x1800464b9  call    cs:__imp_EnterCriticalSection
0x1800464bf  test    r13, r13
0x1800464c2  jz      loc_180046671
0x1800464c8  test    r12d, r12d
0x1800464cb  jz      loc_180046671
0x1800464d1  xor     esi, esi
0x1800464d3  xor     ebx, ebx
0x1800464d5  mov     rdx, r12
0x1800464d8  mov     [rbp+arg_0], 0
0x1800464e0  lea     rax, [rbx+30h]
0x1800464e4  mov     [rbp+arg_18], 0
0x1800464ec  mov     ecx, ebx
0x1800464ee  cmp     rdx, rax
0x1800464f1  jb      loc_180046666
0x1800464f7  lea     r15d, [rbx+30h]
0x1800464fb  cmp     r15d, ebx
0x1800464fe  jb      loc_180046635
0x180046504  add     r13, rcx
0x180046507  xor     esi, esi
0x180046509  mov     ecx, [r13+24h]
0x18004650d  add     ecx, r15d
0x180046510  cmp     r12d, ecx
0x180046513  jb      loc_180046666
0x180046519  mov     rax, [r14]
0x18004651c  mov     rdx, r13
0x18004651f  mov     rcx, r14
0x180046522  mov     rax, [rax+88h]
0x180046529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004652e  mov     edx, [r13+20h]; unsigned int
0x180046532  lea     r8, [rbp+arg_0]; struct FSMCameraDeviceProperty **
0x180046536  mov     rcx, r13; struct _DEVPROPKEY *
0x180046539  call    ?CreateFSMDeviceProperty@FSMCameraDeviceProperty@@SAJAEBU_DEVPROPKEY@@KPEAPEAV1@@Z; FSMCameraDeviceProperty::CreateFSMDeviceProperty(_DEVPROPKEY const &,ulong,FSMCameraDeviceProperty * *)
0x18004653e  mov     esi, eax
0x180046540  test    eax, eax
0x180046542  js      loc_180046625
0x180046548  mov     rbx, [rbp+arg_0]
0x18004654c  lea     r9, [rbp+arg_18]
0x180046550  mov     r8d, [r13+24h]
0x180046554  mov     edx, 2
0x180046559  mov     rcx, rbx
0x18004655c  mov     [rsp+30h+var_10], 0
0x180046565  mov     rax, [rbx]
0x180046568  mov     rax, [rax+30h]
0x18004656c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046571  mov     esi, eax
0x180046573  test    eax, eax
0x180046575  js      loc_180046615
0x18004657b  mov     r8d, [r13+24h]; Size
0x18004657f  mov     rcx, [rbp+arg_18]; void *
0x180046583  mov     edx, r15d
0x180046586  add     rdx, [rbp+arg_8]; Src
0x18004658a  call    memcpy_0
0x18004658f  mov     rax, [rbx]
0x180046592  mov     rcx, rbx
0x180046595  mov     edx, [r13+24h]
0x180046599  mov     rax, [rax+38h]
0x18004659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465a2  mov     esi, eax
0x1800465a4  test    eax, eax
0x1800465a6  js      short loc_180046605
0x1800465a8  mov     rax, [r14]
0x1800465ab  mov     rdx, rbx
0x1800465ae  mov     rcx, r14
0x1800465b1  mov     rax, [rax+78h]
0x1800465b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465ba  mov     esi, eax
0x1800465bc  test    eax, eax
0x1800465be  js      short loc_1800465F5
0x1800465c0  mov     ebx, [r13+24h]
0x1800465c4  add     ebx, r15d
0x1800465c7  cmp     ebx, r15d
0x1800465ca  jb      short loc_1800465E0
0x1800465cc  lea     rcx, [rbp+arg_0]
0x1800465d0  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800465d5  mov     r13, [rbp+arg_8]
0x1800465d9  xor     esi, esi
0x1800465db  jmp     loc_1800464D5
0x1800465e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800465e5  mov     esi, 80070216h
0x1800465ea  cmp     al, 1
0x1800465ec  jb      short loc_180046666
0x1800465ee  mov     edx, 34h ; '4'
0x1800465f3  jmp     short loc_180046648
0x1800465f5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800465fa  cmp     al, 1
0x1800465fc  jb      short loc_180046666
0x1800465fe  mov     edx, 33h ; '3'
0x180046603  jmp     short loc_180046648
0x180046605  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004660a  cmp     al, 1
0x18004660c  jb      short loc_180046666
0x18004660e  mov     edx, 32h ; '2'
0x180046613  jmp     short loc_180046648
0x180046615  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004661a  cmp     al, 1
0x18004661c  jb      short loc_180046666
0x18004661e  mov     edx, 31h ; '1'
0x180046623  jmp     short loc_180046648
0x180046625  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004662a  cmp     al, 1
0x18004662c  jb      short loc_180046666
0x18004662e  mov     edx, 30h ; '0'
0x180046633  jmp     short loc_180046648
0x180046635  mov     esi, 80070216h
0x18004663a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004663f  cmp     al, 1
0x180046641  jb      short loc_180046666
0x180046643  mov     edx, 2Fh ; '/'
0x180046648  mov     rcx, cs:WPP_GLOBAL_Control
0x18004664f  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x180046656  mov     r9, r14
0x180046659  mov     dword ptr [rsp+30h+var_10], esi
0x18004665d  mov     rcx, [rcx+10h]
0x180046661  call    WPP_SF_qD
0x180046666  lea     rcx, [rbp+arg_0]
0x18004666a  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004666f  jmp     short loc_1800466A2
0x180046671  mov     esi, 80070057h
0x180046676  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004667b  cmp     al, 1
0x18004667d  jb      short loc_1800466A2
0x18004667f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046686  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x18004668d  mov     edx, 2Eh ; '.'
0x180046692  mov     dword ptr [rsp+30h+var_10], esi
0x180046696  mov     r9, r14
0x180046699  mov     rcx, [rcx+10h]
0x18004669d  call    WPP_SF_qD
0x1800466a2  lea     rcx, [r14+10h]; lpCriticalSection
0x1800466a6  call    cs:__imp_LeaveCriticalSection
0x1800466ac  mov     rbx, [rsp+30h+arg_10]
0x1800466b4  mov     eax, esi
0x1800466b6  add     rsp, 30h
0x1800466ba  pop     r15
0x1800466bc  pop     r14
0x1800466be  pop     r13
0x1800466c0  pop     r12
0x1800466c2  pop     rdi
0x1800466c3  pop     rsi
0x1800466c4  pop     rbp
0x1800466c5  retn
```
