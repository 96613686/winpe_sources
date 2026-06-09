# LogWrite

- ea: `0x1400153c4`
- end: `0x14001588f`
- name: `LogWrite`
- size: `1227`
- prototype: `void(int, __int64, const WCHAR *, ...)`
- caller_count: `45`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140001204`
- `0x140001780`
- `0x140001aa0`
- `0x140001e30`
- `0x1400020c8`
- `0x1400023d8`
- `0x140002edc`
- `0x14000571c`
- `0x140005e3c`
- `0x1400075d0`
- `0x140007700`
- `0x140007c24`
- `0x140007fe4`
- `0x1400084b0`
- `0x1400086a8`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`
- `0x14000984c`
- `0x140009d98`
- `0x14000a1f0`
- `0x14000a310`
- `0x14000abd8`
- `0x14000b0bc`
- `0x14000b32c`
- `0x14000b448`
- `0x14000b748`
- `0x14000bfe4`
- `0x14000c2ac`
- `0x14000c4ac`
- `0x14000d5a8`
- `0x14000da20`
- `0x14000f244`
- `0x14000f988`
- `0x140011154`
- `0x1400115cc`
- `0x140011f30`
- `0x140012b18`
- `0x1400135b4`
- `0x1400137d0`
- `0x1400138fc`
- `0x140013acc`
- `0x140013f68`
- `0x140014364`
- `0x140014a50`

## callees

- `0x14001515c`
- `0x140015220`
- `0x1400153c4`
- `0x140015898`
- `0x140015af0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400154ed`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400154ed`
- `ntoskrnl!DbgPrint` at `0x14001585d`
- `ntoskrnl!DbgPrint` at `0x14001585d`
- `ntoskrnl!EtwWriteTransfer` at `0x140015822`
- `ntoskrnl!EtwWriteTransfer` at `0x140015822`
- `ntoskrnl!_vsnwprintf` at `0x140015627`
- `ntoskrnl!_vsnwprintf` at `0x140015627`
- `ntoskrnl!KeGetCurrentIrql` at `0x140015568`
- `ntoskrnl!KeGetCurrentIrql` at `0x140015568`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001551a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001551a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140015538`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140015664`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140015538`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140015664`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400154e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400154e1`

## pseudocode

