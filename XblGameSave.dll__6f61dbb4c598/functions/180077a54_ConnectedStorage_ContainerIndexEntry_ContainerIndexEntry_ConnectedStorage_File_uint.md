# ConnectedStorage::ContainerIndexEntry::ContainerIndexEntry(ConnectedStorage::File *,uint)

- ea: `0x180077a54`
- end: `0x180077d58`
- name: `??0ContainerIndexEntry@ConnectedStorage@@AEAA@PEAVFile@1@I@Z`
- size: `772`
- prototype: `HSTRING *__fastcall(HSTRING *newString, void **this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180064c74`

## callees

- `0x180003c70`
- `0x180004300`
- `0x180004754`
- `0x180004760`
- `0x180012ed8`
- `0x18001d3bc`
- `0x18001d3f0`
- `0x18004f85c`
- `0x180050da0`
- `0x1800639d4`
- `0x180077a54`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c75`

## pseudocode

```c
HSTRING *__fastcall ConnectedStorage::ContainerIndexEntry::ContainerIndexEntry(
        HSTRING *newString,
        void **this,
        unsigned int a3)
{
  unsigned int v6; // edx
  unsigned int v7; // esi
  unsigned int v8; // edx
  __int64 v9; // rsi
  unsigned int v10; // edx
  unsigned int v11; // esi
  _DWORD *v12; // rsi
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[8]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING *v17; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v18[128]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v19[256]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v20[256]; // [rsp+350h] [rbp+250h] BYREF

  v17 = newString;
  *newString = 0;
  newString[1] = 0;
  newString[2] = 0;
  LODWORD(string) = 0;
  ConnectedStorage::File::Read(this, 4u, &string);
  v7 = (unsigned int)string;
  if ( (unsigned int)string > 0xFF )
  {
    ConnectedStorage::EventWriteCorruptContainerIndexInvalidEntryName((ConnectedStorage *)(unsigned int)string, v6);
    ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException((ConnectedStorage::CorruptIndexFileException *)pExceptionObject);
    throw (ConnectedStorage::CorruptIndexFileException *)pExceptionObject;
  }
  memset_0(v19, 0, sizeof(v19));
  ConnectedStorage::File::Read(this, 2 * v7, v19);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, v7, v19);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString);
  WindowsDeleteString(string);
  if ( a3 >= 0xC )
  {
    LODWORD(string) = 0;
    ConnectedStorage::File::Read(this, 4u, &string);
    v9 = (unsigned int)string;
    if ( (unsigned int)string > 0x7F )
    {
      ConnectedStorage::EventWriteCorruptContainerIndexInvalidEntryName((ConnectedStorage *)(unsigned int)string, v8);
      ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException((ConnectedStorage::CorruptIndexFileException *)pExceptionObject);
      throw (ConnectedStorage::CorruptIndexFileException *)pExceptionObject;
    }
    ConnectedStorage::File::Read(this, 2 * (_DWORD)string, v18);
    if ( (unsigned __int64)(2 * v9) >= 0x100 )
      _report_rangecheckfailure();
    v18[v9] = 0;
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, v9, v18);
    ConnectedStorage::SimpleHStringWrapper::operator=(newString + 1);
    WindowsDeleteString(string);
  }
  LODWORD(string) = 0;
  ConnectedStorage::File::Read(this, 4u, &string);
  v11 = (unsigned int)string;
  if ( (unsigned int)string >= 0x100 )
  {
    ConnectedStorage::EventWriteCorruptContainerIndexEtagLength((ConnectedStorage *)(unsigned int)string, v10);
    ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException((ConnectedStorage::CorruptIndexFileException *)pExceptionObject);
    throw (ConnectedStorage::CorruptIndexFileException *)pExceptionObject;
  }
  memset_0(v20, 0, sizeof(v20));
  ConnectedStorage::File::Read(this, 2 * v11, v20);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, v11, v20);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString + 2);
  WindowsDeleteString(string);
  ConnectedStorage::File::Read(this, 1u, newString + 3);
  v12 = (_DWORD *)newString + 7;
  ConnectedStorage::File::Read(this, 4u, (char *)newString + 28);
  ConnectedStorage::File::Read(this, 0x10u, newString + 4);
  ConnectedStorage::File::Read(this, 8u, newString + 6);
  ConnectedStorage::File::Read(this, 4u, newString + 7);
  ConnectedStorage::File::Read(this, 4u, v15);
  if ( a3 > 0xA )
  {
    ConnectedStorage::File::Read(this, 8u, newString + 8);
  }
  else
  {
    LODWORD(string) = 0;
    ConnectedStorage::File::Read(this, 4u, &string);
    newString[8] = (HSTRING)(unsigned int)string;
  }
  if ( !*v12 )
    *v12 = 1;
  *((_BYTE *)newString + 25) = *((_BYTE *)newString + 24);
  return newString;
}

