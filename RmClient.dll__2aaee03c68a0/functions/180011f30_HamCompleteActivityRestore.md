# HamCompleteActivityRestore

- ea: `0x180011f30`
- end: `0x18001215c`
- name: `HamCompleteActivityRestore`
- size: `556`
- prototype: `__int64 __fastcall(CLIENT_CALL_RETURN, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d14`
- `0x180004550`
- `0x18000dab0`
- `0x18000ffd0`
- `0x180011f00`
- `0x180011f30`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001200c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120d8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120f0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001200c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120d8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800120f0`
- `RPCRT4!NdrClientCall3` at `0x18001204b`
- `RPCRT4!NdrClientCall3` at `0x18001204b`
- `RPCRT4!RpcExceptionFilter` at `0x18001bafa`
- `RPCRT4!RpcExceptionFilter` at `0x18001bafa`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012064`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012064`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCompleteConnection` at `0x18001201b`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCompleteConnection` at `0x18001201b`

## pseudocode

```c
__int64 __fastcall HamCompleteActivityRestore(CLIENT_CALL_RETURN a1, __int64 a2)
{
  int v4; // r14d
  __int64 v5; // rcx
  LONG_PTR v6; // r15
  _QWORD *v7; // r12
  __int64 v8; // r9
  CLIENT_CALL_RETURN v9; // rbx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  CLIENT_CALL_RETURN v17; // [rsp+90h] [rbp+8h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+98h] [rbp+10h] BYREF
  LONG_PTR v19; // [rsp+A0h] [rbp+18h]
  LONG_PTR v20; // [rsp+A8h] [rbp+20h]

  v17.Pointer = a1.Pointer;
  v4 = 1;
  if ( (unsigned int)dword_18002E038 > 5 && tlgKeywordOn((__int64)&dword_18002E038, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      (unsigned __int8 *)qword_180026BB8);
  v6 = a1.Simple + 120;
  v19 = a1.Simple + 120;
  CempLockAcquireExclusive(a1.Simple + 120);
  v7 = (_QWORD *)(a1.Simple + 144);
  v20 = a1.Simple + 144;
  v8 = *(_QWORD *)(a1.Simple + 144);
  if ( a2 == v8 )
  {
    v10 = *(_DWORD *)(a1.Simple + 152);
    if ( v10 )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = *(_QWORD *)(a1.Simple + 136) + 160 * v11;
        if ( *(_QWORD *)(v8 + 8 * v11) != v12 )
          __int2c();
        if ( (*(_BYTE *)(v12 + 152) & 1) == 0 )
          break;
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= v10 )
          goto LABEL_12;
      }
      LODWORD(v9.Pointer) = -1073741436;
    }
    else
    {
LABEL_12:
      *(_DWORD *)(a1.Simple + 128) = 0;
      RtlReleaseSRWLockExclusive(a1.Simple + 120);
      if ( *(_QWORD *)(a1.Simple + 8) )
      {
        LODWORD(v9.Pointer) = HampInProcCompleteConnection();
      }
      else
      {
        v18.Simple = 0;
        v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, *(_QWORD *)a1.Pointer).Pointer;
        v18.Pointer = v9.Pointer;
      }
      v4 = 0;
      if ( SLODWORD(v9.Simple) >= 0 )
      {
        CempLockAcquireExclusive(a1.Simple + 120);
        if ( *(_QWORD *)(a1.Simple + 136) )
        {
          ((void (*)(void))HamFreeBuffer)();
          *(_QWORD *)(a1.Simple + 136) = 0;
        }
        if ( *v7 )
        {
          HamFreeBuffer(*v7);
          *v7 = 0;
        }
        *(_DWORD *)(a1.Simple + 152) = 0;
        *(_DWORD *)(a1.Simple + 128) = 0;
        RtlReleaseSRWLockExclusive(v6);
        LODWORD(v9.Pointer) = 0;
      }
    }
  }
  else
  {
    LODWORD(v9.Pointer) = -1073741584;
  }
  if ( v4 )
  {
    *(_DWORD *)(a1.Simple + 128) = 0;
    RtlReleaseSRWLockExclusive(v6);
  }
  if ( (unsigned int)dword_18002E038 > 4 && tlgKeywordOn((__int64)&dword_18002E038, 3) )
  {
    v18.Pointer = a1.Pointer;
    LODWORD(v17.Pointer) = v9.Pointer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v13,
      (unsigned __int8 *)&word_180026BDE,
      v14,
      v15,
      (__int64)&v17,
      (__int64)&v18);
  }
  return LODWORD(v9.Pointer);
}

