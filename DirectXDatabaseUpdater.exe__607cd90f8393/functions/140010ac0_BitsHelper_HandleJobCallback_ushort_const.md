# BitsHelper::HandleJobCallback(ushort const *)

- ea: `0x140010ac0`
- end: `0x140010c7b`
- name: `?HandleJobCallback@BitsHelper@@QEAAJPEBG@Z`
- size: `443`
- prototype: `__int64 __fastcall(BitsHelper *__hidden this, LPCOLESTR lpsz)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140007ad8`

## callees

- `0x140002f40`
- `0x140005cac`
- `0x140006150`
- `0x14000a4bc`
- `0x1400100e0`
- `0x140010ac0`
- `0x140010c84`
- `0x140011a14`
- `0x140013d10`
- `0x140013f5c`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140010b1c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140010b1c`

## string_xrefs

- `0x140010af6`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010b89`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
__int64 __fastcall BitsHelper::HandleJobCallback(BitsHelper *this, LPCOLESTR lpsz)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  int IsLogonTriggerEnabled; // eax
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // r8d
  struct IBackgroundCopyJob *v15; // [rsp+20h] [rbp-60h] BYREF
  int v16; // [rsp+28h] [rbp-58h] BYREF
  _OWORD v17[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+50h] [rbp-30h]
  char v19; // [rsp+58h] [rbp-28h]
  CLSID pclsid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = BitsHelper::Init(this);
  if ( v4 >= 0 )
  {
    pclsid = 0;
    v4 = CLSIDFromString(lpsz, &pclsid);
    if ( v4 < 0 )
    {
      v5 = 188;
      goto LABEL_3;
    }
    v15 = 0;
    v6 = *(__int64 **)this;
    v7 = **(_QWORD **)this;
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, CLSID *, struct IBackgroundCopyJob **))(v7 + 32))(v6, &pclsid, &v15);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v16 = 0;
      v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, int *))v15->lpVtbl->GetState)(v15, &v16);
      v4 = v8;
      if ( v8 >= 0 )
      {
        if ( v16 == 6 )
        {
          v8 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v15->lpVtbl->Complete)(v15);
          v4 = v8;
          if ( v8 >= 0 )
          {
            memset(v17, 0, sizeof(v17));
            v18 = 0;
            v19 = 0;
            IsLogonTriggerEnabled = TaskHelper::SetIsLogonTriggerEnabled((TaskHelper *)v17, 0);
            if ( IsLogonTriggerEnabled < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xCA,
                v11,
                (const char *)(unsigned int)IsLogonTriggerEnabled,
                (int)v15);
            v12 = TaskHelper::SaveLogonTriggerChange((TaskHelper *)v17);
            if ( v12 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xCB, v13, (const char *)(unsigned int)v12, (int)v15);
            TaskHelper::~TaskHelper((TaskHelper *)v17);
            v4 = 0;
            goto LABEL_22;
          }
          v9 = 198;
        }
        else
        {
          v8 = BitsHelper::HandleError(this, v15);
          v4 = v8;
          if ( v8 >= 0 )
          {
            v4 = 1;
            goto LABEL_22;
          }
          v9 = 210;
        }
      }
      else
      {
        v9 = 194;
      }
    }
    else
    {
      v9 = 191;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v8,
      (int)v15);
LABEL_22:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v15);
    return (unsigned int)v4;
  }
  v5 = 185;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
    (const char *)(unsigned int)v4,
    (int)v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140010ac0  mov     [rsp-18h+arg_10], rbx
