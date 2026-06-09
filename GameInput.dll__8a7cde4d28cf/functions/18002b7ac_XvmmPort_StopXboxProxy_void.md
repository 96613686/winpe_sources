# XvmmPort::StopXboxProxy(void)

- ea: `0x18002b7ac`
- end: `0x18002b903`
- name: `?StopXboxProxy@XvmmPort@@AEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(XvmmPort *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028410`

## callees

- `0x180025234`
- `0x180029c1c`
- `0x18002b7ac`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b808`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b808`

## pseudocode

```c
__int64 __fastcall XvmmPort::StopXboxProxy(XvmmPort *this)
{
  int v2; // ebx
  HRESULT v3; // eax
  LPVOID v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // eax
  __int128 v10; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-30h] BYREF
  char v12; // [rsp+60h] [rbp-10h]
  LPVOID ppv; // [rsp+98h] [rbp+28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h] BYREF

  memset(v11, 0, sizeof(v11));
  v12 = 0;
  v2 = XboxMTAUsageWrapper::Initialize((XboxMTAUsageWrapper *)v11);
  if ( v2 < 0 )
    goto LABEL_17;
  ppv = 0;
  v3 = CoCreateInstance(
         &GUID_f5715449_10f6_4225_a7c6_d584bd3c7f5b,
         0,
         0x17u,
         &GUID_9a57863e_b229_4696_a8d4_40e5eb792d0f,
         &ppv);
  v4 = ppv;
  v2 = v3;
  if ( v3 >= 0 )
  {
    v14 = 0;
    v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_af7f45cf_0c68_46de_afed_252bbff0c9c4,
           &v14);
    if ( v2 >= 0 )
    {
      v6 = *((unsigned __int16 *)this + 40);
      v7 = *(_QWORD *)ppv;
      v10 = *((_OWORD *)this + 4);
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(v7 + 32))(ppv, &v10, v6);
      v5 = v14;
      v2 = v8;
      if ( v8 >= 0 )
      {
        *((_BYTE *)this + 82) = 0;
        if ( v5 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          v14 = 0;
        }
        if ( ppv )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          ppv = 0;
        }
        v2 = 0;
        goto LABEL_17;
      }
    }
    else
    {
      v5 = v14;
    }
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v14 = 0;
    }
    v4 = ppv;
    if ( ppv )
      goto LABEL_4;
  }
  else if ( ppv )
  {
LABEL_4:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(v4);
    ppv = 0;
  }
LABEL_17:
  XboxMTAUsageWrapper::~XboxMTAUsageWrapper((XboxMTAUsageWrapper *)v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002b7ac  mov     [rsp-18h+arg_0], rbx
0x18002b7b1  push    rbp
0x18002b7b2  push    rsi
0x18002b7b3  push    rdi
0x18002b7b4  mov     rbp, rsp
0x18002b7b7  sub     rsp, 70h
0x18002b7bb  xor     esi, esi
0x18002b7bd  mov     rdi, rcx
0x18002b7c0  lea     rcx, [rbp+var_30]; this
0x18002b7c4  mov     [rbp+var_30], rsi
0x18002b7c8  mov     [rbp+var_28], rsi
0x18002b7cc  mov     [rbp+var_20], rsi
0x18002b7d0  mov     [rbp+var_18], rsi
0x18002b7d4  mov     [rbp+var_10], sil
0x18002b7d8  call    ?Initialize@XboxMTAUsageWrapper@@QEAAJXZ; XboxMTAUsageWrapper::Initialize(void)
0x18002b7dd  mov     ebx, eax
0x18002b7df  test    eax, eax
0x18002b7e1  js      loc_18002B8E7
0x18002b7e7  lea     rax, [rbp+arg_8]
0x18002b7eb  mov     [rbp+arg_8], rsi
0x18002b7ef  lea     r9, _GUID_9a57863e_b229_4696_a8d4_40e5eb792d0f; riid
0x18002b7f6  mov     [rsp+70h+ppv], rax; ppv
0x18002b7fb  xor     edx, edx; pUnkOuter
0x18002b7fd  lea     r8d, [rsi+17h]; dwClsContext
0x18002b801  lea     rcx, _GUID_f5715449_10f6_4225_a7c6_d584bd3c7f5b; rclsid
0x18002b808  call    cs:__imp_CoCreateInstance
0x18002b80f  nop     dword ptr [rax+rax+00h]
0x18002b814  mov     rcx, [rbp+arg_8]
0x18002b818  mov     ebx, eax
0x18002b81a  test    eax, eax
0x18002b81c  jns     short loc_18002B83C
0x18002b81e  test    rcx, rcx
0x18002b821  jz      loc_18002B8E7
0x18002b827  mov     rdx, [rcx]
0x18002b82a  mov     rax, [rdx+10h]
0x18002b82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b833  mov     [rbp+arg_8], rsi
0x18002b837  jmp     loc_18002B8E7
0x18002b83c  mov     [rbp+arg_10], rsi
0x18002b840  lea     r8, [rbp+arg_10]
0x18002b844  mov     rax, [rcx]
0x18002b847  lea     rdx, _GUID_af7f45cf_0c68_46de_afed_252bbff0c9c4
0x18002b84e  mov     rax, [rax]
0x18002b851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b856  mov     ebx, eax
0x18002b858  test    eax, eax
0x18002b85a  jns     short loc_18002B887
0x18002b85c  mov     rcx, [rbp+arg_10]
0x18002b860  test    rcx, rcx
0x18002b863  jz      short loc_18002B875
0x18002b865  mov     rdx, [rcx]
0x18002b868  mov     rax, [rdx+10h]
0x18002b86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b871  mov     [rbp+arg_10], rsi
0x18002b875  mov     rcx, [rbp+arg_8]
0x18002b879  test    rcx, rcx
0x18002b87c  jz      short loc_18002B8E7
0x18002b87e  mov     rax, [rcx]
0x18002b881  mov     rax, [rax+10h]
0x18002b885  jmp     short loc_18002B82E
0x18002b887  mov     rcx, [rbp+arg_8]
0x18002b88b  lea     rdx, [rbp+var_40]
0x18002b88f  movups  xmm0, xmmword ptr [rdi+40h]
0x18002b893  movzx   r8d, word ptr [rdi+50h]
0x18002b898  mov     rax, [rcx]
0x18002b89b  movdqu  [rbp+var_40], xmm0
0x18002b8a0  mov     rax, [rax+20h]
0x18002b8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8a9  mov     rcx, [rbp+arg_10]
0x18002b8ad  mov     ebx, eax
0x18002b8af  test    eax, eax
0x18002b8b1  js      short loc_18002B860
0x18002b8b3  mov     [rdi+52h], sil
0x18002b8b7  test    rcx, rcx
0x18002b8ba  jz      short loc_18002B8CC
0x18002b8bc  mov     rax, [rcx]
0x18002b8bf  mov     rax, [rax+10h]
0x18002b8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c8  mov     [rbp+arg_10], rsi
0x18002b8cc  mov     rcx, [rbp+arg_8]
0x18002b8d0  test    rcx, rcx
0x18002b8d3  jz      short loc_18002B8E5
0x18002b8d5  mov     rax, [rcx]
0x18002b8d8  mov     rax, [rax+10h]
0x18002b8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8e1  mov     [rbp+arg_8], rsi
0x18002b8e5  mov     ebx, esi
0x18002b8e7  lea     rcx, [rbp+var_30]; this
0x18002b8eb  call    ??1XboxMTAUsageWrapper@@QEAA@XZ; XboxMTAUsageWrapper::~XboxMTAUsageWrapper(void)
0x18002b8f0  mov     eax, ebx
0x18002b8f2  mov     rbx, [rsp+70h+arg_0]
0x18002b8fa  add     rsp, 70h
0x18002b8fe  pop     rdi
0x18002b8ff  pop     rsi
0x18002b900  pop     rbp
0x18002b901  retn
```
