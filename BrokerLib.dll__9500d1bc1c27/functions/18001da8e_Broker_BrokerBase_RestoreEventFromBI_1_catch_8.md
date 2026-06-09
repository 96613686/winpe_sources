# _Broker::BrokerBase::RestoreEventFromBI_::_1_::catch$8

- ea: `0x18001da8e`
- end: `0x18001dc05`
- name: `_Broker::BrokerBase::RestoreEventFromBI_::_1_::catch$8`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005b50`
- `0x18000e538`
- `0x18000e9f4`
- `0x18000ea30`
- `0x1800126e0`
- `0x18001da8e`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Broker::BrokerBase::RestoreEventFromBI_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  PVOID v5; // rcx
  __int64 v6; // rdi
  char v7; // dl
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rbx
  void *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9

  v5 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = *(_QWORD *)(a2 + 184);
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v6);
  }
  else
  {
    v6 = *(_QWORD *)(a2 + 184);
  }
  if ( *(_BYTE *)(a2 + 97) )
  {
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v5, 2, a3, a4) )
    {
      *(_BYTE *)(a2 + 96) = v7;
      *(_QWORD *)(a2 + 136) = v6;
      v11 = *(_QWORD *)(a2 + 192);
      *(_QWORD *)(a2 + 128) = *(_QWORD *)(v11 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        v8,
        byte_18002207A,
        v9,
        v10,
        (__int64 *)(a2 + 128),
        (__int64 *)(a2 + 136),
        a2 + 96);
    }
    else
    {
      v11 = *(_QWORD *)(a2 + 192);
    }
    v12 = *(void **)(a2 + 176);
    v13 = (*(unsigned int (__fastcall **)(__int64, _QWORD, void *, _QWORD))(v11 + 128))(
            2,
            *(_QWORD *)(v11 + 8),
            v12,
            *(_QWORD *)(a2 + 144));
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v13, v14) )
    {
      *(_DWORD *)(a2 + 112) = v16;
      *(_QWORD *)(a2 + 136) = v6;
      *(_QWORD *)(a2 + 128) = *(_QWORD *)(v11 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v15,
        byte_180021F3C,
        v16,
        v17,
        (__int64 *)(a2 + 128),
        (__int64 *)(a2 + 136),
        a2 + 112);
    }
  }
  else
  {
    v12 = *(void **)(a2 + 176);
  }
  BciHeapFree(*(void **)(a2 + 120));
  BciHeapFree(v12);
  return 0;
}

```

## disassembly

```asm
0x18001da8e  mov     [rsp+arg_8], rdx
0x18001da93  push    rbx
0x18001da94  push    rbp
0x18001da95  push    rsi
0x18001da96  push    rdi
0x18001da97  sub     rsp, 68h
0x18001da9b  mov     rbp, rdx
0x18001da9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daa5  test    dword ptr [rcx+1Ch], 800h
0x18001daac  jz      short loc_18001DAD5
0x18001daae  cmp     byte ptr [rcx+19h], 2
0x18001dab2  jb      short loc_18001DAD5
0x18001dab4  mov     edx, 2Fh ; '/'
0x18001dab9  mov     rdi, [rbp+0B8h]
0x18001dac0  mov     r9, rdi
0x18001dac3  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18001daca  mov     rcx, [rcx+10h]
0x18001dace  call    WPP_SF__guid_
0x18001dad3  jmp     short loc_18001DADC
0x18001dad5  mov     rdi, [rbp+0B8h]
0x18001dadc  cmp     byte ptr [rbp+61h], 0
0x18001dae0  jz      loc_18001DBD8
0x18001dae6  mov     eax, cs:dword_180028000
0x18001daec  cmp     eax, 4
0x18001daef  jbe     short loc_18001DB4A
0x18001daf1  mov     edx, 2
0x18001daf6  call    _tlgKeywordOn
0x18001dafb  test    al, al
0x18001dafd  jz      short loc_18001DB4A
0x18001daff  mov     [rbp+60h], dl
0x18001db02  mov     [rbp+88h], rdi
0x18001db09  mov     rbx, [rbp+0C0h]
0x18001db10  mov     rax, [rbx+8]
0x18001db14  mov     [rbp+80h], rax
0x18001db1b  lea     rax, [rbp+60h]
0x18001db1f  mov     [rsp+88h+var_58], rax
0x18001db24  lea     rax, [rbp+88h]
0x18001db2b  mov     [rsp+88h+var_60], rax
0x18001db30  lea     rax, [rbp+80h]
0x18001db37  mov     [rsp+88h+var_68], rax
0x18001db3c  lea     rdx, byte_18002207A
0x18001db43  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x18001db48  jmp     short loc_18001DB51
0x18001db4a  mov     rbx, [rbp+0C0h]
0x18001db51  mov     r9, [rbp+90h]
0x18001db58  mov     rsi, [rbp+0B0h]
0x18001db5f  mov     r8, rsi
0x18001db62  mov     rdx, [rbx+8]
0x18001db66  mov     ecx, 2
0x18001db6b  mov     rax, [rbx+80h]
0x18001db72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db77  mov     r8d, eax
0x18001db7a  mov     ecx, cs:dword_180028000
0x18001db80  cmp     ecx, 4
0x18001db83  jbe     short loc_18001DBDF
0x18001db85  mov     edx, 2
0x18001db8a  call    _tlgKeywordOn
0x18001db8f  test    al, al
0x18001db91  jz      short loc_18001DBDF
0x18001db93  mov     [rbp+70h], r8d
0x18001db97  mov     [rbp+88h], rdi
0x18001db9e  mov     rax, [rbx+8]
0x18001dba2  mov     [rbp+80h], rax
0x18001dba9  lea     rax, [rbp+70h]
0x18001dbad  mov     [rsp+88h+var_58], rax
0x18001dbb2  lea     rax, [rbp+88h]
0x18001dbb9  mov     [rsp+88h+var_60], rax
0x18001dbbe  lea     rax, [rbp+80h]
0x18001dbc5  mov     [rsp+88h+var_68], rax
0x18001dbca  lea     rdx, byte_180021F3C
0x18001dbd1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001dbd6  jmp     short loc_18001DBDF
0x18001dbd8  mov     rsi, [rbp+0B0h]
0x18001dbdf  mov     rcx, [rbp+78h]; void *
0x18001dbe3  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x18001dbe8  mov     rcx, rsi; void *
0x18001dbeb  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x18001dbf0  nop
0x18001dbf1  mov     rax, 0
0x18001dbfb  add     rsp, 68h
0x18001dbff  pop     rdi
0x18001dc00  pop     rsi
0x18001dc01  pop     rbp
0x18001dc02  pop     rbx
0x18001dc03  retn
```
