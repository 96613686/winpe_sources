# FlowEstablishedClassifyFn

- ea: `0x140004a84`
- end: `0x140004e4e`
- name: `FlowEstablishedClassifyFn`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400063e0`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x1400030dc`
- `0x140004a84`
- `0x140005610`
- `0x140006570`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140004ca2`
- `ntoskrnl!RtlCompareMemory` at `0x140004ca2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e19`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004b22`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004c7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004b22`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004c7d`

## string_xrefs

- `0x140004c2e`: `FlowEstablishedClassifyFn: incoming context`

## pseudocode

```c
void __fastcall FlowEstablishedClassifyFn(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // r9
  __int64 v7; // rcx
  bool v8; // zf
  char v9; // r15
  PCWSTR v10; // rax
  __int64 v11; // rcx
  int v12; // ecx
  char *v13; // rax
  char *v14; // rsi
  char *i; // rbx
  const WCHAR *v16; // rdx
  SIZE_T v17; // rax
  _WORD *v18; // rdx
  __int128 v19; // [rsp+30h] [rbp-89h] BYREF
  int v20; // [rsp+40h] [rbp-79h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v23[4]; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING v24; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+B0h] [rbp-9h] BYREF
  PCWSTR v27; // [rsp+D0h] [rbp+17h]
  int v28; // [rsp+D8h] [rbp+1Fh]
  int v29; // [rsp+DCh] [rbp+23h]

  SourceString = 0;
  v3 = AppIdFromFilter(a2, a2, 17, &SourceString);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v20 = v3;
      *(_QWORD *)&v24.Length = "AppIdFromFilter failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)byte_14000FBD3,
        v4,
        v5,
        (__int64)&v24,
        (__int64)&v20);
    }
    return;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v7 = *(_QWORD *)(a1 + 8);
  v8 = *(_WORD *)a1 == 52;
  memset(v22, 0, 28);
  memset(v23, 0, 28);
  if ( v8 )
  {
    LOWORD(v23[0]) = 2;
    LOWORD(v22[0]) = 2;
    HIDWORD(v22[0]) = _byteswap_ulong(*(_DWORD *)(v7 + 40));
    WORD1(v22[0]) = __ROR2__(*(_WORD *)(v7 + 72), 8);
    HIDWORD(v23[0]) = _byteswap_ulong(*(_DWORD *)(v7 + 104));
  }
  else
  {
    LOWORD(v23[0]) = 23;
    LOWORD(v22[0]) = 23;
    *(_OWORD *)&v22[1] = *(_OWORD *)*(_QWORD *)(v7 + 40);
    WORD1(v22[0]) = __ROR2__(*(_WORD *)(v7 + 72), 8);
    *(_OWORD *)&v23[1] = *(_OWORD *)*(_QWORD *)(v7 + 104);
  }
  WORD1(v23[0]) = __ROR2__(*(_WORD *)(v7 + 120), 8);
  v9 = *(_BYTE *)(v7 + 88);
  if ( (unsigned int)dword_140012050 > 4 )
  {
    v10 = SourceString;
    if ( SourceString )
    {
      v11 = -1;
      do
        ++v11;
      while ( SourceString[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v10 = (PCWSTR)&qword_14000C868;
      v12 = 2;
    }
    v27 = v10;
    v28 = v12;
    v29 = 0;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&dword_14000FE44, 0, 0, 3u, &v26);
  }
  LOBYTE(v6) = v9;
  LogConnectionContextAddressPort("FlowEstablishedClassifyFn: incoming context", v22, v23, v6);
  AcquireSpinLock(&v19, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
  v13 = (char *)RoutePolicyCallout::g_pCalloutContext + 48;
  v14 = (char *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 6);
LABEL_38:
  if ( v14 == v13 )
  {
    if ( (unsigned int)dword_140012050 > 3 )
      tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&byte_14000FE85, 0, 0, 2u, &v26);
    goto LABEL_41;
  }
  for ( i = (char *)*((_QWORD *)v14 + 4); ; i = *(char **)i )
  {
    if ( i == v14 + 32 )
    {
      v14 = *(char **)v14;
      v13 = (char *)RoutePolicyCallout::g_pCalloutContext + 48;
      goto LABEL_38;
    }
    v16 = (const WCHAR *)*((_QWORD *)i + 3);
    v24 = 0;
    RtlInitUnicodeString(&v24, v16);
    if ( v24.Length == DestinationString.Length )
    {
      v17 = RtlCompareMemory(v24.Buffer, DestinationString.Buffer, v24.Length);
      if ( v24.Length == v17 && *((_WORD *)i + 46) == LOWORD(v22[0]) )
      {
        if ( LOWORD(v22[0]) != 2 )
        {
          v18 = i + 94;
          goto LABEL_29;
        }
        if ( *((_DWORD *)i + 17) == HIDWORD(v22[0])
          && *((_WORD *)i + 33) == WORD1(v22[0])
          && *((_DWORD *)i + 24) == HIDWORD(v23[0]) )
        {
          v18 = i + 94;
          if ( *((_WORD *)i + 47) == WORD1(v23[0]) )
            break;
        }
      }
    }
LABEL_35:
    ;
  }
  if ( i[130] == v9 )
    goto LABEL_25;
LABEL_29:
  if ( LOWORD(v22[0]) != 23
    || *(_OWORD *)(i + 72) != *(_OWORD *)&v22[1]
    || *((_WORD *)i + 33) != WORD1(v22[0])
    || *(_OWORD *)(i + 100) != *(_OWORD *)&v23[1]
    || *v18 != WORD1(v23[0])
    || i[130] != v9 )
  {
    goto LABEL_35;
  }
LABEL_25:
  if ( (unsigned int)dword_140012050 > 4 )
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&word_14000EA72, 0, 0, 2u, &v26);
  StopTimerWaitFlowEstablish(i);
LABEL_41:
  if ( (_QWORD)v19 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v19);
  ExFreePoolWithTag((PVOID)SourceString, 0x64667072u);
}

```

