# CVBAExeFile::CopyExepartToHfile(int,CVBAExeFile::EXEPART *)

- ea: `0x1801acd3c`
- end: `0x1801ad027`
- name: `?CopyExepartToHfile@CVBAExeFile@@AEAAIHPEAUEXEPART@1@@Z`
- size: `747`
- prototype: `unsigned int __fastcall(CVBAExeFile *__hidden this, int, struct CVBAExeFile::EXEPART *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801ac2e0`

## callees

- `0x180174e14`
- `0x180174ff8`
- `0x1801acd3c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801acdae`
- `KERNEL32!GetLastError` at `0x1801ace5f`
- `KERNEL32!GetLastError` at `0x1801acf56`
- `KERNEL32!GetLastError` at `0x1801acf88`
- `KERNEL32!GetLastError` at `0x1801acfdd`
- `KERNEL32!GetLastError` at `0x1801acdae`
- `KERNEL32!GetLastError` at `0x1801ace5f`
- `KERNEL32!GetLastError` at `0x1801acf56`
- `KERNEL32!GetLastError` at `0x1801acf88`
- `KERNEL32!GetLastError` at `0x1801acfdd`
- `KERNEL32!_lread` at `0x1801acf4b`
- `KERNEL32!_lread` at `0x1801acf4b`
- `KERNEL32!_lwrite` at `0x1801acda3`
- `KERNEL32!_lwrite` at `0x1801acf7d`
- `KERNEL32!_lwrite` at `0x1801acfd2`
- `KERNEL32!_lwrite` at `0x1801acda3`
- `KERNEL32!_lwrite` at `0x1801acf7d`
- `KERNEL32!_lwrite` at `0x1801acfd2`
- `KERNEL32!_llseek` at `0x1801ace84`
- `KERNEL32!_llseek` at `0x1801ace97`
- `KERNEL32!_llseek` at `0x1801ace84`
- `KERNEL32!_llseek` at `0x1801ace97`
- `KERNEL32!_lclose` at `0x1801ad008`
- `KERNEL32!_lclose` at `0x1801ad008`
- `KERNEL32!_lopen` at `0x1801ace4e`
- `KERNEL32!_lopen` at `0x1801ace4e`

## pseudocode

```c
__int64 __fastcall CVBAExeFile::CopyExepartToHfile(CVBAExeFile *this, HFILE a2, struct CVBAExeFile::EXEPART *a3)
{
  DWORD LastError; // eax
  unsigned int v4; // eax
  DWORD v6; // eax
  unsigned int v7; // eax
  DWORD v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-8050h]
  LONG v11; // [rsp+24h] [rbp-804Ch]
  HFILE v12; // [rsp+28h] [rbp-8048h]
  int v13; // [rsp+30h] [rbp-8040h]
  int v14; // [rsp+34h] [rbp-803Ch]
  UINT v15; // [rsp+38h] [rbp-8038h]
  int v16; // [rsp+3Ch] [rbp-8034h]
  CHAR v17[8]; // [rsp+40h] [rbp-8030h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8028h]
  _BYTE v19[16]; // [rsp+50h] [rbp-8020h] BYREF
  CHAR Buffer[32768]; // [rsp+60h] [rbp-8010h] BYREF

  v12 = -1;
  v10 = 0;
  *(_DWORD *)v17 = 0;
  if ( (*(_DWORD *)a3 & 0x10000000) != 0 )
  {
    if ( _lwrite(a2, *((LPCCH *)a3 + 1), *((_DWORD *)a3 + 1)) == -1 )
    {
LABEL_3:
      LastError = GetLastError();
      v4 = TiperrOfOFErr(LastError);
      return EberrOfHresult(v4);
    }
    return 0;
  }
  else
  {
    if ( (*(_DWORD *)a3 & 0x40000000) != 0 )
    {
      v12 = _lopen(*((LPCSTR *)a3 + 1), 0);
      if ( v12 != -1 )
      {
        v11 = _llseek(v12, 0, 2);
        _llseek(v12, 0, 0);
        v13 = *((_DWORD *)a3 + 1) - v11;
        goto LABEL_12;
      }
      goto LABEL_3;
    }
    if ( *((int *)a3 + 4) >= 0 )
      v14 = 0;
    else
      v14 = -1;
    HIDWORD(v18) = v14;
    LODWORD(v18) = *((_DWORD *)a3 + 4);
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)a3 + 1) + 40LL))(
      *((_QWORD *)a3 + 1),
      v18,
      0,
      0);
    v11 = *((_DWORD *)a3 + 1);
    v13 = 0;
LABEL_12:
    while ( v11 )
    {
      if ( v11 <= 0x8000 )
        v15 = v11;
      else
        v15 = 0x8000;
      if ( (*(_DWORD *)a3 & 0x40000000) != 0 )
      {
        if ( _lread(v12, Buffer, v15) == -1 )
          goto LABEL_21;
      }
      else
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, CHAR *, _QWORD, _BYTE *))(**((_QWORD **)a3 + 1) + 24LL))(
                *((_QWORD *)a3 + 1),
                Buffer,
                v15,
                v19);
        if ( v16 < 0 )
        {
          v10 = EberrOfHresult((unsigned int)v16);
          break;
        }
      }
      if ( _lwrite(a2, Buffer, v15) == -1 )
      {
LABEL_21:
        v6 = GetLastError();
        v7 = TiperrOfOFErr(v6);
        v10 = EberrOfHresult(v7);
        break;
      }
      v11 -= v15;
    }
    if ( !v10 && v13 > 0 && _lwrite(a2, v17, v13) == -1 )
    {
      v8 = GetLastError();
      v9 = TiperrOfOFErr(v8);
      v10 = EberrOfHresult(v9);
    }
    if ( (*(_DWORD *)a3 & 0x40000000) != 0 )
      _lclose(v12);
    return v10;
  }
}

```

