# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001148`
- end: `0x1800011d2`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64 **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180004500`
- `0x180004880`
- `0x180007594`
- `0x180007930`
- `0x1800088dc`

## callees

- `0x18000108c`
- `0x180001148`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &qword_18000F388;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001148  sub     rsp, 78h
0x18000114c  mov     rax, cs:__security_cookie
0x180001153  xor     rax, rsp
0x180001156  mov     [rsp+78h+var_18], rax
0x18000115b  mov     rax, [rsp+78h+arg_20]
0x180001163  xor     r8d, r8d; int
0x180001166  mov     rcx, [rax]
0x180001169  test    rcx, rcx
0x18000116c  jz      short loc_180001185
0x18000116e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001172  inc     rax
0x180001175  cmp     [rcx+rax*2], r8w
0x18000117a  jnz     short loc_180001172
0x18000117c  lea     eax, ds:2[rax*2]
0x180001183  jmp     short loc_180001191
0x180001185  lea     rcx, qword_18000F388
0x18000118c  mov     eax, 2
0x180001191  mov     [rsp+78h+var_20], eax
0x180001195  xor     r9d, r9d; int
0x180001198  lea     rax, [rsp+78h+var_48]
0x18000119d  mov     [rsp+78h+var_28], rcx
0x1800011a2  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x1800011a7  lea     rcx, dword_180013018; int
0x1800011ae  mov     [rsp+78h+var_58], 3; ULONG
0x1800011b6  mov     [rsp+78h+var_1C], r8d
0x1800011bb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011c0  mov     rcx, [rsp+78h+var_18]
0x1800011c5  xor     rcx, rsp; StackCookie
0x1800011c8  call    __security_check_cookie
0x1800011cd  add     rsp, 78h
0x1800011d1  retn
```
