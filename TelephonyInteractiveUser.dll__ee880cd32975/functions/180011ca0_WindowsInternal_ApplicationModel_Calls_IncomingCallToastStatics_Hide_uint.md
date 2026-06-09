# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Hide(uint)

- ea: `0x180011ca0`
- end: `0x180011e56`
- name: `?Hide@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJI@Z`
- size: `438`
- prototype: `int(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x1800021b4`
- `0x1800117e4`
- `0x180011ca0`
- `0x180011e68`
- `0x180015a7c`
- `0x180019010`

## string_xrefs

- `0x180011de4`: `IncomingCall`
- `0x180011d27`: `IncomingCallToastStatics: Hide, callId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Hide(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        unsigned int a2)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v8; // [rsp+30h] [rbp-49h] BYREF
  __int64 v9; // [rsp+38h] [rbp-41h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-39h] BYREF
  __int16 v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 v12; // [rsp+52h] [rbp-27h]
  int v13; // [rsp+5Ah] [rbp-1Fh]
  __int16 v14; // [rsp+5Eh] [rbp-1Bh]
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+60h] [rbp-19h] BYREF
  const char *v16; // [rsp+80h] [rbp+7h]
  __int64 v17; // [rsp+88h] [rbp+Fh]
  unsigned int *v18; // [rsp+90h] [rbp+17h]
  __int64 v19; // [rsp+98h] [rbp+1Fh]
  __int64 *v20; // [rsp+A0h] [rbp+27h]
  __int64 v21; // [rsp+A8h] [rbp+2Fh]

  if ( (unsigned int)dword_180025038 > 5
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    v9 = 0x1000000;
    v20 = &v9;
    v8 = a2;
    v18 = &v8;
    v21 = 8;
    v16 = "IncomingCallToastStatics: Hide, callId";
    v19 = 4;
    v17 = 39;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025038, (unsigned __int8 *)&byte_180020E0D, 0, 0, 5u, &v15);
  }
  v12 = 0;
  v14 = 0;
  v13 = 0;
  Block[0] = &v11;
  Block[1] = &v11;
  v11 = 0;
  v4 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
         Block,
         L"%u",
         a2);
  if ( v4 < 0 )
  {
    v6 = 98;
LABEL_7:
    Log_HREvent_1((unsigned int)v4, 1, v5, v6);
    if ( Block[0] != &v11 )
      operator delete(Block[0]);
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, const unsigned __int16 *, void *, const unsigned __int16 *))(*((_QWORD *)this - 1) + 112LL))(
         (char *)this - 8,
         L"NonImmersivePackage",
         L"Windows.Systemtoast.Calling",
         Block[0],
         L"IncomingCall");
  if ( v4 < 0 )
  {
    v6 = 100;
    goto LABEL_7;
  }
  TraceLogging::IncomingCallToastHidden(a2);
  if ( Block[0] != &v11 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180011ca0  mov     [rsp-8+arg_10], rbx
0x180011ca5  push    rbp
0x180011ca6  push    rsi
0x180011ca7  push    rdi
0x180011ca8  lea     rbp, [rsp-47h]
0x180011cad  sub     rsp, 0C0h
0x180011cb4  mov     rax, cs:__security_cookie
0x180011cbb  xor     rax, rsp
0x180011cbe  mov     [rbp+57h+var_20], rax
0x180011cc2  mov     eax, cs:dword_180025038
0x180011cc8  mov     edi, edx
0x180011cca  mov     rsi, rcx
0x180011ccd  cmp     eax, 5
0x180011cd0  jbe     loc_180011D66
0x180011cd6  mov     rdx, cs:qword_180025050
0x180011cdd  mov     rcx, 400000000000h
0x180011ce7  mov     rax, cs:qword_180025048
0x180011cee  test    rcx, rax
0x180011cf1  jz      short loc_180011D66
0x180011cf3  mov     rax, rdx
0x180011cf6  and     rax, rcx
0x180011cf9  cmp     rax, rdx
0x180011cfc  jnz     short loc_180011D66
0x180011cfe  lea     rax, [rbp+57h+var_98]
0x180011d02  mov     [rbp+57h+var_98], 1000000h
0x180011d0a  mov     [rbp+57h+var_30], rax
0x180011d0e  lea     rdx, byte_180020E0D; int
0x180011d15  lea     rax, [rbp+57h+var_A0]
0x180011d19  mov     [rbp+57h+var_A0], edi
0x180011d1c  mov     [rbp+57h+var_40], rax
0x180011d20  lea     rcx, dword_180025038; int
0x180011d27  lea     rax, aIncomingcallto_4; "IncomingCallToastStatics: Hide, callId"
0x180011d2e  mov     [rbp+57h+var_28], 8
0x180011d36  mov     [rbp+57h+var_50], rax
0x180011d3a  xor     r9d, r9d; int
0x180011d3d  lea     rax, [rbp+57h+var_70]
0x180011d41  mov     [rbp+57h+var_38], 4
0x180011d49  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180011d4e  xor     r8d, r8d; int
0x180011d51  mov     [rsp+0D0h+var_B0], 5; ULONG
0x180011d59  mov     [rbp+57h+var_48], 27h ; '''
0x180011d61  call    _tlgWriteTransfer_EventWriteTransfer
0x180011d66  xor     eax, eax
0x180011d68  mov     [rbp+57h+var_7E], 0
0x180011d70  mov     [rbp+57h+var_72], ax
0x180011d74  lea     rdx, aU; "%u"
0x180011d7b  lea     rax, [rbp+57h+var_80]
0x180011d7f  mov     [rbp+57h+var_76], 0
0x180011d86  mov     [rbp+57h+Block], rax
0x180011d8a  lea     rcx, [rbp+57h+Block]
0x180011d8e  lea     rax, [rbp+57h+var_80]
0x180011d92  mov     r8d, edi
0x180011d95  mov     [rbp+57h+var_88], rax
0x180011d99  xor     eax, eax
0x180011d9b  mov     [rbp+57h+var_80], ax
0x180011d9f  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180011da4  mov     ebx, eax
0x180011da6  test    eax, eax
0x180011da8  jns     short loc_180011DD9
0x180011daa  mov     r9d, 62h ; 'b'
0x180011db0  mov     edx, 1
0x180011db5  mov     ecx, ebx
0x180011db7  call    Log_HREvent_1
0x180011dbc  mov     rcx, [rbp+57h+Block]; Block
0x180011dc0  lea     rax, [rbp+57h+var_80]
0x180011dc4  cmp     rcx, rax
0x180011dc7  jz      short loc_180011DD5
0x180011dc9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180011dd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011dd5  mov     eax, ebx
0x180011dd7  jmp     short loc_180011E37
0x180011dd9  mov     r9, [rbp+57h+Block]
0x180011ddd  lea     rcx, [rsi-8]
0x180011de1  mov     rax, [rcx]
0x180011de4  lea     rdx, aIncomingcall; "IncomingCall"
0x180011deb  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x180011df0  lea     r8, aWindowsSystemt; "Windows.Systemtoast.Calling"
0x180011df7  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x180011dfe  mov     rax, [rax+70h]
0x180011e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e07  mov     ebx, eax
0x180011e09  test    eax, eax
0x180011e0b  jns     short loc_180011E15
0x180011e0d  mov     r9d, 64h ; 'd'
0x180011e13  jmp     short loc_180011DB0
0x180011e15  mov     ecx, edi; unsigned int
0x180011e17  call    ?IncomingCallToastHidden@TraceLogging@@SAXI@Z; TraceLogging::IncomingCallToastHidden(uint)
0x180011e1c  mov     rcx, [rbp+57h+Block]; Block
0x180011e20  lea     rax, [rbp+57h+var_80]
0x180011e24  cmp     rcx, rax
0x180011e27  jz      short loc_180011E35
0x180011e29  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180011e30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011e35  xor     eax, eax
0x180011e37  mov     rcx, [rbp+57h+var_20]
0x180011e3b  xor     rcx, rsp; StackCookie
0x180011e3e  call    __security_check_cookie
0x180011e43  mov     rbx, [rsp+0D0h+arg_10]
0x180011e4b  add     rsp, 0C0h
0x180011e52  pop     rdi
0x180011e53  pop     rsi
0x180011e54  pop     rbp
0x180011e55  retn
```
