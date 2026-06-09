# ShieldProvider::GetFileNameFromFileHandle(ushort * *,void *,ulong)

- ea: `0x140005e1c`
- end: `0x140005f9a`
- name: `?GetFileNameFromFileHandle@ShieldProvider@@YAJPEAPEAGPEAXK@Z`
- size: `382`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 **, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140004588`
- `0x140004e84`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140005578`
- `0x140005e1c`
- `0x140011234`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005ebb`
- `KERNEL32!GetLastError` at `0x140005ebb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140005e90`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140005e90`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetFileNameFromFileHandle(ShieldProvider *this, unsigned __int16 **a2, void *a3)
{
  LPWSTR v3; // rbx
  unsigned __int64 v4; // rsi
  int v5; // r14d
  DWORD FinalPathNameByHandleW; // ebp
  unsigned __int64 v9; // rdx
  int v10; // ebx
  signed int LastFailure; // edi
  signed int LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  LPWSTR lpszFilePath; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  lpszFilePath = 0;
  v5 = 0;
  FinalPathNameByHandleW = 520;
  while ( 1 )
  {
    if ( FinalPathNameByHandleW <= v4 )
    {
LABEL_9:
      if ( FinalPathNameByHandleW <= v4 )
        goto LABEL_29;
      LastError = GetLastError();
      LastFailure = LastError;
      if ( LastError > 0 )
        LastFailure = (unsigned __int16)LastError | 0x80070000;
      if ( LastFailure >= 0 )
      {
LABEL_29:
        *(_QWORD *)this = v3;
        return 0;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v14 = 18;
      goto LABEL_19;
    }
    v4 = FinalPathNameByHandleW;
    if ( v3 )
    {
      operator delete(v3, (unsigned __int64)a2);
      lpszFilePath = 0;
    }
    v10 = CommonUtil::MpNewBuffer<unsigned short>(&lpszFilePath, FinalPathNameByHandleW, a3);
    if ( v10 < 0 )
      break;
    v3 = lpszFilePath;
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(a2, lpszFilePath, FinalPathNameByHandleW, 0);
    if ( !FinalPathNameByHandleW )
    {
      LastFailure = HrGetLastFailure();
      if ( LastFailure < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_20:
          if ( v3 )
            operator delete(v3, (unsigned __int64)a2);
          return (unsigned int)LastFailure;
        }
        v14 = 17;
LABEL_19:
        WPP_SF_d(v13[2], v14, &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids, (unsigned int)LastFailure);
        goto LABEL_20;
      }
    }
    if ( ++v5 >= 3 )
      goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids,
      (unsigned int)v10);
  if ( lpszFilePath )
    operator delete(lpszFilePath, v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005e1c  mov     [rsp+arg_0], rbx
0x140005e21  mov     [rsp+arg_8], rbp
0x140005e26  push    rsi
0x140005e27  push    rdi
0x140005e28  push    r12
0x140005e2a  push    r14
0x140005e2c  push    r15
0x140005e2e  sub     rsp, 20h
0x140005e32  xor     ebx, ebx
0x140005e34  xor     esi, esi
0x140005e36  mov     [rsp+48h+lpszFilePath], rbx
0x140005e3b  xor     r14d, r14d
0x140005e3e  mov     r12, rdx
0x140005e41  mov     r15, rcx
0x140005e44  mov     ebp, 208h
0x140005e49  mov     eax, ebp
0x140005e4b  cmp     rax, rsi
0x140005e4e  jbe     short loc_140005EB0
0x140005e50  mov     esi, eax
0x140005e52  test    rbx, rbx
0x140005e55  jz      short loc_140005E68
0x140005e57  mov     rcx, rbx; void *
0x140005e5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005e5f  mov     [rsp+48h+lpszFilePath], 0
0x140005e68  mov     rdx, rsi
0x140005e6b  lea     rcx, [rsp+48h+lpszFilePath]
0x140005e70  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x140005e75  mov     ebx, eax
0x140005e77  test    eax, eax
0x140005e79  js      loc_140005F3A
0x140005e7f  mov     rbx, [rsp+48h+lpszFilePath]
0x140005e84  xor     r9d, r9d; dwFlags
0x140005e87  mov     rdx, rbx; lpszFilePath
0x140005e8a  mov     r8d, ebp; cchFilePath
0x140005e8d  mov     rcx, r12; hFile
0x140005e90  call    cs:__imp_GetFinalPathNameByHandleW
0x140005e96  mov     ebp, eax
0x140005e98  test    eax, eax
0x140005e9a  jnz     short loc_140005EA7
0x140005e9c  call    HrGetLastFailure
0x140005ea1  mov     edi, eax
0x140005ea3  test    eax, eax
0x140005ea5  js      short loc_140005EF8
0x140005ea7  inc     r14d
0x140005eaa  cmp     r14d, 3
0x140005eae  jl      short loc_140005E49
0x140005eb0  mov     eax, ebp
0x140005eb2  cmp     rax, rsi
0x140005eb5  jbe     loc_140005F7E
0x140005ebb  call    cs:__imp_GetLastError
0x140005ec1  mov     edi, eax
0x140005ec3  test    eax, eax
0x140005ec5  jle     short loc_140005ED0
0x140005ec7  movzx   edi, ax
0x140005eca  or      edi, 80070000h
0x140005ed0  test    edi, edi
0x140005ed2  jns     loc_140005F7E
0x140005ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x140005edf  lea     rax, WPP_GLOBAL_Control
0x140005ee6  cmp     rcx, rax
0x140005ee9  jz      short loc_140005F29
0x140005eeb  test    byte ptr [rcx+1Ch], 1
0x140005eef  jz      short loc_140005F29
0x140005ef1  mov     edx, 12h
0x140005ef6  jmp     short loc_140005F16
0x140005ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140005eff  lea     rax, WPP_GLOBAL_Control
0x140005f06  cmp     rcx, rax
0x140005f09  jz      short loc_140005F29
0x140005f0b  test    byte ptr [rcx+1Ch], 1
0x140005f0f  jz      short loc_140005F29
0x140005f11  mov     edx, 11h
0x140005f16  mov     rcx, [rcx+10h]
0x140005f1a  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x140005f21  mov     r9d, edi
0x140005f24  call    WPP_SF_d
0x140005f29  test    rbx, rbx
0x140005f2c  jz      short loc_140005F36
0x140005f2e  mov     rcx, rbx; void *
0x140005f31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005f36  mov     eax, edi
0x140005f38  jmp     short loc_140005F83
0x140005f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f41  lea     rax, WPP_GLOBAL_Control
0x140005f48  cmp     rcx, rax
0x140005f4b  jz      short loc_140005F6B
0x140005f4d  test    byte ptr [rcx+1Ch], 1
0x140005f51  jz      short loc_140005F6B
0x140005f53  mov     rcx, [rcx+10h]
0x140005f57  lea     r8, WPP_43a8287cf48f3477ddd1e95af916a127_Traceguids
0x140005f5e  mov     edx, 10h
0x140005f63  mov     r9d, ebx
0x140005f66  call    WPP_SF_d
0x140005f6b  mov     rcx, [rsp+48h+lpszFilePath]; void *
0x140005f70  test    rcx, rcx
0x140005f73  jz      short loc_140005F7A
0x140005f75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005f7a  mov     eax, ebx
0x140005f7c  jmp     short loc_140005F83
0x140005f7e  mov     [r15], rbx
0x140005f81  xor     eax, eax
0x140005f83  mov     rbx, [rsp+48h+arg_0]
0x140005f88  mov     rbp, [rsp+48h+arg_8]
0x140005f8d  add     rsp, 20h
0x140005f91  pop     r15
0x140005f93  pop     r14
0x140005f95  pop     r12
0x140005f97  pop     rdi
0x140005f98  pop     rsi
0x140005f99  retn
```
