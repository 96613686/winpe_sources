# _GetContentTempFileStream

- ea: `0x180025074`
- end: `0x1800251bd`
- name: `_GetContentTempFileStream`
- size: `329`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int8, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024f18`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000cc8c`
- `0x1800249dc`
- `0x180025074`
- `0x18005cd60`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180025199`
- `OLEAUT32!__imp_SysFreeString` at `0x180025199`
- `OLEAUT32!__imp_SysStringLen` at `0x1800250c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800250c6`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x18002513e`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x18002513e`

## pseudocode

```c
__int64 __fastcall GetContentTempFileStream(__int64 *a1, unsigned __int8 a2, __int64 a3)
{
  __int64 v3; // rax
  unsigned int v5; // esi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  int MediaTempFilePath; // eax
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v14[2]; // [rsp+40h] [rbp-30h] BYREF

  v3 = *a1;
  v5 = a2;
  pbstr = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v3 + 72))(a1, &pbstr);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = v6;
LABEL_5:
    Log_HREvent_6(v8);
    goto LABEL_13;
  }
  if ( !SysStringLen(pbstr) )
  {
    v7 = -2147467259;
    v8 = -2147467259;
    goto LABEL_5;
  }
  memset(v14, 0, sizeof(v14));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v14);
  MediaTempFilePath = MessagingGetMediaTempFilePath((__int64)pbstr, (__int64)v14);
  v7 = MediaTempFilePath;
  if ( MediaTempFilePath >= 0 )
  {
    v12 = 0;
    v10 = CreateWrapFileNameStm(*(_QWORD *)&v14[0], 0, v5, &v12);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v10 = ATL::CComPtrBase<ChatServiceAttachment>::CopyTo(&v12, a3);
      v7 = v10;
      if ( v10 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v14);
        v7 = 0;
        goto LABEL_13;
      }
    }
    Log_HREvent_6(v10);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  }
  else
  {
    Log_HREvent_6(MediaTempFilePath);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v14);
LABEL_13:
  SysFreeString(pbstr);
  return v7;
}

```

## disassembly

```asm
0x180025074  mov     [rsp-18h+arg_18], rbx
0x180025079  push    rbp
0x18002507a  push    rsi
0x18002507b  push    rdi
0x18002507c  mov     rbp, rsp
0x18002507f  sub     rsp, 70h
0x180025083  mov     rax, cs:__security_cookie
0x18002508a  xor     rax, rsp
0x18002508d  mov     [rbp+var_10], rax
0x180025091  mov     rax, [rcx]
0x180025094  mov     rdi, r8
0x180025097  movzx   esi, dl
0x18002509a  lea     rdx, [rbp+pbstr]
0x18002509e  mov     [rbp+pbstr], 0
0x1800250a6  mov     rax, [rax+48h]
0x1800250aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250af  mov     ebx, eax
0x1800250b1  test    eax, eax
0x1800250b3  jns     short loc_1800250C2
0x1800250b5  mov     edx, 1
0x1800250ba  mov     ecx, eax
0x1800250bc  lea     r9d, [rdx+33h]
0x1800250c0  jmp     short loc_1800250DD
0x1800250c2  mov     rcx, [rbp+pbstr]; pbstr
0x1800250c6  call    cs:__imp_SysStringLen
0x1800250cc  test    eax, eax
0x1800250ce  jnz     short loc_1800250E7
0x1800250d0  mov     ebx, 80004005h
0x1800250d5  lea     r9d, [rax+37h]
0x1800250d9  mov     ecx, ebx; int
0x1800250db  xor     edx, edx
0x1800250dd  call    Log_HREvent_6
0x1800250e2  jmp     loc_180025195
0x1800250e7  xorps   xmm0, xmm0
0x1800250ea  lea     rcx, [rbp+var_30]
0x1800250ee  movups  [rbp+var_30], xmm0
0x1800250f2  movups  [rbp+var_20], xmm0
0x1800250f6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800250fb  mov     rcx, [rbp+pbstr]
0x1800250ff  lea     rdx, [rbp+var_30]
0x180025103  call    ?MessagingGetMediaTempFilePath@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; MessagingGetMediaTempFilePath(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180025108  mov     ebx, eax
0x18002510a  test    eax, eax
0x18002510c  jns     short loc_180025129
0x18002510e  mov     edx, 1
0x180025113  mov     ecx, eax; int
0x180025115  lea     r9d, [rdx+39h]
0x180025119  call    Log_HREvent_6
0x18002511e  lea     rcx, [rbp+var_30]
0x180025122  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180025127  jmp     short loc_180025195
0x180025129  mov     rcx, qword ptr [rbp+var_30]
0x18002512d  lea     r9, [rbp+var_40]
0x180025131  mov     r8d, esi
0x180025134  mov     [rbp+var_40], 0
0x18002513c  xor     edx, edx
0x18002513e  call    cs:__imp_CreateWrapFileNameStm
0x180025144  mov     ebx, eax
0x180025146  test    eax, eax
0x180025148  jns     short loc_180025167
0x18002514a  mov     r9d, 41h ; 'A'
0x180025150  mov     edx, 1
0x180025155  mov     ecx, eax; int
0x180025157  call    Log_HREvent_6
0x18002515c  lea     rcx, [rbp+var_40]
0x180025160  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025165  jmp     short loc_18002511E
0x180025167  mov     rdx, rdi
0x18002516a  lea     rcx, [rbp+var_40]
0x18002516e  call    ?CopyTo@?$CComPtrBase@VChatServiceAttachment@@@ATL@@QEAAJPEAPEAVChatServiceAttachment@@@Z; ATL::CComPtrBase<ChatServiceAttachment>::CopyTo(ChatServiceAttachment * *)
0x180025173  mov     ebx, eax
0x180025175  test    eax, eax
0x180025177  jns     short loc_180025181
0x180025179  mov     r9d, 43h ; 'C'
0x18002517f  jmp     short loc_180025150
0x180025181  lea     rcx, [rbp+var_40]
0x180025185  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002518a  lea     rcx, [rbp+var_30]
0x18002518e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180025193  xor     ebx, ebx
0x180025195  mov     rcx, [rbp+pbstr]; bstrString
0x180025199  call    cs:__imp_SysFreeString
0x18002519f  mov     eax, ebx
0x1800251a1  mov     rcx, [rbp+var_10]
0x1800251a5  xor     rcx, rsp; StackCookie
0x1800251a8  call    __security_check_cookie
0x1800251ad  mov     rbx, [rsp+70h+arg_18]
0x1800251b5  add     rsp, 70h
0x1800251b9  pop     rdi
0x1800251ba  pop     rsi
0x1800251bb  pop     rbp
0x1800251bc  retn
```
