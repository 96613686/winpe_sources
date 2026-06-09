# ConnectClassifyFn

- ea: `0x1400037a4`
- end: `0x140003da4`
- name: `ConnectClassifyFn`
- size: `1536`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400063e0`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x1400013b0`
- `0x140001aac`
- `0x1400030dc`
- `0x1400037a4`
- `0x140003dac`
- `0x140004e54`
- `0x140005610`
- `0x14000646c`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`
- `0x14000a780`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400039f8`
- `ntoskrnl!RtlCompareMemory` at `0x1400039f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ab0`
- `ntoskrnl!ExAllocatePool2` at `0x140003b9e`
- `ntoskrnl!ExAllocatePool2` at `0x140003b9e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003846`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400039d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003846`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400039d5`

## string_xrefs

- `0x14000397c`: `ConnectClassifyFn: incoming context`

## pseudocode

```c
void __fastcall ConnectClassifyFn(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // r9
  __int64 v7; // rcx
  bool v8; // zf
  __int16 v9; // r12
  __int16 v10; // di
  __int16 v11; // ax
  __int16 v12; // di
  char v13; // r13
  PCWSTR v14; // rax
  __int64 v15; // rcx
  int v16; // ecx
  int Length; // ecx
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rsi
  __int64 *v21; // r15
  __int64 *i; // rbx
  const WCHAR *v23; // rdx
  SIZE_T v24; // rax
  __int16 v25; // r13
  size_t v26; // rax
  __int128 *v27; // r12
  __int64 v28; // r9
  __int64 Pool2; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  _QWORD *v33; // rdi
  size_t v34; // r8
  const unsigned __int16 *v35; // r8
  unsigned __int16 **v36; // rdx
  void *v37; // rcx
  unsigned __int16 **v38; // rdx
  int TimerWaitFlowEstablish; // eax
  __int64 **v40; // rax
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  char v43; // bl
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  int v46; // [rsp+30h] [rbp-D0h] BYREF
  size_t Size; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING v48; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR SourceString[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v50; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD Src[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v52[4]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+E0h] [rbp-20h] BYREF
  int *v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  size_t *p_Size; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  _BYTE v60[28]; // [rsp+120h] [rbp+20h] BYREF
  PCWSTR v61; // [rsp+140h] [rbp+40h]
  int v62; // [rsp+148h] [rbp+48h]
  int v63; // [rsp+14Ch] [rbp+4Ch]

  SourceString[0] = 0;
  v3 = AppIdFromFilter(a2, a2, 11, SourceString);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v46 = v3;
      Size = (size_t)"AppIdFromFilter failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)byte_14000FA45,
        v4,
        v5,
        (__int64)&Size,
        (__int64)&v46);
    }
    return;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString[0]);
  v7 = *(_QWORD *)(a1 + 8);
  v8 = *(_WORD *)a1 == 66;
  memset(Src, 0, 28);
  memset(v52, 0, 28);
  if ( v8 )
  {
    v9 = 2;
    DWORD1(Src[0]) = _byteswap_ulong(*(_DWORD *)(v7 + 104));
    WORD1(Src[0]) = __ROR2__(*(_WORD *)(v7 + 136), 8);
    LOWORD(Src[0]) = 2;
    HIDWORD(v52[0]) = _byteswap_ulong(*(_DWORD *)(v7 + 40));
    v10 = *(_WORD *)(v7 + 72);
    LOWORD(v52[0]) = 2;
  }
  else
  {
    v9 = 23;
    *(_OWORD *)((char *)Src + 8) = *(_OWORD *)*(_QWORD *)(v7 + 104);
    v11 = *(_WORD *)(v7 + 136);
    LOWORD(Src[0]) = 23;
    WORD1(Src[0]) = __ROR2__(v11, 8);
    *(_OWORD *)&v52[1] = *(_OWORD *)*(_QWORD *)(v7 + 40);
    v10 = *(_WORD *)(v7 + 72);
    LOWORD(v52[0]) = 23;
  }
  v12 = __ROR2__(v10, 8);
  WORD1(v52[0]) = v12;
  v13 = *(_BYTE *)(v7 + 88);
  LOBYTE(v46) = v13;
  LOWORD(Src[0]) = v9;
  if ( (unsigned int)dword_140012050 > 4 )
  {
    v14 = SourceString[0];
    if ( SourceString[0] )
    {
      v15 = -1;
      do
        ++v15;
      while ( SourceString[0][v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v14 = (PCWSTR)&qword_14000C868;
      v16 = 2;
    }
    v61 = v14;
    v62 = v16;
    v63 = 0;
    tlgWriteTransfer_EtwWriteTransfer(
      (int)&dword_140012050,
      (int)&word_14000ECE6,
      0,
      0,
      3u,
      (PEVENT_DATA_DESCRIPTOR)v60);
  }
  LOBYTE(v6) = v13;
  LogConnectionContextAddressPort("ConnectClassifyFn: incoming context", v52, Src, v6);
  AcquireSpinLock(&v48, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
  v20 = (_QWORD *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 6);
  if ( v20 == (_QWORD *)((char *)RoutePolicyCallout::g_pCalloutContext + 48) )
  {
LABEL_26:
    if ( (unsigned int)dword_140012050 > 4 )
    {
      Size = (size_t)"Not match to any existing connection contexts";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        Length,
        (unsigned int)&word_14000E996,
        v18,
        v19,
        (__int64)&Size);
    }
    if ( *(_QWORD *)&v48.Length )
    {
      v50 = v48;
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v50);
    }
    goto LABEL_30;
  }
LABEL_15:
  v21 = v20 + 4;
  for ( i = (__int64 *)v20[4]; ; i = (__int64 *)*i )
  {
    if ( i == v21 )
    {
      v20 = (_QWORD *)*v20;
      if ( v20 != (_QWORD *)((char *)RoutePolicyCallout::g_pCalloutContext + 48) )
        goto LABEL_15;
      goto LABEL_26;
    }
    if ( *((_WORD *)i + 28) == v9 )
    {
      v23 = (const WCHAR *)i[3];
      v50 = 0;
      RtlInitUnicodeString(&v50, v23);
      if ( v50.Length == DestinationString.Length )
      {
        v24 = RtlCompareMemory(v50.Buffer, DestinationString.Buffer, v50.Length);
        Length = v50.Length;
        if ( v50.Length == v24 && *((_BYTE *)i + 130) == v13 )
          break;
      }
    }
LABEL_23:
    ;
  }
  v25 = *((_WORD *)i + 33);
  if ( v25 && v25 != v12 )
  {
    v13 = v46;
    goto LABEL_23;
  }
  v8 = v9 == 2;
  v26 = 16;
  v27 = (__int128 *)((char *)i + 92);
  if ( !v8 )
    v26 = 28;
  Size = v26;
  if ( !*(_WORD *)v27 )
  {
    memmove((char *)i + 92, Src, (unsigned int)v26);
    if ( (unsigned int)dword_140012050 > 4 )
    {
      Size = i[15];
      LOWORD(v46) = v25;
      p_Size = &Size;
      v59 = 8;
      v56 = &v46;
      v57 = 2;
      tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&byte_14000F81D, 0, 0, 4u, &v55);
    }
    if ( !v25 )
      *((_WORD *)i + 33) = v12;
LABEL_56:
    v41 = *((_OWORD *)i + 4);
    v42 = *(_OWORD *)((char *)i + 76);
    v43 = *((_BYTE *)i + 130);
    *(_OWORD *)v60 = v41;
    v44 = *v27;
    *(_OWORD *)&v60[12] = v42;
    v45 = *(__int128 *)((char *)v27 + 12);
    v54[0] = v44;
    *(_OWORD *)((char *)v54 + 12) = v45;
    if ( *(_QWORD *)&v48.Length )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v48);
    LOBYTE(v28) = v43;
    LogConnectionContextAddressPort(
      "ConnectClassifyFn-Successfully correlated CONNECT_REDIRECT to an existing connection context",
      v60,
      v54,
      v28);
    goto LABEL_30;
  }
  Pool2 = ExAllocatePool2(64, 136, 1684435058);
  v33 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    v34 = Size;
    *(_OWORD *)Pool2 = *(_OWORD *)i;
    *(_OWORD *)(Pool2 + 16) = *((_OWORD *)i + 1);
    *(_OWORD *)(Pool2 + 32) = *((_OWORD *)i + 2);
    *(_OWORD *)(Pool2 + 48) = *((_OWORD *)i + 3);
    *(_OWORD *)(Pool2 + 64) = *((_OWORD *)i + 4);
    *(_OWORD *)(Pool2 + 80) = *((_OWORD *)i + 5);
    *(_OWORD *)(Pool2 + 96) = *((_OWORD *)i + 6);
    *(_OWORD *)(Pool2 + 112) = *((_OWORD *)i + 7);
    *(_QWORD *)(Pool2 + 128) = i[16];
    memmove((void *)(Pool2 + 92), Src, v34);
    v36 = (unsigned __int16 **)i[3];
    if ( v36 && RoutePolicyCache::AllocateAndCopyStringParameter((RoutePolicyCache *)(v33 + 3), v36, v35) < 0
      || (v38 = (unsigned __int16 **)i[4]) != 0
      && RoutePolicyCache::AllocateAndCopyStringParameter((RoutePolicyCache *)(v33 + 4), v38, v35) < 0 )
    {
      v37 = v33;
    }
    else
    {
      TimerWaitFlowEstablish = CreateTimerWaitFlowEstablish(v33);
      v37 = v33;
      if ( TimerWaitFlowEstablish >= 0 )
      {
        StartTimerWaitFlowEstablish(v33);
        v40 = (__int64 **)v20[5];
        if ( *v40 != v21 )
          __fastfail(3u);
        *v33 = v21;
        v33[1] = v40;
        *v40 = v33;
        v20[5] = v33;
        if ( (unsigned int)dword_140012050 > 4 )
        {
          Size = v33[15];
          LOWORD(v46) = v25;
          p_Size = &Size;
          v59 = 8;
          v56 = &v46;
          v57 = 2;
          tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&word_14000FC86, 0, 0, 4u, &v55);
        }
        goto LABEL_56;
      }
    }
    FreeConnectionContext(v37);
  }
  else if ( (unsigned int)dword_140012050 > 2 )
  {
    v46 = -1073741670;
    Size = (size_t)"Failed to allocate CONNECTION_CONTEXT";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_14000F335,
      v31,
      v32,
      (__int64)&Size,
      (__int64)&v46);
  }
  if ( *(_QWORD *)&v48.Length )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v48);
LABEL_30:
  ExFreePoolWithTag((PVOID)SourceString[0], 0x64667072u);
}

```

