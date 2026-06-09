# CWwanSmsDevice::OnNewSimMessageStatus(ulong,_WWAN_SMS_FLAG)

- ea: `0x18004b818`
- end: `0x18004ba17`
- name: `?OnNewSimMessageStatus@CWwanSmsDevice@@AEAAXKW4_WWAN_SMS_FLAG@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004aee0`
- `0x18004c474`
- `0x18004c570`

## callees

- `0x180003a60`
- `0x180032f88`
- `0x180048fe8`
- `0x18004b818`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `wwapi!WwanSmsRead` at `0x18004b90f`
- `wwapi!WwanSmsRead` at `0x18004b90f`

## string_xrefs

- `0x18004b9cb`: `Read pending for messageIndex: %d`
- `0x18004b99a`: `Failed to read SIM message at messageIndex %d, SmsFormat: %d and readFlag: %d`
- `0x18004b961`: `WwanSmsRead called for messageIndex: %d, SmsFormat: %d and readFlag: %d has requestId: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanSmsDevice::OnNewSimMessageStatus(__int64 a1, unsigned int a2, int a3)
{
  __int64 v6; // rsi
  __int64 *v7; // r8
  __int64 *v8; // rcx
  __int64 *v9; // rdx
  char v10; // r9
  __int64 *v11; // rax
  signed int v12; // eax
  unsigned int v14; // [rsp+40h] [rbp-19h] BYREF
  int v15; // [rsp+48h] [rbp-11h] BYREF
  void **v16; // [rsp+50h] [rbp-9h]
  __int64 v17; // [rsp+58h] [rbp-1h]
  _BYTE v18[12]; // [rsp+60h] [rbp+7h] BYREF
  int v19; // [rsp+6Ch] [rbp+13h]
  __int64 v20; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned int v21; // [rsp+80h] [rbp+27h]

  v15 = a2;
  v16 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v6 = a1 + 32;
  v17 = a1 + 32;
  (**(void (__fastcall ***)(__int64))(a1 + 32))(a1 + 32);
  v20 = 0;
  v21 = 0;
  v14 = 0;
  if ( !*(_DWORD *)(a1 + 24) )
    goto LABEL_19;
  if ( a3 != 1 )
    goto LABEL_13;
  v7 = *(__int64 **)(a1 + 472);
  v8 = (__int64 *)v7[1];
  v19 = 0;
  v9 = v7;
  if ( !*((_BYTE *)v8 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v8 + 7) >= a2 )
      {
        v10 = 0;
        v9 = v8;
      }
      else
      {
        v10 = 1;
      }
      v11 = v8 + 2;
      if ( !v10 )
        v11 = v8;
      v8 = (__int64 *)*v11;
    }
    while ( !*(_BYTE *)(*v11 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || a2 < *((_DWORD *)v9 + 7) || v9 == v7 )
  {
LABEL_13:
    LODWORD(v20) = *(_DWORD *)(a1 + 168);
    HIDWORD(v20) = a3;
    v21 = a2;
    v12 = WwanSmsRead(*(_QWORD *)(a1 + 144), a1 + 152, &v20, &v14, 0, 0);
    if ( v12 )
    {
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      LogSmsRouterError(
        "CWwanSmsDevice::OnNewSimMessageStatus",
        0x56Bu,
        v12,
        "Failed to read SIM message at messageIndex %d, SmsFormat: %d and readFlag: %d",
        a2,
        *(_DWORD *)(a1 + 168),
        a3);
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long const &,>(
                               a1 + 384,
                               (__int64)v18,
                               &v14)
                + 20LL) = a2;
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
        a1 + 472,
        v18,
        &v15);
      LogSmsRouterInfo(
        "CWwanSmsDevice::OnNewSimMessageStatus",
        0x560u,
        "WwanSmsRead called for messageIndex: %d, SmsFormat: %d and readFlag: %d has requestId: %d",
        v15,
        *(_DWORD *)(a1 + 168),
        a3,
        v14);
    }
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
LABEL_19:
    LogSmsRouterInfo("CWwanSmsDevice::OnNewSimMessageStatus", 0x54Fu, "Read pending for messageIndex: %d", a2);
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
}

```

