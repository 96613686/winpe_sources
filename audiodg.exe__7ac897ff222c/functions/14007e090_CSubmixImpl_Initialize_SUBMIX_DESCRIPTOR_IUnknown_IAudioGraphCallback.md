# CSubmixImpl::Initialize(SUBMIX_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *)

- ea: `0x14007e090`
- end: `0x14007e371`
- name: `?Initialize@CSubmixImpl@@UEAAJPEAUSUBMIX_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@@Z`
- size: `737`
- prototype: `int(CSubmixImpl *__hidden this, struct SUBMIX_DESCRIPTOR *, struct IUnknown *, struct IAudioGraphCallback *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007c060`
- `0x14007d5f0`

## callees

- `0x14000a378`
- `0x14000c33c`
- `0x14000c360`
- `0x14001af2c`
- `0x14001d630`
- `0x14001d790`
- `0x14001d854`
- `0x14001efb4`
- `0x14002427c`
- `0x140031a68`
- `0x140036aa0`
- `0x14004dbf8`
- `0x14005e150`
- `0x14007e090`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007e359`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007e359`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007e2dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007e2dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007e13a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007e183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007e13a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007e183`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSubmixImpl::Initialize(
        CSubmixImpl *this,
        struct SUBMIX_DESCRIPTOR *a2,
        struct IUnknown *a3,
        struct IAudioGraphCallback *a4)
{
  int DeviceGraphObjectCache; // ebx
  __int64 v9; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  const struct tWAVEFORMATEX **v13; // r15
  LPVOID v14; // rax
  void **v15; // rbx
  LPVOID v16; // rax
  __int64 v17; // rcx
  CPipeInstance **v18; // rbx
  int SubmixPipeInstance; // edi
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rax
  ATL::CAtlException *v24; // rbx
  int v25; // [rsp+20h] [rbp-78h]
  char *v26[2]; // [rsp+30h] [rbp-68h] BYREF
  ATL::CAtlException *v27; // [rsp+40h] [rbp-58h] BYREF
  char *v28; // [rsp+48h] [rbp-50h] BYREF
  struct tWAVEFORMATEX *v29; // [rsp+50h] [rbp-48h] BYREF
  char v30; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  DeviceGraphObjectCache = ValidateSubmixDescriptor(a2);
  if ( DeviceGraphObjectCache < 0 )
  {
    v9 = 248;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
      (const char *)(unsigned int)DeviceGraphObjectCache,
      v25);
    return (unsigned int)DeviceGraphObjectCache;
  }
  *((_QWORD *)this + 29) = *((_QWORD *)a2 + 7);
  *((_OWORD *)this + 15) = *(_OWORD *)((char *)a2 + 68);
  *((_DWORD *)this + 64) = *(_DWORD *)a2;
  *((_BYTE *)this + 16) = *((_BYTE *)a2 + 12);
  *((_BYTE *)this + 313) = *((_BYTE *)a2 + 13);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)this + 8,
    0);
  DeviceGraphObjectCache = _AllocString<CTCoAllocPolicy>(v12, v11, *((_QWORD *)a2 + 4), (char *)this + 8);
  if ( DeviceGraphObjectCache < 0 )
  {
    v9 = 256;
    goto LABEL_3;
  }
  v13 = (const struct tWAVEFORMATEX **)((char *)this + 216);
  v14 = CoTaskMemAlloc(*((unsigned int *)a2 + 10));
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    (char *)this + 216,
    v14);
  if ( !*((_QWORD *)this + 27) )
  {
    DeviceGraphObjectCache = -2147024882;
    v9 = 259;
    goto LABEL_3;
  }
  memcpy_0(*((void **)this + 27), *((const void **)a2 + 6), *((unsigned int *)a2 + 10));
  v15 = (void **)((char *)this + 224);
  if ( *((_DWORD *)a2 + 4) )
  {
    v16 = CoTaskMemAlloc(*((unsigned int *)a2 + 4));
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      (char *)this + 224,
      v16);
    if ( !*v15 )
    {
      DeviceGraphObjectCache = -2147024882;
      v9 = 265;
      goto LABEL_3;
    }
    memcpy_0(*v15, *((const void **)a2 + 3), *((unsigned int *)a2 + 4));
  }
  else
  {
    v28 = (char *)this + 224;
    v29 = 0;
    v30 = 1;
    DeviceGraphObjectCache = CloneWaveFormat(*v13, &v29);
    wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v28);
    if ( DeviceGraphObjectCache < 0 )
    {
      v9 = 271;
      goto LABEL_3;
    }
  }
  if ( *((_BYTE *)this + 313) )
    goto LABEL_28;
  v17 = *((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  DeviceGraphObjectCache = GetDeviceGraphObjectCache(
                             a3,
                             *((const unsigned __int16 **)a2 + 4),
                             *((_QWORD *)a2 + 7),
                             *((unsigned __int8 *)a2 + 12),
                             (struct tWAVEFORMATEX *)*v13,
                             (struct IDeviceGraphObjectCache **)this + 33);
  if ( DeviceGraphObjectCache < 0 )
  {
    v9 = 277;
    goto LABEL_3;
  }
  if ( !*((_BYTE *)a2 + 84) )
    goto LABEL_28;
  v18 = (CPipeInstance **)((char *)this + 24);
  SubmixPipeInstance = CPipeInstance::CreateSubmixPipeInstance(
                         *((struct IDeviceGraphObjectCache **)this + 33),
                         a2,
                         (struct CPipeInstance **)this + 3);
  if ( SubmixPipeInstance >= 0 )
  {
    SubmixPipeInstance = CPipeInstance::Initialize(*v18);
    if ( SubmixPipeInstance < 0 )
    {
      v20 = 284;
      goto LABEL_22;
    }
    SubmixPipeInstance = CPipeInstance::ConnectAPOs(*v18, a4);
    if ( SubmixPipeInstance < 0 )
    {
      v20 = 285;
      goto LABEL_22;
    }
    *((_DWORD *)this + 79) = *((_DWORD *)*v18 + 36);
LABEL_28:
    EnterCriticalSection(&g_CritSecSubmixList);
    v26[1] = (char *)&g_CritSecSubmixList;
    try
    {
      v26[0] = (char *)this;
      v23 = ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::NewNode(v21, v26, v22, SubmixList);
      if ( SubmixList )
        *(_QWORD *)(SubmixList + 8) = v23;
      else
        qword_1400E7BA8 = v23;
      SubmixList = v23;
    }
    catch ( ATL::CAtlException *v27 )
    {
      v24 = v27;
      if ( *(_DWORD *)v27 == -1073741571 )
        _o__resetstkoflw();
      LODWORD(v26[0]) = *(_DWORD *)v24;
      SubmixPipeInstance = (int)v26[0];
      if ( SLODWORD(v26[0]) < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
          (const char *)LODWORD(v26[0]),
          v25);
LABEL_36:
        LeaveCriticalSection(&g_CritSecSubmixList);
        return (unsigned int)SubmixPipeInstance;
      }
    }
    SubmixPipeInstance = 0;
    goto LABEL_36;
  }
  v20 = 283;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\submix.cpp",
    (const char *)(unsigned int)SubmixPipeInstance,
    v25);
  return (unsigned int)SubmixPipeInstance;
}

```

