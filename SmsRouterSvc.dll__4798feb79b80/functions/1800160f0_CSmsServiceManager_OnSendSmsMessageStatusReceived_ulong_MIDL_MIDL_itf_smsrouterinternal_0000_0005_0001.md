# CSmsServiceManager::OnSendSmsMessageStatusReceived(ulong,__MIDL___MIDL_itf_smsrouterinternal_0000_0005_0001 *)

- ea: `0x1800160f0`
- end: `0x1800162e1`
- name: `?OnSendSmsMessageStatusReceived@CSmsServiceManager@@UEAAJKPEAU__MIDL___MIDL_itf_smsrouterinternal_0000_0005_0001@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this, unsigned int, struct __MIDL___MIDL_itf_smsrouterinternal_0000_0005_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f50`
- `0x180003f8c`
- `0x180013fd8`
- `0x1800160f0`
- `0x180018334`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180016265`
- `ntdll!RtlPublishWnfStateData` at `0x180016265`

## string_xrefs

- `0x18001616d`: `CSmsServiceManager::OnSendSmsMessageStatusReceived`
- `0x180016222`: `CSmsServiceManager::OnSendSmsMessageStatusReceived`
- `0x180016288`: `CSmsServiceManager::OnSendSmsMessageStatusReceived`
- `0x180016216`: `SendMessage completed ContextId %lu, IsSuccessful: %d, hr: 0x%08X, dwMsgIdsSize: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSmsServiceManager::OnSendSmsMessageStatusReceived(
        CSmsServiceManager *this,
        unsigned int a2,
        struct __MIDL___MIDL_itf_smsrouterinternal_0000_0005_0001 *a3)
{
  char *v5; // r14
  char *v6; // rdi
  unsigned int v8; // r15d
  _DWORD *v9; // rbx
  int v10; // eax
  __int64 i; // rdx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // esi
  _BYTE v15[56]; // [rsp+50h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF
  _DWORD *v18; // [rsp+A8h] [rbp+20h]

