# ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources(IMtfPropertyBag *)

- ea: `0x18001c840`
- end: `0x18001cad3`
- name: `?UpdateAllDataSources@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIMtfPropertyBag@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IMtfPropertyBag *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180006074`
- `0x180014014`
- `0x180014258`
- `0x180016a08`
- `0x180019a28`
- `0x18001b604`
- `0x18001b8f4`
- `0x18001c840`
- `0x18001d1f4`
- `0x18002bca0`
- `0x18002f010`

## string_xrefs

- `0x18001c86e`: `UpdateAllDataSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources(
        ipx::mtf::CMtfSuggestionClient *this,
        struct IMtfPropertyBag *a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  struct IMtfPropertyBag *v7; // rcx
  int v8; // eax
  struct IMtfPropertyBag *v9; // rcx
  int v10; // eax
  struct IMtfPropertyBag *v11; // rcx
  const char *v12; // r9
  struct IMtfPropertyBag *v13; // rcx
  unsigned int v14; // [rsp+20h] [rbp-1B8h]
  struct IMtfPropertyBag *v15; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v16[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "UpdateAllDataSource");
  v16[0] = &MtfPlatformTelemetry::UpdateAllDataSource::`vftable';
  MtfPlatformTelemetry::UpdateAllDataSource::StartActivity((MtfPlatformTelemetry::UpdateAllDataSource *)v16);
  if ( !a2 )
  {
    v16[0] = &MtfPlatformTelemetry::UpdateAllDataSource::`vftable';
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return 2147942487LL;
  }
  try
  {
    v15 = 0;
    v5 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
           (ipx::mtf::CMtfSuggestionClient *)((char *)this - 8),
           0x1Bu,
           0,
           0,
           0,
           0,
           0,
           0,
           &v15);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, GUID *, struct IMtfPropertyBag *))(*(_QWORD *)v15 + 48LL))(
             v15,
             &GUID_MTFCORE_PROPERTYBAG,
             a2);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v10 = ipx::mtf::CMtfSuggestionClient::RepairAndRequest(
                (ipx::mtf::CMtfSuggestionClient *)((char *)this - 8),
                *((_WORD *)this + 98),
                v15);
        v6 = v10;
        if ( v10 >= 0 )
        {
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
          v13 = v15;
          if ( v15 )
          {
            v15 = 0;
            (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v16[0] = &MtfPlatformTelemetry::UpdateAllDataSource::`vftable';
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
          wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9BE,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v10,
          v14);
        v11 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9BC,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v8,
          v14);
        v9 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9BA,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v5,
        v14);
      v7 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    v16[0] = &MtfPlatformTelemetry::UpdateAllDataSource::`vftable';
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9C3,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18001c840  mov     [rsp+arg_10], rbx
0x18001c845  mov     [rsp+arg_18], rsi
0x18001c84a  push    rdi
0x18001c84b  push    r12
0x18001c84d  push    r14
0x18001c84f  sub     rsp, 1C0h
0x18001c856  mov     rax, cs:__security_cookie
0x18001c85d  xor     rax, rsp
0x18001c860  mov     [rsp+1D8h+var_28], rax
0x18001c868  mov     rdi, rdx
0x18001c86b  mov     rsi, rcx
0x18001c86e  lea     rdx, aUpdatealldatas; "UpdateAllDataSource"
0x18001c875  lea     rcx, [rsp+1D8h+var_178]
0x18001c87a  call    ??0?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001c87f  lea     r12, ??_7UpdateAllDataSource@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::UpdateAllDataSource::`vftable'
0x18001c886  mov     [rsp+1D8h+var_178], r12
0x18001c88b  lea     rcx, [rsp+1D8h+var_178]; this
0x18001c890  call    ?StartActivity@UpdateAllDataSource@MtfPlatformTelemetry@@QEAAXXZ; MtfPlatformTelemetry::UpdateAllDataSource::StartActivity(void)
0x18001c895  nop
0x18001c896  test    rdi, rdi
0x18001c899  jnz     short loc_18001C8BE
0x18001c89b  mov     [rsp+1D8h+var_178], r12
0x18001c8a0  lea     rcx, [rsp+1D8h+var_178]
0x18001c8a5  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c8aa  lea     rcx, [rsp+1D8h+var_178]
0x18001c8af  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c8b4  mov     eax, 80070057h
0x18001c8b9  jmp     loc_18001CAA9
0x18001c8be  mov     [rsp+1D8h+var_188], 0
0x18001c8c7  lea     rax, [rsp+1D8h+var_188]
0x18001c8cc  mov     [rsp+1D8h+var_198], rax; struct IMtfPropertyBag **
0x18001c8d1  mov     [rsp+1D8h+var_1A0], 0; struct IMtfSuggestionInputQuery *
0x18001c8da  mov     [rsp+1D8h+var_1A8], 0; struct IMtfSuggestionContextProperty *
0x18001c8e3  mov     [rsp+1D8h+var_1B0], 0; struct IMtfSuggestionCandidatePrimitive *
0x18001c8ec  mov     [rsp+1D8h+var_1B8], 0; int
0x18001c8f4  xor     r9d, r9d; unsigned __int8 *
0x18001c8f7  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x18001c8fa  lea     edx, [r9+1Bh]; unsigned int
0x18001c8fe  lea     rcx, [rsi-8]; this
0x18001c902  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x18001c907  mov     ebx, eax
0x18001c909  test    eax, eax
0x18001c90b  jns     short loc_18001C96A
0x18001c90d  mov     rcx, [rsp+1D8h]; this
0x18001c915  mov     r9d, eax; char *
0x18001c918  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001c91f  mov     edx, 9BAh; void *
0x18001c924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c929  nop
0x18001c92a  mov     rcx, [rsp+1D8h+var_188]
0x18001c92f  test    rcx, rcx
0x18001c932  jz      short loc_18001C94A
0x18001c934  mov     [rsp+1D8h+var_188], 0
0x18001c93d  mov     rax, [rcx]
0x18001c940  mov     rax, [rax+10h]
0x18001c944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c949  nop
0x18001c94a  mov     [rsp+1D8h+var_178], r12
0x18001c94f  lea     rcx, [rsp+1D8h+var_178]
0x18001c954  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c959  lea     rcx, [rsp+1D8h+var_178]
0x18001c95e  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c963  mov     eax, ebx
0x18001c965  jmp     loc_18001CAA9
0x18001c96a  mov     rcx, [rsp+1D8h+var_188]
0x18001c96f  mov     rax, [rcx]
0x18001c972  mov     r8, rdi
0x18001c975  lea     rdx, GUID_MTFCORE_PROPERTYBAG
0x18001c97c  mov     rax, [rax+30h]
0x18001c980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c985  mov     ebx, eax
0x18001c987  test    eax, eax
0x18001c989  jns     short loc_18001C9E8
0x18001c98b  mov     rcx, [rsp+1D8h]; this
0x18001c993  mov     r9d, eax; char *
0x18001c996  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001c99d  mov     edx, 9BCh; void *
0x18001c9a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c9a7  nop
0x18001c9a8  mov     rcx, [rsp+1D8h+var_188]
0x18001c9ad  test    rcx, rcx
0x18001c9b0  jz      short loc_18001C9C8
0x18001c9b2  mov     [rsp+1D8h+var_188], 0
0x18001c9bb  mov     rax, [rcx]
0x18001c9be  mov     rax, [rax+10h]
0x18001c9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9c7  nop
0x18001c9c8  mov     [rsp+1D8h+var_178], r12
0x18001c9cd  lea     rcx, [rsp+1D8h+var_178]
0x18001c9d2  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c9d7  lea     rcx, [rsp+1D8h+var_178]
0x18001c9dc  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c9e1  mov     eax, ebx
0x18001c9e3  jmp     loc_18001CAA9
0x18001c9e8  mov     r8, [rsp+1D8h+var_188]; struct IMtfPropertyBag *
0x18001c9ed  movzx   edx, word ptr [rsi+0C4h]; unsigned __int16
0x18001c9f4  lea     rcx, [rsi-8]; this
0x18001c9f8  call    ?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)
0x18001c9fd  mov     ebx, eax
0x18001c9ff  test    eax, eax
0x18001ca01  jns     short loc_18001CA5D
0x18001ca03  mov     rcx, [rsp+1D8h]; this
0x18001ca0b  mov     r9d, eax; char *
0x18001ca0e  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001ca15  mov     edx, 9BEh; void *
0x18001ca1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca1f  nop
0x18001ca20  mov     rcx, [rsp+1D8h+var_188]
0x18001ca25  test    rcx, rcx
0x18001ca28  jz      short loc_18001CA40
0x18001ca2a  mov     [rsp+1D8h+var_188], 0
0x18001ca33  mov     rax, [rcx]
0x18001ca36  mov     rax, [rax+10h]
0x18001ca3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca3f  nop
0x18001ca40  mov     [rsp+1D8h+var_178], r12
0x18001ca45  lea     rcx, [rsp+1D8h+var_178]
0x18001ca4a  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ca4f  lea     rcx, [rsp+1D8h+var_178]
0x18001ca54  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ca59  mov     eax, ebx
0x18001ca5b  jmp     short loc_18001CAA9
0x18001ca5d  lea     rcx, [rsp+1D8h+var_178]
0x18001ca62  call    ?Stop@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ca67  nop
0x18001ca68  mov     rcx, [rsp+1D8h+var_188]
0x18001ca6d  test    rcx, rcx
0x18001ca70  jz      short loc_18001CA88
0x18001ca72  mov     [rsp+1D8h+var_188], 0
0x18001ca7b  mov     rax, [rcx]
0x18001ca7e  mov     rax, [rax+10h]
0x18001ca82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca87  nop
0x18001ca88  mov     [rsp+1D8h+var_178], r12
0x18001ca8d  lea     rcx, [rsp+1D8h+var_178]
0x18001ca92  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ca97  lea     rcx, [rsp+1D8h+var_178]
0x18001ca9c  call    ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001caa1  xor     eax, eax
0x18001caa3  jmp     short loc_18001CAA9
0x18001caa5  mov     eax, dword ptr [rsp+1D8h+var_188]
0x18001caa9  mov     rcx, [rsp+1D8h+var_28]
0x18001cab1  xor     rcx, rsp; StackCookie
0x18001cab4  call    __security_check_cookie
0x18001cab9  lea     r11, [rsp+1D8h+var_18]
0x18001cac1  mov     rbx, [r11+30h]
0x18001cac5  mov     rsi, [r11+38h]
0x18001cac9  mov     rsp, r11
0x18001cacc  pop     r14
0x18001cace  pop     r12
0x18001cad0  pop     rdi
0x18001cad1  retn
```
