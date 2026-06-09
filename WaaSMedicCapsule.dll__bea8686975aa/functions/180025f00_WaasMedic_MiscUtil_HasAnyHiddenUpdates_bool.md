# WaasMedic::MiscUtil::HasAnyHiddenUpdates(bool &)

- ea: `0x180025f00`
- end: `0x1800262a0`
- name: `?HasAnyHiddenUpdates@MiscUtil@WaasMedic@@SAJAEA_N@Z`
- size: `928`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003a650`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x180025f00`
- `0x18002695c`
- `0x1800271a8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f4e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800260df`
- `OLEAUT32!__imp_SysFreeString` at `0x18002614c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002623b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800260df`
- `OLEAUT32!__imp_SysFreeString` at `0x18002614c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002623b`

## string_xrefs

- `0x1800260ac`: `Checking for hidden updates against serviceId = %s`
- `0x180026211`: `get_item for updateServiceCollection failed`
- `0x18002628e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::MiscUtil::HasAnyHiddenUpdates(bool *a1)
{
  HRESULT v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // eax
  int v7; // ebx
  int HasHiddenUpdates; // edi
  int v9; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  const char *v11; // [rsp+28h] [rbp-20h]
  LPVOID v12; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  bool v15; // [rsp+70h] [rbp+28h] BYREF
  int v16; // [rsp+78h] [rbp+30h] BYREF
  __int64 v17; // [rsp+80h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+40h] BYREF

  v17 = 0;
  v13 = 0;
  v16 = 0;
  *a1 = 0;
  v12 = 0;
  v2 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         1u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v12);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v2,
      ppv);
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v12 + 56LL))(v12, &v17);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    if ( v12 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    return v4;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 72LL))(v17, &v16);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    if ( v12 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    return v4;
  }
  v7 = 0;
  if ( v16 > 0 )
  {
    do
    {
      v15 = 0;
      bstrString = 0;
      HasHiddenUpdates = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 56LL))(
                           v17,
                           (unsigned int)v7,
                           &v13);
      if ( HasHiddenUpdates < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x225,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
          (const char *)(unsigned int)HasHiddenUpdates,
          (int)"get_item for updateServiceCollection failed",
          v11);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v12 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        return (unsigned int)HasHiddenUpdates;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 120LL))(v13, &bstrString);
      HasHiddenUpdates = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
          (const char *)(unsigned int)v9,
          ppv);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v12 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        return (unsigned int)HasHiddenUpdates;
      }
      LogLevelW(4u, L"Checking for hidden updates against serviceId = %s", bstrString);
      HasHiddenUpdates = WaasMedic::MiscUtil::ServiceHasHiddenUpdates(&bstrString, &v15);
      if ( HasHiddenUpdates >= 0 && v15 )
      {
        *a1 = 1;
        if ( bstrString )
          SysFreeString(bstrString);
        goto LABEL_37;
      }
      if ( bstrString )
        SysFreeString(bstrString);
      ++v7;
    }
    while ( v7 < v16 );
    if ( HasHiddenUpdates < 0 && !*a1 )
    {
      if ( v12 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      return (unsigned int)HasHiddenUpdates;
    }
  }
LABEL_37:
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return 0;
}

```

## disassembly

