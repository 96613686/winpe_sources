# CStreamInstance::CreateBridgeStreamToTargetStreamGroup(BRIDGE_STREAM_DESCRIPTOR *,IUnknown *,IStreamGroup *,SYSTEM_AUDIO_STREAM *)

- ea: `0x14007d700`
- end: `0x14007daca`
- name: `?CreateBridgeStreamToTargetStreamGroup@CStreamInstance@@UEAAJPEAUBRIDGE_STREAM_DESCRIPTOR@@PEAUIUnknown@@PEAUIStreamGroup@@PEAUSYSTEM_AUDIO_STREAM@@@Z`
- size: `970`
- prototype: `int(CStreamInstance *__hidden this, struct BRIDGE_STREAM_DESCRIPTOR *, struct IUnknown *, struct IStreamGroup *, struct SYSTEM_AUDIO_STREAM *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000a378`
- `0x14000ad48`
- `0x14000c33c`
- `0x14001ae80`
- `0x14001af2c`
- `0x14001c9ac`
- `0x14001d854`
- `0x140033358`
- `0x14004dbf8`
- `0x14005e150`
- `0x14007ade4`
- `0x14007b7d0`
- `0x14007d700`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007d823`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007d91e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007da9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007d823`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007d91e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007da9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007d737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007d737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007d847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007d847`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStreamInstance::CreateBridgeStreamToTargetStreamGroup(
        CStreamInstance *this,
        struct BRIDGE_STREAM_DESCRIPTOR *a2,
        struct IUnknown *a3,
        struct IStreamGroup *a4,
        struct SYSTEM_AUDIO_STREAM *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, struct IAudioProcessingObject **); // r14
  struct IAudioProcessingObject *v14; // rcx
  int v15; // eax
  struct tWAVEFORMATEX *v16; // rbx
  LPVOID v17; // rax
  int DeviceGraphObjectCache; // eax
  struct CPipeInstance *v19; // r9
  unsigned int v20; // r14d
  int v21; // eax
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  CPipeInstance *v24; // r14
  struct IAudioProcessingObject *v25; // rbx
  CBridgeToAPOProcessNode **Head; // rax
  int BridgeToApo; // eax
  int v29; // [rsp+20h] [rbp-50h]
  int v30; // [rsp+20h] [rbp-50h]
  int v31; // [rsp+20h] [rbp-50h]
  int v32; // [rsp+20h] [rbp-50h]
  struct IDeviceGraphObjectCache **v33; // [rsp+28h] [rbp-48h]
  struct IDeviceGraphObjectCache *v34; // [rsp+50h] [rbp-20h] BYREF
  CPipeInstance *v35; // [rsp+58h] [rbp-18h] BYREF
  __int128 v36; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  struct IAudioProcessingObject *v38; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v39; // [rsp+A8h] [rbp+38h] BYREF

  v35 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *((_DWORD *)a5 + 236) = 0;
  if ( !a2 )
  {
    v11 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
      (const char *)v11,
      v29);
    goto LABEL_11;
  }
  v11 = ValidateAudioStreamDirection(*(unsigned int *)a2, v10);
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_4;
  v38 = 0;
  v39 = 0;
  (**(void (__fastcall ***)(struct IStreamGroup *, GUID *, __int64 *))a4)(
    a4,
    &GUID_78c8e80a_c79b_465b_be08_cd0c3ec0edda,
    &v39);
  v12 = v39;
  if ( v39 )
  {
    v13 = *(__int64 (__fastcall **)(__int64, struct IAudioProcessingObject **))(*(_QWORD *)v39 + 24LL);
    v14 = v38;
    v38 = 0;
    if ( v14 )
      ((void (__fastcall *)(struct IAudioProcessingObject *))v14->lpVtbl->Release)(v14);
    v15 = v13(v12, &v38);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23E,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        (const char *)(unsigned int)v15,
        v29);
LABEL_10:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
LABEL_11:
      if ( v9 )
        LeaveCriticalSection(v9);
      goto LABEL_39;
    }
  }
  if ( v38 )
  {
    v16 = 0;
    a5 = 0;
    if ( *((_DWORD *)a2 + 17) )
    {
      v17 = CoTaskMemAlloc(*((unsigned int *)a2 + 17));
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &a5,
        v17);
      v16 = (struct tWAVEFORMATEX *)a5;
      if ( !a5 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x247,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
          (const char *)0x8007000ELL,
          v29);
LABEL_17:
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &a5,
          0);
        goto LABEL_10;
      }
      memcpy_0(a5, *((const void **)a2 + 9), *((unsigned int *)a2 + 17));
    }
    v34 = 0;
    DeviceGraphObjectCache = GetDeviceGraphObjectCache(
                               a3,
                               *((const unsigned __int16 **)a2 + 7),
                               *((_QWORD *)a2 + 6),
                               *((_DWORD *)a2 + 2) == 1,
                               v16,
                               &v34);
    v20 = DeviceGraphObjectCache;
    if ( DeviceGraphObjectCache < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        (const char *)(unsigned int)DeviceGraphObjectCache,
        v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &a5,
        0);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
      if ( v9 )
        LeaveCriticalSection(v9);
      v11 = v20;
      goto LABEL_39;
    }
    v21 = CPipeInstance::CreateBridgeStreamPipeInstanceToTargetApo(
            v34,
            a2,
            v38,
            v19,
            v16,
            (struct SYSTEM_AUDIO_STREAM *)v33,
            &v35);
    v11 = v21;
    if ( v21 < 0 )
    {
      v22 = 597;
LABEL_25:
      v23 = (unsigned int)v21;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        (const char *)v23,
        v31);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
      goto LABEL_17;
    }
    v24 = v35;
    v21 = CPipeInstance::Initialize(v35);
    v11 = v21;
    if ( v21 < 0 )
    {
      v22 = 599;
      goto LABEL_25;
    }
    v21 = CPipeInstance::ConnectAPOs(v24, 0);
    v11 = v21;
    if ( v21 < 0 )
    {
      v22 = 600;
      goto LABEL_25;
    }
    v25 = v38;
    Head = (CBridgeToAPOProcessNode **)ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead((char *)v24 + 16);
    BridgeToApo = CBridgeToAPOProcessNode::CreateBridgeToApo(
                    *Head,
                    *((struct IDeviceGraphObjectCache **)v24 + 30),
                    a2,
                    v25,
                    *((_DWORD *)v24 + 36));
    v11 = BridgeToApo;
    if ( BridgeToApo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48A,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\pipeinstance.cpp",
        (const char *)(unsigned int)BridgeToApo,
        v32);
      v23 = v11;
      v22 = 601;
      goto LABEL_26;
    }
    v36 = *((_OWORD *)a2 + 2);
    v31 = (int)v24;
    v21 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, CPipeInstance *))(*((_QWORD *)this - 1) + 144LL))(
            (char *)this - 8,
            0,
            *(unsigned int *)a2,
            v24);
    v11 = v21;
    if ( v21 < 0 )
    {
      v22 = 611;
      goto LABEL_25;
    }
    v35 = 0;
    *((_BYTE *)this + 256) = 1;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&a5, 0);
  }
  PublishDeviceGraphWnfState();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  if ( v9 )
    LeaveCriticalSection(v9);
  v11 = 0;
LABEL_39:
  ATL::CAutoPtr<CPipeInstance>::Free(&v35);
  return v11;
}

```

