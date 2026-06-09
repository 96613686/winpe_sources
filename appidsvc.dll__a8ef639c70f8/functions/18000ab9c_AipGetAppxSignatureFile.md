# AipGetAppxSignatureFile

- ea: `0x18000ab9c`
- end: `0x18000af08`
- name: `AipGetAppxSignatureFile`
- size: `876`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, BYTE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004c28`

## callees

- `0x18000880c`
- `0x18000ab10`
- `0x18000ab9c`
- `0x18000d010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000aeb1`
- `ntdll!RtlFreeHeap` at `0x18000aed7`
- `ntdll!RtlFreeHeap` at `0x18000aeef`
- `ntdll!RtlFreeHeap` at `0x18000aeb1`
- `ntdll!RtlFreeHeap` at `0x18000aed7`
- `ntdll!RtlFreeHeap` at `0x18000aeef`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18000abcf`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18000ac6c`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18000abcf`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18000ac6c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackagePathByFullName` at `0x18000acf8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackagePathByFullName` at `0x18000adee`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackagePathByFullName` at `0x18000acf8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackagePathByFullName` at `0x18000adee`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!PublisherFromPackageFullName` at `0x18000acb4`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!PublisherFromPackageFullName` at `0x18000acb4`

## pseudocode

```c
__int64 __fastcall AipGetAppxSignatureFile(PCWSTR packageFullName, BYTE **a2, unsigned __int16 **a3)
{
  WCHAR *v6; // r15
  unsigned __int16 *v7; // r14
  LONG v8; // eax
  signed int v9; // ebx
  BYTE *v10; // rsi
  void (__fastcall *v11)(const wchar_t *, const wchar_t *); // rax
  const wchar_t *v12; // rdx
  const wchar_t *v13; // rcx
  BYTE *v14; // rax
  LONG v15; // eax
  int v16; // ebx
  int v17; // eax
  int v18; // ebx
  LONG StagedPackagePathByFullName; // eax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rbx
  LONG v22; // eax
  int v23; // ebx
  int v25[6]; // [rsp+30h] [rbp-18h] BYREF
  UINT32 bufferLength; // [rsp+A8h] [rbp+60h] BYREF

  bufferLength = 0;
  v6 = 0;
  v7 = 0;
  v8 = PackageIdFromFullName(packageFullName, 0, &bufferLength, 0);
  v9 = v8;
  if ( v8 == 122 )
  {
    v25[0] = 8193;
    v14 = (BYTE *)AiAlloc(bufferLength + 16386LL);
    v10 = v14;
    if ( !v14 )
    {
      v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
      v9 = -1073741801;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_40;
      v12 = (const wchar_t *)&qword_18000F230;
      v13 = L".0";
      goto LABEL_39;
    }
    v15 = PackageIdFromFullName(packageFullName, 0, &bufferLength, v14);
    if ( v15 )
    {
      v16 = (unsigned __int16)v15;
      v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
      v9 = v16 | 0x80070000;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_40;
      v12 = L"*,";
      v13 = L".0";
      goto LABEL_39;
    }
    *((_QWORD *)v10 + 3) = &v10[bufferLength];
    v17 = PublisherFromPackageFullName(packageFullName, v25);
    if ( v17 )
    {
      v18 = (unsigned __int16)v17;
      v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
      v9 = v18 | 0x80070000;
      if ( !g_AiLogFunctionCallErrorEvent )
        goto LABEL_40;
      v12 = L"8:";
      v13 = L".0";
      goto LABEL_39;
    }
    bufferLength = 0;
    StagedPackagePathByFullName = GetStagedPackagePathByFullName(packageFullName, &bufferLength, 0);
    v9 = StagedPackagePathByFullName;
    if ( StagedPackagePathByFullName == 122 )
    {
      v6 = (WCHAR *)AiAlloc(2LL * bufferLength);
      if ( v6 )
      {
        v20 = 2LL * bufferLength;
        if ( v20 + 4 >= v20 )
        {
          v21 = v20 + 38;
          if ( v20 + 38 >= v20 + 4 )
          {
            v22 = GetStagedPackagePathByFullName(packageFullName, &bufferLength, v6);
            if ( v22 )
            {
              v23 = (unsigned __int16)v22;
              v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
              v9 = v23 | 0x80070000;
              if ( !g_AiLogFunctionCallErrorEvent )
                goto LABEL_40;
              v12 = L"<>";
              v13 = L".0";
            }
            else
            {
              v7 = (unsigned __int16 *)AiAlloc(v21);
              if ( v7 )
              {
                v9 = RtlStringCbPrintfW(v7, v21, L"%s\\%s", v6, L"AppxSignature.p7x");
                if ( v9 >= 0 )
                  goto LABEL_40;
                v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
                if ( !g_AiLogFunctionCallErrorEvent )
                  goto LABEL_40;
                v12 = L"$&";
                v13 = L".0";
              }
              else
              {
                v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
                v9 = -1073741801;
                if ( !g_AiLogFunctionCallErrorEvent )
                  goto LABEL_40;
                v12 = (const wchar_t *)&qword_18000F1E0;
                v13 = L".0";
              }
            }
          }
          else
          {
            v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
            v9 = -1073741675;
            if ( !g_AiLogFunctionCallErrorEvent )
              goto LABEL_40;
            v12 = (const wchar_t *)&qword_18000F290;
            v13 = L".0";
          }
        }
        else
        {
          v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
          v9 = -1073741675;
          if ( !g_AiLogFunctionCallErrorEvent )
            goto LABEL_40;
          v12 = (const wchar_t *)&qword_18000F270;
          v13 = L".0";
        }
      }
      else
      {
        v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
        v9 = -1073741801;
        if ( !g_AiLogFunctionCallErrorEvent )
          goto LABEL_40;
        v12 = (const wchar_t *)&qword_18000F150;
        v13 = L".0";
      }
      goto LABEL_39;
    }
    if ( StagedPackagePathByFullName )
      v9 = (unsigned __int16)StagedPackagePathByFullName | 0x80070000;
    v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
    if ( g_AiLogFunctionCallErrorEvent )
    {
      v12 = L"<>";
      v13 = L".0";
      goto LABEL_39;
    }
  }
  else
  {
    v10 = 0;
    if ( v8 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
    {
      v11 = (void (__fastcall *)(const wchar_t *, const wchar_t *))g_AiLogFunctionCallErrorEvent;
      if ( g_AiLogFunctionCallErrorEvent )
      {
        v12 = L"*,";
        v13 = L".0";
LABEL_39:
        v11(v13, v12);
      }
    }
  }
LABEL_40:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v9 < 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  }
  else
  {
    *a3 = v7;
    *a2 = v10;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ab9c  push    rbp
0x18000ab9e  push    rbx
0x18000ab9f  push    rsi
0x18000aba0  push    rdi
0x18000aba1  push    r12
0x18000aba3  push    r13
0x18000aba5  push    r14
0x18000aba7  push    r15
0x18000aba9  mov     rbp, rsp
0x18000abac  sub     rsp, 48h
0x18000abb0  mov     r12, r8
0x18000abb3  mov     [rbp+bufferLength], 0
0x18000abba  mov     r13, rdx
0x18000abbd  lea     r8, [rbp+bufferLength]; bufferLength
0x18000abc1  xor     edx, edx; flags
0x18000abc3  xor     r9d, r9d; buffer
0x18000abc6  mov     rdi, rcx
0x18000abc9  xor     r15d, r15d
0x18000abcc  xor     r14d, r14d
0x18000abcf  call    cs:__imp_PackageIdFromFullName
0x18000abd5  mov     ebx, eax
0x18000abd7  cmp     eax, 7Ah ; 'z'
0x18000abda  jz      short loc_18000AC16
0x18000abdc  xor     esi, esi
0x18000abde  test    eax, eax
0x18000abe0  jz      short loc_18000ABEB
0x18000abe2  movzx   ebx, ax
0x18000abe5  or      ebx, 80070000h
0x18000abeb  test    ebx, ebx
0x18000abed  jns     loc_18000AE9F
0x18000abf3  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000abfa  test    rax, rax
0x18000abfd  jz      loc_18000AE9F
0x18000ac03  lea     rdx, asc_18000F190; "*,"
0x18000ac0a  lea     rcx, a0_14; ".0"
0x18000ac11  jmp     loc_18000AE97
0x18000ac16  mov     ecx, [rbp+bufferLength]
0x18000ac19  add     rcx, 4002h
0x18000ac20  mov     [rbp+var_18], 2001h
0x18000ac27  call    AiAlloc
0x18000ac2c  mov     rsi, rax
0x18000ac2f  test    rax, rax
0x18000ac32  jnz     short loc_18000AC60
0x18000ac34  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ac3b  mov     r8d, 0C0000017h
0x18000ac41  mov     ebx, r8d
0x18000ac44  test    rax, rax
0x18000ac47  jz      loc_18000AE9F
0x18000ac4d  lea     rdx, qword_18000F230
0x18000ac54  lea     rcx, a0_15; ".0"
0x18000ac5b  jmp     loc_18000AE9A
0x18000ac60  mov     r9, rsi; buffer
0x18000ac63  lea     r8, [rbp+bufferLength]; bufferLength
0x18000ac67  xor     edx, edx; flags
0x18000ac69  mov     rcx, rdi; packageFullName
0x18000ac6c  call    cs:__imp_PackageIdFromFullName
0x18000ac72  test    eax, eax
0x18000ac74  jz      short loc_18000ACA2
0x18000ac76  movzx   ebx, ax
0x18000ac79  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ac80  or      ebx, 80070000h
0x18000ac86  test    rax, rax
0x18000ac89  jz      loc_18000AE9F
0x18000ac8f  lea     rdx, asc_18000F180; "*,"
0x18000ac96  lea     rcx, a0_16; ".0"
0x18000ac9d  jmp     loc_18000AE97
0x18000aca2  mov     r8d, [rbp+bufferLength]
0x18000aca6  lea     rdx, [rbp+var_18]
0x18000acaa  add     r8, rsi
0x18000acad  mov     rcx, rdi
0x18000acb0  mov     [rsi+18h], r8
0x18000acb4  call    cs:__imp_PublisherFromPackageFullName
0x18000acba  test    eax, eax
0x18000acbc  jz      short loc_18000ACEA
0x18000acbe  movzx   ebx, ax
0x18000acc1  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000acc8  or      ebx, 80070000h
0x18000acce  test    rax, rax
0x18000acd1  jz      loc_18000AE9F
0x18000acd7  lea     rdx, a8_3; "8:"
0x18000acde  lea     rcx, a0_17; ".0"
0x18000ace5  jmp     loc_18000AE97
0x18000acea  xor     r8d, r8d; path
0x18000aced  mov     [rbp+bufferLength], r14d
0x18000acf1  lea     rdx, [rbp+bufferLength]; pathLength
0x18000acf5  mov     rcx, rdi; packageFullName
0x18000acf8  call    cs:__imp_GetStagedPackagePathByFullName
0x18000acfe  mov     ebx, eax
0x18000ad00  cmp     eax, 7Ah ; 'z'
0x18000ad03  jz      short loc_18000AD35
0x18000ad05  test    eax, eax
0x18000ad07  jz      short loc_18000AD12
0x18000ad09  movzx   ebx, ax
0x18000ad0c  or      ebx, 80070000h
0x18000ad12  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ad19  test    rax, rax
0x18000ad1c  jz      loc_18000AE9F
0x18000ad22  lea     rdx, asc_18000F280; "<>"
0x18000ad29  lea     rcx, a0_18; ".0"
0x18000ad30  jmp     loc_18000AE97
0x18000ad35  mov     ecx, [rbp+bufferLength]
0x18000ad38  add     rcx, rcx
0x18000ad3b  call    AiAlloc
0x18000ad40  mov     r15, rax
0x18000ad43  test    rax, rax
0x18000ad46  jnz     short loc_18000AD74
0x18000ad48  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ad4f  mov     r8d, 0C0000017h
0x18000ad55  mov     ebx, r8d
0x18000ad58  test    rax, rax
0x18000ad5b  jz      loc_18000AE9F
0x18000ad61  lea     rdx, qword_18000F150
0x18000ad68  lea     rcx, a0_19; ".0"
0x18000ad6f  jmp     loc_18000AE9A
0x18000ad74  mov     eax, [rbp+bufferLength]
0x18000ad77  add     rax, rax
0x18000ad7a  lea     rcx, [rax+4]
0x18000ad7e  cmp     rcx, rax
0x18000ad81  jnb     short loc_18000ADAF
0x18000ad83  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ad8a  mov     r8d, 0C0000095h
0x18000ad90  mov     ebx, r8d
0x18000ad93  test    rax, rax
0x18000ad96  jz      loc_18000AE9F
0x18000ad9c  lea     rdx, qword_18000F270
0x18000ada3  lea     rcx, a0_20; ".0"
0x18000adaa  jmp     loc_18000AE9A
0x18000adaf  lea     rbx, [rcx+22h]
0x18000adb3  cmp     rbx, rcx
0x18000adb6  jnb     short loc_18000ADE4
0x18000adb8  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000adbf  mov     r8d, 0C0000095h
0x18000adc5  mov     ebx, r8d
0x18000adc8  test    rax, rax
0x18000adcb  jz      loc_18000AE9F
0x18000add1  lea     rdx, qword_18000F290
0x18000add8  lea     rcx, a0_21; ".0"
0x18000addf  jmp     loc_18000AE9A
0x18000ade4  mov     r8, r15; path
0x18000ade7  lea     rdx, [rbp+bufferLength]; pathLength
0x18000adeb  mov     rcx, rdi; packageFullName
0x18000adee  call    cs:__imp_GetStagedPackagePathByFullName
0x18000adf4  test    eax, eax
0x18000adf6  jz      short loc_18000AE21
0x18000adf8  movzx   ebx, ax
0x18000adfb  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ae02  or      ebx, 80070000h
0x18000ae08  test    rax, rax
0x18000ae0b  jz      loc_18000AE9F
0x18000ae11  lea     rdx, asc_18000F1A0; "<>"
0x18000ae18  lea     rcx, a0_22; ".0"
0x18000ae1f  jmp     short loc_18000AE97
0x18000ae21  mov     rcx, rbx
0x18000ae24  call    AiAlloc
0x18000ae29  mov     r14, rax
0x18000ae2c  test    rax, rax
0x18000ae2f  jnz     short loc_18000AE56
0x18000ae31  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ae38  mov     r8d, 0C0000017h
0x18000ae3e  mov     ebx, r8d
0x18000ae41  test    rax, rax
0x18000ae44  jz      short loc_18000AE9F
0x18000ae46  lea     rdx, qword_18000F1E0
0x18000ae4d  lea     rcx, a0_23; ".0"
0x18000ae54  jmp     short loc_18000AE9A
0x18000ae56  lea     rax, aAppxsignatureP; "AppxSignature.p7x"
0x18000ae5d  mov     r9, r15
0x18000ae60  lea     r8, aSS; "%s\\%s"
0x18000ae67  mov     [rsp+48h+var_28], rax
0x18000ae6c  mov     rdx, rbx; unsigned __int64
0x18000ae6f  mov     rcx, r14; unsigned __int16 *
0x18000ae72  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ae77  mov     ebx, eax
0x18000ae79  test    eax, eax
0x18000ae7b  jns     short loc_18000AE9F
0x18000ae7d  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000ae84  test    rax, rax
0x18000ae87  jz      short loc_18000AE9F
0x18000ae89  lea     rdx, asc_18000F1C0; "$&"
0x18000ae90  lea     rcx, a0_24; ".0"
0x18000ae97  mov     r8d, ebx
0x18000ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9f  mov     rcx, gs:60h
0x18000aea8  mov     r8, r15; P
0x18000aeab  xor     edx, edx; Flags
0x18000aead  mov     rcx, [rcx+30h]; HeapHandle
0x18000aeb1  call    cs:__imp_RtlFreeHeap
0x18000aeb7  test    ebx, ebx
0x18000aeb9  js      short loc_18000AEC5
0x18000aebb  mov     [r12], r14
0x18000aebf  mov     [r13+0], rsi
0x18000aec3  jmp     short loc_18000AEF5
0x18000aec5  mov     rcx, gs:60h
0x18000aece  mov     r8, r14; P
0x18000aed1  xor     edx, edx; Flags
0x18000aed3  mov     rcx, [rcx+30h]; HeapHandle
0x18000aed7  call    cs:__imp_RtlFreeHeap
0x18000aedd  mov     rcx, gs:60h
0x18000aee6  mov     r8, rsi; P
0x18000aee9  xor     edx, edx; Flags
0x18000aeeb  mov     rcx, [rcx+30h]; HeapHandle
0x18000aeef  call    cs:__imp_RtlFreeHeap
0x18000aef5  mov     eax, ebx
0x18000aef7  add     rsp, 48h
0x18000aefb  pop     r15
0x18000aefd  pop     r14
0x18000aeff  pop     r13
0x18000af01  pop     r12
0x18000af03  pop     rdi
0x18000af04  pop     rsi
0x18000af05  pop     rbx
0x18000af06  pop     rbp
0x18000af07  retn
```
