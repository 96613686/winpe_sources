# CRdpIdAdapter::DeserializePropertyBag(_RDPIDD_OPCODE_SET_PROPERTY_BAG * const,IPropertyStore *)

- ea: `0x180015d80`
- end: `0x180016269`
- name: `?DeserializePropertyBag@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_SET_PROPERTY_BAG@@PEAUIPropertyStore@@@Z`
- size: `1257`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *const, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001afa8`

## callees

- `0x180007b20`
- `0x1800089f0`
- `0x180011584`
- `0x180015d80`
- `0x18001dd50`
- `0x18001ddbc`
- `0x18001ddf4`
- `0x18003f010`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x180015edc`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180015edc`
- `PROPSYS!InitPropVariantFromBuffer` at `0x180015f78`
- `PROPSYS!InitPropVariantFromBuffer` at `0x180015f78`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016019`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001602e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016019`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001602e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f22`

## string_xrefs

- `0x18001609a`: `Unable to move to RDPIDD_PROPERTY_BAG_ENTRY because buffer is too small`
- `0x18001619a`: `Unable to cast to 'CLSID' because buffer is too small`
- `0x180016201`: `Unable read BLOB data because buffer is too small`
- `0x180016225`: `Unable to move to next RDPIDD_PROPERTY_BAG_ENTRY because buffer is too small`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRdpIdAdapter::DeserializePropertyBag(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *const a2,
        struct IPropertyStore *a3)
{
  unsigned int v4; // r14d
  unsigned int *v5; // rbx
  unsigned int v6; // edx
  __int16 v7; // ax
  __int16 v8; // ax
  int v9; // esi
  __int16 v10; // ax
  unsigned int v11; // eax
  __int64 v12; // r15
  void *v13; // rax
  unsigned __int64 v14; // rdx
  unsigned int inited; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // edx
  int v19; // [rsp+20h] [rbp-30h]
  char *v20; // [rsp+28h] [rbp-28h]
  PROPVARIANT ppropvar[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v4 = *(_DWORD *)a2 - 28;
  if ( v4 < 0x1C )
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0xFD9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0xC0000023LL,
      (int)"Unable to move to RDPIDD_PROPERTY_BAG_ENTRY because buffer is too small",
      v20);
  v5 = (unsigned int *)((char *)a2 + 28);
  while ( 1 )
  {
    if ( v4 < *v5 )
    {
      LODWORD(v20) = *v5;
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0xFE8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"RDPIDD_PROPERTY_BAG_ENTRY structure has invalid size %d",
        v20);
    }
    *(_OWORD *)ppropvar = 0;
    v22 = 0;
    v6 = v5[6];
    if ( v6 > 6 )
    {
      switch ( v6 )
      {
        case 7u:
          if ( *v5 < 0x24 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x1052,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to 'double' because buffer is too small",
              v20);
          LOWORD(ppropvar[0]) = 5;
          ppropvar[1] = *(PROPVARIANT *)(v5 + 7);
LABEL_41:
          v9 = 36;
          break;
        case 8u:
          v14 = v5[7];
          if ( v14 > (unsigned __int64)*v5 - 28 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x107E,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable read BLOB data because buffer is too small",
              v20);
          v9 = v14 + 28;
          inited = InitPropVariantFromBuffer(v5 + 8, v14, ppropvar);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x1084,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)inited,
            (int)"Failed to initialize BLOB property",
            v20);
          break;
        case 9u:
          v9 = *v5;
          LOWORD(ppropvar[0]) = 31;
          v12 = (unsigned int)(v9 - 28);
          v13 = CoTaskMemAlloc(v12 + 2);
          ppropvar[1] = v13;
          if ( !v13 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1070,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0x8007000ELL,
              v19);
          memcpy_0(v13, v5 + 7, (unsigned int)v12);
          *(_WORD *)((char *)ppropvar[1] + v12) = 0;
          break;
        case 0xAu:
          if ( *v5 < 0x2C )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x1061,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to 'CLSID' because buffer is too small",
              v20);
          v9 = 44;
          v11 = InitPropVariantFromCLSID((const IID *const)(v5 + 7), ppropvar);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x1065,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)v11,
            (int)"Failed to initialize GUID property",
            v20);
          break;
        default:
