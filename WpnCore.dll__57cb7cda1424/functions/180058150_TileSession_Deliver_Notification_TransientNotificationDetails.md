# TileSession::Deliver(Notification *,TransientNotificationDetails *)

- ea: `0x180058150`
- end: `0x18005833c`
- name: `?Deliver@TileSession@@UEAAJPEAVNotification@@PEAVTransientNotificationDetails@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(TileSession *__hidden this, struct Notification *, struct TransientNotificationDetails *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180011618`
- `0x180013360`
- `0x1800296b4`
- `0x180058150`
- `0x180058344`
- `0x18005841c`
- `0x180058464`
- `0x180058bb4`
- `0x18005a02c`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180058279`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180058279`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800581bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800581bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005832f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005832f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TileSession::Deliver(TileSession *this, RTL_SRWLOCK *a2, struct TransientNotificationDetails *a3)
{
  int v6; // ebx
  RTL_SRWLOCK *v7; // rdx
  __int64 v8; // rcx
  char v9; // si
  unsigned __int64 v10; // rbx
  __int128 *v11; // rdx
  unsigned int v12; // r15d
  TileSession *v13; // r14
  char v14; // bl
  _QWORD *handlerKey; // rax
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-50h]
  LPVOID pv[3]; // [rsp+28h] [rbp-48h] BYREF
  __int128 v20; // [rsp+40h] [rbp-30h] BYREF
  __int128 v21; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v18 = 0;
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v6 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, LPVOID *))a2[4].Ptr + 4))(a2 + 4, pv);
  if ( v6 < 0 )
  {
    v17 = 76;
  }
  else
  {
    AcquireSRWLockShared(a2 + 44);
    v18 = (_DWORD)a2 + 352;
    v7 = a2 + 13;
    v20 = 0;
    v21 = 0;
    if ( a2[16].Ptr > (PVOID)7 )
      v7 = (RTL_SRWLOCK *)v7->Ptr;
    std::wstring::_Construct<2,unsigned short const *>(&v20, v7, a2[15].Ptr);
    v9 = 2;
    if ( a2 != (RTL_SRWLOCK *)-352LL )
      ReleaseSRWLockShared(a2 + 44);
    v10 = *((_QWORD *)&v21 + 1);
    v11 = &v20;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v11 = (__int128 *)v20;
    v12 = TileSession::DeliveryTypeFromNotificationTypeName(v8, v11);
    if ( v10 > 7 )
      std::_Deallocate<16>((void *)v20, 2 * v10 + 2);
    v13 = (TileSession *)((char *)this - 8);
    if ( (unsigned __int8)TileSession::IsWildCardEnabled(v13, v12) )
      goto LABEL_11;
    handlerKey = (_QWORD *)Notification::get_handlerKey(a2, &v20);
    v9 = 3;
    v18 = 3;
    if ( handlerKey[3] > 7u )
      handlerKey = (_QWORD *)*handlerKey;
    if ( (unsigned __int8)TileSession::IsAppSubscribed(v13, handlerKey, v12) )
LABEL_11:
      v14 = 1;
    else
      v14 = 0;
    if ( (v9 & 1) != 0 && *((_QWORD *)&v21 + 1) > 7u )
      std::_Deallocate<16>((void *)v20, 2LL * *((_QWORD *)&v21 + 1) + 2);
    if ( !v14 || (v6 = TileSession::DeliverInternal(v13, (struct Notification *)a2, a3), v6 >= 0) )
    {
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      return 0;
    }
    v17 = 82;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\tilesession.cpp",
    (const char *)(unsigned int)v6,
    v18);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180058150  push    rbp
