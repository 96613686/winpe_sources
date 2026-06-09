# pGetStreamLabels(UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x1800339d8`
- end: `0x180033b9e`
- name: `?pGetStreamLabels@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVString@UnBCL@@@2@@Z`
- size: `454`
- prototype: `__int64 __fastcall(UnBCL::String *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f040`

## callees

- `0x1800339d8`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033b67`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a66`
- `api-ms-win-core-file-l1-2-2!FindNextStreamW` at `0x180033b56`
- `api-ms-win-core-file-l1-2-2!FindNextStreamW` at `0x180033b56`
- `api-ms-win-core-file-l1-2-2!FindFirstStreamW` at `0x180033a3f`
- `api-ms-win-core-file-l1-2-2!FindFirstStreamW` at `0x180033a3f`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180033b0a`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180033b0a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033ab1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033ab1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033acc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033acc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033a2c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033a2c`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180033a9e`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180033a9e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033ae8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033ae8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033b48`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033b48`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033b2a`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033b2a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033af4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033af4`

## pseudocode

```c
__int64 __fastcall pGetStreamLabels(UnBCL::String *a1, __int64 a2)
{
  const WCHAR *CString; // rax
  HANDLE FirstStreamW; // rbp
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax
  unsigned int v9; // esi
  UnBCL::String *v10; // rax
  UnBCL::String *v11; // rbx
  UnBCL::String *v12; // rax
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  _BYTE v17[24]; // [rsp+28h] [rbp-2A0h] BYREF
  _BYTE FindStreamData[8]; // [rsp+40h] [rbp-288h] BYREF
  unsigned __int16 v19[300]; // [rsp+48h] [rbp-280h] BYREF

  memset_0(FindStreamData, 0, 0x258u);
  if ( a1 && a2 )
  {
    CString = UnBCL::String::get_CString(a1);
    FirstStreamW = FindFirstStreamW(CString, FindStreamInfoStandard, FindStreamData, 0);
    if ( FirstStreamW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
        v7 = 1;
      if ( v7 )
      {
        v8 = GetLastError();
        v9 = v8;
        if ( v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
    else
    {
      v9 = 0;
      do
      {
        if ( UnBCL::String::Compare(v19, L"::$DATA", 1) )
        {
          v10 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v11 = v10;
          if ( v10 )
          {
            UnBCL::String::String(v10, v19);
            *(_QWORD *)v11 = &UnBCL::String::`local vftable';
          }
          else
          {
            v11 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v17, v11);
          v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v17);
          if ( UnBCL::String::EndsWith(v12, L":$DATA", 1) )
          {
            v13 = *(int *)(*(_QWORD *)(a2 + 8) + 16LL);
            v14 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v13 + a2 + 8) + 40LL);
            v15 = UnBCL::SmartPtr<UnBCL::String>::Steal(v17);
            v14(v13 + a2 + 8, v15);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v17);
        }
      }
      while ( FindNextStreamW(FirstStreamW, FindStreamData) );
      FindClose(FirstStreamW);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x1800339d8  mov     [rsp+arg_10], rbx
0x1800339dd  mov     [rsp+arg_18], rbp
0x1800339e2  push    rsi
0x1800339e3  push    rdi
0x1800339e4  push    r14
0x1800339e6  sub     rsp, 2B0h
0x1800339ed  mov     rax, cs:__security_cookie
0x1800339f4  xor     rax, rsp
0x1800339f7  mov     [rsp+2C8h+var_28], rax
0x1800339ff  mov     r14, rdx
0x180033a02  mov     rbx, rcx
0x180033a05  xor     edx, edx; Val
0x180033a07  mov     r8d, 258h; Size
0x180033a0d  lea     rcx, [rsp+2C8h+FindStreamData]; void *
0x180033a12  call    memset_0
0x180033a17  test    rbx, rbx
0x180033a1a  jz      loc_180033B6F
0x180033a20  test    r14, r14
0x180033a23  jz      loc_180033B6F
0x180033a29  mov     rcx, rbx
0x180033a2c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033a32  mov     rcx, rax; lpFileName
0x180033a35  xor     r9d, r9d; dwFlags
0x180033a38  lea     r8, [rsp+2C8h+FindStreamData]; lpFindStreamData
0x180033a3d  xor     edx, edx; InfoLevel
0x180033a3f  call    cs:__imp_FindFirstStreamW
0x180033a45  mov     rbp, rax
0x180033a48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033a4c  jnz     short loc_180033A8A
0x180033a4e  call    cs:__imp_GetLastError
0x180033a54  mov     ebx, 80070000h
0x180033a59  test    eax, eax
0x180033a5b  jle     short loc_180033A64
0x180033a5d  movzx   eax, ax
0x180033a60  or      eax, ebx
0x180033a62  test    eax, eax
0x180033a64  jns     short loc_180033A80
0x180033a66  call    cs:__imp_GetLastError
0x180033a6c  mov     esi, eax
0x180033a6e  test    eax, eax
0x180033a70  jle     loc_180033B74
0x180033a76  movzx   esi, ax
0x180033a79  or      esi, ebx
0x180033a7b  jmp     loc_180033B74
0x180033a80  mov     esi, 80004005h
0x180033a85  jmp     loc_180033B74
0x180033a8a  xor     esi, esi
0x180033a8c  mov     r8d, 1
0x180033a92  lea     rdx, aData; "::$DATA"
0x180033a99  lea     rcx, [rsp+2C8h+var_280]
0x180033a9e  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x180033aa4  test    eax, eax
0x180033aa6  jz      loc_180033B4E
0x180033aac  mov     ecx, 18h
0x180033ab1  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180033ab7  mov     rbx, rax
0x180033aba  mov     [rsp+2C8h+var_2A8], rax
0x180033abf  test    rax, rax
0x180033ac2  jz      short loc_180033ADE
0x180033ac4  lea     rdx, [rsp+2C8h+var_280]
0x180033ac9  mov     rcx, rax
0x180033acc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180033ad2  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180033ad9  mov     [rbx], rax
0x180033adc  jmp     short loc_180033AE0
0x180033ade  xor     ebx, ebx
0x180033ae0  mov     rdx, rbx
0x180033ae3  lea     rcx, [rsp+2C8h+var_2A0]
0x180033ae8  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180033aee  nop
0x180033aef  lea     rcx, [rsp+2C8h+var_2A0]
0x180033af4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180033afa  mov     r8d, 1
0x180033b00  lea     rdx, aData_0; ":$DATA"
0x180033b07  mov     rcx, rax
0x180033b0a  call    cs:__imp_?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x180033b10  test    eax, eax
0x180033b12  jz      short loc_180033B43
0x180033b14  mov     rax, [r14+8]
0x180033b18  movsxd  rdi, dword ptr [rax+10h]
0x180033b1c  mov     rax, [rdi+r14+8]
0x180033b21  mov     rbx, [rax+28h]
0x180033b25  lea     rcx, [rsp+2C8h+var_2A0]
0x180033b2a  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x180033b30  mov     rdx, rax
0x180033b33  lea     rcx, [r14+8]
0x180033b37  add     rcx, rdi
0x180033b3a  mov     rax, rbx
0x180033b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b42  nop
0x180033b43  lea     rcx, [rsp+2C8h+var_2A0]
0x180033b48  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180033b4e  lea     rdx, [rsp+2C8h+FindStreamData]; lpFindStreamData
0x180033b53  mov     rcx, rbp; hFindStream
0x180033b56  call    cs:__imp_FindNextStreamW
0x180033b5c  test    eax, eax
0x180033b5e  jnz     loc_180033A8C
0x180033b64  mov     rcx, rbp; hFindFile
0x180033b67  call    cs:__imp_FindClose
0x180033b6d  jmp     short loc_180033B74
0x180033b6f  mov     esi, 80070057h
0x180033b74  mov     eax, esi
0x180033b76  mov     rcx, [rsp+2C8h+var_28]
0x180033b7e  xor     rcx, rsp; StackCookie
0x180033b81  call    __security_check_cookie
0x180033b86  lea     r11, [rsp+2C8h+var_18]
0x180033b8e  mov     rbx, [r11+30h]
0x180033b92  mov     rbp, [r11+38h]
0x180033b96  mov     rsp, r11
0x180033b99  pop     r14
0x180033b9b  pop     rdi
0x180033b9c  pop     rsi
0x180033b9d  retn
```
