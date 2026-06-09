# NlsUpdateCacheInfo

- ea: `0x1800024b0`
- end: `0x18000299f`
- name: `NlsUpdateCacheInfo`
- size: `1263`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800023c0`

## callees

- `0x1800024b0`
- `0x1800029b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180002527`
- `ntdll!RtlAllocateHeap` at `0x180002560`
- `ntdll!RtlAllocateHeap` at `0x180002527`
- `ntdll!RtlAllocateHeap` at `0x180002560`
- `ntdll!wcsncpy_s` at `0x1800027f6`
- `ntdll!wcsncpy_s` at `0x1800027f6`
- `ntdll!NtQueryValueKey` at `0x1800028f1`
- `ntdll!NtQueryValueKey` at `0x1800028f1`
- `ntdll!RtlFreeHeap` at `0x180002837`
- `ntdll!RtlFreeHeap` at `0x18000285a`
- `ntdll!RtlFreeHeap` at `0x18000298b`
- `ntdll!RtlFreeHeap` at `0x180002837`
- `ntdll!RtlFreeHeap` at `0x18000285a`
- `ntdll!RtlFreeHeap` at `0x18000298b`
- `ntdll!NtQueryMultipleValueKey` at `0x18000273e`
- `ntdll!NtQueryMultipleValueKey` at `0x18000273e`

## pseudocode

```c
char __fastcall NlsUpdateCacheInfo(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rbp
  int v3; // ebx
  HANDLE v4; // r12
  struct _KEY_VALUE_ENTRY *v5; // r14
  wchar_t *Heap; // rax
  wchar_t *v7; // r15
  struct _KEY_VALUE_ENTRY *v8; // rax
  NTSTATUS v9; // eax
  __int64 v10; // rdi
  __int16 *v11; // rsi
  ULONG DataLength; // ecx
  const wchar_t *v13; // r8
  ULONG Type; // edx
  __int64 *v15; // rdx
  ULONG v16; // ecx
  __int16 v17; // dx
  wchar_t v18; // r9
  ULONG BufferLength; // [rsp+78h] [rbp+10h] BYREF
  int v21; // [rsp+7Ch] [rbp+14h]
  ULONG ResultLength; // [rsp+80h] [rbp+18h] BYREF

  v21 = HIDWORD(a2);
  v2 = pNlsRegUserInfo;
  v3 = 0;
  v4 = hCPanelIntlKeyRead;
  BufferLength = 0;
  ResultLength = 0;
  v5 = 0;
  *((_DWORD *)pNlsRegUserInfo + 394) = 1;
  *(_DWORD *)((char *)v2 + 1242) = 0xFFFF;
  v2[313] = 0xFFFF;
  *(_DWORD *)((char *)v2 + 1414) = 0xFFFF;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x67Cu);
  v7 = Heap;
  if ( v4 )
  {
    if ( Heap )
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
        ResultLength = 0;
        if ( NtQueryMultipleValueKey(v4, v8, 0x1Eu, v7, &BufferLength, &ResultLength) < 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
          v5 = 0;
        }
      }
    }
  }
  do
  {
    LOBYTE(v9) = v3;
    v10 = 24LL * v3;
    v11 = (__int16 *)((char *)(&OverrideDetails)[(unsigned __int64)v10 / 8 + 1] + (_QWORD)v2);
    if ( v5 && v3 < 30 )
    {
      DataLength = v5[(unsigned __int64)v10 / 0x18].DataLength;
      v13 = (wchar_t *)((char *)v7 + v5[(unsigned __int64)v10 / 0x18].DataOffset);
      ResultLength = DataLength;
      Type = v5[(unsigned __int64)v10 / 0x18].Type;
    }
    else if ( !v4
           || !v7
           || (v9 = NtQueryValueKey(
                      v4,
                      (PUNICODE_STRING)(&OverrideDetails)[(unsigned __int64)v10 / 8],
                      KeyValuePartialInformation,
                      v7,
                      0xB6u,
                      &ResultLength),
               v13 = v7 + 6,
               DataLength = ResultLength - 12,
               ResultLength -= 12,
               Type = *((_DWORD *)v7 + 1),
               v9 < 0) )
    {
LABEL_29:
      *v11 = -1;
      if ( (&OverrideDetails)[(unsigned __int64)v10 / 8 + 2] )
      {
        LOBYTE(v9) = 0;
        v11[1] = 0;
      }
      goto LABEL_17;
    }
    if ( Type != 1 )
      goto LABEL_29;
    if ( !v13 )
      goto LABEL_29;
    if ( !DataLength )
      goto LABEL_29;
    if ( (DataLength & 1) != 0 )
      goto LABEL_29;
    LOBYTE(v9) = DataLength;
    if ( *(const wchar_t *)((char *)v13 + DataLength - 2) )
      goto LABEL_29;
    v15 = (&OverrideDetails)[(unsigned __int64)v10 / 8 + 2];
    v16 = (DataLength >> 1) - 1;
    ResultLength = v16;
    if ( v15 )
    {
      v9 = wcsncpy_s((wchar_t *)v11 + 1, (rsize_t)v15 - 1, v13, v16);
      if ( v9 )
      {
        *(_DWORD *)v11 = 0xFFFF;
      }
      else
      {
        LOBYTE(v9) = ResultLength;
        *v11 = ResultLength;
      }
    }
    else
    {
      if ( v16 && (v17 = 0, v16 <= 3) )
      {
        while ( v16 )
        {
          v18 = *v13;
          LOBYTE(v9) = *v13 - 48;
          if ( (unsigned __int16)(*v13 - 48) > 9u )
            goto LABEL_26;
          --v16;
          LOBYTE(v9) = 4 * v17;
          ResultLength = v16;
          v17 = v18 + 10 * v17 - 48;
          ++v13;
        }
      }
      else
      {
LABEL_26:
        v17 = -1;
      }
      *v11 = v17;
    }
LABEL_17:
    ++v3;
  }
  while ( (unsigned int)v3 < 0x20 );
  if ( v5 )
    LOBYTE(v9) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v7 )
    LOBYTE(v9) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v4 )
    LOBYTE(v9) = ReadSettingsCache((wchar_t *)v2, v4);
  return v9;
}

