# UICCSEProxy::GetIccId(uchar * *,ulong *)

- ea: `0x1800779b0`
- end: `0x180077bd1`
- name: `?GetIccId@UICCSEProxy@@UEAAJPEAPEAEPEAK@Z`
- size: `545`
- prototype: `__int64 __fastcall(UICCSEProxy *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x1800127c0`
- `0x180076594`
- `0x1800779b0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077b15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180077aac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UICCSEProxy::GetIccId(UICCSEProxy *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v6; // rcx
  int Resource; // eax
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r8
  volatile signed __int32 *v11; // rdi
  _BYTE *v12; // rax
  void *v13; // rdi
  _BYTE *v14; // rcx
  int v15; // eax
  volatile signed __int32 *v16; // rsi
  int v18; // [rsp+20h] [rbp-50h]
  unsigned int v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h]
  _BYTE *v21; // [rsp+40h] [rbp-30h]
  int v22[4]; // [rsp+48h] [rbp-28h] BYREF
  const wchar_t *v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v20 = 0;
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v23 = L"SecureElement::GetIccId";
    v24 = 48;
    McGenEventWrite_EventWriteTransfer(this, ")#", a3, 2, v22);
  }
  v6 = *((_QWORD *)this + 2);
  *(_OWORD *)v22 = 0;
  Resource = OnDemandResource<UICCSmartcardConnection,UICCSmartcardConnectionManager>::GetResource(
               *(_QWORD *)(v6 + 144),
               v22);
  v8 = Resource;
  if ( Resource < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\uicc\\src\\uiccsecureelement.cpp",
      (const char *)(unsigned int)Resource,
      v18);
LABEL_5:
    v11 = *(volatile signed __int32 **)&v22[2];
    if ( *(_QWORD *)&v22[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v22[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    goto LABEL_20;
  }
  v19 = 16;
  v12 = CoTaskMemAlloc(0x10u);
  v13 = v12;
  v21 = v12;
  if ( v12 )
  {
    v14 = v12 + 16;
    do
      *v12++ = 0;
    while ( v12 != v14 );
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, void *, unsigned int *))(**(_QWORD **)v22 + 48LL))(*(_QWORD *)v22, v13, &v19);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\uicc\\src\\uiccsecureelement.cpp",
      (const char *)(unsigned int)v15,
      v18);
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_5;
  }
  *a3 = v19;
  v16 = *(volatile signed __int32 **)&v22[2];
  if ( *(_QWORD *)&v22[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v22[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  *a2 = (unsigned __int8 *)v13;
  v8 = 0;
LABEL_20:
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v23 = L"SecureElement::GetIccId";
    v24 = 48;
    McGenEventWrite_EventWriteTransfer(v9, "*#", v10, 2, v22);
  }
  return v8;
}

```

## disassembly

