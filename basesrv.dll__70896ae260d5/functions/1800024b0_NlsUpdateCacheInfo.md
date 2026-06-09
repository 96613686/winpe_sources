# NlsUpdateCacheInfo

- ea: `0x1800024b0`
- end: `0x1800029e0`
- name: `NlsUpdateCacheInfo`
- size: `1328`
- prototype: `BOOLEAN __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800023c0`

## callees

- `0x1800024b0`
- `0x1800029f0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000252b`
- `ntdll!RtlAllocateHeap` at `0x18000256a`
- `ntdll!RtlAllocateHeap` at `0x18000252b`
- `ntdll!RtlAllocateHeap` at `0x18000256a`
- `ntdll!wcsncpy_s` at `0x180002817`
- `ntdll!wcsncpy_s` at `0x180002817`
- `ntdll!NtQueryValueKey` at `0x180002937`
- `ntdll!NtQueryValueKey` at `0x180002937`
- `ntdll!RtlFreeHeap` at `0x180002868`
- `ntdll!RtlFreeHeap` at `0x180002893`
- `ntdll!RtlFreeHeap` at `0x1800029cc`
- `ntdll!RtlFreeHeap` at `0x180002868`
- `ntdll!RtlFreeHeap` at `0x180002893`
- `ntdll!RtlFreeHeap` at `0x1800029cc`
- `ntdll!NtQueryMultipleValueKey` at `0x18000274a`
- `ntdll!NtQueryMultipleValueKey` at `0x18000274a`

## pseudocode

