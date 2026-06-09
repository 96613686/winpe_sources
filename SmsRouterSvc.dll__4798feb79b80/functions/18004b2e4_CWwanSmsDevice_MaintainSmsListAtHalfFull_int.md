# CWwanSmsDevice::MaintainSmsListAtHalfFull(int)

- ea: `0x18004b2e4`
- end: `0x18004b4f6`
- name: `?MaintainSmsListAtHalfFull@CWwanSmsDevice@@AEAAXH@Z`
- size: `530`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004c12c`
- `0x18004c474`
- `0x18004d1d8`
- `0x18004d928`
- `0x18004e378`

## callees

- `0x18000498c`
- `0x180032f88`
- `0x180048dd8`
- `0x18004b2e4`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `wwapi!WwanSmsDelete` at `0x18004b416`
- `wwapi!WwanSmsDelete` at `0x18004b416`

## string_xrefs

- `0x18004b39c`: `Store full handling in progress. Number of read messages (%d), MaxMessage (%d)`
- `0x18004b386`: `Number of read messages (%d) are greater than half full (%d/2), try to delete as much as possible`
- `0x18004b42b`: `WwanSmsDelete called for messageIndex: %d, has requestId: %d`
- `0x18004b4bd`: `Message list (%d) already at half full (%d/2), nothing to be done`
- `0x18004b48b`: `Failed to delete SIM message at messageIndex %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWwanSmsDevice::MaintainSmsListAtHalfFull(CWwanSmsDevice *this, int a2)
{
  char *v4; // rbx
  unsigned __int64 v5; // r9
  unsigned int v6; // edx
  char *v7; // r8
  int v8; // esi
  signed int v9; // eax
  _BYTE v10[24]; // [rsp+40h] [rbp-18h] BYREF
  int v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v4 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  v12 = 0;
  v11 = 0;
  v5 = (__int64)(*((_QWORD *)this + 57) - *((_QWORD *)this + 56)) >> 4;
  if ( !v5 )
  {
    LogSmsRouterInfo("CWwanSmsDevice::MaintainSmsListAtHalfFull", 0x6FFu, "Message list is empty, nothing can be done");
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return;
  }
  if ( v5 <= (unsigned __int64)*((unsigned int *)this + 43) >> 1 )
  {
    if ( !a2 )
    {
      LogSmsRouterInfo(
        "CWwanSmsDevice::MaintainSmsListAtHalfFull",
        0x718u,
        "Message list (%d) already at half full (%d/2), nothing to be done",
        v5,
        *((_DWORD *)this + 43));
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
      return;
    }
    v6 = 1807;
    v7 = "Store full handling in progress. Number of read messages (%d), MaxMessage (%d)";
  }
  else
  {
    v6 = 1798;
    v7 = "Number of read messages (%d) are greater than half full (%d/2), try to delete as much as possible";
  }
  LogSmsRouterInfo("CWwanSmsDevice::MaintainSmsListAtHalfFull", v6, v7);
  std::_Sort_unchecked<SmsReadMsgData *,bool (*)(SmsReadMsgData const &,SmsReadMsgData const &)>(
    *((char **)this + 56),
    *((__int128 **)this + 57),
    (__int64)(*((_QWORD *)this + 57) - *((_QWORD *)this + 56)) >> 4,
    (unsigned __int8 (__fastcall *)(__int128 *, __int128 *))SmsMsgDataCompare);
  v8 = **((_DWORD **)this + 56);
  LODWORD(v12) = 1;
  HIDWORD(v12) = v8;
  v9 = WwanSmsDelete(*((_QWORD *)this + 18), (char *)this + 152, &v12, &v11, 0, 0);
  if ( v9 )
  {
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    LogSmsRouterError(
      "CWwanSmsDevice::MaintainSmsListAtHalfFull",
      0x72Fu,
      v9,
      "Failed to delete SIM message at messageIndex %d",
      v8);
  }
  else
  {
    LogSmsRouterInfo(
      "CWwanSmsDevice::MaintainSmsListAtHalfFull",
      0x728u,
      "WwanSmsDelete called for messageIndex: %d, has requestId: %d",
      v8,
      v11);
    memmove_0(
      *((void **)this + 56),
      (const void *)(*((_QWORD *)this + 56) + 16LL),
      *((_QWORD *)this + 57) - (*((_QWORD *)this + 56) + 16LL));
    *((_QWORD *)this + 57) -= 16LL;
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
      (char *)this + 488,
      v10,
      &v11);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
}

