# Base::TempFile::GeneratePath(void)

- ea: `0x18002eae0`
- end: `0x18002ec3f`
- name: `?GeneratePath@TempFile@Base@@AEAAXXZ`
- size: `351`
- prototype: `void __fastcall(Base::TempFile *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180079e30`

## callees

- `0x1800041a4`
- `0x180004908`
- `0x180004e88`
- `0x180025f90`
- `0x18002eae0`
- `0x18002ec48`
- `0x18002ec74`
- `0x18002ecc8`
- `0x18005ea5c`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x18002eb61`
- `KERNEL32!GetTempPath2W` at `0x18002eb61`
- `KERNEL32!GetTempFileNameW` at `0x18002ebf8`
- `KERNEL32!GetTempFileNameW` at `0x18002ebf8`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ec02`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ec02`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Base::TempFile::GeneratePath(Base::TempFile *this)
{
  const struct Base::String *v2; // rsi
  __int64 v3; // r8
  const WCHAR *v4; // rbx
  const WCHAR *v5; // rdi
  int v6; // ecx
  Base *v7; // rcx
  LPCWSTR lpPathName; // [rsp+40h] [rbp+20h] BYREF
  LPCWSTR lpPrefixString; // [rsp+48h] [rbp+28h] BYREF

  if ( !*((_BYTE *)this + 24) )
  {
    v2 = (Base::TempFile *)((char *)this + 16);
    Base::String::String((Base::String *)&lpPathName, (Base::TempFile *)((char *)this + 16));
    Base::Path::RemoveFileSpec((Base::Path *)&lpPathName);
    v4 = lpPathName;
    if ( !*((_DWORD *)lpPathName - 4) || !Base::Path::FileExists((Base::Path *)&lpPathName) )
    {
      if ( ((*((_DWORD *)v4 - 3) - 260) | (1 - *((_DWORD *)v4 - 2))) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpPathName, 260, v3);
        v4 = lpPathName;
      }
      if ( (unsigned int)GetTempPath2W(261, v4) - 1 > 0x103 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, L".");
        v4 = lpPathName;
      }
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&lpPathName, 0xFFFFFFFFLL);
    }
    Base::String::String((Base::String *)&lpPrefixString, v2);
    Base::Path::StripPath((Base::Path *)&lpPrefixString);
    v5 = lpPrefixString;
    if ( !*((_DWORD *)lpPrefixString - 4) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPrefixString, L"~PI");
      v5 = lpPrefixString;
    }
    v6 = *(_DWORD *)(*(_QWORD *)v2 - 12LL) - 260;
    if ( (v6 | (1 - *(_DWORD *)(*(_QWORD *)v2 - 8LL))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(
        v2,
        260,
        v6 | (unsigned int)(1 - *(_DWORD *)(*(_QWORD *)v2 - 8LL)));
    if ( !GetTempFileNameW(v4, v5, 0, *(LPWSTR *)v2) )
    {
      Base::ThrowLastError(v7);
      __debugbreak();
    }
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v2, 0xFFFFFFFFLL);
    *((_BYTE *)this + 24) = 1;
    Base::String::~String((Base::String *)&lpPrefixString);
    Base::String::~String((Base::String *)&lpPathName);
  }
}

```

## disassembly

