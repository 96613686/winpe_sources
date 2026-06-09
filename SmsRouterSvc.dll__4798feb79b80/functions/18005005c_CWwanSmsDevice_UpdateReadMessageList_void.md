# CWwanSmsDevice::UpdateReadMessageList(void)

- ea: `0x18005005c`
- end: `0x18005022c`
- name: `?UpdateReadMessageList@CWwanSmsDevice@@AEAAXXZ`
- size: `464`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004aee0`
- `0x18004c474`

## callees

- `0x180003a60`
- `0x180032f88`
- `0x180048fe8`
- `0x18005005c`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `wwapi!WwanSmsRead` at `0x18005013d`
- `wwapi!WwanSmsRead` at `0x18005013d`

## string_xrefs

- `0x1800501df`: `Failed to read SIM message at messageIndex %d, SmsFormat: %d and readFlag: %d`
- `0x18005019f`: `WwanSmsRead called for messageIndex: %d, SmsFormat: %d and readFlag: %d has requestId: %d`
- `0x1800500bf`: `Old Message Read Already in progress, RequestId = %d`
- `0x1800500cb`: `CWwanSmsDevice::UpdateReadMessageList`
- `0x1800501ab`: `CWwanSmsDevice::UpdateReadMessageList`
- `0x1800501ee`: `CWwanSmsDevice::UpdateReadMessageList`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWwanSmsDevice::UpdateReadMessageList(CWwanSmsDevice *this)
{
  char *v2; // rdi
  int v3; // r9d
  __int64 v4; // rax
  signed int v5; // eax
  unsigned int v6; // [rsp+40h] [rbp-40h] BYREF
  int v7; // [rsp+44h] [rbp-3Ch] BYREF
  void **v8; // [rsp+48h] [rbp-38h]
  char *v9; // [rsp+50h] [rbp-30h]
  _BYTE v10[16]; // [rsp+58h] [rbp-28h] BYREF
  int v11; // [rsp+68h] [rbp-18h] BYREF
  __int64 v12; // [rsp+6Ch] [rbp-14h]

  v8 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v2 = (char *)this + 32;
  v9 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  v6 = 0;
  v7 = 0;
  v3 = *((_DWORD *)this + 44);
  if ( v3 == -1 )
  {
    v4 = *((_QWORD *)this + 56);
    if ( v4 != *((_QWORD *)this + 57) )
      *((_QWORD *)this + 57) = v4;
    v11 = *((_DWORD *)this + 42);
    v12 = 3;
    v5 = WwanSmsRead(*((_QWORD *)this + 18), (char *)this + 152, &v11, &v6, 0, 0);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      LogSmsRouterError(
        "CWwanSmsDevice::UpdateReadMessageList",
        0x757u,
        v5,
        "Failed to read SIM message at messageIndex %d, SmsFormat: %d and readFlag: %d",
        0,
        *((_DWORD *)this + 42),
        3);
    }
    else
    {
      *((_DWORD *)this + 44) = v6;
      *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long const &,>(
                               (__int64)this + 384,
                               (__int64)v10,
                               &v6)
                + 20LL) = 0;
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
        (char *)this + 472,
        v10,
        &v7);
      LogSmsRouterInfo(
        "CWwanSmsDevice::UpdateReadMessageList",
        0x74Cu,
        "WwanSmsRead called for messageIndex: %d, SmsFormat: %d and readFlag: %d has requestId: %d",
        v7,
        *((_DWORD *)this + 42),
        3,
        v6);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    LogSmsRouterInfo(
      "CWwanSmsDevice::UpdateReadMessageList",
      0x73Bu,
      "Old Message Read Already in progress, RequestId = %d",
      v3);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
}

```

## disassembly

