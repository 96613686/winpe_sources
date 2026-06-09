# ipx::mtf::CMtfSuggestionClient::UpdateDataSource(_GUID const &,IMtfPropertyBag *)

- ea: `0x18001cae0`
- end: `0x18001cdb3`
- name: `?UpdateDataSource@CMtfSuggestionClient@mtf@ipx@@UEAAJAEBU_GUID@@PEAUIMtfPropertyBag@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, const struct _GUID *, struct IMtfPropertyBag *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180014014`
- `0x180014258`
- `0x180016a08`
- `0x180019a28`
- `0x18001b77c`
- `0x18001b8f4`
- `0x18001cae0`
- `0x18001d1f4`
- `0x18002bca0`
- `0x18002f010`

## string_xrefs

- `0x18001cb0a`: `UpdateDataSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UpdateDataSource(
        ipx::mtf::CMtfSuggestionClient *this,
        const struct _GUID *a2,
        struct IMtfPropertyBag *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  struct IMtfPropertyBag *v8; // rcx
  int v9; // eax
  struct IMtfPropertyBag *v10; // rcx
  int v11; // eax
  struct IMtfPropertyBag *v12; // rcx
  const char *v13; // r9
  __int64 result; // rax
  struct IMtfPropertyBag *v15; // rcx
  unsigned int v16; // [rsp+20h] [rbp-1D8h]
  unsigned int v17; // [rsp+20h] [rbp-1D8h]
  struct IMtfPropertyBag *v18; // [rsp+50h] [rbp-1A8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-190h]
  _QWORD v21[42]; // [rsp+70h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "UpdateDataSource");
  v21[0] = &MtfPlatformTelemetry::UpdateDataSource::`vftable';
  MtfPlatformTelemetry::UpdateDataSource::StartActivity((MtfPlatformTelemetry::UpdateDataSource *)v21);
  try
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4
      || !a3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x988,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)0x80070057LL,
        v16);
      v21[0] = &MtfPlatformTelemetry::UpdateDataSource::`vftable';
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v21);
      result = 2147942487LL;
    }
    else
    {
      v20 = 0;
      v19 = (__int128)*a2;
      v18 = 0;
      v6 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
             (ipx::mtf::CMtfSuggestionClient *)((char *)this - 8),
             0x1Au,
             (const struct MTFCORE_SIMPLEPARAM *)&v19,
             0,
             0,
             0,
             0,
             0,
             &v18);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x995,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v6,
          v17);
        v8 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v8 + 16LL))(v8);
        }
LABEL_16:
        v21[0] = &MtfPlatformTelemetry::UpdateDataSource::`vftable';
        wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
        wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v21);
        return v7;
      }
      v9 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, struct IMtfPropertyBag *))(*(_QWORD *)v18 + 48LL))(
             v18,
             &GUID_MTFCORE_PROPERTYBAG,
             a3);
      v7 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x997,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v9,
          v17);
        v10 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v10 + 16LL))(v10);
        }
        goto LABEL_16;
      }
      v11 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(
              (ipx::mtf::CMtfSuggestionClient *)((char *)this - 8),
              *((_WORD *)this + 98),
              v18);
      v7 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x999,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v11,
          v17);
        v12 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        goto LABEL_16;
      }
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v21);
      v15 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v21[0] = &MtfPlatformTelemetry::UpdateDataSource::`vftable';
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
      wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v21);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x99E,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18001cae0  push    rbx
0x18001cae2  push    rsi
0x18001cae3  push    rdi
0x18001cae4  push    r12
0x18001cae6  push    r14
0x18001cae8  sub     rsp, 1D0h
0x18001caef  mov     rax, cs:__security_cookie
0x18001caf6  xor     rax, rsp
0x18001caf9  mov     [rsp+1F8h+var_38], rax
0x18001cb01  mov     rdi, r8
0x18001cb04  mov     rbx, rdx
0x18001cb07  mov     rsi, rcx
0x18001cb0a  lea     rdx, aUpdatedatasour; "UpdateDataSource"
0x18001cb11  lea     rcx, [rsp+1F8h+var_188]
0x18001cb16  call    ??0?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001cb1b  lea     r12, ??_7UpdateDataSource@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::UpdateDataSource::`vftable'
0x18001cb22  mov     [rsp+1F8h+var_188], r12
0x18001cb27  lea     rcx, [rsp+1F8h+var_188]; this
0x18001cb2c  call    ?StartActivity@UpdateDataSource@MtfPlatformTelemetry@@QEAAXXZ; MtfPlatformTelemetry::UpdateDataSource::StartActivity(void)
0x18001cb31  nop
0x18001cb32  mov     rax, [rbx]
0x18001cb35  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001cb3c  jnz     short loc_18001CB4F
0x18001cb3e  mov     rax, [rbx+8]
0x18001cb42  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001cb49  jz      loc_18001CD50
0x18001cb4f  test    rdi, rdi
0x18001cb52  jz      loc_18001CD50
0x18001cb58  xor     eax, eax
0x18001cb5a  mov     [rsp+1F8h+var_190], rax
0x18001cb5f  movups  xmm0, xmmword ptr [rbx]
0x18001cb62  movdqu  [rsp+1F8h+var_1A0], xmm0
0x18001cb68  mov     [rsp+1F8h+var_1A8], rax
0x18001cb6d  lea     rax, [rsp+1F8h+var_1A8]
0x18001cb72  mov     [rsp+1F8h+var_1B8], rax; struct IMtfPropertyBag **
0x18001cb77  mov     [rsp+1F8h+var_1C0], 0; struct IMtfSuggestionInputQuery *
0x18001cb80  mov     [rsp+1F8h+var_1C8], 0; struct IMtfSuggestionContextProperty *
0x18001cb89  mov     [rsp+1F8h+var_1D0], 0; struct IMtfSuggestionCandidatePrimitive *
0x18001cb92  mov     [rsp+1F8h+var_1D8], 0; int
0x18001cb9a  xor     r9d, r9d; unsigned __int8 *
0x18001cb9d  lea     r8, [rsp+1F8h+var_1A0]; struct MTFCORE_SIMPLEPARAM *
0x18001cba2  lea     edx, [r9+1Ah]; unsigned int
0x18001cba6  lea     rcx, [rsi-8]; this
0x18001cbaa  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x18001cbaf  mov     ebx, eax
0x18001cbb1  test    eax, eax
0x18001cbb3  jns     short loc_18001CC12
0x18001cbb5  mov     rcx, [rsp+1F8h]; this
0x18001cbbd  mov     r9d, eax; char *
0x18001cbc0  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001cbc7  mov     edx, 995h; void *
0x18001cbcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbd1  nop
0x18001cbd2  mov     rcx, [rsp+1F8h+var_1A8]
0x18001cbd7  test    rcx, rcx
0x18001cbda  jz      short loc_18001CBF2
0x18001cbdc  mov     [rsp+1F8h+var_1A8], 0
0x18001cbe5  mov     rax, [rcx]
0x18001cbe8  mov     rax, [rax+10h]
0x18001cbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf1  nop
0x18001cbf2  mov     [rsp+1F8h+var_188], r12
0x18001cbf7  lea     rcx, [rsp+1F8h+var_188]
0x18001cbfc  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001cc01  lea     rcx, [rsp+1F8h+var_188]
0x18001cc06  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001cc0b  mov     eax, ebx
0x18001cc0d  jmp     loc_18001CD93
0x18001cc12  mov     rcx, [rsp+1F8h+var_1A8]
0x18001cc17  mov     rax, [rcx]
0x18001cc1a  mov     r8, rdi
0x18001cc1d  lea     rdx, GUID_MTFCORE_PROPERTYBAG
0x18001cc24  mov     rax, [rax+30h]
0x18001cc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc2d  mov     ebx, eax
0x18001cc2f  test    eax, eax
0x18001cc31  jns     short loc_18001CC90
0x18001cc33  mov     rcx, [rsp+1F8h]; this
0x18001cc3b  mov     r9d, eax; char *
0x18001cc3e  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001cc45  mov     edx, 997h; void *
0x18001cc4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc4f  nop
0x18001cc50  mov     rcx, [rsp+1F8h+var_1A8]
0x18001cc55  test    rcx, rcx
0x18001cc58  jz      short loc_18001CC70
0x18001cc5a  mov     [rsp+1F8h+var_1A8], 0
0x18001cc63  mov     rax, [rcx]
0x18001cc66  mov     rax, [rax+10h]
0x18001cc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc6f  nop
0x18001cc70  mov     [rsp+1F8h+var_188], r12
0x18001cc75  lea     rcx, [rsp+1F8h+var_188]
0x18001cc7a  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001cc7f  lea     rcx, [rsp+1F8h+var_188]
0x18001cc84  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001cc89  mov     eax, ebx
0x18001cc8b  jmp     loc_18001CD93
0x18001cc90  mov     r8, [rsp+1F8h+var_1A8]; struct IMtfPropertyBag *
0x18001cc95  movzx   edx, word ptr [rsi+0C4h]; unsigned __int16
0x18001cc9c  lea     rcx, [rsi-8]; this
0x18001cca0  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x18001cca5  mov     ebx, eax
0x18001cca7  test    eax, eax
0x18001cca9  jns     short loc_18001CD08
0x18001ccab  mov     rcx, [rsp+1F8h]; this
0x18001ccb3  mov     r9d, eax; char *
0x18001ccb6  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001ccbd  mov     edx, 999h; void *
0x18001ccc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ccc7  nop
0x18001ccc8  mov     rcx, [rsp+1F8h+var_1A8]
0x18001cccd  test    rcx, rcx
0x18001ccd0  jz      short loc_18001CCE8
0x18001ccd2  mov     [rsp+1F8h+var_1A8], 0
0x18001ccdb  mov     rax, [rcx]
0x18001ccde  mov     rax, [rax+10h]
0x18001cce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce7  nop
0x18001cce8  mov     [rsp+1F8h+var_188], r12
0x18001cced  lea     rcx, [rsp+1F8h+var_188]
0x18001ccf2  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ccf7  lea     rcx, [rsp+1F8h+var_188]
0x18001ccfc  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001cd01  mov     eax, ebx
0x18001cd03  jmp     loc_18001CD93
0x18001cd08  lea     rcx, [rsp+1F8h+var_188]
0x18001cd0d  call    ?Stop@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001cd12  nop
0x18001cd13  mov     rcx, [rsp+1F8h+var_1A8]
0x18001cd18  test    rcx, rcx
0x18001cd1b  jz      short loc_18001CD33
0x18001cd1d  mov     [rsp+1F8h+var_1A8], 0
0x18001cd26  mov     rax, [rcx]
0x18001cd29  mov     rax, [rax+10h]
0x18001cd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd32  nop
0x18001cd33  mov     [rsp+1F8h+var_188], r12
0x18001cd38  lea     rcx, [rsp+1F8h+var_188]
0x18001cd3d  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001cd42  lea     rcx, [rsp+1F8h+var_188]
0x18001cd47  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001cd4c  xor     eax, eax
0x18001cd4e  jmp     short loc_18001CD93
0x18001cd50  mov     rcx, [rsp+1F8h]; this
0x18001cd58  mov     ebx, 80070057h
0x18001cd5d  mov     r9d, ebx; char *
0x18001cd60  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001cd67  mov     edx, 988h; void *
0x18001cd6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd71  nop
0x18001cd72  mov     [rsp+1F8h+var_188], r12
0x18001cd77  lea     rcx, [rsp+1F8h+var_188]
0x18001cd7c  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001cd81  lea     rcx, [rsp+1F8h+var_188]
0x18001cd86  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001cd8b  mov     eax, ebx
0x18001cd8d  jmp     short loc_18001CD93
0x18001cd8f  mov     eax, dword ptr [rsp+1F8h+var_1A8]
0x18001cd93  mov     rcx, [rsp+1F8h+var_38]
0x18001cd9b  xor     rcx, rsp; StackCookie
0x18001cd9e  call    __security_check_cookie
0x18001cda3  add     rsp, 1D0h
0x18001cdaa  pop     r14
0x18001cdac  pop     r12
0x18001cdae  pop     rdi
0x18001cdaf  pop     rsi
0x18001cdb0  pop     rbx
0x18001cdb1  retn
```