0x140010ac5  push    rbp
0x140010ac6  push    rsi
0x140010ac7  push    rdi
0x140010ac8  mov     rbp, rsp
0x140010acb  sub     rsp, 80h
0x140010ad2  mov     rax, cs:__security_cookie
0x140010ad9  xor     rax, rsp
0x140010adc  mov     [rbp+var_10], rax
0x140010ae0  mov     rsi, rdx
0x140010ae3  mov     rdi, rcx
0x140010ae6  call    ?Init@BitsHelper@@AEAAJXZ; BitsHelper::Init(void)
0x140010aeb  mov     ebx, eax
0x140010aed  test    eax, eax
0x140010aef  jns     short loc_140010B0E
0x140010af1  mov     edx, 0B9h; void *
0x140010af6  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010afd  mov     r9d, ebx; char *
0x140010b00  mov     rcx, [rbp+18h]; this
0x140010b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010b09  jmp     loc_140010C5A
0x140010b0e  xorps   xmm0, xmm0
0x140010b11  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x140010b15  lea     rdx, [rbp+pclsid]; pclsid
0x140010b19  mov     rcx, rsi; lpsz
0x140010b1c  call    cs:__imp_CLSIDFromString
0x140010b22  mov     ebx, eax
0x140010b24  test    eax, eax
0x140010b26  jns     short loc_140010B2F
0x140010b28  mov     edx, 0BCh
0x140010b2d  jmp     short loc_140010AF6
0x140010b2f  mov     [rbp+var_60], 0
0x140010b37  mov     rcx, [rdi]
0x140010b3a  mov     rax, [rcx]
0x140010b3d  mov     [rbp+var_60], 0
0x140010b45  lea     r8, [rbp+var_60]
0x140010b49  lea     rdx, [rbp+pclsid]
0x140010b4d  mov     rax, [rax+20h]
0x140010b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b56  mov     ebx, eax
0x140010b58  test    eax, eax
0x140010b5a  jns     short loc_140010B63
0x140010b5c  mov     edx, 0BFh
0x140010b61  jmp     short loc_140010B89
0x140010b63  mov     [rbp+var_58], 0
0x140010b6a  mov     rcx, [rbp+var_60]
0x140010b6e  mov     rax, [rcx]
0x140010b71  lea     rdx, [rbp+var_58]
0x140010b75  mov     rax, [rax+70h]
0x140010b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b7e  mov     ebx, eax
0x140010b80  test    eax, eax
0x140010b82  jns     short loc_140010BA1
0x140010b84  mov     edx, 0C2h; void *
0x140010b89  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010b90  mov     r9d, eax; char *
0x140010b93  mov     rcx, [rbp+18h]; this
0x140010b97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010b9c  jmp     loc_140010C51
0x140010ba1  cmp     [rbp+var_58], 6
0x140010ba5  jnz     loc_140010C30
0x140010bab  mov     rcx, [rbp+var_60]
0x140010baf  mov     rax, [rcx]
0x140010bb2  mov     rax, [rax+48h]
0x140010bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bbb  mov     ebx, eax
0x140010bbd  test    eax, eax
0x140010bbf  jns     short loc_140010BC8
0x140010bc1  mov     edx, 0C6h
0x140010bc6  jmp     short loc_140010B89
0x140010bc8  xorps   xmm0, xmm0
0x140010bcb  movdqu  [rbp+var_50], xmm0
0x140010bd0  xorps   xmm1, xmm1
0x140010bd3  movdqu  [rbp+var_40], xmm1
0x140010bd8  mov     [rbp+var_30], 0
0x140010be0  mov     [rbp+var_28], 0
0x140010be4  xor     edx, edx; bool
0x140010be6  lea     rcx, [rbp+var_50]; this
0x140010bea  call    ?SetIsLogonTriggerEnabled@TaskHelper@@QEAAJ_N@Z; TaskHelper::SetIsLogonTriggerEnabled(bool)
0x140010bef  mov     rcx, [rbp+18h]; this
0x140010bf3  test    eax, eax
0x140010bf5  jns     short loc_140010C04
0x140010bf7  mov     r9d, eax; char *
0x140010bfa  mov     edx, 0CAh; void *
0x140010bff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140010c04  lea     rcx, [rbp+var_50]; this
0x140010c08  call    ?SaveLogonTriggerChange@TaskHelper@@QEAAJXZ; TaskHelper::SaveLogonTriggerChange(void)
0x140010c0d  mov     rcx, [rbp+18h]; this
0x140010c11  test    eax, eax
0x140010c13  jns     short loc_140010C23
0x140010c15  mov     r9d, eax; char *
0x140010c18  mov     edx, 0CBh; void *
0x140010c1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140010c22  nop
0x140010c23  lea     rcx, [rbp+var_50]; this
0x140010c27  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x140010c2c  xor     ebx, ebx
0x140010c2e  jmp     short loc_140010C51
0x140010c30  mov     rdx, [rbp+var_60]; struct IBackgroundCopyJob *
0x140010c34  mov     rcx, rdi; this
0x140010c37  call    ?HandleError@BitsHelper@@AEAAJPEAUIBackgroundCopyJob@@@Z; BitsHelper::HandleError(IBackgroundCopyJob *)
0x140010c3c  mov     ebx, eax
0x140010c3e  test    eax, eax
0x140010c40  jns     short loc_140010C4C
0x140010c42  mov     edx, 0D2h
0x140010c47  jmp     loc_140010B89
0x140010c4c  mov     ebx, 1
0x140010c51  lea     rcx, [rbp+var_60]
0x140010c55  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010c5a  mov     eax, ebx
0x140010c5c  mov     rcx, [rbp+var_10]
0x140010c60  xor     rcx, rsp; StackCookie
0x140010c63  call    __security_check_cookie
0x140010c68  mov     rbx, [rsp+80h+arg_10]
0x140010c70  add     rsp, 80h
0x140010c77  pop     rdi
0x140010c78  pop     rsi
0x140010c79  pop     rbp
0x140010c7a  retn
```