LABEL_57:
          v17 = wil::verify_hresult<long>(2147942487LL);
          LODWORD(v20) = v18;
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x108B,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)v17,
            (int)"Unsupported property type: %d",
            v20,
            ppropvar[0],
            ppropvar[1],
            v22);
      }
    }
    else if ( v6 == 6 )
    {
      if ( *v5 < 0x20 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x1043,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Unable to cast to 'float' because buffer is too small",
          v20);
      v9 = 32;
      LOWORD(ppropvar[0]) = 4;
      LODWORD(ppropvar[1]) = v5[7];
    }
    else
    {
      if ( v6 != 1 )
      {
        if ( v6 == 2 )
        {
          if ( *v5 < 0x20 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x1007,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to 'int32_t' because buffer is too small",
              v20);
          v8 = 3;
        }
        else
        {
          if ( v6 != 3 )
          {
            if ( v6 == 4 )
            {
              if ( *v5 < 0x24 )
                wil::details::in1diag3::Throw_NtStatusMsg(
                  retaddr,
                  (void *)0x1025,
                  (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                  (const char *)0xC0000023LL,
                  (int)"Unable to cast to 'int64_t' because buffer is too small",
                  v20);
              v7 = 20;
            }
            else
            {
              if ( v6 != 5 )
                goto LABEL_57;
              if ( *v5 < 0x24 )
                wil::details::in1diag3::Throw_NtStatusMsg(
                  retaddr,
                  (void *)0x1034,
                  (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                  (const char *)0xC0000023LL,
                  (int)"Unable to cast to 'uint64_t' because buffer is too small",
                  v20);
              v7 = 21;
            }
            LOWORD(ppropvar[0]) = v7;
            ppropvar[1] = *(PROPVARIANT *)(v5 + 7);
            goto LABEL_41;
          }
          if ( *v5 < 0x20 )
            wil::details::in1diag3::Throw_NtStatusMsg(
              retaddr,
              (void *)0x1016,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0xC0000023LL,
              (int)"Unable to cast to 'uint32_t' because buffer is too small",
              v20);
          v8 = 19;
        }
        v9 = 32;
        LOWORD(ppropvar[0]) = v8;
        LODWORD(ppropvar[1]) = v5[7];
        goto LABEL_42;
      }
      if ( *v5 < 0x1D )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Unable to cast to 'bool' because buffer is too small",
          v20);
      v9 = 29;
      LOWORD(ppropvar[0]) = 11;
      v10 = *((_BYTE *)v5 + 28) ? -1 : 0;
      LOWORD(ppropvar[1]) = v10;
    }
LABEL_42:
    v16 = ((__int64 (__fastcall *)(struct IPropertyStore *, unsigned int *, PROPVARIANT *))a3->lpVtbl->SetValue)(
            a3,
            v5 + 1,
            ppropvar);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1093,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v16,
      (int)"Failed to add property value",
      v20);
    if ( *v5 != ((v9 + 7) & 0xFFFFFFF8) )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x109E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"RDPIDD_PROPERTY_BAG_ENTRY structure is not aligned on 8 byte boundary",
        v20);
    v4 -= *v5;
    if ( !v4 )
      break;
    if ( v4 < 0x1C )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x10B2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Unable to move to next RDPIDD_PROPERTY_BAG_ENTRY because buffer is too small",
        v20);
    v5 = (unsigned int *)((char *)v5 + *v5);
    PropVariantClear(ppropvar);
  }
  PropVariantClear(ppropvar);
}

