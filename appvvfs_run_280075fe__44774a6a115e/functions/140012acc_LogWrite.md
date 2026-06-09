# LogWrite

- ea: `0x140012acc`
- end: `0x140012f97`
- name: `LogWrite`
- size: `1227`
- prototype: ``
- caller_count: `53`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400011c0`
- `0x1400019e8`
- `0x140002b4c`
- `0x140002e90`
- `0x1400031bc`
- `0x1400034a0`
- `0x1400037ac`
- `0x140003978`
- `0x140003c00`
- `0x140003f24`
- `0x1400046bc`
- `0x140005b48`
- `0x140005d34`
- `0x140005dc8`
- `0x140006064`
- `0x140006104`
- `0x1400061b4`
- `0x140006710`
- `0x140006c10`
- `0x140007124`
- `0x1400074f4`
- `0x14000783c`
- `0x140008100`
- `0x14000874c`
- `0x140008c04`
- `0x140008e7c`
- `0x140009784`
- `0x140009d44`
- `0x14000aefc`
- `0x14000b1f0`
- `0x14000b4ec`
- `0x14000be3c`
- `0x14000c40c`
- `0x14000c6fc`
- `0x14000c8c4`
- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`
- `0x14000d258`
- `0x14000e18c`
- `0x14000e59c`
- `0x14000e944`
- `0x14000eb14`
- `0x14000f188`
- `0x14000f7ac`
- `0x14000fae0`
- `0x14000fd38`
- `0x140010654`
- `0x1400107c8`
- `0x140024140`

## callees

