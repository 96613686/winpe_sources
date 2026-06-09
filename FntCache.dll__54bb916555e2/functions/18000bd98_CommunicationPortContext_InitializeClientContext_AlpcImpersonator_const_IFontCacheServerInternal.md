# CommunicationPortContext::InitializeClientContext(AlpcImpersonator const &,IFontCacheServerInternal *)

- ea: `0x18000bd98`
- end: `0x18000bf9a`
- name: `?InitializeClientContext@CommunicationPortContext@@AEAAXAEBVAlpcImpersonator@@PEAUIFontCacheServerInternal@@@Z`
- size: `514`
- prototype: `void __fastcall(CommunicationPortContext *__hidden this, const struct AlpcImpersonator *, struct IFontCacheServerInternal *)`
- caller_count: `6`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c20c`
- `0x18000c674`
- `0x18000c6cc`
- `0x180095cac`
- `0x18009664c`
- `0x1800b9e8c`

## callees

- `0x18000bc70`
- `0x18000bcc4`
- `0x18000bd98`
- `0x18000d7ec`
- `0x18001db38`
- `0x180028c50`
- `0x18008fb04`
- `0x180096f68`
- `0x1800974ec`
- `0x18009853c`
- `0x18009c0e0`
- `0x1800aa650`
- `0x1800aa674`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf69`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CommunicationPortContext::InitializeClientContext(
        CommunicationPortContext *this,
        const struct AlpcImpersonator *a2,
        struct IFontCacheServerInternal *a3)
{
  void *v5; // rdi
  struct Sid *UserSid; // rbx
  __int64 v7; // rax
  char *v8; // rsi
  __int64 v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  char v12; // al
  struct DWrite::RefString::Data *v13[2]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-19h] BYREF
  _DWORD v15[6]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+Fh]
  int v17; // [rsp+70h] [rbp+17h]
  int v18; // [rsp+74h] [rbp+1Bh]
  _QWORD *v19; // [rsp+78h] [rbp+1Fh]

  v5 = OpenAccessToken((unsigned int)this, (bool)a2);
  v14[0] = v5;
  *((_DWORD *)this + 17) = GetTokenSessionId((const struct AccessToken *)v14);
  UserSid = CreateUserSid((struct AccessToken *)v14);
  v14[1] = UserSid;
  v7 = Sid::ToString(UserSid, v13);
  v8 = (char *)this + 56;
  DWrite::RefString::operator=((char *)this + 56, v7);
  DWrite::RefString::DecrementRef(v13[0]);
  if ( *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) >= 0xBu
    && !wmemcmp((const wchar_t *)(*((_QWORD *)this + 7) + 8LL), L"S-1-5-90-0-", 0xBu) )
  {
    v9 = DWrite::RefString::RefString((DWrite::RefString *)v13, L"S-1-5-18");
    DWrite::RefString::operator=((char *)this + 56, v9);
    DWrite::RefString::DecrementRef(v13[0]);
  }
  v10 = (_QWORD *)(*(_QWORD *)v8 + 8LL);
  if ( *(_DWORD *)(*(_QWORD *)v8 + 4LL) <= 9u )
    goto LABEL_13;
  v11 = *v10 - 0x2D0031002D0053LL;
  if ( *v10 == 0x2D0031002D0053LL )
  {
    v11 = *(_QWORD *)(*(_QWORD *)v8 + 16LL) - 0x310032002D0035LL;
    if ( *(_QWORD *)(*(_QWORD *)v8 + 16LL) == 0x310032002D0035LL )
      v11 = *(unsigned __int16 *)(*(_QWORD *)v8 + 24LL) - 45LL;
  }
  if ( v11 )