```c
BOOLEAN __fastcall NlsUpdateCacheInfo(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rbp
  __int64 v3; // rsi
  HANDLE v4; // rbx
  struct _KEY_VALUE_ENTRY *v5; // r15
  wchar_t *Heap; // rax
  wchar_t *v7; // r9
  struct _KEY_VALUE_ENTRY *v8; // rax
  int v9; // edi
  char *v10; // r12
  char *v11; // r13
  ULONG *p_DataLength; // rbx
  __int16 *v13; // r14
  ULONG v14; // ecx
  const wchar_t *v15; // r8
  ULONG v16; // edx
  __int64 v17; // rdx
  ULONG v18; // ecx
  errno_t v19; // eax
  BOOLEAN result; // al
  __int16 v21; // dx
  NTSTATUS v22; // eax
  wchar_t v23; // r9
  HANDLE KeyHandle; // [rsp+30h] [rbp-58h]
  wchar_t *ValueBuffer; // [rsp+90h] [rbp+8h]
  ULONG BufferLength; // [rsp+98h] [rbp+10h] BYREF
  int v27; // [rsp+9Ch] [rbp+14h]
  ULONG ResultLength; // [rsp+A0h] [rbp+18h] BYREF
  char *v29; // [rsp+A8h] [rbp+20h]

  v27 = HIDWORD(a2);
  v2 = pNlsRegUserInfo;
  v3 = 0;
  v4 = hCPanelIntlKeyRead;
  BufferLength = 0;
  v5 = 0;
  ResultLength = 0;
  *((_DWORD *)pNlsRegUserInfo + 394) = 1;
  *(_DWORD *)((char *)v2 + 1242) = 0xFFFF;
  v2[313] = 0xFFFF;
  *(_DWORD *)((char *)v2 + 1414) = 0xFFFF;
  KeyHandle = v4;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x67Cu);
  ValueBuffer = Heap;
  v7 = Heap;
  if ( v4 && Heap )
  {
    v8 = (struct _KEY_VALUE_ENTRY *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x67Cu);
    v5 = v8;
    if ( v8 )
    {
      v8->ValueName = (PUNICODE_STRING)OverrideDetails;
      v8[1].ValueName = (PUNICODE_STRING)&sList;
      v8[2].ValueName = (PUNICODE_STRING)&sDecimal;
      v8[3].ValueName = (PUNICODE_STRING)&sThousand;
      v8[4].ValueName = (PUNICODE_STRING)&sGrouping;
      v8[5].ValueName = (PUNICODE_STRING)&sNativeDigits;
      v8[6].ValueName = (PUNICODE_STRING)&sMonDecimalSep;
      v8[7].ValueName = (PUNICODE_STRING)&sMonThousandSep;
      v8[8].ValueName = (PUNICODE_STRING)&sMonGrouping;
      v8[9].ValueName = (PUNICODE_STRING)&sPositiveSign;
      v8[10].ValueName = (PUNICODE_STRING)&sNegativeSign;
      v8[11].ValueName = (PUNICODE_STRING)&sTimeFormat;
      v8[12].ValueName = (PUNICODE_STRING)&sShortTime;
      v8[13].ValueName = (PUNICODE_STRING)&s1159;
      v8[14].ValueName = (PUNICODE_STRING)&s2359;
      v8[15].ValueName = (PUNICODE_STRING)&sShortDate;
      v8[16].ValueName = (PUNICODE_STRING)&sYearMonth;
      v8[17].ValueName = (PUNICODE_STRING)&sLongDate;
      v8[18].ValueName = (PUNICODE_STRING)&iCountry;
      v8[19].ValueName = (PUNICODE_STRING)&iMeasure;
      v8[20].ValueName = (PUNICODE_STRING)&iPaperSize;
      v8[21].ValueName = (PUNICODE_STRING)&iDigits;
      v8[22].ValueName = (PUNICODE_STRING)&iLZero;
      v8[23].ValueName = (PUNICODE_STRING)&iNegNumber;
      v8[24].ValueName = (PUNICODE_STRING)&NumShape;
      v8[25].ValueName = (PUNICODE_STRING)&iCurrDigits;
      v8[26].ValueName = (PUNICODE_STRING)&iCurrency;
      v8[27].ValueName = (PUNICODE_STRING)&iNegCurr;
      v8[28].ValueName = (PUNICODE_STRING)&iFirstDayOfWeek;
      v8[29].ValueName = (PUNICODE_STRING)L" \"";
      BufferLength = 940;
      if ( NtQueryMultipleValueKey(v4, v8, 0x1Eu, ValueBuffer, &BufferLength, &ResultLength) < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        v5 = 0;
      }
    }
    v7 = ValueBuffer;
  }
  v9 = 0;
  v10 = (char *)((char *)&OverrideDetails - (char *)v5);
  v11 = (char *)((char *)&qword_18000F008 - (char *)v5);
  p_DataLength = &v5->DataLength;
  v29 = (char *)((char *)&qword_18000F008 - (char *)v5);
  while ( 1 )
  {
    v13 = (__int16 *)((char *)v2 + *(_QWORD *)((char *)p_DataLength + (_QWORD)v10));
    if ( v5 && v9 < 30 )
    {
      v14 = *p_DataLength;
      v15 = (wchar_t *)((char *)v7 + p_DataLength[1]);
      ResultLength = *p_DataLength;
      v16 = p_DataLength[2];
    }
    else if ( v3 >= 32
           || !KeyHandle
           || !v7
           || (v22 = NtQueryValueKey(
                       KeyHandle,
                       *(PUNICODE_STRING *)((char *)p_DataLength + (_QWORD)v10 - 8),
                       KeyValuePartialInformation,
                       v7,
                       0xB6u,
                       &ResultLength),
               v14 = ResultLength - 12,
               ResultLength -= 12,
               v15 = ValueBuffer + 6,
               v16 = *((_DWORD *)ValueBuffer + 1),
               v22 < 0) )
    {
LABEL_32:
      *v13 = -1;
      if ( *(_QWORD *)&v11[(_QWORD)p_DataLength] )
        v13[1] = 0;
      goto LABEL_20;
    }
    if ( v16 != 1 || !v15 || !v14 || (v14 & 1) != 0 || *(const wchar_t *)((char *)v15 + v14 - 2) )
      goto LABEL_32;
    v17 = *(_QWORD *)&v11[(_QWORD)p_DataLength];
    v18 = (v14 >> 1) - 1;
    ResultLength = v18;
    if ( v17 )
    {
      v19 = wcsncpy_s((wchar_t *)v13 + 1, v17 - 1, v15, v18);
      v11 = v29;
      if ( v19 )
        *(_DWORD *)v13 = 0xFFFF;
      else
        *v13 = ResultLength;
    }
    else
    {
      v21 = 0;
      if ( v18 - 1 <= 2 )
      {
        while ( v18 )
        {
          v23 = *v15;
          if ( (unsigned __int16)(*v15 - 48) > 9u )
            goto LABEL_29;
          ResultLength = --v18;
          v21 = v23 + 10 * v21 - 48;
          ++v15;
        }
      }
      else
      {
LABEL_29:
        v21 = -1;
      }
      *v13 = v21;
    }
LABEL_20:
    ++v9;
    ++v3;
    p_DataLength += 6;
    if ( (unsigned int)v9 >= 0x20 )
      break;
    v7 = ValueBuffer;
  }
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  result = (unsigned __int8)ValueBuffer;
  if ( ValueBuffer )
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ValueBuffer);
  if ( KeyHandle )
    return ReadSettingsCache(v2);
  return result;
}

```

