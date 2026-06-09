# CSmsServiceManager::SendMessageClose(ulong *)

- ea: `0x180016d90`
- end: `0x180016e6b`
- name: `?SendMessageClose@CSmsServiceManager@@QEAAJPEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aa30`

## callees

- `0x180013fd8`
- `0x180016d90`
- `0x180018210`
- `0x180018334`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180016e00`
- `ntdll!NtDeleteWnfStateName` at `0x180016e00`

## string_xrefs

- `0x180016e20`: `SendMessage.NtDeleteWnfStateName for ContextId: %lu failed`
- `0x180016e2f`: `CSmsServiceManager::SendMessageClose`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsServiceManager::SendMessageClose(CSmsServiceManager *this, unsigned int *a2)
{
  char *v4; // rdi
  char *v5; // rbp
  __int64 v6; // rax
  int v7; // ebx
  unsigned int v8; // ebx
  _BYTE v10[56]; // [rsp+40h] [rbp-38h] BYREF
  char v11; // [rsp+80h] [rbp+8h] BYREF

  v4 = (char *)this + 40;
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  v5 = (char *)this + 856;
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::find(
                    (char *)this + 856,
                    &v11,
                    a2) == *((_QWORD *)this + 108)
    || (v6 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<unsigned long,>(
               (__int64)this + 856,
               (__int64)v10,
               a2),
        v7 = NtDeleteWnfStateName(*(_QWORD *)(*(_QWORD *)v6 + 24LL)),
        std::_Hash<stdext::_Hmap_traits<unsigned long,std::unique_ptr<SendMessageContext>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SendMessageContext>>>,0>>::erase(
          v5,
          a2),
        !v7) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return 0;
  }
  else
  {
    v8 = v7 | 0x10000000;
    LogSmsRouterError(
      "CSmsServiceManager::SendMessageClose",
      0x20Au,
      v8,
      "SendMessage.NtDeleteWnfStateName for ContextId: %lu failed",
      (_DWORD)a2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return v8;
  }
}

```

## disassembly

```asm
0x180016d90  push    rbx
0x180016d92  push    rbp
0x180016d93  push    rsi
0x180016d94  push    rdi
0x180016d95  sub     rsp, 58h
0x180016d99  mov     rsi, rdx
0x180016d9c  mov     rbx, rcx
0x180016d9f  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180016da6  mov     [rsp+78h+var_48], rax
0x180016dab  lea     rdi, [rcx+28h]
0x180016daf  mov     [rsp+78h+var_40], rdi
0x180016db4  mov     rax, [rdi]
0x180016db7  mov     rcx, rdi
0x180016dba  mov     rax, [rax]
0x180016dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc2  nop
0x180016dc3  lea     rbp, [rbx+358h]
0x180016dca  mov     r8, rsi
0x180016dcd  lea     rdx, [rsp+78h+arg_0]
0x180016dd5  mov     rcx, rbp
0x180016dd8  call    ?find@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::find(ulong const &)
0x180016ddd  mov     rdx, [rbx+360h]
0x180016de4  cmp     [rax], rdx
0x180016de7  jz      short loc_180016E50
0x180016de9  mov     r8, rsi
0x180016dec  lea     rdx, [rsp+78h+var_38]
0x180016df1  mov     rcx, rbp
0x180016df4  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x180016df9  mov     rcx, [rax]
0x180016dfc  mov     rcx, [rcx+18h]
0x180016e00  call    cs:__imp_NtDeleteWnfStateName
0x180016e06  mov     ebx, eax
0x180016e08  mov     rdx, rsi
0x180016e0b  mov     rcx, rbp
0x180016e0e  call    ?erase@?$_Hash@V?$_Hmap_traits@KV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$unique_ptr@USendMessageContext@@U?$default_delete@USendMessageContext@@@std@@@std@@@std@@@2@$0A@@stdext@@@std@@QEAA_KAEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::unique_ptr<SendMessageContext>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::unique_ptr<SendMessageContext>>>,0>>::erase(ulong const &)
0x180016e13  test    ebx, ebx
0x180016e15  jz      short loc_180016E50
0x180016e17  bts     ebx, 1Ch
0x180016e1b  mov     [rsp+78h+var_58], rsi
0x180016e20  lea     r9, aSendmessageNtd; "SendMessage.NtDeleteWnfStateName for Co"...
0x180016e27  mov     r8d, ebx; int
0x180016e2a  mov     edx, 20Ah; unsigned int
0x180016e2f  lea     rcx, aCsmsserviceman_14; "CSmsServiceManager::SendMessageClose"
0x180016e36  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180016e3b  nop
0x180016e3c  mov     rax, [rdi]
0x180016e3f  mov     rcx, rdi
0x180016e42  mov     rax, [rax+8]
0x180016e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e4b  nop
0x180016e4c  mov     eax, ebx
0x180016e4e  jmp     short loc_180016E62
0x180016e50  mov     rax, [rdi]
0x180016e53  mov     rcx, rdi
0x180016e56  mov     rax, [rax+8]
0x180016e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5f  nop
0x180016e60  xor     eax, eax
0x180016e62  add     rsp, 58h
0x180016e66  pop     rdi
0x180016e67  pop     rsi
0x180016e68  pop     rbp
0x180016e69  pop     rbx
0x180016e6a  retn
```