## disassembly

```asm
0x14007e090  push    rbx
0x14007e092  push    rsi
0x14007e093  push    rdi
0x14007e094  push    r12
0x14007e096  push    r13
0x14007e098  push    r14
0x14007e09a  push    r15
0x14007e09c  sub     rsp, 60h
0x14007e0a0  mov     r12, r9
0x14007e0a3  mov     r13, r8
0x14007e0a6  mov     rdi, rdx
0x14007e0a9  mov     rsi, rcx
0x14007e0ac  mov     rcx, rdx; struct SUBMIX_DESCRIPTOR *
0x14007e0af  call    ?ValidateSubmixDescriptor@@YAJPEAUSUBMIX_DESCRIPTOR@@@Z; ValidateSubmixDescriptor(SUBMIX_DESCRIPTOR *)
0x14007e0b4  mov     ebx, eax
0x14007e0b6  test    eax, eax
0x14007e0b8  jns     short loc_14007E0DD
0x14007e0ba  mov     edx, 0F8h; void *
0x14007e0bf  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007e0c6  mov     r9d, ebx; char *
0x14007e0c9  mov     rcx, [rsp+98h]; this
0x14007e0d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e0d6  mov     eax, ebx
0x14007e0d8  jmp     loc_14007E361
0x14007e0dd  mov     rax, [rdi+38h]
0x14007e0e1  mov     [rsi+0E8h], rax
0x14007e0e8  movups  xmm0, xmmword ptr [rdi+44h]
0x14007e0ec  movdqu  xmmword ptr [rsi+0F0h], xmm0
0x14007e0f4  mov     eax, [rdi]
0x14007e0f6  mov     [rsi+100h], eax
0x14007e0fc  mov     al, [rdi+0Ch]
0x14007e0ff  mov     [rsi+10h], al
0x14007e102  mov     al, [rdi+0Dh]
0x14007e105  mov     [rsi+139h], al
0x14007e10b  xor     edx, edx
0x14007e10d  lea     rcx, [rsi+8]
0x14007e111  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14007e116  lea     r9, [rsi+8]
0x14007e11a  mov     r8, [rdi+20h]
0x14007e11e  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x14007e123  mov     ebx, eax
0x14007e125  test    eax, eax
0x14007e127  jns     short loc_14007E130
0x14007e129  mov     edx, 100h
0x14007e12e  jmp     short loc_14007E0BF
0x14007e130  lea     r15, [rsi+0D8h]
0x14007e137  mov     ecx, [rdi+28h]; cb
0x14007e13a  call    cs:__imp_CoTaskMemAlloc
0x14007e140  mov     rdx, rax
0x14007e143  mov     rcx, r15
0x14007e146  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007e14b  mov     rcx, [r15]; void *
0x14007e14e  test    rcx, rcx
0x14007e151  jnz     short loc_14007E162
0x14007e153  mov     ebx, 8007000Eh
0x14007e158  mov     edx, 103h
0x14007e15d  jmp     loc_14007E0BF
0x14007e162  mov     r8d, [rdi+28h]; Size
0x14007e166  mov     rdx, [rdi+30h]; Src
0x14007e16a  call    memcpy_0
0x14007e16f  lea     rbx, [rsi+0E0h]
0x14007e176  cmp     dword ptr [rdi+10h], 0
0x14007e17a  jbe     loc_14007E21A
0x14007e180  mov     ecx, [rdi+10h]; cb
0x14007e183  call    cs:__imp_CoTaskMemAlloc
0x14007e189  mov     rdx, rax
0x14007e18c  mov     rcx, rbx
0x14007e18f  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14007e194  mov     rcx, [rbx]; void *
0x14007e197  test    rcx, rcx
0x14007e19a  jnz     short loc_14007E1AB
0x14007e19c  mov     ebx, 8007000Eh
0x14007e1a1  mov     edx, 109h
0x14007e1a6  jmp     loc_14007E0BF
0x14007e1ab  mov     r8d, [rdi+10h]; Size
0x14007e1af  mov     rdx, [rdi+18h]; Src
0x14007e1b3  call    memcpy_0
0x14007e1b8  cmp     byte ptr [rsi+139h], 0
0x14007e1bf  jnz     loc_14007E2D3
0x14007e1c5  lea     r14, [rsi+108h]
0x14007e1cc  mov     rcx, [r14]
0x14007e1cf  mov     qword ptr [r14], 0
0x14007e1d6  test    rcx, rcx
0x14007e1d9  jz      short loc_14007E1E8
0x14007e1db  mov     rax, [rcx]
0x14007e1de  mov     rax, [rax+10h]
0x14007e1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e1e7  nop
0x14007e1e8  movzx   r9d, byte ptr [rdi+0Ch]; int
0x14007e1ed  mov     [rsp+98h+var_70], r14; struct IDeviceGraphObjectCache **
0x14007e1f2  mov     rax, [r15]
0x14007e1f5  mov     [rsp+98h+var_78], rax; int
0x14007e1fa  mov     r8, [rdi+38h]; __int64
0x14007e1fe  mov     rdx, [rdi+20h]; unsigned __int16 *
0x14007e202  mov     rcx, r13; struct IUnknown *
0x14007e205  call    ?GetDeviceGraphObjectCache@@YAJPEAUIUnknown@@PEBG_JHPEAUtWAVEFORMATEX@@PEAPEAUIDeviceGraphObjectCache@@@Z; GetDeviceGraphObjectCache(IUnknown *,ushort const *,__int64,int,tWAVEFORMATEX *,IDeviceGraphObjectCache * *)
0x14007e20a  mov     ebx, eax
0x14007e20c  test    eax, eax
0x14007e20e  jns     short loc_14007E258
0x14007e210  mov     edx, 115h
0x14007e215  jmp     loc_14007E0BF
0x14007e21a  mov     [rsp+98h+var_50], rbx
0x14007e21f  mov     [rsp+98h+var_48], 0
0x14007e228  mov     [rsp+98h+var_40], 1
0x14007e22d  lea     rdx, [rsp+98h+var_48]; struct tWAVEFORMATEX **
0x14007e232  mov     rcx, [r15]; Src
0x14007e235  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x14007e23a  mov     ebx, eax
0x14007e23c  lea     rcx, [rsp+98h+var_50]
0x14007e241  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14007e246  test    ebx, ebx
0x14007e248  jns     loc_14007E1B8
0x14007e24e  mov     edx, 10Fh
0x14007e253  jmp     loc_14007E0BF
0x14007e258  cmp     byte ptr [rdi+54h], 0
0x14007e25c  jz      short loc_14007E2D3
0x14007e25e  lea     rbx, [rsi+18h]
0x14007e262  mov     r8, rbx; struct CPipeInstance **
0x14007e265  mov     rdx, rdi; struct SUBMIX_DESCRIPTOR *
0x14007e268  mov     rcx, [r14]; struct IDeviceGraphObjectCache *
0x14007e26b  call    ?CreateSubmixPipeInstance@CPipeInstance@@SAJPEAUIDeviceGraphObjectCache@@PEAUSUBMIX_DESCRIPTOR@@PEAPEAV1@@Z; CPipeInstance::CreateSubmixPipeInstance(IDeviceGraphObjectCache *,SUBMIX_DESCRIPTOR *,CPipeInstance * *)
0x14007e270  mov     edi, eax
0x14007e272  test    eax, eax
0x14007e274  jns     short loc_14007E297
0x14007e276  mov     edx, 11Bh; void *
0x14007e27b  mov     rcx, [rsp+98h]; this
0x14007e283  mov     r9d, edi; char *
0x14007e286  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007e28d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e292  jmp     loc_14007E35F
0x14007e297  mov     rcx, [rbx]; this
0x14007e29a  call    ?Initialize@CPipeInstance@@QEAAJXZ; CPipeInstance::Initialize(void)
0x14007e29f  mov     edi, eax
0x14007e2a1  test    eax, eax
0x14007e2a3  jns     short loc_14007E2AC
0x14007e2a5  mov     edx, 11Ch
0x14007e2aa  jmp     short loc_14007E27B
0x14007e2ac  mov     rdx, r12; struct IAudioGraphCallback *
0x14007e2af  mov     rcx, [rbx]; this
0x14007e2b2  call    ?ConnectAPOs@CPipeInstance@@QEAAJPEAUIAudioGraphCallback@@@Z; CPipeInstance::ConnectAPOs(IAudioGraphCallback *)
0x14007e2b7  mov     edi, eax
0x14007e2b9  test    eax, eax
0x14007e2bb  jns     short loc_14007E2C4
0x14007e2bd  mov     edx, 11Dh
0x14007e2c2  jmp     short loc_14007E27B
0x14007e2c4  mov     rax, [rbx]
0x14007e2c7  mov     ecx, [rax+90h]
0x14007e2cd  mov     [rsi+13Ch], ecx
0x14007e2d3  lea     rbx, ?g_CritSecSubmixList@@3Vcritical_section@wil@@A; wil::critical_section g_CritSecSubmixList
0x14007e2da  mov     rcx, rbx; lpCriticalSection
0x14007e2dd  call    cs:__imp_EnterCriticalSection
0x14007e2e3  mov     [rsp+98h+var_60], rbx
0x14007e2e8  mov     [rsp+98h+var_68], rsi
0x14007e2ed  mov     r9, cs:?SubmixList@@3V?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@A; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>> SubmixList
0x14007e2f4  lea     rdx, [rsp+98h+var_68]
0x14007e2f9  call    ?NewNode@?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVCSubmixImpl@@PEAV312@1@Z; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::NewNode(CSubmixImpl * const &,ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::CNode *,ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>>::CNode *)
0x14007e2fe  mov     rcx, cs:?SubmixList@@3V?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@A; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>> SubmixList
0x14007e305  test    rcx, rcx
0x14007e308  jz      short loc_14007E310
0x14007e30a  mov     [rcx+8], rax
0x14007e30e  jmp     short loc_14007E317
0x14007e310  mov     cs:qword_1400E7BA8, rax
0x14007e317  mov     cs:?SubmixList@@3V?$CAtlList@PEAVCSubmixImpl@@V?$CElementTraits@PEAVCSubmixImpl@@@ATL@@@ATL@@A, rax; ATL::CAtlList<CSubmixImpl *,ATL::CElementTraits<CSubmixImpl *>> SubmixList
0x14007e31e  jmp     short loc_14007E354
0x14007e320  mov     edi, dword ptr [rsp+98h+var_68]
0x14007e324  test    edi, edi
0x14007e326  jns     short loc_14007E34D
0x14007e328  mov     rcx, [rsp+98h]; this
0x14007e330  mov     r9d, edi; char *
0x14007e333  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14007e33a  mov     edx, 128h; void *
0x14007e33f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007e344  lea     rbx, ?g_CritSecSubmixList@@3Vcritical_section@wil@@A; wil::critical_section g_CritSecSubmixList
0x14007e34b  jmp     short loc_14007E356
0x14007e34d  lea     rbx, ?g_CritSecSubmixList@@3Vcritical_section@wil@@A; wil::critical_section g_CritSecSubmixList
0x14007e354  xor     edi, edi
0x14007e356  mov     rcx, rbx; lpCriticalSection
0x14007e359  call    cs:__imp_LeaveCriticalSection
0x14007e35f  mov     eax, edi
0x14007e361  add     rsp, 60h
0x14007e365  pop     r15
0x14007e367  pop     r14
0x14007e369  pop     r13
0x14007e36b  pop     r12
0x14007e36d  pop     rdi
0x14007e36e  pop     rsi
0x14007e36f  pop     rbx
0x14007e370  retn
```
