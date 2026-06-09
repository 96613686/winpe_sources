# VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])

- ea: `0x140006684`
- end: `0x140006711`
- name: `??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z`
- size: `141`
- prototype: `ULONG __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, __int64, __int64, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ed90`
- `0x14000eed0`
- `0x14000f010`
- `0x140022a10`

## callees

- `0x140002310`
- `0x140006684`
- `0x14000d5cc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400066ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400066ee`

## pseudocode

```c
ULONG __fastcall VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  struct _VML_ETW_TRACE *v5; // rbx
  ULONG result; // eax
  unsigned int v9; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-34h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-20h] BYREF

  v5 = g_VmlEtwTrace;
  if ( g_VmlEtwTrace )
  {
    VmCreateDataDescriptor(&v12, &v10, a5);
    VmCreateDataDescriptor(&UserData, &v9, a4);
    return EventWrite(*((_QWORD *)v5 + 2), EventDescriptor, 2u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140006684  mov     r11, rsp
0x140006687  mov     [r11+10h], rbx
0x14000668b  mov     [r11+18h], rsi
0x14000668f  push    rdi
0x140006690  sub     rsp, 50h
0x140006694  mov     rax, cs:__security_cookie
0x14000669b  xor     rax, rsp
0x14000669e  mov     [rsp+58h+var_10], rax
0x1400066a3  mov     rbx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x1400066aa  mov     rsi, r9
0x1400066ad  mov     r8, [rsp+58h+arg_20]; unsigned __int16 *
0x1400066b5  mov     rdi, rcx
0x1400066b8  test    rbx, rbx
0x1400066bb  jz      short loc_1400066F4
0x1400066bd  lea     rdx, [r11-34h]; unsigned int *
0x1400066c1  lea     rcx, [r11-20h]; struct _EVENT_DATA_DESCRIPTOR *
0x1400066c5  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400066ca  mov     r8, rsi; unsigned __int16 *
0x1400066cd  lea     rdx, [rsp+58h+var_38]; unsigned int *
0x1400066d2  lea     rcx, [rsp+58h+UserData]; struct _EVENT_DATA_DESCRIPTOR *
0x1400066d7  call    ?VmCreateDataDescriptor@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@AEAIPEBG@Z; VmCreateDataDescriptor(_EVENT_DATA_DESCRIPTOR *,uint &,ushort const *)
0x1400066dc  mov     rcx, [rbx+10h]; RegHandle
0x1400066e0  lea     r9, [rsp+58h+UserData]; UserData
0x1400066e5  mov     r8d, 2; UserDataCount
0x1400066eb  mov     rdx, rdi; EventDescriptor
0x1400066ee  call    cs:__imp_EventWrite
0x1400066f4  mov     rcx, [rsp+58h+var_10]
0x1400066f9  xor     rcx, rsp; StackCookie
0x1400066fc  call    __security_check_cookie
0x140006701  mov     rbx, [rsp+58h+arg_8]
0x140006706  mov     rsi, [rsp+58h+arg_10]
0x14000670b  add     rsp, 50h
0x14000670f  pop     rdi
0x140006710  retn
```