```c
void LogWrite(int a1, __int64 a2, const WCHAR *a3, ...)
{
  char v5; // al
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 LogBufferEntry; // rax
  __int64 v10; // rbx
  struct _UNICODE_STRING *v11; // r15
  USHORT Length; // cx
  unsigned __int16 *v13; // rdi
  wchar_t *v14; // r10
  size_t v15; // rsi
  NTSTATUS appended; // eax
  unsigned __int16 v17; // r9
  unsigned __int16 *v18; // rdx
  unsigned __int16 v19; // r8
  wchar_t **v20; // rcx
  int v21; // eax
  __int16 v22; // cx
  unsigned __int64 v23; // rdx
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  int v26; // edx
  int v27; // [rsp+34h] [rbp-134h] BYREF
  int v28; // [rsp+38h] [rbp-130h] BYREF
  __int64 v29; // [rsp+40h] [rbp-128h]
  wchar_t *v30; // [rsp+48h] [rbp-120h]
  size_t v31; // [rsp+50h] [rbp-118h]
  __int64 v32; // [rsp+58h] [rbp-110h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-108h] BYREF
  __int16 v34; // [rsp+72h] [rbp-F6h]
  char *v35; // [rsp+78h] [rbp-F0h]
  int v36; // [rsp+80h] [rbp-E8h] BYREF
  char v37; // [rsp+84h] [rbp-E4h]
  _BYTE v38[11]; // [rsp+85h] [rbp-E3h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-D8h] BYREF
  int *v40; // [rsp+A0h] [rbp-C8h]
  int v41; // [rsp+A8h] [rbp-C0h]
  int v42; // [rsp+ACh] [rbp-BCh]
  int *v43; // [rsp+B0h] [rbp-B8h]
  __int64 v44; // [rsp+B8h] [rbp-B0h]
  const WCHAR *v45; // [rsp+C0h] [rbp-A8h]
  int v46; // [rsp+C8h] [rbp-A0h]
  int v47; // [rsp+CCh] [rbp-9Ch]
  const WCHAR *v48; // [rsp+D0h] [rbp-98h]
  __int64 v49; // [rsp+D8h] [rbp-90h]
  int *v50; // [rsp+E0h] [rbp-88h]
  __int64 v51; // [rsp+E8h] [rbp-80h]
  char v52; // [rsp+F0h] [rbp-78h] BYREF
  va_list Args; // [rsp+188h] [rbp+20h] BYREF

  va_start(Args, a3);
  v29 = 0;
  if ( (a1 & dword_14001F3A4) != 0 && dword_14001F2C4 )
  {
    if ( (unsigned __int8)(byte_14001F2C8 - 1) <= 3u
      || (qword_14001F2B0 & 0x8000000000000001uLL) == 0
      || (v5 = 1, (qword_14001F2B8 & 0x8000000000000001uLL) != qword_14001F2B8) )
    {
      v5 = 0;
    }
    if ( v5 )
    {
      v36 = LogDebugMessage;
      *(_QWORD *)v38 = 0x1000000;
      *(_DWORD *)&v38[7] = 0x80000000;
      v6 = a1 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
            v37 = v8 == 1 ? 5 : 0;
          else
            v37 = 4;
        }
        else
        {
          v37 = 3;
        }
      }
      else
      {
        v37 = 2;
      }
      LogBufferEntry = AllocateLogBufferEntry();
      v10 = LogBufferEntry;
      v32 = LogBufferEntry;
      if ( LogBufferEntry )
      {
        v11 = (struct _UNICODE_STRING *)(LogBufferEntry + 24);
        PsGetCurrentThreadId();
        PsGetCurrentProcessId();
        v34 = 42;
        v35 = &v52;
        if ( RtlAppendUnicodeStringToString(v11, &DestinationString) < 0 || RtlAppendUnicodeToString(v11, L": [") < 0 )
        {
LABEL_54:
          FreeLogBufferEntry(v10);
          return;
        }
        Length = v11->Length;
        *(_QWORD *)(v10 + 32) += 2 * ((unsigned __int64)v11->Length >> 1);
        *(_WORD *)(v10 + 26) -= Length;
        v11->Length = 0;
        v13 = (unsigned __int16 *)(v10 + 24);
        if ( KeGetCurrentIrql() )
        {
          appended = RtlAppendUnicodeToString((PUNICODE_STRING)(v10 + 24), a3);
LABEL_41:
          if ( appended >= 0 )
          {
            v23 = v11->Length;
            if ( v23 + 2 <= *(unsigned __int16 *)(v10 + 26) )
            {
              *(_WORD *)(*(_QWORD *)(v10 + 32) + 2 * (v23 >> 1)) = 0;
              if ( (unsigned int)(a1 - 4) <= 1 )
              {
                McTemplateK0z_EtwWriteTransfer(AppVClientDbg_Context, &v36, a2, v10 + 40);
              }
              else if ( (unsigned int)dword_14001F338 > 5
                     && (qword_14001F348 & 0x200000000000LL) != 0
                     && (qword_14001F350 & 0x200000000000LL) == qword_14001F350 )
              {
                v27 = a1;
                v43 = &v27;
                v44 = 4;
                v24 = (const WCHAR *)(v10 + 40);
                if ( v10 == -40 )
                {
                  v24 = &SourceString;
                  v26 = 2;
                }
                else
                {
                  v25 = -1;
                  do
                    ++v25;
                  while ( v24[v25] );
                  v26 = 2 * v25 + 2;
                }
                v45 = v24;
                v46 = v26;
                v47 = 0;
                v48 = &SourceString;
                v49 = 2;
                v28 = 0;
                v50 = &v28;
                v51 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 5;
                EventDescriptor.Keyword = 0x200000000000LL;
                UserData.Ptr = (ULONGLONG)EventInformation;
                UserData.Size = *(unsigned __int16 *)EventInformation;
                UserData.Reserved = 2;
                v40 = &dword_14001D99C;
                v41 = 54;
                v42 = 1;
                LODWORD(v29) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
              }
            }
          }
          goto LABEL_54;
        }
        v14 = 0;
        v30 = 0;
        v15 = 0;
        v31 = 0;
        appended = 0;
        v17 = *v13;
        if ( (*v13 & 1) != 0
          || (v18 = (unsigned __int16 *)(v10 + 26), v19 = *(_WORD *)(v10 + 26), (v19 & 1) != 0)
          || v17 > v19
          || v19 == 0xFFFF )
        {
          v20 = (wchar_t **)(v10 + 32);
          v18 = (unsigned __int16 *)(v10 + 26);
        }
        else
        {
          v20 = (wchar_t **)(v10 + 32);
          if ( *(_QWORD *)(v10 + 32) || !v17 && !v19 )
            goto LABEL_31;
        }
        appended = -1073741811;
LABEL_31:
        if ( appended >= 0 )
        {
          if ( v10 != -24 )
          {
            v14 = *v20;
            v30 = *v20;
            v15 = (unsigned __int64)*v18 >> 1;
            v31 = v15;
          }
          v21 = _vsnwprintf(v14, v15, a3, Args);
          if ( v21 < 0 || (v22 = v21, v21 > v15) )
          {
            v22 = v15;
            appended = -2147483643;
          }
          else
          {
            appended = 0;
          }
          *v13 = 2 * v22;
        }
        v29 = 0;
        goto LABEL_41;
      }
    }
  }
}

```

