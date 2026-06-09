# Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(ushort const *,ushort const *,Microsoft::Resources::Runtime::_SetQualifierFlags)

- ea: `0x180045d4c`
- end: `0x180045f3e`
- name: `?UpdateQualifierIfChanged@CQualifierEvent@Core@Resources@ApplicationModel@Windows@@QEAAJPEBG0W4_SetQualifierFlags@Runtime@3Microsoft@@@Z`
- size: `498`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043c2c`
- `0x180043e50`
- `0x180065c40`
- `0x180078020`
- `0x1800b1de0`
- `0x1800b5a60`

## callees

- `0x1800218b4`
- `0x18002c8d0`
- `0x180045d4c`
- `0x180045f44`
- `0x18004619c`
- `0x180046d08`
- `0x180046d70`
- `0x180046f58`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045e17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045e4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045e4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045e8b`

## string_xrefs

- `0x180045e76`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180045ea6`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180045ebe`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180045f1e`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(
        RTL_SRWLOCK *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-49h]
  RTL_SRWLOCK *v15; // [rsp+30h] [rbp-39h] BYREF
  char v16; // [rsp+38h] [rbp-31h]
  _BYTE v17[16]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v18[14]; // [rsp+50h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  bool v20; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( (a4 & 0x10) != 0 )
  {
    v15 = 0;
    if ( (*(int (__fastcall **)(_QWORD, const unsigned __int16 *, RTL_SRWLOCK **))(**((_QWORD **)a1->Ptr + 4) + 112LL))(
           *((_QWORD *)a1->Ptr + 4),
           a2,
           &v15) < 0
      || !(*((unsigned __int8 (__fastcall **)(RTL_SRWLOCK *))v15->Ptr + 2))(v15) )
    {
      v8 = -2147024891;
      v13 = 1063;
      goto LABEL_16;
    }
  }
  v20 = 0;
  v8 = Microsoft::Resources::Runtime::CContext::CheckIfQualifierValueUpdateIsAllowedAndRequired(
         (Microsoft::Resources::Runtime::CContext *)a1->Ptr,
         a2,
         a3,
         (a4 & 8) != 0,
         &v20);
  if ( (v8 & 0x80000000) != 0 )
  {
    v13 = 1069;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
      (const char *)v8,
      v14);
    return v8;
  }
  if ( !v20 )
    return 0;
  v18[0] = &Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::`vftable';
  v18[1] = 0;
  v18[2] = 0;
  v18[4] = 0;
  v18[6] = 0;
  v18[3] = Microsoft::Resources::CompareGenericType<Microsoft::Resources::Build::PriFileMerger::PriFileInfo const *>;
  v9 = Microsoft::Resources::Runtime::CContext::SetAttributeValue(a1->Ptr, a2, a3, a4);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x432,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
      (const char *)(unsigned int)v9,
      v14);
  }
  else
  {
    if ( (a4 & 0x40) != 0 )
    {
LABEL_9:
      Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::~DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>(v18);
      return 0;
    }
    v15 = a1 + 2;
    v16 = 1;
    AcquireSRWLockShared(a1 + 2);
    v10 = Windows::ApplicationModel::Resources::Core::CInvokerHandler::Set(v17, a2, a3, &a1[3]);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x438,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
        (const char *)(unsigned int)v10,
        v14);
      ReleaseSRWLockShared(a1 + 2);
    }
    else
    {
      v11 = Windows::ApplicationModel::Resources::Core::CInvokerHandler::Invoke((Windows::ApplicationModel::Resources::Core::CInvokerHandler *)v17);
      v8 = v11;
      if ( v11 >= 0 )
      {
        ReleaseSRWLockShared(a1 + 2);
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43A,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
        (const char *)(unsigned int)v11,
        v14);
      Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock((Microsoft::Resources::AutoReaderWriterLock *)&v15);
    }
  }
  Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::~DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>(v18);
  return v8;
}

