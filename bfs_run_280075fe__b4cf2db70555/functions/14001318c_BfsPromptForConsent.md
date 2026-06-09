# BfsPromptForConsent

- ea: `0x14001318c`
- end: `0x1400134dd`
- name: `BfsPromptForConsent`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000dadc`

## callees

- `0x140001008`
- `0x14001318c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14001328f`
- `msrpc!RpcBindingCreateW` at `0x140013301`
- `msrpc!RpcBindingCreateW` at `0x140013301`
- `msrpc!RpcBindingBind` at `0x140013336`
- `msrpc!RpcBindingBind` at `0x140013336`
- `msrpc!RpcExceptionFilter` at `0x14001404b`
- `msrpc!RpcExceptionFilter` at `0x14001404b`
- `msrpc!RpcBindingUnbind` at `0x14001349b`
- `msrpc!RpcBindingUnbind` at `0x14001349b`
- `msrpc!NdrClientCall3` at `0x1400133b0`
- `msrpc!NdrClientCall3` at `0x1400133b0`
- `msrpc!RpcBindingFree` at `0x1400134ac`
- `msrpc!RpcBindingFree` at `0x1400134ac`

## pseudocode

```c
__int64 __fastcall BfsPromptForConsent(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  char v5; // si
  unsigned int Pointer; // ebx
  RPC_STATUS v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  RPC_STATUS v11; // eax
  CLIENT_CALL_RETURN v12; // rax
  CLIENT_CALL_RETURN v13; // rcx
  CLIENT_CALL_RETURN v14; // r8
  CLIENT_CALL_RETURN v15; // r9
  int v17; // [rsp+20h] [rbp-178h]
  __int64 v18; // [rsp+58h] [rbp-140h] BYREF
  unsigned int v19; // [rsp+60h] [rbp-138h]
  CLIENT_CALL_RETURN v20; // [rsp+68h] [rbp-130h]
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp-128h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+78h] [rbp-120h] BYREF
  int v23; // [rsp+A0h] [rbp-F8h] BYREF
  __int64 v24; // [rsp+A4h] [rbp-F4h]
  int v25; // [rsp+ACh] [rbp-ECh]
  __int128 v26; // [rsp+B0h] [rbp-E8h]
  __int128 v27; // [rsp+C0h] [rbp-D8h]
  __int64 v28; // [rsp+D0h] [rbp-C8h]
  int v29; // [rsp+D8h] [rbp-C0h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v30; // [rsp+E0h] [rbp-B8h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v31; // [rsp+F0h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+128h] [rbp-70h] BYREF
  __int64 *v33; // [rsp+148h] [rbp-50h]
  __int64 v34; // [rsp+150h] [rbp-48h]

  v18 = a4;
  memset(&v31.ProtocolSequence + 1, 0, 28);
  v5 = 0;
  v30 = 0;
  memset(&Security, 0, sizeof(Security));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  Pointer = 0;
  v29 = 1;
  *a5 = 0;
  Binding = 0;
  v31.Version = 1;
  v31.Flags = 1;
  v31.ProtocolSequence = 3;
  v31.ObjectUuid = (UUID)xmmword_140016654;
  v23 = 5;
  v25 = 3;
  v24 = 17;
  *(_QWORD *)&v27 = SeExports->SeLocalSystemSid;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v23;
  v30.Version = 1;
  *(_QWORD *)&v30.Flags = 0x500000002LL;
  v7 = RpcBindingCreateW(&v31, &Security, &v30, &Binding);
  if ( v7 )
  {
    if ( v7 > 0 )
      Pointer = (unsigned __int16)v7 | 0xC0070000;
    else
      Pointer = v7;
    goto LABEL_22;
  }
  v11 = RpcBindingBind(0, Binding, byte_140016650);
  if ( v11 )
  {
    if ( v11 > 0 )
      Pointer = (unsigned __int16)v11 | 0xC0070000;
    else
      Pointer = v11;
LABEL_22:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v33 = &v18;
      LODWORD(v18) = Pointer;
      v34 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v8, (unsigned __int8 *)&byte_140016D91, v9, v10, v17, &v32);
    }
    goto LABEL_24;
  }
  v5 = 1;
  v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Binding).Pointer;
  v20.Pointer = v12.Pointer;
  if ( LODWORD(v12.Pointer) )
  {
    if ( SLODWORD(v12.Simple) > 0 )
      Pointer = LOWORD(v12.Pointer) | 0xC0070000;
    else
      Pointer = (unsigned int)v12.Pointer;
    v19 = Pointer;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v18) = Pointer;
      v33 = &v18;
      v34 = 4;
      tlgWriteTransfer_EtwWriteTransfer(
        v13.Simple,
        (unsigned __int8 *)&byte_140016D91,
        v14.Simple,
        v15.Simple,
        (int)L"appSiloFileSystem",
        &v32);
    }
  }
  else if ( !v29 )
  {
    *a5 = 1;
  }
LABEL_24:
  if ( Binding )
  {
    if ( v5 )
      RpcBindingUnbind(Binding);
    RpcBindingFree(&Binding);
  }
  return Pointer;
}

