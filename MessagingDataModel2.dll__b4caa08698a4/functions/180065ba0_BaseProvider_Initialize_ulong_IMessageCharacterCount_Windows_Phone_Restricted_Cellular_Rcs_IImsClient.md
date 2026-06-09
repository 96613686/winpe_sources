# BaseProvider::Initialize(ulong,IMessageCharacterCount *,Windows::Phone::Restricted::Cellular::Rcs::IImsClient *)

- ea: `0x180065ba0`
- end: `0x180065f56`
- name: `?Initialize@BaseProvider@@UEAAJKPEAVIMessageCharacterCount@@PEAUIImsClient@Rcs@Cellular@Restricted@Phone@Windows@@@Z`
- size: `950`
- prototype: `int(BaseProvider *__hidden this, unsigned int, struct IMessageCharacterCount *, struct Windows::Phone::Restricted::Cellular::Rcs::IImsClient *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067340`

## callees

- `0x180003e00`
- `0x180005c50`
- `0x1800065c8`
- `0x180008870`
- `0x18002416c`
- `0x180026898`
- `0x18004eab0`
- `0x18005bc80`
- `0x180062630`
- `0x1800652f4`
- `0x180065488`
- `0x180065ba0`
- `0x1800660c8`
- `0x180067780`
- `0x18006867c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065c30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180065c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065c4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180065c01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180065c01`
- `PhoneUtil!CellularApiHelper_CreateInstance` at `0x180065ca4`
- `PhoneUtil!CellularApiHelper_CreateInstance` at `0x180065ca4`

## pseudocode

