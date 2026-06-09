# GetFilenameInAppContainerStorage(ushort *,uint,void *,ushort const *,...)

- ea: `0x180003210`
- end: `0x180003345`
- name: `?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ`
- size: `309`
- prototype: `__int64(unsigned __int16 *, unsigned int, PSID Sid, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002c40`
- `0x180002f40`
- `0x18003d734`
- `0x18005151c`

## callees

- `0x180003210`
- `0x180003710`
- `0x180045380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000327f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000327f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003235`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003235`
- `USERENV!GetAppContainerFolderPath` at `0x180003252`
- `USERENV!GetAppContainerFolderPath` at `0x180003252`

## pseudocode

```c
__int64 GetFilenameInAppContainerStorage(
        unsigned __int16 *a1,
        unsigned int a2,
        PSID Sid,
        const unsigned __int16 *a4,
        ...)
{
  int AppContainerFolderPath; // edi
  __int64 v8; // rax
  unsigned __int16 *v9; // r14
  unsigned int v10; // esi
  wchar_t *v11; // rcx
  size_t v12; // rbx
  int v13; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[3]; // [rsp+28h] [rbp-40h] BYREF
  va_list Args; // [rsp+90h] [rbp+28h] BYREF

  va_start(Args, a4);
  StringSid = 0;
  pv[0] = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    return 2147500037LL;
  AppContainerFolderPath = GetAppContainerFolderPath(StringSid, pv);
  if ( AppContainerFolderPath >= 0 )
  {
    AppContainerFolderPath = StringCchPrintfW(a1, a2, L"%s\\", pv[0]);
    if ( AppContainerFolderPath >= 0 && a4 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a1[v8] );
      v9 = &a1[v8];
      v10 = a2 - v8;
      if ( v10 )
      {
        if ( v10 > 0x7FFFFFFF )
        {
          AppContainerFolderPath = -2147024809;
          *v9 = 0;
        }
        else
        {
          v11 = &a1[v8];
          v12 = v10 - 1LL;
          v13 = vsnwprintf(v11, v12, a4, Args);
          if ( v13 < 0 || v13 > v12 )
          {
            v9[v12] = 0;
            AppContainerFolderPath = -2147024774;
          }
          else
          {
            AppContainerFolderPath = 0;
            if ( v13 == v12 )
              v9[v12] = 0;
          }
        }
      }
      else
      {
        AppContainerFolderPath = -2147024809;
      }
    }
    CoTaskMemFree(pv[0]);
  }
  LocalFree(StringSid);
  return (unsigned int)AppContainerFolderPath;
}

```

## disassembly

```asm
0x180003210  mov     [rsp+Format], r9
0x180003215  push    rbx
0x180003216  push    rbp
0x180003217  push    rsi
0x180003218  sub     rsp, 50h
0x18000321c  mov     esi, edx
0x18000321e  mov     rbx, rcx
0x180003221  xor     ebp, ebp
0x180003223  lea     rdx, [rsp+68h+StringSid]; StringSid
0x180003228  mov     rcx, r8; Sid
0x18000322b  mov     [rsp+68h+StringSid], rbp
0x180003230  mov     [rsp+68h+pv], rbp
0x180003235  call    cs:__imp_ConvertSidToStringSidW
0x18000323b  test    eax, eax
0x18000323d  jz      loc_18000331E
0x180003243  mov     rcx, [rsp+68h+StringSid]
0x180003248  lea     rdx, [rsp+68h+pv]
0x18000324d  mov     [rsp+68h+var_20], rdi
0x180003252  call    cs:__imp_GetAppContainerFolderPath
0x180003258  mov     edi, eax
0x18000325a  test    eax, eax
0x18000325c  js      short loc_180003285
0x18000325e  mov     r9, [rsp+68h+pv]
0x180003263  lea     r8, aS_4; "%s\\"
0x18000326a  mov     edx, esi; unsigned __int64
0x18000326c  mov     rcx, rbx; unsigned __int16 *
0x18000326f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003274  mov     edi, eax
0x180003276  test    eax, eax
0x180003278  jns     short loc_18000329F
0x18000327a  mov     rcx, [rsp+68h+pv]; pv
0x18000327f  call    cs:__imp_CoTaskMemFree
0x180003285  mov     rcx, [rsp+68h+StringSid]; hMem
0x18000328a  call    cs:__imp_LocalFree
0x180003290  mov     eax, edi
0x180003292  mov     rdi, [rsp+68h+var_20]
0x180003297  add     rsp, 50h
0x18000329b  pop     rsi
0x18000329c  pop     rbp
0x18000329d  pop     rbx
0x18000329e  retn
0x18000329f  mov     r8, [rsp+68h+Format]; Format
0x1800032a7  test    r8, r8
0x1800032aa  jz      short loc_18000327A
0x1800032ac  mov     [rsp+68h+var_28], r14
0x1800032b1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800032b8  nop     dword ptr [rax+rax+00000000h]
0x1800032c0  inc     rax
0x1800032c3  cmp     [rbx+rax*2], bp
0x1800032c7  jnz     short loc_1800032C0
0x1800032c9  lea     r14, [rbx+rax*2]
0x1800032cd  lea     r9, [rsp+68h+Args]; Args
0x1800032d5  sub     esi, eax
0x1800032d7  jz      short loc_180003336
0x1800032d9  cmp     esi, 7FFFFFFFh
0x1800032df  ja      short loc_180003328
0x1800032e1  mov     ebx, esi
0x1800032e3  mov     rcx, r14; Buffer
0x1800032e6  dec     rbx
0x1800032e9  mov     rdx, rbx; BufferCount
0x1800032ec  call    _vsnwprintf
0x1800032f1  test    eax, eax
0x1800032f3  js      short loc_18000330A
0x1800032f5  cdqe
0x1800032f7  cmp     rax, rbx
0x1800032fa  ja      short loc_18000330A
0x1800032fc  mov     edi, ebp
0x1800032fe  jz      short loc_18000332F
0x180003300  mov     r14, [rsp+68h+var_28]
0x180003305  jmp     loc_18000327A
0x18000330a  mov     [r14+rbx*2], bp
0x18000330f  mov     edi, 8007007Ah
0x180003314  mov     r14, [rsp+68h+var_28]
0x180003319  jmp     loc_18000327A
0x18000331e  mov     eax, 80004005h
0x180003323  jmp     loc_180003297
0x180003328  mov     edi, 80070057h
0x18000332d  jmp     short loc_18000333F
0x18000332f  mov     [r14+rbx*2], bp
0x180003334  jmp     short loc_180003300
0x180003336  mov     edi, 80070057h
0x18000333b  test    esi, esi
0x18000333d  jz      short loc_180003300
0x18000333f  mov     [r14], bp
0x180003343  jmp     short loc_180003300
```