```

## disassembly

```asm
0x180011f30  mov     [rsp+arg_0], rcx
0x180011f35  push    rbx
0x180011f36  push    rsi
0x180011f37  push    r12
0x180011f39  push    r13
0x180011f3b  push    r14
0x180011f3d  push    r15
0x180011f3f  sub     rsp, 58h
0x180011f43  mov     rbx, rdx
0x180011f46  mov     rsi, rcx
0x180011f49  mov     eax, cs:dword_18002E038
0x180011f4f  mov     r14d, 1
0x180011f55  cmp     eax, 5
0x180011f58  jbe     short loc_180011F79
0x180011f5a  mov     edx, r14d
0x180011f5d  lea     rcx, dword_18002E038
0x180011f64  call    _tlgKeywordOn
0x180011f69  test    al, al
0x180011f6b  jz      short loc_180011F79
0x180011f6d  lea     rdx, qword_180026BB8
0x180011f74  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180011f79  lea     rax, [rsi+78h]
0x180011f7d  mov     [rsp+88h+var_48], rax
0x180011f82  mov     r15, rax
0x180011f85  mov     [rsp+88h+arg_10], rax
0x180011f8d  mov     rcx, rax
0x180011f90  call    CempLockAcquireExclusive
0x180011f95  lea     r12, [rsi+90h]
0x180011f9c  mov     [rsp+88h+arg_18], r12
0x180011fa4  mov     r9, [r12]
0x180011fa8  cmp     rbx, r9
0x180011fab  jz      short loc_180011FB7
0x180011fad  mov     ebx, 0C00000F0h
0x180011fb2  jmp     loc_1800120E0
0x180011fb7  lea     rax, [rsi+98h]
0x180011fbe  mov     [rsp+88h+var_40], rax
0x180011fc3  mov     r8d, [rax]
0x180011fc6  test    r8d, r8d
0x180011fc9  jz      short loc_180011FF8
0x180011fcb  xor     edx, edx
0x180011fcd  mov     r11, [rsi+88h]
0x180011fd4  lea     r10, [rdx+rdx*4]
0x180011fd8  shl     r10, 5
0x180011fdc  add     r10, r11
0x180011fdf  cmp     [r9+rdx*8], r10
0x180011fe3  jz      short loc_180011FE7
0x180011fe5  int     2Ch; Windows NT - assertion failure
0x180011fe7  test    [r10+98h], r14b
0x180011fee  jz      short loc_180012025
0x180011ff0  add     edx, r14d
0x180011ff3  cmp     edx, r8d
0x180011ff6  jb      short loc_180011FD4
0x180011ff8  lea     r13, [r15+8]
0x180011ffc  mov     [rsp+88h+var_50], r13
0x180012001  mov     dword ptr [r13+0], 0
0x180012009  mov     rcx, r15
0x18001200c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012012  mov     rcx, [rsi+8]
0x180012016  test    rcx, rcx
0x180012019  jz      short loc_18001202F
0x18001201b  call    cs:__imp_HampInProcCompleteConnection
0x180012021  mov     ebx, eax
0x180012023  jmp     short loc_18001208D
0x180012025  mov     ebx, 0C0000184h
0x18001202a  jmp     loc_1800120E0
0x18001202f  mov     [rsp+88h+arg_8], 0
0x18001203b  mov     r9, [rsi]
0x18001203e  xor     r8d, r8d; pReturnValue
0x180012041  mov     edx, r14d; nProcNum
0x180012044  lea     rcx, pProxyInfo; pProxyInfo
0x18001204b  call    cs:__imp_NdrClientCall3
0x180012051  mov     rbx, rax
0x180012054  mov     [rsp+88h+arg_8], rax
0x18001205c  mov     [rsp+88h+var_58], eax
0x180012060  jmp     short loc_18001208D
0x180012062  mov     ecx, eax; Status
0x180012064  call    cs:__imp_I_RpcMapWin32Status
0x18001206a  mov     ebx, eax
0x18001206c  mov     [rsp+88h+var_58], eax
0x180012070  mov     rsi, [rsp+88h+arg_0]
0x180012078  mov     r15, [rsp+88h+arg_10]
0x180012080  mov     r12, [rsp+88h+arg_18]
0x180012088  mov     r13, [rsp+88h+var_50]
0x18001208d  xor     r14d, r14d
0x180012090  test    ebx, ebx
0x180012092  js      short loc_1800120E0
0x180012094  mov     rcx, [rsp+88h+var_48]
0x180012099  call    CempLockAcquireExclusive
0x18001209e  mov     rcx, [rsi+88h]
0x1800120a5  test    rcx, rcx
0x1800120a8  jz      short loc_1800120B6
0x1800120aa  call    HamFreeBuffer
0x1800120af  mov     [rsi+88h], r14
0x1800120b6  cmp     [r12], r14
0x1800120ba  jz      short loc_1800120C9
0x1800120bc  mov     rcx, [r12]
0x1800120c0  call    HamFreeBuffer
0x1800120c5  mov     [r12], r14
0x1800120c9  mov     rax, [rsp+88h+var_40]
0x1800120ce  mov     [rax], r14d
0x1800120d1  mov     [r13+0], r14d
0x1800120d5  mov     rcx, r15
0x1800120d8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800120de  xor     ebx, ebx
0x1800120e0  test    r14d, r14d
0x1800120e3  jz      short loc_1800120F6
0x1800120e5  mov     dword ptr [r15+8], 0
0x1800120ed  mov     rcx, r15
0x1800120f0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800120f6  mov     eax, cs:dword_18002E038
0x1800120fc  cmp     eax, 4
0x1800120ff  jbe     short loc_18001214B
0x180012101  mov     edx, 3
0x180012106  lea     rcx, dword_18002E038
0x18001210d  call    _tlgKeywordOn
0x180012112  test    al, al
0x180012114  jz      short loc_18001214B
0x180012116  mov     [rsp+88h+arg_8], rsi
0x18001211e  mov     dword ptr [rsp+88h+arg_0], ebx
0x180012125  lea     rax, [rsp+88h+arg_8]
0x18001212d  mov     [rsp+88h+var_60], rax
0x180012132  lea     rax, [rsp+88h+arg_0]
0x18001213a  mov     [rsp+88h+var_68], rax
0x18001213f  lea     rdx, word_180026BDE
0x180012146  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001214b  mov     eax, ebx
0x18001214d  add     rsp, 58h
0x180012151  pop     r15
0x180012153  pop     r14
0x180012155  pop     r13
0x180012157  pop     r12
0x180012159  pop     rsi
0x18001215a  pop     rbx
0x18001215b  retn
0x18001baec  push    rbp
0x18001baee  sub     rsp, 30h
0x18001baf2  mov     rbp, rdx
0x18001baf5  mov     rcx, [rcx]
0x18001baf8  mov     ecx, [rcx]; ExceptionCode
0x18001bafa  call    cs:__imp_RpcExceptionFilter
0x18001bb00  nop
0x18001bb01  add     rsp, 30h
0x18001bb05  pop     rbp
0x18001bb06  retn
```
