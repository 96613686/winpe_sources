# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800088fc`
- end: `0x180008c13`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800088b0`
- `0x1800088d0`
- `0x180008f60`

## callees

- `0x180002218`
- `0x180005368`
- `0x1800056c8`
- `0x18000626c`
- `0x180006f6c`
- `0x180007a88`
- `0x1800088fc`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008ace`
- `msvcrt!memcpy_s` at `0x180008ace`
- `KERNEL32!GetModuleHandleW` at `0x180008a76`
- `KERNEL32!GetModuleHandleW` at `0x180008a76`
- `KERNEL32!LeaveCriticalSection` at `0x1800089b8`
- `KERNEL32!LeaveCriticalSection` at `0x180008b40`
- `KERNEL32!LeaveCriticalSection` at `0x180008b7e`
- `KERNEL32!LeaveCriticalSection` at `0x1800089b8`
- `KERNEL32!LeaveCriticalSection` at `0x180008b40`
- `KERNEL32!LeaveCriticalSection` at `0x180008b7e`
- `KERNEL32!EnterCriticalSection` at `0x18000899d`
- `KERNEL32!EnterCriticalSection` at `0x180008a86`
- `KERNEL32!EnterCriticalSection` at `0x180008b1b`
- `KERNEL32!EnterCriticalSection` at `0x180008b5c`
- `KERNEL32!EnterCriticalSection` at `0x18000899d`
- `KERNEL32!EnterCriticalSection` at `0x180008a86`
- `KERNEL32!EnterCriticalSection` at `0x180008b1b`
- `KERNEL32!EnterCriticalSection` at `0x180008b5c`
- `KERNEL32!GetModuleFileNameW` at `0x180008a01`
- `KERNEL32!GetModuleFileNameW` at `0x180008a01`

## string_xrefs