## disassembly

```asm
0x18004b818  mov     [rsp-8+arg_18], rbx
0x18004b81d  push    rbp
0x18004b81e  push    rsi
0x18004b81f  push    rdi
0x18004b820  push    r14
0x18004b822  push    r15
0x18004b824  lea     rbp, [rsp-37h]
0x18004b829  sub     rsp, 90h
0x18004b830  mov     rax, cs:__security_cookie
0x18004b837  xor     rax, rsp
0x18004b83a  mov     [rbp+57h+var_28], rax
0x18004b83e  mov     r15d, r8d
0x18004b841  mov     edi, edx
0x18004b843  mov     rbx, rcx
0x18004b846  mov     [rbp+57h+var_68], edx
0x18004b849  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004b850  mov     [rbp+57h+var_60], rax
0x18004b854  lea     rsi, [rcx+20h]
0x18004b858  mov     [rbp+57h+var_58], rsi
0x18004b85c  mov     rax, [rsi]
0x18004b85f  mov     rcx, rsi
0x18004b862  mov     rax, [rax]
0x18004b865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b86a  nop
0x18004b86b  xor     eax, eax
0x18004b86d  mov     [rbp+57h+var_38], rax
0x18004b871  mov     [rbp+57h+var_30], eax
0x18004b874  mov     [rbp+57h+var_70], eax
0x18004b877  cmp     [rbx+18h], eax
0x18004b87a  jz      loc_18004B9C8
0x18004b880  cmp     r15d, 1
0x18004b884  jnz     short loc_18004B8D4
0x18004b886  mov     r8, [rbx+1D8h]
0x18004b88d  mov     rcx, [r8+8]
0x18004b891  mov     [rbp+57h+var_44], eax
0x18004b894  mov     rdx, r8
0x18004b897  cmp     [rcx+19h], al
0x18004b89a  jnz     short loc_18004B8C0
0x18004b89c  cmp     [rcx+1Ch], edi
0x18004b89f  jnb     short loc_18004B8A6
0x18004b8a1  mov     r9b, 1
0x18004b8a4  jmp     short loc_18004B8AC
0x18004b8a6  xor     r9b, r9b
0x18004b8a9  mov     rdx, rcx
0x18004b8ac  lea     rax, [rcx+10h]
0x18004b8b0  test    r9b, r9b
0x18004b8b3  cmovz   rax, rcx
0x18004b8b7  mov     rcx, [rax]
0x18004b8ba  cmp     byte ptr [rcx+19h], 0
0x18004b8be  jz      short loc_18004B89C
0x18004b8c0  cmp     byte ptr [rdx+19h], 0
0x18004b8c4  jnz     short loc_18004B8D4
0x18004b8c6  cmp     edi, [rdx+1Ch]
0x18004b8c9  jb      short loc_18004B8D4
0x18004b8cb  cmp     rdx, r8
0x18004b8ce  jnz     loc_18004B9C8
0x18004b8d4  mov     r14, rbx
0x18004b8d7  mov     eax, [rbx+0A8h]
0x18004b8dd  mov     dword ptr [rbp+57h+var_38], eax
0x18004b8e0  mov     dword ptr [rbp+57h+var_38+4], r15d
0x18004b8e4  mov     [rbp+57h+var_30], edi
0x18004b8e7  lea     rdx, [rbx+98h]
0x18004b8ee  mov     [rsp+0B0h+var_88], 0
0x18004b8f7  mov     [rsp+0B0h+var_90], 0
0x18004b900  lea     r9, [rbp+57h+var_70]
0x18004b904  lea     r8, [rbp+57h+var_38]
0x18004b908  mov     rcx, [rbx+90h]
0x18004b90f  call    cs:__imp_WwanSmsRead
0x18004b915  test    eax, eax
0x18004b917  jnz     short loc_18004B97B
0x18004b919  lea     rcx, [rbx+180h]
0x18004b920  lea     r8, [rbp+57h+var_70]
0x18004b924  lea     rdx, [rbp+57h+var_50]
0x18004b928  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKK@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004b92d  mov     rcx, [rax]
0x18004b930  mov     [rcx+14h], edi
0x18004b933  lea     rcx, [rbx+1D8h]
0x18004b93a  lea     r8, [rbp+57h+var_68]
0x18004b93e  lea     rdx, [rbp+57h+var_50]
0x18004b942  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong const &)
0x18004b947  mov     eax, [rbp+57h+var_70]
0x18004b94a  mov     [rsp+0B0h+var_80], eax
0x18004b94e  mov     dword ptr [rsp+0B0h+var_88], r15d
0x18004b953  mov     eax, [rbx+0A8h]
0x18004b959  mov     dword ptr [rsp+0B0h+var_90], eax
0x18004b95d  mov     r9d, [rbp+57h+var_68]
0x18004b961  lea     r8, aWwansmsreadCal; "WwanSmsRead called for messageIndex: %d"...
0x18004b968  mov     edx, 560h; unsigned int
0x18004b96d  lea     rcx, aCwwansmsdevice_0; "CWwanSmsDevice::OnNewSimMessageStatus"
0x18004b974  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b979  jmp     short loc_18004B9B6
0x18004b97b  mov     ecx, [rbx+0A8h]
0x18004b981  test    eax, eax
0x18004b983  jle     short loc_18004B98D
0x18004b985  movzx   eax, ax
0x18004b988  or      eax, 80070000h
0x18004b98d  mov     [rsp+0B0h+var_80], r15d
0x18004b992  mov     dword ptr [rsp+0B0h+var_88], ecx
0x18004b996  mov     dword ptr [rsp+0B0h+var_90], edi
0x18004b99a  lea     r9, aFailedToReadSi_0; "Failed to read SIM message at messageIn"...
0x18004b9a1  mov     r8d, eax; int
0x18004b9a4  mov     edx, 56Bh; unsigned int
0x18004b9a9  lea     rcx, aCwwansmsdevice_0; "CWwanSmsDevice::OnNewSimMessageStatus"
0x18004b9b0  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004b9b5  nop
0x18004b9b6  mov     rax, [rsi]
0x18004b9b9  mov     rcx, rsi
0x18004b9bc  mov     rax, [rax+8]
0x18004b9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9c5  nop
0x18004b9c6  jmp     short loc_18004B9F4
0x18004b9c8  mov     r9d, edi
0x18004b9cb  lea     r8, aReadPendingFor; "Read pending for messageIndex: %d"
0x18004b9d2  mov     edx, 54Fh; unsigned int
0x18004b9d7  lea     rcx, aCwwansmsdevice_0; "CWwanSmsDevice::OnNewSimMessageStatus"
0x18004b9de  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b9e3  nop
0x18004b9e4  mov     rax, [rsi]
0x18004b9e7  mov     rcx, rsi
0x18004b9ea  mov     rax, [rax+8]
0x18004b9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9f3  nop
0x18004b9f4  mov     rcx, [rbp+57h+var_28]
0x18004b9f8  xor     rcx, rsp; StackCookie
0x18004b9fb  call    __security_check_cookie
0x18004ba00  mov     rbx, [rsp+0B0h+arg_18]
0x18004ba08  add     rsp, 90h
0x18004ba0f  pop     r15
0x18004ba11  pop     r14
0x18004ba13  pop     rdi
0x18004ba14  pop     rsi
0x18004ba15  pop     rbp
0x18004ba16  retn
```
