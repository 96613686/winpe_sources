# BaseProvider::_IsRcsSupportedForRecipient(IPOutlookApp3 *,Messaging::SContactInfo const &,ComposeData const &,int *)

- ea: `0x180066ee0`
- end: `0x180067130`
- name: `?_IsRcsSupportedForRecipient@BaseProvider@@MEAAJPEAUIPOutlookApp3@@AEBUSContactInfo@Messaging@@AEBUComposeData@@PEAH@Z`
- size: `592`
- prototype: `int(BaseProvider *__hidden this, struct IPOutlookApp3 *, const struct Messaging::SContactInfo *, const struct ComposeData *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x1800660c8`
- `0x1800668e8`
- `0x180066ee0`
- `0x1800676a4`
- `0x1800b9ea0`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `PhoneUtil!GetTelUriFromDialString` at `0x180067073`
- `PhoneUtil!GetTelUriFromDialString` at `0x180067073`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180067018`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180067018`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180067035`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180067035`

## pseudocode

```c
__int64 __fastcall BaseProvider::_IsRcsSupportedForRecipient(
        BaseProvider *this,
        struct IPOutlookApp3 *a2,
        const struct Messaging::SContactInfo *a3,
        const struct ComposeData *a4,
        int *a5)
{
  __int64 v7; // rcx
  int v8; // eax
  BaseProvider *v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // rax
  int DefaultOutgoingLine; // eax
  unsigned int v14; // r8d
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  struct IItem2 *v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h]
  _OWORD v20[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[128]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[96]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v24[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  v16 = 0;
  *a5 = 0;
  v7 = *((_QWORD *)this + 6);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v7 + 24LL))(v7, *((_QWORD *)a3 + 1), &v16);
    if ( v8 < 0 )
      Log_HREvent_41(v8);
    goto LABEL_17;
  }
  memset(v20, 0, sizeof(v20));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v20);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v20,
                           *(_QWORD *)(v10 + 8)) )
  {
    v11 = -2147024882;
    Log_HREvent_41(-2147024882);
LABEL_13:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v20);
    return v11;
  }
  v18 = 0;
  v19 = 0;
  if ( (int)FindContactByPhoneNumber(a2, v20, &v18, 0) < 0 )
  {
    v16 = 0;
  }
  else
  {
    v12 = *(_QWORD *)a2;
    v17 = 0;
    DefaultOutgoingLine = (*(__int64 (__fastcall **)(struct IPOutlookApp3 *, __int64 *, struct IItem2 **))(v12 + 120))(
                            a2,
                            &v18,
                            &v17);
    v11 = DefaultOutgoingLine;
    if ( DefaultOutgoingLine < 0 )
      goto LABEL_12;
    v21 = 0;
    memset_0(v22, 0, 0x13Cu);
    DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v21);
    v11 = DefaultOutgoingLine;
    if ( DefaultOutgoingLine < 0
      || (DefaultOutgoingLine = PhoneGetProviderLineServiceInfo(&v21, v22),
          v11 = DefaultOutgoingLine,
          DefaultOutgoingLine < 0)
      || (memset_0(v24, 0, sizeof(v24)),
          DefaultOutgoingLine = GetTelUriFromDialString(*(const unsigned __int16 **)&v20[0], v23, v24, 0x40u),
          v11 = DefaultOutgoingLine,
          DefaultOutgoingLine < 0)
      || (DefaultOutgoingLine = GetContactCapabilities(v17, v24, v14, (enum RCSeState *)&v16),
          v11 = DefaultOutgoingLine,
          DefaultOutgoingLine < 0) )
    {
LABEL_12:
      Log_HREvent_41(DefaultOutgoingLine);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
      goto LABEL_13;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v20);
LABEL_17:
  *a5 = (v16 & 0x20) != 0 && ((v16 & 0x40) != 0 || !(unsigned int)BaseProvider::_ComposeDataHasMultimedia(v9, a4));
  return 0;
}

```

## disassembly

