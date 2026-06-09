# _CleanupMessage

- ea: `0x180024bd0`
- end: `0x180024e2c`
- name: `_CleanupMessage`
- size: `604`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800245a0`
- `0x1800245b0`
- `0x1800383d0`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000bf7c`
- `0x1800249dc`
- `0x180024bd0`
- `0x1800251c4`
- `0x1800255c0`
- `0x180025604`
- `0x180025674`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024dd3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024dc9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024dc9`

## pseudocode

```c
__int64 __fastcall CleanupMessage(__int64 *a1, int a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int TempFileReferencedInAttachment; // eax
  int v12; // eax
  LPCWSTR *i; // rbx
  signed int LastError; // eax
  bool v15; // sf
  unsigned int v17; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+38h] [rbp-21h] BYREF
  __int64 v19; // [rsp+40h] [rbp-19h] BYREF
  __int128 v20; // [rsp+48h] [rbp-11h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h]
  _OWORD v22[2]; // [rsp+60h] [rbp+7h] BYREF

  v2 = *a1;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v2 + 64))(a1, &v17);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = *a1;
    v19 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 240))(a1, &v19);
    v6 = v8;
    if ( v8 < 0 )
    {
      Log_HREvent_6(v8);
LABEL_31:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      return v6;
    }
    v21 = 0;
    v20 = 0;
    utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(&v20);
    if ( (unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::reserve(&v20) )
    {
      while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19) )
      {
        v18 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 32LL))(v19, &v18);
        v6 = v10;
        if ( v10 < 0 )
        {
          Log_HREvent_6(v10);
          goto LABEL_18;
        }
        memset(v22, 0, sizeof(v22));
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v22);
        TempFileReferencedInAttachment = GetTempFileReferencedInAttachment(v17, v18, v22);
        if ( TempFileReferencedInAttachment < 0 )
          Log_HREvent_6(TempFileReferencedInAttachment);
        if ( *(_QWORD *)&v22[0] != *((_QWORD *)&v22[0] + 1)
          && !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                                 &v20,
                                 v22) )
        {
          v6 = -2147024882;
          Log_HREvent_6(-2147024882);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
LABEL_18:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
          goto LABEL_8;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
      }
      if ( !a2 || (v12 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 200))(a1), v6 = v12, v12 >= 0) )
      {
        for ( i = (LPCWSTR *)v20; i != *((LPCWSTR **)&v20 + 1); i += 4 )
        {
          if ( !DeleteFileW(*i) )
          {
            LastError = GetLastError();
            v15 = LastError < 0;
            if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
              v15 = LastError < 0;
            }
            if ( v15 )
              Log_HREvent_6(LastError);
          }
        }
        utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v20);
        v6 = 0;
        goto LABEL_31;
      }
      v9 = v12;
    }
    else
    {
      v6 = -2147024882;
      v9 = -2147024882;
    }
    Log_HREvent_6(v9);
LABEL_8:
    utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v20);
    goto LABEL_31;
  }
  Log_HREvent_6(v5);
  return v6;
}

