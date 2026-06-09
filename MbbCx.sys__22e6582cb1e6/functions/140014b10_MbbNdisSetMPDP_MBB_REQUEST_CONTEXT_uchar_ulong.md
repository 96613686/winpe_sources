# MbbNdisSetMPDP(_MBB_REQUEST_CONTEXT *,uchar *,ulong *)

- ea: `0x140014b10`
- end: `0x140014d41`
- name: `?MbbNdisSetMPDP@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK@Z`
- size: `561`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001300`
- `0x1400051ac`
- `0x140014b10`
- `0x140020ed8`
- `0x1400212ec`
- `0x140047e50`
- `0x140047e90`

## string_xrefs

- `0x140014c2b`: `MbbCxCommandOnNonPhysicalInterface`
- `0x140014cc6`: `MbbCxCommandOnNonPhysicalInterface`

## pseudocode

```c
__int64 __fastcall MbbNdisSetMPDP(struct _MBB_REQUEST_CONTEXT *a1, unsigned __int8 *a2, unsigned int *a3)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rsi
  int v7; // r8d
  int v8; // r9d
  bool v9; // zf
  int *v10; // rcx
  int *v11; // rdx
  int *v13; // [rsp+20h] [rbp-39h]
  const wchar_t **v14; // [rsp+28h] [rbp-31h]
  const wchar_t **v15; // [rsp+38h] [rbp-21h]
  int *v16; // [rsp+48h] [rbp-11h]
  int v17; // [rsp+50h] [rbp-9h] BYREF
  int v18; // [rsp+54h] [rbp-5h] BYREF
  int v19; // [rsp+58h] [rbp-1h] BYREF
  const wchar_t *v20; // [rsp+60h] [rbp+7h] BYREF
  __int128 *v21; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v22; // [rsp+70h] [rbp+17h] BYREF
  __int128 v23; // [rsp+78h] [rbp+1Fh] BYREF

  v4 = *(_QWORD *)(*((_QWORD *)a1 + 53) + 40LL);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         *((_QWORD *)a1 + 13),
         off_14005DF38);
  if ( *(_DWORD *)(v6 + 92) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        105,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        *((_DWORD *)a1 + 4),
        *(_DWORD *)(v4 + 4));
    }
    v9 = *(_DWORD *)(v4 + 4) == 1;
    v23 = 0;
    if ( v9 )
    {
      if ( (unsigned int)dword_14005E0C8 <= 5 )
        return 3221225860LL;
      LODWORD(v10) = 0;
      if ( (qword_14005E0D8 & 0x400000000000LL) == 0 || (qword_14005E0E0 & 0x400000000000LL) != qword_14005E0E0 )
        return 3221225860LL;
      v17 = 0;
      v20 = (const wchar_t *)(v6 + 64);
      v11 = &dword_1400587BC;
      v19 = -1073741436;
      v21 = &v23;
      v22 = L"MbbCxCommandOnNonPhysicalInterface";
      v16 = &v17;
      v15 = &v20;
      v14 = &v22;
      v13 = &v19;
    }
    else
    {
      if ( (unsigned int)dword_14005E0C8 <= 5
        || (qword_14005E0D8 & 0x400000000000LL) == 0
        || (qword_14005E0E0 & 0x400000000000LL) != qword_14005E0E0 )
      {
        return 3221225860LL;
      }
      v19 = *(_DWORD *)(v6 + 92);
      v11 = (int *)&unk_140058718;
      v17 = -1073741436;
      v22 = (const wchar_t *)(v6 + 64);
      v21 = &v23;
      v20 = L"MbbCxCommandOnNonPhysicalInterface";
      v16 = &v19;
      v15 = &v22;
      v14 = &v20;
      v10 = &v17;
      v13 = &v17;
    }
    v18 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v10,
      (_DWORD)v11,
      v7,
      v8,
      (__int64)v13,
      (__int64)v14,
      (__int64)&v21,
      (__int64)v15,
      (__int64)&v18,
      (__int64)v16);
    return 3221225860LL;
  }
  if ( *(_DWORD *)(v4 + 4) == 1 )
    return MbbUtilWwanDeleteMPDP(a1);
  else
    return MbbUtilWwanCreateMPDP(a1, v5, v7, v8);
}

