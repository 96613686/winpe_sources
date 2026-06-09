# GetContentId

- ea: `0x18002fec0`
- end: `0x18003028e`
- name: `GetContentId`
- size: `974`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cabc`

## callees

- `0x18002fec0`
- `0x180030294`
- `0x180030320`
- `0x18003c918`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030001`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003000a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030001`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003000a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030260`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030087`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ffb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030087`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800301a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800301a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003014d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003026b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003014d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003026b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030123`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030123`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002ff03`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002ff03`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageNameAndPublisherIdFromFamilyName` at `0x18002ff49`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageNameAndPublisherIdFromFamilyName` at `0x18002ffe1`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageNameAndPublisherIdFromFamilyName` at `0x18002ff49`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageNameAndPublisherIdFromFamilyName` at `0x18002ffe1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180030225`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180030225`

## pseudocode

```c
__int64 __fastcall GetContentId(LPCWSTR lpValue, int a2, struct _GUID *a3)
{
  int v4; // r14d
  LSTATUS v6; // eax
  int v7; // ebx
  WCHAR *v8; // rbx
  WCHAR *v9; // rdi
  LONG v10; // eax
  signed int v11; // esi
  int ContentId; // r13d
  WCHAR *packagePublisherId; // r15
  WCHAR *v14; // r14
  LONG v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  bool v19; // zf
  wchar_t **v20; // r15
  unsigned __int64 v21; // r14
  unsigned __int16 *v22; // rsi
  LSTATUS v24; // eax
  LSTATUS ValueW; // eax
  unsigned int v26; // edx
  void *v27; // rcx
  OLECHAR *v28; // rdi
  LSTATUS v29; // eax
  UINT32 packageNameLength[2]; // [rsp+40h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-18h] BYREF
  PVOID hMem; // [rsp+50h] [rbp-10h] BYREF
  UINT32 packagePublisherIdLength; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  *a3 = 0;
  if ( a2 == 2 )
  {
    phkResult = 0;
    *a3 = 0;
    v6 = RegOpenCurrentUser(0x20019u, &phkResult);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 >= 0 )
    {
      if ( lpValue )
      {
        *(_QWORD *)packageNameLength = 0;
        v24 = RegOpenKeyExW(
                phkResult,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\ContentId",
                0,
                0x20019u,
                (PHKEY)packageNameLength);
        v7 = v24;
        if ( v24 > 0 )
          v7 = (unsigned __int16)v24 | 0x80070000;
        if ( v7 >= 0 )
        {
          packagePublisherIdLength = 0;
          ValueW = RegGetValueW(*(HKEY *)packageNameLength, 0, lpValue, 2u, 0, 0, &packagePublisherIdLength);
          v7 = ValueW;
          if ( ValueW > 0 )
            v7 = (unsigned __int16)ValueW | 0x80070000;
          if ( v7 >= 0 )
          {
            hMem = 0;
            v7 = CTLocalAllocPolicy::Alloc(v27, v26, packagePublisherIdLength, &hMem);
            if ( v7 >= 0 )
            {
              v28 = (OLECHAR *)hMem;
              v29 = RegGetValueW(*(HKEY *)packageNameLength, 0, lpValue, 2u, 0, hMem, &packagePublisherIdLength);
              v7 = v29;
              if ( v29 > 0 )
                v7 = (unsigned __int16)v29 | 0x80070000;
              if ( v7 >= 0 )
              {
                v7 = IIDFromString(v28, a3);
                v28 = 0;
              }
              LocalFree(v28);
            }
          }
        }
        if ( *(_QWORD *)packageNameLength )
          RegCloseKey(*(HKEY *)packageNameLength);
        RegCloseKey(phkResult);
      }
      if ( v7 >= 0 )
        return (unsigned int)v7;
    }
  }
  packagePublisherIdLength = 0;
  packageNameLength[0] = 0;
  v8 = 0;
  v9 = 0;
  v10 = PackageNameAndPublisherIdFromFamilyName(lpValue, packageNameLength, 0, &packagePublisherIdLength, 0);
  v11 = v10;
  ContentId = -2147024362;
  if ( v10 == 122 )
  {
    if ( is_mul_ok(packagePublisherIdLength, 2u) )
    {
      packagePublisherId = (WCHAR *)LocalAlloc(0x40u, 2LL * packagePublisherIdLength);
      if ( packagePublisherId )
      {
        if ( is_mul_ok(packageNameLength[0], 2u) )
        {
          v14 = (WCHAR *)LocalAlloc(0x40u, 2LL * packageNameLength[0]);
          if ( v14 )
          {
            v15 = PackageNameAndPublisherIdFromFamilyName(
                    lpValue,
                    packageNameLength,
                    v14,
                    &packagePublisherIdLength,
                    packagePublisherId);
            v11 = v15;
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
            if ( v11 >= 0 )
            {
              v8 = v14;
              v9 = packagePublisherId;
              v14 = 0;
              packagePublisherId = 0;
            }
            LocalFree(v14);
          }
          else
          {
            v11 = -2147024882;
          }
        }
        else
        {
          v11 = -2147024362;
        }
        LocalFree(packagePublisherId);
        v4 = a2;
      }
      else
      {
        v11 = -2147024882;
      }
    }
    else
    {
      v11 = -2147024362;
    }
  }
  else if ( v10 > 0 )
  {
    v11 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v11 < 0 )
    return (unsigned int)v11;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( v8[v17] );
  v18 = -1;
  do
    v19 = v9[++v18] == 0;
  while ( !v19 );
  v20 = &off_1800BF498[v4];
  do
    v19 = (*v20)[++v16] == 0;
  while ( !v19 );
  hMem = 0;
  v21 = v17 + 3 + v16 + v18;
  if ( is_mul_ok(v21, 2u) )
  {
    v22 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v21);
    if ( v22 )
    {
      ContentId = StringCchPrintfW(v22, v21, L"%s:%s:%s", v8, v9, *v20);
      if ( ContentId >= 0 )
      {
        ContentId = GetContentId(v22, a3);
        LocalFree(v22);
      }
    }
    else
    {
      ContentId = -2147024882;
    }
  }
  LocalFree(v8);
  LocalFree(v9);
  return (unsigned int)ContentId;
}

