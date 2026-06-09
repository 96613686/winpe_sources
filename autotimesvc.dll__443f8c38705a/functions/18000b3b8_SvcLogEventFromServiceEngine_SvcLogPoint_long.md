# SvcLogEventFromServiceEngine(SvcLogPoint,long)

- ea: `0x18000b3b8`
- end: `0x18000b447`
- name: `?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003860`
- `0x180003b00`

## callees

- `0x180001270`
- `0x1800012f0`
- `0x18000b3b8`

## pseudocode

```c
__int64 __fastcall SvcLogEventFromServiceEngine(__int64 a1, int a2)
{
  __int64 result; // rax
  __int16 *v3; // rdx

  result = (unsigned int)dword_18001C010;
  if ( a2 < 0 )
  {
    if ( (unsigned int)dword_18001C010 > 2 )
    {
      result = tlgKeywordOn(&dword_18001C010, 0x400000000001LL);
      if ( (_BYTE)result )
      {
        v3 = word_180016962;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                 (__int64)&dword_18001C010,
                 (__int64)v3,
                 0);
      }
    }
  }
  else if ( (unsigned int)dword_18001C010 > 4 )
  {
    result = tlgKeywordOn(&dword_18001C010, 1);
    if ( (_BYTE)result )
    {
      v3 = (__int16 *)&dword_1800169C4;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               (__int64)&dword_18001C010,
               (__int64)v3,
               0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b3b8  sub     rsp, 38h
0x18000b3bc  mov     eax, cs:dword_18001C010
0x18000b3c2  mov     r8d, edx
0x18000b3c5  mov     r9d, ecx
0x18000b3c8  test    edx, edx
0x18000b3ca  js      short loc_18000B3EF
0x18000b3cc  cmp     eax, 4
0x18000b3cf  jbe     short loc_18000B442
0x18000b3d1  mov     edx, 1
0x18000b3d6  lea     rcx, dword_18001C010
0x18000b3dd  call    _tlgKeywordOn
0x18000b3e2  test    al, al
0x18000b3e4  jz      short loc_18000B442
0x18000b3e6  lea     rdx, dword_1800169C4
0x18000b3ed  jmp     short loc_18000B415
0x18000b3ef  cmp     eax, 2
0x18000b3f2  jbe     short loc_18000B442
0x18000b3f4  mov     rdx, 400000000001h
0x18000b3fe  lea     rcx, dword_18001C010
0x18000b405  call    _tlgKeywordOn
0x18000b40a  test    al, al
0x18000b40c  jz      short loc_18000B442
0x18000b40e  lea     rdx, word_180016962
0x18000b415  lea     rax, [rsp+38h+arg_8]
0x18000b41a  mov     [rsp+38h+var_10], rax
0x18000b41f  lea     rax, [rsp+38h+arg_10]
0x18000b424  mov     [rsp+38h+arg_8], r8d
0x18000b429  lea     rcx, dword_18001C010
0x18000b430  xor     r8d, r8d
0x18000b433  mov     [rsp+38h+var_18], rax
0x18000b438  mov     [rsp+38h+arg_10], r9d
0x18000b43d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000b442  add     rsp, 38h
0x18000b446  retn
```