```asm
0x18005005c  mov     [rsp-8+arg_8], rbx
0x180050061  mov     [rsp-8+arg_10], rdi
0x180050066  push    rbp
0x180050067  mov     rbp, rsp
0x18005006a  sub     rsp, 80h
0x180050071  mov     rax, cs:__security_cookie
0x180050078  xor     rax, rsp
0x18005007b  mov     [rbp+var_8], rax
0x18005007f  mov     rbx, rcx
0x180050082  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180050089  mov     [rbp+var_38], rax
0x18005008d  lea     rdi, [rcx+20h]
0x180050091  mov     [rbp+var_30], rdi
0x180050095  mov     rax, [rdi]
0x180050098  mov     rcx, rdi
0x18005009b  mov     rax, [rax]
0x18005009e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500a3  nop
0x1800500a4  mov     [rbp+var_40], 0
0x1800500ab  mov     [rbp+var_3C], 0
0x1800500b2  mov     r9d, [rbx+0B0h]
0x1800500b9  cmp     r9d, 0FFFFFFFFh
0x1800500bd  jz      short loc_1800500ED
0x1800500bf  lea     r8, aOldMessageRead; "Old Message Read Already in progress, R"...
0x1800500c6  mov     edx, 73Bh; unsigned int
0x1800500cb  lea     rcx, aCwwansmsdevice_5; "CWwanSmsDevice::UpdateReadMessageList"
0x1800500d2  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800500d7  nop
0x1800500d8  mov     rax, [rdi]
0x1800500db  mov     rcx, rdi
0x1800500de  mov     rax, [rax+8]
0x1800500e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500e7  nop
0x1800500e8  jmp     loc_18005020B
0x1800500ed  mov     rax, [rbx+1C0h]
0x1800500f4  cmp     rax, [rbx+1C8h]
0x1800500fb  jz      short loc_180050104
0x1800500fd  mov     [rbx+1C8h], rax
0x180050104  mov     eax, [rbx+0A8h]
0x18005010a  mov     [rbp+var_18], eax
0x18005010d  mov     [rbp+var_14], 3
0x180050115  lea     rdx, [rbx+98h]
0x18005011c  mov     [rsp+80h+var_58], 0
0x180050125  mov     [rsp+80h+var_60], 0
0x18005012e  lea     r9, [rbp+var_40]
0x180050132  lea     r8, [rbp+var_18]
0x180050136  mov     rcx, [rbx+90h]
0x18005013d  call    cs:__imp_WwanSmsRead
0x180050143  test    eax, eax
0x180050145  jnz     short loc_1800501B9
0x180050147  mov     eax, [rbp+var_40]
0x18005014a  mov     [rbx+0B0h], eax
0x180050150  lea     rcx, [rbx+180h]
0x180050157  lea     r8, [rbp+var_40]
0x18005015b  lea     rdx, [rbp+var_28]
0x18005015f  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKK@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x180050164  mov     rcx, [rax]
0x180050167  mov     dword ptr [rcx+14h], 0
0x18005016e  lea     rcx, [rbx+1D8h]
0x180050175  lea     r8, [rbp+var_3C]
0x180050179  lea     rdx, [rbp+var_28]
0x18005017d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong const &)
0x180050182  mov     eax, [rbp+var_40]
0x180050185  mov     [rsp+80h+var_50], eax
0x180050189  mov     dword ptr [rsp+80h+var_58], 3
0x180050191  mov     eax, [rbx+0A8h]
0x180050197  mov     dword ptr [rsp+80h+var_60], eax
0x18005019b  mov     r9d, [rbp+var_3C]
0x18005019f  lea     r8, aWwansmsreadCal; "WwanSmsRead called for messageIndex: %d"...
0x1800501a6  mov     edx, 74Ch; unsigned int
0x1800501ab  lea     rcx, aCwwansmsdevice_5; "CWwanSmsDevice::UpdateReadMessageList"
0x1800501b2  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800501b7  jmp     short loc_1800501FB
0x1800501b9  mov     ecx, [rbx+0A8h]
0x1800501bf  test    eax, eax
0x1800501c1  jle     short loc_1800501CB
0x1800501c3  movzx   eax, ax
0x1800501c6  or      eax, 80070000h
0x1800501cb  mov     [rsp+80h+var_50], 3
0x1800501d3  mov     dword ptr [rsp+80h+var_58], ecx
0x1800501d7  mov     dword ptr [rsp+80h+var_60], 0
0x1800501df  lea     r9, aFailedToReadSi_0; "Failed to read SIM message at messageIn"...
0x1800501e6  mov     r8d, eax; int
0x1800501e9  mov     edx, 757h; unsigned int
0x1800501ee  lea     rcx, aCwwansmsdevice_5; "CWwanSmsDevice::UpdateReadMessageList"
0x1800501f5  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800501fa  nop
0x1800501fb  mov     rax, [rdi]
0x1800501fe  mov     rcx, rdi
0x180050201  mov     rax, [rax+8]
0x180050205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005020a  nop
0x18005020b  mov     rcx, [rbp+var_8]
0x18005020f  xor     rcx, rsp; StackCookie
0x180050212  call    __security_check_cookie
0x180050217  lea     r11, [rsp+80h+var_s0]
0x18005021f  mov     rbx, [r11+18h]
0x180050223  mov     rdi, [r11+20h]
0x180050227  mov     rsp, r11
0x18005022a  pop     rbp
0x18005022b  retn
```
