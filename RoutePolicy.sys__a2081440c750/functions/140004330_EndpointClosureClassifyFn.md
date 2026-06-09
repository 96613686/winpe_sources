# EndpointClosureClassifyFn

- ea: `0x140004330`
- end: `0x1400047fa`
- name: `EndpointClosureClassifyFn`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400063e0`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x1400013b0`
- `0x140001440`
- `0x1400030dc`
- `0x140004330`
- `0x140005874`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400046be`
- `ntoskrnl!RtlCompareMemory` at `0x1400046be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004628`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004628`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004599`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004674`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004599`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004674`

## string_xrefs

- `0x14000442c`: `No local V6 address incoming`
- `0x14000447b`: `No remote V6 address incoming`

## pseudocode

```c
void __fastcall EndpointClosureClassifyFn(__int64 a1, __int64 a2, int a3, int a4)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rbx
  bool v12; // zf
  __int64 v13; // rax
  __int64 *v14; // rcx
  int v15; // r13d
  __int16 v16; // r15
  __int16 v17; // r14
  char v18; // di
  __int16 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rax
  __int16 v22; // r14
  int v23; // eax
  const wchar_t *v24; // rax
  int Length; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 *i; // rdi
  const char *v29; // rax
  __int16 *v30; // rdx
  __int64 *v31; // rax
  __int64 *v32; // rbx
  char v33; // r12
  __int16 v34; // r13
  SIZE_T v35; // rax
  int v36; // eax
  int v37; // r8d
  int v38; // r9d
  char v39; // [rsp+50h] [rbp-89h]
  char v40; // [rsp+51h] [rbp-88h]
  const char *v41; // [rsp+58h] [rbp-81h] BYREF
  const char *v42; // [rsp+60h] [rbp-79h] BYREF
  __int16 v43; // [rsp+68h] [rbp-71h]
  __int16 v44; // [rsp+6Ah] [rbp-6Fh]
  __int128 v45; // [rsp+70h] [rbp-69h] BYREF
  __int128 v46; // [rsp+80h] [rbp-59h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp-49h] BYREF
  struct _UNICODE_STRING v48; // [rsp+98h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v50[2]; // [rsp+B8h] [rbp-21h] BYREF
  __int128 *v51; // [rsp+D8h] [rbp-1h]
  __int64 v52; // [rsp+E0h] [rbp+7h]

  if ( *(_DWORD *)(a1 + 4) <= 8u )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( (unsigned int)dword_140012050 <= 2 )
      return;
    LODWORD(v41) = -1073741811;
    v9 = "Insufficient value count";
    v10 = &byte_14000ED1F;
    goto LABEL_4;
  }
  v11 = 0;
  v12 = *(_WORD *)a1 == 64;
  v39 = 0;
  v13 = *(_QWORD *)(a1 + 8);
  memset(v50, 0, 28);
  v14 = *(__int64 **)(v13 + 136);
  v15 = 23;
  if ( v12 )
  {
    LOWORD(v50[0].Ptr) = 2;
    if ( v14 )
      v11 = *v14;
    v15 = 2;
    v16 = *(_WORD *)(v13 + 72);
    v17 = *(_WORD *)(v13 + 120);
    LODWORD(v41) = _byteswap_ulong(*(_DWORD *)(v13 + 104));
    v18 = *(_BYTE *)(v13 + 88);
    v19 = __ROR2__(v16, 8);
  }
  else
  {
    LOWORD(v50[0].Ptr) = 23;
    if ( v14 )
      v11 = *v14;
    if ( *(_DWORD *)(v13 + 32) != 11 && (unsigned int)dword_140012050 > 4 )
    {
      v41 = "No local V6 address incoming";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v14,
        (unsigned int)byte_14000F3B9,
        a3,
        a4,
        (__int64)&v41);
    }
    v20 = *(_QWORD *)(a1 + 8);
    v19 = __ROR2__(*(_WORD *)(v20 + 72), 8);
    if ( *(_DWORD *)(v20 + 96) == 11 )
    {
      *(struct _EVENT_DATA_DESCRIPTOR *)&v50[0].Size = *(struct _EVENT_DATA_DESCRIPTOR *)*(_QWORD *)(v20 + 104);
    }
    else
    {
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v41 = "No remote V6 address incoming";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v14,
          (unsigned int)&unk_14000EB48,
          a3,
          a4,
          (__int64)&v41);
      }
      v39 = 1;
    }
    v21 = *(_QWORD *)(a1 + 8);
    v17 = *(_WORD *)(v21 + 120);
    v18 = *(_BYTE *)(v21 + 88);
    LODWORD(v41) = HIDWORD(v50[0].Ptr);
  }
  LODWORD(v42) = v15;
  v40 = v18;
  v22 = __ROR2__(v17, 8);
  SourceString = 0;
  v23 = AppIdFromFilter(a2, a2, 10, &SourceString);
  if ( v23 < 0 )
  {
    v6 = dword_140012050;
    if ( (unsigned int)dword_140012050 <= 2 )
      return;
    LODWORD(v41) = v23;
    v10 = byte_14000FABD;
    v9 = "AppIdFromFilter failed";
LABEL_4:
    v42 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (_DWORD)v10,
      v7,
      v8,
      (__int64)&v42,
      (__int64)&v41);
    return;
  }
  if ( (unsigned int)dword_140012050 > 4 )
  {
    *(_QWORD *)&v46 = SourceString;
    *(_QWORD *)&v48.Length = v11;
    v24 = L"IPv4";
    if ( (_WORD)v15 != 2 )
      v24 = L"IPv6";
    v43 = v22;
    *(_QWORD *)&v45 = v24;
    v44 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      L"IPv6",
      &unk_14000F7B8);
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  AcquireSpinLock(&v46, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
  for ( i = (__int64 *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 6); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)((char *)RoutePolicyCallout::g_pCalloutContext + 48) )
    {
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v29 = "No matching interface";
        v30 = &word_14000F2A6;
        goto LABEL_33;
      }
      goto LABEL_34;
    }
    if ( i[2] == v11 )
      break;
  }
  v31 = i + 4;
  v32 = (__int64 *)i[4];
  while ( v32 != v31 )
  {
    v48 = 0;
    RtlInitUnicodeString(&v48, (PCWSTR)v32[3]);
    if ( (_WORD)v15 == 2 )
    {
      if ( *((_WORD *)v32 + 47) == v22 && *((_DWORD *)v32 + 24) == (_DWORD)v41 )
        goto LABEL_57;
    }
    else if ( (_WORD)v15 == 23
           && *((_WORD *)v32 + 47) == v22
           && (v39
            || *(__int64 *)((char *)v32 + 100) == *(_QWORD *)&v50[0].Size
            && *(__int64 *)((char *)v32 + 108) == v50[1].Ptr) )
    {
LABEL_57:
      v33 = 1;
      goto LABEL_44;
    }
    v33 = 0;
LABEL_44:
    if ( *((_WORD *)v32 + 28) == (_WORD)v15 && v48.Length == DestinationString.Length )
    {
      v34 = *((_WORD *)v32 + 33);
      v35 = RtlCompareMemory(v48.Buffer, DestinationString.Buffer, v48.Length);
      Length = v48.Length;
      if ( v48.Length == v35 && *((_BYTE *)v32 + 130) == v40 && v34 == v19 && v33 )
      {
        if ( (unsigned int)dword_140012050 > 4 )
        {
          *(_QWORD *)&v45 = v32[15];
          v52 = 8;
          v51 = &v45;
          tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&dword_14000FDD4, 0, 0, 3u, v50);
        }
        v36 = PrepareCleanupResourcesWorkItem(i, (struct CONNECTION_CONTEXT *)v32);
        if ( v36 < 0 && (unsigned int)dword_140012050 > 2 )
        {
          LODWORD(v41) = v36;
          *(_QWORD *)&v45 = "Failed to cleanup resources";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_140012050,
            (unsigned int)&unk_14000E9F8,
            v37,
            v38,
            (__int64)&v45,
            (__int64)&v41);
        }
        goto LABEL_34;
      }
      LOWORD(v15) = (_WORD)v42;
    }
    v32 = (__int64 *)*v32;
    v31 = i + 4;
  }
  if ( (unsigned int)dword_140012050 <= 4 )
    goto LABEL_34;
  v29 = "Not match to any existing connection contexts";
  v30 = word_14000FE12;
LABEL_33:
  *(_QWORD *)&v45 = v29;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
    Length,
    (_DWORD)v30,
    v26,
    v27,
    (__int64)&v45);
LABEL_34:
  if ( (_QWORD)v46 )
  {
    v45 = v46;
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v45);
  }
  ExFreePoolWithTag((PVOID)SourceString, 0x64667072u);
}

```

