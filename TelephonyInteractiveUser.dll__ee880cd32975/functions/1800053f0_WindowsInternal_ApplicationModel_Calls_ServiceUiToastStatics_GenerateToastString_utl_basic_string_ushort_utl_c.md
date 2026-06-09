# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_GenerateToastString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,long)

- ea: `0x1800053f0`
- end: `0x180005764`
- name: `?_GenerateToastString@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@J@Z`
- size: `884`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004ef0`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180004d80`
- `0x180004d8c`
- `0x1800052b0`
- `0x1800053f0`
- `0x180005a90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005499`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800054e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005512`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800055cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000565b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800056a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005499`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800054e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005512`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800055cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000565b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800056a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000554c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000554c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005603`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005611`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005603`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000555a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000555a`

## string_xrefs

- `0x180005541`: `PhoneServiceRes.dll`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_GenerateToastString(
        __int64 a1,
        __int64 a2,
        int a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  HMODULE Library; // rax
  HMODULE v8; // rbx
  signed int LastError; // eax
  __int64 v10; // r8
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v15; // r8
  WCHAR Buffer[4]; // [rsp+30h] [rbp-50h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-48h] BYREF
  __int16 v18; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+4Ah] [rbp-36h]
  int v20; // [rsp+52h] [rbp-2Eh]
  __int16 v21; // [rsp+56h] [rbp-2Ah]
  void *v22[2]; // [rsp+58h] [rbp-28h] BYREF
  __int16 v23; // [rsp+68h] [rbp-18h] BYREF
  __int64 v24; // [rsp+6Ah] [rbp-16h]
  int v25; // [rsp+72h] [rbp-Eh]
  __int16 v26; // [rsp+76h] [rbp-Ah]

  v24 = 0;
  v26 = 0;
  v25 = 0;
  v22[0] = &v23;
  v22[1] = &v23;
  v23 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  Block[0] = &v18;
  Block[1] = &v18;
  v18 = 0;
  if ( a3 == -2147023695 || a3 == -2147023436 )
  {
    *(_QWORD *)Buffer = 0;
    if ( !LoadStringW(g_resourceDll, 0x271Cu, Buffer, 0) )
    {
      Log_AssertionEvent_0();
      __int2c();
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v22,
                             *(_QWORD *)Buffer) )
    {
      v6 = 116;
      goto LABEL_40;
    }
    *(_QWORD *)Buffer = 0;
    if ( !LoadStringW(g_resourceDll, 0x271Du, Buffer, 0) )
    {
      Log_AssertionEvent_0();
      __int2c();
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             Block,
                             *(_QWORD *)Buffer) )
    {
      v6 = 117;
      goto LABEL_40;
    }
  }
  else
  {
    *(_QWORD *)Buffer = 0;
    if ( a3 == 20 )
    {
      if ( !LoadStringW(g_resourceDll, 0x271Au, Buffer, 0) )
      {
        Log_AssertionEvent_0();
        __int2c();
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v22,
                               *(_QWORD *)Buffer) )
      {
        v6 = 122;
        goto LABEL_40;
      }
      Library = LoadLibraryExW(L"PhoneServiceRes.dll", 0, 2u);
      v8 = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v12 = 0;
        v13 = 124;
        goto LABEL_20;
      }
      *(_QWORD *)Buffer = 0;
      if ( !LoadStringW(Library, 0x2758u, Buffer, 0) )
      {
        Log_AssertionEvent_0();
        __int2c();
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               Block,
                               *(_QWORD *)Buffer) )
      {
        Log_HREvent(2147942414LL, 0, v15, 128);
        FreeLibrary(v8);
LABEL_41:
        if ( Block[0] != &v18 )
          operator delete(Block[0]);
        if ( v22[0] != &v23 )
          operator delete(v22[0]);
        return 2147942414LL;
      }
      FreeLibrary(v8);
    }
    else
    {
      if ( !LoadStringW(g_resourceDll, 0x271Au, Buffer, 0) )
      {
        Log_AssertionEvent_0();
        __int2c();
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v22,
                               *(_QWORD *)Buffer) )
      {
        v6 = 133;
LABEL_40:
        Log_HREvent(2147942414LL, 0, v5, v6);
        goto LABEL_41;
      }
      *(_QWORD *)Buffer = 0;
      if ( !LoadStringW(g_resourceDll, 0x271Bu, Buffer, 0) )
      {
        Log_AssertionEvent_0();
        __int2c();
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               Block,
                               *(_QWORD *)Buffer) )
      {
        v6 = 134;
        goto LABEL_40;
      }
    }
  }
  v11 = WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_FormatIncomingCallToastXml(
          a1,
          (const unsigned __int16 *)v22[0],
          (const unsigned __int16 *)Block[0],
          a2);
  if ( v11 < 0 )
  {
    v12 = 1;
    v13 = 138;
LABEL_20:
    Log_HREvent((unsigned int)v11, v12, v10, v13);
    if ( Block[0] != &v18 )
      operator delete(Block[0]);
    if ( v22[0] != &v23 )
      operator delete(v22[0]);
    return (unsigned int)v11;
  }
  if ( Block[0] != &v18 )
    operator delete(Block[0]);
  if ( v22[0] != &v23 )
    operator delete(v22[0]);
  return 0;
}

```

