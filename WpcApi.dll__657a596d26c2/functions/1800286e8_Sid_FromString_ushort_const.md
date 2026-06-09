# Sid::FromString(ushort const *)

- ea: `0x1800286e8`
- end: `0x180028835`
- name: `?FromString@Sid@@SA?AV1@PEBG@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000bf74`
- `0x18000c164`
- `0x18000f638`
- `0x180014370`
- `0x180014480`
- `0x180014600`
- `0x18001757c`
- `0x18002840c`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180005f9c`
- `0x18000dd9c`
- `0x1800195c4`
- `0x1800286e8`
- `0x180028aa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287cc`

## pseudocode

```c
__int64 __fastcall Sid::FromString(__int64 a1, int a2)
{
  __int64 v4; // rdx
  signed int LastError; // eax
  unsigned int v7; // ebx
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v9[112]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v10; // [rsp+F0h] [rbp-28h]

  Sid::TryFromString(v9);
  v4 = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        (unsigned int)WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids,
        a2,
        v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_OWORD *)a1 = *(_OWORD *)v10;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(v4 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(v4 + 32);
  *(_OWORD *)(a1 + 48) = *(_OWORD *)(v4 + 48);
  *(_DWORD *)(a1 + 64) = *(_DWORD *)(v4 + 64);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_OWORD *)(a1 + 72) = *(_OWORD *)(v4 + 72);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)(v4 + 88);
  *(_QWORD *)(v4 + 88) = 0;
  *(_QWORD *)(v4 + 96) = 7;
  *(_WORD *)(v4 + 72) = 0;
  if ( v10 )
    std::wstring::~wstring((char **)(v10 + 72));
  return a1;
}

```

## disassembly

```asm
0x1800286e8  mov     [rsp+arg_10], rbx
0x1800286ed  push    rdi
0x1800286ee  sub     rsp, 110h
0x1800286f5  mov     rax, cs:__security_cookie
0x1800286fc  xor     rax, rsp
0x1800286ff  mov     [rsp+118h+var_18], rax
0x180028707  mov     rdi, rdx
0x18002870a  mov     rbx, rcx
0x18002870d  mov     [rsp+118h+var_D8], rcx
0x180028712  lea     rcx, [rsp+118h+var_98]
0x18002871a  call    ?TryFromString@Sid@@SA?AV?$Optional@VSid@@@@PEBG@Z; Sid::TryFromString(ushort const *)
0x18002871f  nop
0x180028720  mov     rdx, [rsp+118h+var_28]
0x180028728  test    rdx, rdx
0x18002872b  jz      loc_1800287CC
0x180028731  movups  xmm0, xmmword ptr [rdx]
0x180028734  movups  xmmword ptr [rbx], xmm0
0x180028737  movups  xmm1, xmmword ptr [rdx+10h]
0x18002873b  movups  xmmword ptr [rbx+10h], xmm1
0x18002873f  movups  xmm0, xmmword ptr [rdx+20h]
0x180028743  movups  xmmword ptr [rbx+20h], xmm0
0x180028747  movups  xmm1, xmmword ptr [rdx+30h]
0x18002874b  movups  xmmword ptr [rbx+30h], xmm1
0x18002874f  mov     eax, [rdx+40h]
0x180028752  mov     [rbx+40h], eax
0x180028755  xorps   xmm0, xmm0
0x180028758  movups  xmmword ptr [rbx+48h], xmm0
0x18002875c  mov     qword ptr [rbx+58h], 0
0x180028764  mov     qword ptr [rbx+60h], 0
0x18002876c  movups  xmm0, xmmword ptr [rdx+48h]
0x180028770  movups  xmmword ptr [rbx+48h], xmm0
0x180028774  movups  xmm1, xmmword ptr [rdx+58h]
0x180028778  movups  xmmword ptr [rbx+58h], xmm1
0x18002877c  mov     qword ptr [rdx+58h], 0
0x180028784  mov     qword ptr [rdx+60h], 7
0x18002878c  xor     ecx, ecx
0x18002878e  mov     [rdx+48h], cx
0x180028792  mov     rcx, [rsp+118h+var_28]
0x18002879a  test    rcx, rcx
0x18002879d  jz      short loc_1800287A8
0x18002879f  add     rcx, 48h ; 'H'
0x1800287a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800287a8  mov     rax, rbx
0x1800287ab  mov     rcx, [rsp+118h+var_18]
0x1800287b3  xor     rcx, rsp; StackCookie
0x1800287b6  call    __security_check_cookie
0x1800287bb  mov     rbx, [rsp+118h+arg_10]
0x1800287c3  add     rsp, 110h
0x1800287ca  pop     rdi
0x1800287cb  retn
0x1800287cc  call    cs:__imp_GetLastError
0x1800287d2  nop
0x1800287d3  mov     ebx, eax
0x1800287d5  test    eax, eax
0x1800287d7  jle     short loc_1800287E2
0x1800287d9  movzx   ebx, ax
0x1800287dc  or      ebx, 80070000h
0x1800287e2  lea     rax, WPP_GLOBAL_Control
0x1800287e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287f0  cmp     rcx, rax
0x1800287f3  jz      short loc_180028817
0x1800287f5  test    byte ptr [rcx+1Ch], 1
0x1800287f9  jz      short loc_180028817
0x1800287fb  mov     edx, 0Ch
0x180028800  mov     [rsp+118h+var_F8], ebx
0x180028804  mov     r9, rdi
0x180028807  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x18002880e  mov     rcx, [rcx+10h]
0x180028812  call    WPP_SF_Sd
0x180028817  mov     edx, ebx; int
0x180028819  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18002881e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180028823  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002882a  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002882f  call    _CxxThrowException_0
```
