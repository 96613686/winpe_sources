# pGetOOBEEndTime(void)

- ea: `0x18000cbc4`
- end: `0x18000cdaf`
- name: `?pGetOOBEEndTime@@YAPEAVDateTime@UnBCL@@XZ`
- size: `491`
- prototype: `struct UnBCL::DateTime *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a900`

## callees

- `0x18000272c`
- `0x180003c88`
- `0x1800047a8`
- `0x180006744`
- `0x18000cbc4`
- `0x180036010`

## import_xrefs

- `unbcl!??0DateTime@UnBCL@@QEAA@HHHHHHH@Z` at `0x18000ccd0`
- `unbcl!??0DateTime@UnBCL@@QEAA@HHHHHHH@Z` at `0x18000ccd0`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18000cc68`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18000cc68`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000cce8`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000cce8`
- `unbcl!?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z` at `0x18000cc46`
- `unbcl!?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z` at `0x18000cc46`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18000cc53`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18000cc53`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000cd64`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000cd64`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000cd6d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000cd6d`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18000cd7e`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18000cd7e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000cc8a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000cd4e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000cc8a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000cd4e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18000cd35`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18000cd35`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000cd42`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000cd42`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000cc1b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000cc5e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000cc1b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000cc5e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000cbf6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000cc39`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000cbf6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000cc39`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x18000cc04`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x18000cc04`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000cbd8`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x18000cbd8`

## pseudocode

