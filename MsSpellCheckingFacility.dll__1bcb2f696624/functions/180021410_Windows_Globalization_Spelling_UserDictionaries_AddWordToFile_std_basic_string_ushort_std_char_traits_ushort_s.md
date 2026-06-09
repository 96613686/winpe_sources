# Windows::Globalization::Spelling::UserDictionaries::AddWordToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180021410`
- end: `0x1800217a1`
- name: `?AddWordToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `913`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180046920`
- `0x18004b100`

## callees

- `0x1800202e4`
- `0x180021410`
- `0x1800222ac`
- `0x18003a2ec`
- `0x18004186c`
- `0x180046e94`
- `0x18004b4e0`
- `0x18004b55c`
- `0x180061320`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214bf`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800214d3`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800214d3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002171e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002171e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180021710`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180021710`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x1800216e4`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x1800216e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800214b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800214b0`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800215b3`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800215d8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800215b3`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800215d8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021550`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021600`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021550`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021600`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x180021741`
- `api-ms-win-core-file-l1-1-0!UnlockFile` at `0x180021741`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Globalization::Spelling::UserDictionaries::AddWordToFile(const WCHAR *lpFileName, __int64 a2)
{
  const WCHAR *v3; // rsi
  DWORD v4; // r15d
  unsigned int v5; // r14d
  char v6; // r12
  __int64 FileW; // rdi
  _QWORD *v8; // rdx
  _WORD *v9; // rax
  DWORD v10; // ebx
  LPCVOID *v11; // rdx
  _WORD Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  _LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  _BYTE v18[64]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFile; // [rsp+B0h] [rbp-50h]
  _QWORD v20[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v21; // [rsp+F8h] [rbp-8h]

  v3 = lpFileName;
  if ( !*((_QWORD *)lpFileName + 2) )
    return 0;
  v20[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
  v20[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
  v21 = v20;
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    v3 = *(const WCHAR **)lpFileName;
  v4 = 2;
  v5 = 0;
  v6 = 1;
  while ( v5 < 5 )
  {
    FileW = (__int64)CreateFileW(v3, 0xC0000004, 3u, 0, 4u, 0x10000000u, 0);
    if ( FileW != -1 )
      goto LABEL_10;
    if ( GetLastError() - 2 <= 1 )
      break;
    SleepEx(v4, 1);
    v4 *= 2;
    ++v5;
  }
  FileW = -1;
LABEL_10:
  std::function<int (void *)>::function<int (void *)>(v18, v20);
  hFile = (HANDLE)FileW;
  if ( v21 )
  {
    v8 = v20;
    LOBYTE(v8) = v21 != v20;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v8);
    FileW = (__int64)hFile;
  }
  if ( FileW == -1 )
    goto LABEL_41;
  NewFilePointer.QuadPart = 0;
  Buffer[0] = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile((HANDLE)FileW, Buffer, 2u, &NumberOfBytesRead, 0) )
    goto LABEL_41;
  *(_OWORD *)lpBuffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpBuffer[0]) = 0;
  if ( NumberOfBytesRead )
  {
    if ( Buffer[0] == 0xFEFF )
    {
      if ( SetFilePointerEx(hFile, 0, &NewFilePointer, 2u) )
      {
        NewFilePointer.QuadPart -= 2LL;
        if ( SetFilePointerEx(hFile, NewFilePointer, 0, 0) )
        {
          if ( ReadFile(hFile, Buffer, 2u, &NumberOfBytesRead, 0) )
          {
            NewFilePointer.QuadPart += NumberOfBytesRead;
            if ( Buffer[0] != 10 && Buffer[0] != 13 && Buffer[0] != 0xFEFF )
              std::wstring::_Append<unsigned short>(lpBuffer);
            goto LABEL_27;
          }
          std::wstring::_Tidy_deallocate(lpBuffer);
          if ( hFile )
            std::_Func_class<int,void *>::operator()(v18);
          std::_Func_class<void,UserDictionary *>::_Tidy(v18);
          return 0;
        }
      }
    }
    std::wstring::_Tidy_deallocate(lpBuffer);
LABEL_41:
    std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v18);
    return 0;
  }
  std::wstring::push_back(lpBuffer, 65279);
LABEL_27:
  if ( *(_QWORD *)(a2 + 16) )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v9 = (_WORD *)a2;
    else
      v9 = *(_WORD **)a2;
    if ( *v9 == 35 )
      std::wstring::push_back(lpBuffer, 32);
    std::wstring::_Append<unsigned short>(lpBuffer);
    std::wstring::_Append<unsigned short>(lpBuffer);
  }
  v10 = 2 * si128.m128i_i32[0];
  LockFile(hFile, NewFilePointer.LowPart, NewFilePointer.HighPart, 2 * si128.m128i_i32[0], 0);
  v11 = lpBuffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v11 = (LPCVOID *)lpBuffer[0];
  if ( WriteFile(hFile, v11, v10, &NumberOfBytesRead, 0) )
    SetEndOfFile(hFile);
  else
    v6 = 0;
  UnlockFile(hFile, NewFilePointer.LowPart, NewFilePointer.HighPart, v10, 0);
  std::wstring::_Tidy_deallocate(lpBuffer);
  std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v18);
  return v6;
}

```