## disassembly

```asm
0x140004330  push    rbp
0x140004332  push    rbx
0x140004333  push    rsi
0x140004334  push    rdi
0x140004335  push    r12
0x140004337  push    r13
0x140004339  push    r14
0x14000433b  push    r15
0x14000433d  lea     rbp, [rsp-1Fh]
0x140004342  sub     rsp, 0F8h
0x140004349  mov     rax, cs:__security_cookie
0x140004350  xor     rax, rsp
0x140004353  mov     [rbp+57h+var_48], rax
0x140004357  cmp     dword ptr [rcx+4], 8
0x14000435b  mov     r12, rdx
0x14000435e  mov     rdi, rcx
0x140004361  ja      short loc_1400043B2
0x140004363  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140004368  mov     eax, cs:dword_140012050
0x14000436e  mov     esi, 2
0x140004373  cmp     eax, esi
0x140004375  jbe     loc_140004634
0x14000437b  mov     dword ptr [rsp+130h+var_D8], 0C000000Dh
0x140004383  lea     rax, aInsufficientVa; "Insufficient value count"
0x14000438a  lea     rdx, byte_14000ED1F
0x140004391  mov     [rbp+57h+var_D0], rax
0x140004395  lea     rax, [rsp+130h+var_D8]
0x14000439a  mov     [rsp+130h+var_108], rax
0x14000439f  lea     rax, [rbp+57h+var_D0]
0x1400043a3  mov     qword ptr [rsp+130h+var_110], rax
0x1400043a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400043ad  jmp     loc_140004634
0x1400043b2  xor     eax, eax
0x1400043b4  xor     ebx, ebx
0x1400043b6  cmp     word ptr [rdi], 40h ; '@'
0x1400043ba  xorps   xmm0, xmm0
0x1400043bd  mov     [rsp+130h+var_E0], al
0x1400043c1  mov     rax, [rcx+8]
0x1400043c5  movups  xmmword ptr [rbp+57h+var_78.Ptr], xmm0
0x1400043c9  lea     esi, [rbx+2]
0x1400043cc  movups  xmmword ptr [rbp+57h+var_78.0Ch], xmm0
0x1400043d0  mov     rcx, [rax+88h]
0x1400043d7  lea     r13d, [rbx+17h]
0x1400043db  jnz     short loc_14000440E
0x1400043dd  mov     word ptr [rbp+57h+var_78.Ptr], si
0x1400043e1  test    rcx, rcx
0x1400043e4  jz      short loc_1400043E9
0x1400043e6  mov     rbx, [rcx]
0x1400043e9  mov     edi, [rax+68h]
0x1400043ec  movzx   r13d, si
0x1400043f0  movzx   r15d, word ptr [rax+48h]
0x1400043f5  movzx   r14d, word ptr [rax+78h]
0x1400043fa  bswap   edi
0x1400043fc  mov     dword ptr [rsp+130h+var_D8], edi
0x140004400  mov     dil, [rax+58h]
0x140004404  ror     r15w, 8
0x140004409  jmp     loc_1400044B6
0x14000440e  mov     word ptr [rbp+57h+var_78.Ptr], r13w
0x140004413  test    rcx, rcx
0x140004416  jz      short loc_14000441B
0x140004418  mov     rbx, [rcx]
0x14000441b  cmp     dword ptr [rax+20h], 0Bh
0x14000441f  jz      short loc_14000444E
0x140004421  mov     eax, cs:dword_140012050
0x140004427  cmp     eax, 4
0x14000442a  jbe     short loc_14000444E
0x14000442c  lea     rax, aNoLocalV6Addre; "No local V6 address incoming"
0x140004433  mov     [rsp+130h+var_D8], rax
0x140004438  lea     rdx, byte_14000F3B9
0x14000443f  lea     rax, [rsp+130h+var_D8]
0x140004444  mov     qword ptr [rsp+130h+var_110], rax
0x140004449  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000444e  mov     rax, [rdi+8]
0x140004452  movzx   r15d, word ptr [rax+48h]
0x140004457  ror     r15w, 8
0x14000445c  cmp     dword ptr [rax+60h], 0Bh
0x140004460  jnz     short loc_140004470
0x140004462  mov     rax, [rax+68h]
0x140004466  movups  xmm0, xmmword ptr [rax]
0x140004469  movdqu  xmmword ptr [rbp+57h+var_78.Size], xmm0
0x14000446e  jmp     short loc_1400044A2
0x140004470  mov     eax, cs:dword_140012050
0x140004476  cmp     eax, 4
0x140004479  jbe     short loc_14000449D
0x14000447b  lea     rax, aNoRemoteV6Addr; "No remote V6 address incoming"
0x140004482  mov     [rsp+130h+var_D8], rax
0x140004487  lea     rdx, unk_14000EB48
0x14000448e  lea     rax, [rsp+130h+var_D8]
0x140004493  mov     qword ptr [rsp+130h+var_110], rax
0x140004498  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000449d  mov     [rsp+130h+var_E0], 1
0x1400044a2  mov     rax, [rdi+8]
0x1400044a6  movzx   r14d, word ptr [rax+78h]
0x1400044ab  mov     dil, [rax+58h]
0x1400044af  mov     eax, dword ptr [rbp+57h+var_78.Ptr+4]
0x1400044b2  mov     dword ptr [rsp+130h+var_D8], eax
0x1400044b6  mov     r8d, 0Ah
0x1400044bc  mov     dword ptr [rbp+57h+var_D0], r13d
0x1400044c0  lea     r9, [rbp+57h+SourceString]
0x1400044c4  mov     [rsp+130h+var_DF], dil
0x1400044c9  mov     rcx, r12
0x1400044cc  ror     r14w, 8
0x1400044d1  mov     [rbp+57h+SourceString], 0
0x1400044d9  call    AppIdFromFilter
0x1400044de  test    eax, eax
0x1400044e0  jns     short loc_140004507
0x1400044e2  mov     ecx, cs:dword_140012050
0x1400044e8  cmp     ecx, esi
0x1400044ea  jbe     loc_140004634
0x1400044f0  mov     dword ptr [rsp+130h+var_D8], eax
0x1400044f4  lea     rdx, byte_14000FABD
0x1400044fb  lea     rax, aAppidfromfilte; "AppIdFromFilter failed"
0x140004502  jmp     loc_140004391
0x140004507  mov     eax, cs:dword_140012050
0x14000450d  cmp     eax, 4
0x140004510  jbe     short loc_14000458A
0x140004512  mov     rax, [rbp+57h+SourceString]
0x140004516  lea     rcx, aIpv6; "IPv6"
0x14000451d  mov     qword ptr [rbp+57h+var_B0], rax
0x140004521  lea     rdx, unk_14000F7B8
0x140004528  cmp     si, r13w
0x14000452c  mov     qword ptr [rbp+57h+var_98.Length], rbx
0x140004530  lea     rax, aIpv4; "IPv4"
0x140004537  mov     [rsp+130h+var_DE], dil
0x14000453c  cmovnz  rax, rcx
0x140004540  mov     [rbp+57h+var_C8], r14w
0x140004545  mov     qword ptr [rbp+57h+var_C0], rax
0x140004549  lea     rax, [rbp+57h+var_B0]
0x14000454d  mov     [rsp+130h+var_E8], rax
0x140004552  lea     rax, [rbp+57h+var_98]
0x140004556  mov     [rsp+130h+var_F0], rax
0x14000455b  lea     rax, [rsp+130h+var_DE]
0x140004560  mov     [rsp+130h+var_F8], rax
0x140004565  lea     rax, [rbp+57h+var_C0]
0x140004569  mov     [rsp+130h+var_100], rax
0x14000456e  lea     rax, [rbp+57h+var_C8]
0x140004572  mov     [rsp+130h+var_108], rax
0x140004577  lea     rax, [rbp+57h+var_C6]
0x14000457b  mov     qword ptr [rsp+130h+var_110], rax
0x140004580  mov     [rbp+57h+var_C6], r15w
0x140004585  call    ??$Write@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14000458a  mov     rdx, [rbp+57h+SourceString]; SourceString
0x14000458e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004592  xorps   xmm0, xmm0
0x140004595  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140004599  call    cs:__imp_RtlInitUnicodeString
0x1400045a0  nop     dword ptr [rax+rax+00h]
0x1400045a5  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400045ac  lea     rcx, [rbp+57h+var_B0]
0x1400045b0  add     rdx, 28h ; '('
0x1400045b4  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x1400045b9  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400045c0  add     rax, 30h ; '0'
0x1400045c4  mov     rdi, [rax]
0x1400045c7  jmp     short loc_1400045D6
0x1400045c9  cmp     [rdi+10h], rbx
0x1400045cd  jz      loc_140004655
0x1400045d3  mov     rdi, [rdi]
0x1400045d6  cmp     rdi, rax
0x1400045d9  jnz     short loc_1400045C9
0x1400045db  mov     eax, cs:dword_140012050
0x1400045e1  cmp     eax, 4
0x1400045e4  jbe     short loc_140004606
0x1400045e6  lea     rax, aNoMatchingInte; "No matching interface"
0x1400045ed  lea     rdx, word_14000F2A6
0x1400045f4  mov     qword ptr [rbp+57h+var_C0], rax
0x1400045f8  lea     rax, [rbp+57h+var_C0]
0x1400045fc  mov     qword ptr [rsp+130h+var_110], rax
0x140004601  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140004606  cmp     qword ptr [rbp+57h+var_B0], 0
0x14000460b  jz      short loc_14000461F
0x14000460d  movaps  xmm0, [rbp+57h+var_B0]
0x140004611  lea     rcx, [rbp+57h+var_C0]; struct SpinLockAndSavedIrql *
0x140004615  movdqa  [rbp+57h+var_C0], xmm0
0x14000461a  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x14000461f  mov     rcx, [rbp+57h+SourceString]; P
0x140004623  mov     edx, 64667072h; Tag
0x140004628  call    cs:__imp_ExFreePoolWithTag
0x14000462f  nop     dword ptr [rax+rax+00h]
0x140004634  mov     rcx, [rbp+57h+var_48]
0x140004638  xor     rcx, rsp; StackCookie
0x14000463b  call    __security_check_cookie
0x140004640  add     rsp, 0F8h
0x140004647  pop     r15
0x140004649  pop     r14
0x14000464b  pop     r13
0x14000464d  pop     r12
0x14000464f  pop     rdi
0x140004650  pop     rsi
0x140004651  pop     rbx
0x140004652  pop     rbp
0x140004653  retn
0x140004655  lea     rax, [rdi+20h]
0x140004659  mov     rbx, [rax]
0x14000465c  cmp     rbx, rax
0x14000465f  jz      loc_1400047D8
0x140004665  xorps   xmm0, xmm0
0x140004668  lea     rcx, [rbp+57h+var_98]; DestinationString
0x14000466c  movups  xmmword ptr [rbp+57h+var_98.Length], xmm0
0x140004670  mov     rdx, [rbx+18h]; SourceString
0x140004674  call    cs:__imp_RtlInitUnicodeString
0x14000467b  nop     dword ptr [rax+rax+00h]
0x140004680  cmp     si, r13w
0x140004684  jnz     short loc_1400046FA
0x140004686  cmp     [rbx+5Eh], r14w
0x14000468b  jnz     short loc_14000469A
0x14000468d  mov     eax, dword ptr [rsp+130h+var_D8]
0x140004691  cmp     [rbx+60h], eax
0x140004694  jz      loc_14000472F
0x14000469a  xor     r12b, r12b
0x14000469d  cmp     [rbx+38h], r13w
0x1400046a2  jnz     short loc_1400046EE
0x1400046a4  movzx   eax, [rbp+57h+var_98.Length]
0x1400046a8  cmp     ax, [rbp+57h+DestinationString.Length]
0x1400046ac  jnz     short loc_1400046EE
0x1400046ae  mov     rdx, [rbp+57h+DestinationString.Buffer]; Source2
0x1400046b2  mov     r8d, eax; Length
0x1400046b5  mov     rcx, [rbp+57h+var_98.Buffer]; Source1
0x1400046b9  movzx   r13d, word ptr [rbx+42h]
0x1400046be  call    cs:__imp_RtlCompareMemory
0x1400046c5  nop     dword ptr [rax+rax+00h]
0x1400046ca  movzx   ecx, [rbp+57h+var_98.Length]
0x1400046ce  cmp     rcx, rax
0x1400046d1  jnz     short loc_1400046EA
0x1400046d3  mov     al, [rsp+130h+var_DF]
0x1400046d7  cmp     [rbx+82h], al
0x1400046dd  jnz     short loc_1400046EA
0x1400046df  cmp     r13w, r15w
0x1400046e3  jnz     short loc_1400046EA
0x1400046e5  test    r12b, r12b
0x1400046e8  jnz     short loc_140004737
0x1400046ea  mov     r13d, dword ptr [rbp+57h+var_D0]
0x1400046ee  mov     rbx, [rbx]
0x1400046f1  lea     rax, [rdi+20h]
0x1400046f5  jmp     loc_14000465C
0x1400046fa  mov     eax, 17h
0x1400046ff  cmp     ax, r13w
0x140004703  jnz     short loc_14000469A
0x140004705  cmp     [rbx+5Eh], r14w
0x14000470a  jnz     short loc_14000469A
0x14000470c  cmp     [rsp+130h+var_E0], 0
0x140004711  jnz     short loc_14000472F
0x140004713  mov     rax, [rbx+64h]
0x140004717  cmp     rax, qword ptr [rbp+57h+var_78.Size]
0x14000471b  jnz     loc_14000469A
0x140004721  mov     rax, [rbx+6Ch]
0x140004725  cmp     rax, [rbp+57h+var_68]
0x140004729  jnz     loc_14000469A
0x14000472f  mov     r12b, 1
0x140004732  jmp     loc_14000469D
0x140004737  mov     eax, cs:dword_140012050
0x14000473d  cmp     eax, 4
0x140004740  jbe     short loc_140004784
0x140004742  mov     rax, [rbx+78h]
0x140004746  lea     rdx, dword_14000FDD4; int
0x14000474d  mov     qword ptr [rbp+57h+var_C0], rax
0x140004751  lea     rcx, dword_140012050; int
0x140004758  lea     rax, [rbp+57h+var_C0]
0x14000475c  mov     [rbp+57h+var_50], 8
0x140004764  mov     [rbp+57h+var_58], rax
0x140004768  xor     r9d, r9d; int
0x14000476b  lea     rax, [rbp+57h+var_78]
0x14000476f  xor     r8d, r8d; int
0x140004772  mov     [rsp+130h+var_108], rax; PEVENT_DATA_DESCRIPTOR
0x140004777  mov     [rsp+130h+var_110], 3; ULONG
0x14000477f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004784  mov     rdx, rbx; struct CONNECTION_CONTEXT *
0x140004787  mov     rcx, rdi; P
0x14000478a  call    ?PrepareCleanupResourcesWorkItem@@YAJPEAUINTERFACE_CONTEXT@RoutePolicyCallout@@PEAUCONNECTION_CONTEXT@2@@Z; PrepareCleanupResourcesWorkItem(RoutePolicyCallout::INTERFACE_CONTEXT *,RoutePolicyCallout::CONNECTION_CONTEXT *)
0x14000478f  test    eax, eax
0x140004791  jns     loc_140004606
0x140004797  mov     ecx, cs:dword_140012050
0x14000479d  cmp     ecx, esi
0x14000479f  jbe     loc_140004606
0x1400047a5  mov     dword ptr [rsp+130h+var_D8], eax
0x1400047a9  lea     rdx, unk_14000E9F8
0x1400047b0  lea     rax, aFailedToCleanu; "Failed to cleanup resources"
0x1400047b7  mov     qword ptr [rbp+57h+var_C0], rax
0x1400047bb  lea     rax, [rsp+130h+var_D8]
0x1400047c0  mov     [rsp+130h+var_108], rax
0x1400047c5  lea     rax, [rbp+57h+var_C0]
0x1400047c9  mov     qword ptr [rsp+130h+var_110], rax
0x1400047ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400047d3  jmp     loc_140004606
0x1400047d8  mov     eax, cs:dword_140012050
0x1400047de  cmp     eax, 4
0x1400047e1  jbe     loc_140004606
0x1400047e7  lea     rax, aNotMatchToAnyE; "Not match to any existing connection co"...
0x1400047ee  lea     rdx, word_14000FE12
0x1400047f5  jmp     loc_1400045F4
```
