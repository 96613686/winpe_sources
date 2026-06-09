# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180015614`
- end: `0x1800156d3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `191`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002de0c`
- `0x180031ff0`

## callees

- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800156b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800156b8`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int8 *v8; // [rsp+58h] [rbp-28h]
  int v9; // [rsp+60h] [rbp-20h]
  int v10; // [rsp+64h] [rbp-1Ch]
  __int64 v11; // [rsp+68h] [rbp-18h]
  __int64 v12; // [rsp+70h] [rbp-10h]

  v11 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v12 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v9 = *(unsigned __int16 *)(a2 + 11);
  v8 = a2 + 11;
  UserData.Reserved = 2;
  v10 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x180015614  push    rbp
0x180015616  mov     rbp, rsp
0x180015619  sub     rsp, 80h
0x180015620  mov     rax, cs:__security_cookie
0x180015627  xor     rax, rsp
0x18001562a  mov     [rbp+var_8], rax
0x18001562e  mov     rax, [rbp+arg_20]
0x180015632  mov     r10, rcx
0x180015635  mov     [rbp+var_18], rax
0x180015639  lea     rcx, [rdx+0Bh]
0x18001563d  movzx   eax, byte ptr [rdx]
0x180015640  xor     r9d, r9d; RelatedActivityId
0x180015643  shl     eax, 18h
0x180015646  xor     r8d, r8d; ActivityId
0x180015649  mov     dword ptr [rbp+EventDescriptor.Id], eax
0x18001564c  movzx   eax, word ptr [rdx+1]
0x180015650  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x180015653  mov     rax, [rdx+3]
0x180015657  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18001565b  mov     [rbp+EventDescriptor.Keyword], rax
0x18001565f  mov     rax, [r10+8]
0x180015663  mov     [rbp+var_38.Ptr], rax
0x180015667  mov     [rbp+var_10], 8
0x18001566f  movzx   eax, word ptr [rax]
0x180015672  mov     [rbp+var_38.Size], eax
0x180015675  movzx   eax, word ptr [rcx]
0x180015678  mov     [rbp+var_20], eax
0x18001567b  lea     rax, _TraceLoggingMetadataEnd
0x180015682  mov     [rbp+var_28], rcx
0x180015686  lea     rcx, _TraceLoggingMetadata
0x18001568d  sub     eax, ecx
0x18001568f  mov     dword ptr [rbp+var_38.0Ch], 2
0x180015696  mov     [rbp+var_1C], 1
0x18001569d  mov     [rbp+var_50], eax
0x1800156a0  mov     eax, [rbp+var_50]
0x1800156a3  mov     rcx, [r10+20h]; RegHandle
0x1800156a7  lea     rax, [rbp+var_38]
0x1800156ab  mov     [rsp+80h+UserData], rax; UserData
0x1800156b0  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x1800156b8  call    cs:__imp_EventWriteTransfer
0x1800156be  mov     rcx, [rbp+var_8]
0x1800156c2  xor     rcx, rsp; StackCookie
0x1800156c5  call    __security_check_cookie
0x1800156ca  add     rsp, 80h
0x1800156d1  pop     rbp
0x1800156d2  retn
```