## disassembly

```asm
0x140004a84  mov     [rsp-8+arg_10], rbx
0x140004a89  mov     [rsp-8+arg_18], rsi
0x140004a8e  push    rbp
0x140004a8f  push    rdi
0x140004a90  push    r12
0x140004a92  push    r14
0x140004a94  push    r15
0x140004a96  lea     rbp, [rsp-37h]
0x140004a9b  sub     rsp, 0F0h
0x140004aa2  mov     rax, cs:__security_cookie
0x140004aa9  xor     rax, rsp
0x140004aac  mov     [rbp+57h+var_30], rax
0x140004ab0  xor     r12d, r12d
0x140004ab3  lea     r9, [rbp+57h+SourceString]
0x140004ab7  mov     rbx, rcx
0x140004aba  mov     [rbp+57h+SourceString], r12
0x140004abe  mov     rcx, rdx
0x140004ac1  lea     r8d, [r12+11h]
0x140004ac6  call    AppIdFromFilter
0x140004acb  test    eax, eax
0x140004acd  jns     short loc_140004B13
0x140004acf  mov     ecx, cs:dword_140012050
0x140004ad5  lea     edi, [r12+2]
0x140004ada  cmp     ecx, edi
0x140004adc  jbe     loc_140004E25
0x140004ae2  mov     [rbp+57h+var_D0], eax
0x140004ae5  lea     rdx, byte_14000FBD3
0x140004aec  lea     rax, aAppidfromfilte; "AppIdFromFilter failed"
0x140004af3  mov     qword ptr [rbp+57h+var_80.Length], rax
0x140004af7  lea     rax, [rbp+57h+var_D0]
0x140004afb  mov     [rsp+110h+var_E8], rax
0x140004b00  lea     rax, [rbp+57h+var_80]
0x140004b04  mov     qword ptr [rsp+110h+var_F0], rax
0x140004b09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140004b0e  jmp     loc_140004E25
0x140004b13  mov     rdx, [rbp+57h+SourceString]; SourceString
0x140004b17  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004b1b  xorps   xmm0, xmm0
0x140004b1e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140004b22  call    cs:__imp_RtlInitUnicodeString
0x140004b29  nop     dword ptr [rax+rax+00h]
0x140004b2e  mov     rcx, [rbx+8]
0x140004b32  xor     eax, eax
0x140004b34  cmp     word ptr [rbx], 34h ; '4'
0x140004b38  xorps   xmm0, xmm0
0x140004b3b  xorps   xmm1, xmm1
0x140004b3e  mov     eax, 17h
0x140004b43  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x140004b47  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x140004b4b  lea     edi, [rax-15h]
0x140004b4e  movups  xmmword ptr [rbp+57h+var_C0+0Ch], xmm0
0x140004b52  movups  xmmword ptr [rbp+57h+var_A0+0Ch], xmm1
0x140004b56  jnz     short loc_140004B7E
0x140004b58  mov     word ptr [rbp+57h+var_A0], di
0x140004b5c  mov     word ptr [rbp+57h+var_C0], di
0x140004b60  mov     eax, [rcx+28h]
0x140004b63  bswap   eax
0x140004b65  mov     dword ptr [rbp+57h+var_C0+4], eax
0x140004b68  movzx   eax, word ptr [rcx+48h]
0x140004b6c  ror     ax, 8
0x140004b70  mov     word ptr [rbp+57h+var_C0+2], ax
0x140004b74  mov     eax, [rcx+68h]
0x140004b77  bswap   eax
0x140004b79  mov     dword ptr [rbp+57h+var_A0+4], eax
0x140004b7c  jmp     short loc_140004BAA
0x140004b7e  mov     word ptr [rbp+57h+var_A0], ax
0x140004b82  mov     word ptr [rbp+57h+var_C0], ax
0x140004b86  mov     rax, [rcx+28h]
0x140004b8a  movups  xmm0, xmmword ptr [rax]
0x140004b8d  movdqu  xmmword ptr [rbp+57h+var_C0+8], xmm0
0x140004b92  movzx   eax, word ptr [rcx+48h]
0x140004b96  ror     ax, 8
0x140004b9a  mov     word ptr [rbp+57h+var_C0+2], ax
0x140004b9e  mov     rax, [rcx+68h]
0x140004ba2  movups  xmm0, xmmword ptr [rax]
0x140004ba5  movdqu  xmmword ptr [rbp+57h+var_A0+8], xmm0
0x140004baa  movzx   eax, word ptr [rcx+78h]
0x140004bae  ror     ax, 8
0x140004bb2  mov     word ptr [rbp+57h+var_A0+2], ax
0x140004bb6  mov     eax, cs:dword_140012050
0x140004bbc  mov     r15b, [rcx+58h]
0x140004bc0  cmp     eax, 4
0x140004bc3  jbe     short loc_140004C23
0x140004bc5  mov     rax, [rbp+57h+SourceString]
0x140004bc9  test    rax, rax
0x140004bcc  jz      short loc_140004BE5
0x140004bce  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004bd2  inc     rcx
0x140004bd5  cmp     [rax+rcx*2], r12w
0x140004bda  jnz     short loc_140004BD2
0x140004bdc  lea     ecx, ds:2[rcx*2]
0x140004be3  jmp     short loc_140004BEE
0x140004be5  lea     rax, qword_14000C868
0x140004bec  mov     ecx, edi
0x140004bee  mov     [rbp+57h+var_40], rax
0x140004bf2  lea     rdx, dword_14000FE44; int
0x140004bf9  lea     rax, [rbp+57h+var_60]
0x140004bfd  mov     [rbp+57h+var_38], ecx
0x140004c00  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140004c05  lea     rcx, dword_140012050; int
0x140004c0c  xor     r9d, r9d; int
0x140004c0f  mov     [rsp+110h+var_F0], 3; ULONG
0x140004c17  xor     r8d, r8d; int
0x140004c1a  mov     [rbp+57h+var_34], r12d
0x140004c1e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004c23  mov     r9b, r15b
0x140004c26  lea     r8, [rbp+57h+var_A0]
0x140004c2a  lea     rdx, [rbp+57h+var_C0]
0x140004c2e  lea     rcx, aFlowestablishe; "FlowEstablishedClassifyFn: incoming con"...
0x140004c35  call    LogConnectionContextAddressPort
0x140004c3a  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004c41  lea     rcx, [rsp+110h+var_E0]
0x140004c46  add     rdx, 28h ; '('
0x140004c4a  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140004c4f  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004c56  add     rax, 30h ; '0'
0x140004c5a  mov     rsi, [rax]
0x140004c5d  jmp     loc_140004DBA
0x140004c62  lea     r14, [rsi+20h]
0x140004c66  mov     rbx, [r14]
0x140004c69  jmp     loc_140004DA3
0x140004c6e  mov     rdx, [rbx+18h]; SourceString
0x140004c72  lea     rcx, [rbp+57h+var_80]; DestinationString
0x140004c76  xorps   xmm0, xmm0
0x140004c79  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x140004c7d  call    cs:__imp_RtlInitUnicodeString
0x140004c84  nop     dword ptr [rax+rax+00h]
0x140004c89  movzx   eax, [rbp+57h+var_80.Length]
0x140004c8d  cmp     ax, [rbp+57h+DestinationString.Length]
0x140004c91  jnz     loc_140004DA0
0x140004c97  mov     rdx, [rbp+57h+DestinationString.Buffer]; Source2
0x140004c9b  mov     r8d, eax; Length
0x140004c9e  mov     rcx, [rbp+57h+var_80.Buffer]; Source1
0x140004ca2  call    cs:__imp_RtlCompareMemory
0x140004ca9  nop     dword ptr [rax+rax+00h]
0x140004cae  movzx   ecx, [rbp+57h+var_80.Length]
0x140004cb2  cmp     rcx, rax
0x140004cb5  jnz     loc_140004DA0
0x140004cbb  movzx   ecx, word ptr [rbp+57h+var_C0]
0x140004cbf  cmp     [rbx+5Ch], cx
0x140004cc3  jnz     loc_140004DA0
0x140004cc9  movzx   r8d, word ptr [rbp+57h+var_C0+2]
0x140004cce  movzx   r9d, word ptr [rbp+57h+var_A0+2]
0x140004cd3  cmp     di, cx
0x140004cd6  jnz     short loc_140004D50
0x140004cd8  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x140004cdb  cmp     [rbx+44h], eax
0x140004cde  jnz     loc_140004DA0
0x140004ce4  cmp     [rbx+42h], r8w
0x140004ce9  jnz     loc_140004DA0
0x140004cef  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x140004cf2  cmp     [rbx+60h], eax
0x140004cf5  jnz     loc_140004DA0
0x140004cfb  lea     rdx, [rbx+5Eh]
0x140004cff  cmp     [rdx], r9w
0x140004d03  jnz     loc_140004DA0
0x140004d09  cmp     [rbx+82h], r15b
0x140004d10  jnz     short loc_140004D54
0x140004d12  mov     eax, cs:dword_140012050
0x140004d18  cmp     eax, 4
0x140004d1b  jbe     short loc_140004D43
0x140004d1d  lea     rax, [rbp+57h+var_60]
0x140004d21  xor     r9d, r9d; int
0x140004d24  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140004d29  lea     rdx, word_14000EA72; int
0x140004d30  xor     r8d, r8d; int
0x140004d33  mov     [rsp+110h+var_F0], edi; ULONG
0x140004d37  lea     rcx, dword_140012050; int
0x140004d3e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004d43  mov     rcx, rbx
0x140004d46  call    StopTimerWaitFlowEstablish
0x140004d4b  jmp     loc_140004DF4
0x140004d50  lea     rdx, [rbx+5Eh]
0x140004d54  mov     eax, 17h
0x140004d59  cmp     ax, cx
0x140004d5c  jnz     short loc_140004DA0
0x140004d5e  mov     rax, [rbx+48h]
0x140004d62  cmp     rax, qword ptr [rbp+57h+var_C0+8]
0x140004d66  jnz     short loc_140004DA0
0x140004d68  mov     rax, [rbx+50h]
0x140004d6c  cmp     rax, qword ptr [rbp+57h+var_C0+10h]
0x140004d70  jnz     short loc_140004DA0
0x140004d72  cmp     [rbx+42h], r8w
0x140004d77  jnz     short loc_140004DA0
0x140004d79  mov     rax, [rbx+64h]
0x140004d7d  cmp     rax, qword ptr [rbp+57h+var_A0+8]
0x140004d81  jnz     short loc_140004DA0
0x140004d83  mov     rax, [rbx+6Ch]
0x140004d87  cmp     rax, qword ptr [rbp+57h+var_A0+10h]
0x140004d8b  jnz     short loc_140004DA0
0x140004d8d  cmp     [rdx], r9w
0x140004d91  jnz     short loc_140004DA0
0x140004d93  cmp     [rbx+82h], r15b
0x140004d9a  jz      loc_140004D12
0x140004da0  mov     rbx, [rbx]
0x140004da3  cmp     rbx, r14
0x140004da6  jnz     loc_140004C6E
0x140004dac  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140004db3  mov     rsi, [rsi]
0x140004db6  add     rax, 30h ; '0'
0x140004dba  cmp     rsi, rax
0x140004dbd  jnz     loc_140004C62
0x140004dc3  mov     eax, cs:dword_140012050
0x140004dc9  cmp     eax, 3
0x140004dcc  jbe     short loc_140004DF4
0x140004dce  lea     rax, [rbp+57h+var_60]
0x140004dd2  xor     r9d, r9d; int
0x140004dd5  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x140004dda  lea     rdx, byte_14000FE85; int
0x140004de1  xor     r8d, r8d; int
0x140004de4  mov     [rsp+110h+var_F0], edi; ULONG
0x140004de8  lea     rcx, dword_140012050; int
0x140004def  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004df4  cmp     qword ptr [rsp+110h+var_E0], r12
0x140004df9  jz      short loc_140004E10
0x140004dfb  movaps  xmm0, [rsp+110h+var_E0]
0x140004e00  lea     rcx, [rsp+110h+var_E0]; struct SpinLockAndSavedIrql *
0x140004e05  movdqa  [rsp+110h+var_E0], xmm0
0x140004e0b  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140004e10  mov     rcx, [rbp+57h+SourceString]; P
0x140004e14  mov     edx, 64667072h; Tag
0x140004e19  call    cs:__imp_ExFreePoolWithTag
0x140004e20  nop     dword ptr [rax+rax+00h]
0x140004e25  mov     rcx, [rbp+57h+var_30]
0x140004e29  xor     rcx, rsp; StackCookie
0x140004e2c  call    __security_check_cookie
0x140004e31  lea     r11, [rsp+110h+var_20]
0x140004e39  mov     rbx, [r11+40h]
0x140004e3d  mov     rsi, [r11+48h]
0x140004e41  mov     rsp, r11
0x140004e44  pop     r15
0x140004e46  pop     r14
0x140004e48  pop     r12
0x140004e4a  pop     rdi
0x140004e4b  pop     rbp
0x140004e4c  retn
```
