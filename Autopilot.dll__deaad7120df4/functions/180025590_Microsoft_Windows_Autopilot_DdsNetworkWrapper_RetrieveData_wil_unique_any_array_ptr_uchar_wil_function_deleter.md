# Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)

- ea: `0x180025590`
- end: `0x180025950`
- name: `?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024878`
- `0x180025e74`

## callees

- `0x1800098db`
- `0x180010744`
- `0x180010764`
- `0x180022828`
- `0x180022be8`
- `0x180025590`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002574d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002580d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002574d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002580d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800258cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800256a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800256a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025771`
- `WINHTTP!WinHttpReadData` at `0x1800257df`
- `WINHTTP!WinHttpReadData` at `0x1800257df`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800255d2`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800255d2`

## string_xrefs

- `0x1800255ea`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800256c5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002579f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800257f7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025888`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800258fe`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(__int64 a1, __int64 a2)
{
  DWORD v4; // esi
  const char *v5; // r9
  unsigned int LastError; // ebx
  _QWORD *v8; // rdi
  LPVOID v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r12
  char *v12; // rdi
  int v13; // r14d
  __int64 i; // rsi
  __int64 v15; // r15
  __int64 v16; // r14
  void *v17; // rax
  void *v18; // rdi
  const char *v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rdx
  void *v22; // rdi
  const char *v23; // r9
  int v24[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v25; // [rsp+28h] [rbp-60h]
  char v26; // [rsp+30h] [rbp-58h] BYREF
  __int128 v27; // [rsp+40h] [rbp-48h] BYREF
  __int64 v28; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+90h] [rbp+8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF

  v27 = 0;
  v28 = 0;
  v4 = 0;
  while ( 1 )
  {
    dwNumberOfBytesAvailable = 0;
    if ( !WinHttpQueryDataAvailable(*(HINTERNET *)(a1 + 80), &dwNumberOfBytesAvailable) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2B2,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    v5);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
      return LastError;
    }
    if ( !dwNumberOfBytesAvailable )
    {
      if ( v4 )
      {
        v8 = (_QWORD *)v27;
        if ( *((_QWORD *)&v27 + 1) - (_QWORD)v27 == 16 )
        {
          if ( a2 != (_QWORD)v27 )
          {
            v9 = *(LPVOID *)a2;
            if ( *(_QWORD *)a2 )
            {
              CoTaskMemFree(*(LPVOID *)a2);
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              v9 = 0;
            }
            v10 = *(_QWORD *)(a2 + 8);
            *(_QWORD *)a2 = *v8;
            *(_QWORD *)(a2 + 8) = v8[1];
            *v8 = v9;
            v8[1] = v10;
          }
        }
        else
        {
          v11 = v4;
          v12 = (char *)CoTaskMemAlloc(v4);
          if ( !v12 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D3,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              (const char *)0x8007000ELL,
              v24[0]);
            std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
            return 2147942414LL;
          }
          v13 = 0;
          v15 = *((_QWORD *)&v27 + 1);
          for ( i = v27; i != v15; i += 16 )
          {
            memcpy_0(&v12[v13], *(const void **)i, *(_QWORD *)(i + 8));
            v13 += *(_DWORD *)(i + 8);
          }
          if ( (char *)a2 != &v26 )
          {
            if ( *(_QWORD *)a2 )
            {
              CoTaskMemFree(*(LPVOID *)a2);
              *(_QWORD *)(a2 + 8) = 0;
            }
            *(_QWORD *)a2 = v12;
            *(_QWORD *)(a2 + 8) = v11;
            v12 = 0;
          }
          if ( v12 )
            CoTaskMemFree(v12);
        }
      }
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
      return 0;
    }
    v16 = dwNumberOfBytesAvailable;
    v17 = CoTaskMemAlloc(dwNumberOfBytesAvailable);
    v18 = v17;
    *(_QWORD *)v24 = v17;
    v25 = v16;
    if ( !v17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8007000ELL,
        0);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
      return 2147942414LL;
    }
    dwNumberOfBytesRead = 0;
    if ( !WinHttpReadData(*(HINTERNET *)(a1 + 80), v17, v16, &dwNumberOfBytesRead) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2C0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              v19);
      CoTaskMemFree(v18);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
      return v20;
    }
    v21 = *((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) == v28 )
    {
      try
      {
        std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Emplace_reallocate<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
          (char **)&v27,
          *((char **)&v27 + 1),
          v24);
        v22 = *(void **)v24;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x2E1,
                               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                               v23);
      }
    }
    else
    {
      **((_QWORD **)&v27 + 1) = v18;
      *(_QWORD *)(v21 + 8) = v16;
      v22 = 0;
      v25 = 0;
      *((_QWORD *)&v27 + 1) += 16LL;
    }
    if ( dwNumberOfBytesRead + v4 < v4 )
      break;
    if ( dwNumberOfBytesRead != dwNumberOfBytesAvailable )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v24[0]);
      if ( v22 )
        CoTaskMemFree(v22);
      std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
      return 2147549183LL;
    }
    v4 += dwNumberOfBytesRead;
    if ( v22 )
    {
      CoTaskMemFree(v22);
      *(_QWORD *)v24 = 0;
      v25 = 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C3,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
    (const char *)0x80070216LL,
    v24[0]);
  if ( v22 )
    CoTaskMemFree(v22);
  std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>((void **)&v27);
  return 2147942934LL;
}

```

