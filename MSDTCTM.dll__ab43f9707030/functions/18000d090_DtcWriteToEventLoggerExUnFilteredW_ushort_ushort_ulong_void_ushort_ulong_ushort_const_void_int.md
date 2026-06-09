# DtcWriteToEventLoggerExUnFilteredW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)

- ea: `0x18000d090`
- end: `0x18000d276`
- name: `?DtcWriteToEventLoggerExUnFilteredW@@YAJGGKPEAXGKPEAPEBG0H@Z`
- size: `486`
- prototype: `int(unsigned __int16, unsigned __int16, unsigned int, void *, unsigned __int16, unsigned int, const unsigned __int16 **, void *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010b40`
- `0x180013e24`
- `0x180085624`

## callees

- `0x18000d090`
- `0x18001075c`
- `0x180025104`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d224`
- `ADVAPI32!DeregisterEventSource` at `0x18000d24e`
- `ADVAPI32!DeregisterEventSource` at `0x18000d24e`
- `ADVAPI32!RegisterEventSourceW` at `0x18000d0de`
- `ADVAPI32!RegisterEventSourceW` at `0x18000d0de`
- `ADVAPI32!ReportEventW` at `0x18000d212`
- `ADVAPI32!ReportEventW` at `0x18000d212`

## pseudocode

```c
__int64 __fastcall DtcWriteToEventLoggerExUnFilteredW(
        char a1,
        WORD a2,
        DWORD a3,
        void *a4,
        WORD wNumStrings,
        unsigned int Size,
        const unsigned __int16 **lpStrings,
        void *Src,
        int a9)
{
  const WCHAR *v12; // rdx
  const WCHAR *v13; // rax
  HANDLE v14; // rbx
  WORD v16; // si
  void *v17; // rbp
  void *lpRawData; // r13
  char *v19; // r14
  int ServiceNameFromTmInstance; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  char *v23; // rax
  unsigned int v24; // edi
  signed int LastError; // eax
  size_t v26; // [rsp+50h] [rbp-38h] BYREF
  unsigned int dwDataSize; // [rsp+A8h] [rbp+20h]
  int v28; // [rsp+D0h] [rbp+48h]

  if ( a9 )
  {
    v12 = L"MSDTC 2";
    v13 = L"MSDTC Client 2";
  }
  else
  {
    v12 = L"MSDTC";
    v13 = L"MSDTC Client";
  }
  if ( !g_fEventSourceMsdtcCore )
    v12 = v13;
  v14 = RegisterEventSourceW(0, v12);
  if ( !v14 )
    return 2147500037LL;
  v16 = a1 & 0x1F;
  v17 = 0;
  lpRawData = Src;
  v19 = 0;
  dwDataSize = Size;
  v26 = 0;
  if ( g_fEventSourceMsdtcCore )
  {
    ServiceNameFromTmInstance = GetServiceNameFromTmInstance((unsigned __int16 **)&v26);
    v17 = (void *)v26;
    if ( ServiceNameFromTmInstance >= 0 )
    {
      if ( v26 )
      {
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v26 + 2 * v21) );
        v22 = 2 * v21;
        LODWORD(v26) = v22;
        if ( Src )
          v22 += Size + 4;
        v28 = v22;
        v23 = (char *)CoTaskMemAlloc(v22);
        if ( v23 )
        {
          v19 = v23;
          dwDataSize = v28;
          if ( Src )
          {
            memcpy_0(v23, Src, Size);
            *(_DWORD *)&v19[Size] = 0;
            v23 = &v19[Size + 4];
          }
          memcpy_0(v23, v17, (unsigned int)v26);
          lpRawData = v19;
        }
      }
    }
  }
  v24 = 0;
  if ( !ReportEventW(v14, v16, a2, a3, 0, wNumStrings, dwDataSize, lpStrings, lpRawData) )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
  }
  CoTaskMemFree(v17);
  CoTaskMemFree(v19);
  DeregisterEventSource(v14);
  return v24;
}