```

## disassembly

```asm
0x18002fec0  mov     [rsp-38h+arg_10], r8
0x18002fec5  mov     [rsp-38h+arg_8], edx
0x18002fec9  push    rbp
0x18002feca  push    rbx
0x18002fecb  push    rsi
0x18002fecc  push    rdi
0x18002fecd  push    r12
0x18002fecf  push    r14
0x18002fed1  push    r15
0x18002fed3  mov     rbp, rsp
0x18002fed6  sub     rsp, 60h
0x18002feda  xor     r15d, r15d
0x18002fedd  xorps   xmm0, xmm0
0x18002fee0  mov     rsi, r8
0x18002fee3  mov     r14d, edx
0x18002fee6  mov     r12, rcx
0x18002fee9  movups  xmmword ptr [r8], xmm0
0x18002feed  cmp     edx, 2
0x18002fef0  jnz     short loc_18002FF20
0x18002fef2  lea     rdx, [rbp+phkResult]; phkResult
0x18002fef6  mov     [rbp+phkResult], r15
0x18002fefa  mov     ecx, 20019h; samDesired
0x18002feff  movups  xmmword ptr [r8], xmm0
0x18002ff03  call    cs:__imp_RegOpenCurrentUser
0x18002ff09  mov     ebx, eax
0x18002ff0b  test    eax, eax
0x18002ff0d  jle     short loc_18002FF18
0x18002ff0f  movzx   ebx, ax
0x18002ff12  or      ebx, 80070000h
0x18002ff18  test    ebx, ebx
0x18002ff1a  jns     loc_1800300FD
0x18002ff20  lea     r9, [rbp+packagePublisherIdLength]; packagePublisherIdLength
0x18002ff24  mov     [rsp+60h+arg_0], r13
0x18002ff2c  xor     r8d, r8d; packageName
0x18002ff2f  mov     [rbp+packagePublisherIdLength], r15d
0x18002ff33  lea     rdx, [rbp+packageNameLength]; packageNameLength
0x18002ff37  mov     [rbp+packageNameLength], r15d
0x18002ff3b  mov     rcx, r12; packageFamilyName
0x18002ff3e  mov     [rsp+60h+packagePublisherId], r15; packagePublisherId
0x18002ff43  mov     rbx, r15
0x18002ff46  mov     rdi, r15
0x18002ff49  call    cs:__imp_PackageNameAndPublisherIdFromFamilyName
0x18002ff4f  mov     esi, eax
0x18002ff51  mov     r13d, 80070216h
0x18002ff57  cmp     eax, 7Ah ; 'z'
0x18002ff5a  jnz     loc_18003016C
0x18002ff60  mov     ecx, [rbp+packagePublisherIdLength]
0x18002ff63  mov     eax, 2
0x18002ff68  mul     rcx
0x18002ff6b  test    rdx, rdx
0x18002ff6e  jnz     loc_180030246
0x18002ff74  mov     rdx, rax; uBytes
0x18002ff77  mov     ecx, 40h ; '@'; uFlags
0x18002ff7c  call    cs:__imp_LocalAlloc
0x18002ff82  xor     esi, esi
0x18002ff84  mov     r15, rax
0x18002ff87  test    rax, rax
0x18002ff8a  mov     eax, 8007000Eh
0x18002ff8f  cmovz   esi, eax
0x18002ff92  test    r15, r15
0x18002ff95  jz      short loc_180030014
0x18002ff97  mov     ecx, [rbp+packageNameLength]
0x18002ff9a  mov     eax, 2
0x18002ff9f  mul     rcx
0x18002ffa2  test    rdx, rdx
0x18002ffa5  jnz     loc_18003023E
0x18002ffab  mov     rdx, rax; uBytes
0x18002ffae  mov     ecx, 40h ; '@'; uFlags
0x18002ffb3  call    cs:__imp_LocalAlloc
0x18002ffb9  xor     esi, esi
0x18002ffbb  mov     r14, rax
0x18002ffbe  test    rax, rax
0x18002ffc1  mov     eax, 8007000Eh
0x18002ffc6  cmovz   esi, eax
0x18002ffc9  test    r14, r14
0x18002ffcc  jz      short loc_180030007
0x18002ffce  lea     r9, [rbp+packagePublisherIdLength]; packagePublisherIdLength
0x18002ffd2  mov     [rsp+60h+packagePublisherId], r15; packagePublisherId
0x18002ffd7  mov     r8, r14; packageName
0x18002ffda  lea     rdx, [rbp+packageNameLength]; packageNameLength
0x18002ffde  mov     rcx, r12; packageFamilyName
0x18002ffe1  call    cs:__imp_PackageNameAndPublisherIdFromFamilyName
0x18002ffe7  mov     esi, eax
0x18002ffe9  test    eax, eax
0x18002ffeb  jle     short loc_18002FFF6
0x18002ffed  movzx   esi, ax
0x18002fff0  or      esi, 80070000h
0x18002fff6  test    esi, esi
0x18002fff8  jns     loc_180030276
0x18002fffe  mov     rcx, r14; hMem
0x180030001  call    cs:__imp_LocalFree
0x180030007  mov     rcx, r15; hMem
0x18003000a  call    cs:__imp_LocalFree
0x180030010  mov     r14d, [rbp+arg_8]
0x180030014  test    esi, esi
0x180030016  js      loc_180030287
0x18003001c  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180030023  mov     rdx, r9
0x180030026  inc     rdx
0x180030029  cmp     word ptr [rbx+rdx*2], 0
0x18003002e  jnz     short loc_180030026
0x180030030  mov     r8, r9
0x180030033  cmp     word ptr [rdi+r8*2+2], 0
0x18003003a  lea     r8, [r8+1]
0x18003003e  jnz     short loc_180030033
0x180030040  lea     rcx, off_1800BF498; "win8xappx"
0x180030047  movsxd  rax, r14d
0x18003004a  lea     r15, [rcx+rax*8]
0x18003004e  mov     rcx, [rcx+rax*8]
0x180030052  cmp     word ptr [rcx+r9*2+2], 0
0x180030059  lea     r9, [r9+1]
0x18003005d  jnz     short loc_180030052
0x18003005f  add     rdx, 3
0x180030063  mov     [rbp+hMem], 0
0x18003006b  lea     r14, [r9+r8]
0x18003006f  mov     eax, 2
0x180030074  add     r14, rdx
0x180030077  mul     r14
0x18003007a  test    rdx, rdx
0x18003007d  jnz     short loc_1800300D1
0x18003007f  mov     rdx, rax; uBytes
0x180030082  mov     ecx, 40h ; '@'; uFlags
0x180030087  call    cs:__imp_LocalAlloc
0x18003008d  xor     r13d, r13d
0x180030090  mov     rsi, rax
0x180030093  test    rax, rax
0x180030096  mov     eax, 8007000Eh
0x18003009b  cmovz   r13d, eax
0x18003009f  test    rsi, rsi
0x1800300a2  jz      short loc_1800300D1
0x1800300a4  mov     rcx, [r15]
0x1800300a7  lea     r8, aSSS; "%s:%s:%s"
0x1800300ae  mov     [rsp+60h+pvData], rcx
0x1800300b3  mov     r9, rbx
0x1800300b6  mov     rcx, rsi; unsigned __int16 *
0x1800300b9  mov     [rsp+60h+packagePublisherId], rdi
0x1800300be  mov     rdx, r14; unsigned __int64
0x1800300c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800300c6  mov     r13d, eax
0x1800300c9  test    eax, eax
0x1800300cb  jns     loc_18003024E
0x1800300d1  mov     rcx, rbx; hMem
0x1800300d4  call    cs:__imp_LocalFree
0x1800300da  mov     rcx, rdi; hMem
0x1800300dd  call    cs:__imp_LocalFree
0x1800300e3  mov     eax, r13d
0x1800300e6  mov     r13, [rsp+60h+arg_0]
0x1800300ee  add     rsp, 60h
0x1800300f2  pop     r15
0x1800300f4  pop     r14
0x1800300f6  pop     r12
0x1800300f8  pop     rdi
0x1800300f9  pop     rsi
0x1800300fa  pop     rbx
0x1800300fb  pop     rbp
0x1800300fc  retn
0x1800300fd  test    r12, r12
0x180030100  jz      short loc_180030153
0x180030102  mov     rcx, [rbp+phkResult]; hKey
0x180030106  lea     rax, [rbp+packageNameLength]
0x18003010a  mov     r9d, 20019h; samDesired
0x180030110  mov     [rsp+60h+packagePublisherId], rax; phkResult
0x180030115  xor     r8d, r8d; ulOptions
0x180030118  mov     qword ptr [rbp+packageNameLength], r15
0x18003011c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180030123  call    cs:__imp_RegOpenKeyExW
0x180030129  mov     ebx, eax
0x18003012b  test    eax, eax
0x18003012d  jle     short loc_180030138
0x18003012f  movzx   ebx, ax
0x180030132  or      ebx, 80070000h
0x180030138  test    ebx, ebx
0x18003013a  jns     short loc_180030182
0x18003013c  mov     rcx, qword ptr [rbp+packageNameLength]; hKey
0x180030140  test    rcx, rcx
0x180030143  jnz     loc_18003026B
0x180030149  mov     rcx, [rbp+phkResult]; hKey
0x18003014d  call    cs:__imp_RegCloseKey
0x180030153  test    ebx, ebx
0x180030155  js      loc_18002FF20
0x18003015b  mov     eax, ebx
0x18003015d  add     rsp, 60h
0x180030161  pop     r15
0x180030163  pop     r14
0x180030165  pop     r12
0x180030167  pop     rdi
0x180030168  pop     rsi
0x180030169  pop     rbx
0x18003016a  pop     rbp
0x18003016b  retn
0x18003016c  test    eax, eax
0x18003016e  jle     loc_180030014
0x180030174  movzx   esi, ax
0x180030177  or      esi, 80070000h
0x18003017d  jmp     loc_180030014
0x180030182  mov     rcx, qword ptr [rbp+packageNameLength]; hkey
0x180030186  lea     rax, [rbp+packagePublisherIdLength]
0x18003018a  mov     [rsp+60h+pcbData], rax; pcbData
0x18003018f  mov     r9d, 2; dwFlags
0x180030195  mov     [rsp+60h+pvData], r15; pvData
0x18003019a  mov     r8, r12; lpValue
0x18003019d  xor     edx, edx; lpSubKey
0x18003019f  mov     [rsp+60h+packagePublisherId], r15; pdwType
0x1800301a4  mov     [rbp+packagePublisherIdLength], r15d
0x1800301a8  call    cs:__imp_RegGetValueW
0x1800301ae  mov     ebx, eax
0x1800301b0  test    eax, eax
0x1800301b2  jle     short loc_1800301BD
0x1800301b4  movzx   ebx, ax
0x1800301b7  or      ebx, 80070000h
0x1800301bd  test    ebx, ebx
0x1800301bf  js      loc_18003013C
0x1800301c5  mov     r8d, [rbp+packagePublisherIdLength]; unsigned __int64
0x1800301c9  lea     r9, [rbp+hMem]; void **
0x1800301cd  mov     [rbp+hMem], r15
0x1800301d1  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800301d6  mov     ebx, eax
0x1800301d8  test    eax, eax
0x1800301da  js      loc_18003013C
0x1800301e0  mov     rdi, [rbp+hMem]
0x1800301e4  lea     rax, [rbp+packagePublisherIdLength]
0x1800301e8  mov     rcx, qword ptr [rbp+packageNameLength]; hkey
0x1800301ec  mov     r9d, 2; dwFlags
0x1800301f2  mov     [rsp+60h+pcbData], rax; pcbData
0x1800301f7  mov     r8, r12; lpValue
0x1800301fa  mov     [rsp+60h+pvData], rdi; pvData
0x1800301ff  xor     edx, edx; lpSubKey
0x180030201  mov     [rsp+60h+packagePublisherId], r15; pdwType
0x180030206  call    cs:__imp_RegGetValueW
0x18003020c  mov     ebx, eax
0x18003020e  test    eax, eax
0x180030210  jle     short loc_18003021B
0x180030212  movzx   ebx, ax
0x180030215  or      ebx, 80070000h
0x18003021b  test    ebx, ebx
0x18003021d  js      short loc_180030230
0x18003021f  mov     rdx, rsi; lpiid
0x180030222  mov     rcx, rdi; lpsz
0x180030225  call    cs:__imp_IIDFromString
0x18003022b  mov     ebx, eax
0x18003022d  mov     rdi, r15
0x180030230  mov     rcx, rdi; hMem
0x180030233  call    cs:__imp_LocalFree
0x180030239  jmp     loc_18003013C
0x18003023e  mov     esi, r13d
0x180030241  jmp     loc_180030007
0x180030246  mov     esi, r13d
0x180030249  jmp     loc_180030014
0x18003024e  mov     rdx, [rbp+arg_10]; struct _GUID *
0x180030252  mov     rcx, rsi; lpSrcStr
0x180030255  call    ?GetContentId@@YAJPEBGPEAU_GUID@@@Z; GetContentId(ushort const *,_GUID *)
0x18003025a  mov     rcx, rsi; hMem
0x18003025d  mov     r13d, eax
0x180030260  call    cs:__imp_LocalFree
0x180030266  jmp     loc_1800300D1
0x18003026b  call    cs:__imp_RegCloseKey
0x180030271  jmp     loc_180030149
0x180030276  mov     rbx, r14
0x180030279  mov     rdi, r15
0x18003027c  xor     r14d, r14d
0x18003027f  xor     r15d, r15d
0x180030282  jmp     loc_18002FFFE
0x180030287  mov     eax, esi
0x180030289  jmp     loc_1800300E6
```
