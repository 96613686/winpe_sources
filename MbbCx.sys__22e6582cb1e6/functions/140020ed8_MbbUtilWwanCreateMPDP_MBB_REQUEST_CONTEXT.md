# MbbUtilWwanCreateMPDP(_MBB_REQUEST_CONTEXT *)

- ea: `0x140020ed8`
- end: `0x1400212e3`
- name: `?MbbUtilWwanCreateMPDP@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, __int64, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014b10`

## callees

- `0x140001300`
- `0x140001db8`
- `0x1400099cc`
- `0x14001f25c`
- `0x140020ed8`
- `0x140047e50`
- `0x140047e90`

## string_xrefs

- `0x1400210cf`: `MbbCxMbxDeviceCreateAdapter`
- `0x140021267`: `MbbCxCompleted`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanCreateMPDP(struct _MBB_REQUEST_CONTEXT *a1, __int64 a2, int a3, int a4)
{
  __int64 *v4; // rax
  __int64 v6; // rdi
  int v7; // ebx
  __int64 *v8; // rax
  __int64 v9; // rcx
  MbxDevice *v10; // rax
  int v11; // r8d
  int v12; // r9d
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r14
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rcx
  int v20; // [rsp+50h] [rbp-9h] BYREF
  int v21; // [rsp+54h] [rbp-5h] BYREF
  int v22; // [rsp+58h] [rbp-1h] BYREF
  struct NETADAPTER__ *v23; // [rsp+60h] [rbp+7h] BYREF
  const wchar_t *v24; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v25; // [rsp+70h] [rbp+17h] BYREF
  __int128 v26; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v27; // [rsp+88h] [rbp+2Fh] BYREF

  v4 = (__int64 *)*((_QWORD *)a1 + 6);
  v23 = 0;
  v6 = *v4;
  if ( *(_DWORD *)(*v4 + 1136) < *(_DWORD *)(*v4 + 1152) )
  {
    v10 = (MbxDevice *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
                         WdfDriverGlobals,
                         *(_QWORD *)(v6 + 1160),
                         off_14005DF70);
    v7 = MbxDevice::CreateAdapter(v10, &v23, 0);
    if ( v7 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct NETADAPTER__ *, __int64 *))(WdfFunctions_01031 + 1616))(
              WdfDriverGlobals,
              v23,
              off_14005DF38)
          + 24;
      MbbUtilIndicateMPDPState(a1, v7, (struct _MINIPORT_INTERFACE_CONTEXT *)v15);
      v7 = 65537;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          3,
          100,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          *(_DWORD *)(v15 + 68));
      if ( (unsigned int)dword_14005E0C8 > 5
        && (qword_14005E0D8 & 0x400000000000LL) != 0
        && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
      {
        v22 = *(_DWORD *)(v15 + 68);
        v21 = *(_DWORD *)(v6 + 1136);
        *(_QWORD *)&v26 = v15 + 40;
        v18 = **(_QWORD **)(v6 + 1144);
        v24 = L"MbbCxCompleted";
        v25 = (const wchar_t *)(v18 + 40);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v18 + 40,
          (unsigned int)byte_14005891B,
          v16,
          v17,
          (__int64)&v20,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v26,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
    else
    {
      v27 = 0;
      if ( (unsigned int)dword_14005E0C8 > 5
        && (qword_14005E0D8 & 0x400000000000LL) != 0
        && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
      {
        v21 = *(_DWORD *)(v6 + 1136);
        v25 = (const wchar_t *)&v27;
        v13 = *(__int64 **)(v6 + 1144);
        v22 = 0;
        v14 = *v13;
        *(_QWORD *)&v26 = L"MbbCxMbxDeviceCreateAdapter";
        v24 = (const wchar_t *)(v14 + 40);
        v20 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14 + 40,
          (unsigned int)word_140058B6A,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v26,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v22);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          99,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v7);
      if ( v23 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        3,
        98,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        *((_DWORD *)a1 + 4));
    v7 = -1073741637;
    v26 = 0;
    if ( (unsigned int)dword_14005E0C8 > 5
      && (qword_14005E0D8 & 0x400000000000LL) != 0
      && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
    {
      v21 = *(_DWORD *)(v6 + 1136);
      v23 = (struct NETADAPTER__ *)&v26;
      v8 = *(__int64 **)(v6 + 1144);
      v20 = 0;
      v9 = *v8;
      v25 = L"MbbCxOnLimitMaxSupportedContexts";
      v24 = (const wchar_t *)(v9 + 40);
      v22 = -1073741637;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9 + 40,
        (unsigned int)byte_1400589ED,
        a3,
        a4,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140020ed8  mov     [rsp-8+arg_8], rbx
0x140020edd  mov     [rsp-8+arg_10], rsi
0x140020ee2  push    rbp
0x140020ee3  push    rdi
0x140020ee4  push    r14
0x140020ee6  lea     rbp, [rsp-47h]
0x140020eeb  sub     rsp, 0A0h
0x140020ef2  mov     rax, cs:__security_cookie
0x140020ef9  xor     rax, rsp
0x140020efc  mov     [rbp+57h+var_18], rax
0x140020f00  mov     rax, [rcx+30h]
0x140020f04  mov     rsi, rcx
0x140020f07  mov     [rbp+57h+var_50], 0
0x140020f0f  mov     rdi, [rax]
0x140020f12  mov     eax, [rdi+480h]
0x140020f18  cmp     [rdi+470h], eax
0x140020f1e  jb      loc_140021023
0x140020f24  lea     rax, WPP_RECORDER_INITIALIZED
0x140020f2b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020f32  jz      short loc_140020F63
0x140020f34  mov     eax, [rcx+10h]
0x140020f37  mov     r9d, 62h ; 'b'
0x140020f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f44  mov     dl, 2
0x140020f46  mov     dword ptr [rsp+0B0h+var_88], eax
0x140020f4a  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140020f51  mov     [rsp+0B0h+var_90], rax
0x140020f56  lea     r8d, [r9-5Fh]
0x140020f5a  mov     rcx, [rcx+40h]
0x140020f5e  call    WPP_RECORDER_SF_d
0x140020f63  mov     eax, cs:dword_14005E0C8
0x140020f69  xorps   xmm0, xmm0
0x140020f6c  mov     ebx, 0C00000BBh
0x140020f71  movups  [rbp+57h+var_38], xmm0
0x140020f75  cmp     eax, 5
0x140020f78  jbe     loc_1400212BC
0x140020f7e  mov     rdx, cs:qword_14005E0E0
0x140020f85  mov     rcx, 400000000000h
0x140020f8f  mov     rax, cs:qword_14005E0D8
0x140020f96  test    rcx, rax
0x140020f99  jz      loc_1400212BC
0x140020f9f  mov     rax, rdx
0x140020fa2  and     rax, rcx
0x140020fa5  cmp     rax, rdx
0x140020fa8  jnz     loc_1400212BC
0x140020fae  mov     eax, [rdi+470h]
0x140020fb4  lea     rdx, byte_1400589ED
0x140020fbb  mov     [rbp+57h+var_5C], eax
0x140020fbe  lea     rax, [rbp+57h+var_38]
0x140020fc2  mov     [rbp+57h+var_50], rax
0x140020fc6  mov     rax, [rdi+478h]
0x140020fcd  mov     [rbp+57h+var_60], 0
0x140020fd4  mov     rcx, [rax]
0x140020fd7  lea     rax, aMbbcxonlimitma
0x140020fde  mov     [rbp+57h+var_40], rax
0x140020fe2  add     rcx, 28h ; '('
0x140020fe6  lea     rax, [rbp+57h+var_60]
0x140020fea  mov     [rbp+57h+var_48], rcx
0x140020fee  mov     [rsp+0B0h+var_68], rax
0x140020ff3  lea     rax, [rbp+57h+var_5C]
0x140020ff7  mov     [rsp+0B0h+var_70], rax
0x140020ffc  lea     rax, [rbp+57h+var_50]
0x140021000  mov     [rsp+0B0h+var_78], rax
0x140021005  lea     rax, [rbp+57h+var_48]
0x140021009  mov     [rsp+0B0h+var_80], rax
0x14002100e  lea     rax, [rbp+57h+var_40]
0x140021012  mov     [rsp+0B0h+var_88], rax
0x140021017  lea     rax, [rbp+57h+var_58]
0x14002101b  mov     [rbp+57h+var_58], ebx
0x14002101e  jmp     loc_1400212B2
0x140021023  mov     rax, cs:WdfFunctions_01031
0x14002102a  mov     r8, cs:off_14005DF70
0x140021031  mov     rdx, [rdi+488h]
0x140021038  mov     rcx, cs:WdfDriverGlobals
0x14002103f  mov     rax, [rax+650h]
0x140021046  call    _guard_dispatch_icall
0x14002104b  xor     r8d, r8d; bool
0x14002104e  lea     rdx, [rbp+57h+var_50]; struct NETADAPTER__ **
0x140021052  mov     rcx, rax; this
0x140021055  call    ?CreateAdapter@MbxDevice@@QEAAJPEAPEAUNETADAPTER__@@_N@Z
0x14002105a  mov     ebx, eax
0x14002105c  test    eax, eax
0x14002105e  jns     loc_140021188
0x140021064  mov     eax, cs:dword_14005E0C8
0x14002106a  xorps   xmm0, xmm0
0x14002106d  movups  [rbp+57h+var_28], xmm0
0x140021071  cmp     eax, 5
0x140021074  jbe     loc_140021120
0x14002107a  mov     rdx, cs:qword_14005E0E0
0x140021081  mov     rcx, 400000000000h
0x14002108b  mov     rax, cs:qword_14005E0D8
0x140021092  test    rcx, rax
0x140021095  jz      loc_140021120
0x14002109b  mov     rax, rdx
0x14002109e  and     rax, rcx
0x1400210a1  cmp     rax, rdx
0x1400210a4  jnz     short loc_140021120
0x1400210a6  mov     eax, [rdi+470h]
0x1400210ac  lea     rdx, word_140058B6A
0x1400210b3  mov     [rbp+57h+var_5C], eax
0x1400210b6  lea     rax, [rbp+57h+var_28]
0x1400210ba  mov     [rbp+57h+var_40], rax
0x1400210be  mov     rax, [rdi+478h]
0x1400210c5  mov     [rbp+57h+var_58], 0
0x1400210cc  mov     rcx, [rax]
0x1400210cf  lea     rax, aMbbcxmbxdevice
0x1400210d6  mov     qword ptr [rbp+57h+var_38], rax
0x1400210da  add     rcx, 28h ; '('
0x1400210de  lea     rax, [rbp+57h+var_58]
0x1400210e2  mov     [rbp+57h+var_48], rcx
0x1400210e6  mov     [rsp+0B0h+var_68], rax
0x1400210eb  lea     rax, [rbp+57h+var_5C]
0x1400210ef  mov     [rsp+0B0h+var_70], rax
0x1400210f4  lea     rax, [rbp+57h+var_40]
0x1400210f8  mov     [rsp+0B0h+var_78], rax
0x1400210fd  lea     rax, [rbp+57h+var_48]
0x140021101  mov     [rsp+0B0h+var_80], rax
0x140021106  lea     rax, [rbp+57h+var_38]
0x14002110a  mov     [rsp+0B0h+var_88], rax
0x14002110f  lea     rax, [rbp+57h+var_60]
0x140021113  mov     [rsp+0B0h+var_90], rax
0x140021118  mov     [rbp+57h+var_60], ebx
0x14002111b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z
0x140021120  lea     rax, WPP_RECORDER_INITIALIZED
0x140021127  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002112e  jz      short loc_14002115C
0x140021130  mov     rcx, cs:WPP_GLOBAL_Control
0x140021137  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14002113e  mov     r9d, 63h ; 'c'
0x140021144  mov     dword ptr [rsp+0B0h+var_88], ebx
0x140021148  mov     dl, 2
0x14002114a  mov     [rsp+0B0h+var_90], rax
0x14002114f  mov     rcx, [rcx+40h]
0x140021153  lea     r8d, [r9-62h]
0x140021157  call    WPP_RECORDER_SF_d
0x14002115c  mov     rdx, [rbp+57h+var_50]
0x140021160  test    rdx, rdx
0x140021163  jz      loc_1400212BC
0x140021169  mov     rax, cs:WdfFunctions_01031
0x140021170  mov     rcx, cs:WdfDriverGlobals
0x140021177  mov     rax, [rax+680h]
0x14002117e  call    _guard_dispatch_icall
0x140021183  jmp     loc_1400212BC
0x140021188  mov     rax, cs:WdfFunctions_01031
0x14002118f  mov     r8, cs:off_14005DF38
0x140021196  mov     rdx, [rbp+57h+var_50]
0x14002119a  mov     rcx, cs:WdfDriverGlobals
0x1400211a1  mov     rax, [rax+650h]
0x1400211a8  call    _guard_dispatch_icall
0x1400211ad  mov     edx, ebx; int
0x1400211af  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x1400211b2  lea     r14, [rax+18h]
0x1400211b6  mov     r8, r14; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400211b9  call    ?MbbUtilIndicateMPDPState@@YAXPEAU_MBB_REQUEST_CONTEXT@@HPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z
0x1400211be  mov     ebx, 10001h
0x1400211c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400211ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400211d1  jz      short loc_140021203
0x1400211d3  mov     eax, [r14+44h]
0x1400211d7  mov     r9d, 64h ; 'd'
0x1400211dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211e4  mov     dl, 4
0x1400211e6  mov     dword ptr [rsp+0B0h+var_88], eax
0x1400211ea  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x1400211f1  mov     [rsp+0B0h+var_90], rax
0x1400211f6  lea     r8d, [r9-61h]
0x1400211fa  mov     rcx, [rcx+40h]
0x1400211fe  call    WPP_RECORDER_SF_d
0x140021203  mov     eax, cs:dword_14005E0C8
0x140021209  cmp     eax, 5
0x14002120c  jbe     loc_1400212BC
0x140021212  mov     rdx, cs:qword_14005E0E0
0x140021219  mov     rcx, 400000000000h
0x140021223  mov     rax, cs:qword_14005E0D8
0x14002122a  test    rcx, rax
0x14002122d  jz      loc_1400212BC
0x140021233  mov     rax, rdx
0x140021236  and     rax, rcx
0x140021239  cmp     rax, rdx
0x14002123c  jnz     short loc_1400212BC
0x14002123e  mov     eax, [r14+44h]
0x140021242  lea     rdx, byte_14005891B
0x140021249  mov     [rbp+57h+var_58], eax
0x14002124c  mov     eax, [rdi+470h]
0x140021252  mov     [rbp+57h+var_5C], eax
0x140021255  lea     rax, [r14+28h]
0x140021259  mov     qword ptr [rbp+57h+var_38], rax
0x14002125d  mov     rax, [rdi+478h]
0x140021264  mov     rcx, [rax]
0x140021267  lea     rax, aMbbcxcompleted
0x14002126e  mov     [rbp+57h+var_48], rax
0x140021272  add     rcx, 28h ; '('
0x140021276  lea     rax, [rbp+57h+var_58]
0x14002127a  mov     [rbp+57h+var_40], rcx
0x14002127e  mov     [rsp+0B0h+var_68], rax
0x140021283  lea     rax, [rbp+57h+var_5C]
0x140021287  mov     [rsp+0B0h+var_70], rax
0x14002128c  lea     rax, [rbp+57h+var_38]
0x140021290  mov     [rsp+0B0h+var_78], rax
0x140021295  lea     rax, [rbp+57h+var_40]
0x140021299  mov     [rsp+0B0h+var_80], rax
0x14002129e  lea     rax, [rbp+57h+var_48]
0x1400212a2  mov     [rsp+0B0h+var_88], rax
0x1400212a7  lea     rax, [rbp+57h+var_60]
0x1400212ab  mov     [rbp+57h+var_60], 0
0x1400212b2  mov     [rsp+0B0h+var_90], rax
0x1400212b7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z
0x1400212bc  mov     eax, ebx
0x1400212be  mov     rcx, [rbp+57h+var_18]
0x1400212c2  xor     rcx, rsp; StackCookie
0x1400212c5  call    __security_check_cookie
0x1400212ca  lea     r11, [rsp+0B0h+var_10]
0x1400212d2  mov     rbx, [r11+28h]
0x1400212d6  mov     rsi, [r11+30h]
0x1400212da  mov     rsp, r11
0x1400212dd  pop     r14
0x1400212df  pop     rdi
0x1400212e0  pop     rbp
0x1400212e1  retn
```
