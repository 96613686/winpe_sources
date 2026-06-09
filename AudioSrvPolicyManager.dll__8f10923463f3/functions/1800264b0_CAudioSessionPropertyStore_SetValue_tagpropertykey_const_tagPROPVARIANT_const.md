# CAudioSessionPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x1800264b0`
- end: `0x1800266c3`
- name: `?SetValue@CAudioSessionPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `531`
- prototype: `int(CAudioSessionPropertyStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a384`
- `0x1800264b0`
- `0x1800266cc`
- `0x18002cae8`
- `0x180031eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026507`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026507`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002661a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800266a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002661a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800266a2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002655b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800265e3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002655b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800265e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002658c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002658c`

## pseudocode

```c
__int64 __fastcall CAudioSessionPropertyStore::SetValue(
        CAudioSessionPropertyStore *this,
        const struct _tagpropertykey *a2,
        const PROPVARIANT *a3)
{
  _QWORD *v7; // r14
  char *i; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  HRESULT v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  char *v14; // rax
  char *v15; // rdi
  HRESULT v16; // eax
  unsigned int v17; // esi
  GUID fmtid; // xmm0
  PROPVARIANT pvarDest[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char *v22; // [rsp+70h] [rbp+8h] BYREF

  if ( CAudioSessionPropertyStore::IsValidProperty(this, (const struct tagPROPVARIANT *)a3) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v7 = (_QWORD *)((char *)this + 32);
    for ( i = (char *)this + 32; ; i = (char *)(v9 + 48) )
    {
      v9 = *(_QWORD *)i;
      if ( !*(_QWORD *)i )
        break;
      if ( *(_DWORD *)(v9 + 16) == a2->pid )
      {
        v10 = *(_QWORD *)v9 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)v9 == *(_QWORD *)&a2->fmtid.Data1 )
          v10 = *(_QWORD *)(v9 + 8) - *(_QWORD *)a2->fmtid.Data4;
        if ( !v10 )
        {
          *(_OWORD *)pvarDest = 0;
          v20 = 0;
          v11 = PropVariantCopy(pvarDest, a3);
          v12 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F3,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
              (const char *)(unsigned int)v11,
              (int)pvarDest[0]);
LABEL_25:
            if ( this != (CAudioSessionPropertyStore *)-48LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
            return v12;
          }
          PropVariantClear((PROPVARIANT *)(*(_QWORD *)i + 24LL));
          v13 = *(_QWORD *)i;
          *(_OWORD *)(v13 + 24) = *(_OWORD *)pvarDest;
          *(_QWORD *)(v13 + 40) = v20;
          goto LABEL_21;
        }
      }
    }
    v14 = (char *)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v22 = v14;
    v15 = v14;
    if ( !v14 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)0x8007000ELL,
        (int)pvarDest[0]);
      std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v22);
      goto LABEL_25;
    }
    *(_OWORD *)(v14 + 24) = 0;
    *((_QWORD *)v14 + 5) = 0;
    v16 = PropVariantCopy((PROPVARIANT *)v14 + 3, a3);
    v17 = v16;
    if ( v16 >= 0 )
    {
      while ( *v7 )
        v7 = (_QWORD *)(*v7 + 48LL);
      *((_QWORD *)v15 + 6) = 0;
      *((_DWORD *)v15 + 4) = a2->pid;
      fmtid = a2->fmtid;
      v22 = 0;
      *(GUID *)v15 = fmtid;
      *v7 = v15;
      std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v22);
LABEL_21:
      *((_BYTE *)this + 88) = 1;
      if ( this != (CAudioSessionPropertyStore *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v16,
      (int)pvarDest[0]);
    std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v22);
    if ( this != (CAudioSessionPropertyStore *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return v17;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x8007065ELL,
      (int)pvarDest[0]);
    return 2147944030LL;
  }
}

