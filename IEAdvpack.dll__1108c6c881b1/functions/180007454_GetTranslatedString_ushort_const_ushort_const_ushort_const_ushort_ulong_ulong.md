# GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)

- ea: `0x180007454`
- end: `0x18000769f`
- name: `?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z`
- size: `587`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpAppName, LPCWSTR lpKeyName, unsigned __int16 *, DWORD, unsigned int *)`
- caller_count: `21`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180002ad4`
- `0x1800040e0`
- `0x180004880`
- `0x180005584`
- `0x180005f80`
- `0x180008330`
- `0x180009928`
- `0x18000a0c0`
- `0x18000a24c`
- `0x18000a428`
- `0x18000a61c`
- `0x18000c0c0`
- `0x18000d564`
- `0x18000d7ac`
- `0x18000dbec`
- `0x18000de30`
- `0x18000e060`
- `0x18000ef90`
- `0x18000f7b0`
- `0x180010050`
- `0x1800114d0`

## callees

- `0x1800020a0`
- `0x1800021dc`
- `0x1800022bc`
- `0x1800045e8`
- `0x180006068`
- `0x180007454`
- `0x180007968`
- `0x180008ec4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007637`
- `KERNEL32!GetLastError` at `0x180007637`
- `KERNEL32!LocalFree` at `0x1800075bc`
- `KERNEL32!LocalFree` at `0x180007678`
- `KERNEL32!LocalFree` at `0x180007686`
- `KERNEL32!LocalFree` at `0x1800075bc`
- `KERNEL32!LocalFree` at `0x180007678`
- `KERNEL32!LocalFree` at `0x180007686`
- `KERNEL32!LocalAlloc` at `0x1800074f9`
- `KERNEL32!LocalAlloc` at `0x180007509`
- `KERNEL32!LocalAlloc` at `0x1800075ce`
- `KERNEL32!LocalAlloc` at `0x1800074f9`
- `KERNEL32!LocalAlloc` at `0x180007509`
- `KERNEL32!LocalAlloc` at `0x1800075ce`

## pseudocode

