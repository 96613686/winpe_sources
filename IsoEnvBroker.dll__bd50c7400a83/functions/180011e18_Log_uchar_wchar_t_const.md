# Log(uchar,wchar_t const *,...)

- ea: `0x180011e18`
- end: `0x180012005`
- name: `?Log@@YAXEPEB_WZZ`
- size: `493`
- prototype: `void(unsigned __int8, const wchar_t *, ...)`
- caller_count: `107`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180010b00`
- `0x180012140`
- `0x180013b04`
- `0x180023170`
- `0x1800238a0`
- `0x180023f50`
- `0x180023fb0`
- `0x180025a90`
- `0x180025dc0`
- `0x180025e20`
- `0x180026234`
- `0x180026368`
- `0x180026780`
- `0x180026870`
- `0x180026974`
- `0x1800274e0`
- `0x180027b60`
- `0x180027bd0`
- `0x180027c30`
- `0x180027ca0`
- `0x180028ac0`
- `0x180028de0`
- `0x180028e40`
- `0x1800293e4`
- `0x180029ad0`
- `0x180029de0`
- `0x180029e40`
- `0x180032e60`
- `0x180032f38`
- `0x180033104`
- `0x1800337d0`
- `0x180034898`
- `0x180034d48`
- `0x18003886c`
- `0x18003976c`
- `0x1800399a0`
- `0x18003abe4`
- `0x18003b968`
- `0x18003c4a4`
- `0x18003cc34`
- `0x18003cfc8`
- `0x18003d158`
- `0x18003ff5c`
- `0x180040874`
- `0x180040c90`
- `0x180040d30`
- `0x1800414dc`
- `0x180041b64`
- `0x180043304`
- `0x180043484`

## callees

- `0x180001008`
- `0x180002520`
- `0x180003198`
- `0x180010374`
- `0x180011d64`
- `0x180011e18`
- `0x1800133ac`
- `0x180064360`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011f48`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011f48`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011fe4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011fe4`

## pseudocode

