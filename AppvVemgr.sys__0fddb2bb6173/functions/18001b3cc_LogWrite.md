# LogWrite

- ea: `0x18001b3cc`
- end: `0x18001b897`
- name: `LogWrite`
- size: `1227`
- prototype: `void(int, __int64, const WCHAR *, ...)`
- caller_count: `45`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180001f78`
- `0x1800021d0`
- `0x1800033a8`
- `0x180003558`
- `0x1800054e8`
- `0x180005890`
- `0x180005ec4`
- `0x1800062bc`
- `0x180006460`
- `0x180006cac`
- `0x180006eec`
- `0x180008164`
- `0x18000855c`
- `0x180008778`
- `0x180008900`
- `0x180008fc8`
- `0x1800090c4`
- `0x180009208`
- `0x1800098d8`
- `0x180009d44`
- `0x18000d72c`
- `0x18000fe44`
- `0x180010058`
- `0x1800107e4`
- `0x1800109c4`
- `0x180012004`
- `0x180012264`
- `0x1800124d0`
- `0x180013718`
- `0x1800141d0`
- `0x180014338`
- `0x1800145a8`
- `0x180015978`
- `0x180015dd0`
- `0x180015ea0`
- `0x180015fa4`
- `0x180016f64`
- `0x180017c7c`
- `0x180018270`
- `0x180018484`
- `0x180018b9c`
- `0x180018ea0`
- `0x180019014`
- `0x180019b1c`
- `0x18001a594`

## callees

- `0x18000fdc0`
- `0x18001b164`
- `0x18001b228`
- `0x18001b3cc`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18001b82a`
- `ntoskrnl!EtwWriteTransfer` at `0x18001b82a`
- `ntoskrnl!DbgPrint` at `0x18001b865`
- `ntoskrnl!DbgPrint` at `0x18001b865`
- `ntoskrnl!_vsnwprintf` at `0x18001b62f`
- `ntoskrnl!_vsnwprintf` at `0x18001b62f`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001b570`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001b570`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18001b522`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18001b522`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b540`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b66c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b540`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b66c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18001b4f5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18001b4f5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18001b4e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18001b4e9`

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
  if ( (a1 & dword_180027228) != 0 && dword_180027074 )
  {
    if ( (unsigned __int8)(byte_180027078 - 1) <= 3u
      || (qword_180027060 & 0x8000000000000001uLL) == 0
      || (v5 = 1, (qword_180027068 & 0x8000000000000001uLL) != qword_180027068) )
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
              else if ( (unsigned int)dword_1800270E8 > 5
                     && (qword_1800270F8 & 0x200000000000LL) != 0
                     && (qword_180027100 & 0x200000000000LL) == qword_180027100 )
              {
                v27 = a1;
                v43 = &v27;
                v44 = 4;
                v24 = (int *)(v10 + 40);
                if ( v10 == -40 )
                {
                  v24 = &dword_18001E3EC;
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
                v48 = &dword_18001E3EC;
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
                v40 = &dword_180024D9C;
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
0x18001b3cc  mov     [rsp+Format], r8
0x18001b3d1  mov     qword ptr [rsp+Args], r9
0x18001b3d6  push    rbx
0x18001b3d7  push    rsi
0x18001b3d8  push    rdi
0x18001b3d9  push    r12
0x18001b3db  push    r13
0x18001b3dd  push    r14
0x18001b3df  push    r15
0x18001b3e1  sub     rsp, 130h
0x18001b3e8  mov     rax, cs:__security_cookie
0x18001b3ef  xor     rax, rsp
0x18001b3f2  mov     [rsp+168h+var_48], rax
0x18001b3fa  mov     r12, rdx
0x18001b3fd  mov     r14d, ecx
0x18001b400  xor     r13d, r13d
0x18001b403  mov     [rsp+168h+var_128], r13
0x18001b408  test    cs:dword_180027228, ecx
0x18001b40e  jz      loc_18001B873
0x18001b414  cmp     cs:dword_180027074, r13d
0x18001b41b  jz      loc_18001B873
0x18001b421  mov     al, cs:byte_180027078
0x18001b427  dec     al
0x18001b429  cmp     al, 3
0x18001b42b  jbe     short loc_18001B455
0x18001b42d  mov     rdx, 8000000000000001h
0x18001b437  test    cs:qword_180027060, rdx
0x18001b43e  jz      short loc_18001B455
0x18001b440  mov     rax, cs:qword_180027068
0x18001b447  and     rax, rdx
0x18001b44a  cmp     rax, cs:qword_180027068
0x18001b451  mov     al, 1
0x18001b453  jz      short loc_18001B458
0x18001b455  mov     al, r13b
0x18001b458  test    al, al
0x18001b45a  jz      loc_18001B873
0x18001b460  mov     eax, cs:LogDebugMessage
0x18001b466  mov     [rsp+168h+var_E8], eax
0x18001b46d  movsd   xmm0, cs:qword_18002203D
0x18001b475  movsd   qword ptr [rsp+168h+var_E3], xmm0
0x18001b47e  mov     eax, dword ptr cs:qword_18002203D+7
0x18001b484  mov     dword ptr [rsp+168h+var_E3+7], eax
0x18001b48b  sub     ecx, 1
0x18001b48e  jz      short loc_18001B4C7
0x18001b490  sub     ecx, 1
0x18001b493  jz      short loc_18001B4BD
0x18001b495  sub     ecx, 1
0x18001b498  jz      short loc_18001B4B3
0x18001b49a  cmp     ecx, 1
0x18001b49d  jz      short loc_18001B4A9
0x18001b49f  mov     [rsp+168h+var_E4], r13b
0x18001b4a7  jmp     short loc_18001B4CF
0x18001b4a9  mov     [rsp+168h+var_E4], 5
0x18001b4b1  jmp     short loc_18001B4CF
0x18001b4b3  mov     [rsp+168h+var_E4], 4
0x18001b4bb  jmp     short loc_18001B4CF
0x18001b4bd  mov     [rsp+168h+var_E4], 3
0x18001b4c5  jmp     short loc_18001B4CF
0x18001b4c7  mov     [rsp+168h+var_E4], 2
0x18001b4cf  call    AllocateLogBufferEntry
0x18001b4d4  mov     rbx, rax
0x18001b4d7  mov     [rsp+168h+var_110], rax
0x18001b4dc  test    rax, rax
0x18001b4df  jz      loc_18001B85C
0x18001b4e5  lea     r15, [rax+18h]
0x18001b4e9  call    cs:__imp_PsGetCurrentThreadId
0x18001b4f0  nop     dword ptr [rax+rax+00h]
0x18001b4f5  call    cs:__imp_PsGetCurrentProcessId
0x18001b4fc  nop     dword ptr [rax+rax+00h]
0x18001b501  mov     eax, 2Ah ; '*'
0x18001b506  mov     [rsp+168h+var_F6], ax
0x18001b50b  lea     rax, [rsp+168h+var_78]
0x18001b513  mov     [rsp+168h+var_F0], rax
0x18001b518  lea     rdx, DestinationString; Source
0x18001b51f  mov     rcx, r15; Destination
0x18001b522  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001b529  nop     dword ptr [rax+rax+00h]
0x18001b52e  test    eax, eax
0x18001b530  js      loc_18001B854
0x18001b536  lea     rdx, asc_180024890; ": ["
0x18001b53d  mov     rcx, r15; Destination
0x18001b540  call    cs:__imp_RtlAppendUnicodeToString
0x18001b547  nop     dword ptr [rax+rax+00h]
0x18001b54c  test    eax, eax
0x18001b54e  js      loc_18001B854
0x18001b554  movzx   ecx, word ptr [r15]
0x18001b558  mov     eax, ecx
0x18001b55a  shr     rax, 1
0x18001b55d  add     rax, rax
0x18001b560  add     [rbx+20h], rax
0x18001b564  sub     [rbx+1Ah], cx
0x18001b568  mov     [r15], r13w
0x18001b56c  lea     rdi, [rbx+18h]
0x18001b570  call    cs:__imp_KeGetCurrentIrql
0x18001b577  nop     dword ptr [rax+rax+00h]
0x18001b57c  test    al, al
0x18001b57e  jnz     loc_18001B661
0x18001b584  lea     r11, [rsp+168h+Args]
0x18001b58c  mov     [rsp+168h+var_120], r13
0x18001b591  mov     [rsp+168h+var_118], r13
0x18001b596  mov     r10, r13
0x18001b599  mov     [rsp+168h+var_120], r13
0x18001b59e  mov     rsi, r13
0x18001b5a1  mov     [rsp+168h+var_118], r13
0x18001b5a6  mov     eax, r13d
0x18001b5a9  mov     [rsp+168h+var_138], eax
0x18001b5ad  movzx   r9d, word ptr [rdi]
0x18001b5b1  test    r9b, 1
0x18001b5b5  jnz     short loc_18001B5ED
0x18001b5b7  lea     rdx, [rdi+2]
0x18001b5bb  movzx   r8d, word ptr [rdx]
0x18001b5bf  test    r8b, 1
0x18001b5c3  jnz     short loc_18001B5ED
0x18001b5c5  cmp     r9w, r8w
0x18001b5c9  ja      short loc_18001B5ED
0x18001b5cb  mov     ecx, 0FFFEh
0x18001b5d0  cmp     r8w, cx
0x18001b5d4  ja      short loc_18001B5ED
0x18001b5d6  lea     rcx, [rdi+8]
0x18001b5da  cmp     [rcx], r13
0x18001b5dd  jnz     short loc_18001B5FE
0x18001b5df  test    r9w, r9w
0x18001b5e3  jnz     short loc_18001B5F5
0x18001b5e5  test    r8w, r8w
0x18001b5e9  jz      short loc_18001B5FE
0x18001b5eb  jmp     short loc_18001B5F5
0x18001b5ed  lea     rcx, [rdi+8]
0x18001b5f1  lea     rdx, [rdi+2]
0x18001b5f5  mov     eax, 0C000000Dh
0x18001b5fa  mov     [rsp+168h+var_138], eax
0x18001b5fe  test    eax, eax
0x18001b600  js      short loc_18001B65A
0x18001b602  test    rdi, rdi
0x18001b605  jz      short loc_18001B61A
0x18001b607  mov     r10, [rcx]
0x18001b60a  mov     [rsp+168h+var_120], r10
0x18001b60f  movzx   esi, word ptr [rdx]
0x18001b612  shr     rsi, 1
0x18001b615  mov     [rsp+168h+var_118], rsi
0x18001b61a  test    eax, eax
0x18001b61c  js      short loc_18001B65A
0x18001b61e  mov     r9, r11; Args
0x18001b621  mov     r8, [rsp+168h+Format]; Format
0x18001b629  mov     rdx, rsi; Count
0x18001b62c  mov     rcx, r10; Dest
0x18001b62f  call    cs:__imp__vsnwprintf
0x18001b636  nop     dword ptr [rax+rax+00h]
0x18001b63b  test    eax, eax
0x18001b63d  js      short loc_18001B64C
0x18001b63f  movsxd  rcx, eax
0x18001b642  cmp     rcx, rsi
0x18001b645  ja      short loc_18001B64C
0x18001b647  mov     eax, r13d
0x18001b64a  jmp     short loc_18001B654
0x18001b64c  mov     rcx, rsi
0x18001b64f  mov     eax, 80000005h
0x18001b654  add     cx, cx
0x18001b657  mov     [rdi], cx
0x18001b65a  mov     [rsp+168h+var_128], r13
0x18001b65f  jmp     short loc_18001B678
0x18001b661  mov     rdx, [rsp+168h+Format]; Source
0x18001b669  mov     rcx, rdi; Destination
0x18001b66c  call    cs:__imp_RtlAppendUnicodeToString
0x18001b673  nop     dword ptr [rax+rax+00h]
0x18001b678  test    eax, eax
0x18001b67a  js      loc_18001B854
0x18001b680  movzx   edx, word ptr [r15]
0x18001b684  lea     rcx, [rdx+2]
0x18001b688  movzx   eax, word ptr [rbx+1Ah]
0x18001b68c  cmp     rcx, rax
0x18001b68f  ja      loc_18001B854
0x18001b695  shr     rdx, 1
0x18001b698  mov     rcx, [rbx+20h]
0x18001b69c  mov     [rcx+rdx*2], r13w
0x18001b6a1  lea     eax, [r14-4]
0x18001b6a5  cmp     eax, 1
0x18001b6a8  jbe     loc_18001B838
0x18001b6ae  mov     eax, cs:dword_1800270E8
0x18001b6b4  cmp     eax, 5
0x18001b6b7  jbe     loc_18001B854
0x18001b6bd  mov     rcx, cs:qword_180027100
0x18001b6c4  mov     rax, cs:qword_1800270F8
0x18001b6cb  mov     r8, 200000000000h
0x18001b6d5  test    r8, rax
0x18001b6d8  jz      loc_18001B854
0x18001b6de  mov     rax, rcx
0x18001b6e1  and     rax, r8
0x18001b6e4  cmp     rax, rcx
0x18001b6e7  jnz     loc_18001B854
0x18001b6ed  mov     [rsp+168h+var_134], r14d
0x18001b6f2  lea     rax, [rsp+168h+var_134]
0x18001b6f7  mov     [rsp+168h+var_B8], rax
0x18001b6ff  mov     [rsp+168h+var_B0], 4
0x18001b70b  lea     rcx, [rbx+28h]
0x18001b70f  test    rcx, rcx
0x18001b712  jz      short loc_18001B732
0x18001b714  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b718  inc     rax
0x18001b71b  cmp     [rcx+rax*2], r13w
0x18001b720  jnz     short loc_18001B718
0x18001b722  lea     edx, ds:2[rax*2]
0x18001b729  lea     rax, dword_18001E3EC
0x18001b730  jmp     short loc_18001B741
0x18001b732  lea     rax, dword_18001E3EC
0x18001b739  mov     rcx, rax
0x18001b73c  mov     edx, 2
0x18001b741  mov     [rsp+168h+var_A8], rcx
0x18001b749  mov     [rsp+168h+var_A0], edx
0x18001b750  mov     [rsp+168h+var_9C], r13d
0x18001b758  mov     [rsp+168h+var_98], rax
0x18001b760  mov     [rsp+168h+var_90], 2
0x18001b76c  mov     [rsp+168h+var_130], r13d
0x18001b771  lea     rax, [rsp+168h+var_130]
0x18001b776  mov     [rsp+168h+var_88], rax
0x18001b77e  mov     [rsp+168h+var_80], 4
0x18001b78a  mov     dword ptr [rsp+168h+EventDescriptor.Id], 0B000000h
0x18001b792  movzx   eax, cs:word_180024D92
0x18001b799  mov     dword ptr [rsp+168h+EventDescriptor.Level], eax
0x18001b79d  mov     [rsp+168h+EventDescriptor.Keyword], r8
0x18001b7a2  mov     rax, cs:EventInformation
0x18001b7a9  mov     [rsp+168h+var_D8.Ptr], rax
0x18001b7b1  movzx   eax, word ptr [rax]
0x18001b7b4  mov     [rsp+168h+var_D8.Size], eax
0x18001b7bb  mov     dword ptr [rsp+168h+var_D8.0Ch], 2
0x18001b7c6  lea     rax, dword_180024D9C
0x18001b7cd  mov     [rsp+168h+var_C8], rax
0x18001b7d5  mov     [rsp+168h+var_C0], 36h ; '6'
0x18001b7e0  mov     [rsp+168h+var_BC], 1
0x18001b7eb  lea     rax, _TraceLoggingMetadataEnd
0x18001b7f2  lea     rcx, _TraceLoggingMetadata
0x18001b7f9  sub     eax, ecx
0x18001b7fb  mov     dword ptr [rsp+168h+var_128], eax
0x18001b7ff  mov     eax, dword ptr [rsp+168h+var_128]
0x18001b803  lea     rax, [rsp+168h+var_D8]
0x18001b80b  mov     [rsp+168h+UserData], rax; UserData
0x18001b810  mov     [rsp+168h+UserDataCount], 6; UserDataCount
0x18001b818  xor     r9d, r9d; RelatedActivityId
0x18001b81b  xor     r8d, r8d; ActivityId
0x18001b81e  lea     rdx, [rsp+168h+EventDescriptor]; EventDescriptor
0x18001b823  mov     rcx, cs:RegHandle; RegHandle
0x18001b82a  call    cs:__imp_EtwWriteTransfer
0x18001b831  nop     dword ptr [rax+rax+00h]
0x18001b836  jmp     short loc_18001B854
0x18001b838  lea     r9, [rbx+28h]
0x18001b83c  mov     r8, r12
0x18001b83f  lea     rdx, [rsp+168h+var_E8]
0x18001b847  lea     rcx, AppVClientDbg_Context
0x18001b84e  call    McTemplateK0z_EtwWriteTransfer
0x18001b853  nop
0x18001b854  mov     rcx, rbx
0x18001b857  call    FreeLogBufferEntry
0x18001b85c  jmp     short loc_18001B873
0x18001b85e  lea     rcx, aADebugLogMessa; "A debug log message generated an except"...
0x18001b865  call    cs:__imp_DbgPrint
0x18001b86c  nop     dword ptr [rax+rax+00h]
0x18001b871  int     2Ch; Windows NT - assertion failure
0x18001b873  mov     rcx, [rsp+168h+var_48]
0x18001b87b  xor     rcx, rsp; StackCookie
0x18001b87e  call    __security_check_cookie
0x18001b883  add     rsp, 130h
0x18001b88a  pop     r15
0x18001b88c  pop     r14
0x18001b88e  pop     r13
0x18001b890  pop     r12
0x18001b892  pop     rdi
0x18001b893  pop     rsi
0x18001b894  pop     rbx
0x18001b895  retn
0x18001c457  push    rbp
0x18001c459  sub     rsp, 30h
0x18001c45d  mov     rbp, rdx
0x18001c460  mov     rcx, [rbp+58h]
0x18001c464  call    FreeLogBufferEntry
0x18001c469  nop
0x18001c46a  add     rsp, 30h
0x18001c46e  pop     rbp
0x18001c46f  retn
```