- `0x140012764`
- `0x1400128d0`
- `0x140012acc`
- `0x140012fa0`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140012d2f`
- `ntoskrnl!_vsnwprintf` at `0x140012d2f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012be9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012be9`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140012bf5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140012bf5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012c70`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012c70`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012c40`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012d6c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012c40`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140012d6c`
- `ntoskrnl!DbgPrint` at `0x140012f65`
- `ntoskrnl!DbgPrint` at `0x140012f65`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140012c22`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140012c22`
- `ntoskrnl!EtwWriteTransfer` at `0x140012f2a`
- `ntoskrnl!EtwWriteTransfer` at `0x140012f2a`

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
  unsigned __int16 Length; // cx
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
  int *v24; // rcx
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
  int *v45; // [rsp+C0h] [rbp-A8h]
  int v46; // [rsp+C8h] [rbp-A0h]
  int v47; // [rsp+CCh] [rbp-9Ch]
  int *v48; // [rsp+D0h] [rbp-98h]
  __int64 v49; // [rsp+D8h] [rbp-90h]
  int *v50; // [rsp+E0h] [rbp-88h]
  __int64 v51; // [rsp+E8h] [rbp-80h]
  char v52; // [rsp+F0h] [rbp-78h] BYREF
  va_list Args; // [rsp+188h] [rbp+20h] BYREF

  va_start(Args, a3);
  v29 = 0;
  if ( (a1 & dword_14001F1D0) != 0 && dword_14001F024 )
  {
    if ( (unsigned __int8)(byte_14001F028 - 1) <= 3u
      || (qword_14001F010 & 0x8000000000000001uLL) == 0
      || (v5 = 1, (qword_14001F018 & 0x8000000000000001uLL) != qword_14001F018) )
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
              else if ( (unsigned int)dword_14001F0E0 > 5
                     && (qword_14001F0F0 & 0x200000000000LL) != 0
                     && (qword_14001F0F8 & 0x200000000000LL) == qword_14001F0F8 )
              {
                v27 = a1;
                v43 = &v27;
                v44 = 4;
                v24 = (int *)(v10 + 40);
                if ( v10 == -40 )
                {
                  v24 = &dword_14001C62C;
                  v26 = 2;
                }
                else
                {
                  v25 = -1;
                  do
                    ++v25;
                  while ( *((_WORD *)v24 + v25) );
                  v26 = 2 * v25 + 2;
                }
                v45 = v24;
                v46 = v26;
                v47 = 0;
                v48 = &dword_14001C62C;
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
                v40 = &dword_14001CB9C;
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
0x140012acc  mov     [rsp+Format], r8
0x140012ad1  mov     qword ptr [rsp+Args], r9
0x140012ad6  push    rbx
0x140012ad7  push    rsi
0x140012ad8  push    rdi
0x140012ad9  push    r12
0x140012adb  push    r13
0x140012add  push    r14
0x140012adf  push    r15
0x140012ae1  sub     rsp, 130h
0x140012ae8  mov     rax, cs:__security_cookie
0x140012aef  xor     rax, rsp
0x140012af2  mov     [rsp+168h+var_48], rax
0x140012afa  mov     r12, rdx
0x140012afd  mov     r14d, ecx
0x140012b00  xor     r13d, r13d
0x140012b03  mov     [rsp+168h+var_128], r13
0x140012b08  test    cs:dword_14001F1D0, ecx
0x140012b0e  jz      loc_140012F73
0x140012b14  cmp     cs:dword_14001F024, r13d
0x140012b1b  jz      loc_140012F73
0x140012b21  mov     al, cs:byte_14001F028
0x140012b27  dec     al
0x140012b29  cmp     al, 3
0x140012b2b  jbe     short loc_140012B55
0x140012b2d  mov     rdx, 8000000000000001h
0x140012b37  test    cs:qword_14001F010, rdx
0x140012b3e  jz      short loc_140012B55
0x140012b40  mov     rax, cs:qword_14001F018
0x140012b47  and     rax, rdx
0x140012b4a  cmp     rax, cs:qword_14001F018
0x140012b51  mov     al, 1
0x140012b53  jz      short loc_140012B58
0x140012b55  mov     al, r13b
0x140012b58  test    al, al
0x140012b5a  jz      loc_140012F73
0x140012b60  mov     eax, cs:LogDebugMessage
0x140012b66  mov     [rsp+168h+var_E8], eax
0x140012b6d  movsd   xmm0, cs:qword_1400178ED
0x140012b75  movsd   qword ptr [rsp+168h+var_E3], xmm0
0x140012b7e  mov     eax, dword ptr cs:qword_1400178ED+7
0x140012b84  mov     dword ptr [rsp+168h+var_E3+7], eax
0x140012b8b  sub     ecx, 1
0x140012b8e  jz      short loc_140012BC7
0x140012b90  sub     ecx, 1
0x140012b93  jz      short loc_140012BBD
0x140012b95  sub     ecx, 1
0x140012b98  jz      short loc_140012BB3
0x140012b9a  cmp     ecx, 1
0x140012b9d  jz      short loc_140012BA9
0x140012b9f  mov     [rsp+168h+var_E4], r13b
0x140012ba7  jmp     short loc_140012BCF
0x140012ba9  mov     [rsp+168h+var_E4], 5
0x140012bb1  jmp     short loc_140012BCF
0x140012bb3  mov     [rsp+168h+var_E4], 4
0x140012bbb  jmp     short loc_140012BCF
0x140012bbd  mov     [rsp+168h+var_E4], 3
0x140012bc5  jmp     short loc_140012BCF
0x140012bc7  mov     [rsp+168h+var_E4], 2
0x140012bcf  call    AllocateLogBufferEntry
0x140012bd4  mov     rbx, rax
0x140012bd7  mov     [rsp+168h+var_110], rax
0x140012bdc  test    rax, rax
0x140012bdf  jz      loc_140012F5C
0x140012be5  lea     r15, [rax+18h]
0x140012be9  call    cs:__imp_PsGetCurrentThreadId
0x140012bf0  nop     dword ptr [rax+rax+00h]
0x140012bf5  call    cs:__imp_PsGetCurrentProcessId
0x140012bfc  nop     dword ptr [rax+rax+00h]
0x140012c01  mov     eax, 2Ah ; '*'
0x140012c06  mov     [rsp+168h+var_F6], ax
0x140012c0b  lea     rax, [rsp+168h+var_78]
0x140012c13  mov     [rsp+168h+var_F0], rax
0x140012c18  lea     rdx, DestinationString; Source
0x140012c1f  mov     rcx, r15; Destination
0x140012c22  call    cs:__imp_RtlAppendUnicodeStringToString
0x140012c29  nop     dword ptr [rax+rax+00h]
0x140012c2e  test    eax, eax
0x140012c30  js      loc_140012F54
0x140012c36  lea     rdx, asc_14001C640; ": ["
0x140012c3d  mov     rcx, r15; Destination
0x140012c40  call    cs:__imp_RtlAppendUnicodeToString
0x140012c47  nop     dword ptr [rax+rax+00h]
0x140012c4c  test    eax, eax
0x140012c4e  js      loc_140012F54
0x140012c54  movzx   ecx, word ptr [r15]
0x140012c58  mov     eax, ecx
0x140012c5a  shr     rax, 1
0x140012c5d  add     rax, rax
0x140012c60  add     [rbx+20h], rax
0x140012c64  sub     [rbx+1Ah], cx
0x140012c68  mov     [r15], r13w
0x140012c6c  lea     rdi, [rbx+18h]
0x140012c70  call    cs:__imp_KeGetCurrentIrql
0x140012c77  nop     dword ptr [rax+rax+00h]
0x140012c7c  test    al, al
0x140012c7e  jnz     loc_140012D61
0x140012c84  lea     r11, [rsp+168h+Args]
0x140012c8c  mov     [rsp+168h+var_120], r13
0x140012c91  mov     [rsp+168h+var_118], r13
0x140012c96  mov     r10, r13
0x140012c99  mov     [rsp+168h+var_120], r13
0x140012c9e  mov     rsi, r13
0x140012ca1  mov     [rsp+168h+var_118], r13
0x140012ca6  mov     eax, r13d
0x140012ca9  mov     [rsp+168h+var_138], eax
0x140012cad  movzx   r9d, word ptr [rdi]
0x140012cb1  test    r9b, 1
0x140012cb5  jnz     short loc_140012CED
0x140012cb7  lea     rdx, [rdi+2]
0x140012cbb  movzx   r8d, word ptr [rdx]
0x140012cbf  test    r8b, 1
0x140012cc3  jnz     short loc_140012CED
0x140012cc5  cmp     r9w, r8w
0x140012cc9  ja      short loc_140012CED
0x140012ccb  mov     ecx, 0FFFEh
0x140012cd0  cmp     r8w, cx
0x140012cd4  ja      short loc_140012CED
0x140012cd6  lea     rcx, [rdi+8]
0x140012cda  cmp     [rcx], r13
0x140012cdd  jnz     short loc_140012CFE
0x140012cdf  test    r9w, r9w
0x140012ce3  jnz     short loc_140012CF5
0x140012ce5  test    r8w, r8w
0x140012ce9  jz      short loc_140012CFE
0x140012ceb  jmp     short loc_140012CF5
0x140012ced  lea     rcx, [rdi+8]
0x140012cf1  lea     rdx, [rdi+2]
0x140012cf5  mov     eax, 0C000000Dh
0x140012cfa  mov     [rsp+168h+var_138], eax
0x140012cfe  test    eax, eax
0x140012d00  js      short loc_140012D5A
0x140012d02  test    rdi, rdi
0x140012d05  jz      short loc_140012D1A
0x140012d07  mov     r10, [rcx]
0x140012d0a  mov     [rsp+168h+var_120], r10
0x140012d0f  movzx   esi, word ptr [rdx]
0x140012d12  shr     rsi, 1
0x140012d15  mov     [rsp+168h+var_118], rsi
0x140012d1a  test    eax, eax
0x140012d1c  js      short loc_140012D5A
0x140012d1e  mov     r9, r11; Args
0x140012d21  mov     r8, [rsp+168h+Format]; Format
0x140012d29  mov     rdx, rsi; Count
0x140012d2c  mov     rcx, r10; Dest
0x140012d2f  call    cs:__imp__vsnwprintf
0x140012d36  nop     dword ptr [rax+rax+00h]
0x140012d3b  test    eax, eax
0x140012d3d  js      short loc_140012D4C
0x140012d3f  movsxd  rcx, eax
0x140012d42  cmp     rcx, rsi
0x140012d45  ja      short loc_140012D4C
0x140012d47  mov     eax, r13d
0x140012d4a  jmp     short loc_140012D54
0x140012d4c  mov     rcx, rsi
0x140012d4f  mov     eax, 80000005h
0x140012d54  add     cx, cx
0x140012d57  mov     [rdi], cx
0x140012d5a  mov     [rsp+168h+var_128], r13
0x140012d5f  jmp     short loc_140012D78
0x140012d61  mov     rdx, [rsp+168h+Format]; Source
0x140012d69  mov     rcx, rdi; Destination
0x140012d6c  call    cs:__imp_RtlAppendUnicodeToString
0x140012d73  nop     dword ptr [rax+rax+00h]
0x140012d78  test    eax, eax
0x140012d7a  js      loc_140012F54
0x140012d80  movzx   edx, word ptr [r15]
0x140012d84  lea     rcx, [rdx+2]
0x140012d88  movzx   eax, word ptr [rbx+1Ah]
0x140012d8c  cmp     rcx, rax
0x140012d8f  ja      loc_140012F54
0x140012d95  shr     rdx, 1
0x140012d98  mov     rcx, [rbx+20h]
0x140012d9c  mov     [rcx+rdx*2], r13w
0x140012da1  lea     eax, [r14-4]
0x140012da5  cmp     eax, 1
0x140012da8  jbe     loc_140012F38
0x140012dae  mov     eax, cs:dword_14001F0E0
0x140012db4  cmp     eax, 5
0x140012db7  jbe     loc_140012F54
0x140012dbd  mov     rcx, cs:qword_14001F0F8
0x140012dc4  mov     rax, cs:qword_14001F0F0
0x140012dcb  mov     r8, 200000000000h
0x140012dd5  test    r8, rax
0x140012dd8  jz      loc_140012F54
0x140012dde  mov     rax, rcx
0x140012de1  and     rax, r8
0x140012de4  cmp     rax, rcx
0x140012de7  jnz     loc_140012F54
0x140012ded  mov     [rsp+168h+var_134], r14d
0x140012df2  lea     rax, [rsp+168h+var_134]
0x140012df7  mov     [rsp+168h+var_B8], rax
0x140012dff  mov     [rsp+168h+var_B0], 4
0x140012e0b  lea     rcx, [rbx+28h]
0x140012e0f  test    rcx, rcx
0x140012e12  jz      short loc_140012E32
0x140012e14  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012e18  inc     rax
0x140012e1b  cmp     [rcx+rax*2], r13w
0x140012e20  jnz     short loc_140012E18
0x140012e22  lea     edx, ds:2[rax*2]
0x140012e29  lea     rax, dword_14001C62C
0x140012e30  jmp     short loc_140012E41
0x140012e32  lea     rax, dword_14001C62C
0x140012e39  mov     rcx, rax
0x140012e3c  mov     edx, 2
0x140012e41  mov     [rsp+168h+var_A8], rcx
0x140012e49  mov     [rsp+168h+var_A0], edx
0x140012e50  mov     [rsp+168h+var_9C], r13d
0x140012e58  mov     [rsp+168h+var_98], rax
0x140012e60  mov     [rsp+168h+var_90], 2
0x140012e6c  mov     [rsp+168h+var_130], r13d
0x140012e71  lea     rax, [rsp+168h+var_130]
0x140012e76  mov     [rsp+168h+var_88], rax
0x140012e7e  mov     [rsp+168h+var_80], 4
0x140012e8a  mov     dword ptr [rsp+168h+EventDescriptor.Id], 0B000000h
0x140012e92  movzx   eax, cs:word_14001CB92
0x140012e99  mov     dword ptr [rsp+168h+EventDescriptor.Level], eax
0x140012e9d  mov     [rsp+168h+EventDescriptor.Keyword], r8
0x140012ea2  mov     rax, cs:EventInformation
0x140012ea9  mov     [rsp+168h+var_D8.Ptr], rax
0x140012eb1  movzx   eax, word ptr [rax]
0x140012eb4  mov     [rsp+168h+var_D8.Size], eax
0x140012ebb  mov     dword ptr [rsp+168h+var_D8.0Ch], 2
0x140012ec6  lea     rax, dword_14001CB9C
0x140012ecd  mov     [rsp+168h+var_C8], rax
0x140012ed5  mov     [rsp+168h+var_C0], 36h ; '6'
0x140012ee0  mov     [rsp+168h+var_BC], 1
0x140012eeb  lea     rax, _TraceLoggingMetadataEnd
0x140012ef2  lea     rcx, _TraceLoggingMetadata
0x140012ef9  sub     eax, ecx
0x140012efb  mov     dword ptr [rsp+168h+var_128], eax
0x140012eff  mov     eax, dword ptr [rsp+168h+var_128]
0x140012f03  lea     rax, [rsp+168h+var_D8]
0x140012f0b  mov     [rsp+168h+UserData], rax; UserData
0x140012f10  mov     [rsp+168h+UserDataCount], 6; UserDataCount
0x140012f18  xor     r9d, r9d; RelatedActivityId
0x140012f1b  xor     r8d, r8d; ActivityId
0x140012f1e  lea     rdx, [rsp+168h+EventDescriptor]; EventDescriptor
0x140012f23  mov     rcx, cs:RegHandle; RegHandle
0x140012f2a  call    cs:__imp_EtwWriteTransfer
0x140012f31  nop     dword ptr [rax+rax+00h]
0x140012f36  jmp     short loc_140012F54
0x140012f38  lea     r9, [rbx+28h]
0x140012f3c  mov     r8, r12
0x140012f3f  lea     rdx, [rsp+168h+var_E8]
0x140012f47  lea     rcx, AppVClientDbg_Context
0x140012f4e  call    McTemplateK0z_EtwWriteTransfer
0x140012f53  nop
0x140012f54  mov     rcx, rbx
0x140012f57  call    FreeLogBufferEntry
0x140012f5c  jmp     short loc_140012F73
0x140012f5e  lea     rcx, aADebugLogMessa; "A debug log message generated an except"...
0x140012f65  call    cs:__imp_DbgPrint
0x140012f6c  nop     dword ptr [rax+rax+00h]
0x140012f71  int     2Ch; Windows NT - assertion failure
0x140012f73  mov     rcx, [rsp+168h+var_48]
0x140012f7b  xor     rcx, rsp; StackCookie
0x140012f7e  call    __security_check_cookie
0x140012f83  add     rsp, 130h
0x140012f8a  pop     r15
0x140012f8c  pop     r14
0x140012f8e  pop     r13
0x140012f90  pop     r12
0x140012f92  pop     rdi
0x140012f93  pop     rsi
0x140012f94  pop     rbx
0x140012f95  retn
0x1400157b1  push    rbp
0x1400157b3  sub     rsp, 30h
0x1400157b7  mov     rbp, rdx
0x1400157ba  mov     rcx, [rbp+58h]
0x1400157be  call    FreeLogBufferEntry
0x1400157c3  nop
0x1400157c4  add     rsp, 30h
0x1400157c8  pop     rbp
0x1400157c9  retn
```