```asm
0x180025f00  push    rbp
0x180025f02  push    rbx
0x180025f03  push    rsi
0x180025f04  push    rdi
0x180025f05  mov     rbp, rsp
0x180025f08  sub     rsp, 48h
0x180025f0c  mov     rsi, rcx
0x180025f0f  mov     [rbp+arg_10], 0
0x180025f17  mov     [rbp+var_10], 0
0x180025f1f  mov     [rbp+arg_8], 0
0x180025f26  mov     byte ptr [rcx], 0
0x180025f29  mov     [rbp+var_18], 0
0x180025f31  lea     rax, [rbp+var_18]
0x180025f35  mov     [rsp+48h+ppv], rax; int
0x180025f3a  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x180025f41  xor     edx, edx; pUnkOuter
0x180025f43  lea     r8d, [rdx+1]; dwClsContext
0x180025f47  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x180025f4e  call    cs:__imp_CoCreateInstance
0x180025f54  mov     rcx, [rbp+20h]; this
0x180025f58  test    eax, eax
0x180025f5a  js      loc_18002628B
0x180025f60  mov     rcx, [rbp+var_18]
0x180025f64  mov     rax, [rcx]
0x180025f67  lea     rdx, [rbp+arg_10]
0x180025f6b  mov     rax, [rax+38h]
0x180025f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f74  mov     ebx, eax
0x180025f76  test    eax, eax
0x180025f78  jns     short loc_180025FDC
0x180025f7a  mov     rcx, [rbp+20h]; this
0x180025f7e  mov     r9d, eax; char *
0x180025f81  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180025f88  mov     edx, 21Ch; void *
0x180025f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f92  nop
0x180025f93  mov     rcx, [rbp+var_18]
0x180025f97  test    rcx, rcx
0x180025f9a  jz      short loc_180025FA9
0x180025f9c  mov     rax, [rcx]
0x180025f9f  mov     rax, [rax+10h]
0x180025fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fa8  nop
0x180025fa9  mov     rcx, [rbp+var_10]
0x180025fad  test    rcx, rcx
0x180025fb0  jz      short loc_180025FBF
0x180025fb2  mov     rax, [rcx]
0x180025fb5  mov     rax, [rax+10h]
0x180025fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fbe  nop
0x180025fbf  mov     rcx, [rbp+arg_10]
0x180025fc3  test    rcx, rcx
0x180025fc6  jz      short loc_180025FD5
0x180025fc8  mov     rax, [rcx]
0x180025fcb  mov     rax, [rax+10h]
0x180025fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fd4  nop
0x180025fd5  mov     eax, ebx
0x180025fd7  jmp     loc_180026197
0x180025fdc  mov     rcx, [rbp+arg_10]
0x180025fe0  mov     rax, [rcx]
0x180025fe3  lea     rdx, [rbp+arg_8]
0x180025fe7  mov     rax, [rax+48h]
0x180025feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ff0  mov     ebx, eax
0x180025ff2  test    eax, eax
0x180025ff4  jns     short loc_180026053
0x180025ff6  mov     rcx, [rbp+20h]; this
0x180025ffa  mov     r9d, eax; char *
0x180025ffd  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026004  mov     edx, 21Dh; void *
0x180026009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002600e  nop
0x18002600f  mov     rcx, [rbp+var_18]
0x180026013  test    rcx, rcx
0x180026016  jz      short loc_180026025
0x180026018  mov     rax, [rcx]
0x18002601b  mov     rax, [rax+10h]
0x18002601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026024  nop
0x180026025  mov     rcx, [rbp+var_10]
0x180026029  test    rcx, rcx
0x18002602c  jz      short loc_18002603B
0x18002602e  mov     rax, [rcx]
0x180026031  mov     rax, [rax+10h]
0x180026035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002603a  nop
0x18002603b  mov     rcx, [rbp+arg_10]
0x18002603f  test    rcx, rcx
0x180026042  jz      short loc_180026051
0x180026044  mov     rax, [rcx]
0x180026047  mov     rax, [rax+10h]
0x18002604b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026050  nop
0x180026051  jmp     short loc_180025FD5
0x180026053  xor     ebx, ebx
0x180026055  cmp     [rbp+arg_8], ebx
0x180026058  jle     loc_180026153
0x18002605e  mov     [rbp+arg_0], 0
0x180026062  mov     [rbp+bstrString], 0
0x18002606a  mov     rcx, [rbp+arg_10]
0x18002606e  mov     rax, [rcx]
0x180026071  lea     r8, [rbp+var_10]
0x180026075  mov     edx, ebx
0x180026077  mov     rax, [rax+38h]
0x18002607b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026080  mov     edi, eax
0x180026082  test    eax, eax
0x180026084  js      loc_18002620D
0x18002608a  mov     rcx, [rbp+var_10]
0x18002608e  mov     rax, [rcx]
0x180026091  lea     rdx, [rbp+bstrString]
0x180026095  mov     rax, [rax+78h]
0x180026099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002609e  mov     edi, eax
0x1800260a0  test    eax, eax
0x1800260a2  js      loc_1800261A0
0x1800260a8  mov     r8, [rbp+bstrString]
0x1800260ac  lea     rdx, aCheckingForHid; "Checking for hidden updates against ser"...
0x1800260b3  mov     ecx, 4; unsigned __int8
0x1800260b8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800260bd  lea     rdx, [rbp+arg_0]
0x1800260c1  lea     rcx, [rbp+bstrString]
0x1800260c5  call    ?ServiceHasHiddenUpdates@MiscUtil@WaasMedic@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z; WaasMedic::MiscUtil::ServiceHasHiddenUpdates(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,bool &)
0x1800260ca  mov     edi, eax
0x1800260cc  test    eax, eax
0x1800260ce  js      short loc_1800260D6
0x1800260d0  cmp     [rbp+arg_0], 0
0x1800260d4  jnz     short loc_180026140
0x1800260d6  mov     rcx, [rbp+bstrString]; bstrString
0x1800260da  test    rcx, rcx
0x1800260dd  jz      short loc_1800260E5
0x1800260df  call    cs:__imp_SysFreeString
0x1800260e5  inc     ebx
0x1800260e7  cmp     ebx, [rbp+arg_8]
0x1800260ea  jl      loc_18002605E
0x1800260f0  test    edi, edi
0x1800260f2  jns     short loc_180026153
0x1800260f4  cmp     byte ptr [rsi], 0
0x1800260f7  jnz     short loc_180026153
0x1800260f9  mov     rcx, [rbp+var_18]
0x1800260fd  test    rcx, rcx
0x180026100  jz      short loc_18002610F
0x180026102  mov     rax, [rcx]
0x180026105  mov     rax, [rax+10h]
0x180026109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002610e  nop
0x18002610f  mov     rcx, [rbp+var_10]
0x180026113  test    rcx, rcx
0x180026116  jz      short loc_180026125
0x180026118  mov     rax, [rcx]
0x18002611b  mov     rax, [rax+10h]
0x18002611f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026124  nop
0x180026125  mov     rcx, [rbp+arg_10]
0x180026129  test    rcx, rcx
0x18002612c  jz      short loc_18002613B
0x18002612e  mov     rax, [rcx]
0x180026131  mov     rax, [rax+10h]
0x180026135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002613a  nop
0x18002613b  jmp     loc_180026284
0x180026140  mov     byte ptr [rsi], 1
0x180026143  mov     rcx, [rbp+bstrString]; bstrString
0x180026147  test    rcx, rcx
0x18002614a  jz      short loc_180026153
0x18002614c  call    cs:__imp_SysFreeString
0x180026152  nop
0x180026153  mov     rcx, [rbp+var_18]
0x180026157  test    rcx, rcx
0x18002615a  jz      short loc_180026169
0x18002615c  mov     rax, [rcx]
0x18002615f  mov     rax, [rax+10h]
0x180026163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026168  nop
0x180026169  mov     rcx, [rbp+var_10]
0x18002616d  test    rcx, rcx
0x180026170  jz      short loc_18002617F
0x180026172  mov     rax, [rcx]
0x180026175  mov     rax, [rax+10h]
0x180026179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002617e  nop
0x18002617f  mov     rcx, [rbp+arg_10]
0x180026183  test    rcx, rcx
0x180026186  jz      short loc_180026195
0x180026188  mov     rax, [rcx]
0x18002618b  mov     rax, [rax+10h]
0x18002618f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026194  nop
0x180026195  xor     eax, eax
0x180026197  add     rsp, 48h
0x18002619b  pop     rdi
0x18002619c  pop     rsi
0x18002619d  pop     rbx
0x18002619e  pop     rbp
0x18002619f  retn
0x1800261a0  mov     rcx, [rbp+20h]; this
0x1800261a4  mov     r9d, edi; char *
0x1800261a7  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800261ae  mov     edx, 227h; void *
0x1800261b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261b8  nop
0x1800261b9  mov     rcx, [rbp+bstrString]; bstrString
0x1800261bd  test    rcx, rcx
0x1800261c0  jz      short loc_1800261C9
0x1800261c2  call    cs:__imp_SysFreeString
0x1800261c8  nop
0x1800261c9  mov     rcx, [rbp+var_18]
0x1800261cd  test    rcx, rcx
0x1800261d0  jz      short loc_1800261DF
0x1800261d2  mov     rax, [rcx]
0x1800261d5  mov     rax, [rax+10h]
0x1800261d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261de  nop
0x1800261df  mov     rcx, [rbp+var_10]
0x1800261e3  test    rcx, rcx
0x1800261e6  jz      short loc_1800261F5
0x1800261e8  mov     rax, [rcx]
0x1800261eb  mov     rax, [rax+10h]
0x1800261ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261f4  nop
0x1800261f5  mov     rcx, [rbp+arg_10]
0x1800261f9  test    rcx, rcx
0x1800261fc  jz      short loc_18002620B
0x1800261fe  mov     rax, [rcx]
0x180026201  mov     rax, [rax+10h]
0x180026205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002620a  nop
0x18002620b  jmp     short loc_180026284
0x18002620d  mov     rcx, [rbp+20h]; this
0x180026211  lea     rax, aGetItemForUpda; "get_item for updateServiceCollection fa"...
0x180026218  mov     [rsp+48h+ppv], rax; int
0x18002621d  mov     r9d, edi; char *
0x180026220  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026227  mov     edx, 225h; void *
0x18002622c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026231  nop
0x180026232  mov     rcx, [rbp+bstrString]; bstrString
0x180026236  test    rcx, rcx
0x180026239  jz      short loc_180026242
0x18002623b  call    cs:__imp_SysFreeString
0x180026241  nop
0x180026242  mov     rcx, [rbp+var_18]
0x180026246  test    rcx, rcx
0x180026249  jz      short loc_180026258
0x18002624b  mov     rax, [rcx]
0x18002624e  mov     rax, [rax+10h]
0x180026252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026257  nop
0x180026258  mov     rcx, [rbp+var_10]
0x18002625c  test    rcx, rcx
0x18002625f  jz      short loc_18002626E
0x180026261  mov     rax, [rcx]
0x180026264  mov     rax, [rax+10h]
0x180026268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002626d  nop
0x18002626e  mov     rcx, [rbp+arg_10]
0x180026272  test    rcx, rcx
0x180026275  jz      short loc_180026284
0x180026277  mov     rax, [rcx]
0x18002627a  mov     rax, [rax+10h]
0x18002627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026283  nop
0x180026284  mov     eax, edi
0x180026286  jmp     loc_180026197
0x18002628b  mov     r9d, eax; char *
0x18002628e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026295  mov     edx, 1C9Bh; void *
0x18002629a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