0x180058152  push    rbx
0x180058153  push    rsi
0x180058154  push    rdi
0x180058155  push    r12
0x180058157  push    r14
0x180058159  push    r15
0x18005815b  mov     rbp, rsp
0x18005815e  sub     rsp, 70h
0x180058162  mov     rax, cs:__security_cookie
0x180058169  xor     rax, rsp
0x18005816c  mov     [rbp+var_10], rax
0x180058170  mov     r12, r8
0x180058173  mov     rdi, rdx
0x180058176  mov     r14, rcx
0x180058179  mov     dword ptr [rbp+var_50], 0
0x180058180  mov     [rbp+pv], 0
0x180058188  lea     rcx, [rdx+20h]
0x18005818c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058190  mov     [rbp+var_40], rax
0x180058194  mov     [rbp+var_38], rax
0x180058198  mov     rax, [rcx]
0x18005819b  lea     rdx, [rbp+pv]
0x18005819f  mov     rax, [rax+20h]
0x1800581a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581a8  mov     ebx, eax
0x1800581aa  test    eax, eax
0x1800581ac  js      loc_18005830D
0x1800581b2  lea     rbx, [rdi+160h]
0x1800581b9  mov     rcx, rbx; SRWLock
0x1800581bc  call    cs:__imp_AcquireSRWLockShared
0x1800581c2  mov     [rbp+var_50], rbx
0x1800581c6  lea     rdx, [rdi+68h]
0x1800581ca  xorps   xmm0, xmm0
0x1800581cd  movups  [rbp+var_30], xmm0
0x1800581d1  xorps   xmm1, xmm1
0x1800581d4  movdqu  [rbp+var_20], xmm1
0x1800581d9  mov     r8, [rdx+10h]
0x1800581dd  cmp     qword ptr [rdx+18h], 7
0x1800581e2  jbe     short loc_1800581E7
0x1800581e4  mov     rdx, [rdx]
0x1800581e7  lea     rcx, [rbp+var_30]
0x1800581eb  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800581f0  mov     esi, 2
0x1800581f5  test    rbx, rbx
0x1800581f8  jnz     short loc_180058276
0x1800581fa  mov     rbx, qword ptr [rbp+var_20+8]
0x1800581fe  lea     rdx, [rbp+var_30]
0x180058202  cmp     rbx, 7
0x180058206  cmova   rdx, qword ptr [rbp+var_30]
0x18005820b  call    ?DeliveryTypeFromNotificationTypeName@TileSession@@AEAA?AW4TileDeliveryType@@PEBG@Z; TileSession::DeliveryTypeFromNotificationTypeName(ushort const *)
0x180058210  mov     r15d, eax
0x180058213  cmp     rbx, 7
0x180058217  ja      loc_1800582DC
0x18005821d  add     r14, 0FFFFFFFFFFFFFFF8h
0x180058221  mov     edx, r15d
0x180058224  mov     rcx, r14
0x180058227  call    ?IsWildCardEnabled@TileSession@@AEAA_NW4TileDeliveryType@@@Z; TileSession::IsWildCardEnabled(TileDeliveryType)
0x18005822c  test    al, al
0x18005822e  jz      short loc_180058284
0x180058230  mov     bl, 1
0x180058232  test    sil, 1
0x180058236  jz      short loc_180058246
0x180058238  mov     rdx, qword ptr [rbp+var_20+8]
0x18005823c  cmp     rdx, 7
0x180058240  ja      loc_1800582F2
0x180058246  test    bl, bl
0x180058248  jnz     short loc_1800582BD
0x18005824a  mov     rcx, [rbp+pv]; pv
0x18005824e  test    rcx, rcx
0x180058251  jz      short loc_180058259
0x180058253  call    cs:__imp_CoTaskMemFree
0x180058259  xor     eax, eax
0x18005825b  mov     rcx, [rbp+var_10]
0x18005825f  xor     rcx, rsp; StackCookie
0x180058262  call    __security_check_cookie
0x180058267  add     rsp, 70h
0x18005826b  pop     r15
0x18005826d  pop     r14
0x18005826f  pop     r12
0x180058271  pop     rdi
0x180058272  pop     rsi
0x180058273  pop     rbx
0x180058274  pop     rbp
0x180058275  retn
0x180058276  mov     rcx, rbx; SRWLock
0x180058279  call    cs:__imp_ReleaseSRWLockShared
0x18005827f  jmp     loc_1800581FA
0x180058284  lea     rdx, [rbp+var_30]
0x180058288  mov     rcx, rdi
0x18005828b  call    ?get_handlerKey@Notification@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Notification::get_handlerKey(void)
0x180058290  nop
0x180058291  mov     esi, 3
0x180058296  mov     dword ptr [rbp+var_50], esi
0x180058299  cmp     qword ptr [rax+18h], 7
0x18005829e  ja      short loc_180058308
0x1800582a0  mov     r8d, r15d
0x1800582a3  mov     rdx, rax
0x1800582a6  mov     rcx, r14
0x1800582a9  call    ?IsAppSubscribed@TileSession@@AEAA_NPEBGW4TileDeliveryType@@@Z; TileSession::IsAppSubscribed(ushort const *,TileDeliveryType)
0x1800582ae  test    al, al
0x1800582b0  jnz     loc_180058230
0x1800582b6  xor     bl, bl
0x1800582b8  jmp     loc_180058232
0x1800582bd  mov     r8, r12; struct TransientNotificationDetails *
0x1800582c0  mov     rdx, rdi; struct Notification *
0x1800582c3  mov     rcx, r14; this
0x1800582c6  call    ?DeliverInternal@TileSession@@AEAAJPEAVNotification@@PEAVTransientNotificationDetails@@@Z; TileSession::DeliverInternal(Notification *,TransientNotificationDetails *)
0x1800582cb  mov     ebx, eax
0x1800582cd  test    eax, eax
0x1800582cf  jns     loc_18005824A
0x1800582d5  mov     edx, 52h ; 'R'
0x1800582da  jmp     short loc_180058312
0x1800582dc  lea     rdx, ds:2[rbx*2]
0x1800582e4  mov     rcx, qword ptr [rbp+var_30]
0x1800582e8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800582ed  jmp     loc_18005821D
0x1800582f2  lea     rdx, ds:2[rdx*2]
0x1800582fa  mov     rcx, qword ptr [rbp+var_30]
0x1800582fe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180058303  jmp     loc_180058246
0x180058308  mov     rax, [rax]
0x18005830b  jmp     short loc_1800582A0
0x18005830d  mov     edx, 4Ch ; 'L'; void *
0x180058312  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180058319  mov     r9d, ebx; char *
0x18005831c  mov     rcx, [rbp+38h]; this
0x180058320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058325  nop
0x180058326  mov     rcx, [rbp+pv]; pv
0x18005832a  test    rcx, rcx
0x18005832d  jz      short loc_180058335
0x18005832f  call    cs:__imp_CoTaskMemFree
0x180058335  mov     eax, ebx
0x180058337  jmp     loc_18005825B
```
