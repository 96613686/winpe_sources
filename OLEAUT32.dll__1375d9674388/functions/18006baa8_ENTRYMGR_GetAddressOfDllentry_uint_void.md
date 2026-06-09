# ENTRYMGR::GetAddressOfDllentry(uint,void * *)

- ea: `0x18006baa8`
- end: `0x18006bcc9`
- name: `?GetAddressOfDllentry@ENTRYMGR@@QEAAJIPEAPEAX@Z`
- size: `545`
- prototype: `__int64 __fastcall(ENTRYMGR *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18005eef0`

## callees

- `0x18004d900`
- `0x18004e530`
- `0x180060550`
- `0x180067b34`
- `0x18006ba60`
- `0x18006baa8`
- `0x18006bd74`
- `0x18006d5b8`
- `0x18006d734`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006bb60`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006bbd5`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006bb60`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006bbd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bc7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bc7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006bbf9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006bbf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bbe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bc0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bc4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bbe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bc0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18006bc4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc11`

## pseudocode

```c
__int64 __fastcall ENTRYMGR::GetAddressOfDllentry(ENTRYMGR *this, unsigned int a2, FARPROC *a3)
{
  __int64 v4; // rdi
  __int64 v6; // rsi
  int NamMgr; // ebx
  const char *v8; // r8
  __int64 v9; // rax
  unsigned __int8 *v10; // rax
  UINT v11; // r14d
  unsigned int v12; // eax
  DWORD LastError; // eax
  unsigned int v14; // r9d
  char *p_Destination; // rdx
  FARPROC ProcAddress; // rax
  struct NAMMGR *v18; // [rsp+20h] [rbp-E0h] BYREF
  char v19[272]; // [rsp+30h] [rbp-D0h] BYREF
  char Destination; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v21[255]; // [rsp+141h] [rbp+41h] BYREF

  v4 = a2;
  v18 = 0;
  Destination = 0;
  memset_0(v21, 0, 0xFEu);
  v6 = *((_QWORD *)this + 2);
  NamMgr = DYN_TYPEROOT::GetNamMgr(*((DYN_TYPEROOT **)this + 12), &v18);
  if ( NamMgr >= 0 )
  {
    v8 = (const char *)((*(_WORD *)(v4 + v6 + 2) & 0xFFFE) + **((_QWORD **)v18 + 9) + 8LL);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( (unsigned int)(v9 + 1) <= 0xFF )
    {
      strcpy_s(&Destination, 0xFFu, v8);
      memset_0(v19, 0, 0x108u);
      if ( (Destination == 92 || mbschr((const unsigned __int8 *)&Destination, 0x3Au))
        && (unsigned int)OpenLongFileA(&Destination, (__int64)v19, 0x4000) == -1 )
      {
        v10 = mbsrchr((const unsigned __int8 *)&Destination, 0x5Cu);
        if ( !v10 )
          v10 = mbsrchr((const unsigned __int8 *)&Destination, 0x3Au);
        strcpy_s(&Destination, 0xFFu, (const char *)v10);
      }
      v11 = SetErrorMode(0x8001u);
      if ( *(_DWORD *)(v4 + v6 + 16) >= 0x20u
        || (v12 = (unsigned int)LoadLibraryExA(&Destination, 0, 0), *(_DWORD *)(v4 + v6 + 16) = v12, v12 >= 0x20) )
      {
        NamMgr = 0;
        SetErrorMode(v11);
        if ( *(_WORD *)(v4 + v6) )
        {
          p_Destination = (char *)*(unsigned __int16 *)(v4 + v6 + 4);
        }
        else
        {
          ENTRYMGR::DllEntryNameOfHchunk(this, *(unsigned __int16 *)(v4 + v6 + 4), &Destination, v14);
          p_Destination = &Destination;
        }
        ProcAddress = GetProcAddress((HMODULE)*(unsigned int *)(v4 + v6 + 16), p_Destination);
        *a3 = ProcAddress;
        if ( !ProcAddress )
        {
          NamMgr = -2147319761;
          ReleaseLibrary((HINSTANCE)*(unsigned int *)(v4 + v6 + 16));
          *(_DWORD *)(v4 + v6 + 16) = 0;
        }
      }
      else
      {
        SetErrorMode(v11);
        LastError = GetLastError();
        if ( LastError == 2 || LastError - 126 <= 1 )
        {
          return (unsigned int)-2147287038;
        }
        else if ( LastError == 3 )
        {
          return (unsigned int)-2147287037;
        }
        else
        {
          return (unsigned int)(LastError != 0 ? -2147312566 : -2147024882);
        }
      }
    }
    else
    {
      return (unsigned int)-2147319786;
    }
  }
  return (unsigned int)NamMgr;
}

```

