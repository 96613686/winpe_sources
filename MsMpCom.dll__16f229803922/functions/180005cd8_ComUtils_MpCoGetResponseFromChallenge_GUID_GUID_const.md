# ComUtils::MpCoGetResponseFromChallenge(_GUID *,_GUID const &)

- ea: `0x180005cd8`
- end: `0x180005e2a`
- name: `?MpCoGetResponseFromChallenge@ComUtils@@YAJPEAU_GUID@@AEBU2@@Z`
- size: `338`
- prototype: `__int64 __fastcall(ComUtils *__hidden this, struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003110`

## callees

- `0x180005cd8`
- `0x180005e30`
- `0x180006d2c`
- `0x180009330`
- `0x180009440`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180005d25`
- `KERNEL32!GetTickCount` at `0x180005d25`
- `mpclient!MpFreeMemory` at `0x180005d66`
- `mpclient!MpFreeMemory` at `0x180005dad`
- `mpclient!MpFreeMemory` at `0x180005dfd`
- `mpclient!MpFreeMemory` at `0x180005d66`
- `mpclient!MpFreeMemory` at `0x180005dad`
- `mpclient!MpFreeMemory` at `0x180005dfd`

## pseudocode

```c
__int64 __fastcall ComUtils::MpCoGetResponseFromChallenge(ComUtils *this, struct _GUID *a2, const struct _GUID *a3)
{
  int v5; // edx
  int SystemInfo; // ebx
  int v7; // ecx
  __int64 result; // rax
  int v9; // edx
  UUID v10; // xmm6
  unsigned __int64 i; // rcx
  unsigned int v12; // [rsp+38h] [rbp-49h] BYREF
  __int64 v13; // [rsp+40h] [rbp-41h] BYREF
  DWORD TickCount; // [rsp+48h] [rbp-39h] BYREF
  _DWORD v15[4]; // [rsp+68h] [rbp-19h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-9h] BYREF
  __int128 v17; // [rsp+88h] [rbp+7h] BYREF

  v15[0] = -1581532052;
  Uuid = 0;
  v15[1] = 1186634282;
  v15[2] = -728976193;
  v15[3] = -1717598600;
  v12 = 0;
  TickCount = GetTickCount();
  v13 = 0;
  SystemInfo = MpRpcQuerySystemInfo((unsigned int)v15, v5, (unsigned int)&TickCount, (unsigned int)&v12, (__int64)&v13);
  if ( SystemInfo < 0 )
  {
    if ( v13 )
      MpFreeMemory(v13);
    if ( (unsigned int)(SystemInfo + 2147418106) <= 1
      || (unsigned int)(SystemInfo + 2147416395) <= 0xA && (v7 = 1569, _bittest(&v7, SystemInfo + 2147416395)) )
    {
      result = ComUtils::MpGetReportingGuid(&Uuid);
      if ( (int)result < 0 )
        return result;
      goto LABEL_12;
    }
    return (unsigned int)SystemInfo;
  }
  if ( !v13 )
    return (unsigned int)-2147418113;
  if ( v12 < 0x14 )
  {
    MpFreeMemory(v13);
    return (unsigned int)-2147418113;
  }
  v10 = *(UUID *)v13;
  MpFreeMemory(v13);
  Uuid = v10;
LABEL_12:
  for ( i = 0; i < 2; ++i )
    *((_QWORD *)&Uuid.Data1 + i) ^= *((_QWORD *)&a2->Data1 + i);
  v13 = 16;
  v17 = 0;
  MpHashCalcDigest(i, v9, (unsigned int)&Uuid, (unsigned int)&v13, (__int64)&v17);
  result = 0;
  *(_OWORD *)this = v17;
  return result;
}