```

## disassembly

```asm
0x180045d4c  push    rbp
0x180045d4e  push    rbx
0x180045d4f  push    rsi
0x180045d50  push    rdi
0x180045d51  push    r14
0x180045d53  push    r15
0x180045d55  lea     rbp, [rsp-2Fh]
0x180045d5a  sub     rsp, 98h
0x180045d61  mov     edi, r9d
0x180045d64  mov     r15, r8
0x180045d67  mov     r14, rdx
0x180045d6a  mov     rsi, rcx
0x180045d6d  test    r9b, 10h
0x180045d71  jnz     loc_180045ED3
0x180045d77  mov     [rbp+57h+arg_18], 0
0x180045d7b  mov     r9d, edi
0x180045d7e  shr     r9d, 3
0x180045d82  and     r9b, 1; bool
0x180045d86  lea     rax, [rbp+57h+arg_18]
0x180045d8a  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180045d8f  mov     r8, r15; unsigned __int16 *
0x180045d92  mov     rdx, r14; unsigned __int16 *
0x180045d95  mov     rcx, [rsi]; this
0x180045d98  call    ?CheckIfQualifierValueUpdateIsAllowedAndRequired@CContext@Runtime@Resources@Microsoft@@QEBAJPEBG0_NPEA_N@Z; Microsoft::Resources::Runtime::CContext::CheckIfQualifierValueUpdateIsAllowedAndRequired(ushort const *,ushort const *,bool,bool *)
0x180045d9d  mov     ebx, eax
0x180045d9f  test    eax, eax
0x180045da1  js      loc_180045EB9
0x180045da7  cmp     [rbp+57h+arg_18], 0
0x180045dab  jz      loc_180045E5D
0x180045db1  lea     rax, ??_7?$DefList@PEAVCResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@P6AHPEBX0@ZP6A_N0PEAH@Z@Resources@Microsoft@@6B@; const Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::`vftable'
0x180045db8  mov     [rbp+57h+var_70], rax
0x180045dbc  mov     [rbp+57h+var_68], 0
0x180045dc4  mov     [rbp+57h+var_60], 0
0x180045dcc  mov     [rbp+57h+var_50], 0
0x180045dd4  mov     [rbp+57h+var_40], 0
0x180045ddc  lea     rax, ??$CompareGenericType@PEBVPriFileInfo@PriFileMerger@Build@Resources@Microsoft@@@Resources@Microsoft@@YAHPEBX0@Z; Microsoft::Resources::CompareGenericType<Microsoft::Resources::Build::PriFileMerger::PriFileInfo const *>(void const *,void const *)
0x180045de3  mov     [rbp+57h+var_58], rax
0x180045de7  mov     r9d, edi
0x180045dea  mov     r8, r15
0x180045ded  mov     rdx, r14
0x180045df0  mov     rcx, [rsi]
0x180045df3  call    ?SetAttributeValue@CContext@Runtime@Resources@Microsoft@@QEAAJPEBG0W4_SetQualifierFlags@234@@Z; Microsoft::Resources::Runtime::CContext::SetAttributeValue(ushort const *,ushort const *,Microsoft::Resources::Runtime::_SetQualifierFlags)
0x180045df8  mov     ebx, eax
0x180045dfa  test    eax, eax
0x180045dfc  js      loc_180045E9F
0x180045e02  test    dil, 40h
0x180045e06  jnz     short loc_180045E54
0x180045e08  lea     rdi, [rsi+10h]
0x180045e0c  mov     [rbp+57h+var_90], rdi
0x180045e10  mov     [rbp+57h+var_88], 1
0x180045e14  mov     rcx, rdi; SRWLock
0x180045e17  call    cs:__imp_AcquireSRWLockShared
0x180045e1d  nop
0x180045e1e  lea     r9, [rsi+18h]
0x180045e22  mov     r8, r15
0x180045e25  mov     rdx, r14
0x180045e28  lea     rcx, [rbp+57h+var_80]
0x180045e2c  call    ?Set@CInvokerHandler@Core@Resources@ApplicationModel@Windows@@QEAAJPEBG0PEAV?$DefList@PEAVCResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@P6AHPEBX0@ZP6A_N0PEAH@Z@3Microsoft@@@Z; Windows::ApplicationModel::Resources::Core::CInvokerHandler::Set(ushort const *,ushort const *,Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)> *)
0x180045e31  mov     ebx, eax
0x180045e33  test    eax, eax
0x180045e35  js      short loc_180045E6F
0x180045e37  lea     rcx, [rbp+57h+var_80]; this
0x180045e3b  call    ?Invoke@CInvokerHandler@Core@Resources@ApplicationModel@Windows@@QEAAJXZ; Windows::ApplicationModel::Resources::Core::CInvokerHandler::Invoke(void)
0x180045e40  mov     ebx, eax
0x180045e42  test    eax, eax
0x180045e44  js      loc_180045F17
0x180045e4a  mov     rcx, rdi; SRWLock
0x180045e4d  call    cs:__imp_ReleaseSRWLockShared
0x180045e53  nop
0x180045e54  lea     rcx, [rbp+57h+var_70]
0x180045e58  call    ??1?$DefList@PEAVCResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@P6AHPEBX0@ZP6A_N0PEAH@Z@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::~DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>(void)
0x180045e5d  xor     eax, eax
0x180045e5f  add     rsp, 98h
0x180045e66  pop     r15
0x180045e68  pop     r14
0x180045e6a  pop     rdi
0x180045e6b  pop     rsi
0x180045e6c  pop     rbx
0x180045e6d  pop     rbp
0x180045e6e  retn
0x180045e6f  mov     rcx, [rbp+5Fh]; this
0x180045e73  mov     r9d, eax; char *
0x180045e76  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180045e7d  mov     edx, 438h; void *
0x180045e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045e87  nop
0x180045e88  mov     rcx, rdi; SRWLock
0x180045e8b  call    cs:__imp_ReleaseSRWLockShared
0x180045e91  nop
0x180045e92  lea     rcx, [rbp+57h+var_70]
0x180045e96  call    ??1?$DefList@PEAVCResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@P6AHPEBX0@ZP6A_N0PEAH@Z@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>::~DefList<Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *,int (*)(void const *,void const *),bool (*)(void const *,int *)>(void)
0x180045e9b  mov     eax, ebx
0x180045e9d  jmp     short loc_180045E5F
0x180045e9f  mov     rcx, [rbp+5Fh]; this
0x180045ea3  mov     r9d, eax; char *
0x180045ea6  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180045ead  mov     edx, 432h; void *
0x180045eb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045eb7  jmp     short loc_180045E92
0x180045eb9  mov     edx, 42Dh; void *
0x180045ebe  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180045ec5  mov     r9d, ebx; char *
0x180045ec8  mov     rcx, [rbp+5Fh]; this
0x180045ecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045ed1  jmp     short loc_180045E9B
0x180045ed3  mov     [rbp+57h+var_90], 0
0x180045edb  mov     rax, [rcx]
0x180045ede  mov     rcx, [rax+20h]
0x180045ee2  mov     rax, [rcx]
0x180045ee5  lea     r8, [rbp+57h+var_90]
0x180045ee9  mov     rax, [rax+70h]
0x180045eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ef2  test    eax, eax
0x180045ef4  js      loc_1800C2BFA
0x180045efa  mov     rcx, [rbp+57h+var_90]
0x180045efe  mov     rax, [rcx]
0x180045f01  mov     rax, [rax+10h]
0x180045f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f0a  test    al, al
0x180045f0c  jnz     loc_180045D77
0x180045f12  jmp     loc_1800C2BFA
0x180045f17  mov     rcx, [rbp+5Fh]; this
0x180045f1b  mov     r9d, eax; char *
0x180045f1e  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180045f25  mov     edx, 43Ah; void *
0x180045f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f2f  nop
0x180045f30  lea     rcx, [rbp+57h+var_90]; this
0x180045f34  call    ??1AutoReaderWriterLock@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock(void)
0x180045f39  jmp     loc_180045E92
0x1800c2bfa  mov     ebx, 80070005h
0x1800c2bff  mov     edx, 427h
0x1800c2c04  jmp     loc_180045EBE
```