  v17 = a2;
  v5 = (char *)this + 840;
  v6 = (char *)this + 24;
  (**((void (__fastcall ***)(char *))this + 3))((char *)this + 24);
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::find(
                    v5,
                    &v16,
                    &v17) == *((_QWORD *)v5 + 1) )
  {
    LogSmsRouterError(
      "CSmsServiceManager::OnSendSmsMessageStatusReceived",
      0x1D6u,
      -2147467259,
      "SmsSendMessage context %lu not found",
      a2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    return 2147500037LL;
  }
  else
  {
    v18 = 0;
    v8 = 4 * *((_DWORD *)a3 + 7) + 32;
    v9 = operator new[](v8);
    v18 = v9;
    *v9 = *((_DWORD *)a3 + 1) == 0;
    v9[1] = *((_DWORD *)a3 + 2);
    v9[2] = *((_DWORD *)a3 + 3);
    v9[3] = *((_DWORD *)a3 + 4);
    v9[4] = *((_DWORD *)a3 + 5);
    v9[5] = *((_DWORD *)a3 + 6);
    v10 = *((_DWORD *)a3 + 7);
    v9[6] = v10;
    for ( i = 0; (unsigned int)i < v9[6]; i = (unsigned int)(i + 1) )
      v9[i + 7] = *((_DWORD *)a3 + i + 8);
    LogSmsRouterInfo(
      "CSmsServiceManager::OnSendSmsMessageStatusReceived",
      0x1ECu,
      "SendMessage completed ContextId %lu, IsSuccessful: %d, hr: 0x%08X, dwMsgIdsSize: %lu",
      a2,
      *((_DWORD *)a3 + 1),
      *((_DWORD *)a3 + 2),
      *((_DWORD *)a3 + 7));
    v16 = a2;
    v12 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
            (__int64)v5,
            (__int64)v15,
            &v16);
    v13 = RtlPublishWnfStateData(**(_QWORD **)(*(_QWORD *)v12 + 24LL), 0, v9, v8, 0);
    if ( v13 )
    {
      v14 = v13 | 0x10000000;
      LogSmsRouterError(
        "CSmsServiceManager::OnSendSmsMessageStatusReceived",
        0x1F7u,
        v13 | 0x10000000,
        "SendMessage.RtlPublishWnfStateData for ContextId: %lu failed",
        a2);
      operator delete(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      return v14;
    }
    else
    {
      operator delete(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800160f0  mov     [rsp+arg_10], rbx
0x1800160f5  mov     [rsp+arg_8], edx
0x1800160f9  push    rbp
0x1800160fa  push    rsi
0x1800160fb  push    rdi
0x1800160fc  push    r14
0x1800160fe  push    r15
0x180016100  sub     rsp, 60h
0x180016104  mov     rsi, r8
0x180016107  mov     ebp, edx
0x180016109  lea     r14, [rcx+348h]
0x180016110  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180016117  mov     [rsp+88h+var_48], rax
0x18001611c  lea     rdi, [rcx+18h]
0x180016120  mov     [rsp+88h+var_40], rdi
0x180016125  mov     rax, [rdi]
0x180016128  mov     rcx, rdi
0x18001612b  mov     rax, [rax]
0x18001612e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016133  nop
0x180016134  lea     r8, [rsp+88h+arg_8]
0x18001613c  lea     rdx, [rsp+88h+arg_0]
0x180016144  mov     rcx, r14
0x180016147  call    ?find@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::find(ulong const &)
0x18001614c  mov     rcx, [r14+8]
0x180016150  cmp     [rax], rcx
0x180016153  jnz     short loc_180016191
0x180016155  mov     dword ptr [rsp+88h+var_68], ebp
0x180016159  lea     r9, aSmssendmessage; "SmsSendMessage context %lu not found"
0x180016160  mov     ebx, 80004005h
0x180016165  mov     r8d, ebx; int
0x180016168  mov     edx, 1D6h; unsigned int
0x18001616d  lea     rcx, aCsmsserviceman_17; "CSmsServiceManager::OnSendSmsMessageSta"...
0x180016174  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180016179  nop
0x18001617a  mov     rdx, [rdi]
0x18001617d  mov     rcx, rdi
0x180016180  mov     rax, [rdx+8]
0x180016184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016189  nop
0x18001618a  mov     eax, ebx
0x18001618c  jmp     loc_1800162CD
0x180016191  mov     [rsp+88h+arg_18], 0
0x18001619d  mov     eax, [rsi+1Ch]
0x1800161a0  lea     r15d, ds:20h[rax*4]
0x1800161a8  mov     ecx, r15d; unsigned __int64
0x1800161ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800161b0  mov     rbx, rax
0x1800161b3  mov     [rsp+88h+arg_18], rax
0x1800161bb  xor     ecx, ecx
0x1800161bd  cmp     [rsi+4], ecx
0x1800161c0  setz    cl
0x1800161c3  mov     [rax], ecx
0x1800161c5  mov     ecx, [rsi+8]
0x1800161c8  mov     [rax+4], ecx
0x1800161cb  mov     ecx, [rsi+0Ch]
0x1800161ce  mov     [rax+8], ecx
0x1800161d1  mov     eax, [rsi+10h]
0x1800161d4  mov     [rbx+0Ch], eax
0x1800161d7  mov     eax, [rsi+14h]
0x1800161da  mov     [rbx+10h], eax
0x1800161dd  mov     eax, [rsi+18h]
0x1800161e0  mov     [rbx+14h], eax
0x1800161e3  mov     eax, [rsi+1Ch]
0x1800161e6  mov     [rbx+18h], eax
0x1800161e9  xor     edx, edx
0x1800161eb  test    eax, eax
0x1800161ed  jz      short loc_1800161FE
0x1800161ef  mov     eax, [rsi+rdx*4+20h]
0x1800161f3  mov     [rbx+rdx*4+1Ch], eax
0x1800161f7  inc     edx
0x1800161f9  cmp     edx, [rbx+18h]
0x1800161fc  jb      short loc_1800161EF
0x1800161fe  mov     eax, [rsi+1Ch]
0x180016201  mov     [rsp+88h+var_58], eax
0x180016205  mov     eax, [rsi+8]
0x180016208  mov     [rsp+88h+var_60], eax
0x18001620c  mov     eax, [rsi+4]
0x18001620f  mov     dword ptr [rsp+88h+var_68], eax
0x180016213  mov     r9d, ebp
0x180016216  lea     r8, aSendmessageCom_0; "SendMessage completed ContextId %lu, Is"...
0x18001621d  mov     edx, 1ECh; unsigned int
0x180016222  lea     rcx, aCsmsserviceman_17; "CSmsServiceManager::OnSendSmsMessageSta"...
0x180016229  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001622e  mov     [rsp+88h+arg_0], ebp
0x180016235  lea     r8, [rsp+88h+arg_0]
0x18001623d  lea     rdx, [rsp+88h+var_38]
0x180016242  mov     rcx, r14
0x180016245  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x18001624a  mov     rcx, [rax]
0x18001624d  mov     rcx, [rcx+18h]
0x180016251  mov     [rsp+88h+var_68], 0
0x18001625a  mov     r9d, r15d
0x18001625d  mov     r8, rbx
0x180016260  xor     edx, edx
0x180016262  mov     rcx, [rcx]
0x180016265  call    cs:__imp_RtlPublishWnfStateData
0x18001626b  mov     esi, eax
0x18001626d  test    eax, eax
0x18001626f  jz      short loc_1800162B2
0x180016271  bts     esi, 1Ch
0x180016275  mov     dword ptr [rsp+88h+var_68], ebp
0x180016279  lea     r9, aSendmessageRtl; "SendMessage.RtlPublishWnfStateData for "...
0x180016280  mov     r8d, esi; int
0x180016283  mov     edx, 1F7h; unsigned int
0x180016288  lea     rcx, aCsmsserviceman_17; "CSmsServiceManager::OnSendSmsMessageSta"...
0x18001628f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180016294  nop
0x180016295  mov     rcx, rbx; Block
0x180016298  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001629d  nop
0x18001629e  mov     rax, [rdi]
0x1800162a1  mov     rcx, rdi
0x1800162a4  mov     rax, [rax+8]
0x1800162a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ad  nop
0x1800162ae  mov     eax, esi
0x1800162b0  jmp     short loc_1800162CD
0x1800162b2  mov     rcx, rbx; Block
0x1800162b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800162ba  nop
0x1800162bb  mov     rax, [rdi]
0x1800162be  mov     rcx, rdi
0x1800162c1  mov     rax, [rax+8]
0x1800162c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ca  nop
0x1800162cb  xor     eax, eax
0x1800162cd  mov     rbx, [rsp+88h+arg_10]
0x1800162d5  add     rsp, 60h
0x1800162d9  pop     r15
0x1800162db  pop     r14
0x1800162dd  pop     rdi
0x1800162de  pop     rsi
0x1800162df  pop     rbp
0x1800162e0  retn
```
