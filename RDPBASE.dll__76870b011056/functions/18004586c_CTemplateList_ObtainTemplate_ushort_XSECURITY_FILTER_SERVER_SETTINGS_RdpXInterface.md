# CTemplateList::ObtainTemplate(ushort *,_XSECURITY_FILTER_SERVER_SETTINGS *,RdpXInterface * *)

- ea: `0x18004586c`
- end: `0x180045cd8`
- name: `?ObtainTemplate@CTemplateList@@QEAAJPEAGPEAU_XSECURITY_FILTER_SERVER_SETTINGS@@PEAPEAURdpXInterface@@@Z`
- size: `1132`
- prototype: `int(CTemplateList *__hidden this, unsigned __int16 *, struct _XSECURITY_FILTER_SERVER_SETTINGS *, struct RdpXInterface **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ec1c0`

## callees

- `0x18001cc3c`
- `0x18004298c`
- `0x18004586c`
- `0x180046a84`
- `0x1800711c8`
- `0x1800787d4`
- `0x1800795c4`
- `0x180087e24`
- `0x1800888d8`
- `0x1800923f8`
- `0x180103598`
- `0x18010369c`
- `0x1801614b8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800458a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800458a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800459b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800459b0`

## string_xrefs

- `0x180045b7b`: `CTemplateItem`
- `0x180045a61`: `GetInstanceOfSecFilterServerTemplate failed`
- `0x180045a4e`: `pItem->GetTemplate failed`
- `0x180045afe`: `pItem->Replace failed`
- `0x180045caa`: `"CTemplateItem"`

## pseudocode

```c
__int64 __fastcall CTemplateList::ObtainTemplate(
        CTemplateList *this,
        unsigned __int16 *a2,
        struct _XSECURITY_FILTER_SERVER_SETTINGS *a3,
        struct RdpXInterface **a4)
{
  _QWORD *v4; // r14
  unsigned int v8; // r15d
  _QWORD *i; // rbx
  wchar_t *v10; // rdi
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // ebx
  unsigned int v14; // eax
  int v15; // edx
  struct RdpXInterface *v16; // rcx
  struct RdpXInterface *v18; // rbx
  unsigned int v19; // eax
  const char *v20; // rcx
  unsigned int InstanceOfSecFilterServerTemplate; // eax
  _DWORD *v22; // rax
  _DWORD *v23; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct RdpXInterface *v25; // [rsp+80h] [rbp+40h] BYREF
  _DWORD *v26; // [rsp+90h] [rbp+50h] BYREF

  v4 = 0;
  v26 = 0;
  v25 = 0;
  AcquireSRWLockExclusive(&SRWLock);
  dword_1801F00D0 = 1;
  *a4 = 0;
  v8 = *(_DWORD *)a3;
  for ( i = (_QWORD *)qword_1801F00D8; ; i = (_QWORD *)*i )
  {
    if ( !i )
    {
      InstanceOfSecFilterServerTemplate = GetInstanceOfSecFilterServerTemplate(a3, &v25);
      v13 = MapXResultToHR(InstanceOfSecFilterServerTemplate);
      if ( v13 >= 0 )
      {
        v22 = operator new(0xA0u);
        v23 = v22;
        if ( !v22 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_6b47be7a35413a139bab3fcf5a916819_Traceguids,
              CurrentThreadActivityIdPrefix,
              (__int64)"\"CTemplateItem\"");
          }
          v13 = -2147024882;
          goto LABEL_16;
        }
        v22[6] = -607474739;
        v22[7] = 1;
        *((_QWORD *)v22 + 2) = "CTemplateItem";
        *(_QWORD *)v22 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
        *((_QWORD *)v22 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
        *(_QWORD *)v22 = &SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'};
        *((_QWORD *)v22 + 1) = &CTemplateItem::`vftable'{for `CTSObject'};
        v22[10] = 0;
        *((_QWORD *)v22 + 4) = v22;
        *((_QWORD *)v22 + 19) = 0;
        *((_WORD *)v22 + 28) = 0;
        v22[31] = 0;
        *((_BYTE *)v22 + 128) = 0;
        *((_QWORD *)v22 + 17) = 0;
        v22[36] = 0;
        *((_QWORD *)v22 + 6) = 0;
        TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v26);
        v26 = v23;
        v4 = v23;
        TCntPtr<CRdpUdpConnection>::SafeAddRef(&v26);
        v13 = CTemplateItem::Initialize(
                (CTemplateItem *)v23,
                a2,
                *(_DWORD *)a3,
                *((_BYTE *)a3 + 5),
                *((unsigned __int8 **)a3 + 2),
                *((_DWORD *)a3 + 6),
                v25);
        if ( v13 >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 4) + 8LL))(*((_QWORD *)v23 + 4));
          *((_QWORD *)v23 + 6) = qword_1801F00D8;
          qword_1801F00D8 = (__int64)(v23 + 12);
          goto LABEL_15;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_16;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 18;
        v20 = "pItem->Initialize failed";
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_16;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 16;
LABEL_26:
        v20 = "GetInstanceOfSecFilterServerTemplate failed";
      }