```

## disassembly

```asm
0x180015d80  push    rbp
0x180015d82  push    rbx
0x180015d83  push    rsi
0x180015d84  push    rdi
0x180015d85  push    r12
0x180015d87  push    r14
0x180015d89  push    r15
0x180015d8b  mov     rbp, rsp
0x180015d8e  sub     rsp, 50h
0x180015d92  mov     r12, r8
0x180015d95  mov     r14d, [rdx]
0x180015d98  sub     r14d, 1Ch
0x180015d9c  cmp     r14d, 1Ch
0x180015da0  jb      loc_180016096
0x180015da6  lea     rbx, [rdx+1Ch]
0x180015daa  lea     rdi, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180015db1  mov     eax, [rbx]
0x180015db3  cmp     r14d, eax
0x180015db6  jb      loc_18001606E
0x180015dbc  mov     ecx, 20h ; ' '
0x180015dc1  xorps   xmm0, xmm0
0x180015dc4  xor     eax, eax
0x180015dc6  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180015dca  mov     [rbp+var_10], rax
0x180015dce  mov     edx, [rbx+18h]
0x180015dd1  cmp     edx, 6
0x180015dd4  ja      loc_180015EA6
0x180015dda  jz      loc_180015E84
0x180015de0  mov     eax, edx
0x180015de2  sub     eax, 1
0x180015de5  jz      short loc_180015E59
0x180015de7  sub     eax, 1
0x180015dea  jz      short loc_180015E3B
0x180015dec  sub     eax, 1
0x180015def  jz      short loc_180015E2C
0x180015df1  sub     eax, 1
0x180015df4  jz      short loc_180015E1C
0x180015df6  cmp     eax, 1
0x180015df9  jnz     loc_1800161BA
0x180015dff  cmp     dword ptr [rbx], 24h ; '$'
0x180015e02  jb      loc_1800160BE
0x180015e08  lea     eax, [rcx-0Bh]
0x180015e0b  mov     word ptr [rbp+ppropvar], ax
0x180015e0f  mov     rax, [rbx+1Ch]
0x180015e13  mov     [rbp+ppropvar+8], rax
0x180015e17  jmp     loc_180015FB6
0x180015e1c  cmp     dword ptr [rbx], 24h ; '$'
0x180015e1f  jb      loc_1800160E2
0x180015e25  mov     eax, 14h
0x180015e2a  jmp     short loc_180015E0B
0x180015e2c  cmp     [rbx], ecx
0x180015e2e  jb      loc_180016106
0x180015e34  mov     eax, 13h
0x180015e39  jmp     short loc_180015E48
0x180015e3b  cmp     [rbx], ecx
0x180015e3d  jb      loc_18001612A
0x180015e43  mov     eax, 3
0x180015e48  mov     esi, ecx
0x180015e4a  mov     word ptr [rbp+ppropvar], ax
0x180015e4e  mov     eax, [rbx+1Ch]
0x180015e51  mov     dword ptr [rbp+ppropvar+8], eax
0x180015e54  jmp     loc_180015FBB
0x180015e59  cmp     dword ptr [rbx], 1Dh
0x180015e5c  jb      loc_18001614E
0x180015e62  mov     esi, 1Dh
0x180015e67  lea     eax, [rsi-12h]
0x180015e6a  mov     word ptr [rbp+ppropvar], ax
0x180015e6e  cmp     byte ptr [rbx+1Ch], 0
0x180015e72  jz      short loc_180015E79
0x180015e74  or      eax, 0FFFFFFFFh
0x180015e77  jmp     short loc_180015E7B
0x180015e79  xor     eax, eax
0x180015e7b  mov     word ptr [rbp+ppropvar+8], ax
0x180015e7f  jmp     loc_180015FBB
0x180015e84  cmp     [rbx], ecx
0x180015e86  jb      loc_180016172
0x180015e8c  mov     esi, ecx
0x180015e8e  mov     eax, 4
0x180015e93  mov     word ptr [rbp+ppropvar], ax
0x180015e97  movss   xmm0, dword ptr [rbx+1Ch]
0x180015e9c  movss   dword ptr [rbp+ppropvar+8], xmm0
0x180015ea1  jmp     loc_180015FBB
0x180015ea6  mov     eax, edx
0x180015ea8  sub     eax, 7
0x180015eab  jz      loc_180015F9A
0x180015eb1  sub     eax, 1
0x180015eb4  jz      loc_180015F5B
0x180015eba  sub     eax, 1
0x180015ebd  jz      short loc_180015F0D
0x180015ebf  cmp     eax, 1
0x180015ec2  jnz     loc_1800161BA
0x180015ec8  cmp     dword ptr [rbx], 2Ch ; ','
0x180015ecb  jb      loc_180016196
0x180015ed1  lea     esi, [rax+2Bh]
0x180015ed4  lea     rcx, [rbx+1Ch]; clsid
0x180015ed8  lea     rdx, [rbp+ppropvar]; ppropvar
0x180015edc  call    cs:__imp_InitPropVariantFromCLSID
0x180015ee3  nop     dword ptr [rax+rax+00h]
0x180015ee8  lea     rdx, aFailedToInitia_3; "Failed to initialize GUID property"
0x180015eef  mov     qword ptr [rsp+50h+var_30], rdx; int
0x180015ef4  mov     edx, 1065h; void *
0x180015ef9  mov     r8, rdi; unsigned int
0x180015efc  mov     r9d, eax; char *
0x180015eff  mov     rcx, [rbp+38h]; this
0x180015f03  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015f08  jmp     loc_180015FBB
0x180015f0d  mov     esi, [rbx]
0x180015f0f  mov     eax, 1Fh
0x180015f14  mov     word ptr [rbp+ppropvar], ax
0x180015f18  lea     eax, [rsi-1Ch]
0x180015f1b  mov     r15d, eax
0x180015f1e  lea     rcx, [rax+2]; cb
0x180015f22  call    cs:__imp_CoTaskMemAlloc
0x180015f29  nop     dword ptr [rax+rax+00h]
0x180015f2e  mov     [rbp+ppropvar+8], rax
0x180015f32  mov     rcx, [rbp+38h]; this
0x180015f36  test    rax, rax
0x180015f39  jz      loc_1800161E9
0x180015f3f  lea     rdx, [rbx+1Ch]; Src
0x180015f43  mov     r8d, r15d; Size
0x180015f46  mov     rcx, rax; void *
0x180015f49  call    memcpy_0
0x180015f4e  xor     ecx, ecx
0x180015f50  mov     rax, [rbp+ppropvar+8]
0x180015f54  mov     [r15+rax], cx
0x180015f59  jmp     short loc_180015FBB
0x180015f5b  mov     edx, [rbx+1Ch]; cb
0x180015f5e  mov     eax, [rbx]
0x180015f60  sub     rax, 1Ch
0x180015f64  cmp     rdx, rax
0x180015f67  ja      loc_1800161FD
0x180015f6d  lea     esi, [rdx+1Ch]
0x180015f70  lea     rcx, [rbx+20h]; pv
0x180015f74  lea     r8, [rbp+ppropvar]; ppropvar
0x180015f78  call    cs:__imp_InitPropVariantFromBuffer
0x180015f7f  nop     dword ptr [rax+rax+00h]
0x180015f84  lea     rdx, aFailedToInitia; "Failed to initialize BLOB property"
0x180015f8b  mov     qword ptr [rsp+50h+var_30], rdx
0x180015f90  mov     edx, 1084h
0x180015f95  jmp     loc_180015EF9
0x180015f9a  cmp     dword ptr [rbx], 24h ; '$'
0x180015f9d  jb      loc_18001604A
0x180015fa3  mov     eax, 5
0x180015fa8  mov     word ptr [rbp+ppropvar], ax
0x180015fac  movsd   xmm0, qword ptr [rbx+1Ch]
0x180015fb1  movsd   [rbp+ppropvar+8], xmm0
0x180015fb6  mov     esi, 24h ; '$'
0x180015fbb  mov     rax, [r12]
0x180015fbf  lea     rdx, [rbx+4]
0x180015fc3  lea     r8, [rbp+ppropvar]
0x180015fc7  mov     rcx, r12
0x180015fca  mov     rax, [rax+30h]
0x180015fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd3  mov     rcx, [rbp+38h]; this
0x180015fd7  lea     rdx, aFailedToAddPro; "Failed to add property value"
0x180015fde  mov     qword ptr [rsp+50h+var_30], rdx; int
0x180015fe3  mov     r9d, eax; char *
0x180015fe6  mov     r8, rdi; unsigned int
0x180015fe9  mov     edx, 1093h; void *
0x180015fee  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015ff3  lea     eax, [rsi+7]
0x180015ff6  and     eax, 0FFFFFFF8h
0x180015ff9  cmp     [rbx], eax
0x180015ffb  jnz     loc_180016245
0x180016001  sub     r14d, [rbx]
0x180016004  jz      short loc_18001602A
0x180016006  cmp     r14d, 1Ch
0x18001600a  jb      loc_180016221
0x180016010  mov     eax, [rbx]
0x180016012  add     rbx, rax
0x180016015  lea     rcx, [rbp+ppropvar]; pvar
0x180016019  call    cs:__imp_PropVariantClear
0x180016020  nop     dword ptr [rax+rax+00h]
0x180016025  jmp     loc_180015DB1
0x18001602a  lea     rcx, [rbp+ppropvar]; pvar
0x18001602e  call    cs:__imp_PropVariantClear
0x180016035  nop     dword ptr [rax+rax+00h]
0x18001603a  add     rsp, 50h
0x18001603e  pop     r15
0x180016040  pop     r14
0x180016042  pop     r12
0x180016044  pop     rdi
0x180016045  pop     rsi
0x180016046  pop     rbx
0x180016047  pop     rbp
0x180016048  retn
0x18001604a  mov     rcx, [rbp+38h]; this
0x18001604e  lea     rax, aUnableToCastTo_13; "Unable to cast to 'double' because buff"...
0x180016055  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001605a  mov     r9d, 0C0000023h; char *
0x180016060  mov     r8, rdi; unsigned int
0x180016063  mov     edx, 1052h; void *
0x180016068  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001606e  mov     rcx, [rbp+38h]; this
0x180016072  mov     dword ptr [rsp+50h+var_28], eax; char *
0x180016076  lea     rax, aRdpiddProperty_0; "RDPIDD_PROPERTY_BAG_ENTRY structure has"...
0x18001607d  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016082  mov     r9d, 0C0000023h; char *
0x180016088  mov     r8, rdi; unsigned int
0x18001608b  mov     edx, 0FE8h; void *
0x180016090  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016096  mov     rcx, [rbp+38h]; this
0x18001609a  lea     rax, aUnableToMoveTo; "Unable to move to RDPIDD_PROPERTY_BAG_E"...
0x1800160a1  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800160a6  mov     r9d, 0C0000023h; char *
0x1800160ac  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800160b3  mov     edx, 0FD9h; void *
0x1800160b8  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800160be  mov     rcx, [rbp+38h]; this
0x1800160c2  lea     rax, aUnableToCastTo_0; "Unable to cast to 'uint64_t' because bu"...
0x1800160c9  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800160ce  mov     r9d, 0C0000023h; char *
0x1800160d4  mov     r8, rdi; unsigned int
0x1800160d7  mov     edx, 1034h; void *
0x1800160dc  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800160e2  mov     rcx, [rbp+38h]; this
0x1800160e6  lea     rax, aUnableToCastTo_3; "Unable to cast to 'int64_t' because buf"...
0x1800160ed  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800160f2  mov     r9d, 0C0000023h; char *
0x1800160f8  mov     r8, rdi; unsigned int
0x1800160fb  mov     edx, 1025h; void *
0x180016100  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016106  mov     rcx, [rbp+38h]; this
0x18001610a  lea     rax, aUnableToCastTo_2; "Unable to cast to 'uint32_t' because bu"...
0x180016111  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016116  mov     r9d, 0C0000023h; char *
0x18001611c  mov     r8, rdi; unsigned int
0x18001611f  mov     edx, 1016h; void *
0x180016124  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001612a  mov     rcx, [rbp+38h]; this
0x18001612e  lea     rax, aUnableToCastTo_7; "Unable to cast to 'int32_t' because buf"...
0x180016135  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001613a  mov     r9d, 0C0000023h; char *
0x180016140  mov     r8, rdi; unsigned int
0x180016143  mov     edx, 1007h; void *
0x180016148  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001614e  mov     rcx, [rbp+38h]; this
0x180016152  lea     rax, aUnableToCastTo_12; "Unable to cast to 'bool' because buffer"...
0x180016159  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001615e  mov     r9d, 0C0000023h; char *
0x180016164  mov     r8, rdi; unsigned int
0x180016167  mov     edx, 0FF8h; void *
0x18001616c  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016172  mov     rcx, [rbp+38h]; this
0x180016176  lea     rax, aUnableToCastTo_1; "Unable to cast to 'float' because buffe"...
0x18001617d  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016182  mov     r9d, 0C0000023h; char *
0x180016188  mov     r8, rdi; unsigned int
0x18001618b  mov     edx, 1043h; void *
0x180016190  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016196  mov     rcx, [rbp+38h]; this
0x18001619a  lea     rax, aUnableToCastTo_15; "Unable to cast to 'CLSID' because buffe"...
0x1800161a1  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800161a6  mov     r9d, 0C0000023h; char *
0x1800161ac  mov     r8, rdi; unsigned int
0x1800161af  mov     edx, 1061h; void *
0x1800161b4  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800161ba  mov     ecx, 80070057h
0x1800161bf  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800161c4  mov     r9d, eax; char *
0x1800161c7  mov     rcx, [rbp+38h]; this
0x1800161cb  mov     dword ptr [rsp+50h+var_28], edx; char *
0x1800161cf  lea     rax, aUnsupportedPro; "Unsupported property type: %d"
0x1800161d6  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800161db  mov     r8, rdi; unsigned int
0x1800161de  mov     edx, 108Bh; void *
0x1800161e3  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800161e9  mov     r9d, 8007000Eh; char *
0x1800161ef  mov     r8, rdi; unsigned int
0x1800161f2  mov     edx, 1070h; void *
0x1800161f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800161fd  mov     rcx, [rbp+38h]; this
0x180016201  lea     rax, aUnableReadBlob; "Unable read BLOB data because buffer is"...
0x180016208  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001620d  mov     r9d, 0C0000023h; char *
0x180016213  mov     r8, rdi; unsigned int
0x180016216  mov     edx, 107Eh; void *
0x18001621b  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016221  mov     rcx, [rbp+38h]; this
0x180016225  lea     rax, aUnableToMoveTo_0; "Unable to move to next RDPIDD_PROPERTY_"...
0x18001622c  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016231  mov     r9d, 0C0000023h; char *
0x180016237  mov     r8, rdi; unsigned int
0x18001623a  mov     edx, 10B2h; void *
0x18001623f  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180016245  mov     rcx, [rbp+38h]; this
0x180016249  lea     rax, aRdpiddProperty; "RDPIDD_PROPERTY_BAG_ENTRY structure is "...
0x180016250  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016255  mov     r9d, 0C0000023h; char *
0x18001625b  mov     r8, rdi; unsigned int
0x18001625e  mov     edx, 109Eh; void *
0x180016263  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