## disassembly

```asm
0x180021410  mov     [rsp-8+arg_10], rbx
0x180021415  mov     [rsp-8+arg_18], rsi
0x18002141a  push    rbp
0x18002141b  push    rdi
0x18002141c  push    r12
0x18002141e  push    r14
0x180021420  push    r15
0x180021422  lea     rbp, [rsp-10h]
0x180021427  sub     rsp, 110h
0x18002142e  mov     rax, cs:__security_cookie
0x180021435  xor     rax, rsp
0x180021438  mov     [rbp+30h+var_30], rax
0x18002143c  mov     rbx, rdx
0x18002143f  mov     rsi, rcx
0x180021442  cmp     qword ptr [rcx+10h], 0
0x180021447  jz      loc_180021777
0x18002144d  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x180021454  mov     [rbp+30h+var_70], rax
0x180021458  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x18002145f  mov     [rbp+30h+var_68], rax
0x180021463  lea     rax, [rbp+30h+var_70]
0x180021467  mov     [rbp+30h+var_38], rax
0x18002146b  cmp     qword ptr [rcx+18h], 7
0x180021470  jbe     short loc_180021475
0x180021472  mov     rsi, [rcx]
0x180021475  mov     r15d, 2
0x18002147b  xor     r14d, r14d
0x18002147e  lea     r12d, [r15-1]
0x180021482  cmp     r14d, 5
0x180021486  jnb     short loc_1800214E1
0x180021488  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180021491  mov     [rsp+130h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180021499  mov     [rsp+130h+dwCreationDisposition], 4; dwCreationDisposition
0x1800214a1  xor     r9d, r9d; lpSecurityAttributes
0x1800214a4  mov     edx, 0C0000004h; dwDesiredAccess
0x1800214a9  lea     r8d, [r9+3]; dwShareMode
0x1800214ad  mov     rcx, rsi; lpFileName
0x1800214b0  call    cs:__imp_CreateFileW
0x1800214b6  mov     rdi, rax
0x1800214b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800214bd  jnz     short loc_1800214E5
0x1800214bf  call    cs:__imp_GetLastError
0x1800214c5  add     eax, 0FFFFFFFEh
0x1800214c8  cmp     eax, r12d
0x1800214cb  jbe     short loc_1800214E1
0x1800214cd  mov     edx, r12d; bAlertable
0x1800214d0  mov     ecx, r15d; dwMilliseconds
0x1800214d3  call    cs:__imp_SleepEx
0x1800214d9  add     r15d, r15d
0x1800214dc  add     r14d, r12d
0x1800214df  jmp     short loc_180021482
0x1800214e1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800214e5  lea     rdx, [rbp+30h+var_70]
0x1800214e9  lea     rcx, [rsp+130h+var_C0]
0x1800214ee  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x1800214f3  mov     [rbp+30h+hFile], rdi
0x1800214f7  mov     rcx, [rbp+30h+var_38]
0x1800214fb  test    rcx, rcx
0x1800214fe  jz      short loc_18002151A
0x180021500  mov     rax, [rcx]
0x180021503  lea     rdx, [rbp+30h+var_70]
0x180021507  cmp     rcx, rdx
0x18002150a  setnz   dl
0x18002150d  mov     rax, [rax+20h]
0x180021511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021516  mov     rdi, [rbp+30h+hFile]
0x18002151a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002151e  jz      loc_18002176D
0x180021524  mov     qword ptr [rsp+130h+NewFilePointer], 0
0x18002152d  xor     eax, eax
0x18002152f  mov     [rsp+130h+Buffer], ax
0x180021534  mov     [rsp+130h+NumberOfBytesRead], eax
0x180021538  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; lpOverlapped
0x18002153d  lea     r9, [rsp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021542  lea     esi, [rax+2]
0x180021545  mov     r8d, esi; nNumberOfBytesToRead
0x180021548  lea     rdx, [rsp+130h+Buffer]; lpBuffer
0x18002154d  mov     rcx, rdi; hFile
0x180021550  call    cs:__imp_ReadFile
0x180021556  test    eax, eax
0x180021558  jz      loc_18002176D
0x18002155e  xorps   xmm0, xmm0
0x180021561  movups  xmmword ptr [rsp+130h+lpBuffer], xmm0
0x180021566  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002156e  movdqu  [rsp+130h+var_D0], xmm1
0x180021574  xor     eax, eax
0x180021576  mov     word ptr [rsp+130h+lpBuffer], ax
0x18002157b  cmp     [rsp+130h+NumberOfBytesRead], eax
0x18002157f  jnz     short loc_180021595
0x180021581  mov     edx, 0FEFFh
0x180021586  lea     rcx, [rsp+130h+lpBuffer]
0x18002158b  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180021590  jmp     loc_18002166B
0x180021595  mov     edi, 0FEFFh
0x18002159a  cmp     [rsp+130h+Buffer], di
0x18002159f  jnz     loc_180021762
0x1800215a5  xor     edx, edx; liDistanceToMove
0x1800215a7  mov     r9d, esi; dwMoveMethod
0x1800215aa  lea     r8, [rsp+130h+NewFilePointer]; lpNewFilePointer
0x1800215af  mov     rcx, [rbp+30h+hFile]; hFile
0x1800215b3  call    cs:__imp_SetFilePointerEx
0x1800215b9  test    eax, eax
0x1800215bb  jz      loc_180021762
0x1800215c1  mov     rdx, qword ptr [rsp+130h+NewFilePointer]
0x1800215c6  sub     rdx, rsi; liDistanceToMove
0x1800215c9  mov     qword ptr [rsp+130h+NewFilePointer], rdx
0x1800215ce  xor     r9d, r9d; dwMoveMethod
0x1800215d1  xor     r8d, r8d; lpNewFilePointer
0x1800215d4  mov     rcx, [rbp+30h+hFile]; hFile
0x1800215d8  call    cs:__imp_SetFilePointerEx
0x1800215de  test    eax, eax
0x1800215e0  jz      loc_180021762
0x1800215e6  mov     qword ptr [rsp+130h+dwCreationDisposition], 0; lpOverlapped
0x1800215ef  lea     r9, [rsp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800215f4  mov     r8d, esi; nNumberOfBytesToRead
0x1800215f7  lea     rdx, [rsp+130h+Buffer]; lpBuffer
0x1800215fc  mov     rcx, [rbp+30h+hFile]; hFile
0x180021600  call    cs:__imp_ReadFile
0x180021606  test    eax, eax
0x180021608  jnz     short loc_180021638
0x18002160a  lea     rcx, [rsp+130h+lpBuffer]
0x18002160f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021614  nop
0x180021615  mov     rdx, [rbp+30h+hFile]
0x180021619  test    rdx, rdx
0x18002161c  jz      short loc_180021628
0x18002161e  lea     rcx, [rsp+130h+var_C0]
0x180021623  call    ??R?$_Func_class@HPEAX@std@@QEBAHPEAX@Z; std::_Func_class<int,void *>::operator()(void *)
0x180021628  lea     rcx, [rsp+130h+var_C0]
0x18002162d  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180021632  nop
0x180021633  jmp     loc_180021777
0x180021638  mov     eax, [rsp+130h+NumberOfBytesRead]
0x18002163c  add     qword ptr [rsp+130h+NewFilePointer], rax
0x180021641  movzx   eax, [rsp+130h+Buffer]
0x180021646  cmp     ax, 0Ah
0x18002164a  jz      short loc_18002166B
0x18002164c  cmp     ax, 0Dh
0x180021650  jz      short loc_18002166B
0x180021652  cmp     ax, di
0x180021655  jz      short loc_18002166B
0x180021657  mov     r8, rsi
0x18002165a  lea     rdx, asc_1800D3F9C; "\r\n"
0x180021661  lea     rcx, [rsp+130h+lpBuffer]; Src
0x180021666  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002166b  cmp     qword ptr [rbx+10h], 0
0x180021670  jbe     short loc_1800216C5
0x180021672  cmp     qword ptr [rbx+18h], 7
0x180021677  jbe     short loc_18002167E
0x180021679  mov     rax, [rbx]
0x18002167c  jmp     short loc_180021681
0x18002167e  mov     rax, rbx
0x180021681  cmp     word ptr [rax], 23h ; '#'
0x180021685  jnz     short loc_180021696
0x180021687  mov     edx, 20h ; ' '
0x18002168c  lea     rcx, [rsp+130h+lpBuffer]
0x180021691  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180021696  mov     r8, [rbx+10h]
0x18002169a  cmp     qword ptr [rbx+18h], 7
0x18002169f  jbe     short loc_1800216A4
0x1800216a1  mov     rbx, [rbx]
0x1800216a4  mov     rdx, rbx
0x1800216a7  lea     rcx, [rsp+130h+lpBuffer]; Src
0x1800216ac  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800216b1  mov     r8, rsi
0x1800216b4  lea     rdx, asc_1800D3F9C; "\r\n"
0x1800216bb  lea     rcx, [rsp+130h+lpBuffer]; Src
0x1800216c0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800216c5  mov     eax, dword ptr [rsp+130h+var_D0]
0x1800216c9  lea     ebx, [rax+rax]
0x1800216cc  mov     [rsp+130h+dwCreationDisposition], 0; nNumberOfBytesToLockHigh
0x1800216d4  mov     r9d, ebx; nNumberOfBytesToLockLow
0x1800216d7  mov     r8d, dword ptr [rsp+130h+NewFilePointer+4]; dwFileOffsetHigh
0x1800216dc  mov     edx, dword ptr [rsp+130h+NewFilePointer]; dwFileOffsetLow
0x1800216e0  mov     rcx, [rbp+30h+hFile]; hFile
0x1800216e4  call    cs:__imp_LockFile
0x1800216ea  lea     rdx, [rsp+130h+lpBuffer]
0x1800216ef  cmp     qword ptr [rsp+130h+var_D0+8], 7
0x1800216f5  cmova   rdx, [rsp+130h+lpBuffer]; lpBuffer
0x1800216fb  mov     qword ptr [rsp+130h+dwCreationDisposition], 0; lpOverlapped
0x180021704  lea     r9, [rsp+130h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180021709  mov     r8d, ebx; nNumberOfBytesToWrite
0x18002170c  mov     rcx, [rbp+30h+hFile]; hFile
0x180021710  call    cs:__imp_WriteFile
0x180021716  test    eax, eax
0x180021718  jz      short loc_180021726
0x18002171a  mov     rcx, [rbp+30h+hFile]; hFile
0x18002171e  call    cs:__imp_SetEndOfFile
0x180021724  jmp     short loc_180021729
0x180021726  xor     r12b, r12b
0x180021729  mov     [rsp+130h+dwCreationDisposition], 0; nNumberOfBytesToUnlockHigh
0x180021731  mov     r9d, ebx; nNumberOfBytesToUnlockLow
0x180021734  mov     r8d, dword ptr [rsp+130h+NewFilePointer+4]; dwFileOffsetHigh
0x180021739  mov     edx, dword ptr [rsp+130h+NewFilePointer]; dwFileOffsetLow
0x18002173d  mov     rcx, [rbp+30h+hFile]; hFile
0x180021741  call    cs:__imp_UnlockFile
0x180021747  nop
0x180021748  lea     rcx, [rsp+130h+lpBuffer]
0x18002174d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021752  nop
0x180021753  lea     rcx, [rsp+130h+var_C0]
0x180021758  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x18002175d  mov     al, r12b
0x180021760  jmp     short loc_180021779
0x180021762  lea     rcx, [rsp+130h+lpBuffer]
0x180021767  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002176c  nop
0x18002176d  lea     rcx, [rsp+130h+var_C0]
0x180021772  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180021777  xor     al, al
0x180021779  mov     rcx, [rbp+30h+var_30]
0x18002177d  xor     rcx, rsp; StackCookie
0x180021780  call    __security_check_cookie
0x180021785  lea     r11, [rsp+130h+var_20]
0x18002178d  mov     rbx, [r11+40h]
0x180021791  mov     rsi, [r11+48h]
0x180021795  mov     rsp, r11
0x180021798  pop     r15
0x18002179a  pop     r14
0x18002179c  pop     r12
0x18002179e  pop     rdi
0x18002179f  pop     rbp
0x1800217a0  retn
```