```

## disassembly

```asm
0x180077a54  mov     [rsp-8+arg_10], rbx
0x180077a59  mov     [rsp-8+arg_18], rsi
0x180077a5e  push    rbp
0x180077a5f  push    rdi
0x180077a60  push    r12
0x180077a62  push    r14
0x180077a64  push    r15
0x180077a66  lea     rbp, [rsp-460h]
0x180077a6e  sub     rsp, 560h
0x180077a75  mov     rax, cs:__security_cookie
0x180077a7c  xor     rax, rsp
0x180077a7f  mov     [rbp+480h+var_30], rax
0x180077a86  mov     r12d, r8d
0x180077a89  mov     rdi, rdx
0x180077a8c  mov     rbx, rcx
0x180077a8f  mov     [rsp+580h+var_538], rcx
0x180077a94  mov     qword ptr [rcx], 0
0x180077a9b  mov     qword ptr [rcx+8], 0
0x180077aa3  mov     qword ptr [rcx+10h], 0
0x180077aab  mov     dword ptr [rsp+580h+string], 0
0x180077ab3  lea     r8, [rsp+580h+string]; void *
0x180077ab8  mov     edx, 4; unsigned int
0x180077abd  mov     rcx, rdi; this
0x180077ac0  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077ac5  mov     esi, dword ptr [rsp+580h+string]
0x180077ac9  cmp     esi, 0FFh
0x180077acf  jbe     short loc_180077AF4
0x180077ad1  mov     ecx, esi; this
0x180077ad3  call    ?EventWriteCorruptContainerIndexInvalidEntryName@ConnectedStorage@@YAXI@Z; ConnectedStorage::EventWriteCorruptContainerIndexInvalidEntryName(uint)
0x180077ad8  lea     rcx, [rsp+580h+pExceptionObject]; this
0x180077add  call    ??0CorruptIndexFileException@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException(void)
0x180077ae2  lea     rdx, _TI2?AVCorruptIndexFileException@ConnectedStorage@@; pThrowInfo
0x180077ae9  lea     rcx, [rsp+580h+pExceptionObject]; pExceptionObject
0x180077aee  call    _CxxThrowException_0
0x180077af4  xor     edx, edx; Val
0x180077af6  mov     r8d, 200h; Size
0x180077afc  lea     rcx, [rbp+480h+var_430]; void *
0x180077b00  call    memset_0
0x180077b05  lea     edx, [rsi+rsi]; unsigned int
0x180077b08  lea     r8, [rbp+480h+var_430]; void *
0x180077b0c  mov     rcx, rdi; this
0x180077b0f  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077b14  lea     r8, [rbp+480h+var_430]; unsigned __int16 *
0x180077b18  mov     edx, esi; unsigned int
0x180077b1a  lea     rcx, [rsp+580h+string]; string
0x180077b1f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@IPEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(uint,ushort const *)
0x180077b24  nop
0x180077b25  mov     rdx, rax
0x180077b28  mov     rcx, rbx; newString
0x180077b2b  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180077b30  nop
0x180077b31  mov     rcx, [rsp+580h+string]; string
0x180077b36  call    cs:__imp_WindowsDeleteString
0x180077b3c  cmp     r12d, 0Ch
0x180077b40  jb      loc_180077BDA
0x180077b46  mov     dword ptr [rsp+580h+string], 0
0x180077b4e  lea     r8, [rsp+580h+string]; void *
0x180077b53  mov     edx, 4; unsigned int
0x180077b58  mov     rcx, rdi; this
0x180077b5b  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077b60  mov     esi, dword ptr [rsp+580h+string]
0x180077b64  cmp     esi, 7Fh
0x180077b67  jbe     short loc_180077B8C
0x180077b69  mov     ecx, esi; this
0x180077b6b  call    ?EventWriteCorruptContainerIndexInvalidEntryName@ConnectedStorage@@YAXI@Z; ConnectedStorage::EventWriteCorruptContainerIndexInvalidEntryName(uint)
0x180077b70  lea     rcx, [rsp+580h+pExceptionObject]; this
0x180077b75  call    ??0CorruptIndexFileException@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException(void)
0x180077b7a  lea     rdx, _TI2?AVCorruptIndexFileException@ConnectedStorage@@; pThrowInfo
0x180077b81  lea     rcx, [rsp+580h+pExceptionObject]; pExceptionObject
0x180077b86  call    _CxxThrowException_0
0x180077b8c  lea     edx, [rsi+rsi]; unsigned int
0x180077b8f  lea     r8, [rsp+580h+var_530]; void *
0x180077b94  mov     rcx, rdi; this
0x180077b97  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077b9c  lea     rcx, [rsi+rsi]
0x180077ba0  cmp     rcx, 100h
0x180077ba7  jnb     short loc_180077C23
0x180077ba9  xor     eax, eax
0x180077bab  mov     [rsp+rcx+580h+var_530], ax
0x180077bb0  lea     r8, [rsp+580h+var_530]; unsigned __int16 *
0x180077bb5  mov     edx, esi; unsigned int
0x180077bb7  lea     rcx, [rsp+580h+string]; string
0x180077bbc  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@IPEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(uint,ushort const *)
0x180077bc1  nop
0x180077bc2  mov     rdx, rax
0x180077bc5  lea     rcx, [rbx+8]; newString
0x180077bc9  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180077bce  nop
0x180077bcf  mov     rcx, [rsp+580h+string]; string
0x180077bd4  call    cs:__imp_WindowsDeleteString
0x180077bda  mov     dword ptr [rsp+580h+string], 0
0x180077be2  lea     r8, [rsp+580h+string]; void *
0x180077be7  mov     edx, 4; unsigned int
0x180077bec  mov     rcx, rdi; this
0x180077bef  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077bf4  mov     esi, dword ptr [rsp+580h+string]
0x180077bf8  cmp     esi, 100h
0x180077bfe  jb      short loc_180077C29
0x180077c00  mov     ecx, esi; this
0x180077c02  call    ?EventWriteCorruptContainerIndexEtagLength@ConnectedStorage@@YAXI@Z; ConnectedStorage::EventWriteCorruptContainerIndexEtagLength(uint)
0x180077c07  lea     rcx, [rsp+580h+pExceptionObject]; this
0x180077c0c  call    ??0CorruptIndexFileException@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CorruptIndexFileException::CorruptIndexFileException(void)
0x180077c11  lea     rdx, _TI2?AVCorruptIndexFileException@ConnectedStorage@@; pThrowInfo
0x180077c18  lea     rcx, [rsp+580h+pExceptionObject]; pExceptionObject
0x180077c1d  call    _CxxThrowException_0
0x180077c23  call    __report_rangecheckfailure
0x180077c29  xor     edx, edx; Val
0x180077c2b  mov     r8d, 200h; Size
0x180077c31  lea     rcx, [rbp+480h+var_230]; void *
0x180077c38  call    memset_0
0x180077c3d  lea     edx, [rsi+rsi]; unsigned int
0x180077c40  lea     r8, [rbp+480h+var_230]; void *
0x180077c47  mov     rcx, rdi; this
0x180077c4a  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077c4f  lea     r8, [rbp+480h+var_230]; unsigned __int16 *
0x180077c56  mov     edx, esi; unsigned int
0x180077c58  lea     rcx, [rsp+580h+string]; string
0x180077c5d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@IPEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(uint,ushort const *)
0x180077c62  nop
0x180077c63  mov     rdx, rax
0x180077c66  lea     rcx, [rbx+10h]; newString
0x180077c6a  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180077c6f  nop
0x180077c70  mov     rcx, [rsp+580h+string]; string
0x180077c75  call    cs:__imp_WindowsDeleteString
0x180077c7b  lea     r8, [rbx+18h]; void *
0x180077c7f  mov     edx, 1; unsigned int
0x180077c84  mov     rcx, rdi; this
0x180077c87  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077c8c  lea     rsi, [rbx+1Ch]
0x180077c90  mov     r8, rsi; void *
0x180077c93  mov     r15d, 4
0x180077c99  mov     edx, r15d; unsigned int
0x180077c9c  mov     rcx, rdi; this
0x180077c9f  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077ca4  lea     r8, [rbx+20h]; void *
0x180077ca8  lea     edx, [r15+0Ch]; unsigned int
0x180077cac  mov     rcx, rdi; this
0x180077caf  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077cb4  lea     r8, [rbx+30h]; void *
0x180077cb8  lea     edx, [r15+4]; unsigned int
0x180077cbc  mov     rcx, rdi; this
0x180077cbf  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077cc4  lea     r8, [rbx+38h]; void *
0x180077cc8  mov     edx, r15d; unsigned int
0x180077ccb  mov     rcx, rdi; this
0x180077cce  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077cd3  lea     r8, [rsp+580h+var_558]; void *
0x180077cd8  mov     edx, r15d; unsigned int
0x180077cdb  mov     rcx, rdi; this
0x180077cde  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077ce3  mov     rcx, rdi; this
0x180077ce6  cmp     r12d, 0Ah
0x180077cea  ja      short loc_180077D0B
0x180077cec  mov     dword ptr [rsp+580h+string], 0
0x180077cf4  lea     r8, [rsp+580h+string]; void *
0x180077cf9  mov     edx, r15d; unsigned int
0x180077cfc  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077d01  mov     eax, dword ptr [rsp+580h+string]
0x180077d05  mov     [rbx+40h], rax
0x180077d09  jmp     short loc_180077D19
0x180077d0b  lea     r8, [rbx+40h]; void *
0x180077d0f  mov     edx, 8; unsigned int
0x180077d14  call    ?Read@File@ConnectedStorage@@QEAAXKPEAX@Z; ConnectedStorage::File::Read(ulong,void *)
0x180077d19  cmp     dword ptr [rsi], 0
0x180077d1c  jnz     short loc_180077D24
0x180077d1e  mov     dword ptr [rsi], 1
0x180077d24  mov     cl, [rbx+18h]
0x180077d27  mov     [rbx+19h], cl
0x180077d2a  mov     rax, rbx
0x180077d2d  mov     rcx, [rbp+480h+var_30]
0x180077d34  xor     rcx, rsp; StackCookie
0x180077d37  call    __security_check_cookie
0x180077d3c  lea     r11, [rsp+580h+var_20]
0x180077d44  mov     rbx, [r11+40h]
0x180077d48  mov     rsi, [r11+48h]
0x180077d4c  mov     rsp, r11
0x180077d4f  pop     r15
0x180077d51  pop     r14
0x180077d53  pop     r12
0x180077d55  pop     rdi
0x180077d56  pop     rbp
0x180077d57  retn
```