```

## disassembly

```asm
0x18004b2e4  mov     r11, rsp
0x18004b2e7  mov     [r11+10h], rbx
0x18004b2eb  mov     [r11+20h], rsi
0x18004b2ef  push    rdi
0x18004b2f0  sub     rsp, 50h
0x18004b2f4  mov     esi, edx
0x18004b2f6  mov     rdi, rcx
0x18004b2f9  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004b300  mov     [r11-28h], rax
0x18004b304  lea     rbx, [rcx+20h]
0x18004b308  mov     [r11-20h], rbx
0x18004b30c  mov     rax, [rbx]
0x18004b30f  mov     rcx, rbx
0x18004b312  mov     rax, [rax]
0x18004b315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b31a  nop
0x18004b31b  mov     [rsp+58h+arg_10], 0
0x18004b324  mov     [rsp+58h+arg_0], 0
0x18004b32c  mov     r9, [rdi+1C8h]
0x18004b333  sub     r9, [rdi+1C0h]
0x18004b33a  sar     r9, 4
0x18004b33e  test    r9, r9
0x18004b341  jnz     short loc_18004B371
0x18004b343  lea     r8, aMessageListIsE; "Message list is empty, nothing can be d"...
0x18004b34a  mov     edx, 6FFh; unsigned int
0x18004b34f  lea     rcx, aCwwansmsdevice_14; "CWwanSmsDevice::MaintainSmsListAtHalfFu"...
0x18004b356  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b35b  nop
0x18004b35c  mov     rax, [rbx]
0x18004b35f  mov     rcx, rbx
0x18004b362  mov     rax, [rax+8]
0x18004b366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b36b  nop
0x18004b36c  jmp     loc_18004B4E6
0x18004b371  mov     ecx, [rdi+0ACh]
0x18004b377  mov     eax, ecx
0x18004b379  shr     rax, 1
0x18004b37c  cmp     r9, rax
0x18004b37f  jbe     short loc_18004B38F
0x18004b381  mov     edx, 706h
0x18004b386  lea     r8, aNumberOfReadMe; "Number of read messages (%d) are greate"...
0x18004b38d  jmp     short loc_18004B3A3
0x18004b38f  test    esi, esi
0x18004b391  jz      loc_18004B4B9
0x18004b397  mov     edx, 70Fh; unsigned int
0x18004b39c  lea     r8, aStoreFullHandl; "Store full handling in progress. Number"...
0x18004b3a3  mov     dword ptr [rsp+58h+var_38], ecx
0x18004b3a7  lea     rcx, aCwwansmsdevice_14; "CWwanSmsDevice::MaintainSmsListAtHalfFu"...
0x18004b3ae  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b3b3  mov     rdx, [rdi+1C8h]
0x18004b3ba  mov     rcx, [rdi+1C0h]
0x18004b3c1  mov     r8, rdx
0x18004b3c4  sub     r8, rcx
0x18004b3c7  sar     r8, 4
0x18004b3cb  lea     r9, ?SmsMsgDataCompare@@YA_NAEBUSmsReadMsgData@@0@Z; SmsMsgDataCompare(SmsReadMsgData const &,SmsReadMsgData const &)
0x18004b3d2  call    ??$_Sort_unchecked@PEAUSmsReadMsgData@@P6A_NAEBU1@0@Z@std@@YAXPEAUSmsReadMsgData@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<SmsReadMsgData *,bool (*)(SmsReadMsgData const &,SmsReadMsgData const &)>(SmsReadMsgData *,SmsReadMsgData *,__int64,bool (*)(SmsReadMsgData const &,SmsReadMsgData const &))
0x18004b3d7  mov     rax, [rdi+1C0h]
0x18004b3de  mov     esi, [rax]
0x18004b3e0  mov     dword ptr [rsp+58h+arg_10], 1
0x18004b3e8  mov     dword ptr [rsp+58h+arg_10+4], esi
0x18004b3ec  lea     rdx, [rdi+98h]
0x18004b3f3  mov     [rsp+58h+var_30], 0
0x18004b3fc  mov     [rsp+58h+var_38], 0
0x18004b405  lea     r9, [rsp+58h+arg_0]
0x18004b40a  lea     r8, [rsp+58h+arg_10]
0x18004b40f  mov     rcx, [rdi+90h]
0x18004b416  call    cs:__imp_WwanSmsDelete
0x18004b41c  test    eax, eax
0x18004b41e  jnz     short loc_18004B47D
0x18004b420  mov     eax, [rsp+58h+arg_0]
0x18004b424  mov     dword ptr [rsp+58h+var_38], eax
0x18004b428  mov     r9d, esi
0x18004b42b  lea     r8, aWwansmsdeleteC; "WwanSmsDelete called for messageIndex: "...
0x18004b432  mov     edx, 728h; unsigned int
0x18004b437  lea     rcx, aCwwansmsdevice_14; "CWwanSmsDevice::MaintainSmsListAtHalfFu"...
0x18004b43e  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b443  mov     rcx, [rdi+1C0h]; void *
0x18004b44a  lea     rdx, [rcx+10h]; Src
0x18004b44e  mov     r8, [rdi+1C8h]
0x18004b455  sub     r8, rdx; Size
0x18004b458  call    memmove_0
0x18004b45d  add     qword ptr [rdi+1C8h], 0FFFFFFFFFFFFFFF0h
0x18004b465  lea     rcx, [rdi+1E8h]
0x18004b46c  lea     r8, [rsp+58h+arg_0]
0x18004b471  lea     rdx, [rsp+58h+var_18]
0x18004b476  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong const &)
0x18004b47b  jmp     short loc_18004B4A7
0x18004b47d  jle     short loc_18004B487
0x18004b47f  movzx   eax, ax
0x18004b482  or      eax, 80070000h
0x18004b487  mov     dword ptr [rsp+58h+var_38], esi
0x18004b48b  lea     r9, aFailedToDelete_0; "Failed to delete SIM message at message"...
0x18004b492  mov     r8d, eax; int
0x18004b495  mov     edx, 72Fh; unsigned int
0x18004b49a  lea     rcx, aCwwansmsdevice_14; "CWwanSmsDevice::MaintainSmsListAtHalfFu"...
0x18004b4a1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004b4a6  nop
0x18004b4a7  mov     rax, [rbx]
0x18004b4aa  mov     rcx, rbx
0x18004b4ad  mov     rax, [rax+8]
0x18004b4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4b6  nop
0x18004b4b7  jmp     short loc_18004B4E6
0x18004b4b9  mov     dword ptr [rsp+58h+var_38], ecx
0x18004b4bd  lea     r8, aMessageListDAl; "Message list (%d) already at half full "...
0x18004b4c4  mov     edx, 718h; unsigned int
0x18004b4c9  lea     rcx, aCwwansmsdevice_14; "CWwanSmsDevice::MaintainSmsListAtHalfFu"...
0x18004b4d0  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004b4d5  nop
0x18004b4d6  mov     rax, [rbx]
0x18004b4d9  mov     rcx, rbx
0x18004b4dc  mov     rax, [rax+8]
0x18004b4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4e5  nop
0x18004b4e6  mov     rbx, [rsp+58h+arg_8]
0x18004b4eb  mov     rsi, [rsp+58h+arg_18]
0x18004b4f0  add     rsp, 50h
0x18004b4f4  pop     rdi
0x18004b4f5  retn
```
