# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_RemoveToastNotifications(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180014c10`
- end: `0x180014d92`
- name: `?_RemoveToastNotifications@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG000@Z`
- size: `386`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000155c`
- `0x180001dc0`
- `0x180011e68`
- `0x180014c10`
- `0x180019010`

## string_xrefs

- `0x180014c7a`: `IncomingCallToastStatics: Remove, aumId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_RemoveToastNotifications(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // [rsp+30h] [rbp-41h]
  const unsigned __int16 **v17; // [rsp+38h] [rbp-39h]
  __int64 *v18; // [rsp+40h] [rbp-31h]
  __int64 v19; // [rsp+50h] [rbp-21h] BYREF
  const unsigned __int16 *v20; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v21[3]; // [rsp+60h] [rbp-11h] BYREF
  __int64 v22; // [rsp+78h] [rbp+7h] BYREF

  if ( (unsigned int)dword_180025038 > 4
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    v19 = 16779264;
    v21[2] = "IncomingCallToastStatics: Remove, aumId";
    v20 = a5;
    v18 = &v19;
    v17 = &v20;
    v16 = v21;
    v21[0] = a4;
    v21[1] = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      qword_180025050,
      byte_180020C55);
  }
  v9 = *(_QWORD *)this;
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64 *))(v9 + 120))(
          this,
          &v22);
  if ( v10 < 0 )
  {
    v12 = 549;
LABEL_7:
    Log_HREvent_1((unsigned int)v10, 1, v11, v12);
    v13 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return (unsigned int)v10;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, _QWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD *, const unsigned __int16 **, __int64 *))(*(_QWORD *)v22 + 80LL))(
          v22,
          a2,
          a3,
          0,
          a4,
          a5,
          v16,
          v17,
          v18);
  if ( v10 < 0 )
  {
    v12 = 551;
    goto LABEL_7;
  }
  v15 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180014c10  push    rbp
0x180014c12  push    rbx
0x180014c13  push    rsi
0x180014c14  push    rdi
0x180014c15  push    r14
0x180014c17  push    r15
0x180014c19  lea     rbp, [rsp-27h]
0x180014c1e  sub     rsp, 98h
0x180014c25  mov     rax, cs:__security_cookie
0x180014c2c  xor     rax, rsp
0x180014c2f  mov     [rbp+4Fh+var_40], rax
0x180014c33  mov     eax, cs:dword_180025038
0x180014c39  mov     rsi, r9
0x180014c3c  mov     r14, [rbp+4Fh+arg_20]
0x180014c40  mov     rdi, r8
0x180014c43  mov     r15, rdx
0x180014c46  mov     rbx, rcx
0x180014c49  cmp     eax, 4
0x180014c4c  jbe     loc_180014CD2
0x180014c52  mov     rcx, cs:qword_180025050
0x180014c59  mov     rdx, 400000000000h
0x180014c63  mov     rax, cs:qword_180025048
0x180014c6a  test    rdx, rax
0x180014c6d  jz      short loc_180014CD2
0x180014c6f  mov     rax, rcx
0x180014c72  and     rax, rdx
0x180014c75  cmp     rax, rcx
0x180014c78  jnz     short loc_180014CD2
0x180014c7a  lea     rax, aIncomingcallto; "IncomingCallToastStatics: Remove, aumId"
0x180014c81  mov     [rbp+4Fh+var_70], 1000800h
0x180014c89  mov     [rbp+4Fh+var_50], rax
0x180014c8d  lea     rdx, byte_180020C55
0x180014c94  lea     rax, [rbp+4Fh+var_70]
0x180014c98  mov     [rbp+4Fh+var_68], r14
0x180014c9c  mov     [rsp+0C0h+var_80], rax
0x180014ca1  lea     rax, [rbp+4Fh+var_68]
0x180014ca5  mov     [rsp+0C0h+var_88], rax
0x180014caa  lea     rax, [rbp+4Fh+var_60]
0x180014cae  mov     [rsp+0C0h+var_90], rax
0x180014cb3  lea     rax, [rbp+4Fh+var_58]
0x180014cb7  mov     [rsp+0C0h+var_98], rax
0x180014cbc  lea     rax, [rbp+4Fh+var_50]
0x180014cc0  mov     [rsp+0C0h+var_A0], rax
0x180014cc5  mov     [rbp+4Fh+var_60], r9
0x180014cc9  mov     [rbp+4Fh+var_58], r8
0x180014ccd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180014cd2  mov     rax, [rbx]
0x180014cd5  lea     rdx, [rbp+4Fh+var_48]
0x180014cd9  mov     rcx, rbx
0x180014cdc  mov     [rbp+4Fh+var_48], 0
0x180014ce4  mov     rax, [rax+78h]
0x180014ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ced  mov     ebx, eax
0x180014cef  test    eax, eax
0x180014cf1  jns     short loc_180014D26
0x180014cf3  mov     r9d, 225h
0x180014cf9  mov     edx, 1
0x180014cfe  mov     ecx, ebx
0x180014d00  call    Log_HREvent_1
0x180014d05  mov     rcx, [rbp+4Fh+var_48]
0x180014d09  test    rcx, rcx
0x180014d0c  jz      short loc_180014D22
0x180014d0e  mov     [rbp+4Fh+var_48], 0
0x180014d16  mov     rdx, [rcx]
0x180014d19  mov     rax, [rdx+10h]
0x180014d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d22  mov     eax, ebx
0x180014d24  jmp     short loc_180014D76
0x180014d26  mov     rcx, [rbp+4Fh+var_48]
0x180014d2a  xor     r9d, r9d
0x180014d2d  mov     [rsp+0C0h+var_98], r14
0x180014d32  mov     r8, rdi
0x180014d35  mov     rdx, r15
0x180014d38  mov     [rsp+0C0h+var_A0], rsi
0x180014d3d  mov     rax, [rcx]
0x180014d40  mov     rax, [rax+50h]
0x180014d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d49  mov     ebx, eax
0x180014d4b  test    eax, eax
0x180014d4d  jns     short loc_180014D57
0x180014d4f  mov     r9d, 227h
0x180014d55  jmp     short loc_180014CF9
0x180014d57  mov     rcx, [rbp+4Fh+var_48]
0x180014d5b  test    rcx, rcx
0x180014d5e  jz      short loc_180014D74
0x180014d60  mov     [rbp+4Fh+var_48], 0
0x180014d68  mov     rax, [rcx]
0x180014d6b  mov     rax, [rax+10h]
0x180014d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d74  xor     eax, eax
0x180014d76  mov     rcx, [rbp+4Fh+var_40]
0x180014d7a  xor     rcx, rsp; StackCookie
0x180014d7d  call    __security_check_cookie
0x180014d82  add     rsp, 98h
0x180014d89  pop     r15
0x180014d8b  pop     r14
0x180014d8d  pop     rdi
0x180014d8e  pop     rsi
0x180014d8f  pop     rbx
0x180014d90  pop     rbp
0x180014d91  retn
```
