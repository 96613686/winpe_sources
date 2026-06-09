# CMidi2UMP2BSMidiTransform::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *,ulong *,IMidiCallback *,__int64,IMidiDeviceManager *)

- ea: `0x18000c2c0`
- end: `0x18000c3ef`
- name: `?Initialize@CMidi2UMP2BSMidiTransform@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001@@PEAKPEAUIMidiCallback@@_JPEAUIMidiDeviceManager@@@Z`
- size: `303`
- prototype: `int(CMidi2UMP2BSMidiTransform *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *, unsigned int *, struct IMidiCallback *, __int64, struct IMidiDeviceManager *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800016dc`
- `0x180007744`
- `0x1800095b8`
- `0x18000a65c`
- `0x18000c2c0`
- `0x18000e8fc`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2UMP2BSMidiTransform::Initialize(
        CMidi2UMP2BSMidiTransform *this,
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
  char *v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rbx
  struct IMidiCallback *v18; // rcx
  int v19; // [rsp+20h] [rbp-38h]
  int v20[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CMidi2UMP2BSMidiTransform *v22; // [rsp+70h] [rbp+18h] BYREF

  v8 = (_DWORD *)*((_QWORD *)MidiUMP2BSTransformTelemetryProvider::Instance() + 1);
  if ( *v8 > 4u )
  {
    v22 = this;
    *(_QWORD *)v20 = "CMidi2UMP2BSMidiTransform::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)byte_18001210D,
      v9,
      v10,
      (__int64)v20,
      (__int64)&v22);
  }
  if ( *(_DWORD *)a3 != 2 )
  {
    v11 = 30;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\transform\\umptobytestream\\midi2.ump2bsmiditransform.cpp",
      (const char *)0x8007065ELL,
      v19);
    return 2147944030LL;
  }
  if ( *((_DWORD *)a3 + 1) != 1 )
  {
    v11 = 31;
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
  return 0;
}

```

## disassembly

```asm
0x18000c2c0  mov     [rsp+arg_0], rbx
0x18000c2c5  mov     [rsp+arg_8], rbp
0x18000c2ca  push    rsi
0x18000c2cb  push    rdi
0x18000c2cc  push    r14
0x18000c2ce  sub     rsp, 40h
0x18000c2d2  mov     rbx, r8
0x18000c2d5  mov     rbp, rdx
0x18000c2d8  mov     rdi, rcx
0x18000c2db  call    ?Instance@MidiUMP2BSTransformTelemetryProvider@@KAPEAV1@XZ; MidiUMP2BSTransformTelemetryProvider::Instance(void)
0x18000c2e0  mov     rcx, [rax+8]
0x18000c2e4  mov     eax, [rcx]
0x18000c2e6  cmp     eax, 4
0x18000c2e9  jbe     short loc_18000C31C
0x18000c2eb  mov     [rsp+58h+arg_10], rdi
0x18000c2f0  lea     rax, aCmidi2ump2bsmi_1; "CMidi2UMP2BSMidiTransform::Initialize"
0x18000c2f7  mov     qword ptr [rsp+58h+var_28], rax
0x18000c2fc  lea     rax, [rsp+58h+arg_10]
0x18000c301  mov     [rsp+58h+var_30], rax
0x18000c306  lea     rax, [rsp+58h+var_28]
0x18000c30b  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000c310  lea     rdx, byte_18001210D
0x18000c317  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c31c  cmp     dword ptr [rbx], 2
0x18000c31f  jz      short loc_18000C346
0x18000c321  mov     edx, 1Eh; void *
0x18000c326  mov     ebx, 8007065Eh
0x18000c32b  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umptobytestre"...
0x18000c332  mov     r9d, ebx; char *
0x18000c335  mov     rcx, [rsp+58h]; this
0x18000c33a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c33f  mov     eax, ebx
0x18000c341  jmp     loc_18000C3DC
0x18000c346  cmp     dword ptr [rbx+4], 1
0x18000c34a  jz      short loc_18000C353
0x18000c34c  mov     edx, 1Fh
0x18000c351  jmp     short loc_18000C326
0x18000c353  lea     rcx, [rdi+38h]
0x18000c357  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c35b  xor     r14d, r14d
0x18000c35e  inc     rdx
0x18000c361  cmp     [rbp+rdx*2+0], r14w
0x18000c367  jnz     short loc_18000C35E
0x18000c369  cmp     rdx, [rcx+18h]
0x18000c36d  ja      short loc_18000C39B
0x18000c36f  cmp     qword ptr [rcx+18h], 7
0x18000c374  jbe     short loc_18000C37B
0x18000c376  mov     rsi, [rcx]
0x18000c379  jmp     short loc_18000C37E
0x18000c37b  mov     rsi, rcx
0x18000c37e  mov     [rcx+10h], rdx
0x18000c382  lea     rbx, [rdx+rdx]
0x18000c386  mov     r8, rbx; Size
0x18000c389  mov     rdx, rbp; Src
0x18000c38c  mov     rcx, rsi; void *
0x18000c38f  call    memmove_0
0x18000c394  mov     [rbx+rsi], r14w
0x18000c399  jmp     short loc_18000C3A4
0x18000c39b  mov     r9, rbp
0x18000c39e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18000c3a3  nop
0x18000c3a4  mov     rbx, [rdi+58h]
0x18000c3a8  mov     rcx, [rsp+58h+arg_20]
0x18000c3b0  mov     [rdi+58h], rcx
0x18000c3b4  test    rcx, rcx
0x18000c3b7  jz      short loc_18000C3C5
0x18000c3b9  mov     rax, [rcx]
0x18000c3bc  mov     rax, [rax+8]
0x18000c3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c5  test    rbx, rbx
0x18000c3c8  jz      short loc_18000C3DA
0x18000c3ca  mov     rax, [rbx]
0x18000c3cd  mov     rcx, rbx
0x18000c3d0  mov     rax, [rax+10h]
0x18000c3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d9  nop
0x18000c3da  xor     eax, eax
0x18000c3dc  mov     rbx, [rsp+58h+arg_0]
0x18000c3e1  mov     rbp, [rsp+58h+arg_8]
0x18000c3e6  add     rsp, 40h
0x18000c3ea  pop     r14
0x18000c3ec  pop     rdi
0x18000c3ed  pop     rsi
0x18000c3ee  retn
```
