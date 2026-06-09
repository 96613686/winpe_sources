# Notifier::AddCache(ICollectionNotify *,_GUID *)

- ea: `0x18000cd8c`
- end: `0x18000cf80`
- name: `?AddCache@Notifier@@QEAAJPEAUICollectionNotify@@PEAU_GUID@@@Z`
- size: `500`
- prototype: `int(Notifier *__hidden this, struct ICollectionNotify *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ca20`

## callees

- `0x1800097d4`
- `0x18000cd8c`
- `0x18000d078`
- `0x18000d15c`
- `0x18000d284`
- `0x18000dbe8`
- `0x180023444`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000cdda`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000cdda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ceff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ceff`

## pseudocode

```c
HRESULT __fastcall Notifier::AddCache(Notifier *this, IUnknown *a2, struct _GUID *a3)
{
  HRESULT result; // eax
  int inited; // ebx
  char *v8; // rax
  void *v9; // rsi
  GUID v10; // xmm0
  unsigned int v11; // r14d
  _QWORD *i; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  GUID pguid; // [rsp+40h] [rbp-48h] BYREF

  pguid = GUID_NULL;
  if ( !a3 )
    return -2147024809;
  *a3 = GUID_NULL;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    UTSemReadWriteES::LockWrite((Notifier *)((char *)this + 40));
    inited = ImpersonateAndSetProxyBlanketForCallback(a2);
    if ( inited >= 0 )
    {
      v8 = (char *)CoTaskMemAlloc(0x18u);
      v9 = v8;
      if ( v8 )
      {
        v10 = pguid;
        *(_QWORD *)v8 = a2;
        *(GUID *)(v8 + 8) = v10;
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
        inited = 0;
        v11 = pguid.Data1 % *((_DWORD *)this + 2);
        if ( *(_QWORD *)this )
        {
          for ( i = *(_QWORD **)(*(_QWORD *)this + 8LL * (pguid.Data1 % *((_DWORD *)this + 2))); i; i = (_QWORD *)*i )
          {
            v13 = *(_QWORD *)((char *)i + 12) - *(_QWORD *)&pguid.Data1;
            if ( !v13 )
              v13 = *(_QWORD *)((char *)i + 20) - *(_QWORD *)pguid.Data4;
            if ( !v13 )
              break;
          }
          if ( i )
            goto LABEL_20;
        }
        if ( *(_QWORD *)this )
        {
          if ( *((_DWORD *)this + 3) >= *((_DWORD *)this + 2) )
          {
            CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::GrowHashTable(this);
            v11 = pguid.Data1 % *((_DWORD *)this + 2);
          }
        }
        else
        {
          inited = CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::InitHashTable(
                     this,
                     *((unsigned int *)this + 2));
          if ( inited < 0 )
            goto LABEL_21;
        }
        v14 = CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::NewAssoc(this);
        i = (_QWORD *)v14;
        if ( v14 )
        {
          *(_DWORD *)(v14 + 8) = v11;
          *(GUID *)(v14 + 12) = pguid;
          *(_QWORD *)v14 = *(_QWORD *)(*(_QWORD *)this + 8LL * v11);
          *(_QWORD *)(*(_QWORD *)this + 8LL * v11) = v14;
LABEL_20:
          i[4] = v9;
          goto LABEL_21;
        }
        inited = -2147024882;
LABEL_21:
        if ( inited < 0 )
          CoTaskMemFree(v9);
        else
          *a3 = pguid;
        goto LABEL_29;
      }
      inited = -2147024882;
    }
LABEL_29:
    UTSemReadWriteES::UnlockWrite((Notifier *)((char *)this + 40));
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x18000cd8c  mov     [rsp+arg_18], rbx
0x18000cd91  push    rsi
0x18000cd92  push    rdi
0x18000cd93  push    r12
0x18000cd95  push    r14
0x18000cd97  push    r15
0x18000cd99  sub     rsp, 60h
0x18000cd9d  mov     rax, cs:__security_cookie
0x18000cda4  xor     rax, rsp
0x18000cda7  mov     [rsp+88h+var_38], rax
0x18000cdac  mov     r15, r8
0x18000cdaf  mov     r14, rdx
0x18000cdb2  mov     rdi, rcx
0x18000cdb5  mov     [rsp+88h+var_58], rcx
0x18000cdba  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000cdc1  movdqu  xmmword ptr [rsp+88h+pguid.Data1], xmm0
0x18000cdc7  test    r8, r8
0x18000cdca  jz      loc_18000CF79
0x18000cdd0  movdqu  xmmword ptr [r8], xmm0
0x18000cdd5  lea     rcx, [rsp+88h+pguid]; pguid
0x18000cdda  call    cs:__imp_CoCreateGuid
0x18000cde0  test    eax, eax
0x18000cde2  js      loc_18000CF57
0x18000cde8  lea     rcx, [rdi+28h]; this
0x18000cdec  call    ?LockWrite@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::LockWrite(void)
0x18000cdf1  nop
0x18000cdf2  mov     rcx, r14; pProxy
0x18000cdf5  call    ?ImpersonateAndSetProxyBlanketForCallback@@YAJPEAUIUnknown@@@Z; ImpersonateAndSetProxyBlanketForCallback(IUnknown *)
0x18000cdfa  mov     ebx, eax
0x18000cdfc  mov     [rsp+88h+var_64], eax
0x18000ce00  test    eax, eax
0x18000ce02  js      loc_18000CF4C
0x18000ce08  mov     ecx, 18h; cb
0x18000ce0d  call    cs:__imp_CoTaskMemAlloc
0x18000ce13  mov     rsi, rax
0x18000ce16  test    rax, rax
0x18000ce19  jz      loc_18000CF07
0x18000ce1f  movaps  xmm0, xmmword ptr [rsp+88h+pguid.Data1]
0x18000ce24  mov     [rax], r14
0x18000ce27  movdqu  xmmword ptr [rax+8], xmm0
0x18000ce2c  test    rsi, rsi
0x18000ce2f  jz      loc_18000CEF1
0x18000ce35  mov     rax, [r14]
0x18000ce38  mov     rcx, r14
0x18000ce3b  mov     rax, [rax+8]
0x18000ce3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce44  xor     ebx, ebx
0x18000ce46  mov     [rsp+88h+var_60], ebx
0x18000ce4a  mov     [rsp+88h+var_68], ebx
0x18000ce4e  xor     edx, edx
0x18000ce50  mov     eax, [rsp+88h+pguid.Data1]
0x18000ce54  div     dword ptr [rdi+8]
0x18000ce57  mov     r14d, edx
0x18000ce5a  mov     [rsp+88h+var_68], r14d
0x18000ce5f  mov     rcx, [rdi]
0x18000ce62  test    rcx, rcx
0x18000ce65  jz      short loc_18000CE96
0x18000ce67  mov     eax, r14d
0x18000ce6a  mov     rcx, [rcx+rdx*8]
0x18000ce6e  test    rcx, rcx
0x18000ce71  jz      short loc_18000CE91
0x18000ce73  mov     rax, [rcx+0Ch]
0x18000ce77  sub     rax, qword ptr [rsp+88h+pguid.Data1]
0x18000ce7c  jnz     short loc_18000CE87
0x18000ce7e  mov     rax, [rcx+14h]
0x18000ce82  sub     rax, qword ptr [rsp+88h+pguid.Data4]
0x18000ce87  test    rax, rax
0x18000ce8a  jz      short loc_18000CE91
0x18000ce8c  mov     rcx, [rcx]
0x18000ce8f  jmp     short loc_18000CE6E
0x18000ce91  test    rcx, rcx
0x18000ce94  jnz     short loc_18000CED9
0x18000ce96  cmp     [rdi], rbx
0x18000ce99  jz      short loc_18000CF15
0x18000ce9b  mov     eax, [rdi+8]
0x18000ce9e  cmp     [rdi+0Ch], eax
0x18000cea1  jnb     loc_18000CF2F
0x18000cea7  mov     rcx, rdi
0x18000ceaa  call    ?NewAssoc@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@IEAAPEAUCAssoc@1@XZ; CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::NewAssoc(void)
0x18000ceaf  mov     rcx, rax
0x18000ceb2  test    rax, rax
0x18000ceb5  jz      short loc_18000CF0E
0x18000ceb7  mov     [rax+8], r14d
0x18000cebb  movaps  xmm0, xmmword ptr [rsp+88h+pguid.Data1]
0x18000cec0  movdqu  xmmword ptr [rax+0Ch], xmm0
0x18000cec5  mov     r8d, r14d
0x18000cec8  mov     rax, [rdi]
0x18000cecb  mov     rdx, [rax+r8*8]
0x18000cecf  mov     [rcx], rdx
0x18000ced2  mov     rax, [rdi]
0x18000ced5  mov     [rax+r8*8], rcx
0x18000ced9  mov     [rcx+20h], rsi
0x18000cedd  mov     [rsp+88h+var_64], ebx
0x18000cee1  test    ebx, ebx
0x18000cee3  js      short loc_18000CEFC
0x18000cee5  movaps  xmm0, xmmword ptr [rsp+88h+pguid.Data1]
0x18000ceea  movdqu  xmmword ptr [r15], xmm0
0x18000ceef  jmp     short loc_18000CF4C
0x18000cef1  mov     ebx, 8007000Eh
0x18000cef6  mov     [rsp+88h+var_64], ebx
0x18000cefa  jmp     short loc_18000CF4C
0x18000cefc  mov     rcx, rsi; pv
0x18000ceff  call    cs:__imp_CoTaskMemFree
0x18000cf05  jmp     short loc_18000CF4C
0x18000cf07  xor     esi, esi
0x18000cf09  jmp     loc_18000CE2C
0x18000cf0e  mov     ebx, 8007000Eh
0x18000cf13  jmp     short loc_18000CEDD
0x18000cf15  mov     edx, [rdi+8]
0x18000cf18  mov     rcx, rdi
0x18000cf1b  call    ?InitHashTable@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@QEAAJIH@Z; CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::InitHashTable(uint,int)
0x18000cf20  mov     ebx, eax
0x18000cf22  mov     [rsp+88h+var_60], eax
0x18000cf26  test    eax, eax
0x18000cf28  js      short loc_18000CEDD
0x18000cf2a  jmp     loc_18000CEA7
0x18000cf2f  mov     rcx, rdi
0x18000cf32  call    ?GrowHashTable@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@IEAAXXZ; CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::GrowHashTable(void)
0x18000cf37  xor     edx, edx
0x18000cf39  mov     eax, [rsp+88h+pguid.Data1]
0x18000cf3d  div     dword ptr [rdi+8]
0x18000cf40  mov     r14d, edx
0x18000cf43  mov     [rsp+88h+var_68], edx
0x18000cf47  jmp     loc_18000CEA7
0x18000cf4c  lea     rcx, [rdi+28h]; this
0x18000cf50  call    ?UnlockWrite@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockWrite(void)
0x18000cf55  mov     eax, ebx
0x18000cf57  mov     rcx, [rsp+88h+var_38]
0x18000cf5c  xor     rcx, rsp; StackCookie
0x18000cf5f  call    __security_check_cookie
0x18000cf64  mov     rbx, [rsp+88h+arg_18]
0x18000cf6c  add     rsp, 60h
0x18000cf70  pop     r15
0x18000cf72  pop     r14
0x18000cf74  pop     r12
0x18000cf76  pop     rdi
0x18000cf77  pop     rsi
0x18000cf78  retn
0x18000cf79  mov     eax, 80070057h
0x18000cf7e  jmp     short loc_18000CF57
0x180043a3e  push    rbp
0x180043a40  sub     rsp, 20h
0x180043a44  mov     rbp, rdx
0x180043a47  mov     rcx, [rbp+30h]
0x180043a4b  add     rcx, 28h ; '('; this
0x180043a4f  call    ?UnlockWrite@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockWrite(void)
0x180043a54  nop
0x180043a55  add     rsp, 20h
0x180043a59  pop     rbp
0x180043a5a  retn
```
