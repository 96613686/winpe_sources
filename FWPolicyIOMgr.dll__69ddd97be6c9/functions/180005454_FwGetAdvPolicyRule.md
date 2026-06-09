# FwGetAdvPolicyRule

- ea: `0x180005454`
- end: `0x180005758`
- name: `FwGetAdvPolicyRule`
- size: `772`
- prototype: `__int64 __usercall@<rax>(struct _tag_FW_RULE_MANIPULATOR *@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180005360`
- `0x18001d320`
- `0x18001d580`

## callees

- `0x180003bc0`
- `0x1800042c4`
- `0x180005454`
- `0x180019a70`
- `0x18001ae18`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `fwbase!FwFree` at `0x180005701`
- `fwbase!FwFree` at `0x180005713`
- `fwbase!FwFree` at `0x180005724`
- `fwbase!FwFree` at `0x180005701`
- `fwbase!FwFree` at `0x180005713`
- `fwbase!FwFree` at `0x180005724`
- `fwbase!FwStringCopy` at `0x18000559c`
- `fwbase!FwStringCopy` at `0x18000559c`
- `fwbase!FwNtStatusToHResult` at `0x180005661`
- `fwbase!FwNtStatusToHResult` at `0x180005661`
- `fwbase!FwRegOpenKey` at `0x1800054c8`
- `fwbase!FwRegOpenKey` at `0x1800054c8`
- `fwbase!FwRegQueryString` at `0x18000552c`
- `fwbase!FwRegQueryString` at `0x18000552c`
- `fwbase!FwRegCloseKey` at `0x180005733`
- `fwbase!FwRegCloseKey` at `0x180005733`

## pseudocode