LABEL_13:
    v12 = 0;
  else
    v12 = 1;
  *((_BYTE *)this + 72) = v12;
  *(_OWORD *)v13 = 0;
  v15[0] = 1;
  v15[1] = 0;
  v15[2] = *((_DWORD *)this + 17);
  v15[3] = 0;
  v15[4] = 0;
  v15[5] = 0;
  v16 = (-(__int64)(v12 != 0) & 0xFF8D9A8CFCF70407uLL) + 0x726573756E6F6ELL;
  *(_OWORD *)v13 = 0;
  v17 = 3;
  v18 = 0;
  v19 = v10;
  EventLogger::LogGenericEvent(*((unsigned int *)this + 4), 0x74726F5063706C41LL, 1953066601, v15, 3);
  (*(void (__fastcall **)(struct IFontCacheServerInternal *, _QWORD, __int64, char *))(*(_QWORD *)a3 + 48LL))(
    a3,
    *((unsigned int *)this + 17),
    *(_QWORD *)v8 + 8LL,
    (char *)this + 48);
  if ( UserSid )
  {
    std::vector<unsigned char>::_Tidy(UserSid);
    operator delete(UserSid, 0x18u);
  }
  CloseHandle(v5);
}

```

## disassembly

```asm
0x18000bd98  mov     [rsp-8+arg_8], rbx
0x18000bd9d  push    rbp
0x18000bd9e  push    rsi
0x18000bd9f  push    rdi
0x18000bda0  push    r14
0x18000bda2  push    r15
0x18000bda4  lea     rbp, [rsp-37h]
0x18000bda9  sub     rsp, 90h
0x18000bdb0  mov     rax, cs:__security_cookie
0x18000bdb7  xor     rax, rsp
0x18000bdba  mov     [rbp+57h+var_30], rax
0x18000bdbe  mov     r15, r8
0x18000bdc1  mov     r14, rcx
0x18000bdc4  call    ?OpenAccessToken@@YAPEAXK_N@Z; OpenAccessToken(ulong,bool)
0x18000bdc9  mov     rdi, rax
0x18000bdcc  mov     [rbp+57h+var_70], rax
0x18000bdd0  lea     rcx, [rbp+57h+var_70]; struct AccessToken *
0x18000bdd4  call    ?GetTokenSessionId@@YAIAEBVAccessToken@@@Z; GetTokenSessionId(AccessToken const &)
0x18000bdd9  mov     [r14+44h], eax
0x18000bddd  lea     rcx, [rbp+57h+var_70]; struct AccessToken *
0x18000bde1  call    ?CreateUserSid@@YAPEAVSid@@AEAVAccessToken@@@Z; CreateUserSid(AccessToken &)
0x18000bde6  mov     rbx, rax
0x18000bde9  mov     [rbp+57h+var_68], rax
0x18000bded  lea     rdx, [rbp+57h+var_80]
0x18000bdf1  mov     rcx, rax
0x18000bdf4  call    ?ToString@Sid@@QEBA?AVRefString@DWrite@@XZ; Sid::ToString(void)
0x18000bdf9  lea     rsi, [r14+38h]
0x18000bdfd  mov     rdx, rax
0x18000be00  mov     rcx, rsi
0x18000be03  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18000be08  mov     rcx, [rbp+57h+var_80]; struct DWrite::RefString::Data *
0x18000be0c  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000be11  mov     rcx, [rsi]
0x18000be14  mov     r8d, 0Bh; N
0x18000be1a  cmp     [rcx+4], r8d
0x18000be1e  jb      short loc_18000BE58
0x18000be20  add     rcx, 8; S1
0x18000be24  lea     rdx, aS15900; "S-1-5-90-0-"
0x18000be2b  call    wmemcmp
0x18000be30  test    eax, eax
0x18000be32  jnz     short loc_18000BE58
0x18000be34  lea     rdx, aS1518; "S-1-5-18"
0x18000be3b  lea     rcx, [rbp+57h+var_80]; this
0x18000be3f  call    ??0RefString@DWrite@@QEAA@PEB_W@Z; DWrite::RefString::RefString(wchar_t const *)
0x18000be44  mov     rdx, rax
0x18000be47  mov     rcx, rsi
0x18000be4a  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18000be4f  mov     rcx, [rbp+57h+var_80]; struct DWrite::RefString::Data *
0x18000be53  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000be58  mov     rax, [rsi]
0x18000be5b  lea     rdx, [rax+8]
0x18000be5f  cmp     dword ptr [rax+4], 9
0x18000be63  jbe     loc_18000BF92
0x18000be69  mov     rcx, [rdx]
0x18000be6c  sub     rcx, cs:qword_1800EAEC8
0x18000be73  jnz     short loc_18000BE90
0x18000be75  mov     rcx, [rdx+8]
0x18000be79  sub     rcx, cs:qword_1800EAED0
0x18000be80  jnz     short loc_18000BE90
0x18000be82  movzx   ecx, word ptr [rdx+10h]
0x18000be86  movzx   eax, cs:word_1800EAED8
0x18000be8d  sub     rcx, rax
0x18000be90  test    rcx, rcx
0x18000be93  jnz     loc_18000BF92
0x18000be99  mov     al, 1
0x18000be9b  mov     [r14+48h], al
0x18000be9f  neg     al
0x18000bea1  sbb     rcx, rcx
0x18000bea4  mov     rax, 0FF8D9A8CFCF70407h
0x18000beae  and     rcx, rax
0x18000beb1  mov     rax, 726573756E6F6Eh
0x18000bebb  add     rcx, rax
0x18000bebe  xorps   xmm0, xmm0
0x18000bec1  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000bec5  mov     [rbp+57h+var_60], 1
0x18000becc  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000becf  mov     [rbp+57h+var_5C], eax
0x18000bed2  mov     eax, [r14+44h]
0x18000bed6  mov     [rbp+57h+var_58], eax
0x18000bed9  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x18000bedc  mov     [rbp+57h+var_54], eax
0x18000bedf  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000bee3  mov     [rbp+57h+var_50], 0
0x18000beea  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000beed  mov     [rbp+57h+var_4C], eax
0x18000bef0  mov     [rbp+57h+var_48], rcx
0x18000bef4  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000bef8  mov     ecx, 3
0x18000befd  mov     [rbp+57h+var_40], ecx
0x18000bf00  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000bf03  mov     [rbp+57h+var_3C], eax
0x18000bf06  mov     [rbp+57h+var_38], rdx
0x18000bf0a  mov     rdx, 74726F5063706C41h
0x18000bf14  mov     [rsp+0B0h+var_90], rcx
0x18000bf19  lea     r9, [rbp+57h+var_60]
0x18000bf1d  mov     r8d, 74696E69h
0x18000bf23  mov     ecx, [r14+10h]
0x18000bf27  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x18000bf2c  mov     rax, [r15]
0x18000bf2f  lea     r9, [r14+30h]
0x18000bf33  mov     r8, [rsi]
0x18000bf36  add     r8, 8
0x18000bf3a  mov     edx, [r14+44h]
0x18000bf3e  mov     rcx, r15
0x18000bf41  mov     rax, [rax+30h]
0x18000bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf4a  nop
0x18000bf4b  test    rbx, rbx
0x18000bf4e  jz      short loc_18000BF66
0x18000bf50  mov     rcx, rbx
0x18000bf53  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000bf58  mov     edx, 18h; unsigned __int64
0x18000bf5d  mov     rcx, rbx; void *
0x18000bf60  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bf65  nop
0x18000bf66  mov     rcx, rdi; hObject
0x18000bf69  call    cs:__imp_CloseHandle
0x18000bf6f  mov     rcx, [rbp+57h+var_30]
0x18000bf73  xor     rcx, rsp; StackCookie
0x18000bf76  call    __security_check_cookie
0x18000bf7b  mov     rbx, [rsp+0B0h+arg_8]
0x18000bf83  add     rsp, 90h
0x18000bf8a  pop     r15
0x18000bf8c  pop     r14
0x18000bf8e  pop     rdi
0x18000bf8f  pop     rsi
0x18000bf90  pop     rbp
0x18000bf91  retn
0x18000bf92  xor     al, al
0x18000bf94  jmp     loc_18000BE9B
```
