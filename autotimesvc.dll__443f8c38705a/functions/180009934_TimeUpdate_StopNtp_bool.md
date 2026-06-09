# TimeUpdate::StopNtp(bool)

- ea: `0x180009934`
- end: `0x1800099de`
- name: `?StopNtp@TimeUpdate@@AEAAX_N@Z`
- size: `170`
- prototype: `void __fastcall(TimeUpdate *this, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800061ac`
- `0x180006350`
- `0x1800084c4`

## callees

- `0x1800010f4`
- `0x1800012f0`
- `0x180009934`
- `0x18000b668`
- `0x18000b86c`
- `0x18000b9f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800099bd`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800099bd`

## pseudocode

```c
void __fastcall TimeUpdate::StopNtp(TimeUpdate *this, bool a2)
{
  bool v4; // si

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
      (__int64)&dword_18001C010,
      (__int64)byte_1800164AD,
      0);
  v4 = !a2 && !WNFNotificationDispatcher::IsQueueEmpty((TimeUpdate *)((char *)this + 144));
  WNFNotificationDispatcher::Stop((TimeUpdate *)((char *)this + 144), a2);
  *((_DWORD *)this + 15) = 1;
  WakeByAddressAll((char *)this + 60);
  if ( v4 )
    WNFNotificationDispatcher::Enqueue((int *)this + 36, 32);
}

```

## disassembly

```asm
0x180009934  push    rbx
0x180009936  push    rbp
0x180009937  push    rsi
0x180009938  push    rdi
0x180009939  sub     rsp, 38h
0x18000993d  mov     eax, cs:dword_18001C010
0x180009943  mov     dil, dl
0x180009946  mov     rbp, rcx
0x180009949  cmp     eax, 4
0x18000994c  jbe     short loc_180009988
0x18000994e  mov     edx, 1
0x180009953  lea     rcx, dword_18001C010
0x18000995a  call    _tlgKeywordOn
0x18000995f  test    al, al
0x180009961  jz      short loc_180009988
0x180009963  lea     rax, [rsp+58h+arg_8]
0x180009968  mov     [rsp+58h+arg_8], dil
0x18000996d  xor     r8d, r8d
0x180009970  mov     [rsp+58h+var_38], rax
0x180009975  lea     rdx, byte_1800164AD
0x18000997c  lea     rcx, dword_18001C010
0x180009983  call    ??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)
0x180009988  lea     rbx, [rbp+90h]
0x18000998f  test    dil, dil
0x180009992  jnz     short loc_1800099A5
0x180009994  mov     rcx, rbx; this
0x180009997  call    ?IsQueueEmpty@WNFNotificationDispatcher@@QEBA_NXZ; WNFNotificationDispatcher::IsQueueEmpty(void)
0x18000999c  test    al, al
0x18000999e  jnz     short loc_1800099A5
0x1800099a0  mov     sil, 1
0x1800099a3  jmp     short loc_1800099A8
0x1800099a5  xor     sil, sil
0x1800099a8  mov     dl, dil; bool
0x1800099ab  mov     rcx, rbx; this
0x1800099ae  call    ?Stop@WNFNotificationDispatcher@@QEAAX_N@Z; WNFNotificationDispatcher::Stop(bool)
0x1800099b3  lea     rcx, [rbp+3Ch]; Address
0x1800099b7  mov     dword ptr [rcx], 1
0x1800099bd  call    cs:__imp_WakeByAddressAll
0x1800099c3  test    sil, sil
0x1800099c6  jz      short loc_1800099D5
0x1800099c8  mov     edx, 20h ; ' '
0x1800099cd  mov     rcx, rbx
0x1800099d0  call    ?Enqueue@WNFNotificationDispatcher@@QEAA_NW4ActionType@@@Z; WNFNotificationDispatcher::Enqueue(ActionType)
0x1800099d5  add     rsp, 38h
0x1800099d9  pop     rdi
0x1800099da  pop     rsi
0x1800099db  pop     rbp
0x1800099dc  pop     rbx
0x1800099dd  retn
```