## disassembly

```asm
0x1400037a4  mov     [rsp-8+arg_10], rbx
0x1400037a9  push    rbp
0x1400037aa  push    rsi
0x1400037ab  push    rdi
0x1400037ac  push    r12
0x1400037ae  push    r13
0x1400037b0  push    r14
0x1400037b2  push    r15
0x1400037b4  lea     rbp, [rsp-60h]
0x1400037b9  sub     rsp, 160h
0x1400037c0  mov     rax, cs:__security_cookie
0x1400037c7  xor     rax, rsp
0x1400037ca  mov     [rbp+90h+var_40], rax
0x1400037ce  xor     r15d, r15d
0x1400037d1  lea     r9, [rsp+190h+SourceString]
0x1400037d6  mov     rbx, rcx
0x1400037d9  mov     [rsp+190h+SourceString], r15
0x1400037de  mov     rcx, rdx
0x1400037e1  lea     r8d, [r15+0Bh]
0x1400037e5  call    AppIdFromFilter
0x1400037ea  test    eax, eax
0x1400037ec  jns     short loc_140003836
0x1400037ee  mov     ecx, cs:dword_140012050
0x1400037f4  lea     r14d, [r15+2]
0x1400037f8  cmp     ecx, r14d
0x1400037fb  jbe     loc_140003ABC
0x140003801  mov     [rsp+190h+var_160], eax
0x140003805  lea     rdx, byte_14000FA45
0x14000380c  lea     rax, aAppidfromfilte; "AppIdFromFilter failed"
0x140003813  mov     [rsp+190h+Size], rax
0x140003818  lea     rax, [rsp+190h+var_160]
0x14000381d  mov     [rsp+190h+var_168], rax
0x140003822  lea     rax, [rsp+190h+Size]
0x140003827  mov     qword ptr [rsp+190h+var_170], rax
0x14000382c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003831  jmp     loc_140003ABC
0x140003836  mov     rdx, [rsp+190h+SourceString]; SourceString
0x14000383b  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x14000383f  xorps   xmm0, xmm0
0x140003842  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x140003846  call    cs:__imp_RtlInitUnicodeString
0x14000384d  nop     dword ptr [rax+rax+00h]
0x140003852  mov     rcx, [rbx+8]
0x140003856  xor     eax, eax
0x140003858  cmp     word ptr [rbx], 42h ; 'B'
0x14000385c  xorps   xmm0, xmm0
0x14000385f  xorps   xmm1, xmm1
0x140003862  movups  [rsp+190h+Src], xmm0
0x140003867  lea     r14d, [rax+2]
0x14000386b  movups  xmmword ptr [rbp+90h+var_100], xmm1
0x14000386f  movups  [rsp+190h+Src+0Ch], xmm0
0x140003874  movups  xmmword ptr [rbp+90h+var_100+0Ch], xmm1
0x140003878  jnz     short loc_1400038B0
0x14000387a  mov     eax, [rcx+68h]
0x14000387d  movzx   r12d, r14w
0x140003881  bswap   eax
0x140003883  mov     dword ptr [rsp+190h+Src+4], eax
0x140003887  movzx   eax, word ptr [rcx+88h]
0x14000388e  ror     ax, 8
0x140003892  mov     word ptr [rsp+190h+Src+2], ax
0x140003897  mov     word ptr [rsp+190h+Src], r14w
0x14000389d  mov     eax, [rcx+28h]
0x1400038a0  bswap   eax
0x1400038a2  mov     dword ptr [rbp+90h+var_100+4], eax
0x1400038a5  movzx   edi, word ptr [rcx+48h]
0x1400038a9  mov     word ptr [rbp+90h+var_100], r14w
0x1400038ae  jmp     short loc_1400038EE
0x1400038b0  mov     rax, [rcx+68h]
0x1400038b4  mov     r12d, 17h
0x1400038ba  movups  xmm0, xmmword ptr [rax]
0x1400038bd  movdqu  [rsp+190h+Src+8], xmm0
0x1400038c3  movzx   eax, word ptr [rcx+88h]
0x1400038ca  mov     word ptr [rsp+190h+Src], r12w
0x1400038d0  ror     ax, 8
0x1400038d4  mov     word ptr [rsp+190h+Src+2], ax
0x1400038d9  mov     rax, [rcx+28h]
0x1400038dd  movups  xmm0, xmmword ptr [rax]
0x1400038e0  movdqu  xmmword ptr [rbp+90h+var_100+8], xmm0
0x1400038e5  movzx   edi, word ptr [rcx+48h]
0x1400038e9  mov     word ptr [rbp+90h+var_100], r12w
0x1400038ee  mov     eax, cs:dword_140012050
0x1400038f4  ror     di, 8
0x1400038f8  mov     word ptr [rbp+90h+var_100+2], di
0x1400038fc  mov     r13b, [rcx+58h]
0x140003900  mov     byte ptr [rsp+190h+var_160], r13b
0x140003905  mov     word ptr [rsp+190h+Src], r12w
0x14000390b  cmp     eax, 4
0x14000390e  jbe     short loc_140003970
0x140003910  mov     rax, [rsp+190h+SourceString]
0x140003915  test    rax, rax
0x140003918  jz      short loc_140003931
0x14000391a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000391e  inc     rcx
0x140003921  cmp     [rax+rcx*2], r15w
0x140003926  jnz     short loc_14000391E
0x140003928  lea     ecx, ds:2[rcx*2]
0x14000392f  jmp     short loc_14000393B
0x140003931  lea     rax, qword_14000C868
0x140003938  mov     ecx, r14d
0x14000393b  mov     [rbp+90h+var_50], rax
0x14000393f  lea     rdx, word_14000ECE6; int
0x140003946  lea     rax, [rbp+90h+var_70]
0x14000394a  mov     [rbp+90h+var_48], ecx
0x14000394d  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x140003952  lea     rcx, dword_140012050; int
0x140003959  xor     r9d, r9d; int
0x14000395c  mov     [rsp+190h+var_170], 3; ULONG
0x140003964  xor     r8d, r8d; int
0x140003967  mov     [rbp+90h+var_44], r15d
0x14000396b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003970  mov     r9b, r13b
0x140003973  lea     r8, [rsp+190h+Src]
0x140003978  lea     rdx, [rbp+90h+var_100]
0x14000397c  lea     rcx, aConnectclassif; "ConnectClassifyFn: incoming context"
0x140003983  call    LogConnectionContextAddressPort
0x140003988  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x14000398f  lea     rcx, [rsp+190h+var_150]
0x140003994  add     rdx, 28h ; '('
0x140003998  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x14000399d  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400039a4  add     rax, 30h ; '0'
0x1400039a8  mov     rsi, [rax]
0x1400039ab  cmp     rsi, rax
0x1400039ae  jz      loc_140003A5D
0x1400039b4  lea     r15, [rsi+20h]
0x1400039b8  mov     rbx, [r15]
0x1400039bb  jmp     short loc_140003A3A
0x1400039bd  cmp     [rbx+38h], r12w
0x1400039c2  jnz     short loc_140003A37
0x1400039c4  mov     rdx, [rbx+18h]; SourceString
0x1400039c8  lea     rcx, [rsp+190h+var_130]; DestinationString
0x1400039cd  xorps   xmm0, xmm0
0x1400039d0  movups  xmmword ptr [rsp+190h+var_130.Length], xmm0
0x1400039d5  call    cs:__imp_RtlInitUnicodeString
0x1400039dc  nop     dword ptr [rax+rax+00h]
0x1400039e1  movzx   eax, [rsp+190h+var_130.Length]
0x1400039e6  cmp     ax, [rbp+90h+DestinationString.Length]
0x1400039ea  jnz     short loc_140003A37
0x1400039ec  mov     rdx, [rbp+90h+DestinationString.Buffer]; Source2
0x1400039f0  mov     r8d, eax; Length
0x1400039f3  mov     rcx, [rsp+190h+var_130.Buffer]; Source1
0x1400039f8  call    cs:__imp_RtlCompareMemory
0x1400039ff  nop     dword ptr [rax+rax+00h]
0x140003a04  movzx   ecx, [rsp+190h+var_130.Length]
0x140003a09  cmp     rcx, rax
0x140003a0c  jnz     short loc_140003A37
0x140003a0e  cmp     [rbx+82h], r13b
0x140003a15  jnz     short loc_140003A37
0x140003a17  movzx   r13d, word ptr [rbx+42h]
0x140003a1c  xor     edx, edx
0x140003a1e  test    r13w, r13w
0x140003a22  jz      loc_140003AE4
0x140003a28  cmp     r13w, di
0x140003a2c  jz      loc_140003AE4
0x140003a32  mov     r13b, byte ptr [rsp+190h+var_160]
0x140003a37  mov     rbx, [rbx]
0x140003a3a  cmp     rbx, r15
0x140003a3d  jnz     loc_1400039BD
0x140003a43  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003a4a  mov     rsi, [rsi]
0x140003a4d  add     rax, 30h ; '0'
0x140003a51  cmp     rsi, rax
0x140003a54  jnz     loc_1400039B4
0x140003a5a  xor     r15d, r15d
0x140003a5d  mov     eax, cs:dword_140012050
0x140003a63  cmp     eax, 4
0x140003a66  jbe     short loc_140003A8A
0x140003a68  lea     rax, aNotMatchToAnyE; "Not match to any existing connection co"...
0x140003a6f  mov     [rsp+190h+Size], rax
0x140003a74  lea     rdx, word_14000E996
0x140003a7b  lea     rax, [rsp+190h+Size]
0x140003a80  mov     qword ptr [rsp+190h+var_170], rax
0x140003a85  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140003a8a  cmp     qword ptr [rsp+190h+var_150], r15
0x140003a8f  jz      short loc_140003AA6
0x140003a91  movaps  xmm0, [rsp+190h+var_150]
0x140003a96  lea     rcx, [rsp+190h+var_130]; struct SpinLockAndSavedIrql *
0x140003a9b  movdqa  xmmword ptr [rsp+190h+var_130.Length], xmm0
0x140003aa1  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140003aa6  mov     edx, 64667072h; Tag
0x140003aab  mov     rcx, [rsp+190h+SourceString]; P
0x140003ab0  call    cs:__imp_ExFreePoolWithTag
0x140003ab7  nop     dword ptr [rax+rax+00h]
0x140003abc  mov     rcx, [rbp+90h+var_40]
0x140003ac0  xor     rcx, rsp; StackCookie
0x140003ac3  call    __security_check_cookie
0x140003ac8  mov     rbx, [rsp+190h+arg_10]
0x140003ad0  add     rsp, 160h
0x140003ad7  pop     r15
0x140003ad9  pop     r14
0x140003adb  pop     r13
0x140003add  pop     r12
0x140003adf  pop     rdi
0x140003ae0  pop     rsi
0x140003ae1  pop     rbp
0x140003ae2  retn
0x140003ae4  cmp     r12w, r14w
0x140003ae8  mov     eax, 10h
0x140003aed  lea     r12, [rbx+5Ch]
0x140003af1  mov     esi, 64667072h
0x140003af6  lea     ecx, [rax+0Ch]
0x140003af9  cmovnz  eax, ecx
0x140003afc  mov     [rsp+190h+Size], rax
0x140003b01  cmp     [r12], dx
0x140003b06  jnz     loc_140003B93
0x140003b0c  mov     r8d, eax; Size
0x140003b0f  lea     rdx, [rsp+190h+Src]; Src
0x140003b14  mov     rcx, r12; void *
0x140003b17  call    memmove
0x140003b1c  mov     eax, cs:dword_140012050
0x140003b22  cmp     eax, 4
0x140003b25  jbe     short loc_140003B7E
0x140003b27  mov     rax, [rbx+78h]
0x140003b2b  lea     rdx, byte_14000F81D; int
0x140003b32  mov     [rsp+190h+Size], rax
0x140003b37  lea     rcx, dword_140012050; int
0x140003b3e  lea     rax, [rsp+190h+Size]
0x140003b43  mov     word ptr [rsp+190h+var_160], r13w
0x140003b49  mov     [rbp+90h+var_80], rax
0x140003b4d  xor     r9d, r9d; int
0x140003b50  lea     rax, [rsp+190h+var_160]
0x140003b55  mov     [rbp+90h+var_78], 8
0x140003b5d  mov     [rbp+90h+var_90], rax
0x140003b61  xor     r8d, r8d; int
0x140003b64  lea     rax, [rbp+90h+var_B0]
0x140003b68  mov     [rbp+90h+var_88], r14
0x140003b6c  mov     [rsp+190h+var_168], rax; PEVENT_DATA_DESCRIPTOR
0x140003b71  mov     [rsp+190h+var_170], 4; ULONG
0x140003b79  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003b7e  xor     ecx, ecx
0x140003b80  test    r13w, r13w
0x140003b84  jnz     loc_140003D43
0x140003b8a  mov     [rbx+42h], di
0x140003b8e  jmp     loc_140003D43
0x140003b93  mov     edx, 88h
0x140003b98  mov     r8d, esi
0x140003b9b  lea     ecx, [rdx-48h]
0x140003b9e  call    cs:__imp_ExAllocatePool2
0x140003ba5  nop     dword ptr [rax+rax+00h]
0x140003baa  mov     rdi, rax
0x140003bad  test    rax, rax
0x140003bb0  jnz     short loc_140003C15
0x140003bb2  mov     eax, cs:dword_140012050
0x140003bb8  cmp     eax, r14d
0x140003bbb  jbe     short loc_140003BF1
0x140003bbd  lea     rax, aFailedToAlloca_8; "Failed to allocate CONNECTION_CONTEXT"
0x140003bc4  mov     [rsp+190h+var_160], 0C000009Ah
0x140003bcc  mov     [rsp+190h+Size], rax
0x140003bd1  lea     rdx, byte_14000F335
0x140003bd8  lea     rax, [rsp+190h+var_160]
0x140003bdd  mov     [rsp+190h+var_168], rax
0x140003be2  lea     rax, [rsp+190h+Size]
0x140003be7  mov     qword ptr [rsp+190h+var_170], rax
0x140003bec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003bf1  cmp     qword ptr [rsp+190h+var_150], 0
0x140003bf7  jz      short loc_140003C0E
0x140003bf9  movaps  xmm0, [rsp+190h+var_150]
0x140003bfe  lea     rcx, [rsp+190h+var_150]; struct SpinLockAndSavedIrql *
0x140003c03  movdqa  [rsp+190h+var_150], xmm0
0x140003c09  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140003c0e  mov     edx, esi
0x140003c10  jmp     loc_140003AAB
0x140003c15  movups  xmm0, xmmword ptr [rbx]
0x140003c18  mov     r8, [rsp+190h+Size]; Size
0x140003c1d  lea     rcx, [rdi+5Ch]; void *
0x140003c21  lea     rdx, [rsp+190h+Src]; Src
0x140003c26  movups  xmmword ptr [rax], xmm0
0x140003c29  movups  xmm1, xmmword ptr [rbx+10h]
0x140003c2d  movups  xmmword ptr [rax+10h], xmm1
0x140003c31  movups  xmm0, xmmword ptr [rbx+20h]
0x140003c35  movups  xmmword ptr [rax+20h], xmm0
0x140003c39  movups  xmm1, xmmword ptr [rbx+30h]
0x140003c3d  movups  xmmword ptr [rax+30h], xmm1
0x140003c41  movups  xmm0, xmmword ptr [rbx+40h]
0x140003c45  movups  xmmword ptr [rax+40h], xmm0
0x140003c49  movups  xmm1, xmmword ptr [rbx+50h]
0x140003c4d  movups  xmmword ptr [rax+50h], xmm1
0x140003c51  movups  xmm0, xmmword ptr [rbx+60h]
0x140003c55  movups  xmmword ptr [rax+60h], xmm0
0x140003c59  movups  xmm1, xmmword ptr [rbx+70h]
0x140003c5d  movups  xmmword ptr [rax+70h], xmm1
0x140003c61  mov     rax, [rbx+80h]
0x140003c68  mov     [rdi+80h], rax
0x140003c6f  call    memmove
0x140003c74  mov     rdx, [rbx+18h]; unsigned __int16 **
0x140003c78  test    rdx, rdx
0x140003c7b  jz      short loc_140003C97
0x140003c7d  lea     rcx, [rdi+18h]; this
0x140003c81  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140003c86  test    eax, eax
0x140003c88  jns     short loc_140003C97
0x140003c8a  mov     rcx, rdi; P
0x140003c8d  call    FreeConnectionContext
0x140003c92  jmp     loc_140003BF1
0x140003c97  mov     rdx, [rbx+20h]; unsigned __int16 **
0x140003c9b  test    rdx, rdx
0x140003c9e  jz      short loc_140003CAD
0x140003ca0  lea     rcx, [rdi+20h]; this
0x140003ca4  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140003ca9  test    eax, eax
  ... truncated ...
```