- `0x180008ba0`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  int v22; // ebx
  int v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 Source[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v26[0] = 0;
  v26[1] = 0;
  v25 = &ATL::CRegObject::`vftable';
  v27 = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v29 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v9 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_33;
      }
      v15 = Filename;
      v16 = 0;
      do
      {
        v17 = *v15;
        if ( !*v15 )
          break;
        Source[v16] = v17;
        if ( v17 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Source[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Source[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v19 = -1;
        v32 = 34;
        v20 = -1;
        do
          ++v20;
        while ( Source[v20] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v20 + 1)) )
        {
          v11 = -2147467259;
          goto LABEL_33;
        }
        do
          ++v19;
        while ( *(_WORD *)&Destination[2 * v19 - 2] );
        v21 = 2LL * (int)v19 + 2;
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        if ( v21 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v21 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v18 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = Source;
      }
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = v22 == 0 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_33:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v25,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  a3 != 0);
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v11 = Error;
    goto LABEL_33;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800088fc  mov     [rsp-8+arg_10], rbx
0x180008901  push    rbp
0x180008902  push    rsi
0x180008903  push    rdi
0x180008904  push    r12
0x180008906  push    r13
0x180008908  push    r14
0x18000890a  push    r15
0x18000890c  lea     rbp, [rsp-9D0h]
0x180008914  sub     rsp, 0AD0h
0x18000891b  mov     rax, cs:__security_cookie
0x180008922  xor     rax, rsp
0x180008925  mov     [rbp+0A00h+var_40], rax
0x18000892c  xor     r13d, r13d
0x18000892f  mov     r12d, edx
0x180008932  xorps   xmm0, xmm0
0x180008935  mov     [rsp+0B00h+var_AC8], r13
0x18000893a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008941  mov     [rsp+0B00h+var_AC0], r13
0x180008946  mov     [rsp+0B00h+var_AD0], rax
0x18000894b  mov     r14, rcx
0x18000894e  xor     eax, eax
0x180008950  mov     [rsp+0B00h+var_AB8], r13d
0x180008955  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000895a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000895f  mov     rbx, r9
0x180008962  mov     [rsp+0B00h+var_A88], r13b
0x180008967  mov     r15d, r8d
0x18000896a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000896f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180008974  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008979  mov     edi, eax
0x18000897b  test    eax, eax
0x18000897d  js      loc_180008BD7
0x180008983  mov     [rsp+0B00h+var_A88], 1
0x180008988  test    rbx, rbx
0x18000898b  jz      short loc_1800089CA
0x18000898d  jmp     short loc_1800089C2
0x18000898f  mov     rsi, [rbx+8]
0x180008993  test    rsi, rsi
0x180008996  jz      short loc_1800089BE
0x180008998  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000899d  call    cs:__imp_EnterCriticalSection
0x1800089a3  mov     r8, rsi; unsigned __int16 *
0x1800089a6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800089ab  mov     rdx, rdi; unsigned __int16 *
0x1800089ae  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800089b3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800089b8  call    cs:__imp_LeaveCriticalSection
0x1800089be  add     rbx, 10h
0x1800089c2  mov     rdi, [rbx]
0x1800089c5  test    rdi, rdi
0x1800089c8  jnz     short loc_18000898F
0x1800089ca  mov     rax, [r14]
0x1800089cd  lea     rdx, [rsp+0B00h+var_AD0]
0x1800089d2  mov     rcx, r14
0x1800089d5  mov     rax, [rax+28h]
0x1800089d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089de  mov     ebx, eax
0x1800089e0  test    eax, eax
0x1800089e2  js      loc_180008BC9
0x1800089e8  mov     rbx, cs:hInstance
0x1800089ef  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800089f6  mov     edi, 104h
0x1800089fb  mov     rcx, rbx; hModule
0x1800089fe  mov     r8d, edi; nSize
0x180008a01  call    cs:__imp_GetModuleFileNameW
0x180008a07  test    eax, eax
0x180008a09  jnz     short loc_180008A17
0x180008a0b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008a10  mov     ebx, eax
0x180008a12  jmp     loc_180008BC9
0x180008a17  cmp     eax, edi
0x180008a19  jnz     short loc_180008A25
0x180008a1b  mov     ebx, 8007007Ah
0x180008a20  jmp     loc_180008BC9
0x180008a25  lea     rdx, [rbp+0A00h+Filename]
0x180008a2c  mov     ecx, r13d
0x180008a2f  mov     r9d, 27h ; '''
0x180008a35  movzx   r8d, word ptr [rdx]
0x180008a39  test    r8w, r8w
0x180008a3d  jz      short loc_180008A69
0x180008a3f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180008a45  cmp     r8w, r9w
0x180008a49  jnz     short loc_180008A5B
0x180008a4b  cmp     ecx, 206h
0x180008a51  jnb     short loc_180008A5B
0x180008a53  inc     ecx
0x180008a55  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180008a5b  add     rdx, 2
0x180008a5f  inc     ecx
0x180008a61  cmp     ecx, 207h
0x180008a67  jb      short loc_180008A35
0x180008a69  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180008a6f  test    rbx, rbx
0x180008a72  jz      short loc_180008A95
0x180008a74  xor     ecx, ecx; lpModuleName
0x180008a76  call    cs:__imp_GetModuleHandleW
0x180008a7c  cmp     rbx, rax
0x180008a7f  jz      short loc_180008A95
0x180008a81  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008a86  call    cs:__imp_EnterCriticalSection
0x180008a8c  lea     r8, [rbp+0A00h+Source]
0x180008a90  jmp     loc_180008B28
0x180008a95  mov     edi, 22h ; '"'
0x180008a9a  lea     rcx, [rbp+0A00h+Source]
0x180008a9e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008aa2  mov     [rbp+0A00h+var_460], di
0x180008aa9  mov     rax, rbx
0x180008aac  inc     rax
0x180008aaf  cmp     [rcx+rax*2], r13w
0x180008ab4  jnz     short loc_180008AAC
0x180008ab6  inc     eax
0x180008ab8  lea     r8, [rbp+0A00h+Source]; Source
0x180008abc  movsxd  r9, eax
0x180008abf  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180008ac6  add     r9, r9; SourceSize
0x180008ac9  mov     edx, 414h; DestinationSize
0x180008ace  call    cs:__imp_memcpy_s
0x180008ad4  test    eax, eax
0x180008ad6  jnz     loc_180008BC4
0x180008adc  lea     rax, [rbp+0A00h+var_460]
0x180008ae3  inc     rbx
0x180008ae6  cmp     [rax+rbx*2], r13w
0x180008aeb  jnz     short loc_180008AE3
0x180008aed  movsxd  rax, ebx
0x180008af0  lea     rcx, ds:2[rax*2]
0x180008af8  mov     [rbp+rax*2+0A00h+var_460], di
0x180008b00  cmp     rcx, 418h
0x180008b07  jnb     loc_180008C0D
0x180008b0d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180008b16  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008b1b  call    cs:__imp_EnterCriticalSection
0x180008b21  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180008b28  lea     rdx, aModule; "Module"
0x180008b2f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180008b34  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008b39  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008b3e  mov     ebx, eax
0x180008b40  call    cs:__imp_LeaveCriticalSection
0x180008b46  neg     ebx
0x180008b48  mov     edi, 8007000Eh
0x180008b4d  sbb     ebx, ebx
0x180008b4f  not     ebx
0x180008b51  and     ebx, edi
0x180008b53  test    ebx, ebx
0x180008b55  js      short loc_180008BC9
0x180008b57  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008b5c  call    cs:__imp_EnterCriticalSection
0x180008b62  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180008b66  lea     rdx, aModuleRaw; "Module_Raw"
0x180008b6d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180008b72  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008b77  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008b7c  mov     ebx, eax
0x180008b7e  call    cs:__imp_LeaveCriticalSection
0x180008b84  mov     ecx, ebx
0x180008b86  neg     ecx
0x180008b88  sbb     eax, eax
0x180008b8a  not     eax
0x180008b8c  and     eax, edi
0x180008b8e  test    ebx, ebx
0x180008b90  jz      loc_180008A10
0x180008b96  mov     eax, r13d
0x180008b99  movzx   r8d, r12w; unsigned __int16 *
0x180008b9d  test    r15d, r15d
0x180008ba0  lea     r9, aRegistry; "REGISTRY"
0x180008ba7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180008bae  setnz   al
0x180008bb1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008bb6  mov     [rsp+0B00h+var_AE0], eax; int
0x180008bba  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008bbf  jmp     loc_180008A10
0x180008bc4  mov     ebx, 80004005h
0x180008bc9  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008bce  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008bd3  mov     eax, ebx
0x180008bd5  jmp     short loc_180008BE3
0x180008bd7  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008bdc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008be1  mov     eax, edi
0x180008be3  mov     rcx, [rbp+0A00h+var_40]
0x180008bea  xor     rcx, rsp; StackCookie
0x180008bed  call    __security_check_cookie
0x180008bf2  mov     rbx, [rsp+0B00h+arg_10]
0x180008bfa  add     rsp, 0AD0h
0x180008c01  pop     r15
0x180008c03  pop     r14
0x180008c05  pop     r13
0x180008c07  pop     r12
0x180008c09  pop     rdi
0x180008c0a  pop     rsi
0x180008c0b  pop     rbp
0x180008c0c  retn
0x180008c0d  call    __report_rangecheckfailure
```