```c
__int64 __fastcall GetTranslatedString(
        const unsigned __int16 *a1,
        LPCWSTR lpAppName,
        LPCWSTR lpKeyName,
        unsigned __int16 *a4,
        DWORD a5,
        unsigned int *a6)
{
  unsigned __int16 *v6; // rdi
  signed int v11; // ebx
  int v12; // r13d
  WCHAR *v13; // rbp
  WCHAR *v14; // rax
  int v15; // r8d
  __int64 v16; // rax
  int LineText; // eax
  signed int LastError; // eax
  DWORD ReturnBufferSize; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+34h] [rbp-54h]

  v6 = 0;
  ReturnBufferSize = 0;
  v21 = 0;
  v11 = 0;
  v12 = 0;
  if ( hLibModule )
  {
    if ( !InfHandle )
      MySetupOpenInfFile(a1);
    goto LABEL_11;
  }
  if ( !(unsigned int)CheckOSVersion() || !ctx )
  {
    v12 = dword_1800257F8;
    dword_1800257F8 = 1;
    v21 = 1;
    goto LABEL_11;
  }
  v13 = 0;
  dword_1800257F8 = 0;
  if ( !(unsigned int)InitializeSetupAPI() )
  {
    v11 = -2147024809;
    goto LABEL_35;
  }
  v11 = MySetupOpenInfFile(a1);
  if ( v11 >= 0 )
  {
LABEL_11:
    v13 = (WCHAR *)LocalAlloc(0x40u, 0x1000u);
    v14 = (WCHAR *)LocalAlloc(0x40u, 0x2000u);
    v6 = v14;
    if ( v13 && v14 )
    {
      if ( dword_1800257F8 == 1 )
      {
        if ( !(unsigned int)MyGetPrivateProfileString(a1, lpAppName, lpKeyName, v13, 0x800u) )
        {
          v11 = -2147024809;
          goto LABEL_33;
        }
        if ( hLibModule )
        {
          v11 = -2147418113;
          goto LABEL_33;
        }
        FormStrWithoutPlaceHolders(v13, v6, v15, a1);
        v16 = -1;
        do
          ++v16;
        while ( v6[v16] );
        ReturnBufferSize = v16 + 1;
        goto LABEL_25;
      }
      LineText = MySetupGetLineText(lpAppName, lpKeyName, v14, 0x1000u, &ReturnBufferSize);
      v11 = LineText;
      if ( LineText >= 0 )
      {
LABEL_25:
        if ( a4 )
        {
          if ( ReturnBufferSize <= a5 )
            StringCchCopyW(a4, a5, v6);
          else
            v11 = -2147024774;
        }
        else
        {
          v11 = 0;
        }
LABEL_33:
        if ( v21 )
          dword_1800257F8 = v12;
        goto LABEL_35;
      }
      if ( LineText != -2147024774 )
        goto LABEL_33;
      LocalFree(v6);
      v6 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * ReturnBufferSize);
      if ( v6 )
      {
        v11 = MySetupGetLineText(lpAppName, lpKeyName, v6, ReturnBufferSize, &ReturnBufferSize);
        if ( v11 < 0 )
          goto LABEL_33;
        goto LABEL_25;
      }
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
LABEL_35:
  if ( a6 )
    *a6 = ReturnBufferSize;
  if ( v13 )
    LocalFree(v13);
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007454  push    rbx
0x180007456  push    rbp
0x180007457  push    rsi
0x180007458  push    rdi
0x180007459  push    r12
0x18000745b  push    r13
0x18000745d  push    r14
0x18000745f  push    r15
0x180007461  sub     rsp, 48h
0x180007465  xor     edi, edi
0x180007467  mov     r12, r9
0x18000746a  cmp     cs:hLibModule, rdi
0x180007471  mov     r14, r8
0x180007474  mov     r15, rdx
0x180007477  mov     [rsp+88h+ReturnBufferSize], edi
0x18000747b  mov     rsi, rcx
0x18000747e  mov     [rsp+88h+var_54], edi
0x180007482  lea     ebp, [rdi+1]
0x180007485  mov     ebx, edi
0x180007487  mov     r13d, edi
0x18000748a  jnz     short loc_1800074DF
0x18000748c  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x180007491  test    eax, eax
0x180007493  jz      short loc_1800074CC
0x180007495  cmp     cs:?ctx@@3UADVCONTEXTW@@A, di; ADVCONTEXTW ctx
0x18000749c  jz      short loc_1800074CC
0x18000749e  mov     ebp, edi
0x1800074a0  mov     cs:dword_1800257F8, ebx
0x1800074a6  call    ?InitializeSetupAPI@@YAHXZ; InitializeSetupAPI(void)
0x1800074ab  test    eax, eax
0x1800074ad  jz      short loc_1800074C2
0x1800074af  mov     rcx, rsi; unsigned __int16 *
0x1800074b2  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x1800074b7  mov     ebx, eax
0x1800074b9  test    eax, eax
0x1800074bb  jns     short loc_1800074ED
0x1800074bd  jmp     loc_18000765D
0x1800074c2  mov     ebx, 80070057h
0x1800074c7  jmp     loc_18000765D
0x1800074cc  mov     r13d, cs:dword_1800257F8
0x1800074d3  mov     cs:dword_1800257F8, ebp
0x1800074d9  mov     [rsp+88h+var_54], ebp
0x1800074dd  jmp     short loc_1800074ED
0x1800074df  cmp     cs:InfHandle, rdi
0x1800074e6  jnz     short loc_1800074ED
0x1800074e8  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x1800074ed  mov     edi, 40h ; '@'
0x1800074f2  mov     edx, 1000h; uBytes
0x1800074f7  mov     ecx, edi; uFlags
0x1800074f9  call    cs:__imp_LocalAlloc
0x1800074ff  mov     edx, 2000h; uBytes
0x180007504  mov     ecx, edi; uFlags
0x180007506  mov     rbp, rax
0x180007509  call    cs:__imp_LocalAlloc
0x18000750f  mov     rdi, rax
0x180007512  test    rbp, rbp
0x180007515  jz      loc_180007637
0x18000751b  test    rax, rax
0x18000751e  jz      loc_180007637
0x180007524  cmp     cs:dword_1800257F8, 1
0x18000752b  jnz     short loc_18000758E
0x18000752d  mov     r9, rbp; lpString1
0x180007530  mov     dword ptr [rsp+88h+var_68], 800h; DWORD
0x180007538  mov     r8, r14; lpKeyName
0x18000753b  mov     rdx, r15; lpAppName
0x18000753e  mov     rcx, rsi; lpFileName
0x180007541  call    ?MyGetPrivateProfileString@@YAHPEBG00PEAGK@Z; MyGetPrivateProfileString(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x180007546  xor     r14d, r14d
0x180007549  test    eax, eax
0x18000754b  jnz     short loc_180007557
0x18000754d  mov     ebx, 80070057h
0x180007552  jmp     loc_18000764F
0x180007557  cmp     cs:hLibModule, r14
0x18000755e  jz      short loc_18000756A
0x180007560  mov     ebx, 8000FFFFh
0x180007565  jmp     loc_18000764F
0x18000756a  mov     r9, rsi; unsigned __int16 *
0x18000756d  mov     rdx, rdi; unsigned __int16 *
0x180007570  mov     rcx, rbp; unsigned __int16 *
0x180007573  call    ?FormStrWithoutPlaceHolders@@YAKPEBGPEAGH0@Z; FormStrWithoutPlaceHolders(ushort const *,ushort *,int,ushort const *)
0x180007578  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000757c  inc     rax
0x18000757f  cmp     [rdi+rax*2], r14w
0x180007584  jnz     short loc_18000757C
0x180007586  inc     eax
0x180007588  mov     [rsp+88h+ReturnBufferSize], eax
0x18000758c  jmp     short loc_180007607
0x18000758e  lea     rax, [rsp+88h+ReturnBufferSize]
0x180007593  mov     r9d, 1000h; ReturnBufferSize
0x180007599  mov     r8, rdi; ReturnBuffer
0x18000759c  mov     [rsp+88h+var_68], rax; PDWORD
0x1800075a1  mov     rdx, r14; Key
0x1800075a4  mov     rcx, r15; Section
0x1800075a7  call    ?MySetupGetLineText@@YAJPEBG0PEAGKPEAK@Z; MySetupGetLineText(ushort const *,ushort const *,ushort *,ulong,ulong *)
0x1800075ac  mov     ebx, eax
0x1800075ae  test    eax, eax
0x1800075b0  jns     short loc_180007604
0x1800075b2  cmp     eax, 8007007Ah
0x1800075b7  jnz     short loc_18000760E
0x1800075b9  mov     rcx, rdi; hMem
0x1800075bc  call    cs:__imp_LocalFree
0x1800075c2  mov     edx, [rsp+88h+ReturnBufferSize]
0x1800075c6  mov     ecx, 40h ; '@'; uFlags
0x1800075cb  add     rdx, rdx; uBytes
0x1800075ce  call    cs:__imp_LocalAlloc
0x1800075d4  mov     rdi, rax
0x1800075d7  test    rax, rax
0x1800075da  jz      short loc_180007637
0x1800075dc  mov     r9d, [rsp+88h+ReturnBufferSize]; ReturnBufferSize
0x1800075e1  lea     rax, [rsp+88h+ReturnBufferSize]
0x1800075e6  mov     r8, rdi; ReturnBuffer
0x1800075e9  mov     [rsp+88h+var_68], rax; PDWORD
0x1800075ee  mov     rdx, r14; Key
0x1800075f1  mov     rcx, r15; Section
0x1800075f4  call    ?MySetupGetLineText@@YAJPEBG0PEAGKPEAK@Z; MySetupGetLineText(ushort const *,ushort const *,ushort *,ulong,ulong *)
0x1800075f9  xor     r14d, r14d
0x1800075fc  mov     ebx, eax
0x1800075fe  test    eax, eax
0x180007600  jns     short loc_180007607
0x180007602  jmp     short loc_18000764F
0x180007604  xor     r14d, r14d
0x180007607  test    r12, r12
0x18000760a  jnz     short loc_180007613
0x18000760c  xor     ebx, ebx
0x18000760e  xor     r14d, r14d
0x180007611  jmp     short loc_18000764F
0x180007613  mov     eax, [rsp+88h+arg_20]
0x18000761a  cmp     [rsp+88h+ReturnBufferSize], eax
0x18000761e  jbe     short loc_180007627
0x180007620  mov     ebx, 8007007Ah
0x180007625  jmp     short loc_18000764F
0x180007627  mov     rdx, rax; unsigned __int64
0x18000762a  mov     r8, rdi; unsigned __int16 *
0x18000762d  mov     rcx, r12; unsigned __int16 *
0x180007630  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007635  jmp     short loc_18000764F
0x180007637  call    cs:__imp_GetLastError
0x18000763d  xor     r14d, r14d
0x180007640  mov     ebx, eax
0x180007642  test    eax, eax
0x180007644  jle     short loc_18000764F
0x180007646  movzx   ebx, ax
0x180007649  or      ebx, 80070000h
0x18000764f  cmp     [rsp+88h+var_54], r14d
0x180007654  jz      short loc_18000765D
0x180007656  mov     cs:dword_1800257F8, r13d
0x18000765d  mov     rcx, [rsp+88h+arg_28]
0x180007665  test    rcx, rcx
0x180007668  jz      short loc_180007670
0x18000766a  mov     eax, [rsp+88h+ReturnBufferSize]
0x18000766e  mov     [rcx], eax
0x180007670  test    rbp, rbp
0x180007673  jz      short loc_18000767E
0x180007675  mov     rcx, rbp; hMem
0x180007678  call    cs:__imp_LocalFree
0x18000767e  test    rdi, rdi
0x180007681  jz      short loc_18000768C
0x180007683  mov     rcx, rdi; hMem
0x180007686  call    cs:__imp_LocalFree
0x18000768c  mov     eax, ebx
0x18000768e  add     rsp, 48h
0x180007692  pop     r15
0x180007694  pop     r14
0x180007696  pop     r13
0x180007698  pop     r12
0x18000769a  pop     rdi
0x18000769b  pop     rsi
0x18000769c  pop     rbp
0x18000769d  pop     rbx
0x18000769e  retn
```
