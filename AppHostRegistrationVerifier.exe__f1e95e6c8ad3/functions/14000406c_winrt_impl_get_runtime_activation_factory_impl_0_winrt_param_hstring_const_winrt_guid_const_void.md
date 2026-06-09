# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x14000406c`
- end: `0x140004332`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `710`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000400c`

## callees

- `0x140001ed0`
- `0x140002210`
- `0x140002e54`
- `0x140003073`
- `0x14000308b`
- `0x140003097`
- `0x1400030a3`
- `0x1400030d3`
- `0x140003c10`
- `0x140003cd8`
- `0x14000406c`
- `0x1400077d0`
- `0x140007be0`
- `0x140007eec`
- `0x140012010`

## string_xrefs

- `0x1400040d1`: `combase.dll`
- `0x14000422c`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  int *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rcx
  HMODULE v20; // rdi
  FARPROC v21; // rax
  bool v22; // zf
  unsigned int (__fastcall ***v24)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h]
  unsigned __int64 v28; // [rsp+48h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
    ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
    if ( ActivationFactory_0 == -2147221008 )
    {
      Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
      ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
      if ( !ProcAddress )
      {
        *a1 = -2147221008;
        return a1;
      }
      v24 = 0;
      ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v24);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v27 = 0;
      v28 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(int **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &dword_1400140E4;
        v14 = 0;
      }
      std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v28 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v27 )
          break;
        v16 = (char *)v15 + 2 * v27;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 )
          break;
        v18 = (last_trivial_2 - (__int64)v15) >> 1;
        if ( v18 == -1 )
          break;
        std::wstring::resize(lpLibFileName, v18);
        std::wstring::append(lpLibFileName, L".dll");
        v19 = (const WCHAR *)lpLibFileName;
        if ( v28 > 7 )
          v19 = lpLibFileName[0];
        v20 = LoadLibraryExW_0(v19, 0, 0x1000u);
        std::wstring::resize(lpLibFileName, v27 - 4);
        if ( v20 )
        {
          v21 = WINRT_IMPL_GetProcAddress(v20, "DllGetActivationFactory");
          if ( v21 )
          {
            v24 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v21)(
                    *a2,
                    &v24)
              && !(**v24)(v24, a3, a4) )
            {
              *a1 = 0;
              if ( v24 )
                winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v24);
              if ( v28 > 7 )
                std::_Deallocate<16>((_QWORD *)lpLibFileName[0], 2 * v28 + 2);
              v27 = 0;
              LOWORD(lpLibFileName[0]) = 0;
              v22 = pperrinfo == 0;
              goto LABEL_35;
            }
            if ( v24 )
              winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v24);
          }
          WINRT_IMPL_FreeLibrary(v20);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
      if ( v28 > 7 )
        std::_Deallocate<16>((_QWORD *)lpLibFileName[0], 2 * v28 + 2);
      v27 = 0;
      LOWORD(lpLibFileName[0]) = 0;
      v22 = pperrinfo == 0;
LABEL_35:
      v28 = 7;
      if ( !v22 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000406c  push    rbp
0x14000406e  push    rbx
0x14000406f  push    rsi
0x140004070  push    rdi
0x140004071  push    r12
0x140004073  push    r13
0x140004075  push    r14
0x140004077  push    r15
0x140004079  mov     rbp, rsp
0x14000407c  sub     rsp, 68h
0x140004080  mov     rax, cs:__security_cookie
0x140004087  xor     rax, rsp
0x14000408a  mov     [rbp+var_18], rax
0x14000408e  mov     r13, r9
0x140004091  mov     r12, r8
0x140004094  mov     r15, rdx
0x140004097  mov     rsi, rcx
0x14000409a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1400040a1  mov     r8, r9
0x1400040a4  mov     rdx, r12
0x1400040a7  mov     rcx, [r15]
0x1400040aa  test    rax, rax
0x1400040ad  jz      short loc_1400040BB
0x1400040af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040b4  mov     [rsi], eax
0x1400040b6  jmp     loc_140004312
0x1400040bb  call    RoGetActivationFactory_0
0x1400040c0  mov     ebx, eax
0x1400040c2  cmp     eax, 800401F0h
0x1400040c7  jnz     short loc_14000411D
0x1400040c9  xor     edx, edx; hFile
0x1400040cb  mov     r8d, 1000h; dwFlags
0x1400040d1  lea     rcx, LibFileName; "combase.dll"
0x1400040d8  call    LoadLibraryExW_0
0x1400040dd  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x1400040e4  mov     rcx, rax; hModule
0x1400040e7  call    WINRT_IMPL_GetProcAddress
0x1400040ec  test    rax, rax
0x1400040ef  jnz     short loc_1400040FC
0x1400040f1  mov     dword ptr [rsi], 800401F0h
0x1400040f7  jmp     loc_140004312
0x1400040fc  mov     [rbp+var_48], 0
0x140004104  lea     rcx, [rbp+var_48]
0x140004108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000410d  mov     r8, r13
0x140004110  mov     rdx, r12
0x140004113  mov     rcx, [r15]
0x140004116  call    RoGetActivationFactory_0
0x14000411b  mov     ebx, eax
0x14000411d  test    ebx, ebx
0x14000411f  jnz     short loc_140004128
0x140004121  mov     [rsi], ebx
0x140004123  jmp     loc_140004312
0x140004128  mov     [rbp+pperrinfo], 0
0x140004130  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140004134  xor     ecx, ecx; dwReserved
0x140004136  call    GetErrorInfo_0
0x14000413b  xorps   xmm0, xmm0
0x14000413e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x140004142  mov     [rbp+var_28], 0
0x14000414a  mov     [rbp+var_20], 0
0x140004152  mov     rax, [r15]
0x140004155  test    rax, rax
0x140004158  jz      short loc_140004164
0x14000415a  mov     rdx, [rax+10h]
0x14000415e  mov     r8d, [rax+4]
0x140004162  jmp     short loc_14000416E
0x140004164  lea     rdx, dword_1400140E4
0x14000416b  xor     r8d, r8d
0x14000416e  lea     rcx, [rbp+lpLibFileName]
0x140004172  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140004177  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000417b  mov     rax, [rbp+var_28]
0x14000417f  lea     r14, [rbp+lpLibFileName]
0x140004183  cmp     [rbp+var_20], 7
0x140004188  cmova   r14, [rbp+lpLibFileName]
0x14000418d  test    rax, rax
0x140004190  jz      loc_1400042C5
0x140004196  dec     rax
0x140004199  cmp     rax, rcx
0x14000419c  cmovnb  rax, rcx
0x1400041a0  inc     rax
0x1400041a3  lea     rdi, [r14+rax*2]
0x1400041a7  mov     r8d, 2Eh ; '.'
0x1400041ad  mov     rdx, rdi
0x1400041b0  mov     rcx, r14
0x1400041b3  call    __std_find_last_trivial_2
0x1400041b8  cmp     rax, rdi
0x1400041bb  jz      loc_1400042C5
0x1400041c1  sub     rax, r14
0x1400041c4  sar     rax, 1
0x1400041c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400041cb  jz      loc_1400042C5
0x1400041d1  mov     rdx, rax
0x1400041d4  lea     rcx, [rbp+lpLibFileName]
0x1400041d8  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400041dd  lea     rdx, aDll; ".dll"
0x1400041e4  lea     rcx, [rbp+lpLibFileName]
0x1400041e8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400041ed  lea     rcx, [rbp+lpLibFileName]
0x1400041f1  cmp     [rbp+var_20], 7
0x1400041f6  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1400041fb  xor     edx, edx; hFile
0x1400041fd  mov     r8d, 1000h; dwFlags
0x140004203  call    LoadLibraryExW_0
0x140004208  mov     rdi, rax
0x14000420b  mov     rdx, [rbp+var_28]
0x14000420f  add     rdx, 0FFFFFFFFFFFFFFFCh
0x140004213  lea     rcx, [rbp+lpLibFileName]
0x140004217  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14000421c  xor     r14d, r14d
0x14000421f  test    rdi, rdi
0x140004222  lea     rcx, [r14-1]
0x140004226  jz      loc_14000417B
0x14000422c  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x140004233  mov     rcx, rdi; hModule
0x140004236  call    WINRT_IMPL_GetProcAddress
0x14000423b  test    rax, rax
0x14000423e  jz      short loc_14000427C
0x140004240  mov     [rbp+var_48], r14
0x140004244  lea     rdx, [rbp+var_48]
0x140004248  mov     rcx, [r15]
0x14000424b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004250  test    eax, eax
0x140004252  jnz     short loc_14000426D
0x140004254  mov     rcx, [rbp+var_48]
0x140004258  mov     rax, [rcx]
0x14000425b  mov     r8, r13
0x14000425e  mov     rdx, r12
0x140004261  mov     rax, [rax]
0x140004264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004269  test    eax, eax
0x14000426b  jz      short loc_140004289
0x14000426d  cmp     [rbp+var_48], r14
0x140004271  jz      short loc_14000427C
0x140004273  lea     rcx, [rbp+var_48]
0x140004277  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000427c  mov     rcx, rdi; hLibModule
0x14000427f  call    WINRT_IMPL_FreeLibrary
0x140004284  jmp     loc_140004177
0x140004289  mov     [rsi], r14d
0x14000428c  cmp     [rbp+var_48], r14
0x140004290  jz      short loc_14000429B
0x140004292  lea     rcx, [rbp+var_48]
0x140004296  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000429b  mov     rdx, [rbp+var_20]
0x14000429f  cmp     rdx, 7
0x1400042a3  jbe     short loc_1400042B6
0x1400042a5  lea     rdx, ds:2[rdx*2]
0x1400042ad  mov     rcx, [rbp+lpLibFileName]
0x1400042b1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400042b6  mov     [rbp+var_28], r14
0x1400042ba  mov     word ptr [rbp+lpLibFileName], r14w
0x1400042bf  cmp     [rbp+pperrinfo], r14
0x1400042c3  jmp     short loc_1400042FF
0x1400042c5  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1400042c9  xor     ecx, ecx; dwReserved
0x1400042cb  call    SetErrorInfo_0
0x1400042d0  mov     [rsi], ebx
0x1400042d2  mov     rdx, [rbp+var_20]
0x1400042d6  cmp     rdx, 7
0x1400042da  jbe     short loc_1400042ED
0x1400042dc  lea     rdx, ds:2[rdx*2]
0x1400042e4  mov     rcx, [rbp+lpLibFileName]
0x1400042e8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400042ed  mov     [rbp+var_28], 0
0x1400042f5  xor     eax, eax
0x1400042f7  mov     word ptr [rbp+lpLibFileName], ax
0x1400042fb  cmp     [rbp+pperrinfo], rax
0x1400042ff  mov     [rbp+var_20], 7
0x140004307  jz      short loc_140004312
0x140004309  lea     rcx, [rbp+pperrinfo]
0x14000430d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140004312  mov     rax, rsi
0x140004315  mov     rcx, [rbp+var_18]
0x140004319  xor     rcx, rsp; StackCookie
0x14000431c  call    __security_check_cookie
0x140004321  add     rsp, 68h
0x140004325  pop     r15
0x140004327  pop     r14
0x140004329  pop     r13
0x14000432b  pop     r12
0x14000432d  pop     rdi
0x14000432e  pop     rsi
0x14000432f  pop     rbx
0x140004330  pop     rbp
0x140004331  retn
```
