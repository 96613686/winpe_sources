# Broker::TimeBroker::ConvertEventBlobToParameters(_BR_EVENT_PARAMETER_BLOB const *,_TbiTimeEventCreationParameters &)

- ea: `0x180015464`
- end: `0x180015527`
- name: `?ConvertEventBlobToParameters@TimeBroker@Broker@@CAXPEBU_BR_EVENT_PARAMETER_BLOB@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `195`
- prototype: `void __fastcall(const struct _BR_EVENT_PARAMETER_BLOB *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d388`

## callees

- `0x1800116f4`
- `0x18001396c`
- `0x180013978`
- `0x180015048`
- `0x180015464`

## pseudocode

```c
void __fastcall Broker::TimeBroker::ConvertEventBlobToParameters(
        const struct _BR_EVENT_PARAMETER_BLOB *a1,
        struct _TbiTimeEventCreationParameters *a2)
{
  __int64 v2; // rbx
  unsigned int v5; // ecx
  __int64 v6; // rsi
  struct _TbiTimeEventCreationParameters *v7; // r8
  __int64 v8; // rax
  _BYTE pExceptionObject[88]; // [rsp+20h] [rbp-58h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  v5 = *(_DWORD *)(v2 + 56);
  v6 = v5 + 72;
  if ( v5 >= 0xFFFFFFB8 )
  {
    Broker::BILayer::Failure::Failure((Broker::BILayer::Failure *)pExceptionObject, -1073741811);
    throw (Broker::BILayer::Failure *)pExceptionObject;
  }
  if ( (unsigned int)v6 > *(unsigned __int16 *)a1 )
  {
    Broker::BILayer::Failure::Failure((Broker::BILayer::Failure *)pExceptionObject, -1073741811);
    throw (Broker::BILayer::Failure *)pExceptionObject;
  }
  if ( v5 )
    *(_QWORD *)(v2 + 64) = v2 + 72;
  memset_0(a2, 0, 0xF8u);
  Broker::AdaptFormatFromBIStorage((Broker *)v2, a2, v7);
  *((_DWORD *)a2 + 22) = 0;
  *((_DWORD *)a2 + 18) = 0;
  if ( *(unsigned __int16 *)a1 >= (unsigned int)(v6 + 20) )
  {
    v8 = *((_QWORD *)a1 + 1);
    *(_OWORD *)((char *)a2 + 72) = *(_OWORD *)(v6 + v8);
    *((_DWORD *)a2 + 22) = *(_DWORD *)(v6 + v8 + 16);
  }
}

```

## disassembly

```asm
0x180015464  push    rbx
0x180015466  push    rbp
0x180015467  push    rsi
0x180015468  push    rdi
0x180015469  sub     rsp, 58h
0x18001546d  mov     rbx, [rcx+8]
0x180015471  mov     rdi, rcx
0x180015474  mov     rbp, rdx
0x180015477  mov     ecx, [rbx+38h]
0x18001547a  lea     esi, [rcx+48h]
0x18001547d  cmp     esi, 48h ; 'H'
0x180015480  jb      short loc_1800154E5
0x180015482  movzx   eax, word ptr [rdi]
0x180015485  cmp     esi, eax
0x180015487  ja      short loc_180015506
0x180015489  test    ecx, ecx
0x18001548b  jz      short loc_180015495
0x18001548d  lea     rax, [rbx+48h]
0x180015491  mov     [rbx+40h], rax
0x180015495  xor     edx, edx; Val
0x180015497  mov     r8d, 0F8h; Size
0x18001549d  mov     rcx, rbp; void *
0x1800154a0  call    memset_0
0x1800154a5  mov     rdx, rbp; struct _TbiTimeEventCreationParametersW8_ForBI *
0x1800154a8  mov     rcx, rbx; this
0x1800154ab  call    ?AdaptFormatFromBIStorage@Broker@@YAXAEBU_TbiTimeEventCreationParametersW8_ForBI@@AEAU_TbiTimeEventCreationParameters@@@Z; Broker::AdaptFormatFromBIStorage(_TbiTimeEventCreationParametersW8_ForBI const &,_TbiTimeEventCreationParameters &)
0x1800154b0  mov     dword ptr [rbp+58h], 0
0x1800154b7  lea     ecx, [rsi+14h]
0x1800154ba  mov     dword ptr [rbp+48h], 0
0x1800154c1  movzx   eax, word ptr [rdi]
0x1800154c4  cmp     eax, ecx
0x1800154c6  jb      short loc_1800154DC
0x1800154c8  mov     rax, [rdi+8]
0x1800154cc  movups  xmm0, xmmword ptr [rsi+rax]
0x1800154d0  movdqu  xmmword ptr [rbp+48h], xmm0
0x1800154d5  mov     eax, [rsi+rax+10h]
0x1800154d9  mov     [rbp+58h], eax
0x1800154dc  add     rsp, 58h
0x1800154e0  pop     rdi
0x1800154e1  pop     rsi
0x1800154e2  pop     rbp
0x1800154e3  pop     rbx
0x1800154e4  retn
0x1800154e5  mov     edx, 0C000000Dh; int
0x1800154ea  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800154ef  call    ??0Failure@BILayer@Broker@@QEAA@J@Z; Broker::BILayer::Failure::Failure(long)
0x1800154f4  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x1800154fb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180015500  call    _CxxThrowException_0
0x180015506  mov     edx, 0C000000Dh; int
0x18001550b  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180015510  call    ??0Failure@BILayer@Broker@@QEAA@J@Z; Broker::BILayer::Failure::Failure(long)
0x180015515  lea     rdx, _TI3?AUFailure@BILayer@Broker@@; pThrowInfo
0x18001551c  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180015521  call    _CxxThrowException_0
```