```

## disassembly

```asm
0x180024bd0  push    rbp
0x180024bd2  push    rbx
0x180024bd3  push    rsi
0x180024bd4  push    rdi
0x180024bd5  lea     rbp, [rsp-3Fh]
0x180024bda  sub     rsp, 98h
0x180024be1  mov     rax, cs:__security_cookie
0x180024be8  xor     rax, rsp
0x180024beb  mov     [rbp+57h+var_30], rax
0x180024bef  mov     rax, [rcx]
0x180024bf2  mov     esi, edx
0x180024bf4  lea     rdx, [rbp+57h+var_80]
0x180024bf8  mov     [rbp+57h+var_80], 0
0x180024bff  mov     rdi, rcx
0x180024c02  mov     rax, [rax+40h]
0x180024c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0b  mov     ebx, eax
0x180024c0d  test    eax, eax
0x180024c0f  jns     short loc_180024C28
0x180024c11  mov     edx, 1
0x180024c16  mov     r9d, 16Bh
0x180024c1c  mov     ecx, eax; int
0x180024c1e  call    Log_HREvent_6
0x180024c23  jmp     loc_180024E12
0x180024c28  mov     rax, [rdi]
0x180024c2b  lea     rdx, [rbp+57h+var_70]
0x180024c2f  mov     rcx, rdi
0x180024c32  mov     [rbp+57h+var_70], 0
0x180024c3a  mov     rax, [rax+0F0h]
0x180024c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c46  mov     ebx, eax
0x180024c48  test    eax, eax
0x180024c4a  jns     short loc_180024C63
0x180024c4c  mov     edx, 1
0x180024c51  mov     r9d, 172h
0x180024c57  mov     ecx, eax; int
0x180024c59  call    Log_HREvent_6
0x180024c5e  jmp     loc_180024E09
0x180024c63  xor     eax, eax
0x180024c65  lea     rcx, [rbp+57h+var_68]
0x180024c69  xorps   xmm0, xmm0
0x180024c6c  mov     [rbp+57h+var_58], rax
0x180024c70  movups  [rbp+57h+var_68], xmm0
0x180024c74  call    ??0?$vector@V?$CComPtr@VChatServiceMessage@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceMessage@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>::vector<ATL::CComPtr<ChatServiceMessage>,utl::allocator<ATL::CComPtr<ChatServiceMessage>>>(void)
0x180024c79  lea     rcx, [rbp+57h+var_68]
0x180024c7d  call    ?reserve@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::reserve(unsigned __int64)
0x180024c82  test    al, al
0x180024c84  jnz     short loc_180024CA8
0x180024c86  mov     ebx, 8007000Eh
0x180024c8b  xor     edx, edx
0x180024c8d  mov     ecx, ebx; int
0x180024c8f  mov     r9d, 177h
0x180024c95  call    Log_HREvent_6
0x180024c9a  lea     rcx, [rbp+57h+var_68]
0x180024c9e  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x180024ca3  jmp     loc_180024E09
0x180024ca8  mov     rcx, [rbp+57h+var_70]
0x180024cac  mov     rax, [rcx]
0x180024caf  mov     rax, [rax+18h]
0x180024cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cb8  test    eax, eax
0x180024cba  jnz     loc_180024D8E
0x180024cc0  mov     rcx, [rbp+57h+var_70]
0x180024cc4  lea     rdx, [rbp+57h+var_78]
0x180024cc8  mov     [rbp+57h+var_78], 0
0x180024cd0  mov     rax, [rcx]
0x180024cd3  mov     rax, [rax+20h]
0x180024cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cdc  mov     ebx, eax
0x180024cde  test    eax, eax
0x180024ce0  js      loc_180024D6E
0x180024ce6  xorps   xmm0, xmm0
0x180024ce9  lea     rcx, [rbp+57h+var_50]
0x180024ced  movups  [rbp+57h+var_50], xmm0
0x180024cf1  movups  [rbp+57h+var_40], xmm0
0x180024cf5  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180024cfa  mov     rdx, [rbp+57h+var_78]
0x180024cfe  lea     r8, [rbp+57h+var_50]
0x180024d02  mov     ecx, [rbp+57h+var_80]
0x180024d05  call    _GetTempFileReferencedInAttachment
0x180024d0a  test    eax, eax
0x180024d0c  jns     short loc_180024D1D
0x180024d0e  xor     edx, edx
0x180024d10  mov     r9d, 180h
0x180024d16  mov     ecx, eax; int
0x180024d18  call    Log_HREvent_6
0x180024d1d  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180024d21  cmp     qword ptr [rbp+57h+var_50], rax
0x180024d25  jz      short loc_180024D38
0x180024d27  lea     rdx, [rbp+57h+var_50]
0x180024d2b  lea     rcx, [rbp+57h+var_68]
0x180024d2f  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180024d34  test    al, al
0x180024d36  jz      short loc_180024D4F
0x180024d38  lea     rcx, [rbp+57h+var_50]
0x180024d3c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180024d41  lea     rcx, [rbp+57h+var_78]
0x180024d45  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024d4a  jmp     loc_180024CA8
0x180024d4f  mov     ebx, 8007000Eh
0x180024d54  xor     edx, edx
0x180024d56  mov     ecx, ebx; int
0x180024d58  mov     r9d, 184h
0x180024d5e  call    Log_HREvent_6
0x180024d63  lea     rcx, [rbp+57h+var_50]
0x180024d67  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180024d6c  jmp     short loc_180024D80
0x180024d6e  mov     edx, 1
0x180024d73  mov     r9d, 17Ch
0x180024d79  mov     ecx, eax; int
0x180024d7b  call    Log_HREvent_6
0x180024d80  lea     rcx, [rbp+57h+var_78]
0x180024d84  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024d89  jmp     loc_180024C9A
0x180024d8e  test    esi, esi
0x180024d90  jz      short loc_180024DBC
0x180024d92  mov     rax, [rdi]
0x180024d95  mov     rcx, rdi
0x180024d98  mov     rax, [rax+0C8h]
0x180024d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024da4  mov     ebx, eax
0x180024da6  test    eax, eax
0x180024da8  jns     short loc_180024DBC
0x180024daa  mov     edx, 1
0x180024daf  mov     r9d, 18Bh
0x180024db5  mov     ecx, eax
0x180024db7  jmp     loc_180024C95
0x180024dbc  mov     rbx, qword ptr [rbp+57h+var_68]
0x180024dc0  cmp     rbx, qword ptr [rbp+57h+var_68+8]
0x180024dc4  jz      short loc_180024DFE
0x180024dc6  mov     rcx, [rbx]; lpFileName
0x180024dc9  call    cs:__imp_DeleteFileW
0x180024dcf  test    eax, eax
0x180024dd1  jnz     short loc_180024DF8
0x180024dd3  call    cs:__imp_GetLastError
0x180024dd9  test    eax, eax
0x180024ddb  jle     short loc_180024DE7
0x180024ddd  movzx   eax, ax
0x180024de0  or      eax, 80070000h
0x180024de5  test    eax, eax
0x180024de7  jns     short loc_180024DF8
0x180024de9  xor     edx, edx
0x180024deb  mov     r9d, 193h
0x180024df1  mov     ecx, eax; int
0x180024df3  call    Log_HREvent_6
0x180024df8  add     rbx, 20h ; ' '
0x180024dfc  jmp     short loc_180024DC0
0x180024dfe  lea     rcx, [rbp+57h+var_68]
0x180024e02  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x180024e07  xor     ebx, ebx
0x180024e09  lea     rcx, [rbp+57h+var_70]
0x180024e0d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180024e12  mov     eax, ebx
0x180024e14  mov     rcx, [rbp+57h+var_30]
0x180024e18  xor     rcx, rsp; StackCookie
0x180024e1b  call    __security_check_cookie
0x180024e20  add     rsp, 98h
0x180024e27  pop     rdi
0x180024e28  pop     rsi
0x180024e29  pop     rbx
0x180024e2a  pop     rbp
0x180024e2b  retn
```
