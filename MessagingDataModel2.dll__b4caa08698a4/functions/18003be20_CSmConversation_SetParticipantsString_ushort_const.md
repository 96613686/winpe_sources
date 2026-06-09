# CSmConversation::SetParticipantsString(ushort const *)

- ea: `0x18003be20`
- end: `0x18003c0ff`
- name: `?SetParticipantsString@CSmConversation@@UEAAJPEBG@Z`
- size: `735`
- prototype: `__int64 __fastcall(CSmConversation *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000b7d4`
- `0x180032264`
- `0x18003afe4`
- `0x18003be20`
- `0x18003e8ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18003bf12`
- `msvcrt!wcstok_s` at `0x18003bf6f`
- `msvcrt!wcstok_s` at `0x18003bf12`
- `msvcrt!wcstok_s` at `0x18003bf6f`
- `msvcrt!wcsrchr` at `0x18003bf27`
- `msvcrt!wcsrchr` at `0x18003bf27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003be6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003be6d`
- `CEMAPI!HrSetOneProp` at `0x18003c09b`
- `CEMAPI!HrSetOneProp` at `0x18003c09b`

## pseudocode

```c
__int64 __fastcall CSmConversation::SetParticipantsString(CSmConversation *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  wchar_t *i; // rax
  wchar_t *v8; // rax
  int v9; // eax
  wchar_t *v10; // rbx
  int v11; // eax
  int v12; // ecx
  HRESULT MapiConversation; // eax
  LPMAPIPROP lpMapiProp; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-31h] BYREF
  struct _SPropValue Prop; // [rsp+40h] [rbp-29h] BYREF
  __int64 v18; // [rsp+58h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-9h] BYREF
  __int16 *v20; // [rsp+68h] [rbp-1h] BYREF
  __int16 *v21; // [rsp+70h] [rbp+7h]
  __int16 v22; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+7Ah] [rbp+11h]
  int v24; // [rsp+82h] [rbp+19h]
  __int16 v25; // [rsp+86h] [rbp+1Dh]
  wchar_t *String[2]; // [rsp+88h] [rbp+1Fh] BYREF
  __int16 v27; // [rsp+98h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+9Ah] [rbp+31h]
  int v29; // [rsp+A2h] [rbp+39h]
  __int16 v30; // [rsp+A6h] [rbp+3Dh]

  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
         0,
         0x17u,
         &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
         &ppv);
  v5 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent_15(v4);
    goto LABEL_22;
  }
  v28 = 0;
  v30 = 0;
  v29 = 0;
  String[0] = (wchar_t *)&v27;
  String[1] = (wchar_t *)&v27;
  v27 = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          String,
                          a2) )
  {
    Context = 0;
    for ( i = wcstok_s(String[0], &Delimiter, &Context); ; i = wcstok_s(0, &Delimiter, &Context) )
    {
      v10 = i;
      if ( !i )
        break;
      v8 = wcsrchr(i, 0x40u);
      v9 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, _QWORD, __int64, _DWORD))(*(_QWORD *)ppv + 24LL))(
             ppv,
             v10,
             (unsigned int)(v8 != 0) + 1,
             0xFFFFFFFFLL,
             0);
      v5 = v9;
      if ( v9 < 0 )
      {
        v6 = v9;
        goto LABEL_5;
      }
    }
    v18 = 0;
    ATL::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>(
      &v18,
      ppv);
    v23 = 0;
    v25 = 0;
    v20 = &v22;
    v21 = &v22;
    v22 = 0;
    v24 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int16 **))(*(_QWORD *)v18 + 96LL))(v18, &v20);
    v5 = v11;
    if ( v11 >= 0 )
    {
      if ( (unsigned __int64)(v21 - v20) < 0xFA0 )
      {
        lpMapiProp = 0;
        MapiConversation = CSmConversation::_GetMapiConversation(this, (struct IMAPIConversation **)&lpMapiProp);
        v5 = MapiConversation;
        if ( MapiConversation >= 0 )
        {
          Prop.Value = (union _PV)(unsigned __int64)v20;
          Prop.dwAlignPad = 0;
          Prop.ulPropTag = -2104426465;
          MapiConversation = HrSetOneProp(lpMapiProp, &Prop);
          v5 = MapiConversation;
          if ( MapiConversation >= 0 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v20);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(String);
            v5 = 0;
            goto LABEL_22;
          }
        }
        Log_HREvent_15(MapiConversation);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
LABEL_14:
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
        goto LABEL_6;
      }
      v5 = -2147317563;
      v12 = -2147317563;
    }
    else
    {
      v12 = v11;
    }
    Log_HREvent_15(v12);
    goto LABEL_14;
  }
  v5 = -2147024882;
  v6 = -2147024882;
LABEL_5:
  Log_HREvent_15(v6);
LABEL_6:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(String);
LABEL_22:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v5;
}

```

