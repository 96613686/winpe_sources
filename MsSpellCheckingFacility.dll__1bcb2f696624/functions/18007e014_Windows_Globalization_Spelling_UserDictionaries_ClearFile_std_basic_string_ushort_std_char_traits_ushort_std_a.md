# Windows::Globalization::Spelling::UserDictionaries::ClearFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007e014`
- end: `0x18007e110`
- name: `?ClearFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180040d88`
- `0x180046920`

## callees

- `0x1800222ac`
- `0x180038aa0`
- `0x180038b40`
- `0x18004186c`
- `0x180061320`
- `0x18007e014`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007e0e0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007e0e0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e0d2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e0d2`

## pseudocode

```c
char __fastcall Windows::Globalization::Spelling::UserDictionaries::ClearFile(const WCHAR *a1)
{
  bool v2; // cc
  __int64 File; // rax
  char v4; // bl
  _QWORD v5[8]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v6[64]; // [rsp+80h] [rbp-68h] BYREF
  HANDLE hFile; // [rsp+C0h] [rbp-28h]

  if ( !*((_QWORD *)a1 + 2) )
    return 0;
  v2 = *((_QWORD *)a1 + 3) <= 7u;
  v5[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
  v5[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
  v5[7] = v5;
  if ( !v2 )
    a1 = *(const WCHAR **)a1;
  File = Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(a1, 0xC0000004, 3u, 0, 4u, 0x10000000u);
  std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(v6, File, v5);
  std::_Func_class<void,UserDictionary *>::_Tidy(v5);
  if ( hFile == (HANDLE)-1LL )
  {
    v4 = 0;
  }
  else
  {
    WriteFile(hFile, &Windows::Globalization::Spelling::UserDictionaries::UTF16BOM, 2u, 0, 0);
    SetEndOfFile(hFile);
    v4 = 1;
  }
  std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v6);
  return v4;
}

```

## disassembly

```asm
0x18007e014  push    rbx
0x18007e016  sub     rsp, 0E0h
0x18007e01d  mov     rax, cs:__security_cookie
0x18007e024  xor     rax, rsp
0x18007e027  mov     [rsp+0E8h+var_18], rax
0x18007e02f  cmp     qword ptr [rcx+10h], 0
0x18007e034  jnz     short loc_18007E03D
0x18007e036  xor     al, al
0x18007e038  jmp     loc_18007E0F7
0x18007e03d  cmp     qword ptr [rcx+18h], 7
0x18007e042  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x18007e049  mov     [rsp+0E8h+var_A8], rax
0x18007e04e  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x18007e055  mov     [rsp+0E8h+var_A0], rax
0x18007e05a  lea     rax, [rsp+0E8h+var_A8]
0x18007e05f  mov     [rsp+0E8h+var_70], rax
0x18007e064  jbe     short loc_18007E069
0x18007e066  mov     rcx, [rcx]; lpFileName
0x18007e069  xor     r9d, r9d; lpSecurityAttributes
0x18007e06c  mov     [rsp+0E8h+var_C0], 10000000h; DWORD
0x18007e074  mov     edx, 0C0000004h; dwDesiredAccess
0x18007e079  mov     dword ptr [rsp+0E8h+lpOverlapped], 4; DWORD
0x18007e081  lea     r8d, [r9+3]; dwShareMode
0x18007e085  call    ?AttemptCreateFile@UserDictionaries@Spelling@Globalization@Windows@@CAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKK@Z; Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)
0x18007e08a  mov     rdx, rax
0x18007e08d  lea     r8, [rsp+0E8h+var_A8]
0x18007e092  lea     rcx, [rsp+0E8h+var_68]
0x18007e09a  call    ??$?0V?$function@$$A6AHPEAX@Z@std@@$0A@@?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6AHPEAX@Z@1@@Z; std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(void *,std::function<int (void *)> &&)
0x18007e09f  lea     rcx, [rsp+0E8h+var_A8]
0x18007e0a4  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x18007e0a9  mov     rcx, [rsp+0E8h+hFile]; hFile
0x18007e0b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007e0b5  jnz     short loc_18007E0BB
0x18007e0b7  xor     ebx, ebx
0x18007e0b9  jmp     short loc_18007E0E8
0x18007e0bb  xor     r9d, r9d; lpNumberOfBytesWritten
0x18007e0be  mov     [rsp+0E8h+lpOverlapped], 0; lpOverlapped
0x18007e0c7  lea     rdx, ?UTF16BOM@UserDictionaries@Spelling@Globalization@Windows@@2GB; lpBuffer
0x18007e0ce  lea     r8d, [r9+2]; nNumberOfBytesToWrite
0x18007e0d2  call    cs:__imp_WriteFile
0x18007e0d8  mov     rcx, [rsp+0E8h+hFile]; hFile
0x18007e0e0  call    cs:__imp_SetEndOfFile
0x18007e0e6  mov     bl, 1
0x18007e0e8  lea     rcx, [rsp+0E8h+var_68]
0x18007e0f0  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x18007e0f5  mov     al, bl
0x18007e0f7  mov     rcx, [rsp+0E8h+var_18]
0x18007e0ff  xor     rcx, rsp; StackCookie
0x18007e102  call    __security_check_cookie
0x18007e107  add     rsp, 0E0h
0x18007e10e  pop     rbx
0x18007e10f  retn
```