LABEL_27:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)WPP_6b47be7a35413a139bab3fcf5a916819_Traceguids,
        v14,
        (__int64)v20,
        v13);
      goto LABEL_16;
    }
    v10 = (wchar_t *)(i - 6);
    if ( *((_DWORD *)i + 19) == v8 && !wcsicmp(v10 + 28, a2) )
      break;
  }
  v4 = i - 6;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 4) + 8LL))(*((_QWORD *)v10 + 4));
  if ( *((_BYTE *)v10 + 128) == *((_BYTE *)a3 + 5) )
  {
    v11 = *((_DWORD *)a3 + 6);
    if ( *((_DWORD *)v10 + 36) == v11 && !memcmp_0(*((const void **)v10 + 17), *((const void **)a3 + 2), v11) )
    {
      v18 = (struct RdpXInterface *)*((_QWORD *)v10 + 19);
      if ( !v18 )
      {
        v13 = -2147024894;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_6b47be7a35413a139bab3fcf5a916819_Traceguids,
            v19,
            (__int64)"pItem->GetTemplate failed",
            2);
        }
        goto LABEL_16;
      }
      (**(void (__fastcall ***)(_QWORD))v18)(*((_QWORD *)v10 + 19));
      v25 = v18;
      v13 = 0;
      goto LABEL_15;
    }
  }
  v12 = GetInstanceOfSecFilterServerTemplate(a3, &v25);
  v13 = MapXResultToHR(v12);
  if ( v13 >= 0 )
  {
    v13 = CTemplateItem::Replace(
            (CTemplateItem *)v10,
            *((_BYTE *)a3 + 5),
            *((unsigned __int8 **)a3 + 2),
            *((_DWORD *)a3 + 6),
            v25);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 14;
      v20 = "pItem->Replace failed";
      goto LABEL_27;
    }
LABEL_15:
    v16 = v25;
    *a4 = v25;
    (**(void (__fastcall ***)(struct RdpXInterface *))v16)(v16);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 13;
    goto LABEL_26;
  }
