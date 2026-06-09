# BfsPromptForConsent

- ea: `0x1400132c4`
- end: `0x140013615`
- name: `BfsPromptForConsent`
- size: `849`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000dc70`

## callees

- `0x140001008`
- `0x1400132c4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400133c7`
- `msrpc!RpcBindingCreateW` at `0x140013439`
- `msrpc!RpcBindingCreateW` at `0x140013439`
- `msrpc!RpcBindingBind` at `0x14001346e`
- `msrpc!RpcBindingBind` at `0x14001346e`
- `msrpc!RpcExceptionFilter` at `0x14001418b`
- `msrpc!RpcExceptionFilter` at `0x14001418b`
- `msrpc!RpcBindingUnbind` at `0x1400135d3`
- `msrpc!RpcBindingUnbind` at `0x1400135d3`
- `msrpc!NdrClientCall3` at `0x1400134e8`
- `msrpc!NdrClientCall3` at `0x1400134e8`
- `msrpc!RpcBindingFree` at `0x1400135e4`
- `msrpc!RpcBindingFree` at `0x1400135e4`

## pseudocode

```c
__int64 __fastcall BfsPromptForConsent(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  char v5; // si
  unsigned int Pointer; // ebx
  RPC_STATUS v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  RPC_STATUS v11; // eax
  CLIENT_CALL_RETURN v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
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
  v31.ObjectUuid = (UUID)xmmword_140016644;
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
  v11 = RpcBindingBind(0, Binding, byte_140016640);
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
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v9, v10, v17, &v32);
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
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v14, v15, (int)L"appSiloFileSystem", &v32);
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
0x1400132c4  mov     r11, rsp
0x1400132c7  push    rbx
0x1400132c8  push    rsi
0x1400132c9  push    r12
0x1400132cb  push    r13
0x1400132cd  push    r14
0x1400132cf  push    r15
0x1400132d1  sub     rsp, 168h
0x1400132d8  mov     rax, cs:__security_cookie
0x1400132df  xor     rax, rsp
0x1400132e2  mov     [rsp+198h+var_40], rax
0x1400132ea  mov     [rsp+198h+var_140], r9
0x1400132ef  mov     r13, r8
0x1400132f2  mov     r12, rdx
0x1400132f5  mov     r15, rcx
0x1400132f8  mov     r14, [rsp+198h+arg_20]
0x140013300  xorps   xmm0, xmm0
0x140013303  movdqu  [rsp+198h+var_9C], xmm0
0x14001330c  mov     qword ptr [r11-8Ch], 0
0x140013317  mov     [rsp+198h+var_84], 0
0x140013322  xor     sil, sil
0x140013325  movups  [rsp+198h+var_B8], xmm0
0x14001332d  xorps   xmm1, xmm1
0x140013330  xor     eax, eax
0x140013332  movups  xmmword ptr [rsp+198h+Security.Version], xmm1
0x140013337  movups  xmmword ptr [rsp+198h+Security.AuthnLevel], xmm1
0x14001333f  mov     [r11-100h], rax
0x140013346  movups  [rsp+198h+var_F8], xmm0
0x14001334e  movups  [rsp+198h+var_E8], xmm0
0x140013356  movups  [rsp+198h+var_D8], xmm0
0x14001335e  mov     [r11-0C8h], rax
0x140013365  xor     ebx, ebx
0x140013367  lea     r8d, [rax+1]
0x14001336b  mov     [r11-0C0h], r8d
0x140013372  mov     [r14], al
0x140013375  mov     [rsp+198h+Binding], rax
0x14001337a  mov     [r11-0A8h], r8d
0x140013381  mov     [r11-0A4h], r8d
0x140013388  mov     [rsp+198h+var_A0], 3
0x140013393  movups  xmm0, cs:xmmword_140016644
0x14001339a  movdqu  xmmword ptr [r11-80h], xmm0
0x1400133a0  lea     edx, [rax+5]
0x1400133a3  mov     dword ptr [rsp+198h+var_F8], edx
0x1400133aa  mov     dword ptr [rsp+198h+var_F8+8], eax
0x1400133b1  mov     dword ptr [rsp+198h+var_F8+0Ch], 3
0x1400133bc  mov     dword ptr [rsp+198h+var_F8+4], 11h
0x1400133c7  mov     rax, cs:__imp_SeExports
0x1400133ce  mov     rcx, [rax]
0x1400133d1  mov     rax, [rcx+108h]
0x1400133d8  mov     [r11-0D8h], rax
0x1400133df  mov     [rsp+198h+Security.Version], r8d
0x1400133e4  mov     [rsp+198h+Security.AuthnLevel], 6
0x1400133ef  mov     [rsp+198h+Security.AuthnSvc], 14h
0x1400133fa  lea     rax, [r11-0F8h]
0x140013401  mov     [r11-100h], rax
0x140013408  mov     [r11-0B8h], r8d
0x14001340f  mov     dword ptr [rsp+198h+var_B8+4], 2
0x14001341a  mov     dword ptr [rsp+198h+var_B8+8], edx
0x140013421  lea     r9, [rsp+198h+Binding]; Binding
0x140013426  lea     r8, [r11-0B8h]; Options
0x14001342d  lea     rdx, [rsp+198h+Security]; Security
0x140013432  lea     rcx, [r11-0A8h]; Template
0x140013439  call    cs:__imp_RpcBindingCreateW
0x140013440  nop     dword ptr [rax+rax+00h]
0x140013445  test    eax, eax
0x140013447  jz      short loc_140013460
0x140013449  jg      short loc_14001344F
0x14001344b  mov     ebx, eax
0x14001344d  jmp     short loc_140013458
0x14001344f  movzx   ebx, ax
0x140013452  or      ebx, 0C0070000h
0x140013458  test    ebx, ebx
0x14001345a  js      loc_140013583
0x140013460  lea     r8, byte_140016640; IfSpec
0x140013467  mov     rdx, [rsp+198h+Binding]; Binding
0x14001346c  xor     ecx, ecx; pAsync
0x14001346e  call    cs:__imp_RpcBindingBind
0x140013475  nop     dword ptr [rax+rax+00h]
0x14001347a  test    eax, eax
0x14001347c  jz      short loc_140013495
0x14001347e  jg      short loc_140013484
0x140013480  mov     ebx, eax
0x140013482  jmp     short loc_14001348D
0x140013484  movzx   ebx, ax
0x140013487  or      ebx, 0C0070000h
0x14001348d  test    ebx, ebx
0x14001348f  js      loc_140013583
0x140013495  mov     sil, 1
0x140013498  mov     [rsp+198h+var_148], sil
0x14001349d  mov     [rsp+198h+var_130], 0
0x1400134a6  lea     rax, [rsp+198h+var_C0]
0x1400134ae  mov     [rsp+198h+var_150], rax
0x1400134b3  mov     rax, [rsp+198h+var_140]
0x1400134b8  mov     [rsp+198h+var_158], eax
0x1400134bc  mov     [rsp+198h+var_160], r13
0x1400134c1  mov     [rsp+198h+var_168], r12
0x1400134c6  mov     [rsp+198h+var_170], r15
0x1400134cb  lea     rax, aAppsilofilesys; "appSiloFileSystem"
0x1400134d2  mov     qword ptr [rsp+198h+var_178], rax; int
0x1400134d7  mov     r9, [rsp+198h+Binding]
0x1400134dc  xor     r8d, r8d; pReturnValue
0x1400134df  xor     edx, edx; nProcNum
0x1400134e1  lea     rcx, pProxyInfo; pProxyInfo
0x1400134e8  call    cs:__imp_NdrClientCall3
0x1400134ef  nop     dword ptr [rax+rax+00h]
0x1400134f4  mov     [rsp+198h+var_130], rax
0x1400134f9  test    eax, eax
0x1400134fb  jz      short loc_140013557
0x1400134fd  jg      short loc_140013503
0x1400134ff  mov     ebx, eax
0x140013501  jmp     short loc_14001350C
0x140013503  movzx   ebx, ax
0x140013506  or      ebx, 0C0070000h
0x14001350c  mov     [rsp+198h+var_138], ebx
0x140013510  test    ebx, ebx
0x140013512  jns     short loc_140013557
0x140013514  mov     eax, cs:dword_140019000
0x14001351a  cmp     eax, 3
0x14001351d  jbe     short loc_140013555
0x14001351f  mov     dword ptr [rsp+198h+var_140], ebx
0x140013523  lea     rax, [rsp+198h+var_140]
0x140013528  mov     [rsp+198h+var_50], rax
0x140013530  mov     [rsp+198h+var_48], 4
0x14001353c  lea     rax, [rsp+198h+var_70]
0x140013544  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x140013549  lea     rdx, byte_140016D91; int
0x140013550  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013555  jmp     short loc_1400135C4
0x140013557  cmp     [rsp+198h+var_C0], 0
0x14001355f  jnz     short loc_140013565
0x140013561  mov     byte ptr [r14], 1
0x140013565  jmp     short loc_14001357F
0x140013567  mov     ebx, eax
0x140013569  test    eax, eax
0x14001356b  jle     short loc_140013576
0x14001356d  movzx   ebx, ax
0x140013570  or      ebx, 0C0070000h
0x140013576  mov     [rsp+198h+var_138], ebx
0x14001357a  mov     sil, [rsp+198h+var_148]
0x14001357f  test    ebx, ebx
0x140013581  jns     short loc_1400135C4
0x140013583  mov     eax, cs:dword_140019000
0x140013589  cmp     eax, 3
0x14001358c  jbe     short loc_1400135C4
0x14001358e  lea     rax, [rsp+198h+var_140]
0x140013593  mov     [rsp+198h+var_50], rax
0x14001359b  lea     rax, [rsp+198h+var_70]
0x1400135a3  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x1400135a8  mov     dword ptr [rsp+198h+var_140], ebx
0x1400135ac  mov     [rsp+198h+var_48], 4
0x1400135b8  lea     rdx, byte_140016D91; int
0x1400135bf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400135c4  mov     rcx, [rsp+198h+Binding]; Binding
0x1400135c9  test    rcx, rcx
0x1400135cc  jz      short loc_1400135F0
0x1400135ce  test    sil, sil
0x1400135d1  jz      short loc_1400135DF
0x1400135d3  call    cs:__imp_RpcBindingUnbind
0x1400135da  nop     dword ptr [rax+rax+00h]
0x1400135df  lea     rcx, [rsp+198h+Binding]; Binding
0x1400135e4  call    cs:__imp_RpcBindingFree
0x1400135eb  nop     dword ptr [rax+rax+00h]
0x1400135f0  mov     eax, ebx
0x1400135f2  mov     rcx, [rsp+198h+var_40]
0x1400135fa  xor     rcx, rsp; StackCookie
0x1400135fd  call    __security_check_cookie
0x140013602  add     rsp, 168h
0x140013609  pop     r15
0x14001360b  pop     r14
0x14001360d  pop     r13
0x14001360f  pop     r12
0x140013611  pop     rsi
0x140013612  pop     rbx
0x140013613  retn
0x14001417d  push    rbp
0x14001417f  sub     rsp, 50h
0x140014183  mov     rbp, rdx
0x140014186  mov     rcx, [rcx]
0x140014189  mov     ecx, [rcx]; ExceptionCode
0x14001418b  call    cs:__imp_RpcExceptionFilter
0x140014192  nop     dword ptr [rax+rax+00h]
0x140014197  nop
0x140014198  add     rsp, 50h
0x14001419c  pop     rbp
0x14001419d  retn
```