## disassembly

```asm
0x14007d700  mov     [rsp-28h+arg_10], rbx
0x14007d705  mov     [rsp-28h+arg_18], rsi
0x14007d70a  push    rbp
0x14007d70b  push    rdi
0x14007d70c  push    r12
0x14007d70e  push    r14
0x14007d710  push    r15
0x14007d712  mov     rbp, rsp
0x14007d715  sub     rsp, 70h
0x14007d719  mov     r14, r9
0x14007d71c  mov     r12, r8
0x14007d71f  mov     rsi, rdx
0x14007d722  mov     r15, rcx
0x14007d725  mov     [rbp+var_18], 0
0x14007d72d  lea     rdi, [rcx+0D8h]
0x14007d734  mov     rcx, rdi; lpCriticalSection
0x14007d737  call    cs:__imp_EnterCriticalSection
0x14007d73d  mov     rax, [rbp+arg_20]
0x14007d741  mov     dword ptr [rax+3B0h], 0
0x14007d74b  test    rsi, rsi
0x14007d74e  jnz     short loc_14007D757
0x14007d750  mov     ebx, 80004003h
0x14007d755  jmp     short loc_14007D764
0x14007d757  mov     ecx, [rsi]
0x14007d759  call    ?ValidateAudioStreamDirection@@YAJW4SYSTEM_AUDIO_STREAM_TYPE@@@Z; ValidateAudioStreamDirection(SYSTEM_AUDIO_STREAM_TYPE)
0x14007d75e  mov     ebx, eax
0x14007d760  test    eax, eax
0x14007d762  jns     short loc_14007D781
0x14007d764  mov     rcx, [rbp+28h]; this
0x14007d768  mov     r9d, ebx; char *
0x14007d76b  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d772  mov     edx, 236h; void *
0x14007d777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d77c  jmp     loc_14007D817
0x14007d781  mov     [rbp+arg_0], 0
0x14007d789  mov     [rbp+arg_8], 0
0x14007d791  mov     rax, [r14]
0x14007d794  lea     r8, [rbp+arg_8]
0x14007d798  lea     rdx, _GUID_78c8e80a_c79b_465b_be08_cd0c3ec0edda
0x14007d79f  mov     rcx, r14
0x14007d7a2  mov     rax, [rax]
0x14007d7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d7aa  mov     rbx, [rbp+arg_8]
0x14007d7ae  test    rbx, rbx
0x14007d7b1  jz      short loc_14007D82E
0x14007d7b3  mov     rax, [rbx]
0x14007d7b6  mov     r14, [rax+18h]
0x14007d7ba  mov     rcx, [rbp+arg_0]
0x14007d7be  mov     [rbp+arg_0], 0
0x14007d7c6  test    rcx, rcx
0x14007d7c9  jz      short loc_14007D7D8
0x14007d7cb  mov     rdx, [rcx]
0x14007d7ce  mov     rax, [rdx+10h]
0x14007d7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d7d7  nop
0x14007d7d8  lea     rdx, [rbp+arg_0]
0x14007d7dc  mov     rcx, rbx
0x14007d7df  mov     rax, r14
0x14007d7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d7e7  mov     ebx, eax
0x14007d7e9  test    eax, eax
0x14007d7eb  jns     short loc_14007D82E
0x14007d7ed  mov     rcx, [rbp+28h]; this
0x14007d7f1  mov     r9d, eax; char *
0x14007d7f4  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d7fb  mov     edx, 23Eh; void *
0x14007d800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d805  lea     rcx, [rbp+arg_8]
0x14007d809  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d80e  lea     rcx, [rbp+arg_0]
0x14007d812  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d817  test    rdi, rdi
0x14007d81a  jz      loc_14007DAA6
0x14007d820  mov     rcx, rdi; lpCriticalSection
0x14007d823  call    cs:__imp_LeaveCriticalSection
0x14007d829  jmp     loc_14007DAA6
0x14007d82e  cmp     [rbp+arg_0], 0
0x14007d833  jz      loc_14007DA7F
0x14007d839  xor     ebx, ebx
0x14007d83b  mov     [rbp+arg_20], rbx
0x14007d83f  cmp     [rsi+44h], ebx
0x14007d842  jbe     short loc_14007D8A0
0x14007d844  mov     ecx, [rsi+44h]; cb
0x14007d847  call    cs:__imp_CoTaskMemAlloc
0x14007d84d  mov     rdx, rax
0x14007d850  lea     rcx, [rbp+arg_20]
0x14007d854  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007d859  mov     rbx, [rbp+arg_20]
0x14007d85d  test    rbx, rbx
0x14007d860  jnz     short loc_14007D88F
0x14007d862  mov     rcx, [rbp+28h]; this
0x14007d866  mov     ebx, 8007000Eh
0x14007d86b  mov     r9d, ebx; char *
0x14007d86e  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d875  mov     edx, 247h; void *
0x14007d87a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d87f  xor     edx, edx
0x14007d881  lea     rcx, [rbp+arg_20]
0x14007d885  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007d88a  jmp     loc_14007D805
0x14007d88f  mov     r8d, [rsi+44h]; Size
0x14007d893  mov     rdx, [rsi+48h]; Src
0x14007d897  mov     rcx, rbx; void *
0x14007d89a  call    memcpy_0
0x14007d89f  nop
0x14007d8a0  mov     [rbp+var_20], 0
0x14007d8a8  xor     r9d, r9d
0x14007d8ab  cmp     dword ptr [rsi+8], 1
0x14007d8af  setz    r9b; int
0x14007d8b3  lea     rax, [rbp+var_20]
0x14007d8b7  mov     [rsp+70h+var_48], rax; struct SYSTEM_AUDIO_STREAM *
0x14007d8bc  mov     [rsp+70h+var_50], rbx; int
0x14007d8c1  mov     r8, [rsi+30h]; __int64
0x14007d8c5  mov     rdx, [rsi+38h]; unsigned __int16 *
0x14007d8c9  mov     rcx, r12; struct IUnknown *
0x14007d8cc  call    ?GetDeviceGraphObjectCache@@YAJPEAUIUnknown@@PEBG_JHPEAUtWAVEFORMATEX@@PEAPEAUIDeviceGraphObjectCache@@@Z; GetDeviceGraphObjectCache(IUnknown *,ushort const *,__int64,int,tWAVEFORMATEX *,IDeviceGraphObjectCache * *)
0x14007d8d1  mov     r14d, eax
0x14007d8d4  test    eax, eax
0x14007d8d6  jns     short loc_14007D92C
0x14007d8d8  mov     rcx, [rbp+28h]; this
0x14007d8dc  mov     r9d, eax; char *
0x14007d8df  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d8e6  mov     edx, 24Ch; void *
0x14007d8eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d8f0  lea     rcx, [rbp+var_20]
0x14007d8f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d8f9  xor     edx, edx
0x14007d8fb  lea     rcx, [rbp+arg_20]
0x14007d8ff  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007d904  lea     rcx, [rbp+arg_8]
0x14007d908  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d90d  lea     rcx, [rbp+arg_0]
0x14007d911  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d916  test    rdi, rdi
0x14007d919  jz      short loc_14007D924
0x14007d91b  mov     rcx, rdi; lpCriticalSection
0x14007d91e  call    cs:__imp_LeaveCriticalSection
0x14007d924  mov     ebx, r14d
0x14007d927  jmp     loc_14007DAA6
0x14007d92c  lea     rax, [rbp+var_18]
0x14007d930  mov     [rsp+70h+var_40], rax; struct CPipeInstance **
0x14007d935  mov     [rsp+70h+var_50], rbx; int
0x14007d93a  mov     r8, [rbp+arg_0]; struct IAudioProcessingObject *
0x14007d93e  mov     rdx, rsi; struct BRIDGE_STREAM_DESCRIPTOR *
0x14007d941  mov     rcx, [rbp+var_20]; struct IDeviceGraphObjectCache *
0x14007d945  call    ?CreateBridgeStreamPipeInstanceToTargetApo@CPipeInstance@@SAJPEAUIDeviceGraphObjectCache@@PEAUBRIDGE_STREAM_DESCRIPTOR@@PEAUIAudioProcessingObject@@PEAV1@PEAUtWAVEFORMATEX@@PEAUSYSTEM_AUDIO_STREAM@@PEAPEAV1@@Z; CPipeInstance::CreateBridgeStreamPipeInstanceToTargetApo(IDeviceGraphObjectCache *,BRIDGE_STREAM_DESCRIPTOR *,IAudioProcessingObject *,CPipeInstance *,tWAVEFORMATEX *,SYSTEM_AUDIO_STREAM *,CPipeInstance * *)
0x14007d94a  mov     ebx, eax
0x14007d94c  test    eax, eax
0x14007d94e  jns     short loc_14007D976
0x14007d950  mov     edx, 255h; void *
0x14007d955  mov     r9d, eax; char *
0x14007d958  mov     rcx, [rbp+28h]; this
0x14007d95c  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d963  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d968  lea     rcx, [rbp+var_20]
0x14007d96c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007d971  jmp     loc_14007D87F
0x14007d976  mov     r14, [rbp+var_18]
0x14007d97a  mov     rcx, r14; this
0x14007d97d  call    ?Initialize@CPipeInstance@@QEAAJXZ; CPipeInstance::Initialize(void)
0x14007d982  mov     ebx, eax
0x14007d984  test    eax, eax
0x14007d986  jns     short loc_14007D98F
0x14007d988  mov     edx, 257h
0x14007d98d  jmp     short loc_14007D955
0x14007d98f  xor     edx, edx; struct IAudioGraphCallback *
0x14007d991  mov     rcx, r14; this
0x14007d994  call    ?ConnectAPOs@CPipeInstance@@QEAAJPEAUIAudioGraphCallback@@@Z; CPipeInstance::ConnectAPOs(IAudioGraphCallback *)
0x14007d999  mov     ebx, eax
0x14007d99b  test    eax, eax
0x14007d99d  jns     short loc_14007D9A6
0x14007d99f  mov     edx, 258h
0x14007d9a4  jmp     short loc_14007D955
0x14007d9a6  mov     rbx, [rbp+arg_0]
0x14007d9aa  lea     rcx, [r14+10h]
0x14007d9ae  call    ?GetHead@?$CAtlList@PEAVCProcessNode@@V?$CElementTraits@PEAVCProcessNode@@@ATL@@@ATL@@QEAAAEAPEAVCProcessNode@@XZ; ATL::CAtlList<CProcessNode *,ATL::CElementTraits<CProcessNode *>>::GetHead(void)
0x14007d9b3  mov     ecx, [r14+90h]
0x14007d9ba  mov     dword ptr [rsp+70h+var_50], ecx; int
0x14007d9be  mov     r9, rbx; struct IAudioProcessingObject *
0x14007d9c1  mov     r8, rsi; struct BRIDGE_STREAM_DESCRIPTOR *
0x14007d9c4  mov     rdx, [r14+0F0h]; struct IDeviceGraphObjectCache *
0x14007d9cb  mov     rcx, [rax]; this
0x14007d9ce  call    ?CreateBridgeToApo@CBridgeToAPOProcessNode@@QEAAJPEAUIDeviceGraphObjectCache@@PEAUBRIDGE_STREAM_DESCRIPTOR@@PEAUIAudioProcessingObject@@I@Z; CBridgeToAPOProcessNode::CreateBridgeToApo(IDeviceGraphObjectCache *,BRIDGE_STREAM_DESCRIPTOR *,IAudioProcessingObject *,uint)
0x14007d9d3  mov     ebx, eax
0x14007d9d5  test    eax, eax
0x14007d9d7  jns     short loc_14007D9FE
0x14007d9d9  mov     rcx, [rbp+28h]; this
0x14007d9dd  mov     r9d, eax; char *
0x14007d9e0  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007d9e7  mov     edx, 48Ah; void *
0x14007d9ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d9f1  mov     r9d, ebx
0x14007d9f4  mov     edx, 259h
0x14007d9f9  jmp     loc_14007D958
0x14007d9fe  lea     rcx, [r15-8]
0x14007da02  movups  xmm0, xmmword ptr [rsi+20h]
0x14007da06  movdqu  [rbp+var_10], xmm0
0x14007da0b  mov     rax, [rcx]
0x14007da0e  mov     rdx, [rsi+18h]
0x14007da12  mov     [rsp+70h+var_30], rdx
0x14007da17  lea     rdx, [rbp+var_10]
0x14007da1b  mov     [rsp+70h+var_38], rdx
0x14007da20  mov     rdx, [rsi+30h]
0x14007da24  mov     [rsp+70h+var_40], rdx
0x14007da29  mov     [rsp+70h+var_48], 0
0x14007da32  mov     [rsp+70h+var_50], r14
0x14007da37  mov     r9, r14
0x14007da3a  mov     r8d, [rsi]
0x14007da3d  xor     edx, edx
0x14007da3f  mov     rax, [rax+90h]
0x14007da46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007da4b  mov     ebx, eax
0x14007da4d  test    eax, eax
0x14007da4f  jns     short loc_14007DA5B
0x14007da51  mov     edx, 263h
0x14007da56  jmp     loc_14007D955
0x14007da5b  mov     [rbp+var_18], 0
0x14007da63  mov     byte ptr [r15+100h], 1
0x14007da6b  lea     rcx, [rbp+var_20]
0x14007da6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007da74  xor     edx, edx
0x14007da76  lea     rcx, [rbp+arg_20]
0x14007da7a  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007da7f  call    ?PublishDeviceGraphWnfState@@YAXXZ; PublishDeviceGraphWnfState(void)
0x14007da84  lea     rcx, [rbp+arg_8]
0x14007da88  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007da8d  lea     rcx, [rbp+arg_0]
0x14007da91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007da96  test    rdi, rdi
0x14007da99  jz      short loc_14007DAA4
0x14007da9b  mov     rcx, rdi; lpCriticalSection
0x14007da9e  call    cs:__imp_LeaveCriticalSection
0x14007daa4  xor     ebx, ebx
0x14007daa6  lea     rcx, [rbp+var_18]
0x14007daaa  call    ?Free@?$CAutoPtr@VCPipeInstance@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CPipeInstance>::Free(void)
0x14007daaf  mov     eax, ebx
0x14007dab1  lea     r11, [rsp+70h+var_s0]
0x14007dab6  mov     rbx, [r11+40h]
0x14007daba  mov     rsi, [r11+48h]
0x14007dabe  mov     rsp, r11
0x14007dac1  pop     r15
0x14007dac3  pop     r14
0x14007dac5  pop     r12
0x14007dac7  pop     rdi
0x14007dac8  pop     rbp
0x14007dac9  retn
```
