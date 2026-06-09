# FSMakeTempDirPath

- ea: `0x1800033c0`
- end: `0x18000350e`
- name: `FSMakeTempDirPath`
- size: `334`
- prototype: `_BOOL8 __fastcall(_WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b7a0`
- `0x18000dabc`

## callees

- `0x180002f2c`
- `0x1800030c4`
- `0x1800033c0`
- `0x180003514`
- `0x180013700`

## import_xrefs

- `msvcrt!time` at `0x180003417`
- `msvcrt!time` at `0x180003417`
- `KERNEL32!SetLastError` at `0x1800034d8`
- `KERNEL32!SetLastError` at `0x1800034d8`
- `KERNEL32!GetFileAttributesW` at `0x180003458`
- `KERNEL32!GetFileAttributesW` at `0x180003458`
- `KERNEL32!GetLastError` at `0x180003477`
- `KERNEL32!GetLastError` at `0x180003477`
- `KERNEL32!GetTempPath2W` at `0x1800033fe`
- `KERNEL32!GetTempPath2W` at `0x1800033fe`

## pseudocode

```c
_BOOL8 __fastcall FSMakeTempDirPath(_WORD *a1)
{
  __int64 v2; // rdi
  unsigned int TempPath2W; // ebx
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rbp
  DWORD FileAttributesW; // eax
  DWORD LastError; // ebx
  WCHAR *v9; // rcx
  __int64 v10; // rax
  _WORD *v11; // rcx
  time_t Time; // [rsp+20h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-238h] BYREF

  v2 = 260;
  Time = 0;
  TempPath2W = GetTempPath2W(260, FileName);
  if ( TempPath2W )
  {
    if ( TempPath2W <= 0x104 )
    {
      time(&Time);
      v4 = TempPath2W;
      v5 = 259LL - TempPath2W;
      v6 = &FileName[v4];
      while ( (int)StringCchPrintfW(v6, v5, L"%lu", (unsigned int)Time) >= 0 )
      {
        ++Time;
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
        {
          if ( !(unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(FileName, 0) )
            goto LABEL_8;
          LastError = 0;
          v9 = FileName;
          v10 = 2147483646;
          do
          {
            if ( !v10 )
              break;
            if ( !*v9 )
              break;
            *a1++ = *v9++;
            --v10;
            --v2;
          }
          while ( v2 );
          v11 = a1 - 1;
          if ( v2 )
            v11 = a1;
          *v11 = 0;
          if ( !v2 )
          {
            FSRemoveDirPath(FileName);
            LastError = 13;
          }
          goto LABEL_18;
        }
      }
    }
    LastError = 122;
  }
  else
  {
LABEL_8:
    LastError = GetLastError();
  }
LABEL_18:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800033c0  mov     [rsp+arg_8], rbx
0x1800033c5  mov     [rsp+arg_10], rbp
0x1800033ca  push    rsi
0x1800033cb  push    rdi
0x1800033cc  push    r14
0x1800033ce  sub     rsp, 250h
0x1800033d5  mov     rax, cs:__security_cookie
0x1800033dc  xor     rax, rsp
0x1800033df  mov     [rsp+268h+var_28], rax
0x1800033e7  mov     rsi, rcx
0x1800033ea  lea     rdx, [rsp+268h+FileName]
0x1800033ef  mov     edi, 104h
0x1800033f4  xor     r14d, r14d
0x1800033f7  mov     ecx, edi
0x1800033f9  mov     [rsp+268h+Time], r14
0x1800033fe  call    cs:__imp_GetTempPath2W
0x180003404  mov     ebx, eax
0x180003406  test    eax, eax
0x180003408  jz      short loc_180003477
0x18000340a  cmp     ebx, edi
0x18000340c  ja      loc_1800034D1
0x180003412  lea     rcx, [rsp+268h+Time]; Time
0x180003417  call    cs:__imp_time
0x18000341d  mov     eax, ebx
0x18000341f  lea     rbp, [rsp+268h+FileName]
0x180003424  lea     ebx, [rdi-1]
0x180003427  sub     rbx, rax
0x18000342a  lea     rbp, [rbp+rax*2+0]
0x18000342f  mov     r9d, dword ptr [rsp+268h+Time]
0x180003434  lea     r8, aLu; "%lu"
0x18000343b  mov     rdx, rbx; unsigned __int64
0x18000343e  mov     rcx, rbp; unsigned __int16 *
0x180003441  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003446  test    eax, eax
0x180003448  js      loc_1800034D1
0x18000344e  inc     [rsp+268h+Time]
0x180003453  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180003458  call    cs:__imp_GetFileAttributesW
0x18000345e  cmp     eax, 0FFFFFFFFh
0x180003461  jz      short loc_180003467
0x180003463  test    al, 10h
0x180003465  jnz     short loc_18000342F
0x180003467  xor     edx, edx; StringSecurityDescriptor
0x180003469  lea     rcx, [rsp+268h+FileName]; lpFileName
0x18000346e  call    FSMakeDirPathExist_StringSecurityDescriptor
0x180003473  test    eax, eax
0x180003475  jnz     short loc_180003481
0x180003477  call    cs:__imp_GetLastError
0x18000347d  mov     ebx, eax
0x18000347f  jmp     short loc_1800034D6
0x180003481  mov     ebx, r14d
0x180003484  lea     rcx, [rsp+268h+FileName]
0x180003489  mov     eax, 7FFFFFFEh
0x18000348e  test    rax, rax
0x180003491  jz      short loc_1800034AF
0x180003493  movzx   edx, word ptr [rcx]
0x180003496  test    dx, dx
0x180003499  jz      short loc_1800034AF
0x18000349b  mov     [rsi], dx
0x18000349e  add     rcx, 2
0x1800034a2  add     rsi, 2
0x1800034a6  dec     rax
0x1800034a9  sub     rdi, 1
0x1800034ad  jnz     short loc_18000348E
0x1800034af  test    rdi, rdi
0x1800034b2  lea     rcx, [rsi-2]
0x1800034b6  cmovnz  rcx, rsi
0x1800034ba  mov     [rcx], r14w
0x1800034be  jnz     short loc_1800034D6
0x1800034c0  lea     rcx, [rsp+268h+FileName]
0x1800034c5  call    FSRemoveDirPath
0x1800034ca  mov     ebx, 0Dh
0x1800034cf  jmp     short loc_1800034D6
0x1800034d1  mov     ebx, 7Ah ; 'z'
0x1800034d6  mov     ecx, ebx; dwErrCode
0x1800034d8  call    cs:__imp_SetLastError
0x1800034de  test    ebx, ebx
0x1800034e0  mov     eax, r14d
0x1800034e3  setz    al
0x1800034e6  mov     rcx, [rsp+268h+var_28]
0x1800034ee  xor     rcx, rsp; StackCookie
0x1800034f1  call    __security_check_cookie
0x1800034f6  lea     r11, [rsp+268h+var_18]
0x1800034fe  mov     rbx, [r11+28h]
0x180003502  mov     rbp, [r11+30h]
0x180003506  mov     rsp, r11
0x180003509  pop     r14
0x18000350b  pop     rdi
0x18000350c  pop     rsi
0x18000350d  retn
```