LABEL_16:
  dword_1801F00D0 = 0;
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v25 )
    (*(void (__fastcall **)(struct RdpXInterface *))(*(_QWORD *)v25 + 8LL))(v25);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4[4] + 16LL))(v4[4]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004586c  mov     [rsp-38h+arg_8], rbx
0x180045871  mov     [rsp-38h+arg_0], rcx
0x180045876  push    rbp
0x180045877  push    rsi
0x180045878  push    rdi
0x180045879  push    r12
0x18004587b  push    r13
0x18004587d  push    r14
0x18004587f  push    r15
0x180045881  mov     rbp, rsp
0x180045884  sub     rsp, 40h
0x180045888  xor     r14d, r14d
0x18004588b  lea     rcx, SRWLock; SRWLock
0x180045892  mov     [rbp+arg_10], r14
0x180045896  mov     r13, r9
0x180045899  mov     [rbp+arg_0], r14
0x18004589d  mov     rsi, r8
0x1800458a0  mov     r12, rdx
0x1800458a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800458a9  mov     cs:dword_1801F00D0, 1
0x1800458b3  mov     [r13+0], r14
0x1800458b7  mov     r15d, [rsi]
0x1800458ba  mov     rbx, cs:qword_1801F00D8
0x1800458c1  test    rbx, rbx
0x1800458c4  jz      loc_180045B0A
0x1800458ca  lea     rdi, [rbx-30h]
0x1800458ce  cmp     [rdi+7Ch], r15d
0x1800458d2  jz      short loc_1800458D9
0x1800458d4  mov     rbx, [rbx]
0x1800458d7  jmp     short loc_1800458C1
0x1800458d9  lea     rcx, [rdi+38h]; String1
0x1800458dd  mov     rdx, r12; String2
0x1800458e0  call    _wcsicmp
0x1800458e5  test    eax, eax
0x1800458e7  jnz     short loc_1800458D4
0x1800458e9  mov     rcx, [rdi+20h]
0x1800458ed  mov     r14, rdi
0x1800458f0  mov     rax, [rcx]
0x1800458f3  mov     rax, [rax+8]
0x1800458f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458fc  mov     al, [rsi+5]
0x1800458ff  cmp     [rdi+80h], al
0x180045905  jnz     short loc_18004592D
0x180045907  mov     eax, [rsi+18h]
0x18004590a  cmp     [rdi+90h], eax
0x180045910  jnz     short loc_18004592D
0x180045912  mov     rdx, [rsi+10h]; Buf2
0x180045916  mov     r8d, eax; Size
0x180045919  mov     rcx, [rdi+88h]; Buf1
0x180045920  call    memcmp_0
0x180045925  test    eax, eax
0x180045927  jz      loc_1800459FA
0x18004592d  lea     rdx, [rbp+arg_0]
0x180045931  mov     rcx, rsi
0x180045934  call    ?GetInstanceOfSecFilterServerTemplate@@YA?AW4_XResult32@@PEAU_XSECURITY_FILTER_SERVER_SETTINGS@@PEAPEAURdpXInterface@@@Z; GetInstanceOfSecFilterServerTemplate(_XSECURITY_FILTER_SERVER_SETTINGS *,RdpXInterface * *)
0x180045939  mov     ecx, eax
0x18004593b  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x180045940  mov     ebx, eax
0x180045942  test    eax, eax
0x180045944  jns     loc_180045AA3
0x18004594a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045951  lea     rax, WPP_GLOBAL_Control
0x180045958  cmp     rcx, rax
0x18004595b  jz      short loc_18004599F
0x18004595d  test    byte ptr [rcx+1Ch], 8
0x180045961  jz      short loc_18004599F
0x180045963  cmp     byte ptr [rcx+19h], 2
0x180045967  jb      short loc_18004599F
0x180045969  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004596e  mov     edx, 0Dh
0x180045973  jmp     loc_180045A61
0x180045978  mov     rax, [rbx]
0x18004597b  mov     rcx, rbx
0x18004597e  mov     rax, [rax]
0x180045981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045986  mov     [rbp+arg_0], rbx
0x18004598a  xor     ebx, ebx
0x18004598c  mov     rcx, [rbp+arg_0]
0x180045990  mov     [r13+0], rcx
0x180045994  mov     rax, [rcx]
0x180045997  mov     rax, [rax]
0x18004599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004599f  lea     rcx, SRWLock; SRWLock
0x1800459a6  mov     cs:dword_1801F00D0, 0
0x1800459b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800459b6  mov     rcx, [rbp+arg_0]
0x1800459ba  test    rcx, rcx
0x1800459bd  jz      short loc_1800459CB
0x1800459bf  mov     rax, [rcx]
0x1800459c2  mov     rax, [rax+8]
0x1800459c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459cb  test    r14, r14
0x1800459ce  jz      short loc_1800459E0
0x1800459d0  mov     rcx, [r14+20h]
0x1800459d4  mov     rax, [rcx]
0x1800459d7  mov     rax, [rax+10h]
0x1800459db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459e0  mov     eax, ebx
0x1800459e2  mov     rbx, [rsp+40h+arg_8]
0x1800459ea  add     rsp, 40h
0x1800459ee  pop     r15
0x1800459f0  pop     r14
0x1800459f2  pop     r13
0x1800459f4  pop     r12
0x1800459f6  pop     rdi
0x1800459f7  pop     rsi
0x1800459f8  pop     rbp
0x1800459f9  retn
0x1800459fa  mov     rbx, [rdi+98h]
0x180045a01  test    rbx, rbx
0x180045a04  jnz     loc_180045978
0x180045a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a11  lea     rax, WPP_GLOBAL_Control
0x180045a18  mov     edi, 80070002h
0x180045a1d  mov     ebx, edi
0x180045a1f  cmp     rcx, rax
0x180045a22  jz      loc_18004599F
0x180045a28  test    byte ptr [rcx+1Ch], 8
0x180045a2c  jz      loc_18004599F
0x180045a32  cmp     byte ptr [rcx+19h], 2
0x180045a36  jb      loc_18004599F
0x180045a3c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045a41  mov     edx, 0Fh
0x180045a46  mov     [rsp+40h+var_18], 80070002h
0x180045a4e  lea     rcx, aPitemGettempla; "pItem->GetTemplate failed"
0x180045a55  jmp     short loc_180045A7F
0x180045a57  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045a5c  mov     edx, 10h
0x180045a61  lea     rcx, aGetinstanceofs; "GetInstanceOfSecFilterServerTemplate fa"...
0x180045a68  jmp     short loc_180045A7B
0x180045a6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045a6f  mov     edx, 12h
0x180045a74  lea     rcx, aPitemInitializ; "pItem->Initialize failed"
0x180045a7b  mov     [rsp+40h+var_18], ebx
0x180045a7f  mov     [rsp+40h+var_20], rcx
0x180045a84  lea     r8, WPP_6b47be7a35413a139bab3fcf5a916819_Traceguids
0x180045a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a92  mov     r9d, eax
0x180045a95  mov     rcx, [rcx+10h]
0x180045a99  call    WPP_SF_DsD
0x180045a9e  jmp     loc_18004599F
0x180045aa3  mov     rax, [rbp+arg_0]
0x180045aa7  mov     rcx, rdi; this
0x180045aaa  mov     r9d, [rsi+18h]; unsigned int
0x180045aae  mov     r8, [rsi+10h]; unsigned __int8 *
0x180045ab2  mov     dl, [rsi+5]; unsigned __int8
0x180045ab5  mov     [rsp+40h+var_20], rax; struct RdpXInterface *
0x180045aba  call    ?Replace@CTemplateItem@@QEAAJEPEAEKPEAURdpXInterface@@@Z; CTemplateItem::Replace(uchar,uchar *,ulong,RdpXInterface *)
0x180045abf  mov     ebx, eax
0x180045ac1  test    eax, eax
0x180045ac3  jns     loc_18004598C
0x180045ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ad0  lea     rax, WPP_GLOBAL_Control
0x180045ad7  cmp     rcx, rax
0x180045ada  jz      loc_18004599F
0x180045ae0  test    byte ptr [rcx+1Ch], 8
0x180045ae4  jz      loc_18004599F
0x180045aea  cmp     byte ptr [rcx+19h], 2
0x180045aee  jb      loc_18004599F
0x180045af4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045af9  mov     edx, 0Eh
0x180045afe  lea     rcx, aPitemReplaceFa; "pItem->Replace failed"
0x180045b05  jmp     loc_180045A7B
0x180045b0a  lea     rdx, [rbp+arg_0]
0x180045b0e  mov     rcx, rsi
0x180045b11  call    ?GetInstanceOfSecFilterServerTemplate@@YA?AW4_XResult32@@PEAU_XSECURITY_FILTER_SERVER_SETTINGS@@PEAPEAURdpXInterface@@@Z; GetInstanceOfSecFilterServerTemplate(_XSECURITY_FILTER_SERVER_SETTINGS *,RdpXInterface * *)
0x180045b16  mov     ecx, eax
0x180045b18  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x180045b1d  mov     ebx, eax
0x180045b1f  test    eax, eax
0x180045b21  jns     short loc_180045B53
0x180045b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b2a  lea     rax, WPP_GLOBAL_Control
0x180045b31  cmp     rcx, rax
0x180045b34  jz      loc_18004599F
0x180045b3a  test    byte ptr [rcx+1Ch], 8
0x180045b3e  jz      loc_18004599F
0x180045b44  cmp     byte ptr [rcx+19h], 2
0x180045b48  jb      loc_18004599F
0x180045b4e  jmp     loc_180045A57
0x180045b53  mov     ecx, 0A0h; Size
0x180045b58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045b5d  mov     rdi, rax
0x180045b60  test    rax, rax
0x180045b63  jz      loc_180045C7F
0x180045b69  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180045b70  lea     rcx, [rbp+arg_10]
0x180045b74  mov     dword ptr [rdi+1Ch], 1
0x180045b7b  lea     rax, aCtemplateitem_0; "CTemplateItem"
0x180045b82  mov     [rdi+10h], rax
0x180045b86  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180045b8d  mov     [rdi], rax
0x180045b90  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180045b97  mov     [rdi+8], rax
0x180045b9b  lea     rax, ??_7?$SlidingStats@N$04$00@@6BINonDelegatingUnknown@@@; const SlidingStats<double,5,1>::`vftable'{for `INonDelegatingUnknown'}
0x180045ba2  mov     [rdi], rax
0x180045ba5  lea     rax, ??_7CTemplateItem@@6BCTSObject@@@; const CTemplateItem::`vftable'{for `CTSObject'}
0x180045bac  mov     [rdi+8], rax
0x180045bb0  xor     eax, eax
0x180045bb2  mov     [rdi+28h], r14d
0x180045bb6  mov     [rdi+20h], rdi
0x180045bba  mov     [rdi+98h], r14
0x180045bc1  mov     [rdi+38h], ax
0x180045bc5  mov     [rdi+7Ch], eax
0x180045bc8  mov     [rdi+80h], al
0x180045bce  mov     [rdi+88h], rax
0x180045bd5  mov     [rdi+90h], eax
0x180045bdb  mov     [rdi+30h], rax
0x180045bdf  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x180045be4  lea     rcx, [rbp+arg_10]
0x180045be8  mov     [rbp+arg_10], rdi
0x180045bec  mov     r14, rdi
0x180045bef  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x180045bf4  mov     rax, [rbp+arg_0]
0x180045bf8  mov     rdx, r12; unsigned __int16 *
0x180045bfb  mov     r9b, [rsi+5]; unsigned __int8
0x180045bff  mov     rcx, rdi; this
0x180045c02  mov     r8d, [rsi]; unsigned int
0x180045c05  mov     [rsp+40h+var_10], rax; struct RdpXInterface *
0x180045c0a  mov     eax, [rsi+18h]
0x180045c0d  mov     [rsp+40h+var_18], eax; unsigned int
0x180045c11  mov     rax, [rsi+10h]
0x180045c15  mov     [rsp+40h+var_20], rax; unsigned __int8 *
0x180045c1a  call    ?Initialize@CTemplateItem@@QEAAJPEAGIEPEAEKPEAURdpXInterface@@@Z; CTemplateItem::Initialize(ushort *,uint,uchar,uchar *,ulong,RdpXInterface *)
0x180045c1f  mov     ebx, eax
0x180045c21  test    eax, eax
0x180045c23  jns     short loc_180045C55
0x180045c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c2c  lea     rax, WPP_GLOBAL_Control
0x180045c33  cmp     rcx, rax
0x180045c36  jz      loc_18004599F
0x180045c3c  test    byte ptr [rcx+1Ch], 8
0x180045c40  jz      loc_18004599F
0x180045c46  cmp     byte ptr [rcx+19h], 2
0x180045c4a  jb      loc_18004599F
0x180045c50  jmp     loc_180045A6A
0x180045c55  mov     rcx, [rdi+20h]
0x180045c59  mov     rax, [rcx]
0x180045c5c  mov     rax, [rax+8]
0x180045c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c65  mov     rax, cs:qword_1801F00D8
0x180045c6c  lea     rcx, [rdi+30h]
0x180045c70  mov     [rcx], rax
0x180045c73  mov     cs:qword_1801F00D8, rcx
0x180045c7a  jmp     loc_18004598C
0x180045c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c86  lea     rax, WPP_GLOBAL_Control
0x180045c8d  cmp     rcx, rax
0x180045c90  jz      short loc_180045CCE
0x180045c92  test    byte ptr [rcx+1Ch], 8
0x180045c96  jz      short loc_180045CCE
0x180045c98  cmp     byte ptr [rcx+19h], 2
0x180045c9c  jb      short loc_180045CCE
0x180045c9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045caa  lea     r8, aCtemplateitem; "\"CTemplateItem\""
0x180045cb1  mov     [rsp+40h+var_20], r8
0x180045cb6  mov     edx, 11h
0x180045cbb  mov     r9d, eax
0x180045cbe  lea     r8, WPP_6b47be7a35413a139bab3fcf5a916819_Traceguids
0x180045cc5  mov     rcx, [rcx+10h]
0x180045cc9  call    WPP_SF_Ds
0x180045cce  mov     ebx, 8007000Eh
0x180045cd3  jmp     loc_18004599F
```