## disassembly

```asm
0x1800024b0  mov     rax, rsp
0x1800024b3  mov     [rax+18h], r8d
0x1800024b7  mov     [rax+10h], rdx
0x1800024bb  mov     [rax+8], rcx
0x1800024bf  push    rbx
0x1800024c0  push    rbp
0x1800024c1  push    rsi
0x1800024c2  push    rdi
0x1800024c3  push    r12
0x1800024c5  push    r13
0x1800024c7  push    r14
0x1800024c9  push    r15
0x1800024cb  sub     rsp, 48h
0x1800024cf  mov     rbp, cs:pNlsRegUserInfo
0x1800024d6  xor     esi, esi
0x1800024d8  mov     rbx, cs:hCPanelIntlKeyRead
0x1800024df  mov     r8d, 67Ch; Size
0x1800024e5  mov     [rax+10h], esi
0x1800024e8  mov     r15d, esi
0x1800024eb  mov     [rax+18h], esi
0x1800024ee  mov     dword ptr [rbp+628h], 1
0x1800024f8  lea     edx, [rsi+8]; Flags
0x1800024fb  mov     dword ptr [rbp+4DAh], 0FFFFh
0x180002505  mov     dword ptr [rbp+4E4h], 0FFFFh
0x18000250f  mov     dword ptr [rbp+586h], 0FFFFh
0x180002519  mov     rcx, gs:60h
0x180002522  mov     [rsp+88h+KeyHandle], rbx
0x180002527  mov     rcx, [rcx+30h]; HeapHandle
0x18000252b  call    cs:__imp_RtlAllocateHeap
0x180002532  nop     dword ptr [rax+rax+00h]
0x180002537  mov     [rsp+88h+ValueBuffer], rax
0x18000253f  mov     r9, rax
0x180002542  test    rbx, rbx
0x180002545  jz      loc_180002766
0x18000254b  test    rax, rax
0x18000254e  jz      loc_180002766
0x180002554  mov     rcx, gs:60h
0x18000255d  lea     edx, [rsi+8]; Flags
0x180002560  mov     r8d, 67Ch; Size
0x180002566  mov     rcx, [rcx+30h]; HeapHandle
0x18000256a  call    cs:__imp_RtlAllocateHeap
0x180002571  nop     dword ptr [rax+rax+00h]
0x180002576  mov     r15, rax
0x180002579  test    rax, rax
0x18000257c  jz      loc_18000275E
0x180002582  mov     rcx, cs:OverrideDetails
0x180002589  lea     r8d, [rsi+1Eh]; EntryCount
0x18000258d  mov     [rax], rcx
0x180002590  mov     rdx, r15; ValueEntries
0x180002593  mov     rcx, cs:off_18000F018
0x18000259a  mov     [rax+18h], rcx
0x18000259e  mov     rcx, cs:off_18000F030
0x1800025a5  mov     [rax+30h], rcx
0x1800025a9  mov     rcx, cs:off_18000F048
0x1800025b0  mov     [rax+48h], rcx
0x1800025b4  mov     rcx, cs:off_18000F060
0x1800025bb  mov     r9, [rsp+88h+ValueBuffer]; ValueBuffer
0x1800025c3  mov     [rax+60h], rcx
0x1800025c7  mov     rcx, cs:off_18000F078
0x1800025ce  mov     [rax+78h], rcx
0x1800025d2  mov     rcx, rbx; KeyHandle
0x1800025d5  mov     rax, cs:off_18000F090
0x1800025dc  mov     [r15+90h], rax
0x1800025e3  mov     rax, cs:off_18000F0A8
0x1800025ea  mov     [r15+0A8h], rax
0x1800025f1  mov     rax, cs:off_18000F0C0
0x1800025f8  mov     [r15+0C0h], rax
0x1800025ff  mov     rax, cs:off_18000F0D8
0x180002606  mov     [r15+0D8h], rax
0x18000260d  mov     rax, cs:off_18000F0F0
0x180002614  mov     [r15+0F0h], rax
0x18000261b  mov     rax, cs:off_18000F108
0x180002622  mov     [r15+108h], rax
0x180002629  mov     rax, cs:off_18000F120
0x180002630  mov     [r15+120h], rax
0x180002637  mov     rax, cs:off_18000F138
0x18000263e  mov     [r15+138h], rax
0x180002645  mov     rax, cs:off_18000F150
0x18000264c  mov     [r15+150h], rax
0x180002653  mov     rax, cs:off_18000F168
0x18000265a  mov     [r15+168h], rax
0x180002661  mov     rax, cs:off_18000F180
0x180002668  mov     [r15+180h], rax
0x18000266f  mov     rax, cs:off_18000F198
0x180002676  mov     [r15+198h], rax
0x18000267d  mov     rax, cs:off_18000F1B0
0x180002684  mov     [r15+1B0h], rax
0x18000268b  mov     rax, cs:off_18000F1C8
0x180002692  mov     [r15+1C8h], rax
0x180002699  mov     rax, cs:off_18000F1E0
0x1800026a0  mov     [r15+1E0h], rax
0x1800026a7  mov     rax, cs:off_18000F1F8
0x1800026ae  mov     [r15+1F8h], rax
0x1800026b5  mov     rax, cs:off_18000F210
0x1800026bc  mov     [r15+210h], rax
0x1800026c3  mov     rax, cs:off_18000F228
0x1800026ca  mov     [r15+228h], rax
0x1800026d1  mov     rax, cs:off_18000F240
0x1800026d8  mov     [r15+240h], rax
0x1800026df  mov     rax, cs:off_18000F258
0x1800026e6  mov     [r15+258h], rax
0x1800026ed  mov     rax, cs:off_18000F270
0x1800026f4  mov     [r15+270h], rax
0x1800026fb  mov     rax, cs:off_18000F288
0x180002702  mov     [r15+288h], rax
0x180002709  mov     rax, cs:off_18000F2A0
0x180002710  mov     [r15+2A0h], rax
0x180002717  mov     rax, cs:off_18000F2B8; " \""
0x18000271e  mov     [r15+2B8h], rax
0x180002725  lea     rax, [rsp+88h+ResultLength]
0x18000272d  mov     [rsp+88h+RequiredBufferLength], rax; RequiredBufferLength
0x180002732  lea     rax, [rsp+88h+arg_8]
0x18000273a  mov     [rsp+88h+BufferLength], rax; BufferLength
0x18000273f  mov     [rsp+88h+arg_8], 3ACh
0x18000274a  call    cs:__imp_NtQueryMultipleValueKey
0x180002751  nop     dword ptr [rax+rax+00h]
0x180002756  test    eax, eax
0x180002758  js      loc_1800029BA
0x18000275e  mov     r9, [rsp+88h+ValueBuffer]
0x180002766  lea     r12, OverrideDetails
0x18000276d  mov     edi, esi
0x18000276f  sub     r12, r15
0x180002772  lea     r13, qword_18000F008
0x180002779  sub     r13, r15
0x18000277c  lea     rbx, [r15+8]
0x180002780  mov     [rsp+88h+arg_18], r13
0x180002788  jmp     short loc_180002798
0x180002790  mov     r9, [rsp+88h+ValueBuffer]; KeyValueInformation
0x180002798  mov     r14, [r12+rbx]
0x18000279c  add     r14, rbp
0x18000279f  test    r15, r15
0x1800027a2  jz      loc_1800028E2
0x1800027a8  cmp     edi, 1Eh
0x1800027ab  jge     loc_1800028E2
0x1800027b1  mov     r8d, [rbx+4]
0x1800027b5  mov     ecx, [rbx]
0x1800027b7  add     r8, r9; Source
0x1800027ba  mov     [rsp+88h+ResultLength], ecx
0x1800027c1  mov     edx, [rbx+8]
0x1800027c4  cmp     edx, 1
0x1800027c7  jnz     loc_1800028E8
0x1800027cd  test    r8, r8
0x1800027d0  jz      loc_1800028E8
0x1800027d6  test    ecx, ecx
0x1800027d8  jz      loc_1800028E8
0x1800027de  test    dl, cl
0x1800027e0  jnz     loc_1800028E8
0x1800027e6  mov     eax, ecx
0x1800027e8  cmp     word ptr [rax+r8-2], 0
0x1800027ef  jnz     loc_1800028E8
0x1800027f5  mov     rdx, [rbx+r13]
0x1800027f9  shr     ecx, 1
0x1800027fb  dec     ecx
0x1800027fd  mov     [rsp+88h+ResultLength], ecx
0x180002804  test    rdx, rdx
0x180002807  jz      loc_1800028C3
0x18000280d  mov     r9d, ecx; MaxCount
0x180002810  dec     rdx; SizeInWords
0x180002813  lea     rcx, [r14+2]; Destination
0x180002817  call    cs:__imp_wcsncpy_s
0x18000281e  nop     dword ptr [rax+rax+00h]
0x180002823  mov     r13, [rsp+88h+arg_18]
0x18000282b  test    eax, eax
0x18000282d  jnz     loc_1800029AE
0x180002833  movzx   eax, word ptr [rsp+88h+ResultLength]
0x18000283b  mov     [r14], ax
0x18000283f  inc     edi
0x180002841  inc     rsi
0x180002844  add     rbx, 18h
0x180002848  cmp     edi, 20h ; ' '
0x18000284b  jb      loc_180002790
0x180002851  test    r15, r15
0x180002854  jz      short loc_180002874
0x180002856  mov     rcx, gs:60h
0x18000285f  mov     r8, r15; P
0x180002862  xor     edx, edx; Flags
0x180002864  mov     rcx, [rcx+30h]; HeapHandle
0x180002868  call    cs:__imp_RtlFreeHeap
0x18000286f  nop     dword ptr [rax+rax+00h]
0x180002874  mov     rax, [rsp+88h+ValueBuffer]
0x18000287c  test    rax, rax
0x18000287f  jz      short loc_18000289F
0x180002881  mov     rcx, gs:60h
0x18000288a  mov     r8, rax; P
0x18000288d  xor     edx, edx; Flags
0x18000288f  mov     rcx, [rcx+30h]; HeapHandle
0x180002893  call    cs:__imp_RtlFreeHeap
0x18000289a  nop     dword ptr [rax+rax+00h]
0x18000289f  mov     rdx, [rsp+88h+KeyHandle]
0x1800028a4  test    rdx, rdx
0x1800028a7  jz      short loc_1800028B1
0x1800028a9  mov     rcx, rbp
0x1800028ac  call    ReadSettingsCache
0x1800028b1  add     rsp, 48h
0x1800028b5  pop     r15
0x1800028b7  pop     r14
0x1800028b9  pop     r13
0x1800028bb  pop     r12
0x1800028bd  pop     rdi
0x1800028be  pop     rsi
0x1800028bf  pop     rbp
0x1800028c0  pop     rbx
0x1800028c1  retn
0x1800028c3  xor     eax, eax
0x1800028c5  movzx   edx, ax
0x1800028c8  lea     eax, [rcx-1]
0x1800028cb  cmp     eax, 2
0x1800028ce  jbe     loc_180002970
0x1800028d4  mov     edx, 0FFFFh
0x1800028d9  mov     [r14], dx
0x1800028dd  jmp     loc_18000283F
0x1800028e2  cmp     rsi, 20h ; ' '
0x1800028e6  jl      short loc_180002905
0x1800028e8  mov     word ptr [r14], 0FFFFh
0x1800028ee  cmp     qword ptr [rbx+r13], 0
0x1800028f3  jbe     loc_18000283F
0x1800028f9  xor     eax, eax
0x1800028fb  mov     [r14+2], ax
0x180002900  jmp     loc_18000283F
0x180002905  mov     rax, [rsp+88h+KeyHandle]
0x18000290a  test    rax, rax
0x18000290d  jz      short loc_1800028E8
0x18000290f  test    r9, r9
0x180002912  jz      short loc_1800028E8
0x180002914  mov     rdx, [r12+rbx-8]; ValueName
0x180002919  lea     rcx, [rsp+88h+ResultLength]
0x180002921  mov     [rsp+88h+RequiredBufferLength], rcx; ResultLength
0x180002926  mov     r8d, 2; KeyValueInformationClass
0x18000292c  mov     rcx, rax; KeyHandle
0x18000292f  mov     dword ptr [rsp+88h+BufferLength], 0B6h; Length
0x180002937  call    cs:__imp_NtQueryValueKey
0x18000293e  nop     dword ptr [rax+rax+00h]
0x180002943  mov     rdx, [rsp+88h+ValueBuffer]
0x18000294b  mov     ecx, [rsp+88h+ResultLength]
0x180002952  add     ecx, 0FFFFFFF4h
0x180002955  mov     [rsp+88h+ResultLength], ecx
0x18000295c  lea     r8, [rdx+0Ch]
0x180002960  mov     edx, [rdx+4]
0x180002963  test    eax, eax
0x180002965  jns     loc_1800027C4
0x18000296b  jmp     loc_1800028E8
0x180002970  test    ecx, ecx
0x180002972  jz      loc_1800028D9
0x180002978  movzx   r9d, word ptr [r8]
0x18000297c  lea     eax, [r9-30h]
0x180002980  cmp     ax, 9
0x180002984  ja      loc_1800028D4
0x18000298a  movzx   eax, dx
0x18000298d  dec     ecx
0x18000298f  shl     ax, 2
0x180002993  add     dx, ax
0x180002996  mov     [rsp+88h+ResultLength], ecx
0x18000299d  add     dx, dx
0x1800029a0  sub     dx, 30h ; '0'
0x1800029a4  add     dx, r9w
0x1800029a8  add     r8, 2
0x1800029ac  jmp     short loc_180002970
0x1800029ae  mov     dword ptr [r14], 0FFFFh
0x1800029b5  jmp     loc_18000283F
0x1800029ba  mov     rcx, gs:60h
0x1800029c3  mov     r8, r15; P
0x1800029c6  xor     edx, edx; Flags
0x1800029c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800029cc  call    cs:__imp_RtlFreeHeap
0x1800029d3  nop     dword ptr [rax+rax+00h]
0x1800029d8  mov     r15, rsi
0x1800029db  jmp     loc_18000275E
```