## disassembly

```asm
0x18003be20  mov     [rsp-8+arg_10], rbx
0x18003be25  push    rbp
0x18003be26  push    rsi
0x18003be27  push    rdi
0x18003be28  lea     rbp, [rsp-47h]
0x18003be2d  sub     rsp, 0B0h
0x18003be34  mov     rax, cs:__security_cookie
0x18003be3b  xor     rax, rsp
0x18003be3e  mov     [rbp+57h+var_18], rax
0x18003be42  mov     rdi, rdx
0x18003be45  mov     [rbp+57h+var_60], 0
0x18003be4d  xor     edx, edx; pUnkOuter
0x18003be4f  lea     rax, [rbp+57h+var_60]
0x18003be53  mov     rsi, rcx
0x18003be56  mov     [rsp+0C0h+ppv], rax; ppv
0x18003be5b  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x18003be62  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x18003be69  lea     r8d, [rdx+17h]; dwClsContext
0x18003be6d  call    cs:__imp_CoCreateInstance
0x18003be73  mov     ebx, eax
0x18003be75  test    eax, eax
0x18003be77  jns     short loc_18003BE97
0x18003be79  mov     r9d, 5F1h
0x18003be7f  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003be86  mov     edx, 1
0x18003be8b  mov     ecx, eax; int
0x18003be8d  call    Log_HREvent_15
0x18003be92  jmp     loc_18003C0D5
0x18003be97  xor     eax, eax
0x18003be99  mov     [rbp+57h+var_26], 0
0x18003bea1  mov     [rbp+57h+var_1A], ax
0x18003bea5  lea     rcx, [rbp+57h+String]
0x18003bea9  lea     rax, [rbp+57h+var_28]
0x18003bead  mov     [rbp+57h+var_1E], 0
0x18003beb4  mov     [rbp+57h+String], rax
0x18003beb8  mov     rdx, rdi
0x18003bebb  lea     rax, [rbp+57h+var_28]
0x18003bebf  mov     [rbp+57h+var_30], rax
0x18003bec3  xor     eax, eax
0x18003bec5  mov     [rbp+57h+var_28], ax
0x18003bec9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18003bece  test    al, al
0x18003bed0  jnz     short loc_18003BEFB
0x18003bed2  mov     ebx, 8007000Eh
0x18003bed7  mov     r9d, 5F4h
0x18003bedd  mov     ecx, ebx; int
0x18003bedf  xor     edx, edx
0x18003bee1  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003bee8  call    Log_HREvent_15
0x18003beed  lea     rcx, [rbp+57h+String]
0x18003bef1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003bef6  jmp     loc_18003C0D5
0x18003befb  mov     rcx, [rbp+57h+String]; String
0x18003beff  lea     r8, [rbp+57h+Context]; Context
0x18003bf03  lea     rdx, Delimiter; Delimiter
0x18003bf0a  mov     [rbp+57h+Context], 0
0x18003bf12  call    cs:__imp_wcstok_s
0x18003bf18  mov     edi, 1
0x18003bf1d  jmp     short loc_18003BF75
0x18003bf1f  mov     edx, 40h ; '@'; Ch
0x18003bf24  mov     rcx, rbx; Str
0x18003bf27  call    cs:__imp_wcsrchr
0x18003bf2d  mov     rcx, [rbp+57h+var_60]
0x18003bf31  mov     rdx, rbx
0x18003bf34  neg     rax
0x18003bf37  mov     dword ptr [rsp+0C0h+ppv], 0
0x18003bf3f  sbb     r8d, r8d
0x18003bf42  or      r9d, 0FFFFFFFFh
0x18003bf46  mov     rax, [rcx]
0x18003bf49  neg     r8d
0x18003bf4c  add     r8d, edi
0x18003bf4f  mov     rax, [rax+18h]
0x18003bf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf58  mov     ebx, eax
0x18003bf5a  test    eax, eax
0x18003bf5c  js      loc_18003C004
0x18003bf62  lea     r8, [rbp+57h+Context]; Context
0x18003bf66  xor     ecx, ecx; String
0x18003bf68  lea     rdx, Delimiter; Delimiter
0x18003bf6f  call    cs:__imp_wcstok_s
0x18003bf75  mov     rbx, rax
0x18003bf78  test    rax, rax
0x18003bf7b  jnz     short loc_18003BF1F
0x18003bf7d  mov     rdx, [rbp+57h+var_60]
0x18003bf81  lea     rcx, [rbp+57h+var_68]
0x18003bf85  mov     [rbp+57h+var_68], 0
0x18003bf8d  call    ??0?$CComQIPtr@VISmRecipientCollectionPriv@@$1?_GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>(IUnknown *)
0x18003bf92  mov     rcx, [rbp+57h+var_68]
0x18003bf96  lea     rdx, [rbp+57h+var_58]
0x18003bf9a  xor     eax, eax
0x18003bf9c  mov     [rbp+57h+var_46], 0
0x18003bfa4  mov     [rbp+57h+var_3A], ax
0x18003bfa8  lea     rax, [rbp+57h+var_48]
0x18003bfac  mov     [rbp+57h+var_58], rax
0x18003bfb0  lea     rax, [rbp+57h+var_48]
0x18003bfb4  mov     [rbp+57h+var_50], rax
0x18003bfb8  xor     eax, eax
0x18003bfba  mov     [rbp+57h+var_48], ax
0x18003bfbe  mov     [rbp+57h+var_3E], 0
0x18003bfc5  mov     rax, [rcx]
0x18003bfc8  mov     rax, [rax+60h]
0x18003bfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfd1  mov     ebx, eax
0x18003bfd3  test    eax, eax
0x18003bfd5  jns     short loc_18003C013
0x18003bfd7  mov     r9d, 608h
0x18003bfdd  mov     edx, edi
0x18003bfdf  mov     ecx, eax; int
0x18003bfe1  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003bfe8  call    Log_HREvent_15
0x18003bfed  lea     rcx, [rbp+57h+var_58]
0x18003bff1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003bff6  lea     rcx, [rbp+57h+var_68]
0x18003bffa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bfff  jmp     loc_18003BEED
0x18003c004  mov     r9d, 600h
0x18003c00a  mov     edx, edi
0x18003c00c  mov     ecx, eax
0x18003c00e  jmp     loc_18003BEE1
0x18003c013  mov     rax, [rbp+57h+var_50]
0x18003c017  sub     rax, [rbp+57h+var_58]
0x18003c01b  sar     rax, 1
0x18003c01e  cmp     rax, 0FA0h
0x18003c024  jb      short loc_18003C037
0x18003c026  mov     ebx, 800288C5h
0x18003c02b  mov     r9d, 60Ah
0x18003c031  mov     ecx, ebx
0x18003c033  xor     edx, edx
0x18003c035  jmp     short loc_18003BFE1
0x18003c037  lea     rdx, [rbp+57h+lpMapiProp]; struct IMAPIConversation **
0x18003c03b  mov     [rbp+57h+lpMapiProp], 0
0x18003c043  mov     rcx, rsi; this
0x18003c046  call    ?_GetMapiConversation@CSmConversation@@IEAAJPEAPEAUIMAPIConversation@@@Z; CSmConversation::_GetMapiConversation(IMAPIConversation * *)
0x18003c04b  mov     ebx, eax
0x18003c04d  test    eax, eax
0x18003c04f  jns     short loc_18003C075
0x18003c051  mov     r9d, 60Dh
0x18003c057  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003c05e  mov     edx, edi
0x18003c060  mov     ecx, eax; int
0x18003c062  call    Log_HREvent_15
0x18003c067  lea     rcx, [rbp+57h+lpMapiProp]
0x18003c06b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c070  jmp     loc_18003BFED
0x18003c075  mov     rax, [rbp+57h+var_58]
0x18003c079  lea     rdx, [rbp+57h+Prop]; lpProp
0x18003c07d  mov     rcx, [rbp+57h+lpMapiProp]; lpMapiProp
0x18003c081  mov     qword ptr [rbp+57h+Prop.Value], rax
0x18003c085  mov     [rbp+57h+Prop.dwAlignPad], 0
0x18003c08c  mov     qword ptr [rbp+57h+Prop.Value+8], 0
0x18003c094  mov     [rbp+57h+Prop.ulPropTag], 8291001Fh
0x18003c09b  call    cs:__imp_HrSetOneProp
0x18003c0a1  mov     ebx, eax
0x18003c0a3  test    eax, eax
0x18003c0a5  jns     short loc_18003C0AF
0x18003c0a7  mov     r9d, 613h
0x18003c0ad  jmp     short loc_18003C057
0x18003c0af  lea     rcx, [rbp+57h+lpMapiProp]
0x18003c0b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c0b8  lea     rcx, [rbp+57h+var_58]
0x18003c0bc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003c0c1  lea     rcx, [rbp+57h+var_68]
0x18003c0c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c0ca  lea     rcx, [rbp+57h+String]
0x18003c0ce  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003c0d3  xor     ebx, ebx
0x18003c0d5  lea     rcx, [rbp+57h+var_60]
0x18003c0d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c0de  mov     eax, ebx
0x18003c0e0  mov     rcx, [rbp+57h+var_18]
0x18003c0e4  xor     rcx, rsp; StackCookie
0x18003c0e7  call    __security_check_cookie
0x18003c0ec  mov     rbx, [rsp+0C0h+arg_10]
0x18003c0f4  add     rsp, 0B0h
0x18003c0fb  pop     rdi
0x18003c0fc  pop     rsi
0x18003c0fd  pop     rbp
0x18003c0fe  retn
```
