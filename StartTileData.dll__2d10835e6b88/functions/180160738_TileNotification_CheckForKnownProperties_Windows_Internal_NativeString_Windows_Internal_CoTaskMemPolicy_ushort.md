# TileNotification::CheckForKnownProperties(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue> &,TileNotification::RecursedPayloadInfo *)

- ea: `0x180160738`
- end: `0x180160b52`
- name: `?CheckForKnownProperties@TileNotification@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAV?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@PEAURecursedPayloadInfo@1@@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801db28c`

## callees

- `0x180160738`
- `0x180161204`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801607a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160831`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801608be`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160947`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801609d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160a5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160aea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801607a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160831`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801608be`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160947`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801609d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160a5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180160aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801607c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801608dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801609f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801607c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801608dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801609f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160b0d`

## string_xrefs

- `0x180160b32`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\tilenotification.cpp`
- `0x1801608b7`: `hint-originalTemplate`
- `0x180160940`: `template`

## pseudocode

```c
__int64 __fastcall TileNotification::CheckForKnownProperties(__int64 a1, __int64 a2, __int64 *a3, __int64 a4)
{
  __int64 v5; // rdx
  const WCHAR *v8; // rcx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, __int64); // rdi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  const WCHAR *v14; // rcx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64); // rdi
  __int64 v17; // rdx
  const WCHAR *v18; // rcx
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, __int64); // rdi
  __int64 v21; // rdx
  const WCHAR *v22; // rcx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, __int64); // rdi
  __int64 v25; // rdx
  const WCHAR *v26; // rcx
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, __int64); // rdi
  __int64 v29; // rdx
  const WCHAR *v30; // rcx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64); // rdi
  __int64 v33; // rdx
  const WCHAR *v34; // rcx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64); // rdi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = *(_QWORD *)(a2 + 8);
  if ( v5 != -1 )
  {
    v8 = *(const WCHAR **)a2;
    if ( *(_QWORD *)a2 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !*(_QWORD *)a2 )
  {
    LODWORD(v5) = 0;
LABEL_8:
    v8 = &String1;
    goto LABEL_9;
  }
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v5) );
  v8 = *(const WCHAR **)a2;
LABEL_9:
  if ( CompareStringOrdinal(v8, v5, L"displayName", -1, 1) == 2 )
  {
    *(_BYTE *)(a4 + 2) = 1;
    v9 = *a3;
    v10 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 152LL);
    WindowsDeleteString(*(HSTRING *)(a4 + 24));
    *(_QWORD *)(a4 + 24) = 0;
    v11 = v10(v9, a4 + 24);
    if ( v11 < 0 )
    {
      v12 = 1141;
LABEL_78:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\tilenotification.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
      return 0;
    }
    return 0;
  }
  v13 = *(_QWORD *)(a2 + 8);
  if ( v13 != -1 )
  {
    v14 = *(const WCHAR **)a2;
    if ( *(_QWORD *)a2 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( !*(_QWORD *)a2 )
  {
    LODWORD(v13) = 0;
LABEL_19:
    v14 = &String1;
    goto LABEL_20;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v13) );
  v14 = *(const WCHAR **)a2;
LABEL_20:
  if ( CompareStringOrdinal(v14, v13, L"branding", -1, 1) != 2 )
  {
    v17 = *(_QWORD *)(a2 + 8);
    if ( v17 == -1 )
    {
      if ( *(_QWORD *)a2 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v17) );
        v18 = *(const WCHAR **)a2;
LABEL_31:
        if ( CompareStringOrdinal(v18, v17, L"hint-originalTemplate", -1, 1) == 2 )
        {
          v19 = *a3;
          v20 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 152LL);
          WindowsDeleteString(*(HSTRING *)(a4 + 8));
          *(_QWORD *)(a4 + 8) = 0;
          v11 = v20(v19, a4 + 8);
          if ( v11 < 0 )
          {
            v12 = 1153;
            goto LABEL_78;
          }
          return 0;
        }
        v21 = *(_QWORD *)(a2 + 8);
        if ( v21 == -1 )
        {
          if ( *(_QWORD *)a2 )
          {
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v21) );
            v22 = *(const WCHAR **)a2;
LABEL_42:
            if ( CompareStringOrdinal(v22, v21, L"template", -1, 1) == 2 )
            {
              v23 = *a3;
              v24 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 152LL);
              WindowsDeleteString(*(HSTRING *)(a4 + 16));
              *(_QWORD *)(a4 + 16) = 0;
              v11 = v24(v23, a4 + 16);
              if ( v11 < 0 )
              {
                v12 = 1159;
                goto LABEL_78;
              }
              return 0;
            }
            v25 = *(_QWORD *)(a2 + 8);
            if ( v25 == -1 )
            {
              if ( *(_QWORD *)a2 )
              {
                v25 = -1;
                do
                  ++v25;
                while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v25) );
                v26 = *(const WCHAR **)a2;
LABEL_53:
                if ( CompareStringOrdinal(v26, v25, L"hint-overlay", -1, 1) == 2 )
                {
                  *(_BYTE *)(a4 + 4) = 1;
                  v27 = *a3;
                  v28 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 152LL);
                  WindowsDeleteString(*(HSTRING *)(a4 + 40));
                  *(_QWORD *)(a4 + 40) = 0;
                  v11 = v28(v27, a4 + 40);
                  if ( v11 < 0 )
                  {
                    v12 = 1165;
                    goto LABEL_78;
                  }
                  return 0;
                }
                v29 = *(_QWORD *)(a2 + 8);
                if ( v29 == -1 )
                {
                  if ( *(_QWORD *)a2 )
                  {
                    v29 = -1;
                    do
                      ++v29;
                    while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v29) );
                    v30 = *(const WCHAR **)a2;
LABEL_64:
                    if ( CompareStringOrdinal(v30, v29, L"hint-presentation", -1, 1) == 2 )
                    {
                      *(_BYTE *)(a4 + 5) = 1;
                      v31 = *a3;
                      v32 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 152LL);
                      WindowsDeleteString(*(HSTRING *)(a4 + 48));
                      *(_QWORD *)(a4 + 48) = 0;
                      v11 = v32(v31, a4 + 48);
                      if ( v11 < 0 )
                      {
                        v12 = 1171;
                        goto LABEL_78;
                      }
                      return 0;
                    }
                    v33 = *(_QWORD *)(a2 + 8);
                    if ( v33 == -1 )
                    {
                      if ( *(_QWORD *)a2 )
                      {
                        v33 = -1;
                        do
                          ++v33;
                        while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v33) );
                        v34 = *(const WCHAR **)a2;
LABEL_75:
                        if ( CompareStringOrdinal(v34, v33, L"arguments", -1, 1) == 2 )
                        {
                          *(_BYTE *)(a4 + 6) = 1;
                          v35 = *a3;
                          v36 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 152LL);
                          WindowsDeleteString(*(HSTRING *)(a4 + 56));
                          *(_QWORD *)(a4 + 56) = 0;
                          v11 = v36(v35, a4 + 56);
                          if ( v11 < 0 )
                          {
                            v12 = 1176;
                            goto LABEL_78;
                          }
                        }
                        return 0;
                      }
                      LODWORD(v33) = 0;
                    }
                    else
                    {
                      v34 = *(const WCHAR **)a2;
                      if ( *(_QWORD *)a2 )
                        goto LABEL_75;
                    }
                    v34 = &String1;
                    goto LABEL_75;
                  }
                  LODWORD(v29) = 0;
                }
                else
                {
                  v30 = *(const WCHAR **)a2;
                  if ( *(_QWORD *)a2 )
                    goto LABEL_64;
                }
                v30 = &String1;
                goto LABEL_64;
              }
              LODWORD(v25) = 0;
            }
            else
            {
              v26 = *(const WCHAR **)a2;
              if ( *(_QWORD *)a2 )
                goto LABEL_53;
            }
            v26 = &String1;
            goto LABEL_53;
          }
          LODWORD(v21) = 0;
        }
        else
        {
          v22 = *(const WCHAR **)a2;
          if ( *(_QWORD *)a2 )
            goto LABEL_42;
        }
        v22 = &String1;
        goto LABEL_42;
      }
      LODWORD(v17) = 0;
    }
    else
    {
      v18 = *(const WCHAR **)a2;
      if ( *(_QWORD *)a2 )
        goto LABEL_31;
    }
    v18 = &String1;
    goto LABEL_31;
  }
  *(_BYTE *)(a4 + 3) = 1;
  v15 = *a3;
  v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 152LL);
  WindowsDeleteString(*(HSTRING *)(a4 + 32));
  *(_QWORD *)(a4 + 32) = 0;
  v11 = v16(v15, a4 + 32);
  if ( v11 < 0 )
  {
    v12 = 1147;
    goto LABEL_78;
  }
  return 0;
}

```

