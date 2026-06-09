# CNgcReader::ProcessControlPower(ulong,uchar *,ulong *)

- ea: `0x180019dd8`
- end: `0x180019ff7`
- name: `?ProcessControlPower@CNgcReader@@IEAAKKPEAEPEAK@Z`
- size: `543`
- prototype: `__int64 __fastcall(CNgcReader *this, int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013740`

## callees

- `0x1800044e0`
- `0x18000d7a0`
- `0x180010bac`
- `0x180014d88`
- `0x1800151f8`
- `0x180019dd8`
- `0x18001a000`
- `0x18001a01c`
- `0x1800315b8`
- `0x1800326d0`

## string_xrefs

- `0x180019e16`: `CNgcReader::ProcessControlPower`

## pseudocode

```c
__int64 __fastcall CNgcReader::ProcessControlPower(CNgcReader *this, int a2, unsigned __int8 *a3, unsigned int *a4)
{
  unsigned int v8; // ebx
  int v9; // eax
  CNgcReader *v10; // rcx
  void *v11; // rbx
  CNgcReader *v12; // rcx
  int v14; // [rsp+30h] [rbp-69h] BYREF
  int v15; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-59h] BYREF
  void **v18; // [rsp+48h] [rbp-51h] BYREF
  void *v19; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int8 *v20; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int8 **v21; // [rsp+60h] [rbp-39h] BYREF
  __int16 v22; // [rsp+68h] [rbp-31h]
  _QWORD *v23; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v24[3]; // [rsp+78h] [rbp-21h] BYREF
  char v25[32]; // [rsp+90h] [rbp-9h] BYREF

  v14 = 0;
  v15 = 0;
  strcpy(v25, "CNgcReader::ProcessControlPower");
  v24[0] = v25;
  v24[1] = &v15;
  v24[2] = &v14;
  lambda_4d126fd5415134dbf464fc27b336c2ec_::operator()(v24);
  v15 = 1;
  v23 = v24;
  if ( !a2 )
  {
    CLockWrite::CLockWrite((CLockWrite *)v17, (CNgcReader *)((char *)this + 56));
    Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
    CLockWrite::~CLockWrite((CLockWrite *)v17);
    v8 = CNgcReader::CopyControlResult(v12, 0, 0, a3, a4);
    v14 = v8;
    goto LABEL_13;
  }
  if ( (unsigned int)(a2 - 1) >= 2 )
  {
    v8 = -2146435068;
    v14 = -2146435068;
    goto LABEL_13;
  }
  CLockWrite::CLockWrite((CLockWrite *)v17, (CNgcReader *)((char *)this + 56));
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
  CLockWrite::~CLockWrite((CLockWrite *)v17);
  v18 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable';
  v19 = 0;
  v20 = 0;
  v16 = 0;
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(&v18);
  v9 = GidsHandlerRpcAcquireChannel((const struct _GUID *)((char *)this + 760), &v19, &v20, &v16);
  v8 = v9;
  if ( v9 < 0 )
  {
    v14 = v9;
LABEL_8:
    v18 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(&v18);
    goto LABEL_13;
  }
  v21 = &v20;
  v22 = 256;
  v8 = CNgcReader::CopyControlResult(v10, v20, v16, a3, a4);
  v14 = v8;
  if ( v8 )
  {
    wil::details::ScopeExitFnGuard__lambda_86b19b821f5432fcf723276fb3a27966___::operator()(&v21);
    goto LABEL_8;
  }
  CLockWrite::CLockWrite((CLockWrite *)v17, (CNgcReader *)((char *)this + 56));
  v11 = v19;
  v19 = 0;
  if ( v11 != *((void **)this + 110) )
  {
    Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
    *((_QWORD *)this + 110) = v11;
  }
  CLockWrite::~CLockWrite((CLockWrite *)v17);
  wil::details::ScopeExitFnGuard__lambda_86b19b821f5432fcf723276fb3a27966___::operator()(&v21);
  v18 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(&v18);
  v8 = v14;
LABEL_13:
  WppTraceUnwinder__lambda_4d126fd5415134dbf464fc27b336c2ec____::_WppTraceUnwinder__lambda_4d126fd5415134dbf464fc27b336c2ec____(&v23);
  return v8;
}

```

