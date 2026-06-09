# _anonymous_namespace_::FindInstanceByPath

- ea: `0x14000e7fc`
- end: `0x14000eae9`
- name: `_anonymous_namespace_::FindInstanceByPath`
- size: `749`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, BSTR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000ec38`

## callees

- `0x140003158`
- `0x1400043a0`
- `0x1400095e4`
- `0x14000e7fc`
- `0x14000f364`
- `0x1400137e0`
- `0x1400138ac`
- `0x140013918`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000e981`
- `KERNEL32!GetProcAddress` at `0x14000e981`
- `KERNEL32!LoadLibraryExW` at `0x14000e947`
- `KERNEL32!LoadLibraryExW` at `0x14000e965`
- `KERNEL32!LoadLibraryExW` at `0x14000e947`
- `KERNEL32!LoadLibraryExW` at `0x14000e965`
- `KERNEL32!GetLastError` at `0x14000e993`
- `KERNEL32!GetLastError` at `0x14000e993`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ea14`
- `OLEAUT32!__imp_SysFreeString` at `0x14000eada`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ea14`
- `OLEAUT32!__imp_SysFreeString` at `0x14000eada`

## string_xrefs

- `0x14000e940`: `Kernel32.dll`
- `0x14000e95e`: `api-ms-win-core-libraryloader-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall anonymous_namespace_::FindInstanceByPath(__int64 a1, unsigned __int64 a2, BSTR *a3)
{
  __int64 v6; // rdx
  const unsigned __int16 *v7; // r9
  int v8; // ebx
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // r8
  __int64 v11; // rcx
  BSTR v12; // rsi
  Microsoft::DiagnosticsHub::UnifiedPlatform *v13; // rdi
  DWORD v14; // ebx
  HMODULE Library; // rax
  __int64 v16; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned int v20; // r8d
  __int64 v21; // rdx
  BSTR v22; // rax
  Microsoft::DiagnosticsHub::UnifiedPlatform *v23[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v24; // [rsp+50h] [rbp-30h]
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+68h] [rbp-18h] BYREF

  *(_OWORD *)v23 = 0;
  v24 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  std::vector<unsigned short>::vector<unsigned short>(v23, 2 * v6 + 2);
  v8 = Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(
         v23[0],
         (unsigned __int16 *)((v23[1] - v23[0]) >> 1),
         a2,
         v7);
  if ( v8 < 0 )
    goto LABEL_27;
  v27 = 0;
  v26 = 0;
  while ( 1 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)a1 + 24LL))(a1, 1, &v26, &v27)
      || v27 != 1 )
    {
      v8 = -518979493;
      goto LABEL_25;
    }
    bstrString = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v26 + 80LL))(v26, 0, &bstrString) < 0 )
    {
      v11 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_22;
    }
    v12 = bstrString;
    v13 = v23[0];
    v14 = IsWindowsVersionOrGreater(v9, 2u, v10) << 11;
    if ( dword_140024BA0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&dword_140024BA0);
      if ( dword_140024BA0 == -1 )
      {
        qword_140024BB4 = 0;
        dword_140024BBC = 0;
        qword_140024BA8 = 0;
        dword_140024BB0 = 0;
        Library = LoadLibraryExW(L"Kernel32.dll", 0, v14);
        *(__int64 *)((char *)&qword_140024BB4 + 4) = (__int64)Library;
        if ( !Library
          && (Library = LoadLibraryExW(L"api-ms-win-core-libraryloader-l1-1-0.dll", 0, v14),
              (*(__int64 *)((char *)&qword_140024BB4 + 4) = (__int64)Library) == 0)
          || (qword_140024BA8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))GetProcAddress(Library, "FindStringOrdinal")) == 0 )
        {
          dword_140024BB0 = GetLastError();
        }
        Init_thread_footer(&dword_140024BA0);
      }
    }
    if ( !dword_140024BB0 && qword_140024BA8 )
    {
      if ( !(unsigned int)qword_140024BA8(0x100000, v13, 0xFFFFFFFFLL, v12, -1, 1) )
        goto LABEL_37;
      goto LABEL_20;
    }
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v13 + v18) );
    v19 = -1;
    do
      ++v19;
    while ( v12[v19] );
    if ( v19 <= v18 )
      break;
LABEL_20:
    v16 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
LABEL_22:
    SysFreeString(bstrString);
  }
  v20 = 0;
  if ( v19 )
  {
    v21 = 0;
    while ( *((_WORD *)v13 + v21) == v12[v21] )
    {
      v21 = ++v20;
      if ( v20 >= v19 )
        goto LABEL_37;
    }
    goto LABEL_20;
  }
LABEL_37:
  v22 = bstrString;
  bstrString = 0;
  *a3 = v22;
  SysFreeString(0);
  v8 = 0;
LABEL_25:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_27:
  std::vector<unsigned short>::~vector<unsigned short>(v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e7fc  push    rbp
0x14000e7fe  push    rbx
0x14000e7ff  push    rsi
0x14000e800  push    rdi
0x14000e801  push    r12
0x14000e803  push    r14
0x14000e805  push    r15
0x14000e807  mov     rbp, rsp
0x14000e80a  sub     rsp, 80h
0x14000e811  mov     rax, cs:__security_cookie
0x14000e818  xor     rax, rsp
0x14000e81b  mov     [rbp+var_10], rax
0x14000e81f  mov     r15, r8
0x14000e822  mov     rbx, rdx
0x14000e825  mov     r14, rcx
0x14000e828  xorps   xmm0, xmm0
0x14000e82b  xor     eax, eax
0x14000e82d  movups  xmmword ptr [rbp+var_40], xmm0
0x14000e831  mov     [rbp+var_30], rax
0x14000e835  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000e839  xor     r12d, r12d
0x14000e83c  inc     rdx
0x14000e83f  cmp     [rbx+rdx*2], r12w
0x14000e844  jnz     short loc_14000E83C
0x14000e846  lea     rdx, ds:2[rdx*2]
0x14000e84e  lea     rcx, [rbp+var_40]
0x14000e852  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x14000e857  nop
0x14000e858  mov     rcx, [rbp+var_40]; this
0x14000e85c  mov     rdx, [rbp+var_40+8]
0x14000e860  sub     rdx, rcx
0x14000e863  sar     rdx, 1; unsigned __int16 *
0x14000e866  mov     r8, rbx; unsigned __int64
0x14000e869  call    ?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)
0x14000e86e  mov     ebx, eax
0x14000e870  test    eax, eax
0x14000e872  js      loc_14000EA5B
0x14000e878  mov     [rbp+var_18], r12d
0x14000e87c  mov     [rbp+var_20], r12
0x14000e880  jmp     loc_14000EA1A
0x14000e885  cmp     [rbp+var_18], 1
0x14000e889  jnz     loc_14000EA3F
0x14000e88f  mov     [rbp+bstrString], r12
0x14000e893  mov     rcx, [rbp+var_20]
0x14000e897  mov     rax, [rcx]
0x14000e89a  lea     r8, [rbp+bstrString]
0x14000e89e  xor     edx, edx
0x14000e8a0  mov     rax, [rax+50h]
0x14000e8a4  call    cs:__guard_dispatch_icall_fptr
0x14000e8aa  test    eax, eax
0x14000e8ac  jns     short loc_14000E8CE
0x14000e8ae  mov     rcx, [rbp+var_20]
0x14000e8b2  test    rcx, rcx
0x14000e8b5  jz      short loc_14000E8C9
0x14000e8b7  mov     [rbp+var_20], r12
0x14000e8bb  mov     rax, [rcx]
0x14000e8be  mov     rax, [rax+10h]
0x14000e8c2  call    cs:__guard_dispatch_icall_fptr
0x14000e8c8  nop
0x14000e8c9  jmp     loc_14000EA10
0x14000e8ce  mov     rsi, [rbp+bstrString]
0x14000e8d2  mov     rdi, [rbp+var_40]
0x14000e8d6  mov     edx, 2; unsigned __int16
0x14000e8db  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x14000e8e0  movzx   ebx, al
0x14000e8e3  shl     ebx, 0Bh
0x14000e8e6  mov     edx, 4
0x14000e8eb  mov     rax, gs:58h
0x14000e8f4  mov     rcx, [rax]
0x14000e8f7  mov     eax, [rdx+rcx]
0x14000e8fa  cmp     cs:dword_140024BA0, eax
0x14000e900  jle     loc_14000E9AB
0x14000e906  lea     rcx, dword_140024BA0
0x14000e90d  call    _Init_thread_header
0x14000e912  cmp     cs:dword_140024BA0, 0FFFFFFFFh
0x14000e919  jnz     loc_14000E9AB
0x14000e91f  mov     cs:qword_140024BB4, r12
0x14000e926  mov     cs:dword_140024BBC, r12d
0x14000e92d  mov     cs:qword_140024BA8, r12
0x14000e934  mov     cs:dword_140024BB0, r12d
0x14000e93b  mov     r8d, ebx; dwFlags
0x14000e93e  xor     edx, edx; hFile
0x14000e940  lea     rcx, LibFileName; "Kernel32.dll"
0x14000e947  call    cs:__imp_LoadLibraryExW
0x14000e94d  mov     cs:qword_140024BB4+4, rax
0x14000e954  test    rax, rax
0x14000e957  jnz     short loc_14000E977
0x14000e959  mov     r8d, ebx; dwFlags
0x14000e95c  xor     edx, edx; hFile
0x14000e95e  lea     rcx, aApiMsWinCoreLi; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x14000e965  call    cs:__imp_LoadLibraryExW
0x14000e96b  mov     cs:qword_140024BB4+4, rax
0x14000e972  test    rax, rax
0x14000e975  jz      short loc_14000E993
0x14000e977  lea     rdx, aFindstringordi; "FindStringOrdinal"
0x14000e97e  mov     rcx, rax; hModule
0x14000e981  call    cs:__imp_GetProcAddress
0x14000e987  test    rax, rax
0x14000e98a  mov     cs:qword_140024BA8, rax
0x14000e991  jnz     short loc_14000E99F
0x14000e993  call    cs:__imp_GetLastError
0x14000e999  mov     cs:dword_140024BB0, eax
0x14000e99f  lea     rcx, dword_140024BA0
0x14000e9a6  call    _Init_thread_footer
0x14000e9ab  cmp     cs:dword_140024BB0, r12d
0x14000e9b2  jnz     loc_14000EA84
0x14000e9b8  mov     rax, cs:qword_140024BA8
0x14000e9bf  test    rax, rax
0x14000e9c2  jz      loc_14000EA84
0x14000e9c8  mov     [rsp+80h+var_58], 1
0x14000e9d0  mov     [rsp+80h+var_60], 0FFFFFFFFh
0x14000e9d8  mov     r9, rsi
0x14000e9db  or      r8d, 0FFFFFFFFh
0x14000e9df  mov     rdx, rdi
0x14000e9e2  mov     ecx, 100000h
0x14000e9e7  call    cs:__guard_dispatch_icall_fptr
0x14000e9ed  test    eax, eax
0x14000e9ef  jz      loc_14000EACD
0x14000e9f5  mov     rcx, [rbp+var_20]
0x14000e9f9  test    rcx, rcx
0x14000e9fc  jz      short loc_14000EA10
0x14000e9fe  mov     [rbp+var_20], r12
0x14000ea02  mov     rax, [rcx]
0x14000ea05  mov     rax, [rax+10h]
0x14000ea09  call    cs:__guard_dispatch_icall_fptr
0x14000ea0f  nop
0x14000ea10  mov     rcx, [rbp+bstrString]; bstrString
0x14000ea14  call    cs:__imp_SysFreeString
0x14000ea1a  mov     rax, [r14]
0x14000ea1d  lea     r9, [rbp+var_18]
0x14000ea21  lea     r8, [rbp+var_20]
0x14000ea25  mov     edx, 1
0x14000ea2a  mov     rcx, r14
0x14000ea2d  mov     rax, [rax+18h]
0x14000ea31  call    cs:__guard_dispatch_icall_fptr
0x14000ea37  test    eax, eax
0x14000ea39  jz      loc_14000E885
0x14000ea3f  mov     ebx, 0E111005Bh
0x14000ea44  mov     rcx, [rbp+var_20]
0x14000ea48  test    rcx, rcx
0x14000ea4b  jz      short loc_14000EA5B
0x14000ea4d  mov     rdx, [rcx]
0x14000ea50  mov     rax, [rdx+10h]
0x14000ea54  call    cs:__guard_dispatch_icall_fptr
0x14000ea5a  nop
0x14000ea5b  lea     rcx, [rbp+var_40]
0x14000ea5f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000ea64  mov     eax, ebx
0x14000ea66  mov     rcx, [rbp+var_10]
0x14000ea6a  xor     rcx, rsp; StackCookie
0x14000ea6d  call    __security_check_cookie
0x14000ea72  add     rsp, 80h
0x14000ea79  pop     r15
0x14000ea7b  pop     r14
0x14000ea7d  pop     r12
0x14000ea7f  pop     rdi
0x14000ea80  pop     rsi
0x14000ea81  pop     rbx
0x14000ea82  pop     rbp
0x14000ea83  retn
0x14000ea84  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ea88  inc     rax
0x14000ea8b  cmp     [rdi+rax*2], r12w
0x14000ea90  jnz     short loc_14000EA88
0x14000ea92  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000ea96  inc     rcx
0x14000ea99  cmp     [rsi+rcx*2], r12w
0x14000ea9e  jnz     short loc_14000EA96
0x14000eaa0  cmp     rcx, rax
0x14000eaa3  ja      loc_14000E9F5
0x14000eaa9  mov     r8d, r12d
0x14000eaac  test    rcx, rcx
0x14000eaaf  jz      short loc_14000EACD
0x14000eab1  mov     rdx, r12
0x14000eab4  movzx   eax, word ptr [rsi+rdx*2]
0x14000eab8  cmp     [rdi+rdx*2], ax
0x14000eabc  jnz     loc_14000E9F5
0x14000eac2  inc     r8d
0x14000eac5  mov     edx, r8d
0x14000eac8  cmp     rdx, rcx
0x14000eacb  jb      short loc_14000EAB4
0x14000eacd  mov     rax, [rbp+bstrString]
0x14000ead1  mov     [rbp+bstrString], r12
0x14000ead5  mov     [r15], rax
0x14000ead8  xor     ecx, ecx; bstrString
0x14000eada  call    cs:__imp_SysFreeString
0x14000eae0  mov     ebx, r12d
0x14000eae3  jmp     loc_14000EA44
```