```c
void Log(unsigned __int8 a1, const wchar_t *a2, ...)
{
  unsigned int v2; // edi
  bool v3; // si
  bool v4; // bl
  unsigned int *v5; // rcx
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int16 *v9; // rdx
  const wchar_t *v10; // r10
  int v11; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-E0h]
  const WCHAR *SystemTime[3]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t Buffer[1024]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v15[2048]; // [rsp+878h] [rbp+770h] BYREF
  __int64 ArgList; // [rsp+10C8h] [rbp+FC0h] BYREF
  va_list ArgLista; // [rsp+10C8h] [rbp+FC0h]
  __int64 v19; // [rsp+10D0h] [rbp+FC8h]
  va_list va1; // [rsp+10D8h] [rbp+FD0h] BYREF

  va_start(va1, a2);
  va_start(ArgLista, a2);
  ArgList = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  v2 = a1;
  v3 = (char *)g_hLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  v4 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372988>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59372988>::GetImpl'::`2'::impl) )
  {
    v5 = (unsigned int *)*((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( v5 )
      v4 = v2 < *v5;
  }
  if ( v3 || v4 )
  {
    SystemTime[0] = 0;
    vswprintf_s(Buffer, 0x400u, a2, ArgLista);
    if ( !v4 )
      goto LABEL_16;
    if ( v2 == 2 )
    {
      v6 = (_DWORD *)*((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
      if ( *v6 <= 2u )
        goto LABEL_16;
      v9 = word_1800AB6D2;
    }
    else if ( v2 == 3 )
    {
      v6 = (_DWORD *)*((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
      if ( *v6 <= 3u )
        goto LABEL_16;
      v9 = (__int16 *)&unk_1800AB708;
    }
    else
    {
      v6 = (_DWORD *)*((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
      if ( *v6 <= 4u )
        goto LABEL_16;
      v9 = (__int16 *)qword_1800AB740;
    }
    SystemTime[0] = Buffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)v6,
      (__int64)v9,
      v7,
      v8,
      SystemTime);
LABEL_16:
    if ( v3 )
    {
      *(_OWORD *)&SystemTime[1] = 0;
      GetLocalTime((LPSYSTEMTIME)&SystemTime[1]);
      if ( (_BYTE)v2 == 2 )
      {
        v10 = L"ERROR: ";
      }
      else
      {
        v10 = L"WARNING: ";
        if ( (_BYTE)v2 != 3 )
          v10 = &word_180096C4C;
      }
      LODWORD(lpOverlapped) = LOWORD(SystemTime[2]);
      v11 = swprintf_s<1024>(
              v15,
              L"[%02d/%02d %02d:%02d:%02d] %s%s\n",
              WORD1(SystemTime[1]),
              HIWORD(SystemTime[1]),
              lpOverlapped,
              WORD1(SystemTime[2]),
              WORD2(SystemTime[2]),
              v10,
              Buffer);
      LODWORD(SystemTime[0]) = 0;
      WriteFile(g_hLogFile, v15, 2 * v11, (LPDWORD)SystemTime, 0);
    }
  }
}

```

## disassembly

```asm
0x180011e18  mov     rax, rsp
0x180011e1b  mov     [rax+10h], rdx
0x180011e1f  mov     [rax+18h], r8
0x180011e23  mov     [rax+20h], r9
0x180011e27  push    rbp
0x180011e28  push    rbx
0x180011e29  push    rsi
0x180011e2a  push    rdi
0x180011e2b  lea     rbp, [rax-0FA8h]
0x180011e32  mov     eax, 1088h
0x180011e37  call    _alloca_probe
0x180011e3c  sub     rsp, rax
0x180011e3f  mov     rax, cs:__security_cookie
0x180011e46  xor     rax, rsp
0x180011e49  mov     [rbp+0FA0h+var_30], rax
0x180011e50  mov     rax, cs:?g_hLogFile@@3PEAXEA; void * g_hLogFile
0x180011e57  dec     rax
0x180011e5a  movzx   edi, cl
0x180011e5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011e61  setbe   sil
0x180011e65  xor     bl, bl
0x180011e67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59372988@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59372988@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372988> `wil::Feature<__WilFeatureTraits_Feature_ID59372988>::GetImpl(void)'::`2'::impl
0x180011e6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59372988@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372988>::__private_IsEnabled(void)
0x180011e73  test    al, al
0x180011e75  jz      short loc_180011E8D
0x180011e77  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180011e7c  mov     rcx, [rax+8]
0x180011e80  test    rcx, rcx
0x180011e83  jz      short loc_180011E8D
0x180011e85  mov     ecx, [rcx]
0x180011e87  cmp     edi, ecx
0x180011e89  jnb     short loc_180011E8D
0x180011e8b  mov     bl, 1
0x180011e8d  test    sil, sil
0x180011e90  jnz     short loc_180011E9A
0x180011e92  test    bl, bl
0x180011e94  jz      loc_180011FEA
0x180011e9a  mov     r8, [rbp+0FA0h+Format]; Format
0x180011ea1  lea     r9, [rbp+0FA0h+ArgList]; ArgList
0x180011ea8  mov     edx, 400h; BufferCount
0x180011ead  mov     qword ptr [rsp+10A0h+SystemTime], 0
0x180011eb6  lea     rcx, [rsp+10A0h+Buffer]; Buffer
0x180011ebb  call    vswprintf_s
0x180011ec0  test    bl, bl
0x180011ec2  jz      short loc_180011F32
0x180011ec4  mov     ecx, edi
0x180011ec6  sub     ecx, 2
0x180011ec9  jz      short loc_180011F02
0x180011ecb  cmp     ecx, 1
0x180011ece  jz      short loc_180011EE9
0x180011ed0  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180011ed5  mov     rcx, [rax+8]
0x180011ed9  mov     eax, [rcx]
0x180011edb  cmp     eax, 4
0x180011ede  jbe     short loc_180011F32
0x180011ee0  lea     rdx, qword_1800AB740
0x180011ee7  jmp     short loc_180011F19
0x180011ee9  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180011eee  mov     rcx, [rax+8]
0x180011ef2  mov     eax, [rcx]
0x180011ef4  cmp     eax, 3
0x180011ef7  jbe     short loc_180011F32
0x180011ef9  lea     rdx, unk_1800AB708
0x180011f00  jmp     short loc_180011F19
0x180011f02  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180011f07  mov     rcx, [rax+8]
0x180011f0b  mov     eax, [rcx]
0x180011f0d  cmp     eax, 2
0x180011f10  jbe     short loc_180011F32
0x180011f12  lea     rdx, word_1800AB6D2
0x180011f19  lea     rax, [rsp+10A0h+Buffer]
0x180011f1e  mov     qword ptr [rsp+10A0h+SystemTime], rax
0x180011f23  lea     rax, [rsp+10A0h+SystemTime]
0x180011f28  mov     [rsp+10A0h+lpOverlapped], rax
0x180011f2d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180011f32  test    sil, sil
0x180011f35  jz      loc_180011FEA
0x180011f3b  xorps   xmm0, xmm0
0x180011f3e  lea     rcx, [rsp+10A0h+SystemTime+8]; lpSystemTime
0x180011f43  movups  xmmword ptr [rsp+10A0h+SystemTime+8], xmm0
0x180011f48  call    cs:__imp_GetLocalTime
0x180011f4e  cmp     dil, 2
0x180011f52  jnz     short loc_180011F5D
0x180011f54  lea     r10, aError; "ERROR: "
0x180011f5b  jmp     short loc_180011F73
0x180011f5d  cmp     dil, 3
0x180011f61  lea     r10, aWarning; "WARNING: "
0x180011f68  lea     rax, word_180096C4C
0x180011f6f  cmovnz  r10, rax
0x180011f73  movzx   ecx, word ptr [rsp+10A0h+SystemTime+12h]
0x180011f78  lea     r11, [rsp+10A0h+Buffer]
0x180011f7d  movzx   edx, word ptr [rsp+10A0h+SystemTime+10h]
0x180011f82  movzx   eax, word ptr [rsp+10A0h+SystemTime+14h]
0x180011f87  movzx   r9d, word ptr [rsp+10A0h+SystemTime+0Eh]
0x180011f8d  movzx   r8d, word ptr [rsp+10A0h+SystemTime+0Ah]
0x180011f93  mov     [rsp+40h], r11
0x180011f98  mov     [rsp+10A0h+var_1068], r10
0x180011f9d  mov     dword ptr [rsp+10A0h+var_1070], eax
0x180011fa1  mov     [rsp+10A0h+var_1078], ecx
0x180011fa5  lea     rcx, [rbp+0FA0h+var_830]
0x180011fac  mov     dword ptr [rsp+10A0h+lpOverlapped], edx
0x180011fb0  lea     rdx, a02d02d02d02d02; "[%02d/%02d %02d:%02d:%02d] %s%s\n"
0x180011fb7  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@_WPEB_WZZ; swprintf_s<1024>(wchar_t (&)[1024],wchar_t const *,...)
0x180011fbc  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hFile
0x180011fc3  lea     r9, [rsp+10A0h+SystemTime]; lpNumberOfBytesWritten
0x180011fc8  lea     rdx, [rbp+0FA0h+var_830]; lpBuffer
0x180011fcf  mov     dword ptr [rsp+10A0h+SystemTime], 0
0x180011fd7  mov     [rsp+10A0h+lpOverlapped], 0; lpOverlapped
0x180011fe0  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180011fe4  call    cs:__imp_WriteFile
0x180011fea  mov     rcx, [rbp+0FA0h+var_30]
0x180011ff1  xor     rcx, rsp; StackCookie
0x180011ff4  call    __security_check_cookie
0x180011ff9  add     rsp, 1088h
0x180012000  pop     rdi
0x180012001  pop     rsi
0x180012002  pop     rbx
0x180012003  pop     rbp
0x180012004  retn
```
