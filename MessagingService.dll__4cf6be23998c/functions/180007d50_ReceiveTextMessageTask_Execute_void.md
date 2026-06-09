# ReceiveTextMessageTask::Execute(void)

- ea: `0x180007d50`
- end: `0x180008018`
- name: `?Execute@ReceiveTextMessageTask@@UEAAJXZ`
- size: `712`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000108c`
- `0x1800044dc`
- `0x180007b4c`
- `0x180007d50`
- `0x180008e54`
- `0x180009120`
- `0x18000a1c0`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180007dc6`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180007e2c`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180007e8a`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180007ed5`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180007f3a`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::Execute(ReceiveTextMessageTask *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 (__fastcall ***v5)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // edi
  int v9; // eax
  struct Windows::Devices::Sms::ISmsMessageBase *v10; // rdi
  int v11; // eax
  unsigned int v12; // esi
  struct Windows::Devices::Sms::ISmsMessageBase *v13; // [rsp+30h] [rbp-19h] BYREF
  int v14; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v16; // [rsp+50h] [rbp+7h]
  int v17; // [rsp+58h] [rbp+Fh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+60h] [rbp+17h] BYREF

  v14 = 0;
  v16 = 1;
  v13 = 0;
  v15[1] = this;
  v15[0] = &v14;
  v2 = ReceiveTextMessageTask::_ParseTrigger(this, &v13);
  v14 = v2;
  v3 = v2;
  if ( v2 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v2,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v13 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( (_BYTE)v16 )
      lambda_0114ab26b247e5f7282800c6f07085b7_::operator()(v15);
    return v3;
  }
  v5 = (__int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *))v13;
  v17 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *, int *))(*(_QWORD *)v13 + 72LL))(
         v13,
         &v17);
  v14 = v6;
  v8 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v6,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    goto LABEL_9;
  }
  v13 = 0;
  v9 = TextMessage::CreateInstance(v5, v7, &v13);
  v14 = v9;
  v8 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v9,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v13 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v13 + 8LL))(v13);
    if ( !v5 )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( this == (ReceiveTextMessageTask *)-40LL )
  {
    v8 = -2147467261;
    v14 = -2147467261;
    Log_HREvent_0(
      2147500035LL,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v13 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v13 + 8LL))(v13);
LABEL_9:
    if ( !v5 )
    {
LABEL_11:
      if ( (_BYTE)v16 )
        lambda_0114ab26b247e5f7282800c6f07085b7_::operator()(v15);
      return v8;
    }
LABEL_10:
    ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *)))(*v5)[2])(v5);
    goto LABEL_11;
  }
  v10 = v13;
  *((_QWORD *)this + 5) = v13;
  if ( v10 )
    (**(void (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *))v10)(v10);
  v14 = 0;
  v11 = ReceiveTextMessageTask::_ReceiveMessage(this);
  v14 = v11;
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( (unsigned int)dword_180013018 > 4 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_180010703, 0, 0, 2u, &v18);
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v10 + 8LL))(v10);
    if ( v5 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *)))(*v5)[2])(v5);
    if ( (_BYTE)v16 )
      lambda_0114ab26b247e5f7282800c6f07085b7_::operator()(v15);
    return 0;
  }
  else
  {
    Log_HREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    if ( v10 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v10 + 8LL))(v10);
    if ( v5 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *)))(*v5)[2])(v5);
    if ( (_BYTE)v16 )
      lambda_0114ab26b247e5f7282800c6f07085b7_::operator()(v15);
    return v12;
  }
}