```

## disassembly

```asm
0x14001318c  mov     r11, rsp
0x14001318f  push    rbx
0x140013190  push    rsi
0x140013191  push    r12
0x140013193  push    r13
0x140013195  push    r14
0x140013197  push    r15
0x140013199  sub     rsp, 168h
0x1400131a0  mov     rax, cs:__security_cookie
0x1400131a7  xor     rax, rsp
0x1400131aa  mov     [rsp+198h+var_40], rax
0x1400131b2  mov     [rsp+198h+var_140], r9
0x1400131b7  mov     r13, r8
0x1400131ba  mov     r12, rdx
0x1400131bd  mov     r15, rcx
0x1400131c0  mov     r14, [rsp+198h+arg_20]
0x1400131c8  xorps   xmm0, xmm0
0x1400131cb  movdqu  [rsp+198h+var_9C], xmm0
0x1400131d4  mov     qword ptr [r11-8Ch], 0
0x1400131df  mov     [rsp+198h+var_84], 0
0x1400131ea  xor     sil, sil
0x1400131ed  movups  [rsp+198h+var_B8], xmm0
0x1400131f5  xorps   xmm1, xmm1
0x1400131f8  xor     eax, eax
0x1400131fa  movups  xmmword ptr [rsp+198h+Security.Version], xmm1
0x1400131ff  movups  xmmword ptr [rsp+198h+Security.AuthnLevel], xmm1
0x140013207  mov     [r11-100h], rax
0x14001320e  movups  [rsp+198h+var_F8], xmm0
0x140013216  movups  [rsp+198h+var_E8], xmm0
0x14001321e  movups  [rsp+198h+var_D8], xmm0
0x140013226  mov     [r11-0C8h], rax
0x14001322d  xor     ebx, ebx
0x14001322f  lea     r8d, [rax+1]
0x140013233  mov     [r11-0C0h], r8d
0x14001323a  mov     [r14], al
0x14001323d  mov     [rsp+198h+Binding], rax
0x140013242  mov     [r11-0A8h], r8d
0x140013249  mov     [r11-0A4h], r8d
0x140013250  mov     [rsp+198h+var_A0], 3
0x14001325b  movups  xmm0, cs:xmmword_140016654
0x140013262  movdqu  xmmword ptr [r11-80h], xmm0
0x140013268  lea     edx, [rax+5]
0x14001326b  mov     dword ptr [rsp+198h+var_F8], edx
0x140013272  mov     dword ptr [rsp+198h+var_F8+8], eax
0x140013279  mov     dword ptr [rsp+198h+var_F8+0Ch], 3
0x140013284  mov     dword ptr [rsp+198h+var_F8+4], 11h
0x14001328f  mov     rax, cs:__imp_SeExports
0x140013296  mov     rcx, [rax]
0x140013299  mov     rax, [rcx+108h]
0x1400132a0  mov     [r11-0D8h], rax
0x1400132a7  mov     [rsp+198h+Security.Version], r8d
0x1400132ac  mov     [rsp+198h+Security.AuthnLevel], 6
0x1400132b7  mov     [rsp+198h+Security.AuthnSvc], 14h
0x1400132c2  lea     rax, [r11-0F8h]
0x1400132c9  mov     [r11-100h], rax
0x1400132d0  mov     [r11-0B8h], r8d
0x1400132d7  mov     dword ptr [rsp+198h+var_B8+4], 2
0x1400132e2  mov     dword ptr [rsp+198h+var_B8+8], edx
0x1400132e9  lea     r9, [rsp+198h+Binding]; Binding
0x1400132ee  lea     r8, [r11-0B8h]; Options
0x1400132f5  lea     rdx, [rsp+198h+Security]; Security
0x1400132fa  lea     rcx, [r11-0A8h]; Template
0x140013301  call    cs:__imp_RpcBindingCreateW
0x140013308  nop     dword ptr [rax+rax+00h]
0x14001330d  test    eax, eax
0x14001330f  jz      short loc_140013328
0x140013311  jg      short loc_140013317
0x140013313  mov     ebx, eax
0x140013315  jmp     short loc_140013320
0x140013317  movzx   ebx, ax
0x14001331a  or      ebx, 0C0070000h
0x140013320  test    ebx, ebx
0x140013322  js      loc_14001344B
0x140013328  lea     r8, byte_140016650; IfSpec
0x14001332f  mov     rdx, [rsp+198h+Binding]; Binding
0x140013334  xor     ecx, ecx; pAsync
0x140013336  call    cs:__imp_RpcBindingBind
0x14001333d  nop     dword ptr [rax+rax+00h]
0x140013342  test    eax, eax
0x140013344  jz      short loc_14001335D
0x140013346  jg      short loc_14001334C
0x140013348  mov     ebx, eax
0x14001334a  jmp     short loc_140013355
0x14001334c  movzx   ebx, ax
0x14001334f  or      ebx, 0C0070000h
0x140013355  test    ebx, ebx
0x140013357  js      loc_14001344B
0x14001335d  mov     sil, 1
0x140013360  mov     [rsp+198h+var_148], sil
0x140013365  mov     [rsp+198h+var_130], 0
0x14001336e  lea     rax, [rsp+198h+var_C0]
0x140013376  mov     [rsp+198h+var_150], rax
0x14001337b  mov     rax, [rsp+198h+var_140]
0x140013380  mov     [rsp+198h+var_158], eax
0x140013384  mov     [rsp+198h+var_160], r13
0x140013389  mov     [rsp+198h+var_168], r12
0x14001338e  mov     [rsp+198h+var_170], r15
0x140013393  lea     rax, aAppsilofilesys; "appSiloFileSystem"
0x14001339a  mov     qword ptr [rsp+198h+var_178], rax; int
0x14001339f  mov     r9, [rsp+198h+Binding]
0x1400133a4  xor     r8d, r8d; pReturnValue
0x1400133a7  xor     edx, edx; nProcNum
0x1400133a9  lea     rcx, pProxyInfo; pProxyInfo
0x1400133b0  call    cs:__imp_NdrClientCall3
0x1400133b7  nop     dword ptr [rax+rax+00h]
0x1400133bc  mov     [rsp+198h+var_130], rax
0x1400133c1  test    eax, eax
0x1400133c3  jz      short loc_14001341F
0x1400133c5  jg      short loc_1400133CB
0x1400133c7  mov     ebx, eax
0x1400133c9  jmp     short loc_1400133D4
0x1400133cb  movzx   ebx, ax
0x1400133ce  or      ebx, 0C0070000h
0x1400133d4  mov     [rsp+198h+var_138], ebx
0x1400133d8  test    ebx, ebx
0x1400133da  jns     short loc_14001341F
0x1400133dc  mov     eax, cs:dword_140019000
0x1400133e2  cmp     eax, 3
0x1400133e5  jbe     short loc_14001341D
0x1400133e7  mov     dword ptr [rsp+198h+var_140], ebx
0x1400133eb  lea     rax, [rsp+198h+var_140]
0x1400133f0  mov     [rsp+198h+var_50], rax
0x1400133f8  mov     [rsp+198h+var_48], 4
0x140013404  lea     rax, [rsp+198h+var_70]
0x14001340c  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x140013411  lea     rdx, byte_140016D91; int
0x140013418  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001341d  jmp     short loc_14001348C
0x14001341f  cmp     [rsp+198h+var_C0], 0
0x140013427  jnz     short loc_14001342D
0x140013429  mov     byte ptr [r14], 1
0x14001342d  jmp     short loc_140013447
0x14001342f  mov     ebx, eax
0x140013431  test    eax, eax
0x140013433  jle     short loc_14001343E
0x140013435  movzx   ebx, ax
0x140013438  or      ebx, 0C0070000h
0x14001343e  mov     [rsp+198h+var_138], ebx
0x140013442  mov     sil, [rsp+198h+var_148]
0x140013447  test    ebx, ebx
0x140013449  jns     short loc_14001348C
0x14001344b  mov     eax, cs:dword_140019000
0x140013451  cmp     eax, 3
0x140013454  jbe     short loc_14001348C
0x140013456  lea     rax, [rsp+198h+var_140]
0x14001345b  mov     [rsp+198h+var_50], rax
0x140013463  lea     rax, [rsp+198h+var_70]
0x14001346b  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x140013470  mov     dword ptr [rsp+198h+var_140], ebx
0x140013474  mov     [rsp+198h+var_48], 4
0x140013480  lea     rdx, byte_140016D91; int
0x140013487  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001348c  mov     rcx, [rsp+198h+Binding]; Binding
0x140013491  test    rcx, rcx
0x140013494  jz      short loc_1400134B8
0x140013496  test    sil, sil
0x140013499  jz      short loc_1400134A7
0x14001349b  call    cs:__imp_RpcBindingUnbind
0x1400134a2  nop     dword ptr [rax+rax+00h]
0x1400134a7  lea     rcx, [rsp+198h+Binding]; Binding
0x1400134ac  call    cs:__imp_RpcBindingFree
0x1400134b3  nop     dword ptr [rax+rax+00h]
0x1400134b8  mov     eax, ebx
0x1400134ba  mov     rcx, [rsp+198h+var_40]
0x1400134c2  xor     rcx, rsp; StackCookie
0x1400134c5  call    __security_check_cookie
0x1400134ca  add     rsp, 168h
0x1400134d1  pop     r15
0x1400134d3  pop     r14
0x1400134d5  pop     r13
0x1400134d7  pop     r12
0x1400134d9  pop     rsi
0x1400134da  pop     rbx
0x1400134db  retn
0x14001403d  push    rbp
0x14001403f  sub     rsp, 50h
0x140014043  mov     rbp, rdx
0x140014046  mov     rcx, [rcx]
0x140014049  mov     ecx, [rcx]; ExceptionCode
0x14001404b  call    cs:__imp_RpcExceptionFilter
0x140014052  nop     dword ptr [rax+rax+00h]
0x140014057  nop
0x140014058  add     rsp, 50h
0x14001405c  pop     rbp
0x14001405d  retn
```