```

## disassembly

```asm
0x1800264b0  mov     [rsp+arg_8], rbx
0x1800264b5  mov     [rsp+arg_10], rbp
0x1800264ba  push    rsi
0x1800264bb  push    rdi
0x1800264bc  push    r12
0x1800264be  push    r14
0x1800264c0  push    r15
0x1800264c2  sub     rsp, 40h
0x1800264c6  mov     rbp, rdx
0x1800264c9  mov     r12, r8
0x1800264cc  mov     rdx, r8; struct tagPROPVARIANT *
0x1800264cf  mov     r15, rcx
0x1800264d2  call    ?IsValidProperty@CAudioSessionPropertyStore@@AEAA_NPEBUtagPROPVARIANT@@@Z; CAudioSessionPropertyStore::IsValidProperty(tagPROPVARIANT const *)
0x1800264d7  test    al, al
0x1800264d9  jnz     short loc_180026500
0x1800264db  mov     rcx, [rsp+68h]; this
0x1800264e0  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800264e7  mov     ebx, 8007065Eh
0x1800264ec  mov     edx, 1E5h; void *
0x1800264f1  mov     r9d, ebx; char *
0x1800264f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264f9  mov     eax, ebx
0x1800264fb  jmp     loc_1800266AA
0x180026500  lea     rbx, [r15+30h]
0x180026504  mov     rcx, rbx; lpCriticalSection
0x180026507  call    cs:__imp_EnterCriticalSection
0x18002650d  lea     r14, [r15+20h]
0x180026511  mov     rsi, r14
0x180026514  mov     rcx, [rsi]
0x180026517  test    rcx, rcx
0x18002651a  jz      loc_1800265AE
0x180026520  mov     eax, [rbp+10h]
0x180026523  cmp     [rcx+10h], eax
0x180026526  jnz     short loc_18002653E
0x180026528  mov     rax, [rcx]
0x18002652b  sub     rax, [rbp+0]
0x18002652f  jnz     short loc_180026539
0x180026531  mov     rax, [rcx+8]
0x180026535  sub     rax, [rbp+8]
0x180026539  test    rax, rax
0x18002653c  jz      short loc_180026544
0x18002653e  lea     rsi, [rcx+30h]
0x180026542  jmp     short loc_180026514
0x180026544  xorps   xmm0, xmm0
0x180026547  lea     rcx, [rsp+68h+pvarDest]; pvarDest
0x18002654c  xor     eax, eax
0x18002654e  mov     rdx, r12; pvarSrc
0x180026551  movups  xmmword ptr [rsp+68h+pvarDest], xmm0; int
0x180026556  mov     [rsp+68h+var_38], rax
0x18002655b  call    cs:__imp_PropVariantCopy
0x180026561  mov     edi, eax
0x180026563  test    eax, eax
0x180026565  jns     short loc_180026585
0x180026567  mov     rcx, [rsp+68h]; this
0x18002656c  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180026573  mov     r9d, eax; char *
0x180026576  mov     edx, 1F3h; void *
0x18002657b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026580  jmp     loc_18002669A
0x180026585  mov     rcx, [rsi]
0x180026588  add     rcx, 18h; pvar
0x18002658c  call    cs:__imp_PropVariantClear
0x180026592  mov     rax, [rsi]
0x180026595  movups  xmm0, xmmword ptr [rsp+68h+pvarDest]
0x18002659a  movups  xmmword ptr [rax+18h], xmm0
0x18002659e  movsd   xmm1, [rsp+68h+var_38]
0x1800265a4  movsd   qword ptr [rax+28h], xmm1
0x1800265a9  jmp     loc_18002665B
0x1800265ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800265b5  mov     ecx, 38h ; '8'; unsigned __int64
0x1800265ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800265bf  mov     [rsp+68h+arg_0], rax
0x1800265c4  mov     rdi, rax
0x1800265c7  test    rax, rax
0x1800265ca  jz      loc_180026672
0x1800265d0  lea     rcx, [rax+18h]; pvarDest
0x1800265d4  xorps   xmm0, xmm0
0x1800265d7  xor     eax, eax
0x1800265d9  mov     rdx, r12; pvarSrc
0x1800265dc  movups  xmmword ptr [rcx], xmm0
0x1800265df  mov     [rcx+10h], rax
0x1800265e3  call    cs:__imp_PropVariantCopy
0x1800265e9  mov     esi, eax
0x1800265eb  test    eax, eax
0x1800265ed  jns     short loc_18002662B
0x1800265ef  mov     rcx, [rsp+68h]; this
0x1800265f4  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800265fb  mov     r9d, eax; char *
0x1800265fe  mov     edx, 208h; void *
0x180026603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026608  lea     rcx, [rsp+68h+arg_0]
0x18002660d  call    ??1?$unique_ptr@Upropstoreinfo_tag@@U?$default_delete@Upropstoreinfo_tag@@@std@@@std@@QEAA@XZ; std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(void)
0x180026612  test    rbx, rbx
0x180026615  jz      short loc_180026620
0x180026617  mov     rcx, rbx; lpCriticalSection
0x18002661a  call    cs:__imp_LeaveCriticalSection
0x180026620  mov     eax, esi
0x180026622  jmp     loc_1800266AA
0x180026627  lea     r14, [rax+30h]
0x18002662b  mov     rax, [r14]
0x18002662e  test    rax, rax
0x180026631  jnz     short loc_180026627
0x180026633  mov     [rdi+30h], rax
0x180026637  lea     rcx, [rsp+68h+arg_0]
0x18002663c  mov     eax, [rbp+10h]
0x18002663f  mov     [rdi+10h], eax
0x180026642  movups  xmm0, xmmword ptr [rbp+0]
0x180026646  mov     [rsp+68h+arg_0], 0
0x18002664f  movdqu  xmmword ptr [rdi], xmm0
0x180026653  mov     [r14], rdi
0x180026656  call    ??1?$unique_ptr@Upropstoreinfo_tag@@U?$default_delete@Upropstoreinfo_tag@@@std@@@std@@QEAA@XZ; std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(void)
0x18002665b  mov     byte ptr [r15+58h], 1
0x180026660  test    rbx, rbx
0x180026663  jz      short loc_18002666E
0x180026665  mov     rcx, rbx; lpCriticalSection
0x180026668  call    cs:__imp_LeaveCriticalSection
0x18002666e  xor     eax, eax
0x180026670  jmp     short loc_1800266AA
0x180026672  mov     rcx, [rsp+68h]; this
0x180026677  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18002667e  mov     edi, 8007000Eh
0x180026683  mov     edx, 204h; void *
0x180026688  mov     r9d, edi; char *
0x18002668b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026690  lea     rcx, [rsp+68h+arg_0]
0x180026695  call    ??1?$unique_ptr@Upropstoreinfo_tag@@U?$default_delete@Upropstoreinfo_tag@@@std@@@std@@QEAA@XZ; std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(void)
0x18002669a  test    rbx, rbx
0x18002669d  jz      short loc_1800266A8
0x18002669f  mov     rcx, rbx; lpCriticalSection
0x1800266a2  call    cs:__imp_LeaveCriticalSection
0x1800266a8  mov     eax, edi
0x1800266aa  lea     r11, [rsp+68h+var_28]
0x1800266af  mov     rbx, [r11+38h]
0x1800266b3  mov     rbp, [r11+40h]
0x1800266b7  mov     rsp, r11
0x1800266ba  pop     r15
0x1800266bc  pop     r14
0x1800266be  pop     r12
0x1800266c0  pop     rdi
0x1800266c1  pop     rsi
0x1800266c2  retn
```