```

## disassembly

```asm
0x180005cd8  mov     rax, rsp
0x180005cdb  push    rbp
0x180005cdc  push    rbx
0x180005cdd  push    rsi
0x180005cde  push    rdi
0x180005cdf  lea     rbp, [rax-5Fh]
0x180005ce3  sub     rsp, 0B8h
0x180005cea  movaps  xmmword ptr [rax-38h], xmm6
0x180005cee  mov     rax, cs:__security_cookie
0x180005cf5  xor     rax, rsp
0x180005cf8  mov     [rbp+57h+var_40], rax
0x180005cfc  xorps   xmm0, xmm0
0x180005cff  mov     [rbp+57h+var_70], 0A1BBBC6Ch
0x180005d06  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180005d0a  mov     rdi, rdx
0x180005d0d  mov     [rbp+57h+var_6C], 46BA9A2Ah
0x180005d14  mov     rsi, rcx
0x180005d17  mov     [rbp+57h+var_68], 0D48CB4BFh
0x180005d1e  mov     [rbp+57h+var_64], 999F8678h
0x180005d25  call    cs:__imp_GetTickCount
0x180005d2b  lea     r9, [rbp+57h+var_A0]
0x180005d2f  mov     [rbp+57h+var_A0], 0
0x180005d36  mov     [rbp+57h+var_90], eax
0x180005d39  lea     r8, [rbp+57h+var_90]
0x180005d3d  lea     rax, [rbp+57h+var_98]
0x180005d41  mov     [rbp+57h+var_98], 0
0x180005d49  lea     rcx, [rbp+57h+var_70]
0x180005d4d  mov     [rsp+20h], rax
0x180005d52  call    MpRpcQuerySystemInfo
0x180005d57  mov     rcx, [rbp+57h+var_98]
0x180005d5b  mov     ebx, eax
0x180005d5d  test    eax, eax
0x180005d5f  jns     short loc_180005D9F
0x180005d61  test    rcx, rcx
0x180005d64  jz      short loc_180005D6C
0x180005d66  call    cs:__imp_MpFreeMemory
0x180005d6c  lea     eax, [rbx+7FFEFFFAh]
0x180005d72  cmp     eax, 1
0x180005d75  jbe     short loc_180005D90
0x180005d77  lea     eax, [rbx+7FFEF94Bh]
0x180005d7d  cmp     eax, 0Ah
0x180005d80  ja      loc_180005E08
0x180005d86  mov     ecx, 621h
0x180005d8b  bt      ecx, eax
0x180005d8e  jnb     short loc_180005E08
0x180005d90  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180005d94  call    ComUtils__MpGetReportingGuid
0x180005d99  test    eax, eax
0x180005d9b  jns     short loc_180005DB8
0x180005d9d  jmp     short loc_180005E0A
0x180005d9f  test    rcx, rcx
0x180005da2  jz      short loc_180005E03
0x180005da4  cmp     [rbp+57h+var_A0], 14h
0x180005da8  jb      short loc_180005DFD
0x180005daa  movups  xmm6, xmmword ptr [rcx]
0x180005dad  call    cs:__imp_MpFreeMemory
0x180005db3  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm6
0x180005db8  xor     ecx, ecx
0x180005dba  mov     rax, [rdi+rcx*8]
0x180005dbe  xor     qword ptr [rbp+rcx*8+57h+Uuid.Data1], rax
0x180005dc3  inc     rcx
0x180005dc6  cmp     rcx, 2
0x180005dca  jb      short loc_180005DBA
0x180005dcc  xorps   xmm0, xmm0
0x180005dcf  mov     [rbp+57h+var_98], 10h
0x180005dd7  lea     rax, [rbp+57h+var_50]
0x180005ddb  lea     r9, [rbp+57h+var_98]
0x180005ddf  mov     [rsp+20h], rax
0x180005de4  lea     r8, [rbp+57h+Uuid]
0x180005de8  movups  [rbp+57h+var_50], xmm0
0x180005dec  call    MpHashCalcDigest
0x180005df1  movups  xmm0, [rbp+57h+var_50]
0x180005df5  xor     eax, eax
0x180005df7  movdqu  xmmword ptr [rsi], xmm0
0x180005dfb  jmp     short loc_180005E0A
0x180005dfd  call    cs:__imp_MpFreeMemory
0x180005e03  mov     ebx, 8000FFFFh
0x180005e08  mov     eax, ebx
0x180005e0a  mov     rcx, [rbp+57h+var_40]
0x180005e0e  xor     rcx, rsp; StackCookie
0x180005e11  call    __security_check_cookie
0x180005e16  movaps  xmm6, [rsp+0D0h+var_38+8]
0x180005e1e  add     rsp, 0B8h
0x180005e25  pop     rdi
0x180005e26  pop     rsi
0x180005e27  pop     rbx
0x180005e28  pop     rbp
0x180005e29  retn
```