## disassembly

```asm
0x1400153c4  mov     [rsp+Format], r8
0x1400153c9  mov     qword ptr [rsp+Args], r9
0x1400153ce  push    rbx
0x1400153cf  push    rsi
0x1400153d0  push    rdi
0x1400153d1  push    r12
0x1400153d3  push    r13
0x1400153d5  push    r14
0x1400153d7  push    r15
0x1400153d9  sub     rsp, 130h
0x1400153e0  mov     rax, cs:__security_cookie
0x1400153e7  xor     rax, rsp
0x1400153ea  mov     [rsp+168h+var_48], rax
0x1400153f2  mov     r12, rdx
0x1400153f5  mov     r14d, ecx
0x1400153f8  xor     r13d, r13d
0x1400153fb  mov     [rsp+168h+var_128], r13
0x140015400  test    cs:dword_14001F3A4, ecx
0x140015406  jz      loc_14001586B
0x14001540c  cmp     cs:dword_14001F2C4, r13d
0x140015413  jz      loc_14001586B
0x140015419  mov     al, cs:byte_14001F2C8
0x14001541f  dec     al
0x140015421  cmp     al, 3
0x140015423  jbe     short loc_14001544D
0x140015425  mov     rdx, 8000000000000001h
0x14001542f  test    cs:qword_14001F2B0, rdx
0x140015436  jz      short loc_14001544D
0x140015438  mov     rax, cs:qword_14001F2B8
0x14001543f  and     rax, rdx
0x140015442  cmp     rax, cs:qword_14001F2B8
0x140015449  mov     al, 1
0x14001544b  jz      short loc_140015450
0x14001544d  mov     al, r13b
0x140015450  test    al, al
0x140015452  jz      loc_14001586B
0x140015458  mov     eax, cs:LogDebugMessage
0x14001545e  mov     [rsp+168h+var_E8], eax
0x140015465  movsd   xmm0, cs:qword_14001897D
0x14001546d  movsd   qword ptr [rsp+168h+var_E3], xmm0
0x140015476  mov     eax, dword ptr cs:qword_14001897D+7
0x14001547c  mov     dword ptr [rsp+168h+var_E3+7], eax
0x140015483  sub     ecx, 1
0x140015486  jz      short loc_1400154BF
0x140015488  sub     ecx, 1
0x14001548b  jz      short loc_1400154B5
0x14001548d  sub     ecx, 1
0x140015490  jz      short loc_1400154AB
0x140015492  cmp     ecx, 1
0x140015495  jz      short loc_1400154A1
0x140015497  mov     [rsp+168h+var_E4], r13b
0x14001549f  jmp     short loc_1400154C7
0x1400154a1  mov     [rsp+168h+var_E4], 5
0x1400154a9  jmp     short loc_1400154C7
0x1400154ab  mov     [rsp+168h+var_E4], 4
0x1400154b3  jmp     short loc_1400154C7
0x1400154b5  mov     [rsp+168h+var_E4], 3
0x1400154bd  jmp     short loc_1400154C7
0x1400154bf  mov     [rsp+168h+var_E4], 2
0x1400154c7  call    AllocateLogBufferEntry
0x1400154cc  mov     rbx, rax
0x1400154cf  mov     [rsp+168h+var_110], rax
0x1400154d4  test    rax, rax
0x1400154d7  jz      loc_140015854
0x1400154dd  lea     r15, [rax+18h]
0x1400154e1  call    cs:__imp_PsGetCurrentThreadId
0x1400154e8  nop     dword ptr [rax+rax+00h]
0x1400154ed  call    cs:__imp_PsGetCurrentProcessId
0x1400154f4  nop     dword ptr [rax+rax+00h]
0x1400154f9  mov     eax, 2Ah ; '*'
0x1400154fe  mov     [rsp+168h+var_F6], ax
0x140015503  lea     rax, [rsp+168h+var_78]
0x14001550b  mov     [rsp+168h+var_F0], rax
0x140015510  lea     rdx, DestinationString; Source
0x140015517  mov     rcx, r15; Destination
0x14001551a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140015521  nop     dword ptr [rax+rax+00h]
0x140015526  test    eax, eax
0x140015528  js      loc_14001584C
0x14001552e  lea     rdx, asc_14001D7B0; ": ["
0x140015535  mov     rcx, r15; Destination
0x140015538  call    cs:__imp_RtlAppendUnicodeToString
0x14001553f  nop     dword ptr [rax+rax+00h]
0x140015544  test    eax, eax
0x140015546  js      loc_14001584C
0x14001554c  movzx   ecx, word ptr [r15]
0x140015550  mov     eax, ecx
0x140015552  shr     rax, 1
0x140015555  add     rax, rax
0x140015558  add     [rbx+20h], rax
0x14001555c  sub     [rbx+1Ah], cx
0x140015560  mov     [r15], r13w
0x140015564  lea     rdi, [rbx+18h]
0x140015568  call    cs:__imp_KeGetCurrentIrql
0x14001556f  nop     dword ptr [rax+rax+00h]
0x140015574  test    al, al
0x140015576  jnz     loc_140015659
0x14001557c  lea     r11, [rsp+168h+Args]
0x140015584  mov     [rsp+168h+var_120], r13
0x140015589  mov     [rsp+168h+var_118], r13
0x14001558e  mov     r10, r13
0x140015591  mov     [rsp+168h+var_120], r13
0x140015596  mov     rsi, r13
0x140015599  mov     [rsp+168h+var_118], r13
0x14001559e  mov     eax, r13d
0x1400155a1  mov     [rsp+168h+var_138], eax
0x1400155a5  movzx   r9d, word ptr [rdi]
0x1400155a9  test    r9b, 1
0x1400155ad  jnz     short loc_1400155E5
0x1400155af  lea     rdx, [rdi+2]
0x1400155b3  movzx   r8d, word ptr [rdx]
0x1400155b7  test    r8b, 1
0x1400155bb  jnz     short loc_1400155E5
0x1400155bd  cmp     r9w, r8w
0x1400155c1  ja      short loc_1400155E5
0x1400155c3  mov     ecx, 0FFFEh
0x1400155c8  cmp     r8w, cx
0x1400155cc  ja      short loc_1400155E5
0x1400155ce  lea     rcx, [rdi+8]
0x1400155d2  cmp     [rcx], r13
0x1400155d5  jnz     short loc_1400155F6
0x1400155d7  test    r9w, r9w
0x1400155db  jnz     short loc_1400155ED
0x1400155dd  test    r8w, r8w
0x1400155e1  jz      short loc_1400155F6
0x1400155e3  jmp     short loc_1400155ED
0x1400155e5  lea     rcx, [rdi+8]
0x1400155e9  lea     rdx, [rdi+2]
0x1400155ed  mov     eax, 0C000000Dh
0x1400155f2  mov     [rsp+168h+var_138], eax
0x1400155f6  test    eax, eax
0x1400155f8  js      short loc_140015652
0x1400155fa  test    rdi, rdi
0x1400155fd  jz      short loc_140015612
0x1400155ff  mov     r10, [rcx]
0x140015602  mov     [rsp+168h+var_120], r10
0x140015607  movzx   esi, word ptr [rdx]
0x14001560a  shr     rsi, 1
0x14001560d  mov     [rsp+168h+var_118], rsi
0x140015612  test    eax, eax
0x140015614  js      short loc_140015652
0x140015616  mov     r9, r11; Args
0x140015619  mov     r8, [rsp+168h+Format]; Format
0x140015621  mov     rdx, rsi; Count
0x140015624  mov     rcx, r10; Dest
0x140015627  call    cs:__imp__vsnwprintf
0x14001562e  nop     dword ptr [rax+rax+00h]
0x140015633  test    eax, eax
0x140015635  js      short loc_140015644
0x140015637  movsxd  rcx, eax
0x14001563a  cmp     rcx, rsi
0x14001563d  ja      short loc_140015644
0x14001563f  mov     eax, r13d
0x140015642  jmp     short loc_14001564C
0x140015644  mov     rcx, rsi
0x140015647  mov     eax, 80000005h
0x14001564c  add     cx, cx
0x14001564f  mov     [rdi], cx
0x140015652  mov     [rsp+168h+var_128], r13
0x140015657  jmp     short loc_140015670
0x140015659  mov     rdx, [rsp+168h+Format]; Source
0x140015661  mov     rcx, rdi; Destination
0x140015664  call    cs:__imp_RtlAppendUnicodeToString
0x14001566b  nop     dword ptr [rax+rax+00h]
0x140015670  test    eax, eax
0x140015672  js      loc_14001584C
0x140015678  movzx   edx, word ptr [r15]
0x14001567c  lea     rcx, [rdx+2]
0x140015680  movzx   eax, word ptr [rbx+1Ah]
0x140015684  cmp     rcx, rax
0x140015687  ja      loc_14001584C
0x14001568d  shr     rdx, 1
0x140015690  mov     rcx, [rbx+20h]
0x140015694  mov     [rcx+rdx*2], r13w
0x140015699  lea     eax, [r14-4]
0x14001569d  cmp     eax, 1
0x1400156a0  jbe     loc_140015830
0x1400156a6  mov     eax, cs:dword_14001F338
0x1400156ac  cmp     eax, 5
0x1400156af  jbe     loc_14001584C
0x1400156b5  mov     rcx, cs:qword_14001F350
0x1400156bc  mov     rax, cs:qword_14001F348
0x1400156c3  mov     r8, 200000000000h
0x1400156cd  test    r8, rax
0x1400156d0  jz      loc_14001584C
0x1400156d6  mov     rax, rcx
0x1400156d9  and     rax, r8
0x1400156dc  cmp     rax, rcx
0x1400156df  jnz     loc_14001584C
0x1400156e5  mov     [rsp+168h+var_134], r14d
0x1400156ea  lea     rax, [rsp+168h+var_134]
0x1400156ef  mov     [rsp+168h+var_B8], rax
0x1400156f7  mov     [rsp+168h+var_B0], 4
0x140015703  lea     rcx, [rbx+28h]
0x140015707  test    rcx, rcx
0x14001570a  jz      short loc_14001572A
0x14001570c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015710  inc     rax
0x140015713  cmp     [rcx+rax*2], r13w
0x140015718  jnz     short loc_140015710
0x14001571a  lea     edx, ds:2[rax*2]
0x140015721  lea     rax, SourceString
0x140015728  jmp     short loc_140015739
0x14001572a  lea     rax, SourceString
0x140015731  mov     rcx, rax
0x140015734  mov     edx, 2
0x140015739  mov     [rsp+168h+var_A8], rcx
0x140015741  mov     [rsp+168h+var_A0], edx
0x140015748  mov     [rsp+168h+var_9C], r13d
0x140015750  mov     [rsp+168h+var_98], rax
0x140015758  mov     [rsp+168h+var_90], 2
0x140015764  mov     [rsp+168h+var_130], r13d
0x140015769  lea     rax, [rsp+168h+var_130]
0x14001576e  mov     [rsp+168h+var_88], rax
0x140015776  mov     [rsp+168h+var_80], 4
0x140015782  mov     dword ptr [rsp+168h+EventDescriptor.Id], 0B000000h
0x14001578a  movzx   eax, cs:word_14001D992
0x140015791  mov     dword ptr [rsp+168h+EventDescriptor.Level], eax
0x140015795  mov     [rsp+168h+EventDescriptor.Keyword], r8
0x14001579a  mov     rax, cs:EventInformation
0x1400157a1  mov     [rsp+168h+var_D8.Ptr], rax
0x1400157a9  movzx   eax, word ptr [rax]
0x1400157ac  mov     [rsp+168h+var_D8.Size], eax
0x1400157b3  mov     dword ptr [rsp+168h+var_D8.0Ch], 2
0x1400157be  lea     rax, dword_14001D99C
0x1400157c5  mov     [rsp+168h+var_C8], rax
0x1400157cd  mov     [rsp+168h+var_C0], 36h ; '6'
0x1400157d8  mov     [rsp+168h+var_BC], 1
0x1400157e3  lea     rax, _TraceLoggingMetadataEnd
0x1400157ea  lea     rcx, _TraceLoggingMetadata
0x1400157f1  sub     eax, ecx
0x1400157f3  mov     dword ptr [rsp+168h+var_128], eax
0x1400157f7  mov     eax, dword ptr [rsp+168h+var_128]
0x1400157fb  lea     rax, [rsp+168h+var_D8]
0x140015803  mov     [rsp+168h+UserData], rax; UserData
0x140015808  mov     [rsp+168h+UserDataCount], 6; UserDataCount
0x140015810  xor     r9d, r9d; RelatedActivityId
0x140015813  xor     r8d, r8d; ActivityId
0x140015816  lea     rdx, [rsp+168h+EventDescriptor]; EventDescriptor
0x14001581b  mov     rcx, cs:RegHandle; RegHandle
0x140015822  call    cs:__imp_EtwWriteTransfer
0x140015829  nop     dword ptr [rax+rax+00h]
0x14001582e  jmp     short loc_14001584C
0x140015830  lea     r9, [rbx+28h]
0x140015834  mov     r8, r12
0x140015837  lea     rdx, [rsp+168h+var_E8]
0x14001583f  lea     rcx, AppVClientDbg_Context
0x140015846  call    McTemplateK0z_EtwWriteTransfer
0x14001584b  nop
0x14001584c  mov     rcx, rbx
0x14001584f  call    FreeLogBufferEntry
0x140015854  jmp     short loc_14001586B
0x140015856  lea     rcx, aADebugLogMessa; "A debug log message generated an except"...
0x14001585d  call    cs:__imp_DbgPrint
0x140015864  nop     dword ptr [rax+rax+00h]
0x140015869  int     2Ch; Windows NT - assertion failure
0x14001586b  mov     rcx, [rsp+168h+var_48]
0x140015873  xor     rcx, rsp; StackCookie
0x140015876  call    __security_check_cookie
0x14001587b  add     rsp, 130h
0x140015882  pop     r15
0x140015884  pop     r14
0x140015886  pop     r13
0x140015888  pop     r12
0x14001588a  pop     rdi
0x14001588b  pop     rsi
0x14001588c  pop     rbx
0x14001588d  retn
0x140016457  push    rbp
0x140016459  sub     rsp, 30h
0x14001645d  mov     rbp, rdx
0x140016460  mov     rcx, [rbp+58h]
0x140016464  call    FreeLogBufferEntry
0x140016469  nop
0x14001646a  add     rsp, 30h
0x14001646e  pop     rbp
0x14001646f  retn
```
