# CWwanSmsDevice::OnSmsReadComplete(WWAN_INTERFACE_OBJECT *)

- ea: `0x18004c268`
- end: `0x18004c46e`
- name: `?OnSmsReadComplete@CWwanSmsDevice@@AEAAXPEAUWWAN_INTERFACE_OBJECT@@@Z`
- size: `518`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this, struct WWAN_INTERFACE_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004cb00`

## callees

- `0x180018334`
- `0x180049670`
- `0x18004c268`
- `0x18004d928`
- `0x18004e378`
- `0x18005120c`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x18004c31f`: `CWwanSmsDevice::OnSmsReadComplete`
- `0x18004c430`: `CWwanSmsDevice::OnSmsReadComplete`
- `0x18004c44a`: `CWwanSmsDevice::OnSmsReadComplete`
- `0x18004c313`: `Sms read completed for apiId: %d, messageIndex: %d, result: %d`
- `0x18004c424`: `Failed to read SIM message at index %d`
- `0x18004c43e`: `Sim has no new messages to be read`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWwanSmsDevice::OnSmsReadComplete(CWwanSmsDevice *this, struct WWAN_INTERFACE_OBJECT *a2)
{
  int v4; // edi
  int v5; // r13d
  int v6; // r12d
  char *v7; // r15
  _DWORD *v8; // rbx
  int v9; // esi
  signed int v10; // r8d
  unsigned int v11; // edx
  int v12; // eax
  __int64 v13; // [rsp+20h] [rbp-58h]
  _DWORD *v14; // [rsp+80h] [rbp+8h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( *((_QWORD *)this + 50) )
  {
    std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::find(
      (char *)this + 384,
      &v14,
      (char *)a2 + 2100);
    v8 = v14;
    if ( v14 != *((_DWORD **)this + 49) )
    {
      LODWORD(v14) = 1;
      v9 = v8[4];
      v5 = v8[5];
      LogSmsRouterInfo(
        "CWwanSmsDevice::OnSmsReadComplete",
        0x42Du,
        "Sms read completed for apiId: %d, messageIndex: %d, result: %d",
        *((_DWORD *)a2 + 525),
        v5,
        *((_DWORD *)a2 + 529));
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::erase(
        (char *)this + 472,
        v8 + 5);
      std::_Hash<stdext::_Hmap_traits<unsigned long,unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,unsigned long>>>>,0>(
        (_QWORD *)this + 48,
        &v15,
        v8);
      if ( *((_DWORD *)this + 44) == v9 )
      {
        v6 = 1;
        *((_DWORD *)this + 44) = -1;
        v4 = 1;
      }
      else
      {
        v4 = (int)v14;
      }
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
  if ( v4 )
  {
    v10 = *((_DWORD *)a2 + 529);
    if ( v10 || (v11 = *((_DWORD *)a2 + 511)) == 0 )
    {
      if ( v5 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        LODWORD(v13) = v5;
        LogSmsRouterError(
          "CWwanSmsDevice::OnSmsReadComplete",
          0x457u,
          v10,
          "Failed to read SIM message at index %d",
          v13);
      }
      else
      {
        LogSmsRouterInfo("CWwanSmsDevice::OnSmsReadComplete", 0x45Eu, "Sim has no new messages to be read");
      }
    }
    else
    {
      v12 = *((_DWORD *)a2 + 510);
      if ( v12 == 3 )
      {
        CWwanSmsDevice::ProcessReadPduMessages(this, *((char **)a2 + 256), v11, 1, v6);
      }
      else if ( v12 == 7 )
      {
        CWwanSmsDevice::ProcessReadCdmaMessages(this, *((char **)a2 + 256), v11, 1, v6);
      }
      else
      {
        LODWORD(v13) = *((_DWORD *)a2 + 510);
        LogSmsRouterError("CWwanSmsDevice::OnSmsReadComplete", 0x44Du, -2147418113, "Invalid SMS format %d", v13);
      }
    }
  }
}

```

## disassembly

```asm
0x18004c268  mov     [rsp+arg_8], rbx
0x18004c26d  push    rbp
0x18004c26e  push    rsi
0x18004c26f  push    rdi
0x18004c270  push    r12
0x18004c272  push    r13
0x18004c274  push    r14
0x18004c276  push    r15
0x18004c278  sub     rsp, 40h
0x18004c27c  mov     rbp, rdx
0x18004c27f  mov     r14, rcx
0x18004c282  xor     edi, edi
0x18004c284  xor     r13d, r13d
0x18004c287  xor     r12d, r12d
0x18004c28a  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004c291  mov     [rsp+78h+var_48], rax
0x18004c296  lea     r15, [rcx+20h]
0x18004c29a  mov     [rsp+78h+var_40], r15
0x18004c29f  mov     rax, [r15]
0x18004c2a2  mov     rcx, r15
0x18004c2a5  mov     rax, [rax]
0x18004c2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2ad  nop
0x18004c2ae  lea     rax, [r14+180h]
0x18004c2b5  cmp     [rax+10h], r12
0x18004c2b9  jbe     loc_18004C376
0x18004c2bf  lea     r8, [rbp+834h]
0x18004c2c6  lea     rdx, [rsp+78h+arg_0]
0x18004c2ce  mov     rcx, rax
0x18004c2d1  call    ?find@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::find(ulong const &)
0x18004c2d6  mov     rbx, [rsp+78h+arg_0]
0x18004c2de  cmp     rbx, [r14+188h]
0x18004c2e5  jz      loc_18004C376
0x18004c2eb  mov     dword ptr [rsp+78h+arg_0], 1
0x18004c2f6  mov     esi, [rbx+10h]
0x18004c2f9  mov     r13d, [rbx+14h]
0x18004c2fd  mov     eax, [rbp+844h]
0x18004c303  mov     [rsp+78h+var_50], eax; int
0x18004c307  mov     dword ptr [rsp+78h+var_58], r13d
0x18004c30c  mov     r9d, [rbp+834h]
0x18004c313  lea     r8, aSmsReadComplet; "Sms read completed for apiId: %d, messa"...
0x18004c31a  mov     edx, 42Dh; unsigned int
0x18004c31f  lea     rcx, aCwwansmsdevice_13; "CWwanSmsDevice::OnSmsReadComplete"
0x18004c326  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004c32b  lea     rcx, [r14+1D8h]
0x18004c332  lea     rdx, [rbx+14h]
0x18004c336  call    ?erase@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::erase(ulong const &)
0x18004c33b  mov     r8, rbx
0x18004c33e  lea     rdx, [rsp+78h+arg_10]
0x18004c346  lea     rcx, [r14+180h]
0x18004c34d  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Hmap_traits@KKV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKK@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@1@V21@@Z; std::_Hash<stdext::_Hmap_traits<ulong,ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,ulong>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,ulong>>>>)
0x18004c352  cmp     [r14+0B0h], esi
0x18004c359  jnz     short loc_18004C36F
0x18004c35b  lea     r12d, [rdi+1]
0x18004c35f  mov     dword ptr [r14+0B0h], 0FFFFFFFFh
0x18004c36a  mov     edi, r12d
0x18004c36d  jmp     short loc_18004C376
0x18004c36f  mov     edi, dword ptr [rsp+78h+arg_0]
0x18004c376  mov     rax, [r15]
0x18004c379  mov     rcx, r15
0x18004c37c  mov     rax, [rax+8]
0x18004c380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c385  nop
0x18004c386  test    edi, edi
0x18004c388  jz      loc_18004C456
0x18004c38e  mov     r8d, [rbp+844h]
0x18004c395  test    r8d, r8d
0x18004c398  jnz     short loc_18004C40A
0x18004c39a  mov     edx, [rbp+7FCh]
0x18004c3a0  test    edx, edx
0x18004c3a2  jz      short loc_18004C40A
0x18004c3a4  mov     eax, [rbp+7F8h]
0x18004c3aa  cmp     eax, 3
0x18004c3ad  jz      short loc_18004C3EB
0x18004c3af  cmp     eax, 7
0x18004c3b2  jz      short loc_18004C3CC
0x18004c3b4  mov     dword ptr [rsp+78h+var_58], eax
0x18004c3b8  lea     r9, aInvalidSmsForm; "Invalid SMS format %d"
0x18004c3bf  mov     edx, 44Dh
0x18004c3c4  mov     r8d, 8000FFFFh
0x18004c3ca  jmp     short loc_18004C430
0x18004c3cc  mov     dword ptr [rsp+78h+var_58], r12d; int
0x18004c3d1  mov     r9d, 1; int
0x18004c3d7  mov     r8d, edx; unsigned int
0x18004c3da  mov     rdx, [rbp+800h]; void *
0x18004c3e1  mov     rcx, r14; this
0x18004c3e4  call    ?ProcessReadCdmaMessages@CWwanSmsDevice@@AEAAXPEAXKHHH@Z; CWwanSmsDevice::ProcessReadCdmaMessages(void *,ulong,int,int,int)
0x18004c3e9  jmp     short loc_18004C456
0x18004c3eb  mov     dword ptr [rsp+78h+var_58], r12d; int
0x18004c3f0  mov     r9d, 1; int
0x18004c3f6  mov     r8d, edx; unsigned int
0x18004c3f9  mov     rdx, [rbp+800h]; void *
0x18004c400  mov     rcx, r14; this
0x18004c403  call    ?ProcessReadPduMessages@CWwanSmsDevice@@AEAAXPEAXKHHH@Z; CWwanSmsDevice::ProcessReadPduMessages(void *,ulong,int,int,int)
0x18004c408  jmp     short loc_18004C456
0x18004c40a  test    r13d, r13d
0x18004c40d  jz      short loc_18004C43E
0x18004c40f  test    r8d, r8d
0x18004c412  jle     short loc_18004C41F
0x18004c414  movzx   r8d, r8w
0x18004c418  or      r8d, 80070000h; int
0x18004c41f  mov     dword ptr [rsp+78h+var_58], r13d
0x18004c424  lea     r9, aFailedToReadSi; "Failed to read SIM message at index %d"
0x18004c42b  mov     edx, 457h; unsigned int
0x18004c430  lea     rcx, aCwwansmsdevice_13; "CWwanSmsDevice::OnSmsReadComplete"
0x18004c437  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004c43c  jmp     short loc_18004C456
0x18004c43e  lea     r8, aSimHasNoNewMes; "Sim has no new messages to be read"
0x18004c445  mov     edx, 45Eh; unsigned int
0x18004c44a  lea     rcx, aCwwansmsdevice_13; "CWwanSmsDevice::OnSmsReadComplete"
0x18004c451  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004c456  mov     rbx, [rsp+78h+arg_8]
0x18004c45e  add     rsp, 40h
0x18004c462  pop     r15
0x18004c464  pop     r14
0x18004c466  pop     r13
0x18004c468  pop     r12
0x18004c46a  pop     rdi
0x18004c46b  pop     rsi
0x18004c46c  pop     rbp
0x18004c46d  retn
```