```c
struct UnBCL::DateTime *__fastcall pGetOOBEEndTime(__int64 a1)
{
  __int64 LocalMachine; // rax
  const struct UnBCL::String *v2; // rax
  struct UnBCL::RegistryKey *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int16 *v7; // rdi
  UnBCL::DateTime *v8; // rax
  UnBCL::DateTime *v9; // rsi
  struct UnBCL::String *v11; // rax
  UnBCL::Win32Exception *v12; // rbx
  UnBCL::String *v13; // rax
  const unsigned __int16 *CString; // rax
  void **v15; // [rsp+40h] [rbp-9h] BYREF
  __int64 v16; // [rsp+48h] [rbp-1h]
  _QWORD v17[2]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v19[48]; // [rsp+70h] [rbp+27h] BYREF
  __int64 pExceptionObject; // [rsp+B0h] [rbp+67h] BYREF
  UnBCL::Win32Exception *v21; // [rsp+B8h] [rbp+6Fh]

  LocalMachine = UnBCL::Registry::GetLocalMachine(a1);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v17, LocalMachine);
  v2 = (const struct UnBCL::String *)UnBCL::String::String(
                                       (UnBCL::String *)v19,
                                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats");
  v3 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v17[1], v2);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v15, (__int64)v3);
  UnBCL::String::~String((UnBCL::String *)v19);
  v4 = v16;
  if ( !v16 )
  {
    v11 = UnBCL::String::Format(
            L"The key HKLM\\%s doesn't exist",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v19, v11);
    v12 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v21 = v12;
    if ( v12 )
    {
      v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v19);
      CString = UnBCL::String::get_CString(v13);
      UnBCL::Win32Exception::Win32Exception(v12, 2u, CString);
      *(_QWORD *)v12 = &UnBCL::Win32Exception::`local vftable';
    }
    else
    {
      v12 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::Win32Exception>(v12);
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v5 = UnBCL::String::String((UnBCL::String *)v19, L"EndTimeStamp");
  UnBCL::RegistryKey::GetBinaryValue(v4, v5);
  UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(v18);
  UnBCL::String::~String((UnBCL::String *)v19);
  v6 = UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::operator->(v18);
  v7 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 56LL))(v6, 0);
  v8 = (UnBCL::DateTime *)UnBCL::Object::operator new(0x18u);
  v9 = v8;
  pExceptionObject = (__int64)v8;
  if ( v8 )
  {
    UnBCL::DateTime::DateTime(v8, *v7, v7[1], v7[3], v7[4], v7[5], v7[6], v7[7]);
    *(_QWORD *)v9 = &UnBCL::DateTime::`local vftable';
  }
  else
  {
    v9 = 0;
  }
  UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v18);
  v15 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v15);
  v17[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v17);
  return v9;
}

```

## disassembly

```asm
0x18000cbc4  mov     [rsp-8+arg_10], rbx
0x18000cbc9  push    rbp
0x18000cbca  push    rsi
0x18000cbcb  push    rdi
0x18000cbcc  lea     rbp, [rsp-47h]
0x18000cbd1  sub     rsp, 90h
0x18000cbd8  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000cbde  mov     rdx, rax
0x18000cbe1  lea     rcx, [rbp+57h+var_50]
0x18000cbe5  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000cbea  nop
0x18000cbeb  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cbf2  lea     rcx, [rbp+57h+var_30]
0x18000cbf6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000cbfc  nop
0x18000cbfd  mov     rdx, rax
0x18000cc00  mov     rcx, [rbp+57h+var_48]
0x18000cc04  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *)
0x18000cc0a  mov     rdx, rax
0x18000cc0d  lea     rcx, [rbp+57h+var_60]
0x18000cc11  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000cc16  nop
0x18000cc17  lea     rcx, [rbp+57h+var_30]
0x18000cc1b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000cc21  mov     rbx, [rbp+57h+var_58]
0x18000cc25  test    rbx, rbx
0x18000cc28  jz      loc_18000CD27
0x18000cc2e  lea     rdx, aEndtimestamp; "EndTimeStamp"
0x18000cc35  lea     rcx, [rbp+57h+var_30]
0x18000cc39  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000cc3f  nop
0x18000cc40  mov     rdx, rax
0x18000cc43  mov     rcx, rbx
0x18000cc46  call    cs:__imp_?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z; UnBCL::RegistryKey::GetBinaryValue(UnBCL::String const *)
0x18000cc4c  mov     rdx, rax
0x18000cc4f  lea     rcx, [rbp+57h+var_40]
0x18000cc53  call    cs:__imp_??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z; UnBCL::SmartPtr<UnBCL::Array<uchar>>::SmartPtr<UnBCL::Array<uchar>>(UnBCL::Array<uchar> *)
0x18000cc59  nop
0x18000cc5a  lea     rcx, [rbp+57h+var_30]
0x18000cc5e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000cc64  lea     rcx, [rbp+57h+var_40]
0x18000cc68  call    cs:__imp_??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ; UnBCL::SmartPtr<UnBCL::Array<uchar>>::operator->(void)
0x18000cc6e  mov     r8, rax
0x18000cc71  mov     rcx, [rax]
0x18000cc74  mov     rax, [rcx+38h]
0x18000cc78  xor     edx, edx
0x18000cc7a  mov     rcx, r8
0x18000cc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc82  mov     rdi, rax
0x18000cc85  mov     ecx, 18h
0x18000cc8a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000cc90  mov     rsi, rax
0x18000cc93  mov     [rbp+57h+pExceptionObject], rax
0x18000cc97  test    rax, rax
0x18000cc9a  jz      short loc_18000CCE2
0x18000cc9c  movzx   ecx, word ptr [rdi+0Eh]
0x18000cca0  movzx   r10d, word ptr [rdi+0Ch]
0x18000cca5  movzx   r11d, word ptr [rdi+0Ah]
0x18000ccaa  movzx   ebx, word ptr [rdi+8]
0x18000ccae  movzx   r9d, word ptr [rdi+6]
0x18000ccb3  movzx   r8d, word ptr [rdi+2]
0x18000ccb8  movzx   edx, word ptr [rdi]
0x18000ccbb  mov     [rsp+0A0h+var_68], ecx
0x18000ccbf  mov     [rsp+0A0h+var_70], r10d
0x18000ccc4  mov     [rsp+0A0h+var_78], r11d
0x18000ccc9  mov     [rsp+0A0h+var_80], ebx
0x18000cccd  mov     rcx, rax
0x18000ccd0  call    cs:__imp_??0DateTime@UnBCL@@QEAA@HHHHHHH@Z; UnBCL::DateTime::DateTime(int,int,int,int,int,int,int)
0x18000ccd6  lea     rax, ??_SDateTime@UnBCL@@6B@; const UnBCL::DateTime::`local vftable'
0x18000ccdd  mov     [rsi], rax
0x18000cce0  jmp     short loc_18000CCE4
0x18000cce2  xor     esi, esi
0x18000cce4  lea     rcx, [rbp+57h+var_40]
0x18000cce8  call    cs:__imp_??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Array<uchar>>::~SmartPtr<UnBCL::Array<uchar>>(void)
0x18000ccee  nop
0x18000ccef  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000ccf6  mov     [rbp+57h+var_60], rbx
0x18000ccfa  lea     rcx, [rbp+57h+var_60]
0x18000ccfe  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000cd03  nop
0x18000cd04  mov     [rbp+57h+var_50], rbx
0x18000cd08  lea     rcx, [rbp+57h+var_50]
0x18000cd0c  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000cd11  mov     rax, rsi
0x18000cd14  mov     rbx, [rsp+0A0h+arg_10]
0x18000cd1c  add     rsp, 90h
0x18000cd23  pop     rdi
0x18000cd24  pop     rsi
0x18000cd25  pop     rbp
0x18000cd26  retn
0x18000cd27  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cd2e  lea     rcx, aTheKeyHklmSDoe; "The key HKLM\\%s doesn't exist"
0x18000cd35  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18000cd3b  mov     rdx, rax
0x18000cd3e  lea     rcx, [rbp+57h+var_30]
0x18000cd42  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18000cd48  nop
0x18000cd49  mov     ecx, 40h ; '@'
0x18000cd4e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000cd54  mov     rbx, rax
0x18000cd57  mov     [rbp+57h+arg_8], rax
0x18000cd5b  test    rax, rax
0x18000cd5e  jz      short loc_18000CD90
0x18000cd60  lea     rcx, [rbp+57h+var_30]
0x18000cd64  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18000cd6a  mov     rcx, rax
0x18000cd6d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18000cd73  mov     r8, rax
0x18000cd76  mov     edx, 2
0x18000cd7b  mov     rcx, rbx
0x18000cd7e  call    cs:__imp_??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x18000cd84  lea     rax, ??_SWin32Exception@UnBCL@@6B@; const UnBCL::Win32Exception::`local vftable'
0x18000cd8b  mov     [rbx], rax
0x18000cd8e  jmp     short loc_18000CD92
0x18000cd90  xor     ebx, ebx
0x18000cd92  mov     rcx, rbx
0x18000cd95  call    ??$AddStackTraceToException@VWin32Exception@UnBCL@@@@YAPEAVWin32Exception@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::Win32Exception>(UnBCL::Win32Exception *,char const *)
0x18000cd9a  mov     [rbp+57h+pExceptionObject], rax
0x18000cd9e  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18000cda5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000cda9  call    _CxxThrowException_0
```
