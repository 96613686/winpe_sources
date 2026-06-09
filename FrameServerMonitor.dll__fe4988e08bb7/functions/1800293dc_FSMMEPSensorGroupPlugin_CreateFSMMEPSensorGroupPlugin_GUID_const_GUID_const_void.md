# FSMMEPSensorGroupPlugin::CreateFSMMEPSensorGroupPlugin(_GUID const &,_GUID const &,void * *)

- ea: `0x1800293dc`
- end: `0x180029535`
- name: `?CreateFSMMEPSensorGroupPlugin@FSMMEPSensorGroupPlugin@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `345`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011c20`

## callees

- `0x18000261c`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d4f8`
- `0x1800293dc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029450`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029450`

## pseudocode

```c
__int64 __fastcall FSMMEPSensorGroupPlugin::CreateFSMMEPSensorGroupPlugin(
        const struct _GUID *a1,
        const struct _GUID *a2,
        void **a3)
{
  int v5; // ebx
  int v6; // r8d
  __int64 v7; // rdx
  char *v8; // rdi
  __int64 v9; // rax
  char *v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = 0;
  if ( a3 )
  {
    *a3 = 0;
    v8 = (char *)operator new(0x48u);
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 1;
      *(_QWORD *)v8 = &FSMMEPSensorGroupPlugin::`vftable';
      InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
      *(GUID *)(v8 + 56) = GUID_00000000_0000_0000_0000_000000000000;
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids, v8);
      v9 = *(_QWORD *)v8;
      v11 = v8;
      v5 = (*(__int64 (__fastcall **)(char *, const struct _GUID *))(v9 + 56))(v8, a1);
      if ( v5 >= 0 )
      {
        v5 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))v8)(
               v8,
               &GUID_29fa81ab_e0f7_4abc_b00f_fb2e520b4595,
               a3);
        if ( v5 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 13;
          goto LABEL_15;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 12;
        goto LABEL_15;
      }
    }
    else
    {
      v5 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 11;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v5 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = (unsigned int)(v6 + 10);
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids, 0, v5);
    }
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800293dc  mov     rax, rsp
0x1800293df  mov     [rax+8], rbx
0x1800293e3  mov     [rax+18h], rsi
0x1800293e7  mov     [rax+10h], rdx
0x1800293eb  push    rdi
0x1800293ec  sub     rsp, 30h
0x1800293f0  mov     qword ptr [rax+10h], 0
0x1800293f8  mov     rsi, r8
0x1800293fb  mov     rbx, rcx
0x1800293fe  test    r8, r8
0x180029401  jnz     short loc_18002941E
0x180029403  mov     ebx, 80004003h
0x180029408  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002940d  cmp     al, 1
0x18002940f  jb      loc_180029519
0x180029415  lea     edx, [r8+0Ah]
0x180029419  jmp     loc_1800294FB
0x18002941e  mov     ecx, 48h ; 'H'; Size
0x180029423  mov     qword ptr [r8], 0
0x18002942a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002942f  mov     rdi, rax
0x180029432  test    rax, rax
0x180029435  jz      loc_1800294E8
0x18002943b  lea     rax, ??_7FSMMEPSensorGroupPlugin@@6B@; const FSMMEPSensorGroupPlugin::`vftable'
0x180029442  mov     dword ptr [rdi+8], 1
0x180029449  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002944d  mov     [rdi], rax
0x180029450  call    cs:__imp_InitializeCriticalSection
0x180029456  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002945d  movdqu  xmmword ptr [rdi+38h], xmm0
0x180029462  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180029467  cmp     al, 10h
0x180029469  jb      short loc_18002948D
0x18002946b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029472  lea     r8, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids
0x180029479  mov     edx, 0Eh
0x18002947e  mov     r9, rdi
0x180029481  mov     rcx, [rcx+0D8h]
0x180029488  call    WPP_SF_q
0x18002948d  mov     rax, [rdi]
0x180029490  mov     rdx, rbx
0x180029493  mov     rcx, rdi
0x180029496  mov     [rsp+38h+arg_8], rdi
0x18002949b  mov     rax, [rax+38h]
0x18002949f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294a4  mov     ebx, eax
0x1800294a6  test    eax, eax
0x1800294a8  jns     short loc_1800294BA
0x1800294aa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800294af  cmp     al, 1
0x1800294b1  jb      short loc_180029519
0x1800294b3  mov     edx, 0Ch
0x1800294b8  jmp     short loc_1800294FB
0x1800294ba  mov     rax, [rdi]
0x1800294bd  lea     rdx, _GUID_29fa81ab_e0f7_4abc_b00f_fb2e520b4595
0x1800294c4  mov     r8, rsi
0x1800294c7  mov     rcx, rdi
0x1800294ca  mov     rax, [rax]
0x1800294cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d2  mov     ebx, eax
0x1800294d4  test    eax, eax
0x1800294d6  jns     short loc_180029519
0x1800294d8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800294dd  cmp     al, 1
0x1800294df  jb      short loc_180029519
0x1800294e1  mov     edx, 0Dh
0x1800294e6  jmp     short loc_1800294FB
0x1800294e8  mov     ebx, 8007000Eh
0x1800294ed  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800294f2  cmp     al, 1
0x1800294f4  jb      short loc_180029519
0x1800294f6  mov     edx, 0Bh
0x1800294fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180029502  lea     r8, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids
0x180029509  xor     r9d, r9d
0x18002950c  mov     [rsp+38h+var_18], ebx
0x180029510  mov     rcx, [rcx+10h]
0x180029514  call    WPP_SF_qD
0x180029519  lea     rcx, [rsp+38h+arg_8]
0x18002951e  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180029523  mov     rsi, [rsp+38h+arg_10]
0x180029528  mov     eax, ebx
0x18002952a  mov     rbx, [rsp+38h+arg_0]
0x18002952f  add     rsp, 30h
0x180029533  pop     rdi
0x180029534  retn
```
