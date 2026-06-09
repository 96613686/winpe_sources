# ReceiveTextMessageTask::_FindReplacementMessage(ISmMessage * *)

- ea: `0x1800088dc`
- end: `0x180008d5f`
- name: `?_FindReplacementMessage@ReceiveTextMessageTask@@AEAAJPEAPEAUISmMessage@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this, struct ISmMessage **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009120`

## callees

- `0x180001148`
- `0x1800044dc`
- `0x1800088dc`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008945`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800089ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008945`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800089ab`

## string_xrefs

- `0x180008957`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x1800089bd`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008a0f`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008a86`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008adb`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008b85`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008d21`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_FindReplacementMessage(
        ReceiveTextMessageTask *this,
        struct ISmMessage **a2)
{
  int v4; // r14d
  HRESULT v5; // eax
  int v6; // edi
  HRESULT v8; // eax
  void (*v9)(void); // rax
  __int64 v10; // rdx
  unsigned int v11; // r9d
  int v12; // eax
  int v13; // eax
  void (*v14)(void); // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  void (*v19)(void); // rax
  int v20; // eax
  __int64 v21; // rcx
  struct ISmMessage *v22; // rcx
  LPVOID v23; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  struct ISmMessage *v26; // [rsp+48h] [rbp-28h] BYREF
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h] BYREF
  int v29; // [rsp+60h] [rbp-10h] BYREF

  *a2 = 0;
  v4 = *(_DWORD *)(*((_QWORD *)this + 5) + 132LL);
  if ( !v4 )
    return 0;
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
         0,
         0x17u,
         &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
         &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v5,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_4:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v6;
  }
  v23 = 0;
  v8 = CoCreateInstance(
         &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
         0,
         0x17u,
         &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
         &v23);
  v6 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_0(
      (unsigned int)v8,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
LABEL_9:
    if ( !v23 )
      goto LABEL_4;
    v9 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
LABEL_11:
    v9();
    goto LABEL_4;
  }
  v10 = *((_QWORD *)this + 5);
  v11 = *(_DWORD *)(v10 + 136);
  if ( v11 - 1 > 8 && v11 < 0x65 || v11 - 101 <= 0x63 )
  {
    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v23 + 24LL))(v23, *(_QWORD *)(v10 + 24), 1);
    v6 = v12;
    if ( v12 < 0 )
    {
      Log_HREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( !v23 )
        goto LABEL_4;
      v9 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
      goto LABEL_11;
    }
    v25 = 0;
    v13 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, v23, &v25);
    v6 = v13;
    if ( v13 < 0 )
    {
      Log_HREvent_0(
        (unsigned int)v13,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      if ( !v25 )
        goto LABEL_9;
      v14 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_26:
      v14();
      goto LABEL_9;
    }
    v28 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 88LL))(v25, &v28) >= 0 )
    {
      v27 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, &v27);
      v6 = v18;
      if ( v18 >= 0 )
      {
        while ( 1 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
          v21 = v27;
          if ( v20 )
            goto LABEL_48;
          v26 = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, struct ISmMessage **))(*(_QWORD *)v27 + 32LL))(v27, &v26);
          if ( v6 < 0 )
            break;
          v29 = 0;
          v6 = (*(__int64 (__fastcall **)(struct ISmMessage *, int *))(*(_QWORD *)v26 + 464LL))(v26, &v29);
          if ( v6 < 0 )
            break;
          v22 = v26;
          if ( v4 == v29 )
          {
            *a2 = v26;
            if ( v22 )
            {
              (*(void (__fastcall **)(struct ISmMessage *))(*(_QWORD *)v22 + 8LL))(v22);
              if ( v26 )
                (*(void (__fastcall **)(struct ISmMessage *))(*(_QWORD *)v26 + 16LL))(v26);
            }
            v21 = v27;
LABEL_48:
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            goto LABEL_50;
          }
          if ( v26 )
            (*(void (**)(void))(*(_QWORD *)v26 + 16LL))();
        }
        Log_HREvent_0(
          (unsigned int)v6,
          1,
          "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
        if ( v26 )
          (*(void (__fastcall **)(struct ISmMessage *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v27 )
        {
          v19 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
          goto LABEL_33;
        }
      }
      else
      {
        Log_HREvent_0(
          (unsigned int)v18,
          1,
          "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
        if ( v27 )
        {
          v19 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
LABEL_33:
          v19();
        }
      }
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( !v25 )
        goto LABEL_9;
      v14 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
      goto LABEL_26;
    }
    if ( (unsigned int)dword_180013018 > 4 )
    {
      v26 = (struct ISmMessage *)L"No conversation found.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v15,
        (int)word_1800105BA,
        v16,
        v17,
        (__int64 **)&v26);
    }
LABEL_50:
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v23 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  Log_HREvent_0(
    2147549183LL,
    0,
    "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
  if ( v23 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800088dc  mov     [rsp-18h+arg_10], rbx
0x1800088e1  mov     [rsp-18h+arg_18], rsi
0x1800088e6  push    rbp
0x1800088e7  push    rdi
0x1800088e8  push    r14
0x1800088ea  mov     rbp, rsp
0x1800088ed  sub     rsp, 70h
0x1800088f1  mov     rax, cs:__security_cookie
0x1800088f8  xor     rax, rsp
0x1800088fb  mov     [rbp+var_8], rax
0x1800088ff  mov     qword ptr [rdx], 0
0x180008906  mov     rsi, rdx
0x180008909  mov     rax, [rcx+28h]
0x18000890d  mov     rbx, rcx
0x180008910  mov     r14d, [rax+84h]
0x180008917  test    r14d, r14d
0x18000891a  jz      loc_180008CF0
0x180008920  xor     edx, edx; pUnkOuter
0x180008922  mov     [rbp+var_38], 0
0x18000892a  lea     rax, [rbp+var_38]
0x18000892e  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x180008935  mov     [rsp+70h+ppv], rax; ppv
0x18000893a  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x180008941  lea     r8d, [rdx+17h]; dwClsContext
0x180008945  call    cs:__imp_CoCreateInstance
0x18000894b  mov     edi, eax
0x18000894d  test    eax, eax
0x18000894f  jns     short loc_180008986
0x180008951  mov     r9d, 108h
0x180008957  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000895e  mov     edx, 1
0x180008963  mov     ecx, eax
0x180008965  call    Log_HREvent_0
0x18000896a  mov     rcx, [rbp+var_38]
0x18000896e  test    rcx, rcx
0x180008971  jz      short loc_18000897F
0x180008973  mov     rax, [rcx]
0x180008976  mov     rax, [rax+10h]
0x18000897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897f  mov     eax, edi
0x180008981  jmp     loc_180008CF2
0x180008986  xor     edx, edx; pUnkOuter
0x180008988  mov     [rbp+var_40], 0
0x180008990  lea     rax, [rbp+var_40]
0x180008994  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x18000899b  mov     [rsp+70h+ppv], rax; ppv
0x1800089a0  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x1800089a7  lea     r8d, [rdx+17h]; dwClsContext
0x1800089ab  call    cs:__imp_CoCreateInstance
0x1800089b1  mov     edi, eax
0x1800089b3  test    eax, eax
0x1800089b5  jns     short loc_1800089E7
0x1800089b7  mov     r9d, 10Bh
0x1800089bd  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800089c4  mov     edx, 1
0x1800089c9  mov     ecx, eax
0x1800089cb  call    Log_HREvent_0
0x1800089d0  mov     rcx, [rbp+var_40]
0x1800089d4  test    rcx, rcx
0x1800089d7  jz      short loc_18000896A
0x1800089d9  mov     rax, [rcx]
0x1800089dc  mov     rax, [rax+10h]
0x1800089e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e5  jmp     short loc_18000896A
0x1800089e7  mov     rdx, [rbx+28h]
0x1800089eb  mov     r9d, [rdx+88h]
0x1800089f2  lea     eax, [r9-1]
0x1800089f6  cmp     eax, 8
0x1800089f9  jbe     short loc_180008A01
0x1800089fb  cmp     r9d, 65h ; 'e'
0x1800089ff  jb      short loc_180008A56
0x180008a01  lea     eax, [r9-65h]
0x180008a05  cmp     eax, 63h ; 'c'
0x180008a08  jbe     short loc_180008A56
0x180008a0a  mov     ebx, 8000FFFFh
0x180008a0f  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008a16  mov     ecx, ebx
0x180008a18  mov     r9d, 10Eh
0x180008a1e  xor     edx, edx
0x180008a20  call    Log_HREvent_0
0x180008a25  mov     rcx, [rbp+var_40]
0x180008a29  test    rcx, rcx
0x180008a2c  jz      short loc_180008A3A
0x180008a2e  mov     rax, [rcx]
0x180008a31  mov     rax, [rax+10h]
0x180008a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a3a  mov     rcx, [rbp+var_38]
0x180008a3e  test    rcx, rcx
0x180008a41  jz      short loc_180008A4F
0x180008a43  mov     rdx, [rcx]
0x180008a46  mov     rax, [rdx+10h]
0x180008a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a4f  mov     eax, ebx
0x180008a51  jmp     loc_180008CF2
0x180008a56  mov     rcx, [rbp+var_40]
0x180008a5a  mov     ebx, 1
0x180008a5f  mov     rdx, [rdx+18h]
0x180008a63  mov     r8d, ebx
0x180008a66  mov     dword ptr [rsp+70h+ppv], 0
0x180008a6e  mov     rax, [rcx]
0x180008a71  mov     rax, [rax+18h]
0x180008a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a7a  mov     edi, eax
0x180008a7c  test    eax, eax
0x180008a7e  jns     short loc_180008AAF
0x180008a80  mov     r9d, 110h
0x180008a86  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008a8d  mov     edx, ebx
0x180008a8f  mov     ecx, eax
0x180008a91  call    Log_HREvent_0
0x180008a96  mov     rcx, [rbp+var_40]
0x180008a9a  test    rcx, rcx
0x180008a9d  jz      loc_18000896A
0x180008aa3  mov     rdx, [rcx]
0x180008aa6  mov     rax, [rdx+10h]
0x180008aaa  jmp     loc_1800089E0
0x180008aaf  mov     rcx, [rbp+var_38]
0x180008ab3  lea     r8, [rbp+var_30]
0x180008ab7  mov     rdx, [rbp+var_40]
0x180008abb  mov     [rbp+var_30], 0
0x180008ac3  mov     rax, [rcx]
0x180008ac6  mov     rax, [rax+30h]
0x180008aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acf  mov     edi, eax
0x180008ad1  test    eax, eax
0x180008ad3  jns     short loc_180008B09
0x180008ad5  mov     r9d, 113h
0x180008adb  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008ae2  mov     edx, ebx
0x180008ae4  mov     ecx, eax
0x180008ae6  call    Log_HREvent_0
0x180008aeb  mov     rcx, [rbp+var_30]
0x180008aef  test    rcx, rcx
0x180008af2  jz      loc_1800089D0
0x180008af8  mov     rdx, [rcx]
0x180008afb  mov     rax, [rdx+10h]
0x180008aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b04  jmp     loc_1800089D0
0x180008b09  mov     rcx, [rbp+var_30]
0x180008b0d  lea     rdx, [rbp+var_18]
0x180008b11  mov     [rbp+var_18], 0
0x180008b19  mov     rax, [rcx]
0x180008b1c  mov     rax, [rax+58h]
0x180008b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b25  test    eax, eax
0x180008b27  jns     short loc_180008B5D
0x180008b29  mov     eax, cs:dword_180013018
0x180008b2f  cmp     eax, 4
0x180008b32  jbe     loc_180008C9C
0x180008b38  lea     rax, aNoConversation; "No conversation found."
0x180008b3f  mov     [rbp+var_28], rax
0x180008b43  lea     rdx, word_1800105BA
0x180008b4a  lea     rax, [rbp+var_28]
0x180008b4e  mov     [rsp+70h+ppv], rax
0x180008b53  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180008b58  jmp     loc_180008C9C
0x180008b5d  mov     rcx, [rbp+var_30]
0x180008b61  lea     rdx, [rbp+var_20]
0x180008b65  mov     [rbp+var_20], 0
0x180008b6d  mov     rax, [rcx]
0x180008b70  mov     rax, [rax+18h]
0x180008b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b79  mov     edi, eax
0x180008b7b  test    eax, eax
0x180008b7d  jns     short loc_180008BD8
0x180008b7f  mov     r9d, 124h
0x180008b85  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008b8c  mov     edx, ebx
0x180008b8e  mov     ecx, eax
0x180008b90  call    Log_HREvent_0
0x180008b95  mov     rcx, [rbp+var_20]
0x180008b99  test    rcx, rcx
0x180008b9c  jz      short loc_180008BAA
0x180008b9e  mov     rdx, [rcx]
0x180008ba1  mov     rax, [rdx+10h]
0x180008ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008baa  mov     rcx, [rbp+var_18]
0x180008bae  test    rcx, rcx
0x180008bb1  jz      short loc_180008BBF
0x180008bb3  mov     rax, [rcx]
0x180008bb6  mov     rax, [rax+10h]
0x180008bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbf  mov     rcx, [rbp+var_30]
0x180008bc3  test    rcx, rcx
0x180008bc6  jz      loc_1800089D0
0x180008bcc  mov     rax, [rcx]
0x180008bcf  mov     rax, [rax+10h]
0x180008bd3  jmp     loc_180008AFF
0x180008bd8  mov     rcx, [rbp+var_20]
0x180008bdc  mov     rax, [rcx]
0x180008bdf  mov     rax, [rax+18h]
0x180008be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be8  mov     rcx, [rbp+var_20]
0x180008bec  test    eax, eax
0x180008bee  jnz     loc_180008C8B
0x180008bf4  mov     [rbp+var_28], 0
0x180008bfc  lea     rdx, [rbp+var_28]
0x180008c00  mov     rax, [rcx]
0x180008c03  mov     rax, [rax+20h]
0x180008c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0c  mov     edi, eax
0x180008c0e  test    eax, eax
0x180008c10  js      loc_180008D1B
0x180008c16  mov     rcx, [rbp+var_28]
0x180008c1a  lea     rdx, [rbp+var_10]
0x180008c1e  mov     [rbp+var_10], 0
0x180008c25  mov     rax, [rcx]
0x180008c28  mov     rax, [rax+1D0h]
0x180008c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c34  mov     edi, eax
0x180008c36  test    eax, eax
0x180008c38  js      loc_180008D13
0x180008c3e  mov     rcx, [rbp+var_28]
0x180008c42  cmp     r14d, [rbp+var_10]
0x180008c46  jz      short loc_180008C5E
0x180008c48  test    rcx, rcx
0x180008c4b  jz      short loc_180008BD8
0x180008c4d  mov     rax, [rcx]
0x180008c50  mov     rax, [rax+10h]
0x180008c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c59  jmp     loc_180008BD8
0x180008c5e  mov     [rsi], rcx
0x180008c61  test    rcx, rcx
0x180008c64  jz      short loc_180008C87
0x180008c66  mov     rax, [rcx]
0x180008c69  mov     rax, [rax+8]
0x180008c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c72  mov     rcx, [rbp+var_28]
0x180008c76  test    rcx, rcx
0x180008c79  jz      short loc_180008C87
0x180008c7b  mov     rax, [rcx]
0x180008c7e  mov     rax, [rax+10h]
0x180008c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c87  mov     rcx, [rbp+var_20]
0x180008c8b  test    rcx, rcx
0x180008c8e  jz      short loc_180008C9C
0x180008c90  mov     rax, [rcx]
0x180008c93  mov     rax, [rax+10h]
0x180008c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9c  mov     rcx, [rbp+var_18]
0x180008ca0  test    rcx, rcx
0x180008ca3  jz      short loc_180008CB1
0x180008ca5  mov     rax, [rcx]
0x180008ca8  mov     rax, [rax+10h]
0x180008cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb1  mov     rcx, [rbp+var_30]
0x180008cb5  test    rcx, rcx
0x180008cb8  jz      short loc_180008CC6
0x180008cba  mov     rax, [rcx]
0x180008cbd  mov     rax, [rax+10h]
0x180008cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc6  mov     rcx, [rbp+var_40]
0x180008cca  test    rcx, rcx
0x180008ccd  jz      short loc_180008CDB
0x180008ccf  mov     rax, [rcx]
0x180008cd2  mov     rax, [rax+10h]
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  mov     rcx, [rbp+var_38]
0x180008cdf  test    rcx, rcx
0x180008ce2  jz      short loc_180008CF0
0x180008ce4  mov     rax, [rcx]
0x180008ce7  mov     rax, [rax+10h]
0x180008ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf0  xor     eax, eax
0x180008cf2  mov     rcx, [rbp+var_8]
0x180008cf6  xor     rcx, rsp; StackCookie
0x180008cf9  call    __security_check_cookie
0x180008cfe  lea     r11, [rsp+70h+var_s0]
0x180008d03  mov     rbx, [r11+30h]
0x180008d07  mov     rsi, [r11+38h]
0x180008d0b  mov     rsp, r11
0x180008d0e  pop     r14
0x180008d10  pop     rdi
0x180008d11  pop     rbp
0x180008d12  retn
0x180008d13  mov     r9d, 12Ch
0x180008d19  jmp     short loc_180008D21
0x180008d1b  mov     r9d, 129h
0x180008d21  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008d28  mov     edx, ebx
0x180008d2a  mov     ecx, edi
0x180008d2c  call    Log_HREvent_0
0x180008d31  mov     rcx, [rbp+var_28]
0x180008d35  test    rcx, rcx
0x180008d38  jz      short loc_180008D46
0x180008d3a  mov     rax, [rcx]
0x180008d3d  mov     rax, [rax+10h]
0x180008d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d46  mov     rcx, [rbp+var_20]
0x180008d4a  test    rcx, rcx
0x180008d4d  jz      loc_180008BAA
0x180008d53  mov     rax, [rcx]
0x180008d56  mov     rax, [rax+10h]
0x180008d5a  jmp     loc_180008BA5
```
