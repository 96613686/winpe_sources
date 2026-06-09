# CommonUtil::UtilValidateAndDeleteByHandle

- ea: `0x140013df8`
- end: `0x14001419c`
- name: `CommonUtil::UtilValidateAndDeleteByHandle`
- size: `932`
- prototype: `__int64 __fastcall(wchar_t *, char, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140013444`

## callees

- `0x1400137ac`
- `0x1400138a0`
- `0x140013df8`
- `0x14001419c`
- `0x14003a5c0`
- `0x140085d38`
- `0x140085d94`

## import_xrefs

- `KERNEL32!GetFileInformationByHandleEx` at `0x140013f76`
- `KERNEL32!GetFileInformationByHandleEx` at `0x140014081`
- `KERNEL32!GetFileInformationByHandleEx` at `0x140013f76`
- `KERNEL32!GetFileInformationByHandleEx` at `0x140014081`
- `KERNEL32!CreateFileW` at `0x140013ee9`
- `KERNEL32!CreateFileW` at `0x140013ee9`
- `KERNEL32!CloseHandle` at `0x140014165`
- `KERNEL32!CloseHandle` at `0x140014165`
- `KERNEL32!GetLastError` at `0x140013ef8`
- `KERNEL32!GetLastError` at `0x140014008`
- `KERNEL32!GetLastError` at `0x14001408b`
- `KERNEL32!GetLastError` at `0x1400140de`
- `KERNEL32!GetLastError` at `0x14001412b`
- `KERNEL32!GetLastError` at `0x140013ef8`
- `KERNEL32!GetLastError` at `0x140014008`
- `KERNEL32!GetLastError` at `0x14001408b`
- `KERNEL32!GetLastError` at `0x1400140de`
- `KERNEL32!GetLastError` at `0x14001412b`
- `KERNEL32!SetFileInformationByHandle` at `0x140013ffa`
- `KERNEL32!SetFileInformationByHandle` at `0x1400140d4`
- `KERNEL32!SetFileInformationByHandle` at `0x140014121`
- `KERNEL32!SetFileInformationByHandle` at `0x140013ffa`
- `KERNEL32!SetFileInformationByHandle` at `0x1400140d4`
- `KERNEL32!SetFileInformationByHandle` at `0x140014121`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilValidateAndDeleteByHandle(wchar_t *a1, char a2, char a3, unsigned __int8 a4)
{
  int v4; // r15d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax
  HANDLE FileW; // rax
  const wchar_t *v12; // r8
  bool v13; // r9
  void *v14; // rsi
  signed int v15; // ebx
  signed int v16; // ebx
  signed int LastError; // r14d
  __int64 v18; // rcx
  int v19; // edx
  int v20; // eax
  _BYTE v21[4]; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  _OWORD v23[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h]

  v4 = a4;
  if ( !a1 || !*a1 )
    return 2147942487LL;
  if ( a3 && (unsigned __int8)CommonUtil::UtilIsUncPath(a1) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return 2147942405LL;
    v9 = 49;
LABEL_13:
    WPP_SF_S(*(_QWORD *)(v8 + 16), v9, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids, a1);
    return 2147942405LL;
  }
  if ( a2 && (unsigned __int8)CommonUtil::UtilIsUncLoopback(a1) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return 2147942405LL;
    v9 = 50;
    goto LABEL_13;
  }
  FileW = CreateFileW(a1, 0x10080u, 7u, 0, 3u, (v4 << 25) + 0x200000, 0);
  v14 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( a2 )
    {
      if ( !(_BYTE)v4 )
      {
        FileInformation = 0;
        if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u) )
        {
          if ( (FileInformation & 0x400) != 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids, a1);
            }
            v16 = -2147024891;
            goto LABEL_58;
          }
        }
      }
    }
    else if ( !a3 )
    {
LABEL_34:
      v21[0] = 1;
      if ( !SetFileInformationByHandle(v14, FileDispositionInfo, v21, 1u) )
      {
        LastError = GetLastError();
        if ( LastError != 5 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v19 = 53;
LABEL_39:
            WPP_SF_Sd(
              *(_QWORD *)(v18 + 16),
              v19,
              (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
              (_DWORD)a1,
              LastError);
            goto LABEL_40;
          }
          goto LABEL_40;
        }
        v24 = 0;
        memset(v23, 0, sizeof(v23));
        if ( !GetFileInformationByHandleEx(v14, FileBasicInfo, v23, 0x28u) )
        {
          LastError = GetLastError();
          v18 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v19 = 54;
            goto LABEL_39;
          }
LABEL_40:
          v16 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v16 = LastError;
          goto LABEL_58;
        }
        v20 = v24 & 0xFFFFFFFE;
        if ( (v24 & 0xFFFFFFFE) == 0 )
          v20 = 128;
        LODWORD(v24) = v20;
        if ( !SetFileInformationByHandle(v14, FileBasicInfo, v23, 0x28u) )
        {
          LastError = GetLastError();
          v18 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v19 = 55;
            goto LABEL_39;
          }
          goto LABEL_40;
        }
        if ( !SetFileInformationByHandle(v14, FileDispositionInfo, v21, 1u) )
        {
          LastError = GetLastError();
          v18 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v19 = 56;
            goto LABEL_39;
          }
          goto LABEL_40;
        }
      }
      v16 = 0;
