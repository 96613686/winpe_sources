# WinMain

- ea: `0x1403e75dc`
- end: `0x1403e7c1a`
- name: `WinMain`
- size: `1598`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1403e14dc`

## callees

- `0x14001e1cc`
- `0x140021ab8`
- `0x140045380`
- `0x140057bb0`
- `0x1400a16b0`
- `0x140141978`
- `0x1401687e8`
- `0x140193970`
- `0x1401a2f7c`
- `0x1401eae6c`
- `0x1402a10a8`
- `0x1402a1404`
- `0x14031a914`
- `0x14031aa48`
- `0x140394c14`
- `0x1403bc590`
- `0x1403d3320`
- `0x1403d3a98`
- `0x1403e1680`
- `0x1403e75dc`
- `0x1403f1828`
- `0x1407b0e20`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1403e765c`
- `KERNEL32!GetTickCount` at `0x1403e76e7`
- `KERNEL32!GetTickCount` at `0x1403e7706`
- `KERNEL32!GetTickCount` at `0x1403e765c`
- `KERNEL32!GetTickCount` at `0x1403e76e7`
- `KERNEL32!GetTickCount` at `0x1403e7706`
- `KERNEL32!GetModuleHandleW` at `0x1403e761e`
- `KERNEL32!GetModuleHandleW` at `0x1403e761e`
- `KERNEL32!GetProcAddress` at `0x1403e7638`
- `KERNEL32!GetProcAddress` at `0x1403e7638`
- `ole32!CoInitializeSecurity` at `0x1403e76b5`
- `ole32!CoInitializeSecurity` at `0x1403e76b5`
- `ole32!CoUninitialize` at `0x1403e7783`
- `ole32!CoUninitialize` at `0x1403e7bdb`
- `ole32!CoUninitialize` at `0x1403e7783`
- `ole32!CoUninitialize` at `0x1403e7bdb`

## string_xrefs

