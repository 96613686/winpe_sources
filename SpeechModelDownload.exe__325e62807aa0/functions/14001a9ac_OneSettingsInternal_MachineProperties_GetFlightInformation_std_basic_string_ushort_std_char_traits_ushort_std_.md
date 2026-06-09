# OneSettingsInternal::MachineProperties::GetFlightInformation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,int &)

- ea: `0x14001a9ac`
- end: `0x14001ab23`
- name: `?GetFlightInformation@MachineProperties@OneSettingsInternal@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAH@Z`
- size: `375`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140017ca4`

## callees

- `0x140002600`
- `0x1400138c8`
- `0x140013a2c`
- `0x140014a98`
- `0x140015b60`
- `0x14001a9ac`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001a9ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001a9ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aaae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aaae`

## pseudocode

```c
__int64 __fastcall OneSettingsInternal::MachineProperties::GetFlightInformation(__int64 a1, _DWORD *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  char *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  __int64 v9; // rax
  LPVOID v10; // rcx
  __int16 v12; // [rsp+30h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v15[2]; // [rsp+48h] [rbp-11h] BYREF
  char *v16[4]; // [rsp+68h] [rbp+Fh] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
  v5 = v4;
  *(_QWORD *)(a1 + 16) = 0;
  if ( *(_QWORD *)(a1 + 24) <= 7u )
    v6 = (char *)a1;
  else
    v6 = *(char **)a1;
  *(_WORD *)v6 = 0;
  *a2 = 1;
  if ( v4 >= 0 )
  {
    pv = 0;
    v7 = *(_QWORD *)ppv;
    pv = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(v7 + 48))(ppv, &pv);
    if ( v5 >= 0 )
    {
      memset(v15, 0, sizeof(v15));
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)pv + v8) );
      std::wstring::_Construct<1,unsigned short const *>(v15, pv, v8);
      v9 = OneSettingsInternal::Common::trim<std::wstring>((__int64)v16, v15);
      std::wstring::operator=((char **)a1, v9);
      std::wstring::~wstring(v16);
      std::wstring::~wstring((char **)v15);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v5 >= 0 )
    {
      v12 = -1;
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 112LL))(ppv, &v12);
      if ( v5 >= 0 )
        *a2 = v12 == -1;
    }
  }
  v10 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001a9ac  mov     [rsp-8+arg_10], rbx
0x14001a9b1  push    rbp
0x14001a9b2  push    rsi
0x14001a9b3  push    rdi
0x14001a9b4  push    r14
0x14001a9b6  push    r15
0x14001a9b8  lea     rbp, [rsp-37h]
0x14001a9bd  sub     rsp, 90h
0x14001a9c4  mov     rax, cs:__security_cookie
0x14001a9cb  xor     rax, rsp
0x14001a9ce  mov     [rbp+57h+var_28], rax
0x14001a9d2  mov     rsi, rdx
0x14001a9d5  mov     rdi, rcx
0x14001a9d8  xor     r14d, r14d
0x14001a9db  mov     [rbp+57h+var_78], r14
0x14001a9df  lea     rax, [rbp+57h+var_78]
0x14001a9e3  mov     [rsp+0B0h+ppv], rax; ppv
0x14001a9e8  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x14001a9ef  lea     r15d, [r14+1]
0x14001a9f3  mov     r8d, r15d; dwClsContext
0x14001a9f6  xor     edx, edx; pUnkOuter
0x14001a9f8  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x14001a9ff  call    cs:__imp_CoCreateInstance
0x14001aa05  mov     ebx, eax
0x14001aa07  mov     [rdi+10h], r14
0x14001aa0b  cmp     qword ptr [rdi+18h], 7
0x14001aa10  jbe     short loc_14001AA17
0x14001aa12  mov     rcx, [rdi]
0x14001aa15  jmp     short loc_14001AA1A
0x14001aa17  mov     rcx, rdi
0x14001aa1a  mov     [rcx], r14w
0x14001aa1e  mov     [rsi], r15d
0x14001aa21  test    eax, eax
0x14001aa23  js      loc_14001AAE4
0x14001aa29  mov     [rbp+57h+pv], r14
0x14001aa2d  mov     rcx, [rbp+57h+var_78]
0x14001aa31  mov     rax, [rcx]
0x14001aa34  mov     [rbp+57h+pv], r14
0x14001aa38  lea     rdx, [rbp+57h+pv]
0x14001aa3c  mov     rax, [rax+30h]
0x14001aa40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa45  mov     ebx, eax
0x14001aa47  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001aa4b  test    eax, eax
0x14001aa4d  js      short loc_14001AAA5
0x14001aa4f  mov     rdx, [rbp+57h+pv]
0x14001aa53  xorps   xmm0, xmm0
0x14001aa56  movups  [rbp+57h+var_68], xmm0
0x14001aa5a  xorps   xmm1, xmm1
0x14001aa5d  movdqu  [rbp+57h+var_58], xmm1
0x14001aa62  mov     r8, r15
0x14001aa65  inc     r8
0x14001aa68  cmp     [rdx+r8*2], r14w
0x14001aa6d  jnz     short loc_14001AA65
0x14001aa6f  lea     rcx, [rbp+57h+var_68]
0x14001aa73  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001aa78  nop
0x14001aa79  lea     rdx, [rbp+57h+var_68]
0x14001aa7d  lea     rcx, [rbp+57h+var_48]
0x14001aa81  call    ??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OneSettingsInternal::Common::trim<std::wstring>(std::wstring const &)
0x14001aa86  mov     rdx, rax
0x14001aa89  mov     rcx, rdi
0x14001aa8c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001aa91  lea     rcx, [rbp+57h+var_48]
0x14001aa95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001aa9a  nop
0x14001aa9b  lea     rcx, [rbp+57h+var_68]
0x14001aa9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001aaa4  nop
0x14001aaa5  mov     rcx, [rbp+57h+pv]; pv
0x14001aaa9  test    rcx, rcx
0x14001aaac  jz      short loc_14001AAB4
0x14001aaae  call    cs:__imp_CoTaskMemFree
0x14001aab4  test    ebx, ebx
0x14001aab6  js      short loc_14001AAE4
0x14001aab8  mov     [rbp+57h+var_80], r15w
0x14001aabd  mov     rcx, [rbp+57h+var_78]
0x14001aac1  mov     rax, [rcx]
0x14001aac4  lea     rdx, [rbp+57h+var_80]
0x14001aac8  mov     rax, [rax+70h]
0x14001aacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aad1  mov     ebx, eax
0x14001aad3  test    eax, eax
0x14001aad5  js      short loc_14001AAE4
0x14001aad7  mov     eax, r14d
0x14001aada  cmp     [rbp+57h+var_80], r15w
0x14001aadf  setz    al
0x14001aae2  mov     [rsi], eax
0x14001aae4  mov     rcx, [rbp+57h+var_78]
0x14001aae8  test    rcx, rcx
0x14001aaeb  jz      short loc_14001AAFE
0x14001aaed  mov     [rbp+57h+var_78], r14
0x14001aaf1  mov     rax, [rcx]
0x14001aaf4  mov     rax, [rax+10h]
0x14001aaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aafd  nop
0x14001aafe  mov     eax, ebx
0x14001ab00  mov     rcx, [rbp+57h+var_28]
0x14001ab04  xor     rcx, rsp; StackCookie
0x14001ab07  call    __security_check_cookie
0x14001ab0c  mov     rbx, [rsp+0B0h+arg_10]
0x14001ab14  add     rsp, 90h
0x14001ab1b  pop     r15
0x14001ab1d  pop     r14
0x14001ab1f  pop     rdi
0x14001ab20  pop     rsi
0x14001ab21  pop     rbp
0x14001ab22  retn
```
