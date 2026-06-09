# CMidi2BS2UMPMidiTransform::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *,ulong *,IMidiCallback *,__int64,IMidiDeviceManager *)

- ea: `0x18000a840`
- end: `0x18000a976`
- name: `?Initialize@CMidi2BS2UMPMidiTransform@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001@@PEAKPEAUIMidiCallback@@_JPEAUIMidiDeviceManager@@@Z`
- size: `310`
- prototype: `int(CMidi2BS2UMPMidiTransform *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *, unsigned int *, struct IMidiCallback *, __int64, struct IMidiDeviceManager *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800016dc`
- `0x1800076b4`
- `0x180009528`
- `0x18000a5c0`
- `0x18000a840`
- `0x18000b3fc`
- `0x18000c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2BS2UMPMidiTransform::Initialize(
        CMidi2BS2UMPMidiTransform *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5)
{
  _DWORD *v8; // rcx
  __int64 v9; // r8
  int v10; // r9d
  __int64 v11; // rdx
  char **v13; // rcx
  unsigned __int64 v14; // rdx
  char *v15; // rbp
  __int64 v16; // rbx
  __int64 v17; // rbx
  struct IMidiCallback *v18; // rcx
  unsigned __int8 v19; // al
  int v20; // [rsp+20h] [rbp-58h]
  int v21[2]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  CMidi2BS2UMPMidiTransform *v23; // [rsp+90h] [rbp+18h] BYREF

  v8 = (_DWORD *)*((_QWORD *)MidiBS2UMPTransformTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    v23 = this;
    *(_QWORD *)v21 = "CMidi2BS2UMPMidiTransform::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)byte_18000EEF5,
      v9,
      v10,
      (__int64)v21,
      (__int64)&v23);
  }
  if ( *(_DWORD *)a3 != 1 )
  {
    v11 = 26;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\transform\\bytestreamtoump\\midi2.bs2umpmiditransform.cpp",
      (const char *)0x8007065ELL,
      v20);
    return 2147944030LL;
  }
  if ( *((_DWORD *)a3 + 1) != 2 )
  {
    v11 = 27;
    goto LABEL_5;
  }
  v13 = (char **)((char *)this + 56);
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  if ( v14 > *((_QWORD *)this + 10) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v13,
      v14,
      v9,
      a2);
  }
  else
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v15 = (char *)this + 56;
    else
      v15 = *v13;
    *((_QWORD *)this + 9) = v14;
    v16 = 2 * v14;
    memmove_0(v15, a2, 2 * v14);
    *(_WORD *)&v15[v16] = 0;
  }
  v17 = *((_QWORD *)this + 11);
  v18 = a5;
  *((_QWORD *)this + 11) = a5;
  if ( v18 )
    (*(void (__fastcall **)(struct IMidiCallback *))(*(_QWORD *)v18 + 8LL))(v18);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v19 = *((_BYTE *)a3 + 8);
  if ( v19 <= 0xFu )
    *((_BYTE *)this + 232) = v19;
  return 0;
}

```

## disassembly

```asm
0x18000a840  push    rbx
0x18000a842  push    rbp
0x18000a843  push    rsi
0x18000a844  push    rdi
0x18000a845  push    r14
0x18000a847  push    r15
0x18000a849  sub     rsp, 48h
0x18000a84d  mov     rsi, r8
0x18000a850  mov     r14, rdx
0x18000a853  mov     rdi, rcx
0x18000a856  call    ?Instance@MidiBS2UMPTransformTelemetryProvider@@KAPEAV1@XZ; MidiBS2UMPTransformTelemetryProvider::Instance(void)
0x18000a85b  mov     rcx, [rax+8]
0x18000a85f  mov     eax, [rcx]
0x18000a861  cmp     eax, 4
0x18000a864  jbe     short loc_18000A89D
0x18000a866  mov     [rsp+78h+arg_10], rdi
0x18000a86e  lea     rax, aCmidi2bs2umpmi; "CMidi2BS2UMPMidiTransform::Initialize"
0x18000a875  mov     qword ptr [rsp+78h+var_48], rax
0x18000a87a  lea     rax, [rsp+78h+arg_10]
0x18000a882  mov     [rsp+78h+var_50], rax
0x18000a887  lea     rax, [rsp+78h+var_48]
0x18000a88c  mov     qword ptr [rsp+78h+var_58], rax; int
0x18000a891  lea     rdx, byte_18000EEF5
0x18000a898  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000a89d  cmp     dword ptr [rsi], 1
0x18000a8a0  jz      short loc_18000A8C7
0x18000a8a2  mov     edx, 1Ah; void *
0x18000a8a7  mov     ebx, 8007065Eh
0x18000a8ac  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transform\\bytestreamtou"...
0x18000a8b3  mov     r9d, ebx; char *
0x18000a8b6  mov     rcx, [rsp+78h]; this
0x18000a8bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8c0  mov     eax, ebx
0x18000a8c2  jmp     loc_18000A969
0x18000a8c7  cmp     dword ptr [rsi+4], 2
0x18000a8cb  jz      short loc_18000A8D4
0x18000a8cd  mov     edx, 1Bh
0x18000a8d2  jmp     short loc_18000A8A7
0x18000a8d4  lea     rcx, [rdi+38h]
0x18000a8d8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a8dc  xor     r15d, r15d
0x18000a8df  inc     rdx
0x18000a8e2  cmp     [r14+rdx*2], r15w
0x18000a8e7  jnz     short loc_18000A8DF
0x18000a8e9  cmp     rdx, [rcx+18h]
0x18000a8ed  ja      short loc_18000A91B
0x18000a8ef  cmp     qword ptr [rcx+18h], 7
0x18000a8f4  jbe     short loc_18000A8FB
0x18000a8f6  mov     rbp, [rcx]
0x18000a8f9  jmp     short loc_18000A8FE
0x18000a8fb  mov     rbp, rcx
0x18000a8fe  mov     [rcx+10h], rdx
0x18000a902  lea     rbx, [rdx+rdx]
0x18000a906  mov     r8, rbx; Size
0x18000a909  mov     rdx, r14; Src
0x18000a90c  mov     rcx, rbp; void *
0x18000a90f  call    memmove_0
0x18000a914  mov     [rbx+rbp], r15w
0x18000a919  jmp     short loc_18000A924
0x18000a91b  mov     r9, r14
0x18000a91e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18000a923  nop
0x18000a924  mov     rbx, [rdi+58h]
0x18000a928  mov     rcx, [rsp+78h+arg_20]
0x18000a930  mov     [rdi+58h], rcx
0x18000a934  test    rcx, rcx
0x18000a937  jz      short loc_18000A945
0x18000a939  mov     rax, [rcx]
0x18000a93c  mov     rax, [rax+8]
0x18000a940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a945  test    rbx, rbx
0x18000a948  jz      short loc_18000A95A
0x18000a94a  mov     rax, [rbx]
0x18000a94d  mov     rcx, rbx
0x18000a950  mov     rax, [rax+10h]
0x18000a954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a959  nop
0x18000a95a  mov     al, [rsi+8]
0x18000a95d  cmp     al, 0Fh
0x18000a95f  ja      short loc_18000A967
0x18000a961  mov     [rdi+0E8h], al
0x18000a967  xor     eax, eax
0x18000a969  add     rsp, 48h
0x18000a96d  pop     r15
0x18000a96f  pop     r14
0x18000a971  pop     rdi
0x18000a972  pop     rsi
0x18000a973  pop     rbp
0x18000a974  pop     rbx
0x18000a975  retn
```
