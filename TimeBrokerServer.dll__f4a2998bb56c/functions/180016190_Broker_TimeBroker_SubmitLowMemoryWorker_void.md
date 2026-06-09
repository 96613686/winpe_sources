# Broker::TimeBroker::SubmitLowMemoryWorker(void)

- ea: `0x180016190`
- end: `0x180016207`
- name: `?SubmitLowMemoryWorker@TimeBroker@Broker@@AEAAXXZ`
- size: `119`
- prototype: `void __fastcall(Broker::TimeBroker *this, __int64, int, void (*)(void *, unsigned int, unsigned int))`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019de2`
- `0x180019e10`
- `0x180019e3e`
- `0x18001a900`
- `0x18001bd50`

## callees

- `0x180001008`
- `0x18000d2a8`
- `0x18000ee60`
- `0x180016190`

## pseudocode

```c
void __fastcall Broker::TimeBroker::SubmitLowMemoryWorker(
        Broker::TimeBroker *this,
        __int64 a2,
        int a3,
        void (*a4)(void *, unsigned int, unsigned int))
{
  bool v4; // zf
  union _LARGE_INTEGER v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  union _LARGE_INTEGER v9; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 160) )
  {
    v4 = *((_QWORD *)this + 14) == 0;
    *((_BYTE *)this + 160) = 1;
    if ( !v4 )
    {
      v5.QuadPart = *((_QWORD *)this + 25) + *((unsigned int *)this + 41);
      Broker::SystemTimer::SetTimer(*((union _LARGE_INTEGER **)this + 14), v5, a3, a4);
      if ( (unsigned int)dword_180026058 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180026058, 1) )
        {
          v9 = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v6,
            (__int64)byte_1800206DB,
            v7,
            v8,
            (__int64)&v9);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180016190  push    rbx
0x180016192  sub     rsp, 30h
0x180016196  cmp     byte ptr [rcx+0A0h], 0
0x18001619d  jnz     short loc_180016201
0x18001619f  cmp     qword ptr [rcx+70h], 0
0x1800161a4  mov     byte ptr [rcx+0A0h], 1
0x1800161ab  jz      short loc_180016201
0x1800161ad  mov     ebx, [rcx+0A4h]
0x1800161b3  add     rbx, [rcx+0C8h]
0x1800161ba  mov     rcx, [rcx+70h]; this
0x1800161be  mov     rdx, rbx; union _LARGE_INTEGER
0x1800161c1  call    ?SetTimer@SystemTimer@Broker@@QEAAX_J@Z; Broker::SystemTimer::SetTimer(__int64)
0x1800161c6  mov     eax, cs:dword_180026058
0x1800161cc  cmp     eax, 5
0x1800161cf  jbe     short loc_180016201
0x1800161d1  mov     edx, 1
0x1800161d6  lea     rcx, dword_180026058
0x1800161dd  call    _tlgKeywordOn
0x1800161e2  test    al, al
0x1800161e4  jz      short loc_180016201
0x1800161e6  lea     rax, [rsp+38h+arg_0]
0x1800161eb  mov     [rsp+38h+arg_0], rbx
0x1800161f0  lea     rdx, byte_1800206DB
0x1800161f7  mov     [rsp+38h+var_18], rax
0x1800161fc  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180016201  add     rsp, 30h
0x180016205  pop     rbx
0x180016206  retn
```
