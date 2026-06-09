# _anonymous_namespace_::CreateStandardCollectorServiceForDevice

- ea: `0x14000fcfc`
- end: `0x140010089`
- name: `_anonymous_namespace_::CreateStandardCollectorServiceForDevice`
- size: `909`
- prototype: `__int64 __fastcall(__int64, LPVOID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000356c`

## callees

- `0x140003494`
- `0x1400043a0`
- `0x140008b1c`
- `0x14000f098`
- `0x14000fcfc`
- `0x1400104f0`
- `0x1400108a8`
- `0x1400137e0`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x14000fd91`
- `VCRUNTIME140!wcsrchr` at `0x14000fd91`
- `KERNEL32!GlobalFree` at `0x140010040`
- `KERNEL32!GlobalFree` at `0x14000ff78`
- `KERNEL32!GlobalFree` at `0x140010040`
- `KERNEL32!GlobalAlloc` at `0x14000ff6f`
- `KERNEL32!GlobalAlloc` at `0x14000ff6f`
- `KERNEL32!CreateFileW` at `0x14000fea6`
- `KERNEL32!CreateFileW` at `0x14000fea6`
- `KERNEL32!WaitNamedPipeW` at `0x14000fe7b`
- `KERNEL32!WaitNamedPipeW` at `0x14000fe7b`
- `KERNEL32!ReadFile` at `0x14000ff17`
- `KERNEL32!ReadFile` at `0x14000ff17`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdfd`
- `KERNEL32!LeaveCriticalSection` at `0x14000fe4d`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdfd`
- `KERNEL32!LeaveCriticalSection` at `0x14000fe4d`
- `KERNEL32!EnterCriticalSection` at `0x14000fd4a`
- `KERNEL32!EnterCriticalSection` at `0x14000fd4a`
- `KERNEL32!GetLastError` at `0x14000fe65`
- `KERNEL32!GetLastError` at `0x14000ff21`
- `KERNEL32!GetLastError` at `0x14000ff3a`
- `KERNEL32!GetLastError` at `0x14000ff8c`
- `KERNEL32!GetLastError` at `0x14000fe65`
- `KERNEL32!GetLastError` at `0x14000ff21`
- `KERNEL32!GetLastError` at `0x14000ff3a`
- `KERNEL32!GetLastError` at `0x14000ff8c`
- `KERNEL32!CloseHandle` at `0x140010059`
- `KERNEL32!CloseHandle` at `0x140010059`
- `ole32!CreateStreamOnHGlobal` at `0x14000ffb2`
- `ole32!CreateStreamOnHGlobal` at `0x14000ffb2`
- `ole32!CoUnmarshalInterface` at `0x140010012`
- `ole32!CoUnmarshalInterface` at `0x140010012`

## string_xrefs

- `0x14000fe5c`: `\\.\pipe\StandardCollector.Service170`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CreateStandardCollectorServiceForDevice(__int64 a1, LPVOID *a2)
{
  int ModulePath; // ebx
  wchar_t *v4; // rax
  wchar_t *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  signed int v8; // eax
  struct _RTL_CRITICAL_SECTION *FileW; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  signed int v12; // eax
  int v13; // edi
  HGLOBAL v14; // rax
  void *v15; // rsi
  signed int LastError; // eax
  __int64 v17; // [rsp+40h] [rbp-49h] BYREF
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-41h] BYREF
  char *v19; // [rsp+58h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+60h] [rbp-29h]
  __int128 v21; // [rsp+68h] [rbp-21h]
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp-11h] BYREF
  LPSTREAM ppstm; // [rsp+80h] [rbp-9h] BYREF
  wchar_t *Str[2]; // [rsp+88h] [rbp-1h] BYREF
  __int128 v25; // [rsp+98h] [rbp+Fh]
  wchar_t *v26; // [rsp+A8h] [rbp+1Fh]

  if ( !byte_140024AE0 )
  {
    v20 = &CriticalSection;
    EnterCriticalSection(&CriticalSection);
    if ( !byte_140024AE0 )
    {
      *(_OWORD *)Str = 0;
      v25 = 0;
      v26 = 0;
      ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x140000000LL);
      if ( ModulePath < 0 )
        goto LABEL_9;
      v4 = wcsrchr(Str[0], 0x5Cu);
      if ( v4 )
      {
        *v4 = 0;
        v5 = Str[0];
        *((wchar_t **)&v25 + 1) = Str[0];
        v26 = v4 + 1;
        ModulePath = 0;
      }
      else
      {
        ModulePath = -2147024735;
        v5 = (wchar_t *)*((_QWORD *)&v25 + 1);
      }
      if ( ModulePath < 0
        || (v17 = 0, ModulePath = DiagHubCommon::RegisterStandardCollectorProxyStubs((__int64)v5), ModulePath < 0) )
      {
LABEL_9:
        std::vector<unsigned short>::~vector<unsigned short>(Str);
        LeaveCriticalSection(&CriticalSection);
        return (unsigned int)ModulePath;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      byte_140024AE0 = 1;
      std::vector<unsigned short>::~vector<unsigned short>(Str);
    }
    LeaveCriticalSection(&CriticalSection);
  }
  v7 = 0;
  while ( 1 )
  {
    FileW = (struct _RTL_CRITICAL_SECTION *)CreateFileW(
                                              L"\\\\.\\pipe\\StandardCollector.Service170",
                                              0x80000000,
                                              0,
                                              0,
                                              3u,
                                              0,
                                              0);
    if ( FileW != (struct _RTL_CRITICAL_SECTION *)-1LL )
    {
      v7 = FileW;
      v20 = FileW;
      lpBuffer[0] = (LPVOID)std::_Allocate<16,std::_Default_allocate_traits>(256, v10, v11);
      v19 = (char *)lpBuffer[0] + 256;
      memset_0(lpBuffer[0], 0, 0x100u);
      lpBuffer[1] = (char *)lpBuffer[0] + 256;
      v17 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v17);
      if ( ReadFile(v7, lpBuffer[0], 0x100u, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead <= 0x100 )
        {
          v21 = 0;
          v14 = GlobalAlloc(2u, 0);
          v15 = v14;
          *(_QWORD *)&v21 = GlobalFree;
          *((_QWORD *)&v21 + 1) = v14;
          if ( v14 )
          {
            ppstm = 0;
            v13 = CreateStreamOnHGlobal(v14, 0, &ppstm);
            if ( v13 >= 0 )
            {
              v13 = ((__int64 (__fastcall *)(LPSTREAM, LPVOID, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
                      ppstm,
                      lpBuffer[0],
                      NumberOfBytesRead,
                      0);
              if ( v13 >= 0 )
              {
                v17 = 0;
                v13 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
                if ( v13 >= 0 )
                {
                  v13 = CoUnmarshalInterface(ppstm, &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44, a2);
                  if ( v13 >= 0 )
                    v13 = 0;
                }
              }
            }
            if ( ppstm )
              ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
          }
          else
          {
            LastError = GetLastError();
            v13 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v13 = LastError;
          }
          if ( v15 )
            GlobalFree(v15);
        }
        else
        {
          v13 = -518979548;
        }
      }
      else
      {
        v12 = GetLastError();
        v13 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v13 = v12;
      }
      std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
      goto LABEL_40;
    }
    v8 = GetLastError();
    if ( v8 != 231 )
      break;
    if ( !WaitNamedPipeW(L"\\\\.\\pipe\\StandardCollector.Service170", 0) )
    {
      v8 = GetLastError();
      break;
    }
  }
  v13 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v13 = v8;
LABEL_40:
  if ( v7 )
    CloseHandle(v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000fcfc  mov     [rsp-8+arg_0], rbx
0x14000fd01  mov     [rsp-8+arg_10], rsi
0x14000fd06  push    rbp
0x14000fd07  push    rdi
0x14000fd08  push    r12
0x14000fd0a  push    r14
0x14000fd0c  push    r15
0x14000fd0e  lea     rbp, [rsp-37h]
0x14000fd13  sub     rsp, 0C0h
0x14000fd1a  mov     rax, cs:__security_cookie
0x14000fd21  xor     rax, rsp
0x14000fd24  mov     [rbp+57h+var_30], rax
0x14000fd28  mov     r14, rdx
0x14000fd2b  mov     al, cs:byte_140024AE0
0x14000fd31  xor     r15d, r15d
0x14000fd34  test    al, al
0x14000fd36  jnz     loc_14000FE53
0x14000fd3c  lea     rdi, CriticalSection
0x14000fd43  mov     [rbp+57h+var_80], rdi
0x14000fd47  mov     rcx, rdi; lpCriticalSection
0x14000fd4a  call    cs:__imp_EnterCriticalSection
0x14000fd50  nop
0x14000fd51  mov     al, cs:byte_140024AE0
0x14000fd57  test    al, al
0x14000fd59  jnz     loc_14000FE4A
0x14000fd5f  xorps   xmm0, xmm0
0x14000fd62  movdqu  xmmword ptr [rbp+57h+Str], xmm0
0x14000fd67  xorps   xmm1, xmm1
0x14000fd6a  movdqu  [rbp+57h+var_48], xmm1
0x14000fd6f  mov     [rbp+57h+var_38], r15
0x14000fd73  lea     rdx, [rbp+57h+Str]
0x14000fd77  lea     rcx, cs:140000000h; hModule
0x14000fd7e  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x14000fd83  mov     ebx, eax
0x14000fd85  test    eax, eax
0x14000fd87  js      short loc_14000FDF0
0x14000fd89  lea     edx, [r15+5Ch]; Ch
0x14000fd8d  mov     rcx, [rbp+57h+Str]; Str
0x14000fd91  call    cs:__imp_wcsrchr
0x14000fd97  test    rax, rax
0x14000fd9a  jnz     short loc_14000FDA7
0x14000fd9c  mov     ebx, 800700A1h
0x14000fda1  mov     rcx, qword ptr [rbp+57h+var_48+8]
0x14000fda5  jmp     short loc_14000FDBE
0x14000fda7  mov     [rax], r15w
0x14000fdab  mov     rcx, [rbp+57h+Str]
0x14000fdaf  mov     qword ptr [rbp+57h+var_48+8], rcx
0x14000fdb3  add     rax, 2
0x14000fdb7  mov     [rbp+57h+var_38], rax
0x14000fdbb  mov     ebx, r15d
0x14000fdbe  test    ebx, ebx
0x14000fdc0  js      short loc_14000FDF0
0x14000fdc2  mov     [rbp+57h+var_A0], r15
0x14000fdc6  lea     rdx, [rbp+57h+var_A0]
0x14000fdca  call    ?RegisterStandardCollectorProxyStubs@DiagHubCommon@@YAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z; DiagHubCommon::RegisterStandardCollectorProxyStubs(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration> &)
0x14000fdcf  mov     ebx, eax
0x14000fdd1  test    eax, eax
0x14000fdd3  jns     short loc_14000FE0A
0x14000fdd5  mov     rcx, [rbp+57h+var_A0]
0x14000fdd9  test    rcx, rcx
0x14000fddc  jz      short loc_14000FDF0
0x14000fdde  mov     rax, [rcx]
0x14000fde1  mov     edx, 1
0x14000fde6  mov     rax, [rax]
0x14000fde9  call    cs:__guard_dispatch_icall_fptr
0x14000fdef  nop
0x14000fdf0  lea     rcx, [rbp+57h+Str]
0x14000fdf4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000fdf9  nop
0x14000fdfa  mov     rcx, rdi; lpCriticalSection
0x14000fdfd  call    cs:__imp_LeaveCriticalSection
0x14000fe03  mov     eax, ebx
0x14000fe05  jmp     loc_140010061
0x14000fe0a  mov     rbx, [rbp+57h+var_A0]
0x14000fe0e  mov     rax, [rbx]
0x14000fe11  mov     rcx, rbx
0x14000fe14  mov     rax, [rax+8]
0x14000fe18  call    cs:__guard_dispatch_icall_fptr
0x14000fe1e  mov     edx, 1
0x14000fe23  mov     eax, edx
0x14000fe25  xchg    al, cs:byte_140024AE0
0x14000fe2b  test    rbx, rbx
0x14000fe2e  jz      short loc_14000FE40
0x14000fe30  mov     rax, [rbx]
0x14000fe33  mov     rcx, rbx
0x14000fe36  mov     rax, [rax]
0x14000fe39  call    cs:__guard_dispatch_icall_fptr
0x14000fe3f  nop
0x14000fe40  lea     rcx, [rbp+57h+Str]
0x14000fe44  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000fe49  nop
0x14000fe4a  mov     rcx, rdi; lpCriticalSection
0x14000fe4d  call    cs:__imp_LeaveCriticalSection
0x14000fe53  mov     rbx, r15
0x14000fe56  mov     r12d, 3
0x14000fe5c  lea     rdi, FileName; "\\\\.\\pipe\\StandardCollector.Service1"...
0x14000fe63  jmp     short loc_14000FE89
0x14000fe65  call    cs:__imp_GetLastError
0x14000fe6b  cmp     eax, 0E7h
0x14000fe70  jnz     loc_14000FF40
0x14000fe76  xor     edx, edx; nTimeOut
0x14000fe78  mov     rcx, rdi; lpNamedPipeName
0x14000fe7b  call    cs:__imp_WaitNamedPipeW
0x14000fe81  test    eax, eax
0x14000fe83  jz      loc_14000FF3A
0x14000fe89  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x14000fe8e  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x14000fe93  mov     [rsp+0E0h+dwCreationDisposition], r12d; dwCreationDisposition
0x14000fe98  xor     r9d, r9d; lpSecurityAttributes
0x14000fe9b  xor     r8d, r8d; dwShareMode
0x14000fe9e  mov     edx, 80000000h; dwDesiredAccess
0x14000fea3  mov     rcx, rdi; lpFileName
0x14000fea6  call    cs:__imp_CreateFileW
0x14000feac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000feb0  mov     rsi, rax
0x14000feb3  jz      short loc_14000FE65
0x14000feb5  mov     rbx, rax
0x14000feb8  mov     [rbp+57h+var_80], rax
0x14000febc  xorps   xmm1, xmm1
0x14000febf  movdqu  xmmword ptr [rbp+57h+lpBuffer], xmm1
0x14000fec4  mov     [rbp+57h+var_88], r15
0x14000fec8  mov     r12d, 100h
0x14000fece  mov     ecx, r12d
0x14000fed1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000fed6  mov     [rbp+57h+lpBuffer], rax
0x14000feda  lea     rdi, [rax+100h]
0x14000fee1  mov     [rbp+57h+var_88], rdi
0x14000fee5  mov     r8d, r12d; Size
0x14000fee8  xor     edx, edx; Val
0x14000feea  mov     rcx, rax; void *
0x14000feed  call    memset_0
0x14000fef2  mov     [rbp+57h+lpBuffer+8], rdi
0x14000fef6  mov     [rbp+57h+var_A0], r15
0x14000fefa  lea     rcx, [rbp+57h+var_A0]
0x14000fefe  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x14000ff03  nop
0x14000ff04  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r15; lpOverlapped
0x14000ff09  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000ff0d  mov     r8d, r12d; nNumberOfBytesToRead
0x14000ff10  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x14000ff14  mov     rcx, rbx; hFile
0x14000ff17  call    cs:__imp_ReadFile
0x14000ff1d  test    eax, eax
0x14000ff1f  jnz     short loc_14000FF53
0x14000ff21  call    cs:__imp_GetLastError
0x14000ff27  movzx   edi, ax
0x14000ff2a  or      edi, 80070000h
0x14000ff30  test    eax, eax
0x14000ff32  cmovle  edi, eax
0x14000ff35  jmp     loc_140010047
0x14000ff3a  call    cs:__imp_GetLastError
0x14000ff40  movzx   edi, ax
0x14000ff43  or      edi, 80070000h
0x14000ff49  test    eax, eax
0x14000ff4b  cmovle  edi, eax
0x14000ff4e  jmp     loc_140010051
0x14000ff53  cmp     [rbp+57h+NumberOfBytesRead], r12d
0x14000ff57  jbe     short loc_14000FF63
0x14000ff59  mov     edi, 0E1110024h
0x14000ff5e  jmp     loc_140010047
0x14000ff63  xorps   xmm0, xmm0
0x14000ff66  movups  [rbp+57h+var_78], xmm0
0x14000ff6a  xor     edx, edx; dwBytes
0x14000ff6c  lea     ecx, [rdx+2]; uFlags
0x14000ff6f  call    cs:__imp_GlobalAlloc
0x14000ff75  mov     rsi, rax
0x14000ff78  mov     rcx, cs:__imp_GlobalFree
0x14000ff7f  mov     qword ptr [rbp+57h+var_78], rcx
0x14000ff83  mov     qword ptr [rbp+57h+var_78+8], rax
0x14000ff87  test    rax, rax
0x14000ff8a  jnz     short loc_14000FFA5
0x14000ff8c  call    cs:__imp_GetLastError
0x14000ff92  movzx   edi, ax
0x14000ff95  or      edi, 80070000h
0x14000ff9b  test    eax, eax
0x14000ff9d  cmovle  edi, eax
0x14000ffa0  jmp     loc_140010038
0x14000ffa5  mov     [rbp+57h+ppstm], r15
0x14000ffa9  lea     r8, [rbp+57h+ppstm]; ppstm
0x14000ffad  xor     edx, edx; fDeleteOnRelease
0x14000ffaf  mov     rcx, rsi; hGlobal
0x14000ffb2  call    cs:__imp_CreateStreamOnHGlobal
0x14000ffb8  mov     edi, eax
0x14000ffba  test    eax, eax
0x14000ffbc  js      short loc_140010021
0x14000ffbe  mov     rcx, [rbp+57h+ppstm]
0x14000ffc2  mov     rax, [rcx]
0x14000ffc5  xor     r9d, r9d
0x14000ffc8  mov     r8d, [rbp+57h+NumberOfBytesRead]
0x14000ffcc  mov     rdx, [rbp+57h+lpBuffer]
0x14000ffd0  mov     rax, [rax+20h]
0x14000ffd4  call    cs:__guard_dispatch_icall_fptr
0x14000ffda  mov     edi, eax
0x14000ffdc  test    eax, eax
0x14000ffde  js      short loc_140010021
0x14000ffe0  mov     [rbp+57h+var_A0], r15
0x14000ffe4  mov     rcx, [rbp+57h+ppstm]
0x14000ffe8  mov     rax, [rcx]
0x14000ffeb  xor     r9d, r9d
0x14000ffee  xor     r8d, r8d
0x14000fff1  mov     rdx, r15
0x14000fff4  mov     rax, [rax+28h]
0x14000fff8  call    cs:__guard_dispatch_icall_fptr
0x14000fffe  mov     edi, eax
0x140010000  test    eax, eax
0x140010002  js      short loc_140010021
0x140010004  mov     r8, r14; ppv
0x140010007  lea     rdx, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44; riid
0x14001000e  mov     rcx, [rbp+57h+ppstm]; pStm
0x140010012  call    cs:__imp_CoUnmarshalInterface
0x140010018  mov     edi, eax
0x14001001a  test    eax, eax
0x14001001c  js      short loc_140010021
0x14001001e  mov     edi, r15d
0x140010021  mov     rcx, [rbp+57h+ppstm]
0x140010025  test    rcx, rcx
0x140010028  jz      short loc_140010038
0x14001002a  mov     rax, [rcx]
0x14001002d  mov     rax, [rax+10h]
0x140010031  call    cs:__guard_dispatch_icall_fptr
0x140010037  nop
0x140010038  test    rsi, rsi
0x14001003b  jz      short loc_140010047
0x14001003d  mov     rcx, rsi; hMem
0x140010040  call    cs:__imp_GlobalFree
0x140010046  nop
0x140010047  lea     rcx, [rbp+57h+lpBuffer]
0x14001004b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140010050  nop
0x140010051  test    rbx, rbx
0x140010054  jz      short loc_14001005F
0x140010056  mov     rcx, rbx; hObject
0x140010059  call    cs:__imp_CloseHandle
0x14001005f  mov     eax, edi
0x140010061  mov     rcx, [rbp+57h+var_30]
0x140010065  xor     rcx, rsp; StackCookie
0x140010068  call    __security_check_cookie
0x14001006d  lea     r11, [rsp+0E0h+var_20]
0x140010075  mov     rbx, [r11+30h]
0x140010079  mov     rsi, [r11+40h]
0x14001007d  mov     rsp, r11
0x140010080  pop     r15
0x140010082  pop     r14
0x140010084  pop     r12
0x140010086  pop     rdi
0x140010087  pop     rbp
0x140010088  retn
```