```

## disassembly

```asm
0x140014b10  push    rbp
0x140014b12  push    rbx
0x140014b13  push    rsi
0x140014b14  push    rdi
0x140014b15  lea     rbp, [rsp-3Fh]
0x140014b1a  sub     rsp, 98h
0x140014b21  mov     rax, cs:__security_cookie
0x140014b28  xor     rax, rsp
0x140014b2b  mov     [rbp+57h+var_28], rax
0x140014b2f  mov     rax, [rcx+1A8h]
0x140014b36  mov     rdi, rcx
0x140014b39  mov     rdx, [rcx+68h]
0x140014b3d  mov     r8, cs:off_14005DF38
0x140014b44  mov     rcx, cs:WdfDriverGlobals
0x140014b4b  mov     rbx, [rax+28h]
0x140014b4f  mov     rax, cs:WdfFunctions_01031
0x140014b56  mov     rax, [rax+650h]
0x140014b5d  call    _guard_dispatch_icall
0x140014b62  mov     rsi, rax
0x140014b65  cmp     dword ptr [rax+5Ch], 0
0x140014b69  jz      loc_140014D13
0x140014b6f  lea     rax, WPP_RECORDER_INITIALIZED
0x140014b76  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014b7d  jz      short loc_140014BB5
0x140014b7f  mov     ecx, [rbx+4]
0x140014b82  mov     r9d, 69h ; 'i'
0x140014b88  mov     eax, [rdi+10h]
0x140014b8b  mov     dl, 2
0x140014b8d  mov     dword ptr [rsp+0B0h+var_80], ecx
0x140014b91  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b98  mov     dword ptr [rsp+0B0h+var_88], eax
0x140014b9c  lea     r8d, [r9-66h]
0x140014ba0  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140014ba7  mov     [rsp+0B0h+var_90], rax
0x140014bac  mov     rcx, [rcx+40h]
0x140014bb0  call    WPP_RECORDER_SF_DD
0x140014bb5  cmp     dword ptr [rbx+4], 1
0x140014bb9  xorps   xmm0, xmm0
0x140014bbc  mov     eax, cs:dword_14005E0C8
0x140014bc2  mov     edi, 0C0000184h
0x140014bc7  movups  [rbp+57h+var_38], xmm0
0x140014bcb  jnz     loc_140014C71
0x140014bd1  cmp     eax, 5
0x140014bd4  jbe     loc_140014D0F
0x140014bda  mov     rdx, cs:qword_14005E0E0
0x140014be1  mov     rcx, 400000000000h
0x140014beb  mov     rax, cs:qword_14005E0D8
0x140014bf2  test    rcx, rax
0x140014bf5  jz      loc_140014D0F
0x140014bfb  mov     rax, rdx
0x140014bfe  and     rax, rcx
0x140014c01  cmp     rax, rdx
0x140014c04  jnz     loc_140014D0F
0x140014c0a  lea     rax, [rsi+40h]
0x140014c0e  mov     [rbp+57h+var_60], 0
0x140014c15  mov     [rbp+57h+var_50], rax
0x140014c19  lea     rdx, dword_1400587BC
0x140014c20  lea     rax, [rbp+57h+var_38]
0x140014c24  mov     [rbp+57h+var_58], edi
0x140014c27  mov     [rbp+57h+var_48], rax
0x140014c2b  lea     rax, aMbbcxcommandon; "MbbCxCommandOnNonPhysicalInterface"
0x140014c32  mov     [rbp+57h+var_40], rax
0x140014c36  lea     rax, [rbp+57h+var_60]
0x140014c3a  mov     [rsp+0B0h+var_68], rax
0x140014c3f  lea     rax, [rbp+57h+var_5C]
0x140014c43  mov     [rsp+0B0h+var_70], rax
0x140014c48  lea     rax, [rbp+57h+var_50]
0x140014c4c  mov     [rsp+0B0h+var_78], rax
0x140014c51  lea     rax, [rbp+57h+var_48]
0x140014c55  mov     [rsp+0B0h+var_80], rax
0x140014c5a  lea     rax, [rbp+57h+var_40]
0x140014c5e  mov     [rsp+0B0h+var_88], rax
0x140014c63  lea     rax, [rbp+57h+var_58]
0x140014c67  mov     [rsp+0B0h+var_90], rax
0x140014c6c  jmp     loc_140014D03
0x140014c71  cmp     eax, 5
0x140014c74  jbe     loc_140014D0F
0x140014c7a  mov     rdx, cs:qword_14005E0E0
0x140014c81  mov     rcx, 400000000000h
0x140014c8b  mov     rax, cs:qword_14005E0D8
0x140014c92  test    rcx, rax
0x140014c95  jz      short loc_140014D0F
0x140014c97  mov     rax, rdx
0x140014c9a  and     rax, rcx
0x140014c9d  cmp     rax, rdx
0x140014ca0  jnz     short loc_140014D0F
0x140014ca2  mov     eax, [rsi+5Ch]
0x140014ca5  lea     rcx, [rbp+57h+var_40]
0x140014ca9  mov     [rbp+57h+var_58], eax
0x140014cac  lea     rdx, unk_140058718
0x140014cb3  lea     rax, [rsi+40h]
0x140014cb7  mov     [rbp+57h+var_60], edi
0x140014cba  mov     [rbp+57h+var_40], rax
0x140014cbe  lea     rax, [rbp+57h+var_38]
0x140014cc2  mov     [rbp+57h+var_48], rax
0x140014cc6  lea     rax, aMbbcxcommandon; "MbbCxCommandOnNonPhysicalInterface"
0x140014ccd  mov     [rbp+57h+var_50], rax
0x140014cd1  lea     rax, [rbp+57h+var_58]
0x140014cd5  mov     [rsp+0B0h+var_68], rax
0x140014cda  lea     rax, [rbp+57h+var_5C]
0x140014cde  mov     [rsp+0B0h+var_70], rax
0x140014ce3  mov     [rsp+0B0h+var_78], rcx
0x140014ce8  lea     rcx, [rbp+57h+var_48]
0x140014cec  mov     [rsp+0B0h+var_80], rcx
0x140014cf1  lea     rcx, [rbp+57h+var_50]
0x140014cf5  mov     [rsp+0B0h+var_88], rcx
0x140014cfa  lea     rcx, [rbp+57h+var_60]
0x140014cfe  mov     [rsp+0B0h+var_90], rcx
0x140014d03  mov     [rbp+57h+var_5C], 0
0x140014d0a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@533@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140014d0f  mov     eax, edi
0x140014d11  jmp     short loc_140014D28
0x140014d13  cmp     dword ptr [rbx+4], 1
0x140014d17  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x140014d1a  jnz     short loc_140014D23
0x140014d1c  call    ?MbbUtilWwanDeleteMPDP@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilWwanDeleteMPDP(_MBB_REQUEST_CONTEXT *)
0x140014d21  jmp     short loc_140014D28
0x140014d23  call    ?MbbUtilWwanCreateMPDP@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilWwanCreateMPDP(_MBB_REQUEST_CONTEXT *)
0x140014d28  mov     rcx, [rbp+57h+var_28]
0x140014d2c  xor     rcx, rsp; StackCookie
0x140014d2f  call    __security_check_cookie
0x140014d34  add     rsp, 98h
0x140014d3b  pop     rdi
0x140014d3c  pop     rsi
0x140014d3d  pop     rbx
0x140014d3e  pop     rbp
0x140014d3f  retn
```