```asm
0x1800779b0  push    rbp
0x1800779b2  push    rbx
0x1800779b3  push    rsi
0x1800779b4  push    rdi
0x1800779b5  push    r12
0x1800779b7  push    r14
0x1800779b9  push    r15
0x1800779bb  mov     rbp, rsp
0x1800779be  sub     rsp, 70h
0x1800779c2  mov     rax, cs:__security_cookie
0x1800779c9  xor     rax, rsp
0x1800779cc  mov     [rbp+var_8], rax
0x1800779d0  mov     r15, r8
0x1800779d3  mov     r12, rdx
0x1800779d6  mov     rbx, rcx
0x1800779d9  xor     r14d, r14d
0x1800779dc  mov     [rbp+var_38], r14
0x1800779e0  lea     rax, aSecureelementG; "SecureElement::GetIccId"
0x1800779e7  test    cs:byte_180132D81, 10h
0x1800779ee  jz      short loc_180077A15
0x1800779f0  mov     [rbp+var_18], rax
0x1800779f4  mov     [rbp+var_10], 30h ; '0'
0x1800779fc  lea     rax, [rbp+var_28]
0x180077a00  mov     qword ptr [rsp+70h+var_50], rax; int
0x180077a05  lea     r9d, [r14+2]
0x180077a09  lea     rdx, SEMgr_Event_COM_API_Start; ")#"
0x180077a10  call    McGenEventWrite_EventWriteTransfer
0x180077a15  mov     rcx, [rbx+10h]
0x180077a19  xorps   xmm0, xmm0
0x180077a1c  movdqu  xmmword ptr [rbp+var_28], xmm0
0x180077a21  lea     rdx, [rbp+var_28]
0x180077a25  mov     rcx, [rcx+90h]
0x180077a2c  call    ?GetResource@?$OnDemandResource@UUICCSmartcardConnection@@VUICCSmartcardConnectionManager@@@@QEAAJPEAV?$shared_ptr@UUICCSmartcardConnection@@@std@@@Z; OnDemandResource<UICCSmartcardConnection,UICCSmartcardConnectionManager>::GetResource(std::shared_ptr<UICCSmartcardConnection> *)
0x180077a31  mov     esi, eax
0x180077a33  test    eax, eax
0x180077a35  jns     short loc_180077AA0
0x180077a37  mov     rcx, [rbp+38h]; this
0x180077a3b  mov     r9d, eax; char *
0x180077a3e  lea     r8, aOnecoreuapDsNf; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180077a45  mov     edx, 3Ch ; '<'; void *
0x180077a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077a4f  nop
0x180077a50  mov     rdi, qword ptr [rbp+var_28+8]
0x180077a54  test    rdi, rdi
0x180077a57  jz      loc_180077B6E
0x180077a5d  or      ebx, 0FFFFFFFFh
0x180077a60  mov     eax, ebx
0x180077a62  lock xadd [rdi+8], eax
0x180077a67  add     eax, ebx
0x180077a69  jnz     loc_180077B6E
0x180077a6f  mov     rax, [rdi]
0x180077a72  mov     rcx, rdi
0x180077a75  mov     rax, [rax]
0x180077a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a7d  mov     eax, ebx
0x180077a7f  lock xadd [rdi+0Ch], eax
0x180077a84  add     eax, ebx
0x180077a86  jnz     loc_180077B6E
0x180077a8c  mov     rax, [rdi]
0x180077a8f  mov     rcx, rdi
0x180077a92  mov     rax, [rax+8]
0x180077a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a9b  jmp     loc_180077B6E
0x180077aa0  mov     [rbp+var_40], 10h
0x180077aa7  mov     ecx, 10h; cb
0x180077aac  call    cs:__imp_CoTaskMemAlloc
0x180077ab2  mov     rdi, rax
0x180077ab5  mov     [rbp+var_30], rax
0x180077ab9  test    rax, rax
0x180077abc  jz      short loc_180077AD3
0x180077abe  lea     rcx, [rax+10h]
0x180077ac2  cmp     rax, rcx
0x180077ac5  jz      short loc_180077AD3
0x180077ac7  xor     edx, edx
0x180077ac9  mov     [rax], dl
0x180077acb  inc     rax
0x180077ace  cmp     rax, rcx
0x180077ad1  jnz     short loc_180077AC7
0x180077ad3  mov     rcx, qword ptr [rbp+var_28]
0x180077ad7  mov     rax, [rcx]
0x180077ada  lea     r8, [rbp+var_40]
0x180077ade  mov     rdx, rdi
0x180077ae1  mov     rax, [rax+30h]
0x180077ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077aea  mov     esi, eax
0x180077aec  test    eax, eax
0x180077aee  jns     short loc_180077B20
0x180077af0  mov     rcx, [rbp+38h]; this
0x180077af4  mov     r9d, eax; char *
0x180077af7  lea     r8, aOnecoreuapDsNf; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180077afe  mov     edx, 41h ; 'A'; void *
0x180077b03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077b08  nop
0x180077b09  test    rdi, rdi
0x180077b0c  jz      loc_180077A50
0x180077b12  mov     rcx, rdi; pv
0x180077b15  call    cs:__imp_CoTaskMemFree
0x180077b1b  jmp     loc_180077A50
0x180077b20  mov     eax, [rbp+var_40]
0x180077b23  mov     [r15], eax
0x180077b26  mov     rsi, qword ptr [rbp+var_28+8]
0x180077b2a  test    rsi, rsi
0x180077b2d  jz      short loc_180077B65
0x180077b2f  or      ebx, 0FFFFFFFFh
0x180077b32  mov     eax, ebx
0x180077b34  lock xadd [rsi+8], eax
0x180077b39  add     eax, ebx
0x180077b3b  jnz     short loc_180077B65
0x180077b3d  mov     rax, [rsi]
0x180077b40  mov     rcx, rsi
0x180077b43  mov     rax, [rax]
0x180077b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b4b  mov     eax, ebx
0x180077b4d  lock xadd [rsi+0Ch], eax
0x180077b52  add     eax, ebx
0x180077b54  jnz     short loc_180077B65
0x180077b56  mov     rax, [rsi]
0x180077b59  mov     rcx, rsi
0x180077b5c  mov     rax, [rax+8]
0x180077b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b65  xor     r14d, r14d
0x180077b68  mov     [r12], rdi
0x180077b6c  xor     esi, esi
0x180077b6e  test    cs:byte_180132D81, 10h
0x180077b75  jz      short loc_180077BA6
0x180077b77  lea     rax, aSecureelementG; "SecureElement::GetIccId"
0x180077b7e  mov     [rbp+var_18], rax
0x180077b82  mov     [rbp+var_10], 30h ; '0'
0x180077b8a  lea     rax, [rbp+var_28]
0x180077b8e  mov     qword ptr [rsp+70h+var_50], rax
0x180077b93  mov     r9d, 2
0x180077b99  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x180077ba0  call    McGenEventWrite_EventWriteTransfer
0x180077ba5  nop
0x180077ba6  test    r14, r14
0x180077ba9  jz      short loc_180077BB4
0x180077bab  mov     rcx, r14; pv
0x180077bae  call    cs:__imp_CoTaskMemFree
0x180077bb4  mov     eax, esi
0x180077bb6  mov     rcx, [rbp+var_8]
0x180077bba  xor     rcx, rsp; StackCookie
0x180077bbd  call    __security_check_cookie
0x180077bc2  add     rsp, 70h
0x180077bc6  pop     r15
0x180077bc8  pop     r14
0x180077bca  pop     r12
0x180077bcc  pop     rdi
0x180077bcd  pop     rsi
0x180077bce  pop     rbx
0x180077bcf  pop     rbp
0x180077bd0  retn
```