```c
__int64 __fastcall FwGetAdvPolicyRule(
        struct _tag_FW_RULE_MANIPULATOR *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct _tag_FW_BLOB_RULE **a5)
{
  int *v5; // rdi
  struct _tag_FW_BLOB_RULE *v9; // rsi
  __int64 v10; // rcx
  int v11; // ebx
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  struct _tag_FW_BLOB_RULE *v15; // rax
  HKEY v16; // rdx
  int inited; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-30h] BYREF
  __int64 v25; // [rsp+50h] [rbp-28h] BYREF
  int v26; // [rsp+58h] [rbp-20h] BYREF

  v5 = &dword_18004C8D0;
  v25 = 0;
  v26 = 0;
  if ( !dword_18004C8D0 )
    v5 = 0;
  v23 = 0;
  v24 = 0;
  v9 = 0;
  v10 = a2;
  if ( a3 )
  {
    v11 = FwRegOpenKey(a2, a3, 1, &v25, &v26);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 19;
LABEL_8:
        v14 = (unsigned int)v11;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v14);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    v10 = v25;
  }
  else
  {
    v25 = a2;
  }
  v11 = FwRegQueryString(v10, 0, a4, &v24, &v26);
  if ( v11 >= 0 )
  {
    if ( !v26 )
    {
      v11 = -2147024894;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 21;
        goto LABEL_8;
      }
      goto LABEL_45;
    }
    v11 = FwStringCopy(a4, &v23);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 22;
        goto LABEL_8;
      }
      goto LABEL_45;
    }
    v15 = (struct _tag_FW_BLOB_RULE *)(*(__int64 (**)(void))a1)();
    v9 = v15;
    if ( !v15 )
    {
      v11 = -2147024882;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 23;
        goto LABEL_8;
      }
      goto LABEL_45;
    }
    inited = FwAdvPolicyInitRule(a1, v16, v23, v24, v15);
    v23 = 0;
    v11 = inited;
    if ( inited == -2147467263
      || inited == -2147418113
      || inited == -2147024809
      || inited == -2147024883
      || inited == (unsigned int)FwNtStatusToHResult(3221225485LL) )
    {
      v11 = 0;
    }
    else
    {
      if ( v11 < 0 && v5 )
      {
        if ( (unsigned int)*v5 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x800000000000LL) )
        {
          v22 = (__int64)v24;
          v21 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            (int)v5,
            (int)&word_18004192E,
            v18,
            v19,
            (__int64 **)&v22,
            (__int64)&v21);
        }
        v14 = (unsigned int)v11;
LABEL_40:
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 24;
          goto LABEL_9;
        }
        goto LABEL_45;
      }
      v14 = (unsigned int)v11;
      if ( v11 < 0 )
        goto LABEL_40;
    }
    *a5 = v9;
    v9 = 0;
    goto LABEL_45;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v13 = 20;
    goto LABEL_8;
  }
LABEL_45:
  FwFree(v23);
  v23 = 0;
  FwFree(v24);
  v24 = 0;
  FwFree(v9);
  if ( v25 != a2 )
    FwRegCloseKey(v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005454  push    rbp
0x180005456  push    rbx
0x180005457  push    rsi
0x180005458  push    rdi
0x180005459  push    r12
0x18000545b  push    r13
0x18000545d  push    r14
0x18000545f  push    r15
0x180005461  mov     rbp, rsp
0x180005464  sub     rsp, 78h
0x180005468  mov     rax, cs:__security_cookie
0x18000546f  xor     rax, rsp
0x180005472  mov     [rbp+var_18], rax
0x180005476  mov     r12, [rbp+arg_20]
0x18000547a  lea     rdi, dword_18004C8D0
0x180005481  mov     r13, rdx
0x180005484  mov     r14, rcx
0x180005487  mov     ecx, cs:dword_18004C8D0
0x18000548d  xor     edx, edx
0x18000548f  test    ecx, ecx
0x180005491  mov     [rbp+var_28], rdx
0x180005495  mov     r15, r9
0x180005498  mov     [rbp+var_20], edx
0x18000549b  cmovz   rdi, rdx
0x18000549f  mov     [rbp+var_38], rdx
0x1800054a3  mov     [rbp+var_30], rdx
0x1800054a7  mov     r10, r8
0x1800054aa  mov     esi, edx
0x1800054ac  mov     rcx, r13
0x1800054af  test    r8, r8
0x1800054b2  jz      short loc_180005516
0x1800054b4  lea     rax, [rbp+var_20]
0x1800054b8  lea     r8d, [rdx+1]
0x1800054bc  mov     [rsp+78h+var_58], rax
0x1800054c1  mov     rdx, r10
0x1800054c4  lea     r9, [rbp+var_28]
0x1800054c8  call    cs:__imp_FwRegOpenKey
0x1800054ce  mov     ebx, eax
0x1800054d0  test    eax, eax
0x1800054d2  jns     short loc_180005510
0x1800054d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054db  lea     rax, WPP_GLOBAL_Control
0x1800054e2  cmp     rcx, rax
0x1800054e5  jz      loc_1800056FD
0x1800054eb  test    byte ptr [rcx+1Ch], 1
0x1800054ef  jz      loc_1800056FD
0x1800054f5  lea     edx, [rsi+13h]
0x1800054f8  mov     r9d, ebx
0x1800054fb  mov     rcx, [rcx+10h]
0x1800054ff  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x180005506  call    WPP_SF_d
0x18000550b  jmp     loc_1800056FD
0x180005510  mov     rcx, [rbp+var_28]
0x180005514  jmp     short loc_18000551A
0x180005516  mov     [rbp+var_28], rcx
0x18000551a  lea     rax, [rbp+var_20]
0x18000551e  mov     r8, r15
0x180005521  lea     r9, [rbp+var_30]
0x180005525  mov     [rsp+78h+var_58], rax
0x18000552a  xor     edx, edx
0x18000552c  call    cs:__imp_FwRegQueryString
0x180005532  mov     ebx, eax
0x180005534  test    eax, eax
0x180005536  jns     short loc_180005560
0x180005538  mov     rcx, cs:WPP_GLOBAL_Control
0x18000553f  lea     rax, WPP_GLOBAL_Control
0x180005546  cmp     rcx, rax
0x180005549  jz      loc_1800056FD
0x18000554f  test    byte ptr [rcx+1Ch], 1
0x180005553  jz      loc_1800056FD
0x180005559  mov     edx, 14h
0x18000555e  jmp     short loc_1800054F8
0x180005560  cmp     [rbp+var_20], esi
0x180005563  jnz     short loc_180005595
0x180005565  mov     ebx, 80070002h
0x18000556a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005571  lea     rax, WPP_GLOBAL_Control
0x180005578  cmp     rcx, rax
0x18000557b  jz      loc_1800056FD
0x180005581  test    byte ptr [rcx+1Ch], 1
0x180005585  jz      loc_1800056FD
0x18000558b  mov     edx, 15h
0x180005590  jmp     loc_1800054F8
0x180005595  lea     rdx, [rbp+var_38]
0x180005599  mov     rcx, r15
0x18000559c  call    cs:__imp_FwStringCopy
0x1800055a2  mov     ebx, eax
0x1800055a4  test    eax, eax
0x1800055a6  jns     short loc_1800055D3
0x1800055a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055af  lea     rax, WPP_GLOBAL_Control
0x1800055b6  cmp     rcx, rax
0x1800055b9  jz      loc_1800056FD
0x1800055bf  test    byte ptr [rcx+1Ch], 1
0x1800055c3  jz      loc_1800056FD
0x1800055c9  mov     edx, 16h
0x1800055ce  jmp     loc_1800054F8
0x1800055d3  mov     rax, [r14]
0x1800055d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055db  mov     rsi, rax
0x1800055de  test    rax, rax
0x1800055e1  jnz     short loc_180005611
0x1800055e3  mov     ebx, 8007000Eh
0x1800055e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055ef  lea     rax, WPP_GLOBAL_Control
0x1800055f6  cmp     rcx, rax
0x1800055f9  jz      loc_1800056FD
0x1800055ff  test    byte ptr [rcx+1Ch], 1
0x180005603  jz      loc_1800056FD
0x180005609  lea     edx, [rsi+17h]
0x18000560c  jmp     loc_1800054F8
0x180005611  mov     r9, [rbp+var_30]; unsigned __int16 *
0x180005615  mov     rcx, r14; struct _tag_FW_RULE_MANIPULATOR *
0x180005618  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18000561c  mov     [rsp+78h+var_58], rsi; struct _tag_FW_BLOB_RULE *
0x180005621  call    ?FwAdvPolicyInitRule@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAUHKEY__@@PEBG2PEAU_tag_FW_BLOB_RULE@@@Z; FwAdvPolicyInitRule(_tag_FW_RULE_MANIPULATOR *,HKEY__ *,ushort const *,ushort const *,_tag_FW_BLOB_RULE *)
0x180005626  mov     [rbp+var_38], 0
0x18000562e  mov     ebx, eax
0x180005630  cmp     eax, 80004001h
0x180005635  jz      loc_1800056F5
0x18000563b  cmp     eax, 8000FFFFh
0x180005640  jz      loc_1800056F5
0x180005646  cmp     eax, 80070057h
0x18000564b  jz      loc_1800056F5
0x180005651  cmp     eax, 8007000Dh
0x180005656  jz      loc_1800056F5
0x18000565c  mov     ecx, 0C000000Dh
0x180005661  call    cs:__imp_FwNtStatusToHResult
0x180005667  cmp     ebx, eax
0x180005669  jz      loc_1800056F5
0x18000566f  test    ebx, ebx
0x180005671  jns     short loc_1800056CB
0x180005673  test    rdi, rdi
0x180005676  jz      short loc_1800056CB
0x180005678  mov     eax, [rdi]
0x18000567a  cmp     eax, 5
0x18000567d  jbe     short loc_1800056C6
0x18000567f  mov     rdx, 800000000000h
0x180005689  mov     rcx, rdi
0x18000568c  call    _tlgKeywordOn
0x180005691  test    al, al
0x180005693  jz      short loc_1800056C6
0x180005695  mov     rax, [rbp+var_30]
0x180005699  lea     rdx, word_18004192E
0x1800056a0  mov     [rbp+var_40], rax
0x1800056a4  mov     rcx, rdi; int
0x1800056a7  lea     rax, [rbp+var_48]
0x1800056ab  mov     [rbp+var_48], 2000000h
0x1800056b3  mov     [rsp+78h+var_50], rax; __int64
0x1800056b8  lea     rax, [rbp+var_40]
0x1800056bc  mov     [rsp+78h+var_58], rax; __int64
0x1800056c1  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800056c6  mov     r9d, ebx
0x1800056c9  jmp     short loc_1800056D2
0x1800056cb  mov     r9d, ebx
0x1800056ce  test    ebx, ebx
0x1800056d0  jns     short loc_1800056F7
0x1800056d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056d9  lea     rax, WPP_GLOBAL_Control
0x1800056e0  cmp     rcx, rax
0x1800056e3  jz      short loc_1800056FD
0x1800056e5  test    byte ptr [rcx+1Ch], 1
0x1800056e9  jz      short loc_1800056FD
0x1800056eb  mov     edx, 18h
0x1800056f0  jmp     loc_1800054FB
0x1800056f5  xor     ebx, ebx
0x1800056f7  mov     [r12], rsi
0x1800056fb  xor     esi, esi
0x1800056fd  mov     rcx, [rbp+var_38]
0x180005701  call    cs:__imp_FwFree
0x180005707  mov     rcx, [rbp+var_30]
0x18000570b  mov     [rbp+var_38], 0
0x180005713  call    cs:__imp_FwFree
0x180005719  mov     rcx, rsi
0x18000571c  mov     [rbp+var_30], 0
0x180005724  call    cs:__imp_FwFree
0x18000572a  mov     rcx, [rbp+var_28]
0x18000572e  cmp     rcx, r13
0x180005731  jz      short loc_180005739
0x180005733  call    cs:__imp_FwRegCloseKey
0x180005739  mov     eax, ebx
0x18000573b  mov     rcx, [rbp+var_18]
0x18000573f  xor     rcx, rsp; StackCookie
0x180005742  call    __security_check_cookie
0x180005747  add     rsp, 78h
0x18000574b  pop     r15
0x18000574d  pop     r14
0x18000574f  pop     r13
0x180005751  pop     r12
0x180005753  pop     rdi
0x180005754  pop     rsi
0x180005755  pop     rbx
0x180005756  pop     rbp
0x180005757  retn
```