```asm
0x18002eae0  mov     [rsp-18h+arg_10], rbx
0x18002eae5  mov     [rsp-18h+arg_18], rsi
0x18002eaea  push    rbp
0x18002eaeb  push    rdi
0x18002eaec  push    r14
0x18002eaee  mov     rbp, rsp
0x18002eaf1  sub     rsp, 20h
0x18002eaf5  mov     r14, rcx
0x18002eaf8  cmp     byte ptr [rcx+18h], 0
0x18002eafc  jnz     loc_18002EC2C
0x18002eb02  lea     rsi, [rcx+10h]
0x18002eb06  mov     rdx, rsi; struct Base::String *
0x18002eb09  lea     rcx, [rbp+lpPathName]; this
0x18002eb0d  call    ??0String@Base@@QEAA@AEBV01@@Z; Base::String::String(Base::String const &)
0x18002eb12  nop
0x18002eb13  lea     rcx, [rbp+lpPathName]; this
0x18002eb17  call    ?RemoveFileSpec@Path@Base@@QEAAAEAV12@XZ; Base::Path::RemoveFileSpec(void)
0x18002eb1c  mov     rbx, [rbp+lpPathName]
0x18002eb20  cmp     dword ptr [rbx-10h], 0
0x18002eb24  jz      short loc_18002EB33
0x18002eb26  lea     rcx, [rbp+lpPathName]; this
0x18002eb2a  call    ?FileExists@Path@Base@@QEBA_NXZ; Base::Path::FileExists(void)
0x18002eb2f  test    al, al
0x18002eb31  jnz     short loc_18002EB90
0x18002eb33  mov     ecx, 1
0x18002eb38  sub     ecx, [rbx-8]
0x18002eb3b  mov     eax, [rbx-0Ch]
0x18002eb3e  sub     eax, 104h
0x18002eb43  or      ecx, eax
0x18002eb45  jge     short loc_18002EB59
0x18002eb47  mov     edx, 104h
0x18002eb4c  lea     rcx, [rbp+lpPathName]
0x18002eb50  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002eb55  mov     rbx, [rbp+lpPathName]
0x18002eb59  mov     rdx, rbx
0x18002eb5c  mov     ecx, 105h
0x18002eb61  call    cs:__imp_GetTempPath2W
0x18002eb67  dec     eax
0x18002eb69  cmp     eax, 103h
0x18002eb6e  jbe     short loc_18002EB84
0x18002eb70  lea     rdx, asc_18008DE48; "."
0x18002eb77  lea     rcx, [rbp+lpPathName]
0x18002eb7b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002eb80  mov     rbx, [rbp+lpPathName]
0x18002eb84  or      edx, 0FFFFFFFFh
0x18002eb87  lea     rcx, [rbp+lpPathName]
0x18002eb8b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002eb90  mov     rdx, rsi; struct Base::String *
0x18002eb93  lea     rcx, [rbp+lpPrefixString]; this
0x18002eb97  call    ??0String@Base@@QEAA@AEBV01@@Z; Base::String::String(Base::String const &)
0x18002eb9c  nop
0x18002eb9d  lea     rcx, [rbp+lpPrefixString]; this
0x18002eba1  call    ?StripPath@Path@Base@@QEAAAEAV12@XZ; Base::Path::StripPath(void)
0x18002eba6  mov     rdi, [rbp+lpPrefixString]
0x18002ebaa  cmp     dword ptr [rdi-10h], 0
0x18002ebae  jnz     short loc_18002EBC4
0x18002ebb0  lea     rdx, aPi; "~PI"
0x18002ebb7  lea     rcx, [rbp+lpPrefixString]
0x18002ebbb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002ebc0  mov     rdi, [rbp+lpPrefixString]
0x18002ebc4  mov     rax, [rsi]
0x18002ebc7  mov     r8d, 1
0x18002ebcd  sub     r8d, [rax-8]
0x18002ebd1  mov     ecx, [rax-0Ch]
0x18002ebd4  sub     ecx, 104h
0x18002ebda  or      r8d, ecx
0x18002ebdd  jge     short loc_18002EBEC
0x18002ebdf  mov     edx, 104h
0x18002ebe4  mov     rcx, rsi
0x18002ebe7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002ebec  mov     r9, [rsi]; lpTempFileName
0x18002ebef  xor     r8d, r8d; uUnique
0x18002ebf2  mov     rdx, rdi; lpPrefixString
0x18002ebf5  mov     rcx, rbx; lpPathName
0x18002ebf8  call    cs:__imp_GetTempFileNameW
0x18002ebfe  test    eax, eax
0x18002ec00  jnz     short loc_18002EC09
0x18002ec02  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002ec08  int     3; Trap to Debugger
0x18002ec09  or      edx, 0FFFFFFFFh
0x18002ec0c  mov     rcx, rsi
0x18002ec0f  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002ec14  mov     byte ptr [r14+18h], 1
0x18002ec19  lea     rcx, [rbp+lpPrefixString]; this
0x18002ec1d  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002ec22  nop
0x18002ec23  lea     rcx, [rbp+lpPathName]; this
0x18002ec27  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002ec2c  mov     rbx, [rsp+20h+arg_10]
0x18002ec31  mov     rsi, [rsp+20h+arg_18]
0x18002ec36  add     rsp, 20h
0x18002ec3a  pop     r14
0x18002ec3c  pop     rdi
0x18002ec3d  pop     rbp
0x18002ec3e  retn
```