## disassembly

```asm
0x1801acd3c  mov     [rsp-8+arg_10], r8
0x1801acd41  mov     [rsp-8+hFile], edx
0x1801acd45  mov     [rsp-8+arg_0], rcx
0x1801acd4a  push    rbp
0x1801acd4b  mov     rbp, rsp
0x1801acd4e  mov     eax, 8070h
0x1801acd53  call    _alloca_probe
0x1801acd58  sub     rsp, rax
0x1801acd5b  mov     rax, cs:__security_cookie
0x1801acd62  xor     rax, rsp
0x1801acd65  mov     [rbp+var_10], rax
0x1801acd69  mov     [rsp+8070h+var_8048], 0FFFFFFFFh
0x1801acd71  mov     [rsp+8070h+var_8050], 0
0x1801acd79  mov     dword ptr [rsp+8070h+var_8030], 0
0x1801acd81  mov     rax, [rbp+arg_10]
0x1801acd85  mov     eax, [rax]
0x1801acd87  and     eax, 10000000h
0x1801acd8c  test    eax, eax
0x1801acd8e  jz      short loc_1801ACDD0
0x1801acd90  mov     rax, [rbp+arg_10]
0x1801acd94  mov     r8d, [rax+4]; uBytes
0x1801acd98  mov     rax, [rbp+arg_10]
0x1801acd9c  mov     rdx, [rax+8]; lpBuffer
0x1801acda0  mov     ecx, [rbp+hFile]; hFile
0x1801acda3  call    cs:__imp__lwrite
0x1801acda9  cmp     eax, 0FFFFFFFFh
0x1801acdac  jnz     short loc_1801ACDC9
0x1801acdae  call    cs:__imp_GetLastError
0x1801acdb4  mov     ecx, eax
0x1801acdb6  call    TiperrOfOFErr
0x1801acdbb  mov     ecx, eax
0x1801acdbd  call    EberrOfHresult
0x1801acdc2  jmp     loc_1801AD012
0x1801acdc7  jmp     short loc_1801ACDD0
0x1801acdc9  xor     eax, eax
0x1801acdcb  jmp     loc_1801AD012
0x1801acdd0  mov     rax, [rbp+arg_10]
0x1801acdd4  mov     eax, [rax]
0x1801acdd6  and     eax, 40000000h
0x1801acddb  test    eax, eax
0x1801acddd  jnz     short loc_1801ACE44
0x1801acddf  mov     rax, [rbp+arg_10]
0x1801acde3  cmp     dword ptr [rax+10h], 0
0x1801acde7  jge     short loc_1801ACDF3
0x1801acde9  mov     [rsp+8070h+var_803C], 0FFFFFFFFh
0x1801acdf1  jmp     short loc_1801ACDFB
0x1801acdf3  mov     [rsp+8070h+var_803C], 0
0x1801acdfb  mov     eax, [rsp+8070h+var_803C]
0x1801acdff  mov     dword ptr [rsp+8070h+var_8028+4], eax
0x1801ace03  mov     rax, [rbp+arg_10]
0x1801ace07  mov     eax, [rax+10h]
0x1801ace0a  mov     dword ptr [rsp+8070h+var_8028], eax
0x1801ace0e  mov     rax, [rbp+arg_10]
0x1801ace12  mov     rax, [rax+8]
0x1801ace16  mov     rcx, [rbp+arg_10]
0x1801ace1a  mov     rcx, [rcx+8]
0x1801ace1e  mov     rax, [rax]
0x1801ace21  xor     r9d, r9d
0x1801ace24  xor     r8d, r8d
0x1801ace27  mov     rdx, [rsp+8070h+var_8028]
0x1801ace2c  call    qword ptr [rax+28h]
0x1801ace2f  mov     rax, [rbp+arg_10]
0x1801ace33  mov     eax, [rax+4]
0x1801ace36  mov     [rsp+8070h+var_804C], eax
0x1801ace3a  mov     [rsp+8070h+var_8040], 0
0x1801ace42  jmp     short loc_1801ACEBE
0x1801ace44  xor     edx, edx; iReadWrite
0x1801ace46  mov     rax, [rbp+arg_10]
0x1801ace4a  mov     rcx, [rax+8]; lpPathName
0x1801ace4e  call    cs:__imp__lopen
0x1801ace54  mov     [rsp+8070h+var_8048], eax
0x1801ace58  cmp     [rsp+8070h+var_8048], 0FFFFFFFFh
0x1801ace5d  jnz     short loc_1801ACE78
0x1801ace5f  call    cs:__imp_GetLastError
0x1801ace65  mov     ecx, eax
0x1801ace67  call    TiperrOfOFErr
0x1801ace6c  mov     ecx, eax
0x1801ace6e  call    EberrOfHresult
0x1801ace73  jmp     loc_1801AD012
0x1801ace78  mov     r8d, 2; iOrigin
0x1801ace7e  xor     edx, edx; lOffset
0x1801ace80  mov     ecx, [rsp+8070h+var_8048]; hFile
0x1801ace84  call    cs:__imp__llseek
0x1801ace8a  mov     [rsp+8070h+var_804C], eax
0x1801ace8e  xor     r8d, r8d; iOrigin
0x1801ace91  xor     edx, edx; lOffset
0x1801ace93  mov     ecx, [rsp+8070h+var_8048]; hFile
0x1801ace97  call    cs:__imp__llseek
0x1801ace9d  mov     rax, [rbp+arg_10]
0x1801acea1  mov     ecx, [rsp+8070h+var_804C]
0x1801acea5  mov     eax, [rax+4]
0x1801acea8  sub     eax, ecx
0x1801aceaa  mov     [rsp+8070h+var_8040], eax
0x1801aceae  cmp     [rsp+8070h+var_8050], 0
0x1801aceb3  jz      short loc_1801ACEBE
0x1801aceb5  mov     eax, [rsp+8070h+var_8050]
0x1801aceb9  jmp     loc_1801AD012
0x1801acebe  cmp     [rsp+8070h+var_804C], 0
0x1801acec3  jz      loc_1801ACFB7
0x1801acec9  cmp     [rsp+8070h+var_804C], 8000h
0x1801aced1  jle     short loc_1801ACEDD
0x1801aced3  mov     [rsp+8070h+var_8038], 8000h
0x1801acedb  jmp     short loc_1801ACEE5
0x1801acedd  mov     eax, [rsp+8070h+var_804C]
0x1801acee1  mov     [rsp+8070h+var_8038], eax
0x1801acee5  mov     eax, [rsp+8070h+var_8038]
0x1801acee9  mov     [rsp+8070h+uBytes], eax
0x1801aceed  mov     rax, [rbp+arg_10]
0x1801acef1  mov     eax, [rax]
0x1801acef3  and     eax, 40000000h
0x1801acef8  test    eax, eax
0x1801acefa  jnz     short loc_1801ACF3D
0x1801acefc  mov     rax, [rbp+arg_10]
0x1801acf00  mov     rax, [rax+8]
0x1801acf04  mov     rcx, [rbp+arg_10]
0x1801acf08  mov     rcx, [rcx+8]
0x1801acf0c  mov     rax, [rax]
0x1801acf0f  lea     r9, [rsp+8070h+var_8020]
0x1801acf14  mov     r8d, [rsp+8070h+uBytes]
0x1801acf19  lea     rdx, [rsp+8070h+Buffer]
0x1801acf1e  call    qword ptr [rax+18h]
0x1801acf21  mov     [rsp+8070h+var_8034], eax
0x1801acf25  cmp     [rsp+8070h+var_8034], 0
0x1801acf2a  jge     short loc_1801ACF3B
0x1801acf2c  mov     ecx, [rsp+8070h+var_8034]
0x1801acf30  call    EberrOfHresult
0x1801acf35  mov     [rsp+8070h+var_8050], eax
0x1801acf39  jmp     short loc_1801ACFB7
0x1801acf3b  jmp     short loc_1801ACF70
0x1801acf3d  mov     r8d, [rsp+8070h+uBytes]; uBytes
0x1801acf42  lea     rdx, [rsp+8070h+Buffer]; lpBuffer
0x1801acf47  mov     ecx, [rsp+8070h+var_8048]; hFile
0x1801acf4b  call    cs:__imp__lread
0x1801acf51  cmp     eax, 0FFFFFFFFh
0x1801acf54  jnz     short loc_1801ACF70
0x1801acf56  call    cs:__imp_GetLastError
0x1801acf5c  mov     ecx, eax
0x1801acf5e  call    TiperrOfOFErr
0x1801acf63  mov     ecx, eax
0x1801acf65  call    EberrOfHresult
0x1801acf6a  mov     [rsp+8070h+var_8050], eax
0x1801acf6e  jmp     short loc_1801ACFB7
0x1801acf70  mov     r8d, [rsp+8070h+uBytes]; uBytes
0x1801acf75  lea     rdx, [rsp+8070h+Buffer]; lpBuffer
0x1801acf7a  mov     ecx, [rbp+hFile]; hFile
0x1801acf7d  call    cs:__imp__lwrite
0x1801acf83  cmp     eax, 0FFFFFFFFh
0x1801acf86  jnz     short loc_1801ACFA2
0x1801acf88  call    cs:__imp_GetLastError
0x1801acf8e  mov     ecx, eax
0x1801acf90  call    TiperrOfOFErr
0x1801acf95  mov     ecx, eax
0x1801acf97  call    EberrOfHresult
0x1801acf9c  mov     [rsp+8070h+var_8050], eax
0x1801acfa0  jmp     short loc_1801ACFB7
0x1801acfa2  mov     eax, [rsp+8070h+uBytes]
0x1801acfa6  mov     ecx, [rsp+8070h+var_804C]
0x1801acfaa  sub     ecx, eax
0x1801acfac  mov     eax, ecx
0x1801acfae  mov     [rsp+8070h+var_804C], eax
0x1801acfb2  jmp     loc_1801ACEBE
0x1801acfb7  cmp     [rsp+8070h+var_8050], 0
0x1801acfbc  jnz     short loc_1801ACFF5
0x1801acfbe  cmp     [rsp+8070h+var_8040], 0
0x1801acfc3  jle     short loc_1801ACFF5
0x1801acfc5  mov     r8d, [rsp+8070h+var_8040]; uBytes
0x1801acfca  lea     rdx, [rsp+8070h+var_8030]; lpBuffer
0x1801acfcf  mov     ecx, [rbp+hFile]; hFile
0x1801acfd2  call    cs:__imp__lwrite
0x1801acfd8  cmp     eax, 0FFFFFFFFh
0x1801acfdb  jnz     short loc_1801ACFF5
0x1801acfdd  call    cs:__imp_GetLastError
0x1801acfe3  mov     ecx, eax
0x1801acfe5  call    TiperrOfOFErr
0x1801acfea  mov     ecx, eax
0x1801acfec  call    EberrOfHresult
0x1801acff1  mov     [rsp+8070h+var_8050], eax
0x1801acff5  mov     rax, [rbp+arg_10]
0x1801acff9  mov     eax, [rax]
0x1801acffb  and     eax, 40000000h
0x1801ad000  test    eax, eax
0x1801ad002  jz      short loc_1801AD00E
0x1801ad004  mov     ecx, [rsp+8070h+var_8048]; hFile
0x1801ad008  call    cs:__imp__lclose
0x1801ad00e  mov     eax, [rsp+8070h+var_8050]
0x1801ad012  mov     rcx, [rbp+var_10]
0x1801ad016  xor     rcx, rsp; StackCookie
0x1801ad019  call    __security_check_cookie
0x1801ad01e  add     rsp, 8070h
0x1801ad025  pop     rbp
0x1801ad026  retn
```