- `0x1403e7617`: `Kernel32.dll`
- `0x1403e762e`: `SetDefaultDllDirectories`
- `0x1403e7742`: `Startup complete. {'LibletsTimeSpent':'%d','LoggingTimeSpent':'%d','TimeSpent':'%d'}`
- `0x1403e77c5`: `Failed to call CoInitializeSecurity`
- `0x1403e7a26`: `/service`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  HMODULE ModuleHandleW; // rax
  int v5; // edi
  FARPROC ProcAddress; // rax
  DWORD TickCount; // r12d
  HRESULT v8; // r15d
  DWORD v9; // esi
  LPSTR v10; // r14
  DWORD v11; // eax
  void **v13; // rax
  int v14; // edx
  _QWORD *v15; // rax
  char v16; // di
  char v17; // si
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  __int64 (__fastcall ***v20)(_QWORD, LPSTR); // rcx
  unsigned int v21; // edi
  int v22; // r9d
  int v23; // [rsp+50h] [rbp-298h] BYREF
  void ***v24; // [rsp+58h] [rbp-290h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-288h]
  char v26; // [rsp+68h] [rbp-280h] BYREF
  void **v27; // [rsp+70h] [rbp-278h] BYREF
  void ****v28; // [rsp+78h] [rbp-270h]
  char *v29; // [rsp+80h] [rbp-268h]
  LPSTR v30; // [rsp+88h] [rbp-260h] BYREF
  DWORD v31; // [rsp+90h] [rbp-258h] BYREF
  int v32; // [rsp+98h] [rbp-250h] BYREF
  char v33; // [rsp+9Ch] [rbp-24Ch]
  int v34; // [rsp+A0h] [rbp-248h]
  _BYTE v35[40]; // [rsp+A8h] [rbp-240h] BYREF
  void **v36; // [rsp+D0h] [rbp-218h] BYREF
  __int128 v37; // [rsp+D8h] [rbp-210h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-200h]
  _QWORD v39[3]; // [rsp+F8h] [rbp-1F0h] BYREF
  __int16 v40; // [rsp+110h] [rbp-1D8h]
  WCHAR v41[64]; // [rsp+118h] [rbp-1D0h] BYREF
  WCHAR String1[20]; // [rsp+198h] [rbp-150h] BYREF
  _QWORD v43[10]; // [rsp+1C0h] [rbp-128h] BYREF
  _QWORD v44[22]; // [rsp+210h] [rbp-D8h] BYREF

  v30 = lpCmdLine;
  v23 = 0;
  ModuleHandleW = GetModuleHandleW(L"Kernel32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
    if ( ProcAddress )
      v5 = ((unsigned int (__fastcall *)(__int64))ProcAddress)(2048) == 0 ? 3 : 0;
    else
      v5 = 2;
  }
  else
  {
    v5 = 1;
  }
  TickCount = GetTickCount();
  v32 = 66;
  v33 = 0;
  v34 = 2;
  sub_1400A16B0(&v32);
  v8 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  LODWORD(v24) = v8;
  sub_1403D3320(&v30);
  dword_140BE1C68 = 37;
  sub_14031AA48(v35);
  v9 = GetTickCount();
  v10 = v30;
  sub_1401A2F7C((__int64)v30);
  sub_1403BC590(v5);
  v11 = GetTickCount();
  v23 = v11 - TickCount;
  v31 = v11 - v9;
  LODWORD(v30) = v9 - TickCount;
  sub_140394C14(
    v44,
    L"Startup complete. {'LibletsTimeSpent':'%d','LoggingTimeSpent':'%d','TimeSpent':'%d'}",
    &v30,
    &v31,
    &v23);
  if ( (unsigned __int8)sub_1403D3A98() )
  {
    if ( v8 < 0 )
    {
      v13 = (void **)sub_1402A10A8(String1, L"%x", &v24);
      if ( (unsigned __int64)v13[3] > 7 )
        v13 = (void **)*v13;
      v24 = (void ***)v13;
      sub_140021AB8((__int64)v41, L"Failed to call CoInitializeSecurity");
      sub_1401EAE6C((unsigned int)v43, v14, (unsigned int)v41, (unsigned int)L"HResult", (__int64)&v24);
      v43[0] = &C2R::ContextData::`vftable';
      v36 = &C2R::CommonTelemetry::`vftable';
      v37 = 0;
      si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
      LOWORD(v37) = 0;
      if ( sub_140057BB0(50631104, 0x3B0u, 0xFu, 0) )
      {
        v24 = &v36;
        v25 = v43;
        v27 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v28 = &v24;
        v29 = &v26;
        sub_140141978(50631104, 944, 15, 0, (__int64)L"wWinMain", (__int64)&v27);
      }
      sub_140045380(&v37);
      sub_140193970(v43);
      sub_140045380(v41);
      sub_140045380(String1);
    }
    v15 = v44;
    if ( v44[3] > 7u )
      v15 = (_QWORD *)v44[0];
    v39[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v39[1] = L"ContextData";
    v39[2] = v15;
    v40 = 0;
    v36 = &C2R::CommonTelemetry::`vftable';
    v37 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
    LOWORD(v37) = 0;
    if ( sub_140057BB0(17920196, 0x3B0u, 0x32u, 0) )
    {
      v24 = &v36;
      v25 = v39;
      v27 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v28 = &v24;
      v29 = &v26;
      sub_140141978(17920196, 944, 50, 0, (__int64)L"::wWinMain", (__int64)&v27);
    }
    sub_140045380(&v37);
    sub_140021AB8((__int64)String1, v10);
    v16 = 1;
    v23 = 1;
    if ( !(unsigned int)sub_1401687E8(String1, L"/service")
      || (sub_140021AB8((__int64)v41, v10),
          v16 = 3,
          v23 = 3,
          v17 = 0,
          !(unsigned int)sub_1401687E8(v41, L"/containersystem")) )
    {
      v17 = 1;
    }
    if ( (v16 & 2) != 0 )
    {
      v16 &= ~2u;
      sub_140045380(v41);
    }
    if ( (v16 & 1) != 0 )
      sub_140045380(String1);
    if ( v17 )
    {
      v18 = sub_14001E1CC(8u);
      if ( v18 )
        *v18 = &ServiceStartupBehavior::`vftable';
      else
        v18 = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD *, LPSTR))*v18)(v18, v10);
    }
    else
    {
      sub_140021AB8((__int64)v41, L"started");
      sub_1403F1828(v41, 0);
      sub_140045380(v41);
      v19 = sub_14001E1CC(0x18u);
      v20 = (__int64 (__fastcall ***)(_QWORD, LPSTR))v19;
      if ( v19 )
      {
        v19[2] = 147;
        v19[1] = 0;
        *v19 = &ClickToRunStartupBehavior::`vftable';
      }
      else
      {
        v20 = 0;
      }
      v21 = (**v20)(v20, v10);
      v23 = v21;
      sub_140021AB8((__int64)v41, L"ended");
      sub_1403F1828(v41, v21);
      sub_140045380(v41);
      sub_1402A1404(4273097, 14, 50, v22, (__int64)L"Main: returned: %d", &v23);
    }
    sub_140045380(v44);
    sub_14031A914(v35);
    if ( v33 )
      CoUninitialize();
    return v23;
  }
  else
  {
    sub_140045380(v44);
    sub_14031A914(v35);
    if ( v33 )
      CoUninitialize();
    return 17000;
  }
}

```

## disassembly

```asm
0x1403e75dc  mov     r11, rsp
0x1403e75df  mov     [r11+8], rbx
0x1403e75e3  mov     [r11+10h], rsi
0x1403e75e7  mov     [r11+20h], rdi
0x1403e75eb  push    r12
0x1403e75ed  push    r14
0x1403e75ef  push    r15
0x1403e75f1  sub     rsp, 2D0h
0x1403e75f8  mov     rax, cs:__security_cookie
0x1403e75ff  xor     rax, rsp
0x1403e7602  mov     [rsp+2E8h+var_28], rax
0x1403e760a  mov     [r11-260h], r8
0x1403e7611  xor     ebx, ebx
0x1403e7613  mov     [rsp+2E8h+var_298], ebx
0x1403e7617  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x1403e761e  call    cs:GetModuleHandleW
0x1403e7624  test    rax, rax
0x1403e7627  jnz     short loc_1403E762E
0x1403e7629  lea     edi, [rbx+1]
0x1403e762c  jmp     short loc_1403E765C
0x1403e762e  lea     rdx, aSetdefaultdlld; "SetDefaultDllDirectories"
0x1403e7635  mov     rcx, rax; hModule
0x1403e7638  call    cs:__imp_GetProcAddress
0x1403e763e  test    rax, rax
0x1403e7641  jnz     short loc_1403E7648
0x1403e7643  lea     edi, [rax+2]
0x1403e7646  jmp     short loc_1403E765C
0x1403e7648  mov     ecx, 800h
0x1403e764d  call    cs:__guard_dispatch_icall_fptr
0x1403e7653  neg     eax
0x1403e7655  sbb     edi, edi
0x1403e7657  not     edi
0x1403e7659  and     edi, 3
0x1403e765c  call    cs:__imp_GetTickCount
0x1403e7662  mov     r12d, eax
0x1403e7665  mov     [rsp+2E8h+var_250], 42h ; 'B'
0x1403e7670  mov     [rsp+2E8h+var_24C], bl
0x1403e7677  mov     [rsp+2E8h+var_248], 2
0x1403e7682  lea     rcx, [rsp+2E8h+var_250]
0x1403e768a  call    sub_1400A16B0
0x1403e768f  nop
0x1403e7690  mov     [rsp+2E8h+pReserved3], rbx; pReserved3
0x1403e7695  mov     [rsp+2E8h+dwCapabilities], ebx; dwCapabilities
0x1403e7699  mov     [rsp+2E8h+pAuthList], rbx; pAuthList
0x1403e769e  mov     [rsp+2E8h+dwImpLevel], 3; dwImpLevel
0x1403e76a6  mov     [rsp+2E8h+dwAuthnLevel], ebx; dwAuthnLevel
0x1403e76aa  xor     r9d, r9d; pReserved1
0x1403e76ad  xor     r8d, r8d; asAuthSvc
0x1403e76b0  or      edx, 0FFFFFFFFh; cAuthSvc
0x1403e76b3  xor     ecx, ecx; pSecDesc
0x1403e76b5  call    cs:CoInitializeSecurity
0x1403e76bb  mov     r15d, eax
0x1403e76be  mov     dword ptr [rsp+2E8h+var_290], eax
0x1403e76c2  lea     rcx, [rsp+2E8h+var_260]
0x1403e76ca  call    sub_1403D3320
0x1403e76cf  mov     cs:dword_140BE1C68, 25h ; '%'
0x1403e76d9  lea     rcx, [rsp+2E8h+var_240]
0x1403e76e1  call    sub_14031AA48
0x1403e76e6  nop
0x1403e76e7  call    cs:__imp_GetTickCount
0x1403e76ed  mov     esi, eax
0x1403e76ef  mov     r14, [rsp+2E8h+var_260]
0x1403e76f7  mov     rcx, r14
0x1403e76fa  call    sub_1401A2F7C
0x1403e76ff  mov     ecx, edi
0x1403e7701  call    sub_1403BC590
0x1403e7706  call    cs:__imp_GetTickCount
0x1403e770c  mov     ecx, eax
0x1403e770e  sub     ecx, r12d
0x1403e7711  mov     [rsp+2E8h+var_298], ecx
0x1403e7715  sub     eax, esi
0x1403e7717  mov     [rsp+2E8h+var_258], eax
0x1403e771e  sub     esi, r12d
0x1403e7721  mov     dword ptr [rsp+2E8h+var_260], esi
0x1403e7728  lea     rax, [rsp+2E8h+var_298]
0x1403e772d  mov     qword ptr [rsp+2E8h+dwAuthnLevel], rax
0x1403e7732  lea     r9, [rsp+2E8h+var_258]
0x1403e773a  lea     r8, [rsp+2E8h+var_260]
0x1403e7742  lea     rdx, aStartupComplet; "Startup complete. {'LibletsTimeSpent':'"...
0x1403e7749  lea     rcx, [rsp+2E8h+var_D8]
0x1403e7751  call    sub_140394C14
0x1403e7756  nop
0x1403e7757  call    sub_1403D3A98
0x1403e775c  test    al, al
0x1403e775e  jnz     short loc_1403E7793
0x1403e7760  lea     rcx, [rsp+2E8h+var_D8]; void *
0x1403e7768  call    sub_140045380
0x1403e776d  lea     rcx, [rsp+2E8h+var_240]
0x1403e7775  call    sub_14031A914
0x1403e777a  cmp     [rsp+2E8h+var_24C], bl
0x1403e7781  jz      short loc_1403E7789
0x1403e7783  call    cs:__imp_CoUninitialize
0x1403e7789  mov     eax, 4268h
0x1403e778e  jmp     loc_1403E7BEC
0x1403e7793  test    r15d, r15d
0x1403e7796  jns     loc_1403E78FC
0x1403e779c  lea     r8, [rsp+2E8h+var_290]
0x1403e77a1  lea     rdx, asc_14095E64C; "%x"
0x1403e77a8  lea     rcx, [rsp+2E8h+String1]
0x1403e77b0  call    sub_1402A10A8
0x1403e77b5  nop
0x1403e77b6  cmp     qword ptr [rax+18h], 7
0x1403e77bb  jbe     short loc_1403E77C0
0x1403e77bd  mov     rax, [rax]
0x1403e77c0  mov     [rsp+2E8h+var_290], rax
0x1403e77c5  lea     rdx, aFailedToCallCo; "Failed to call CoInitializeSecurity"
0x1403e77cc  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e77d4  call    sub_140021AB8
0x1403e77d9  lea     rax, [rsp+2E8h+var_290]
0x1403e77de  mov     qword ptr [rsp+2E8h+dwAuthnLevel], rax
0x1403e77e3  lea     r9, aHresult; "HResult"
0x1403e77ea  lea     r8, [rsp+2E8h+var_1D0]
0x1403e77f2  lea     rcx, [rsp+2E8h+var_128]
0x1403e77fa  call    sub_1401EAE6C
0x1403e77ff  lea     rax, ??_7ContextData@C2R@@6B@; const C2R::ContextData::`vftable'
0x1403e7806  mov     [rsp+2E8h+var_128], rax
0x1403e780e  lea     r15, ??_7CommonTelemetry@C2R@@6B@; const C2R::CommonTelemetry::`vftable'
0x1403e7815  mov     [rsp+2E8h+var_218], r15
0x1403e781d  xorps   xmm0, xmm0
0x1403e7820  movups  [rsp+2E8h+var_210], xmm0
0x1403e7828  movdqa  xmm1, cs:xmmword_14082E430
0x1403e7830  movdqu  [rsp+2E8h+var_200], xmm1
0x1403e7839  mov     word ptr [rsp+2E8h+var_210], bx
0x1403e7841  xor     r9d, r9d
0x1403e7844  lea     r12d, [r9+0Fh]
0x1403e7848  mov     r8d, r12d
0x1403e784b  mov     esi, 3B0h
0x1403e7850  mov     edx, esi
0x1403e7852  mov     ecx, 30491C0h
0x1403e7857  call    sub_140057BB0
0x1403e785c  lea     rdi, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1403e7863  test    al, al
0x1403e7865  jz      short loc_1403E78C5
0x1403e7867  lea     rax, [rsp+2E8h+var_218]
0x1403e786f  mov     [rsp+2E8h+var_290], rax
0x1403e7874  lea     rax, [rsp+2E8h+var_128]
0x1403e787c  mov     [rsp+2E8h+var_288], rax
0x1403e7881  mov     [rsp+2E8h+var_278], rdi
0x1403e7886  lea     rax, [rsp+2E8h+var_290]
0x1403e788b  mov     [rsp+2E8h+var_270], rax
0x1403e7890  lea     rax, [rsp+2E8h+var_280]
0x1403e7895  mov     [rsp+2E8h+var_268], rax
0x1403e789d  xor     r9d, r9d
0x1403e78a0  lea     rax, [rsp+2E8h+var_278]
0x1403e78a5  mov     qword ptr [rsp+2E8h+dwImpLevel], rax
0x1403e78aa  lea     rax, aWwinmain; "wWinMain"
0x1403e78b1  mov     qword ptr [rsp+2E8h+dwAuthnLevel], rax
0x1403e78b6  mov     r8d, r12d
0x1403e78b9  mov     edx, esi
0x1403e78bb  mov     ecx, 30491C0h
0x1403e78c0  call    sub_140141978
0x1403e78c5  lea     rcx, [rsp+2E8h+var_210]; void *
0x1403e78cd  call    sub_140045380
0x1403e78d2  lea     rcx, [rsp+2E8h+var_128]
0x1403e78da  call    sub_140193970
0x1403e78df  lea     rcx, [rsp+2E8h+var_1D0]; void *
0x1403e78e7  call    sub_140045380
0x1403e78ec  nop
0x1403e78ed  lea     rcx, [rsp+2E8h+String1]; void *
0x1403e78f5  call    sub_140045380
0x1403e78fa  jmp     short loc_1403E790F
0x1403e78fc  lea     r15, ??_7CommonTelemetry@C2R@@6B@; const C2R::CommonTelemetry::`vftable'
0x1403e7903  mov     esi, 3B0h
0x1403e7908  lea     rdi, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1403e790f  lea     rax, [rsp+2E8h+var_D8]
0x1403e7917  cmp     [rsp+2E8h+var_C0], 7
0x1403e7920  cmova   rax, [rsp+2E8h+var_D8]
0x1403e7929  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x1403e7930  mov     [rsp+2E8h+var_1F0], rcx
0x1403e7938  lea     rcx, aContextdata; "ContextData"
0x1403e793f  mov     [rsp+2E8h+var_1E8], rcx
0x1403e7947  mov     [rsp+2E8h+var_1E0], rax
0x1403e794f  mov     [rsp+2E8h+var_1D8], bx
0x1403e7957  mov     [rsp+2E8h+var_218], r15
0x1403e795f  xorps   xmm0, xmm0
0x1403e7962  movups  [rsp+2E8h+var_210], xmm0
0x1403e796a  movdqa  xmm1, cs:xmmword_14082E430
0x1403e7972  movdqu  [rsp+2E8h+var_200], xmm1
0x1403e797b  mov     word ptr [rsp+2E8h+var_210], bx
0x1403e7983  xor     r9d, r9d
0x1403e7986  lea     r12d, [r9+32h]
0x1403e798a  mov     r8d, r12d
0x1403e798d  mov     edx, esi
0x1403e798f  mov     r15d, 11170C4h
0x1403e7995  mov     ecx, r15d
0x1403e7998  call    sub_140057BB0
0x1403e799d  test    al, al
0x1403e799f  jz      short loc_1403E79FD
0x1403e79a1  lea     rax, [rsp+2E8h+var_218]
0x1403e79a9  mov     [rsp+2E8h+var_290], rax
0x1403e79ae  lea     rax, [rsp+2E8h+var_1F0]
0x1403e79b6  mov     [rsp+2E8h+var_288], rax
0x1403e79bb  mov     [rsp+2E8h+var_278], rdi
0x1403e79c0  lea     rax, [rsp+2E8h+var_290]
0x1403e79c5  mov     [rsp+2E8h+var_270], rax
0x1403e79ca  lea     rax, [rsp+2E8h+var_280]
0x1403e79cf  mov     [rsp+2E8h+var_268], rax
0x1403e79d7  xor     r9d, r9d
0x1403e79da  lea     rax, [rsp+2E8h+var_278]
0x1403e79df  mov     qword ptr [rsp+2E8h+dwImpLevel], rax
0x1403e79e4  lea     rax, aWwinmain_0; "::wWinMain"
0x1403e79eb  mov     qword ptr [rsp+2E8h+dwAuthnLevel], rax
0x1403e79f0  mov     r8d, r12d
0x1403e79f3  mov     edx, esi
0x1403e79f5  mov     ecx, r15d
0x1403e79f8  call    sub_140141978
0x1403e79fd  lea     rcx, [rsp+2E8h+var_210]; void *
0x1403e7a05  call    sub_140045380
0x1403e7a0a  mov     rdx, r14
0x1403e7a0d  lea     rcx, [rsp+2E8h+String1]
0x1403e7a15  call    sub_140021AB8
0x1403e7a1a  mov     edi, 1
0x1403e7a1f  mov     [rsp+2E8h+var_298], edi
0x1403e7a23  mov     r8b, dil
0x1403e7a26  lea     rdx, aService; "/service"
0x1403e7a2d  lea     rcx, [rsp+2E8h+String1]; lpString1
0x1403e7a35  call    sub_1401687E8
0x1403e7a3a  test    eax, eax
0x1403e7a3c  jz      short loc_1403E7A76
0x1403e7a3e  mov     rdx, r14
0x1403e7a41  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e7a49  call    sub_140021AB8
0x1403e7a4e  nop
0x1403e7a4f  mov     edi, 3
0x1403e7a54  mov     [rsp+2E8h+var_298], edi
0x1403e7a58  mov     r8b, 1
0x1403e7a5b  lea     rdx, aContainersyste_0; "/containersystem"
0x1403e7a62  lea     rcx, [rsp+2E8h+var_1D0]; lpString1
0x1403e7a6a  call    sub_1401687E8
0x1403e7a6f  test    eax, eax
0x1403e7a71  mov     sil, bl
0x1403e7a74  jnz     short loc_1403E7A79
0x1403e7a76  mov     sil, 1
0x1403e7a79  test    dil, 2
0x1403e7a7d  jz      short loc_1403E7A90
0x1403e7a7f  and     edi, 0FFFFFFFDh
0x1403e7a82  lea     rcx, [rsp+2E8h+var_1D0]; void *
0x1403e7a8a  call    sub_140045380
0x1403e7a8f  nop
0x1403e7a90  test    dil, 1
0x1403e7a94  jz      short loc_1403E7AA3
0x1403e7a96  lea     rcx, [rsp+2E8h+String1]; void *
0x1403e7a9e  call    sub_140045380
0x1403e7aa3  test    sil, sil
0x1403e7aa6  jz      short loc_1403E7AE1
0x1403e7aa8  mov     ecx, 8
0x1403e7aad  call    sub_14001E1CC
0x1403e7ab2  mov     rcx, rax
0x1403e7ab5  test    rax, rax
0x1403e7ab8  jz      short loc_1403E7AC6
0x1403e7aba  lea     rax, ??_7ServiceStartupBehavior@@6B@; const ServiceStartupBehavior::`vftable'
0x1403e7ac1  mov     [rcx], rax
0x1403e7ac4  jmp     short loc_1403E7AC9
0x1403e7ac6  mov     rcx, rbx
0x1403e7ac9  mov     rax, [rcx]
0x1403e7acc  mov     rdx, r14
0x1403e7acf  mov     rax, [rax]
0x1403e7ad2  call    cs:__guard_dispatch_icall_fptr
0x1403e7ad8  mov     [rsp+2E8h+var_298], eax
0x1403e7adc  jmp     loc_1403E7BB0
0x1403e7ae1  lea     rdx, aStarted; "started"
0x1403e7ae8  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e7af0  call    sub_140021AB8
0x1403e7af5  nop
0x1403e7af6  xor     edx, edx
0x1403e7af8  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e7b00  call    sub_1403F1828
0x1403e7b05  nop
0x1403e7b06  lea     rcx, [rsp+2E8h+var_1D0]; void *
0x1403e7b0e  call    sub_140045380
0x1403e7b13  mov     ecx, 18h
0x1403e7b18  call    sub_14001E1CC
0x1403e7b1d  mov     rcx, rax
0x1403e7b20  test    rax, rax
0x1403e7b23  jz      short loc_1403E7B3D
0x1403e7b25  mov     qword ptr [rax+10h], 93h
0x1403e7b2d  mov     [rax+8], rbx
0x1403e7b31  lea     rax, ??_7ClickToRunStartupBehavior@@6B@; const ClickToRunStartupBehavior::`vftable'
0x1403e7b38  mov     [rcx], rax
0x1403e7b3b  jmp     short loc_1403E7B40
0x1403e7b3d  mov     rcx, rbx
0x1403e7b40  mov     rax, [rcx]
0x1403e7b43  mov     rdx, r14
0x1403e7b46  mov     rax, [rax]
0x1403e7b49  call    cs:__guard_dispatch_icall_fptr
0x1403e7b4f  mov     edi, eax
0x1403e7b51  mov     [rsp+2E8h+var_298], eax
0x1403e7b55  lea     rdx, aEnded; "ended"
0x1403e7b5c  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e7b64  call    sub_140021AB8
0x1403e7b69  nop
0x1403e7b6a  mov     edx, edi
0x1403e7b6c  lea     rcx, [rsp+2E8h+var_1D0]
0x1403e7b74  call    sub_1403F1828
0x1403e7b79  nop
0x1403e7b7a  lea     rcx, [rsp+2E8h+var_1D0]; void *
0x1403e7b82  call    sub_140045380
0x1403e7b87  lea     rax, [rsp+2E8h+var_298]
0x1403e7b8c  mov     qword ptr [rsp+2E8h+dwImpLevel], rax
0x1403e7b91  lea     rax, aMainReturnedD; "Main: returned: %d"
  ... truncated ...
```
