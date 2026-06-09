# LocationCallerInfoHelper::GetExecutionHostAppInfoWin32(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800201a0`
- end: `0x1800204fd`
- name: `?GetExecutionHostAppInfoWin32@LocationCallerInfoHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `861`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800690f0`

## callees

- `0x1800201a0`
- `0x1800208b0`
- `0x180020994`
- `0x1800209d4`
- `0x180020a6c`
- `0x180020ad0`
- `0x180020c64`
- `0x18009cc18`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800bf610`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800203cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800203cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002035b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002035b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002040b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002040b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020291`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020243`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020243`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002032c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002032c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180020264`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180020264`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002022a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002022a`

## string_xrefs

- `0x180020325`: `aepic.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall LocationCallerInfoHelper::GetExecutionHostAppInfoWin32(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE v6; // rax
  void *v7; // rbx
  signed int LastError; // eax
  signed int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // eax
  size_t N; // r8
  int v14; // r9d
  __int64 v15; // rax
  __int64 v16; // rbx
  HMODULE LibraryW; // rax
  HMODULE v18; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v20; // rax
  void (*v21)(void); // r14
  _WORD *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  signed int v26; // eax
  __int16 **v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int16 *v30; // r11
  __int64 v31; // r8
  __int64 v32; // r10
  _WORD *v33; // rax
  __int16 v34; // si
  _WORD *v35; // rcx
  __int16 *v36; // r10
  _WORD *v37; // rax
  __int16 v38; // cx
  _BYTE v39[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 **v40; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[56]; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwProcessId; // [rsp+A0h] [rbp-60h]
  DWORD dwSize; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v45[16]; // [rsp+E8h] [rbp-18h] BYREF
  int v46[6]; // [rsp+F8h] [rbp-8h]
  _BYTE v47[96]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR ExeName[264]; // [rsp+170h] [rbp+70h] BYREF

  v40 = 0;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 260;
  std::wstring::wstring(v45);
  memset_0(v42, 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) )
  {
    v9 = -2147467259;
    goto LABEL_21;
  }
  v6 = OpenProcess(0x400u, 0, dwProcessId);
  v7 = v6;
  if ( v6 )
  {
    if ( QueryFullProcessImageNameW(v6, 1u, ExeName, &dwSize) )
    {
      CloseHandle(v7);
      goto LABEL_9;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    CloseHandle(v7);
  }
  else
  {
    v26 = GetLastError();
    v9 = v26;
    if ( v26 > 0 )
      v9 = (unsigned __int16)v26 | 0x80070000;
  }
  if ( v9 >= 0 )
  {
LABEL_9:
    v10 = std::_WChar_traits<unsigned short>::length(ExeName);
    std::wstring::_Assign<unsigned short>(v45, ExeName, v10);
    std::_WChar_traits<unsigned short>::length(L"/\\");
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45, v11);
    v15 = std::_Traits_find_last_of<std::char_traits<unsigned short>>(v12, v46[0], N, v14, N);
    if ( v15 == -1 )
    {
      v9 = -2147418113;
      goto LABEL_21;
    }
    v16 = std::wstring::substr(v45, v39, v15 + 1);
    if ( a3 != v16 )
    {
      std::wstring::_Tidy_deallocate(a3);
      std::wstring::_Take_contents(a3, v16);
    }
    std::wstring::_Tidy_deallocate(v39);
    LibraryW = LoadLibraryW(L"aepic.dll");
    v18 = LibraryW;
    if ( !LibraryW )
    {
      v9 = -2147024770;
      goto LABEL_21;
    }
    ProcAddress = GetProcAddress(LibraryW, "PicRetrieveFileInfo");
    v20 = GetProcAddress(v18, "PicFreeFileInfo");
    v21 = (void (*)(void))v20;
    if ( ProcAddress && v20 )
    {
      v9 = ((__int64 (__fastcall *)(WCHAR *, __int64, __int16 ***))ProcAddress)(ExeName, 256, &v40);
      if ( v9 >= 0 )
      {
        v27 = v40;
        if ( !v40 )
        {
LABEL_20:
          FreeLibrary(v18);
          goto LABEL_21;
        }
        v28 = 2147483646;
        v29 = 2147483646;
        v30 = v40[1];
        v31 = 45;
        v32 = 45;
        v33 = v47;
        do
        {
          if ( !v29 )
            break;
          v34 = *v30;
          if ( !*v30 )
            break;
          ++v30;
          *v33++ = v34;
          --v29;
          --v32;
        }
        while ( v32 );
        v35 = v33 - 1;
        if ( v32 )
          v35 = v33;
        *v35 = 0;
        v36 = *v27;
        v37 = RpcCallAttributes;
        do
        {
          if ( !v28 )
            break;
          v38 = *v36;
          if ( !*v36 )
            break;
          ++v36;
          *v37++ = v38;
          --v28;
          --v31;
        }
        while ( v31 );
        v22 = v37 - 1;
        if ( v31 )
          v22 = v37;
        *v22 = 0;
        v23 = std::_WChar_traits<unsigned short>::length(v47);
        std::wstring::_Assign<unsigned short>(a1, v47, v23);
        v24 = std::_WChar_traits<unsigned short>::length(RpcCallAttributes);
        std::wstring::_Assign<unsigned short>(a2, RpcCallAttributes, v24);
      }
    }
    else
    {
      v9 = -2147024769;
    }
    if ( v40 )
    {
      v21();
      v40 = 0;
    }
    goto LABEL_20;
  }
LABEL_21:
  std::wstring::_Tidy_deallocate(v45);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800201a0  mov     [rsp-8+arg_18], rbx
0x1800201a5  push    rbp
0x1800201a6  push    rsi
0x1800201a7  push    rdi
0x1800201a8  push    r12
0x1800201aa  push    r13
0x1800201ac  push    r14
0x1800201ae  push    r15
0x1800201b0  lea     rbp, [rsp-290h]
0x1800201b8  sub     rsp, 390h
0x1800201bf  mov     rax, cs:__security_cookie
0x1800201c6  xor     rax, rsp
0x1800201c9  mov     [rbp+2C0h+var_40], rax
0x1800201d0  mov     rsi, r8
0x1800201d3  mov     r12, rdx
0x1800201d6  mov     r15, rcx
0x1800201d9  xor     r13d, r13d
0x1800201dc  mov     [rsp+3C0h+var_370], r13
0x1800201e1  xor     edx, edx; Val
0x1800201e3  mov     r8d, 208h; Size
0x1800201e9  lea     rcx, [rbp+2C0h+ExeName]; void *
0x1800201ed  call    memset_0
0x1800201f2  mov     [rbp+2C0h+dwSize], 104h
0x1800201f9  lea     rcx, [rbp+2C0h+var_2D8]
0x1800201fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020202  nop
0x180020203  xor     edx, edx; Val
0x180020205  lea     r8d, [r13+70h]; Size
0x180020209  lea     rcx, [rsp+3C0h+var_358]; void *
0x18002020e  call    memset_0
0x180020213  mov     [rsp+3C0h+RpcCallAttributes], 3
0x18002021b  mov     [rsp+3C0h+var_35C], 10h
0x180020223  lea     rdx, [rsp+3C0h+RpcCallAttributes]; RpcCallAttributes
0x180020228  xor     ecx, ecx; ClientBinding
0x18002022a  call    cs:__imp_RpcServerInqCallAttributesW
0x180020230  test    eax, eax
0x180020232  jnz     loc_1800204E8
0x180020238  mov     r8d, [rbp+2C0h+dwProcessId]; dwProcessId
0x18002023c  xor     edx, edx; bInheritHandle
0x18002023e  mov     ecx, 400h; dwDesiredAccess
0x180020243  call    cs:__imp_OpenProcess
0x180020249  mov     rbx, rax
0x18002024c  test    rax, rax
0x18002024f  jz      loc_18002040B
0x180020255  lea     r9, [rbp+2C0h+dwSize]; lpdwSize
0x180020259  lea     r8, [rbp+2C0h+ExeName]; lpExeName
0x18002025d  lea     edx, [r13+1]; dwFlags
0x180020261  mov     rcx, rax; hProcess
0x180020264  call    cs:__imp_QueryFullProcessImageNameW
0x18002026a  test    eax, eax
0x18002026c  jz      short loc_180020279
0x18002026e  mov     rcx, rbx; hObject
0x180020271  call    cs:__imp_CloseHandle
0x180020277  jmp     short loc_18002029F
0x180020279  call    cs:__imp_GetLastError
0x18002027f  mov     edi, eax
0x180020281  test    eax, eax
0x180020283  jle     short loc_18002028E
0x180020285  movzx   edi, ax
0x180020288  or      edi, 80070000h
0x18002028e  mov     rcx, rbx; hObject
0x180020291  call    cs:__imp_CloseHandle
0x180020297  test    edi, edi
0x180020299  js      loc_1800203D6
0x18002029f  lea     rcx, [rbp+2C0h+ExeName]
0x1800202a3  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800202a8  mov     r8, rax
0x1800202ab  lea     rdx, [rbp+2C0h+ExeName]
0x1800202af  lea     rcx, [rbp+2C0h+var_2D8]
0x1800202b3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800202b8  lea     rcx, S; "/\\"
0x1800202bf  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800202c4  mov     r8, rax
0x1800202c7  lea     rcx, [rbp+2C0h+var_2D8]
0x1800202cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800202d0  mov     rcx, rax; int
0x1800202d3  mov     [rsp+3C0h+N], r8; N
0x1800202d8  mov     rdx, qword ptr [rbp+2C0h+var_2C8]; int
0x1800202dc  call    ??$_Traits_find_last_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800202e1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800202e5  cmp     rax, r9
0x1800202e8  jz      loc_18002042A
0x1800202ee  lea     r8, [rax+1]
0x1800202f2  lea     rdx, [rsp+3C0h+var_390]
0x1800202f7  lea     rcx, [rbp+2C0h+var_2D8]
0x1800202fb  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180020300  mov     rbx, rax
0x180020303  cmp     rsi, rax
0x180020306  jz      short loc_18002031B
0x180020308  mov     rcx, rsi
0x18002030b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020310  mov     rdx, rbx
0x180020313  mov     rcx, rsi
0x180020316  call    ?_Take_contents@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x18002031b  lea     rcx, [rsp+3C0h+var_390]
0x180020320  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020325  lea     rcx, LibFileName; "aepic.dll"
0x18002032c  call    cs:__imp_LoadLibraryW
0x180020332  mov     rbx, rax
0x180020335  test    rax, rax
0x180020338  jz      loc_1800204F2
0x18002033e  lea     rdx, ProcName; "PicRetrieveFileInfo"
0x180020345  mov     rcx, rax; hModule
0x180020348  call    cs:__imp_GetProcAddress
0x18002034e  mov     rdi, rax
0x180020351  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180020358  mov     rcx, rbx; hModule
0x18002035b  call    cs:__imp_GetProcAddress
0x180020361  mov     r14, rax
0x180020364  test    rdi, rdi
0x180020367  jnz     loc_180020431
0x18002036d  mov     edi, 8007007Fh
0x180020372  jmp     short loc_1800203B5
0x180020374  lea     rdx, [rax-2]
0x180020378  test    r8, r8
0x18002037b  cmovnz  rdx, rax
0x18002037f  mov     [rdx], r13w
0x180020383  lea     rcx, [rbp+2C0h+var_2B0]
0x180020387  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002038c  mov     r8, rax
0x18002038f  lea     rdx, [rbp+2C0h+var_2B0]
0x180020393  mov     rcx, r15
0x180020396  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002039b  lea     rcx, [rsp+3C0h+RpcCallAttributes]
0x1800203a0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800203a5  mov     r8, rax
0x1800203a8  lea     rdx, [rsp+3C0h+RpcCallAttributes]
0x1800203ad  mov     rcx, r12
0x1800203b0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800203b5  mov     rcx, [rsp+3C0h+var_370]
0x1800203ba  test    rcx, rcx
0x1800203bd  jz      short loc_1800203CC
0x1800203bf  mov     rax, r14
0x1800203c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203c7  mov     [rsp+3C0h+var_370], r13
0x1800203cc  mov     rcx, rbx; hLibModule
0x1800203cf  call    cs:__imp_FreeLibrary
0x1800203d5  nop
0x1800203d6  lea     rcx, [rbp+2C0h+var_2D8]
0x1800203da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800203df  mov     eax, edi
0x1800203e1  mov     rcx, [rbp+2C0h+var_40]
0x1800203e8  xor     rcx, rsp; StackCookie
0x1800203eb  call    __security_check_cookie
0x1800203f0  mov     rbx, [rsp+3C0h+arg_18]
0x1800203f8  add     rsp, 390h
0x1800203ff  pop     r15
0x180020401  pop     r14
0x180020403  pop     r13
0x180020405  pop     r12
0x180020407  pop     rdi
0x180020408  pop     rsi
0x180020409  pop     rbp
0x18002040a  retn
0x18002040b  call    cs:__imp_GetLastError
0x180020411  nop
0x180020412  mov     edi, eax
0x180020414  test    eax, eax
0x180020416  jle     loc_180020297
0x18002041c  movzx   edi, ax
0x18002041f  or      edi, 80070000h
0x180020425  jmp     loc_180020297
0x18002042a  mov     edi, 8000FFFFh
0x18002042f  jmp     short loc_1800203D6
0x180020431  test    r14, r14
0x180020434  jz      loc_18002036D
0x18002043a  lea     r8, [rsp+3C0h+var_370]
0x18002043f  mov     edx, 100h
0x180020444  lea     rcx, [rbp+2C0h+ExeName]
0x180020448  mov     rax, rdi
0x18002044b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020450  mov     edi, eax
0x180020452  test    eax, eax
0x180020454  js      loc_1800203B5
0x18002045a  mov     r9, [rsp+3C0h+var_370]
0x18002045f  test    r9, r9
0x180020462  jz      loc_1800203CC
0x180020468  mov     edx, 7FFFFFFEh
0x18002046d  mov     ecx, edx
0x18002046f  mov     r11, [r9+8]
0x180020473  mov     r8d, 2Dh ; '-'
0x180020479  mov     r10d, r8d
0x18002047c  lea     rax, [rbp+2C0h+var_2B0]
0x180020480  test    rcx, rcx
0x180020483  jz      short loc_1800204A2
0x180020485  movzx   esi, word ptr [r11]
0x180020489  test    si, si
0x18002048c  jz      short loc_1800204A2
0x18002048e  add     r11, 2
0x180020492  mov     [rax], si
0x180020495  add     rax, 2
0x180020499  dec     rcx
0x18002049c  sub     r10, 1
0x1800204a0  jnz     short loc_180020480
0x1800204a2  lea     rcx, [rax-2]
0x1800204a6  test    r10, r10
0x1800204a9  cmovnz  rcx, rax
0x1800204ad  mov     [rcx], r13w
0x1800204b1  mov     r10, [r9]
0x1800204b4  lea     rax, [rsp+3C0h+RpcCallAttributes]
0x1800204b9  test    rdx, rdx
0x1800204bc  jz      loc_180020374
0x1800204c2  movzx   ecx, word ptr [r10]
0x1800204c6  test    cx, cx
0x1800204c9  jz      loc_180020374
0x1800204cf  add     r10, 2
0x1800204d3  mov     [rax], cx
0x1800204d6  add     rax, 2
0x1800204da  dec     rdx
0x1800204dd  sub     r8, 1
0x1800204e1  jnz     short loc_1800204B9
0x1800204e3  jmp     loc_180020374
0x1800204e8  mov     edi, 80004005h
0x1800204ed  jmp     loc_1800203D6
0x1800204f2  mov     edi, 8007007Eh
0x1800204f7  jmp     loc_1800203D6
```