```

## disassembly

```asm
0x18000d090  mov     qword ptr [rsp+arg_18], r9
0x18000d095  push    rbx
0x18000d096  push    rsi
0x18000d097  push    r12
0x18000d099  push    r15
0x18000d09b  sub     rsp, 68h
0x18000d09f  cmp     [rsp+88h+arg_40], 0
0x18000d0a7  mov     r15d, r8d
0x18000d0aa  movzx   r12d, dx
0x18000d0ae  movzx   esi, cx
0x18000d0b1  jnz     short loc_18000D0C3
0x18000d0b3  lea     rdx, aMsdtc; "MSDTC"
0x18000d0ba  lea     rax, aMsdtcClient; "MSDTC Client"
0x18000d0c1  jmp     short loc_18000D0D1
0x18000d0c3  lea     rdx, aMsdtc2; "MSDTC 2"
0x18000d0ca  lea     rax, Source; "MSDTC Client 2"
0x18000d0d1  cmp     cs:?g_fEventSourceMsdtcCore@@3HA, 0; int g_fEventSourceMsdtcCore
0x18000d0d8  cmovz   rdx, rax; lpSourceName
0x18000d0dc  xor     ecx, ecx; lpUNCServerName
0x18000d0de  call    cs:__imp_RegisterEventSourceW
0x18000d0e4  mov     rbx, rax
0x18000d0e7  test    rax, rax
0x18000d0ea  jnz     short loc_18000D0F6
0x18000d0ec  mov     eax, 80004005h
0x18000d0f1  jmp     loc_18000D26B
0x18000d0f6  mov     [rsp+88h+arg_0], rbp
0x18000d0fe  and     si, 1Fh
0x18000d102  mov     [rsp+88h+arg_8], rdi
0x18000d10a  xor     ebp, ebp
0x18000d10c  mov     edi, dword ptr [rsp+88h+Size]
0x18000d113  mov     [rsp+88h+arg_10], r13
0x18000d11b  mov     r13, [rsp+88h+Src]
0x18000d123  mov     [rsp+88h+var_28], r14
0x18000d128  xor     r14d, r14d
0x18000d12b  cmp     cs:?g_fEventSourceMsdtcCore@@3HA, ebp; int g_fEventSourceMsdtcCore
0x18000d131  mov     [rsp+88h+arg_18], edi
0x18000d138  mov     [rsp+88h+var_38], rbp
0x18000d13d  jz      loc_18000D1D4
0x18000d143  lea     rcx, [rsp+88h+var_38]; unsigned __int16 **
0x18000d148  call    ?GetServiceNameFromTmInstance@@YAJPEAPEAG@Z; GetServiceNameFromTmInstance(ushort * *)
0x18000d14d  mov     rbp, [rsp+88h+var_38]
0x18000d152  test    eax, eax
0x18000d154  js      short loc_18000D1D4
0x18000d156  test    rbp, rbp
0x18000d159  jz      short loc_18000D1D4
0x18000d15b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d162  inc     rax
0x18000d165  cmp     [rbp+rax*2+0], r14w
0x18000d16b  jnz     short loc_18000D162
0x18000d16d  add     eax, eax
0x18000d16f  mov     dword ptr [rsp+88h+var_38], eax
0x18000d173  test    r13, r13
0x18000d176  jz      short loc_18000D17D
0x18000d178  add     eax, 4
0x18000d17b  add     eax, edi
0x18000d17d  mov     ecx, eax; cb
0x18000d17f  mov     [rsp+88h+arg_40], eax
0x18000d186  call    cs:__imp_CoTaskMemAlloc
0x18000d18c  test    rax, rax
0x18000d18f  jz      short loc_18000D1D4
0x18000d191  mov     ecx, [rsp+88h+arg_40]
0x18000d198  mov     r14, rax
0x18000d19b  mov     [rsp+88h+arg_18], ecx
0x18000d1a2  test    r13, r13
0x18000d1a5  jz      short loc_18000D1C1
0x18000d1a7  mov     r8, rdi; Size
0x18000d1aa  mov     rdx, r13; Src
0x18000d1ad  mov     rcx, rax; void *
0x18000d1b0  call    memcpy_0
0x18000d1b5  lea     rax, [rdi+r14]
0x18000d1b9  xor     ecx, ecx
0x18000d1bb  mov     [rax], ecx
0x18000d1bd  add     rax, 4
0x18000d1c1  mov     r8d, dword ptr [rsp+88h+var_38]; Size
0x18000d1c6  mov     rdx, rbp; Src
0x18000d1c9  mov     rcx, rax; void *
0x18000d1cc  call    memcpy_0
0x18000d1d1  mov     r13, r14
0x18000d1d4  mov     rax, [rsp+88h+arg_30]
0x18000d1dc  xor     edi, edi
0x18000d1de  mov     [rsp+88h+lpRawData], r13; lpRawData
0x18000d1e3  mov     r9d, r15d; dwEventID
0x18000d1e6  mov     [rsp+88h+lpStrings], rax; lpStrings
0x18000d1eb  movzx   r8d, r12w; wCategory
0x18000d1ef  mov     eax, [rsp+88h+arg_18]
0x18000d1f6  movzx   edx, si; wType
0x18000d1f9  mov     [rsp+88h+dwDataSize], eax; dwDataSize
0x18000d1fd  mov     rcx, rbx; hEventLog
0x18000d200  movzx   eax, [rsp+88h+arg_20]
0x18000d208  mov     [rsp+88h+wNumStrings], ax; wNumStrings
0x18000d20d  mov     [rsp+88h+lpUserSid], rdi; lpUserSid
0x18000d212  call    cs:__imp_ReportEventW
0x18000d218  mov     r13, [rsp+88h+arg_10]
0x18000d220  test    eax, eax
0x18000d222  jnz     short loc_18000D239
0x18000d224  call    cs:__imp_GetLastError
0x18000d22a  mov     edi, eax
0x18000d22c  test    eax, eax
0x18000d22e  jle     short loc_18000D239
0x18000d230  movzx   edi, ax
0x18000d233  or      edi, 80070000h
0x18000d239  mov     rcx, rbp; pv
0x18000d23c  call    cs:__imp_CoTaskMemFree
0x18000d242  mov     rcx, r14; pv
0x18000d245  call    cs:__imp_CoTaskMemFree
0x18000d24b  mov     rcx, rbx; hEventLog
0x18000d24e  call    cs:__imp_DeregisterEventSource
0x18000d254  mov     r14, [rsp+88h+var_28]
0x18000d259  mov     eax, edi
0x18000d25b  mov     rdi, [rsp+88h+arg_8]
0x18000d263  mov     rbp, [rsp+88h+arg_0]
0x18000d26b  add     rsp, 68h
0x18000d26f  pop     r15
0x18000d271  pop     r12
0x18000d273  pop     rsi
0x18000d274  pop     rbx
0x18000d275  retn
```