```asm
0x180066ee0  push    rbp
0x180066ee2  push    rbx
0x180066ee3  push    rsi
0x180066ee4  push    rdi
0x180066ee5  lea     rbp, [rsp-158h]
0x180066eed  sub     rsp, 258h
0x180066ef4  mov     rax, cs:__security_cookie
0x180066efb  xor     rax, rsp
0x180066efe  mov     [rbp+170h+var_30], rax
0x180066f05  mov     rdi, [rbp+170h+arg_20]
0x180066f0c  mov     rsi, r9
0x180066f0f  mov     r9, r8
0x180066f12  mov     [rsp+270h+var_240], 0
0x180066f1a  mov     rbx, rdx
0x180066f1d  mov     dword ptr [rdi], 0
0x180066f23  mov     rcx, [rcx+30h]
0x180066f27  test    rcx, rcx
0x180066f2a  jz      short loc_180066F5D
0x180066f2c  mov     rax, [rcx]
0x180066f2f  lea     r8, [rsp+270h+var_240]
0x180066f34  mov     rdx, [r9+8]
0x180066f38  mov     rax, [rax+18h]
0x180066f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f41  test    eax, eax
0x180066f43  jns     loc_1800670EB
0x180066f49  xor     edx, edx
0x180066f4b  mov     r9d, 3D7h
0x180066f51  mov     ecx, eax; int
0x180066f53  call    Log_HREvent_41
0x180066f58  jmp     loc_1800670EB
0x180066f5d  xorps   xmm0, xmm0
0x180066f60  lea     rcx, [rsp+270h+var_220]
0x180066f65  movups  [rsp+270h+var_220], xmm0
0x180066f6a  movups  [rsp+270h+var_210], xmm0
0x180066f6f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180066f74  mov     rdx, [r8+8]
0x180066f78  lea     rcx, [rsp+270h+var_220]
0x180066f7d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180066f82  test    al, al
0x180066f84  jnz     short loc_180066F9F
0x180066f86  mov     ebx, 8007000Eh
0x180066f8b  xor     edx, edx
0x180066f8d  mov     ecx, ebx; int
0x180066f8f  mov     r9d, 3DFh
0x180066f95  call    Log_HREvent_41
0x180066f9a  jmp     loc_1800670BF
0x180066f9f  xor     eax, eax
0x180066fa1  lea     r8, [rsp+270h+var_230]
0x180066fa6  xor     r9d, r9d
0x180066fa9  mov     [rsp+270h+var_230], rax
0x180066fae  lea     rdx, [rsp+270h+var_220]
0x180066fb3  mov     [rsp+270h+var_228], eax
0x180066fb7  mov     rcx, rbx
0x180066fba  call    ?FindContactByPhoneNumber@@YAJPEAUIPOutlookApp3@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAUOLITEMID@@PEAK@Z; FindContactByPhoneNumber(IPOutlookApp3 *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,OLITEMID *,ulong *)
0x180066fbf  test    eax, eax
0x180066fc1  js      loc_1800670D9
0x180066fc7  mov     rax, [rbx]
0x180066fca  lea     r8, [rsp+270h+var_238]
0x180066fcf  lea     rdx, [rsp+270h+var_230]
0x180066fd4  mov     [rsp+270h+var_238], 0
0x180066fdd  mov     rcx, rbx
0x180066fe0  mov     rax, [rax+78h]
0x180066fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fe9  mov     ebx, eax
0x180066feb  test    eax, eax
0x180066fed  jns     short loc_180066FFA
0x180066fef  mov     r9d, 3E5h
0x180066ff5  jmp     loc_1800670A9
0x180066ffa  xorps   xmm0, xmm0
0x180066ffd  lea     rcx, [rbp+170h+var_1F0]; void *
0x180067001  xor     edx, edx; Val
0x180067003  mov     r8d, 13Ch; Size
0x180067009  movups  [rsp+270h+var_200], xmm0
0x18006700e  call    memset_0
0x180067013  lea     rcx, [rsp+270h+var_200]
0x180067018  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x18006701e  mov     ebx, eax
0x180067020  test    eax, eax
0x180067022  jns     short loc_18006702C
0x180067024  mov     r9d, 3E9h
0x18006702a  jmp     short loc_1800670A9
0x18006702c  lea     rdx, [rbp+170h+var_1F0]
0x180067030  lea     rcx, [rsp+270h+var_200]
0x180067035  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x18006703b  mov     ebx, eax
0x18006703d  test    eax, eax
0x18006703f  jns     short loc_180067049
0x180067041  mov     r9d, 3EAh
0x180067047  jmp     short loc_1800670A9
0x180067049  xor     edx, edx; Val
0x18006704b  lea     rcx, [rbp+170h+var_B0]; void *
0x180067052  mov     r8d, 80h; Size
0x180067058  call    memset_0
0x18006705d  mov     rcx, qword ptr [rsp+270h+var_220]
0x180067062  lea     r8, [rbp+170h+var_B0]
0x180067069  mov     r9d, 40h ; '@'
0x18006706f  lea     rdx, [rbp+170h+var_170]
0x180067073  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x180067079  mov     ebx, eax
0x18006707b  test    eax, eax
0x18006707d  jns     short loc_180067087
0x18006707f  mov     r9d, 3EDh
0x180067085  jmp     short loc_1800670A9
0x180067087  mov     rcx, [rsp+270h+var_238]; struct IItem2 *
0x18006708c  lea     r9, [rsp+270h+var_240]; enum RCSeState *
0x180067091  lea     rdx, [rbp+170h+var_B0]; unsigned __int16 *
0x180067098  call    ?GetContactCapabilities@@YAJPEAUIItem2@@PEBGKPEAW4RCSeState@@@Z; GetContactCapabilities(IItem2 *,ushort const *,ulong,RCSeState *)
0x18006709d  mov     ebx, eax
0x18006709f  test    eax, eax
0x1800670a1  jns     short loc_1800670CD
0x1800670a3  mov     r9d, 3EEh
0x1800670a9  mov     edx, 1
0x1800670ae  mov     ecx, eax; int
0x1800670b0  call    Log_HREvent_41
0x1800670b5  lea     rcx, [rsp+270h+var_238]
0x1800670ba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800670bf  lea     rcx, [rsp+270h+var_220]
0x1800670c4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800670c9  mov     eax, ebx
0x1800670cb  jmp     short loc_180067115
0x1800670cd  lea     rcx, [rsp+270h+var_238]
0x1800670d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800670d7  jmp     short loc_1800670E1
0x1800670d9  mov     [rsp+270h+var_240], 0
0x1800670e1  lea     rcx, [rsp+270h+var_220]
0x1800670e6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800670eb  test    byte ptr [rsp+270h+var_240], 20h
0x1800670f0  jz      short loc_18006710D
0x1800670f2  test    byte ptr [rsp+270h+var_240], 40h
0x1800670f7  jnz     short loc_180067105
0x1800670f9  mov     rdx, rsi; struct ComposeData *
0x1800670fc  call    ?_ComposeDataHasMultimedia@BaseProvider@@AEBAHAEBUComposeData@@@Z; BaseProvider::_ComposeDataHasMultimedia(ComposeData const &)
0x180067101  test    eax, eax
0x180067103  jnz     short loc_18006710D
0x180067105  mov     dword ptr [rdi], 1
0x18006710b  jmp     short loc_180067113
0x18006710d  mov     dword ptr [rdi], 0
0x180067113  xor     eax, eax
0x180067115  mov     rcx, [rbp+170h+var_30]
0x18006711c  xor     rcx, rsp; StackCookie
0x18006711f  call    __security_check_cookie
0x180067124  add     rsp, 258h
0x18006712b  pop     rdi
0x18006712c  pop     rsi
0x18006712d  pop     rbx
0x18006712e  pop     rbp
0x18006712f  retn
```