LABEL_58:
      CloseHandle(v14);
      return (unsigned int)v16;
    }
    LOBYTE(v12) = a3;
    v16 = CommonUtil::UtilValidateResolvedPath(v14, a1, v12, v13);
    if ( v16 < 0 )
      goto LABEL_58;
    goto LABEL_34;
  }
  v15 = GetLastError();
  if ( (unsigned int)(v15 - 2) <= 1 )
    return 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      51,
      (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
      (_DWORD)a1,
      v15);
  result = (unsigned __int16)v15 | 0x80070000;
  if ( v15 <= 0 )
    return (unsigned int)v15;
  return result;
}

```

## disassembly

```asm
0x140013df8  mov     [rsp-28h+arg_8], rbx
0x140013dfd  mov     [rsp-28h+arg_10], rsi
0x140013e02  push    rbp
0x140013e03  push    rdi
0x140013e04  push    r12
0x140013e06  push    r14
0x140013e08  push    r15
0x140013e0a  mov     rbp, rsp
0x140013e0d  sub     rsp, 80h
0x140013e14  mov     rax, cs:__security_cookie
0x140013e1b  xor     rax, rsp
0x140013e1e  mov     [rbp+var_8], rax
0x140013e22  xor     r12d, r12d
0x140013e25  movzx   r15d, r9b
0x140013e29  mov     bl, r8b
0x140013e2c  mov     r14b, dl
0x140013e2f  mov     rdi, rcx
0x140013e32  test    rcx, rcx
0x140013e35  jz      loc_14001416F
0x140013e3b  cmp     [rcx], r12w
0x140013e3f  jz      loc_14001416F
0x140013e45  test    bl, bl
0x140013e47  jz      short loc_140013E72
0x140013e49  call    CommonUtil__UtilIsUncPath
0x140013e4e  test    al, al
0x140013e50  jz      short loc_140013E72
0x140013e52  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e59  lea     rax, WPP_GLOBAL_Control
0x140013e60  cmp     rcx, rax
0x140013e63  jz      short loc_140013EB4
0x140013e65  test    byte ptr [rcx+1Ch], 1
0x140013e69  jz      short loc_140013EB4
0x140013e6b  lea     edx, [r12+31h]
0x140013e70  jmp     short loc_140013EA1
0x140013e72  test    r14b, r14b
0x140013e75  jz      short loc_140013EBE
0x140013e77  mov     rcx, rdi
0x140013e7a  call    CommonUtil__UtilIsUncLoopback
0x140013e7f  test    al, al
0x140013e81  jz      short loc_140013EBE
0x140013e83  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e8a  lea     rax, WPP_GLOBAL_Control
0x140013e91  cmp     rcx, rax
0x140013e94  jz      short loc_140013EB4
0x140013e96  test    byte ptr [rcx+1Ch], 1
0x140013e9a  jz      short loc_140013EB4
0x140013e9c  mov     edx, 32h ; '2'
0x140013ea1  mov     rcx, [rcx+10h]
0x140013ea5  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x140013eac  mov     r9, rdi
0x140013eaf  call    WPP_SF_S
0x140013eb4  mov     eax, 80070005h
0x140013eb9  jmp     loc_140014174
0x140013ebe  mov     eax, r15d
0x140013ec1  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x140013ec6  xor     r9d, r9d; lpSecurityAttributes
0x140013ec9  shl     eax, 19h
0x140013ecc  add     eax, 200000h
0x140013ed1  mov     edx, 10080h; dwDesiredAccess
0x140013ed6  mov     [rsp+80h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140013eda  mov     rcx, rdi; lpFileName
0x140013edd  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x140013ee5  lea     r8d, [r9+7]; dwShareMode
0x140013ee9  call    cs:__imp_CreateFileW
0x140013eef  mov     rsi, rax
0x140013ef2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140013ef6  jnz     short loc_140013F57
0x140013ef8  call    cs:__imp_GetLastError
0x140013efe  mov     ebx, eax
0x140013f00  lea     ecx, [rax-2]
0x140013f03  cmp     ecx, 1
0x140013f06  jbe     short loc_140013F4D
0x140013f08  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f0f  lea     rax, WPP_GLOBAL_Control
0x140013f16  cmp     rcx, rax
0x140013f19  jz      short loc_140013F3B
0x140013f1b  test    byte ptr [rcx+1Ch], 1
0x140013f1f  jz      short loc_140013F3B
0x140013f21  mov     rcx, [rcx+10h]
0x140013f25  lea     edx, [rsi+34h]
0x140013f28  mov     r9, rdi
0x140013f2b  mov     [rsp+80h+dwCreationDisposition], ebx
0x140013f2f  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x140013f36  call    WPP_SF_Sd
0x140013f3b  movzx   eax, bx
0x140013f3e  or      eax, 80070000h
0x140013f43  test    ebx, ebx
0x140013f45  cmovle  eax, ebx
0x140013f48  jmp     loc_140014174
0x140013f4d  mov     eax, 1
0x140013f52  jmp     loc_140014174
0x140013f57  test    r14b, r14b
0x140013f5a  jz      short loc_140013FC4
0x140013f5c  test    r15b, r15b
0x140013f5f  jnz     short loc_140013FC8
0x140013f61  mov     r9d, 8; dwBufferSize
0x140013f67  mov     [rbp+FileInformation], r12
0x140013f6b  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140013f6f  mov     rcx, rsi; hFile
0x140013f72  lea     edx, [r9+1]; FileInformationClass
0x140013f76  call    cs:__imp_GetFileInformationByHandleEx
0x140013f7c  test    eax, eax
0x140013f7e  jz      short loc_140013FC8
0x140013f80  test    dword ptr [rbp+FileInformation], 400h
0x140013f87  jz      short loc_140013FC8
0x140013f89  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f90  lea     rax, WPP_GLOBAL_Control
0x140013f97  cmp     rcx, rax
0x140013f9a  jz      short loc_140013FBA
0x140013f9c  test    byte ptr [rcx+1Ch], 1
0x140013fa0  jz      short loc_140013FBA
0x140013fa2  mov     rcx, [rcx+10h]
0x140013fa6  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x140013fad  mov     edx, 34h ; '4'
0x140013fb2  mov     r9, rdi
0x140013fb5  call    WPP_SF_S
0x140013fba  mov     ebx, 80070005h
0x140013fbf  jmp     loc_140014162
0x140013fc4  test    bl, bl
0x140013fc6  jz      short loc_140013FE3
0x140013fc8  mov     r8b, bl; wchar_t *
0x140013fcb  mov     rdx, rdi; void *
0x140013fce  mov     rcx, rsi; hFile
0x140013fd1  call    ?UtilValidateResolvedPath@CommonUtil@@YAJPEAXPEB_W_N@Z; CommonUtil::UtilValidateResolvedPath(void *,wchar_t const *,bool)
0x140013fd6  mov     ebx, eax
0x140013fd8  shr     eax, 1Fh
0x140013fdb  test    al, al
0x140013fdd  jnz     loc_140014162
0x140013fe3  mov     r9d, 1; dwBufferSize
0x140013fe9  mov     [rbp+var_3C], 1
0x140013fed  lea     r8, [rbp+var_3C]; lpFileInformation
0x140013ff1  mov     rcx, rsi; hFile
0x140013ff4  lea     ebx, [r9+3]
0x140013ff8  mov     edx, ebx; FileInformationClass
0x140013ffa  call    cs:__imp_SetFileInformationByHandle
0x140014000  test    eax, eax
0x140014002  jnz     loc_14001415F
0x140014008  call    cs:__imp_GetLastError
0x14001400e  mov     r14d, eax
0x140014011  cmp     eax, 5
0x140014014  jz      short loc_140014060
0x140014016  mov     rcx, cs:WPP_GLOBAL_Control
0x14001401d  lea     rax, WPP_GLOBAL_Control
0x140014024  cmp     rcx, rax
0x140014027  jz      short loc_14001404A
0x140014029  test    byte ptr [rcx+1Ch], 1
0x14001402d  jz      short loc_14001404A
0x14001402f  lea     edx, [rbx+31h]
0x140014032  mov     rcx, [rcx+10h]
0x140014036  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x14001403d  mov     r9, rdi
0x140014040  mov     [rsp+80h+dwCreationDisposition], r14d
0x140014045  call    WPP_SF_Sd
0x14001404a  movzx   ebx, r14w
0x14001404e  or      ebx, 80070000h
0x140014054  test    r14d, r14d
0x140014057  cmovle  ebx, r14d
0x14001405b  jmp     loc_140014162
0x140014060  xor     eax, eax
0x140014062  lea     r8, [rbp+var_30]; lpFileInformation
0x140014066  xorps   xmm0, xmm0
0x140014069  mov     [rbp+var_10], rax
0x14001406d  xor     edx, edx; FileInformationClass
0x14001406f  mov     rcx, rsi; hFile
0x140014072  movups  [rbp+var_30], xmm0
0x140014076  lea     r14d, [rax+28h]
0x14001407a  mov     r9d, r14d; dwBufferSize
0x14001407d  movups  [rbp+var_20], xmm0
0x140014081  call    cs:__imp_GetFileInformationByHandleEx
0x140014087  test    eax, eax
0x140014089  jnz     short loc_1400140B7
0x14001408b  call    cs:__imp_GetLastError
0x140014091  mov     r14d, eax
0x140014094  mov     rcx, cs:WPP_GLOBAL_Control
0x14001409b  lea     rax, WPP_GLOBAL_Control
0x1400140a2  cmp     rcx, rax
0x1400140a5  jz      short loc_14001404A
0x1400140a7  test    byte ptr [rcx+1Ch], 1
0x1400140ab  jz      short loc_14001404A
0x1400140ad  mov     edx, 36h ; '6'
0x1400140b2  jmp     loc_140014032
0x1400140b7  mov     eax, dword ptr [rbp+var_10]
0x1400140ba  lea     r8, [rbp+var_30]; lpFileInformation
0x1400140be  and     eax, 0FFFFFFFEh
0x1400140c1  mov     ecx, 80h
0x1400140c6  mov     r9d, r14d; dwBufferSize
0x1400140c9  cmovz   eax, ecx
0x1400140cc  xor     edx, edx; FileInformationClass
0x1400140ce  mov     rcx, rsi; hFile
0x1400140d1  mov     dword ptr [rbp+var_10], eax
0x1400140d4  call    cs:__imp_SetFileInformationByHandle
0x1400140da  test    eax, eax
0x1400140dc  jnz     short loc_140014112
0x1400140de  call    cs:__imp_GetLastError
0x1400140e4  mov     r14d, eax
0x1400140e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140ee  lea     rax, WPP_GLOBAL_Control
0x1400140f5  cmp     rcx, rax
0x1400140f8  jz      loc_14001404A
0x1400140fe  test    byte ptr [rcx+1Ch], 1
0x140014102  jz      loc_14001404A
0x140014108  mov     edx, 37h ; '7'
0x14001410d  jmp     loc_140014032
0x140014112  mov     r9d, 1; dwBufferSize
0x140014118  lea     r8, [rbp+var_3C]; lpFileInformation
0x14001411c  mov     edx, ebx; FileInformationClass
0x14001411e  mov     rcx, rsi; hFile
0x140014121  call    cs:__imp_SetFileInformationByHandle
0x140014127  test    eax, eax
0x140014129  jnz     short loc_14001415F
0x14001412b  call    cs:__imp_GetLastError
0x140014131  mov     r14d, eax
0x140014134  mov     rcx, cs:WPP_GLOBAL_Control
0x14001413b  lea     rax, WPP_GLOBAL_Control
0x140014142  cmp     rcx, rax
0x140014145  jz      loc_14001404A
0x14001414b  test    byte ptr [rcx+1Ch], 1
0x14001414f  jz      loc_14001404A
0x140014155  mov     edx, 38h ; '8'
0x14001415a  jmp     loc_140014032
0x14001415f  mov     ebx, r12d
0x140014162  mov     rcx, rsi; hObject
0x140014165  call    cs:__imp_CloseHandle
0x14001416b  mov     eax, ebx
0x14001416d  jmp     short loc_140014174
0x14001416f  mov     eax, 80070057h
0x140014174  mov     rcx, [rbp+var_8]
0x140014178  xor     rcx, rsp; StackCookie
0x14001417b  call    __security_check_cookie
0x140014180  lea     r11, [rsp+80h+var_s0]
0x140014188  mov     rbx, [r11+38h]
0x14001418c  mov     rsi, [r11+40h]
0x140014190  mov     rsp, r11
0x140014193  pop     r15
0x140014195  pop     r14
0x140014197  pop     r12
0x140014199  pop     rdi
0x14001419a  pop     rbp
0x14001419b  retn
```