```

## disassembly

```asm
0x180007d50  mov     [rsp-8+arg_8], rbx
0x180007d55  mov     [rsp-8+arg_10], rsi
0x180007d5a  push    rbp
0x180007d5b  push    rdi
0x180007d5c  push    r15
0x180007d5e  lea     rbp, [rsp-47h]
0x180007d63  sub     rsp, 90h
0x180007d6a  mov     rax, cs:__security_cookie
0x180007d71  xor     rax, rsp
0x180007d74  mov     [rbp+57h+var_20], rax
0x180007d78  xor     eax, eax
0x180007d7a  mov     [rbp+57h+var_68], 0
0x180007d81  mov     [rbp+57h+var_50], rax
0x180007d85  lea     rdx, [rbp+57h+var_70]; struct Windows::Devices::Sms::ISmsMessageBase **
0x180007d89  xorps   xmm0, xmm0
0x180007d8c  mov     [rbp+57h+var_70], 0
0x180007d94  movups  [rbp+57h+var_60], xmm0
0x180007d98  lea     rax, [rbp+57h+var_68]
0x180007d9c  mov     qword ptr [rbp+57h+var_60+8], rcx
0x180007da0  mov     r15d, 1
0x180007da6  mov     qword ptr [rbp+57h+var_60], rax
0x180007daa  mov     rsi, rcx
0x180007dad  mov     byte ptr [rbp+57h+var_50], r15b
0x180007db1  call    ?_ParseTrigger@ReceiveTextMessageTask@@AEAAJPEAPEAUISmsMessageBase@Sms@Devices@Windows@@@Z; ReceiveTextMessageTask::_ParseTrigger(Windows::Devices::Sms::ISmsMessageBase * *)
0x180007db6  mov     [rbp+57h+var_68], eax
0x180007db9  mov     ebx, eax
0x180007dbb  test    eax, eax
0x180007dbd  jns     short loc_180007DFF
0x180007dbf  lea     r9d, [r15+31h]
0x180007dc3  mov     edx, r15d
0x180007dc6  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007dcd  mov     ecx, eax
0x180007dcf  call    Log_HREvent_0
0x180007dd4  mov     rcx, [rbp+57h+var_70]
0x180007dd8  test    rcx, rcx
0x180007ddb  jz      short loc_180007DE9
0x180007ddd  mov     rax, [rcx]
0x180007de0  mov     rax, [rax+10h]
0x180007de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de9  cmp     byte ptr [rbp+57h+var_50], 0
0x180007ded  jz      short loc_180007DF8
0x180007def  lea     rcx, [rbp+57h+var_60]
0x180007df3  call    _lambda_0114ab26b247e5f7282800c6f07085b7___operator__
0x180007df8  mov     eax, ebx
0x180007dfa  jmp     loc_180007FF4
0x180007dff  mov     rbx, [rbp+57h+var_70]
0x180007e03  lea     rdx, [rbp+57h+var_48]
0x180007e07  mov     [rbp+57h+var_48], 0
0x180007e0e  mov     rcx, rbx
0x180007e11  mov     rax, [rbx]
0x180007e14  mov     rax, [rax+48h]
0x180007e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1d  mov     [rbp+57h+var_68], eax
0x180007e20  mov     edi, eax
0x180007e22  test    eax, eax
0x180007e24  jns     short loc_180007E67
0x180007e26  mov     r9d, 36h ; '6'
0x180007e2c  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007e33  mov     edx, r15d
0x180007e36  mov     ecx, eax
0x180007e38  call    Log_HREvent_0
0x180007e3d  test    rbx, rbx
0x180007e40  jz      short loc_180007E51
0x180007e42  mov     rcx, [rbx]
0x180007e45  mov     rax, [rcx+10h]
0x180007e49  mov     rcx, rbx
0x180007e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e51  cmp     byte ptr [rbp+57h+var_50], 0
0x180007e55  jz      short loc_180007E60
0x180007e57  lea     rcx, [rbp+57h+var_60]
0x180007e5b  call    _lambda_0114ab26b247e5f7282800c6f07085b7___operator__
0x180007e60  mov     eax, edi
0x180007e62  jmp     loc_180007FF4
0x180007e67  lea     r8, [rbp+57h+var_70]; struct TextMessage **
0x180007e6b  mov     [rbp+57h+var_70], 0
0x180007e73  mov     rcx, rbx; struct Windows::Devices::Sms::ISmsMessageBase *
0x180007e76  call    ?CreateInstance@TextMessage@@SAJPEAUISmsMessageBase@Sms@Devices@Windows@@KPEAPEAV1@@Z; TextMessage::CreateInstance(Windows::Devices::Sms::ISmsMessageBase *,ulong,TextMessage * *)
0x180007e7b  mov     [rbp+57h+var_68], eax
0x180007e7e  mov     edi, eax
0x180007e80  test    eax, eax
0x180007e82  jns     short loc_180007EBE
0x180007e84  mov     r9d, 3Dh ; '='
0x180007e8a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007e91  mov     edx, r15d
0x180007e94  mov     ecx, eax
0x180007e96  call    Log_HREvent_0
0x180007e9b  mov     rcx, [rbp+57h+var_70]
0x180007e9f  test    rcx, rcx
0x180007ea2  jz      short loc_180007EB0
0x180007ea4  mov     rax, [rcx]
0x180007ea7  mov     rax, [rax+8]
0x180007eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb0  test    rbx, rbx
0x180007eb3  jz      short loc_180007E51
0x180007eb5  mov     rax, [rbx]
0x180007eb8  mov     rax, [rax+10h]
0x180007ebc  jmp     short loc_180007E49
0x180007ebe  lea     rax, [rsi+28h]
0x180007ec2  test    rax, rax
0x180007ec5  jnz     short loc_180007F02
0x180007ec7  mov     edi, 80004003h
0x180007ecc  lea     r9d, [rax+40h]
0x180007ed0  mov     ecx, edi
0x180007ed2  mov     [rbp+57h+var_68], edi
0x180007ed5  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007edc  mov     edx, r15d
0x180007edf  call    Log_HREvent_0
0x180007ee4  mov     rcx, [rbp+57h+var_70]
0x180007ee8  test    rcx, rcx
0x180007eeb  jz      loc_180007E3D
0x180007ef1  mov     rax, [rcx]
0x180007ef4  mov     rax, [rax+8]
0x180007ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007efd  jmp     loc_180007E3D
0x180007f02  mov     rdi, [rbp+57h+var_70]
0x180007f06  mov     [rax], rdi
0x180007f09  test    rdi, rdi
0x180007f0c  jz      short loc_180007F1C
0x180007f0e  mov     rax, [rdi]
0x180007f11  mov     rcx, rdi
0x180007f14  mov     rax, [rax]
0x180007f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1c  mov     rcx, rsi; this
0x180007f1f  mov     [rbp+57h+var_68], 0
0x180007f26  call    ?_ReceiveMessage@ReceiveTextMessageTask@@AEAAJXZ; ReceiveTextMessageTask::_ReceiveMessage(void)
0x180007f2b  mov     [rbp+57h+var_68], eax
0x180007f2e  mov     esi, eax
0x180007f30  test    eax, eax
0x180007f32  jns     short loc_180007F86
0x180007f34  mov     r9d, 43h ; 'C'
0x180007f3a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180007f41  mov     edx, r15d
0x180007f44  mov     ecx, eax
0x180007f46  call    Log_HREvent_0
0x180007f4b  test    rdi, rdi
0x180007f4e  jz      short loc_180007F5F
0x180007f50  mov     rcx, [rdi]
0x180007f53  mov     rax, [rcx+8]
0x180007f57  mov     rcx, rdi
0x180007f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5f  test    rbx, rbx
0x180007f62  jz      short loc_180007F73
0x180007f64  mov     rax, [rbx]
0x180007f67  mov     rcx, rbx
0x180007f6a  mov     rax, [rax+10h]
0x180007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f73  cmp     byte ptr [rbp+57h+var_50], 0
0x180007f77  jz      short loc_180007F82
0x180007f79  lea     rcx, [rbp+57h+var_60]
0x180007f7d  call    _lambda_0114ab26b247e5f7282800c6f07085b7___operator__
0x180007f82  mov     eax, esi
0x180007f84  jmp     short loc_180007FF4
0x180007f86  mov     eax, cs:dword_180013018
0x180007f8c  cmp     eax, 4
0x180007f8f  jbe     short loc_180007FBB
0x180007f91  lea     rax, [rbp+57h+var_40]
0x180007f95  xor     r9d, r9d; int
0x180007f98  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x180007f9d  lea     rdx, byte_180010703; int
0x180007fa4  xor     r8d, r8d; int
0x180007fa7  mov     [rsp+0A0h+var_80], 2; ULONG
0x180007faf  lea     rcx, dword_180013018; int
0x180007fb6  call    _tlgWriteTransfer_EventWriteTransfer
0x180007fbb  test    rdi, rdi
0x180007fbe  jz      short loc_180007FCF
0x180007fc0  mov     rax, [rdi]
0x180007fc3  mov     rcx, rdi
0x180007fc6  mov     rax, [rax+8]
0x180007fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fcf  test    rbx, rbx
0x180007fd2  jz      short loc_180007FE3
0x180007fd4  mov     rax, [rbx]
0x180007fd7  mov     rcx, rbx
0x180007fda  mov     rax, [rax+10h]
0x180007fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe3  cmp     byte ptr [rbp+57h+var_50], 0
0x180007fe7  jz      short loc_180007FF2
0x180007fe9  lea     rcx, [rbp+57h+var_60]
0x180007fed  call    _lambda_0114ab26b247e5f7282800c6f07085b7___operator__
0x180007ff2  xor     eax, eax
0x180007ff4  mov     rcx, [rbp+57h+var_20]
0x180007ff8  xor     rcx, rsp; StackCookie
0x180007ffb  call    __security_check_cookie
0x180008000  lea     r11, [rsp+0A0h+var_10]
0x180008008  mov     rbx, [r11+28h]
0x18000800c  mov     rsi, [r11+30h]
0x180008010  mov     rsp, r11
0x180008013  pop     r15
0x180008015  pop     rdi
0x180008016  pop     rbp
0x180008017  retn
```