## disassembly

```asm
0x180019dd8  push    rbp
0x180019dda  push    rbx
0x180019ddb  push    rsi
0x180019ddc  push    rdi
0x180019ddd  push    r12
0x180019ddf  push    r14
0x180019de1  push    r15
0x180019de3  lea     rbp, [rsp-27h]
0x180019de8  sub     rsp, 0C0h
0x180019def  mov     rax, cs:__security_cookie
0x180019df6  xor     rax, rsp
0x180019df9  mov     [rbp+57h+var_40], rax
0x180019dfd  mov     r12, r9
0x180019e00  mov     r15, r8
0x180019e03  mov     ebx, edx
0x180019e05  mov     rsi, rcx
0x180019e08  mov     [rbp+57h+var_C0], 0
0x180019e0f  mov     [rbp+57h+var_BC], 0
0x180019e16  movups  xmm0, xmmword ptr cs:aCngcreaderProc_3; "CNgcReader::ProcessControlPower"
0x180019e1d  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180019e21  movups  xmm1, xmmword ptr cs:aCngcreaderProc_3+10h; "essControlPower"
0x180019e28  movups  xmmword ptr [rbp+57h+var_60+10h], xmm1
0x180019e2c  lea     rax, [rbp+57h+var_60]
0x180019e30  mov     [rbp+57h+var_78], rax
0x180019e34  lea     rax, [rbp+57h+var_BC]
0x180019e38  mov     [rbp+57h+var_70], rax
0x180019e3c  lea     rax, [rbp+57h+var_C0]
0x180019e40  mov     [rbp+57h+var_68], rax
0x180019e44  lea     rcx, [rbp+57h+var_78]
0x180019e48  call    _lambda_4d126fd5415134dbf464fc27b336c2ec___operator__
0x180019e4d  mov     [rbp+57h+var_BC], 1
0x180019e54  lea     rax, [rbp+57h+var_78]
0x180019e58  mov     [rbp+57h+var_80], rax
0x180019e5c  test    ebx, ebx
0x180019e5e  jz      loc_180019F95
0x180019e64  sub     ebx, 1
0x180019e67  jz      short loc_180019E7B
0x180019e69  cmp     ebx, 1
0x180019e6c  jz      short loc_180019E7B
0x180019e6e  mov     ebx, 80100004h
0x180019e73  mov     [rbp+57h+var_C0], ebx
0x180019e76  jmp     loc_180019FCE
0x180019e7b  lea     rdx, [rsi+38h]; struct CAccessLock *
0x180019e7f  lea     rcx, [rbp+57h+var_B0]; this
0x180019e83  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180019e88  lea     rdi, [rsi+368h]
0x180019e8f  mov     rcx, rdi
0x180019e92  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019e97  lea     rcx, [rbp+57h+var_B0]; this
0x180019e9b  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180019ea0  lea     rax, ??_7?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable'
0x180019ea7  mov     [rbp+57h+var_A8], rax
0x180019eab  mov     [rbp+57h+var_A0], 0
0x180019eb3  mov     [rbp+57h+var_98], 0
0x180019ebb  mov     [rbp+57h+var_B8], 0
0x180019ec2  lea     rcx, [rbp+57h+var_A8]
0x180019ec6  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019ecb  lea     rcx, [rsi+2F8h]; struct _GUID *
0x180019ed2  lea     r9, [rbp+57h+var_B8]; unsigned int *
0x180019ed6  lea     r8, [rbp+57h+var_98]; unsigned __int8 **
0x180019eda  lea     rdx, [rbp+57h+var_A0]; void **
0x180019ede  call    ?GidsHandlerRpcAcquireChannel@@YAJPEBU_GUID@@PEAPEAXPEAPEAEPEAK@Z; GidsHandlerRpcAcquireChannel(_GUID const *,void * *,uchar * *,ulong *)
0x180019ee3  mov     ebx, eax
0x180019ee5  test    eax, eax
0x180019ee7  jns     short loc_180019EEE
0x180019ee9  mov     [rbp+57h+var_C0], eax
0x180019eec  jmp     short loc_180019F24
0x180019eee  lea     rax, [rbp+57h+var_98]
0x180019ef2  mov     [rbp+57h+var_90], rax
0x180019ef6  mov     [rbp+57h+var_88], 100h
0x180019efc  mov     [rsp+0F0h+var_D0], r12; unsigned int *
0x180019f01  mov     r9, r15; unsigned __int8 *
0x180019f04  mov     r8d, [rbp+57h+var_B8]; unsigned int
0x180019f08  mov     rdx, [rbp+57h+var_98]; unsigned __int8 *
0x180019f0c  call    ?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z; CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)
0x180019f11  mov     ebx, eax
0x180019f13  mov     [rbp+57h+var_C0], eax
0x180019f16  test    eax, eax
0x180019f18  jz      short loc_180019F3D
0x180019f1a  lea     rcx, [rbp+57h+var_90]
0x180019f1e  call    wil__details__ScopeExitFnGuard__lambda_86b19b821f5432fcf723276fb3a27966_____operator__
0x180019f23  nop
0x180019f24  lea     rax, ??_7?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable'
0x180019f2b  mov     [rbp+57h+var_A8], rax
0x180019f2f  lea     rcx, [rbp+57h+var_A8]
0x180019f33  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019f38  jmp     loc_180019FCE
0x180019f3d  lea     rdx, [rsi+38h]; struct CAccessLock *
0x180019f41  lea     rcx, [rbp+57h+var_B0]; this
0x180019f45  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180019f4a  mov     rbx, [rbp+57h+var_A0]
0x180019f4e  mov     [rbp+57h+var_A0], 0
0x180019f56  cmp     rbx, [rdi+8]
0x180019f5a  jz      short loc_180019F68
0x180019f5c  mov     rcx, rdi
0x180019f5f  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019f64  mov     [rdi+8], rbx
0x180019f68  lea     rcx, [rbp+57h+var_B0]; this
0x180019f6c  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180019f71  nop
0x180019f72  lea     rcx, [rbp+57h+var_90]
0x180019f76  call    wil__details__ScopeExitFnGuard__lambda_86b19b821f5432fcf723276fb3a27966_____operator__
0x180019f7b  nop
0x180019f7c  lea     rax, ??_7?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable'
0x180019f83  mov     [rbp+57h+var_A8], rax
0x180019f87  lea     rcx, [rbp+57h+var_A8]
0x180019f8b  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019f90  mov     ebx, [rbp+57h+var_C0]
0x180019f93  jmp     short loc_180019FCE
0x180019f95  lea     rdx, [rsi+38h]; struct CAccessLock *
0x180019f99  lea     rcx, [rbp+57h+var_B0]; this
0x180019f9d  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180019fa2  lea     rcx, [rsi+368h]
0x180019fa9  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x180019fae  lea     rcx, [rbp+57h+var_B0]; this
0x180019fb2  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180019fb7  mov     [rsp+0F0h+var_D0], r12; unsigned int *
0x180019fbc  mov     r9, r15; unsigned __int8 *
0x180019fbf  xor     r8d, r8d; unsigned int
0x180019fc2  xor     edx, edx; unsigned __int8 *
0x180019fc4  call    ?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z; CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)
0x180019fc9  mov     ebx, eax
0x180019fcb  mov     [rbp+57h+var_C0], eax
0x180019fce  lea     rcx, [rbp+57h+var_80]
0x180019fd2  call    WppTraceUnwinder__lambda_4d126fd5415134dbf464fc27b336c2ec_______WppTraceUnwinder__lambda_4d126fd5415134dbf464fc27b336c2ec____
0x180019fd7  mov     eax, ebx
0x180019fd9  mov     rcx, [rbp+57h+var_40]
0x180019fdd  xor     rcx, rsp; StackCookie
0x180019fe0  call    __security_check_cookie
0x180019fe5  add     rsp, 0C0h
0x180019fec  pop     r15
0x180019fee  pop     r14
0x180019ff0  pop     r12
0x180019ff2  pop     rdi
0x180019ff3  pop     rsi
0x180019ff4  pop     rbx
0x180019ff5  pop     rbp
0x180019ff6  retn
```
