# _anonymous_namespace_::FindInstanceByPath

- ea: `0x180043bd8`
- end: `0x180043ef5`
- name: `_anonymous_namespace_::FindInstanceByPath`
- size: `797`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180044044`

## callees

- `0x18000a17c`
- `0x180027d7c`
- `0x18002f17c`
- `0x180041c78`
- `0x180043bd8`
- `0x180049b50`
- `0x180049bac`
- `0x180049c18`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180043d4d`
- `KERNEL32!LoadLibraryExW` at `0x180043d6b`
- `KERNEL32!LoadLibraryExW` at `0x180043d4d`
- `KERNEL32!LoadLibraryExW` at `0x180043d6b`
- `KERNEL32!GetLastError` at `0x180043d99`
- `KERNEL32!GetLastError` at `0x180043d99`
- `KERNEL32!GetProcAddress` at `0x180043d87`
- `KERNEL32!GetProcAddress` at `0x180043d87`
- `OLEAUT32!__imp_SysFreeString` at `0x180043e1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180043ee9`
- `OLEAUT32!__imp_SysFreeString` at `0x180043e1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180043ee9`

## string_xrefs

- `0x180043d46`: `Kernel32.dll`
- `0x180043d64`: `api-ms-win-core-libraryloader-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::FindInstanceByPath(__int64 a1, __int64 a2, BSTR *a3)
{
  __int64 v6; // rdx
  const unsigned __int16 *v7; // r9
  int v8; // ebx
  __int64 v9; // r15
  _QWORD *ThreadLocalStoragePointer; // r12
  unsigned __int16 v11; // cx
  unsigned __int16 v12; // r8
  __int64 v13; // rcx
  BSTR v14; // rsi
  Microsoft::DiagnosticsHub::UnifiedPlatform *v15; // rdi
  DWORD v16; // ebx
  HMODULE Library; // rax
  __int64 v18; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // r8d
  __int64 v23; // rdx
  BSTR v24; // rax
  Microsoft::DiagnosticsHub::UnifiedPlatform *v25[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v26; // [rsp+50h] [rbp-30h]
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+60h] [rbp-20h] BYREF
  int v29; // [rsp+68h] [rbp-18h] BYREF

  *(_OWORD *)v25 = 0;
  v26 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  std::vector<unsigned short>::vector<unsigned short>(v25, 2 * v6 + 2);
  v8 = Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(
         v25[0],
         (unsigned __int16 *)((v25[1] - v25[0]) >> 1),
         a2,
         v7);
  if ( v8 >= 0 )
  {
    v29 = 0;
    v28 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)a1 + 24LL))(a1, 1, &v28, &v29) )
    {
      v9 = (unsigned int)tls_index;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      while ( v29 == 1 )
      {
        bstrString = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v28 + 80LL))(v28, 0, &bstrString) >= 0 )
        {
          v14 = bstrString;
          v15 = v25[0];
          v16 = IsWindowsVersionOrGreater(v11, 2u, v12) << 11;
          if ( dword_180077B10 > *(_DWORD *)(ThreadLocalStoragePointer[v9] + 4LL) )
          {
            Init_thread_header(&dword_180077B10);
            if ( dword_180077B10 == -1 )
            {
              qword_180077B24 = 0;
              dword_180077B2C = 0;
              qword_180077B18 = 0;
              dword_180077B20 = 0;
              Library = LoadLibraryExW(L"Kernel32.dll", 0, v16);
              *(__int64 *)((char *)&qword_180077B24 + 4) = (__int64)Library;
              if ( !Library
                && (Library = LoadLibraryExW(L"api-ms-win-core-libraryloader-l1-1-0.dll", 0, v16),
                    (*(__int64 *)((char *)&qword_180077B24 + 4) = (__int64)Library) == 0)
                || (qword_180077B18 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))GetProcAddress(Library, "FindStringOrdinal")) == 0 )
              {
                dword_180077B20 = GetLastError();
              }
              Init_thread_footer(&dword_180077B10);
            }
          }
          v8 = 0;
          if ( dword_180077B20 || !qword_180077B18 )
          {
            v20 = -1;
            do
              ++v20;
            while ( *((_WORD *)v15 + v20) );
            v21 = -1;
            do
              ++v21;
            while ( v14[v21] );
            if ( v21 <= v20 )
            {
              v22 = 0;
              if ( !v21 )
              {
LABEL_37:
                v24 = bstrString;
                bstrString = 0;
                *a3 = v24;
                SysFreeString(0);
                goto LABEL_25;
              }
              v23 = 0;
              while ( *((_WORD *)v15 + v23) == v14[v23] )
              {
                v23 = ++v22;
                if ( v22 >= v21 )
                  goto LABEL_37;
              }
            }
          }
          else if ( !(unsigned int)qword_180077B18(0x100000, v15, 0xFFFFFFFFLL, v14, -1, 1) )
          {
            goto LABEL_37;
          }
          v18 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
        }
        else
        {
          v13 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
        SysFreeString(bstrString);
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)a1 + 24LL))(
               a1,
               1,
               &v28,
               &v29) )
        {
          break;
        }
      }
    }
    v8 = -518979493;
LABEL_25:
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043bd8  mov     [rsp-38h+arg_18], rbx
0x180043bdd  push    rbp
0x180043bde  push    rsi
0x180043bdf  push    rdi
0x180043be0  push    r12
0x180043be2  push    r13
0x180043be4  push    r14
0x180043be6  push    r15
0x180043be8  mov     rbp, rsp
0x180043beb  sub     rsp, 80h
0x180043bf2  mov     rax, cs:__security_cookie
0x180043bf9  xor     rax, rsp
0x180043bfc  mov     [rbp+var_10], rax
0x180043c00  mov     r13, r8
0x180043c03  mov     rbx, rdx
0x180043c06  mov     r14, rcx
0x180043c09  xorps   xmm0, xmm0
0x180043c0c  xor     eax, eax
0x180043c0e  movups  xmmword ptr [rbp+var_40], xmm0
0x180043c12  mov     [rbp+var_30], rax
0x180043c16  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043c1a  xor     edi, edi
0x180043c1c  inc     rdx
0x180043c1f  cmp     [rbx+rdx*2], di
0x180043c23  jnz     short loc_180043C1C
0x180043c25  lea     rdx, ds:2[rdx*2]
0x180043c2d  lea     rcx, [rbp+var_40]
0x180043c31  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180043c36  nop
0x180043c37  mov     rcx, [rbp+var_40]; this
0x180043c3b  mov     rdx, [rbp+var_40+8]
0x180043c3f  sub     rdx, rcx
0x180043c42  sar     rdx, 1; unsigned __int16 *
0x180043c45  mov     r8, rbx; unsigned __int64
0x180043c48  call    ?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)
0x180043c4d  mov     ebx, eax
0x180043c4f  test    eax, eax
0x180043c51  js      loc_180043E62
0x180043c57  xor     ebx, ebx
0x180043c59  mov     [rbp+var_18], ebx
0x180043c5c  mov     [rbp+var_20], rbx
0x180043c60  mov     rax, [r14]
0x180043c63  lea     r9, [rbp+var_18]
0x180043c67  lea     r8, [rbp+var_20]
0x180043c6b  lea     edx, [rbx+1]
0x180043c6e  mov     rcx, r14
0x180043c71  mov     rax, [rax+18h]
0x180043c75  call    cs:__guard_dispatch_icall_fptr
0x180043c7b  test    eax, eax
0x180043c7d  jnz     loc_180043E46
0x180043c83  mov     r15d, cs:_tls_index
0x180043c8a  mov     r12, gs:58h
0x180043c93  cmp     [rbp+var_18], 1
0x180043c97  jnz     loc_180043E46
0x180043c9d  mov     [rbp+bstrString], rbx
0x180043ca1  mov     rcx, [rbp+var_20]
0x180043ca5  mov     rax, [rcx]
0x180043ca8  lea     r8, [rbp+bstrString]
0x180043cac  xor     edx, edx
0x180043cae  mov     rax, [rax+50h]
0x180043cb2  call    cs:__guard_dispatch_icall_fptr
0x180043cb8  test    eax, eax
0x180043cba  jns     short loc_180043CDC
0x180043cbc  mov     rcx, [rbp+var_20]
0x180043cc0  test    rcx, rcx
0x180043cc3  jz      short loc_180043CD7
0x180043cc5  mov     [rbp+var_20], rbx
0x180043cc9  mov     rax, [rcx]
0x180043ccc  mov     rax, [rax+10h]
0x180043cd0  call    cs:__guard_dispatch_icall_fptr
0x180043cd6  nop
0x180043cd7  jmp     loc_180043E17
0x180043cdc  mov     rsi, [rbp+bstrString]
0x180043ce0  mov     rdi, [rbp+var_40]
0x180043ce4  mov     edx, 2; unsigned __int16
0x180043ce9  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180043cee  movzx   ebx, al
0x180043cf1  shl     ebx, 0Bh
0x180043cf4  mov     ecx, 4
0x180043cf9  mov     rax, [r12+r15*8]
0x180043cfd  mov     ecx, [rcx+rax]
0x180043d00  cmp     cs:dword_180077B10, ecx
0x180043d06  jle     loc_180043DB1
0x180043d0c  lea     rcx, dword_180077B10
0x180043d13  call    _Init_thread_header
0x180043d18  cmp     cs:dword_180077B10, 0FFFFFFFFh
0x180043d1f  jnz     loc_180043DB1
0x180043d25  xor     eax, eax
0x180043d27  mov     cs:qword_180077B24, rax
0x180043d2e  mov     cs:dword_180077B2C, eax
0x180043d34  mov     cs:qword_180077B18, rax
0x180043d3b  mov     cs:dword_180077B20, eax
0x180043d41  mov     r8d, ebx; dwFlags
0x180043d44  xor     edx, edx; hFile
0x180043d46  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x180043d4d  call    cs:__imp_LoadLibraryExW
0x180043d53  mov     cs:qword_180077B24+4, rax
0x180043d5a  test    rax, rax
0x180043d5d  jnz     short loc_180043D7D
0x180043d5f  mov     r8d, ebx; dwFlags
0x180043d62  xor     edx, edx; hFile
0x180043d64  lea     rcx, aApiMsWinCoreLi; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x180043d6b  call    cs:__imp_LoadLibraryExW
0x180043d71  mov     cs:qword_180077B24+4, rax
0x180043d78  test    rax, rax
0x180043d7b  jz      short loc_180043D99
0x180043d7d  lea     rdx, aFindstringordi; "FindStringOrdinal"
0x180043d84  mov     rcx, rax; hModule
0x180043d87  call    cs:__imp_GetProcAddress
0x180043d8d  test    rax, rax
0x180043d90  mov     cs:qword_180077B18, rax
0x180043d97  jnz     short loc_180043DA5
0x180043d99  call    cs:__imp_GetLastError
0x180043d9f  mov     cs:dword_180077B20, eax
0x180043da5  lea     rcx, dword_180077B10
0x180043dac  call    _Init_thread_footer
0x180043db1  xor     ebx, ebx
0x180043db3  cmp     cs:dword_180077B20, ebx
0x180043db9  jnz     loc_180043E94
0x180043dbf  mov     rax, cs:qword_180077B18
0x180043dc6  test    rax, rax
0x180043dc9  jz      loc_180043E94
0x180043dcf  mov     [rsp+80h+var_58], 1
0x180043dd7  mov     [rsp+80h+var_60], 0FFFFFFFFh
0x180043ddf  mov     r9, rsi
0x180043de2  or      r8d, 0FFFFFFFFh
0x180043de6  mov     rdx, rdi
0x180043de9  mov     ecx, 100000h
0x180043dee  call    cs:__guard_dispatch_icall_fptr
0x180043df4  test    eax, eax
0x180043df6  jz      loc_180043EDB
0x180043dfc  mov     rcx, [rbp+var_20]
0x180043e00  test    rcx, rcx
0x180043e03  jz      short loc_180043E17
0x180043e05  mov     [rbp+var_20], rbx
0x180043e09  mov     rax, [rcx]
0x180043e0c  mov     rax, [rax+10h]
0x180043e10  call    cs:__guard_dispatch_icall_fptr
0x180043e16  nop
0x180043e17  mov     rcx, [rbp+bstrString]; bstrString
0x180043e1b  call    cs:__imp_SysFreeString
0x180043e21  mov     rax, [r14]
0x180043e24  lea     r9, [rbp+var_18]
0x180043e28  lea     r8, [rbp+var_20]
0x180043e2c  mov     edx, 1
0x180043e31  mov     rcx, r14
0x180043e34  mov     rax, [rax+18h]
0x180043e38  call    cs:__guard_dispatch_icall_fptr
0x180043e3e  test    eax, eax
0x180043e40  jz      loc_180043C93
0x180043e46  mov     ebx, 0E111005Bh
0x180043e4b  mov     rcx, [rbp+var_20]
0x180043e4f  test    rcx, rcx
0x180043e52  jz      short loc_180043E62
0x180043e54  mov     rdx, [rcx]
0x180043e57  mov     rax, [rdx+10h]
0x180043e5b  call    cs:__guard_dispatch_icall_fptr
0x180043e61  nop
0x180043e62  lea     rcx, [rbp+var_40]
0x180043e66  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180043e6b  mov     eax, ebx
0x180043e6d  mov     rcx, [rbp+var_10]
0x180043e71  xor     rcx, rsp; StackCookie
0x180043e74  call    __security_check_cookie
0x180043e79  mov     rbx, [rsp+80h+arg_18]
0x180043e81  add     rsp, 80h
0x180043e88  pop     r15
0x180043e8a  pop     r14
0x180043e8c  pop     r13
0x180043e8e  pop     r12
0x180043e90  pop     rdi
0x180043e91  pop     rsi
0x180043e92  pop     rbp
0x180043e93  retn
0x180043e94  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043e98  inc     rax
0x180043e9b  cmp     [rdi+rax*2], bx
0x180043e9f  jnz     short loc_180043E98
0x180043ea1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043ea5  inc     rcx
0x180043ea8  cmp     [rsi+rcx*2], bx
0x180043eac  jnz     short loc_180043EA5
0x180043eae  cmp     rcx, rax
0x180043eb1  ja      loc_180043DFC
0x180043eb7  mov     r8d, ebx
0x180043eba  test    rcx, rcx
0x180043ebd  jz      short loc_180043EDB
0x180043ebf  mov     rdx, rbx
0x180043ec2  movzx   eax, word ptr [rsi+rdx*2]
0x180043ec6  cmp     [rdi+rdx*2], ax
0x180043eca  jnz     loc_180043DFC
0x180043ed0  inc     r8d
0x180043ed3  mov     edx, r8d
0x180043ed6  cmp     rdx, rcx
0x180043ed9  jb      short loc_180043EC2
0x180043edb  mov     rax, [rbp+bstrString]
0x180043edf  mov     [rbp+bstrString], rbx
0x180043ee3  mov     [r13+0], rax
0x180043ee7  xor     ecx, ecx; bstrString
0x180043ee9  call    cs:__imp_SysFreeString
0x180043eef  jmp     loc_180043E4B
```