## disassembly

```asm
0x18006baa8  mov     [rsp-8+arg_18], rbx
0x18006baad  push    rbp
0x18006baae  push    rsi
0x18006baaf  push    rdi
0x18006bab0  push    r12
0x18006bab2  push    r13
0x18006bab4  push    r14
0x18006bab6  push    r15
0x18006bab8  lea     rbp, [rsp-150h]
0x18006bac0  sub     rsp, 250h
0x18006bac7  mov     rax, cs:__security_cookie
0x18006bace  xor     rax, rsp
0x18006bad1  mov     [rbp+180h+var_40], rax
0x18006bad8  mov     r15, r8
0x18006badb  mov     edi, edx
0x18006badd  mov     r13, rcx
0x18006bae0  xor     r12d, r12d
0x18006bae3  xor     edx, edx; Val
0x18006bae5  mov     [rsp+280h+var_260], r12
0x18006baea  mov     r8d, 0FEh; Size
0x18006baf0  mov     [rbp+180h+Destination], r12b
0x18006baf4  lea     rcx, [rbp+180h+var_13F]; void *
0x18006baf8  call    memset_0
0x18006bafd  mov     rcx, [r13+60h]; this
0x18006bb01  lea     rdx, [rsp+280h+var_260]; struct NAMMGR **
0x18006bb06  mov     rsi, [r13+10h]
0x18006bb0a  call    ?GetNamMgr@DYN_TYPEROOT@@QEAAJPEAPEAVNAMMGR@@@Z; DYN_TYPEROOT::GetNamMgr(NAMMGR * *)
0x18006bb0f  mov     ebx, eax
0x18006bb11  test    eax, eax
0x18006bb13  js      loc_18006BC9D
0x18006bb19  mov     rax, [rsp+280h+var_260]
0x18006bb1e  movzx   edx, word ptr [rdi+rsi+2]
0x18006bb23  and     edx, 0FFFEh
0x18006bb29  mov     rcx, [rax+48h]
0x18006bb2d  mov     r8, [rcx]
0x18006bb30  add     r8, 8
0x18006bb34  add     r8, rdx; Source
0x18006bb37  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bb3b  inc     rax
0x18006bb3e  cmp     [r8+rax], r12b
0x18006bb42  jnz     short loc_18006BB3B
0x18006bb44  inc     eax
0x18006bb46  mov     ebx, 0FFh
0x18006bb4b  cmp     eax, ebx
0x18006bb4d  jbe     short loc_18006BB59
0x18006bb4f  mov     ebx, 80028016h
0x18006bb54  jmp     loc_18006BC9D
0x18006bb59  mov     rdx, rbx; SizeInBytes
0x18006bb5c  lea     rcx, [rbp+180h+Destination]; Destination
0x18006bb60  call    cs:__imp_strcpy_s
0x18006bb66  xor     edx, edx; Val
0x18006bb68  lea     rcx, [rsp+280h+var_250]; void *
0x18006bb6d  mov     r8d, 108h; Size
0x18006bb73  call    memset_0
0x18006bb78  cmp     [rbp+180h+Destination], 5Ch ; '\'
0x18006bb7c  mov     r14d, 3Ah ; ':'
0x18006bb82  jz      short loc_18006BB95
0x18006bb84  mov     edx, r14d; C
0x18006bb87  lea     rcx, [rbp+180h+Destination]; Str
0x18006bb8b  call    _mbschr
0x18006bb90  test    rax, rax
0x18006bb93  jz      short loc_18006BBDB
0x18006bb95  mov     r8d, 4000h
0x18006bb9b  lea     rdx, [rsp+280h+var_250]
0x18006bba0  lea     rcx, [rbp+180h+Destination]; lpFileName
0x18006bba4  call    OpenLongFileA
0x18006bba9  cmp     eax, 0FFFFFFFFh
0x18006bbac  jnz     short loc_18006BBDB
0x18006bbae  lea     edx, [rax+5Dh]; C
0x18006bbb1  lea     rcx, [rbp+180h+Destination]; String
0x18006bbb5  call    _mbsrchr
0x18006bbba  test    rax, rax
0x18006bbbd  jnz     short loc_18006BBCB
0x18006bbbf  mov     edx, r14d; C
0x18006bbc2  lea     rcx, [rbp+180h+Destination]; String
0x18006bbc6  call    _mbsrchr
0x18006bbcb  mov     r8, rax; Source
0x18006bbce  lea     rcx, [rbp+180h+Destination]; Destination
0x18006bbd2  mov     rdx, rbx; SizeInBytes
0x18006bbd5  call    cs:__imp_strcpy_s
0x18006bbdb  mov     ecx, 8001h; uMode
0x18006bbe0  call    cs:__imp_SetErrorMode
0x18006bbe6  cmp     dword ptr [rdi+rsi+10h], 20h ; ' '
0x18006bbeb  mov     r14d, eax
0x18006bbee  jnb     short loc_18006BC49
0x18006bbf0  xor     r8d, r8d; dwFlags
0x18006bbf3  lea     rcx, [rbp+180h+Destination]; lpLibFileName
0x18006bbf7  xor     edx, edx; hFile
0x18006bbf9  call    cs:__imp_LoadLibraryExA
0x18006bbff  mov     [rdi+rsi+10h], eax
0x18006bc03  cmp     eax, 20h ; ' '
0x18006bc06  jnb     short loc_18006BC49
0x18006bc08  mov     ecx, r14d; uMode
0x18006bc0b  call    cs:__imp_SetErrorMode
0x18006bc11  call    cs:__imp_GetLastError
0x18006bc17  cmp     eax, 2
0x18006bc1a  jz      short loc_18006BC42
0x18006bc1c  lea     ecx, [rax-7Eh]
0x18006bc1f  cmp     ecx, 1
0x18006bc22  jbe     short loc_18006BC42
0x18006bc24  cmp     eax, 3
0x18006bc27  jnz     short loc_18006BC30
0x18006bc29  mov     ebx, 80030003h
0x18006bc2e  jmp     short loc_18006BC9D
0x18006bc30  neg     eax
0x18006bc32  sbb     ebx, ebx
0x18006bc34  and     ebx, 0FFFB9C3Ch
0x18006bc3a  add     ebx, 8007000Eh
0x18006bc40  jmp     short loc_18006BC9D
0x18006bc42  mov     ebx, 80030002h
0x18006bc47  jmp     short loc_18006BC9D
0x18006bc49  mov     ecx, r14d; uMode
0x18006bc4c  mov     ebx, r12d
0x18006bc4f  call    cs:__imp_SetErrorMode
0x18006bc55  cmp     [rdi+rsi], r12w
0x18006bc5a  jz      short loc_18006BC63
0x18006bc5c  movzx   edx, word ptr [rdi+rsi+4]
0x18006bc61  jmp     short loc_18006BC78
0x18006bc63  movzx   edx, word ptr [rdi+rsi+4]; unsigned int
0x18006bc68  lea     r8, [rbp+180h+Destination]; char *
0x18006bc6c  mov     rcx, r13; this
0x18006bc6f  call    ?DllEntryNameOfHchunk@ENTRYMGR@@QEAAJIPEADI@Z; ENTRYMGR::DllEntryNameOfHchunk(uint,char *,uint)
0x18006bc74  lea     rdx, [rbp+180h+Destination]; lpProcName
0x18006bc78  mov     ecx, [rdi+rsi+10h]; hModule
0x18006bc7c  call    cs:__imp_GetProcAddress
0x18006bc82  mov     [r15], rax
0x18006bc85  test    rax, rax
0x18006bc88  jnz     short loc_18006BC9D
0x18006bc8a  mov     ecx, [rdi+rsi+10h]; HINSTANCE
0x18006bc8e  mov     ebx, 8002802Fh
0x18006bc93  call    ?ReleaseLibrary@@YAXPEAUHINSTANCE__@@@Z; ReleaseLibrary(HINSTANCE__ *)
0x18006bc98  mov     [rdi+rsi+10h], r12d
0x18006bc9d  mov     eax, ebx
0x18006bc9f  mov     rcx, [rbp+180h+var_40]
0x18006bca6  xor     rcx, rsp; StackCookie
0x18006bca9  call    __security_check_cookie
0x18006bcae  mov     rbx, [rsp+280h+arg_18]
0x18006bcb6  add     rsp, 250h
0x18006bcbd  pop     r15
0x18006bcbf  pop     r14
0x18006bcc1  pop     r13
0x18006bcc3  pop     r12
0x18006bcc5  pop     rdi
0x18006bcc6  pop     rsi
0x18006bcc7  pop     rbp
0x18006bcc8  retn
```