## disassembly

```asm
0x180160738  push    rbx
0x18016073a  push    rbp
0x18016073b  push    rsi
0x18016073c  push    rdi
0x18016073d  push    r12
0x18016073f  push    r14
0x180160741  push    r15
0x180160743  sub     rsp, 30h
0x180160747  mov     rbx, rdx
0x18016074a  lea     r15, String1
0x180160751  mov     rdx, [rdx+8]; cchCount1
0x180160755  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180160759  xor     ebp, ebp
0x18016075b  mov     r14, r9
0x18016075e  mov     rsi, r8
0x180160761  cmp     rdx, rdi
0x180160764  jnz     short loc_180160784
0x180160766  mov     rax, [rbx]
0x180160769  test    rax, rax
0x18016076c  jz      short loc_18016077F
0x18016076e  mov     rdx, rdi
0x180160771  inc     rdx
0x180160774  cmp     [rax+rdx*2], bp
0x180160778  jnz     short loc_180160771
0x18016077a  mov     rcx, rax
0x18016077d  jmp     short loc_18016078F
0x18016077f  mov     rdx, rbp
0x180160782  jmp     short loc_18016078C
0x180160784  mov     rcx, [rbx]
0x180160787  test    rcx, rcx
0x18016078a  jnz     short loc_18016078F
0x18016078c  mov     rcx, r15; lpString1
0x18016078f  mov     r12d, 1
0x180160795  lea     r8, aDisplayname_0; "displayName"
0x18016079c  mov     r9d, edi; cchCount2
0x18016079f  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x1801607a4  call    cs:__imp_CompareStringOrdinal
0x1801607aa  cmp     eax, 2
0x1801607ad  jnz     short loc_1801607F0
0x1801607af  mov     [r14+2], r12b
0x1801607b3  lea     rbx, [r14+18h]
0x1801607b7  mov     rsi, [rsi]
0x1801607ba  mov     rcx, [rbx]; string
0x1801607bd  mov     rax, [rsi]
0x1801607c0  mov     rdi, [rax+98h]
0x1801607c7  call    cs:__imp_WindowsDeleteString
0x1801607cd  mov     rdx, rbx
0x1801607d0  mov     [rbx], rbp
0x1801607d3  mov     rcx, rsi
0x1801607d6  mov     rax, rdi
0x1801607d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801607de  test    eax, eax
0x1801607e0  jns     loc_180160B41
0x1801607e6  mov     edx, 475h
0x1801607eb  jmp     loc_180160B2D
0x1801607f0  mov     rdx, [rbx+8]; cchCount1
0x1801607f4  cmp     rdx, rdi
0x1801607f7  jnz     short loc_180160817
0x1801607f9  mov     rax, [rbx]
0x1801607fc  test    rax, rax
0x1801607ff  jz      short loc_180160812
0x180160801  mov     rdx, rdi
0x180160804  inc     rdx
0x180160807  cmp     [rax+rdx*2], bp
0x18016080b  jnz     short loc_180160804
0x18016080d  mov     rcx, rax
0x180160810  jmp     short loc_180160822
0x180160812  mov     rdx, rbp
0x180160815  jmp     short loc_18016081F
0x180160817  mov     rcx, [rbx]
0x18016081a  test    rcx, rcx
0x18016081d  jnz     short loc_180160822
0x18016081f  mov     rcx, r15; lpString1
0x180160822  mov     r9d, edi; cchCount2
0x180160825  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x18016082a  lea     r8, aBranding; "branding"
0x180160831  call    cs:__imp_CompareStringOrdinal
0x180160837  cmp     eax, 2
0x18016083a  jnz     short loc_18016087D
0x18016083c  mov     [r14+3], r12b
0x180160840  lea     rbx, [r14+20h]
0x180160844  mov     rsi, [rsi]
0x180160847  mov     rcx, [rbx]; string
0x18016084a  mov     rax, [rsi]
0x18016084d  mov     rdi, [rax+98h]
0x180160854  call    cs:__imp_WindowsDeleteString
0x18016085a  mov     rdx, rbx
0x18016085d  mov     [rbx], rbp
0x180160860  mov     rcx, rsi
0x180160863  mov     rax, rdi
0x180160866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016086b  test    eax, eax
0x18016086d  jns     loc_180160B41
0x180160873  mov     edx, 47Bh
0x180160878  jmp     loc_180160B2D
0x18016087d  mov     rdx, [rbx+8]; cchCount1
0x180160881  cmp     rdx, rdi
0x180160884  jnz     short loc_1801608A4
0x180160886  mov     rax, [rbx]
0x180160889  test    rax, rax
0x18016088c  jz      short loc_18016089F
0x18016088e  mov     rdx, rdi
0x180160891  inc     rdx
0x180160894  cmp     [rax+rdx*2], bp
0x180160898  jnz     short loc_180160891
0x18016089a  mov     rcx, rax
0x18016089d  jmp     short loc_1801608AF
0x18016089f  mov     rdx, rbp
0x1801608a2  jmp     short loc_1801608AC
0x1801608a4  mov     rcx, [rbx]
0x1801608a7  test    rcx, rcx
0x1801608aa  jnz     short loc_1801608AF
0x1801608ac  mov     rcx, r15; lpString1
0x1801608af  mov     r9d, edi; cchCount2
0x1801608b2  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x1801608b7  lea     r8, aHintOriginalte; "hint-originalTemplate"
0x1801608be  call    cs:__imp_CompareStringOrdinal
0x1801608c4  cmp     eax, 2
0x1801608c7  jnz     short loc_180160906
0x1801608c9  mov     rsi, [rsi]
0x1801608cc  lea     rbx, [r14+8]
0x1801608d0  mov     rcx, [rbx]; string
0x1801608d3  mov     rax, [rsi]
0x1801608d6  mov     rdi, [rax+98h]
0x1801608dd  call    cs:__imp_WindowsDeleteString
0x1801608e3  mov     rdx, rbx
0x1801608e6  mov     [rbx], rbp
0x1801608e9  mov     rcx, rsi
0x1801608ec  mov     rax, rdi
0x1801608ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801608f4  test    eax, eax
0x1801608f6  jns     loc_180160B41
0x1801608fc  mov     edx, 481h
0x180160901  jmp     loc_180160B2D
0x180160906  mov     rdx, [rbx+8]; cchCount1
0x18016090a  cmp     rdx, rdi
0x18016090d  jnz     short loc_18016092D
0x18016090f  mov     rax, [rbx]
0x180160912  test    rax, rax
0x180160915  jz      short loc_180160928
0x180160917  mov     rdx, rdi
0x18016091a  inc     rdx
0x18016091d  cmp     [rax+rdx*2], bp
0x180160921  jnz     short loc_18016091A
0x180160923  mov     rcx, rax
0x180160926  jmp     short loc_180160938
0x180160928  mov     rdx, rbp
0x18016092b  jmp     short loc_180160935
0x18016092d  mov     rcx, [rbx]
0x180160930  test    rcx, rcx
0x180160933  jnz     short loc_180160938
0x180160935  mov     rcx, r15; lpString1
0x180160938  mov     r9d, edi; cchCount2
0x18016093b  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x180160940  lea     r8, aTemplate; "template"
0x180160947  call    cs:__imp_CompareStringOrdinal
0x18016094d  cmp     eax, 2
0x180160950  jnz     short loc_18016098F
0x180160952  mov     rsi, [rsi]
0x180160955  lea     rbx, [r14+10h]
0x180160959  mov     rcx, [rbx]; string
0x18016095c  mov     rax, [rsi]
0x18016095f  mov     rdi, [rax+98h]
0x180160966  call    cs:__imp_WindowsDeleteString
0x18016096c  mov     rdx, rbx
0x18016096f  mov     [rbx], rbp
0x180160972  mov     rcx, rsi
0x180160975  mov     rax, rdi
0x180160978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016097d  test    eax, eax
0x18016097f  jns     loc_180160B41
0x180160985  mov     edx, 487h
0x18016098a  jmp     loc_180160B2D
0x18016098f  mov     rdx, [rbx+8]; cchCount1
0x180160993  cmp     rdx, rdi
0x180160996  jnz     short loc_1801609B6
0x180160998  mov     rax, [rbx]
0x18016099b  test    rax, rax
0x18016099e  jz      short loc_1801609B1
0x1801609a0  mov     rdx, rdi
0x1801609a3  inc     rdx
0x1801609a6  cmp     [rax+rdx*2], bp
0x1801609aa  jnz     short loc_1801609A3
0x1801609ac  mov     rcx, rax
0x1801609af  jmp     short loc_1801609C1
0x1801609b1  mov     rdx, rbp
0x1801609b4  jmp     short loc_1801609BE
0x1801609b6  mov     rcx, [rbx]
0x1801609b9  test    rcx, rcx
0x1801609bc  jnz     short loc_1801609C1
0x1801609be  mov     rcx, r15; lpString1
0x1801609c1  mov     r9d, edi; cchCount2
0x1801609c4  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x1801609c9  lea     r8, aHintOverlay; "hint-overlay"
0x1801609d0  call    cs:__imp_CompareStringOrdinal
0x1801609d6  cmp     eax, 2
0x1801609d9  jnz     short loc_180160A1C
0x1801609db  mov     [r14+4], r12b
0x1801609df  lea     rbx, [r14+28h]
0x1801609e3  mov     rsi, [rsi]
0x1801609e6  mov     rcx, [rbx]; string
0x1801609e9  mov     rax, [rsi]
0x1801609ec  mov     rdi, [rax+98h]
0x1801609f3  call    cs:__imp_WindowsDeleteString
0x1801609f9  mov     rdx, rbx
0x1801609fc  mov     [rbx], rbp
0x1801609ff  mov     rcx, rsi
0x180160a02  mov     rax, rdi
0x180160a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a0a  test    eax, eax
0x180160a0c  jns     loc_180160B41
0x180160a12  mov     edx, 48Dh
0x180160a17  jmp     loc_180160B2D
0x180160a1c  mov     rdx, [rbx+8]; cchCount1
0x180160a20  cmp     rdx, rdi
0x180160a23  jnz     short loc_180160A43
0x180160a25  mov     rax, [rbx]
0x180160a28  test    rax, rax
0x180160a2b  jz      short loc_180160A3E
0x180160a2d  mov     rdx, rdi
0x180160a30  inc     rdx
0x180160a33  cmp     [rax+rdx*2], bp
0x180160a37  jnz     short loc_180160A30
0x180160a39  mov     rcx, rax
0x180160a3c  jmp     short loc_180160A4E
0x180160a3e  mov     rdx, rbp
0x180160a41  jmp     short loc_180160A4B
0x180160a43  mov     rcx, [rbx]
0x180160a46  test    rcx, rcx
0x180160a49  jnz     short loc_180160A4E
0x180160a4b  mov     rcx, r15; lpString1
0x180160a4e  mov     r9d, edi; cchCount2
0x180160a51  mov     [rsp+68h+bIgnoreCase], r12d; bIgnoreCase
0x180160a56  lea     r8, aHintPresentati; "hint-presentation"
0x180160a5d  call    cs:__imp_CompareStringOrdinal
0x180160a63  cmp     eax, 2
0x180160a66  jnz     short loc_180160AA9
0x180160a68  mov     [r14+5], r12b
0x180160a6c  lea     rbx, [r14+30h]
0x180160a70  mov     rsi, [rsi]
0x180160a73  mov     rcx, [rbx]; string
0x180160a76  mov     rax, [rsi]
0x180160a79  mov     rdi, [rax+98h]
0x180160a80  call    cs:__imp_WindowsDeleteString
0x180160a86  mov     rdx, rbx
0x180160a89  mov     [rbx], rbp
0x180160a8c  mov     rcx, rsi
0x180160a8f  mov     rax, rdi
0x180160a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a97  test    eax, eax
0x180160a99  jns     loc_180160B41
0x180160a9f  mov     edx, 493h
0x180160aa4  jmp     loc_180160B2D
0x180160aa9  mov     rdx, [rbx+8]; cchCount1
0x180160aad  cmp     rdx, rdi
0x180160ab0  jnz     short loc_180160AD0
0x180160ab2  mov     rax, [rbx]
0x180160ab5  test    rax, rax
0x180160ab8  jz      short loc_180160ACB
0x180160aba  mov     rdx, rdi
0x180160abd  inc     rdx
0x180160ac0  cmp     [rax+rdx*2], bp
0x180160ac4  jnz     short loc_180160ABD
0x180160ac6  mov     rcx, rax
0x180160ac9  jmp     short loc_180160ADB
0x180160acb  mov     rdx, rbp
0x180160ace  jmp     short loc_180160AD8
0x180160ad0  mov     rcx, [rbx]
0x180160ad3  test    rcx, rcx
0x180160ad6  jnz     short loc_180160ADB
0x180160ad8  mov     rcx, r15; lpString1
0x180160adb  mov     r9d, edi; cchCount2
0x180160ade  mov     [rsp+68h+bIgnoreCase], r12d; int
0x180160ae3  lea     r8, aArguments; "arguments"
0x180160aea  call    cs:__imp_CompareStringOrdinal
0x180160af0  cmp     eax, 2
0x180160af3  jnz     short loc_180160B41
0x180160af5  mov     [r14+6], r12b
0x180160af9  lea     rbx, [r14+38h]
0x180160afd  mov     rsi, [rsi]
0x180160b00  mov     rcx, [rbx]; string
0x180160b03  mov     rax, [rsi]
0x180160b06  mov     rdi, [rax+98h]
0x180160b0d  call    cs:__imp_WindowsDeleteString
0x180160b13  mov     rdx, rbx
0x180160b16  mov     [rbx], rbp
0x180160b19  mov     rcx, rsi
0x180160b1c  mov     rax, rdi
0x180160b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160b24  test    eax, eax
0x180160b26  jns     short loc_180160B41
0x180160b28  mov     edx, 498h; void *
0x180160b2d  mov     rcx, [rsp+68h]; this
0x180160b32  lea     r8, aShellcommonShe_221; "shellcommon\\shell\\tiles\\sharedmodel"...
0x180160b39  mov     r9d, eax; char *
0x180160b3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180160b41  xor     eax, eax
0x180160b43  add     rsp, 30h
0x180160b47  pop     r15
0x180160b49  pop     r14
  ... truncated ...
```
