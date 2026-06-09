# Broker::TimeBroker::ValidateSystemTime(_SYSTEMTIME const &)

- ea: `0x180002000`
- end: `0x180002155`
- name: `?ValidateSystemTime@TimeBroker@Broker@@AEAA_JAEBU_SYSTEMTIME@@@Z`
- size: `341`
- prototype: `_FILETIME __fastcall(Broker::TimeBroker *this, const struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x180002000`
- `0x180012dd0`
- `0x180013978`
- `0x180016880`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000203d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000203d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000204f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000204f`

## pseudocode

```c
_FILETIME __fastcall Broker::TimeBroker::ValidateSystemTime(Broker::TimeBroker *this, const struct _SYSTEMTIME *a2)
{
  SYSTEMTIME v2; // xmm0
  BOOL v4; // edi
  BOOL v5; // r8d
  bool v6; // dl
  bool v7; // al
  bool v8; // cl
  bool v9; // al
  _FILETIME FileTime; // [rsp+50h] [rbp-48h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-40h] BYREF
  __int128 v13; // [rsp+60h] [rbp-38h]
  int v14; // [rsp+70h] [rbp-28h]
  SYSTEMTIME SystemTime; // [rsp+78h] [rbp-20h] BYREF

  v2 = *a2;
  FileTime = 0;
  SystemTime = v2;
  v4 = SystemTimeToFileTime(&SystemTime, &FileTime);
  v5 = FileTimeToSystemTime(&FileTime, &SystemTime);
  v6 = 0;
  if ( v4 )
    v6 = a2->wYear == SystemTime.wYear;
  v7 = 0;
  if ( v5 )
    v7 = a2->wMonth == SystemTime.wMonth;
  v8 = 0;
  v9 = v6 && v7;
  if ( a2->wDay == SystemTime.wDay )
    v8 = v9;
  if ( a2->wHour != SystemTime.wHour || !v8 || a2->wMinute != SystemTime.wMinute )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_ddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v14 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v13 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  return FileTime;
}

```

## disassembly

```asm
0x180002000  mov     [rsp+arg_0], rbx
0x180002005  push    rdi
0x180002006  sub     rsp, 90h
0x18000200d  mov     rax, cs:__security_cookie
0x180002014  xor     rax, rsp
0x180002017  mov     [rsp+98h+var_10], rax
0x18000201f  movups  xmm0, xmmword ptr [rdx]
0x180002022  mov     rbx, rdx
0x180002025  mov     qword ptr [rsp+98h+FileTime.dwLowDateTime], 0
0x18000202e  lea     rdx, [rsp+98h+FileTime]; lpFileTime
0x180002033  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x180002038  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18000203d  call    cs:__imp_SystemTimeToFileTime
0x180002043  lea     rdx, [rsp+98h+SystemTime]; lpSystemTime
0x180002048  mov     edi, eax
0x18000204a  lea     rcx, [rsp+98h+FileTime]; lpFileTime
0x18000204f  call    cs:__imp_FileTimeToSystemTime
0x180002055  movzx   r9d, word ptr [rbx]
0x180002059  xor     ecx, ecx
0x18000205b  cmp     r9w, [rsp+98h+SystemTime.wYear]
0x180002061  mov     r8d, eax
0x180002064  movzx   r11d, word ptr [rbx+6]
0x180002069  movzx   r10d, word ptr [rbx+8]
0x18000206e  setz    cl
0x180002071  xor     edx, edx
0x180002073  test    edi, edi
0x180002075  movzx   edi, word ptr [rbx+2]
0x180002079  cmovnz  edx, ecx
0x18000207c  xor     ecx, ecx
0x18000207e  cmp     di, [rsp+98h+SystemTime.wMonth]
0x180002083  setz    cl
0x180002086  xor     eax, eax
0x180002088  test    r8d, r8d
0x18000208b  movzx   r8d, word ptr [rbx+0Ah]
0x180002090  cmovnz  eax, ecx
0x180002093  xor     ecx, ecx
0x180002095  and     eax, edx
0x180002097  cmp     r11w, [rsp+98h+SystemTime.wDay]
0x18000209d  cmovz   ecx, eax
0x1800020a0  xor     eax, eax
0x1800020a2  cmp     r10w, [rsp+98h+SystemTime.wHour]
0x1800020ab  setz    al
0x1800020ae  and     ecx, eax
0x1800020b0  cmp     r8w, [rsp+98h+SystemTime.wMinute]
0x1800020b9  setz    al
0x1800020bc  test    al, cl
0x1800020be  jz      short loc_1800020E6
0x1800020c0  mov     rax, qword ptr [rsp+98h+FileTime.dwLowDateTime]
0x1800020c5  mov     rcx, [rsp+98h+var_10]
0x1800020cd  xor     rcx, rsp; StackCookie
0x1800020d0  call    __security_check_cookie
0x1800020d5  mov     rbx, [rsp+98h+arg_0]
0x1800020dd  add     rsp, 90h
0x1800020e4  pop     rdi
0x1800020e5  retn
0x1800020e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020ed  test    byte ptr [rcx+1Ch], 20h
0x1800020f1  jnz     short loc_180002121
0x1800020f3  xorps   xmm0, xmm0
0x1800020f6  mov     [rsp+98h+var_28], 4
0x1800020fe  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180002105  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000210c  mov     [rsp+98h+pExceptionObject], rax
0x180002111  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180002116  movups  [rsp+98h+var_38], xmm0
0x18000211b  call    _CxxThrowException_0
0x180002121  cmp     byte ptr [rcx+19h], 2
0x180002125  jb      short loc_1800020F3
0x180002127  movzx   eax, word ptr [rbx+0Eh]
0x18000212b  movzx   edx, word ptr [rbx+0Ch]
0x18000212f  mov     rcx, [rcx+10h]
0x180002133  mov     [rsp+98h+var_50], eax
0x180002137  mov     [rsp+98h+var_58], edx
0x18000213b  mov     [rsp+98h+var_60], r8d
0x180002140  mov     [rsp+98h+var_68], r10d
0x180002145  mov     [rsp+98h+var_70], r11d
0x18000214a  mov     [rsp+98h+var_78], edi
0x18000214e  call    WPP_SF_ddddddd
0x180002153  jmp     short loc_1800020F3
```