## disassembly

```asm
0x180025590  mov     [rsp+arg_8], rbx
0x180025595  push    rsi
0x180025596  push    rdi
0x180025597  push    r12
0x180025599  push    r14
0x18002559b  push    r15
0x18002559d  sub     rsp, 60h
0x1800255a1  mov     rbx, rdx
0x1800255a4  mov     r15, rcx
0x1800255a7  xorps   xmm0, xmm0
0x1800255aa  movdqu  [rsp+88h+var_48], xmm0
0x1800255b0  mov     [rsp+88h+var_38], 0
0x1800255b9  xor     esi, esi
0x1800255bb  mov     [rsp+88h+dwNumberOfBytesAvailable], 0
0x1800255c6  lea     rdx, [rsp+88h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800255ce  mov     rcx, [r15+50h]; hRequest
0x1800255d2  call    cs:__imp_WinHttpQueryDataAvailable
0x1800255d9  nop     dword ptr [rax+rax+00h]
0x1800255de  test    eax, eax
0x1800255e0  jnz     short loc_18002560E
0x1800255e2  mov     rcx, [rsp+88h]; this
0x1800255ea  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800255f1  mov     edx, 2B2h; void *
0x1800255f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800255fb  mov     ebx, eax
0x1800255fd  lea     rcx, [rsp+88h+var_48]
0x180025602  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180025607  mov     eax, ebx
0x180025609  jmp     loc_18002593A
0x18002560e  mov     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x180025615  test    eax, eax
0x180025617  jnz     loc_18002576B
0x18002561d  test    esi, esi
0x18002561f  jnz     short loc_180025632
0x180025621  lea     rcx, [rsp+88h+var_48]
0x180025626  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x18002562b  xor     eax, eax
0x18002562d  jmp     loc_18002593A
0x180025632  mov     rdi, qword ptr [rsp+88h+var_48]
0x180025637  mov     rax, qword ptr [rsp+88h+var_48+8]
0x18002563c  sub     rax, rdi
0x18002563f  cmp     rax, 10h
0x180025643  jnz     short loc_18002569C
0x180025645  cmp     rbx, rdi
0x180025648  jz      short loc_18002568B
0x18002564a  mov     rdx, [rbx]
0x18002564d  test    rdx, rdx
0x180025650  jz      short loc_180025672
0x180025652  mov     rcx, rdx; pv
0x180025655  call    cs:__imp_CoTaskMemFree
0x18002565c  nop     dword ptr [rax+rax+00h]
0x180025661  mov     qword ptr [rbx], 0
0x180025668  mov     qword ptr [rbx+8], 0
0x180025670  xor     edx, edx
0x180025672  mov     rcx, [rbx+8]
0x180025676  mov     rax, [rdi]
0x180025679  mov     [rbx], rax
0x18002567c  mov     rax, [rdi+8]
0x180025680  mov     [rbx+8], rax
0x180025684  mov     [rdi], rdx
0x180025687  mov     [rdi+8], rcx
0x18002568b  lea     rcx, [rsp+88h+var_48]
0x180025690  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180025695  xor     eax, eax
0x180025697  jmp     loc_18002593A
0x18002569c  mov     r12d, esi
0x18002569f  mov     ecx, esi; cb
0x1800256a1  call    cs:__imp_CoTaskMemAlloc
0x1800256a8  nop     dword ptr [rax+rax+00h]
0x1800256ad  mov     rdi, rax
0x1800256b0  test    rax, rax
0x1800256b3  jnz     short loc_1800256E8
0x1800256b5  mov     rcx, [rsp+88h]; this
0x1800256bd  mov     ebx, 8007000Eh
0x1800256c2  mov     r9d, ebx; char *
0x1800256c5  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800256cc  mov     edx, 2D3h; void *
0x1800256d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256d6  nop
0x1800256d7  lea     rcx, [rsp+88h+var_48]
0x1800256dc  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x1800256e1  mov     eax, ebx
0x1800256e3  jmp     loc_18002593A
0x1800256e8  xor     r14d, r14d
0x1800256eb  mov     rsi, qword ptr [rsp+88h+var_48]
0x1800256f0  mov     r15, qword ptr [rsp+88h+var_48+8]
0x1800256f5  jmp     short loc_180025711
0x1800256f7  mov     ecx, r14d
0x1800256fa  add     rcx, rdi; void *
0x1800256fd  mov     r8, [rsi+8]; Size
0x180025701  mov     rdx, [rsi]; Src
0x180025704  call    memcpy_0
0x180025709  add     r14d, [rsi+8]
0x18002570d  add     rsi, 10h
0x180025711  cmp     rsi, r15
0x180025714  jnz     short loc_1800256F7
0x180025716  lea     rax, [rsp+88h+var_58]
0x18002571b  cmp     rbx, rax
0x18002571e  jz      short loc_180025745
0x180025720  mov     rcx, [rbx]; pv
0x180025723  test    rcx, rcx
0x180025726  jz      short loc_18002573C
0x180025728  call    cs:__imp_CoTaskMemFree
0x18002572f  nop     dword ptr [rax+rax+00h]
0x180025734  mov     qword ptr [rbx+8], 0
0x18002573c  mov     [rbx], rdi
0x18002573f  mov     [rbx+8], r12
0x180025743  xor     edi, edi
0x180025745  test    rdi, rdi
0x180025748  jz      short loc_18002575A
0x18002574a  mov     rcx, rdi; pv
0x18002574d  call    cs:__imp_CoTaskMemFree
0x180025754  nop     dword ptr [rax+rax+00h]
0x180025759  nop
0x18002575a  lea     rcx, [rsp+88h+var_48]
0x18002575f  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180025764  xor     eax, eax
0x180025766  jmp     loc_18002593A
0x18002576b  mov     r14, rax
0x18002576e  mov     rcx, rax; cb
0x180025771  call    cs:__imp_CoTaskMemAlloc
0x180025778  nop     dword ptr [rax+rax+00h]
0x18002577d  mov     rdi, rax
0x180025780  mov     qword ptr [rsp+88h+var_68], rax; int
0x180025785  mov     [rsp+88h+var_60], r14
0x18002578a  test    rax, rax
0x18002578d  jnz     short loc_1800257C2
0x18002578f  mov     rcx, [rsp+88h]; this
0x180025797  mov     ebx, 8007000Eh
0x18002579c  mov     r9d, ebx; char *
0x18002579f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800257a6  mov     edx, 2B9h; void *
0x1800257ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800257b0  nop
0x1800257b1  lea     rcx, [rsp+88h+var_48]
0x1800257b6  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x1800257bb  mov     eax, ebx
0x1800257bd  jmp     loc_18002593A
0x1800257c2  mov     [rsp+88h+dwNumberOfBytesRead], 0
0x1800257cd  lea     r9, [rsp+88h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800257d5  mov     r8d, r14d; dwNumberOfBytesToRead
0x1800257d8  mov     rdx, rdi; lpBuffer
0x1800257db  mov     rcx, [r15+50h]; hRequest
0x1800257df  call    cs:__imp_WinHttpReadData
0x1800257e6  nop     dword ptr [rax+rax+00h]
0x1800257eb  test    eax, eax
0x1800257ed  jnz     short loc_18002582B
0x1800257ef  mov     rcx, [rsp+88h]; this
0x1800257f7  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800257fe  mov     edx, 2C0h; void *
0x180025803  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025808  mov     ebx, eax
0x18002580a  mov     rcx, rdi; pv
0x18002580d  call    cs:__imp_CoTaskMemFree
0x180025814  nop     dword ptr [rax+rax+00h]
0x180025819  nop
0x18002581a  lea     rcx, [rsp+88h+var_48]
0x18002581f  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x180025824  mov     eax, ebx
0x180025826  jmp     loc_18002593A
0x18002582b  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180025830  cmp     rdx, [rsp+88h+var_38]
0x180025835  jz      short loc_18002584D
0x180025837  mov     [rdx], rdi
0x18002583a  mov     [rdx+8], r14
0x18002583e  xor     edi, edi
0x180025840  mov     [rsp+88h+var_60], rdi
0x180025845  add     qword ptr [rsp+88h+var_48+8], 10h
0x18002584b  jmp     short loc_180025861
0x18002584d  lea     r8, [rsp+88h+var_68]
0x180025852  lea     rcx, [rsp+88h+var_48]
0x180025857  call    ??$_Emplace_reallocate@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@AEAAPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Emplace_reallocate<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)
0x18002585c  mov     rdi, qword ptr [rsp+88h+var_68]
0x180025861  mov     eax, [rsp+88h+dwNumberOfBytesRead]
0x180025868  lea     ecx, [rax+rsi]
0x18002586b  cmp     ecx, esi
0x18002586d  jb      short loc_1800258EE
0x18002586f  cmp     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x180025876  jz      short loc_1800258BD
0x180025878  mov     rcx, [rsp+88h]; this
0x180025880  mov     ebx, 8000FFFFh
0x180025885  mov     r9d, ebx; char *
0x180025888  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002588f  mov     edx, 2C6h; void *
0x180025894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025899  nop
0x18002589a  test    rdi, rdi
0x18002589d  jz      short loc_1800258AF
0x18002589f  mov     rcx, rdi; pv
0x1800258a2  call    cs:__imp_CoTaskMemFree
0x1800258a9  nop     dword ptr [rax+rax+00h]
0x1800258ae  nop
0x1800258af  lea     rcx, [rsp+88h+var_48]
0x1800258b4  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x1800258b9  mov     eax, ebx
0x1800258bb  jmp     short loc_18002593A
0x1800258bd  mov     esi, ecx
0x1800258bf  test    rdi, rdi
0x1800258c2  jz      loc_1800255BB
0x1800258c8  mov     rcx, rdi; pv
0x1800258cb  call    cs:__imp_CoTaskMemFree
0x1800258d2  nop     dword ptr [rax+rax+00h]
0x1800258d7  mov     qword ptr [rsp+88h+var_68], 0
0x1800258e0  mov     [rsp+88h+var_60], 0
0x1800258e9  jmp     loc_1800255BB
0x1800258ee  mov     rcx, [rsp+88h]; this
0x1800258f6  mov     ebx, 80070216h
0x1800258fb  mov     r9d, ebx; char *
0x1800258fe  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025905  mov     edx, 2C3h; void *
0x18002590a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002590f  nop
0x180025910  test    rdi, rdi
0x180025913  jz      short loc_180025925
0x180025915  mov     rcx, rdi; pv
0x180025918  call    cs:__imp_CoTaskMemFree
0x18002591f  nop     dword ptr [rax+rax+00h]
0x180025924  nop
0x180025925  lea     rcx, [rsp+88h+var_48]
0x18002592a  call    ??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(void)
0x18002592f  mov     eax, ebx
0x180025931  jmp     short loc_18002593A
0x180025933  mov     eax, [rsp+88h+dwNumberOfBytesAvailable]
0x18002593a  mov     rbx, [rsp+88h+arg_8]
0x180025942  add     rsp, 60h
0x180025946  pop     r15
0x180025948  pop     r14
0x18002594a  pop     r12
0x18002594c  pop     rdi
0x18002594d  pop     rsi
0x18002594e  retn
```
