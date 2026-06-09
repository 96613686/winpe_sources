# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180010d30`
- end: `0x180010e11`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `225`
- prototype: `int __fastcall(__int64, const GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010e20`

## callees

- `0x180010d30`
- `0x1800181b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010df9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010df9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(__int64 a1, const GUID *a2)
{
  __int64 v2; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-30h] BYREF
  char *v6; // [rsp+58h] [rbp-20h]
  int v7; // [rsp+60h] [rbp-18h]
  int v8; // [rsp+64h] [rbp-14h]

  if ( *(_DWORD *)a1 > 5u && (*(_QWORD *)(a1 + 16) & 0x400000000000LL) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 24) & 0x400000000000LL;
    if ( v2 == *(_QWORD *)(a1 + 24) )
    {
      *(_DWORD *)&EventDescriptor.Level = 517;
      UserData.Ptr = *(_QWORD *)(a1 + 8);
      EventDescriptor.Keyword = 0x400000000000LL;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v6 = &byte_18002760F;
      UserData.Reserved = 2;
      v7 = 32;
      v8 = 1;
      LODWORD(v2) = EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a2, 0, 2u, &UserData);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180010d30  sub     rsp, 78h
0x180010d34  mov     rax, cs:__security_cookie
0x180010d3b  xor     rax, rsp
0x180010d3e  mov     [rsp+78h+var_10], rax
0x180010d43  cmp     dword ptr [rcx], 5
0x180010d46  mov     r10, rcx
0x180010d49  jbe     loc_180010DFF
0x180010d4f  mov     r8, 400000000000h
0x180010d59  test    [rcx+10h], r8
0x180010d5d  jz      loc_180010DFF
0x180010d63  mov     rax, [rcx+18h]
0x180010d67  and     rax, r8
0x180010d6a  cmp     rax, [rcx+18h]
0x180010d6e  jnz     loc_180010DFF
0x180010d74  movzx   eax, cs:word_180027605
0x180010d7b  xor     r9d, r9d; RelatedActivityId
0x180010d7e  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x180010d82  mov     rax, [rcx+8]
0x180010d86  lea     rcx, _TraceLoggingMetadata
0x180010d8d  mov     [rsp+78h+var_30.Ptr], rax
0x180010d92  mov     [rsp+78h+EventDescriptor.Keyword], r8
0x180010d97  mov     r8, rdx; ActivityId
0x180010d9a  mov     dword ptr [rsp+78h+EventDescriptor.Id], 0B000000h
0x180010da2  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x180010da7  movzx   eax, word ptr [rax]
0x180010daa  mov     [rsp+78h+var_30.Size], eax
0x180010dae  lea     rax, byte_18002760F
0x180010db5  mov     [rsp+78h+var_20], rax
0x180010dba  lea     rax, _TraceLoggingMetadataEnd
0x180010dc1  sub     eax, ecx
0x180010dc3  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x180010dcb  mov     [rsp+78h+var_18], 20h ; ' '
0x180010dd3  mov     [rsp+78h+var_14], 1
0x180010ddb  mov     [rsp+78h+var_48], eax
0x180010ddf  mov     eax, [rsp+78h+var_48]
0x180010de3  mov     rcx, [r10+20h]; RegHandle
0x180010de7  lea     rax, [rsp+78h+var_30]
0x180010dec  mov     [rsp+78h+UserData], rax; UserData
0x180010df1  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x180010df9  call    cs:__imp_EventWriteTransfer
0x180010dff  mov     rcx, [rsp+78h+var_10]
0x180010e04  xor     rcx, rsp; StackCookie
0x180010e07  call    __security_check_cookie
0x180010e0c  add     rsp, 78h
0x180010e10  retn
```