## disassembly

```asm
0x1800053f0  mov     [rsp-18h+arg_10], rbx
0x1800053f5  push    rbp
0x1800053f6  push    rsi
0x1800053f7  push    rdi
0x1800053f8  mov     rbp, rsp
0x1800053fb  sub     rsp, 80h
0x180005402  mov     rax, cs:__security_cookie
0x180005409  xor     rax, rsp
0x18000540c  mov     [rbp+var_8], rax
0x180005410  xor     eax, eax
0x180005412  mov     [rbp+var_16], 0
0x18000541a  mov     [rbp+var_A], ax
0x18000541e  mov     rsi, rdx
0x180005421  lea     rax, [rbp+var_18]
0x180005425  mov     [rbp+var_E], 0
0x18000542c  mov     [rbp+var_28], rax
0x180005430  mov     rdi, rcx
0x180005433  lea     rax, [rbp+var_18]
0x180005437  mov     [rbp+var_20], rax
0x18000543b  xor     eax, eax
0x18000543d  mov     [rbp+var_18], ax
0x180005441  mov     [rbp+var_36], rax
0x180005445  mov     [rbp+var_2E], eax
0x180005448  mov     [rbp+var_2A], ax
0x18000544c  lea     rax, [rbp+var_38]
0x180005450  mov     [rbp+Block], rax
0x180005454  lea     rax, [rbp+var_38]
0x180005458  mov     [rbp+var_40], rax
0x18000545c  xor     eax, eax
0x18000545e  mov     [rbp+var_38], ax
0x180005462  cmp     r8d, 800704B1h
0x180005469  jz      loc_180005644
0x18000546f  cmp     r8d, 800705B4h
0x180005476  jz      loc_180005644
0x18000547c  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180005483  xor     r9d, r9d; cchBufferMax
0x180005486  cmp     r8d, 14h
0x18000548a  mov     qword ptr [rbp+Buffer], rax
0x18000548e  lea     r8, [rbp+Buffer]; lpBuffer
0x180005492  mov     edx, 271Ah; uID
0x180005497  jz      short loc_180005512
0x180005499  call    cs:__imp_LoadStringW
0x18000549f  test    eax, eax
0x1800054a1  jnz     short loc_1800054AA
0x1800054a3  call    Log_AssertionEvent_0
0x1800054a8  int     2Ch; Windows NT - assertion failure
0x1800054aa  mov     rdx, qword ptr [rbp+Buffer]
0x1800054ae  lea     rcx, [rbp+var_28]
0x1800054b2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800054b7  test    al, al
0x1800054b9  jnz     short loc_1800054C6
0x1800054bb  mov     r9d, 85h
0x1800054c1  jmp     loc_1800056CC
0x1800054c6  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800054cd  lea     r8, [rbp+Buffer]; lpBuffer
0x1800054d1  xor     r9d, r9d; cchBufferMax
0x1800054d4  mov     qword ptr [rbp+Buffer], 0
0x1800054dc  mov     edx, 271Bh; uID
0x1800054e1  call    cs:__imp_LoadStringW
0x1800054e7  test    eax, eax
0x1800054e9  jnz     short loc_1800054F2
0x1800054eb  call    Log_AssertionEvent_0
0x1800054f0  int     2Ch; Windows NT - assertion failure
0x1800054f2  mov     rdx, qword ptr [rbp+Buffer]
0x1800054f6  lea     rcx, [rbp+Block]
0x1800054fa  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800054ff  test    al, al
0x180005501  jnz     loc_180005617
0x180005507  mov     r9d, 86h
0x18000550d  jmp     loc_1800056CC
0x180005512  call    cs:__imp_LoadStringW
0x180005518  test    eax, eax
0x18000551a  jnz     short loc_180005523
0x18000551c  call    Log_AssertionEvent_0
0x180005521  int     2Ch; Windows NT - assertion failure
0x180005523  mov     rdx, qword ptr [rbp+Buffer]
0x180005527  lea     rcx, [rbp+var_28]
0x18000552b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180005530  test    al, al
0x180005532  jnz     short loc_18000553F
0x180005534  mov     r9d, 7Ah ; 'z'
0x18000553a  jmp     loc_1800056CC
0x18000553f  xor     edx, edx; hFile
0x180005541  lea     rcx, aPhoneservicere; "PhoneServiceRes.dll"
0x180005548  lea     r8d, [rdx+2]; dwFlags
0x18000554c  call    cs:__imp_LoadLibraryExW
0x180005552  mov     rbx, rax
0x180005555  test    rax, rax
0x180005558  jnz     short loc_1800055B5
0x18000555a  call    cs:__imp_GetLastError
0x180005560  mov     ebx, eax
0x180005562  test    eax, eax
0x180005564  jle     short loc_18000556F
0x180005566  movzx   ebx, ax
0x180005569  or      ebx, 80070000h
0x18000556f  xor     edx, edx
0x180005571  lea     r9d, [rdx+7Ch]
0x180005575  mov     ecx, ebx
0x180005577  call    Log_HREvent
0x18000557c  mov     rcx, [rbp+Block]; Block
0x180005580  lea     rax, [rbp+var_38]
0x180005584  cmp     rcx, rax
0x180005587  jz      short loc_180005595
0x180005589  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180005590  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005595  mov     rcx, [rbp+var_28]; Block
0x180005599  lea     rax, [rbp+var_18]
0x18000559d  cmp     rcx, rax
0x1800055a0  jz      short loc_1800055AE
0x1800055a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800055a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800055ae  mov     eax, ebx
0x1800055b0  jmp     loc_180005745
0x1800055b5  xor     r9d, r9d; cchBufferMax
0x1800055b8  mov     qword ptr [rbp+Buffer], 0
0x1800055c0  lea     r8, [rbp+Buffer]; lpBuffer
0x1800055c4  mov     edx, 2758h; uID
0x1800055c9  mov     rcx, rbx; hInstance
0x1800055cc  call    cs:__imp_LoadStringW
0x1800055d2  test    eax, eax
0x1800055d4  jnz     short loc_1800055DD
0x1800055d6  call    Log_AssertionEvent_0
0x1800055db  int     2Ch; Windows NT - assertion failure
0x1800055dd  mov     rdx, qword ptr [rbp+Buffer]
0x1800055e1  lea     rcx, [rbp+Block]
0x1800055e5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800055ea  test    al, al
0x1800055ec  jnz     short loc_18000560E
0x1800055ee  xor     edx, edx
0x1800055f0  mov     ecx, 8007000Eh
0x1800055f5  mov     r9d, 80h
0x1800055fb  call    Log_HREvent
0x180005600  mov     rcx, rbx; hLibModule
0x180005603  call    cs:__imp_FreeLibrary
0x180005609  jmp     loc_1800056D8
0x18000560e  mov     rcx, rbx; hLibModule
0x180005611  call    cs:__imp_FreeLibrary
0x180005617  mov     r8, [rbp+Block]
0x18000561b  mov     r9, rsi
0x18000561e  mov     rdx, [rbp+var_28]
0x180005622  mov     rcx, rdi
0x180005625  call    ?_FormatIncomingCallToastXml@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG0PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_FormatIncomingCallToastXml(ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000562a  mov     ebx, eax
0x18000562c  test    eax, eax
0x18000562e  jns     loc_180005711
0x180005634  mov     edx, 1
0x180005639  mov     r9d, 8Ah
0x18000563f  jmp     loc_180005575
0x180005644  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000564b  lea     r8, [rbp+Buffer]; lpBuffer
0x18000564f  xor     r9d, r9d; cchBufferMax
0x180005652  mov     qword ptr [rbp+Buffer], rax
0x180005656  mov     edx, 271Ch; uID
0x18000565b  call    cs:__imp_LoadStringW
0x180005661  test    eax, eax
0x180005663  jnz     short loc_18000566C
0x180005665  call    Log_AssertionEvent_0
0x18000566a  int     2Ch; Windows NT - assertion failure
0x18000566c  mov     rdx, qword ptr [rbp+Buffer]
0x180005670  lea     rcx, [rbp+var_28]
0x180005674  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180005679  test    al, al
0x18000567b  jnz     short loc_180005685
0x18000567d  mov     r9d, 74h ; 't'
0x180005683  jmp     short loc_1800056CC
0x180005685  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000568c  lea     r8, [rbp+Buffer]; lpBuffer
0x180005690  xor     r9d, r9d; cchBufferMax
0x180005693  mov     qword ptr [rbp+Buffer], 0
0x18000569b  mov     edx, 271Dh; uID
0x1800056a0  call    cs:__imp_LoadStringW
0x1800056a6  test    eax, eax
0x1800056a8  jnz     short loc_1800056B1
0x1800056aa  call    Log_AssertionEvent_0
0x1800056af  int     2Ch; Windows NT - assertion failure
0x1800056b1  mov     rdx, qword ptr [rbp+Buffer]
0x1800056b5  lea     rcx, [rbp+Block]
0x1800056b9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800056be  test    al, al
0x1800056c0  jnz     loc_180005617
0x1800056c6  mov     r9d, 75h ; 'u'
0x1800056cc  xor     edx, edx
0x1800056ce  mov     ecx, 8007000Eh
0x1800056d3  call    Log_HREvent
0x1800056d8  mov     rcx, [rbp+Block]; Block
0x1800056dc  lea     rax, [rbp+var_38]
0x1800056e0  cmp     rcx, rax
0x1800056e3  jz      short loc_1800056F1
0x1800056e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800056ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056f1  mov     rcx, [rbp+var_28]; Block
0x1800056f5  lea     rax, [rbp+var_18]
0x1800056f9  cmp     rcx, rax
0x1800056fc  jz      short loc_18000570A
0x1800056fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180005705  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000570a  mov     eax, 8007000Eh
0x18000570f  jmp     short loc_180005745
0x180005711  mov     rcx, [rbp+Block]; Block
0x180005715  lea     rax, [rbp+var_38]
0x180005719  cmp     rcx, rax
0x18000571c  jz      short loc_18000572A
0x18000571e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180005725  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000572a  mov     rcx, [rbp+var_28]; Block
0x18000572e  lea     rax, [rbp+var_18]
0x180005732  cmp     rcx, rax
0x180005735  jz      short loc_180005743
0x180005737  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000573e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005743  xor     eax, eax
0x180005745  mov     rcx, [rbp+var_8]
0x180005749  xor     rcx, rsp; StackCookie
0x18000574c  call    __security_check_cookie
0x180005751  mov     rbx, [rsp+80h+arg_10]
0x180005759  add     rsp, 80h
0x180005760  pop     rdi
0x180005761  pop     rsi
0x180005762  pop     rbp
0x180005763  retn
```