```c
__int64 __fastcall BaseProvider::Initialize(
        BaseProvider *this,
        unsigned int a2,
        struct IMessageCharacterCount *a3,
        struct IUnknown *a4)
{
  struct IUnknown **v5; // rcx
  int Instance; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v11; // eax
  struct IMessagingMultiSimConverter **v12; // r14
  int InstanceWithPhoneOM; // eax
  __int64 v14; // rdx
  struct IMessagingMultiSimConverter *v15; // rcx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  _QWORD *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rbx
  struct IUnknown *v24; // rdx
  struct IUnknown *v25; // r15
  _QWORD v27[2]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v29[4]; // [rsp+60h] [rbp-29h] BYREF
  int v30; // [rsp+64h] [rbp-25h] BYREF
  struct IUnknown *v31; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-19h] BYREF
  __int16 v33; // [rsp+80h] [rbp-9h] BYREF
  __int64 v34; // [rsp+82h] [rbp-7h]
  int v35; // [rsp+8Ah] [rbp+1h]
  __int16 v36; // [rsp+8Eh] [rbp+5h]

  *((_DWORD *)this + 2) = a2;
  v5 = (struct IUnknown **)((char *)this + 80);
  if ( *v5 != a4 )
    ATL::AtlComPtrAssign(v5, a4);
  Instance = CoCreateInstance(
               &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
               0,
               0x17u,
               &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
               (LPVOID *)this + 9);
  if ( Instance < 0 )
    goto LABEL_4;
  EventW = CreateEventW(0, 1, 0, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset((char *)this + 11704, EventW);
  if ( !*((_QWORD *)this + 1463) )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  Instance = PhoneAPIAccess::Initialize((BaseProvider *)((char *)this + 11672));
  if ( Instance >= 0 )
  {
    v29[0] = 1;
    v31 = 0;
    if ( (int)GetCellularApiHelper((struct ICellularApiHelper **)&v31) < 0 )
    {
      v11 = CellularApiHelper_CreateInstance(&v31);
      Instance = v11;
      if ( v11 < 0 )
      {
        Log_HREvent_41(v11);
LABEL_44:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
        return (unsigned int)Instance;
      }
      if ( *((struct IUnknown **)this + 8) != v31 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 8, v31);
    }
    v27[0] = this;
    v12 = (struct IMessagingMultiSimConverter **)((char *)this + 40);
    v27[1] = v29;
    InstanceWithPhoneOM = MessagingMultiSimConverter_CreateInstanceWithPhoneOM((char *)this + 40);
    Instance = InstanceWithPhoneOM;
    if ( InstanceWithPhoneOM < 0 )
    {
      Log_HREvent_41(InstanceWithPhoneOM);
LABEL_17:
      tlx::_UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___::__UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___(v27);
      goto LABEL_44;
    }
    v14 = *((unsigned int *)this + 2);
    v28[1] = v29;
    v34 = 0;
    v32[0] = &v33;
    v35 = 0;
    v36 = 0;
    v33 = 0;
    v30 = 0;
    v15 = *v12;
    v32[1] = &v33;
    v28[0] = this;
    v16 = (*(__int64 (__fastcall **)(struct IMessagingMultiSimConverter *, __int64, int *, _QWORD *))(*(_QWORD *)v15 + 40LL))(
            v15,
            v14,
            &v30,
            v32);
    Instance = v16;
    if ( v16 < 0 )
      goto LABEL_19;
    v18 = v30;
    if ( v30 )
    {
      v16 = (*(__int64 (__fastcall **)(struct IMessagingMultiSimConverter *, _QWORD, char *))(*(_QWORD *)*v12 + 32LL))(
              *v12,
              *((unsigned int *)this + 2),
              (char *)this + 12);
      Instance = v16;
      if ( v16 < 0 )
        goto LABEL_19;
      v18 = v30;
    }
    v16 = MessagingSettings::Initialize(
            (BaseProvider *)((char *)this + 88),
            a2,
            (const unsigned __int16 *)(v32[0] & -(__int64)(v18 != 0)));
    Instance = v16;
    if ( v16 >= 0 )
    {
      v19 = operator new(0x28u);
      if ( v19 )
      {
        v19[2] = 0;
        *v19 = &MmsProvider::`vftable';
        v19[1] = 0;
        v19[3] = 0;
        v19[4] = 0;
      }
      else
      {
        v19 = 0;
      }
      v20 = *((_QWORD *)this + 1461);
      *((_QWORD *)this + 1461) = v19;
      if ( v20 )
        utl::default_delete<SmsProvider>::operator()();
      if ( !*((_QWORD *)this + 1461) )
        goto LABEL_31;
      v21 = operator new(0x38u);
      if ( v21 )
      {
        v21[1] = 0;
        *v21 = &SmsProvider::`vftable';
        v21[2] = 0;
        v21[3] = 0;
        v21[4] = 0;
        v21[5] = 0;
        v21[6] = 0;
      }
      else
      {
        v21 = 0;
      }
      v22 = *((_QWORD *)this + 1462);
      *((_QWORD *)this + 1462) = v21;
      if ( v22 )
        utl::default_delete<SmsProvider>::operator()();
      if ( !*((_QWORD *)this + 1462) )
      {
LABEL_31:
        Instance = -2147024882;
        v17 = -2147024882;
        goto LABEL_20;
      }
      v23 = *((_QWORD *)this + 1461);
      v24 = (struct IUnknown *)*v12;
      v25 = (struct IUnknown *)*((_QWORD *)this + 9);
      *(_DWORD *)(v23 + 16) = a2;
      *(_QWORD *)(v23 + 8) = a3;
      if ( *(struct IUnknown **)(v23 + 24) != v24 )
        ATL::AtlComPtrAssign((struct IUnknown **)(v23 + 24), v24);
      if ( *(struct IUnknown **)(v23 + 32) != v25 )
        ATL::AtlComPtrAssign((struct IUnknown **)(v23 + 32), v25);
      v16 = SmsProvider::Initialize(
              *((SmsProvider **)this + 1462),
              *v12,
              (BaseProvider *)((char *)this + 88),
              *((struct ISmStore **)this + 9),
              a2,
              (struct ICellularApiHelper *)v31,
              a3);
      Instance = v16;
      if ( v16 >= 0 )
      {
        *((_QWORD *)this + 4) = a3;
        v29[0] = 0;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
        tlx::_UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___::__UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___(v28);
        tlx::_UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___::__UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___(v27);
        Instance = 0;
        goto LABEL_44;
      }
    }
LABEL_19:
    v17 = v16;
LABEL_20:
    Log_HREvent_41(v17);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
    tlx::_UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___::__UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___(v28);
    goto LABEL_17;
  }
LABEL_4:
  Log_HREvent_41(Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180065ba0  push    rbp
0x180065ba2  push    rbx
0x180065ba3  push    rsi
0x180065ba4  push    rdi
0x180065ba5  push    r12
0x180065ba7  push    r13
0x180065ba9  push    r14
0x180065bab  push    r15
0x180065bad  lea     rbp, [rsp-1Fh]
0x180065bb2  sub     rsp, 0A8h
0x180065bb9  mov     rax, cs:__security_cookie
0x180065bc0  xor     rax, rsp
0x180065bc3  mov     [rbp+57h+var_50], rax
0x180065bc7  mov     [rcx+8], edx
0x180065bca  mov     rdi, rcx
0x180065bcd  add     rcx, 50h ; 'P'; struct IUnknown **
0x180065bd1  mov     r13, r8
0x180065bd4  mov     r12d, edx
0x180065bd7  cmp     [rcx], r9
0x180065bda  jz      short loc_180065BE4
0x180065bdc  mov     rdx, r9; struct IUnknown *
0x180065bdf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180065be4  xor     edx, edx; pUnkOuter
0x180065be6  lea     r15, [rdi+48h]
0x180065bea  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x180065bf1  mov     [rsp+0E0h+ppv], r15; ppv
0x180065bf6  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x180065bfd  lea     r8d, [rdx+17h]; dwClsContext
0x180065c01  call    cs:__imp_CoCreateInstance
0x180065c07  mov     ebx, eax
0x180065c09  test    eax, eax
0x180065c0b  jns     short loc_180065C22
0x180065c0d  mov     edx, 1
0x180065c12  lea     r9d, [rdx+47h]
0x180065c16  mov     ecx, ebx; int
0x180065c18  call    Log_HREvent_41
0x180065c1d  jmp     loc_180065F34
0x180065c22  xor     r9d, r9d; lpName
0x180065c25  xor     r8d, r8d; bInitialState
0x180065c28  xor     ecx, ecx; lpEventAttributes
0x180065c2a  lea     esi, [r9+1]
0x180065c2e  mov     edx, esi; bManualReset
0x180065c30  call    cs:__imp_CreateEventW
0x180065c36  lea     rbx, [rdi+2DB8h]
0x180065c3d  mov     rdx, rax
0x180065c40  mov     rcx, rbx
0x180065c43  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x180065c48  cmp     qword ptr [rbx], 0
0x180065c4c  jnz     short loc_180065C6B
0x180065c4e  call    cs:__imp_GetLastError
0x180065c54  mov     ebx, eax
0x180065c56  test    eax, eax
0x180065c58  jle     short loc_180065C63
0x180065c5a  movzx   ebx, ax
0x180065c5d  or      ebx, 80070000h
0x180065c63  xor     edx, edx
0x180065c65  lea     r9d, [rdx+4Bh]
0x180065c69  jmp     short loc_180065C16
0x180065c6b  lea     rcx, [rdi+2D98h]; this
0x180065c72  call    ?Initialize@PhoneAPIAccess@@QEAAJXZ; PhoneAPIAccess::Initialize(void)
0x180065c77  mov     ebx, eax
0x180065c79  test    eax, eax
0x180065c7b  jns     short loc_180065C87
0x180065c7d  mov     r9d, 4Dh ; 'M'
0x180065c83  mov     edx, esi
0x180065c85  jmp     short loc_180065C16
0x180065c87  lea     rcx, [rbp+57h+var_78]; struct ICellularApiHelper **
0x180065c8b  mov     [rbp+57h+var_80], sil
0x180065c8f  mov     [rbp+57h+var_78], 0
0x180065c97  call    ?GetCellularApiHelper@@YAJPEAPEAUICellularApiHelper@@@Z; GetCellularApiHelper(ICellularApiHelper * *)
0x180065c9c  test    eax, eax
0x180065c9e  jns     short loc_180065CD6
0x180065ca0  lea     rcx, [rbp+57h+var_78]
0x180065ca4  call    cs:__imp_CellularApiHelper_CreateInstance
0x180065caa  mov     ebx, eax
0x180065cac  test    eax, eax
0x180065cae  jns     short loc_180065CC4
0x180065cb0  mov     r9d, 54h ; 'T'
0x180065cb6  mov     edx, esi
0x180065cb8  mov     ecx, eax; int
0x180065cba  call    Log_HREvent_41
0x180065cbf  jmp     loc_180065F2B
0x180065cc4  mov     rdx, [rbp+57h+var_78]; struct IUnknown *
0x180065cc8  lea     rcx, [rdi+40h]; struct IUnknown **
0x180065ccc  cmp     [rcx], rdx
0x180065ccf  jz      short loc_180065CD6
0x180065cd1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180065cd6  lea     rax, [rbp+57h+var_80]
0x180065cda  mov     [rbp+57h+var_A0], rdi
0x180065cde  lea     r14, [rdi+28h]
0x180065ce2  mov     [rbp+57h+var_98], rax
0x180065ce6  mov     rcx, r14
0x180065ce9  call    MessagingMultiSimConverter_CreateInstanceWithPhoneOM
0x180065cee  xor     ecx, ecx
0x180065cf0  mov     ebx, eax
0x180065cf2  test    eax, eax
0x180065cf4  jns     short loc_180065D11
0x180065cf6  lea     r9d, [rcx+5Fh]
0x180065cfa  mov     edx, esi
0x180065cfc  mov     ecx, eax; int
0x180065cfe  call    Log_HREvent_41
0x180065d03  lea     rcx, [rbp+57h+var_A0]
0x180065d07  call    tlx___UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97_______UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___
0x180065d0c  jmp     loc_180065F2B
0x180065d11  mov     edx, [rdi+8]
0x180065d14  lea     rax, [rbp+57h+var_80]
0x180065d18  mov     [rbp+57h+var_88], rax
0x180065d1c  lea     r9, [rbp+57h+var_70]
0x180065d20  mov     [rbp+57h+var_5E], rcx
0x180065d24  lea     rax, [rbp+57h+var_60]
0x180065d28  mov     [rbp+57h+var_70], rax
0x180065d2c  lea     r8, [rbp+57h+var_7C]
0x180065d30  mov     [rbp+57h+var_56], ecx
0x180065d33  lea     rax, [rbp+57h+var_60]
0x180065d37  mov     [rbp+57h+var_52], cx
0x180065d3b  mov     [rbp+57h+var_60], cx
0x180065d3f  mov     [rbp+57h+var_7C], ecx
0x180065d42  mov     rcx, [r14]
0x180065d45  mov     [rbp+57h+var_68], rax
0x180065d49  mov     [rbp+57h+var_90], rdi
0x180065d4d  mov     rax, [rcx]
0x180065d50  mov     rax, [rax+28h]
0x180065d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d59  mov     ebx, eax
0x180065d5b  test    eax, eax
0x180065d5d  jns     short loc_180065D82
0x180065d5f  mov     r9d, 67h ; 'g'
0x180065d65  mov     edx, esi
0x180065d67  mov     ecx, eax; int
0x180065d69  call    Log_HREvent_41
0x180065d6e  lea     rcx, [rbp+57h+var_70]
0x180065d72  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180065d77  lea     rcx, [rbp+57h+var_90]
0x180065d7b  call    tlx___UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e_______UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___
0x180065d80  jmp     short loc_180065D03
0x180065d82  mov     eax, [rbp+57h+var_7C]
0x180065d85  test    eax, eax
0x180065d87  jz      short loc_180065DB0
0x180065d89  mov     rcx, [r14]
0x180065d8c  lea     r8, [rdi+0Ch]
0x180065d90  mov     edx, [rdi+8]
0x180065d93  mov     rax, [rcx]
0x180065d96  mov     rax, [rax+20h]
0x180065d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d9f  mov     ebx, eax
0x180065da1  test    eax, eax
0x180065da3  jns     short loc_180065DAD
0x180065da5  mov     r9d, 6Bh ; 'k'
0x180065dab  jmp     short loc_180065D65
0x180065dad  mov     eax, [rbp+57h+var_7C]
0x180065db0  neg     eax
0x180065db2  lea     rcx, [rdi+58h]; this
0x180065db6  mov     edx, r12d; unsigned int
0x180065db9  sbb     r8, r8
0x180065dbc  and     r8, [rbp+57h+var_70]; unsigned __int16 *
0x180065dc0  call    ?Initialize@MessagingSettings@@QEAAJKPEBG@Z; MessagingSettings::Initialize(ulong,ushort const *)
0x180065dc5  mov     ebx, eax
0x180065dc7  test    eax, eax
0x180065dc9  jns     short loc_180065DD3
0x180065dcb  mov     r9d, 6Eh ; 'n'
0x180065dd1  jmp     short loc_180065D65
0x180065dd3  mov     ecx, 28h ; '('; Size
0x180065dd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065ddd  xor     ebx, ebx
0x180065ddf  test    rax, rax
0x180065de2  jz      short loc_180065E00
0x180065de4  lea     rcx, ??_7MmsProvider@@6B@; const MmsProvider::`vftable'
0x180065deb  mov     [rax+10h], rbx
0x180065def  mov     [rax], rcx
0x180065df2  mov     [rax+8], rbx
0x180065df6  mov     [rax+18h], rbx
0x180065dfa  mov     [rax+20h], rbx
0x180065dfe  jmp     short loc_180065E03
0x180065e00  mov     rax, rbx
0x180065e03  mov     rdx, [rdi+2DA8h]
0x180065e0a  mov     [rdi+2DA8h], rax
0x180065e11  test    rdx, rdx
0x180065e14  jz      short loc_180065E1B
0x180065e16  call    ??R?$default_delete@VSmsProvider@@@utl@@QEBAXPEAVSmsProvider@@@Z; utl::default_delete<SmsProvider>::operator()(SmsProvider *)
0x180065e1b  cmp     [rdi+2DA8h], rbx
0x180065e22  jnz     short loc_180065E38
0x180065e24  mov     r9d, 71h ; 'q'
0x180065e2a  mov     ebx, 8007000Eh
0x180065e2f  xor     edx, edx
0x180065e31  mov     ecx, ebx
0x180065e33  jmp     loc_180065D69
0x180065e38  mov     ecx, 38h ; '8'; Size
0x180065e3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065e42  test    rax, rax
0x180065e45  jz      short loc_180065E6B
0x180065e47  lea     rcx, ??_7SmsProvider@@6B@; const SmsProvider::`vftable'
0x180065e4e  mov     [rax+8], rbx
0x180065e52  mov     [rax], rcx
0x180065e55  mov     [rax+10h], rbx
0x180065e59  mov     [rax+18h], rbx
0x180065e5d  mov     [rax+20h], rbx
0x180065e61  mov     [rax+28h], rbx
0x180065e65  mov     [rax+30h], rbx
0x180065e69  jmp     short loc_180065E6E
0x180065e6b  mov     rax, rbx
0x180065e6e  mov     rdx, [rdi+2DB0h]
0x180065e75  mov     [rdi+2DB0h], rax
0x180065e7c  test    rdx, rdx
0x180065e7f  jz      short loc_180065E86
0x180065e81  call    ??R?$default_delete@VSmsProvider@@@utl@@QEBAXPEAVSmsProvider@@@Z; utl::default_delete<SmsProvider>::operator()(SmsProvider *)
0x180065e86  cmp     [rdi+2DB0h], rbx
0x180065e8d  jnz     short loc_180065E97
0x180065e8f  mov     r9d, 74h ; 't'
0x180065e95  jmp     short loc_180065E2A
0x180065e97  mov     rbx, [rdi+2DA8h]
0x180065e9e  mov     rdx, [r14]; struct IUnknown *
0x180065ea1  mov     r15, [r15]
0x180065ea4  lea     rcx, [rbx+18h]; struct IUnknown **
0x180065ea8  mov     [rbx+10h], r12d
0x180065eac  mov     [rbx+8], r13
0x180065eb0  cmp     [rcx], rdx
0x180065eb3  jz      short loc_180065EBA
0x180065eb5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180065eba  lea     rcx, [rbx+20h]; struct IUnknown **
0x180065ebe  cmp     [rcx], r15
0x180065ec1  jz      short loc_180065ECB
0x180065ec3  mov     rdx, r15; struct IUnknown *
0x180065ec6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180065ecb  mov     rax, [rbp+57h+var_78]
0x180065ecf  lea     r8, [rdi+58h]; struct MessagingSettings *
0x180065ed3  mov     r9, [rdi+48h]; struct ISmStore *
0x180065ed7  mov     rdx, [r14]; struct IMessagingMultiSimConverter *
0x180065eda  mov     rcx, [rdi+2DB0h]; this
0x180065ee1  mov     [rsp+0E0h+var_B0], r13; struct IMessageCharacterCount *
0x180065ee6  mov     [rsp+0E0h+var_B8], rax; struct ICellularApiHelper *
0x180065eeb  mov     dword ptr [rsp+0E0h+ppv], r12d; unsigned int
0x180065ef0  call    ?Initialize@SmsProvider@@QEAAJPEAUIMessagingMultiSimConverter@@PEAVMessagingSettings@@PEAUISmStore@@KPEAUICellularApiHelper@@PEAVIMessageCharacterCount@@@Z; SmsProvider::Initialize(IMessagingMultiSimConverter *,MessagingSettings *,ISmStore *,ulong,ICellularApiHelper *,IMessageCharacterCount *)
0x180065ef5  mov     ebx, eax
0x180065ef7  test    eax, eax
0x180065ef9  jns     short loc_180065F06
0x180065efb  mov     r9d, 7Ah ; 'z'
0x180065f01  jmp     loc_180065D65
0x180065f06  lea     rcx, [rbp+57h+var_70]
0x180065f0a  mov     [rdi+20h], r13
0x180065f0e  mov     [rbp+57h+var_80], 0
0x180065f12  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180065f17  lea     rcx, [rbp+57h+var_90]
0x180065f1b  call    tlx___UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e_______UndoInGroup__lambda_776360f6d01e25700e65ea57cb11134e___
0x180065f20  lea     rcx, [rbp+57h+var_A0]
0x180065f24  call    tlx___UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97_______UndoInGroup__lambda_263e91d4cc264e6a01f668b5d22e1e97___
0x180065f29  xor     ebx, ebx
0x180065f2b  lea     rcx, [rbp+57h+var_78]
0x180065f2f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180065f34  mov     eax, ebx
0x180065f36  mov     rcx, [rbp+57h+var_50]
0x180065f3a  xor     rcx, rsp; StackCookie
0x180065f3d  call    __security_check_cookie
0x180065f42  add     rsp, 0A8h
0x180065f49  pop     r15
0x180065f4b  pop     r14
0x180065f4d  pop     r13
0x180065f4f  pop     r12
0x180065f51  pop     rdi
0x180065f52  pop     rsi
0x180065f53  pop     rbx
0x180065f54  pop     rbp
0x180065f55  retn
```