```

## disassembly

```asm
0x1800024b0  mov     rax, rsp
0x1800024b3  mov     [rax+8], rbx
0x1800024b7  mov     [rax+18h], r8d
0x1800024bb  mov     [rax+10h], rdx
0x1800024bf  push    rbp
0x1800024c0  push    rsi
0x1800024c1  push    rdi
0x1800024c2  push    r12
0x1800024c4  push    r13
0x1800024c6  push    r14
0x1800024c8  push    r15
0x1800024ca  sub     rsp, 30h
0x1800024ce  mov     rbp, cs:pNlsRegUserInfo
0x1800024d5  xor     ebx, ebx
0x1800024d7  mov     r12, cs:hCPanelIntlKeyRead
0x1800024de  mov     edx, 8; Flags
0x1800024e3  mov     [rax+10h], ebx
0x1800024e6  mov     r8d, 67Ch; Size
0x1800024ec  mov     [rax+18h], ebx
0x1800024ef  mov     r14d, ebx
0x1800024f2  mov     dword ptr [rbp+628h], 1
0x1800024fc  mov     dword ptr [rbp+4DAh], 0FFFFh
0x180002506  mov     dword ptr [rbp+4E4h], 0FFFFh
0x180002510  mov     dword ptr [rbp+586h], 0FFFFh
0x18000251a  mov     rcx, gs:60h
0x180002523  mov     rcx, [rcx+30h]; HeapHandle
0x180002527  call    cs:__imp_RtlAllocateHeap
0x18000252e  nop     dword ptr [rax+rax+00h]
0x180002533  mov     r15, rax
0x180002536  test    r12, r12
0x180002539  jz      loc_180002752
0x18000253f  test    rax, rax
0x180002542  jz      loc_180002752
0x180002548  mov     rcx, gs:60h
0x180002551  mov     edx, 8; Flags
0x180002556  mov     r8d, 67Ch; Size
0x18000255c  mov     rcx, [rcx+30h]; HeapHandle
0x180002560  call    cs:__imp_RtlAllocateHeap
0x180002567  nop     dword ptr [rax+rax+00h]
0x18000256c  mov     r14, rax
0x18000256f  test    rax, rax
0x180002572  jz      loc_180002752
0x180002578  mov     rax, cs:OverrideDetails
0x18000257f  mov     r9, r15; ValueBuffer
0x180002582  mov     [r14], rax
0x180002585  mov     r8d, 1Eh; EntryCount
0x18000258b  mov     rax, cs:off_18000F018
0x180002592  mov     rdx, r14; ValueEntries
0x180002595  mov     [r14+18h], rax
0x180002599  mov     rcx, r12; KeyHandle
0x18000259c  mov     rax, cs:off_18000F030
0x1800025a3  mov     [r14+30h], rax
0x1800025a7  mov     rax, cs:off_18000F048
0x1800025ae  mov     [r14+48h], rax
0x1800025b2  mov     rax, cs:off_18000F060
0x1800025b9  mov     [r14+60h], rax
0x1800025bd  mov     rax, cs:off_18000F078
0x1800025c4  mov     [r14+78h], rax
0x1800025c8  mov     rax, cs:off_18000F090
0x1800025cf  mov     [r14+90h], rax
0x1800025d6  mov     rax, cs:off_18000F0A8
0x1800025dd  mov     [r14+0A8h], rax
0x1800025e4  mov     rax, cs:off_18000F0C0
0x1800025eb  mov     [r14+0C0h], rax
0x1800025f2  mov     rax, cs:off_18000F0D8
0x1800025f9  mov     [r14+0D8h], rax
0x180002600  mov     rax, cs:off_18000F0F0
0x180002607  mov     [r14+0F0h], rax
0x18000260e  mov     rax, cs:off_18000F108
0x180002615  mov     [r14+108h], rax
0x18000261c  mov     rax, cs:off_18000F120
0x180002623  mov     [r14+120h], rax
0x18000262a  mov     rax, cs:off_18000F138
0x180002631  mov     [r14+138h], rax
0x180002638  mov     rax, cs:off_18000F150
0x18000263f  mov     [r14+150h], rax
0x180002646  mov     rax, cs:off_18000F168
0x18000264d  mov     [r14+168h], rax
0x180002654  mov     rax, cs:off_18000F180
0x18000265b  mov     [r14+180h], rax
0x180002662  mov     rax, cs:off_18000F198
0x180002669  mov     [r14+198h], rax
0x180002670  mov     rax, cs:off_18000F1B0
0x180002677  mov     [r14+1B0h], rax
0x18000267e  mov     rax, cs:off_18000F1C8
0x180002685  mov     [r14+1C8h], rax
0x18000268c  mov     rax, cs:off_18000F1E0
0x180002693  mov     [r14+1E0h], rax
0x18000269a  mov     rax, cs:off_18000F1F8
0x1800026a1  mov     [r14+1F8h], rax
0x1800026a8  mov     rax, cs:off_18000F210
0x1800026af  mov     [r14+210h], rax
0x1800026b6  mov     rax, cs:off_18000F228
0x1800026bd  mov     [r14+228h], rax
0x1800026c4  mov     rax, cs:off_18000F240
0x1800026cb  mov     [r14+240h], rax
0x1800026d2  mov     rax, cs:off_18000F258
0x1800026d9  mov     [r14+258h], rax
0x1800026e0  mov     rax, cs:off_18000F270
0x1800026e7  mov     [r14+270h], rax
0x1800026ee  mov     rax, cs:off_18000F288
0x1800026f5  mov     [r14+288h], rax
0x1800026fc  mov     rax, cs:off_18000F2A0
0x180002703  mov     [r14+2A0h], rax
0x18000270a  mov     rax, cs:off_18000F2B8; " \""
0x180002711  mov     [r14+2B8h], rax
0x180002718  lea     rax, [rsp+68h+ResultLength]
0x180002720  mov     [rsp+68h+RequiredBufferLength], rax; RequiredBufferLength
0x180002725  lea     rax, [rsp+68h+arg_8]
0x18000272a  mov     [rsp+68h+BufferLength], rax; BufferLength
0x18000272f  mov     [rsp+68h+arg_8], 3ACh
0x180002737  mov     [rsp+68h+ResultLength], ebx
0x18000273e  call    cs:__imp_NtQueryMultipleValueKey
0x180002745  nop     dword ptr [rax+rax+00h]
0x18000274a  test    eax, eax
0x18000274c  js      loc_180002979
0x180002752  lea     r13, OverrideDetails
0x180002759  nop     dword ptr [rax+00000000h]
0x180002760  movsxd  rax, ebx
0x180002763  lea     rcx, [rax+rax*2]
0x180002767  lea     rdi, ds:0[rcx*8]
0x18000276f  mov     rsi, [rdi+r13+8]
0x180002774  add     rsi, rbp
0x180002777  test    r14, r14
0x18000277a  jz      loc_1800028A1
0x180002780  cmp     ebx, 1Eh
0x180002783  jge     loc_1800028A1
0x180002789  mov     r8d, [r14+rdi+0Ch]
0x18000278e  mov     ecx, [r14+rdi+8]
0x180002793  add     r8, r15; Source
0x180002796  mov     [rsp+68h+ResultLength], ecx
0x18000279d  mov     edx, [r14+rdi+10h]
0x1800027a2  cmp     edx, 1
0x1800027a5  jnz     loc_1800028A6
0x1800027ab  test    r8, r8
0x1800027ae  jz      loc_1800028A6
0x1800027b4  test    ecx, ecx
0x1800027b6  jz      loc_1800028A6
0x1800027bc  test    dl, cl
0x1800027be  jnz     loc_1800028A6
0x1800027c4  mov     eax, ecx
0x1800027c6  cmp     word ptr [rax+r8-2], 0
0x1800027cd  jnz     loc_1800028A6
0x1800027d3  mov     rdx, [rdi+r13+10h]
0x1800027d8  shr     ecx, 1
0x1800027da  dec     ecx
0x1800027dc  mov     [rsp+68h+ResultLength], ecx
0x1800027e3  test    rdx, rdx
0x1800027e6  jz      loc_18000288C
0x1800027ec  mov     r9d, ecx; MaxCount
0x1800027ef  dec     rdx; SizeInWords
0x1800027f2  lea     rcx, [rsi+2]; Destination
0x1800027f6  call    cs:__imp_wcsncpy_s
0x1800027fd  nop     dword ptr [rax+rax+00h]
0x180002802  test    eax, eax
0x180002804  jnz     loc_18000296E
0x18000280a  movzx   eax, word ptr [rsp+68h+ResultLength]
0x180002812  mov     [rsi], ax
0x180002815  inc     ebx
0x180002817  cmp     ebx, 20h ; ' '
0x18000281a  jb      loc_180002760
0x180002820  test    r14, r14
0x180002823  jz      short loc_180002843
0x180002825  mov     rcx, gs:60h
0x18000282e  mov     r8, r14; P
0x180002831  xor     edx, edx; Flags
0x180002833  mov     rcx, [rcx+30h]; HeapHandle
0x180002837  call    cs:__imp_RtlFreeHeap
0x18000283e  nop     dword ptr [rax+rax+00h]
0x180002843  test    r15, r15
0x180002846  jz      short loc_180002866
0x180002848  mov     rcx, gs:60h
0x180002851  mov     r8, r15; P
0x180002854  xor     edx, edx; Flags
0x180002856  mov     rcx, [rcx+30h]; HeapHandle
0x18000285a  call    cs:__imp_RtlFreeHeap
0x180002861  nop     dword ptr [rax+rax+00h]
0x180002866  test    r12, r12
0x180002869  jz      short loc_180002876
0x18000286b  mov     rdx, r12
0x18000286e  mov     rcx, rbp
0x180002871  call    ReadSettingsCache
0x180002876  mov     rbx, [rsp+68h+arg_0]
0x18000287b  add     rsp, 30h
0x18000287f  pop     r15
0x180002881  pop     r14
0x180002883  pop     r13
0x180002885  pop     r12
0x180002887  pop     rdi
0x180002888  pop     rsi
0x180002889  pop     rbp
0x18000288a  retn
0x18000288c  test    ecx, ecx
0x18000288e  jnz     loc_180002920
0x180002894  mov     edx, 0FFFFh
0x180002899  mov     [rsi], dx
0x18000289c  jmp     loc_180002815
0x1800028a1  cmp     ebx, 20h ; ' '
0x1800028a4  jl      short loc_1800028C2
0x1800028a6  mov     word ptr [rsi], 0FFFFh
0x1800028ab  cmp     qword ptr [rdi+r13+10h], 0
0x1800028b1  jbe     loc_180002815
0x1800028b7  xor     eax, eax
0x1800028b9  mov     [rsi+2], ax
0x1800028bd  jmp     loc_180002815
0x1800028c2  test    r12, r12
0x1800028c5  jz      short loc_1800028A6
0x1800028c7  test    r15, r15
0x1800028ca  jz      short loc_1800028A6
0x1800028cc  mov     rdx, [rdi+r13]; ValueName
0x1800028d0  lea     rax, [rsp+68h+ResultLength]
0x1800028d8  mov     [rsp+68h+RequiredBufferLength], rax; ResultLength
0x1800028dd  mov     r9, r15; KeyValueInformation
0x1800028e0  mov     r8d, 2; KeyValueInformationClass
0x1800028e6  mov     dword ptr [rsp+68h+BufferLength], 0B6h; Length
0x1800028ee  mov     rcx, r12; KeyHandle
0x1800028f1  call    cs:__imp_NtQueryValueKey
0x1800028f8  nop     dword ptr [rax+rax+00h]
0x1800028fd  mov     ecx, [rsp+68h+ResultLength]
0x180002904  lea     r8, [r15+0Ch]
0x180002908  add     ecx, 0FFFFFFF4h
0x18000290b  mov     [rsp+68h+ResultLength], ecx
0x180002912  mov     edx, [r15+4]
0x180002916  test    eax, eax
0x180002918  jns     loc_1800027A2
0x18000291e  jmp     short loc_1800028A6
0x180002920  xor     edx, edx
0x180002922  cmp     ecx, 3
0x180002925  ja      loc_180002894
0x18000292b  nop     dword ptr [rax+rax+00h]
0x180002930  test    ecx, ecx
0x180002932  jz      loc_180002899
0x180002938  movzx   r9d, word ptr [r8]
0x18000293c  lea     eax, [r9-30h]
0x180002940  cmp     ax, 9
0x180002944  ja      loc_180002894
0x18000294a  movzx   eax, dx
0x18000294d  dec     ecx
0x18000294f  shl     ax, 2
0x180002953  add     dx, ax
0x180002956  mov     [rsp+68h+ResultLength], ecx
0x18000295d  add     dx, dx
0x180002960  sub     dx, 30h ; '0'
0x180002964  add     dx, r9w
0x180002968  add     r8, 2
0x18000296c  jmp     short loc_180002930
0x18000296e  mov     dword ptr [rsi], 0FFFFh
0x180002974  jmp     loc_180002815
0x180002979  mov     rcx, gs:60h
0x180002982  mov     r8, r14; P
0x180002985  xor     edx, edx; Flags
0x180002987  mov     rcx, [rcx+30h]; HeapHandle
0x18000298b  call    cs:__imp_RtlFreeHeap
0x180002992  nop     dword ptr [rax+rax+00h]
0x180002997  mov     r14, rbx
0x18000299a  jmp     loc_180002752
```
